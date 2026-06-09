# __vcrt_uninitialize_locks

- ea: `0x140005308`
- end: `0x14000533f`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002f68`
- `0x140002f98`
- `0x1400052b8`

## callees

- `0x140005308`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005327`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005327`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_14000A7C8;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_14000A7A0[5 * (unsigned int)--v0]);
    --dword_14000A7C8;
  }
  return 1;
}

```

## disassembly

```asm
0x140005308  push    rbx
0x14000530a  sub     rsp, 20h
0x14000530e  mov     ebx, cs:dword_14000A7C8
0x140005314  jmp     short loc_140005333
0x140005316  lea     rax, qword_14000A7A0
0x14000531d  dec     ebx
0x14000531f  lea     rcx, [rbx+rbx*4]
0x140005323  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x140005327  call    cs:__imp_DeleteCriticalSection
0x14000532d  dec     cs:dword_14000A7C8
0x140005333  test    ebx, ebx
0x140005335  jnz     short loc_140005316
0x140005337  mov     al, 1
0x140005339  add     rsp, 20h
0x14000533d  pop     rbx
0x14000533e  retn
```
