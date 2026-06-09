# __vcrt_uninitialize_locks

- ea: `0x180046bcc`
- end: `0x180046c03`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180044584`
- `0x1800445e8`
- `0x180046b7c`

## callees

- `0x180046bcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046beb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046beb`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_180063318;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1800632F0[5 * (unsigned int)--v0]);
    --dword_180063318;
  }
  return 1;
}

```

## disassembly

```asm
0x180046bcc  push    rbx
0x180046bce  sub     rsp, 20h
0x180046bd2  mov     ebx, cs:dword_180063318
0x180046bd8  jmp     short loc_180046BF7
0x180046bda  lea     rax, qword_1800632F0
0x180046be1  dec     ebx
0x180046be3  lea     rcx, [rbx+rbx*4]
0x180046be7  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180046beb  call    cs:__imp_DeleteCriticalSection
0x180046bf1  dec     cs:dword_180063318
0x180046bf7  test    ebx, ebx
0x180046bf9  jnz     short loc_180046BDA
0x180046bfb  mov     al, 1
0x180046bfd  add     rsp, 20h
0x180046c01  pop     rbx
0x180046c02  retn
```
