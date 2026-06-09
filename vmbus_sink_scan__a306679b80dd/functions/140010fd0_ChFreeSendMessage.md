# ChFreeSendMessage

- ea: `0x140010fd0`
- end: `0x140010fef`
- name: `ChFreeSendMessage`
- size: `31`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x14000f5f0`
- `0x140010344`
- `0x140010f54`
- `0x140011c40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010fdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010fdd`

## pseudocode

```c
void __fastcall ChFreeSendMessage(__int64 a1)
{
  ExFreePoolWithTag((PVOID)(a1 - 56), 0x73756256u);
}

```

## disassembly

```asm
0x140010fd0  sub     rsp, 28h
0x140010fd4  add     rcx, 0FFFFFFFFFFFFFFC8h; P
0x140010fd8  mov     edx, 73756256h; Tag
0x140010fdd  call    cs:__imp_ExFreePoolWithTag
0x140010fe4  nop     dword ptr [rax+rax+00h]
0x140010fe9  add     rsp, 28h
0x140010fed  retn
```
