# SampGetDomainPolicy(_POLICY_ACCOUNT_DOMAIN_INFO *)

- ea: `0x180041034`
- end: `0x1800412c3`
- name: `?SampGetDomainPolicy@@YAJPEAU_POLICY_ACCOUNT_DOMAIN_INFO@@@Z`
- size: `655`
- prototype: `__int64 __fastcall(struct _POLICY_ACCOUNT_DOMAIN_INFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18003f354`

## callees

- `0x18002cd80`
- `0x1800372ac`
- `0x180041034`
- `0x180041560`
- `0x1800af7a0`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x1800410e8`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004123a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800410e8`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004123a`
- `ntdll!RtlAppendUnicodeToString` at `0x1800410d2`
- `ntdll!RtlAppendUnicodeToString` at `0x180041224`
- `ntdll!RtlAppendUnicodeToString` at `0x1800410d2`
- `ntdll!RtlAppendUnicodeToString` at `0x180041224`
- `ntdll!RtlSubAuthorityCountSid` at `0x180041293`
- `ntdll!RtlSubAuthorityCountSid` at `0x180041293`
- `ntdll!RtlSubAuthoritySid` at `0x18004113b`
- `ntdll!RtlSubAuthoritySid` at `0x18004113b`
- `ntdll!RtlInitializeSid` at `0x18004112c`
- `ntdll!RtlInitializeSid` at `0x18004112c`
- `ntdll!RtlAllocateHeap` at `0x180041091`
- `ntdll!RtlAllocateHeap` at `0x18004110b`
- `ntdll!RtlAllocateHeap` at `0x1800411e3`
- `ntdll!RtlAllocateHeap` at `0x180041262`
- `ntdll!RtlAllocateHeap` at `0x180041091`
- `ntdll!RtlAllocateHeap` at `0x18004110b`
- `ntdll!RtlAllocateHeap` at `0x1800411e3`
- `ntdll!RtlAllocateHeap` at `0x180041262`
- `ntdll!RtlCopyUnicodeString` at `0x1800410c2`
- `ntdll!RtlCopyUnicodeString` at `0x180041214`
- `ntdll!RtlCopyUnicodeString` at `0x1800410c2`
- `ntdll!RtlCopyUnicodeString` at `0x180041214`
- `ntdll!RtlLengthRequiredSid` at `0x1800410f3`
- `ntdll!RtlLengthRequiredSid` at `0x1800410f3`
- `ntdll!RtlCopySid` at `0x180041280`
- `ntdll!RtlCopySid` at `0x180041280`
- `ntdll!RtlLengthSid` at `0x180041247`
- `ntdll!RtlLengthSid` at `0x180041247`
- `ntdll!RtlInitUnicodeString` at `0x180041076`
- `ntdll!RtlInitUnicodeString` at `0x1800411c8`
- `ntdll!RtlInitUnicodeString` at `0x180041076`
- `ntdll!RtlInitUnicodeString` at `0x1800411c8`

## pseudocode

```c
__int64 __fastcall SampGetDomainPolicy(struct _POLICY_ACCOUNT_DOMAIN_INFO *a1)
{
  ULONG v2; // eax
  PVOID Heap; // rax
  __int64 v4; // rcx
  __int64 result; // rax
  ULONG v6; // ebx
  PVOID v7; // rax
  PUCHAR v8; // rax
  __int64 v9; // rdx
  struct _POLICY_ACCOUNT_DOMAIN_INFO *v10; // [rsp+20h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+28h] [rbp-20h] BYREF

  v10 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  RtlInitUnicodeString(&stru_1800EF7E0, L"Builtin");
  Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x100u);
  if ( !Destination.Buffer )
    return 3221225495LL;
  *(_DWORD *)&Destination.Length = 0x1000000;
  RtlCopyUnicodeString(&Destination, &stru_1800EF810);
  dword_1800EF708 = RtlAppendUnicodeToString(&Destination, L"\\");
  RtlAppendUnicodeStringToString(&Destination, &stru_1800EF7E0);
  v2 = RtlLengthRequiredSid(1u);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  SampBuiltinDomainSid = Heap;
  if ( !Heap )
    return 3221225495LL;
  RtlInitializeSid(Heap, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(SampBuiltinDomainSid, 0) = 32;
  if ( a1 )
  {
    dword_1800EF708 = 0;
    goto LABEL_10;
  }
  LOBYTE(v4) = 1;
  result = SampGetAccountDomainInfo(v4, &v10);
  dword_1800EF708 = result;
  if ( (int)result >= 0 )
  {
    a1 = v10;
LABEL_10:
    SampAccountDomainSid = a1->DomainSid;
    RtlInitUnicodeString(&stru_1800EF7D0, L"Account");
    stru_1800EF7F0.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x200u);
    if ( stru_1800EF7F0.Buffer )
    {
      *(_DWORD *)&stru_1800EF7F0.Length = 0x2000000;
      RtlCopyUnicodeString(&stru_1800EF7F0, &stru_1800EF810);
      dword_1800EF708 = RtlAppendUnicodeToString(&stru_1800EF7F0, L"\\");
      RtlAppendUnicodeStringToString(&stru_1800EF7F0, &stru_1800EF7D0);
      v6 = RtlLengthSid(SampAccountDomainSid) + 4;
      v7 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      qword_1800EF7B0 = v7;
      if ( v7 )
      {
        dword_1800EF708 = RtlCopySid(v6, v7, SampAccountDomainSid);
        v8 = RtlSubAuthorityCountSid(qword_1800EF7B0);
        ++*v8;
        SetCurrentDomain(0, v9);
        return 0;
      }
    }
    return 3221225495LL;
  }
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 13, WPP_f50d46da04da33107d90bf406b0e9591_Traceguids, (unsigned int)result);
    return (unsigned int)dword_1800EF708;
  }
  return result;
}

```

## disassembly

```asm
0x180041034  mov     [rsp+arg_8], rbx
0x180041039  push    rdi
0x18004103a  sub     rsp, 40h
0x18004103e  mov     rax, cs:__security_cookie
0x180041045  xor     rax, rsp
0x180041048  mov     [rsp+48h+var_18], rax
0x18004104d  mov     rbx, rcx
0x180041050  mov     [rsp+48h+var_28], 0
0x180041059  lea     rcx, stru_1800EF7E0; DestinationString
0x180041060  mov     dword ptr [rsp+48h+IdentifierAuthority.Value], 0
0x180041068  lea     rdx, aBuiltin_0; "Builtin"
0x18004106f  mov     word ptr [rsp+48h+IdentifierAuthority.Value+4], 500h
0x180041076  call    cs:__imp_RtlInitUnicodeString
0x18004107c  mov     rcx, gs:60h
0x180041085  xor     edx, edx; Flags
0x180041087  mov     r8d, 100h; Size
0x18004108d  mov     rcx, [rcx+30h]; HeapHandle
0x180041091  call    cs:__imp_RtlAllocateHeap
0x180041097  mov     cs:Destination.Buffer, rax
0x18004109e  test    rax, rax
0x1800410a1  jz      loc_1800412A6
0x1800410a7  lea     rdi, Destination
0x1800410ae  mov     dword ptr cs:Destination.Length, 1000000h
0x1800410b8  mov     rcx, rdi; DestinationString
0x1800410bb  lea     rdx, stru_1800EF810; SourceString
0x1800410c2  call    cs:__imp_RtlCopyUnicodeString
0x1800410c8  lea     rdx, asc_1800CA5C4; "\\"
0x1800410cf  mov     rcx, rdi; Destination
0x1800410d2  call    cs:__imp_RtlAppendUnicodeToString
0x1800410d8  lea     rdx, stru_1800EF7E0; Source
0x1800410df  mov     rcx, rdi; Destination
0x1800410e2  mov     cs:dword_1800EF708, eax
0x1800410e8  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800410ee  mov     ecx, 1; SubAuthorityCount
0x1800410f3  call    cs:__imp_RtlLengthRequiredSid
0x1800410f9  mov     rcx, gs:60h
0x180041102  xor     edx, edx; Flags
0x180041104  mov     r8d, eax; Size
0x180041107  mov     rcx, [rcx+30h]; HeapHandle
0x18004110b  call    cs:__imp_RtlAllocateHeap
0x180041111  mov     cs:SampBuiltinDomainSid, rax
0x180041118  test    rax, rax
0x18004111b  jz      loc_1800412A6
0x180041121  mov     r8b, 1; SubAuthorityCount
0x180041124  lea     rdx, [rsp+48h+IdentifierAuthority]; IdentifierAuthority
0x180041129  mov     rcx, rax; Sid
0x18004112c  call    cs:__imp_RtlInitializeSid
0x180041132  mov     rcx, cs:SampBuiltinDomainSid; Sid
0x180041139  xor     edx, edx; SubAuthority
0x18004113b  call    cs:__imp_RtlSubAuthoritySid
0x180041141  mov     dword ptr [rax], 20h ; ' '
0x180041147  test    rbx, rbx
0x18004114a  jnz     short loc_1800411A5
0x18004114c  lea     rdx, [rsp+48h+var_28]
0x180041151  mov     cl, 1
0x180041153  call    SampGetAccountDomainInfo
0x180041158  mov     cs:dword_1800EF708, eax
0x18004115e  test    eax, eax
0x180041160  jns     short loc_18004119E
0x180041162  mov     rcx, cs:WPP_GLOBAL_Control
0x180041169  test    byte ptr [rcx+44h], 1
0x18004116d  jz      loc_1800412AB
0x180041173  cmp     byte ptr [rcx+41h], 2
0x180041177  jb      loc_1800412AB
0x18004117d  mov     rcx, [rcx+38h]
0x180041181  lea     edx, [rbx+0Dh]
0x180041184  mov     r9d, eax
0x180041187  lea     r8, WPP_f50d46da04da33107d90bf406b0e9591_Traceguids
0x18004118e  call    WPP_SF_d
0x180041193  mov     eax, cs:dword_1800EF708
0x180041199  jmp     loc_1800412AB
0x18004119e  mov     rbx, [rsp+48h+var_28]
0x1800411a3  jmp     short loc_1800411AF
0x1800411a5  mov     cs:dword_1800EF708, 0
0x1800411af  mov     rax, [rbx+10h]
0x1800411b3  lea     rdx, aAccount; "Account"
0x1800411ba  lea     rcx, stru_1800EF7D0; DestinationString
0x1800411c1  mov     cs:SampAccountDomainSid, rax
0x1800411c8  call    cs:__imp_RtlInitUnicodeString
0x1800411ce  mov     rcx, gs:60h
0x1800411d7  xor     edx, edx; Flags
0x1800411d9  mov     r8d, 200h; Size
0x1800411df  mov     rcx, [rcx+30h]; HeapHandle
0x1800411e3  call    cs:__imp_RtlAllocateHeap
0x1800411e9  mov     cs:stru_1800EF7F0.Buffer, rax
0x1800411f0  test    rax, rax
0x1800411f3  jz      loc_1800412A6
0x1800411f9  lea     rbx, stru_1800EF7F0
0x180041200  mov     dword ptr cs:stru_1800EF7F0.Length, 2000000h
0x18004120a  mov     rcx, rbx; DestinationString
0x18004120d  lea     rdx, stru_1800EF810; SourceString
0x180041214  call    cs:__imp_RtlCopyUnicodeString
0x18004121a  lea     rdx, asc_1800CA5C4; "\\"
0x180041221  mov     rcx, rbx; Destination
0x180041224  call    cs:__imp_RtlAppendUnicodeToString
0x18004122a  lea     rdx, stru_1800EF7D0; Source
0x180041231  mov     rcx, rbx; Destination
0x180041234  mov     cs:dword_1800EF708, eax
0x18004123a  call    cs:__imp_RtlAppendUnicodeStringToString
0x180041240  mov     rcx, cs:SampAccountDomainSid; Sid
0x180041247  call    cs:__imp_RtlLengthSid
0x18004124d  mov     rcx, gs:60h
0x180041256  xor     edx, edx; Flags
0x180041258  lea     ebx, [rax+4]
0x18004125b  mov     rcx, [rcx+30h]; HeapHandle
0x18004125f  mov     r8d, ebx; Size
0x180041262  call    cs:__imp_RtlAllocateHeap
0x180041268  mov     cs:qword_1800EF7B0, rax
0x18004126f  test    rax, rax
0x180041272  jz      short loc_1800412A6
0x180041274  mov     r8, cs:SampAccountDomainSid; SourceSid
0x18004127b  mov     rdx, rax; DestinationSid
0x18004127e  mov     ecx, ebx; DestinationSidLength
0x180041280  call    cs:__imp_RtlCopySid
0x180041286  mov     rcx, cs:qword_1800EF7B0; Sid
0x18004128d  mov     cs:dword_1800EF708, eax
0x180041293  call    cs:__imp_RtlSubAuthorityCountSid
0x180041299  xor     ecx, ecx
0x18004129b  inc     byte ptr [rax]
0x18004129d  call    ?SetCurrentDomain@@YAXW4_SAMP_DOMAIN_SELECTOR@@@Z; SetCurrentDomain(_SAMP_DOMAIN_SELECTOR)
0x1800412a2  xor     eax, eax
0x1800412a4  jmp     short loc_1800412AB
0x1800412a6  mov     eax, 0C0000017h
0x1800412ab  mov     rcx, [rsp+48h+var_18]
0x1800412b0  xor     rcx, rsp; StackCookie
0x1800412b3  call    __security_check_cookie
0x1800412b8  mov     rbx, [rsp+48h+arg_8]
0x1800412bd  add     rsp, 40h
0x1800412c1  pop     rdi
0x1800412c2  retn
```
