# TLoad64BitDllsMgr::QueryInterface(_GUID const &,void * *)

- ea: `0x140007a9c`
- end: `0x140007cf9`
- name: `?QueryInterface@TLoad64BitDllsMgr@@QEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `605`
- prototype: `__int64 __fastcall(TLoad64BitDllsMgr *__hidden this, const struct _GUID *, void **)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14000cca0`
- `0x14000d9e0`
- `0x14000ddd0`
- `0x14000dfe0`
- `0x14000e110`
- `0x14000e290`
- `0x14000e3c0`
- `0x14000e530`
- `0x14000e6a0`

## callees

- `0x140001b50`
- `0x140007a9c`
- `0x140010400`
- `0x140016010`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::QueryInterface(TLoad64BitDllsMgr *this, const struct _GUID *a2, TLPCMgr **a3)
{
  unsigned int v5; // esi
  char *v6; // rax
  _QWORD *v7; // rdi
  _BYTE *v8; // r8
  __int64 v9; // rdx
  const char *v10; // rax
  __int64 v11; // rcx
  _BYTE *v12; // rax
  char *v13; // rax
  _BYTE *v14; // r8
  const char *v15; // rax
  __int64 v16; // rcx
  _BYTE *v17; // rax
  char *v18; // rax
  _BYTE *v19; // r8
  const char *v20; // rax
  __int64 v21; // rcx
  _BYTE *v22; // rax
  TLPCMgr *v23; // rax

  if ( !a3 )
    return (unsigned int)-2147024809;
  v5 = 0;
  *a3 = 0;
  if ( *(_OWORD *)a2 == *(_OWORD *)&IID_PRINTEREVENT )
  {
    v6 = (char *)operator new(0x40u);
    v7 = v6;
    if ( v6 )
    {
      v8 = v6 + 24;
      *(_OWORD *)(v6 + 24) = 0;
      v9 = 2147483646;
      v10 = "TPrinterEventMgr";
      *((_OWORD *)v8 + 1) = 0;
      v11 = 32;
      do
      {
        if ( !v9 )
          break;
        if ( !*v10 )
          break;
        *v8++ = *v10++;
        --v9;
        --v11;
      }
      while ( v11 );
      v12 = v8 - 1;
      if ( v11 )
        v12 = v8;
      *v12 = 0;
      *v7 = &TPrinterEventMgr::`vftable'{for `TRefCntMgr'};
      v7[2] = &TPrinterEventMgr::`vftable'{for `TPrinterDriver'};
      *((_DWORD *)v7 + 2) = 0;
      v7[7] = this;
      goto LABEL_33;
    }
LABEL_34:
    v7 = 0;
    goto LABEL_35;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_PRINTUIOPERATIONS.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_PRINTUIOPERATIONS.Data4 )
  {
    v13 = (char *)operator new(0x38u);
    v7 = v13;
    if ( !v13 )
      goto LABEL_34;
    v14 = v13 + 16;
    *((_OWORD *)v13 + 1) = 0;
    v9 = 2147483646;
    v15 = "TPrintUIMgr";
    *((_OWORD *)v14 + 1) = 0;
    v16 = 32;
    do
    {
      if ( !v9 )
        break;
      if ( !*v15 )
        break;
      *v14++ = *v15++;
      --v9;
      --v16;
    }
    while ( v16 );
    v17 = v14 - 1;
    if ( v16 )
      v17 = v14;
    *v17 = 0;
  }
  else
  {
    if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_PRINTERCONFIGURATION.Data1
      || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_PRINTERCONFIGURATION.Data4 )
    {
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_LPCMGR.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_LPCMGR.Data4 )
      {
        v23 = (TLPCMgr *)operator new(0x190u);
        if ( v23 )
          v23 = TLPCMgr::TLPCMgr(v23, this);
        *a3 = v23;
      }
      else
      {
        v5 = -2147467262;
      }
      goto LABEL_42;
    }
    v18 = (char *)operator new(0x38u);
    v7 = v18;
    if ( !v18 )
      goto LABEL_34;
    v19 = v18 + 16;
    *((_OWORD *)v18 + 1) = 0;
    v9 = 2147483646;
    v20 = "TPrinterCfgMgr";
    *((_OWORD *)v19 + 1) = 0;
    v21 = 32;
    do
    {
      if ( !v9 )
        break;
      if ( !*v20 )
        break;
      *v19++ = *v20++;
      --v9;
      --v21;
    }
    while ( v21 );
    v22 = v19 - 1;
    if ( v21 )
      v22 = v19;
    *v22 = 0;
  }
  *((_DWORD *)v7 + 2) = 0;
  *v7 = &TPrinterCfgMgr::`vftable';
  v7[6] = this;
LABEL_33:
  (*(void (__fastcall **)(TLoad64BitDllsMgr *, __int64))(*(_QWORD *)this + 8LL))(this, v9);
LABEL_35:
  *a3 = (TLPCMgr *)v7;
LABEL_42:
  if ( *a3 )
    (*(void (__fastcall **)(TLPCMgr *))(*(_QWORD *)*a3 + 8LL))(*a3);
  else
    return (unsigned int)-2147024882;
  return v5;
}

```

## disassembly

```asm
0x140007a9c  push    rbx
0x140007a9e  push    rsi
0x140007a9f  push    rdi
0x140007aa0  push    r14
0x140007aa2  sub     rsp, 28h
0x140007aa6  mov     rbx, r8
0x140007aa9  mov     r14, rcx
0x140007aac  test    r8, r8
0x140007aaf  jnz     short loc_140007ABB
0x140007ab1  mov     esi, 80070057h
0x140007ab6  jmp     loc_140007CED
0x140007abb  xor     esi, esi
0x140007abd  mov     [r8], rsi
0x140007ac0  mov     rax, [rdx]
0x140007ac3  cmp     rax, qword ptr cs:?IID_PRINTEREVENT@@3U_GUID@@A.Data1; _GUID IID_PRINTEREVENT ...
0x140007aca  jnz     loc_140007B62
0x140007ad0  mov     rax, [rdx+8]
0x140007ad4  cmp     rax, qword ptr cs:?IID_PRINTEREVENT@@3U_GUID@@A.Data4; _GUID IID_PRINTEREVENT ...
0x140007adb  jnz     loc_140007B62
0x140007ae1  lea     ecx, [rsi+40h]; Size
0x140007ae4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007ae9  mov     rdi, rax
0x140007aec  test    rax, rax
0x140007aef  jz      loc_140007C8E
0x140007af5  lea     r8, [rax+18h]
0x140007af9  xorps   xmm0, xmm0
0x140007afc  movups  xmmword ptr [r8], xmm0
0x140007b00  mov     edx, 7FFFFFFEh
0x140007b05  lea     rax, aTprintereventm_2; "TPrinterEventMgr"
0x140007b0c  movups  xmmword ptr [r8+10h], xmm0
0x140007b11  lea     ecx, [rsi+20h]
0x140007b14  test    rdx, rdx
0x140007b17  jz      short loc_140007B33
0x140007b19  mov     r9b, [rax]
0x140007b1c  test    r9b, r9b
0x140007b1f  jz      short loc_140007B33
0x140007b21  mov     [r8], r9b
0x140007b24  inc     rax
0x140007b27  inc     r8
0x140007b2a  dec     rdx
0x140007b2d  sub     rcx, 1
0x140007b31  jnz     short loc_140007B14
0x140007b33  test    rcx, rcx
0x140007b36  lea     rax, [r8-1]
0x140007b3a  cmovnz  rax, r8
0x140007b3e  mov     [rax], sil
0x140007b41  lea     rax, ??_7TPrinterEventMgr@@6BTRefCntMgr@@@; const TPrinterEventMgr::`vftable'{for `TRefCntMgr'}
0x140007b48  mov     [rdi], rax
0x140007b4b  lea     rax, ??_7TPrinterEventMgr@@6BTPrinterDriver@@@; const TPrinterEventMgr::`vftable'{for `TPrinterDriver'}
0x140007b52  mov     [rdi+10h], rax
0x140007b56  mov     [rdi+8], esi
0x140007b59  mov     [rdi+38h], r14
0x140007b5d  jmp     loc_140007C7D
0x140007b62  mov     rax, [rdx]
0x140007b65  cmp     rax, qword ptr cs:?IID_PRINTUIOPERATIONS@@3U_GUID@@A.Data1; _GUID IID_PRINTUIOPERATIONS ...
0x140007b6c  jnz     short loc_140007BEB
0x140007b6e  mov     rax, [rdx+8]
0x140007b72  cmp     rax, qword ptr cs:?IID_PRINTUIOPERATIONS@@3U_GUID@@A.Data4; _GUID IID_PRINTUIOPERATIONS ...
0x140007b79  jnz     short loc_140007BEB
0x140007b7b  mov     ecx, 38h ; '8'; Size
0x140007b80  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007b85  mov     rdi, rax
0x140007b88  test    rax, rax
0x140007b8b  jz      loc_140007C8E
0x140007b91  lea     r8, [rax+10h]
0x140007b95  xorps   xmm0, xmm0
0x140007b98  movups  xmmword ptr [r8], xmm0
0x140007b9c  mov     edx, 7FFFFFFEh
0x140007ba1  lea     rax, aTprintuimgr; "TPrintUIMgr"
0x140007ba8  movups  xmmword ptr [r8+10h], xmm0
0x140007bad  mov     ecx, 20h ; ' '
0x140007bb2  test    rdx, rdx
0x140007bb5  jz      short loc_140007BD1
0x140007bb7  mov     r9b, [rax]
0x140007bba  test    r9b, r9b
0x140007bbd  jz      short loc_140007BD1
0x140007bbf  mov     [r8], r9b
0x140007bc2  inc     rax
0x140007bc5  inc     r8
0x140007bc8  dec     rdx
0x140007bcb  sub     rcx, 1
0x140007bcf  jnz     short loc_140007BB2
0x140007bd1  test    rcx, rcx
0x140007bd4  lea     rax, [r8-1]
0x140007bd8  cmovnz  rax, r8
0x140007bdc  mov     [rax], sil
0x140007bdf  lea     rax, ??_7TPrinterCfgMgr@@6B@; const TPrinterCfgMgr::`vftable'
0x140007be6  jmp     loc_140007C73
0x140007beb  mov     rax, [rdx]
0x140007bee  cmp     rax, qword ptr cs:?IID_PRINTERCONFIGURATION@@3U_GUID@@A.Data1; _GUID IID_PRINTERCONFIGURATION ...
0x140007bf5  jnz     loc_140007C95
0x140007bfb  mov     rax, [rdx+8]
0x140007bff  cmp     rax, qword ptr cs:?IID_PRINTERCONFIGURATION@@3U_GUID@@A.Data4; _GUID IID_PRINTERCONFIGURATION ...
0x140007c06  jnz     loc_140007C95
0x140007c0c  mov     ecx, 38h ; '8'; Size
0x140007c11  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007c16  mov     rdi, rax
0x140007c19  test    rax, rax
0x140007c1c  jz      short loc_140007C8E
0x140007c1e  lea     r8, [rax+10h]
0x140007c22  xorps   xmm0, xmm0
0x140007c25  movups  xmmword ptr [r8], xmm0
0x140007c29  mov     edx, 7FFFFFFEh
0x140007c2e  lea     rax, aTprintercfgmgr_0; "TPrinterCfgMgr"
0x140007c35  movups  xmmword ptr [r8+10h], xmm0
0x140007c3a  mov     ecx, 20h ; ' '
0x140007c3f  test    rdx, rdx
0x140007c42  jz      short loc_140007C5E
0x140007c44  mov     r9b, [rax]
0x140007c47  test    r9b, r9b
0x140007c4a  jz      short loc_140007C5E
0x140007c4c  mov     [r8], r9b
0x140007c4f  inc     rax
0x140007c52  inc     r8
0x140007c55  dec     rdx
0x140007c58  sub     rcx, 1
0x140007c5c  jnz     short loc_140007C3F
0x140007c5e  test    rcx, rcx
0x140007c61  lea     rax, [r8-1]
0x140007c65  cmovnz  rax, r8
0x140007c69  mov     [rax], sil
0x140007c6c  lea     rax, ??_7TPrinterCfgMgr@@6B@; const TPrinterCfgMgr::`vftable'
0x140007c73  mov     [rdi+8], esi
0x140007c76  mov     [rdi], rax
0x140007c79  mov     [rdi+30h], r14
0x140007c7d  mov     rax, [r14]
0x140007c80  mov     rcx, r14
0x140007c83  mov     rax, [rax+8]
0x140007c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007c8c  jmp     short loc_140007C90
0x140007c8e  xor     edi, edi
0x140007c90  mov     [rbx], rdi
0x140007c93  jmp     short loc_140007CD2
0x140007c95  mov     rax, [rdx]
0x140007c98  cmp     rax, qword ptr cs:?IID_LPCMGR@@3U_GUID@@A.Data1; _GUID IID_LPCMGR ...
0x140007c9f  jnz     short loc_140007CCD
0x140007ca1  mov     rax, [rdx+8]
0x140007ca5  cmp     rax, qword ptr cs:?IID_LPCMGR@@3U_GUID@@A.Data4; _GUID IID_LPCMGR ...
0x140007cac  jnz     short loc_140007CCD
0x140007cae  mov     ecx, 190h; Size
0x140007cb3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007cb8  test    rax, rax
0x140007cbb  jz      short loc_140007CC8
0x140007cbd  mov     rdx, r14; struct TLoad64BitDllsMgr *
0x140007cc0  mov     rcx, rax; this
0x140007cc3  call    ??0TLPCMgr@@QEAA@PEAVTLoad64BitDllsMgr@@@Z; TLPCMgr::TLPCMgr(TLoad64BitDllsMgr *)
0x140007cc8  mov     [rbx], rax
0x140007ccb  jmp     short loc_140007CD2
0x140007ccd  mov     esi, 80004002h
0x140007cd2  mov     rcx, [rbx]
0x140007cd5  test    rcx, rcx
0x140007cd8  jz      short loc_140007CE8
0x140007cda  mov     rax, [rcx]
0x140007cdd  mov     rax, [rax+8]
0x140007ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ce6  jmp     short loc_140007CED
0x140007ce8  mov     esi, 8007000Eh
0x140007ced  mov     eax, esi
0x140007cef  add     rsp, 28h
0x140007cf3  pop     r14
0x140007cf5  pop     rdi
0x140007cf6  pop     rsi
0x140007cf7  pop     rbx
0x140007cf8  retn
```
