# SampIsAccountinProtectedUsers(_UNICODE_STRING *,uchar *)

- ea: `0x1800a05c0`
- end: `0x1800a0a51`
- name: `?SampIsAccountinProtectedUsers@@YAJPEAU_UNICODE_STRING@@PEAE@Z`
- size: `1169`
- prototype: `__int64 __fastcall(PLSA_UNICODE_STRING Names, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009c25c`

## callees

- `0x18001f900`
- `0x180022530`
- `0x180027e24`
- `0x180027ef8`
- `0x180027f2c`
- `0x18002cd80`
- `0x1800372ac`
- `0x18005be9c`
- `0x180077114`
- `0x1800a05c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a07a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a07ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a07b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a07a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a07ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a07b7`
- `ntdll!RtlLengthSid` at `0x1800a073e`
- `ntdll!RtlLengthSid` at `0x1800a073e`
- `ntdll!RtlEqualSid` at `0x1800a0921`
- `ntdll!RtlEqualSid` at `0x1800a0921`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a0799`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a0799`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a074d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a074d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a09c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a09dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a09c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a09dc`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800a0993`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800a09ad`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800a0993`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800a09ad`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x1800a0707`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x1800a0707`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800a097a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800a097a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800a06a2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800a06a2`

## pseudocode

```c
__int64 __fastcall SampIsAccountinProtectedUsers(PLSA_UNICODE_STRING Names, unsigned __int8 *a2)
{
  struct _PSAMP_DEFINED_DOMAINS *v2; // rbx
  void *v5; // rsi
  char v6; // al
  char v7; // r12
  void *v8; // rdi
  int v9; // eax
  unsigned int LastError; // ebx
  PUNICODE_STRING v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  ULONG v14; // ebx
  HLOCAL v15; // rax
  __int64 v16; // rdx
  int MembershipsDs; // eax
  __int64 v18; // rdi
  unsigned int v19; // eax
  unsigned int v21; // [rsp+50h] [rbp-B0h] BYREF
  PLSA_TRANSLATED_SID2 Sids; // [rsp+58h] [rbp-A8h] BYREF
  PVOID PolicyHandle; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid1; // [rsp+68h] [rbp-98h] BYREF
  _OWORD *v25; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+80h] [rbp-80h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v29[2]; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v30[2]; // [rsp+D8h] [rbp-28h]
  _OWORD v31[2]; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD v32[2]; // [rsp+118h] [rbp+18h]

  v2 = SampDefinedDomains;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle = 0;
  v5 = 0;
  ReferencedDomains = 0;
  Sids = 0;
  v21 = 0;
  v26 = 0;
  v6 = SampUsingDsData();
  Sid1 = 0;
  v30[0] = 0;
  v32[0] = 0;
  v25 = 0;
  v7 = 0;
  memset(v29, 0, sizeof(v29));
  v8 = *(void **)((char *)v2 + (v6 != 0 ? 0xAA0 : 0) + 1368);
  *a2 = 0;
  *(_OWORD *)((char *)v30 + 12) = 0;
  memset(v31, 0, sizeof(v31));
  *(_OWORD *)((char *)v32 + 12) = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v9 = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle);
  LastError = v9;
  if ( v9 >= 0 )
  {
    v9 = LsaLookupNames2(PolicyHandle, 0, 1u, Names, &ReferencedDomains, &Sids);
    LastError = v9;
    if ( v9 >= 0 )
    {
      v14 = RtlLengthSid(Sids->Sid);
      v15 = LocalAlloc(0x40u, v14);
      v5 = v15;
      if ( v15 )
      {
        if ( CopySid(v14, v15, Sids->Sid) )
        {
          v9 = SampBuildDsNameFromSidNew(v5);
          LastError = v9;
          if ( v9 >= 0 )
          {
            v9 = SampBuildDsNameFromSidNew(v8);
            LastError = v9;
            if ( v9 >= 0 )
            {
              v25 = v29;
              v9 = SampExtMaybeBeginDsTransactionDs(0);
              LastError = v9;
              if ( v9 >= 0 )
              {
                v7 = 1;
                MembershipsDs = SampExtGetMembershipsDs(&v25, v16, v31, 3, &v21, &v26);
                LastError = MembershipsDs;
                if ( MembershipsDs >= 0 && v21 )
                {
                  v9 = SampCreateFullSid(v8, 0x20Du, &Sid1);
                  LastError = v9;
                  if ( v9 >= 0 )
                  {
                    v18 = 0;
                    if ( v21 )
                    {
                      while ( !RtlEqualSid(Sid1, (PSID)(*(_QWORD *)(v26 + 8 * v18) + 24LL)) )
                      {
                        v18 = (unsigned int)(v18 + 1);
                        if ( (unsigned int)v18 >= v21 )
                          goto LABEL_48;
                      }
                      *a2 = 1;
                    }
                    goto LABEL_48;
                  }
                  v11 = WPP_GLOBAL_Control;
                  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
                    && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
                  {
                    v12 = 395;
                    goto LABEL_5;
                  }
                }
                else
                {
                  v11 = WPP_GLOBAL_Control;
                  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
                    && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
                  {
                    WPP_SF_Dd(
                      WPP_GLOBAL_Control[3].Buffer,
                      394,
                      WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
                      v21,
                      MembershipsDs);
                    goto LABEL_48;
                  }
                }
              }
              else
              {
                v11 = WPP_GLOBAL_Control;
                if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
                  && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
                {
                  v12 = 393;
                  goto LABEL_5;
                }
              }
            }
            else
            {
              v11 = WPP_GLOBAL_Control;
              if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
                && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
              {
                v12 = 392;
                goto LABEL_5;
              }
            }
          }
          else
          {
            v11 = WPP_GLOBAL_Control;
            if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
              && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
            {
              v12 = 391;
              goto LABEL_5;
            }
          }
        }
        else
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            LastError = GetLastError();
          v11 = WPP_GLOBAL_Control;
          if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
            && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
          {
            v12 = 390;
            v13 = LastError;
            goto LABEL_6;
          }
        }
      }
      else
      {
        LastError = -1073741670;
        v11 = WPP_GLOBAL_Control;
        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          v12 = 389;
          v13 = 3221225626LL;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        v12 = 388;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v12 = 387;
LABEL_5:
      v13 = (unsigned int)v9;
LABEL_6:
      WPP_SF_d(v11[3].Buffer, v12, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v13);
LABEL_48:
      v11 = WPP_GLOBAL_Control;
    }
  }
  if ( PolicyHandle )
  {
    LsaClose(PolicyHandle);
    v11 = WPP_GLOBAL_Control;
  }
  if ( ReferencedDomains )
  {
    LsaFreeMemory(ReferencedDomains);
    v11 = WPP_GLOBAL_Control;
  }
  if ( Sids )
  {
    LsaFreeMemory(Sids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    LocalFree(v5);
    v11 = WPP_GLOBAL_Control;
  }
  if ( Sid1 )
  {
    LocalFree(Sid1);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    v19 = SampExtMaybeEndDsTransactionDs((unsigned int)(((int)LastError >> 31) + 3));
    v11 = WPP_GLOBAL_Control;
    LastError = v19;
  }
  if ( (*(_DWORD *)(&v11[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v11[3].Buffer, 396, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, LastError, LastError);
  return LastError;
}

```

## disassembly

```asm
0x1800a05c0  mov     [rsp-8+arg_10], rbx
0x1800a05c5  mov     [rsp-8+arg_18], rsi
0x1800a05ca  push    rbp
0x1800a05cb  push    rdi
0x1800a05cc  push    r12
0x1800a05ce  push    r14
0x1800a05d0  push    r15
0x1800a05d2  lea     rbp, [rsp-40h]
0x1800a05d7  sub     rsp, 140h
0x1800a05de  mov     rax, cs:__security_cookie
0x1800a05e5  xor     rax, rsp
0x1800a05e8  mov     [rbp+60h+var_28], rax
0x1800a05ec  mov     rbx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800a05f3  xorps   xmm0, xmm0
0x1800a05f6  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x1800a05fa  mov     r15, rdx
0x1800a05fd  mov     r14, rcx
0x1800a0600  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x1800a0604  mov     [rsp+160h+PolicyHandle], 0
0x1800a060d  xor     esi, esi
0x1800a060f  movups  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a0613  mov     [rbp+60h+var_E0], 0
0x1800a061b  mov     [rsp+160h+var_108], 0
0x1800a0624  mov     [rsp+160h+var_110], 0
0x1800a062c  mov     [rsp+160h+var_E8], 0
0x1800a0635  call    SampUsingDsData
0x1800a063a  xorps   xmm0, xmm0
0x1800a063d  mov     [rsp+160h+Sid1], rsi
0x1800a0642  xorps   xmm1, xmm1
0x1800a0645  lea     r9, [rsp+160h+PolicyHandle]; PolicyHandle
0x1800a064a  neg     al
0x1800a064c  lea     rdx, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x1800a0650  movups  xmmword ptr [rbp+60h+var_88], xmm0
0x1800a0654  sbb     rcx, rcx
0x1800a0657  mov     r8d, 800h; DesiredAccess
0x1800a065d  and     ecx, 0AA0h
0x1800a0663  xor     eax, eax
0x1800a0665  movups  xmmword ptr [rbp+60h+var_48], xmm1
0x1800a0669  mov     [rsp+160h+var_F0], rax
0x1800a066e  xor     r12b, r12b
0x1800a0671  movups  [rbp+60h+var_A8], xmm0
0x1800a0675  mov     rdi, [rcx+rbx+558h]
0x1800a067d  xor     ecx, ecx; SystemName
0x1800a067f  movups  [rbp+60h+var_98], xmm0
0x1800a0683  mov     [r15], al
0x1800a0686  movups  xmmword ptr [rbp+60h+var_88+0Ch], xmm0
0x1800a068a  movups  [rbp+60h+var_68], xmm1
0x1800a068e  movups  [rbp+60h+var_58], xmm1
0x1800a0692  movups  xmmword ptr [rbp+60h+var_48+0Ch], xmm1
0x1800a0696  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x1800a069a  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x1800a069e  movups  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a06a2  call    cs:__imp_LsaOpenPolicy
0x1800a06a8  mov     ebx, eax
0x1800a06aa  test    eax, eax
0x1800a06ac  jns     short loc_1800A06E6
0x1800a06ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a06b5  test    byte ptr [rcx+44h], 20h
0x1800a06b9  jz      loc_1800A096D
0x1800a06bf  cmp     byte ptr [rcx+41h], 2
0x1800a06c3  jb      loc_1800A096D
0x1800a06c9  mov     edx, 183h
0x1800a06ce  mov     r9d, eax
0x1800a06d1  mov     rcx, [rcx+38h]
0x1800a06d5  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x1800a06dc  call    WPP_SF_d
0x1800a06e1  jmp     loc_1800A0966
0x1800a06e6  mov     rcx, [rsp+160h+PolicyHandle]; PolicyHandle
0x1800a06eb  lea     rax, [rsp+160h+var_108]
0x1800a06f0  mov     [rsp+160h+Sids], rax; Sids
0x1800a06f5  xor     edx, edx; Flags
0x1800a06f7  lea     rax, [rbp+60h+var_E0]
0x1800a06fb  mov     r9, r14; Names
0x1800a06fe  mov     [rsp+160h+ReferencedDomains], rax; ReferencedDomains
0x1800a0703  lea     r8d, [rdx+1]; Count
0x1800a0707  call    cs:__imp_LsaLookupNames2
0x1800a070d  mov     ebx, eax
0x1800a070f  test    eax, eax
0x1800a0711  jns     short loc_1800A0735
0x1800a0713  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a071a  test    byte ptr [rcx+44h], 20h
0x1800a071e  jz      loc_1800A096D
0x1800a0724  cmp     byte ptr [rcx+41h], 2
0x1800a0728  jb      loc_1800A096D
0x1800a072e  mov     edx, 184h
0x1800a0733  jmp     short loc_1800A06CE
0x1800a0735  mov     rcx, [rsp+160h+var_108]
0x1800a073a  mov     rcx, [rcx+8]; Sid
0x1800a073e  call    cs:__imp_RtlLengthSid
0x1800a0744  mov     edx, eax; uBytes
0x1800a0746  mov     ecx, 40h ; '@'; uFlags
0x1800a074b  mov     ebx, eax
0x1800a074d  call    cs:__imp_LocalAlloc
0x1800a0753  mov     rsi, rax
0x1800a0756  test    rax, rax
0x1800a0759  jnz     short loc_1800A078B
0x1800a075b  mov     ebx, 0C000009Ah
0x1800a0760  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0767  test    byte ptr [rcx+44h], 20h
0x1800a076b  jz      loc_1800A096D
0x1800a0771  cmp     byte ptr [rcx+41h], 2
0x1800a0775  jb      loc_1800A096D
0x1800a077b  mov     edx, 185h
0x1800a0780  mov     r9d, 0C000009Ah
0x1800a0786  jmp     loc_1800A06D1
0x1800a078b  mov     r8, [rsp+160h+var_108]
0x1800a0790  mov     rdx, rsi; pDestinationSid
0x1800a0793  mov     ecx, ebx; nDestinationSidLength
0x1800a0795  mov     r8, [r8+8]; pSourceSid
0x1800a0799  call    cs:__imp_CopySid
0x1800a079f  test    eax, eax
0x1800a07a1  jnz     short loc_1800A07EE
0x1800a07a3  call    cs:__imp_GetLastError
0x1800a07a9  test    eax, eax
0x1800a07ab  jg      short loc_1800A07B7
0x1800a07ad  call    cs:__imp_GetLastError
0x1800a07b3  mov     ebx, eax
0x1800a07b5  jmp     short loc_1800A07C6
0x1800a07b7  call    cs:__imp_GetLastError
0x1800a07bd  movzx   ebx, ax
0x1800a07c0  or      ebx, 0C0070000h
0x1800a07c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a07cd  test    byte ptr [rcx+44h], 20h
0x1800a07d1  jz      loc_1800A096D
0x1800a07d7  cmp     byte ptr [rcx+41h], 2
0x1800a07db  jb      loc_1800A096D
0x1800a07e1  mov     edx, 186h
0x1800a07e6  mov     r9d, ebx
0x1800a07e9  jmp     loc_1800A06D1
0x1800a07ee  lea     rdx, [rbp+60h+var_A8]
0x1800a07f2  mov     rcx, rsi; Src
0x1800a07f5  call    SampBuildDsNameFromSidNew
0x1800a07fa  mov     ebx, eax
0x1800a07fc  test    eax, eax
0x1800a07fe  jns     short loc_1800A0825
0x1800a0800  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0807  test    byte ptr [rcx+44h], 20h
0x1800a080b  jz      loc_1800A096D
0x1800a0811  cmp     byte ptr [rcx+41h], 2
0x1800a0815  jb      loc_1800A096D
0x1800a081b  mov     edx, 187h
0x1800a0820  jmp     loc_1800A06CE
0x1800a0825  lea     rdx, [rbp+60h+var_68]
0x1800a0829  mov     rcx, rdi; Src
0x1800a082c  call    SampBuildDsNameFromSidNew
0x1800a0831  mov     ebx, eax
0x1800a0833  test    eax, eax
0x1800a0835  jns     short loc_1800A085C
0x1800a0837  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a083e  test    byte ptr [rcx+44h], 20h
0x1800a0842  jz      loc_1800A096D
0x1800a0848  cmp     byte ptr [rcx+41h], 2
0x1800a084c  jb      loc_1800A096D
0x1800a0852  mov     edx, 188h
0x1800a0857  jmp     loc_1800A06CE
0x1800a085c  lea     rax, [rbp+60h+var_A8]
0x1800a0860  xor     ecx, ecx
0x1800a0862  mov     [rsp+160h+var_F0], rax
0x1800a0867  call    ?SampExtMaybeBeginDsTransactionDs@@YAJW4SAMP_DS_TRANSACTION_CONTROL@@@Z; SampExtMaybeBeginDsTransactionDs(SAMP_DS_TRANSACTION_CONTROL)
0x1800a086c  mov     ebx, eax
0x1800a086e  test    eax, eax
0x1800a0870  jns     short loc_1800A0897
0x1800a0872  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0879  test    byte ptr [rcx+44h], 20h
0x1800a087d  jz      loc_1800A096D
0x1800a0883  cmp     byte ptr [rcx+41h], 2
0x1800a0887  jb      loc_1800A096D
0x1800a088d  mov     edx, 189h
0x1800a0892  jmp     loc_1800A06CE
0x1800a0897  lea     rax, [rsp+160h+var_E8]
0x1800a089c  mov     r9d, 3
0x1800a08a2  mov     [rsp+160h+Sids], rax
0x1800a08a7  lea     r8, [rbp+60h+var_68]
0x1800a08ab  lea     rax, [rsp+160h+var_110]
0x1800a08b0  mov     r12b, 1
0x1800a08b3  lea     rcx, [rsp+160h+var_F0]
0x1800a08b8  mov     [rsp+160h+ReferencedDomains], rax
0x1800a08bd  call    ?SampExtGetMembershipsDs@@YAJPEAPEAU_DSNAME@@KPEAU1@W4__MIDL_drsuapi_0009@@PEAKPEAPEAPEAU1@PEAPEAK3PEAPEAPEAXPEAU_SAMP_USER_ACCOUNT_SETTINGS@@@Z; SampExtGetMembershipsDs(_DSNAME * *,ulong,_DSNAME *,__MIDL_drsuapi_0009,ulong *,_DSNAME * * *,ulong * *,ulong *,void * * *,_SAMP_USER_ACCOUNT_SETTINGS *)
0x1800a08c2  mov     r9d, [rsp+160h+var_110]
0x1800a08c7  mov     ebx, eax
0x1800a08c9  test    eax, eax
0x1800a08cb  js      short loc_1800A093A
0x1800a08cd  test    r9d, r9d
0x1800a08d0  jz      short loc_1800A093A
0x1800a08d2  lea     r8, [rsp+160h+Sid1]
0x1800a08d7  mov     edx, 20Dh
0x1800a08dc  mov     rcx, rdi; SourceSid
0x1800a08df  call    SampCreateFullSid
0x1800a08e4  mov     ebx, eax
0x1800a08e6  test    eax, eax
0x1800a08e8  jns     short loc_1800A0907
0x1800a08ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a08f1  test    byte ptr [rcx+44h], 20h
0x1800a08f5  jz      short loc_1800A096D
0x1800a08f7  cmp     byte ptr [rcx+41h], 2
0x1800a08fb  jb      short loc_1800A096D
0x1800a08fd  mov     edx, 18Bh
0x1800a0902  jmp     loc_1800A06CE
0x1800a0907  xor     edi, edi
0x1800a0909  cmp     [rsp+160h+var_110], edi
0x1800a090d  jbe     short loc_1800A0966
0x1800a090f  mov     rax, [rsp+160h+var_E8]
0x1800a0914  mov     rcx, [rsp+160h+Sid1]; Sid1
0x1800a0919  mov     rdx, [rax+rdi*8]
0x1800a091d  add     rdx, 18h; Sid2
0x1800a0921  call    cs:__imp_RtlEqualSid
0x1800a0927  test    al, al
0x1800a0929  jnz     short loc_1800A0935
0x1800a092b  inc     edi
0x1800a092d  cmp     edi, [rsp+160h+var_110]
0x1800a0931  jb      short loc_1800A090F
0x1800a0933  jmp     short loc_1800A0966
0x1800a0935  mov     [r15], r12b
0x1800a0938  jmp     short loc_1800A0966
0x1800a093a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0941  test    byte ptr [rcx+44h], 20h
0x1800a0945  jz      short loc_1800A096D
0x1800a0947  cmp     byte ptr [rcx+41h], 2
0x1800a094b  jb      short loc_1800A096D
0x1800a094d  mov     rcx, [rcx+38h]
0x1800a0951  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x1800a0958  mov     edx, 18Ah
0x1800a095d  mov     dword ptr [rsp+160h+ReferencedDomains], eax
0x1800a0961  call    WPP_SF_Dd
0x1800a0966  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a096d  mov     rax, [rsp+160h+PolicyHandle]
0x1800a0972  test    rax, rax
0x1800a0975  jz      short loc_1800A0987
0x1800a0977  mov     rcx, rax; ObjectHandle
0x1800a097a  call    cs:__imp_LsaClose
0x1800a0980  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0987  mov     rax, [rbp+60h+var_E0]
0x1800a098b  test    rax, rax
0x1800a098e  jz      short loc_1800A09A0
0x1800a0990  mov     rcx, rax; Buffer
0x1800a0993  call    cs:__imp_LsaFreeMemory
0x1800a0999  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a09a0  mov     rax, [rsp+160h+var_108]
0x1800a09a5  test    rax, rax
0x1800a09a8  jz      short loc_1800A09BA
0x1800a09aa  mov     rcx, rax; Buffer
0x1800a09ad  call    cs:__imp_LsaFreeMemory
0x1800a09b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a09ba  test    rsi, rsi
0x1800a09bd  jz      short loc_1800A09CF
0x1800a09bf  mov     rcx, rsi; hMem
0x1800a09c2  call    cs:__imp_LocalFree
0x1800a09c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a09cf  mov     rax, [rsp+160h+Sid1]
0x1800a09d4  test    rax, rax
0x1800a09d7  jz      short loc_1800A09E9
0x1800a09d9  mov     rcx, rax; hMem
0x1800a09dc  call    cs:__imp_LocalFree
0x1800a09e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a09e9  test    r12b, r12b
0x1800a09ec  jz      short loc_1800A0A02
0x1800a09ee  sar     ebx, 1Fh
0x1800a09f1  lea     ecx, [rbx+3]
0x1800a09f4  call    ?SampExtMaybeEndDsTransactionDs@@YAJW4SAMP_DS_TRANSACTION_CONTROL@@@Z; SampExtMaybeEndDsTransactionDs(SAMP_DS_TRANSACTION_CONTROL)
0x1800a09f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0a00  mov     ebx, eax
0x1800a0a02  test    dword ptr [rcx+44h], 20000h
0x1800a0a09  jz      short loc_1800A0A27
0x1800a0a0b  mov     rcx, [rcx+38h]
0x1800a0a0f  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x1800a0a16  mov     edx, 18Ch
0x1800a0a1b  mov     dword ptr [rsp+160h+ReferencedDomains], ebx
0x1800a0a1f  mov     r9d, ebx
0x1800a0a22  call    WPP_SF_Dd
0x1800a0a27  mov     eax, ebx
0x1800a0a29  mov     rcx, [rbp+60h+var_28]
0x1800a0a2d  xor     rcx, rsp; StackCookie
0x1800a0a30  call    __security_check_cookie
0x1800a0a35  lea     r11, [rsp+160h+var_20]
0x1800a0a3d  mov     rbx, [r11+40h]
0x1800a0a41  mov     rsi, [r11+48h]
0x1800a0a45  mov     rsp, r11
0x1800a0a48  pop     r15
0x1800a0a4a  pop     r14
0x1800a0a4c  pop     r12
0x1800a0a4e  pop     rdi
0x1800a0a4f  pop     rbp
0x1800a0a50  retn
```
