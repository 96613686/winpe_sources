# SampSetDomainPolicy(void)

- ea: `0x18005508c`
- end: `0x180055399`
- name: `?SampSetDomainPolicy@@YAJXZ`
- size: `781`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180053844`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x18002d720`
- `0x18005508c`
- `0x1800af7a0`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18005517b`
- `ntdll!RtlSubAuthoritySid` at `0x18005517b`
- `ntdll!RtlInitializeSid` at `0x180055168`
- `ntdll!RtlInitializeSid` at `0x180055168`
- `ntdll!RtlAllocateHeap` at `0x18005511e`
- `ntdll!RtlAllocateHeap` at `0x1800551d7`
- `ntdll!RtlAllocateHeap` at `0x180055231`
- `ntdll!RtlAllocateHeap` at `0x1800552d6`
- `ntdll!RtlAllocateHeap` at `0x18005511e`
- `ntdll!RtlAllocateHeap` at `0x1800551d7`
- `ntdll!RtlAllocateHeap` at `0x180055231`
- `ntdll!RtlAllocateHeap` at `0x1800552d6`
- `ntdll!RtlLengthRequiredSid` at `0x180055106`
- `ntdll!RtlLengthRequiredSid` at `0x180055106`
- `ntdll!RtlLengthSid` at `0x1800551bd`
- `ntdll!RtlLengthSid` at `0x1800551bd`
- `ntdll!RtlInitUnicodeString` at `0x1800550df`
- `ntdll!RtlInitUnicodeString` at `0x1800550f7`
- `ntdll!RtlInitUnicodeString` at `0x18005528e`
- `ntdll!RtlInitUnicodeString` at `0x1800550df`
- `ntdll!RtlInitUnicodeString` at `0x1800550f7`
- `ntdll!RtlInitUnicodeString` at `0x18005528e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800552a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800552a3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180055346`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180055346`

## pseudocode

```c
__int64 SampSetDomainPolicy(void)
{
  ULONG v0; // eax
  PVOID Heap; // rax
  PUNICODE_STRING v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // r9
  PULONG v6; // rax
  __int64 v7; // rcx
  int AccountDomainInfo; // eax
  unsigned __int16 *v9; // rsi
  SIZE_T v10; // rdi
  PVOID v11; // rax
  struct _PSAMP_DEFINED_DOMAINS *v12; // r14
  unsigned int v13; // r14d
  PVOID v14; // rax
  struct _UNICODE_STRING *v15; // rdi
  DWORD v16; // ecx
  PVOID v17; // rax
  struct _PSAMP_DEFINED_DOMAINS *v18; // rdi
  DWORD nSize[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  *(_QWORD *)nSize = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  RtlInitUnicodeString((PUNICODE_STRING)SampDefinedDomains + 2, L"Builtin");
  RtlInitUnicodeString((PUNICODE_STRING)SampDefinedDomains + 1, L"Builtin");
  v0 = RtlLengthRequiredSid(1u);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v0);
  *((_QWORD *)SampDefinedDomains + 1) = Heap;
  if ( !Heap )
  {
    v2 = WPP_GLOBAL_Control;
    v3 = -1073741670;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v4 = 149;
      v5 = 3221225626LL;
LABEL_19:
      WPP_SF_Dd(v2[3].Buffer, v4, &WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids, v5, v3);
      return v3;
    }
    return v3;
  }
  RtlInitializeSid(Heap, &IdentifierAuthority, 1u);
  v6 = RtlSubAuthoritySid(*((PSID *)SampDefinedDomains + 1), 0);
  LOBYTE(v7) = 1;
  *v6 = 32;
  *((_BYTE *)SampDefinedDomains + 1296) = 1;
  AccountDomainInfo = SampGetAccountDomainInfo(v7, nSize);
  v9 = *(unsigned __int16 **)nSize;
  v3 = AccountDomainInfo;
  if ( AccountDomainInfo < 0 )
  {
    v18 = SampDefinedDomains;
  }
  else
  {
    nSize[0] = 257;
    v10 = RtlLengthSid(*((PSID *)v9 + 2));
    v11 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
    v12 = SampDefinedDomains;
    *((_QWORD *)SampDefinedDomains + 171) = v11;
    if ( !v11 )
      goto LABEL_6;
    memset_0(v11, 0, v10);
    memcpy_0(*((void **)v12 + 171), *((const void **)v9 + 2), v10);
    v13 = v9[1];
    v14 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v9[1]);
    v15 = (struct _UNICODE_STRING *)SampDefinedDomains;
    *((_QWORD *)SampDefinedDomains + 173) = v14;
    if ( !v14 )
      goto LABEL_6;
    memset_0(v14, 0, v13);
    memcpy_0(v15[86].Buffer, *((const void **)v9 + 1), *v9);
    v15[86].Length = *v9;
    v15[86].MaximumLength = v9[1];
    RtlInitUnicodeString(v15 + 87, L"Account");
    if ( GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, nSize) )
    {
      v16 = nSize[0];
    }
    else
    {
      v16 = 0;
      Buffer[0] = 0;
    }
    nSize[0] = v16 + 1;
    v17 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * (v16 + 1));
    v18 = SampDefinedDomains;
    *((_QWORD *)SampDefinedDomains + 336) = v17;
    if ( !v17 )
    {
LABEL_6:
      v3 = -1073741670;
      goto LABEL_15;
    }
    memcpy_0(v17, Buffer, 2LL * nSize[0]);
    *((_WORD *)v18 + 1340) = 2 * (LOWORD(nSize[0]) - 1);
    *((_WORD *)v18 + 1341) = 2 * (LOWORD(nSize[0]) - 1);
  }
  *((_BYTE *)v18 + 2656) = 0;
LABEL_15:
  if ( v9 )
    LsaFreeMemory(v9);
  v2 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v4 = 150;
    v5 = v3;
    goto LABEL_19;
  }
  return v3;
}

```

## disassembly

```asm
0x18005508c  push    rbp
0x18005508e  push    rbx
0x18005508f  push    rsi
0x180055090  push    rdi
0x180055091  push    r12
0x180055093  push    r14
0x180055095  lea     rbp, [rsp-168h]
0x18005509d  sub     rsp, 268h
0x1800550a4  mov     rax, cs:__security_cookie
0x1800550ab  xor     rax, rsp
0x1800550ae  mov     [rbp+190h+var_40], rax
0x1800550b5  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800550bc  lea     rdx, aBuiltin_0; "Builtin"
0x1800550c3  add     rcx, 20h ; ' '; DestinationString
0x1800550c7  mov     qword ptr [rsp+290h+nSize], 0
0x1800550d0  mov     dword ptr [rsp+290h+IdentifierAuthority.Value], 0
0x1800550d8  mov     word ptr [rsp+290h+IdentifierAuthority.Value+4], 500h
0x1800550df  call    cs:__imp_RtlInitUnicodeString
0x1800550e5  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800550ec  lea     rdx, aBuiltin_0; "Builtin"
0x1800550f3  add     rcx, 10h; DestinationString
0x1800550f7  call    cs:__imp_RtlInitUnicodeString
0x1800550fd  mov     r12d, 1
0x180055103  mov     ecx, r12d; SubAuthorityCount
0x180055106  call    cs:__imp_RtlLengthRequiredSid
0x18005510c  mov     rcx, gs:60h
0x180055115  xor     edx, edx; Flags
0x180055117  mov     r8d, eax; Size
0x18005511a  mov     rcx, [rcx+30h]; HeapHandle
0x18005511e  call    cs:__imp_RtlAllocateHeap
0x180055124  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18005512b  mov     [rcx+8], rax
0x18005512f  test    rax, rax
0x180055132  jnz     short loc_18005515D
0x180055134  mov     rcx, cs:WPP_GLOBAL_Control
0x18005513b  mov     ebx, 0C000009Ah
0x180055140  test    dword ptr [rcx+44h], 20000h
0x180055147  jz      loc_180055378
0x18005514d  mov     edx, 95h
0x180055152  mov     r9d, 0C000009Ah
0x180055158  jmp     loc_180055364
0x18005515d  mov     r8b, r12b; SubAuthorityCount
0x180055160  lea     rdx, [rsp+290h+IdentifierAuthority]; IdentifierAuthority
0x180055165  mov     rcx, rax; Sid
0x180055168  call    cs:__imp_RtlInitializeSid
0x18005516e  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180055175  xor     edx, edx; SubAuthority
0x180055177  mov     rcx, [rcx+8]; Sid
0x18005517b  call    cs:__imp_RtlSubAuthoritySid
0x180055181  lea     rdx, [rsp+290h+nSize]
0x180055186  mov     cl, r12b
0x180055189  mov     dword ptr [rax], 20h ; ' '
0x18005518f  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180055196  mov     [rax+510h], r12b
0x18005519d  call    SampGetAccountDomainInfo
0x1800551a2  mov     rsi, qword ptr [rsp+290h+nSize]
0x1800551a7  mov     ebx, eax
0x1800551a9  test    eax, eax
0x1800551ab  js      loc_180055330
0x1800551b1  mov     [rsp+290h+nSize], 101h
0x1800551b9  mov     rcx, [rsi+10h]; Sid
0x1800551bd  call    cs:__imp_RtlLengthSid
0x1800551c3  mov     rcx, gs:60h
0x1800551cc  xor     edx, edx; Flags
0x1800551ce  mov     r8d, eax; Size
0x1800551d1  mov     edi, eax
0x1800551d3  mov     rcx, [rcx+30h]; HeapHandle
0x1800551d7  call    cs:__imp_RtlAllocateHeap
0x1800551dd  mov     r14, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800551e4  mov     [r14+558h], rax
0x1800551eb  test    rax, rax
0x1800551ee  jnz     short loc_1800551FA
0x1800551f0  mov     ebx, 0C000009Ah
0x1800551f5  jmp     loc_18005533E
0x1800551fa  mov     r8, rdi; Size
0x1800551fd  xor     edx, edx; Val
0x1800551ff  mov     rcx, rax; void *
0x180055202  call    memset_0
0x180055207  mov     rdx, [rsi+10h]; Src
0x18005520b  mov     r8, rdi; Size
0x18005520e  mov     rcx, [r14+558h]; void *
0x180055215  call    memcpy_0
0x18005521a  mov     rcx, gs:60h
0x180055223  xor     edx, edx; Flags
0x180055225  movzx   r14d, word ptr [rsi+2]
0x18005522a  mov     r8d, r14d; Size
0x18005522d  mov     rcx, [rcx+30h]; HeapHandle
0x180055231  call    cs:__imp_RtlAllocateHeap
0x180055237  mov     rdi, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18005523e  mov     [rdi+568h], rax
0x180055245  test    rax, rax
0x180055248  jz      short loc_1800551F0
0x18005524a  mov     r8d, r14d; Size
0x18005524d  xor     edx, edx; Val
0x18005524f  mov     rcx, rax; void *
0x180055252  call    memset_0
0x180055257  movzx   r8d, word ptr [rsi]; Size
0x18005525b  mov     rdx, [rsi+8]; Src
0x18005525f  mov     rcx, [rdi+568h]; void *
0x180055266  call    memcpy_0
0x18005526b  movzx   eax, word ptr [rsi]
0x18005526e  lea     rcx, [rdi+570h]; DestinationString
0x180055275  mov     [rdi+560h], ax
0x18005527c  lea     rdx, aAccount; "Account"
0x180055283  movzx   eax, word ptr [rsi+2]
0x180055287  mov     [rdi+562h], ax
0x18005528e  call    cs:__imp_RtlInitUnicodeString
0x180055294  lea     r8, [rsp+290h+nSize]; nSize
0x180055299  mov     ecx, 3; NameType
0x18005529e  lea     rdx, [rsp+290h+Buffer]; lpBuffer
0x1800552a3  call    cs:__imp_GetComputerNameExW
0x1800552a9  test    eax, eax
0x1800552ab  jnz     short loc_1800552B6
0x1800552ad  xor     ecx, ecx
0x1800552af  mov     [rsp+290h+Buffer], ax
0x1800552b4  jmp     short loc_1800552BA
0x1800552b6  mov     ecx, [rsp+290h+nSize]
0x1800552ba  add     ecx, r12d
0x1800552bd  xor     edx, edx; Flags
0x1800552bf  mov     r8d, ecx
0x1800552c2  mov     [rsp+290h+nSize], ecx
0x1800552c6  add     r8, r8; Size
0x1800552c9  mov     rcx, gs:60h
0x1800552d2  mov     rcx, [rcx+30h]; HeapHandle
0x1800552d6  call    cs:__imp_RtlAllocateHeap
0x1800552dc  mov     rdi, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800552e3  mov     [rdi+0A80h], rax
0x1800552ea  test    rax, rax
0x1800552ed  jz      loc_1800551F0
0x1800552f3  mov     r8d, [rsp+290h+nSize]
0x1800552f8  lea     rdx, [rsp+290h+Buffer]; Src
0x1800552fd  add     r8, r8; Size
0x180055300  mov     rcx, rax; void *
0x180055303  call    memcpy_0
0x180055308  movzx   eax, word ptr [rsp+290h+nSize]
0x18005530d  sub     ax, r12w
0x180055311  add     ax, ax
0x180055314  mov     [rdi+0A78h], ax
0x18005531b  movzx   eax, word ptr [rsp+290h+nSize]
0x180055320  sub     ax, r12w
0x180055324  add     ax, ax
0x180055327  mov     [rdi+0A7Ah], ax
0x18005532e  jmp     short loc_180055337
0x180055330  mov     rdi, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180055337  mov     byte ptr [rdi+0A60h], 0
0x18005533e  test    rsi, rsi
0x180055341  jz      short loc_18005534C
0x180055343  mov     rcx, rsi; Buffer
0x180055346  call    cs:__imp_LsaFreeMemory
0x18005534c  mov     rcx, cs:WPP_GLOBAL_Control
0x180055353  test    dword ptr [rcx+44h], 20000h
0x18005535a  jz      short loc_180055378
0x18005535c  mov     edx, 96h
0x180055361  mov     r9d, ebx
0x180055364  mov     rcx, [rcx+38h]
0x180055368  lea     r8, WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids
0x18005536f  mov     [rsp+290h+var_270], ebx
0x180055373  call    WPP_SF_Dd
0x180055378  mov     eax, ebx
0x18005537a  mov     rcx, [rbp+190h+var_40]
0x180055381  xor     rcx, rsp; StackCookie
0x180055384  call    __security_check_cookie
0x180055389  add     rsp, 268h
0x180055390  pop     r14
0x180055392  pop     r12
0x180055394  pop     rdi
0x180055395  pop     rsi
0x180055396  pop     rbx
0x180055397  pop     rbp
0x180055398  retn
```
