# SampDsGetDomainInfo(void * *,_UNICODE_STRING *,_UNICODE_STRING *,uchar *)

- ea: `0x18005ab30`
- end: `0x18005ad32`
- name: `?SampDsGetDomainInfo@@YAJPEAPEAXPEAU_UNICODE_STRING@@1PEAE@Z`
- size: `514`
- prototype: `__int64 __fastcall(void **, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005b4e0`

## callees

- `0x180012a28`
- `0x1800234e8`
- `0x180027e24`
- `0x1800372ac`
- `0x18005ab30`
- `0x18005ad5c`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18005acb9`
- `ntdll!RtlFreeHeap` at `0x18005acd6`
- `ntdll!RtlFreeHeap` at `0x18005acb9`
- `ntdll!RtlFreeHeap` at `0x18005acd6`
- `ntdll!RtlLengthSid` at `0x18005abc4`
- `ntdll!RtlLengthSid` at `0x18005abf1`
- `ntdll!RtlLengthSid` at `0x18005abc4`
- `ntdll!RtlLengthSid` at `0x18005abf1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005abd1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005abd1`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x18005ab74`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x18005ab74`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x18005ace5`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x18005ace5`
- `DNSAPI!DnsNameCompare_W` at `0x18005ac7e`
- `DNSAPI!DnsNameCompare_W` at `0x18005ac7e`
- `DNSAPI!DnsNameCompareEx_W` at `0x18005ac91`
- `DNSAPI!DnsNameCompareEx_W` at `0x18005ac91`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtGetDomainCrossRefSettings` at `0x18005ac22`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtGetDomainCrossRefSettings` at `0x18005ac22`

## pseudocode

```c
__int64 __fastcall SampDsGetDomainInfo(
        void **a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        unsigned __int8 *a4)
{
  WCHAR *v4; // rdi
  unsigned int v9; // eax
  int DomainCrossRefSettings; // ebx
  void *v11; // rcx
  ULONG v12; // eax
  HLOCAL v13; // rax
  ULONG v14; // eax
  int v15; // eax
  int NullTerminateString; // eax
  WCHAR *v17; // rsi
  char IsEnabled; // al
  PCWSTR pName1[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v21; // [rsp+70h] [rbp+30h] BYREF
  PCWSTR pName2; // [rsp+88h] [rbp+48h] BYREF

  v4 = 0;
  pName1[0] = 0;
  *a1 = 0;
  pName2 = 0;
  v21 = 0;
  *a4 = 0;
  v9 = LsaIQueryInformationPolicyTrusted(12, &v21);
  DomainCrossRefSettings = v9;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 5u )
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 14, WPP_4fe2a72f4b7d39ff2f3b29ec2f08b9d0_Traceguids, v9);
  if ( DomainCrossRefSettings >= 0 )
  {
    v11 = *(void **)(v21 + 64);
    if ( !v11 )
    {
      DomainCrossRefSettings = -1073741704;
      goto LABEL_25;
    }
    v12 = RtlLengthSid(v11);
    v13 = LocalAlloc(0x40u, v12);
    *a1 = v13;
    if ( !v13 )
    {
      DomainCrossRefSettings = -1073741801;
      goto LABEL_25;
    }
    v14 = RtlLengthSid(*(PSID *)(v21 + 64));
    memcpy_0(*a1, *(const void **)(v21 + 64), v14);
    v15 = SampShouldCallNtdsaApiSet();
    DomainCrossRefSettings = v15;
    if ( v15 == -1073741637 )
      goto LABEL_13;
    if ( v15 >= 0 )
      DomainCrossRefSettings = NtdsaExtGetDomainCrossRefSettings(a2, a3);
    if ( DomainCrossRefSettings >= 0 )
    {
LABEL_13:
      NullTerminateString = SampMakeNullTerminateString(v21 + 16, pName1);
      v17 = (WCHAR *)pName1[0];
      DomainCrossRefSettings = NullTerminateString;
      if ( NullTerminateString >= 0 )
      {
        DomainCrossRefSettings = SampMakeNullTerminateString(v21 + 32, &pName2);
        if ( DomainCrossRefSettings < 0 )
        {
          v4 = (WCHAR *)pName2;
          goto LABEL_21;
        }
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_5977_1413>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_5977_1413>::GetImpl'::`2'::impl);
        v4 = (WCHAR *)pName2;
        if ( !IsEnabled )
        {
          if ( (unsigned int)DnsNameCompareEx_W(v17, pName2, 0) != 1 )
            goto LABEL_21;
          goto LABEL_17;
        }
        if ( DnsNameCompare_W(v17, pName2) )
LABEL_17:
          *a4 = 1;
      }
LABEL_21:
      if ( v17 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
      if ( v4 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    }
  }
LABEL_25:
  LsaIFree_LSAPR_POLICY_INFORMATION(12, v21);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      15,
      WPP_4fe2a72f4b7d39ff2f3b29ec2f08b9d0_Traceguids,
      (unsigned int)DomainCrossRefSettings,
      DomainCrossRefSettings);
  return (unsigned int)DomainCrossRefSettings;
}

```

## disassembly

```asm
0x18005ab30  mov     [rsp-28h+arg_8], rbx
0x18005ab35  mov     [rsp-28h+arg_10], rsi
0x18005ab3a  push    rbp
0x18005ab3b  push    rdi
0x18005ab3c  push    r12
0x18005ab3e  push    r14
0x18005ab40  push    r15
0x18005ab42  mov     rbp, rsp
0x18005ab45  sub     rsp, 40h
0x18005ab49  xor     edi, edi
0x18005ab4b  mov     [rbp+pName1], 0
0x18005ab53  mov     r12, rdx
0x18005ab56  mov     [rcx], rdi
0x18005ab59  mov     rsi, rcx
0x18005ab5c  mov     [rbp+pName2], rdi
0x18005ab60  lea     rdx, [rbp+arg_0]
0x18005ab64  mov     [rbp+arg_0], rdi
0x18005ab68  lea     ecx, [rdi+0Ch]
0x18005ab6b  mov     [r9], dil
0x18005ab6e  mov     r14, r9
0x18005ab71  mov     r15, r8
0x18005ab74  call    cs:__imp_LsaIQueryInformationPolicyTrusted
0x18005ab7a  mov     ebx, eax
0x18005ab7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ab83  test    byte ptr [rcx+44h], 20h
0x18005ab87  jz      short loc_18005ABA5
0x18005ab89  cmp     byte ptr [rcx+41h], 5
0x18005ab8d  jb      short loc_18005ABA5
0x18005ab8f  mov     rcx, [rcx+38h]
0x18005ab93  lea     edx, [rdi+0Eh]
0x18005ab96  mov     r9d, eax
0x18005ab99  lea     r8, WPP_4fe2a72f4b7d39ff2f3b29ec2f08b9d0_Traceguids
0x18005aba0  call    WPP_SF_d
0x18005aba5  test    ebx, ebx
0x18005aba7  js      loc_18005ACDC
0x18005abad  mov     rax, [rbp+arg_0]
0x18005abb1  mov     rcx, [rax+40h]; Sid
0x18005abb5  test    rcx, rcx
0x18005abb8  jnz     short loc_18005ABC4
0x18005abba  mov     ebx, 0C0000078h
0x18005abbf  jmp     loc_18005ACDC
0x18005abc4  call    cs:__imp_RtlLengthSid
0x18005abca  mov     edx, eax; uBytes
0x18005abcc  mov     ecx, 40h ; '@'; uFlags
0x18005abd1  call    cs:__imp_LocalAlloc
0x18005abd7  mov     [rsi], rax
0x18005abda  test    rax, rax
0x18005abdd  jnz     short loc_18005ABE9
0x18005abdf  mov     ebx, 0C0000017h
0x18005abe4  jmp     loc_18005ACDC
0x18005abe9  mov     rcx, [rbp+arg_0]
0x18005abed  mov     rcx, [rcx+40h]; Sid
0x18005abf1  call    cs:__imp_RtlLengthSid
0x18005abf7  mov     rdx, [rbp+arg_0]
0x18005abfb  mov     rcx, [rsi]; void *
0x18005abfe  mov     r8d, eax; Size
0x18005ac01  mov     rdx, [rdx+40h]; Src
0x18005ac05  call    memcpy_0
0x18005ac0a  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18005ac0f  mov     ebx, eax
0x18005ac11  cmp     eax, 0C00000BBh
0x18005ac16  jz      short loc_18005AC32
0x18005ac18  test    eax, eax
0x18005ac1a  js      short loc_18005AC2A
0x18005ac1c  mov     rdx, r15
0x18005ac1f  mov     rcx, r12
0x18005ac22  call    cs:__imp_NtdsaExtGetDomainCrossRefSettings
0x18005ac28  mov     ebx, eax
0x18005ac2a  test    ebx, ebx
0x18005ac2c  js      loc_18005ACDC
0x18005ac32  mov     rcx, [rbp+arg_0]
0x18005ac36  lea     rdx, [rbp+pName1]
0x18005ac3a  add     rcx, 10h
0x18005ac3e  call    SampMakeNullTerminateString
0x18005ac43  mov     rsi, [rbp+pName1]
0x18005ac47  mov     ebx, eax
0x18005ac49  test    eax, eax
0x18005ac4b  js      short loc_18005ACA2
0x18005ac4d  mov     rcx, [rbp+arg_0]
0x18005ac51  lea     rdx, [rbp+pName2]
0x18005ac55  add     rcx, 20h ; ' '
0x18005ac59  call    SampMakeNullTerminateString
0x18005ac5e  mov     ebx, eax
0x18005ac60  test    eax, eax
0x18005ac62  js      short loc_18005AC9E
0x18005ac64  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_5977_1413@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_5977_1413@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_5977_1413> `wil::Feature<__WilFeatureTraits_Feature_5977_1413>::GetImpl(void)'::`2'::impl
0x18005ac6b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_5977_1413@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_5977_1413>::__private_IsEnabled(void)
0x18005ac70  mov     rdi, [rbp+pName2]
0x18005ac74  mov     rcx, rsi; pName1
0x18005ac77  mov     rdx, rdi; pName2
0x18005ac7a  test    al, al
0x18005ac7c  jz      short loc_18005AC8E
0x18005ac7e  call    cs:__imp_DnsNameCompare_W
0x18005ac84  test    eax, eax
0x18005ac86  jz      short loc_18005ACA2
0x18005ac88  mov     byte ptr [r14], 1
0x18005ac8c  jmp     short loc_18005ACA2
0x18005ac8e  xor     r8d, r8d
0x18005ac91  call    cs:__imp_DnsNameCompareEx_W
0x18005ac97  cmp     eax, 1
0x18005ac9a  jnz     short loc_18005ACA2
0x18005ac9c  jmp     short loc_18005AC88
0x18005ac9e  mov     rdi, [rbp+pName2]
0x18005aca2  test    rsi, rsi
0x18005aca5  jz      short loc_18005ACBF
0x18005aca7  mov     rcx, gs:60h
0x18005acb0  mov     r8, rsi; P
0x18005acb3  xor     edx, edx; Flags
0x18005acb5  mov     rcx, [rcx+30h]; HeapHandle
0x18005acb9  call    cs:__imp_RtlFreeHeap
0x18005acbf  test    rdi, rdi
0x18005acc2  jz      short loc_18005ACDC
0x18005acc4  mov     rcx, gs:60h
0x18005accd  mov     r8, rdi; P
0x18005acd0  xor     edx, edx; Flags
0x18005acd2  mov     rcx, [rcx+30h]; HeapHandle
0x18005acd6  call    cs:__imp_RtlFreeHeap
0x18005acdc  mov     rdx, [rbp+arg_0]
0x18005ace0  mov     ecx, 0Ch
0x18005ace5  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x18005aceb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005acf2  test    dword ptr [rcx+44h], 20000h
0x18005acf9  jz      short loc_18005AD17
0x18005acfb  mov     rcx, [rcx+38h]
0x18005acff  lea     r8, WPP_4fe2a72f4b7d39ff2f3b29ec2f08b9d0_Traceguids
0x18005ad06  mov     edx, 0Fh
0x18005ad0b  mov     [rsp+40h+var_20], ebx
0x18005ad0f  mov     r9d, ebx
0x18005ad12  call    WPP_SF_Dd
0x18005ad17  lea     r11, [rsp+40h+var_s0]
0x18005ad1c  mov     eax, ebx
0x18005ad1e  mov     rbx, [r11+38h]
0x18005ad22  mov     rsi, [r11+40h]
0x18005ad26  mov     rsp, r11
0x18005ad29  pop     r15
0x18005ad2b  pop     r14
0x18005ad2d  pop     r12
0x18005ad2f  pop     rdi
0x18005ad30  pop     rbp
0x18005ad31  retn
```
