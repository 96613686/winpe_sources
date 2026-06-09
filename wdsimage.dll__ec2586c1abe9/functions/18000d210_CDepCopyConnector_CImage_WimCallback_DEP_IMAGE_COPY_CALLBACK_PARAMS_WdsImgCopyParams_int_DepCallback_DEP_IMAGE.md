# CDepCopyConnector<&CImage::WimCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_DepCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,void *,int *)

- ea: `0x18000d210`
- end: `0x18000d224`
- name: `?_DepCallback@?$CDepCopyConnector@$1?WimCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z@@SAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAXPEAH@Z`
- size: `20`
- prototype: `__int64 __fastcall(struct _DEP_IMAGE_COPY_CALLBACK_PARAMS *, struct WdsImgCopyParams *, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ce00`

## pseudocode

```c
__int64 __fastcall CDepCopyConnector<&public: long CImage::WimCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_DepCallback(
        struct _DEP_IMAGE_COPY_CALLBACK_PARAMS *a1,
        CImage **a2,
        int *a3)
{
  return CImage::WimCallback(*a2, a1, (struct WdsImgCopyParams *)a2, a3);
}

```

## disassembly

```asm
0x18000d210  mov     rax, rdx
0x18000d213  mov     r9, r8; int *
0x18000d216  mov     r8, rdx; struct WdsImgCopyParams *
0x18000d219  mov     rdx, rcx; struct _DEP_IMAGE_COPY_CALLBACK_PARAMS *
0x18000d21c  mov     rcx, [rax]; this
0x18000d21f  jmp     ?WimCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z; CImage::WimCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)
```
