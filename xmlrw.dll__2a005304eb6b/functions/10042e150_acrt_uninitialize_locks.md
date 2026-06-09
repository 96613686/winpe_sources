# __acrt_uninitialize_locks

- ea: `0x10042e150`
- end: `0x10042e187`
- name: `__acrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10042e0e0`

## callees

- `0x10042e150`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x10042e16f`
- `KERNEL32!DeleteCriticalSection` at `0x10042e16f`

## pseudocode

```c
char _acrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_100451750;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_100451520[5 * (unsigned int)--v0]);
    --dword_100451750;
  }
  return 1;
}

```

## disassembly

```asm
0x10042e150  push    rbx
0x10042e152  sub     rsp, 20h
0x10042e156  mov     ebx, cs:dword_100451750
0x10042e15c  jmp     short loc_10042E17B
0x10042e15e  lea     rax, qword_100451520
0x10042e165  dec     ebx
0x10042e167  lea     rcx, [rbx+rbx*4]
0x10042e16b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x10042e16f  call    cs:__imp_DeleteCriticalSection
0x10042e175  dec     cs:dword_100451750
0x10042e17b  test    ebx, ebx
0x10042e17d  jnz     short loc_10042E15E
0x10042e17f  mov     al, 1
0x10042e181  add     rsp, 20h
0x10042e185  pop     rbx
0x10042e186  retn
```
