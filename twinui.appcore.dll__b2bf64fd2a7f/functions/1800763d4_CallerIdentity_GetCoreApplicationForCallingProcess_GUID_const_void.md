# CallerIdentity::GetCoreApplicationForCallingProcess(_GUID const &,void * *)

- ea: `0x1800763d4`
- end: `0x180076468`
- name: `?GetCoreApplicationForCallingProcess@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180076218`
- `0x18007655c`

## callees

- `0x18005f54c`
- `0x1800763d4`
- `0x180076a58`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180076413`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180076413`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x180076443`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x180076443`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x180076424`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x180076424`

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
  HANDLE Process; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)&a2->Data1 = 0;
  Process = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle((CallerIdentity *)0x1000, (unsigned int)&Process, a3);
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
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&Process);
  return (unsigned int)CallingProcessHandle;
}

```

## disassembly

```asm
0x1800763d4  mov     rax, rsp
0x1800763d7  mov     [rax+10h], rbx
0x1800763db  mov     [rax+18h], rsi
0x1800763df  mov     [rax+8], rcx
0x1800763e3  push    rdi
0x1800763e4  sub     rsp, 20h
0x1800763e8  mov     rdi, rdx
0x1800763eb  mov     qword ptr [rdx], 0
0x1800763f2  mov     qword ptr [rax+8], 0
0x1800763fa  lea     rdx, [rax+8]; unsigned int
0x1800763fe  mov     ecx, 1000h; this
0x180076403  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x180076408  mov     ebx, eax
0x18007640a  test    eax, eax
0x18007640c  js      short loc_18007644B
0x18007640e  mov     rcx, [rsp+28h+Process]; Process
0x180076413  call    cs:__imp_GetProcessId
0x180076419  mov     esi, eax
0x18007641b  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180076422  mov     ecx, eax
0x180076424  call    cs:__imp_CoreIsApplicationServiceSupported
0x18007642a  mov     ebx, eax
0x18007642c  test    eax, eax
0x18007642e  js      short loc_18007644B
0x180076430  mov     r9, rdi
0x180076433  lea     r8, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x18007643a  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180076441  mov     ecx, esi
0x180076443  call    cs:__imp_CoreQueryApplicationService
0x180076449  mov     ebx, eax
0x18007644b  lea     rcx, [rsp+28h+Process]
0x180076450  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180076455  nop
0x180076456  mov     eax, ebx
0x180076458  mov     rbx, [rsp+28h+arg_8]
0x18007645d  mov     rsi, [rsp+28h+arg_10]
0x180076462  add     rsp, 20h
0x180076466  pop     rdi
0x180076467  retn
```
