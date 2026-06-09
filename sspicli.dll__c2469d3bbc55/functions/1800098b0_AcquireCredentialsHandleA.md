# AcquireCredentialsHandleA

- ea: `0x1800098b0`
- end: `0x180009902`
- name: `AcquireCredentialsHandleA`
- size: `82`
- prototype: `SECURITY_STATUS __stdcall(LPSTR pszPrincipal, LPSTR pszPackage, unsigned int fCredentialUse, void *pvLogonId, void *pAuthData, SEC_GET_KEY_FN pGetKeyFn, void *pvGetKeyArgument, PCredHandle phCredential, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000996c`

## pseudocode

```c
SECURITY_STATUS __stdcall AcquireCredentialsHandleA(
        LPSTR pszPrincipal,
        LPSTR pszPackage,
        unsigned int fCredentialUse,
        void *pvLogonId,
        void *pAuthData,
        SEC_GET_KEY_FN pGetKeyFn,
        void *pvGetKeyArgument,
        PCredHandle phCredential,
        PTimeStamp ptsExpiry)
{
  return AcquireCredentialsHandleCommon(
           (unsigned __int16 *)pszPrincipal,
           pszPackage,
           fCredentialUse,
           pvLogonId,
           pAuthData,
           pGetKeyFn,
           pvGetKeyArgument,
           phCredential,
           ptsExpiry,
           0);
}

```

## disassembly

```asm
0x1800098b0  mov     r11, rsp
0x1800098b3  sub     rsp, 58h
0x1800098b7  mov     rax, [rsp+58h+ptsExpiry]
0x1800098bf  mov     [rsp+58h+var_10], 0; char
0x1800098c4  mov     [r11-18h], rax
0x1800098c8  mov     rax, [rsp+58h+phCredential]
0x1800098d0  mov     [r11-20h], rax
0x1800098d4  mov     rax, [rsp+58h+pvGetKeyArgument]
0x1800098dc  mov     [r11-28h], rax
0x1800098e0  mov     rax, [rsp+58h+pGetKeyFn]
0x1800098e8  mov     [r11-30h], rax
0x1800098ec  mov     rax, [rsp+58h+pAuthData]
0x1800098f4  mov     [r11-38h], rax
0x1800098f8  call    ?AcquireCredentialsHandleCommon@@YAJPEAGPEAXK11P6AX11KPEAPEAXPEAJ@Z1PEAU_SecHandle@@PEAT_LARGE_INTEGER@@E@Z; AcquireCredentialsHandleCommon(ushort *,void *,ulong,void *,void *,void (*)(void *,void *,ulong,void * *,long *),void *,_SecHandle *,_LARGE_INTEGER *,uchar)
0x1800098fd  add     rsp, 58h
0x180009901  retn
```
