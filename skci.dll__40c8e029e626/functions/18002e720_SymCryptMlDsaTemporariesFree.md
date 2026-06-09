# SymCryptMlDsaTemporariesFree

- ea: `0x18002e720`
- end: `0x18002e751`
- name: `SymCryptMlDsaTemporariesFree`
- size: `49`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18002697c`
- `0x180026bf8`
- `0x1800270d4`
- `0x18002d48c`
- `0x18002d6d4`
- `0x18002e158`
- `0x18002e414`

## callees

- `0x180009780`

## import_xrefs

- `securekernel!SkFreePool` at `0x18002e73e`
- `securekernel!SkFreePool` at `0x18002e73e`

## pseudocode

```c
__int64 __fastcall SymCryptMlDsaTemporariesFree(unsigned int *a1)
{
  SymCryptWipeAsm(a1, *a1);
  return SkFreePool(1, (char *)a1 - *(a1 - 1));
}

```

## disassembly

```asm
0x18002e720  push    rbx
0x18002e722  sub     rsp, 20h
0x18002e726  mov     edx, [rcx]
0x18002e728  mov     rbx, rcx
0x18002e72b  call    SymCryptWipeAsm
0x18002e730  mov     eax, [rbx-4]
0x18002e733  mov     ecx, 1
0x18002e738  sub     rbx, rax
0x18002e73b  mov     rdx, rbx
0x18002e73e  call    cs:__imp_SkFreePool
0x18002e745  nop     dword ptr [rax+rax+00h]
0x18002e74a  add     rsp, 20h
0x18002e74e  pop     rbx
0x18002e74f  retn
```
