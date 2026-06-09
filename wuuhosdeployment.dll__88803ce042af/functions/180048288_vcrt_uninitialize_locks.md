# __vcrt_uninitialize_locks

- ea: `0x180048288`
- end: `0x1800482bf`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180044b78`
- `0x180044bdc`
- `0x180048238`

## callees

- `0x180048288`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800482a7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800482a7`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_1800761D8;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1800761B0[5 * (unsigned int)--v0]);
    --dword_1800761D8;
  }
  return 1;
}

```

## disassembly

```asm
0x180048288  push    rbx
0x18004828a  sub     rsp, 20h
0x18004828e  mov     ebx, cs:dword_1800761D8
0x180048294  jmp     short loc_1800482B3
0x180048296  lea     rax, qword_1800761B0
0x18004829d  dec     ebx
0x18004829f  lea     rcx, [rbx+rbx*4]
0x1800482a3  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800482a7  call    cs:__imp_DeleteCriticalSection
0x1800482ad  dec     cs:dword_1800761D8
0x1800482b3  test    ebx, ebx
0x1800482b5  jnz     short loc_180048296
0x1800482b7  mov     al, 1
0x1800482b9  add     rsp, 20h
0x1800482bd  pop     rbx
0x1800482be  retn
```
