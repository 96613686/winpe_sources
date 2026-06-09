# CWmRgSrv::EnumDcomCLSIDs(_GUID *,ulong)

- ea: `0x180004520`
- end: `0x180004538`
- name: `?EnumDcomCLSIDs@CWmRgSrv@@UEAAJPEAU_GUID@@K@Z`
- size: `24`
- prototype: `__int64 __fastcall(CWmRgSrv *__hidden this, struct _GUID *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004520`

## pseudocode

```c
__int64 __fastcall CWmRgSrv::EnumDcomCLSIDs(CWmRgSrv *this, struct _GUID *a2, int a3)
{
  __int64 result; // rax

  result = 2147942659LL;
  if ( !a3 )
  {
    result = 0;
    *a2 = CLSID_WamAdmin;
  }
  return result;
}

```

## disassembly

```asm
0x180004520  mov     eax, 80070103h
0x180004525  test    r8d, r8d
0x180004528  jnz     short locret_180004537
0x18000452a  movups  xmm0, xmmword ptr cs:CLSID_WamAdmin.Data1
0x180004531  xor     eax, eax
0x180004533  movdqu  xmmword ptr [rdx], xmm0
0x180004537  retn
```
