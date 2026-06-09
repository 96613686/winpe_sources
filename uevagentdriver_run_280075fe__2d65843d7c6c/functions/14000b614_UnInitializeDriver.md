# UnInitializeDriver

- ea: `0x14000b614`
- end: `0x14000b72e`
- name: `UnInitializeDriver`
- size: `282`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b5c0`
- `0x14000c614`

## callees

- `0x140001118`
- `0x1400011b0`
- `0x140001298`
- `0x14000a008`
- `0x14000b34c`
- `0x14000b614`

## import_xrefs

- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x14000b661`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x14000b661`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000b6e1`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000b6e1`
- `FLTMGR!FltUnregisterFilter` at `0x14000b6ad`
- `FLTMGR!FltUnregisterFilter` at `0x14000b6ad`

## string_xrefs

- `0x14000b6c9`: `UevFilter.ComPortUnInit: Entry\n`
- `0x14000b6f3`: `UevFilter.ComPortUnInit: Failed resourse deletion, status = 0x%X\n`
- `0x14000b6ff`: `UevFilter.ComPortUnInit: Exit\n`

## pseudocode

```c
__int64 UnInitializeDriver()
{
  NTSTATUS ProcessNotifyRoutine; // eax

  DbgTrace(1, "UevFilter.UnInitializeDriver: Entry\n");
  if ( processEventPortCreated )
  {
    ProcessEventUninitialize();
    processEventPortCreated = 0;
  }
  if ( processNotifyHooked )
  {
    DbgTrace(2, "UevFilter.HookProcessNotify: Entry\n");
    ProcessNotifyRoutine = PsSetCreateProcessNotifyRoutineEx(ProcessNotification, 1u);
    DbgTraceFrmt(2, "UevFilter.HookProcessNotify: Exit, retStatus = 0x%X\n", ProcessNotifyRoutine);
    processNotifyHooked = 0;
  }
  if ( portCreated )
  {
    ComPortClose();
    portCreated = 0;
  }
  if ( filterRegistered )
  {
    FltUnregisterFilter(g_pFilter);
    filterRegistered = 0;
  }
  if ( comPortInitialized )
  {
    DbgTrace(2, "UevFilter.ComPortUnInit: Entry\n");
    if ( ExDeleteResourceLite(&comPortResource) < 0 )
      DbgTraceFrmtErr("UevFilter.ComPortUnInit: Failed resourse deletion, status = 0x%X\n");
    DbgTrace(2, "UevFilter.ComPortUnInit: Exit\n");
    comPortInitialized = 0;
  }
  return DbgTrace(1, "UevFilter.UnInitializeDriver: Exit\n");
}

```

## disassembly

```asm
0x14000b614  sub     rsp, 28h
0x14000b618  lea     rdx, aUevfilterUnini; "UevFilter.UnInitializeDriver: Entry\n"
0x14000b61f  mov     ecx, 1
0x14000b624  call    DbgTrace
0x14000b629  cmp     cs:processEventPortCreated, 0
0x14000b630  jz      short loc_14000B63E
0x14000b632  call    ProcessEventUninitialize
0x14000b637  mov     cs:processEventPortCreated, 0
0x14000b63e  cmp     cs:processNotifyHooked, 0
0x14000b645  jz      short loc_14000B688
0x14000b647  lea     rdx, aUevfilterHookp; "UevFilter.HookProcessNotify: Entry\n"
0x14000b64e  mov     ecx, 2
0x14000b653  call    DbgTrace
0x14000b658  mov     dl, 1; Remove
0x14000b65a  lea     rcx, ProcessNotification; NotifyRoutine
0x14000b661  call    cs:__imp_PsSetCreateProcessNotifyRoutineEx
0x14000b668  nop     dword ptr [rax+rax+00h]
0x14000b66d  lea     rdx, aUevfilterHookp_0; "UevFilter.HookProcessNotify: Exit, retS"...
0x14000b674  mov     ecx, 2
0x14000b679  mov     r8d, eax
0x14000b67c  call    DbgTraceFrmt
0x14000b681  mov     cs:processNotifyHooked, 0
0x14000b688  cmp     cs:portCreated, 0
0x14000b68f  jz      short loc_14000B69D
0x14000b691  call    ComPortClose
0x14000b696  mov     cs:portCreated, 0
0x14000b69d  cmp     cs:filterRegistered, 0
0x14000b6a4  jz      short loc_14000B6C0
0x14000b6a6  mov     rcx, cs:g_pFilter; Filter
0x14000b6ad  call    cs:__imp_FltUnregisterFilter
0x14000b6b4  nop     dword ptr [rax+rax+00h]
0x14000b6b9  mov     cs:filterRegistered, 0
0x14000b6c0  cmp     cs:comPortInitialized, 0
0x14000b6c7  jz      short loc_14000B717
0x14000b6c9  lea     rdx, aUevfilterCompo_0; "UevFilter.ComPortUnInit: Entry\n"
0x14000b6d0  mov     ecx, 2
0x14000b6d5  call    DbgTrace
0x14000b6da  lea     rcx, comPortResource; Resource
0x14000b6e1  call    cs:__imp_ExDeleteResourceLite
0x14000b6e8  nop     dword ptr [rax+rax+00h]
0x14000b6ed  test    eax, eax
0x14000b6ef  jns     short loc_14000B6FF
0x14000b6f1  mov     edx, eax
0x14000b6f3  lea     rcx, aUevfilterCompo_4; "UevFilter.ComPortUnInit: Failed resours"...
0x14000b6fa  call    DbgTraceFrmtErr
0x14000b6ff  lea     rdx, aUevfilterCompo_15; "UevFilter.ComPortUnInit: Exit\n"
0x14000b706  mov     ecx, 2
0x14000b70b  call    DbgTrace
0x14000b710  mov     cs:comPortInitialized, 0
0x14000b717  lea     rdx, aUevfilterUnini_0; "UevFilter.UnInitializeDriver: Exit\n"
0x14000b71e  mov     ecx, 1
0x14000b723  call    DbgTrace
0x14000b728  add     rsp, 28h
0x14000b72c  retn
```
