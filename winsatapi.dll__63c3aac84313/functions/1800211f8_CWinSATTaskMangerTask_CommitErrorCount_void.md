# CWinSATTaskMangerTask::CommitErrorCount(void)

- ea: `0x1800211f8`
- end: `0x18002128c`
- name: `?CommitErrorCount@CWinSATTaskMangerTask@@AEAA_NXZ`
- size: `148`
- prototype: `char __fastcall(CWinSATTaskMangerTask *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180020dcc`

## callees

- `0x18000e6ac`
- `0x1800211f8`
- `0x18002177c`
- `0x180023a94`
- `0x180031010`

## string_xrefs

- `0x180021213`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021253`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021207`: `The task error count is too high, disabling the task`
- `0x18002125e`: `Failed to write the error count to the registry (error count = %u)`
- `0x180021273`: `Incremented TaskErrorCout to %u and sucesfully wrote to the registry`

## pseudocode

```c
char __fastcall CWinSATTaskMangerTask::CommitErrorCount(CWinSATTaskMangerTask *this)
{
  bool v2; // cl
  void (__fastcall *v3)(__int64 *, __int64, __int64); // rax
  bool updated; // al
  int v5; // r9d

  if ( *((_DWORD *)this + 27) >= 3u )
  {
    Log_Text_F(
      "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
      138,
      "The task error count is too high, disabling the task");
    EnableDisableWinSATTask(v2);
    v3 = (void (__fastcall *)(__int64 *, __int64, __int64))*((_QWORD *)this + 17);
    if ( v3 )
      v3(qword_1800487B0, 10270, 1);
  }
  updated = CWinSATTaskMangerTask::UpdateErrorCountRegKey(this, *((_DWORD *)this + 27));
  v5 = *((_DWORD *)this + 27);
  if ( updated )
  {
    Log_Text_F(
      "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
      148,
      "Incremented TaskErrorCout to %u and sucesfully wrote to the registry",
      v5);
    return 1;
  }
  else
  {
    Log_Text_F(
      "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
      144,
      "Failed to write the error count to the registry (error count = %u)",
      v5);
    return 0;
  }
}

```

## disassembly

```asm
0x1800211f8  push    rbx
0x1800211fa  sub     rsp, 20h
0x1800211fe  cmp     dword ptr [rcx+6Ch], 3
0x180021202  mov     rbx, rcx
0x180021205  jb      short loc_180021247
0x180021207  lea     r8, aTheTaskErrorCo; "The task error count is too high, disab"...
0x18002120e  mov     edx, 8Ah
0x180021213  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x18002121a  call    Log_Text_F
0x18002121f  call    ?EnableDisableWinSATTask@@YAJ_N@Z; EnableDisableWinSATTask(bool)
0x180021224  mov     rax, [rbx+88h]
0x18002122b  test    rax, rax
0x18002122e  jz      short loc_180021247
0x180021230  mov     edx, 281Eh
0x180021235  lea     rcx, qword_1800487B0
0x18002123c  mov     r8d, 1
0x180021242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021247  mov     edx, [rbx+6Ch]; unsigned int
0x18002124a  call    ?UpdateErrorCountRegKey@CWinSATTaskMangerTask@@AEAA_NK@Z; CWinSATTaskMangerTask::UpdateErrorCountRegKey(ulong)
0x18002124f  mov     r9d, [rbx+6Ch]
0x180021253  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x18002125a  test    al, al
0x18002125c  jnz     short loc_180021273
0x18002125e  lea     r8, aFailedToWriteT; "Failed to write the error count to the "...
0x180021265  mov     edx, 90h
0x18002126a  call    Log_Text_F
0x18002126f  xor     al, al
0x180021271  jmp     short loc_180021286
0x180021273  lea     r8, aIncrementedTas; "Incremented TaskErrorCout to %u and suc"...
0x18002127a  mov     edx, 94h
0x18002127f  call    Log_Text_F
0x180021284  mov     al, 1
0x180021286  add     rsp, 20h
0x18002128a  pop     rbx
0x18002128b  retn
```
