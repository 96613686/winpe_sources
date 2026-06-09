# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180010550`
- end: `0x1800108b8`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `872`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010094`
- `0x18001a69c`
- `0x18001a868`

## callees

- `0x1800032e0`
- `0x180003e40`
- `0x180004090`
- `0x18000458d`
- `0x1800045a5`
- `0x1800045d5`
- `0x1800045ed`
- `0x1800045f9`
- `0x1800066dc`
- `0x18000f944`
- `0x18000fd74`
- `0x18000ff00`
- `0x180010550`
- `0x1800115e0`
- `0x180029010`

## string_xrefs

- `0x1800105b8`: `combase.dll`
- `0x1800107f8`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const wchar_t *v13; // rdx
  unsigned __int64 v14; // r8
  LPCWSTR *v15; // r14
  char *v16; // rdi
  __int64 last_trivial_2; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rdi
  LPCWSTR *v20; // rcx
  unsigned __int64 v21; // rcx
  LPCWSTR *v22; // r8
  _WORD *v23; // rdi
  unsigned __int64 v24; // rdi
  LPCWSTR *v25; // rcx
  const WCHAR *v26; // rcx
  HMODULE v27; // rdi
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // r8
  LPCWSTR *v30; // rcx
  FARPROC v31; // rax
  unsigned int (__fastcall ***v33)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v36; // [rsp+50h] [rbp-28h]
  unsigned __int64 v37; // [rsp+58h] [rbp-20h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, __int64))winrt_activation_handler)(v8, a3, a4);
    return a1;
  }
  ActivationFactory_0 = RoGetActivationFactory_0(v8, a3, a4);
  if ( ActivationFactory_0 == -2147221008 )
  {
    Library = LoadLibraryExW_0(L"combase.dll", 0, 0x1000u);
    ProcAddress = WINRT_IMPL_GetProcAddress(Library, "CoIncrementMTAUsage");
    if ( !ProcAddress )
    {
      *a1 = -2147221008;
      return a1;
    }
    v33 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v33);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  *(_OWORD *)lpLibFileName = 0;
  v36 = 0;
  v37 = 0;
  v12 = *a2;
  if ( *a2 )
  {
    v13 = *(const wchar_t **)(v12 + 16);
    v14 = *(unsigned int *)(v12 + 4);
  }
  else
  {
    v13 = &WideCharStr;
    v14 = 0;
  }
  std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, v13, v14);
  while ( 1 )
  {
    do
    {
      v15 = lpLibFileName;
      if ( v37 > 7 )
        v15 = (LPCWSTR *)lpLibFileName[0];
      if ( !v36
        || (v16 = (char *)v15 + 2 * v36,
            last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46),
            (char *)last_trivial_2 == v16)
        || (v18 = (last_trivial_2 - (__int64)v15) >> 1, v18 == -1) )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_57;
      }
      v19 = v36;
      if ( v18 > v36 )
      {
        v21 = v18 - v36;
        if ( v18 - v36 > v37 - v36 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpLibFileName);
        }
        else
        {
          v36 = (last_trivial_2 - (__int64)v15) >> 1;
          v22 = lpLibFileName;
          if ( v37 > 7 )
            v22 = (LPCWSTR *)lpLibFileName[0];
          v23 = (_WORD *)v22 + v19;
          if ( v21 )
          {
            while ( v21 )
            {
              *v23++ = 0;
              --v21;
            }
          }
          *((_WORD *)v22 + v18) = 0;
        }
      }
      else
      {
        v36 = (last_trivial_2 - (__int64)v15) >> 1;
        v20 = lpLibFileName;
        if ( v37 > 7 )
          v20 = (LPCWSTR *)lpLibFileName[0];
        *((_WORD *)v20 + v18) = 0;
      }
      v24 = v36;
      if ( v37 - v36 < 4 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          lpLibFileName,
          4);
      }
      else
      {
        v36 += 4LL;
        v25 = lpLibFileName;
        if ( v37 > 7 )
          v25 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v25 + 2 * v24) = (LPCWSTR)0x6C006C0064002ELL;
        *((_WORD *)v25 + v24 + 4) = 0;
      }
      v26 = (const WCHAR *)lpLibFileName;
      if ( v37 > 7 )
        v26 = lpLibFileName[0];
      v27 = LoadLibraryExW_0(v26, 0, 0x1000u);
      v28 = v36;
      v29 = v36 - 4;
      v30 = lpLibFileName;
      if ( v36 >= 4 )
      {
        v36 -= 4LL;
        if ( v37 > 7 )
          v30 = (LPCWSTR *)lpLibFileName[0];
LABEL_45:
        *((_WORD *)v30 + v29) = 0;
        continue;
      }
      if ( v37 - v36 >= 0xFFFFFFFFFFFFFFFCuLL )
      {
        v36 -= 4LL;
        if ( v37 > 7 )
          v30 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v30 + 2 * v28) = 0;
        goto LABEL_45;
      }
      std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpLibFileName);
    }
    while ( !v27 );
    v31 = WINRT_IMPL_GetProcAddress(v27, "DllGetActivationFactory");
    if ( !v31 )
      goto LABEL_53;
    v33 = 0;
    if ( !((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v31)(
            *a2,
            &v33)
      && !(**v33)(v33, a3, a4) )
    {
      break;
    }
    if ( v33 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v33);
LABEL_53:
    WINRT_IMPL_FreeLibrary(v27);
  }
  *a1 = 0;
  if ( v33 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v33);
LABEL_57:
  std::wstring::~wstring(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180010550  push    rbp
0x180010552  push    rbx
0x180010553  push    rsi
0x180010554  push    rdi
0x180010555  push    r12
0x180010557  push    r13
0x180010559  push    r14
0x18001055b  push    r15
0x18001055d  mov     rbp, rsp
0x180010560  sub     rsp, 78h
0x180010564  mov     rax, cs:__security_cookie
0x18001056b  xor     rax, rsp
0x18001056e  mov     [rbp+var_18], rax
0x180010572  mov     r13, r9
0x180010575  mov     r12, r8
0x180010578  mov     r15, rdx
0x18001057b  mov     rsi, rcx
0x18001057e  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180010585  xor     r14d, r14d
0x180010588  mov     r8, r9
0x18001058b  mov     rdx, r12
0x18001058e  mov     rcx, [r15]
0x180010591  test    rax, rax
0x180010594  jz      short loc_1800105A2
0x180010596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001059b  mov     [rsi], eax
0x18001059d  jmp     loc_180010898
0x1800105a2  call    RoGetActivationFactory_0
0x1800105a7  mov     ebx, eax
0x1800105a9  cmp     eax, 800401F0h
0x1800105ae  jnz     short loc_180010600
0x1800105b0  xor     edx, edx; hFile
0x1800105b2  mov     r8d, 1000h; dwFlags
0x1800105b8  lea     rcx, LibFileName; "combase.dll"
0x1800105bf  call    LoadLibraryExW_0
0x1800105c4  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x1800105cb  mov     rcx, rax; hModule
0x1800105ce  call    WINRT_IMPL_GetProcAddress
0x1800105d3  test    rax, rax
0x1800105d6  jnz     short loc_1800105E3
0x1800105d8  mov     dword ptr [rsi], 800401F0h
0x1800105de  jmp     loc_180010898
0x1800105e3  mov     [rbp+var_48], r14
0x1800105e7  lea     rcx, [rbp+var_48]
0x1800105eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105f0  mov     r8, r13
0x1800105f3  mov     rdx, r12
0x1800105f6  mov     rcx, [r15]
0x1800105f9  call    RoGetActivationFactory_0
0x1800105fe  mov     ebx, eax
0x180010600  test    ebx, ebx
0x180010602  jnz     short loc_18001060C
0x180010604  mov     [rsi], r14d
0x180010607  jmp     loc_180010898
0x18001060c  mov     [rbp+pperrinfo], r14
0x180010610  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180010614  xor     ecx, ecx; dwReserved
0x180010616  call    GetErrorInfo_0
0x18001061b  xorps   xmm0, xmm0
0x18001061e  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x180010622  mov     [rbp+var_28], r14
0x180010626  mov     [rbp+var_20], r14
0x18001062a  mov     rax, [r15]
0x18001062d  test    rax, rax
0x180010630  jz      short loc_18001063C
0x180010632  mov     rdx, [rax+10h]
0x180010636  mov     r8d, [rax+4]
0x18001063a  jmp     short loc_180010646
0x18001063c  lea     rdx, WideCharStr
0x180010643  mov     r8, r14
0x180010646  lea     rcx, [rbp+lpLibFileName]
0x18001064a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001064f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180010653  mov     rax, [rbp+var_28]
0x180010657  lea     r14, [rbp+lpLibFileName]
0x18001065b  cmp     [rbp+var_20], 7
0x180010660  cmova   r14, [rbp+lpLibFileName]
0x180010665  test    rax, rax
0x180010668  jz      loc_180010872
0x18001066e  dec     rax
0x180010671  cmp     rax, rcx
0x180010674  cmovnb  rax, rcx
0x180010678  inc     rax
0x18001067b  lea     rdi, [r14+rax*2]
0x18001067f  mov     r8d, 2Eh ; '.'
0x180010685  mov     rdx, rdi
0x180010688  mov     rcx, r14
0x18001068b  call    __std_find_last_trivial_2
0x180010690  mov     rdx, rax
0x180010693  cmp     rax, rdi
0x180010696  jz      loc_180010872
0x18001069c  sub     rdx, r14
0x18001069f  sar     rdx, 1
0x1800106a2  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800106a6  jz      loc_180010872
0x1800106ac  mov     rdi, [rbp+var_28]
0x1800106b0  cmp     rdx, rdi
0x1800106b3  ja      short loc_1800106CF
0x1800106b5  mov     [rbp+var_28], rdx
0x1800106b9  lea     rcx, [rbp+lpLibFileName]
0x1800106bd  cmp     [rbp+var_20], 7
0x1800106c2  cmova   rcx, [rbp+lpLibFileName]
0x1800106c7  xor     eax, eax
0x1800106c9  mov     [rcx+rdx*2], ax
0x1800106cd  jmp     short loc_18001071C
0x1800106cf  mov     rcx, rdx
0x1800106d2  sub     rcx, rdi
0x1800106d5  mov     rax, [rbp+var_20]
0x1800106d9  sub     rax, rdi
0x1800106dc  cmp     rcx, rax
0x1800106df  ja      short loc_18001070D
0x1800106e1  mov     [rbp+var_28], rdx
0x1800106e5  lea     r8, [rbp+lpLibFileName]
0x1800106e9  cmp     [rbp+var_20], 7
0x1800106ee  cmova   r8, [rbp+lpLibFileName]
0x1800106f3  lea     rdi, [r8+rdi*2]
0x1800106f7  test    rcx, rcx
0x1800106fa  jz      short loc_180010704
0x1800106fc  xor     eax, eax
0x1800106fe  movzx   eax, ax
0x180010701  rep stosw
0x180010704  xor     eax, eax
0x180010706  mov     [r8+rdx*2], ax
0x18001070b  jmp     short loc_18001071C
0x18001070d  mov     r9, rcx
0x180010710  mov     rdx, rcx
0x180010713  lea     rcx, [rbp+lpLibFileName]; Src
0x180010717  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x18001071c  mov     rdi, [rbp+var_28]
0x180010720  mov     rax, [rbp+var_20]
0x180010724  sub     rax, rdi
0x180010727  mov     ecx, 4
0x18001072c  cmp     rax, rcx
0x18001072f  jb      short loc_18001075D
0x180010731  lea     rdx, [rdi+4]
0x180010735  mov     [rbp+var_28], rdx
0x180010739  lea     rcx, [rbp+lpLibFileName]
0x18001073d  cmp     [rbp+var_20], 7
0x180010742  cmova   rcx, [rbp+lpLibFileName]
0x180010747  mov     rax, 6C006C0064002Eh
0x180010751  mov     [rcx+rdi*2], rax
0x180010755  xor     eax, eax
0x180010757  mov     [rcx+rdx*2], ax
0x18001075b  jmp     short loc_18001076E
0x18001075d  mov     [rsp+78h+var_58], rcx; __int64
0x180010762  mov     rdx, rcx
0x180010765  lea     rcx, [rbp+lpLibFileName]; Src
0x180010769  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18001076e  lea     rcx, [rbp+lpLibFileName]
0x180010772  cmp     [rbp+var_20], 7
0x180010777  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18001077c  xor     edx, edx; hFile
0x18001077e  mov     r8d, 1000h; dwFlags
0x180010784  call    LoadLibraryExW_0
0x180010789  mov     rdi, rax
0x18001078c  mov     rdx, [rbp+var_28]
0x180010790  lea     r8, [rdx-4]
0x180010794  lea     rcx, [rbp+lpLibFileName]; Src
0x180010798  cmp     r8, rdx
0x18001079b  ja      short loc_1800107AF
0x18001079d  mov     [rbp+var_28], r8
0x1800107a1  cmp     [rbp+var_20], 7
0x1800107a6  cmova   rcx, [rbp+lpLibFileName]
0x1800107ab  xor     eax, eax
0x1800107ad  jmp     short loc_1800107D6
0x1800107af  mov     rax, [rbp+var_20]
0x1800107b3  sub     rax, rdx
0x1800107b6  mov     r10, 0FFFFFFFFFFFFFFFCh
0x1800107bd  cmp     rax, r10
0x1800107c0  jb      short loc_1800107DD
0x1800107c2  mov     [rbp+var_28], r8
0x1800107c6  cmp     [rbp+var_20], 7
0x1800107cb  cmova   rcx, [rbp+lpLibFileName]
0x1800107d0  xor     eax, eax
0x1800107d2  mov     [rcx+rdx*2], rax
0x1800107d6  mov     [rcx+r8*2], ax
0x1800107db  jmp     short loc_1800107E8
0x1800107dd  mov     r9, r10
0x1800107e0  mov     rdx, r10
0x1800107e3  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x1800107e8  test    rdi, rdi
0x1800107eb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800107f2  jz      loc_180010653
0x1800107f8  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x1800107ff  mov     rcx, rdi; hModule
0x180010802  call    WINRT_IMPL_GetProcAddress
0x180010807  test    rax, rax
0x18001080a  jz      short loc_18001084D
0x18001080c  mov     [rbp+var_48], 0
0x180010814  lea     rdx, [rbp+var_48]
0x180010818  mov     rcx, [r15]
0x18001081b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010820  test    eax, eax
0x180010822  jnz     short loc_18001083D
0x180010824  mov     rcx, [rbp+var_48]
0x180010828  mov     rax, [rcx]
0x18001082b  mov     r8, r13
0x18001082e  mov     rdx, r12
0x180010831  mov     rax, [rax]
0x180010834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010839  test    eax, eax
0x18001083b  jz      short loc_18001085A
0x18001083d  cmp     [rbp+var_48], 0
0x180010842  jz      short loc_18001084D
0x180010844  lea     rcx, [rbp+var_48]
0x180010848  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18001084d  mov     rcx, rdi; hLibModule
0x180010850  call    WINRT_IMPL_FreeLibrary
0x180010855  jmp     loc_18001064F
0x18001085a  mov     dword ptr [rsi], 0
0x180010860  cmp     [rbp+var_48], 0
0x180010865  jz      short loc_18001087F
0x180010867  lea     rcx, [rbp+var_48]
0x18001086b  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180010870  jmp     short loc_18001087F
0x180010872  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180010876  xor     ecx, ecx; dwReserved
0x180010878  call    SetErrorInfo_0
0x18001087d  mov     [rsi], ebx
0x18001087f  lea     rcx, [rbp+lpLibFileName]
0x180010883  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010888  cmp     [rbp+pperrinfo], 0
0x18001088d  jz      short loc_180010898
0x18001088f  lea     rcx, [rbp+pperrinfo]
0x180010893  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180010898  mov     rax, rsi
0x18001089b  mov     rcx, [rbp+var_18]
0x18001089f  xor     rcx, rsp; StackCookie
0x1800108a2  call    __security_check_cookie
0x1800108a7  add     rsp, 78h
0x1800108ab  pop     r15
0x1800108ad  pop     r14
0x1800108af  pop     r13
0x1800108b1  pop     r12
0x1800108b3  pop     rdi
0x1800108b4  pop     rsi
0x1800108b5  pop     rbx
0x1800108b6  pop     rbp
0x1800108b7  retn
```
