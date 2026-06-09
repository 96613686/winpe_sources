# ShutdownComponents(void)

- ea: `0x1004116d0`
- end: `0x100411706`
- name: `?ShutdownComponents@@YAXXZ`
- size: `54`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1004116d0`

## import_xrefs

- `sqlmin!?SQLMinShutdownComponents@@YAXXZ` at `0x1004116d4`
- `sqlmin!?SQLMinShutdownComponents@@YAXXZ` at `0x1004116d4`
- `sqllang!?SQLLangShutdownComponents@@YAXXZ` at `0x1004116da`
- `sqllang!?SQLLangShutdownComponents@@YAXXZ` at `0x1004116da`
- `sbs!?SbsShutdown@@YAXXZ` at `0x1004116f4`

## pseudocode

```c
void ShutdownComponents(void)
{
  SQLMinShutdownComponents();
  SQLLangShutdownComponents();
  if ( *((_DWORD *)qword_10049F360 + 3645) )
    SbsShutdown();
}

```

## disassembly

```asm
0x1004116d0  sub     rsp, 28h
0x1004116d4  call    cs:__imp_?SQLMinShutdownComponents@@YAXXZ; SQLMinShutdownComponents(void)
0x1004116da  call    cs:__imp_?SQLLangShutdownComponents@@YAXXZ; SQLLangShutdownComponents(void)
0x1004116e0  mov     rax, cs:qword_10049F360
0x1004116e7  cmp     dword ptr [rax+38F4h], 0
0x1004116ee  jz      short loc_100411701
0x1004116f0  add     rsp, 28h
0x1004116f4  jmp     cs:__imp_?SbsShutdown@@YAXXZ; SbsShutdown(void)
0x100411701  add     rsp, 28h
0x100411705  retn
```
