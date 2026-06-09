# CompositeFlags::SetFlagUnsafe(uint)

- ea: `0x180019468`
- end: `0x18001946f`
- name: `?SetFlagUnsafe@CompositeFlags@@QEAAXI@Z`
- size: `7`
- prototype: `void __fastcall(CompositeFlags *__hidden this, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002360`
- `0x180019260`
- `0x1800193b8`
- `0x180019478`
- `0x180019840`

## pseudocode

```c
void __fastcall CompositeFlags::SetFlagUnsafe(CompositeFlags *this, int a2)
{
  *(_DWORD *)this |= a2;
}

```

## disassembly

```asm
0x180019468  mov     eax, [rcx]
0x18001946a  or      eax, edx
0x18001946c  mov     [rcx], eax
0x18001946e  retn
```
