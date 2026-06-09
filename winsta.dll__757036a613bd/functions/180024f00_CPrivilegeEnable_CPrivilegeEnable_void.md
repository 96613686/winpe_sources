# CPrivilegeEnable::~CPrivilegeEnable(void)

- ea: `0x180024f00`
- end: `0x180024f2a`
- name: `??1CPrivilegeEnable@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(CPrivilegeEnable *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180028790`

## callees

- `0x180024f00`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180024f1f`
- `ntdll!RtlAdjustPrivilege` at `0x180024f1f`

## pseudocode

```c
void __fastcall CPrivilegeEnable::~CPrivilegeEnable(CPrivilegeEnable *this)
{
  bool v1; // zf
  ULONG v2; // ecx
  unsigned __int8 OldValue; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 4) )
  {
    v1 = *((_BYTE *)this + 5) == 0;
    v2 = *(_DWORD *)this;
    OldValue = 0;
    RtlAdjustPrivilege(v2, 0, !v1, &OldValue);
  }
}

```

## disassembly

```asm
0x180024f00  sub     rsp, 28h
0x180024f04  xor     eax, eax
0x180024f06  cmp     [rcx+4], al
0x180024f09  jz      short loc_180024F25
0x180024f0b  cmp     [rcx+5], al
0x180024f0e  lea     r9, [rsp+28h+OldValue]; OldValue
0x180024f13  mov     ecx, [rcx]; Privilege
0x180024f15  setnz   r8b; ForThread
0x180024f19  mov     [rsp+28h+OldValue], al
0x180024f1d  xor     edx, edx; NewValue
0x180024f1f  call    cs:__imp_RtlAdjustPrivilege
0x180024f25  add     rsp, 28h
0x180024f29  retn
```
