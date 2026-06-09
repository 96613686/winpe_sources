# SampRemoveAccountFromAllAliases(void *,_DSNAME *,__int64,uchar,void *,ulong *,ulong * *)

- ea: `0x180034b6c`
- end: `0x180034f9e`
- name: `?SampRemoveAccountFromAllAliases@@YAJPEAXPEAU_DSNAME@@_JE0PEAKPEAPEAK@Z`
- size: `1074`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, struct _DSNAME *@<rdx>, __int64@<r8>, unsigned __int8@<r9b>, void *, unsigned int *, unsigned int **)`
- caller_count: `3`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180058f40`
- `0x180064380`
- `0x1800a6810`

## callees

- `0x1800022a0`
- `0x1800066f0`
- `0x180015c50`
- `0x1800213d0`
- `0x180021460`
- `0x180022440`
- `0x180027e24`
- `0x180027e70`
- `0x180034758`
- `0x1800348f4`
- `0x180034b6c`
- `0x180077114`
- `0x1800775fc`
- `0x1800aa648`
- `0x1800aeafc`

## import_xrefs

- `ntdll!NtClose` at `0x180034f25`
- `ntdll!NtClose` at `0x180034f25`
- `ntdll!RtlpNtQueryValueKey` at `0x180034dd0`
- `ntdll!RtlpNtQueryValueKey` at `0x180034e15`
- `ntdll!RtlpNtQueryValueKey` at `0x180034dd0`
- `ntdll!RtlpNtQueryValueKey` at `0x180034e15`
- `ntdll!RtlpNtOpenKey` at `0x180034d92`
- `ntdll!RtlpNtOpenKey` at `0x180034d92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034c53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034deb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034c53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034deb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034f1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034f1b`

## pseudocode

```c
__int64 __fastcall SampRemoveAccountFromAllAliases(
        void *a1,
        struct _DSNAME *a2,
        __int64 a3,
        char a4,
        _BYTE *a5,
        unsigned int *a6,
        unsigned int **a7)
{
  _BYTE *v7; // rbx
  unsigned int **v10; // r15
  unsigned int *v11; // r13
  int MembershipsDs; // edi
  int v13; // eax
  unsigned int *v14; // rax
  PUNICODE_STRING v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned int v18; // esi
  PVOID **v19; // rbx
  NTSTATUS v20; // eax
  unsigned int *v21; // rax
  unsigned int *v22; // rbx
  __int64 v23; // r8
  __int64 v24; // r9
  ULONG i; // r15d
  struct _SAMP_OBJECT *v26; // rsi
  int Unused; // [rsp+28h] [rbp-A1h]
  __int64 Unuseda; // [rsp+28h] [rbp-A1h]
  ULONG Type; // [rsp+58h] [rbp-71h] BYREF
  ULONG v31; // [rsp+5Ch] [rbp-6Dh] BYREF
  PVOID HandleId; // [rsp+60h] [rbp-69h] BYREF
  HANDLE KeyHandle; // [rsp+68h] [rbp-61h] BYREF
  __int64 v34; // [rsp+70h] [rbp-59h] BYREF
  __int64 v35; // [rsp+78h] [rbp-51h] BYREF
  struct _UNICODE_STRING v36; // [rsp+80h] [rbp-49h] BYREF
  struct _UNICODE_STRING v37; // [rsp+90h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-29h] BYREF
  ULONG DataLength; // [rsp+120h] [rbp+57h] BYREF
  int v40; // [rsp+124h] [rbp+5Bh]
  PVOID v41; // [rsp+128h] [rbp+5Fh] BYREF

  v40 = HIDWORD(a2);
  v7 = a5;
  v35 = 0;
  KeyHandle = 0;
  v41 = 0;
  Type = 0;
  DataLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v37 = 0;
  v36 = 0;
  if ( a5 && (a5[192] & 2) != 0 )
  {
    v10 = a7;
    v11 = a6;
    LODWORD(v41) = 0;
    v34 = 0;
    if ( a4 )
    {
      *a7 = 0;
      *v11 = 0;
    }
    MembershipsDs = SampExtGetMembershipsDs(&v35, a2, *((_QWORD *)v7 + 22), 2, &v41, &v34);
    if ( MembershipsDs >= 0 )
    {
      v13 = (int)v41;
      if ( (_DWORD)v41 )
      {
        v31 = 0;
        HandleId = 0;
        if ( a4 )
        {
          v14 = (unsigned int *)LocalAlloc(0x40u, 4LL * (unsigned int)v41);
          *v10 = v14;
          if ( !v14 )
          {
            v15 = WPP_GLOBAL_Control;
            MembershipsDs = -1073741670;
            if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            {
              v16 = 41;
              v17 = 3221225626LL;
LABEL_48:
              WPP_SF_Dd(v15[3].Buffer, v16, &WPP_799c13f926ef3db95a69a5604490dfde_Traceguids, v17, MembershipsDs);
              return (unsigned int)MembershipsDs;
            }
            return (unsigned int)MembershipsDs;
          }
          v13 = (int)v41;
        }
        v18 = 0;
        if ( v13 )
        {
          do
          {
            MembershipsDs = SampSplitSid((void *)(*(_QWORD *)(v34 + 8LL * v18) + 24LL), 0, &v31);
            if ( MembershipsDs >= 0 )
            {
              SampSetTransactionWithinDomain(0);
              LOBYTE(Unused) = 1;
              MembershipsDs = SampOpenAccount(3, v7, 2, v31, Unused, &HandleId);
              if ( MembershipsDs >= 0 )
              {
                v19 = (PVOID **)HandleId;
                SampExtRemoveMembershipAttributeDs(*((_QWORD *)HandleId + 22), 3, 3, v35, 0);
                SampDeleteContext(v19);
                v7 = a5;
                if ( a4 )
                {
                  (*v10)[v18] = v31;
                  ++*v11;
                }
              }
            }
            ++v18;
          }
          while ( v18 < (unsigned int)v41 );
        }
      }
    }
  }
  else
  {
    HandleId = 0;
    MembershipsDs = SampBuildAliasMembersKeyName(a1, &v37, &v36);
    if ( MembershipsDs >= 0 )
    {
      ObjectAttributes.RootDirectory = SampKey;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &v36;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v20 = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
      MembershipsDs = v20;
      if ( v20 == -1073741766 || v20 == -1073741772 )
      {
        MembershipsDs = 0;
        if ( a4 )
        {
          *a6 = 0;
          *a7 = 0;
        }
      }
      else if ( v20 >= 0 )
      {
        DataLength = 0;
        MembershipsDs = RtlpNtQueryValueKey(KeyHandle, &Type, 0, &DataLength, 0);
        if ( MembershipsDs == -2147483643 )
        {
          v21 = (unsigned int *)LocalAlloc(0x40u, DataLength);
          v22 = v21;
          if ( v21 )
          {
            MembershipsDs = RtlpNtQueryValueKey(KeyHandle, 0, v21, &DataLength, 0);
            if ( MembershipsDs >= 0 )
            {
              for ( i = 0; i < Type; ++i )
              {
                if ( a4 )
                {
                  if ( v22[i] == 544 )
                    SampChangeAccountOperatorAccessToMember(a1, 2u, 1u);
                  SampSetTransactionWithinDomain(0);
                  LOBYTE(Unuseda) = 1;
                  MembershipsDs = SampOpenAccount(3, a5, 2, v22[i], Unuseda, &v41);
                  if ( MembershipsDs < 0 )
                    goto LABEL_40;
                  SampDeleteContext((PVOID **)v41);
                }
                MembershipsDs = SampCreateAccountContext(3, v22[i], v23, v24, Unuseda, (__int64)&HandleId);
                if ( MembershipsDs < 0 )
                  goto LABEL_39;
                v26 = (struct _SAMP_OBJECT *)HandleId;
                MembershipsDs = SampRemoveAccountFromAlias((struct _SAMP_OBJECT *)HandleId, 3u, a1, 0, 0);
                if ( MembershipsDs >= 0 )
                  MembershipsDs = SampStoreObjectAttributes(v26);
                SampDeleteContext((PVOID **)v26);
                if ( MembershipsDs < 0 )
                  goto LABEL_39;
              }
              MembershipsDs = SampDeleteAliasMembershipKeysForAccount(a1);
            }
LABEL_39:
            if ( a4 )
            {
LABEL_40:
              *a6 = Type;
              *a7 = v22;
            }
            else
            {
              LocalFree(v22);
            }
          }
          else
          {
            MembershipsDs = -1073741670;
          }
        }
        NtClose(KeyHandle);
      }
      SampFreeUnicodeString(&v37);
      SampFreeUnicodeString(&v36);
    }
  }
  v15 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v16 = 42;
    v17 = (unsigned int)MembershipsDs;
    goto LABEL_48;
  }
  return (unsigned int)MembershipsDs;
}

```

## disassembly

```asm
0x180034b6c  mov     rax, rsp
0x180034b6f  mov     [rax+8], rbx
0x180034b73  mov     [rax+18h], r8
0x180034b77  mov     [rax+10h], rdx
0x180034b7b  push    rbp
0x180034b7c  push    rsi
0x180034b7d  push    rdi
0x180034b7e  push    r12
0x180034b80  push    r13
0x180034b82  push    r14
0x180034b84  push    r15
0x180034b86  lea     rbp, [rax-47h]
0x180034b8a  sub     rsp, 0D0h
0x180034b91  mov     rbx, [rbp+3Fh+arg_20]
0x180034b95  xor     r12d, r12d
0x180034b98  mov     [rbp+3Fh+var_90], r12
0x180034b9c  xorps   xmm0, xmm0
0x180034b9f  mov     [rbp+3Fh+KeyHandle], r12
0x180034ba3  xorps   xmm1, xmm1
0x180034ba6  mov     [rbp+3Fh+arg_10], r12
0x180034baa  mov     r14b, r9b
0x180034bad  mov     [rbp+3Fh+Type], r12d
0x180034bb1  mov     r13, rcx
0x180034bb4  mov     [rbp+3Fh+DataLength], r12d
0x180034bb8  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x180034bbc  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x180034bc0  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180034bc4  movups  xmmword ptr [rbp+3Fh+var_78.Length], xmm0
0x180034bc8  movups  xmmword ptr [rbp+3Fh+var_88.Length], xmm1
0x180034bcc  test    rbx, rbx
0x180034bcf  jz      loc_180034D3E
0x180034bd5  test    byte ptr [rbx+0C0h], 2
0x180034bdc  jz      loc_180034D3E
0x180034be2  mov     r15, [rbp+3Fh+arg_30]
0x180034be6  mov     r13, [rbp+3Fh+arg_28]
0x180034bea  mov     dword ptr [rbp+3Fh+arg_10], r12d
0x180034bee  mov     [rbp+3Fh+var_98], r12
0x180034bf2  test    r9b, r9b
0x180034bf5  jz      short loc_180034BFE
0x180034bf7  mov     [r15], r12
0x180034bfa  mov     [r13+0], r12d
0x180034bfe  mov     r8, [rbx+0B0h]
0x180034c05  lea     rax, [rbp+3Fh+var_98]
0x180034c09  mov     [rsp+28h], rax
0x180034c0e  lea     rcx, [rbp+3Fh+var_90]
0x180034c12  lea     rax, [rbp+3Fh+arg_10]
0x180034c16  mov     r9d, 2
0x180034c1c  mov     qword ptr [rsp+100h+Unused], rax
0x180034c21  call    ?SampExtGetMembershipsDs@@YAJPEAPEAU_DSNAME@@KPEAU1@W4__MIDL_drsuapi_0009@@PEAKPEAPEAPEAU1@PEAPEAK3PEAPEAPEAXPEAU_SAMP_USER_ACCOUNT_SETTINGS@@@Z; SampExtGetMembershipsDs(_DSNAME * *,ulong,_DSNAME *,__MIDL_drsuapi_0009,ulong *,_DSNAME * * *,ulong * *,ulong *,void * * *,_SAMP_USER_ACCOUNT_SETTINGS *)
0x180034c26  mov     edi, eax
0x180034c28  test    eax, eax
0x180034c2a  js      loc_180034F55
0x180034c30  mov     eax, dword ptr [rbp+3Fh+arg_10]
0x180034c33  test    eax, eax
0x180034c35  jz      loc_180034F55
0x180034c3b  mov     [rbp+3Fh+var_AC], r12d
0x180034c3f  mov     [rbp+3Fh+HandleId], r12
0x180034c43  test    r14b, r14b
0x180034c46  jz      short loc_180034C8B
0x180034c48  mov     edx, eax
0x180034c4a  mov     ecx, 40h ; '@'; uFlags
0x180034c4f  shl     rdx, 2; uBytes
0x180034c53  call    cs:__imp_LocalAlloc
0x180034c59  mov     [r15], rax
0x180034c5c  test    rax, rax
0x180034c5f  jnz     short loc_180034C88
0x180034c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180034c68  mov     edi, 0C000009Ah
0x180034c6d  test    dword ptr [rcx+44h], 20000h
0x180034c74  jz      loc_180034F81
0x180034c7a  lea     edx, [rax+29h]
0x180034c7d  mov     r9d, 0C000009Ah
0x180034c83  jmp     loc_180034F6D
0x180034c88  mov     eax, dword ptr [rbp+3Fh+arg_10]
0x180034c8b  mov     esi, r12d
0x180034c8e  test    eax, eax
0x180034c90  jz      loc_180034F55
0x180034c96  mov     r12d, 3
0x180034c9c  mov     rax, [rbp+3Fh+var_98]
0x180034ca0  lea     r8, [rbp+3Fh+var_AC]
0x180034ca4  mov     ecx, esi
0x180034ca6  xor     edx, edx
0x180034ca8  mov     rcx, [rax+rcx*8]
0x180034cac  add     rcx, 18h; Src
0x180034cb0  call    SampSplitSid
0x180034cb5  mov     edi, eax
0x180034cb7  test    eax, eax
0x180034cb9  js      short loc_180034D2E
0x180034cbb  xor     ecx, ecx
0x180034cbd  call    SampSetTransactionWithinDomain
0x180034cc2  mov     r9d, [rbp+3Fh+var_AC]
0x180034cc6  lea     rax, [rbp+3Fh+HandleId]
0x180034cca  mov     [rsp+28h], rax
0x180034ccf  mov     r8d, 2
0x180034cd5  mov     rdx, rbx
0x180034cd8  mov     byte ptr [rsp+100h+Unused], 1
0x180034cdd  mov     ecx, r12d
0x180034ce0  call    ?SampOpenAccount@@YAJW4_SAMP_OBJECT_TYPE@@PEAXKKEPEAPEAX@Z; SampOpenAccount(_SAMP_OBJECT_TYPE,void *,ulong,ulong,uchar,void * *)
0x180034ce5  mov     edi, eax
0x180034ce7  test    eax, eax
0x180034ce9  js      short loc_180034D2E
0x180034ceb  mov     rbx, [rbp+3Fh+HandleId]
0x180034cef  mov     r8d, r12d
0x180034cf2  mov     r9, [rbp+3Fh+var_90]
0x180034cf6  mov     edx, r12d
0x180034cf9  mov     qword ptr [rsp+100h+Unused], 0
0x180034d02  mov     rcx, [rbx+0B0h]
0x180034d09  call    ?SampExtRemoveMembershipAttributeDs@@YAJPEAU_DSNAME@@KW4_SAMP_OBJECT_TYPE@@0_J@Z; SampExtRemoveMembershipAttributeDs(_DSNAME *,ulong,_SAMP_OBJECT_TYPE,_DSNAME *,__int64)
0x180034d0e  mov     rcx, rbx; HandleId
0x180034d11  call    SampDeleteContext
0x180034d16  mov     rbx, [rbp+3Fh+arg_20]
0x180034d1a  test    r14b, r14b
0x180034d1d  jz      short loc_180034D2E
0x180034d1f  mov     rax, [r15]
0x180034d22  mov     edx, [rbp+3Fh+var_AC]
0x180034d25  mov     ecx, esi; Sid
0x180034d27  mov     [rax+rcx*4], edx
0x180034d2a  inc     dword ptr [r13+0]
0x180034d2e  inc     esi
0x180034d30  cmp     esi, dword ptr [rbp+3Fh+arg_10]
0x180034d33  jb      loc_180034C9C
0x180034d39  jmp     loc_180034F55
0x180034d3e  lea     r8, [rbp+3Fh+var_88]; struct _UNICODE_STRING *
0x180034d42  mov     [rbp+3Fh+HandleId], r12
0x180034d46  lea     rdx, [rbp+3Fh+var_78]; struct _UNICODE_STRING *
0x180034d4a  call    SampBuildAliasMembersKeyName
0x180034d4f  mov     edi, eax
0x180034d51  test    eax, eax
0x180034d53  js      loc_180034F55
0x180034d59  mov     rax, cs:SampKey
0x180034d60  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x180034d64  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rax
0x180034d68  lea     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x180034d6c  lea     rax, [rbp+3Fh+var_88]
0x180034d70  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x180034d77  xorps   xmm0, xmm0
0x180034d7a  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x180034d7e  xor     r9d, r9d; Unused
0x180034d81  mov     [rbp+3Fh+ObjectAttributes.Attributes], 40h ; '@'
0x180034d88  mov     edx, 20019h; DesiredAccess
0x180034d8d  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180034d92  call    cs:__imp_RtlpNtOpenKey
0x180034d98  mov     edi, eax
0x180034d9a  cmp     eax, 0C000003Ah
0x180034d9f  jz      loc_180034F2D
0x180034da5  cmp     eax, 0C0000034h
0x180034daa  jz      loc_180034F2D
0x180034db0  test    eax, eax
0x180034db2  js      loc_180034F43
0x180034db8  mov     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x180034dbc  lea     r9, [rbp+3Fh+DataLength]; DataLength
0x180034dc0  xor     r8d, r8d; Data
0x180034dc3  mov     [rbp+3Fh+DataLength], r12d
0x180034dc7  lea     rdx, [rbp+3Fh+Type]; Type
0x180034dcb  mov     qword ptr [rsp+100h+Unused], r12; Unused
0x180034dd0  call    cs:__imp_RtlpNtQueryValueKey
0x180034dd6  mov     edi, eax
0x180034dd8  cmp     eax, 80000005h
0x180034ddd  jnz     loc_180034F21
0x180034de3  mov     edx, [rbp+3Fh+DataLength]; uBytes
0x180034de6  mov     ecx, 40h ; '@'; uFlags
0x180034deb  call    cs:__imp_LocalAlloc
0x180034df1  mov     rbx, rax
0x180034df4  test    rax, rax
0x180034df7  jnz     short loc_180034E03
0x180034df9  mov     edi, 0C000009Ah
0x180034dfe  jmp     loc_180034F21
0x180034e03  mov     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x180034e07  lea     r9, [rbp+3Fh+DataLength]; DataLength
0x180034e0b  mov     r8, rbx; Data
0x180034e0e  mov     qword ptr [rsp+100h+Unused], r12; Unused
0x180034e13  xor     edx, edx; Type
0x180034e15  call    cs:__imp_RtlpNtQueryValueKey
0x180034e1b  mov     edi, eax
0x180034e1d  test    eax, eax
0x180034e1f  js      loc_180034F01
0x180034e25  mov     r15d, r12d
0x180034e28  cmp     [rbp+3Fh+Type], r12d
0x180034e2c  jbe     loc_180034EF7
0x180034e32  mov     r12d, 3
0x180034e38  mov     esi, r15d
0x180034e3b  test    r14b, r14b
0x180034e3e  jz      short loc_180034E94
0x180034e40  cmp     dword ptr [rbx+rsi*4], 220h
0x180034e47  jnz     short loc_180034E5A
0x180034e49  mov     edx, 2
0x180034e4e  mov     rcx, r13
0x180034e51  lea     r8d, [rdx-1]
0x180034e55  call    ?SampChangeAccountOperatorAccessToMember@@YAJPEAU_RPC_SID@@W4_SAMP_MEMBERSHIP_DELTA@@1@Z; SampChangeAccountOperatorAccessToMember(_RPC_SID *,_SAMP_MEMBERSHIP_DELTA,_SAMP_MEMBERSHIP_DELTA)
0x180034e5a  xor     ecx, ecx
0x180034e5c  call    SampSetTransactionWithinDomain
0x180034e61  mov     r9d, [rbx+rsi*4]
0x180034e65  lea     rax, [rbp+3Fh+arg_10]
0x180034e69  mov     rdx, [rbp+3Fh+arg_20]
0x180034e6d  mov     r8d, 2
0x180034e73  mov     [rsp+28h], rax
0x180034e78  mov     ecx, r12d
0x180034e7b  mov     byte ptr [rsp+100h+Unused], 1
0x180034e80  call    ?SampOpenAccount@@YAJW4_SAMP_OBJECT_TYPE@@PEAXKKEPEAPEAX@Z; SampOpenAccount(_SAMP_OBJECT_TYPE,void *,ulong,ulong,uchar,void * *)
0x180034e85  mov     edi, eax
0x180034e87  test    eax, eax
0x180034e89  js      short loc_180034F06
0x180034e8b  mov     rcx, [rbp+3Fh+arg_10]; HandleId
0x180034e8f  call    SampDeleteContext
0x180034e94  mov     edx, [rbx+rsi*4]
0x180034e97  lea     rax, [rbp+3Fh+HandleId]
0x180034e9b  mov     ecx, r12d
0x180034e9e  mov     [rsp+28h], rax
0x180034ea3  call    ?SampCreateAccountContext@@YAJW4_SAMP_OBJECT_TYPE@@KEEEPEAPEAU_SAMP_OBJECT@@@Z; SampCreateAccountContext(_SAMP_OBJECT_TYPE,ulong,uchar,uchar,uchar,_SAMP_OBJECT * *)
0x180034ea8  mov     edi, eax
0x180034eaa  test    eax, eax
0x180034eac  js      short loc_180034F01
0x180034eae  mov     rsi, [rbp+3Fh+HandleId]
0x180034eb2  xor     r9d, r9d; struct _DSNAME *
0x180034eb5  mov     rcx, rsi; struct _SAMP_OBJECT *
0x180034eb8  mov     qword ptr [rsp+100h+Unused], 0; __int64
0x180034ec1  mov     r8, r13; void *
0x180034ec4  mov     edx, r12d; unsigned int
0x180034ec7  call    ?SampRemoveAccountFromAlias@@YAJPEAU_SAMP_OBJECT@@KPEAXPEAU_DSNAME@@_J@Z; SampRemoveAccountFromAlias(_SAMP_OBJECT *,ulong,void *,_DSNAME *,__int64)
0x180034ecc  mov     edi, eax
0x180034ece  test    eax, eax
0x180034ed0  js      short loc_180034EDE
0x180034ed2  xor     edx, edx
0x180034ed4  mov     rcx, rsi; struct _SAMP_OBJECT *
0x180034ed7  call    SampStoreObjectAttributes
0x180034edc  mov     edi, eax
0x180034ede  mov     rcx, rsi; HandleId
0x180034ee1  call    SampDeleteContext
0x180034ee6  test    edi, edi
0x180034ee8  js      short loc_180034F01
0x180034eea  inc     r15d
0x180034eed  cmp     r15d, [rbp+3Fh+Type]
0x180034ef1  jb      loc_180034E38
0x180034ef7  mov     rcx, r13; void *
0x180034efa  call    ?SampDeleteAliasMembershipKeysForAccount@@YAJPEAX@Z; SampDeleteAliasMembershipKeysForAccount(void *)
0x180034eff  mov     edi, eax
0x180034f01  test    r14b, r14b
0x180034f04  jz      short loc_180034F18
0x180034f06  mov     eax, [rbp+3Fh+Type]
0x180034f09  mov     rcx, [rbp+3Fh+arg_28]
0x180034f0d  mov     [rcx], eax
0x180034f0f  mov     rax, [rbp+3Fh+arg_30]
0x180034f13  mov     [rax], rbx
0x180034f16  jmp     short loc_180034F21
0x180034f18  mov     rcx, rbx; hMem
0x180034f1b  call    cs:__imp_LocalFree
0x180034f21  mov     rcx, [rbp+3Fh+KeyHandle]; Handle
0x180034f25  call    cs:__imp_NtClose
0x180034f2b  jmp     short loc_180034F43
0x180034f2d  mov     edi, r12d
0x180034f30  test    r14b, r14b
0x180034f33  jz      short loc_180034F43
0x180034f35  mov     rax, [rbp+3Fh+arg_28]
0x180034f39  mov     [rax], r12d
0x180034f3c  mov     rax, [rbp+3Fh+arg_30]
0x180034f40  mov     [rax], r12
0x180034f43  lea     rcx, [rbp+3Fh+var_78]
0x180034f47  call    SampFreeUnicodeString
0x180034f4c  lea     rcx, [rbp+3Fh+var_88]
0x180034f50  call    SampFreeUnicodeString
0x180034f55  mov     rcx, cs:WPP_GLOBAL_Control
0x180034f5c  test    dword ptr [rcx+44h], 20000h
0x180034f63  jz      short loc_180034F81
0x180034f65  mov     edx, 2Ah ; '*'
0x180034f6a  mov     r9d, edi
0x180034f6d  mov     rcx, [rcx+38h]
0x180034f71  lea     r8, WPP_799c13f926ef3db95a69a5604490dfde_Traceguids
0x180034f78  mov     [rsp+100h+Unused], edi
0x180034f7c  call    WPP_SF_Dd
0x180034f81  mov     rbx, [rsp+100h+arg_0]
0x180034f89  mov     eax, edi
0x180034f8b  add     rsp, 0D0h
0x180034f92  pop     r15
0x180034f94  pop     r14
0x180034f96  pop     r13
0x180034f98  pop     r12
0x180034f9a  pop     rdi
0x180034f9b  pop     rsi
0x180034f9c  pop     rbp
0x180034f9d  retn
```
