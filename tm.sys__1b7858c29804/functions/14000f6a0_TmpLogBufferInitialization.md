# TmpLogBufferInitialization

- ea: `0x14000f6a0`
- end: `0x14000f6df`
- name: `TmpLogBufferInitialization`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140024080`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x14000f6cb`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14000f6cb`

## pseudocode

```c
char TmpLogBufferInitialization()
{
  ExInitializePagedLookasideList(&TmpLogWriteLookasideList, 0, 0, 0, 0x308u, 0x6C4C6D54u, 0);
  return 1;
}

```

## disassembly

```asm
0x14000f6a0  sub     rsp, 48h
0x14000f6a4  xor     eax, eax
0x14000f6a6  lea     rcx, TmpLogWriteLookasideList; Lookaside
0x14000f6ad  mov     [rsp+48h+Depth], ax; Depth
0x14000f6b2  xor     r9d, r9d; Flags
0x14000f6b5  mov     [rsp+48h+Tag], 6C4C6D54h; Tag
0x14000f6bd  xor     r8d, r8d; Free
0x14000f6c0  xor     edx, edx; Allocate
0x14000f6c2  mov     [rsp+48h+Size], 308h; Size
0x14000f6cb  call    cs:__imp_ExInitializePagedLookasideList
0x14000f6d2  nop     dword ptr [rax+rax+00h]
0x14000f6d7  mov     al, 1
0x14000f6d9  add     rsp, 48h
0x14000f6dd  retn
```
