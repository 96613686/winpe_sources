# CDepCopyConnector<&CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::Copy(CImage *,IDepImageResolved *,WdsImgCopyParams *,_DEP_IMAGE_COPY_PARAMS *,IDepImage * *)

- ea: `0x1800092fc`
- end: `0x1800093d2`
- name: `?Copy@?$CDepCopyConnector@$1?VhdImportCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z@@SAJPEAVCImage@@PEAVIDepImageResolved@@PEAUWdsImgCopyParams@@PEAU_DEP_IMAGE_COPY_PARAMS@@PEAPEAVIDepImage@@@Z`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000c77c`

## callees

- `0x1800092fc`
- `0x180009c30`
- `0x18000c2d8`
- `0x18000d5b0`
- `0x180011010`

## string_xrefs

- `0x180009354`: `base\eco\wds\wdsimage\src\DepCopyConnector.h`
- `0x180009387`: `base\eco\wds\wdsimage\src\DepCopyConnector.h`
- `0x1800093a9`: `base\eco\wds\wdsimage\src\DepCopyConnector.h`

## pseudocode

```c
__int64 __fastcall CDepCopyConnector<&public: long CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::Copy(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 started; // rsi
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx

  *(_QWORD *)a3 = a1;
  *(_QWORD *)(a4 + 16) = CDepCopyConnector<&public: long CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_DepCallback;
  *(_QWORD *)(a4 + 24) = a3;
  *(_QWORD *)(a4 + 32) = CDepCopyConnector<&public: long CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_ProgressCallback;
  *(_QWORD *)(a4 + 40) = a3;
  if ( (*(_BYTE *)(a3 + 24) & 1) != 0 )
    *(_DWORD *)a4 |= 2u;
  started = (unsigned int)CImage::StartOperationCallback((struct WdsImgCopyParams *)a3);
  if ( (int)ElValidateHr_5(started, v8, "base\\eco\\wds\\wdsimage\\src\\DepCopyConnector.h", 128) >= 0 )
  {
    LODWORD(started) = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
                         a2,
                         *(_QWORD *)(a3 + 8),
                         a4,
                         0);
    if ( (int)ElValidateHr_5((unsigned int)started, v9, "base\\eco\\wds\\wdsimage\\src\\DepCopyConnector.h", 137) >= 0 )
    {
      LODWORD(started) = CImage::EndOperationCallback((struct WdsImgCopyParams *)a3);
      ElValidateHr_5((unsigned int)started, v10, "base\\eco\\wds\\wdsimage\\src\\DepCopyConnector.h", 143);
    }
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800092fc  mov     [rsp+arg_0], rbx
0x180009301  mov     [rsp+arg_8], rsi
0x180009306  mov     [rsp+arg_10], rdi
0x18000930b  push    r14
0x18000930d  sub     rsp, 30h
0x180009311  mov     [r8], rcx
0x180009314  lea     rax, ?_DepCallback@?$CDepCopyConnector@$1?VhdImportCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z@@SAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAXPEAH@Z; CDepCopyConnector<&CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_DepCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,void *,int *)
0x18000931b  mov     [r9+10h], rax
0x18000931f  mov     rbx, r9
0x180009322  lea     rax, ?_ProgressCallback@?$CDepCopyConnector@$1?VhdImportCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z@@SAKT_LARGE_INTEGER@@000KKPEAX11@Z; CDepCopyConnector<&CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_ProgressCallback(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *)
0x180009329  mov     [r9+18h], r8
0x18000932d  mov     [r9+20h], rax
0x180009331  mov     rdi, r8
0x180009334  mov     [r9+28h], r8
0x180009338  mov     r14, rdx
0x18000933b  test    byte ptr [r8+18h], 1
0x180009340  jz      short loc_180009346
0x180009342  or      dword ptr [r9], 2
0x180009346  mov     rcx, rdi; struct WdsImgCopyParams *
0x180009349  call    ?StartOperationCallback@CImage@@SAJPEAUWdsImgCopyParams@@@Z; CImage::StartOperationCallback(WdsImgCopyParams *)
0x18000934e  mov     r9d, 80h
0x180009354  lea     r8, aBaseEcoWdsWdsi_0; "base\\eco\\wds\\wdsimage\\src\\DepCopyC"...
0x18000935b  mov     ecx, eax
0x18000935d  mov     esi, eax
0x18000935f  call    ElValidateHr_5
0x180009364  test    eax, eax
0x180009366  js      short loc_1800093B9
0x180009368  mov     rax, [r14]
0x18000936b  xor     r9d, r9d
0x18000936e  mov     rdx, [rdi+8]
0x180009372  mov     r8, rbx
0x180009375  mov     rcx, r14
0x180009378  mov     rax, [rax+10h]
0x18000937c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009381  mov     r9d, 89h
0x180009387  lea     r8, aBaseEcoWdsWdsi_0; "base\\eco\\wds\\wdsimage\\src\\DepCopyC"...
0x18000938e  mov     ecx, eax
0x180009390  mov     esi, eax
0x180009392  call    ElValidateHr_5
0x180009397  test    eax, eax
0x180009399  js      short loc_1800093B9
0x18000939b  mov     rcx, rdi; struct WdsImgCopyParams *
0x18000939e  call    ?EndOperationCallback@CImage@@SAJPEAUWdsImgCopyParams@@@Z; CImage::EndOperationCallback(WdsImgCopyParams *)
0x1800093a3  mov     r9d, 8Fh
0x1800093a9  lea     r8, aBaseEcoWdsWdsi_0; "base\\eco\\wds\\wdsimage\\src\\DepCopyC"...
0x1800093b0  mov     ecx, eax
0x1800093b2  mov     esi, eax
0x1800093b4  call    ElValidateHr_5
0x1800093b9  mov     rbx, [rsp+38h+arg_0]
0x1800093be  mov     eax, esi
0x1800093c0  mov     rsi, [rsp+38h+arg_8]
0x1800093c5  mov     rdi, [rsp+38h+arg_10]
0x1800093ca  add     rsp, 30h
0x1800093ce  pop     r14
0x1800093d0  retn
```
