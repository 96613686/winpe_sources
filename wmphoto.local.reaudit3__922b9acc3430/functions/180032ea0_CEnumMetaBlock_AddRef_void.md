# CEnumMetaBlock::AddRef(void)

- ea: `0x180032ea0`
- end: `0x180032ead`
- name: `?AddRef@CEnumMetaBlock@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CEnumMetaBlock *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180038810`
- `0x180038820`
- `0x18003ae50`
- `0x18003ae70`

## pseudocode

```c
__int64 __fastcall CEnumMetaBlock::AddRef(CEnumMetaBlock *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x180032ea0  mov     eax, 1
0x180032ea5  lock xadd [rcx+8], eax
0x180032eaa  inc     eax
0x180032eac  retn
```
