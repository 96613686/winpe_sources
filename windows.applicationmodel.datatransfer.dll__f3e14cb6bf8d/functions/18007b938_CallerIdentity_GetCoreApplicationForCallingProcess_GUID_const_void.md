# CallerIdentity::GetCoreApplicationForCallingProcess(_GUID const &,void * *)

- ea: `0x18007b938`
- end: `0x18007b9db`
- name: `?GetCoreApplicationForCallingProcess@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `163`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18007b9e4`

## callees

- `0x18007b938`
- `0x18007bb34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007b972`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007b972`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b9c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b9c2`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x18007b9a2`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x18007b9a2`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x18007b983`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x18007b983`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CallerIdentity::GetCoreApplicationForCallingProcess(
        CallerIdentity *this,
        const struct _GUID *a2,
        void **a3)
{
  int CallingProcessHandle; // ebx
  __int64 ProcessId; // rsi
  char *v6; // rcx
  HANDLE Process; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)&a2->Data1 = 0;
  Process = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(this, a2, &Process);
  if ( CallingProcessHandle >= 0 )
  {
    ProcessId = GetProcessId(Process);
    CallingProcessHandle = CoreIsApplicationServiceSupported(ProcessId, &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1);
    if ( CallingProcessHandle >= 0 )
      CallingProcessHandle = CoreQueryApplicationService(
                               (unsigned int)ProcessId,
                               &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1,
                               &GUID_17b0e613_942a_422d_904c_f90dc71a7dae,
                               a2);
  }
  v6 = (char *)Process;
  Process = 0;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return (unsigned int)CallingProcessHandle;
}

```

## disassembly

```asm
0x18007b938  mov     rax, rsp
0x18007b93b  mov     [rax+10h], rbx
0x18007b93f  mov     [rax+18h], rsi
0x18007b943  mov     [rax+8], rcx
0x18007b947  push    rdi
0x18007b948  sub     rsp, 20h
0x18007b94c  mov     rdi, rdx
0x18007b94f  mov     qword ptr [rdx], 0
0x18007b956  mov     qword ptr [rax+8], 0
0x18007b95e  lea     r8, [rax+8]
0x18007b962  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x18007b967  mov     ebx, eax
0x18007b969  test    eax, eax
0x18007b96b  js      short loc_18007B9AA
0x18007b96d  mov     rcx, [rsp+28h+Process]; Process
0x18007b972  call    cs:__imp_GetProcessId
0x18007b978  mov     esi, eax
0x18007b97a  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x18007b981  mov     ecx, eax
0x18007b983  call    cs:__imp_CoreIsApplicationServiceSupported
0x18007b989  mov     ebx, eax
0x18007b98b  test    eax, eax
0x18007b98d  js      short loc_18007B9AA
0x18007b98f  mov     r9, rdi
0x18007b992  lea     r8, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x18007b999  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x18007b9a0  mov     ecx, esi
0x18007b9a2  call    cs:__imp_CoreQueryApplicationService
0x18007b9a8  mov     ebx, eax
0x18007b9aa  mov     rcx, [rsp+28h+Process]; hObject
0x18007b9af  mov     [rsp+28h+Process], 0
0x18007b9b8  lea     rax, [rcx-1]
0x18007b9bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007b9c0  ja      short loc_18007B9C9
0x18007b9c2  call    cs:__imp_CloseHandle
0x18007b9c8  nop
0x18007b9c9  mov     eax, ebx
0x18007b9cb  mov     rbx, [rsp+28h+arg_8]
0x18007b9d0  mov     rsi, [rsp+28h+arg_10]
0x18007b9d5  add     rsp, 20h
0x18007b9d9  pop     rdi
0x18007b9da  retn
```
