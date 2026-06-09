# CWamAdmin::AddRef(void)

- ea: `0x180001e70`
- end: `0x180001e7d`
- name: `?AddRef@CWamAdmin@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CWamAdmin *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e90`
- `0x180001ea0`

## pseudocode

```c
__int64 __fastcall CWamAdmin::AddRef(CWamAdmin *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 6);
}

```

## disassembly

```asm
0x180001e70  mov     eax, 1
0x180001e75  lock xadd [rcx+18h], eax
0x180001e7a  inc     eax
0x180001e7c  retn
```
