# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x14004ff9c`
- end: `0x14005017e`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004fc78`

## callees

- `0x140009d6c`
- `0x14000a10c`
- `0x14000f7e0`
- `0x140010704`
- `0x1400107e9`
- `0x1400107f5`
- `0x1400449d6`
- `0x140044a36`
- `0x140044a54`
- `0x14004c080`
- `0x14004ff9c`
- `0x14005eb54`
- `0x14005ebac`
- `0x14005fcbc`
- `0x140067010`

## string_xrefs

- `0x14004fffd`: `combase.dll`
- `0x1400500dc`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rcx
  HMODULE v14; // rdi
  FARPROC v15; // rax
  __int64 v16; // rax
  __int64 v18; // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[4]; // [rsp+30h] [rbp-38h] BYREF

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD *))winrt_activation_handler)(v8, a3, a4);
  }
  else
  {
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
      v18 = 0;
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v18);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      std::wstring::wstring(lpLibFileName, a2);
      while ( 1 )
      {
        v12 = std::wstring::rfind(lpLibFileName);
        if ( v12 == -1 )
          break;
        std::wstring::resize(lpLibFileName, v12);
        std::wstring::_Append<unsigned short>(lpLibFileName);
        v13 = (const WCHAR *)lpLibFileName;
        if ( lpLibFileName[3] > (LPCWSTR)7 )
          v13 = lpLibFileName[0];
        v14 = LoadLibraryExW_0(v13, 0, 0x1000u);
        std::wstring::resize(lpLibFileName, lpLibFileName[2] - 2);
        if ( v14 )
        {
          v15 = WINRT_IMPL_GetProcAddress(v14, "DllGetActivationFactory");
          if ( v15 )
          {
            v18 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v15)(*a2, &v18) )
            {
              v16 = v18;
              v18 = 0;
              *a4 = v16;
              *a1 = 0;
              goto LABEL_21;
            }
            if ( v18 )
              winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v18);
          }
          WINRT_IMPL_FreeLibrary(v14);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_21:
      std::wstring::~wstring(lpLibFileName);
      if ( pperrinfo )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&pperrinfo);
    }
    else
    {
      *a1 = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14004ff9c  push    rbp
0x14004ff9e  push    rbx
0x14004ff9f  push    rsi
0x14004ffa0  push    rdi
0x14004ffa1  push    r14
0x14004ffa3  push    r15
0x14004ffa5  mov     rbp, rsp
0x14004ffa8  sub     rsp, 68h
0x14004ffac  mov     rax, cs:__security_cookie
0x14004ffb3  xor     rax, rsp
0x14004ffb6  mov     [rbp+var_18], rax
0x14004ffba  mov     r14, r9
0x14004ffbd  mov     rdi, r8
0x14004ffc0  mov     r15, rdx
0x14004ffc3  mov     rsi, rcx
0x14004ffc6  mov     rcx, [rdx]
0x14004ffc9  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x14004ffd0  mov     r8, r9
0x14004ffd3  mov     rdx, rdi
0x14004ffd6  test    rax, rax
0x14004ffd9  jz      short loc_14004FFE7
0x14004ffdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ffe0  mov     [rsi], eax
0x14004ffe2  jmp     loc_140050162
0x14004ffe7  call    RoGetActivationFactory_0
0x14004ffec  mov     ebx, eax
0x14004ffee  cmp     eax, 800401F0h
0x14004fff3  jnz     short loc_140050049
0x14004fff5  xor     edx, edx; hFile
0x14004fff7  mov     r8d, 1000h; dwFlags
0x14004fffd  lea     rcx, aCombaseDll; "combase.dll"
0x140050004  call    LoadLibraryExW_0
0x140050009  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x140050010  mov     rcx, rax; hModule
0x140050013  call    WINRT_IMPL_GetProcAddress
0x140050018  test    rax, rax
0x14005001b  jnz     short loc_140050028
0x14005001d  mov     dword ptr [rsi], 800401F0h
0x140050023  jmp     loc_140050162
0x140050028  mov     [rbp+var_48], 0
0x140050030  lea     rcx, [rbp+var_48]
0x140050034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050039  mov     r8, r14
0x14005003c  mov     rdx, rdi
0x14005003f  mov     rcx, [r15]
0x140050042  call    RoGetActivationFactory_0
0x140050047  mov     ebx, eax
0x140050049  test    ebx, ebx
0x14005004b  jnz     short loc_140050054
0x14005004d  mov     [rsi], ebx
0x14005004f  jmp     loc_140050162
0x140050054  mov     [rbp+pperrinfo], 0
0x14005005c  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x140050060  xor     ecx, ecx; dwReserved
0x140050062  call    GetErrorInfo_0
0x140050067  mov     rdx, r15
0x14005006a  lea     rcx, [rbp+lpLibFileName]
0x14005006e  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x140050073  lea     rcx, [rbp+lpLibFileName]
0x140050077  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x14005007c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140050080  jz      loc_14005013C
0x140050086  mov     rdx, rax
0x140050089  lea     rcx, [rbp+lpLibFileName]
0x14005008d  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x140050092  mov     r8d, 4
0x140050098  lea     rdx, aDll; ".dll"
0x14005009f  lea     rcx, [rbp+lpLibFileName]; Src
0x1400500a3  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1400500a8  lea     rcx, [rbp+lpLibFileName]
0x1400500ac  cmp     [rbp+var_20], 7
0x1400500b1  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x1400500b6  xor     edx, edx; hFile
0x1400500b8  mov     r8d, 1000h; dwFlags
0x1400500be  call    LoadLibraryExW_0
0x1400500c3  mov     rdi, rax
0x1400500c6  mov     rdx, [rbp+var_28]
0x1400500ca  add     rdx, 0FFFFFFFFFFFFFFFCh
0x1400500ce  lea     rcx, [rbp+lpLibFileName]
0x1400500d2  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1400500d7  test    rdi, rdi
0x1400500da  jz      short loc_140050073
0x1400500dc  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x1400500e3  mov     rcx, rdi; hModule
0x1400500e6  call    WINRT_IMPL_GetProcAddress
0x1400500eb  test    rax, rax
0x1400500ee  jz      short loc_140050118
0x1400500f0  mov     [rbp+var_48], 0
0x1400500f8  lea     rdx, [rbp+var_48]
0x1400500fc  mov     rcx, [r15]
0x1400500ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050104  test    eax, eax
0x140050106  jz      short loc_140050125
0x140050108  cmp     [rbp+var_48], 0
0x14005010d  jz      short loc_140050118
0x14005010f  lea     rcx, [rbp+var_48]
0x140050113  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x140050118  mov     rcx, rdi; hLibModule
0x14005011b  call    WINRT_IMPL_FreeLibrary
0x140050120  jmp     loc_140050073
0x140050125  mov     rax, [rbp+var_48]
0x140050129  mov     [rbp+var_48], 0
0x140050131  mov     [r14], rax
0x140050134  mov     dword ptr [rsi], 0
0x14005013a  jmp     short loc_140050149
0x14005013c  mov     rdx, [rbp+pperrinfo]; perrinfo
0x140050140  xor     ecx, ecx; dwReserved
0x140050142  call    SetErrorInfo_0
0x140050147  mov     [rsi], ebx
0x140050149  lea     rcx, [rbp+lpLibFileName]
0x14005014d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050152  cmp     [rbp+pperrinfo], 0
0x140050157  jz      short loc_140050162
0x140050159  lea     rcx, [rbp+pperrinfo]
0x14005015d  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x140050162  mov     rax, rsi
0x140050165  mov     rcx, [rbp+var_18]
0x140050169  xor     rcx, rsp; StackCookie
0x14005016c  call    __security_check_cookie
0x140050171  add     rsp, 68h
0x140050175  pop     r15
0x140050177  pop     r14
0x140050179  pop     rdi
0x14005017a  pop     rsi
0x14005017b  pop     rbx
0x14005017c  pop     rbp
0x14005017d  retn
```
