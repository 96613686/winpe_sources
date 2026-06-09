# CallerIdentity::GetCoreApplicationForCallingProcess(_GUID const &,void * *)

- ea: `0x1804697c8`
- end: `0x18046986a`
- name: `?GetCoreApplicationForCallingProcess@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `162`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x180469870`

## callees

- `0x1804697c8`
- `0x180469afc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180469802`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180469802`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180469852`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180469852`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x180469832`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x180469832`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x180469813`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x180469813`

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
0x1804697c8  mov     rax, rsp
0x1804697cb  mov     [rax+10h], rbx
0x1804697cf  mov     [rax+18h], rsi
0x1804697d3  mov     [rax+8], rcx
0x1804697d7  push    rdi
0x1804697d8  sub     rsp, 20h
0x1804697dc  mov     rdi, rdx
0x1804697df  mov     qword ptr [rdx], 0
0x1804697e6  lea     rdx, [rax+8]; unsigned int
0x1804697ea  mov     qword ptr [rax+8], 0
0x1804697f2  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x1804697f7  mov     ebx, eax
0x1804697f9  test    eax, eax
0x1804697fb  js      short loc_18046983A
0x1804697fd  mov     rcx, [rsp+28h+Process]; Process
0x180469802  call    cs:__imp_GetProcessId
0x180469808  mov     ecx, eax
0x18046980a  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180469811  mov     esi, eax
0x180469813  call    cs:__imp_CoreIsApplicationServiceSupported
0x180469819  mov     ebx, eax
0x18046981b  test    eax, eax
0x18046981d  js      short loc_18046983A
0x18046981f  mov     r9, rdi
0x180469822  lea     r8, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x180469829  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180469830  mov     ecx, esi
0x180469832  call    cs:__imp_CoreQueryApplicationService
0x180469838  mov     ebx, eax
0x18046983a  mov     rcx, [rsp+28h+Process]; hObject
0x18046983f  mov     [rsp+28h+Process], 0
0x180469848  lea     rax, [rcx-1]
0x18046984c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180469850  ja      short loc_180469858
0x180469852  call    cs:__imp_CloseHandle
0x180469858  mov     rsi, [rsp+28h+arg_10]
0x18046985d  mov     eax, ebx
0x18046985f  mov     rbx, [rsp+28h+arg_8]
0x180469864  add     rsp, 20h
0x180469868  pop     rdi
0x180469869  retn
```
