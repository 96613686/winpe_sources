# ScCreateWellKnownSids

- ea: `0x140002350`
- end: `0x1400026f7`
- name: `ScCreateWellKnownSids`
- size: `935`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x1400039f0`

## callees

- `0x140002350`
- `0x140004bd0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1400023e5`
- `ntdll!RtlAllocateHeap` at `0x14000248a`
- `ntdll!RtlAllocateHeap` at `0x1400024f9`
- `ntdll!RtlAllocateHeap` at `0x140002599`
- `ntdll!RtlAllocateHeap` at `0x140002658`
- `ntdll!RtlAllocateHeap` at `0x1400023e5`
- `ntdll!RtlAllocateHeap` at `0x14000248a`
- `ntdll!RtlAllocateHeap` at `0x1400024f9`
- `ntdll!RtlAllocateHeap` at `0x140002599`
- `ntdll!RtlAllocateHeap` at `0x140002658`
- `ntdll!RtlFreeHeap` at `0x1400026ad`
- `ntdll!RtlFreeHeap` at `0x1400026ad`
- `ntdll!RtlInitializeSid` at `0x140002407`
- `ntdll!RtlInitializeSid` at `0x14000251a`
- `ntdll!RtlInitializeSid` at `0x1400025ba`
- `ntdll!RtlInitializeSid` at `0x140002675`
- `ntdll!RtlInitializeSid` at `0x140002407`
- `ntdll!RtlInitializeSid` at `0x14000251a`
- `ntdll!RtlInitializeSid` at `0x1400025ba`
- `ntdll!RtlInitializeSid` at `0x140002675`
- `ntdll!RtlSubAuthoritySid` at `0x140002422`
- `ntdll!RtlSubAuthoritySid` at `0x1400024c8`
- `ntdll!RtlSubAuthoritySid` at `0x140002529`
- `ntdll!RtlSubAuthoritySid` at `0x140002541`
- `ntdll!RtlSubAuthoritySid` at `0x1400025c9`
- `ntdll!RtlSubAuthoritySid` at `0x1400025e1`
- `ntdll!RtlSubAuthoritySid` at `0x1400025f7`
- `ntdll!RtlSubAuthoritySid` at `0x14000260b`
- `ntdll!RtlSubAuthoritySid` at `0x14000261f`
- `ntdll!RtlSubAuthoritySid` at `0x140002633`
- `ntdll!RtlSubAuthoritySid` at `0x140002686`
- `ntdll!RtlSubAuthoritySid` at `0x14000269e`
- `ntdll!RtlSubAuthoritySid` at `0x140002422`
- `ntdll!RtlSubAuthoritySid` at `0x1400024c8`
- `ntdll!RtlSubAuthoritySid` at `0x140002529`
- `ntdll!RtlSubAuthoritySid` at `0x140002541`
- `ntdll!RtlSubAuthoritySid` at `0x1400025c9`
- `ntdll!RtlSubAuthoritySid` at `0x1400025e1`
- `ntdll!RtlSubAuthoritySid` at `0x1400025f7`
- `ntdll!RtlSubAuthoritySid` at `0x14000260b`
- `ntdll!RtlSubAuthoritySid` at `0x14000261f`
- `ntdll!RtlSubAuthoritySid` at `0x140002633`
- `ntdll!RtlSubAuthoritySid` at `0x140002686`
- `ntdll!RtlSubAuthoritySid` at `0x14000269e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400026c1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400026c1`
- `ntdll!RtlSubAuthorityCountSid` at `0x14000246c`
- `ntdll!RtlSubAuthorityCountSid` at `0x1400024ba`
- `ntdll!RtlSubAuthorityCountSid` at `0x14000246c`
- `ntdll!RtlSubAuthorityCountSid` at `0x1400024ba`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000238e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000238e`
- `ntdll!RtlLengthRequiredSid` at `0x1400023cd`
- `ntdll!RtlLengthRequiredSid` at `0x14000247a`
- `ntdll!RtlLengthRequiredSid` at `0x1400024e1`
- `ntdll!RtlLengthRequiredSid` at `0x140002581`
- `ntdll!RtlLengthRequiredSid` at `0x140002640`
- `ntdll!RtlLengthRequiredSid` at `0x1400023cd`
- `ntdll!RtlLengthRequiredSid` at `0x14000247a`
- `ntdll!RtlLengthRequiredSid` at `0x1400024e1`
- `ntdll!RtlLengthRequiredSid` at `0x140002581`
- `ntdll!RtlLengthRequiredSid` at `0x140002640`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x140002565`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x140002565`
- `ntdll!RtlCopySid` at `0x1400024a4`
- `ntdll!RtlCopySid` at `0x1400024a4`

## pseudocode

```c
__int64 ScCreateWellKnownSids()
{
  __int64 v0; // rdi
  __int64 v1; // rsi
  __int64 *v2; // rbx
  ULONG v3; // eax
  PVOID Heap; // rax
  ULONG v5; // ebx
  unsigned int v6; // edi
  PSID v7; // rbx
  PVOID *v8; // rsi
  ULONG v9; // r15d
  PVOID ProcessHeap; // r12
  ULONG v11; // r14d
  SIZE_T v12; // rbp
  PVOID v13; // rax
  NTSTATUS v14; // ebx
  PUCHAR v15; // rax
  ULONG v16; // eax
  PVOID v17; // rax
  ULONG v18; // eax
  PVOID v19; // rax
  ULONG v20; // eax
  PVOID v21; // rax
  struct _SID_IDENTIFIER_AUTHORITY v23; // [rsp+20h] [rbp-48h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+28h] [rbp-40h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  *(_DWORD *)v23.Value = 0;
  *(_WORD *)&v23.Value[4] = 1280;
  RtlAcquireSRWLockExclusive(&qword_14000F318);
  v0 = 0;
  while ( 1 )
  {
    v1 = 3 * v0;
    v2 = (&off_14000A010)[3 * v0];
    v3 = RtlLengthRequiredSid(1u);
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
    *v2 = (__int64)Heap;
    if ( !Heap )
      break;
    RtlInitializeSid(Heap, (PSID_IDENTIFIER_AUTHORITY)&qword_14000A018[v1], 1u);
    v5 = qword_14000A018[v1 + 1];
    v0 = (unsigned int)(v0 + 1);
    *RtlSubAuthoritySid((PSID)*(&off_14000A010)[v1], 0) = v5;
    if ( (unsigned int)v0 >= 0x12 )
    {
      v6 = 0;
      while ( 1 )
      {
        v7 = BuiltinDomainSid;
        v8 = (PVOID *)(&off_14000A1D0)[2 * v6];
        v9 = dword_14000A1D8[4 * v6];
        ProcessHeap = NtCurrentPeb()->ProcessHeap;
        v11 = *RtlSubAuthorityCountSid(BuiltinDomainSid);
        v12 = RtlLengthRequiredSid(v11 + 1);
        v13 = RtlAllocateHeap(ProcessHeap, 0, v12);
        *v8 = v13;
        if ( !v13 )
          goto LABEL_14;
        v14 = RtlCopySid(v12, v13, v7);
        if ( v14 < 0 )
        {
          RtlFreeHeap(ProcessHeap, 0, *v8);
          goto LABEL_15;
        }
        v15 = RtlSubAuthorityCountSid(*v8);
        ++*v15;
        ++v6;
        *RtlSubAuthoritySid(*v8, v11) = v9;
        if ( v6 >= 8 )
        {
          v16 = RtlLengthRequiredSid(2u);
          v17 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
          AnyPackageSid = v17;
          if ( !v17 )
            goto LABEL_14;
          RtlInitializeSid(v17, &IdentifierAuthority, 2u);
          *RtlSubAuthoritySid(AnyPackageSid, 0) = 2;
          *RtlSubAuthoritySid(AnyPackageSid, 1u) = 1;
          v14 = RtlDeriveCapabilitySidsFromName(
                  L",.",
                  &LpacServicesManagementCapabilityGroupSidBuffer,
                  &LpacServicesManagementCapabilitySidBuffer);
          if ( v14 < 0 )
            goto LABEL_15;
          LpacServicesManagementCapabilitySid = (__int64)&LpacServicesManagementCapabilitySidBuffer;
          v18 = RtlLengthRequiredSid(6u);
          v19 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
          UserModeDriversSid = v19;
          if ( v19 )
          {
            RtlInitializeSid(v19, &v23, 6u);
            *RtlSubAuthoritySid(UserModeDriversSid, 0) = 84;
            *RtlSubAuthoritySid(UserModeDriversSid, 1u) = 0;
            *RtlSubAuthoritySid(UserModeDriversSid, 2u) = 0;
            *RtlSubAuthoritySid(UserModeDriversSid, 3u) = 0;
            *RtlSubAuthoritySid(UserModeDriversSid, 4u) = 0;
            *RtlSubAuthoritySid(UserModeDriversSid, 5u) = 0;
            v20 = RtlLengthRequiredSid(2u);
            v21 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
            AllRestrictedServicesSid = v21;
            if ( v21 )
            {
              RtlInitializeSid(v21, &v23, 2u);
              v14 = 0;
              *RtlSubAuthoritySid(AllRestrictedServicesSid, 0) = 99;
              *RtlSubAuthoritySid(AllRestrictedServicesSid, 1u) = 0;
              goto LABEL_15;
            }
          }
          goto LABEL_14;
        }
      }
    }
  }
LABEL_14:
  v14 = -1073741801;
LABEL_15:
  RtlReleaseSRWLockExclusive(&qword_14000F318);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140002350  push    rbx
0x140002352  push    rsi
0x140002353  push    rdi
0x140002354  push    r13
0x140002356  sub     rsp, 48h
0x14000235a  mov     rax, cs:__security_cookie
0x140002361  xor     rax, rsp
0x140002364  mov     [rsp+68h+var_38], rax
0x140002369  lea     rcx, qword_14000F318
0x140002370  mov     dword ptr [rsp+68h+IdentifierAuthority.Value], 0
0x140002378  mov     word ptr [rsp+68h+IdentifierAuthority.Value+4], 0F00h
0x14000237f  mov     dword ptr [rsp+68h+var_48.Value], 0
0x140002387  mov     word ptr [rsp+68h+var_48.Value+4], 500h
0x14000238e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140002394  mov     [rsp+68h+arg_0], rbp
0x140002399  lea     r13, __ImageBase
0x1400023a0  mov     [rsp+68h+arg_8], r12
0x1400023a5  xor     edi, edi
0x1400023a7  mov     [rsp+68h+arg_10], r14
0x1400023af  mov     [rsp+68h+var_28], r15
0x1400023b4  lea     rcx, [rdi+rdi*2]
0x1400023b8  lea     rsi, ds:0[rcx*8]
0x1400023c0  mov     ecx, 1; SubAuthorityCount
0x1400023c5  mov     rbx, [rsi+r13+0A010h]
0x1400023cd  call    cs:__imp_RtlLengthRequiredSid
0x1400023d3  mov     rcx, gs:60h
0x1400023dc  xor     edx, edx; Flags
0x1400023de  mov     r8d, eax; Size
0x1400023e1  mov     rcx, [rcx+30h]; HeapHandle
0x1400023e5  call    cs:__imp_RtlAllocateHeap
0x1400023eb  mov     [rbx], rax
0x1400023ee  test    rax, rax
0x1400023f1  jz      loc_1400026B5
0x1400023f7  lea     rdx, rva qword_14000A018[r13]
0x1400023fe  mov     r8b, 1; SubAuthorityCount
0x140002401  add     rdx, rsi; IdentifierAuthority
0x140002404  mov     rcx, rax; Sid
0x140002407  call    cs:__imp_RtlInitializeSid
0x14000240d  mov     rcx, [rsi+r13+0A010h]
0x140002415  xor     edx, edx; SubAuthority
0x140002417  mov     ebx, [rsi+r13+0A020h]
0x14000241f  mov     rcx, [rcx]; Sid
0x140002422  call    cs:__imp_RtlSubAuthoritySid
0x140002428  inc     edi
0x14000242a  mov     [rax], ebx
0x14000242c  cmp     edi, 12h
0x14000242f  jb      short loc_1400023B4
0x140002431  xor     edi, edi
0x140002433  nop     dword ptr [rax+00h]
0x140002437  nop     word ptr [rax+rax+00000000h]
0x140002440  mov     rbx, cs:BuiltinDomainSid
0x140002447  mov     eax, edi
0x140002449  mov     rcx, rbx; Sid
0x14000244c  add     rax, rax
0x14000244f  mov     rsi, ds:rva off_14000A1D0[r13+rax*8]
0x140002457  mov     r15d, ds:rva dword_14000A1D8[r13+rax*8]
0x14000245f  mov     rax, gs:60h
0x140002468  mov     r12, [rax+30h]
0x14000246c  call    cs:__imp_RtlSubAuthorityCountSid
0x140002472  movzx   r14d, byte ptr [rax]
0x140002476  lea     ecx, [r14+1]; SubAuthorityCount
0x14000247a  call    cs:__imp_RtlLengthRequiredSid
0x140002480  mov     r8d, eax; Size
0x140002483  xor     edx, edx; Flags
0x140002485  mov     rcx, r12; HeapHandle
0x140002488  mov     ebp, eax
0x14000248a  call    cs:__imp_RtlAllocateHeap
0x140002490  mov     [rsi], rax
0x140002493  test    rax, rax
0x140002496  jz      loc_1400026B5
0x14000249c  mov     r8, rbx; SourceSid
0x14000249f  mov     rdx, rax; DestinationSid
0x1400024a2  mov     ecx, ebp; DestinationSidLength
0x1400024a4  call    cs:__imp_RtlCopySid
0x1400024aa  mov     r8, [rsi]; P
0x1400024ad  mov     ebx, eax
0x1400024af  test    eax, eax
0x1400024b1  js      loc_1400026A8
0x1400024b7  mov     rcx, r8; Sid
0x1400024ba  call    cs:__imp_RtlSubAuthorityCountSid
0x1400024c0  mov     edx, r14d; SubAuthority
0x1400024c3  inc     byte ptr [rax]
0x1400024c5  mov     rcx, [rsi]; Sid
0x1400024c8  call    cs:__imp_RtlSubAuthoritySid
0x1400024ce  inc     edi
0x1400024d0  mov     [rax], r15d
0x1400024d3  cmp     edi, 8
0x1400024d6  jb      loc_140002440
0x1400024dc  mov     ecx, 2; SubAuthorityCount
0x1400024e1  call    cs:__imp_RtlLengthRequiredSid
0x1400024e7  mov     rcx, gs:60h
0x1400024f0  xor     edx, edx; Flags
0x1400024f2  mov     r8d, eax; Size
0x1400024f5  mov     rcx, [rcx+30h]; HeapHandle
0x1400024f9  call    cs:__imp_RtlAllocateHeap
0x1400024ff  mov     cs:AnyPackageSid, rax
0x140002506  test    rax, rax
0x140002509  jz      loc_1400026B5
0x14000250f  mov     r8b, 2; SubAuthorityCount
0x140002512  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x140002517  mov     rcx, rax; Sid
0x14000251a  call    cs:__imp_RtlInitializeSid
0x140002520  mov     rcx, cs:AnyPackageSid; Sid
0x140002527  xor     edx, edx; SubAuthority
0x140002529  call    cs:__imp_RtlSubAuthoritySid
0x14000252f  mov     edx, 1; SubAuthority
0x140002534  mov     dword ptr [rax], 2
0x14000253a  mov     rcx, cs:AnyPackageSid; Sid
0x140002541  call    cs:__imp_RtlSubAuthoritySid
0x140002547  lea     rdi, ?LpacServicesManagementCapabilitySidBuffer@@3PAEA; uchar near * LpacServicesManagementCapabilitySidBuffer
0x14000254e  mov     r8, rdi
0x140002551  lea     rdx, ?LpacServicesManagementCapabilityGroupSidBuffer@@3PAEA; uchar near * LpacServicesManagementCapabilityGroupSidBuffer
0x140002558  lea     rcx, asc_14000A1C0; ",."
0x14000255f  mov     dword ptr [rax], 1
0x140002565  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x14000256b  mov     ebx, eax
0x14000256d  test    eax, eax
0x14000256f  js      loc_1400026BA
0x140002575  mov     ecx, 6; SubAuthorityCount
0x14000257a  mov     cs:LpacServicesManagementCapabilitySid, rdi
0x140002581  call    cs:__imp_RtlLengthRequiredSid
0x140002587  mov     rcx, gs:60h
0x140002590  xor     edx, edx; Flags
0x140002592  mov     r8d, eax; Size
0x140002595  mov     rcx, [rcx+30h]; HeapHandle
0x140002599  call    cs:__imp_RtlAllocateHeap
0x14000259f  mov     cs:UserModeDriversSid, rax
0x1400025a6  test    rax, rax
0x1400025a9  jz      loc_1400026B5
0x1400025af  mov     r8b, 6; SubAuthorityCount
0x1400025b2  lea     rdx, [rsp+68h+var_48]; IdentifierAuthority
0x1400025b7  mov     rcx, rax; Sid
0x1400025ba  call    cs:__imp_RtlInitializeSid
0x1400025c0  mov     rcx, cs:UserModeDriversSid; Sid
0x1400025c7  xor     edx, edx; SubAuthority
0x1400025c9  call    cs:__imp_RtlSubAuthoritySid
0x1400025cf  mov     edx, 1; SubAuthority
0x1400025d4  mov     dword ptr [rax], 54h ; 'T'
0x1400025da  mov     rcx, cs:UserModeDriversSid; Sid
0x1400025e1  call    cs:__imp_RtlSubAuthoritySid
0x1400025e7  xor     edi, edi
0x1400025e9  mov     edx, 2; SubAuthority
0x1400025ee  mov     [rax], edi
0x1400025f0  mov     rcx, cs:UserModeDriversSid; Sid
0x1400025f7  call    cs:__imp_RtlSubAuthoritySid
0x1400025fd  mov     edx, 3; SubAuthority
0x140002602  mov     [rax], edi
0x140002604  mov     rcx, cs:UserModeDriversSid; Sid
0x14000260b  call    cs:__imp_RtlSubAuthoritySid
0x140002611  mov     edx, 4; SubAuthority
0x140002616  mov     [rax], edi
0x140002618  mov     rcx, cs:UserModeDriversSid; Sid
0x14000261f  call    cs:__imp_RtlSubAuthoritySid
0x140002625  mov     edx, 5; SubAuthority
0x14000262a  mov     [rax], edi
0x14000262c  mov     rcx, cs:UserModeDriversSid; Sid
0x140002633  call    cs:__imp_RtlSubAuthoritySid
0x140002639  mov     ecx, 2; SubAuthorityCount
0x14000263e  mov     [rax], edi
0x140002640  call    cs:__imp_RtlLengthRequiredSid
0x140002646  mov     rcx, gs:60h
0x14000264f  xor     edx, edx; Flags
0x140002651  mov     r8d, eax; Size
0x140002654  mov     rcx, [rcx+30h]; HeapHandle
0x140002658  call    cs:__imp_RtlAllocateHeap
0x14000265e  mov     cs:AllRestrictedServicesSid, rax
0x140002665  test    rax, rax
0x140002668  jz      short loc_1400026B5
0x14000266a  mov     r8b, 2; SubAuthorityCount
0x14000266d  lea     rdx, [rsp+68h+var_48]; IdentifierAuthority
0x140002672  mov     rcx, rax; Sid
0x140002675  call    cs:__imp_RtlInitializeSid
0x14000267b  mov     rcx, cs:AllRestrictedServicesSid; Sid
0x140002682  xor     edx, edx; SubAuthority
0x140002684  mov     ebx, edi
0x140002686  call    cs:__imp_RtlSubAuthoritySid
0x14000268c  mov     edx, 1; SubAuthority
0x140002691  mov     dword ptr [rax], 63h ; 'c'
0x140002697  mov     rcx, cs:AllRestrictedServicesSid; Sid
0x14000269e  call    cs:__imp_RtlSubAuthoritySid
0x1400026a4  mov     [rax], edi
0x1400026a6  jmp     short loc_1400026BA
0x1400026a8  xor     edx, edx; Flags
0x1400026aa  mov     rcx, r12; HeapHandle
0x1400026ad  call    cs:__imp_RtlFreeHeap
0x1400026b3  jmp     short loc_1400026BA
0x1400026b5  mov     ebx, 0C0000017h
0x1400026ba  lea     rcx, qword_14000F318
0x1400026c1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1400026c7  mov     r15, [rsp+68h+var_28]
0x1400026cc  mov     eax, ebx
0x1400026ce  mov     r14, [rsp+68h+arg_10]
0x1400026d6  mov     r12, [rsp+68h+arg_8]
0x1400026db  mov     rbp, [rsp+68h+arg_0]
0x1400026e0  mov     rcx, [rsp+68h+var_38]
0x1400026e5  xor     rcx, rsp; StackCookie
0x1400026e8  call    __security_check_cookie
0x1400026ed  add     rsp, 48h
0x1400026f1  pop     r13
0x1400026f3  pop     rdi
0x1400026f4  pop     rsi
0x1400026f5  pop     rbx
0x1400026f6  retn
```
