# ServiceCtrlHandler(ulong)

- ea: `0x180002000`
- end: `0x18000203c`
- name: `?ServiceCtrlHandler@@YAXK@Z`
- size: `60`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002680`

## callees

- `0x180001f80`
- `0x180002000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000201c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000201c`

## pseudocode

```c
void __fastcall ServiceCtrlHandler(DWORD dwControl, __int64 a2)
{
  __int64 v2; // rdx

  if ( dwControl == 1 )
  {
    ReportServiceStatus(3u, a2, 0);
    SetEvent(g_ServiceStopEvent);
    ReportServiceStatus(dword_1800067D4, v2, 0);
  }
}

```

## disassembly

```asm
0x180002000  sub     rsp, 28h
0x180002004  cmp     ecx, 1
0x180002007  jnz     short loc_180002036
0x180002009  xor     r8d, r8d; unsigned int
0x18000200c  lea     ecx, [r8+3]; unsigned int
0x180002010  call    ?ReportServiceStatus@@YAXKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x180002015  mov     rcx, cs:?g_ServiceStopEvent@@3PEAXEA; hEvent
0x18000201c  call    cs:__imp_SetEvent
0x180002023  nop     dword ptr [rax+rax+00h]
0x180002028  mov     ecx, cs:dword_1800067D4; unsigned int
0x18000202e  xor     r8d, r8d; unsigned int
0x180002031  call    ?ReportServiceStatus@@YAXKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x180002036  add     rsp, 28h
0x18000203a  retn
```
