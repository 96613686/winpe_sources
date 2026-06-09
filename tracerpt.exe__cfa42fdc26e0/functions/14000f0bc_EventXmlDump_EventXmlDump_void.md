# EventXmlDump::~EventXmlDump(void)

- ea: `0x14000f0bc`
- end: `0x14000f0fd`
- name: `??1EventXmlDump@@QEAA@XZ`
- size: `65`
- prototype: `void __fastcall(EventXmlDump *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x14000d598`

## callees

- `0x14000f0bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f0f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f0f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f0e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f0e3`

## pseudocode

```c
void __fastcall EventXmlDump::~EventXmlDump(EventXmlDump *this)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = (void *)*((_QWORD *)this + 123);
  *(_QWORD *)this = &EventXmlDump::`vftable'{for `IEventDumpHeaderHandler'};
  *((_QWORD *)this + 1) = &EventXmlDump::`vftable'{for `IEventDumpPropertyHandler'};
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
}

```

## disassembly

```asm
0x14000f0bc  push    rbx
0x14000f0be  sub     rsp, 20h
0x14000f0c2  mov     rbx, [rcx+3D8h]
0x14000f0c9  lea     rax, ??_7EventXmlDump@@6BIEventDumpHeaderHandler@@@; const EventXmlDump::`vftable'{for `IEventDumpHeaderHandler'}
0x14000f0d0  mov     [rcx], rax
0x14000f0d3  lea     rax, ??_7EventXmlDump@@6BIEventDumpPropertyHandler@@@; const EventXmlDump::`vftable'{for `IEventDumpPropertyHandler'}
0x14000f0da  mov     [rcx+8], rax
0x14000f0de  test    rbx, rbx
0x14000f0e1  jz      short loc_14000F0F7
0x14000f0e3  call    cs:__imp_GetProcessHeap
0x14000f0e9  mov     r8, rbx; lpMem
0x14000f0ec  xor     edx, edx; dwFlags
0x14000f0ee  mov     rcx, rax; hHeap
0x14000f0f1  call    cs:__imp_HeapFree
0x14000f0f7  add     rsp, 20h
0x14000f0fb  pop     rbx
0x14000f0fc  retn
```
