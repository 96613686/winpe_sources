# InitPropVariantFromStringEx

- ea: `0x1800340e8`
- end: `0x180034310`
- name: `InitPropVariantFromStringEx`
- size: `552`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d980`
- `0x180031a28`
- `0x180032ff0`

## callees

- `0x180012550`
- `0x180013042`
- `0x18002d034`
- `0x18002f2e4`
- `0x18002fad8`
- `0x18002fc50`
- `0x180030e6c`
- `0x180031644`
- `0x18003189c`
- `0x1800340e8`
- `0x180037010`

## import_xrefs

- `PROPSYS!PropVariantChangeType` at `0x180034242`
- `PROPSYS!PropVariantChangeType` at `0x180034242`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180034282`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180034282`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003424f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003424f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003420c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003420c`

## pseudocode

```c
__int64 __fastcall InitPropVariantFromStringEx(unsigned __int16 *a1, VARTYPE a2, struct tagPROPVARIANT *a3)
{
  __int64 v6; // rdx
  HRESULT inited; // eax
  HRESULT v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rbx
  void *v11; // rax
  __int64 v12; // rdx
  IStream *v13; // rax
  __int64 v14; // rcx
  IStream *v15; // r14
  GUID *v17; // rdx
  PROPVARIANT propvarSrc[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v19; // [rsp+40h] [rbp-48h]

  switch ( a2 )
  {
    case 0x1Fu:
      v6 = -1;
      do
        ++v6;
      while ( a1[v6] );
      inited = _AllocStringWorker<CTCoAllocPolicy>(a1, v6, a1);
      goto LABEL_25;
    case 8u:
      inited = SHSysAllocString(a1, &a3->bstrVal);
LABEL_25:
      v8 = inited;
      goto LABEL_35;
    case 0x101Fu:
      inited = _InitPropVariantFromParsedString(a1, a3);
      goto LABEL_25;
    case 0x1011u:
      inited = _InitPropVariantFromParsedUI1String(a1, (PROPVARIANT *)a3);
      goto LABEL_25;
    case 0x1Eu:
      inited = _DupWideToAnsi(a1, &a3->pszVal);
      goto LABEL_25;
  }
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  v8 = -2147024809;
  if ( !*a1 )
    goto LABEL_28;
  if ( a2 != 13 )
  {
    if ( a2 == 65 )
    {
      v12 = -1;
      do
        ++v12;
      while ( a1[v12] );
      inited = TextToBlob2(a1, v12, &a3->blob);
      goto LABEL_25;
    }
    if ( a2 != 66 && a2 != 68 )
    {
      *(_OWORD *)propvarSrc = 0;
      v19 = 0;
      v9 = -1;
      do
        ++v9;
      while ( a1[v9] );
      v10 = 2 * v9 + 2;
      v11 = CoTaskMemAlloc(v10);
      propvarSrc[1] = v11;
      if ( v11 )
      {
        memcpy_s(v11, v10, a1, v10);
        LOWORD(propvarSrc[0]) = 31;
        v8 = PropVariantChangeType((PROPVARIANT *)a3, propvarSrc, 0, a2);
        PropVariantClear(propvarSrc);
        goto LABEL_35;
      }
LABEL_27:
      v8 = -2147024882;
      goto LABEL_28;
    }
  }
  v13 = SHCreateMemStream(0, 0x400u);
  v15 = v13;
  if ( !v13 )
    goto LABEL_27;
  v8 = TextToBinary(v14, a1, v13);
  if ( v8 >= 0 )
  {
    v17 = &GUID_00000000_0000_0000_c000_000000000046;
    if ( a2 != 13 )
      v17 = &GUID_0000000c_0000_0000_c000_000000000046;
    v8 = (**(__int64 (__fastcall ***)(IStream *, GUID *, __int64))v15)(v15, v17, (__int64)&a3->hVal.QuadPart);
  }
  (*(void (__fastcall **)(IStream *))(*(_QWORD *)v15 + 16LL))(v15);
LABEL_35:
  if ( v8 >= 0 )
  {
    a3->vt = a2;
    return (unsigned int)v8;
  }
LABEL_28:
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800340e8  push    rbx
0x1800340ea  push    rbp
0x1800340eb  push    rsi
0x1800340ec  push    rdi
0x1800340ed  push    r12
0x1800340ef  push    r14
0x1800340f1  push    r15
0x1800340f3  sub     rsp, 50h
0x1800340f7  mov     rax, cs:__security_cookie
0x1800340fe  xor     rax, rsp
0x180034101  mov     [rsp+88h+var_40], rax
0x180034106  movzx   ebp, dx
0x180034109  mov     r14d, 1Fh
0x18003410f  xor     r15d, r15d
0x180034112  mov     rdi, r8
0x180034115  mov     rsi, rcx
0x180034118  cmp     r14w, bp
0x18003411c  jnz     short loc_180034145
0x18003411e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180034122  inc     rdx
0x180034125  cmp     [rcx+rdx*2], r15w
0x18003412a  jnz     short loc_180034122
0x18003412c  lea     rax, [r8+8]
0x180034130  mov     r9, rdx
0x180034133  mov     r8, rsi
0x180034136  mov     [rsp+88h+var_60], rax
0x18003413b  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180034140  jmp     loc_180034274
0x180034145  mov     eax, 8
0x18003414a  cmp     ax, bp
0x18003414d  jnz     short loc_18003415D
0x18003414f  lea     rdx, [r8+8]; unsigned __int16 **
0x180034153  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x180034158  jmp     loc_180034274
0x18003415d  mov     eax, 101Fh
0x180034162  cmp     ax, bp
0x180034165  jnz     short loc_180034174
0x180034167  mov     rdx, rdi; struct tagPROPVARIANT *
0x18003416a  call    ?_InitPropVariantFromParsedString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; _InitPropVariantFromParsedString(ushort const *,tagPROPVARIANT *)
0x18003416f  jmp     loc_180034274
0x180034174  mov     eax, 1011h
0x180034179  cmp     ax, bp
0x18003417c  jnz     short loc_18003418B
0x18003417e  mov     rdx, rdi; pvar
0x180034181  call    ?_InitPropVariantFromParsedUI1String@@YAJPEBGPEAUtagPROPVARIANT@@@Z; _InitPropVariantFromParsedUI1String(ushort const *,tagPROPVARIANT *)
0x180034186  jmp     loc_180034274
0x18003418b  mov     eax, 1Eh
0x180034190  cmp     ax, bp
0x180034193  jnz     short loc_1800341A3
0x180034195  lea     rdx, [r8+8]; char **
0x180034199  call    ?_DupWideToAnsi@@YAJPEBGPEAPEAD@Z; _DupWideToAnsi(ushort const *,char * *)
0x18003419e  jmp     loc_180034274
0x1800341a3  xor     eax, eax
0x1800341a5  xorps   xmm0, xmm0
0x1800341a8  movups  xmmword ptr [r8], xmm0
0x1800341ac  mov     [r8+10h], rax
0x1800341b0  mov     ebx, 80070057h
0x1800341b5  cmp     r15w, [rcx]
0x1800341b9  jz      loc_180034295
0x1800341bf  mov     ecx, ebp
0x1800341c1  lea     r12d, [rax+0Dh]
0x1800341c5  sub     ecx, r12d
0x1800341c8  jz      loc_18003427B
0x1800341ce  sub     ecx, 34h ; '4'
0x1800341d1  jz      loc_18003425A
0x1800341d7  sub     ecx, 1
0x1800341da  jz      loc_18003427B
0x1800341e0  cmp     ecx, 2
0x1800341e3  jz      loc_18003427B
0x1800341e9  movups  xmmword ptr [rsp+88h+propvarSrc], xmm0
0x1800341ee  mov     [rsp+88h+var_48], rax
0x1800341f3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800341f7  inc     rdx
0x1800341fa  cmp     [rsi+rdx*2], r15w
0x1800341ff  jnz     short loc_1800341F7
0x180034201  lea     rbx, ds:2[rdx*2]
0x180034209  mov     rcx, rbx; cb
0x18003420c  call    cs:__imp_CoTaskMemAlloc
0x180034212  mov     [rsp+88h+propvarSrc+8], rax
0x180034217  test    rax, rax
0x18003421a  jz      short loc_180034290
0x18003421c  mov     r9, rbx; SourceSize
0x18003421f  mov     r8, rsi; Source
0x180034222  mov     rdx, rbx; DestinationSize
0x180034225  mov     rcx, rax; Destination
0x180034228  call    memcpy_s
0x18003422d  movzx   r9d, bp; vt
0x180034231  mov     word ptr [rsp+88h+propvarSrc], r14w
0x180034237  xor     r8d, r8d; flags
0x18003423a  lea     rdx, [rsp+88h+propvarSrc]; propvarSrc
0x18003423f  mov     rcx, rdi; ppropvarDest
0x180034242  call    cs:__imp_PropVariantChangeType
0x180034248  lea     rcx, [rsp+88h+propvarSrc]; pvar
0x18003424d  mov     ebx, eax
0x18003424f  call    cs:__imp_PropVariantClear
0x180034255  jmp     loc_180034307
0x18003425a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003425e  inc     rdx; unsigned int
0x180034261  cmp     [rsi+rdx*2], r15w
0x180034266  jnz     short loc_18003425E
0x180034268  add     r8, 8; struct tagBLOB *
0x18003426c  mov     rcx, rsi; unsigned __int16 *
0x18003426f  call    ?TextToBlob2@@YAJPEBGIPEAUtagBLOB@@@Z; TextToBlob2(ushort const *,uint,tagBLOB *)
0x180034274  mov     ebx, eax
0x180034276  jmp     loc_180034307
0x18003427b  mov     edx, 400h; cbInit
0x180034280  xor     ecx, ecx; pInit
0x180034282  call    cs:__imp_SHCreateMemStream
0x180034288  mov     r14, rax
0x18003428b  test    rax, rax
0x18003428e  jnz     short loc_1800342BF
0x180034290  mov     ebx, 8007000Eh
0x180034295  xorps   xmm0, xmm0
0x180034298  xor     eax, eax
0x18003429a  movups  xmmword ptr [rdi], xmm0
0x18003429d  mov     [rdi+10h], rax
0x1800342a1  mov     eax, ebx
0x1800342a3  mov     rcx, [rsp+88h+var_40]
0x1800342a8  xor     rcx, rsp; StackCookie
0x1800342ab  call    __security_check_cookie
0x1800342b0  add     rsp, 50h
0x1800342b4  pop     r15
0x1800342b6  pop     r14
0x1800342b8  pop     r12
0x1800342ba  pop     rdi
0x1800342bb  pop     rsi
0x1800342bc  pop     rbp
0x1800342bd  pop     rbx
0x1800342be  retn
0x1800342bf  mov     r8, r14
0x1800342c2  mov     rdx, rsi
0x1800342c5  call    ?TextToBinary@@YAJW4BINARY_TEXT_ENCODE_SCHEME@@PEBGPEAUIStream@@@Z; TextToBinary(BINARY_TEXT_ENCODE_SCHEME,ushort const *,IStream *)
0x1800342ca  mov     ebx, eax
0x1800342cc  test    eax, eax
0x1800342ce  js      short loc_1800342F8
0x1800342d0  mov     rax, [r14]
0x1800342d3  lea     r8, [rdi+8]
0x1800342d7  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800342de  mov     rcx, r14
0x1800342e1  mov     rax, [rax]
0x1800342e4  cmp     bp, r12w
0x1800342e8  jz      short loc_1800342F1
0x1800342ea  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x1800342f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342f6  mov     ebx, eax
0x1800342f8  mov     rax, [r14]
0x1800342fb  mov     rcx, r14
0x1800342fe  mov     rax, [rax+10h]
0x180034302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034307  test    ebx, ebx
0x180034309  js      short loc_180034295
0x18003430b  mov     [rdi], bp
0x18003430e  jmp     short loc_1800342A1
```
