# CPrivilegeEnable::~CPrivilegeEnable(void)

- ea: `0x180026824`
- end: `0x180026855`
- name: `??1CPrivilegeEnable@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(CPrivilegeEnable *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002a340`

## callees

- `0x180026824`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180026843`
- `ntdll!RtlAdjustPrivilege` at `0x180026843`

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
0x180026824  sub     rsp, 28h
0x180026828  xor     eax, eax
0x18002682a  cmp     [rcx+4], al
0x18002682d  jz      short loc_18002684F
0x18002682f  cmp     [rcx+5], al
0x180026832  lea     r9, [rsp+28h+OldValue]; OldValue
0x180026837  mov     ecx, [rcx]; Privilege
0x180026839  setnz   r8b; ForThread
0x18002683d  mov     [rsp+28h+OldValue], al
0x180026841  xor     edx, edx; NewValue
0x180026843  call    cs:__imp_RtlAdjustPrivilege
0x18002684a  nop     dword ptr [rax+rax+00h]
0x18002684f  add     rsp, 28h
0x180026853  retn
```
