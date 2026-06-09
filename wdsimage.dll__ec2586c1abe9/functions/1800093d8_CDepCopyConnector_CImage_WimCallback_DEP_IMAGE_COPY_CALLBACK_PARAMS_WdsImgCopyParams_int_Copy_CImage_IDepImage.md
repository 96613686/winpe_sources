# CDepCopyConnector<&CImage::WimCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::Copy(CImage *,IDepImageResolved *,WdsImgCopyParams *,_DEP_IMAGE_COPY_PARAMS *,IDepImage * *)

- ea: `0x1800093d8`
- end: `0x1800094b0`
- name: `?Copy@?$CDepCopyConnector@$1?WimCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z@@SAJPEAVCImage@@PEAVIDepImageResolved@@PEAUWdsImgCopyParams@@PEAU_DEP_IMAGE_COPY_PARAMS@@PEAPEAVIDepImage@@@Z`
- size: `216`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000cf80`
- `0x18000d0e8`

## callees

- `0x1800093d8`
- `0x180009c30`
- `0x18000c2d8`
- `0x18000d5b0`
- `0x180011010`

## string_xrefs

- `0x180009430`: `base\eco\wds\wdsimage\src\DepCopyConnector.h`
- `0x180009465`: `base\eco\wds\wdsimage\src\DepCopyConnector.h`
- `0x180009487`: `base\eco\wds\wdsimage\src\DepCopyConnector.h`

## pseudocode

```c
__int64 __fastcall CDepCopyConnector<&public: long CImage::WimCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::Copy(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 started; // rsi
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx

  *(_QWORD *)a3 = a1;
  *(_QWORD *)(a4 + 16) = CDepCopyConnector<&public: long CImage::WimCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_DepCallback;
  *(_QWORD *)(a4 + 24) = a3;
  *(_QWORD *)(a4 + 32) = CDepCopyConnector<&public: long CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_ProgressCallback;
  *(_QWORD *)(a4 + 40) = a3;
  if ( (*(_BYTE *)(a3 + 24) & 1) != 0 )
    *(_DWORD *)a4 |= 2u;
  started = (unsigned int)CImage::StartOperationCallback((struct WdsImgCopyParams *)a3);
  if ( (int)ElValidateHr_5(started, v9, "base\\eco\\wds\\wdsimage\\src\\DepCopyConnector.h", 128) >= 0 )
  {
    LODWORD(started) = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)a2 + 16LL))(
                         a2,
                         *(_QWORD *)(a3 + 8),
                         a4,
                         a5);
    if ( (int)ElValidateHr_5((unsigned int)started, v10, "base\\eco\\wds\\wdsimage\\src\\DepCopyConnector.h", 137) >= 0 )
    {
      LODWORD(started) = CImage::EndOperationCallback((struct WdsImgCopyParams *)a3);
      ElValidateHr_5((unsigned int)started, v11, "base\\eco\\wds\\wdsimage\\src\\DepCopyConnector.h", 143);
    }
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800093d8  mov     [rsp+arg_0], rbx
0x1800093dd  mov     [rsp+arg_8], rsi
0x1800093e2  mov     [rsp+arg_10], rdi
0x1800093e7  push    r14
0x1800093e9  sub     rsp, 30h
0x1800093ed  mov     [r8], rcx
0x1800093f0  lea     rax, ?_DepCallback@?$CDepCopyConnector@$1?WimCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z@@SAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAXPEAH@Z; CDepCopyConnector<&CImage::WimCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_DepCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,void *,int *)
0x1800093f7  mov     [r9+10h], rax
0x1800093fb  mov     rbx, r9
0x1800093fe  lea     rax, ?_ProgressCallback@?$CDepCopyConnector@$1?VhdImportCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z@@SAKT_LARGE_INTEGER@@000KKPEAX11@Z; CDepCopyConnector<&CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_ProgressCallback(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *)
0x180009405  mov     [r9+18h], r8
0x180009409  mov     [r9+20h], rax
0x18000940d  mov     rdi, r8
0x180009410  mov     [r9+28h], r8
0x180009414  mov     r14, rdx
0x180009417  test    byte ptr [r8+18h], 1
0x18000941c  jz      short loc_180009422
0x18000941e  or      dword ptr [r9], 2
0x180009422  mov     rcx, rdi; struct WdsImgCopyParams *
0x180009425  call    ?StartOperationCallback@CImage@@SAJPEAUWdsImgCopyParams@@@Z; CImage::StartOperationCallback(WdsImgCopyParams *)
0x18000942a  mov     r9d, 80h
0x180009430  lea     r8, aBaseEcoWdsWdsi_0; "base\\eco\\wds\\wdsimage\\src\\DepCopyC"...
0x180009437  mov     ecx, eax
0x180009439  mov     esi, eax
0x18000943b  call    ElValidateHr_5
0x180009440  test    eax, eax
0x180009442  js      short loc_180009497
0x180009444  mov     rax, [r14]
0x180009447  mov     r8, rbx
0x18000944a  mov     r9, [rsp+38h+arg_20]
0x18000944f  mov     rcx, r14
0x180009452  mov     rdx, [rdi+8]
0x180009456  mov     rax, [rax+10h]
0x18000945a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000945f  mov     r9d, 89h
0x180009465  lea     r8, aBaseEcoWdsWdsi_0; "base\\eco\\wds\\wdsimage\\src\\DepCopyC"...
0x18000946c  mov     ecx, eax
0x18000946e  mov     esi, eax
0x180009470  call    ElValidateHr_5
0x180009475  test    eax, eax
0x180009477  js      short loc_180009497
0x180009479  mov     rcx, rdi; struct WdsImgCopyParams *
0x18000947c  call    ?EndOperationCallback@CImage@@SAJPEAUWdsImgCopyParams@@@Z; CImage::EndOperationCallback(WdsImgCopyParams *)
0x180009481  mov     r9d, 8Fh
0x180009487  lea     r8, aBaseEcoWdsWdsi_0; "base\\eco\\wds\\wdsimage\\src\\DepCopyC"...
0x18000948e  mov     ecx, eax
0x180009490  mov     esi, eax
0x180009492  call    ElValidateHr_5
0x180009497  mov     rbx, [rsp+38h+arg_0]
0x18000949c  mov     eax, esi
0x18000949e  mov     rsi, [rsp+38h+arg_8]
0x1800094a3  mov     rdi, [rsp+38h+arg_10]
0x1800094a8  add     rsp, 30h
0x1800094ac  pop     r14
0x1800094ae  retn
```
