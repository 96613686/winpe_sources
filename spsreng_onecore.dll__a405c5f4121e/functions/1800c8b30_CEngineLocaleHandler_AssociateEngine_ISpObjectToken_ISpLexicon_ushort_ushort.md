# CEngineLocaleHandler::AssociateEngine(ISpObjectToken *,ISpLexicon *,ushort,ushort)

- ea: `0x1800c8b30`
- end: `0x1800c8fb6`
- name: `?AssociateEngine@CEngineLocaleHandler@@UEAAJPEAUISpObjectToken@@PEAUISpLexicon@@GG@Z`
- size: `1158`
- prototype: `int(CEngineLocaleHandler *__hidden this, struct ISpObjectToken *, struct ISpLexicon *, unsigned __int16, unsigned __int16)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800da0d0`
- `0x1800db1e0`

## callees

- `0x180002470`
- `0x180002db8`
- `0x180002e00`
- `0x1800034b0`
- `0x180004312`
- `0x1800060c0`
- `0x1800061d0`
- `0x1800073b4`
- `0x1800617d0`
- `0x180061a90`
- `0x1800afae8`
- `0x1800c8b30`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c8c3d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c8c3d`

## string_xrefs

- `0x1800c8ea6`: `deucompoundword`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CEngineLocaleHandler::AssociateEngine(
        CEngineLocaleHandler *this,
        struct IUnknown *a2,
        struct IUnknown *a3,
        __int16 a4,
        unsigned __int16 a5)
{
  _QWORD *v8; // rsi
  int v9; // r15d
  HRESULT Instance; // ebx
  _QWORD *v11; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rcx
  unsigned __int16 *v14; // rsi
  __int64 v15; // r14
  __int64 v16; // rbx
  __int64 v17; // r13
  SIZE_T v18; // rax
  unsigned __int16 *v19; // rax
  size_t v20; // rbx
  bool v22; // [rsp+30h] [rbp-D0h] BYREF
  void *Src; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v29; // [rsp+68h] [rbp-98h]
  _QWORD v30[5]; // [rsp+70h] [rbp-90h] BYREF
  int v31; // [rsp+98h] [rbp-68h]
  __int64 v32; // [rsp+9Ch] [rbp-64h]
  __int64 v33; // [rsp+A8h] [rbp-58h]
  _QWORD *v34; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v35[264]; // [rsp+C0h] [rbp-40h] BYREF

  v8 = (_QWORD *)((char *)this + 32);
  if ( *((struct IUnknown **)this + 4) != a2 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 4, a2);
  *((_WORD *)this + 20) = a4;
  *((_DWORD *)this + 11) = a5 != 0;
  v28 = *(_QWORD *)L".ini";
  v29 = aIni[4];
  v30[2] = &g_heap;
  v30[4] = 0;
  v33 = 0;
  v30[3] = 0;
  v31 = 0;
  v32 = 1;
  v9 = 1;
  v30[1] = &CStringHash<char *>::`vftable';
  v30[0] = 0;
  v27 = 0;
  v26 = 0;
  v24 = 0;
  Src = 0;
  v25 = 0;
  if ( a3 && *((struct IUnknown **)this + 6) != a3 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 6, a3);
  if ( a5
    || (Instance = CoCreateInstance(
                     &CLSID_SpShortcut,
                     0,
                     0x17u,
                     &GUID_3df681e2_ea56_11d9_8bde_f66bad1e3f3a,
                     (LPVOID *)this + 7),
        Instance >= 0) )
  {
    v11 = CWinHeap::Alloc(&g_heap, 0x18u, 0);
    v12 = v11;
    v34 = v11;
    if ( v11 )
    {
      *(_OWORD *)v11 = 0;
      v11[2] = 0;
      *((_DWORD *)v11 + 5) = 1;
      *((_BYTE *)v11 + 16) = 0;
      v11[1] = 0;
      *v11 = &CVendorPhoneConverterSR2SR::`vftable';
    }
    else
    {
      v12 = 0;
    }
    *((_QWORD *)this + 12) = v12;
    if ( !v12 )
    {
      Instance = -2147024882;
      v14 = 0;
      goto LABEL_36;
    }
    Instance = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*v12 + 72LL))(
                 v12,
                 *v8,
                 *((unsigned __int16 *)this + 20));
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(CEngineLocaleHandler *))(*(_QWORD *)this + 344LL))(this);
      if ( Instance >= 0 )
      {
        if ( !(*(unsigned __int8 (__fastcall **)(CEngineLocaleHandler *))(*(_QWORD *)this + 424LL))(this)
          || (v13 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 8LL) + 168LL),
              Instance = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 64LL))(v13, 0),
              Instance >= 0) )
        {
          Instance = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 *))(*(_QWORD *)*v8 + 72LL))(
                       *v8,
                       L"Models",
                       &v27);
          if ( Instance >= 0 )
          {
            StringCchPrintfW(v35, 0x104u, L"%d", *((unsigned __int16 *)this + 20));
            Instance = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64 *))(*(_QWORD *)v27 + 72LL))(
                         v27,
                         v35,
                         &v24);
            if ( Instance >= 0 )
            {
              Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 48LL))(v24, 0, &v25);
              if ( Instance >= 0 )
              {
                Instance = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v24 + 72LL))(
                             v24,
                             v25,
                             &v26);
                if ( Instance >= 0 )
                  Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v26 + 48LL))(v26, 0, &Src);
              }
            }
          }
        }
      }
    }
  }
  v14 = 0;
  if ( Instance >= 0 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)&v28 + v15) );
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)Src + v16) );
    v17 = v15 + v16;
    v18 = 2 * (v15 + v16 + 1);
    if ( !is_mul_ok(v15 + v16 + 1, 2u) )
      v18 = -1;
    v19 = (unsigned __int16 *)CWinHeap::Alloc(&g_heap, v18, 0);
    v14 = v19;
    if ( v19 )
    {
      v20 = v16;
      memcpy_0(v19, Src, v20 * 2);
      memcpy_0(&v14[v20], &v28, 2 * v15);
      v14[v17] = 0;
      Instance = CArgParser::Init((CArgParser *)v30, v14);
      if ( Instance >= 0 )
      {
        CArgParser::GetBool((CArgParser *)v30, "console", &v22);
        CArgParser::GetBool((CArgParser *)v30, "tntransducer", (bool *)this + 144);
        CArgParser::GetBool((CArgParser *)v30, "deucompoundword", (bool *)this + 148);
        CArgParser::GetBool((CArgParser *)v30, "ignorewordboundary", (bool *)this + 152);
        v22 = 0;
        CArgParser::GetBool((CArgParser *)v30, "AddTTSPronunciationSupported", &v22);
        CArgParser::GetBool((CArgParser *)v30, "AddTTSPronunciation", (bool *)this + 200);
        if ( !*((_DWORD *)this + 50) || !v22 )
          v9 = 0;
        *((_DWORD *)this + 50) = v9;
        CArgParser::GetBool((CArgParser *)v30, "SRTTSMergedVendorLexicon", (bool *)this + 204);
      }
    }
    else
    {
      Instance = -2147467259;
    }
  }
LABEL_36:
  operator delete(v14);
  CSpDynamicString::_free((CSpDynamicString *)&v25);
  CSpDynamicString::_free((CSpDynamicString *)&Src);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v24);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v26);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v27);
  CArgParser::~CArgParser((CArgParser *)v30);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800c8b30  mov     [rsp-8+arg_18], rbx
0x1800c8b35  push    rbp
0x1800c8b36  push    rsi
0x1800c8b37  push    rdi
0x1800c8b38  push    r12
0x1800c8b3a  push    r13
0x1800c8b3c  push    r14
0x1800c8b3e  push    r15
0x1800c8b40  lea     rbp, [rsp-1E0h]
0x1800c8b48  sub     rsp, 2E0h
0x1800c8b4f  mov     rax, cs:__security_cookie
0x1800c8b56  xor     rax, rsp
0x1800c8b59  mov     [rbp+210h+var_40], rax
0x1800c8b60  movzx   r14d, r9w
0x1800c8b64  mov     rbx, r8
0x1800c8b67  mov     rdi, rcx
0x1800c8b6a  lea     rsi, [rcx+20h]
0x1800c8b6e  cmp     [rsi], rdx
0x1800c8b71  jz      short loc_1800C8B7B
0x1800c8b73  mov     rcx, rsi; struct IUnknown **
0x1800c8b76  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800c8b7b  mov     [rdi+28h], r14w
0x1800c8b80  xor     r12d, r12d
0x1800c8b83  mov     eax, r12d
0x1800c8b86  movzx   r14d, [rbp+210h+arg_20]
0x1800c8b8e  test    r14w, r14w
0x1800c8b92  setnz   al
0x1800c8b95  mov     [rdi+2Ch], eax
0x1800c8b98  movsd   xmm0, qword ptr cs:aIni; ".ini"
0x1800c8ba0  movsd   [rsp+310h+var_2B0], xmm0
0x1800c8ba6  movzx   eax, word ptr cs:aIni+8; ""
0x1800c8bad  mov     [rsp+310h+var_2A8], ax
0x1800c8bb2  lea     r13, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x1800c8bb9  mov     [rbp+210h+var_290], r13
0x1800c8bbd  mov     [rbp+210h+var_280], r12
0x1800c8bc1  mov     [rbp+210h+var_268], r12
0x1800c8bc5  mov     [rbp+210h+var_288], r12
0x1800c8bc9  mov     [rbp+210h+var_278], r12d
0x1800c8bcd  mov     [rbp+210h+var_274], 1
0x1800c8bd5  lea     r15d, [r12+1]
0x1800c8bda  lea     rax, ??_7?$CStringHash@PEAD@@6B@; const CStringHash<char *>::`vftable'
0x1800c8be1  mov     [rsp+310h+var_298], rax
0x1800c8be6  mov     [rsp+310h+var_2A0], r12
0x1800c8beb  mov     [rsp+310h+var_2B8], r12
0x1800c8bf0  mov     [rsp+310h+var_2C0], r12
0x1800c8bf5  mov     [rsp+310h+var_2D0], r12
0x1800c8bfa  mov     [rsp+310h+Src], r12
0x1800c8bff  mov     [rsp+310h+var_2C8], r12
0x1800c8c04  test    rbx, rbx
0x1800c8c07  jz      short loc_1800C8C1A
0x1800c8c09  lea     rcx, [rdi+30h]; struct IUnknown **
0x1800c8c0d  cmp     [rcx], rbx
0x1800c8c10  jz      short loc_1800C8C1A
0x1800c8c12  mov     rdx, rbx; struct IUnknown *
0x1800c8c15  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800c8c1a  test    r14w, r14w
0x1800c8c1e  jnz     short loc_1800C8C4D
0x1800c8c20  lea     rax, [rdi+38h]
0x1800c8c24  mov     [rsp+310h+ppv], rax; ppv
0x1800c8c29  lea     r9, _GUID_3df681e2_ea56_11d9_8bde_f66bad1e3f3a; riid
0x1800c8c30  xor     edx, edx; pUnkOuter
0x1800c8c32  lea     r8d, [rdx+17h]; dwClsContext
0x1800c8c36  lea     rcx, CLSID_SpShortcut; rclsid
0x1800c8c3d  call    cs:__imp_CoCreateInstance
0x1800c8c43  mov     ebx, eax
0x1800c8c45  test    eax, eax
0x1800c8c47  js      loc_1800C8DCB
0x1800c8c4d  xor     r8d, r8d; bool
0x1800c8c50  lea     edx, [r8+18h]; unsigned __int64
0x1800c8c54  mov     rcx, r13; this
0x1800c8c57  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800c8c5c  mov     rcx, rax
0x1800c8c5f  mov     [rbp+210h+var_260], rax
0x1800c8c63  test    rax, rax
0x1800c8c66  jz      short loc_1800C8C8C
0x1800c8c68  xorps   xmm0, xmm0
0x1800c8c6b  xor     eax, eax
0x1800c8c6d  movups  xmmword ptr [rcx], xmm0
0x1800c8c70  mov     [rcx+10h], rax
0x1800c8c74  mov     [rcx+14h], r15d
0x1800c8c78  mov     [rcx+10h], r12b
0x1800c8c7c  mov     [rcx+8], r12
0x1800c8c80  lea     rax, ??_7CVendorPhoneConverterSR2SR@@6B@; const CVendorPhoneConverterSR2SR::`vftable'
0x1800c8c87  mov     [rcx], rax
0x1800c8c8a  jmp     short loc_1800C8C8F
0x1800c8c8c  mov     rcx, r12
0x1800c8c8f  mov     [rdi+60h], rcx
0x1800c8c93  test    rcx, rcx
0x1800c8c96  jz      loc_1800C8F38
0x1800c8c9c  mov     rax, [rcx]
0x1800c8c9f  movzx   r8d, word ptr [rdi+28h]
0x1800c8ca4  mov     rdx, [rsi]
0x1800c8ca7  mov     rax, [rax+48h]
0x1800c8cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8cb0  mov     ebx, eax
0x1800c8cb2  test    eax, eax
0x1800c8cb4  js      loc_1800C8DCB
0x1800c8cba  mov     rax, [rdi]
0x1800c8cbd  mov     rcx, rdi
0x1800c8cc0  mov     rax, [rax+158h]
0x1800c8cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8ccc  mov     ebx, eax
0x1800c8cce  test    eax, eax
0x1800c8cd0  js      loc_1800C8DCB
0x1800c8cd6  mov     rax, [rdi]
0x1800c8cd9  mov     rcx, rdi
0x1800c8cdc  mov     rax, [rax+1A8h]
0x1800c8ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8ce8  test    al, al
0x1800c8cea  jz      short loc_1800C8D13
0x1800c8cec  mov     rax, [rdi+58h]
0x1800c8cf0  mov     rcx, [rax+8]
0x1800c8cf4  mov     rcx, [rcx+0A8h]
0x1800c8cfb  mov     rax, [rcx]
0x1800c8cfe  xor     edx, edx
0x1800c8d00  mov     rax, [rax+40h]
0x1800c8d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8d09  mov     ebx, eax
0x1800c8d0b  test    eax, eax
0x1800c8d0d  js      loc_1800C8DCB
0x1800c8d13  mov     rcx, [rsi]
0x1800c8d16  mov     rax, [rcx]
0x1800c8d19  lea     r8, [rsp+310h+var_2B8]
0x1800c8d1e  lea     rdx, aModels; "Models"
0x1800c8d25  mov     rax, [rax+48h]
0x1800c8d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8d2e  mov     ebx, eax
0x1800c8d30  test    eax, eax
0x1800c8d32  js      loc_1800C8DCB
0x1800c8d38  movzx   r9d, word ptr [rdi+28h]
0x1800c8d3d  lea     r8, aD; "%d"
0x1800c8d44  mov     edx, 104h; unsigned __int64
0x1800c8d49  lea     rcx, [rbp+210h+var_250]; unsigned __int16 *
0x1800c8d4d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c8d52  mov     rcx, [rsp+310h+var_2B8]
0x1800c8d57  mov     rax, [rcx]
0x1800c8d5a  lea     r8, [rsp+310h+var_2D0]
0x1800c8d5f  lea     rdx, [rbp+210h+var_250]
0x1800c8d63  mov     rax, [rax+48h]
0x1800c8d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8d6c  mov     ebx, eax
0x1800c8d6e  test    eax, eax
0x1800c8d70  js      short loc_1800C8DCB
0x1800c8d72  mov     rcx, [rsp+310h+var_2D0]
0x1800c8d77  mov     rax, [rcx]
0x1800c8d7a  lea     r8, [rsp+310h+var_2C8]
0x1800c8d7f  xor     edx, edx
0x1800c8d81  mov     rax, [rax+30h]
0x1800c8d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8d8a  mov     ebx, eax
0x1800c8d8c  test    eax, eax
0x1800c8d8e  js      short loc_1800C8DCB
0x1800c8d90  mov     rcx, [rsp+310h+var_2D0]
0x1800c8d95  mov     rax, [rcx]
0x1800c8d98  lea     r8, [rsp+310h+var_2C0]
0x1800c8d9d  mov     rdx, [rsp+310h+var_2C8]
0x1800c8da2  mov     rax, [rax+48h]
0x1800c8da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8dab  mov     ebx, eax
0x1800c8dad  test    eax, eax
0x1800c8daf  js      short loc_1800C8DCB
0x1800c8db1  mov     rcx, [rsp+310h+var_2C0]
0x1800c8db6  mov     rax, [rcx]
0x1800c8db9  lea     r8, [rsp+310h+Src]
0x1800c8dbe  xor     edx, edx
0x1800c8dc0  mov     rax, [rax+30h]
0x1800c8dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8dc9  mov     ebx, eax
0x1800c8dcb  mov     rsi, r12
0x1800c8dce  test    ebx, ebx
0x1800c8dd0  js      loc_1800C8F40
0x1800c8dd6  lea     rax, [rsp+310h+var_2B0]
0x1800c8ddb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800c8ddf  mov     r14, r8
0x1800c8de2  inc     r14
0x1800c8de5  cmp     [rax+r14*2], r12w
0x1800c8dea  jnz     short loc_1800C8DE2
0x1800c8dec  mov     rax, [rsp+310h+Src]
0x1800c8df1  mov     rbx, r8
0x1800c8df4  inc     rbx
0x1800c8df7  cmp     [rax+rbx*2], r12w
0x1800c8dfc  jnz     short loc_1800C8DF4
0x1800c8dfe  lea     r13, [r14+rbx]
0x1800c8e02  lea     rdx, [r13+1]
0x1800c8e06  mov     eax, 2
0x1800c8e0b  mul     rdx
0x1800c8e0e  cmovb   rax, r8
0x1800c8e12  xor     r8d, r8d; bool
0x1800c8e15  mov     rdx, rax; unsigned __int64
0x1800c8e18  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800c8e1f  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800c8e24  mov     rsi, rax
0x1800c8e27  test    rax, rax
0x1800c8e2a  jz      loc_1800C8F31
0x1800c8e30  add     rbx, rbx
0x1800c8e33  mov     r8, rbx; Size
0x1800c8e36  mov     rdx, [rsp+310h+Src]; Src
0x1800c8e3b  mov     rcx, rax; void *
0x1800c8e3e  call    memcpy_0
0x1800c8e43  lea     r8, [r14+r14]; Size
0x1800c8e47  lea     rcx, [rbx+rsi]; void *
0x1800c8e4b  lea     rdx, [rsp+310h+var_2B0]; Src
0x1800c8e50  call    memcpy_0
0x1800c8e55  mov     [rsi+r13*2], r12w
0x1800c8e5a  mov     rdx, rsi; unsigned __int16 *
0x1800c8e5d  lea     rcx, [rsp+310h+var_2A0]; this
0x1800c8e62  call    ?Init@CArgParser@@QEAAJPEBG@Z; CArgParser::Init(ushort const *)
0x1800c8e67  mov     ebx, eax
0x1800c8e69  test    eax, eax
0x1800c8e6b  js      loc_1800C8F40
0x1800c8e71  lea     r8, [rsp+310h+var_2E0]; bool *
0x1800c8e76  lea     rdx, aConsole; "console"
0x1800c8e7d  lea     rcx, [rsp+310h+var_2A0]; this
0x1800c8e82  call    ?GetBool@CArgParser@@QEAA_NPEBDPEA_N@Z; CArgParser::GetBool(char const *,bool *)
0x1800c8e87  lea     r8, [rdi+90h]; bool *
0x1800c8e8e  lea     rdx, aTntransducer; "tntransducer"
0x1800c8e95  lea     rcx, [rsp+310h+var_2A0]; this
0x1800c8e9a  call    ?GetBool@CArgParser@@QEAA_NPEBDPEA_N@Z; CArgParser::GetBool(char const *,bool *)
0x1800c8e9f  lea     r8, [rdi+94h]; bool *
0x1800c8ea6  lea     rdx, aDeucompoundwor; "deucompoundword"
0x1800c8ead  lea     rcx, [rsp+310h+var_2A0]; this
0x1800c8eb2  call    ?GetBool@CArgParser@@QEAA_NPEBDPEA_N@Z; CArgParser::GetBool(char const *,bool *)
0x1800c8eb7  lea     r8, [rdi+98h]; bool *
0x1800c8ebe  lea     rdx, aIgnorewordboun; "ignorewordboundary"
0x1800c8ec5  lea     rcx, [rsp+310h+var_2A0]; this
0x1800c8eca  call    ?GetBool@CArgParser@@QEAA_NPEBDPEA_N@Z; CArgParser::GetBool(char const *,bool *)
0x1800c8ecf  mov     [rsp+310h+var_2E0], r12b
0x1800c8ed4  lea     r8, [rsp+310h+var_2E0]; bool *
0x1800c8ed9  lea     rdx, aAddttspronunci_0; "AddTTSPronunciationSupported"
0x1800c8ee0  lea     rcx, [rsp+310h+var_2A0]; this
0x1800c8ee5  call    ?GetBool@CArgParser@@QEAA_NPEBDPEA_N@Z; CArgParser::GetBool(char const *,bool *)
0x1800c8eea  lea     r14, [rdi+0C8h]
0x1800c8ef1  mov     r8, r14; bool *
0x1800c8ef4  lea     rdx, aAddttspronunci; "AddTTSPronunciation"
0x1800c8efb  lea     rcx, [rsp+310h+var_2A0]; this
0x1800c8f00  call    ?GetBool@CArgParser@@QEAA_NPEBDPEA_N@Z; CArgParser::GetBool(char const *,bool *)
0x1800c8f05  cmp     [r14], r12d
0x1800c8f08  jz      short loc_1800C8F11
0x1800c8f0a  cmp     [rsp+310h+var_2E0], r12b
0x1800c8f0f  jnz     short loc_1800C8F14
0x1800c8f11  mov     r15d, r12d
0x1800c8f14  mov     [r14], r15d
0x1800c8f17  lea     r8, [rdi+0CCh]; bool *
0x1800c8f1e  lea     rdx, aSrttsmergedven; "SRTTSMergedVendorLexicon"
0x1800c8f25  lea     rcx, [rsp+310h+var_2A0]; this
0x1800c8f2a  call    ?GetBool@CArgParser@@QEAA_NPEBDPEA_N@Z; CArgParser::GetBool(char const *,bool *)
0x1800c8f2f  jmp     short loc_1800C8F40
0x1800c8f31  mov     ebx, 80004005h
0x1800c8f36  jmp     short loc_1800C8F40
0x1800c8f38  mov     ebx, 8007000Eh
0x1800c8f3d  mov     rsi, r12
0x1800c8f40  mov     rcx, rsi; void *
0x1800c8f43  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c8f48  nop
0x1800c8f49  lea     rcx, [rsp+310h+var_2C8]; this
0x1800c8f4e  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x1800c8f53  nop
0x1800c8f54  lea     rcx, [rsp+310h+Src]; this
0x1800c8f59  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x1800c8f5e  nop
0x1800c8f5f  lea     rcx, [rsp+310h+var_2D0]
0x1800c8f64  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800c8f69  nop
0x1800c8f6a  lea     rcx, [rsp+310h+var_2C0]
0x1800c8f6f  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800c8f74  nop
0x1800c8f75  lea     rcx, [rsp+310h+var_2B8]
0x1800c8f7a  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800c8f7f  nop
0x1800c8f80  lea     rcx, [rsp+310h+var_2A0]; this
0x1800c8f85  call    ??1CArgParser@@QEAA@XZ; CArgParser::~CArgParser(void)
0x1800c8f8a  mov     eax, ebx
0x1800c8f8c  mov     rcx, [rbp+210h+var_40]
0x1800c8f93  xor     rcx, rsp; StackCookie
0x1800c8f96  call    __security_check_cookie
0x1800c8f9b  mov     rbx, [rsp+310h+arg_18]
0x1800c8fa3  add     rsp, 2E0h
0x1800c8faa  pop     r15
0x1800c8fac  pop     r14
0x1800c8fae  pop     r13
0x1800c8fb0  pop     r12
0x1800c8fb2  pop     rdi
0x1800c8fb3  pop     rsi
0x1800c8fb4  pop     rbp
0x1800c8fb5  retn
```
