# CRpcUtils::BindSecure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)

- ea: `0x18000c0e8`
- end: `0x18000c154`
- name: `?BindSecure@CRpcUtils@@SAJPEBG0000PEAPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008150`
- `0x180008e30`
- `0x18001f5f8`
- `0x18002cb5c`

## callees

- `0x18000c15c`
- `0x18002fe40`

## string_xrefs

- `0x18000c117`: `Security=Impersonation Dynamic False`

## pseudocode

```c
int __fastcall CRpcUtils::BindSecure(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        void **a6)
{
  struct _RPC_SECURITY_QOS v7; // [rsp+40h] [rbp-28h] BYREF

  v7.Capabilities = 1;
  v7.IdentityTracking = 1;
  v7.Version = 1;
  v7.ImpersonationType = 3;
  return CRpcUtils::BindSecureEx(a1, L"ncacn_np", a3, a4, L"Security=Impersonation Dynamic False", &v7, a6);
}

```

## disassembly

```asm
0x18000c0e8  mov     r11, rsp
0x18000c0eb  sub     rsp, 68h
0x18000c0ef  mov     rax, cs:__security_cookie
0x18000c0f6  xor     rax, rsp
0x18000c0f9  mov     [rsp+68h+var_18], rax
0x18000c0fe  mov     rax, [rsp+68h+arg_28]
0x18000c106  mov     edx, 1
0x18000c10b  mov     [r11-38h], rax
0x18000c10f  lea     rax, [r11-28h]
0x18000c113  mov     [r11-40h], rax
0x18000c117  lea     rax, Options; "Security=Impersonation Dynamic False"
0x18000c11e  mov     [rsp+68h+var_24], edx
0x18000c122  mov     [rsp+68h+var_20], edx
0x18000c126  mov     [rsp+68h+var_28], edx
0x18000c12a  lea     rdx, aNcacnNp; "ncacn_np"
0x18000c131  mov     [r11-48h], rax
0x18000c135  mov     [rsp+68h+var_1C], 3
0x18000c13d  call    ?BindSecureEx@CRpcUtils@@SAJPEBG0000PEAU_RPC_SECURITY_QOS@@PEAPEAX@Z; CRpcUtils::BindSecureEx(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_RPC_SECURITY_QOS *,void * *)
0x18000c142  mov     rcx, [rsp+68h+var_18]
0x18000c147  xor     rcx, rsp; StackCookie
0x18000c14a  call    __security_check_cookie
0x18000c14f  add     rsp, 68h
0x18000c153  retn
```
