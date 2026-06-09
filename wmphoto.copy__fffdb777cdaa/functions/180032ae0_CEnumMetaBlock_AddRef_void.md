# CEnumMetaBlock::AddRef(void)

- ea: `0x180032ae0`
- end: `0x180032aed`
- name: `?AddRef@CEnumMetaBlock@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CEnumMetaBlock *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800381d0`
- `0x1800381e0`
- `0x18003a6d0`
- `0x18003a6f0`

## pseudocode

```c
__int64 __fastcall CEnumMetaBlock::AddRef(CEnumMetaBlock *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x180032ae0  mov     eax, 1
0x180032ae5  lock xadd [rcx+8], eax
0x180032aea  inc     eax
0x180032aec  retn
```
