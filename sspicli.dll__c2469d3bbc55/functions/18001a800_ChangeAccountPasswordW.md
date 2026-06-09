# ChangeAccountPasswordW

- ea: `0x18001a800`
- end: `0x18001a843`
- name: `ChangeAccountPasswordW`
- size: `67`
- prototype: `SECURITY_STATUS __stdcall(SEC_WCHAR *pszPackageName, SEC_WCHAR *pszDomainName, SEC_WCHAR *pszAccountName, SEC_WCHAR *pszOldPassword, SEC_WCHAR *pszNewPassword, BOOLEAN bImpersonating, unsigned int dwReserved, PSecBufferDesc pOutput)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001a33c`

## pseudocode

```c
SECURITY_STATUS __stdcall ChangeAccountPasswordW(
        SEC_WCHAR *pszPackageName,
        SEC_WCHAR *pszDomainName,
        SEC_WCHAR *pszAccountName,
        SEC_WCHAR *pszOldPassword,
        SEC_WCHAR *pszNewPassword,
        BOOLEAN bImpersonating,
        unsigned int dwReserved,
        PSecBufferDesc pOutput)
{
  return ChangeAccountPasswordCommon(
           (const char *)pszPackageName,
           (__int64)pszDomainName,
           (__int64)pszAccountName,
           pszOldPassword,
           pszNewPassword,
           bImpersonating,
           dwReserved,
           pOutput,
           1u);
}

```

## disassembly

```asm
0x18001a800  sub     rsp, 58h
0x18001a804  mov     rax, [rsp+58h+pOutput]
0x18001a80c  mov     [rsp+58h+var_18], 1; unsigned __int8
0x18001a811  mov     [rsp+58h+var_20], rax; struct _SecBufferDesc *
0x18001a816  mov     eax, [rsp+58h+dwReserved]
0x18001a81d  mov     [rsp+58h+var_28], eax; unsigned int
0x18001a821  mov     al, [rsp+58h+bImpersonating]
0x18001a828  mov     [rsp+58h+var_30], al; unsigned __int8
0x18001a82c  mov     rax, [rsp+58h+pszNewPassword]
0x18001a834  mov     [rsp+58h+var_38], rax; void *
0x18001a839  call    ?ChangeAccountPasswordCommon@@YAJPEAX0000EKPEAU_SecBufferDesc@@E@Z; ChangeAccountPasswordCommon(void *,void *,void *,void *,void *,uchar,ulong,_SecBufferDesc *,uchar)
0x18001a83e  add     rsp, 58h
0x18001a842  retn
```
