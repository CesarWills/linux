#
# Makefile for the Linux nfs filesystem routines.
#

obj-$(CONFIG_NFS_FS) += nfs.o

nfs-y 			:= client.o dir.o file.o getroot.o inode.o super.o \
			   direct.o pagelist.o read.o symlink.o unlink.o \
			   write.o namespace.o mount_clnt.o \
			   dns_resolve.o cache_lib.o
nfs-$(CONFIG_ROOT_NFS)	+= nfsroot.o
nfs-$(CONFIG_NFS_V2)	+= proc.o nfs2xdr.o
nfs-$(CONFIG_NFS_V3)	+= nfs3proc.o nfs3xdr.o
nfs-$(CONFIG_NFS_V3_ACL)	+= nfs3acl.o
nfs-$(CONFIG_NFS_V4)	+= nfs4proc.o nfs4xdr.o nfs4state.o nfs4renewd.o \
			   nfs4super.o nfs4file.o delegation.o idmap.o \
			   callback.o callback_xdr.o callback_proc.o \
			   nfs4namespace.o nfs4getroot.o nfs4client.o
nfs-$(CONFIG_NFS_V4_1)	+= pnfs.o pnfs_dev.o

ifeq ($(CONFIG_SYSCTL), y)
nfs-y += sysctl.o
nfs-$(CONFIG_NFS_V4) += nfs4sysctl.o
endif

nfs-$(CONFIG_NFS_FSCACHE) += fscache.o fscache-index.o

obj-$(CONFIG_PNFS_FILE_LAYOUT) += nfs_layout_nfsv41_files.o
nfs_layout_nfsv41_files-y := nfs4filelayout.o nfs4filelayoutdev.o

obj-$(CONFIG_PNFS_OBJLAYOUT) += objlayout/
obj-$(CONFIG_PNFS_BLOCK) += blocklayout/
