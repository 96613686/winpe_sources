# SampDsSetBuiltinDomainPolicy

- ea: `0x18005b380`
- end: `0x18005b4d4`
- name: `SampDsSetBuiltinDomainPolicy`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x18005b380`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18005b46c`
- `ntdll!RtlSubAuthoritySid` at `0x18005b46c`
- `ntdll!RtlInitializeSid` at `0x18005b458`
- `ntdll!RtlInitializeSid` at `0x18005b458`
- `ntdll!RtlAllocateHeap` at `0x18005b400`
- `ntdll!RtlAllocateHeap` at `0x18005b400`
- `ntdll!RtlLengthRequiredSid` at `0x18005b3e8`
- `ntdll!RtlLengthRequiredSid` at `0x18005b3e8`
- `ntdll!RtlInitUnicodeString` at `0x18005b3c2`
- `ntdll!RtlInitUnicodeString` at `0x18005b3dd`
- `ntdll!RtlInitUnicodeString` at `0x18005b3c2`
- `ntdll!RtlInitUnicodeString` at `0x18005b3dd`

## pseudocode

```c
__int64 __fastcall SampDsSetBuiltinDomainPolicy(unsigned int a1)
{
  __int64 v1; // rbx
  ULONG v2; // eax
  PVOID Heap; // rax
  struct _PSAMP_DEFINED_DOMAINS *v5; // rax
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+30h] [rbp-18h] BYREF

  v1 = 1360LL * a1;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  RtlInitUnicodeString((PUNICODE_STRING)((char *)SampDefinedDomains + v1 + 32), L"Builtin");
  RtlInitUnicodeString((PUNICODE_STRING)((char *)SampDefinedDomains + v1 + 16), L"Builtin");
  v2 = RtlLengthRequiredSid(1u);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  *(_QWORD *)((char *)SampDefinedDomains + v1 + 8) = Heap;
  if ( Heap )
  {
    RtlInitializeSid(Heap, &IdentifierAuthority, 1u);
    *RtlSubAuthoritySid(*(PSID *)((char *)SampDefinedDomains + v1 + 8), 0) = 32;
    v5 = SampDefinedDomains;
    *((_BYTE *)SampDefinedDomains + v1 + 1296) = 1;
    *((_BYTE *)v5 + v1 + 1298) = 0;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 13, WPP_4fe2a72f4b7d39ff2f3b29ec2f08b9d0_Traceguids, 0, 0);
    return 0;
  }
  else
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        12,
        WPP_4fe2a72f4b7d39ff2f3b29ec2f08b9d0_Traceguids,
        3221225626LL,
        -1073741670);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x18005b380  push    rbx
0x18005b382  sub     rsp, 40h
0x18005b386  mov     rax, cs:__security_cookie
0x18005b38d  xor     rax, rsp
0x18005b390  mov     [rsp+48h+var_10], rax
0x18005b395  mov     eax, ecx
0x18005b397  lea     rdx, aBuiltin_0; "Builtin"
0x18005b39e  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18005b3a5  imul    rbx, rax, 550h
0x18005b3ac  add     rcx, 20h ; ' '
0x18005b3b0  mov     dword ptr [rsp+48h+IdentifierAuthority.Value], 0
0x18005b3b8  add     rcx, rbx; DestinationString
0x18005b3bb  mov     word ptr [rsp+48h+IdentifierAuthority.Value+4], 500h
0x18005b3c2  call    cs:__imp_RtlInitUnicodeString
0x18005b3c8  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18005b3cf  lea     rdx, aBuiltin_0; "Builtin"
0x18005b3d6  add     rcx, 10h
0x18005b3da  add     rcx, rbx; DestinationString
0x18005b3dd  call    cs:__imp_RtlInitUnicodeString
0x18005b3e3  mov     ecx, 1; SubAuthorityCount
0x18005b3e8  call    cs:__imp_RtlLengthRequiredSid
0x18005b3ee  mov     rcx, gs:60h
0x18005b3f7  xor     edx, edx; Flags
0x18005b3f9  mov     r8d, eax; Size
0x18005b3fc  mov     rcx, [rcx+30h]; HeapHandle
0x18005b400  call    cs:__imp_RtlAllocateHeap
0x18005b406  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18005b40d  mov     [rbx+rcx+8], rax
0x18005b412  test    rax, rax
0x18005b415  jnz     short loc_18005B44D
0x18005b417  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b41e  mov     ebx, 0C000009Ah
0x18005b423  test    dword ptr [rcx+44h], 20000h
0x18005b42a  jz      short loc_18005B449
0x18005b42c  mov     rcx, [rcx+38h]
0x18005b430  lea     edx, [rax+0Ch]
0x18005b433  mov     r9d, 0C000009Ah
0x18005b439  mov     [rsp+48h+var_28], ebx
0x18005b43d  lea     r8, WPP_4fe2a72f4b7d39ff2f3b29ec2f08b9d0_Traceguids
0x18005b444  call    WPP_SF_Dd
0x18005b449  mov     eax, ebx
0x18005b44b  jmp     short loc_18005B4C1
0x18005b44d  mov     r8b, 1; SubAuthorityCount
0x18005b450  lea     rdx, [rsp+48h+IdentifierAuthority]; IdentifierAuthority
0x18005b455  mov     rcx, rax; Sid
0x18005b458  call    cs:__imp_RtlInitializeSid
0x18005b45e  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18005b465  xor     edx, edx; SubAuthority
0x18005b467  mov     rcx, [rbx+rcx+8]; Sid
0x18005b46c  call    cs:__imp_RtlSubAuthoritySid
0x18005b472  mov     dword ptr [rax], 20h ; ' '
0x18005b478  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18005b47f  mov     byte ptr [rbx+rax+510h], 1
0x18005b487  mov     byte ptr [rbx+rax+512h], 0
0x18005b48f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b496  test    dword ptr [rcx+44h], 20000h
0x18005b49d  jz      short loc_18005B4BF
0x18005b49f  mov     rcx, [rcx+38h]
0x18005b4a3  lea     r8, WPP_4fe2a72f4b7d39ff2f3b29ec2f08b9d0_Traceguids
0x18005b4aa  mov     edx, 0Dh
0x18005b4af  mov     [rsp+48h+var_28], 0
0x18005b4b7  xor     r9d, r9d
0x18005b4ba  call    WPP_SF_Dd
0x18005b4bf  xor     eax, eax
0x18005b4c1  mov     rcx, [rsp+48h+var_10]
0x18005b4c6  xor     rcx, rsp; StackCookie
0x18005b4c9  call    __security_check_cookie
0x18005b4ce  add     rsp, 40h
0x18005b4d2  pop     rbx
0x18005b4d3  retn
```
