# SampUpgradeDsrmHive(int)

- ea: `0x1800887a0`
- end: `0x1800888b2`
- name: `?SampUpgradeDsrmHive@@YAJH@Z`
- size: `274`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800799a8`

## callees

- `0x180027e24`
- `0x180088134`
- `0x1800887a0`
- `0x1800abd7c`
- `0x1800ad9e0`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180088876`
- `ntdll!RtlFreeSid` at `0x180088876`
- `ntdll!RtlEqualSid` at `0x180088803`
- `ntdll!RtlEqualSid` at `0x180088803`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x1800887ce`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x1800887e3`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x1800887ce`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x1800887e3`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180088853`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180088867`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180088853`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180088867`

## pseudocode

```c
__int64 __fastcall SampUpgradeDsrmHive(int a1)
{
  int v2; // ebx
  struct _UNICODE_STRING *v4; // [rsp+58h] [rbp+28h] BYREF
  PSID Sid; // [rsp+60h] [rbp+30h] BYREF
  __int64 v6; // [rsp+68h] [rbp+38h] BYREF

  v6 = 0;
  v4 = 0;
  Sid = 0;
  v2 = LsaIQueryInformationPolicyTrusted(3, &v6);
  if ( v2 >= 0 )
  {
    v2 = LsaIQueryInformationPolicyTrusted(14, &v4);
    if ( v2 >= 0 && (a1 || RtlEqualSid(*(PSID *)&v4[1].Length, *(PSID *)(v6 + 16))) )
    {
      v2 = SampGenerateRandomDomainSid(&Sid);
      if ( v2 >= 0 )
      {
        v2 = SampReplaceSidInSamHive(*(void **)&v4[1].Length, Sid);
        if ( v2 >= 0 )
          v2 = SampSetAccountDomainPolicy(v4, Sid, 1u);
      }
    }
  }
  if ( v6 )
    LsaIFree_LSAPR_POLICY_INFORMATION(3, v6);
  if ( v4 )
    LsaIFree_LSAPR_POLICY_INFORMATION(14, v4);
  if ( Sid )
    RtlFreeSid(Sid);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 209, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)v2, v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800887a0  push    rbp
0x1800887a2  push    rbx
0x1800887a3  push    rdi
0x1800887a4  mov     rbp, rsp
0x1800887a7  sub     rsp, 30h
0x1800887ab  mov     edi, ecx
0x1800887ad  mov     [rbp+arg_18], 0
0x1800887b5  mov     ecx, 3
0x1800887ba  mov     [rbp+arg_8], 0
0x1800887c2  lea     rdx, [rbp+arg_18]
0x1800887c6  mov     [rbp+Sid], 0
0x1800887ce  call    cs:__imp_LsaIQueryInformationPolicyTrusted
0x1800887d4  mov     ebx, eax
0x1800887d6  test    eax, eax
0x1800887d8  js      short loc_180088845
0x1800887da  lea     rdx, [rbp+arg_8]
0x1800887de  mov     ecx, 0Eh
0x1800887e3  call    cs:__imp_LsaIQueryInformationPolicyTrusted
0x1800887e9  mov     ebx, eax
0x1800887eb  test    eax, eax
0x1800887ed  js      short loc_180088845
0x1800887ef  test    edi, edi
0x1800887f1  jnz     short loc_18008880D
0x1800887f3  mov     rdx, [rbp+arg_18]
0x1800887f7  mov     rcx, [rbp+arg_8]
0x1800887fb  mov     rdx, [rdx+10h]; Sid2
0x1800887ff  mov     rcx, [rcx+10h]; Sid1
0x180088803  call    cs:__imp_RtlEqualSid
0x180088809  test    al, al
0x18008880b  jz      short loc_180088845
0x18008880d  lea     rcx, [rbp+Sid]; Sid
0x180088811  call    ?SampGenerateRandomDomainSid@@YAJPEAPEAX@Z; SampGenerateRandomDomainSid(void * *)
0x180088816  mov     ebx, eax
0x180088818  test    eax, eax
0x18008881a  js      short loc_180088845
0x18008881c  mov     rcx, [rbp+arg_8]
0x180088820  mov     rdx, [rbp+Sid]; void *
0x180088824  mov     rcx, [rcx+10h]; void *
0x180088828  call    ?SampReplaceSidInSamHive@@YAJPEAX0@Z; SampReplaceSidInSamHive(void *,void *)
0x18008882d  mov     ebx, eax
0x18008882f  test    eax, eax
0x180088831  js      short loc_180088845
0x180088833  mov     rdx, [rbp+Sid]; void *
0x180088837  mov     r8b, 1; unsigned __int8
0x18008883a  mov     rcx, [rbp+arg_8]; struct _UNICODE_STRING *
0x18008883e  call    ?SampSetAccountDomainPolicy@@YAJPEAU_UNICODE_STRING@@PEAXE@Z; SampSetAccountDomainPolicy(_UNICODE_STRING *,void *,uchar)
0x180088843  mov     ebx, eax
0x180088845  mov     rdx, [rbp+arg_18]
0x180088849  test    rdx, rdx
0x18008884c  jz      short loc_180088859
0x18008884e  mov     ecx, 3
0x180088853  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x180088859  mov     rdx, [rbp+arg_8]
0x18008885d  test    rdx, rdx
0x180088860  jz      short loc_18008886D
0x180088862  mov     ecx, 0Eh
0x180088867  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x18008886d  mov     rcx, [rbp+Sid]; Sid
0x180088871  test    rcx, rcx
0x180088874  jz      short loc_18008887C
0x180088876  call    cs:__imp_RtlFreeSid
0x18008887c  mov     rcx, cs:WPP_GLOBAL_Control
0x180088883  test    dword ptr [rcx+44h], 20000h
0x18008888a  jz      short loc_1800888A8
0x18008888c  mov     rcx, [rcx+38h]
0x180088890  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x180088897  mov     edx, 0D1h
0x18008889c  mov     [rsp+30h+var_10], ebx
0x1800888a0  mov     r9d, ebx
0x1800888a3  call    WPP_SF_Dd
0x1800888a8  mov     eax, ebx
0x1800888aa  add     rsp, 30h
0x1800888ae  pop     rdi
0x1800888af  pop     rbx
0x1800888b0  pop     rbp
0x1800888b1  retn
```
