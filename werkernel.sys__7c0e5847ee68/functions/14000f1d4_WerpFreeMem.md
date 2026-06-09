# WerpFreeMem

- ea: `0x14000f1d4`
- end: `0x14000f1f1`
- name: `WerpFreeMem`
- size: `29`
- prototype: `void __fastcall(void *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140012080`
- `0x1400122c0`
- `0x140012588`

## callees

- `0x14000f1d4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f1df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f1df`

## pseudocode

```c
void __fastcall WerpFreeMem(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x14000f1d4  sub     rsp, 28h
0x14000f1d8  test    rcx, rcx
0x14000f1db  jz      short loc_14000F1EB
0x14000f1dd  xor     edx, edx; Tag
0x14000f1df  call    cs:__imp_ExFreePoolWithTag
0x14000f1e6  nop     dword ptr [rax+rax+00h]
0x14000f1eb  add     rsp, 28h
0x14000f1ef  retn
```
