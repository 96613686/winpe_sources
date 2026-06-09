# ChangeAccountPasswordA

- ea: `0x18001a7b0`
- end: `0x18001a7f3`
- name: `ChangeAccountPasswordA`
- size: `67`
- prototype: `SECURITY_STATUS __stdcall(SEC_CHAR *pszPackageName, SEC_CHAR *pszDomainName, SEC_CHAR *pszAccountName, SEC_CHAR *pszOldPassword, SEC_CHAR *pszNewPassword, BOOLEAN bImpersonating, unsigned int dwReserved, PSecBufferDesc pOutput)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001a33c`

## pseudocode

```c
SECURITY_STATUS __stdcall ChangeAccountPasswordA(
        SEC_CHAR *pszPackageName,
        SEC_CHAR *pszDomainName,
        SEC_CHAR *pszAccountName,
        SEC_CHAR *pszOldPassword,
        SEC_CHAR *pszNewPassword,
        BOOLEAN bImpersonating,
        unsigned int dwReserved,
        PSecBufferDesc pOutput)
{
  return ChangeAccountPasswordCommon(
           pszPackageName,
           (__int64)pszDomainName,
           (__int64)pszAccountName,
           pszOldPassword,
           pszNewPassword,
           bImpersonating,
           dwReserved,
           pOutput,
           0);
}

```

## disassembly

```asm
0x18001a7b0  sub     rsp, 58h
0x18001a7b4  mov     rax, [rsp+58h+pOutput]
0x18001a7bc  mov     [rsp+58h+var_18], 0; unsigned __int8
0x18001a7c1  mov     [rsp+58h+var_20], rax; struct _SecBufferDesc *
0x18001a7c6  mov     eax, [rsp+58h+dwReserved]
0x18001a7cd  mov     [rsp+58h+var_28], eax; unsigned int
0x18001a7d1  mov     al, [rsp+58h+bImpersonating]
0x18001a7d8  mov     [rsp+58h+var_30], al; unsigned __int8
0x18001a7dc  mov     rax, [rsp+58h+pszNewPassword]
0x18001a7e4  mov     [rsp+58h+var_38], rax; void *
0x18001a7e9  call    ?ChangeAccountPasswordCommon@@YAJPEAX0000EKPEAU_SecBufferDesc@@E@Z; ChangeAccountPasswordCommon(void *,void *,void *,void *,void *,uchar,ulong,_SecBufferDesc *,uchar)
0x18001a7ee  add     rsp, 58h
0x18001a7f2  retn
```
