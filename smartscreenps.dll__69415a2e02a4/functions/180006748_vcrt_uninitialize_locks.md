# __vcrt_uninitialize_locks

- ea: `0x180006748`
- end: `0x18000677f`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031ac`
- `0x180003210`
- `0x1800066f8`

## callees

- `0x180006748`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006767`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006767`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_18001A3E0;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_18001A3B8[5 * (unsigned int)--v0]);
    --dword_18001A3E0;
  }
  return 1;
}

```

## disassembly

```asm
0x180006748  push    rbx
0x18000674a  sub     rsp, 20h
0x18000674e  mov     ebx, cs:dword_18001A3E0
0x180006754  jmp     short loc_180006773
0x180006756  lea     rax, qword_18001A3B8
0x18000675d  dec     ebx
0x18000675f  lea     rcx, [rbx+rbx*4]
0x180006763  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180006767  call    cs:__imp_DeleteCriticalSection
0x18000676d  dec     cs:dword_18001A3E0
0x180006773  test    ebx, ebx
0x180006775  jnz     short loc_180006756
0x180006777  mov     al, 1
0x180006779  add     rsp, 20h
0x18000677d  pop     rbx
0x18000677e  retn
```
