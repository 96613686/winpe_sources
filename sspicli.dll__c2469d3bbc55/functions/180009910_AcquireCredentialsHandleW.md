# AcquireCredentialsHandleW

- ea: `0x180009910`
- end: `0x180009964`
- name: `AcquireCredentialsHandleW`
- size: `84`
- prototype: `SECURITY_STATUS __stdcall(LPWSTR pszPrincipal, LPWSTR pszPackage, unsigned int fCredentialUse, void *pvLogonId, void *pAuthData, SEC_GET_KEY_FN pGetKeyFn, void *pvGetKeyArgument, PCredHandle phCredential, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000996c`

## pseudocode

```c
SECURITY_STATUS __stdcall AcquireCredentialsHandleW(
        LPWSTR pszPrincipal,
        LPWSTR pszPackage,
        unsigned int fCredentialUse,
        void *pvLogonId,
        void *pAuthData,
        SEC_GET_KEY_FN pGetKeyFn,
        void *pvGetKeyArgument,
        PCredHandle phCredential,
        PTimeStamp ptsExpiry)
{
  return AcquireCredentialsHandleCommon(
           pszPrincipal,
           pszPackage,
           fCredentialUse,
           pvLogonId,
           pAuthData,
           pGetKeyFn,
           pvGetKeyArgument,
           phCredential,
           ptsExpiry,
           1);
}

```

## disassembly

```asm
0x180009910  sub     rsp, 58h
0x180009914  mov     rax, [rsp+58h+ptsExpiry]
0x18000991c  mov     [rsp+58h+var_10], 1; char
0x180009921  mov     [rsp+58h+var_18], rax; union _LARGE_INTEGER *
0x180009926  mov     rax, [rsp+58h+phCredential]
0x18000992e  mov     [rsp+58h+var_20], rax; struct _SecHandle *
0x180009933  mov     rax, [rsp+58h+pvGetKeyArgument]
0x18000993b  mov     [rsp+58h+var_28], rax; void *
0x180009940  mov     rax, [rsp+58h+pGetKeyFn]
0x180009948  mov     [rsp+58h+var_30], rax; void (*)(void *, void *, unsigned int, void **, int *)
0x18000994d  mov     rax, [rsp+58h+pAuthData]
0x180009955  mov     [rsp+58h+var_38], rax; void *
0x18000995a  call    ?AcquireCredentialsHandleCommon@@YAJPEAGPEAXK11P6AX11KPEAPEAXPEAJ@Z1PEAU_SecHandle@@PEAT_LARGE_INTEGER@@E@Z; AcquireCredentialsHandleCommon(ushort *,void *,ulong,void *,void *,void (*)(void *,void *,ulong,void * *,long *),void *,_SecHandle *,_LARGE_INTEGER *,uchar)
0x18000995f  add     rsp, 58h
0x180009963  retn
```
