# __vcrt_uninitialize_locks

- ea: `0x1800154a4`
- end: `0x1800154db`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180011bf8`
- `0x180011c5c`
- `0x180015454`

## callees

- `0x1800154a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800154c3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800154c3`

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
0x1800154a4  push    rbx
0x1800154a6  sub     rsp, 20h
0x1800154aa  mov     ebx, cs:dword_180021E78
0x1800154b0  jmp     short loc_1800154CF
0x1800154b2  lea     rax, qword_180021E50
0x1800154b9  dec     ebx
0x1800154bb  lea     rcx, [rbx+rbx*4]
0x1800154bf  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800154c3  call    cs:__imp_DeleteCriticalSection
0x1800154c9  dec     cs:dword_180021E78
0x1800154cf  test    ebx, ebx
0x1800154d1  jnz     short loc_1800154B2
0x1800154d3  mov     al, 1
0x1800154d5  add     rsp, 20h
0x1800154d9  pop     rbx
0x1800154da  retn
```
