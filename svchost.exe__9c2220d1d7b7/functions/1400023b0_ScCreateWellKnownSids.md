# ScCreateWellKnownSids

- ea: `0x1400023b0`
- end: `0x140002820`
- name: `ScCreateWellKnownSids`
- size: `1136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x140003cd0`

## callees

- `0x1400023b0`
- `0x140004f90`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140002457`
- `ntdll!RtlAllocateHeap` at `0x140002516`
- `ntdll!RtlAllocateHeap` at `0x1400025a3`
- `ntdll!RtlAllocateHeap` at `0x140002667`
- `ntdll!RtlAllocateHeap` at `0x14000275c`
- `ntdll!RtlAllocateHeap` at `0x140002457`
- `ntdll!RtlAllocateHeap` at `0x140002516`
- `ntdll!RtlAllocateHeap` at `0x1400025a3`
- `ntdll!RtlAllocateHeap` at `0x140002667`
- `ntdll!RtlAllocateHeap` at `0x14000275c`
- `ntdll!RtlFreeHeap` at `0x1400027c9`
- `ntdll!RtlFreeHeap` at `0x1400027c9`
- `ntdll!RtlInitializeSid` at `0x14000247f`
- `ntdll!RtlInitializeSid` at `0x1400025ca`
- `ntdll!RtlInitializeSid` at `0x14000268e`
- `ntdll!RtlInitializeSid` at `0x14000277f`
- `ntdll!RtlInitializeSid` at `0x14000247f`
- `ntdll!RtlInitializeSid` at `0x1400025ca`
- `ntdll!RtlInitializeSid` at `0x14000268e`
- `ntdll!RtlInitializeSid` at `0x14000277f`
- `ntdll!RtlSubAuthoritySid` at `0x1400024a0`
- `ntdll!RtlSubAuthoritySid` at `0x140002566`
- `ntdll!RtlSubAuthoritySid` at `0x1400025df`
- `ntdll!RtlSubAuthoritySid` at `0x1400025fd`
- `ntdll!RtlSubAuthoritySid` at `0x1400026a3`
- `ntdll!RtlSubAuthoritySid` at `0x1400026c1`
- `ntdll!RtlSubAuthoritySid` at `0x1400026dd`
- `ntdll!RtlSubAuthoritySid` at `0x1400026f7`
- `ntdll!RtlSubAuthoritySid` at `0x140002711`
- `ntdll!RtlSubAuthoritySid` at `0x14000272b`
- `ntdll!RtlSubAuthoritySid` at `0x140002796`
- `ntdll!RtlSubAuthoritySid` at `0x1400027b4`
- `ntdll!RtlSubAuthoritySid` at `0x1400024a0`
- `ntdll!RtlSubAuthoritySid` at `0x140002566`
- `ntdll!RtlSubAuthoritySid` at `0x1400025df`
- `ntdll!RtlSubAuthoritySid` at `0x1400025fd`
- `ntdll!RtlSubAuthoritySid` at `0x1400026a3`
- `ntdll!RtlSubAuthoritySid` at `0x1400026c1`
- `ntdll!RtlSubAuthoritySid` at `0x1400026dd`
- `ntdll!RtlSubAuthoritySid` at `0x1400026f7`
- `ntdll!RtlSubAuthoritySid` at `0x140002711`
- `ntdll!RtlSubAuthoritySid` at `0x14000272b`
- `ntdll!RtlSubAuthoritySid` at `0x140002796`
- `ntdll!RtlSubAuthoritySid` at `0x1400027b4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400027e3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400027e3`
- `ntdll!RtlSubAuthorityCountSid` at `0x1400024ec`
- `ntdll!RtlSubAuthorityCountSid` at `0x140002552`
- `ntdll!RtlSubAuthorityCountSid` at `0x1400024ec`
- `ntdll!RtlSubAuthorityCountSid` at `0x140002552`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400023ee`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400023ee`
- `ntdll!RtlLengthRequiredSid` at `0x140002439`
- `ntdll!RtlLengthRequiredSid` at `0x140002500`
- `ntdll!RtlLengthRequiredSid` at `0x140002585`
- `ntdll!RtlLengthRequiredSid` at `0x140002649`
- `ntdll!RtlLengthRequiredSid` at `0x14000273e`
- `ntdll!RtlLengthRequiredSid` at `0x140002439`
- `ntdll!RtlLengthRequiredSid` at `0x140002500`
- `ntdll!RtlLengthRequiredSid` at `0x140002585`
- `ntdll!RtlLengthRequiredSid` at `0x140002649`
- `ntdll!RtlLengthRequiredSid` at `0x14000273e`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x140002627`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x140002627`
- `ntdll!RtlCopySid` at `0x140002536`
- `ntdll!RtlCopySid` at `0x140002536`

## pseudocode

```c
__int64 ScCreateWellKnownSids()
{
  __int64 v0; // rdi
  unsigned __int64 v1; // rsi
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
  RtlAcquireSRWLockExclusive(&unk_14000F318);
  v0 = 0;
  while ( 1 )
  {
    v1 = 24 * v0;
    v2 = (&off_14000A010)[3 * v0];
    v3 = RtlLengthRequiredSid(1u);
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
    *v2 = (__int64)Heap;
    if ( !Heap )
      break;
    RtlInitializeSid(Heap, (PSID_IDENTIFIER_AUTHORITY)((char *)&unk_14000A018 + v1), 1u);
    v5 = *(_DWORD *)((char *)&unk_14000A020 + v1);
    v0 = (unsigned int)(v0 + 1);
    *RtlSubAuthoritySid((PSID)*(&off_14000A010)[v1 / 8], 0) = v5;
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
  RtlReleaseSRWLockExclusive(&unk_14000F318);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400023b0  push    rbx
0x1400023b2  push    rsi
0x1400023b3  push    rdi
0x1400023b4  push    r13
0x1400023b6  sub     rsp, 48h
0x1400023ba  mov     rax, cs:__security_cookie
0x1400023c1  xor     rax, rsp
0x1400023c4  mov     [rsp+68h+var_38], rax
0x1400023c9  lea     rcx, unk_14000F318
0x1400023d0  mov     dword ptr [rsp+68h+IdentifierAuthority.Value], 0
0x1400023d8  mov     word ptr [rsp+68h+IdentifierAuthority.Value+4], 0F00h
0x1400023df  mov     dword ptr [rsp+68h+var_48.Value], 0
0x1400023e7  mov     word ptr [rsp+68h+var_48.Value+4], 500h
0x1400023ee  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1400023f5  nop     dword ptr [rax+rax+00h]
0x1400023fa  mov     [rsp+68h+arg_0], rbp
0x1400023ff  lea     r13, __ImageBase
0x140002406  mov     [rsp+68h+arg_8], r12
0x14000240b  xor     edi, edi
0x14000240d  mov     [rsp+68h+arg_10], r14
0x140002415  mov     [rsp+68h+var_28], r15
0x14000241a  nop     word ptr [rax+rax+00h]
0x140002420  lea     rcx, [rdi+rdi*2]
0x140002424  lea     rsi, ds:0[rcx*8]
0x14000242c  mov     ecx, 1; SubAuthorityCount
0x140002431  mov     rbx, [rsi+r13+0A010h]
0x140002439  call    cs:__imp_RtlLengthRequiredSid
0x140002440  nop     dword ptr [rax+rax+00h]
0x140002445  mov     rcx, gs:60h
0x14000244e  xor     edx, edx; Flags
0x140002450  mov     r8d, eax; Size
0x140002453  mov     rcx, [rcx+30h]; HeapHandle
0x140002457  call    cs:__imp_RtlAllocateHeap
0x14000245e  nop     dword ptr [rax+rax+00h]
0x140002463  mov     [rbx], rax
0x140002466  test    rax, rax
0x140002469  jz      loc_1400027D7
0x14000246f  lea     rdx, rva unk_14000A018[r13]
0x140002476  mov     r8b, 1; SubAuthorityCount
0x140002479  add     rdx, rsi; IdentifierAuthority
0x14000247c  mov     rcx, rax; Sid
0x14000247f  call    cs:__imp_RtlInitializeSid
0x140002486  nop     dword ptr [rax+rax+00h]
0x14000248b  mov     rcx, [rsi+r13+0A010h]
0x140002493  xor     edx, edx; SubAuthority
0x140002495  mov     ebx, [rsi+r13+0A020h]
0x14000249d  mov     rcx, [rcx]; Sid
0x1400024a0  call    cs:__imp_RtlSubAuthoritySid
0x1400024a7  nop     dword ptr [rax+rax+00h]
0x1400024ac  inc     edi
0x1400024ae  mov     [rax], ebx
0x1400024b0  cmp     edi, 12h
0x1400024b3  jb      loc_140002420
0x1400024b9  xor     edi, edi
0x1400024bb  nop     dword ptr [rax+rax+00h]
0x1400024c0  mov     rbx, cs:BuiltinDomainSid
0x1400024c7  mov     eax, edi
0x1400024c9  mov     rcx, rbx; Sid
0x1400024cc  add     rax, rax
0x1400024cf  mov     rsi, ds:rva off_14000A1D0[r13+rax*8]
0x1400024d7  mov     r15d, ds:rva dword_14000A1D8[r13+rax*8]
0x1400024df  mov     rax, gs:60h
0x1400024e8  mov     r12, [rax+30h]
0x1400024ec  call    cs:__imp_RtlSubAuthorityCountSid
0x1400024f3  nop     dword ptr [rax+rax+00h]
0x1400024f8  movzx   r14d, byte ptr [rax]
0x1400024fc  lea     ecx, [r14+1]; SubAuthorityCount
0x140002500  call    cs:__imp_RtlLengthRequiredSid
0x140002507  nop     dword ptr [rax+rax+00h]
0x14000250c  mov     r8d, eax; Size
0x14000250f  xor     edx, edx; Flags
0x140002511  mov     rcx, r12; HeapHandle
0x140002514  mov     ebp, eax
0x140002516  call    cs:__imp_RtlAllocateHeap
0x14000251d  nop     dword ptr [rax+rax+00h]
0x140002522  mov     [rsi], rax
0x140002525  test    rax, rax
0x140002528  jz      loc_1400027D7
0x14000252e  mov     r8, rbx; SourceSid
0x140002531  mov     rdx, rax; DestinationSid
0x140002534  mov     ecx, ebp; DestinationSidLength
0x140002536  call    cs:__imp_RtlCopySid
0x14000253d  nop     dword ptr [rax+rax+00h]
0x140002542  mov     r8, [rsi]; P
0x140002545  mov     ebx, eax
0x140002547  test    eax, eax
0x140002549  js      loc_1400027C4
0x14000254f  mov     rcx, r8; Sid
0x140002552  call    cs:__imp_RtlSubAuthorityCountSid
0x140002559  nop     dword ptr [rax+rax+00h]
0x14000255e  mov     edx, r14d; SubAuthority
0x140002561  inc     byte ptr [rax]
0x140002563  mov     rcx, [rsi]; Sid
0x140002566  call    cs:__imp_RtlSubAuthoritySid
0x14000256d  nop     dword ptr [rax+rax+00h]
0x140002572  inc     edi
0x140002574  mov     [rax], r15d
0x140002577  cmp     edi, 8
0x14000257a  jb      loc_1400024C0
0x140002580  mov     ecx, 2; SubAuthorityCount
0x140002585  call    cs:__imp_RtlLengthRequiredSid
0x14000258c  nop     dword ptr [rax+rax+00h]
0x140002591  mov     rcx, gs:60h
0x14000259a  xor     edx, edx; Flags
0x14000259c  mov     r8d, eax; Size
0x14000259f  mov     rcx, [rcx+30h]; HeapHandle
0x1400025a3  call    cs:__imp_RtlAllocateHeap
0x1400025aa  nop     dword ptr [rax+rax+00h]
0x1400025af  mov     cs:AnyPackageSid, rax
0x1400025b6  test    rax, rax
0x1400025b9  jz      loc_1400027D7
0x1400025bf  mov     r8b, 2; SubAuthorityCount
0x1400025c2  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x1400025c7  mov     rcx, rax; Sid
0x1400025ca  call    cs:__imp_RtlInitializeSid
0x1400025d1  nop     dword ptr [rax+rax+00h]
0x1400025d6  mov     rcx, cs:AnyPackageSid; Sid
0x1400025dd  xor     edx, edx; SubAuthority
0x1400025df  call    cs:__imp_RtlSubAuthoritySid
0x1400025e6  nop     dword ptr [rax+rax+00h]
0x1400025eb  mov     edx, 1; SubAuthority
0x1400025f0  mov     dword ptr [rax], 2
0x1400025f6  mov     rcx, cs:AnyPackageSid; Sid
0x1400025fd  call    cs:__imp_RtlSubAuthoritySid
0x140002604  nop     dword ptr [rax+rax+00h]
0x140002609  lea     rdi, ?LpacServicesManagementCapabilitySidBuffer@@3PAEA; uchar near * LpacServicesManagementCapabilitySidBuffer
0x140002610  mov     r8, rdi
0x140002613  lea     rdx, ?LpacServicesManagementCapabilityGroupSidBuffer@@3PAEA; uchar near * LpacServicesManagementCapabilityGroupSidBuffer
0x14000261a  lea     rcx, asc_14000A1C0; ",."
0x140002621  mov     dword ptr [rax], 1
0x140002627  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x14000262e  nop     dword ptr [rax+rax+00h]
0x140002633  mov     ebx, eax
0x140002635  test    eax, eax
0x140002637  js      loc_1400027DC
0x14000263d  mov     ecx, 6; SubAuthorityCount
0x140002642  mov     cs:LpacServicesManagementCapabilitySid, rdi
0x140002649  call    cs:__imp_RtlLengthRequiredSid
0x140002650  nop     dword ptr [rax+rax+00h]
0x140002655  mov     rcx, gs:60h
0x14000265e  xor     edx, edx; Flags
0x140002660  mov     r8d, eax; Size
0x140002663  mov     rcx, [rcx+30h]; HeapHandle
0x140002667  call    cs:__imp_RtlAllocateHeap
0x14000266e  nop     dword ptr [rax+rax+00h]
0x140002673  mov     cs:UserModeDriversSid, rax
0x14000267a  test    rax, rax
0x14000267d  jz      loc_1400027D7
0x140002683  mov     r8b, 6; SubAuthorityCount
0x140002686  lea     rdx, [rsp+68h+var_48]; IdentifierAuthority
0x14000268b  mov     rcx, rax; Sid
0x14000268e  call    cs:__imp_RtlInitializeSid
0x140002695  nop     dword ptr [rax+rax+00h]
0x14000269a  mov     rcx, cs:UserModeDriversSid; Sid
0x1400026a1  xor     edx, edx; SubAuthority
0x1400026a3  call    cs:__imp_RtlSubAuthoritySid
0x1400026aa  nop     dword ptr [rax+rax+00h]
0x1400026af  mov     edx, 1; SubAuthority
0x1400026b4  mov     dword ptr [rax], 54h ; 'T'
0x1400026ba  mov     rcx, cs:UserModeDriversSid; Sid
0x1400026c1  call    cs:__imp_RtlSubAuthoritySid
0x1400026c8  nop     dword ptr [rax+rax+00h]
0x1400026cd  xor     edi, edi
0x1400026cf  mov     edx, 2; SubAuthority
0x1400026d4  mov     [rax], edi
0x1400026d6  mov     rcx, cs:UserModeDriversSid; Sid
0x1400026dd  call    cs:__imp_RtlSubAuthoritySid
0x1400026e4  nop     dword ptr [rax+rax+00h]
0x1400026e9  mov     edx, 3; SubAuthority
0x1400026ee  mov     [rax], edi
0x1400026f0  mov     rcx, cs:UserModeDriversSid; Sid
0x1400026f7  call    cs:__imp_RtlSubAuthoritySid
0x1400026fe  nop     dword ptr [rax+rax+00h]
0x140002703  mov     edx, 4; SubAuthority
0x140002708  mov     [rax], edi
0x14000270a  mov     rcx, cs:UserModeDriversSid; Sid
0x140002711  call    cs:__imp_RtlSubAuthoritySid
0x140002718  nop     dword ptr [rax+rax+00h]
0x14000271d  mov     edx, 5; SubAuthority
0x140002722  mov     [rax], edi
0x140002724  mov     rcx, cs:UserModeDriversSid; Sid
0x14000272b  call    cs:__imp_RtlSubAuthoritySid
0x140002732  nop     dword ptr [rax+rax+00h]
0x140002737  mov     ecx, 2; SubAuthorityCount
0x14000273c  mov     [rax], edi
0x14000273e  call    cs:__imp_RtlLengthRequiredSid
0x140002745  nop     dword ptr [rax+rax+00h]
0x14000274a  mov     rcx, gs:60h
0x140002753  xor     edx, edx; Flags
0x140002755  mov     r8d, eax; Size
0x140002758  mov     rcx, [rcx+30h]; HeapHandle
0x14000275c  call    cs:__imp_RtlAllocateHeap
0x140002763  nop     dword ptr [rax+rax+00h]
0x140002768  mov     cs:AllRestrictedServicesSid, rax
0x14000276f  test    rax, rax
0x140002772  jz      short loc_1400027D7
0x140002774  mov     r8b, 2; SubAuthorityCount
0x140002777  lea     rdx, [rsp+68h+var_48]; IdentifierAuthority
0x14000277c  mov     rcx, rax; Sid
0x14000277f  call    cs:__imp_RtlInitializeSid
0x140002786  nop     dword ptr [rax+rax+00h]
0x14000278b  mov     rcx, cs:AllRestrictedServicesSid; Sid
0x140002792  xor     edx, edx; SubAuthority
0x140002794  mov     ebx, edi
0x140002796  call    cs:__imp_RtlSubAuthoritySid
0x14000279d  nop     dword ptr [rax+rax+00h]
0x1400027a2  mov     edx, 1; SubAuthority
0x1400027a7  mov     dword ptr [rax], 63h ; 'c'
0x1400027ad  mov     rcx, cs:AllRestrictedServicesSid; Sid
0x1400027b4  call    cs:__imp_RtlSubAuthoritySid
0x1400027bb  nop     dword ptr [rax+rax+00h]
0x1400027c0  mov     [rax], edi
0x1400027c2  jmp     short loc_1400027DC
0x1400027c4  xor     edx, edx; Flags
0x1400027c6  mov     rcx, r12; HeapHandle
0x1400027c9  call    cs:__imp_RtlFreeHeap
0x1400027d0  nop     dword ptr [rax+rax+00h]
0x1400027d5  jmp     short loc_1400027DC
0x1400027d7  mov     ebx, 0C0000017h
0x1400027dc  lea     rcx, unk_14000F318
0x1400027e3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1400027ea  nop     dword ptr [rax+rax+00h]
0x1400027ef  mov     r15, [rsp+68h+var_28]
0x1400027f4  mov     eax, ebx
0x1400027f6  mov     r14, [rsp+68h+arg_10]
0x1400027fe  mov     r12, [rsp+68h+arg_8]
0x140002803  mov     rbp, [rsp+68h+arg_0]
0x140002808  mov     rcx, [rsp+68h+var_38]
0x14000280d  xor     rcx, rsp; StackCookie
0x140002810  call    __security_check_cookie
0x140002815  add     rsp, 48h
0x140002819  pop     r13
0x14000281b  pop     rdi
0x14000281c  pop     rsi
0x14000281d  pop     rbx
0x14000281e  retn
```
