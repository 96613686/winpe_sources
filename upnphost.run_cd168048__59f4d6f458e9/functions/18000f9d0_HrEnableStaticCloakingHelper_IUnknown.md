# HrEnableStaticCloakingHelper(IUnknown *)

- ea: `0x18000f9d0`
- end: `0x18000fb05`
- name: `?HrEnableStaticCloakingHelper@@YAJPEAUIUnknown@@@Z`
- size: `309`
- prototype: `__int64 __fastcall(IUnknown *pProxy)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000f7e0`

## callees

- `0x18000f9d0`
- `0x18003b1cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000fa87`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000fa87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fa9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fa9e`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x18000fa40`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x18000fa40`

## pseudocode

```c
__int64 __fastcall HrEnableStaticCloakingHelper(IUnknown *pProxy)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  DWORD pwAuthnSvc; // [rsp+40h] [rbp-10h] BYREF
  LPOLESTR pServerPrincName; // [rsp+48h] [rbp-8h] BYREF
  DWORD dwCapabilities; // [rsp+70h] [rbp+20h] BYREF
  DWORD dwImpLevel; // [rsp+78h] [rbp+28h] BYREF
  DWORD dwAuthnLevel; // [rsp+80h] [rbp+30h] BYREF
  DWORD pAuthzSvc; // [rsp+88h] [rbp+38h] BYREF

  if ( pProxy )
  {
    dwAuthnLevel = 0;
    dwImpLevel = 0;
    dwCapabilities = 0;
    pwAuthnSvc = 0;
    pAuthzSvc = 0;
    pServerPrincName = 0;
    v2 = CoQueryProxyBlanket(
           pProxy,
           &pwAuthnSvc,
           &pAuthzSvc,
           &pServerPrincName,
           &dwAuthnLevel,
           &dwImpLevel,
           0,
           &dwCapabilities);
    v3 = v2;
    if ( v2 < 0 )
    {
      if ( v2 == -2147417833 || v2 == -2147467262 )
        return 0;
    }
    else
    {
      dwCapabilities = dwCapabilities & 0xFFFFFF9F | 0x20;
      v3 = CoSetProxyBlanket(
             pProxy,
             pwAuthnSvc,
             pAuthzSvc,
             pServerPrincName,
             dwAuthnLevel,
             dwImpLevel,
             0,
             dwCapabilities);
      if ( pServerPrincName )
        CoTaskMemFree(pServerPrincName);
      if ( !v3 )
        return v3;
    }
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_75c351f6869f3647f61a30e7f530184a_Traceguids, v3);
    return v3;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000f9d0  mov     r11, rsp
0x18000f9d3  push    rbp
0x18000f9d4  push    rbx
0x18000f9d5  push    rdi
0x18000f9d6  mov     rbp, rsp
0x18000f9d9  sub     rsp, 50h
0x18000f9dd  mov     rdi, rcx
0x18000f9e0  test    rcx, rcx
0x18000f9e3  jz      loc_18000FAB9
0x18000f9e9  lea     rax, [rbp+arg_0]
0x18000f9ed  mov     [rbp+arg_10], 0
0x18000f9f4  mov     [r11-30h], rax
0x18000f9f8  lea     r9, [rbp+pServerPrincName]; pServerPrincName
0x18000f9fc  mov     qword ptr [r11-38h], 0
0x18000fa04  lea     rax, [rbp+arg_8]
0x18000fa08  mov     [r11-40h], rax
0x18000fa0c  lea     r8, [rbp+pAuthzSvc]; pAuthzSvc
0x18000fa10  lea     rax, [rbp+arg_10]
0x18000fa14  mov     [rbp+arg_8], 0
0x18000fa1b  lea     rdx, [rbp+pwAuthnSvc]; pwAuthnSvc
0x18000fa1f  mov     [r11-48h], rax
0x18000fa23  mov     [rbp+arg_0], 0
0x18000fa2a  mov     [rbp+pwAuthnSvc], 0
0x18000fa31  mov     [rbp+pAuthzSvc], 0
0x18000fa38  mov     [rbp+pServerPrincName], 0
0x18000fa40  call    cs:__imp_CoQueryProxyBlanket
0x18000fa47  nop     dword ptr [rax+rax+00h]
0x18000fa4c  mov     ebx, eax
0x18000fa4e  test    eax, eax
0x18000fa50  js      short loc_18000FAC0
0x18000fa52  mov     eax, [rbp+arg_0]
0x18000fa55  mov     rcx, rdi; pProxy
0x18000fa58  mov     r9, [rbp+pServerPrincName]; pServerPrincName
0x18000fa5c  and     eax, 0FFFFFFBFh
0x18000fa5f  mov     r8d, [rbp+pAuthzSvc]; dwAuthzSvc
0x18000fa63  or      eax, 20h
0x18000fa66  mov     edx, [rbp+pwAuthnSvc]; dwAuthnSvc
0x18000fa69  mov     [rsp+50h+dwCapabilities], eax; dwCapabilities
0x18000fa6d  mov     [rbp+arg_0], eax
0x18000fa70  mov     eax, [rbp+arg_8]
0x18000fa73  mov     [rsp+50h+pAuthInfo], 0; pAuthInfo
0x18000fa7c  mov     [rsp+50h+dwImpLevel], eax; dwImpLevel
0x18000fa80  mov     eax, [rbp+arg_10]
0x18000fa83  mov     [rsp+50h+dwAuthnLevel], eax; dwAuthnLevel
0x18000fa87  call    cs:__imp_CoSetProxyBlanket
0x18000fa8e  nop     dword ptr [rax+rax+00h]
0x18000fa93  mov     rcx, [rbp+pServerPrincName]; pv
0x18000fa97  mov     ebx, eax
0x18000fa99  test    rcx, rcx
0x18000fa9c  jz      short loc_18000FAAA
0x18000fa9e  call    cs:__imp_CoTaskMemFree
0x18000faa5  nop     dword ptr [rax+rax+00h]
0x18000faaa  test    ebx, ebx
0x18000faac  jnz     short loc_18000FACE
0x18000faae  mov     eax, ebx
0x18000fab0  add     rsp, 50h
0x18000fab4  pop     rdi
0x18000fab5  pop     rbx
0x18000fab6  pop     rbp
0x18000fab7  retn
0x18000fab9  mov     eax, 80004003h
0x18000fabe  jmp     short loc_18000FAB0
0x18000fac0  cmp     eax, 80010117h
0x18000fac5  jz      short loc_18000FB01
0x18000fac7  cmp     eax, 80004002h
0x18000facc  jz      short loc_18000FB01
0x18000face  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fad5  lea     rax, WPP_GLOBAL_Control
0x18000fadc  cmp     rcx, rax
0x18000fadf  jz      short loc_18000FAAE
0x18000fae1  test    byte ptr [rcx+1Ch], 1
0x18000fae5  jz      short loc_18000FAAE
0x18000fae7  mov     rcx, [rcx+10h]
0x18000faeb  lea     r8, WPP_75c351f6869f3647f61a30e7f530184a_Traceguids
0x18000faf2  mov     edx, 0Fh
0x18000faf7  mov     r9d, ebx
0x18000fafa  call    WPP_SF_d
0x18000faff  jmp     short loc_18000FAAE
0x18000fb01  xor     ebx, ebx
0x18000fb03  jmp     short loc_18000FAAE
```
