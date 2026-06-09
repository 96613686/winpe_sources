# __vcrt_uninitialize_locks

- ea: `0x1400200b4`
- end: `0x1400200eb`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c8a8`
- `0x14001c8d8`
- `0x140020064`

## callees

- `0x1400200b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400200d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400200d3`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_14002EE68;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_14002EE40[5 * (unsigned int)--v0]);
    --dword_14002EE68;
  }
  return 1;
}

```

## disassembly

```asm
0x1400200b4  push    rbx
0x1400200b6  sub     rsp, 20h
0x1400200ba  mov     ebx, cs:dword_14002EE68
0x1400200c0  jmp     short loc_1400200DF
0x1400200c2  lea     rax, qword_14002EE40
0x1400200c9  dec     ebx
0x1400200cb  lea     rcx, [rbx+rbx*4]
0x1400200cf  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1400200d3  call    cs:__imp_DeleteCriticalSection
0x1400200d9  dec     cs:dword_14002EE68
0x1400200df  test    ebx, ebx
0x1400200e1  jnz     short loc_1400200C2
0x1400200e3  mov     al, 1
0x1400200e5  add     rsp, 20h
0x1400200e9  pop     rbx
0x1400200ea  retn
```
