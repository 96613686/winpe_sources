# CBrokeredLauncher::ValidateOrGetQuirkEnabledCallerWindow(Windows::System::ILauncherStatics *,bool *,HWND__ * *)

- ea: `0x1800726f8`
- end: `0x1800729af`
- name: `?ValidateOrGetQuirkEnabledCallerWindow@CBrokeredLauncher@@CAXPEAUILauncherStatics@System@Windows@@PEA_NPEAPEAUHWND__@@@Z`
- size: `695`
- prototype: `void __fastcall(struct Windows::System::ILauncherStatics *, bool *, HWND *)`
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800509cc`
- `0x18005101c`
- `0x180051644`
- `0x1800539c0`
- `0x180085f20`

## callees

- `0x18000f194`
- `0x18003ab7c`
- `0x180042254`
- `0x180053018`
- `0x1800596d8`
- `0x18006323c`
- `0x1800717d0`
- `0x1800726f8`
- `0x180079db8`
- `0x1800b73a4`
- `0x1800e2ff8`
- `0x1800eca7c`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180072849`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180072849`
- `ntdll!RtlInitUnicodeString` at `0x1800727b5`
- `ntdll!RtlInitUnicodeString` at `0x1800727b5`
- `ntdll!RtlCapabilityCheck` at `0x1800727cd`
- `ntdll!RtlCapabilityCheck` at `0x1800727cd`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabledForProcess` at `0x18007273f`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabledForProcess` at `0x18007273f`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x180072870`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x180072870`

## string_xrefs

- `0x180072751`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18007281e`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180072882`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800728cb`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18007290b`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180072951`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall CBrokeredLauncher::ValidateOrGetQuirkEnabledCallerWindow(
        struct Windows::System::ILauncherStatics *a1,
        bool *a2,
        HWND *a3)
{
  int IsEnabledForProcess; // eax
  bool v7; // bl
  int v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  DWORD ProcessId; // eax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  _QWORD *v17; // rax
  int v18; // eax
  const char *v19; // r9
  HANDLE Process; // [rsp+20h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v23; // [rsp+78h] [rbp+10h] BYREF
  __int64 *v24; // [rsp+80h] [rbp+18h] BYREF
  __int64 *v25; // [rsp+88h] [rbp+20h] BYREF

  *a3 = 0;
  wil::GetProcessHandleForClientOfObject(&v24, a1, 4112);
  LODWORD(v23) = 0;
  IsEnabledForProcess = QuirkIsEnabledForProcess(v24, 1114139, &v23);
  if ( IsEnabledForProcess < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x438,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)IsEnabledForProcess,
      (int)Process);
  v7 = (_DWORD)v23 != 0;
  wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v24);
  *a2 = v7;
  if ( v7 )
  {
    try
    {
      wil::GetProcessHandleForClientOfObject(&Process, a1, 4096);
      ProcessId = GetProcessId(Process);
      v25 = 0;
      v12 = CoreQueryApplicationService(
              ProcessId,
              &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1,
              &GUID_1ada0e3e_e4a2_4123_b451_dc96bf800419,
              &v25);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x461,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
          (const char *)(unsigned int)v12,
          (int)Process);
      v24 = 0;
      v13 = *v25;
      v24 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v13 + 64))(v25, &v24);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x464,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
          (const char *)(unsigned int)v14,
          (int)Process);
      v23 = 0;
      v15 = *v24;
      v23 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v15 + 48))(v24, &v23);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x467,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
          (const char *)(unsigned int)v16,
          (int)Process);
      if ( v23 )
      {
        v17 = (_QWORD *)wil::com_ptr_t<Windows::UI::Core::ICoreWindow,wil::err_exception_policy>::query<ICoreWindowInterop>(
                          &v23,
                          &DestinationString);
        v18 = (*(__int64 (__fastcall **)(_QWORD, HWND *))(*(_QWORD *)*v17 + 24LL))(*v17, a3);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x46B,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
            (const char *)(unsigned int)v18,
            (int)Process);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&DestinationString);
      }
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v23);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v24);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v25);
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x46E,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        v19);
    }
  }
  else
  {
    LOBYTE(v23) = 0;
    if ( IsComposableShellEnabled() )
    {
      wil::GetImpersonationTokenForClientOfObject(&v24, a1);
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"shellExperience");
      v8 = RtlCapabilityCheck(v24, &DestinationString, &v23);
      if ( v8 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(retaddr, v9, v10, (const char *)(unsigned int)v8, (int)Process);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v24);
    }
    if ( !(_BYTE)v23 )
    {
      OriginateErrorWithResourceString(-2147483634, &_ImageBase, 0x2D00u);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x454,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)0x8000000ELL,
        (int)Process);
    }
  }
}

```

## disassembly

```asm
0x1800726f8  mov     rax, rsp
0x1800726fb  push    rbx
0x1800726fc  push    rsi
0x1800726fd  push    r12
0x1800726ff  push    r14
0x180072701  push    r15
0x180072703  sub     rsp, 40h
0x180072707  mov     r15, r8
0x18007270a  mov     r14, rdx
0x18007270d  mov     rsi, rcx
0x180072710  xor     r12d, r12d
0x180072713  mov     [r8], r12
0x180072716  mov     r8d, 1010h
0x18007271c  mov     rdx, rcx
0x18007271f  lea     rcx, [rax+18h]
0x180072723  call    ?GetProcessHandleForClientOfObject@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEAUIUnknown@@K@Z; wil::GetProcessHandleForClientOfObject(IUnknown *,ulong)
0x180072728  mov     dword ptr [rsp+68h+arg_8], r12d
0x18007272d  lea     r8, [rsp+68h+arg_8]
0x180072732  mov     edx, 11001Bh
0x180072737  mov     rcx, [rsp+68h+arg_10]
0x18007273f  call    cs:__imp_QuirkIsEnabledForProcess
0x180072745  mov     rcx, [rsp+68h]; this
0x18007274a  test    eax, eax
0x18007274c  jns     short loc_180072762
0x18007274e  mov     r9d, eax; char *
0x180072751  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180072758  mov     edx, 438h; void *
0x18007275d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180072762  cmp     dword ptr [rsp+68h+arg_8], r12d
0x180072767  setnz   bl
0x18007276a  lea     rcx, [rsp+68h+arg_10]
0x180072772  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180072777  mov     [r14], bl
0x18007277a  test    bl, bl
0x18007277c  jnz     loc_180072830
0x180072782  mov     byte ptr [rsp+68h+arg_8], r12b
0x180072787  call    ?IsComposableShellEnabled@@YA_NXZ; IsComposableShellEnabled(void)
0x18007278c  test    al, al
0x18007278e  jz      short loc_1800727F2
0x180072790  mov     rdx, rsi
0x180072793  lea     rcx, [rsp+68h+arg_10]
0x18007279b  call    ?GetImpersonationTokenForClientOfObject@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEAUIUnknown@@K@Z; wil::GetImpersonationTokenForClientOfObject(IUnknown *,ulong)
0x1800727a0  nop
0x1800727a1  xorps   xmm0, xmm0
0x1800727a4  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800727a9  lea     rdx, aShellexperienc; "shellExperience"
0x1800727b0  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800727b5  call    cs:__imp_RtlInitUnicodeString
0x1800727bb  lea     r8, [rsp+68h+arg_8]
0x1800727c0  lea     rdx, [rsp+68h+DestinationString]
0x1800727c5  mov     rcx, [rsp+68h+arg_10]
0x1800727cd  call    cs:__imp_RtlCapabilityCheck
0x1800727d3  mov     rcx, [rsp+68h]; this
0x1800727d8  test    eax, eax
0x1800727da  jns     short loc_1800727E5
0x1800727dc  mov     r9d, eax; char *
0x1800727df  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800727e5  lea     rcx, [rsp+68h+arg_10]
0x1800727ed  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800727f2  cmp     byte ptr [rsp+68h+arg_8], r12b
0x1800727f7  jnz     loc_1800729A2
0x1800727fd  mov     r8d, 2D00h; unsigned int
0x180072803  lea     rdx, __ImageBase; HINSTANCE
0x18007280a  mov     ebx, 8000000Eh
0x18007280f  mov     ecx, ebx; int
0x180072811  call    ?OriginateErrorWithResourceString@@YAXJPEAUHINSTANCE__@@I@Z; OriginateErrorWithResourceString(long,HINSTANCE__ *,uint)
0x180072816  mov     rcx, [rsp+68h]; this
0x18007281b  mov     r9d, ebx; char *
0x18007281e  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180072825  mov     edx, 454h; void *
0x18007282a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072830  mov     r8d, 1000h
0x180072836  mov     rdx, rsi
0x180072839  lea     rcx, [rsp+68h+Process]
0x18007283e  call    ?GetProcessHandleForClientOfObject@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEAUIUnknown@@K@Z; wil::GetProcessHandleForClientOfObject(IUnknown *,ulong)
0x180072843  nop
0x180072844  mov     rcx, [rsp+68h+Process]; Process
0x180072849  call    cs:__imp_GetProcessId
0x18007284f  nop
0x180072850  mov     [rsp+68h+arg_18], r12
0x180072858  lea     r9, [rsp+68h+arg_18]
0x180072860  lea     r8, _GUID_1ada0e3e_e4a2_4123_b451_dc96bf800419
0x180072867  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x18007286e  mov     ecx, eax
0x180072870  call    cs:__imp_CoreQueryApplicationService
0x180072876  mov     rcx, [rsp+68h]; this
0x18007287b  test    eax, eax
0x18007287d  jns     short loc_180072893
0x18007287f  mov     r9d, eax; char *
0x180072882  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180072889  mov     edx, 461h; void *
0x18007288e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072893  mov     [rsp+68h+arg_10], r12
0x18007289b  mov     rcx, [rsp+68h+arg_18]
0x1800728a3  mov     rax, [rcx]
0x1800728a6  mov     [rsp+68h+arg_10], r12
0x1800728ae  lea     rdx, [rsp+68h+arg_10]
0x1800728b6  mov     rax, [rax+40h]
0x1800728ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800728bf  mov     rcx, [rsp+68h]; this
0x1800728c4  test    eax, eax
0x1800728c6  jns     short loc_1800728DC
0x1800728c8  mov     r9d, eax; char *
0x1800728cb  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800728d2  mov     edx, 464h; void *
0x1800728d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800728dc  mov     [rsp+68h+arg_8], r12
0x1800728e1  mov     rcx, [rsp+68h+arg_10]
0x1800728e9  mov     rax, [rcx]
0x1800728ec  mov     [rsp+68h+arg_8], r12
0x1800728f1  lea     rdx, [rsp+68h+arg_8]
0x1800728f6  mov     rax, [rax+30h]
0x1800728fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800728ff  mov     rcx, [rsp+68h]; this
0x180072904  test    eax, eax
0x180072906  jns     short loc_18007291C
0x180072908  mov     r9d, eax; char *
0x18007290b  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180072912  mov     edx, 467h; void *
0x180072917  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007291c  cmp     [rsp+68h+arg_8], r12
0x180072921  jz      short loc_18007296E
0x180072923  lea     rdx, [rsp+68h+DestinationString]
0x180072928  lea     rcx, [rsp+68h+arg_8]
0x18007292d  call    ??$query@UICoreWindowInterop@@@?$com_ptr_t@UICoreWindow@Core@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UICoreWindowInterop@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::UI::Core::ICoreWindow,wil::err_exception_policy>::query<ICoreWindowInterop>(void)
0x180072932  nop
0x180072933  mov     rcx, [rax]
0x180072936  mov     rax, [rcx]
0x180072939  mov     rdx, r15
0x18007293c  mov     rax, [rax+18h]
0x180072940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072945  mov     rcx, [rsp+68h]; this
0x18007294a  test    eax, eax
0x18007294c  jns     short loc_180072963
0x18007294e  mov     r9d, eax; char *
0x180072951  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180072958  mov     edx, 46Bh; void *
0x18007295d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072963  lea     rcx, [rsp+68h+DestinationString]
0x180072968  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18007296d  nop
0x18007296e  lea     rcx, [rsp+68h+arg_8]
0x180072973  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180072978  nop
0x180072979  lea     rcx, [rsp+68h+arg_10]
0x180072981  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180072986  nop
0x180072987  lea     rcx, [rsp+68h+arg_18]
0x18007298f  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180072994  nop
0x180072995  lea     rcx, [rsp+68h+Process]
0x18007299a  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007299f  nop
0x1800729a0  jmp     short $+2
0x1800729a2  add     rsp, 40h
0x1800729a6  pop     r15
0x1800729a8  pop     r14
0x1800729aa  pop     r12
0x1800729ac  pop     rsi
0x1800729ad  pop     rbx
0x1800729ae  retn
```
