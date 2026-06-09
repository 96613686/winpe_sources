# TSObtainLoopbackCredentials(void *,_TS_PRIMARY_CREDENTIAL * *)

- ea: `0x1800147b0`
- end: `0x180014a7c`
- name: `?TSObtainLoopbackCredentials@@YAJPEAXPEAPEAU_TS_PRIMARY_CREDENTIAL@@@Z`
- size: `716`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _TS_PRIMARY_CREDENTIAL **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019958`

## callees

- `0x1800034b0`
- `0x180003830`
- `0x1800053d0`
- `0x180006210`
- `0x18000b550`
- `0x180014720`
- `0x1800147b0`
- `0x18001627c`
- `0x18001d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800148a7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180014941`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800148a7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180014941`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800148c1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800148c1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800148d3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180014972`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800148d3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180014972`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180014960`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180014960`
- `ntdll!NtQueryInformationToken` at `0x1800148fd`
- `ntdll!NtQueryInformationToken` at `0x1800148fd`
- `ntdll!RtlReleaseResource` at `0x1800149da`
- `ntdll!RtlReleaseResource` at `0x1800149da`
- `ntdll!RtlAcquireResourceShared` at `0x1800149b2`
- `ntdll!RtlAcquireResourceShared` at `0x1800149b2`

## pseudocode

```c
__int64 __fastcall TSObtainLoopbackCredentials(HANDLE TokenHandle, struct _TS_PRIMARY_CREDENTIAL **a2)
{
  struct _TS_PRIMARY_CREDENTIAL *v3; // rbx
  PLSA_GET_CLIENT_INFO GetClientInfo; // rax
  struct _TS_CREDENTIAL *v6; // rsi
  NTSTATUS v7; // edi
  int v8; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp-59h] BYREF
  ULONG ReturnLength; // [rsp+64h] [rbp-55h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-51h] BYREF
  PSID pSid; // [rsp+70h] [rbp-49h] BYREF
  struct _TS_PRIMARY_CREDENTIAL *v14; // [rsp+78h] [rbp-41h] BYREF
  struct _TS_CREDENTIAL *v15; // [rsp+80h] [rbp-39h] BYREF
  HANDLE v16[4]; // [rsp+88h] [rbp-31h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp-11h] BYREF
  _OWORD TokenInformation[3]; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v19; // [rsp+E0h] [rbp+27h]

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *a2 = 0;
  ReturnLength = 0;
  v19 = 0;
  v3 = 0;
  v15 = 0;
  v14 = 0;
  GetClientInfo = TSGlobalLsaFunctions->GetClientInfo;
  v6 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  pSid = 0;
  SidToCheck = 0;
  IsMember = 0;
  memset(v16, 0, sizeof(v16));
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v7 = ((__int64 (__fastcall *)(HANDLE *))GetClientInfo)(v16);
  if ( v7 >= 0 )
  {
    if ( !v16[3] )
      return (unsigned int)-1073741790;
    if ( AllocateAndInitializeSid(
           &pIdentifierAuthority,
           6u,
           0x50u,
           0x1A963466u,
           0x5CF1AAB9u,
           0xF8123019,
           0x7448CE95u,
           0x304EFDA0u,
           0,
           0,
           &SidToCheck) )
    {
      if ( !CheckTokenMembership(v16[3], SidToCheck, &IsMember) )
        IsMember = 0;
      FreeSid(SidToCheck);
      if ( !IsMember )
        return (unsigned int)-1073741790;
      v7 = NtQueryInformationToken(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
      if ( v7 < 0 )
        return (unsigned int)v7;
      if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
        return (unsigned int)-1073741801;
      if ( !(unsigned int)CheckTokenMembershipEx(TokenHandle, pSid, 1, &IsMember) )
        IsMember = 0;
      FreeSid(pSid);
      if ( !IsMember )
        return (unsigned int)-2146893048;
      v8 = TSCredTableLocateDefaultCreds((struct _LUID *)TokenInformation + 1, &v15);
      v6 = v15;
      v7 = v8;
      if ( v8 >= 0 )
      {
        if ( *((_QWORD *)v15 + 17) )
        {
          RtlAcquireResourceShared((PRTL_RESOURCE)((char *)v15 + 8), 1u);
          v7 = TSInitPrimaryCreds(
                 (struct _UNICODE_STRING *)(*((_QWORD *)v6 + 17) + 24LL),
                 (struct _UNICODE_STRING *)(*((_QWORD *)v6 + 17) + 8LL),
                 (struct _UNICODE_STRING *)(*((_QWORD *)v6 + 17) + 40LL),
                 &v14);
          RtlReleaseResource((PRTL_RESOURCE)((char *)v6 + 8));
          v3 = v14;
          if ( v7 >= 0 )
            v7 = TSObtainClearCreds(v14, a2);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids);
          v7 = -2146893042;
        }
      }
    }
    else
    {
      v7 = -1073741801;
    }
    if ( v6 )
      TSDereferenceCredential(v6);
    if ( v3 )
      TSFreePrimaryCredentials(v3);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800147b0  mov     [rsp-8+arg_10], rbx
0x1800147b5  mov     [rsp-8+arg_18], rsi
0x1800147ba  push    rbp
0x1800147bb  push    rdi
0x1800147bc  push    r12
0x1800147be  push    r14
0x1800147c0  push    r15
0x1800147c2  lea     rbp, [rsp-37h]
0x1800147c7  sub     rsp, 0F0h
0x1800147ce  mov     rax, cs:__security_cookie
0x1800147d5  xor     rax, rsp
0x1800147d8  mov     [rbp+57h+var_28], rax
0x1800147dc  xor     r12d, r12d
0x1800147df  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800147e5  xorps   xmm0, xmm0
0x1800147e8  mov     [rdx], r12
0x1800147eb  xor     eax, eax
0x1800147ed  mov     [rbp+57h+ReturnLength], r12d
0x1800147f1  mov     [rbp+57h+var_30], rax
0x1800147f5  mov     r14, rcx
0x1800147f8  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800147ff  lea     rcx, [rbp+57h+var_88]
0x180014803  movups  [rbp+57h+var_84], xmm0
0x180014807  mov     ebx, r12d
0x18001480a  mov     [rbp+57h+var_90], r12
0x18001480e  mov     r15, rdx
0x180014811  mov     [rbp+57h+var_98], rbx
0x180014815  mov     rax, [rax+80h]
0x18001481c  mov     esi, r12d
0x18001481f  movups  [rbp+57h+TokenInformation], xmm0
0x180014823  mov     [rbp+57h+var_A0], r12
0x180014827  movups  [rbp+57h+var_50], xmm0
0x18001482b  mov     [rbp+57h+SidToCheck], r12
0x18001482f  movups  [rbp+57h+var_40], xmm0
0x180014833  mov     [rbp+57h+IsMember], r12d
0x180014837  mov     [rbp+57h+var_88], r12d
0x18001483b  movups  [rbp+57h+var_84+0Ch], xmm0
0x18001483f  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x180014843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014848  mov     edi, eax
0x18001484a  test    eax, eax
0x18001484c  js      loc_180014A52
0x180014852  cmp     [rbp+57h+TokenHandle], r12
0x180014856  jnz     short loc_180014862
0x180014858  mov     edi, 0C0000022h
0x18001485d  jmp     loc_180014A52
0x180014862  lea     rax, [rbp+57h+SidToCheck]
0x180014866  mov     r9d, 1A963466h; nSubAuthority1
0x18001486c  mov     [rsp+110h+pSid], rax; pSid
0x180014871  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180014875  mov     [rsp+110h+nSubAuthority7], r12d; nSubAuthority7
0x18001487a  mov     r8d, 50h ; 'P'; nSubAuthority0
0x180014880  mov     [rsp+110h+nSubAuthority6], r12d; nSubAuthority6
0x180014885  mov     dl, 6; nSubAuthorityCount
0x180014887  mov     [rsp+110h+nSubAuthority5], 304EFDA0h; nSubAuthority5
0x18001488f  mov     [rsp+110h+nSubAuthority4], 7448CE95h; nSubAuthority4
0x180014897  mov     [rsp+110h+nSubAuthority3], 0F8123019h; nSubAuthority3
0x18001489f  mov     [rsp+110h+nSubAuthority2], 5CF1AAB9h; nSubAuthority2
0x1800148a7  call    cs:__imp_AllocateAndInitializeSid
0x1800148ad  test    eax, eax
0x1800148af  jz      loc_180014A33
0x1800148b5  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1800148b9  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800148bd  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800148c1  call    cs:__imp_CheckTokenMembership
0x1800148c7  test    eax, eax
0x1800148c9  jnz     short loc_1800148CF
0x1800148cb  mov     [rbp+57h+IsMember], r12d
0x1800148cf  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x1800148d3  call    cs:__imp_FreeSid
0x1800148d9  cmp     [rbp+57h+IsMember], r12d
0x1800148dd  jz      loc_180014858
0x1800148e3  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800148e9  lea     rax, [rbp+57h+ReturnLength]
0x1800148ed  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800148f1  mov     qword ptr [rsp+110h+nSubAuthority2], rax; ReturnLength
0x1800148f6  mov     rcx, r14; TokenHandle
0x1800148f9  lea     edx, [r9-2Eh]; TokenInformationClass
0x1800148fd  call    cs:__imp_NtQueryInformationToken
0x180014903  mov     edi, eax
0x180014905  test    eax, eax
0x180014907  js      loc_180014A52
0x18001490d  lea     rax, [rbp+57h+var_A0]
0x180014911  xor     r9d, r9d; nSubAuthority1
0x180014914  mov     [rsp+110h+pSid], rax; pSid
0x180014919  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001491d  mov     [rsp+110h+nSubAuthority7], r12d; nSubAuthority7
0x180014922  mov     dl, 1; nSubAuthorityCount
0x180014924  mov     [rsp+110h+nSubAuthority6], r12d; nSubAuthority6
0x180014929  mov     [rsp+110h+nSubAuthority5], r12d; nSubAuthority5
0x18001492e  lea     r8d, [r9+4]; nSubAuthority0
0x180014932  mov     [rsp+110h+nSubAuthority4], r12d; nSubAuthority4
0x180014937  mov     [rsp+110h+nSubAuthority3], r12d; nSubAuthority3
0x18001493c  mov     [rsp+110h+nSubAuthority2], r12d; nSubAuthority2
0x180014941  call    cs:__imp_AllocateAndInitializeSid
0x180014947  test    eax, eax
0x180014949  jz      loc_180014A2C
0x18001494f  mov     rdx, [rbp+57h+var_A0]
0x180014953  lea     r9, [rbp+57h+IsMember]
0x180014957  mov     r8d, 1
0x18001495d  mov     rcx, r14
0x180014960  call    cs:__imp_CheckTokenMembershipEx
0x180014966  test    eax, eax
0x180014968  jnz     short loc_18001496E
0x18001496a  mov     [rbp+57h+IsMember], r12d
0x18001496e  mov     rcx, [rbp+57h+var_A0]; pSid
0x180014972  call    cs:__imp_FreeSid
0x180014978  cmp     [rbp+57h+IsMember], r12d
0x18001497c  jnz     short loc_180014988
0x18001497e  mov     edi, 80090308h
0x180014983  jmp     loc_180014A52
0x180014988  lea     rdx, [rbp+57h+var_90]; struct _TS_CREDENTIAL **
0x18001498c  lea     rcx, [rbp+57h+TokenInformation+8]; struct _LUID *
0x180014990  call    ?TSCredTableLocateDefaultCreds@@YAJPEAU_LUID@@PEAPEAU_TS_CREDENTIAL@@@Z; TSCredTableLocateDefaultCreds(_LUID *,_TS_CREDENTIAL * *)
0x180014995  mov     rsi, [rbp+57h+var_90]
0x180014999  mov     edi, eax
0x18001499b  test    eax, eax
0x18001499d  js      loc_180014A38
0x1800149a3  cmp     [rsi+88h], r12
0x1800149aa  jz      short loc_1800149F7
0x1800149ac  mov     dl, 1; Wait
0x1800149ae  lea     rcx, [rsi+8]; Resource
0x1800149b2  call    cs:__imp_RtlAcquireResourceShared
0x1800149b8  mov     rcx, [rsi+88h]
0x1800149bf  lea     r9, [rbp+57h+var_98]; struct _TS_PRIMARY_CREDENTIAL **
0x1800149c3  lea     r8, [rcx+28h]; struct _UNICODE_STRING *
0x1800149c7  lea     rdx, [rcx+8]; struct _UNICODE_STRING *
0x1800149cb  add     rcx, 18h; struct _UNICODE_STRING *
0x1800149cf  call    ?TSInitPrimaryCreds@@YAJPEAU_UNICODE_STRING@@00PEAPEAU_TS_PRIMARY_CREDENTIAL@@@Z; TSInitPrimaryCreds(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_TS_PRIMARY_CREDENTIAL * *)
0x1800149d4  lea     rcx, [rsi+8]; Resource
0x1800149d8  mov     edi, eax
0x1800149da  call    cs:__imp_RtlReleaseResource
0x1800149e0  mov     rbx, [rbp+57h+var_98]
0x1800149e4  test    edi, edi
0x1800149e6  js      short loc_180014A38
0x1800149e8  mov     rdx, r15; struct _TS_PRIMARY_CREDENTIAL **
0x1800149eb  mov     rcx, rbx; struct _TS_PRIMARY_CREDENTIAL *
0x1800149ee  call    ?TSObtainClearCreds@@YAJPEAU_TS_PRIMARY_CREDENTIAL@@PEAPEAU1@@Z; TSObtainClearCreds(_TS_PRIMARY_CREDENTIAL *,_TS_PRIMARY_CREDENTIAL * *)
0x1800149f3  mov     edi, eax
0x1800149f5  jmp     short loc_180014A38
0x1800149f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149fe  lea     rax, WPP_GLOBAL_Control
0x180014a05  cmp     rcx, rax
0x180014a08  jz      short loc_180014A25
0x180014a0a  test    byte ptr [rcx+1Ch], 1
0x180014a0e  jz      short loc_180014A25
0x180014a10  mov     rcx, [rcx+10h]
0x180014a14  lea     r8, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids
0x180014a1b  mov     edx, 35h ; '5'
0x180014a20  call    WPP_SF_
0x180014a25  mov     edi, 8009030Eh
0x180014a2a  jmp     short loc_180014A38
0x180014a2c  mov     edi, 0C0000017h
0x180014a31  jmp     short loc_180014A52
0x180014a33  mov     edi, 0C0000017h
0x180014a38  test    rsi, rsi
0x180014a3b  jz      short loc_180014A45
0x180014a3d  mov     rcx, rsi; struct _TS_CREDENTIAL *
0x180014a40  call    ?TSDereferenceCredential@@YAXPEAU_TS_CREDENTIAL@@@Z; TSDereferenceCredential(_TS_CREDENTIAL *)
0x180014a45  test    rbx, rbx
0x180014a48  jz      short loc_180014A52
0x180014a4a  mov     rcx, rbx; struct _TS_PRIMARY_CREDENTIAL *
0x180014a4d  call    ?TSFreePrimaryCredentials@@YAJPEAU_TS_PRIMARY_CREDENTIAL@@@Z; TSFreePrimaryCredentials(_TS_PRIMARY_CREDENTIAL *)
0x180014a52  mov     eax, edi
0x180014a54  mov     rcx, [rbp+57h+var_28]
0x180014a58  xor     rcx, rsp; StackCookie
0x180014a5b  call    __security_check_cookie
0x180014a60  lea     r11, [rsp+110h+var_20]
0x180014a68  mov     rbx, [r11+40h]
0x180014a6c  mov     rsi, [r11+48h]
0x180014a70  mov     rsp, r11
0x180014a73  pop     r15
0x180014a75  pop     r14
0x180014a77  pop     r12
0x180014a79  pop     rdi
0x180014a7a  pop     rbp
0x180014a7b  retn
```
