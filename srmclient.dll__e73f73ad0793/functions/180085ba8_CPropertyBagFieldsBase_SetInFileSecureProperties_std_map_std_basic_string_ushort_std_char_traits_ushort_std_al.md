# CPropertyBagFieldsBase::SetInFileSecureProperties(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CCaseInsensitiveLess<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &)

- ea: `0x180085ba8`
- end: `0x1800860a5`
- name: `?SetInFileSecureProperties@CPropertyBagFieldsBase@@QEAAXAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `1277`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a1e78`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x18007e5ac`
- `0x180084e28`
- `0x180085ba8`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180085c84`
- `ole32!CoTaskMemAlloc` at `0x180085cc1`
- `ole32!CoTaskMemAlloc` at `0x180085d75`
- `ole32!CoTaskMemAlloc` at `0x180085db1`
- `ole32!CoTaskMemAlloc` at `0x180085c84`
- `ole32!CoTaskMemAlloc` at `0x180085cc1`
- `ole32!CoTaskMemAlloc` at `0x180085d75`
- `ole32!CoTaskMemAlloc` at `0x180085db1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CPropertyBagFieldsBase::SetInFileSecureProperties(__int64 a1, __int64 a2)
{
  struct _FSRM_IN_FILE_SECURE_PROPERTIES **v4; // r15
  struct _FSRM_IN_FILE_SECURE_PROPERTIES *v5; // rax
  struct _FSRM_IN_FILE_SECURE_PROPERTIES *v6; // r14
  SIZE_T v7; // rbx
  unsigned __int16 **v8; // rsi
  const unsigned __int16 *v9; // rbx
  const unsigned __int16 *v10; // r15
  const unsigned __int16 *v11; // r12
  int v12; // eax
  int v13; // eax
  __int64 *v14; // rax
  __int64 *v15; // rax
  __int64 v16; // rax
  int v17; // eax
  char v18; // al
  int v19; // eax
  char v20; // al
  int v21; // eax
  char v22; // al
  char v23; // al
  char v24; // al
  char v25; // al
  char Hr; // al
  struct _FSRM_IN_FILE_SECURE_PROPERTIES *v27; // [rsp+48h] [rbp-1C0h] BYREF
  unsigned __int64 v28; // [rsp+50h] [rbp-1B8h]
  unsigned __int64 v29; // [rsp+58h] [rbp-1B0h]
  struct _FSRM_IN_FILE_SECURE_PROPERTIES **v30; // [rsp+60h] [rbp-1A8h]
  int v31; // [rsp+68h] [rbp-1A0h] BYREF
  __int64 *i; // [rsp+70h] [rbp-198h]
  unsigned __int16 **v33; // [rsp+78h] [rbp-190h]
  _com_error *v34; // [rsp+80h] [rbp-188h] BYREF
  const exception *v35; // [rsp+88h] [rbp-180h] BYREF
  _QWORD v36[4]; // [rsp+90h] [rbp-178h] BYREF
  int v37; // [rsp+B0h] [rbp-158h]
  _DWORD v38[26]; // [rsp+B8h] [rbp-150h] BYREF
  void **v39; // [rsp+120h] [rbp-E8h] BYREF
  int v40; // [rsp+128h] [rbp-E0h]
  unsigned int v41; // [rsp+14Ch] [rbp-BCh]

  v36[0] = L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp";
  v36[1] = L"CPropertyBagFieldsBase::SetInFileSecureProperties";
  v36[2] = L"SRMPROPC";
  v36[3] = 496;
  v37 = 255;
  v38[24] = 0x1000000;
  memset_0(v38, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v39, (const struct CSrmDebugInfo *)v36, 0);
  v27 = 0;
  v4 = (struct _FSRM_IN_FILE_SECURE_PROPERTIES **)(a1 + 40);
  v30 = v4;
  CPropertyBagFieldsBase::ClearInFileSecureProperties(v4);
  try
  {
    if ( *(_QWORD *)(a2 + 16) )
    {
      v5 = (struct _FSRM_IN_FILE_SECURE_PROPERTIES *)CoTaskMemAlloc(0x10u);
      v6 = v5;
      v27 = v5;
      if ( !v5 )
      {
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v39, -2147024882);
        Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v39);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v39, 0x205u, Hr, 0);
      }
      v40 = 0;
      *(_OWORD *)v5 = 0;
      v7 = 16LL * *(_QWORD *)(a2 + 16);
      *((_QWORD *)v5 + 1) = CoTaskMemAlloc(v7);
      if ( !*((_QWORD *)v6 + 1) )
      {
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v39, -2147024882);
        v25 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v39);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v39, 0x20Au, v25, 0);
      }
      v40 = 0;
      memset_0(*((void **)v6 + 1), 0, v7);
      *(_DWORD *)v6 = *(_DWORD *)(a2 + 16);
      v8 = (unsigned __int16 **)*((_QWORD *)v6 + 1);
      v33 = v8;
      v9 = **(const unsigned __int16 ***)(a2 + 8);
      while ( 1 )
      {
        v29 = *(_QWORD *)(a2 + 8);
        if ( v9 == (const unsigned __int16 *)v29 )
          break;
        v10 = v9 + 12;
        v11 = v9 + 32;
        v29 = 2LL * *((_QWORD *)v9 + 5) + 2;
        v28 = *((_QWORD *)v9 + 10);
        *v8 = (unsigned __int16 *)CoTaskMemAlloc(v29);
        if ( !*v8 )
        {
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v39, -2147024882);
          v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v39);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v39, 0x218u, v24, 0);
        }
        v28 = 2 * v28 + 2;
        v40 = 0;
        v8[1] = (unsigned __int16 *)CoTaskMemAlloc(v28);
        if ( !v8[1] )
        {
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v39, -2147024882);
          v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v39);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v39, 0x21Au, v23, 0);
        }
        v40 = 0;
        if ( *((_QWORD *)v9 + 6) >= 8u )
          v10 = *(const unsigned __int16 **)v10;
        v12 = StringCbCopyW(*v8, v29, v10);
        v40 = v12;
        if ( v12 < 0 )
        {
          v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v39);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v39, v19);
          v20 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v39);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v39, 0x21Cu, v20, 0);
        }
        v40 = v12;
        if ( *((_QWORD *)v9 + 11) >= 8u )
          v11 = *(const unsigned __int16 **)v11;
        v13 = StringCbCopyW(v8[1], v28, v11);
        v40 = v13;
        if ( v13 < 0 )
        {
          v21 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v39);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v39, v21);
          v22 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v39);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v39, 0x21Du, v22, 0);
        }
        v40 = v13;
        if ( !*((_BYTE *)v9 + 105) )
        {
          v14 = (__int64 *)*((_QWORD *)v9 + 2);
          if ( *((_BYTE *)v14 + 105) )
          {
            while ( 1 )
            {
              v16 = *((_QWORD *)v9 + 1);
              if ( *(_BYTE *)(v16 + 105) || v9 != *(const unsigned __int16 **)(v16 + 16) )
                break;
              v9 = (const unsigned __int16 *)*((_QWORD *)v9 + 1);
            }
            v9 = (const unsigned __int16 *)*((_QWORD *)v9 + 1);
          }
          else
          {
            v9 = (const unsigned __int16 *)*((_QWORD *)v9 + 2);
            for ( i = v14; ; i = v15 )
            {
              v15 = *(__int64 **)v9;
              if ( *(_BYTE *)(*(_QWORD *)v9 + 105LL) )
                break;
              v9 = *(const unsigned __int16 **)v9;
            }
          }
        }
        v8 += 2;
        v33 = v8;
        v4 = v30;
      }
      *v4 = v6;
      v27 = 0;
    }
  }
  catch ( long v31 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v39,
      v31,
      L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp",
      L"SRMPROPC",
      L"CPropertyBagFieldsBase::SetInFileSecureProperties",
      0x225u,
      v41);
  }
  catch ( _com_error *v34 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v39,
      v34,
      L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp",
      L"SRMPROPC",
      L"CPropertyBagFieldsBase::SetInFileSecureProperties",
      0x225u,
      v41);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v39,
      L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp",
      L"SRMPROPC",
      L"CPropertyBagFieldsBase::SetInFileSecureProperties",
      0x225u,
      v41);
  }
  catch ( const exception *v35 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v39,
      v35,
      L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp",
      L"SRMPROPC",
      L"CPropertyBagFieldsBase::SetInFileSecureProperties",
      0x225u,
      v41);
  }
  CPropertyBagFieldsBase::ClearInFileSecureProperties(&v27);
  if ( v40 < 0 )
  {
    v17 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v39);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v39, v17);
    v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v39);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v39, 0x22Au, v18, 0);
  }
  v39 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v39);
}

```

## disassembly

```asm
0x180085ba8  mov     r11, rsp
0x180085bab  mov     [r11+18h], rbx
0x180085baf  mov     [r11+20h], rsi
0x180085bb3  push    rdi
0x180085bb4  push    r12
0x180085bb6  push    r13
0x180085bb8  push    r14
0x180085bba  push    r15
0x180085bbc  sub     rsp, 1E0h
0x180085bc3  mov     rax, cs:__security_cookie
0x180085bca  xor     rax, rsp
0x180085bcd  mov     [rsp+208h+var_38], rax
0x180085bd5  mov     r13, rdx
0x180085bd8  mov     r15, rcx
0x180085bdb  lea     rax, [r11-178h]
0x180085be2  mov     [rsp+208h+var_1A8], rax
0x180085be7  lea     rax, aBaseFsFsrmUtil_17; "base\\fs\\fsrm\\utilities\\property\\sr"...
0x180085bee  mov     [r11-178h], rax
0x180085bf5  lea     rax, aCpropertybagfi_14; "CPropertyBagFieldsBase::SetInFileSecure"...
0x180085bfc  mov     [r11-170h], rax
0x180085c03  lea     rax, aSrmpropc; "SRMPROPC"
0x180085c0a  mov     [r11-168h], rax
0x180085c11  mov     qword ptr [r11-160h], 1F0h
0x180085c1c  xor     edi, edi
0x180085c1e  mov     [rsp+208h+var_158], 0FFh
0x180085c29  mov     [rsp+208h+var_F0], 1000000h
0x180085c34  xor     edx, edx; Val
0x180085c36  lea     r8d, [rdi+60h]; Size
0x180085c3a  lea     rcx, [r11-150h]; void *
0x180085c41  call    memset_0
0x180085c46  nop
0x180085c47  xor     r8d, r8d
0x180085c4a  lea     rdx, [rsp+208h+var_178]
0x180085c52  lea     rcx, [rsp+208h+var_E8]
0x180085c5a  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180085c5f  nop
0x180085c60  mov     [rsp+208h+var_1C0], rdi
0x180085c65  add     r15, 28h ; '('
0x180085c69  mov     [rsp+208h+var_1A8], r15
0x180085c6e  mov     rcx, r15; struct _FSRM_IN_FILE_SECURE_PROPERTIES **
0x180085c71  call    ?ClearInFileSecureProperties@CPropertyBagFieldsBase@@KAXAEAPEAU_FSRM_IN_FILE_SECURE_PROPERTIES@@@Z; CPropertyBagFieldsBase::ClearInFileSecureProperties(_FSRM_IN_FILE_SECURE_PROPERTIES * &)
0x180085c76  nop
0x180085c77  cmp     [r13+10h], rdi
0x180085c7b  jz      loc_180085D2A
0x180085c81  lea     ecx, [rdi+10h]; cb
0x180085c84  call    cs:__imp_CoTaskMemAlloc
0x180085c8a  mov     r14, rax
0x180085c8d  mov     [rsp+208h+var_1C0], rax
0x180085c92  mov     ecx, [rsp+208h+var_E0]
0x180085c99  mov     [rsp+208h+var_E0], ecx
0x180085ca0  test    rax, rax
0x180085ca3  jz      loc_18008606C
0x180085ca9  mov     [rsp+208h+var_E0], edi
0x180085cb0  xorps   xmm0, xmm0
0x180085cb3  movups  xmmword ptr [rax], xmm0
0x180085cb6  mov     rbx, [r13+10h]
0x180085cba  shl     rbx, 4
0x180085cbe  mov     rcx, rbx; cb
0x180085cc1  call    cs:__imp_CoTaskMemAlloc
0x180085cc7  mov     [r14+8], rax
0x180085ccb  mov     eax, [rsp+208h+var_E0]
0x180085cd2  mov     [rsp+208h+var_E0], eax
0x180085cd9  cmp     [r14+8], rdi
0x180085cdd  jz      loc_180086035
0x180085ce3  mov     [rsp+208h+var_E0], edi
0x180085cea  mov     r8, rbx; Size
0x180085ced  xor     edx, edx; Val
0x180085cef  mov     rcx, [r14+8]; void *
0x180085cf3  call    memset_0
0x180085cf8  mov     eax, [r13+10h]
0x180085cfc  mov     [r14], eax
0x180085cff  mov     rsi, [r14+8]
0x180085d03  mov     [rsp+208h+var_190], rsi
0x180085d08  mov     rbx, [r13+8]
0x180085d0c  mov     rbx, [rbx]
0x180085d0f  mov     [rsp+208h+var_1C8], rbx
0x180085d14  mov     rax, [r13+8]
0x180085d18  mov     [rsp+208h+var_1B0], rax
0x180085d1d  cmp     rbx, rax
0x180085d20  jnz     short loc_180085D4F
0x180085d22  mov     [r15], r14
0x180085d25  mov     [rsp+208h+var_1C0], rdi
0x180085d2a  lea     rcx, [rsp+208h+var_1C0]; struct _FSRM_IN_FILE_SECURE_PROPERTIES **
0x180085d2f  call    ?ClearInFileSecureProperties@CPropertyBagFieldsBase@@KAXAEAPEAU_FSRM_IN_FILE_SECURE_PROPERTIES@@@Z; CPropertyBagFieldsBase::ClearInFileSecureProperties(_FSRM_IN_FILE_SECURE_PROPERTIES * &)
0x180085d34  mov     eax, [rsp+208h+var_E0]
0x180085d3b  mov     [rsp+208h+var_E0], eax
0x180085d42  test    eax, eax
0x180085d44  js      loc_180085F03
0x180085d4a  jmp     loc_180085EB3
0x180085d4f  lea     r15, [rbx+18h]
0x180085d53  lea     r12, [rbx+40h]
0x180085d57  mov     rax, [r15+10h]
0x180085d5b  lea     rax, ds:2[rax*2]
0x180085d63  mov     [rsp+208h+var_1B0], rax
0x180085d68  mov     rcx, [r12+10h]
0x180085d6d  mov     [rsp+208h+var_1B8], rcx
0x180085d72  mov     rcx, rax; cb
0x180085d75  call    cs:__imp_CoTaskMemAlloc
0x180085d7b  mov     [rsi], rax
0x180085d7e  mov     eax, [rsp+208h+var_E0]
0x180085d85  mov     [rsp+208h+var_E0], eax
0x180085d8c  cmp     [rsi], rdi
0x180085d8f  jz      loc_180085FFE
0x180085d95  mov     rax, [rsp+208h+var_1B8]
0x180085d9a  lea     rax, ds:2[rax*2]
0x180085da2  mov     [rsp+208h+var_1B8], rax
0x180085da7  mov     [rsp+208h+var_E0], edi
0x180085dae  mov     rcx, rax; cb
0x180085db1  call    cs:__imp_CoTaskMemAlloc
0x180085db7  mov     [rsi+8], rax
0x180085dbb  mov     eax, [rsp+208h+var_E0]
0x180085dc2  mov     [rsp+208h+var_E0], eax
0x180085dc9  cmp     [rsi+8], rdi
0x180085dcd  jz      loc_180085FC7
0x180085dd3  mov     [rsp+208h+var_E0], edi
0x180085dda  cmp     qword ptr [r15+18h], 8
0x180085ddf  jb      short loc_180085DE4
0x180085de1  mov     r15, [r15]
0x180085de4  mov     r8, r15; unsigned __int16 *
0x180085de7  mov     rdx, [rsp+208h+var_1B0]; unsigned __int64
0x180085dec  mov     rcx, [rsi]; unsigned __int16 *
0x180085def  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180085df4  mov     [rsp+208h+var_E0], eax
0x180085dfb  test    eax, eax
0x180085dfd  js      loc_180085F45
0x180085e03  mov     [rsp+208h+var_E0], eax
0x180085e0a  cmp     qword ptr [r12+18h], 8
0x180085e10  jb      short loc_180085E16
0x180085e12  mov     r12, [r12]
0x180085e16  mov     r8, r12; unsigned __int16 *
0x180085e19  mov     rdx, [rsp+208h+var_1B8]; unsigned __int64
0x180085e1e  mov     rcx, [rsi+8]; unsigned __int16 *
0x180085e22  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180085e27  mov     [rsp+208h+var_E0], eax
0x180085e2e  test    eax, eax
0x180085e30  js      loc_180085F86
0x180085e36  mov     [rsp+208h+var_E0], eax
0x180085e3d  cmp     [rbx+69h], dil
0x180085e41  jnz     short loc_180085E91
0x180085e43  mov     rax, [rbx+10h]
0x180085e47  cmp     [rax+69h], dil
0x180085e4b  jnz     short loc_180085E6F
0x180085e4d  mov     rbx, rax
0x180085e50  mov     [rsp+208h+var_198], rax
0x180085e55  mov     rax, [rbx]
0x180085e58  cmp     [rax+69h], dil
0x180085e5c  jnz     short loc_180085E68
0x180085e5e  mov     rbx, rax
0x180085e61  mov     [rsp+208h+var_198], rax
0x180085e66  jmp     short loc_180085E55
0x180085e68  mov     [rsp+208h+var_1C8], rbx
0x180085e6d  jmp     short loc_180085E91
0x180085e6f  mov     rax, [rbx+8]
0x180085e73  cmp     [rax+69h], dil
0x180085e77  jnz     short loc_180085E89
0x180085e79  cmp     rbx, [rax+10h]
0x180085e7d  jnz     short loc_180085E89
0x180085e7f  mov     rbx, rax
0x180085e82  mov     [rsp+208h+var_1C8], rax
0x180085e87  jmp     short loc_180085E6F
0x180085e89  mov     rbx, rax
0x180085e8c  mov     [rsp+208h+var_1C8], rax
0x180085e91  add     rsi, 10h
0x180085e95  mov     [rsp+208h+var_190], rsi
0x180085e9a  mov     r15, [rsp+208h+var_1A8]
0x180085e9f  jmp     loc_180085D14
0x180085ea4  jmp     loc_180085D2A
0x180085ea9  jmp     loc_180085D2A
0x180085eae  jmp     loc_180085D2A
0x180085eb3  mov     [rsp+208h+var_E0], eax
0x180085eba  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180085ec1  mov     [rsp+208h+var_E8], rax
0x180085ec9  lea     rcx, [rsp+208h+var_E8]; this
0x180085ed1  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180085ed6  mov     rcx, [rsp+208h+var_38]
0x180085ede  xor     rcx, rsp; StackCookie
0x180085ee1  call    __security_check_cookie
0x180085ee6  lea     r11, [rsp+208h+var_28]
0x180085eee  mov     rbx, [r11+40h]
0x180085ef2  mov     rsi, [r11+48h]
0x180085ef6  mov     rsp, r11
0x180085ef9  pop     r15
0x180085efb  pop     r14
0x180085efd  pop     r13
0x180085eff  pop     r12
0x180085f01  pop     rdi
0x180085f02  retn
0x180085f03  lea     rcx, [rsp+208h+var_E8]; this
0x180085f0b  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180085f10  mov     edx, eax; int
0x180085f12  lea     rcx, [rsp+208h+var_E8]; this
0x180085f1a  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180085f1f  lea     rcx, [rsp+208h+var_E8]; this
0x180085f27  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180085f2c  mov     r8d, eax; char
0x180085f2f  xor     r9d, r9d; unsigned __int16 *
0x180085f32  mov     edx, 22Ah; unsigned int
0x180085f37  lea     rcx, [rsp+208h+var_E8]; this
0x180085f3f  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180085f45  lea     rcx, [rsp+208h+var_E8]; this
0x180085f4d  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180085f52  mov     edx, eax; int
0x180085f54  lea     rcx, [rsp+208h+var_E8]; this
0x180085f5c  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180085f61  lea     rcx, [rsp+208h+var_E8]; this
0x180085f69  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180085f6e  mov     r8d, eax; char
0x180085f71  xor     r9d, r9d; unsigned __int16 *
0x180085f74  mov     edx, 21Ch; unsigned int
0x180085f79  lea     rcx, [rsp+208h+var_E8]; this
0x180085f81  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180085f86  lea     rcx, [rsp+208h+var_E8]; this
0x180085f8e  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180085f93  mov     edx, eax; int
0x180085f95  lea     rcx, [rsp+208h+var_E8]; this
0x180085f9d  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180085fa2  lea     rcx, [rsp+208h+var_E8]; this
0x180085faa  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180085faf  mov     r8d, eax; char
0x180085fb2  xor     r9d, r9d; unsigned __int16 *
0x180085fb5  mov     edx, 21Dh; unsigned int
0x180085fba  lea     rcx, [rsp+208h+var_E8]; this
0x180085fc2  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180085fc7  mov     edx, 8007000Eh; int
0x180085fcc  lea     rcx, [rsp+208h+var_E8]; this
0x180085fd4  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180085fd9  lea     rcx, [rsp+208h+var_E8]; this
0x180085fe1  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180085fe6  mov     r8d, eax; char
0x180085fe9  xor     r9d, r9d; unsigned __int16 *
0x180085fec  mov     edx, 21Ah; unsigned int
0x180085ff1  lea     rcx, [rsp+208h+var_E8]; this
0x180085ff9  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180085ffe  mov     edx, 8007000Eh; int
0x180086003  lea     rcx, [rsp+208h+var_E8]; this
0x18008600b  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180086010  lea     rcx, [rsp+208h+var_E8]; this
0x180086018  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18008601d  mov     r8d, eax; char
0x180086020  xor     r9d, r9d; unsigned __int16 *
0x180086023  mov     edx, 218h; unsigned int
0x180086028  lea     rcx, [rsp+208h+var_E8]; this
0x180086030  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180086035  mov     edx, 8007000Eh; int
0x18008603a  lea     rcx, [rsp+208h+var_E8]; this
0x180086042  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180086047  lea     rcx, [rsp+208h+var_E8]; this
0x18008604f  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180086054  mov     r8d, eax; char
0x180086057  xor     r9d, r9d; unsigned __int16 *
0x18008605a  mov     edx, 20Ah; unsigned int
0x18008605f  lea     rcx, [rsp+208h+var_E8]; this
0x180086067  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18008606c  mov     edx, 8007000Eh; int
0x180086071  lea     rcx, [rsp+208h+var_E8]; this
0x180086079  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18008607e  lea     rcx, [rsp+208h+var_E8]; this
0x180086086  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18008608b  mov     r8d, eax; char
0x18008608e  xor     r9d, r9d; unsigned __int16 *
0x180086091  mov     edx, 205h; unsigned int
0x180086096  lea     rcx, [rsp+208h+var_E8]; this
0x18008609e  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
