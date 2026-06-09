# __vcrt_uninitialize_locks

- ea: `0x1800141ec`
- end: `0x180014223`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: `char()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180011c58`
- `0x180011cbc`
- `0x18001419c`

## callees

- `0x1800141ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001420b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001420b`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_18001FED8;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_18001FEB0[5 * (unsigned int)--v0]);
    --dword_18001FED8;
  }
  return 1;
}

```

## disassembly

```asm
0x1800141ec  push    rbx
0x1800141ee  sub     rsp, 20h
0x1800141f2  mov     ebx, cs:dword_18001FED8
0x1800141f8  jmp     short loc_180014217
0x1800141fa  lea     rax, qword_18001FEB0
0x180014201  dec     ebx
0x180014203  lea     rcx, [rbx+rbx*4]
0x180014207  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18001420b  call    cs:__imp_DeleteCriticalSection
0x180014211  dec     cs:dword_18001FED8
0x180014217  test    ebx, ebx
0x180014219  jnz     short loc_1800141FA
0x18001421b  mov     al, 1
0x18001421d  add     rsp, 20h
0x180014221  pop     rbx
0x180014222  retn
```
