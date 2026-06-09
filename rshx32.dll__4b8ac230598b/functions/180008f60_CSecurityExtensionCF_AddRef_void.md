# CSecurityExtensionCF::AddRef(void)

- ea: `0x180008f60`
- end: `0x180008f67`
- name: `?AddRef@CSecurityExtensionCF@@UEAAKXZ`
- size: `7`
- prototype: `__int64 __fastcall(CSecurityExtensionCF *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CSecurityExtensionCF::AddRef(CSecurityExtensionCF *this)
{
  return (unsigned int)++*((_DWORD *)this + 2);
}

```

## disassembly

```asm
0x180008f60  inc     dword ptr [rcx+8]
0x180008f63  mov     eax, [rcx+8]
0x180008f66  retn
```
