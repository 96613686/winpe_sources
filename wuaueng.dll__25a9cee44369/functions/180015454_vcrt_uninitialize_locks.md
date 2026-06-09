# __vcrt_uninitialize_locks

- ea: `0x180015454`
- end: `0x18001548b`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: `char()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180011ba8`
- `0x180011c0c`
- `0x180015404`

## callees

- `0x180015454`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015473`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015473`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_180021E78;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_180021E50[5 * (unsigned int)--v0]);
    --dword_180021E78;
  }
  return 1;
}

```

## disassembly

```asm
0x180015454  push    rbx
0x180015456  sub     rsp, 20h
0x18001545a  mov     ebx, cs:dword_180021E78
0x180015460  jmp     short loc_18001547F
0x180015462  lea     rax, qword_180021E50
0x180015469  dec     ebx
0x18001546b  lea     rcx, [rbx+rbx*4]
0x18001546f  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180015473  call    cs:__imp_DeleteCriticalSection
0x180015479  dec     cs:dword_180021E78
0x18001547f  test    ebx, ebx
0x180015481  jnz     short loc_180015462
0x180015483  mov     al, 1
0x180015485  add     rsp, 20h
0x180015489  pop     rbx
0x18001548a  retn
```
