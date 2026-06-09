# CImage::VhdExport(WdsImgCopyParams *,ulong *)

- ea: `0x18000c35c`
- end: `0x18000c466`
- name: `?VhdExport@CImage@@AEAAJPEAUWdsImgCopyParams@@PEAK@Z`
- size: `266`
- prototype: `int(CImage *__hidden this, struct WdsImgCopyParams *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009cb4`

## callees

- `0x180009c30`
- `0x18000c2d8`
- `0x18000c35c`
- `0x18000d5b0`
- `0x180011010`

## string_xrefs

- `0x18000c3c7`: `base\eco\wds\wdsimage\src\DepCopyConnector.h`
- `0x18000c3fc`: `base\eco\wds\wdsimage\src\DepCopyConnector.h`
- `0x18000c41e`: `base\eco\wds\wdsimage\src\DepCopyConnector.h`

## pseudocode

```c
__int64 __fastcall CImage::VhdExport(CImage *this, struct WdsImgCopyParams *a2, unsigned int *a3)
{
  bool v5; // zf
  __int64 v6; // r14
  __int64 started; // rbx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  _QWORD v13[8]; // [rsp+30h] [rbp-48h] BYREF

  v13[0] = 0;
  v13[1] = 0;
  v13[6] = 0;
  v5 = (*((_BYTE *)a2 + 24) & 1) == 0;
  v6 = *((_QWORD *)this + 49);
  v13[2] = CDepCopyConnector<&public: long CImage::VhdExportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_DepCallback;
  v13[4] = CDepCopyConnector<&public: long CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_ProgressCallback;
  *(_QWORD *)a2 = this;
  v13[3] = a2;
  v13[5] = a2;
  if ( !v5 )
    LODWORD(v13[0]) |= 2u;
  started = (unsigned int)CImage::StartOperationCallback(a2);
  if ( (int)ElValidateHr_5(started, v8, "base\\eco\\wds\\wdsimage\\src\\DepCopyConnector.h", 128) >= 0 )
  {
    LODWORD(started) = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, _QWORD))(*(_QWORD *)v6 + 16LL))(
                         v6,
                         *((_QWORD *)a2 + 1),
                         v13,
                         0);
    if ( (int)ElValidateHr_5((unsigned int)started, v10, "base\\eco\\wds\\wdsimage\\src\\DepCopyConnector.h", 137) >= 0 )
    {
      LODWORD(started) = CImage::EndOperationCallback(a2);
      ElValidateHr_5((unsigned int)started, v11, "base\\eco\\wds\\wdsimage\\src\\DepCopyConnector.h", 143);
    }
  }
  if ( (int)ElValidateHr_5((unsigned int)started, v9, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2995) >= 0 )
    *a3 = 1;
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000c35c  mov     r11, rsp
0x18000c35f  mov     [r11+8], rbx
0x18000c363  mov     [r11+10h], rsi
0x18000c367  mov     [r11+18h], rdi
0x18000c36b  push    r14
0x18000c36d  sub     rsp, 70h
0x18000c371  and     qword ptr [r11-48h], 0
0x18000c376  lea     rax, ?_DepCallback@?$CDepCopyConnector@$1?VhdExportCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z@@SAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAXPEAH@Z; CDepCopyConnector<&CImage::VhdExportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_DepCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,void *,int *)
0x18000c37d  and     qword ptr [r11-40h], 0
0x18000c382  mov     rsi, r8
0x18000c385  and     qword ptr [r11-18h], 0
0x18000c38a  mov     rdi, rdx
0x18000c38d  test    byte ptr [rdx+18h], 1
0x18000c391  mov     r14, [rcx+188h]
0x18000c398  mov     [r11-38h], rax
0x18000c39c  lea     rax, ?_ProgressCallback@?$CDepCopyConnector@$1?VhdImportCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z@@SAKT_LARGE_INTEGER@@000KKPEAX11@Z; CDepCopyConnector<&CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_ProgressCallback(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *)
0x18000c3a3  mov     [r11-28h], rax
0x18000c3a7  mov     [rdx], rcx
0x18000c3aa  mov     [r11-30h], rdx
0x18000c3ae  mov     [r11-20h], rdx
0x18000c3b2  jz      short loc_18000C3B9
0x18000c3b4  or      dword ptr [rsp+78h+var_48], 2
0x18000c3b9  mov     rcx, rdi; struct WdsImgCopyParams *
0x18000c3bc  call    ?StartOperationCallback@CImage@@SAJPEAUWdsImgCopyParams@@@Z; CImage::StartOperationCallback(WdsImgCopyParams *)
0x18000c3c1  mov     r9d, 80h
0x18000c3c7  lea     r8, aBaseEcoWdsWdsi_0; "base\\eco\\wds\\wdsimage\\src\\DepCopyC"...
0x18000c3ce  mov     ecx, eax
0x18000c3d0  mov     ebx, eax
0x18000c3d2  call    ElValidateHr_5
0x18000c3d7  test    eax, eax
0x18000c3d9  js      short loc_18000C42E
0x18000c3db  mov     rax, [r14]
0x18000c3de  lea     r8, [rsp+78h+var_48]
0x18000c3e3  mov     rdx, [rdi+8]
0x18000c3e7  xor     r9d, r9d
0x18000c3ea  mov     rcx, r14
0x18000c3ed  mov     rax, [rax+10h]
0x18000c3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3f6  mov     r9d, 89h
0x18000c3fc  lea     r8, aBaseEcoWdsWdsi_0; "base\\eco\\wds\\wdsimage\\src\\DepCopyC"...
0x18000c403  mov     ecx, eax
0x18000c405  mov     ebx, eax
0x18000c407  call    ElValidateHr_5
0x18000c40c  test    eax, eax
0x18000c40e  js      short loc_18000C42E
0x18000c410  mov     rcx, rdi; struct WdsImgCopyParams *
0x18000c413  call    ?EndOperationCallback@CImage@@SAJPEAUWdsImgCopyParams@@@Z; CImage::EndOperationCallback(WdsImgCopyParams *)
0x18000c418  mov     r9d, 8Fh
0x18000c41e  lea     r8, aBaseEcoWdsWdsi_0; "base\\eco\\wds\\wdsimage\\src\\DepCopyC"...
0x18000c425  mov     ecx, eax
0x18000c427  mov     ebx, eax
0x18000c429  call    ElValidateHr_5
0x18000c42e  mov     r9d, 0BB3h
0x18000c434  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000c43b  mov     ecx, ebx
0x18000c43d  call    ElValidateHr_5
0x18000c442  test    eax, eax
0x18000c444  js      short loc_18000C44C
0x18000c446  mov     dword ptr [rsi], 1
0x18000c44c  lea     r11, [rsp+78h+var_8]
0x18000c451  mov     eax, ebx
0x18000c453  mov     rbx, [r11+10h]
0x18000c457  mov     rsi, [r11+18h]
0x18000c45b  mov     rdi, [r11+20h]
0x18000c45f  mov     rsp, r11
0x18000c462  pop     r14
0x18000c464  retn
```
