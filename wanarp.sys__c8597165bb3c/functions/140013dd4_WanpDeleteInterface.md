# WanpDeleteInterface

- ea: `0x140013dd4`
- end: `0x140013dec`
- name: `WanpDeleteInterface`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140004124`
- `0x140017550`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140013dda`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013dda`

## pseudocode

```c
void __fastcall WanpDeleteInterface(void *a1)
{
  ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x140013dd4  sub     rsp, 28h
0x140013dd8  xor     edx, edx; Tag
0x140013dda  call    cs:__imp_ExFreePoolWithTag
0x140013de1  nop     dword ptr [rax+rax+00h]
0x140013de6  add     rsp, 28h
0x140013dea  retn
```
