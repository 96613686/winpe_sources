# __vcrt_uninitialize_locks

- ea: `0x14002ab18`
- end: `0x14002ab4f`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14002769c`
- `0x1400276cc`
- `0x14002aac8`

## callees

- `0x14002ab18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002ab37`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002ab37`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_140085CA0;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_140085C78[5 * (unsigned int)--v0]);
    --dword_140085CA0;
  }
  return 1;
}

```

## disassembly

```asm
0x14002ab18  push    rbx
0x14002ab1a  sub     rsp, 20h
0x14002ab1e  mov     ebx, cs:dword_140085CA0
0x14002ab24  jmp     short loc_14002AB43
0x14002ab26  lea     rax, qword_140085C78
0x14002ab2d  dec     ebx
0x14002ab2f  lea     rcx, [rbx+rbx*4]
0x14002ab33  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x14002ab37  call    cs:__imp_DeleteCriticalSection
0x14002ab3d  dec     cs:dword_140085CA0
0x14002ab43  test    ebx, ebx
0x14002ab45  jnz     short loc_14002AB26
0x14002ab47  mov     al, 1
0x14002ab49  add     rsp, 20h
0x14002ab4d  pop     rbx
0x14002ab4e  retn
```
