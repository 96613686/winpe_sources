# CShareSecurityInformation::AddRef(void)

- ea: `0x18000af60`
- end: `0x18000af6d`
- name: `?AddRef@CShareSecurityInformation@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(CShareSecurityInformation *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CShareSecurityInformation::AddRef(CShareSecurityInformation *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 6);
}

```

## disassembly

```asm
0x18000af60  mov     eax, 1
0x18000af65  lock xadd [rcx+18h], eax
0x18000af6a  inc     eax
0x18000af6c  retn
```
