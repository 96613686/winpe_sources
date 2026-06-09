# operator delete(void *)

- ea: `0x14003af44`
- end: `0x14003af61`
- name: `??3@YAXPEAX@Z`
- size: `29`
- prototype: `void __fastcall(void *)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14003af68`
- `0x14003c6f8`
- `0x14003c720`
- `0x14003c748`
- `0x14003c770`
- `0x14003c798`
- `0x14003c7c0`
- `0x14003c7e8`

## callees

- `0x14003af44`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003af4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003af4f`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x14003af44  sub     rsp, 28h
0x14003af48  test    rcx, rcx
0x14003af4b  jz      short loc_14003AF5B
0x14003af4d  xor     edx, edx; Tag
0x14003af4f  call    cs:__imp_ExFreePoolWithTag
0x14003af56  nop     dword ptr [rax+rax+00h]
0x14003af5b  add     rsp, 28h
0x14003af5f  retn
```
