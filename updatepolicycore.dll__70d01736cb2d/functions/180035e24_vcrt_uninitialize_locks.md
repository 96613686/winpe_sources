# __vcrt_uninitialize_locks

- ea: `0x180035e24`
- end: `0x180035e5b`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18003251c`
- `0x180032580`
- `0x180035dd4`

## callees

- `0x180035e24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035e43`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035e43`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_18004EA78;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_18004EA50[5 * (unsigned int)--v0]);
    --dword_18004EA78;
  }
  return 1;
}

```

## disassembly

```asm
0x180035e24  push    rbx
0x180035e26  sub     rsp, 20h
0x180035e2a  mov     ebx, cs:dword_18004EA78
0x180035e30  jmp     short loc_180035E4F
0x180035e32  lea     rax, qword_18004EA50
0x180035e39  dec     ebx
0x180035e3b  lea     rcx, [rbx+rbx*4]
0x180035e3f  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180035e43  call    cs:__imp_DeleteCriticalSection
0x180035e49  dec     cs:dword_18004EA78
0x180035e4f  test    ebx, ebx
0x180035e51  jnz     short loc_180035E32
0x180035e53  mov     al, 1
0x180035e55  add     rsp, 20h
0x180035e59  pop     rbx
0x180035e5a  retn
```
