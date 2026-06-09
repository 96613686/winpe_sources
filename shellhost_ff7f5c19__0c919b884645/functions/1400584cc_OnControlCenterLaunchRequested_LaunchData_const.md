# OnControlCenterLaunchRequested(LaunchData const &)

- ea: `0x1400584cc`
- end: `0x1400585fe`
- name: `?OnControlCenterLaunchRequested@@YAXAEBULaunchData@@@Z`
- size: `306`
- prototype: `void __fastcall(const struct LaunchData *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140058bec`
- `0x14005cc00`

## callees

- `0x14000b6a8`
- `0x14000fc7c`
- `0x14000fce4`
- `0x140046a30`
- `0x140052fbc`
- `0x140058464`
- `0x1400584cc`
- `0x140058604`
- `0x14005bfc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400584f8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400584f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14005859b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14005859b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058503`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x140058565`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x140058565`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140058553`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140058553`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14005858a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14005858a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400585d5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400585d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall OnControlCenterLaunchRequested(const struct LaunchData *a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 v5; // rax
  DWORD CurrentProcessId; // eax
  const unsigned __int16 *v7; // rcx
  _BYTE v8[40]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HANDLE MutexW; // [rsp+60h] [rbp+8h] BYREF
  HANDLE Thread; // [rsp+68h] [rbp+10h] BYREF

  if ( *((_QWORD *)a1 + 6) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xD3,
      (unsigned int)"pcshell\\shell\\shellhost\\exe\\main.cpp",
      a4);
  MutexW = CreateMutexW(0, 1, L"ShellHostMutex");
  if ( GetLastError() == 183 )
  {
    if ( dword_1400842B8 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
    {
      Init_thread_header(&dword_1400842B8);
      if ( dword_1400842B8 == -1 )
      {
        IsDebuggerPresent();
        Init_thread_footer(&dword_1400842B8);
      }
    }
    if ( *((_QWORD *)a1 + 2) )
    {
      v5 = std::wstring::wstring(v8, a1);
      OnControlCenterUrlLaunchRequested(v5);
      ShellHostTelemetry::UrlLaunchCompleted();
    }
  }
  else
  {
    CurrentProcessId = GetCurrentProcessId();
    NotifyHostReadyWithProcessId(v7, CurrentProcessId);
    SetProcessShutdownParameters(2u, 0);
    Thread = CreateThread(0, 0, lambda_601d7cc16240833b3b0c73e5bb107e17_::_lambda_invoker_cdecl_, 0, 0, 0);
    WaitForSingleObject(Thread, 0xFFFFFFFF);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Thread);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&MutexW);
}

```

## disassembly

```asm
0x1400584cc  push    rbx
0x1400584ce  sub     rsp, 50h
0x1400584d2  mov     rbx, rcx
0x1400584d5  cmp     qword ptr [rcx+30h], 0
0x1400584da  setnz   al
0x1400584dd  mov     rcx, [rsp+58h]; this
0x1400584e2  test    al, al
0x1400584e4  jnz     loc_1400585EC
0x1400584ea  lea     r8, Name; "ShellHostMutex"
0x1400584f1  mov     edx, 1; bInitialOwner
0x1400584f6  xor     ecx, ecx; lpMutexAttributes
0x1400584f8  call    cs:__imp_CreateMutexW
0x1400584fe  mov     [rsp+58h+arg_0], rax
0x140058503  call    cs:__imp_GetLastError
0x140058509  cmp     eax, 0B7h
0x14005850e  jnz     short loc_140058553
0x140058510  mov     ecx, 4
0x140058515  mov     rax, gs:58h
0x14005851e  mov     rax, [rax]
0x140058521  mov     eax, [rcx+rax]
0x140058524  cmp     cs:dword_1400842B8, eax
0x14005852a  jg      loc_1400585BC
0x140058530  cmp     qword ptr [rbx+10h], 0
0x140058535  jz      short loc_1400585AC
0x140058537  mov     rdx, rbx
0x14005853a  lea     rcx, [rsp+58h+var_28]
0x14005853f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140058544  mov     rcx, rax
0x140058547  call    ?OnControlCenterUrlLaunchRequested@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; OnControlCenterUrlLaunchRequested(std::wstring)
0x14005854c  call    ?UrlLaunchCompleted@ShellHostTelemetry@@SAXXZ; ShellHostTelemetry::UrlLaunchCompleted(void)
0x140058551  jmp     short loc_1400585AC
0x140058553  call    cs:__imp_GetCurrentProcessId
0x140058559  mov     edx, eax; unsigned int
0x14005855b  call    ?NotifyHostReadyWithProcessId@@YA_NPEBGK@Z; NotifyHostReadyWithProcessId(ushort const *,ulong)
0x140058560  xor     edx, edx; dwFlags
0x140058562  lea     ecx, [rdx+2]; dwLevel
0x140058565  call    cs:__imp_SetProcessShutdownParameters
0x14005856b  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x140058574  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x14005857c  xor     r9d, r9d; lpParameter
0x14005857f  lea     r8, _lambda_601d7cc16240833b3b0c73e5bb107e17____lambda_invoker_cdecl_; lpStartAddress
0x140058586  xor     edx, edx; dwStackSize
0x140058588  xor     ecx, ecx; lpThreadAttributes
0x14005858a  call    cs:__imp_CreateThread
0x140058590  mov     [rsp+58h+arg_8], rax
0x140058595  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140058598  mov     rcx, rax; hHandle
0x14005859b  call    cs:__imp_WaitForSingleObject
0x1400585a1  lea     rcx, [rsp+58h+arg_8]
0x1400585a6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400585ab  nop
0x1400585ac  lea     rcx, [rsp+58h+arg_0]
0x1400585b1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400585b6  add     rsp, 50h
0x1400585ba  pop     rbx
0x1400585bb  retn
0x1400585bc  lea     rcx, dword_1400842B8
0x1400585c3  call    _Init_thread_header
0x1400585c8  cmp     cs:dword_1400842B8, 0FFFFFFFFh
0x1400585cf  jnz     loc_140058530
0x1400585d5  call    cs:__imp_IsDebuggerPresent
0x1400585db  lea     rcx, dword_1400842B8
0x1400585e2  call    _Init_thread_footer
0x1400585e7  jmp     loc_140058530
0x1400585ec  lea     r8, aPcshellShellSh; "pcshell\\shell\\shellhost\\exe\\main.cp"...
0x1400585f3  mov     edx, 0D3h; void *
0x1400585f8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
