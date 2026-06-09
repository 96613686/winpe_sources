# __vcrt_uninitialize_locks

- ea: `0x14002bcd8`
- end: `0x14002bd0f`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14002885c`
- `0x14002888c`
- `0x14002bc88`

## callees

- `0x14002bcd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002bcf7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002bcf7`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_140087CA0;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_140087C78[5 * (unsigned int)--v0]);
    --dword_140087CA0;
  }
  return 1;
}

```

## disassembly

```asm
0x14002bcd8  push    rbx
0x14002bcda  sub     rsp, 20h
0x14002bcde  mov     ebx, cs:dword_140087CA0
0x14002bce4  jmp     short loc_14002BD03
0x14002bce6  lea     rax, qword_140087C78
0x14002bced  dec     ebx
0x14002bcef  lea     rcx, [rbx+rbx*4]
0x14002bcf3  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x14002bcf7  call    cs:__imp_DeleteCriticalSection
0x14002bcfd  dec     cs:dword_140087CA0
0x14002bd03  test    ebx, ebx
0x14002bd05  jnz     short loc_14002BCE6
0x14002bd07  mov     al, 1
0x14002bd09  add     rsp, 20h
0x14002bd0d  pop     rbx
0x14002bd0e  retn
```
