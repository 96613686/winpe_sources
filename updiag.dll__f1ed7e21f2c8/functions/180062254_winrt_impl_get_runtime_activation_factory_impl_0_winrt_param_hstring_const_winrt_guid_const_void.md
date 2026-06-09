# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180062254`
- end: `0x180062509`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `693`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e110`

## callees

- `0x18000e7ec`
- `0x180018eec`
- `0x180019080`
- `0x18001adcc`
- `0x180028b18`
- `0x180062254`
- `0x180079130`
- `0x18008f957`
- `0x18008fe00`
- `0x1800958a2`
- `0x180096019`
- `0x180096031`
- `0x180096049`
- `0x180096170`

## string_xrefs

- `0x180062445`: `DllGetActivationFactory`
- `0x1800622b2`: `combase.dll`
- `0x1800622fe`: `combase.dll`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  FARPROC ProcAddress; // rax
  HMODULE LibraryW_0; // rax
  int v10; // ebx
  HMODULE v11; // rax
  FARPROC v12; // rax
  __int64 v13; // rax
  const wchar_t *v14; // rdx
  unsigned __int64 v15; // r8
  LPCWSTR *v16; // r14
  char *v17; // rdi
  __int64 traits_2_unsigned_short; // rax
  const WCHAR *v19; // rcx
  HMODULE v20; // rdi
  FARPROC v21; // rax
  bool v22; // zf
  unsigned int (__fastcall ***v24)(_QWORD, __int64, __int64); // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v27; // [rsp+40h] [rbp-28h]
  unsigned __int64 v28; // [rsp+48h] [rbp-20h]

  if ( winrt_activation_handler )
  {
    *a1 = winrt_activation_handler(*a2, a3, a4);
    return a1;
  }
  ProcAddress = (FARPROC)`winrt::impl::get_runtime_activation_factory_impl<0>'::`2'::handler;
  if ( !`winrt::impl::get_runtime_activation_factory_impl<0>'::`2'::handler )
  {
    LibraryW_0 = LoadLibraryW_0(L"combase.dll");
    ProcAddress = WINRT_IMPL_GetProcAddress(LibraryW_0, "RoGetActivationFactory");
    `winrt::impl::get_runtime_activation_factory_impl<0>'::`2'::handler = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      ProcAddress = (FARPROC)winrt::impl::fallback_RoGetActivationFactory;
      `winrt::impl::get_runtime_activation_factory_impl<0>'::`2'::handler = (__int64)winrt::impl::fallback_RoGetActivationFactory;
    }
  }
  v10 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(*a2, a3, a4);
  if ( v10 == -2147221008 )
  {
    v11 = LoadLibraryW_0(L"combase.dll");
    v12 = WINRT_IMPL_GetProcAddress(v11, "CoIncrementMTAUsage");
    if ( !v12 )
    {
      *a1 = -2147221008;
      return a1;
    }
    v24 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v12)(&v24);
    v10 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))`winrt::impl::get_runtime_activation_factory_impl<0>'::`2'::handler)(
            *a2,
            a3,
            a4);
  }
  if ( !v10 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  *(_OWORD *)lpLibFileName = 0;
  v27 = 0;
  v28 = 0;
  v13 = *a2;
  if ( *a2 )
  {
    v14 = *(const wchar_t **)(v13 + 16);
    v15 = *(unsigned int *)(v13 + 4);
  }
  else
  {
    v14 = &psz;
    v15 = 0;
  }
  std::wstring::_Construct<1,wchar_t const *>(lpLibFileName, v14, v15);
  while ( 1 )
  {
    do
    {
      v16 = lpLibFileName;
      if ( v28 > 7 )
        v16 = (LPCWSTR *)lpLibFileName[0];
      if ( !v27
        || (v17 = (char *)v16 + 2 * v27,
            traits_2_unsigned_short = anonymous_namespace_::__std_find_last_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                        v16,
                                        v17),
            (char *)traits_2_unsigned_short == v17)
        || (traits_2_unsigned_short - (__int64)v16) >> 1 == -1 )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = v10;
        std::wstring::~wstring(lpLibFileName);
        v22 = pperrinfo == 0;
        goto LABEL_34;
      }
      std::wstring::resize(lpLibFileName);
      std::wstring::append(lpLibFileName);
      v19 = (const WCHAR *)lpLibFileName;
      if ( v28 > 7 )
        v19 = lpLibFileName[0];
      v20 = LoadLibraryW_0(v19);
      std::wstring::resize(lpLibFileName);
    }
    while ( !v20 );
    v21 = WINRT_IMPL_GetProcAddress(v20, "DllGetActivationFactory");
    if ( v21 )
      break;
LABEL_29:
    WINRT_IMPL_FreeLibrary(v20);
  }
  v24 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v21)(*a2, &v24)
    || (**v24)(v24, a3, a4) )
  {
    if ( v24 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v24);
    goto LABEL_29;
  }
  *a1 = 0;
  if ( v24 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v24);
  std::wstring::~wstring(lpLibFileName);
  v22 = pperrinfo == 0;
LABEL_34:
  if ( !v22 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180062254  push    rbp
0x180062256  push    rbx
0x180062257  push    rsi
0x180062258  push    rdi
0x180062259  push    r12
0x18006225b  push    r13
0x18006225d  push    r14
0x18006225f  push    r15
0x180062261  mov     rbp, rsp
0x180062264  sub     rsp, 68h
0x180062268  mov     rax, cs:__security_cookie
0x18006226f  xor     rax, rsp
0x180062272  mov     [rbp+var_18], rax
0x180062276  mov     r13, r9
0x180062279  mov     r12, r8
0x18006227c  mov     r15, rdx
0x18006227f  mov     rsi, rcx
0x180062282  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180062289  xor     r14d, r14d
0x18006228c  test    rax, rax
0x18006228f  jz      short loc_1800622A6
0x180062291  mov     r8, r9
0x180062294  mov     rdx, r12
0x180062297  mov     rcx, [r15]
0x18006229a  call    _guard_dispatch_icall
0x18006229f  mov     [rsi], eax
0x1800622a1  jmp     loc_1800624E9
0x1800622a6  mov     rax, cs:?handler@?1???$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@2@AEBUhstring@param@2@AEBUguid@2@PEAPEAX@Z@4P6AHPEAX12@_EEA
0x1800622ad  test    rax, rax
0x1800622b0  jnz     short loc_1800622E7
0x1800622b2  lea     rcx, LibFileName; "combase.dll"
0x1800622b9  call    LoadLibraryW_0
0x1800622be  mov     rcx, rax; hModule
0x1800622c1  lea     rdx, aRogetactivatio; "RoGetActivationFactory"
0x1800622c8  call    WINRT_IMPL_GetProcAddress
0x1800622cd  mov     cs:?handler@?1???$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@2@AEBUhstring@param@2@AEBUguid@2@PEAPEAX@Z@4P6AHPEAX12@_EEA, rax
0x1800622d4  test    rax, rax
0x1800622d7  jnz     short loc_1800622E7
0x1800622d9  lea     rax, ?fallback_RoGetActivationFactory@impl@winrt@@YAHPEAXAEBUguid@2@PEAPEAX@Z; winrt::impl::fallback_RoGetActivationFactory(void *,winrt::guid const &,void * *)
0x1800622e0  mov     cs:?handler@?1???$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@2@AEBUhstring@param@2@AEBUguid@2@PEAPEAX@Z@4P6AHPEAX12@_EEA, rax
0x1800622e7  mov     r8, r13
0x1800622ea  mov     rdx, r12
0x1800622ed  mov     rcx, [r15]
0x1800622f0  call    _guard_dispatch_icall
0x1800622f5  mov     ebx, eax
0x1800622f7  cmp     eax, 800401F0h
0x1800622fc  jnz     short loc_18006234D
0x1800622fe  lea     rcx, LibFileName; "combase.dll"
0x180062305  call    LoadLibraryW_0
0x18006230a  mov     rcx, rax; hModule
0x18006230d  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180062314  call    WINRT_IMPL_GetProcAddress
0x180062319  test    rax, rax
0x18006231c  jnz     short loc_180062329
0x18006231e  mov     dword ptr [rsi], 800401F0h
0x180062324  jmp     loc_1800624E9
0x180062329  mov     [rbp+var_48], r14
0x18006232d  lea     rcx, [rbp+var_48]
0x180062331  call    _guard_dispatch_icall
0x180062336  mov     r8, r13
0x180062339  mov     rdx, r12
0x18006233c  mov     rcx, [r15]
0x18006233f  mov     rax, cs:?handler@?1???$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@2@AEBUhstring@param@2@AEBUguid@2@PEAPEAX@Z@4P6AHPEAX12@_EEA
0x180062346  call    _guard_dispatch_icall
0x18006234b  mov     ebx, eax
0x18006234d  test    ebx, ebx
0x18006234f  jnz     short loc_180062359
0x180062351  mov     [rsi], r14d
0x180062354  jmp     loc_1800624E9
0x180062359  mov     [rbp+pperrinfo], r14
0x18006235d  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180062361  xor     ecx, ecx; dwReserved
0x180062363  call    GetErrorInfo_0
0x180062368  xorps   xmm0, xmm0
0x18006236b  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x18006236f  mov     [rbp+var_28], r14
0x180062373  mov     [rbp+var_20], r14
0x180062377  mov     rax, [r15]
0x18006237a  test    rax, rax
0x18006237d  jz      short loc_180062389
0x18006237f  mov     rdx, [rax+10h]
0x180062383  mov     r8d, [rax+4]
0x180062387  jmp     short loc_180062393
0x180062389  lea     rdx, psz
0x180062390  mov     r8, r14
0x180062393  lea     rcx, [rbp+lpLibFileName]
0x180062397  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006239c  lea     r14, [rbp+lpLibFileName]
0x1800623a0  cmp     [rbp+var_20], 7
0x1800623a5  cmova   r14, [rbp+lpLibFileName]
0x1800623aa  mov     rcx, [rbp+var_28]
0x1800623ae  test    rcx, rcx
0x1800623b1  jz      loc_1800624C3
0x1800623b7  dec     rcx
0x1800623ba  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800623be  cmp     rcx, rax
0x1800623c1  cmovb   rax, rcx
0x1800623c5  inc     rax
0x1800623c8  lea     rdi, [r14+rax*2]
0x1800623cc  mov     rdx, rdi
0x1800623cf  mov     rcx, r14
0x1800623d2  call    _anonymous_namespace_____std_find_last_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1800623d7  cmp     rax, rdi
0x1800623da  jz      loc_1800624C3
0x1800623e0  sub     rax, r14
0x1800623e3  sar     rax, 1
0x1800623e6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800623ea  jz      loc_1800624C3
0x1800623f0  mov     rdx, rax
0x1800623f3  lea     rcx, [rbp+lpLibFileName]; Src
0x1800623f7  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800623fc  mov     r8d, 4
0x180062402  lea     rdx, aDll; ".dll"
0x180062409  lea     rcx, [rbp+lpLibFileName]; Src
0x18006240d  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180062412  lea     rcx, [rbp+lpLibFileName]
0x180062416  cmp     [rbp+var_20], 7
0x18006241b  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x180062420  call    LoadLibraryW_0
0x180062425  mov     rdi, rax
0x180062428  mov     rdx, [rbp+var_28]
0x18006242c  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180062430  lea     rcx, [rbp+lpLibFileName]; Src
0x180062434  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180062439  xor     r14d, r14d
0x18006243c  test    rdi, rdi
0x18006243f  jz      loc_18006239C
0x180062445  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18006244c  mov     rcx, rdi; hModule
0x18006244f  call    WINRT_IMPL_GetProcAddress
0x180062454  test    rax, rax
0x180062457  jz      short loc_180062495
0x180062459  mov     [rbp+var_48], r14
0x18006245d  lea     rdx, [rbp+var_48]
0x180062461  mov     rcx, [r15]
0x180062464  call    _guard_dispatch_icall
0x180062469  test    eax, eax
0x18006246b  jnz     short loc_180062486
0x18006246d  mov     rcx, [rbp+var_48]
0x180062471  mov     rax, [rcx]
0x180062474  mov     r8, r13
0x180062477  mov     rdx, r12
0x18006247a  mov     rax, [rax]
0x18006247d  call    _guard_dispatch_icall
0x180062482  test    eax, eax
0x180062484  jz      short loc_1800624A2
0x180062486  cmp     [rbp+var_48], r14
0x18006248a  jz      short loc_180062495
0x18006248c  lea     rcx, [rbp+var_48]
0x180062490  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180062495  mov     rcx, rdi; hLibModule
0x180062498  call    WINRT_IMPL_FreeLibrary
0x18006249d  jmp     loc_18006239C
0x1800624a2  mov     [rsi], r14d
0x1800624a5  cmp     [rbp+var_48], r14
0x1800624a9  jz      short loc_1800624B4
0x1800624ab  lea     rcx, [rbp+var_48]
0x1800624af  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800624b4  lea     rcx, [rbp+lpLibFileName]
0x1800624b8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800624bd  cmp     [rbp+pperrinfo], r14
0x1800624c1  jmp     short loc_1800624DE
0x1800624c3  mov     rdx, [rbp+pperrinfo]; perrinfo
0x1800624c7  xor     ecx, ecx; dwReserved
0x1800624c9  call    SetErrorInfo_0
0x1800624ce  mov     [rsi], ebx
0x1800624d0  lea     rcx, [rbp+lpLibFileName]
0x1800624d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800624d9  cmp     [rbp+pperrinfo], 0
0x1800624de  jz      short loc_1800624E9
0x1800624e0  lea     rcx, [rbp+pperrinfo]
0x1800624e4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800624e9  mov     rax, rsi
0x1800624ec  mov     rcx, [rbp+var_18]
0x1800624f0  xor     rcx, rsp; StackCookie
0x1800624f3  call    __security_check_cookie
0x1800624f8  add     rsp, 68h
0x1800624fc  pop     r15
0x1800624fe  pop     r14
0x180062500  pop     r13
0x180062502  pop     r12
0x180062504  pop     rdi
0x180062505  pop     rsi
0x180062506  pop     rbx
0x180062507  pop     rbp
0x180062508  retn
```
