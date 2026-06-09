# HrCopyProxyIdentityHelper(IUnknown *,IUnknown *)

- ea: `0x1800209e8`
- end: `0x180020b47`
- name: `?HrCopyProxyIdentityHelper@@YAJPEAUIUnknown@@0@Z`
- size: `351`
- prototype: `__int64 __fastcall(IUnknown *pProxy, IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180020918`

## callees

- `0x1800209e8`
- `0x180038ce4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180020ae9`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180020ae9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020af3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020af3`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180020a53`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180020a90`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180020a53`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180020a90`

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
0x1800209e8  mov     r11, rsp
0x1800209eb  push    rbp
0x1800209ec  push    rbx
0x1800209ed  push    rsi
0x1800209ee  push    rdi
0x1800209ef  push    r14
0x1800209f1  mov     rbp, rsp
0x1800209f4  sub     rsp, 60h
0x1800209f8  xor     r14d, r14d
0x1800209fb  mov     rdi, rdx
0x1800209fe  mov     rsi, rcx
0x180020a01  test    rcx, rcx
0x180020a04  jz      loc_180020AB6
0x180020a0a  test    rdx, rdx
0x180020a0d  jz      loc_180020AB6
0x180020a13  lea     rax, [rbp+dwCapabilities]
0x180020a17  mov     [rbp+dwAuthnLevel], r14d
0x180020a1b  mov     [r11-50h], rax
0x180020a1f  lea     r9, [rbp+pServerPrincName]; pServerPrincName
0x180020a23  mov     [r11-58h], r14
0x180020a27  lea     rax, [rbp+dwImpLevel]
0x180020a2b  mov     [r11-60h], rax
0x180020a2f  lea     r8, [rbp+pAuthzSvc]; pAuthzSvc
0x180020a33  lea     rax, [rbp+dwAuthnLevel]
0x180020a37  mov     [rbp+dwImpLevel], r14d
0x180020a3b  lea     rdx, [rbp+pwAuthnSvc]; pwAuthnSvc
0x180020a3f  mov     [r11-68h], rax
0x180020a43  mov     [rbp+dwCapabilities], r14d
0x180020a47  mov     [rbp+pwAuthnSvc], r14d
0x180020a4b  mov     [rbp+pAuthzSvc], r14d
0x180020a4f  mov     [rbp+pServerPrincName], r14
0x180020a53  call    cs:__imp_CoQueryProxyBlanket
0x180020a59  mov     ebx, eax
0x180020a5b  test    eax, eax
0x180020a5d  js      loc_180020AFB
0x180020a63  mov     [rsp+60h+pCapabilites], r14; pCapabilites
0x180020a68  lea     rax, [rbp+var_8]
0x180020a6c  mov     [rsp+60h+pAuthInfo], rax; pAuthInfo
0x180020a71  lea     rdx, [rbp+var_18]; pwAuthnSvc
0x180020a75  mov     [rsp+60h+pImpLevel], r14; pImpLevel
0x180020a7a  xor     r9d, r9d; pServerPrincName
0x180020a7d  xor     r8d, r8d; pAuthzSvc
0x180020a80  mov     [rsp+60h+pAuthnLevel], r14; pAuthnLevel
0x180020a85  mov     rcx, rdi; pProxy
0x180020a88  mov     [rbp+var_8], r14
0x180020a8c  mov     [rbp+var_18], r14d
0x180020a90  call    cs:__imp_CoQueryProxyBlanket
0x180020a96  mov     ebx, eax
0x180020a98  test    eax, eax
0x180020a9a  jns     short loc_180020ABD
0x180020a9c  mov     rcx, [rbp+pServerPrincName]; pv
0x180020aa0  test    rcx, rcx
0x180020aa3  jnz     short loc_180020AF3
0x180020aa5  test    ebx, ebx
0x180020aa7  jnz     short loc_180020B09
0x180020aa9  mov     eax, ebx
0x180020aab  add     rsp, 60h
0x180020aaf  pop     r14
0x180020ab1  pop     rdi
0x180020ab2  pop     rsi
0x180020ab3  pop     rbx
0x180020ab4  pop     rbp
0x180020ab5  retn
0x180020ab6  mov     eax, 80004003h
0x180020abb  jmp     short loc_180020AAB
0x180020abd  mov     eax, [rbp+dwCapabilities]
0x180020ac0  mov     rcx, rsi; pProxy
0x180020ac3  mov     r9, [rbp+pServerPrincName]; pServerPrincName
0x180020ac7  mov     r8d, [rbp+pAuthzSvc]; dwAuthzSvc
0x180020acb  mov     edx, [rbp+pwAuthnSvc]; dwAuthnSvc
0x180020ace  mov     dword ptr [rsp+60h+pCapabilites], eax; dwCapabilities
0x180020ad2  mov     rax, [rbp+var_8]
0x180020ad6  mov     [rsp+60h+pAuthInfo], rax; pAuthInfo
0x180020adb  mov     eax, [rbp+dwImpLevel]
0x180020ade  mov     dword ptr [rsp+60h+pImpLevel], eax; dwImpLevel
0x180020ae2  mov     eax, [rbp+dwAuthnLevel]
0x180020ae5  mov     dword ptr [rsp+60h+pAuthnLevel], eax; dwAuthnLevel
0x180020ae9  call    cs:__imp_CoSetProxyBlanket
0x180020aef  mov     ebx, eax
0x180020af1  jmp     short loc_180020A9C
0x180020af3  call    cs:__imp_CoTaskMemFree
0x180020af9  jmp     short loc_180020AA5
0x180020afb  cmp     eax, 80010117h
0x180020b00  jz      short loc_180020B3F
0x180020b02  cmp     eax, 80004002h
0x180020b07  jz      short loc_180020B3F
0x180020b09  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b10  lea     rax, WPP_GLOBAL_Control
0x180020b17  cmp     rcx, rax
0x180020b1a  jz      short loc_180020AA9
0x180020b1c  test    byte ptr [rcx+1Ch], 1
0x180020b20  jz      short loc_180020AA9
0x180020b22  mov     rcx, [rcx+10h]
0x180020b26  lea     r8, WPP_75c351f6869f3647f61a30e7f530184a_Traceguids
0x180020b2d  mov     edx, 11h
0x180020b32  mov     r9d, ebx
0x180020b35  call    WPP_SF_d
0x180020b3a  jmp     loc_180020AA9
0x180020b3f  mov     ebx, r14d
0x180020b42  jmp     loc_180020AA9
```
