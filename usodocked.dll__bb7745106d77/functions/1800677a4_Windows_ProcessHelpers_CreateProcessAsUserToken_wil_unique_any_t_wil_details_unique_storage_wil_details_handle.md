# Windows::ProcessHelpers::CreateProcessAsUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800677a4`
- end: `0x180067b31`
- name: `?CreateProcessAsUserToken@ProcessHelpers@Windows@@YA?AV?$unique_struct@U_PROCESS_INFORMATION@@P6AXPEAU1@@Z$1?CloseProcessInformation@details@wil@@YAX0@Z$$T$0A@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@4@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `909`
- prototype: `LPHANDLE __fastcall(LPHANDLE lpTargetHandle, HANDLE *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180055614`

## callees

- `0x180007660`
- `0x180007dfc`
- `0x18000856c`
- `0x180018f7c`
- `0x18001ee04`
- `0x1800209fc`
- `0x180023a18`
- `0x180058020`
- `0x1800677a4`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18006798d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18006798d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800679a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800679ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800679ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800679f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800679a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800679ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800679ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800679f6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800679d8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180067a1f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800679d8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180067a1f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180067856`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180067856`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067a3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067a3e`
- `USERENV!CreateEnvironmentBlock` at `0x180067891`
- `USERENV!CreateEnvironmentBlock` at `0x180067891`
- `USERENV!DestroyEnvironmentBlock` at `0x180067a4f`
- `USERENV!DestroyEnvironmentBlock` at `0x180067a4f`

## string_xrefs

- `0x180067ac2`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\common\processhelpers.cpp`
- `0x180067ad4`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\common\processhelpers.cpp`
- `0x180067ae6`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\common\processhelpers.cpp`
- `0x180067afb`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\common\processhelpers.cpp`
- `0x180067b0d`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\common\processhelpers.cpp`
- `0x180067b1f`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\common\processhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPHANDLE __fastcall Windows::ProcessHelpers::CreateProcessAsUserToken(
        LPHANDLE lpTargetHandle,
        HANDLE *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  char *v8; // rdi
  void **v9; // r14
  const char *v10; // r9
  void *v11; // rdx
  const char *v12; // r9
  _QWORD *v13; // rdx
  _QWORD *v14; // r9
  int v15; // eax
  void *v16; // rcx
  const char *v17; // r9
  HANDLE CurrentProcess; // rbx
  HANDLE v19; // rax
  const char *v20; // r9
  HANDLE v21; // rbx
  HANDLE v22; // rax
  const char *v23; // r9
  int TokenType; // [rsp+20h] [rbp-E0h]
  LPVOID Environment; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpApplicationName[6]; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v29; // [rsp+110h] [rbp+10h]
  _QWORD *v30; // [rsp+118h] [rbp+18h]
  WCHAR CommandLine[264]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+278h]

  lpApplicationName[3] = (LPCWSTR)lpTargetHandle;
  v29 = a3;
  v30 = a4;
  v8 = (char *)operator new(0x18u);
  lpApplicationName[4] = (LPCWSTR)v8;
  *(_OWORD *)v8 = 0;
  *((_DWORD *)v8 + 2) = 1;
  *((_DWORD *)v8 + 3) = 1;
  *(_QWORD *)v8 = &std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::`vftable';
  v9 = (void **)(v8 + 16);
  *((_QWORD *)v8 + 2) = 0;
  lpApplicationName[1] = (LPCWSTR)(v8 + 16);
  lpApplicationName[2] = (LPCWSTR)v8;
  if ( !DuplicateTokenEx(*a2, 0xBu, 0, SecurityImpersonation, TokenPrimary, (PHANDLE)v8 + 2) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\common\\processhelpers.cpp",
      v10);
  Environment = 0;
  if ( v8 == (char *)-16LL )
    v11 = 0;
  else
    v11 = *v9;
  Environment = 0;
  if ( !CreateEnvironmentBlock(&Environment, v11, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\common\\processhelpers.cpp",
      v12);
  if ( a3[3] <= 7u )
    v13 = a3;
  else
    v13 = (_QWORD *)*a3;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
    lpApplicationName,
    v13);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.lpDesktop = L"WinSta0\\Default";
  memset_0(CommandLine, 0, 0x208u);
  if ( a4[3] <= 7u )
    v14 = a4;
  else
    v14 = (_QWORD *)*a4;
  v15 = StringCchPrintfW(CommandLine, 0x104u, L"%s", v14);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\common\\processhelpers.cpp",
      (const char *)(unsigned int)v15,
      TokenType);
  *(_OWORD *)lpTargetHandle = 0;
  lpTargetHandle[2] = 0;
  if ( v8 == (char *)-16LL )
    v16 = 0;
  else
    v16 = *v9;
  if ( !CreateProcessAsUserW(
          v16,
          lpApplicationName[0],
          CommandLine,
          0,
          0,
          0,
          0x400u,
          Environment,
          0,
          &StartupInfo,
          (LPPROCESS_INFORMATION)lpTargetHandle) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\common\\processhelpers.cpp",
      v17);
  CurrentProcess = GetCurrentProcess();
  v19 = GetCurrentProcess();
  if ( !DuplicateHandle(v19, *lpTargetHandle, CurrentProcess, lpTargetHandle, 0, 0, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\common\\processhelpers.cpp",
      v20);
  v21 = GetCurrentProcess();
  v22 = GetCurrentProcess();
  if ( !DuplicateHandle(v22, lpTargetHandle[1], v21, lpTargetHandle + 1, 0, 0, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\common\\processhelpers.cpp",
      v23);
  if ( lpApplicationName[0] )
    CoTaskMemFree((LPVOID)lpApplicationName[0]);
  if ( Environment )
    DestroyEnvironmentBlock(Environment);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v8)(v8);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
  }
  std::wstring::_Tidy_deallocate(a3);
  std::wstring::_Tidy_deallocate(a4);
  return lpTargetHandle;
}

```

## disassembly

```asm
0x1800677a4  push    rbp
0x1800677a6  push    rbx
0x1800677a7  push    rsi
0x1800677a8  push    rdi
0x1800677a9  push    r12
0x1800677ab  push    r14
0x1800677ad  push    r15
0x1800677af  lea     rbp, [rsp-240h]
0x1800677b7  sub     rsp, 340h
0x1800677be  mov     rax, cs:__security_cookie
0x1800677c5  xor     rax, rsp
0x1800677c8  mov     [rbp+270h+var_40], rax
0x1800677cf  mov     r12, r9
0x1800677d2  mov     r15, r8
0x1800677d5  mov     rbx, rdx
0x1800677d8  mov     rsi, rcx
0x1800677db  mov     [rbp+270h+var_2E8], rcx
0x1800677df  mov     [rbp+270h+var_260], r8
0x1800677e3  mov     [rbp+270h+var_258], r9
0x1800677e7  mov     [rsp+370h+var_310], 0
0x1800677ef  xorps   xmm0, xmm0
0x1800677f2  movdqu  [rsp+370h+var_2F8], xmm0
0x1800677f8  mov     ecx, 18h; Size
0x1800677fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180067802  mov     rdi, rax
0x180067805  mov     [rbp+270h+var_2E0], rax
0x180067809  xorps   xmm0, xmm0
0x18006780c  movups  xmmword ptr [rax], xmm0
0x18006780f  mov     ecx, 1
0x180067814  mov     [rax+8], ecx
0x180067817  mov     [rax+0Ch], ecx
0x18006781a  lea     rax, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::`vftable'
0x180067821  mov     [rdi], rax
0x180067824  lea     r14, [rdi+10h]
0x180067828  mov     qword ptr [r14], 0
0x18006782f  mov     [rsp+370h+var_310], 4
0x180067837  mov     qword ptr [rsp+370h+var_2F8], r14
0x18006783c  mov     qword ptr [rbp+270h+var_2F8+8], rdi
0x180067840  mov     [rsp+370h+phNewToken], r14; phNewToken
0x180067845  mov     [rsp+370h+TokenType], ecx; int
0x180067849  lea     r9d, [rcx+1]; ImpersonationLevel
0x18006784d  xor     r8d, r8d; lpTokenAttributes
0x180067850  lea     edx, [rcx+0Ah]; dwDesiredAccess
0x180067853  mov     rcx, [rbx]; hExistingToken
0x180067856  call    cs:__imp_DuplicateTokenEx
0x18006785c  mov     rcx, [rbp+278h]; this
0x180067863  test    eax, eax
0x180067865  jz      loc_180067AD4
0x18006786b  mov     [rsp+370h+Environment], 0
0x180067874  test    r14, r14
0x180067877  jz      short loc_18006787E
0x180067879  mov     rdx, [r14]
0x18006787c  jmp     short loc_180067880
0x18006787e  xor     edx, edx; hToken
0x180067880  mov     [rsp+370h+Environment], 0
0x180067889  xor     r8d, r8d; bInherit
0x18006788c  lea     rcx, [rsp+370h+Environment]; lpEnvironment
0x180067891  call    cs:__imp_CreateEnvironmentBlock
0x180067897  mov     rcx, [rbp+278h]; this
0x18006789e  test    eax, eax
0x1800678a0  jz      loc_180067AE6
0x1800678a6  cmp     qword ptr [r15+18h], 7
0x1800678ab  jbe     short loc_1800678B2
0x1800678ad  mov     rdx, [r15]
0x1800678b0  jmp     short loc_1800678B5
0x1800678b2  mov     rdx, r15
0x1800678b5  lea     rcx, [rsp+370h+lpApplicationName]
0x1800678ba  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x1800678bf  nop
0x1800678c0  mov     ebx, 68h ; 'h'
0x1800678c5  mov     r8d, ebx; Size
0x1800678c8  xor     edx, edx; Val
0x1800678ca  lea     rcx, [rbp+270h+StartupInfo]; void *
0x1800678ce  call    memset_0
0x1800678d3  mov     [rbp+270h+StartupInfo.cb], ebx
0x1800678d6  lea     rax, aWinsta0Default; "WinSta0\\Default"
0x1800678dd  mov     [rbp+270h+StartupInfo.lpDesktop], rax
0x1800678e1  xor     edx, edx; Val
0x1800678e3  mov     r8d, 208h; Size
0x1800678e9  lea     rcx, [rbp+270h+CommandLine]; void *
0x1800678ed  call    memset_0
0x1800678f2  cmp     qword ptr [r12+18h], 7
0x1800678f8  jbe     short loc_180067900
0x1800678fa  mov     r9, [r12]
0x1800678fe  jmp     short loc_180067903
0x180067900  mov     r9, r12
0x180067903  lea     r8, aS; "%s"
0x18006790a  mov     edx, 104h; unsigned __int64
0x18006790f  lea     rcx, [rbp+270h+CommandLine]; unsigned __int16 *
0x180067913  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180067918  mov     rcx, [rbp+278h]; this
0x18006791f  test    eax, eax
0x180067921  js      loc_180067AF8
0x180067927  xorps   xmm0, xmm0
0x18006792a  xor     eax, eax
0x18006792c  movups  xmmword ptr [rsi], xmm0
0x18006792f  mov     [rsi+10h], rax
0x180067933  mov     [rsp+370h+var_310], 5
0x18006793b  mov     rax, [rsp+370h+Environment]
0x180067940  test    r14, r14
0x180067943  jz      short loc_18006794A
0x180067945  mov     rcx, [r14]
0x180067948  jmp     short loc_18006794C
0x18006794a  xor     ecx, ecx; hToken
0x18006794c  mov     [rsp+370h+lpProcessInformation], rsi; lpProcessInformation
0x180067951  lea     rdx, [rbp+270h+StartupInfo]
0x180067955  mov     [rsp+370h+lpStartupInfo], rdx; lpStartupInfo
0x18006795a  mov     [rsp+370h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180067963  mov     [rsp+370h+lpEnvironment], rax; lpEnvironment
0x180067968  mov     [rsp+370h+dwCreationFlags], 400h; dwCreationFlags
0x180067970  mov     dword ptr [rsp+370h+phNewToken], 0; bInheritHandles
0x180067978  mov     qword ptr [rsp+370h+TokenType], 0; lpThreadAttributes
0x180067981  xor     r9d, r9d; lpProcessAttributes
0x180067984  lea     r8, [rbp+270h+CommandLine]; lpCommandLine
0x180067988  mov     rdx, [rsp+370h+lpApplicationName]; lpApplicationName
0x18006798d  call    cs:__imp_CreateProcessAsUserW
0x180067993  mov     rcx, [rbp+278h]; this
0x18006799a  test    eax, eax
0x18006799c  jz      loc_180067B0D
0x1800679a2  call    cs:__imp_GetCurrentProcess
0x1800679a8  mov     rbx, rax
0x1800679ab  call    cs:__imp_GetCurrentProcess
0x1800679b1  mov     r14d, 2
0x1800679b7  mov     [rsp+370h+dwCreationFlags], r14d; dwOptions
0x1800679bc  mov     dword ptr [rsp+370h+phNewToken], 0; bInheritHandle
0x1800679c4  mov     [rsp+370h+TokenType], 0; dwDesiredAccess
0x1800679cc  mov     r9, rsi; lpTargetHandle
0x1800679cf  mov     r8, rbx; hTargetProcessHandle
0x1800679d2  mov     rdx, [rsi]; hSourceHandle
0x1800679d5  mov     rcx, rax; hSourceProcessHandle
0x1800679d8  call    cs:__imp_DuplicateHandle
0x1800679de  mov     rcx, [rbp+278h]; this
0x1800679e5  test    eax, eax
0x1800679e7  jz      loc_180067B1F
0x1800679ed  call    cs:__imp_GetCurrentProcess
0x1800679f3  mov     rbx, rax
0x1800679f6  call    cs:__imp_GetCurrentProcess
0x1800679fc  mov     [rsp+370h+dwCreationFlags], r14d; dwOptions
0x180067a01  mov     dword ptr [rsp+370h+phNewToken], 0; bInheritHandle
0x180067a09  mov     [rsp+370h+TokenType], 0; dwDesiredAccess
0x180067a11  lea     r9, [rsi+8]; lpTargetHandle
0x180067a15  mov     r8, rbx; hTargetProcessHandle
0x180067a18  mov     rdx, [rsi+8]; hSourceHandle
0x180067a1c  mov     rcx, rax; hSourceProcessHandle
0x180067a1f  call    cs:__imp_DuplicateHandle
0x180067a25  mov     rcx, [rbp+278h]; this
0x180067a2c  test    eax, eax
0x180067a2e  jz      loc_180067AC2
0x180067a34  mov     rcx, [rsp+370h+lpApplicationName]; pv
0x180067a39  test    rcx, rcx
0x180067a3c  jz      short loc_180067A45
0x180067a3e  call    cs:__imp_CoTaskMemFree
0x180067a44  nop
0x180067a45  mov     rcx, [rsp+370h+Environment]; lpEnvironment
0x180067a4a  test    rcx, rcx
0x180067a4d  jz      short loc_180067A56
0x180067a4f  call    cs:__imp_DestroyEnvironmentBlock
0x180067a55  nop
0x180067a56  or      ebx, 0FFFFFFFFh
0x180067a59  mov     eax, ebx
0x180067a5b  lock xadd [rdi+8], eax
0x180067a60  add     eax, ebx
0x180067a62  jnz     short loc_180067A8D
0x180067a64  mov     rax, [rdi]
0x180067a67  mov     rcx, rdi
0x180067a6a  mov     rax, [rax]
0x180067a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a72  mov     eax, ebx
0x180067a74  lock xadd [rdi+0Ch], eax
0x180067a79  add     eax, ebx
0x180067a7b  jnz     short loc_180067A8D
0x180067a7d  mov     rdx, [rdi]
0x180067a80  mov     rcx, rdi
0x180067a83  mov     rax, [rdx+8]
0x180067a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a8c  nop
0x180067a8d  mov     rcx, r15
0x180067a90  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180067a95  nop
0x180067a96  mov     rcx, r12
0x180067a99  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180067a9e  mov     rax, rsi
0x180067aa1  mov     rcx, [rbp+270h+var_40]
0x180067aa8  xor     rcx, rsp; StackCookie
0x180067aab  call    __security_check_cookie
0x180067ab0  add     rsp, 340h
0x180067ab7  pop     r15
0x180067ab9  pop     r14
0x180067abb  pop     r12
0x180067abd  pop     rdi
0x180067abe  pop     rsi
0x180067abf  pop     rbx
0x180067ac0  pop     rbp
0x180067ac1  retn
0x180067ac2  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180067ac9  mov     edx, 47h ; 'G'; void *
0x180067ace  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180067ad4  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180067adb  mov     edx, 16h; void *
0x180067ae0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180067ae6  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180067aed  mov     edx, 1Ch; void *
0x180067af2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180067af8  mov     r9d, eax; char *
0x180067afb  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180067b02  mov     edx, 27h ; '''; void *
0x180067b07  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067b0d  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180067b14  mov     edx, 35h ; '5'; void *
0x180067b19  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180067b1f  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180067b26  mov     edx, 3Eh ; '>'; void *
0x180067b2b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
