# __acrt_uninitialize_locks

- ea: `0x10041bbc0`
- end: `0x10041bbf7`
- name: `__acrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10041bb50`

## callees

- `0x10041bbc0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x10041bbdf`
- `KERNEL32!DeleteCriticalSection` at `0x10041bbdf`

## pseudocode

```c
char _acrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_1004357E0;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1004355B0[5 * (unsigned int)--v0]);
    --dword_1004357E0;
  }
  return 1;
}

```

## disassembly

```asm
0x10041bbc0  push    rbx
0x10041bbc2  sub     rsp, 20h
0x10041bbc6  mov     ebx, cs:dword_1004357E0
0x10041bbcc  jmp     short loc_10041BBEB
0x10041bbce  lea     rax, qword_1004355B0
0x10041bbd5  dec     ebx
0x10041bbd7  lea     rcx, [rbx+rbx*4]
0x10041bbdb  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x10041bbdf  call    cs:__imp_DeleteCriticalSection
0x10041bbe5  dec     cs:dword_1004357E0
0x10041bbeb  test    ebx, ebx
0x10041bbed  jnz     short loc_10041BBCE
0x10041bbef  mov     al, 1
0x10041bbf1  add     rsp, 20h
0x10041bbf5  pop     rbx
0x10041bbf6  retn
```
