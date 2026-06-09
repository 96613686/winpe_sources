# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x140050184`
- end: `0x140050384`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `512`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004ec70`
- `0x14004edbc`
- `0x14004f250`
- `0x14004fcd8`
- `0x14004fd38`

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
- `0x140050184`
- `0x14005eb54`
- `0x14005ebac`
- `0x14005fcbc`
- `0x140067010`

## string_xrefs

- `0x1400501e7`: `combase.dll`
- `0x1400502c6`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rcx
  HMODULE v14; // rdi
  FARPROC v15; // rax
  unsigned int (__fastcall ***v17)(_QWORD, __int64, __int64); // [rsp+20h] [rbp-40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName[4]; // [rsp+30h] [rbp-30h] BYREF

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
    v17 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v17);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  std::wstring::wstring(lpLibFileName, a2);
  while ( 1 )
  {
    do
    {
      v12 = std::wstring::rfind(lpLibFileName);
      if ( v12 == -1 )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_23;
      }
      std::wstring::resize(lpLibFileName, v12);
      std::wstring::_Append<unsigned short>(lpLibFileName);
      v13 = (const WCHAR *)lpLibFileName;
      if ( lpLibFileName[3] > (LPCWSTR)7 )
        v13 = lpLibFileName[0];
      v14 = LoadLibraryExW_0(v13, 0, 0x1000u);
      std::wstring::resize(lpLibFileName, lpLibFileName[2] - 2);
    }
    while ( !v14 );
    v15 = WINRT_IMPL_GetProcAddress(v14, "DllGetActivationFactory");
    if ( v15 )
      break;
LABEL_19:
    WINRT_IMPL_FreeLibrary(v14);
  }
  v17 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v15)(*a2, &v17)
    || (**v17)(v17, a3, a4) )
  {
    if ( v17 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v17);
    goto LABEL_19;
  }
  *a1 = 0;
  if ( v17 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v17);
LABEL_23:
  std::wstring::~wstring(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x140050184  push    rbp
0x140050186  push    rbx
0x140050187  push    rsi
0x140050188  push    rdi
0x140050189  push    r12
0x14005018b  push    r14
0x14005018d  push    r15
0x14005018f  mov     rbp, rsp
0x140050192  sub     rsp, 60h
0x140050196  mov     rax, cs:__security_cookie
0x14005019d  xor     rax, rsp
0x1400501a0  mov     [rbp+var_10], rax
0x1400501a4  mov     r12, r9
0x1400501a7  mov     r15, r8
0x1400501aa  mov     r14, rdx
0x1400501ad  mov     rsi, rcx
0x1400501b0  mov     rcx, [rdx]
0x1400501b3  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x1400501ba  mov     r8, r9
0x1400501bd  mov     rdx, r15
0x1400501c0  test    rax, rax
0x1400501c3  jz      short loc_1400501D1
0x1400501c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400501ca  mov     [rsi], eax
0x1400501cc  jmp     loc_140050366
0x1400501d1  call    RoGetActivationFactory_0
0x1400501d6  mov     ebx, eax
0x1400501d8  cmp     eax, 800401F0h
0x1400501dd  jnz     short loc_140050233
0x1400501df  xor     edx, edx; hFile
0x1400501e1  mov     r8d, 1000h; dwFlags
0x1400501e7  lea     rcx, aCombaseDll; "combase.dll"
0x1400501ee  call    LoadLibraryExW_0
0x1400501f3  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x1400501fa  mov     rcx, rax; hModule
0x1400501fd  call    WINRT_IMPL_GetProcAddress
0x140050202  test    rax, rax
0x140050205  jnz     short loc_140050212
0x140050207  mov     dword ptr [rsi], 800401F0h
0x14005020d  jmp     loc_140050366
0x140050212  mov     [rbp+var_40], 0
0x14005021a  lea     rcx, [rbp+var_40]
0x14005021e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050223  mov     r8, r12
0x140050226  mov     rdx, r15
0x140050229  mov     rcx, [r14]
0x14005022c  call    RoGetActivationFactory_0
0x140050231  mov     ebx, eax
0x140050233  test    ebx, ebx
0x140050235  jnz     short loc_14005023E
0x140050237  mov     [rsi], ebx
0x140050239  jmp     loc_140050366
0x14005023e  mov     [rbp+pperrinfo], 0
0x140050246  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x14005024a  xor     ecx, ecx; dwReserved
0x14005024c  call    GetErrorInfo_0
0x140050251  mov     rdx, r14
0x140050254  lea     rcx, [rbp+lpLibFileName]
0x140050258  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x14005025d  lea     rcx, [rbp+lpLibFileName]
0x140050261  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x140050266  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14005026a  jz      loc_140050340
0x140050270  mov     rdx, rax
0x140050273  lea     rcx, [rbp+lpLibFileName]
0x140050277  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14005027c  mov     r8d, 4
0x140050282  lea     rdx, aDll; ".dll"
0x140050289  lea     rcx, [rbp+lpLibFileName]; Src
0x14005028d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x140050292  lea     rcx, [rbp+lpLibFileName]
0x140050296  cmp     [rbp+var_18], 7
0x14005029b  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x1400502a0  xor     edx, edx; hFile
0x1400502a2  mov     r8d, 1000h; dwFlags
0x1400502a8  call    LoadLibraryExW_0
0x1400502ad  mov     rdi, rax
0x1400502b0  mov     rdx, [rbp+var_20]
0x1400502b4  add     rdx, 0FFFFFFFFFFFFFFFCh
0x1400502b8  lea     rcx, [rbp+lpLibFileName]
0x1400502bc  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1400502c1  test    rdi, rdi
0x1400502c4  jz      short loc_14005025D
0x1400502c6  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x1400502cd  mov     rcx, rdi; hModule
0x1400502d0  call    WINRT_IMPL_GetProcAddress
0x1400502d5  test    rax, rax
0x1400502d8  jz      short loc_14005031B
0x1400502da  mov     [rbp+var_40], 0
0x1400502e2  lea     rdx, [rbp+var_40]
0x1400502e6  mov     rcx, [r14]
0x1400502e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400502ee  test    eax, eax
0x1400502f0  jnz     short loc_14005030B
0x1400502f2  mov     rcx, [rbp+var_40]
0x1400502f6  mov     rax, [rcx]
0x1400502f9  mov     r8, r12
0x1400502fc  mov     rdx, r15
0x1400502ff  mov     rax, [rax]
0x140050302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050307  test    eax, eax
0x140050309  jz      short loc_140050328
0x14005030b  cmp     [rbp+var_40], 0
0x140050310  jz      short loc_14005031B
0x140050312  lea     rcx, [rbp+var_40]
0x140050316  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14005031b  mov     rcx, rdi; hLibModule
0x14005031e  call    WINRT_IMPL_FreeLibrary
0x140050323  jmp     loc_14005025D
0x140050328  mov     dword ptr [rsi], 0
0x14005032e  cmp     [rbp+var_40], 0
0x140050333  jz      short loc_14005034D
0x140050335  lea     rcx, [rbp+var_40]
0x140050339  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14005033e  jmp     short loc_14005034D
0x140050340  mov     rdx, [rbp+pperrinfo]; perrinfo
0x140050344  xor     ecx, ecx; dwReserved
0x140050346  call    SetErrorInfo_0
0x14005034b  mov     [rsi], ebx
0x14005034d  lea     rcx, [rbp+lpLibFileName]
0x140050351  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050356  cmp     [rbp+pperrinfo], 0
0x14005035b  jz      short loc_140050366
0x14005035d  lea     rcx, [rbp+pperrinfo]
0x140050361  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x140050366  mov     rax, rsi
0x140050369  mov     rcx, [rbp+var_10]
0x14005036d  xor     rcx, rsp; StackCookie
0x140050370  call    __security_check_cookie
0x140050375  add     rsp, 60h
0x140050379  pop     r15
0x14005037b  pop     r14
0x14005037d  pop     r12
0x14005037f  pop     rdi
0x140050380  pop     rsi
0x140050381  pop     rbx
0x140050382  pop     rbp
0x140050383  retn
```
