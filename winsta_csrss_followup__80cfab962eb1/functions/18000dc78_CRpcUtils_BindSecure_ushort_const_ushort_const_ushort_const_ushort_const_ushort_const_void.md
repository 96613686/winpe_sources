# CRpcUtils::BindSecure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)

- ea: `0x18000dc78`
- end: `0x18000dce5`
- name: `?BindSecure@CRpcUtils@@SAJPEBG0000PEAPEAX@Z`
- size: `109`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006480`
- `0x1800075a0`
- `0x180020c90`
- `0x18002eeec`

## callees

- `0x18000dcec`
- `0x180032c20`

## string_xrefs

- `0x18000dca7`: `Security=Impersonation Dynamic False`

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
0x18000dc78  mov     r11, rsp
0x18000dc7b  sub     rsp, 68h
0x18000dc7f  mov     rax, cs:__security_cookie
0x18000dc86  xor     rax, rsp
0x18000dc89  mov     [rsp+68h+var_18], rax
0x18000dc8e  mov     rax, [rsp+68h+arg_28]
0x18000dc96  mov     edx, 1
0x18000dc9b  mov     [r11-38h], rax
0x18000dc9f  lea     rax, [r11-28h]
0x18000dca3  mov     [r11-40h], rax
0x18000dca7  lea     rax, Options; "Security=Impersonation Dynamic False"
0x18000dcae  mov     [rsp+68h+var_24], edx
0x18000dcb2  mov     [rsp+68h+var_20], edx
0x18000dcb6  mov     [rsp+68h+var_28], edx
0x18000dcba  lea     rdx, aNcacnNp; "ncacn_np"
0x18000dcc1  mov     [r11-48h], rax
0x18000dcc5  mov     [rsp+68h+var_1C], 3
0x18000dccd  call    ?BindSecureEx@CRpcUtils@@SAJPEBG0000PEAU_RPC_SECURITY_QOS@@PEAPEAX@Z; CRpcUtils::BindSecureEx(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_RPC_SECURITY_QOS *,void * *)
0x18000dcd2  mov     rcx, [rsp+68h+var_18]
0x18000dcd7  xor     rcx, rsp; StackCookie
0x18000dcda  call    __security_check_cookie
0x18000dcdf  add     rsp, 68h
0x18000dce3  retn
```
