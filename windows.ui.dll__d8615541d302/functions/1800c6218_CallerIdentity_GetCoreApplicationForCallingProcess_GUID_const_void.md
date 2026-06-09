# CallerIdentity::GetCoreApplicationForCallingProcess(_GUID const &,void * *)

- ea: `0x1800c6218`
- end: `0x1800c62ba`
- name: `?GetCoreApplicationForCallingProcess@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `162`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800bdbd0`

## callees

- `0x1800c6218`
- `0x1800c63ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800c6252`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800c6252`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c62a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c62a2`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x1800c6282`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x1800c6282`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x1800c6263`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x1800c6263`

## pseudocode

```c
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
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(this, (unsigned int)&Process, a3);
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
0x1800c6218  mov     rax, rsp
0x1800c621b  mov     [rax+10h], rbx
0x1800c621f  mov     [rax+18h], rsi
0x1800c6223  mov     [rax+8], rcx
0x1800c6227  push    rdi
0x1800c6228  sub     rsp, 20h
0x1800c622c  mov     rdi, rdx
0x1800c622f  mov     qword ptr [rdx], 0
0x1800c6236  lea     rdx, [rax+8]; unsigned int
0x1800c623a  mov     qword ptr [rax+8], 0
0x1800c6242  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x1800c6247  mov     ebx, eax
0x1800c6249  test    eax, eax
0x1800c624b  js      short loc_1800C628A
0x1800c624d  mov     rcx, [rsp+28h+Process]; Process
0x1800c6252  call    cs:__imp_GetProcessId
0x1800c6258  mov     ecx, eax
0x1800c625a  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x1800c6261  mov     esi, eax
0x1800c6263  call    cs:__imp_CoreIsApplicationServiceSupported
0x1800c6269  mov     ebx, eax
0x1800c626b  test    eax, eax
0x1800c626d  js      short loc_1800C628A
0x1800c626f  mov     r9, rdi
0x1800c6272  lea     r8, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x1800c6279  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x1800c6280  mov     ecx, esi
0x1800c6282  call    cs:__imp_CoreQueryApplicationService
0x1800c6288  mov     ebx, eax
0x1800c628a  mov     rcx, [rsp+28h+Process]; hObject
0x1800c628f  mov     [rsp+28h+Process], 0
0x1800c6298  lea     rax, [rcx-1]
0x1800c629c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800c62a0  ja      short loc_1800C62A8
0x1800c62a2  call    cs:__imp_CloseHandle
0x1800c62a8  mov     rsi, [rsp+28h+arg_10]
0x1800c62ad  mov     eax, ebx
0x1800c62af  mov     rbx, [rsp+28h+arg_8]
0x1800c62b4  add     rsp, 20h
0x1800c62b8  pop     rdi
0x1800c62b9  retn
```
