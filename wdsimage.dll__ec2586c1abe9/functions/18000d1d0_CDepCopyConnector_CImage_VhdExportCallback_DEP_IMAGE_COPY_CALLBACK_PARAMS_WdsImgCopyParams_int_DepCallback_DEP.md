# CDepCopyConnector<&CImage::VhdExportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_DepCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,void *,int *)

- ea: `0x18000d1d0`
- end: `0x18000d1e4`
- name: `?_DepCallback@?$CDepCopyConnector@$1?VhdExportCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z@@SAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAXPEAH@Z`
- size: `20`
- prototype: `__int64 __fastcall(struct _DEP_IMAGE_COPY_CALLBACK_PARAMS *, struct WdsImgCopyParams *, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c46c`

## pseudocode

```c
__int64 __fastcall CDepCopyConnector<&public: long CImage::VhdExportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_DepCallback(
        struct _DEP_IMAGE_COPY_CALLBACK_PARAMS *a1,
        CImage **a2,
        int *a3)
{
  return CImage::VhdExportCallback(*a2, a1, (struct WdsImgCopyParams *)a2, a3);
}

```

## disassembly

```asm
0x18000d1d0  mov     rax, rdx
0x18000d1d3  mov     r9, r8; int *
0x18000d1d6  mov     r8, rdx; struct WdsImgCopyParams *
0x18000d1d9  mov     rdx, rcx; struct _DEP_IMAGE_COPY_CALLBACK_PARAMS *
0x18000d1dc  mov     rcx, [rax]; this
0x18000d1df  jmp     ?VhdExportCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z; CImage::VhdExportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)
```
