# Windows::Usage::GetUserDisplayState(void)

- ea: `0x1800952b0`
- end: `0x18009571b`
- name: `?GetUserDisplayState@Usage@Windows@@AEBA?AW4DisplayState@12@XZ`
- size: `1131`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180095110`
- `0x180095130`
- `0x180095160`
- `0x180095730`

## callees

- `0x180008ea8`
- `0x180009074`
- `0x18000f3a8`
- `0x180010890`
- `0x1800108b4`
- `0x180010e80`
- `0x180010f24`
- `0x1800112d0`
- `0x180011320`
- `0x18001151c`
- `0x180011680`
- `0x1800420e0`
- `0x1800629dc`
- `0x180064ed4`
- `0x180068874`
- `0x18006ea28`
- `0x1800952b0`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800954eb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800954eb`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180095519`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180095519`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800952ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095555`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095570`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009559b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800955af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800952ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095555`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095570`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009559b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800955af`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1800955e7`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1800955e7`
- `SHELL32!SHQueryUserNotificationState` at `0x1800955fc`
- `SHELL32!SHQueryUserNotificationState` at `0x1800955fc`

## string_xrefs

- `0x180095709`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18009565e`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x180095681`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x18009569d`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x1800956b9`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x1800956cb`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x1800956dd`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`

## pseudocode

```c
__int64 Windows::Usage::GetUserDisplayState()
{
  char IsLocalSystem; // bl
  __int64 *System; // rax
  __int64 (__fastcall *v2)(__int64, _BYTE *, _QWORD *); // rbx
  __int16 *traits_2_unsigned_short; // rax
  const char *v4; // r9
  __int64 v5; // r11
  __int64 v6; // rax
  _QWORD *v7; // rax
  __int64 v8; // r8
  volatile signed __int32 *v9; // rbx
  volatile signed __int32 *v10; // rbx
  WCHAR *v11; // rax
  DWORD v12; // eax
  const char *v13; // r9
  const char *v14; // r9
  DWORD v15; // ebx
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  unsigned int v19; // r8d
  const char *v20; // r9
  HRESULT v22; // eax
  _QWORD *v23; // rax
  _BYTE *v24; // rcx
  unsigned int v25; // eax
  int v26; // [rsp+28h] [rbp-E0h]
  unsigned int v27; // [rsp+28h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v29[3]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+70h] [rbp-98h] BYREF
  volatile signed __int32 *v31; // [rsp+78h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-88h] BYREF
  volatile signed __int32 *v33; // [rsp+88h] [rbp-80h]
  WCHAR v34[16]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v35[32]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v36[32]; // [rsp+D0h] [rbp-38h] BYREF
  HANDLE hHandle; // [rsp+F0h] [rbp-18h] BYREF
  HANDLE v38; // [rsp+F8h] [rbp-10h]
  DWORD ExitCode; // [rsp+108h] [rbp+0h] BYREF
  __int128 v40; // [rsp+110h] [rbp+8h] BYREF
  unsigned int v41[4]; // [rsp+120h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+38h]

  hObject[0] = 0;
  IsLocalSystem = Windows::Trust::IsLocalSystem((__int64)hObject);
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
  if ( !IsLocalSystem )
  {
    if ( IsApiSetImplemented("ext-ms-win-shell-shell32-l1-2-0") )
    {
      ExitCode = 5;
      v22 = SHQueryUserNotificationState((QUERY_USER_NOTIFICATION_STATE *)&ExitCode);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x198,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
          (const char *)(unsigned int)v22,
          v26);
      v23 = (_QWORD *)*((_QWORD *)qword_180150918 + 1);
      HIDWORD(v38) = 0;
      v24 = qword_180150918;
      while ( !*((_BYTE *)v23 + 25) )
      {
        if ( *((_DWORD *)v23 + 7) >= (signed int)ExitCode )
          v24 = v23;
        else
          v23 += 2;
        v23 = (_QWORD *)*v23;
      }
      if ( v24[25] || (signed int)ExitCode < *((_DWORD *)v24 + 7) )
        v24 = qword_180150918;
      if ( v24 != qword_180150918 )
        return *((unsigned int *)v24 + 8);
    }
    return 0;
  }
  hObject[0] = 0;
  Windows::CallerToken::GetMostPreferredLoggedOnSessionToken((WCHAR *)hObject);
  if ( (unsigned __int64)hObject[0] - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    return 0;
  System = SystemInterface::Service::GetSystem(&v32);
  v2 = *(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*System + 8LL))(
                                                                             *System,
                                                                             &v30)
                                                            + 48LL);
  traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                         L"DisplayCheck",
                                         word_18012490A,
                                         0);
  if ( traits_2_unsigned_short == word_18012490A
    || (v6 = ((char *)traits_2_unsigned_short - (char *)L"DisplayCheck") >> 1, v6 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v4);
  }
  v29[0] = L"DisplayCheck";
  v29[1] = v6;
  v7 = (_QWORD *)v2(v5, v35, v29);
  if ( v7[3] > 7u )
    v7 = (_QWORD *)*v7;
  v40 = 0;
  *(_OWORD *)v41 = 0;
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)v7 + v8) );
  std::wstring::_Construct<1,wchar_t const *>(&v40, v7);
  std::wstring::~wstring(v35);
  v9 = v31;
  if ( v31 )
  {
    if ( _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  v10 = v33;
  if ( v33 )
  {
    if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  v29[2] = v34;
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - *(_QWORD *)v41) < 0x13 )
    std::_Xlen_string();
  std::wstring::wstring(v34, *(__int64 *)v41, L" /NotificationState", 19);
  v11 = (WCHAR *)std::wstring::wstring(v36, &v40);
  Windows::ProcessHelpers::CreateProcessAsUserToken(&hHandle, hObject, v11, v34);
  v12 = WaitForSingleObject(hHandle, 0x7530u);
  if ( v12 )
  {
    if ( v12 != 258 )
    {
      if ( v12 == -1 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x186,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
          v13);
      v25 = wil::verify_hresult(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x18A,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
        (const char *)v25,
        v27);
    }
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x182,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
      (const char *)0x5B4,
      v27);
  }
  ExitCode = 0;
  if ( !GetExitCodeProcess(hHandle, &ExitCode) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x18F,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
      v14);
  v15 = ExitCode;
  v16 = (const char *)((unsigned __int16)ExitCode | 0x80070000);
  if ( (int)ExitCode <= 0 )
    v16 = (const char *)ExitCode;
  if ( ExitCode > 3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x191,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
      v16,
      v27);
  if ( hHandle && !CloseHandle(hHandle) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v17, v18);
  if ( v38 && !CloseHandle(v38) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v19, v20);
  std::wstring::~wstring(&v40);
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
  return v15;
}

```

## disassembly

```asm
0x1800952b0  mov     rax, rsp
0x1800952b3  mov     [rax+8], rbx
0x1800952b7  mov     [rax+10h], rsi
0x1800952bb  mov     [rax+18h], rdi
0x1800952bf  mov     [rax+20h], r14
0x1800952c3  push    rbp
0x1800952c4  lea     rbp, [rax-38h]
0x1800952c8  sub     rsp, 130h
0x1800952cf  mov     rax, cs:__security_cookie
0x1800952d6  xor     rax, rsp
0x1800952d9  mov     [rbp+30h+var_8], rax
0x1800952dd  xor     esi, esi
0x1800952df  mov     [rsp+130h+hObject], rsi
0x1800952e4  lea     rcx, [rsp+130h+hObject]
0x1800952e9  call    ?IsLocalSystem@Trust@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Trust::IsLocalSystem(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x1800952ee  mov     bl, al
0x1800952f0  mov     rcx, [rsp+130h+hObject]; hObject
0x1800952f5  lea     rdx, [rcx-1]
0x1800952f9  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800952fd  ja      short loc_180095305
0x1800952ff  call    cs:__imp_CloseHandle
0x180095305  test    bl, bl
0x180095307  jz      loc_1800955E0
0x18009530d  mov     [rsp+130h+hObject], rsi
0x180095312  lea     rcx, [rsp+130h+hObject]
0x180095317  call    ?GetMostPreferredLoggedOnSessionToken@CallerToken@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(void)
0x18009531c  nop
0x18009531d  mov     rcx, [rsp+130h+hObject]; hObject
0x180095322  lea     rax, [rcx-1]
0x180095326  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009532a  ja      loc_1800955A5
0x180095330  lea     rcx, [rsp+130h+var_B8]
0x180095335  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18009533a  nop
0x18009533b  mov     rcx, [rax]
0x18009533e  mov     rax, [rcx]
0x180095341  lea     rdx, [rsp+130h+var_C8]
0x180095346  mov     rax, [rax+8]
0x18009534a  call    _guard_dispatch_icall
0x18009534f  nop
0x180095350  mov     r11, [rax]
0x180095353  mov     rax, [r11]
0x180095356  mov     rbx, [rax+30h]
0x18009535a  xor     r8d, r8d
0x18009535d  lea     rdi, word_18012490A
0x180095364  mov     rdx, rdi
0x180095367  lea     r14, aDisplaycheck; "DisplayCheck"
0x18009536e  mov     rcx, r14
0x180095371  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180095376  cmp     rax, rdi
0x180095379  jz      loc_180095705
0x18009537f  sub     rax, r14
0x180095382  sar     rax, 1
0x180095385  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180095389  cmp     rax, rdi
0x18009538c  jz      loc_180095705
0x180095392  mov     [rsp+130h+var_E0], r14
0x180095397  mov     [rsp+130h+var_D8], rax
0x18009539c  lea     r8, [rsp+130h+var_E0]
0x1800953a1  lea     rdx, [rbp+30h+var_88]
0x1800953a5  mov     rcx, r11
0x1800953a8  mov     rax, rbx
0x1800953ab  call    _guard_dispatch_icall
0x1800953b0  nop
0x1800953b1  cmp     qword ptr [rax+18h], 7
0x1800953b6  jbe     short loc_1800953BB
0x1800953b8  mov     rax, [rax]
0x1800953bb  xorps   xmm0, xmm0
0x1800953be  movups  [rbp+30h+var_28], xmm0
0x1800953c2  xorps   xmm1, xmm1
0x1800953c5  movdqu  xmmword ptr [rbp+30h+var_18], xmm1
0x1800953ca  mov     r8, rdi
0x1800953cd  inc     r8
0x1800953d0  cmp     [rax+r8*2], si
0x1800953d5  jnz     short loc_1800953CD
0x1800953d7  mov     rdx, rax
0x1800953da  lea     rcx, [rbp+30h+var_28]
0x1800953de  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800953e3  nop
0x1800953e4  lea     rcx, [rbp+30h+var_88]; void *
0x1800953e8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800953ed  nop
0x1800953ee  mov     rbx, [rsp+130h+var_C0]
0x1800953f3  test    rbx, rbx
0x1800953f6  jz      short loc_18009542C
0x1800953f8  mov     eax, edi
0x1800953fa  lock xadd [rbx+8], eax
0x1800953ff  add     eax, edi
0x180095401  jnz     short loc_18009542C
0x180095403  mov     rax, [rbx]
0x180095406  mov     rcx, rbx
0x180095409  mov     rax, [rax]
0x18009540c  call    _guard_dispatch_icall
0x180095411  mov     eax, edi
0x180095413  lock xadd [rbx+0Ch], eax
0x180095418  add     eax, edi
0x18009541a  jnz     short loc_18009542C
0x18009541c  mov     rax, [rbx]
0x18009541f  mov     rcx, rbx
0x180095422  mov     rax, [rax+8]
0x180095426  call    _guard_dispatch_icall
0x18009542b  nop
0x18009542c  mov     rbx, [rbp+30h+var_B0]
0x180095430  test    rbx, rbx
0x180095433  jz      short loc_180095468
0x180095435  mov     eax, edi
0x180095437  lock xadd [rbx+8], eax
0x18009543c  add     eax, edi
0x18009543e  jnz     short loc_180095468
0x180095440  mov     rax, [rbx]
0x180095443  mov     rcx, rbx
0x180095446  mov     rax, [rax]
0x180095449  call    _guard_dispatch_icall
0x18009544e  mov     eax, edi
0x180095450  lock xadd [rbx+0Ch], eax
0x180095455  add     eax, edi
0x180095457  jnz     short loc_180095468
0x180095459  mov     rax, [rbx]
0x18009545c  mov     rcx, rbx
0x18009545f  mov     rax, [rax+8]
0x180095463  call    _guard_dispatch_icall
0x180095468  lea     rax, [rbp+30h+var_A8]
0x18009546c  mov     qword ptr [rsp+130h+var_D0], rax
0x180095471  mov     rax, 7FFFFFFFFFFFFFFEh
0x18009547b  mov     rcx, qword ptr [rbp+30h+var_18]
0x18009547f  sub     rax, rcx
0x180095482  cmp     rax, 13h
0x180095486  jb      loc_180095693
0x18009548c  lea     r9, [rbp+30h+var_28]
0x180095490  cmp     qword ptr [rbp+30h+var_18+8], 7
0x180095495  cmova   r9, qword ptr [rbp+30h+var_28]
0x18009549a  mov     [rsp+130h+var_100], 13h; __int64
0x1800954a3  lea     rax, aNotificationst; " /NotificationState"
0x1800954aa  mov     [rsp+130h+Src], rax; Src
0x1800954af  mov     qword ptr [rsp+130h+var_110], rcx; int
0x1800954b4  lea     rcx, [rbp+30h+var_A8]; void *
0x1800954b8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800954bd  nop
0x1800954be  lea     rdx, [rbp+30h+var_28]
0x1800954c2  lea     rcx, [rbp+30h+var_68]
0x1800954c6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800954cb  nop
0x1800954cc  lea     r9, [rbp+30h+var_A8]
0x1800954d0  mov     r8, rax
0x1800954d3  lea     rdx, [rsp+130h+hObject]
0x1800954d8  lea     rcx, [rbp+30h+hHandle]; lpTargetHandle
0x1800954dc  call    ?CreateProcessAsUserToken@ProcessHelpers@Windows@@YA?AV?$unique_struct@U_PROCESS_INFORMATION@@P6AXPEAU1@@Z$1?CloseProcessInformation@details@wil@@YAX0@Z$$T$0A@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@4@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; Windows::ProcessHelpers::CreateProcessAsUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::wstring,std::wstring)
0x1800954e1  nop
0x1800954e2  mov     edx, 7530h; dwMilliseconds
0x1800954e7  mov     rcx, [rbp+30h+hHandle]; hHandle
0x1800954eb  call    cs:__imp_WaitForSingleObject
0x1800954f1  test    eax, eax
0x1800954f3  jz      short loc_18009550E
0x1800954f5  cmp     eax, 102h
0x1800954fa  jz      loc_1800956AF
0x180095500  cmp     eax, 0FFFFFFFFh
0x180095503  jnz     loc_180095670
0x180095509  jmp     loc_180095699
0x18009550e  mov     [rbp+30h+ExitCode], esi
0x180095511  lea     rdx, [rbp+30h+ExitCode]; lpExitCode
0x180095515  mov     rcx, [rbp+30h+hHandle]; hProcess
0x180095519  call    cs:__imp_GetExitCodeProcess
0x18009551f  mov     rcx, [rbp+38h]; this
0x180095523  test    eax, eax
0x180095525  jz      loc_1800956CB
0x18009552b  mov     ebx, [rbp+30h+ExitCode]
0x18009552e  movzx   r9d, bx
0x180095532  or      r9d, 80070000h
0x180095539  test    ebx, ebx
0x18009553b  cmovle  r9d, ebx; char *
0x18009553f  mov     rcx, [rbp+38h]; this
0x180095543  cmp     ebx, 3
0x180095546  ja      loc_1800956DD
0x18009554c  mov     rcx, [rbp+30h+hHandle]; hObject
0x180095550  test    rcx, rcx
0x180095553  jz      short loc_180095567
0x180095555  call    cs:__imp_CloseHandle
0x18009555b  mov     rcx, [rbp+38h]; this
0x18009555f  test    eax, eax
0x180095561  jz      loc_1800956EF
0x180095567  mov     rcx, [rbp+30h+var_40]; hObject
0x18009556b  test    rcx, rcx
0x18009556e  jz      short loc_180095582
0x180095570  call    cs:__imp_CloseHandle
0x180095576  mov     rcx, [rbp+38h]; this
0x18009557a  test    eax, eax
0x18009557c  jz      loc_1800956FA
0x180095582  lea     rcx, [rbp+30h+var_28]; void *
0x180095586  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009558b  nop
0x18009558c  mov     rcx, [rsp+130h+hObject]; hObject
0x180095591  lea     rdx, [rcx-1]
0x180095595  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180095599  ja      short loc_1800955A1
0x18009559b  call    cs:__imp_CloseHandle
0x1800955a1  mov     eax, ebx
0x1800955a3  jmp     short loc_1800955B7
0x1800955a5  lea     rax, [rcx-1]
0x1800955a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800955ad  ja      short loc_1800955B5
0x1800955af  call    cs:__imp_CloseHandle
0x1800955b5  xor     eax, eax
0x1800955b7  mov     rcx, [rbp+30h+var_8]
0x1800955bb  xor     rcx, rsp; StackCookie
0x1800955be  call    __security_check_cookie
0x1800955c3  lea     r11, [rsp+130h+var_s0]
0x1800955cb  mov     rbx, [r11+10h]
0x1800955cf  mov     rsi, [r11+18h]
0x1800955d3  mov     rdi, [r11+20h]
0x1800955d7  mov     r14, [r11+28h]
0x1800955db  mov     rsp, r11
0x1800955de  pop     rbp
0x1800955df  retn
0x1800955e0  lea     rcx, aExtMsWinShellS; "ext-ms-win-shell-shell32-l1-2-0"
0x1800955e7  call    cs:__imp_IsApiSetImplemented
0x1800955ed  test    eax, eax
0x1800955ef  jz      short loc_1800955B5
0x1800955f1  mov     [rbp+30h+ExitCode], 5
0x1800955f8  lea     rcx, [rbp+30h+ExitCode]; pquns
0x1800955fc  call    cs:__imp_SHQueryUserNotificationState
0x180095602  test    eax, eax
0x180095604  js      short loc_180095657
0x180095606  mov     rdx, cs:qword_180150918
0x18009560d  mov     rax, [rdx+8]
0x180095611  xor     ecx, ecx
0x180095613  mov     dword ptr [rbp+30h+var_40+4], ecx
0x180095616  mov     rcx, rdx
0x180095619  mov     r8d, [rbp+30h+ExitCode]
0x18009561d  jmp     short loc_180095631
0x18009561f  cmp     [rax+1Ch], r8d
0x180095623  jge     short loc_18009562B
0x180095625  add     rax, 10h
0x180095629  jmp     short loc_18009562E
0x18009562b  mov     rcx, rax
0x18009562e  mov     rax, [rax]
0x180095631  cmp     [rax+19h], sil
0x180095635  jz      short loc_18009561F
0x180095637  cmp     [rcx+19h], sil
0x18009563b  jnz     short loc_180095643
0x18009563d  cmp     r8d, [rcx+1Ch]
0x180095641  jge     short loc_180095646
0x180095643  mov     rcx, rdx
0x180095646  cmp     rcx, rdx
0x180095649  jz      loc_1800955B5
0x18009564f  mov     eax, [rcx+20h]
0x180095652  jmp     loc_1800955B7
0x180095657  mov     rcx, [rbp+38h]; this
0x18009565b  mov     r9d, eax; char *
0x18009565e  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180095665  mov     edx, 198h; void *
0x18009566a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180095670  mov     ecx, 8000FFFFh
0x180095675  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x18009567a  mov     r9d, eax; char *
0x18009567d  mov     rcx, [rbp+38h]; this
0x180095681  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180095688  mov     edx, 18Ah; void *
0x18009568d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180095693  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180095699  mov     rcx, [rbp+38h]; this
0x18009569d  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800956a4  mov     edx, 186h; void *
0x1800956a9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800956af  mov     rcx, [rbp+38h]; this
0x1800956b3  mov     r9d, 5B4h; char *
0x1800956b9  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800956c0  mov     edx, 182h; void *
0x1800956c5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800956cb  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800956d2  mov     edx, 18Fh; void *
0x1800956d7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800956dd  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800956e4  mov     edx, 191h; void *
0x1800956e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800956ef  mov     edx, 9D1h; void *
0x1800956f4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800956fa  mov     edx, 9D1h; void *
0x1800956ff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180095705  mov     rcx, [rbp+38h]; this
0x180095709  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180095710  mov     edx, 0C9h; void *
0x180095715  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
