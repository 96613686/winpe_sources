# CompositeFlags::GetFlag(uint)

- ea: `0x18000ad50`
- end: `0x18000ad55`
- name: `?GetFlag@CompositeFlags@@QEBAHI@Z`
- size: `5`
- prototype: `__int64 __fastcall(CompositeFlags *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000ee74`
- `0x18000ee8c`
- `0x18000eea4`
- `0x18000ef14`
- `0x18000f048`
- `0x18000f060`

## pseudocode

```c
__int64 __fastcall CompositeFlags::GetFlag(CompositeFlags *this, unsigned int a2)
{
  return a2 & *(_DWORD *)this;
}

```

## disassembly

```asm
0x18000ad50  mov     eax, [rcx]
0x18000ad52  and     eax, edx
0x18000ad54  retn
```
