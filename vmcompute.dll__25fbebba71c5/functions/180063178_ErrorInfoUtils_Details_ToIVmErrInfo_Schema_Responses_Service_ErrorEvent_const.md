# ErrorInfoUtils::Details::ToIVmErrInfo(Schema::Responses::Service::ErrorEvent const &)

- ea: `0x180063178`
- end: `0x180063831`
- name: `?ToIVmErrInfo@Details@ErrorInfoUtils@@YA?AV?$VmComPtr@UIVmErrInfo@@@Vml@@AEBUErrorEvent@Service@Responses@Schema@@@Z`
- size: `1721`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180062fb0`

## callees

- `0x180002f50`
- `0x180002f74`
- `0x180003c78`
- `0x180006158`
- `0x18000d108`
- `0x18000e894`
- `0x180017ce8`
- `0x1800183f4`
- `0x180022cd4`
- `0x180023474`
- `0x180024e34`
- `0x18002e898`
- `0x18002ed68`
- `0x18003778c`
- `0x18005b5d4`
- `0x180061b4c`
- `0x18006263c`
- `0x180062738`
- `0x180062808`
- `0x1800628fc`
- `0x1800629f0`
- `0x180062ae4`
- `0x180062d2c`
- `0x180062dac`
- `0x180062e64`
- `0x1800630c4`
- `0x180063178`
- `0x1800639f8`
- `0x180086010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x1800634c5`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x1800634c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063662`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063662`
- `OLEAUT32!__imp_SysFreeString` at `0x180063720`
- `OLEAUT32!__imp_SysFreeString` at `0x180063720`

## string_xrefs

- `0x180063778`: `onecore\vm\common\errorinfoutils\vmerrorinfo.cpp`
- `0x1800637a5`: `onecore\vm\common\errorinfoutils\vmerrorinfo.cpp`
- `0x1800637bd`: `onecore\vm\common\errorinfoutils\vmerrorinfo.cpp`
- `0x1800637d5`: `onecore\vm\common\errorinfoutils\vmerrorinfo.cpp`
- `0x18006380a`: `onecore\vm\common\errorinfoutils\vmerrorinfo.cpp`
- `0x18006381f`: `onecore\vm\common\errorinfoutils\vmerrorinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
LPVOID *__fastcall ErrorInfoUtils::Details::ToIVmErrInfo(LPVOID *a1, __int64 a2)
{
  __int64 v2; // r14
  int v4; // r15d
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rdi
  _QWORD *v7; // rbx
  void *v8; // rax
  unsigned __int64 v9; // rbx
  char *v10; // rdi
  size_t v11; // rbx
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rdi
  _QWORD *v14; // rcx
  void *v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rdi
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  wchar_t *v23; // rax
  int v24; // r8d
  _QWORD *v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // r12
  const wchar_t *v29; // rcx
  __int64 v30; // r15
  int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  HRESULT Instance; // eax
  LPVOID v37; // rcx
  __int64 (__fastcall *v38)(LPVOID, __int64, __int128 *, _QWORD); // r11
  int v39; // eax
  const unsigned __int16 *v40; // rdx
  wchar_t *v41; // rbx
  int v42; // eax
  unsigned int v44; // eax
  int ppv; // [rsp+20h] [rbp-99h]
  int ppva; // [rsp+20h] [rbp-99h]
  int ppvb; // [rsp+20h] [rbp-99h]
  char *v48; // [rsp+28h] [rbp-91h]
  __int128 v49; // [rsp+50h] [rbp-69h] BYREF
  __int64 v50; // [rsp+60h] [rbp-59h]
  int v51; // [rsp+68h] [rbp-51h]
  void *v52[2]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v53; // [rsp+80h] [rbp-39h]
  __int128 v54; // [rsp+88h] [rbp-31h] BYREF
  LPVOID *v55; // [rsp+98h] [rbp-21h]
  wchar_t *EndPtr; // [rsp+A0h] [rbp-19h] BYREF
  int v57[4]; // [rsp+A8h] [rbp-11h] BYREF
  char *v58; // [rsp+B8h] [rbp-1h]
  __int128 v59; // [rsp+C0h] [rbp+7h] BYREF
  _QWORD *v60; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v2 = a2;
  v55 = a1;
  v4 = 0;
  v51 = 0;
  v5 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(a2 + 128) - *(_QWORD *)(a2 + 120)) >> 3);
  *(_OWORD *)v57 = 0;
  v58 = 0;
  if ( v5 )
  {
    if ( v5 > 0xFFFFFFFFFFFFFFFLL )
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Xlength();
    v6 = 16 * v5;
    if ( 16 * v5 )
    {
      if ( v6 < 0x1000 )
      {
        v7 = operator new(16 * v5);
      }
      else
      {
        if ( v6 + 39 < v6 )
          __scrt_throw_std_bad_array_new_length();
        v8 = operator new(v6 + 39);
        if ( !v8 )
          __fastfail(5u);
        v7 = (_QWORD *)(((unsigned __int64)v8 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v7 - 1) = v8;
      }
    }
    else
    {
      v7 = 0;
    }
    *(_QWORD *)v57 = v7;
    v58 = (char *)&v7[v6 / 8];
    LOBYTE(a2) = 0;
    memset_0(v7, a2, 16 * v5);
    do
    {
      v7 += 2;
      --v5;
    }
    while ( v5 );
    *(_QWORD *)&v57[2] = v7;
    EndPtr = 0;
    std::_Tidy_guard<std::vector<_EVENT_DATA_DESCRIPTOR>>::~_Tidy_guard<std::vector<_EVENT_DATA_DESCRIPTOR>>(&EndPtr);
  }
  v9 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v2 + 128) - *(_QWORD *)(v2 + 120)) >> 3);
  *(_OWORD *)v52 = 0;
  v53 = 0;
  if ( v9 )
  {
    std::vector<unsigned int>::_Buy_nonzero(v52, v9);
    v10 = (char *)v52[0];
    v11 = 4 * v9;
    memset_0(v52[0], 0, v11);
    v52[1] = &v10[v11];
    EndPtr = 0;
    std::_Tidy_guard<std::vector<unsigned int>>::~_Tidy_guard<std::vector<unsigned int>>(&EndPtr);
  }
  v12 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v2 + 128) - *(_QWORD *)(v2 + 120)) >> 3);
  v59 = 0;
  v60 = 0;
  if ( v12 )
  {
    if ( v12 > 0xAAAAAAAAAAAAAAALL )
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Xlength();
    v13 = 24 * v12;
    if ( 24 * v12 )
    {
      if ( v13 < 0x1000 )
      {
        v14 = operator new(24 * v12);
      }
      else
      {
        if ( v13 + 39 < v13 )
          __scrt_throw_std_bad_array_new_length();
        v15 = operator new(v13 + 39);
        if ( !v15 )
          __fastfail(5u);
        v14 = (_QWORD *)(((unsigned __int64)v15 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v14 - 1) = v15;
      }
    }
    else
    {
      v14 = 0;
    }
    *(_QWORD *)&v59 = v14;
    v60 = &v14[v13 / 8];
    do
    {
      *v14 = 0;
      v14[1] = 0;
      v14[2] = 0;
      v14 += 3;
      --v12;
    }
    while ( v12 );
    *((_QWORD *)&v59 + 1) = v14;
  }
  v16 = 0;
  v17 = *(_QWORD *)(v2 + 120);
  *(_QWORD *)&v54 = *(_QWORD *)(v2 + 128);
  if ( v17 != (_QWORD)v54 )
  {
    while ( 1 )
    {
      v18 = *(_DWORD *)v17;
      *((_DWORD *)v52[0] + v16) = *(_DWORD *)v17;
      if ( v18 > 7 )
        break;
      if ( v18 == 7 )
      {
        v28 = *(_QWORD *)v57;
        EndPtr = 0;
        v29 = (const wchar_t *)(v17 + 8);
        if ( *(_QWORD *)(v17 + 32) > 7u )
          v29 = *(const wchar_t **)v29;
        v30 = _wcstoi64(v29, &EndPtr, 0);
        if ( *EndPtr )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE6,
            (unsigned int)"onecore\\vm\\common\\errorinfoutils\\vmerrorinfo.cpp",
            (const char *)0x8007000DLL,
            ppv);
        if ( (unsigned __int64)(v30 + 0x80000000LL) > 0xFFFFFFFF )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE8,
            (unsigned int)"onecore\\vm\\common\\errorinfoutils\\vmerrorinfo.cpp",
            (const char *)0x8007000DLL,
            ppv);
        v49 = 0;
        v50 = 0;
        std::vector<unsigned char>::vector<unsigned char>(&v49, 4);
        *(_DWORD *)v49 = v30;
        v31 = DWORD2(v49) - v49;
        *(_QWORD *)(v28 + 16 * v16) = v49;
        *(_DWORD *)(v28 + 16 * v16 + 8) = v31;
        *(_DWORD *)(v28 + 16 * v16 + 12) = 0;
        v4 = v51 | 6;
        v51 |= 6u;
        std::vector<unsigned char>::operator=(v59 + 24 * v16, &v49);
        std::vector<unsigned char>::~vector<unsigned char>(&v49);
        goto LABEL_61;
      }
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( !v19 )
        {
          v24 = 2 * *(_DWORD *)(v17 + 24) + 2;
          v25 = (_QWORD *)(v17 + 8);
          if ( *(_QWORD *)(v17 + 32) > 7u )
            v25 = (_QWORD *)*v25;
          v26 = 2 * v16;
          v27 = *(_QWORD *)v57;
          *(_QWORD *)(*(_QWORD *)v57 + 8 * v26) = v25;
          *(_DWORD *)(v27 + 8 * v26 + 8) = v24;
          *(_DWORD *)(v27 + 8 * v26 + 12) = 0;
          goto LABEL_61;
        }
        v20 = v19 - 1;
        if ( v20 )
        {
          v21 = v20 - 2;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              if ( v22 != 1 )
                goto LABEL_79;
              v23 = (wchar_t *)ErrorInfoUtils::Details::UIntDescriptorFromString<unsigned short>(
                                 &v49,
                                 v17 + 8,
                                 *(_QWORD *)v57 + 16 * v16);
            }
            else
            {
              v23 = ErrorInfoUtils::Details::IntDescriptorFromString<short>(
                      (wchar_t *)&v49,
                      v17 + 8,
                      *(_QWORD *)v57 + 16 * v16);
            }
          }
          else
          {
            v23 = (wchar_t *)ErrorInfoUtils::Details::UIntDescriptorFromString<unsigned char>(
                               &v49,
                               v17 + 8,
                               *(_QWORD *)v57 + 16 * v16);
          }
        }
        else
        {
          v23 = (wchar_t *)ErrorInfoUtils::Details::AnsiStringDescriptorFromString(
                             &v49,
                             v17 + 8,
                             *(_QWORD *)v57 + 16 * v16);
        }
        goto LABEL_60;
      }
LABEL_61:
      ++v16;
      v17 += 40;
      if ( v17 == (_QWORD)v54 )
        goto LABEL_62;
    }
    v32 = v18 - 8;
    if ( v32 )
    {
      v33 = v32 - 1;
      if ( v33 )
      {
        v34 = v33 - 1;
        if ( v34 )
        {
          v35 = v34 - 4;
          if ( v35 )
          {
            if ( v35 != 1 )
            {
LABEL_79:
              v44 = wil::verify_hresult<long>(2147942413LL);
              LODWORD(v48) = *(_DWORD *)v17;
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x16C,
                (unsigned int)"onecore\\vm\\common\\errorinfoutils\\vmerrorinfo.cpp",
                (const char *)v44,
                (int)"Unsupported data type (%u)",
                v48);
            }
            v23 = (wchar_t *)ErrorInfoUtils::Details::GuidDescriptorFromString(&v49, v17 + 8, *(_QWORD *)v57 + 16 * v16);
          }
          else
          {
            v23 = (wchar_t *)ErrorInfoUtils::Details::BinaryDescriptorFromHexString(
                               &v49,
                               v17 + 8,
                               *(_QWORD *)v57 + 16 * v16);
          }
        }
        else
        {
          v23 = (wchar_t *)ErrorInfoUtils::Details::UIntDescriptorFromString<unsigned __int64>(
                             &v49,
                             v17 + 8,
                             *(_QWORD *)v57 + 16 * v16);
        }
      }
      else
      {
        v23 = ErrorInfoUtils::Details::IntDescriptorFromString<__int64>(
                (wchar_t *)&v49,
                v17 + 8,
                *(_QWORD *)v57 + 16 * v16);
      }
    }
    else
    {
      v23 = (wchar_t *)ErrorInfoUtils::Details::UIntDescriptorFromString<unsigned int>(
                         &v49,
                         v17 + 8,
                         *(_QWORD *)v57 + 16 * v16);
    }
LABEL_60:
    std::vector<unsigned char>::operator=(v59 + 24 * v16, v23);
    std::vector<unsigned char>::~vector<unsigned char>(&v49);
    goto LABEL_61;
  }
LABEL_62:
  *a1 = 0;
  v51 = v4 | 1;
  Instance = CoCreateInstance(&CLSID_VmErrInfo, 0, 0x17u, &GUID_758f8814_50a5_44fe_8266_c908cde5e74d, a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x175,
      (unsigned int)"onecore\\vm\\common\\errorinfoutils\\vmerrorinfo.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  v37 = *a1;
  v38 = *(__int64 (__fastcall **)(LPVOID, __int64, __int128 *, _QWORD))(*(_QWORD *)*a1 + 64LL);
  v54 = 0;
  ppvb = v57[0];
  v39 = v38(v37, v2 + 64, &v54, *(unsigned __int16 *)(v2 + 80));
  if ( v39 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17E,
      (unsigned int)"onecore\\vm\\common\\errorinfoutils\\vmerrorinfo.cpp",
      (const char *)(unsigned int)v39,
      ppvb);
  if ( *(_QWORD *)(v2 + 104) )
  {
    EndPtr = 0;
    v40 = (const unsigned __int16 *)(v2 + 88);
    if ( *(_QWORD *)(v2 + 112) > 7u )
      v40 = *(const unsigned __int16 **)v40;
    Vml::VmBstr::VmBstr((Vml::VmBstr *)&EndPtr, v40);
    v41 = EndPtr;
    v42 = (*(__int64 (__fastcall **)(LPVOID, wchar_t *))(*(_QWORD *)*a1 + 120LL))(*a1, EndPtr);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecore\\vm\\common\\errorinfoutils\\vmerrorinfo.cpp",
        (const char *)(unsigned int)v42,
        ppvb);
    if ( v41 )
      SysFreeString(v41);
  }
  std::vector<std::vector<unsigned char>>::_Tidy(&v59);
  std::vector<enum Schema::Requests::System::PropertyType>::~vector<enum Schema::Requests::System::PropertyType>(v52);
  std::vector<_GUID>::~vector<_GUID>(v57);
  return a1;
}

```

## disassembly

```asm
0x180063178  mov     [rsp-8+arg_10], rbx
0x18006317d  push    rbp
0x18006317e  push    rsi
0x18006317f  push    rdi
0x180063180  push    r12
0x180063182  push    r13
0x180063184  push    r14
0x180063186  push    r15
0x180063188  lea     rbp, [rsp-27h]
0x18006318d  sub     rsp, 0E0h
0x180063194  mov     rax, cs:__security_cookie
0x18006319b  xor     rax, rsp
0x18006319e  mov     [rbp+57h+var_38], rax
0x1800631a2  mov     r14, rdx
0x1800631a5  mov     r13, rcx
0x1800631a8  mov     [rbp+57h+var_78], rcx
0x1800631ac  xor     r12d, r12d
0x1800631af  mov     r15d, r12d
0x1800631b2  mov     [rbp+57h+var_A8], r12d
0x1800631b6  xorps   xmm0, xmm0
0x1800631b9  mov     rsi, [rdx+80h]
0x1800631c0  sub     rsi, [rdx+78h]
0x1800631c4  sar     rsi, 3
0x1800631c8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800631d2  imul    rsi, rax
0x1800631d6  movdqu  xmmword ptr [rbp+57h+var_68], xmm0
0x1800631db  mov     [rbp+57h+var_58], r12
0x1800631df  test    rsi, rsi
0x1800631e2  jz      loc_18006327F
0x1800631e8  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800631f2  cmp     rsi, rax
0x1800631f5  ja      loc_18006378A
0x1800631fb  mov     rdi, rsi
0x1800631fe  shl     rdi, 4
0x180063202  test    rdi, rdi
0x180063205  jnz     short loc_18006320C
0x180063207  mov     ebx, r12d
0x18006320a  jmp     short loc_18006324A
0x18006320c  cmp     rdi, 1000h
0x180063213  jb      short loc_18006323F
0x180063215  lea     rcx, [rdi+27h]; Size
0x180063219  cmp     rcx, rdi
0x18006321c  jbe     loc_180063790
0x180063222  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180063227  test    rax, rax
0x18006322a  jnz     short loc_180063231
0x18006322c  lea     ecx, [rax+5]
0x18006322f  int     29h; Win8: RtlFailFast(ecx)
0x180063231  lea     rbx, [rax+27h]
0x180063235  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180063239  mov     [rbx-8], rax
0x18006323d  jmp     short loc_18006324A
0x18006323f  mov     rcx, rdi; Size
0x180063242  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180063247  mov     rbx, rax
0x18006324a  mov     qword ptr [rbp+57h+var_68], rbx
0x18006324e  lea     rax, [rdi+rbx]
0x180063252  mov     [rbp+57h+var_58], rax
0x180063256  mov     r8, rdi; Size
0x180063259  xor     dl, dl; Val
0x18006325b  mov     rcx, rbx; void *
0x18006325e  call    memset_0
0x180063263  add     rbx, 10h
0x180063267  sub     rsi, 1
0x18006326b  jnz     short loc_180063263
0x18006326d  mov     qword ptr [rbp+57h+var_68+8], rbx
0x180063271  mov     [rbp+57h+EndPtr], r12
0x180063275  lea     rcx, [rbp+57h+EndPtr]
0x180063279  call    ??1?$_Tidy_guard@V?$vector@U_EVENT_DATA_DESCRIPTOR@@V?$allocator@U_EVENT_DATA_DESCRIPTOR@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<_EVENT_DATA_DESCRIPTOR>>::~_Tidy_guard<std::vector<_EVENT_DATA_DESCRIPTOR>>(void)
0x18006327e  nop
0x18006327f  xorps   xmm0, xmm0
0x180063282  mov     rbx, [r14+80h]
0x180063289  sub     rbx, [r14+78h]
0x18006328d  sar     rbx, 3
0x180063291  mov     rsi, 0CCCCCCCCCCCCCCCDh
0x18006329b  imul    rbx, rsi
0x18006329f  movdqu  xmmword ptr [rbp+57h+var_A0], xmm0
0x1800632a4  mov     [rbp+57h+var_90], r12
0x1800632a8  test    rbx, rbx
0x1800632ab  jz      short loc_1800632E4
0x1800632ad  mov     rdx, rbx
0x1800632b0  lea     rcx, [rbp+57h+var_A0]
0x1800632b4  call    ?_Buy_nonzero@?$vector@IV?$allocator@I@std@@@std@@AEAAX_K@Z; std::vector<uint>::_Buy_nonzero(unsigned __int64)
0x1800632b9  mov     rdi, [rbp+57h+var_A0]
0x1800632bd  shl     rbx, 2
0x1800632c1  mov     r8, rbx; Size
0x1800632c4  xor     edx, edx; Val
0x1800632c6  mov     rcx, rdi; void *
0x1800632c9  call    memset_0
0x1800632ce  lea     rax, [rbx+rdi]
0x1800632d2  mov     [rbp+57h+var_A0+8], rax
0x1800632d6  mov     [rbp+57h+EndPtr], r12
0x1800632da  lea     rcx, [rbp+57h+EndPtr]
0x1800632de  call    ??1?$_Tidy_guard@V?$vector@IV?$allocator@I@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uint>>::~_Tidy_guard<std::vector<uint>>(void)
0x1800632e3  nop
0x1800632e4  xorps   xmm0, xmm0
0x1800632e7  mov     rbx, [r14+80h]
0x1800632ee  sub     rbx, [r14+78h]
0x1800632f2  sar     rbx, 3
0x1800632f6  imul    rbx, rsi
0x1800632fa  movdqu  [rbp+57h+var_50], xmm0
0x1800632ff  mov     [rbp+57h+var_40], r12
0x180063303  test    rbx, rbx
0x180063306  jz      loc_180063398
0x18006330c  mov     rax, 0AAAAAAAAAAAAAAAh
0x180063316  cmp     rbx, rax
0x180063319  ja      loc_180063796
0x18006331f  lea     rax, [rbx+rbx*2]
0x180063323  lea     rdi, ds:0[rax*8]
0x18006332b  test    rdi, rdi
0x18006332e  jnz     short loc_180063335
0x180063330  mov     rcx, r12
0x180063333  jmp     short loc_180063373
0x180063335  cmp     rdi, 1000h
0x18006333c  jb      short loc_180063368
0x18006333e  lea     rcx, [rdi+27h]; Size
0x180063342  cmp     rcx, rdi
0x180063345  jbe     loc_18006379C
0x18006334b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180063350  test    rax, rax
0x180063353  jnz     short loc_18006335A
0x180063355  lea     ecx, [rax+5]
0x180063358  int     29h; Win8: RtlFailFast(ecx)
0x18006335a  lea     rcx, [rax+27h]
0x18006335e  and     rcx, 0FFFFFFFFFFFFFFE0h
0x180063362  mov     [rcx-8], rax
0x180063366  jmp     short loc_180063373
0x180063368  mov     rcx, rdi; Size
0x18006336b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180063370  mov     rcx, rax
0x180063373  mov     qword ptr [rbp+57h+var_50], rcx
0x180063377  lea     rax, [rdi+rcx]
0x18006337b  mov     [rbp+57h+var_40], rax
0x18006337f  mov     [rcx], r12
0x180063382  mov     [rcx+8], r12
0x180063386  mov     [rcx+10h], r12
0x18006338a  add     rcx, 18h
0x18006338e  sub     rbx, 1
0x180063392  jnz     short loc_18006337F
0x180063394  mov     qword ptr [rbp+57h+var_50+8], rcx
0x180063398  mov     rbx, r12
0x18006339b  mov     rdi, [r14+78h]
0x18006339f  mov     rax, [r14+80h]
0x1800633a6  mov     qword ptr [rbp+57h+var_88], rax
0x1800633aa  cmp     rdi, rax
0x1800633ad  jz      loc_18006363D
0x1800633b3  mov     ecx, [rdi]
0x1800633b5  mov     rax, [rbp+57h+var_A0]
0x1800633b9  mov     [rax+rbx*4], ecx
0x1800633bc  cmp     ecx, 7
0x1800633bf  ja      loc_18006356E
0x1800633c5  jz      loc_18006349E
0x1800633cb  test    ecx, ecx
0x1800633cd  jz      loc_18006362C
0x1800633d3  sub     ecx, 1
0x1800633d6  jz      loc_180063468
0x1800633dc  sub     ecx, 1
0x1800633df  jz      short loc_18006344B
0x1800633e1  sub     ecx, 2
0x1800633e4  jz      short loc_18006342E
0x1800633e6  sub     ecx, 1
0x1800633e9  jz      short loc_180063411
0x1800633eb  cmp     ecx, 1
0x1800633ee  jnz     loc_1800637E7
0x1800633f4  mov     r8, rbx
0x1800633f7  shl     r8, 4
0x1800633fb  add     r8, qword ptr [rbp+57h+var_68]
0x1800633ff  lea     rdx, [rdi+8]
0x180063403  lea     rcx, [rbp+57h+var_C0]
0x180063407  call    ??$UIntDescriptorFromString@G@Details@ErrorInfoUtils@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAU_EVENT_DATA_DESCRIPTOR@@@Z; ErrorInfoUtils::Details::UIntDescriptorFromString<ushort>(std::wstring const &,_EVENT_DATA_DESCRIPTOR *)
0x18006340c  jmp     loc_18006360F
0x180063411  mov     r8, rbx
0x180063414  shl     r8, 4
0x180063418  add     r8, qword ptr [rbp+57h+var_68]
0x18006341c  lea     rdx, [rdi+8]
0x180063420  lea     rcx, [rbp+57h+var_C0]
0x180063424  call    ??$IntDescriptorFromString@F@Details@ErrorInfoUtils@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAU_EVENT_DATA_DESCRIPTOR@@@Z; ErrorInfoUtils::Details::IntDescriptorFromString<short>(std::wstring const &,_EVENT_DATA_DESCRIPTOR *)
0x180063429  jmp     loc_18006360F
0x18006342e  mov     r8, rbx
0x180063431  shl     r8, 4
0x180063435  add     r8, qword ptr [rbp+57h+var_68]
0x180063439  lea     rdx, [rdi+8]
0x18006343d  lea     rcx, [rbp+57h+var_C0]
0x180063441  call    ??$UIntDescriptorFromString@E@Details@ErrorInfoUtils@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAU_EVENT_DATA_DESCRIPTOR@@@Z; ErrorInfoUtils::Details::UIntDescriptorFromString<uchar>(std::wstring const &,_EVENT_DATA_DESCRIPTOR *)
0x180063446  jmp     loc_18006360F
0x18006344b  mov     r8, rbx
0x18006344e  shl     r8, 4
0x180063452  add     r8, qword ptr [rbp+57h+var_68]
0x180063456  lea     rdx, [rdi+8]
0x18006345a  lea     rcx, [rbp+57h+var_C0]
0x18006345e  call    ?AnsiStringDescriptorFromString@Details@ErrorInfoUtils@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEAU_EVENT_DATA_DESCRIPTOR@@@Z; ErrorInfoUtils::Details::AnsiStringDescriptorFromString(std::wstring const &,_EVENT_DATA_DESCRIPTOR *)
0x180063463  jmp     loc_18006360F
0x180063468  mov     eax, [rdi+18h]
0x18006346b  lea     r8d, ds:2[rax*2]
0x180063473  lea     rdx, [rdi+8]
0x180063477  cmp     qword ptr [rdx+18h], 7
0x18006347c  jbe     short loc_180063481
0x18006347e  mov     rdx, [rdx]
0x180063481  mov     rcx, rbx
0x180063484  add     rcx, rcx
0x180063487  mov     rax, qword ptr [rbp+57h+var_68]
0x18006348b  mov     [rax+rcx*8], rdx
0x18006348f  mov     [rax+rcx*8+8], r8d
0x180063494  mov     [rax+rcx*8+0Ch], r12d
0x180063499  jmp     loc_18006362C
0x18006349e  mov     rsi, rbx
0x1800634a1  add     rsi, rsi
0x1800634a4  mov     r12, qword ptr [rbp+57h+var_68]
0x1800634a8  mov     [rbp+57h+EndPtr], 0
0x1800634b0  lea     rcx, [rdi+8]
0x1800634b4  cmp     qword ptr [rcx+18h], 7
0x1800634b9  jbe     short loc_1800634BE
0x1800634bb  mov     rcx, [rcx]; String
0x1800634be  xor     r8d, r8d; Radix
0x1800634c1  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x1800634c5  call    cs:__imp__wcstoi64
0x1800634cc  nop     dword ptr [rax+rax+00h]
0x1800634d1  mov     r15, rax
0x1800634d4  mov     rcx, [rbp+5Fh]; this
0x1800634d8  mov     rax, [rbp+57h+EndPtr]
0x1800634dc  xor     edx, edx
0x1800634de  cmp     [rax], dx
0x1800634e1  jnz     loc_1800637CF
0x1800634e7  mov     rcx, [rbp+5Fh]; this
0x1800634eb  mov     eax, 80000000h
0x1800634f0  add     rax, r15
0x1800634f3  mov     edx, 0FFFFFFFFh
0x1800634f8  cmp     rax, rdx
0x1800634fb  ja      loc_1800637B7
0x180063501  xorps   xmm0, xmm0
0x180063504  xor     eax, eax
0x180063506  movups  [rbp+57h+var_C0], xmm0
0x18006350a  mov     [rbp+57h+var_B0], rax
0x18006350e  lea     edx, [rax+4]
0x180063511  lea     rcx, [rbp+57h+var_C0]
0x180063515  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18006351a  mov     rax, qword ptr [rbp+57h+var_C0]
0x18006351e  mov     [rax], r15d
0x180063521  mov     ecx, dword ptr [rbp+57h+var_C0+8]
0x180063524  mov     rax, qword ptr [rbp+57h+var_C0]
0x180063528  sub     ecx, eax
0x18006352a  mov     [r12+rsi*8], rax
0x18006352e  mov     [r12+rsi*8+8], ecx
0x180063533  mov     dword ptr [r12+rsi*8+0Ch], 0
0x18006353c  mov     r15d, [rbp+57h+var_A8]
0x180063540  or      r15d, 6
0x180063544  mov     [rbp+57h+var_A8], r15d
0x180063548  lea     rcx, [rbx+rbx*2]
0x18006354c  mov     rax, qword ptr [rbp+57h+var_50]
0x180063550  lea     rcx, [rax+rcx*8]
0x180063554  lea     rdx, [rbp+57h+var_C0]
0x180063558  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x18006355d  lea     rcx, [rbp+57h+var_C0]
0x180063561  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180063566  xor     r12d, r12d
0x180063569  jmp     loc_18006362C
0x18006356e  sub     ecx, 8
0x180063571  jz      loc_1800635F7
0x180063577  sub     ecx, 1
0x18006357a  jz      short loc_1800635DD
0x18006357c  sub     ecx, 1
0x18006357f  jz      short loc_1800635C3
0x180063581  sub     ecx, 4
0x180063584  jz      short loc_1800635A9
0x180063586  cmp     ecx, 1
0x180063589  jnz     loc_1800637E7
0x18006358f  mov     r8, rbx
0x180063592  shl     r8, 4
0x180063596  add     r8, qword ptr [rbp+57h+var_68]
0x18006359a  lea     rdx, [rdi+8]
0x18006359e  lea     rcx, [rbp+57h+var_C0]
0x1800635a2  call    ?GuidDescriptorFromString@Details@ErrorInfoUtils@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEAU_EVENT_DATA_DESCRIPTOR@@@Z; ErrorInfoUtils::Details::GuidDescriptorFromString(std::wstring const &,_EVENT_DATA_DESCRIPTOR *)
0x1800635a7  jmp     short loc_18006360F
0x1800635a9  mov     r8, rbx
0x1800635ac  shl     r8, 4
0x1800635b0  add     r8, qword ptr [rbp+57h+var_68]
0x1800635b4  lea     rdx, [rdi+8]
0x1800635b8  lea     rcx, [rbp+57h+var_C0]
0x1800635bc  call    ?BinaryDescriptorFromHexString@Details@ErrorInfoUtils@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEAU_EVENT_DATA_DESCRIPTOR@@@Z; ErrorInfoUtils::Details::BinaryDescriptorFromHexString(std::wstring const &,_EVENT_DATA_DESCRIPTOR *)
0x1800635c1  jmp     short loc_18006360F
0x1800635c3  mov     r8, rbx
0x1800635c6  shl     r8, 4
0x1800635ca  add     r8, qword ptr [rbp+57h+var_68]
0x1800635ce  lea     rdx, [rdi+8]
0x1800635d2  lea     rcx, [rbp+57h+var_C0]
0x1800635d6  call    ??$UIntDescriptorFromString@_K@Details@ErrorInfoUtils@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAU_EVENT_DATA_DESCRIPTOR@@@Z; ErrorInfoUtils::Details::UIntDescriptorFromString<unsigned __int64>(std::wstring const &,_EVENT_DATA_DESCRIPTOR *)
0x1800635db  jmp     short loc_18006360F
0x1800635dd  mov     r8, rbx
0x1800635e0  shl     r8, 4
0x1800635e4  add     r8, qword ptr [rbp+57h+var_68]
0x1800635e8  lea     rdx, [rdi+8]
0x1800635ec  lea     rcx, [rbp+57h+var_C0]
0x1800635f0  call    ??$IntDescriptorFromString@_J@Details@ErrorInfoUtils@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAU_EVENT_DATA_DESCRIPTOR@@@Z; ErrorInfoUtils::Details::IntDescriptorFromString<__int64>(std::wstring const &,_EVENT_DATA_DESCRIPTOR *)
0x1800635f5  jmp     short loc_18006360F
0x1800635f7  mov     r8, rbx
0x1800635fa  shl     r8, 4
0x1800635fe  add     r8, qword ptr [rbp+57h+var_68]
0x180063602  lea     rdx, [rdi+8]
0x180063606  lea     rcx, [rbp+57h+var_C0]
0x18006360a  call    ??$UIntDescriptorFromString@I@Details@ErrorInfoUtils@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAU_EVENT_DATA_DESCRIPTOR@@@Z; ErrorInfoUtils::Details::UIntDescriptorFromString<uint>(std::wstring const &,_EVENT_DATA_DESCRIPTOR *)
  ... truncated ...
```
