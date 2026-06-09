# TdiInitialize9FTriageBlock

- ea: `0x14000515c`
- end: `0x1400051b7`
- name: `TdiInitialize9FTriageBlock`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140004880`

## import_xrefs

- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x1400051a5`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x1400051a5`

## pseudocode

```c
__int64 TdiInitialize9FTriageBlock()
{
  TdiGlobalTriageBlock = -271729937;
  dword_140008344 = 1048577;
  qword_140008348 = 0;
  return NetioRegisterTriageDumpDataCallback(
           qword_1400080C0,
           1,
           TdiPopulateTriageDumpData,
           &TdiGlobalTriageBlock,
           "TDI");
}

```

## disassembly

```asm
0x14000515c  sub     rsp, 38h
0x140005160  lea     rax, aTdi; "TDI"
0x140005167  mov     cs:TdiGlobalTriageBlock, 0EFCDBAEFh
0x140005171  mov     edx, 1
0x140005176  mov     [rsp+38h+var_18], rax
0x14000517b  lea     r9, TdiGlobalTriageBlock
0x140005182  mov     cs:dword_140008344, 100001h
0x14000518c  lea     r8, TdiPopulateTriageDumpData
0x140005193  mov     cs:qword_140008348, 0
0x14000519e  lea     rcx, qword_1400080C0
0x1400051a5  call    cs:__imp_NetioRegisterTriageDumpDataCallback
0x1400051ac  nop     dword ptr [rax+rax+00h]
0x1400051b1  add     rsp, 38h
0x1400051b5  retn
```
