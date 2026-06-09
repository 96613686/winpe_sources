# __vcrt_uninitialize_locks

- ea: `0x100427be4`
- end: `0x100427c1b`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x100427570`
- `0x1004275d4`
- `0x100427bac`

## callees

- `0x100427be4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x100427c03`
- `KERNEL32!DeleteCriticalSection` at `0x100427c03`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_100451358;
  while ( v0 )
  {
    DeleteCriticalSection(&CriticalSection + (unsigned int)--v0);
    --dword_100451358;
  }
  return 1;
}

```

## disassembly

```asm
0x100427be4  push    rbx
0x100427be6  sub     rsp, 20h
0x100427bea  mov     ebx, cs:dword_100451358
0x100427bf0  jmp     short loc_100427C0F
0x100427bf2  lea     rax, CriticalSection
0x100427bf9  dec     ebx
0x100427bfb  lea     rcx, [rbx+rbx*4]
0x100427bff  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x100427c03  call    cs:__imp_DeleteCriticalSection
0x100427c09  dec     cs:dword_100451358
0x100427c0f  test    ebx, ebx
0x100427c11  jnz     short loc_100427BF2
0x100427c13  mov     al, 1
0x100427c15  add     rsp, 20h
0x100427c19  pop     rbx
0x100427c1a  retn
```
