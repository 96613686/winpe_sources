# SampFixBug18471(ulong)

- ea: `0x18009642c`
- end: `0x1800968ac`
- name: `?SampFixBug18471@@YAJK@Z`
- size: `1152`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180098c94`

## callees

- `0x1800022a0`
- `0x180003760`
- `0x180003860`
- `0x1800066f0`
- `0x180011810`
- `0x180011fe0`
- `0x1800167a0`
- `0x180022440`
- `0x1800229d8`
- `0x1800259ec`
- `0x1800270e0`
- `0x180027e24`
- `0x180027e70`
- `0x18002cd80`
- `0x18003cd20`
- `0x180063160`
- `0x180064050`
- `0x180065b60`
- `0x18008b62c`
- `0x18009565c`
- `0x1800957e0`
- `0x180095cc0`
- `0x180095e68`
- `0x180096268`
- `0x18009642c`
- `0x1800aa648`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180096629`
- `ntdll!RtlSubAuthorityCountSid` at `0x180096629`
- `ntdll!RtlSubAuthoritySid` at `0x1800964f3`
- `ntdll!RtlSubAuthoritySid` at `0x18009663c`
- `ntdll!RtlSubAuthoritySid` at `0x1800964f3`
- `ntdll!RtlSubAuthoritySid` at `0x18009663c`
- `ntdll!RtlInitializeSid` at `0x1800964e8`
- `ntdll!RtlInitializeSid` at `0x1800964e8`
- `ntdll!RtlFreeHeap` at `0x18009684d`
- `ntdll!RtlFreeHeap` at `0x18009684d`
- `ntdll!RtlAllocateHeap` at `0x1800964be`
- `ntdll!RtlAllocateHeap` at `0x1800964be`
- `ntdll!RtlLengthRequiredSid` at `0x1800964a6`
- `ntdll!RtlLengthRequiredSid` at `0x1800964a6`
- `ntdll!RtlEqualSid` at `0x180096521`
- `ntdll!RtlEqualSid` at `0x180096521`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009674d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009674d`

## pseudocode

```c
__int64 __fastcall SampFixBug18471(unsigned int a1)
{
  ULONG v1; // eax
  PVOID Heap; // rax
  void *v3; // r12
  int AccountContext; // ebx
  unsigned int v5; // esi
  unsigned int v6; // edi
  PULONG v7; // rax
  unsigned int v8; // ebx
  bool v9; // zf
  BOOLEAN v10; // al
  unsigned int v11; // ecx
  __int64 v12; // r13
  __int64 v13; // r8
  __int64 v14; // r9
  ULONG v15; // ecx
  __int64 v16; // r15
  PUCHAR v17; // rax
  PULONG v18; // rax
  ULONG v19; // ecx
  ULONG v20; // r14d
  __int64 v21; // r8
  __int64 v22; // r9
  struct _SAMP_OBJECT *v23; // rdi
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v27; // [rsp+20h] [rbp-79h]
  int v28; // [rsp+30h] [rbp-69h]
  unsigned int v29; // [rsp+34h] [rbp-65h] BYREF
  void **v30[2]; // [rsp+38h] [rbp-61h] BYREF
  PVOID HandleId; // [rsp+48h] [rbp-51h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-49h] BYREF
  PVOID v33; // [rsp+58h] [rbp-41h] BYREF
  __int64 v34; // [rsp+60h] [rbp-39h] BYREF
  __int64 v35; // [rsp+68h] [rbp-31h]
  PSID v36; // [rsp+78h] [rbp-21h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+80h] [rbp-19h] BYREF
  __int128 v38; // [rsp+88h] [rbp-11h] BYREF
  int v39; // [rsp+98h] [rbp-1h]

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v34 = 0;
  hMem = 0;
  v29 = 0;
  v33 = 0;
  HandleId = 0;
  v39 = 0;
  *(_OWORD *)v30 = 0;
  v38 = 0;
  if ( a1 >= 0x10003 )
    goto LABEL_46;
  v1 = RtlLengthRequiredSid(1u);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
  v3 = Heap;
  if ( !Heap )
  {
    AccountContext = -1073741670;
    goto LABEL_47;
  }
  v5 = -1;
  v28 = -1;
  v6 = -1;
  RtlInitializeSid(Heap, &IdentifierAuthority, 1u);
  v7 = RtlSubAuthoritySid(v3, 0);
  v8 = 0;
  v9 = SampDefinedDomainsCount == 0;
  *v7 = 32;
  if ( !v9 )
  {
    do
    {
      v10 = RtlEqualSid(v3, *((PSID *)SampDefinedDomains + 170 * v8 + 1));
      v11 = v8;
      if ( !v10 )
      {
        v11 = v6;
        v5 = v8;
      }
      ++v8;
      v6 = v11;
    }
    while ( v8 < SampDefinedDomainsCount );
    v28 = v11;
  }
  v35 = 1360LL * v5;
  v36 = *(PSID *)((char *)SampDefinedDomains + v35 + 8);
  AccountContext = SampCreate18471Key();
  if ( AccountContext < 0 )
    goto LABEL_45;
  v12 = 0;
LABEL_11:
  SampSetTransactionDomain(v6);
  SampAcquireReadLock();
  AccountContext = SampCreateAccountContext(3, *((_DWORD *)qword_1800D2E20 + v12), v13, v14, v27, (__int64)&HandleId);
  if ( AccountContext >= 0 )
  {
    AccountContext = SampRetrieveAliasMembers((struct _SAMP_OBJECT *)HandleId, (unsigned int *)v30, &v30[1]);
    SampDeleteContext(HandleId);
    SampReleaseReadLock();
    if ( AccountContext < 0 )
      goto LABEL_45;
    v15 = *((_DWORD *)qword_1800D2E20 + v12);
    if ( v15 != 544 )
    {
      AccountContext = SampAddAliasTo18471Key(v15);
      if ( AccountContext < 0 )
        goto LABEL_45;
    }
    v16 = 0;
    if ( !LODWORD(v30[0]) )
      goto LABEL_43;
    while ( 1 )
    {
      if ( SampMatchDomainPrefix(v30[1][v16], v36) )
      {
        v17 = RtlSubAuthorityCountSid(v30[1][v16]);
        v18 = RtlSubAuthoritySid(v30[1][v16], (unsigned int)*v17 - 1);
        v19 = *((_DWORD *)qword_1800D2E20 + v12);
        v20 = *v18;
        if ( v19 == 544 )
        {
          AccountContext = SampAcquireWriteLock(*(_QWORD *)((char *)SampDefinedDomains + v35));
          if ( AccountContext < 0 )
            goto LABEL_42;
          SampSetTransactionDomain(v5);
          AccountContext = SampCreateAccountContext(2, v20, v21, v22, v27, (__int64)&v33);
          if ( AccountContext >= 0 )
          {
            v23 = (struct _SAMP_OBJECT *)v33;
            AccountContext = SampRetrieveGroupV1Fixed(v33, &v38);
            if ( AccountContext >= 0 )
            {
              LOBYTE(v39) = 1;
              AccountContext = SampReplaceGroupV1Fixed(v23, (struct _SAMP_V1_0A_FIXED_LENGTH_GROUP *)&v38);
              if ( AccountContext >= 0 )
              {
                AccountContext = SampGetAccessAttribute(v23, (__int64)&v34);
                if ( AccountContext >= 0 )
                {
                  AccountContext = SampModifyAccountSecurity((__int64)v23, 2, 1, (void *)v34, &hMem, &v29);
                  if ( AccountContext >= 0 )
                  {
                    AccountContext = SampSetAccessAttribute(v23, 0, (unsigned __int8 *)hMem, v29);
                    LocalFree(hMem);
                    if ( AccountContext >= 0 )
                      AccountContext = SampStoreObjectAttributes(v23);
                  }
                }
              }
            }
            SampDeleteContext(v23);
            SampSetTransactionWithinDomain(0);
            if ( AccountContext < 0 )
            {
              SampReleaseWriteLock(0);
            }
            else
            {
              LOBYTE(v24) = 1;
              AccountContext = SampReleaseWriteLock(v24);
            }
          }
          else
          {
            SampReleaseWriteLock(0);
            if ( AccountContext != -1073741722 )
              goto LABEL_42;
            AccountContext = 0;
          }
        }
        else
        {
          AccountContext = SampCheckMemberUpgradedFor18471(v19, v20);
          if ( AccountContext < 0 )
          {
            AccountContext = SampAcquireWriteLock(*(_QWORD *)((char *)SampDefinedDomains + v35));
            if ( AccountContext < 0 )
              goto LABEL_42;
            SampSetTransactionDomain(v5);
            AccountContext = SampChangeAccountOperatorAccessToMember(v30[1][v16], 1u, 0);
            if ( AccountContext >= 0 )
              AccountContext = SampAddMemberRidTo18471Key(*((_DWORD *)qword_1800D2E20 + v12), v20);
            SampSetTransactionWithinDomain(0);
            if ( AccountContext < 0 )
            {
              SampReleaseWriteLock(0);
LABEL_42:
              v6 = v28;
LABEL_43:
              SamIFree_SAMPR_PSID_ARRAY((struct _SAMPR_PSID_ARRAY *)v30);
              v30[1] = 0;
              if ( AccountContext < 0 )
                goto LABEL_45;
LABEL_44:
              v12 = (unsigned int)(v12 + 1);
              if ( (unsigned int)v12 >= 5 )
                goto LABEL_45;
              goto LABEL_11;
            }
            LOBYTE(v25) = 1;
            AccountContext = SampReleaseWriteLock(v25);
            if ( AccountContext < 0 )
              goto LABEL_42;
          }
        }
      }
      v16 = (unsigned int)(v16 + 1);
      if ( (unsigned int)v16 >= LODWORD(v30[0]) )
        goto LABEL_42;
    }
  }
  SampReleaseReadLock();
  if ( AccountContext == -1073741487 )
  {
    AccountContext = 0;
    goto LABEL_44;
  }
LABEL_45:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  if ( AccountContext >= 0 )
LABEL_46:
    AccountContext = SampCleanup18471();
LABEL_47:
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      19,
      WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids,
      (unsigned int)AccountContext,
      AccountContext);
  return (unsigned int)AccountContext;
}

```

## disassembly

```asm
0x18009642c  push    rbp
0x18009642e  push    rbx
0x18009642f  push    rsi
0x180096430  push    rdi
0x180096431  push    r12
0x180096433  push    r13
0x180096435  push    r14
0x180096437  push    r15
0x180096439  lea     rbp, [rsp-1Fh]
0x18009643e  sub     rsp, 0B8h
0x180096445  mov     rax, cs:__security_cookie
0x18009644c  xor     rax, rsp
0x18009644f  mov     [rbp+57h+var_50], rax
0x180096453  xor     eax, eax
0x180096455  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], 0
0x18009645c  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x180096462  xorps   xmm0, xmm0
0x180096465  mov     [rbp+57h+var_90], 0
0x18009646d  mov     [rbp+57h+hMem], 0
0x180096475  mov     [rbp+57h+var_BC], 0
0x18009647c  mov     [rbp+57h+var_98], 0
0x180096484  mov     [rbp+57h+HandleId], 0
0x18009648c  mov     [rbp+57h+var_58], eax
0x18009648f  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x180096493  movups  [rbp+57h+var_68], xmm0
0x180096497  cmp     ecx, 10003h
0x18009649d  jnb     loc_180096857
0x1800964a3  lea     ecx, [rax+1]; SubAuthorityCount
0x1800964a6  call    cs:__imp_RtlLengthRequiredSid
0x1800964ac  mov     rcx, gs:60h
0x1800964b5  xor     edx, edx; Flags
0x1800964b7  mov     r8d, eax; Size
0x1800964ba  mov     rcx, [rcx+30h]; HeapHandle
0x1800964be  call    cs:__imp_RtlAllocateHeap
0x1800964c4  mov     r12, rax
0x1800964c7  test    rax, rax
0x1800964ca  jnz     short loc_1800964D6
0x1800964cc  mov     ebx, 0C000009Ah
0x1800964d1  jmp     loc_18009685E
0x1800964d6  or      esi, 0FFFFFFFFh
0x1800964d9  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1800964dd  mov     r8b, 1; SubAuthorityCount
0x1800964e0  mov     [rbp+57h+var_C0], esi
0x1800964e3  mov     rcx, r12; Sid
0x1800964e6  mov     edi, esi
0x1800964e8  call    cs:__imp_RtlInitializeSid
0x1800964ee  xor     edx, edx; SubAuthority
0x1800964f0  mov     rcx, r12; Sid
0x1800964f3  call    cs:__imp_RtlSubAuthoritySid
0x1800964f9  xor     ebx, ebx
0x1800964fb  cmp     cs:?SampDefinedDomainsCount@@3KA, ebx; ulong SampDefinedDomainsCount
0x180096501  mov     dword ptr [rax], 20h ; ' '
0x180096507  jbe     short loc_180096540
0x180096509  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180096510  mov     eax, ebx
0x180096512  imul    rcx, rax, 550h
0x180096519  mov     rdx, [rcx+rdx+8]; Sid2
0x18009651e  mov     rcx, r12; Sid1
0x180096521  call    cs:__imp_RtlEqualSid
0x180096527  test    al, al
0x180096529  mov     ecx, ebx
0x18009652b  cmovz   ecx, edi
0x18009652e  cmovz   esi, ebx
0x180096531  inc     ebx
0x180096533  mov     edi, ecx
0x180096535  cmp     ebx, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x18009653b  jb      short loc_180096509
0x18009653d  mov     [rbp+57h+var_C0], ecx
0x180096540  mov     eax, esi
0x180096542  imul    rcx, rax, 550h
0x180096549  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180096550  mov     [rbp+57h+var_88], rcx
0x180096554  mov     rax, [rcx+rax+8]
0x180096559  mov     [rbp+57h+var_78], rax
0x18009655d  call    ?SampCreate18471Key@@YAJXZ; SampCreate18471Key(void)
0x180096562  mov     ebx, eax
0x180096564  test    eax, eax
0x180096566  js      loc_18009683B
0x18009656c  xor     r13d, r13d
0x18009656f  mov     ecx, edi
0x180096571  call    SampSetTransactionDomain
0x180096576  call    SampAcquireReadLock
0x18009657b  lea     rax, [rbp+57h+HandleId]
0x18009657f  mov     ecx, 3
0x180096584  lea     r15, qword_1800D2E20
0x18009658b  mov     [rsp+0F0h+var_C8], rax
0x180096590  mov     edx, [r15+r13*4]
0x180096594  call    ?SampCreateAccountContext@@YAJW4_SAMP_OBJECT_TYPE@@KEEEPEAPEAU_SAMP_OBJECT@@@Z; SampCreateAccountContext(_SAMP_OBJECT_TYPE,ulong,uchar,uchar,uchar,_SAMP_OBJECT * *)
0x180096599  mov     ebx, eax
0x18009659b  test    eax, eax
0x18009659d  jns     short loc_1800965B7
0x18009659f  call    SampReleaseReadLock
0x1800965a4  cmp     ebx, 0C0000151h
0x1800965aa  jnz     loc_18009683B
0x1800965b0  xor     ebx, ebx
0x1800965b2  jmp     loc_18009682E
0x1800965b7  mov     rcx, [rbp+57h+HandleId]; struct _SAMP_OBJECT *
0x1800965bb  lea     r8, [rbp+57h+var_B8+8]; void ***
0x1800965bf  lea     rdx, [rbp+57h+var_B8]; unsigned int *
0x1800965c3  call    ?SampRetrieveAliasMembers@@YAJPEAU_SAMP_OBJECT@@PEAKPEAPEAPEAX@Z; SampRetrieveAliasMembers(_SAMP_OBJECT *,ulong *,void * * *)
0x1800965c8  mov     rcx, [rbp+57h+HandleId]; HandleId
0x1800965cc  mov     ebx, eax
0x1800965ce  call    SampDeleteContext
0x1800965d3  call    SampReleaseReadLock
0x1800965d8  test    ebx, ebx
0x1800965da  js      loc_18009683B
0x1800965e0  mov     ecx, [r15+r13*4]; Value
0x1800965e4  cmp     ecx, 220h
0x1800965ea  jz      short loc_1800965FB
0x1800965ec  call    ?SampAddAliasTo18471Key@@YAJK@Z; SampAddAliasTo18471Key(ulong)
0x1800965f1  mov     ebx, eax
0x1800965f3  test    eax, eax
0x1800965f5  js      loc_18009683B
0x1800965fb  xor     r15d, r15d
0x1800965fe  cmp     dword ptr [rbp+57h+var_B8], r15d
0x180096602  jbe     loc_180096819
0x180096608  mov     rcx, [rbp+57h+var_B8+8]
0x18009660c  mov     rdx, [rbp+57h+var_78]; PSID
0x180096610  mov     rcx, [rcx+r15*8]; Sid
0x180096614  call    ?SampMatchDomainPrefix@@YAEPEAX0@Z; SampMatchDomainPrefix(void *,void *)
0x180096619  test    al, al
0x18009661b  jz      loc_180096800
0x180096621  mov     rcx, [rbp+57h+var_B8+8]
0x180096625  mov     rcx, [rcx+r15*8]; Sid
0x180096629  call    cs:__imp_RtlSubAuthorityCountSid
0x18009662f  mov     rcx, [rbp+57h+var_B8+8]
0x180096633  movzx   edx, byte ptr [rax]
0x180096636  mov     rcx, [rcx+r15*8]; Sid
0x18009663a  dec     edx; SubAuthority
0x18009663c  call    cs:__imp_RtlSubAuthoritySid
0x180096642  lea     rcx, qword_1800D2E20
0x180096649  mov     ecx, [rcx+r13*4]; Value
0x18009664d  mov     r14d, [rax]
0x180096650  cmp     ecx, 220h
0x180096656  jnz     loc_18009678A
0x18009665c  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180096663  mov     rax, [rbp+57h+var_88]
0x180096667  mov     rcx, [rax+rcx]
0x18009666b  call    SampAcquireWriteLock
0x180096670  mov     ebx, eax
0x180096672  test    eax, eax
0x180096674  js      loc_180096816
0x18009667a  mov     ecx, esi
0x18009667c  call    SampSetTransactionDomain
0x180096681  mov     edx, r14d
0x180096684  lea     rax, [rbp+57h+var_98]
0x180096688  mov     r14d, 2
0x18009668e  mov     [rsp+0F0h+var_C8], rax
0x180096693  mov     ecx, r14d
0x180096696  call    ?SampCreateAccountContext@@YAJW4_SAMP_OBJECT_TYPE@@KEEEPEAPEAU_SAMP_OBJECT@@@Z; SampCreateAccountContext(_SAMP_OBJECT_TYPE,ulong,uchar,uchar,uchar,_SAMP_OBJECT * *)
0x18009669b  mov     ebx, eax
0x18009669d  test    eax, eax
0x18009669f  jns     short loc_1800966BB
0x1800966a1  xor     ecx, ecx
0x1800966a3  call    SampReleaseWriteLock
0x1800966a8  cmp     ebx, 0C0000066h
0x1800966ae  jnz     loc_180096816
0x1800966b4  xor     ebx, ebx
0x1800966b6  jmp     loc_180096800
0x1800966bb  mov     rdi, [rbp+57h+var_98]
0x1800966bf  lea     rdx, [rbp+57h+var_68]
0x1800966c3  mov     rcx, rdi
0x1800966c6  call    SampRetrieveGroupV1Fixed
0x1800966cb  mov     ebx, eax
0x1800966cd  test    eax, eax
0x1800966cf  js      loc_180096763
0x1800966d5  lea     rdx, [rbp+57h+var_68]; struct _SAMP_V1_0A_FIXED_LENGTH_GROUP *
0x1800966d9  mov     byte ptr [rbp+57h+var_58], 1
0x1800966dd  mov     rcx, rdi; struct _SAMP_OBJECT *
0x1800966e0  call    ?SampReplaceGroupV1Fixed@@YAJPEAU_SAMP_OBJECT@@PEAU_SAMP_V1_0A_FIXED_LENGTH_GROUP@@@Z; SampReplaceGroupV1Fixed(_SAMP_OBJECT *,_SAMP_V1_0A_FIXED_LENGTH_GROUP *)
0x1800966e5  mov     ebx, eax
0x1800966e7  test    eax, eax
0x1800966e9  js      short loc_180096763
0x1800966eb  lea     rax, [rbp+57h+var_90]
0x1800966ef  xor     r8d, r8d
0x1800966f2  lea     r9, [rbp+57h+var_80]
0x1800966f6  mov     [rsp+0F0h+var_D0], rax; __int64
0x1800966fb  xor     edx, edx
0x1800966fd  mov     rcx, rdi; struct _SAMP_OBJECT *
0x180096700  call    SampGetAccessAttribute
0x180096705  mov     ebx, eax
0x180096707  test    eax, eax
0x180096709  js      short loc_180096763
0x18009670b  mov     r9, [rbp+57h+var_90]
0x18009670f  lea     rax, [rbp+57h+var_BC]
0x180096713  mov     [rsp+0F0h+var_C8], rax
0x180096718  mov     r8b, 1
0x18009671b  lea     rax, [rbp+57h+hMem]
0x18009671f  mov     edx, r14d
0x180096722  mov     rcx, rdi
0x180096725  mov     [rsp+0F0h+var_D0], rax
0x18009672a  call    ?SampModifyAccountSecurity@@YAJPEAU_SAMP_OBJECT@@W4_SAMP_OBJECT_TYPE@@EPEAXPEAPEAXPEAK@Z; SampModifyAccountSecurity(_SAMP_OBJECT *,_SAMP_OBJECT_TYPE,uchar,void *,void * *,ulong *)
0x18009672f  mov     ebx, eax
0x180096731  test    eax, eax
0x180096733  js      short loc_180096763
0x180096735  mov     r9d, [rbp+57h+var_BC]; unsigned int
0x180096739  xor     edx, edx; unsigned int
0x18009673b  mov     r8, [rbp+57h+hMem]; unsigned __int8 *
0x18009673f  mov     rcx, rdi; struct _SAMP_OBJECT *
0x180096742  call    SampSetAccessAttribute
0x180096747  mov     rcx, [rbp+57h+hMem]; hMem
0x18009674b  mov     ebx, eax
0x18009674d  call    cs:__imp_LocalFree
0x180096753  test    ebx, ebx
0x180096755  js      short loc_180096763
0x180096757  xor     edx, edx
0x180096759  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18009675c  call    SampStoreObjectAttributes
0x180096761  mov     ebx, eax
0x180096763  mov     rcx, rdi; HandleId
0x180096766  call    SampDeleteContext
0x18009676b  xor     ecx, ecx
0x18009676d  call    SampSetTransactionWithinDomain
0x180096772  test    ebx, ebx
0x180096774  js      short loc_180096781
0x180096776  mov     cl, 1
0x180096778  call    SampReleaseWriteLock
0x18009677d  mov     ebx, eax
0x18009677f  jmp     short loc_180096800
0x180096781  xor     ecx, ecx
0x180096783  call    SampReleaseWriteLock
0x180096788  jmp     short loc_180096800
0x18009678a  mov     edx, r14d; ULONG
0x18009678d  call    ?SampCheckMemberUpgradedFor18471@@YAJKK@Z; SampCheckMemberUpgradedFor18471(ulong,ulong)
0x180096792  mov     ebx, eax
0x180096794  test    eax, eax
0x180096796  jns     short loc_180096800
0x180096798  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18009679f  mov     rax, [rbp+57h+var_88]
0x1800967a3  mov     rcx, [rax+rcx]
0x1800967a7  call    SampAcquireWriteLock
0x1800967ac  mov     ebx, eax
0x1800967ae  test    eax, eax
0x1800967b0  js      short loc_180096816
0x1800967b2  mov     ecx, esi
0x1800967b4  call    SampSetTransactionDomain
0x1800967b9  mov     rcx, [rbp+57h+var_B8+8]
0x1800967bd  xor     r8d, r8d
0x1800967c0  mov     rcx, [rcx+r15*8]
0x1800967c4  lea     edx, [r8+1]
0x1800967c8  call    ?SampChangeAccountOperatorAccessToMember@@YAJPEAU_RPC_SID@@W4_SAMP_MEMBERSHIP_DELTA@@1@Z; SampChangeAccountOperatorAccessToMember(_RPC_SID *,_SAMP_MEMBERSHIP_DELTA,_SAMP_MEMBERSHIP_DELTA)
0x1800967cd  mov     ebx, eax
0x1800967cf  test    eax, eax
0x1800967d1  js      short loc_1800967E8
0x1800967d3  lea     rcx, qword_1800D2E20
0x1800967da  mov     edx, r14d; ULONG
0x1800967dd  mov     ecx, [rcx+r13*4]; Value
0x1800967e1  call    ?SampAddMemberRidTo18471Key@@YAJKK@Z; SampAddMemberRidTo18471Key(ulong,ulong)
0x1800967e6  mov     ebx, eax
0x1800967e8  xor     ecx, ecx
0x1800967ea  call    SampSetTransactionWithinDomain
0x1800967ef  test    ebx, ebx
0x1800967f1  js      short loc_18009680F
0x1800967f3  mov     cl, 1
0x1800967f5  call    SampReleaseWriteLock
0x1800967fa  mov     ebx, eax
0x1800967fc  test    eax, eax
0x1800967fe  js      short loc_180096816
0x180096800  inc     r15d
0x180096803  cmp     r15d, dword ptr [rbp+57h+var_B8]
0x180096807  jb      loc_180096608
0x18009680d  jmp     short loc_180096816
0x18009680f  xor     ecx, ecx
0x180096811  call    SampReleaseWriteLock
0x180096816  mov     edi, [rbp+57h+var_C0]
0x180096819  lea     rcx, [rbp+57h+var_B8]; struct _SAMPR_PSID_ARRAY *
0x18009681d  call    ?SamIFree_SAMPR_PSID_ARRAY@@YAXPEAU_SAMPR_PSID_ARRAY@@@Z; SamIFree_SAMPR_PSID_ARRAY(_SAMPR_PSID_ARRAY *)
0x180096822  mov     [rbp+57h+var_B8+8], 0
0x18009682a  test    ebx, ebx
0x18009682c  js      short loc_18009683B
0x18009682e  inc     r13d
0x180096831  cmp     r13d, 5
0x180096835  jb      loc_18009656F
0x18009683b  mov     rcx, gs:60h
0x180096844  mov     r8, r12; P
0x180096847  xor     edx, edx; Flags
0x180096849  mov     rcx, [rcx+30h]; HeapHandle
0x18009684d  call    cs:__imp_RtlFreeHeap
0x180096853  test    ebx, ebx
0x180096855  js      short loc_18009685E
0x180096857  call    ?SampCleanup18471@@YAJXZ; SampCleanup18471(void)
0x18009685c  mov     ebx, eax
0x18009685e  mov     rcx, cs:WPP_GLOBAL_Control
0x180096865  test    dword ptr [rcx+44h], 20000h
0x18009686c  jz      short loc_18009688A
0x18009686e  mov     rcx, [rcx+38h]
0x180096872  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x180096879  mov     edx, 13h
0x18009687e  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x180096882  mov     r9d, ebx
0x180096885  call    WPP_SF_Dd
0x18009688a  mov     eax, ebx
0x18009688c  mov     rcx, [rbp+57h+var_50]
0x180096890  xor     rcx, rsp; StackCookie
0x180096893  call    __security_check_cookie
0x180096898  add     rsp, 0B8h
0x18009689f  pop     r15
0x1800968a1  pop     r14
0x1800968a3  pop     r13
0x1800968a5  pop     r12
  ... truncated ...
```
