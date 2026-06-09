# CSecurityExtension::AddRef(void)

- ea: `0x180008f30`
- end: `0x180008f37`
- name: `?AddRef@CSecurityExtension@@UEAAKXZ`
- size: `7`
- prototype: `__int64 __fastcall(CSecurityExtension *this)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008f40`
- `0x180008f50`

## pseudocode

```c
__int64 __fastcall CSecurityExtension::AddRef(CSecurityExtension *this)
{
  return (unsigned int)++*((_DWORD *)this + 6);
}

```

## disassembly

```asm
0x180008f30  inc     dword ptr [rcx+18h]
0x180008f33  mov     eax, [rcx+18h]
0x180008f36  retn
```
