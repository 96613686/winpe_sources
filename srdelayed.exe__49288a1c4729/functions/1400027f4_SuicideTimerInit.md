# SuicideTimerInit

- ea: `0x1400027f4`
- end: `0x14000289c`
- name: `SuicideTimerInit`
- size: `168`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400028a4`

## callees

- `0x1400027f4`

## import_xrefs

- `ntdll!NtCreateThreadEx` at `0x140002891`
- `ntdll!NtCreateThreadEx` at `0x140002891`
- `ntdll!NtCreateEvent` at `0x14000280f`
- `ntdll!NtCreateEvent` at `0x140002833`
- `ntdll!NtCreateEvent` at `0x14000280f`
- `ntdll!NtCreateEvent` at `0x140002833`

## pseudocode

```c
NTSTATUS SuicideTimerInit()
{
  NTSTATUS result; // eax

  result = NtCreateEvent(&g_hExitEvent, 0x1F0003u, 0, NotificationEvent, 0);
  if ( result >= 0 )
  {
    result = NtCreateEvent(&g_hProgressEvent, 0x1F0003u, 0, SynchronizationEvent, 0);
    if ( result >= 0 )
      return NtCreateThreadEx(&g_hThread, 0x1FFFFF, 0, -1, SuicideThread, 0, 0, 0, 0, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1400027f4  sub     rsp, 68h
0x1400027f8  xor     r9d, r9d; EventType
0x1400027fb  mov     [rsp+68h+InitialState], 0; InitialState
0x140002800  xor     r8d, r8d; ObjectAttributes
0x140002803  lea     rcx, g_hExitEvent; EventHandle
0x14000280a  mov     edx, 1F0003h; DesiredAccess
0x14000280f  call    cs:__imp_NtCreateEvent
0x140002815  test    eax, eax
0x140002817  js      short loc_140002897
0x140002819  mov     r9d, 1; EventType
0x14000281f  mov     [rsp+68h+InitialState], 0; InitialState
0x140002824  xor     r8d, r8d; ObjectAttributes
0x140002827  lea     rcx, g_hProgressEvent; EventHandle
0x14000282e  mov     edx, 1F0003h; DesiredAccess
0x140002833  call    cs:__imp_NtCreateEvent
0x140002839  test    eax, eax
0x14000283b  js      short loc_140002897
0x14000283d  mov     [rsp+68h+var_18], 0
0x140002846  lea     rax, SuicideThread
0x14000284d  mov     [rsp+68h+var_20], 0
0x140002856  lea     rcx, g_hThread
0x14000285d  mov     [rsp+68h+var_28], 0
0x140002866  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000286a  mov     [rsp+68h+var_30], 0
0x140002873  xor     r8d, r8d
0x140002876  mov     [rsp+68h+var_38], 0
0x14000287e  mov     edx, 1FFFFFh
0x140002883  mov     [rsp+68h+var_40], 0
0x14000288c  mov     qword ptr [rsp+68h+InitialState], rax
0x140002891  call    cs:__imp_NtCreateThreadEx
0x140002897  add     rsp, 68h
0x14000289b  retn
```
