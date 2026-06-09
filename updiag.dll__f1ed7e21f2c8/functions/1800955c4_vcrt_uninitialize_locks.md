# __vcrt_uninitialize_locks

- ea: `0x1800955c4`
- end: `0x1800955fb`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180091d68`
- `0x180091dcc`
- `0x180095574`

## callees

- `0x1800955c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800955e3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800955e3`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_180184E68;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_180184E40[5 * (unsigned int)--v0]);
    --dword_180184E68;
  }
  return 1;
}

```

## disassembly

```asm
0x1800955c4  push    rbx
0x1800955c6  sub     rsp, 20h
0x1800955ca  mov     ebx, cs:dword_180184E68
0x1800955d0  jmp     short loc_1800955EF
0x1800955d2  lea     rax, qword_180184E40
0x1800955d9  dec     ebx
0x1800955db  lea     rcx, [rbx+rbx*4]
0x1800955df  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800955e3  call    cs:__imp_DeleteCriticalSection
0x1800955e9  dec     cs:dword_180184E68
0x1800955ef  test    ebx, ebx
0x1800955f1  jnz     short loc_1800955D2
0x1800955f3  mov     al, 1
0x1800955f5  add     rsp, 20h
0x1800955f9  pop     rbx
0x1800955fa  retn
```
