# __vcrt_uninitialize_locks

- ea: `0x100417c14`
- end: `0x100417c4b`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1004175a0`
- `0x100417604`
- `0x100417bdc`

## callees

- `0x100417c14`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x100417c33`
- `KERNEL32!DeleteCriticalSection` at `0x100417c33`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_1004353E8;
  while ( v0 )
  {
    DeleteCriticalSection(&CriticalSection + (unsigned int)--v0);
    --dword_1004353E8;
  }
  return 1;
}

```

## disassembly

```asm
0x100417c14  push    rbx
0x100417c16  sub     rsp, 20h
0x100417c1a  mov     ebx, cs:dword_1004353E8
0x100417c20  jmp     short loc_100417C3F
0x100417c22  lea     rax, CriticalSection
0x100417c29  dec     ebx
0x100417c2b  lea     rcx, [rbx+rbx*4]
0x100417c2f  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x100417c33  call    cs:__imp_DeleteCriticalSection
0x100417c39  dec     cs:dword_1004353E8
0x100417c3f  test    ebx, ebx
0x100417c41  jnz     short loc_100417C22
0x100417c43  mov     al, 1
0x100417c45  add     rsp, 20h
0x100417c49  pop     rbx
0x100417c4a  retn
```
