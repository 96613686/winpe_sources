# CWuaClassFactoryBase::AddRef(void)

- ea: `0x14000bee0`
- end: `0x14000beed`
- name: `?AddRef@CWuaClassFactoryBase@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CWuaClassFactoryBase *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x14001a500`
- `0x14001a520`

## pseudocode

```c
__int64 __fastcall CWuaClassFactoryBase::AddRef(CWuaClassFactoryBase *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 6);
}

```

## disassembly

```asm
0x14000bee0  mov     eax, 1
0x14000bee5  lock xadd [rcx+18h], eax
0x14000beea  inc     eax
0x14000beec  retn
```
