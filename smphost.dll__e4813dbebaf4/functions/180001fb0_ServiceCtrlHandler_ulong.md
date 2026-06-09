# ServiceCtrlHandler(ulong)

- ea: `0x180001fb0`
- end: `0x180001fe5`
- name: `?ServiceCtrlHandler@@YAXK@Z`
- size: `53`
- prototype: `void __fastcall(DWORD dwControl, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800025e0`

## callees

- `0x180001f3c`
- `0x180001fb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001fcc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001fcc`

## pseudocode

```c
void __fastcall ServiceCtrlHandler(DWORD dwControl, unsigned int a2)
{
  unsigned int v2; // edx

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
0x180001fb0  sub     rsp, 28h
0x180001fb4  cmp     ecx, 1
0x180001fb7  jnz     short loc_180001FE0
0x180001fb9  xor     r8d, r8d; unsigned int
0x180001fbc  lea     ecx, [r8+3]; unsigned int
0x180001fc0  call    ?ReportServiceStatus@@YAXKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x180001fc5  mov     rcx, cs:?g_ServiceStopEvent@@3PEAXEA; hEvent
0x180001fcc  call    cs:__imp_SetEvent
0x180001fd2  mov     ecx, cs:dword_1800067D4; unsigned int
0x180001fd8  xor     r8d, r8d; unsigned int
0x180001fdb  call    ?ReportServiceStatus@@YAXKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x180001fe0  add     rsp, 28h
0x180001fe4  retn
```
