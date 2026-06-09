# HrEnableStaticCloakingHelper(IUnknown *)

- ea: `0x18001aca8`
- end: `0x18001adca`
- name: `?HrEnableStaticCloakingHelper@@YAJPEAUIUnknown@@@Z`
- size: `290`
- prototype: `__int64 __fastcall(IUnknown *pProxy)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001aad0`

## callees

- `0x18001aca8`
- `0x180038ce4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001ad59`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001ad59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad6a`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x18001ad18`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x18001ad18`

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
0x18001aca8  mov     r11, rsp
0x18001acab  push    rbp
0x18001acac  push    rbx
0x18001acad  push    rdi
0x18001acae  mov     rbp, rsp
0x18001acb1  sub     rsp, 50h
0x18001acb5  mov     rdi, rcx
0x18001acb8  test    rcx, rcx
0x18001acbb  jz      loc_18001AD7E
0x18001acc1  lea     rax, [rbp+arg_0]
0x18001acc5  mov     [rbp+arg_10], 0
0x18001accc  mov     [r11-30h], rax
0x18001acd0  lea     r9, [rbp+pServerPrincName]; pServerPrincName
0x18001acd4  mov     qword ptr [r11-38h], 0
0x18001acdc  lea     rax, [rbp+arg_8]
0x18001ace0  mov     [r11-40h], rax
0x18001ace4  lea     r8, [rbp+pAuthzSvc]; pAuthzSvc
0x18001ace8  lea     rax, [rbp+arg_10]
0x18001acec  mov     [rbp+arg_8], 0
0x18001acf3  lea     rdx, [rbp+pwAuthnSvc]; pwAuthnSvc
0x18001acf7  mov     [r11-48h], rax
0x18001acfb  mov     [rbp+arg_0], 0
0x18001ad02  mov     [rbp+pwAuthnSvc], 0
0x18001ad09  mov     [rbp+pAuthzSvc], 0
0x18001ad10  mov     [rbp+pServerPrincName], 0
0x18001ad18  call    cs:__imp_CoQueryProxyBlanket
0x18001ad1e  mov     ebx, eax
0x18001ad20  test    eax, eax
0x18001ad22  js      short loc_18001AD85
0x18001ad24  mov     eax, [rbp+arg_0]
0x18001ad27  mov     rcx, rdi; pProxy
0x18001ad2a  mov     r9, [rbp+pServerPrincName]; pServerPrincName
0x18001ad2e  and     eax, 0FFFFFFBFh
0x18001ad31  mov     r8d, [rbp+pAuthzSvc]; dwAuthzSvc
0x18001ad35  or      eax, 20h
0x18001ad38  mov     edx, [rbp+pwAuthnSvc]; dwAuthnSvc
0x18001ad3b  mov     [rsp+50h+dwCapabilities], eax; dwCapabilities
0x18001ad3f  mov     [rbp+arg_0], eax
0x18001ad42  mov     eax, [rbp+arg_8]
0x18001ad45  mov     [rsp+50h+pAuthInfo], 0; pAuthInfo
0x18001ad4e  mov     [rsp+50h+dwImpLevel], eax; dwImpLevel
0x18001ad52  mov     eax, [rbp+arg_10]
0x18001ad55  mov     [rsp+50h+dwAuthnLevel], eax; dwAuthnLevel
0x18001ad59  call    cs:__imp_CoSetProxyBlanket
0x18001ad5f  mov     rcx, [rbp+pServerPrincName]; pv
0x18001ad63  mov     ebx, eax
0x18001ad65  test    rcx, rcx
0x18001ad68  jz      short loc_18001AD70
0x18001ad6a  call    cs:__imp_CoTaskMemFree
0x18001ad70  test    ebx, ebx
0x18001ad72  jnz     short loc_18001AD93
0x18001ad74  mov     eax, ebx
0x18001ad76  add     rsp, 50h
0x18001ad7a  pop     rdi
0x18001ad7b  pop     rbx
0x18001ad7c  pop     rbp
0x18001ad7d  retn
0x18001ad7e  mov     eax, 80004003h
0x18001ad83  jmp     short loc_18001AD76
0x18001ad85  cmp     eax, 80010117h
0x18001ad8a  jz      short loc_18001ADC6
0x18001ad8c  cmp     eax, 80004002h
0x18001ad91  jz      short loc_18001ADC6
0x18001ad93  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad9a  lea     rax, WPP_GLOBAL_Control
0x18001ada1  cmp     rcx, rax
0x18001ada4  jz      short loc_18001AD74
0x18001ada6  test    byte ptr [rcx+1Ch], 1
0x18001adaa  jz      short loc_18001AD74
0x18001adac  mov     rcx, [rcx+10h]
0x18001adb0  lea     r8, WPP_75c351f6869f3647f61a30e7f530184a_Traceguids
0x18001adb7  mov     edx, 0Fh
0x18001adbc  mov     r9d, ebx
0x18001adbf  call    WPP_SF_d
0x18001adc4  jmp     short loc_18001AD74
0x18001adc6  xor     ebx, ebx
0x18001adc8  jmp     short loc_18001AD74
```
