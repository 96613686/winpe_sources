# SampChangeAccountOperatorAccessToMember(_RPC_SID *,_SAMP_MEMBERSHIP_DELTA,_SAMP_MEMBERSHIP_DELTA)

- ea: `0x1800aa648`
- end: `0x1800aa9f2`
- name: `?SampChangeAccountOperatorAccessToMember@@YAJPEAU_RPC_SID@@W4_SAMP_MEMBERSHIP_DELTA@@1@Z`
- size: `938`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180034520`
- `0x180034b6c`
- `0x18003526c`
- `0x18009642c`

## callees

- `0x1800022a0`
- `0x180005a80`
- `0x1800066f0`
- `0x180011810`
- `0x1800167a0`
- `0x180021460`
- `0x180022440`
- `0x1800243e0`
- `0x180027e24`
- `0x180027e70`
- `0x18002cd80`
- `0x18003cd20`
- `0x180063160`
- `0x1800631a8`
- `0x180064050`
- `0x18008b62c`
- `0x1800aa648`
- `0x1800aad08`

## import_xrefs

- `ntdll!RtlDeleteSecurityObject` at `0x1800aa903`
- `ntdll!RtlDeleteSecurityObject` at `0x1800aa903`
- `ntdll!RtlEqualSid` at `0x1800aa721`
- `ntdll!RtlEqualSid` at `0x1800aa721`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa95c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa997`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa95c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa997`

## pseudocode

```c
__int64 __fastcall SampChangeAccountOperatorAccessToMember(void *a1, unsigned int a2, unsigned int a3)
{
  unsigned int v3; // r12d
  int AccountContext; // ebx
  PUNICODE_STRING v7; // rcx
  __int64 v8; // rdx
  unsigned int PrimaryDomainStart; // eax
  unsigned int v10; // edx
  unsigned int v11; // edi
  __int64 v12; // r8
  BOOLEAN v13; // al
  unsigned int v14; // ecx
  unsigned int v15; // edi
  struct _SAMP_OBJECT *v16; // r14
  int v17; // esi
  char v18; // al
  int v19; // edi
  char v20; // cl
  int v21; // eax
  unsigned int v22; // r15d
  __int64 v23; // r8
  __int64 i; // rdi
  unsigned int v25; // edi
  int v27; // [rsp+34h] [rbp-35h] BYREF
  unsigned int v28; // [rsp+38h] [rbp-31h] BYREF
  PVOID HandleId; // [rsp+40h] [rbp-29h]
  unsigned int v30; // [rsp+48h] [rbp-21h] BYREF
  unsigned int v31; // [rsp+4Ch] [rbp-1Dh]
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+50h] [rbp-19h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-11h] BYREF
  PSID Sid1; // [rsp+60h] [rbp-9h]
  __int64 v35; // [rsp+68h] [rbp-1h] BYREF
  __int128 v36; // [rsp+70h] [rbp+7h] BYREF
  int v37; // [rsp+80h] [rbp+17h]

  v3 = 0;
  Sid1 = 0;
  hMem = 0;
  LODWORD(HandleId) = 0;
  v28 = 0;
  v37 = 0;
  v27 = 0;
  v36 = 0;
  ObjectDescriptor = 0;
  v35 = 0;
  v30 = 0;
  v31 = SampDefinedDomainsCount;
  AccountContext = SampSplitSid(a1);
  if ( AccountContext >= 0 )
  {
    PrimaryDomainStart = SampDsGetPrimaryDomainStart();
    v10 = SampDefinedDomainsCount;
    v11 = PrimaryDomainStart;
    if ( PrimaryDomainStart < SampDefinedDomainsCount )
    {
      do
      {
        v12 = 1360LL * v11;
        if ( (*(_BYTE *)(*(_QWORD *)((char *)SampDefinedDomains + v12) + 192LL) & 2) == 0 )
        {
          v13 = RtlEqualSid(Sid1, *(PSID *)((char *)SampDefinedDomains + v12 + 8));
          v10 = SampDefinedDomainsCount;
          if ( v13 )
            break;
        }
        ++v11;
      }
      while ( v11 < v10 );
      if ( v11 < v10 )
      {
        v14 = SampTransactionDomainIndexGlobal;
        if ( v11 != SampTransactionDomainIndexGlobal )
        {
          SampSetTransactionWithinDomain(0);
          v31 = SampTransactionDomainIndexGlobal;
          SampSetTransactionDomain(v11);
          v14 = SampTransactionDomainIndexGlobal;
        }
        v15 = (unsigned int)HandleId;
        AccountContext = SampLookupAccountName(v14, (unsigned int)HandleId, 0, (enum _SAMP_OBJECT_TYPE *)&v27);
        if ( AccountContext >= 0 )
        {
          if ( v27 == 2 )
          {
            HandleId = 0;
            AccountContext = SampCreateAccountContext(2, v15);
            if ( AccountContext >= 0 )
            {
              v16 = (struct _SAMP_OBJECT *)HandleId;
              AccountContext = SampRetrieveGroupV1Fixed(HandleId, &v36);
              if ( AccountContext >= 0 )
              {
                v17 = (_BYTE)v37 != 0;
                if ( BYTE1(v37) )
                  ++v17;
                if ( a2 )
                {
                  v3 = 1;
                  v19 = v17;
                  if ( a2 == 2 )
                  {
                    if ( (_BYTE)v37 )
                    {
                      LOBYTE(v37) = v37 - 1;
                      if ( !(_BYTE)v37 )
                      {
                        v19 = v17 - 1;
                        v3 = 2;
                      }
                    }
                  }
                }
                else
                {
                  v18 = v37 + 1;
                  v19 = v17 + 1;
                  LOBYTE(v37) = v18;
                  if ( v18 != 1 )
                    v19 = v17;
                  LOBYTE(v3) = v18 != 1;
                }
                if ( a3 )
                {
                  v22 = 1;
                  if ( a3 == 2 )
                  {
                    if ( BYTE1(v37) )
                    {
                      if ( !--BYTE1(v37) )
                      {
                        --v19;
                        v22 = 2;
                      }
                    }
                  }
                }
                else
                {
                  v20 = BYTE1(v37) + 1;
                  v21 = v19 + 1;
                  BYTE1(v37) = v20;
                  if ( v20 != 1 )
                    v21 = v19;
                  v19 = v21;
                  v22 = v20 != 1;
                }
                AccountContext = SampReplaceGroupV1Fixed(v16, (struct _SAMP_V1_0A_FIXED_LENGTH_GROUP *)&v36);
                if ( AccountContext >= 0 )
                {
                  if ( (v19 != 0) == (v17 != 0)
                    || (AccountContext = SampGetAccessAttribute(v16, (__int64)&v35), AccountContext >= 0)
                    && (LOBYTE(v23) = v19 != 0,
                        AccountContext = SampModifyAccountSecurity(v16, 2, v23, v35, &ObjectDescriptor, &v30),
                        AccountContext >= 0)
                    && (AccountContext = SampSetAccessAttribute(v16, 0, (unsigned __int8 *)ObjectDescriptor, v30),
                        RtlDeleteSecurityObject(&ObjectDescriptor),
                        AccountContext >= 0) )
                  {
                    if ( v3 == 1 && v22 == 1 )
                      goto LABEL_48;
                    AccountContext = SampRetrieveGroupMembers(v16, &v28, (unsigned int **)&hMem);
                    if ( AccountContext >= 0 )
                    {
                      for ( i = 0; (unsigned int)i < v28; i = (unsigned int)(i + 1) )
                      {
                        AccountContext = SampChangeOperatorAccessToUser(*((unsigned int *)hMem + i), v3, v22);
                        if ( AccountContext < 0 )
                          break;
                      }
                      LocalFree(hMem);
                      if ( AccountContext >= 0 )
LABEL_48:
                        AccountContext = SampStoreObjectAttributes(v16);
                    }
                  }
                }
              }
              SampDeleteContext(v16);
            }
          }
          else if ( v27 == 4 )
          {
            AccountContext = SampChangeOperatorAccessToUser(v15, a2, a3);
          }
          else
          {
            AccountContext = 0;
          }
        }
        v25 = v31;
        if ( v31 != SampDefinedDomainsCount )
        {
          SampSetTransactionWithinDomain(0);
          SampSetTransactionDomain(v25);
        }
      }
    }
    LocalFree(Sid1);
    v7 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v8 = 136;
      goto LABEL_54;
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v8 = 135;
LABEL_54:
      WPP_SF_Dd(
        v7[3].Buffer,
        v8,
        WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
        (unsigned int)AccountContext,
        AccountContext);
    }
  }
  return (unsigned int)AccountContext;
}

```

## disassembly

```asm
0x1800aa648  mov     [rsp-8+arg_18], rbx
0x1800aa64d  push    rbp
0x1800aa64e  push    rsi
0x1800aa64f  push    rdi
0x1800aa650  push    r12
0x1800aa652  push    r13
0x1800aa654  push    r14
0x1800aa656  push    r15
0x1800aa658  lea     rbp, [rsp-27h]
0x1800aa65d  sub     rsp, 90h
0x1800aa664  mov     rax, cs:__security_cookie
0x1800aa66b  xor     rax, rsp
0x1800aa66e  mov     [rbp+57h+var_38], rax
0x1800aa672  mov     esi, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x1800aa678  xor     r12d, r12d
0x1800aa67b  mov     r13d, r8d
0x1800aa67e  mov     [rbp+57h+Sid1], r12
0x1800aa682  mov     r15d, edx
0x1800aa685  mov     [rbp+57h+hMem], r12
0x1800aa689  xorps   xmm0, xmm0
0x1800aa68c  mov     dword ptr [rbp+57h+HandleId], r12d
0x1800aa690  xor     eax, eax
0x1800aa692  mov     [rbp+57h+var_88], r12d
0x1800aa696  lea     r8, [rbp+57h+HandleId]
0x1800aa69a  mov     [rbp+57h+var_40], eax
0x1800aa69d  lea     rdx, [rbp+57h+Sid1]
0x1800aa6a1  mov     [rbp+57h+var_8C], r12d
0x1800aa6a5  movups  [rbp+57h+var_50], xmm0
0x1800aa6a9  mov     [rbp+57h+ObjectDescriptor], r12
0x1800aa6ad  mov     [rbp+57h+var_58], r12
0x1800aa6b1  mov     [rbp+57h+var_78], r12d
0x1800aa6b5  mov     [rbp+57h+var_74], esi
0x1800aa6b8  call    SampSplitSid
0x1800aa6bd  mov     ebx, eax
0x1800aa6bf  test    eax, eax
0x1800aa6c1  jns     short loc_1800AA6E1
0x1800aa6c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa6ca  test    dword ptr [rcx+44h], 20000h
0x1800aa6d1  jz      loc_1800AA9C9
0x1800aa6d7  mov     edx, 87h
0x1800aa6dc  jmp     loc_1800AA9B2
0x1800aa6e1  call    SampDsGetPrimaryDomainStart
0x1800aa6e6  mov     edx, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x1800aa6ec  mov     edi, eax
0x1800aa6ee  cmp     eax, edx
0x1800aa6f0  jnb     loc_1800AA993
0x1800aa6f6  mov     esi, 1
0x1800aa6fb  mov     ecx, edi
0x1800aa6fd  imul    r8, rcx, 550h
0x1800aa704  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800aa70b  mov     rax, [r8+rcx]
0x1800aa70f  test    byte ptr [rax+0C0h], 2
0x1800aa716  jnz     short loc_1800AA731
0x1800aa718  mov     rdx, [r8+rcx+8]; Sid2
0x1800aa71d  mov     rcx, [rbp+57h+Sid1]; Sid1
0x1800aa721  call    cs:__imp_RtlEqualSid
0x1800aa727  mov     edx, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x1800aa72d  test    al, al
0x1800aa72f  jnz     short loc_1800AA737
0x1800aa731  add     edi, esi
0x1800aa733  cmp     edi, edx
0x1800aa735  jb      short loc_1800AA6FB
0x1800aa737  cmp     edi, edx
0x1800aa739  jnb     loc_1800AA993
0x1800aa73f  mov     ecx, cs:?SampTransactionDomainIndexGlobal@@3KA; ulong SampTransactionDomainIndexGlobal
0x1800aa745  cmp     edi, ecx
0x1800aa747  jz      short loc_1800AA766
0x1800aa749  xor     ecx, ecx
0x1800aa74b  call    SampSetTransactionWithinDomain
0x1800aa750  mov     eax, cs:?SampTransactionDomainIndexGlobal@@3KA; ulong SampTransactionDomainIndexGlobal
0x1800aa756  mov     ecx, edi
0x1800aa758  mov     [rbp+57h+var_74], eax
0x1800aa75b  call    SampSetTransactionDomain
0x1800aa760  mov     ecx, cs:?SampTransactionDomainIndexGlobal@@3KA; unsigned int
0x1800aa766  mov     edi, dword ptr [rbp+57h+HandleId]
0x1800aa769  lea     r9, [rbp+57h+var_8C]; enum _SAMP_OBJECT_TYPE *
0x1800aa76d  mov     edx, edi; unsigned int
0x1800aa76f  xor     r8d, r8d; struct _UNICODE_STRING *
0x1800aa772  call    ?SampLookupAccountName@@YAJKKPEAU_UNICODE_STRING@@PEAW4_SAMP_OBJECT_TYPE@@@Z; SampLookupAccountName(ulong,ulong,_UNICODE_STRING *,_SAMP_OBJECT_TYPE *)
0x1800aa777  mov     ebx, eax
0x1800aa779  test    eax, eax
0x1800aa77b  js      loc_1800AA97A
0x1800aa781  cmp     [rbp+57h+var_8C], 2
0x1800aa785  jz      short loc_1800AA7A9
0x1800aa787  cmp     [rbp+57h+var_8C], 4
0x1800aa78b  jz      short loc_1800AA795
0x1800aa78d  mov     ebx, r12d
0x1800aa790  jmp     loc_1800AA97A
0x1800aa795  mov     r8d, r13d
0x1800aa798  mov     edx, r15d
0x1800aa79b  mov     ecx, edi
0x1800aa79d  call    ?SampChangeOperatorAccessToUser@@YAJKW4_SAMP_MEMBERSHIP_DELTA@@0@Z; SampChangeOperatorAccessToUser(ulong,_SAMP_MEMBERSHIP_DELTA,_SAMP_MEMBERSHIP_DELTA)
0x1800aa7a2  mov     ebx, eax
0x1800aa7a4  jmp     loc_1800AA97A
0x1800aa7a9  lea     rax, [rbp+57h+HandleId]
0x1800aa7ad  mov     [rbp+57h+HandleId], r12
0x1800aa7b1  mov     edx, edi
0x1800aa7b3  mov     [rsp+0C0h+var_98], rax
0x1800aa7b8  mov     ecx, 2
0x1800aa7bd  call    ?SampCreateAccountContext@@YAJW4_SAMP_OBJECT_TYPE@@KEEEPEAPEAU_SAMP_OBJECT@@@Z; SampCreateAccountContext(_SAMP_OBJECT_TYPE,ulong,uchar,uchar,uchar,_SAMP_OBJECT * *)
0x1800aa7c2  mov     ebx, eax
0x1800aa7c4  test    eax, eax
0x1800aa7c6  js      loc_1800AA97A
0x1800aa7cc  mov     r14, [rbp+57h+HandleId]
0x1800aa7d0  lea     rdx, [rbp+57h+var_50]
0x1800aa7d4  mov     rcx, r14
0x1800aa7d7  call    SampRetrieveGroupV1Fixed
0x1800aa7dc  mov     ebx, eax
0x1800aa7de  test    eax, eax
0x1800aa7e0  js      loc_1800AA972
0x1800aa7e6  mov     al, byte ptr [rbp+57h+var_40]
0x1800aa7e9  mov     esi, r12d
0x1800aa7ec  mov     cl, byte ptr [rbp+57h+var_40+1]
0x1800aa7ef  test    al, al
0x1800aa7f1  mov     edx, 1
0x1800aa7f6  cmovnz  esi, edx
0x1800aa7f9  test    cl, cl
0x1800aa7fb  jz      short loc_1800AA7FF
0x1800aa7fd  add     esi, edx
0x1800aa7ff  test    r15d, r15d
0x1800aa802  jnz     short loc_1800AA817
0x1800aa804  add     al, dl
0x1800aa806  lea     edi, [rsi+1]
0x1800aa809  cmp     al, dl
0x1800aa80b  mov     byte ptr [rbp+57h+var_40], al
0x1800aa80e  cmovnz  edi, esi
0x1800aa811  setnz   r12b
0x1800aa815  jmp     short loc_1800AA833
0x1800aa817  mov     r12d, edx
0x1800aa81a  mov     edi, esi
0x1800aa81c  cmp     r15d, 2
0x1800aa820  jnz     short loc_1800AA833
0x1800aa822  test    al, al
0x1800aa824  jz      short loc_1800AA833
0x1800aa826  add     al, 0FFh
0x1800aa828  mov     byte ptr [rbp+57h+var_40], al
0x1800aa82b  jnz     short loc_1800AA833
0x1800aa82d  lea     edi, [rsi-1]
0x1800aa830  mov     r12d, r15d
0x1800aa833  test    r13d, r13d
0x1800aa836  jnz     short loc_1800AA852
0x1800aa838  add     cl, dl
0x1800aa83a  lea     eax, [rdi+1]
0x1800aa83d  cmp     cl, dl
0x1800aa83f  mov     byte ptr [rbp+57h+var_40+1], cl
0x1800aa842  cmovnz  eax, edi
0x1800aa845  xor     r15d, r15d
0x1800aa848  cmp     cl, dl
0x1800aa84a  mov     edi, eax
0x1800aa84c  setnz   r15b
0x1800aa850  jmp     short loc_1800AA86C
0x1800aa852  mov     r15d, edx
0x1800aa855  cmp     r13d, 2
0x1800aa859  jnz     short loc_1800AA86C
0x1800aa85b  test    cl, cl
0x1800aa85d  jz      short loc_1800AA86C
0x1800aa85f  add     cl, 0FFh
0x1800aa862  mov     byte ptr [rbp+57h+var_40+1], cl
0x1800aa865  jnz     short loc_1800AA86C
0x1800aa867  dec     edi
0x1800aa869  mov     r15d, r13d
0x1800aa86c  lea     rdx, [rbp+57h+var_50]; struct _SAMP_V1_0A_FIXED_LENGTH_GROUP *
0x1800aa870  mov     rcx, r14; struct _SAMP_OBJECT *
0x1800aa873  call    ?SampReplaceGroupV1Fixed@@YAJPEAU_SAMP_OBJECT@@PEAU_SAMP_V1_0A_FIXED_LENGTH_GROUP@@@Z; SampReplaceGroupV1Fixed(_SAMP_OBJECT *,_SAMP_V1_0A_FIXED_LENGTH_GROUP *)
0x1800aa878  mov     ebx, eax
0x1800aa87a  test    eax, eax
0x1800aa87c  js      loc_1800AA972
0x1800aa882  xor     ecx, ecx
0x1800aa884  test    edi, edi
0x1800aa886  setnz   cl
0x1800aa889  xor     eax, eax
0x1800aa88b  test    esi, esi
0x1800aa88d  setnz   al
0x1800aa890  cmp     ecx, eax
0x1800aa892  jz      short loc_1800AA90D
0x1800aa894  lea     rax, [rbp+57h+var_58]
0x1800aa898  xor     r8d, r8d
0x1800aa89b  lea     r9, [rbp+57h+HandleId]
0x1800aa89f  mov     [rsp+0C0h+var_A0], rax; __int64
0x1800aa8a4  xor     edx, edx
0x1800aa8a6  mov     rcx, r14; struct _SAMP_OBJECT *
0x1800aa8a9  call    SampGetAccessAttribute
0x1800aa8ae  mov     ebx, eax
0x1800aa8b0  test    eax, eax
0x1800aa8b2  js      loc_1800AA972
0x1800aa8b8  mov     r9, [rbp+57h+var_58]
0x1800aa8bc  lea     rax, [rbp+57h+var_78]
0x1800aa8c0  mov     [rsp+0C0h+var_98], rax
0x1800aa8c5  test    edi, edi
0x1800aa8c7  lea     rax, [rbp+57h+ObjectDescriptor]
0x1800aa8cb  mov     edx, 2
0x1800aa8d0  setnz   r8b
0x1800aa8d4  mov     [rsp+0C0h+var_A0], rax
0x1800aa8d9  mov     rcx, r14
0x1800aa8dc  call    ?SampModifyAccountSecurity@@YAJPEAU_SAMP_OBJECT@@W4_SAMP_OBJECT_TYPE@@EPEAXPEAPEAXPEAK@Z; SampModifyAccountSecurity(_SAMP_OBJECT *,_SAMP_OBJECT_TYPE,uchar,void *,void * *,ulong *)
0x1800aa8e1  mov     ebx, eax
0x1800aa8e3  test    eax, eax
0x1800aa8e5  js      loc_1800AA972
0x1800aa8eb  mov     r9d, [rbp+57h+var_78]; unsigned int
0x1800aa8ef  xor     edx, edx; unsigned int
0x1800aa8f1  mov     r8, [rbp+57h+ObjectDescriptor]; unsigned __int8 *
0x1800aa8f5  mov     rcx, r14; struct _SAMP_OBJECT *
0x1800aa8f8  call    SampSetAccessAttribute
0x1800aa8fd  lea     rcx, [rbp+57h+ObjectDescriptor]; ObjectDescriptor
0x1800aa901  mov     ebx, eax
0x1800aa903  call    cs:__imp_RtlDeleteSecurityObject
0x1800aa909  test    ebx, ebx
0x1800aa90b  js      short loc_1800AA972
0x1800aa90d  mov     esi, 1
0x1800aa912  cmp     r12d, esi
0x1800aa915  jnz     short loc_1800AA91C
0x1800aa917  cmp     r15d, esi
0x1800aa91a  jz      short loc_1800AA966
0x1800aa91c  lea     r8, [rbp+57h+hMem]; unsigned int **
0x1800aa920  mov     rcx, r14; struct _SAMP_OBJECT *
0x1800aa923  lea     rdx, [rbp+57h+var_88]; unsigned int *
0x1800aa927  call    ?SampRetrieveGroupMembers@@YAJPEAU_SAMP_OBJECT@@PEAKPEAPEAK@Z; SampRetrieveGroupMembers(_SAMP_OBJECT *,ulong *,ulong * *)
0x1800aa92c  mov     ebx, eax
0x1800aa92e  test    eax, eax
0x1800aa930  js      short loc_1800AA972
0x1800aa932  xor     edi, edi
0x1800aa934  cmp     [rbp+57h+var_88], edi
0x1800aa937  jbe     short loc_1800AA958
0x1800aa939  mov     rcx, [rbp+57h+hMem]
0x1800aa93d  mov     r8d, r15d
0x1800aa940  mov     edx, r12d
0x1800aa943  mov     ecx, [rcx+rdi*4]
0x1800aa946  call    ?SampChangeOperatorAccessToUser@@YAJKW4_SAMP_MEMBERSHIP_DELTA@@0@Z; SampChangeOperatorAccessToUser(ulong,_SAMP_MEMBERSHIP_DELTA,_SAMP_MEMBERSHIP_DELTA)
0x1800aa94b  mov     ebx, eax
0x1800aa94d  test    eax, eax
0x1800aa94f  js      short loc_1800AA958
0x1800aa951  add     edi, esi
0x1800aa953  cmp     edi, [rbp+57h+var_88]
0x1800aa956  jb      short loc_1800AA939
0x1800aa958  mov     rcx, [rbp+57h+hMem]; hMem
0x1800aa95c  call    cs:__imp_LocalFree
0x1800aa962  test    ebx, ebx
0x1800aa964  js      short loc_1800AA972
0x1800aa966  xor     edx, edx
0x1800aa968  mov     rcx, r14; struct _SAMP_OBJECT *
0x1800aa96b  call    SampStoreObjectAttributes
0x1800aa970  mov     ebx, eax
0x1800aa972  mov     rcx, r14; HandleId
0x1800aa975  call    SampDeleteContext
0x1800aa97a  mov     edi, [rbp+57h+var_74]
0x1800aa97d  cmp     edi, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x1800aa983  jz      short loc_1800AA993
0x1800aa985  xor     ecx, ecx
0x1800aa987  call    SampSetTransactionWithinDomain
0x1800aa98c  mov     ecx, edi
0x1800aa98e  call    SampSetTransactionDomain
0x1800aa993  mov     rcx, [rbp+57h+Sid1]; hMem
0x1800aa997  call    cs:__imp_LocalFree
0x1800aa99d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa9a4  test    dword ptr [rcx+44h], 20000h
0x1800aa9ab  jz      short loc_1800AA9C9
0x1800aa9ad  mov     edx, 88h
0x1800aa9b2  mov     rcx, [rcx+38h]
0x1800aa9b6  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800aa9bd  mov     r9d, ebx
0x1800aa9c0  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1800aa9c4  call    WPP_SF_Dd
0x1800aa9c9  mov     eax, ebx
0x1800aa9cb  mov     rcx, [rbp+57h+var_38]
0x1800aa9cf  xor     rcx, rsp; StackCookie
0x1800aa9d2  call    __security_check_cookie
0x1800aa9d7  mov     rbx, [rsp+0C0h+arg_18]
0x1800aa9df  add     rsp, 90h
0x1800aa9e6  pop     r15
0x1800aa9e8  pop     r14
0x1800aa9ea  pop     r13
0x1800aa9ec  pop     r12
0x1800aa9ee  pop     rdi
0x1800aa9ef  pop     rsi
0x1800aa9f0  pop     rbp
0x1800aa9f1  retn
```
