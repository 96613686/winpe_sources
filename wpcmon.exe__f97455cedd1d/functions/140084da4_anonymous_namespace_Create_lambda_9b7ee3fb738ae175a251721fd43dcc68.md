# _anonymous_namespace_::Create__lambda_9b7ee3fb738ae175a251721fd43dcc68___

- ea: `0x140084da4`
- end: `0x140085175`
- name: `_anonymous_namespace_::Create__lambda_9b7ee3fb738ae175a251721fd43dcc68___`
- size: `977`
- prototype: `HANDLE *__fastcall(HANDLE *, HANDLE **, HANDLE *, __int64, __int64, LPSTARTUPINFOW, LPVOID *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14007fc64`

## callees

- `0x140005530`
- `0x140006314`
- `0x140006338`
- `0x14000b744`
- `0x14000ccac`
- `0x14000e41c`
- `0x14001c478`
- `0x14001c804`
- `0x14001f6b4`
- `0x1400231d4`
- `0x14002f3a0`
- `0x14003c368`
- `0x14003c3f8`
- `0x14005bbac`
- `0x140060e60`
- `0x140060f58`
- `0x140084c78`
- `0x140084d14`
- `0x140084da4`
- `0x1400a8010`

## import_xrefs

- `ADVAPI32!CreateProcessAsUserW` at `0x1400850a5`
- `ADVAPI32!CreateProcessAsUserW` at `0x1400850a5`
- `KERNEL32!CloseHandle` at `0x1400850c4`
- `KERNEL32!CloseHandle` at `0x1400850c4`
- `KERNEL32!GetLastError` at `0x140084f76`
- `KERNEL32!GetLastError` at `0x140085105`
- `KERNEL32!GetLastError` at `0x140084f76`
- `KERNEL32!GetLastError` at `0x140085105`
- `USERENV!CreateEnvironmentBlock` at `0x140084f5a`
- `USERENV!CreateEnvironmentBlock` at `0x140084f5a`

## pseudocode

```c
HANDLE *__fastcall anonymous_namespace_::Create__lambda_9b7ee3fb738ae175a251721fd43dcc68___(
        HANDLE *a1,
        HANDLE **a2,
        HANDLE *a3,
        __int64 a4,
        __int64 a5,
        LPSTARTUPINFOW a6,
        LPVOID *a7)
{
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  volatile signed __int32 *lpSecurityDescriptor; // rbx
  volatile signed __int32 *v15; // rbx
  signed int LastError; // eax
  const WCHAR *v17; // rax
  LPSTARTUPINFOW lpStartupInfo; // r10
  DWORD dwCreationFlags; // r11d
  BOOL bInheritHandles; // ebx
  struct _SECURITY_ATTRIBUTES *lpThreadAttributes; // rdx
  struct _SECURITY_ATTRIBUTES *v22; // r9
  WCHAR *v23; // r8
  char *hThread; // rcx
  signed int v26; // eax
  unsigned int v27; // ebx
  int v28; // eax
  __int64 v29; // r10
  LPVOID Environment; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h] BYREF
  __int128 v32; // [rsp+70h] [rbp-90h]
  struct _SECURITY_ATTRIBUTES ThreadAttributes; // [rsp+80h] [rbp-80h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v35; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v36[8]; // [rsp+C8h] [rbp-38h] BYREF
  const WCHAR *v37; // [rsp+D0h] [rbp-30h]
  LPWSTR lpCommandLine[4]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v40[40]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v41[64]; // [rsp+1A0h] [rbp+A0h] BYREF

  v31 = (__int64)a1;
  std::wstring::wstring(lpCommandLine, a4);
  Collections::Enumerable<std::wstring>::begin(a5, &v31);
  Collections::Enumerable<std::wstring>::end(v10, &ThreadAttributes);
  while ( v31 != *(_QWORD *)&ThreadAttributes.nLength )
  {
    v11 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v13 = v11[2];
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v13) < 2 )
      std::_Xlen_string();
    if ( v11[3] > 7u )
      v11 = (_QWORD *)*v11;
    std::wstring::wstring(v40, v13, v12, L" \"", 2, v11, v13);
    std::operator+<unsigned short>(pExceptionObject, v40);
    std::wstring::append(lpCommandLine);
    std::wstring::~wstring(pExceptionObject);
    std::wstring::~wstring(v40);
    Collections::Private::EnumerableIterator<std::pair<unsigned int,std::function<bool (DirectUI::Element &)>>>::operator++(&v31);
  }
  lpSecurityDescriptor = (volatile signed __int32 *)ThreadAttributes.lpSecurityDescriptor;
  if ( ThreadAttributes.lpSecurityDescriptor )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)ThreadAttributes.lpSecurityDescriptor + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))lpSecurityDescriptor)(lpSecurityDescriptor);
      if ( _InterlockedExchangeAdd(lpSecurityDescriptor + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)lpSecurityDescriptor + 8LL))(lpSecurityDescriptor);
    }
  }
  v15 = (volatile signed __int32 *)v32;
  if ( (_QWORD)v32 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v32 + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  Environment = 0;
  if ( a3
    && !CreateEnvironmentBlock(&Environment, *a3, 0)
    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      10,
      WPP_0ded210709da34c8e4c43a6ef699ad00_Traceguids,
      (unsigned int)LastError);
  }
  v31 = (__int64)Environment;
  ScopeGuard::ScopeGuard__lambda_3c703c8622ebb91cdf5ebfe81275bcfe___(v41, &v31);
  v35 = 104;
  memset_0(v36, 0, 0x60u);
  v17 = &SubKey;
  if ( a6 )
    v17 = v37;
  v37 = v17;
  lpStartupInfo = (LPSTARTUPINFOW)&v35;
  if ( a6 )
    lpStartupInfo = a6;
  dwCreationFlags = 525312;
  if ( lpStartupInfo->cb != 112 )
    dwCreationFlags = 1024;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  bInheritHandles = lpStartupInfo->cb == 112;
  if ( a7 )
  {
    *(_QWORD *)&ThreadAttributes.nLength = 24;
    *(_OWORD *)&ThreadAttributes.lpSecurityDescriptor = 0;
    ThreadAttributes.lpSecurityDescriptor = *a7;
    lpThreadAttributes = &ThreadAttributes;
    v31 = 24;
    v32 = (unsigned __int64)ThreadAttributes.lpSecurityDescriptor;
    v22 = (struct _SECURITY_ATTRIBUTES *)&v31;
  }
  else
  {
    v22 = 0;
    lpThreadAttributes = 0;
  }
  v23 = (WCHAR *)lpCommandLine;
  if ( lpCommandLine[3] > (LPWSTR)7 )
    v23 = lpCommandLine[0];
  if ( !CreateProcessAsUserW(
          **a2,
          0,
          v23,
          v22,
          lpThreadAttributes,
          bInheritHandles,
          dwCreationFlags,
          Environment,
          0,
          lpStartupInfo,
          &ProcessInformation) )
  {
    v26 = GetLastError();
    v27 = v26;
    if ( v26 > 0 )
      v27 = (unsigned __int16)v26 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v28 = std::wstring::c_str(lpCommandLine);
      WPP_SF_Sd(*(_QWORD *)(v29 + 16), 11, (unsigned int)WPP_0ded210709da34c8e4c43a6ef699ad00_Traceguids, v28, v27);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v27);
    throw (ErrorCodeException *)pExceptionObject;
  }
  hThread = (char *)ProcessInformation.hThread;
  *a1 = ProcessInformation.hProcess;
  if ( (unsigned __int64)(hThread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hThread);
  ScopeGuard::~ScopeGuard((ScopeGuard *)v41);
  std::wstring::~wstring(lpCommandLine);
  return a1;
}

```

## disassembly

```asm
0x140084da4  push    rbp
0x140084da6  push    rbx
0x140084da7  push    rsi
0x140084da8  push    rdi
0x140084da9  push    r13
0x140084dab  push    r14
0x140084dad  push    r15
0x140084daf  lea     rbp, [rsp-0F0h]
0x140084db7  sub     rsp, 1F0h
0x140084dbe  mov     rax, cs:__security_cookie
0x140084dc5  xor     rax, rsp
0x140084dc8  mov     [rbp+120h+var_40], rax
0x140084dcf  mov     rsi, r8
0x140084dd2  mov     r15, rdx
0x140084dd5  mov     rdi, rcx
0x140084dd8  mov     r14, [rbp+120h+arg_28]
0x140084ddf  mov     [rsp+220h+var_1B8], rcx
0x140084de4  mov     rbx, [rbp+120h+arg_20]
0x140084deb  mov     rdx, r9
0x140084dee  lea     rcx, [rbp+120h+lpCommandLine]
0x140084df2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140084df7  nop
0x140084df8  lea     rdx, [rsp+220h+var_1B8]
0x140084dfd  mov     rcx, rbx
0x140084e00  call    ?begin@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEBA?AV?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@2@XZ; Collections::Enumerable<std::wstring>::begin(void)
0x140084e05  nop
0x140084e06  lea     rdx, [rbp+120h+ThreadAttributes]
0x140084e0a  call    ?end@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEBA?AV?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@2@XZ; Collections::Enumerable<std::wstring>::end(void)
0x140084e0f  nop
0x140084e10  mov     rcx, [rsp+220h+var_1B8]
0x140084e15  cmp     rcx, qword ptr [rbp+120h+ThreadAttributes.nLength]
0x140084e19  jz      loc_140084EB4
0x140084e1f  mov     rax, [rcx]
0x140084e22  mov     rax, [rax+10h]
0x140084e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084e2b  mov     rcx, rax
0x140084e2e  mov     rdx, [rax+10h]
0x140084e32  mov     rax, 7FFFFFFFFFFFFFFEh
0x140084e3c  sub     rax, rdx
0x140084e3f  cmp     rax, 2
0x140084e43  jb      loc_14008516F
0x140084e49  cmp     qword ptr [rcx+18h], 7
0x140084e4e  jbe     short loc_140084E53
0x140084e50  mov     rcx, [rcx]
0x140084e53  mov     qword ptr [rsp+220h+dwCreationFlags], rdx
0x140084e58  mov     qword ptr [rsp+220h+bInheritHandles], rcx
0x140084e5d  mov     [rsp+220h+lpThreadAttributes], 2
0x140084e66  lea     r9, asc_1400B8C90; " \""
0x140084e6d  lea     rcx, [rbp+120h+var_A8]
0x140084e71  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x140084e76  nop
0x140084e77  lea     rdx, [rbp+120h+var_A8]
0x140084e7b  lea     rcx, [rbp+120h+pExceptionObject]
0x140084e7f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@G@Z; std::operator+<ushort>(std::wstring &&,ushort)
0x140084e84  nop
0x140084e85  mov     rdx, rax
0x140084e88  lea     rcx, [rbp+120h+lpCommandLine]; Src
0x140084e8c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x140084e91  nop
0x140084e92  lea     rcx, [rbp+120h+pExceptionObject]
0x140084e96  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140084e9b  nop
0x140084e9c  lea     rcx, [rbp+120h+var_A8]
0x140084ea0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140084ea5  lea     rcx, [rsp+220h+var_1B8]
0x140084eaa  call    ??E?$EnumerableIterator@U?$pair@IV?$function@$$A6A_NAEAVElement@DirectUI@@@Z@std@@@std@@@Private@Collections@@QEAAAEAV012@XZ; Collections::Private::EnumerableIterator<std::pair<uint,std::function<bool (DirectUI::Element &)>>>::operator++(void)
0x140084eaf  jmp     loc_140084E10
0x140084eb4  mov     rbx, [rbp+120h+ThreadAttributes.lpSecurityDescriptor]
0x140084eb8  or      r13d, 0FFFFFFFFh
0x140084ebc  test    rbx, rbx
0x140084ebf  jz      short loc_140084EF9
0x140084ec1  mov     eax, r13d
0x140084ec4  lock xadd [rbx+8], eax
0x140084ec9  add     eax, r13d
0x140084ecc  jnz     short loc_140084EF9
0x140084ece  mov     rax, [rbx]
0x140084ed1  mov     rcx, rbx
0x140084ed4  mov     rax, [rax]
0x140084ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084edc  mov     eax, r13d
0x140084edf  lock xadd [rbx+0Ch], eax
0x140084ee4  add     eax, r13d
0x140084ee7  jnz     short loc_140084EF9
0x140084ee9  mov     rax, [rbx]
0x140084eec  mov     rcx, rbx
0x140084eef  mov     rax, [rax+8]
0x140084ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084ef8  nop
0x140084ef9  mov     rbx, qword ptr [rsp+220h+var_1B0]
0x140084efe  test    rbx, rbx
0x140084f01  jz      short loc_140084F3A
0x140084f03  mov     eax, r13d
0x140084f06  lock xadd [rbx+8], eax
0x140084f0b  add     eax, r13d
0x140084f0e  jnz     short loc_140084F3A
0x140084f10  mov     rax, [rbx]
0x140084f13  mov     rcx, rbx
0x140084f16  mov     rax, [rax]
0x140084f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084f1e  mov     eax, r13d
0x140084f21  lock xadd [rbx+0Ch], eax
0x140084f26  add     eax, r13d
0x140084f29  jnz     short loc_140084F3A
0x140084f2b  mov     rax, [rbx]
0x140084f2e  mov     rcx, rbx
0x140084f31  mov     rax, [rax+8]
0x140084f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084f3a  mov     [rsp+220h+Environment], 0
0x140084f43  lea     r13, WPP_GLOBAL_Control
0x140084f4a  test    rsi, rsi
0x140084f4d  jz      short loc_140084FA7
0x140084f4f  xor     r8d, r8d; bInherit
0x140084f52  mov     rdx, [rsi]; hToken
0x140084f55  lea     rcx, [rsp+220h+Environment]; lpEnvironment
0x140084f5a  call    cs:__imp_CreateEnvironmentBlock
0x140084f60  test    eax, eax
0x140084f62  jnz     short loc_140084FA7
0x140084f64  mov     rax, cs:WPP_GLOBAL_Control
0x140084f6b  cmp     rax, r13
0x140084f6e  jz      short loc_140084FA7
0x140084f70  test    byte ptr [rax+1Ch], 1
0x140084f74  jz      short loc_140084FA7
0x140084f76  call    cs:__imp_GetLastError
0x140084f7c  test    eax, eax
0x140084f7e  jle     short loc_140084F88
0x140084f80  movzx   eax, ax
0x140084f83  or      eax, 80070000h
0x140084f88  mov     edx, 0Ah
0x140084f8d  mov     r9d, eax
0x140084f90  lea     r8, WPP_0ded210709da34c8e4c43a6ef699ad00_Traceguids
0x140084f97  mov     rcx, cs:WPP_GLOBAL_Control
0x140084f9e  mov     rcx, [rcx+10h]
0x140084fa2  call    WPP_SF_d
0x140084fa7  mov     rax, [rsp+220h+Environment]
0x140084fac  mov     [rsp+220h+var_1B8], rax
0x140084fb1  lea     rdx, [rsp+220h+var_1B8]
0x140084fb6  lea     rcx, [rbp+120h+var_80]
0x140084fbd  call    ScopeGuard__ScopeGuard__lambda_3c703c8622ebb91cdf5ebfe81275bcfe___
0x140084fc2  nop
0x140084fc3  mov     [rbp+120h+var_160], 68h ; 'h'
0x140084fcb  xor     edx, edx; Val
0x140084fcd  lea     r8d, [rdx+60h]; Size
0x140084fd1  lea     rcx, [rbp+120h+var_158]; void *
0x140084fd5  call    memset_0
0x140084fda  lea     rax, SubKey
0x140084fe1  test    r14, r14
0x140084fe4  cmovnz  rax, [rbp+120h+var_150]
0x140084fe9  mov     [rbp+120h+var_150], rax
0x140084fed  lea     r10, [rbp+120h+var_160]
0x140084ff1  cmovnz  r10, r14
0x140084ff5  mov     eax, 400h
0x140084ffa  mov     r11d, 80400h
0x140085000  cmp     dword ptr [r10], 70h ; 'p'
0x140085004  cmovnz  r11d, eax
0x140085008  xorps   xmm0, xmm0
0x14008500b  xor     eax, eax
0x14008500d  movups  xmmword ptr [rbp+120h+ProcessInformation.hProcess], xmm0
0x140085011  mov     qword ptr [rbp+120h+ProcessInformation.dwProcessId], rax
0x140085015  mov     rsi, [rsp+220h+Environment]
0x14008501a  xor     ebx, ebx
0x14008501c  cmp     dword ptr [r10], 70h ; 'p'
0x140085020  setz    bl
0x140085023  mov     rcx, [rbp+120h+arg_30]
0x14008502a  test    rcx, rcx
0x14008502d  jz      short loc_140085060
0x14008502f  mov     qword ptr [rbp+120h+ThreadAttributes.nLength], 18h
0x140085037  movups  xmmword ptr [rbp+120h+ThreadAttributes.lpSecurityDescriptor], xmm0
0x14008503b  mov     rax, [rcx]
0x14008503e  mov     [rbp+120h+ThreadAttributes.lpSecurityDescriptor], rax
0x140085042  lea     rdx, [rbp+120h+ThreadAttributes]
0x140085046  mov     [rsp+220h+var_1B8], 18h
0x14008504f  movups  [rsp+220h+var_1B0], xmm0
0x140085054  mov     qword ptr [rsp+220h+var_1B0], rax
0x140085059  lea     r9, [rsp+220h+var_1B8]
0x14008505e  jmp     short loc_140085065
0x140085060  xor     r9d, r9d; lpProcessAttributes
0x140085063  xor     edx, edx
0x140085065  lea     r8, [rbp+120h+lpCommandLine]
0x140085069  cmp     [rbp+120h+var_D8], 7
0x14008506e  cmova   r8, [rbp+120h+lpCommandLine]; lpCommandLine
0x140085073  mov     rcx, [r15]
0x140085076  lea     rax, [rbp+120h+ProcessInformation]
0x14008507a  mov     [rsp+220h+lpProcessInformation], rax; lpProcessInformation
0x14008507f  mov     [rsp+220h+lpStartupInfo], r10; lpStartupInfo
0x140085084  mov     [rsp+220h+lpCurrentDirectory], 0; lpCurrentDirectory
0x14008508d  mov     [rsp+220h+lpEnvironment], rsi; lpEnvironment
0x140085092  mov     [rsp+220h+dwCreationFlags], r11d; dwCreationFlags
0x140085097  mov     [rsp+220h+bInheritHandles], ebx; bInheritHandles
0x14008509b  mov     [rsp+220h+lpThreadAttributes], rdx; lpThreadAttributes
0x1400850a0  xor     edx, edx; lpApplicationName
0x1400850a2  mov     rcx, [rcx]; hToken
0x1400850a5  call    cs:__imp_CreateProcessAsUserW
0x1400850ab  test    eax, eax
0x1400850ad  jz      short loc_140085105
0x1400850af  mov     rcx, [rbp+120h+ProcessInformation.hThread]; hObject
0x1400850b3  mov     rax, [rbp+120h+ProcessInformation.hProcess]
0x1400850b7  mov     [rdi], rax
0x1400850ba  lea     rdx, [rcx-1]
0x1400850be  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1400850c2  ja      short loc_1400850CB
0x1400850c4  call    cs:__imp_CloseHandle
0x1400850ca  nop
0x1400850cb  lea     rcx, [rbp+120h+var_80]; this
0x1400850d2  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x1400850d7  nop
0x1400850d8  lea     rcx, [rbp+120h+lpCommandLine]
0x1400850dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400850e1  mov     rax, rdi
0x1400850e4  mov     rcx, [rbp+120h+var_40]
0x1400850eb  xor     rcx, rsp; StackCookie
0x1400850ee  call    __security_check_cookie
0x1400850f3  add     rsp, 1F0h
0x1400850fa  pop     r15
0x1400850fc  pop     r14
0x1400850fe  pop     r13
0x140085100  pop     rdi
0x140085101  pop     rsi
0x140085102  pop     rbx
0x140085103  pop     rbp
0x140085104  retn
0x140085105  call    cs:__imp_GetLastError
0x14008510b  nop
0x14008510c  mov     ebx, eax
0x14008510e  test    eax, eax
0x140085110  jle     short loc_14008511B
0x140085112  movzx   ebx, ax
0x140085115  or      ebx, 80070000h
0x14008511b  mov     r10, cs:WPP_GLOBAL_Control
0x140085122  cmp     r10, r13
0x140085125  jz      short loc_140085153
0x140085127  test    byte ptr [r10+1Ch], 1
0x14008512c  jz      short loc_140085153
0x14008512e  lea     rcx, [rbp+120h+lpCommandLine]
0x140085132  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x140085137  mov     edx, 0Bh
0x14008513c  mov     dword ptr [rsp+220h+lpThreadAttributes], ebx
0x140085140  mov     r9, rax
0x140085143  lea     r8, WPP_0ded210709da34c8e4c43a6ef699ad00_Traceguids
0x14008514a  mov     rcx, [r10+10h]
0x14008514e  call    WPP_SF_Sd
0x140085153  mov     edx, ebx; int
0x140085155  lea     rcx, [rbp+120h+pExceptionObject]; this
0x140085159  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14008515e  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140085165  lea     rcx, [rbp+120h+pExceptionObject]; pExceptionObject
0x140085169  call    _CxxThrowException_0
0x14008516f  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
