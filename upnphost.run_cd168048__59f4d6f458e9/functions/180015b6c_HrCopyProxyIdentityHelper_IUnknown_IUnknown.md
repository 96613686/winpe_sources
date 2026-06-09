# HrCopyProxyIdentityHelper(IUnknown *,IUnknown *)

- ea: `0x180015b6c`
- end: `0x180015ce8`
- name: `?HrCopyProxyIdentityHelper@@YAJPEAUIUnknown@@0@Z`
- size: `380`
- prototype: `__int64 __fastcall(IUnknown *pProxy, IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180015a9c`

## callees

- `0x180015b6c`
- `0x18003b1cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180015c7a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180015c7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015c8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015c8a`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180015bd7`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180015c1a`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180015bd7`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180015c1a`

## pseudocode

```c
__int64 __fastcall HrCopyProxyIdentityHelper(IUnknown *pProxy, IUnknown *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  DWORD pAuthzSvc; // [rsp+40h] [rbp-20h] BYREF
  DWORD pwAuthnSvc; // [rsp+44h] [rbp-1Ch] BYREF
  DWORD v9; // [rsp+48h] [rbp-18h] BYREF
  LPOLESTR pServerPrincName; // [rsp+50h] [rbp-10h] BYREF
  RPC_AUTH_IDENTITY_HANDLE pAuthInfo; // [rsp+58h] [rbp-8h] BYREF
  DWORD dwCapabilities; // [rsp+90h] [rbp+30h] BYREF
  DWORD dwImpLevel; // [rsp+A0h] [rbp+40h] BYREF
  DWORD dwAuthnLevel; // [rsp+A8h] [rbp+48h] BYREF

  if ( pProxy && a2 )
  {
    dwAuthnLevel = 0;
    dwImpLevel = 0;
    dwCapabilities = 0;
    pwAuthnSvc = 0;
    pAuthzSvc = 0;
    pServerPrincName = 0;
    v4 = CoQueryProxyBlanket(
           pProxy,
           &pwAuthnSvc,
           &pAuthzSvc,
           &pServerPrincName,
           &dwAuthnLevel,
           &dwImpLevel,
           0,
           &dwCapabilities);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( v4 == -2147417833 || v4 == -2147467262 )
        return 0;
    }
    else
    {
      pAuthInfo = 0;
      v9 = 0;
      v5 = CoQueryProxyBlanket(a2, &v9, 0, 0, 0, 0, &pAuthInfo, 0);
      if ( (v5 & 0x80000000) == 0 )
        v5 = CoSetProxyBlanket(
               pProxy,
               pwAuthnSvc,
               pAuthzSvc,
               pServerPrincName,
               dwAuthnLevel,
               dwImpLevel,
               pAuthInfo,
               dwCapabilities);
      if ( pServerPrincName )
        CoTaskMemFree(pServerPrincName);
      if ( !v5 )
        return v5;
    }
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_75c351f6869f3647f61a30e7f530184a_Traceguids, v5);
    return v5;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180015b6c  mov     r11, rsp
0x180015b6f  push    rbp
0x180015b70  push    rbx
0x180015b71  push    rsi
0x180015b72  push    rdi
0x180015b73  push    r14
0x180015b75  mov     rbp, rsp
0x180015b78  sub     rsp, 60h
0x180015b7c  xor     r14d, r14d
0x180015b7f  mov     rdi, rdx
0x180015b82  mov     rsi, rcx
0x180015b85  test    rcx, rcx
0x180015b88  jz      loc_180015C47
0x180015b8e  test    rdx, rdx
0x180015b91  jz      loc_180015C47
0x180015b97  lea     rax, [rbp+dwCapabilities]
0x180015b9b  mov     [rbp+dwAuthnLevel], r14d
0x180015b9f  mov     [r11-50h], rax
0x180015ba3  lea     r9, [rbp+pServerPrincName]; pServerPrincName
0x180015ba7  mov     [r11-58h], r14
0x180015bab  lea     rax, [rbp+dwImpLevel]
0x180015baf  mov     [r11-60h], rax
0x180015bb3  lea     r8, [rbp+pAuthzSvc]; pAuthzSvc
0x180015bb7  lea     rax, [rbp+dwAuthnLevel]
0x180015bbb  mov     [rbp+dwImpLevel], r14d
0x180015bbf  lea     rdx, [rbp+pwAuthnSvc]; pwAuthnSvc
0x180015bc3  mov     [r11-68h], rax
0x180015bc7  mov     [rbp+dwCapabilities], r14d
0x180015bcb  mov     [rbp+pwAuthnSvc], r14d
0x180015bcf  mov     [rbp+pAuthzSvc], r14d
0x180015bd3  mov     [rbp+pServerPrincName], r14
0x180015bd7  call    cs:__imp_CoQueryProxyBlanket
0x180015bde  nop     dword ptr [rax+rax+00h]
0x180015be3  mov     ebx, eax
0x180015be5  test    eax, eax
0x180015be7  js      loc_180015C98
0x180015bed  mov     [rsp+60h+pCapabilites], r14; pCapabilites
0x180015bf2  lea     rax, [rbp+var_8]
0x180015bf6  mov     [rsp+60h+pAuthInfo], rax; pAuthInfo
0x180015bfb  lea     rdx, [rbp+var_18]; pwAuthnSvc
0x180015bff  mov     [rsp+60h+pImpLevel], r14; pImpLevel
0x180015c04  xor     r9d, r9d; pServerPrincName
0x180015c07  xor     r8d, r8d; pAuthzSvc
0x180015c0a  mov     [rsp+60h+pAuthnLevel], r14; pAuthnLevel
0x180015c0f  mov     rcx, rdi; pProxy
0x180015c12  mov     [rbp+var_8], r14
0x180015c16  mov     [rbp+var_18], r14d
0x180015c1a  call    cs:__imp_CoQueryProxyBlanket
0x180015c21  nop     dword ptr [rax+rax+00h]
0x180015c26  mov     ebx, eax
0x180015c28  test    eax, eax
0x180015c2a  jns     short loc_180015C4E
0x180015c2c  mov     rcx, [rbp+pServerPrincName]; pv
0x180015c30  test    rcx, rcx
0x180015c33  jnz     short loc_180015C8A
0x180015c35  test    ebx, ebx
0x180015c37  jnz     short loc_180015CA6
0x180015c39  mov     eax, ebx
0x180015c3b  add     rsp, 60h
0x180015c3f  pop     r14
0x180015c41  pop     rdi
0x180015c42  pop     rsi
0x180015c43  pop     rbx
0x180015c44  pop     rbp
0x180015c45  retn
0x180015c47  mov     eax, 80004003h
0x180015c4c  jmp     short loc_180015C3B
0x180015c4e  mov     eax, [rbp+dwCapabilities]
0x180015c51  mov     rcx, rsi; pProxy
0x180015c54  mov     r9, [rbp+pServerPrincName]; pServerPrincName
0x180015c58  mov     r8d, [rbp+pAuthzSvc]; dwAuthzSvc
0x180015c5c  mov     edx, [rbp+pwAuthnSvc]; dwAuthnSvc
0x180015c5f  mov     dword ptr [rsp+60h+pCapabilites], eax; dwCapabilities
0x180015c63  mov     rax, [rbp+var_8]
0x180015c67  mov     [rsp+60h+pAuthInfo], rax; pAuthInfo
0x180015c6c  mov     eax, [rbp+dwImpLevel]
0x180015c6f  mov     dword ptr [rsp+60h+pImpLevel], eax; dwImpLevel
0x180015c73  mov     eax, [rbp+dwAuthnLevel]
0x180015c76  mov     dword ptr [rsp+60h+pAuthnLevel], eax; dwAuthnLevel
0x180015c7a  call    cs:__imp_CoSetProxyBlanket
0x180015c81  nop     dword ptr [rax+rax+00h]
0x180015c86  mov     ebx, eax
0x180015c88  jmp     short loc_180015C2C
0x180015c8a  call    cs:__imp_CoTaskMemFree
0x180015c91  nop     dword ptr [rax+rax+00h]
0x180015c96  jmp     short loc_180015C35
0x180015c98  cmp     eax, 80010117h
0x180015c9d  jz      short loc_180015CE0
0x180015c9f  cmp     eax, 80004002h
0x180015ca4  jz      short loc_180015CE0
0x180015ca6  mov     rcx, cs:WPP_GLOBAL_Control
0x180015cad  lea     rax, WPP_GLOBAL_Control
0x180015cb4  cmp     rcx, rax
0x180015cb7  jz      short loc_180015C39
0x180015cb9  test    byte ptr [rcx+1Ch], 1
0x180015cbd  jz      loc_180015C39
0x180015cc3  mov     rcx, [rcx+10h]
0x180015cc7  lea     r8, WPP_75c351f6869f3647f61a30e7f530184a_Traceguids
0x180015cce  mov     edx, 11h
0x180015cd3  mov     r9d, ebx
0x180015cd6  call    WPP_SF_d
0x180015cdb  jmp     loc_180015C39
0x180015ce0  mov     ebx, r14d
0x180015ce3  jmp     loc_180015C39
```
