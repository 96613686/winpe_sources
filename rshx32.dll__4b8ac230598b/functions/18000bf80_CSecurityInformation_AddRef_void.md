# CSecurityInformation::AddRef(void)

- ea: `0x18000bf80`
- end: `0x18000bf87`
- name: `?AddRef@CSecurityInformation@@UEAAKXZ`
- size: `7`
- prototype: `__int64 __fastcall(CSecurityInformation *this)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180005ef0`
- `0x180005f00`
- `0x180005f10`
- `0x180005f20`
- `0x180005f30`

## pseudocode

```c
__int64 __fastcall CSecurityInformation::AddRef(CSecurityInformation *this)
{
  return (unsigned int)++*((_DWORD *)this + 12);
}

```

## disassembly

```asm
0x18000bf80  inc     dword ptr [rcx+30h]
0x18000bf83  mov     eax, [rcx+30h]
0x18000bf86  retn
```
