# CSidResolver::ResolveSids(ushort const *,ulong,_SID * *,ulong,_RESOLVED_USERNAME_LIST * *)

- ea: `0x1805d8c80`
- end: `0x1805d90e5`
- name: `?ResolveSids@CSidResolver@@UEAAJPEBGKPEAPEAU_SID@@KPEAPEAU_RESOLVED_USERNAME_LIST@@@Z`
- size: `1125`
- prototype: `int(CSidResolver *__hidden this, const unsigned __int16 *, unsigned int, struct _SID **, unsigned int, struct _RESOLVED_USERNAME_LIST **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800143b0`
- `0x1800551d0`
- `0x180147bfc`
- `0x180249e34`
- `0x1802fa8c4`
- `0x1803b1f60`
- `0x1805d8c80`
- `0x1805d949c`
- `0x1805d9914`
- `0x18067d010`

## import_xrefs

- `ntdll!RtlCreateUnicodeString` at `0x1805d8d8b`
- `ntdll!RtlCreateUnicodeString` at `0x1805d8d8b`
- `ntdll!RtlFreeUnicodeString` at `0x1805d9066`
- `ntdll!RtlFreeUnicodeString` at `0x1805d9066`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805d8f92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805d8f92`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1805d8f78`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1805d8f78`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1805d8f19`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1805d8f19`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x1805d8e37`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x1805d8e37`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1805d9056`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1805d9056`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1805d9035`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1805d9046`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1805d9035`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1805d9046`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1805d8ddb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1805d8ddb`

## pseudocode

```c
__int64 __fastcall CSidResolver::ResolveSids(
        CSidResolver *this,
        const unsigned __int16 *a2,
        __int64 a3,
        PSID *a4,
        unsigned int a5,
        struct _RESOLVED_USERNAME_LIST **a6)
{
  struct _RESOLVED_USERNAME_LIST **v6; // r13
  __int64 v9; // r12
  unsigned __int64 v10; // rcx
  int UserNameFromLsaStructures; // ebx
  unsigned int v12; // edx
  char *v13; // rdi
  int v14; // eax
  BOOL v15; // r14d
  NTSTATUS v16; // eax
  __int64 v17; // r8
  int v18; // esi
  __int64 v19; // r8
  __int64 v20; // r15
  __int64 v21; // rsi
  PSID v22; // r9
  unsigned __int16 **v23; // r13
  CSidResolver *v24; // rcx
  unsigned int v25; // r8d
  PSID *v26; // rax
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v28; // ecx
  LPVOID v29; // rcx
  _QWORD *v30; // rdx
  __int64 v31; // r8
  void *v33; // [rsp+30h] [rbp-A9h] BYREF
  struct _RESOLVED_USERNAME_LIST **v34; // [rsp+38h] [rbp-A1h]
  PSID *v35; // [rsp+40h] [rbp-99h]
  LPVOID ppv; // [rsp+48h] [rbp-91h] BYREF
  PLSA_TRANSLATED_NAME Names; // [rsp+50h] [rbp-89h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+58h] [rbp-81h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-79h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-69h] BYREF
  _QWORD v41[2]; // [rsp+A0h] [rbp-39h] BYREF
  PVOID PolicyHandle[2]; // [rsp+B0h] [rbp-29h] BYREF
  CSidResolver *v43; // [rsp+C0h] [rbp-19h] BYREF

  v6 = a6;
  v35 = a4;
  v9 = (unsigned int)a3;
  v43 = this;
  *a6 = 0;
  v34 = a6;
  if ( !(_DWORD)a3 || !a4 || (a5 & 0xEFFFFFF8) != 0 )
    return 2147942487LL;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x100000) != 0 )
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_Shell_Core_Provider_Context, "]D", a3, 1, PolicyHandle);
  LODWORD(v33) = 0;
  UserNameFromLsaStructures = ULongLongToULong(16 * v9, (unsigned int *)&v33);
  if ( UserNameFromLsaStructures < 0 )
  {
    v12 = (unsigned int)v33;
  }
  else
  {
    v10 = (unsigned int)v33;
    v12 = -1;
    if ( (int)v33 + 8 >= (unsigned int)v33 )
      v12 = (_DWORD)v33 + 8;
    UserNameFromLsaStructures = (int)v33 + 8 < (unsigned int)v33 ? 0x80070216 : 0;
  }
  v13 = 0;
  v33 = 0;
  if ( UserNameFromLsaStructures >= 0 )
  {
    v14 = CTCoAllocPolicy::Alloc((void *)v10, 1u, v12, &v33);
    v13 = (char *)v33;
    UserNameFromLsaStructures = v14;
    if ( v14 >= 0 )
      *(_DWORD *)v33 = v9;
  }
  DestinationString = 0;
  if ( UserNameFromLsaStructures >= 0 && !RtlCreateUnicodeString(&DestinationString, a2) )
    UserNameFromLsaStructures = -2147024882;
  v15 = 0;
  if ( UserNameFromLsaStructures < 0 )
    goto LABEL_47;
  Names = 0;
  ReferencedDomains = 0;
  PolicyHandle[0] = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v16 = LsaOpenPolicy((PLSA_UNICODE_STRING)&DestinationString, &ObjectAttributes, 0x800u, PolicyHandle);
  UserNameFromLsaStructures = v16 | 0x10000000;
  if ( v16 < 0 )
    goto LABEL_46;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x100000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ResolveUserNames_MultipleSidsToNamesLookup_Start,
      v17,
      1,
      v41);
  v18 = LsaLookupSids(PolicyHandle[0], v9, a4, &ReferencedDomains, &Names) | 0x10000000;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x100000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ResolveUserNames_MultipleSidsToNamesLookup_Stop,
      v19,
      1,
      v41);
  if ( (int)(v18 + 0x80000000) >= 0 && v18 != -805306253 )
  {
    UserNameFromLsaStructures = v18;
    goto LABEL_45;
  }
  UserNameFromLsaStructures = 0;
  v20 = 0;
  v15 = v18 >= 0;
  while ( (unsigned int)v20 < (unsigned int)v9 )
  {
    v21 = 16LL * (unsigned int)v20;
    v22 = v35[v20];
    v23 = (unsigned __int16 **)&v13[v21 + 16];
    v41[0] = &v35[v20];
    UserNameFromLsaStructures = CSidResolver::_GetUserNameFromLsaStructures(
                                  (CSidResolver *)((char *)v43 - 8),
                                  &Names[(unsigned int)v20],
                                  ReferencedDomains,
                                  v22,
                                  a5,
                                  v23);
    if ( UserNameFromLsaStructures < 0 )
    {
      v15 = 0;
      *(_DWORD *)&v13[v21 + 8] = 0;
      if ( (a5 & 0x10000000) != 0 )
      {
        UserNameFromLsaStructures = CSidResolver::_CheckAndConvertToStringSid(
                                      v24,
                                      *(void **)v41[0],
                                      v25,
                                      (unsigned __int16 **)&v13[v21 + 16]);
        if ( UserNameFromLsaStructures < 0 )
        {
          *v23 = 0;
          break;
        }
      }
LABEL_40:
      v20 = (unsigned int)(v20 + 1);
      if ( UserNameFromLsaStructures < 0 )
        break;
    }
    else
    {
      v26 = (PSID *)v41[0];
      *(_DWORD *)&v13[v21 + 8] = 1;
      LODWORD(v33) = 0;
      WORD2(v33) = 2816;
      SidIdentifierAuthority = GetSidIdentifierAuthority(*v26);
      if ( !SidIdentifierAuthority )
      {
        UserNameFromLsaStructures = ResultFromLastError();
        goto LABEL_40;
      }
      v28 = *(_DWORD *)SidIdentifierAuthority->Value - (_DWORD)v33;
      if ( *(_DWORD *)SidIdentifierAuthority->Value == (_DWORD)v33 )
        v28 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - WORD2(v33);
      if ( v28 )
        goto LABEL_40;
      ppv = 0;
      UserNameFromLsaStructures = CoCreateInstance(
                                    &CLSID_OnlineIdFilter,
                                    0,
                                    1u,
                                    &GUID_e6496873_6ddc_4709_8785_1a5b3267843b,
                                    &ppv);
      if ( UserNameFromLsaStructures < 0 )
        goto LABEL_40;
      CoTaskMemFree(*v23);
      v29 = ppv;
      v30 = (_QWORD *)v41[0];
      *v23 = 0;
      UserNameFromLsaStructures = (*(__int64 (__fastcall **)(LPVOID, _QWORD, char *))(*(_QWORD *)v29 + 56LL))(
                                    v29,
                                    *v30,
                                    &v13[v21 + 16]);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( UserNameFromLsaStructures >= 0 )
        goto LABEL_40;
      if ( UserNameFromLsaStructures != -2147023728 )
      {
        v15 = 0;
        *(_DWORD *)&v13[v21 + 8] = 0;
        break;
      }
      UserNameFromLsaStructures = 0;
      v20 = (unsigned int)(v20 + 1);
    }
  }
  v6 = v34;
LABEL_45:
  LsaFreeMemory(Names);
  LsaFreeMemory(ReferencedDomains);
  LsaClose(PolicyHandle[0]);
LABEL_46:
  RtlFreeUnicodeString(&DestinationString);
  if ( UserNameFromLsaStructures < 0 )
  {
LABEL_47:
    FreeResolvedUserNameList(v13);
    v13 = 0;
  }
  *v6 = (struct _RESOLVED_USERNAME_LIST *)v13;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x100000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ResolveUserNames_ResolveSids_Stop,
      v31,
      1,
      &v43);
  if ( UserNameFromLsaStructures >= 0 )
    return !v15;
  return (unsigned int)UserNameFromLsaStructures;
}

```

## disassembly

```asm
0x1805d8c80  push    rbp
0x1805d8c82  push    rbx
0x1805d8c83  push    rsi
0x1805d8c84  push    rdi
0x1805d8c85  push    r12
0x1805d8c87  push    r13
0x1805d8c89  push    r14
0x1805d8c8b  push    r15
0x1805d8c8d  lea     rbp, [rsp-0Fh]
0x1805d8c92  sub     rsp, 0E8h
0x1805d8c99  mov     rax, cs:__security_cookie
0x1805d8ca0  xor     rax, rsp
0x1805d8ca3  mov     [rbp+47h+var_50], rax
0x1805d8ca7  mov     r13, [rbp+47h+arg_28]
0x1805d8cab  mov     r15, r9
0x1805d8cae  mov     [rsp+120h+var_E0], r9
0x1805d8cb3  mov     rsi, rdx
0x1805d8cb6  mov     r12d, r8d
0x1805d8cb9  mov     [rbp+47h+var_60], rcx
0x1805d8cbd  mov     qword ptr [r13+0], 0
0x1805d8cc5  mov     [rsp+120h+var_E8], r13
0x1805d8cca  test    r8d, r8d
0x1805d8ccd  jz      loc_1805D90BF
0x1805d8cd3  test    r9, r9
0x1805d8cd6  jz      loc_1805D90BF
0x1805d8cdc  test    [rbp+47h+arg_20], 0EFFFFFF8h
0x1805d8ce3  jnz     loc_1805D90BF
0x1805d8ce9  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 10h
0x1805d8cf0  jz      short loc_1805D8D14
0x1805d8cf2  lea     rax, [rbp+47h+PolicyHandle]
0x1805d8cf6  mov     r9d, 1
0x1805d8cfc  lea     rdx, ResolveUserNames_ResolveSids_Start; "]D"
0x1805d8d03  mov     [rsp+120h+Names], rax
0x1805d8d08  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1805d8d0f  call    McGenEventWrite_EventWriteTransfer
0x1805d8d14  mov     rcx, r12
0x1805d8d17  mov     dword ptr [rsp+120h+var_F0], 0
0x1805d8d1f  shl     rcx, 4; unsigned __int64
0x1805d8d23  lea     rdx, [rsp+120h+var_F0]; unsigned int *
0x1805d8d28  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1805d8d2d  mov     ebx, eax
0x1805d8d2f  test    eax, eax
0x1805d8d31  js      short loc_1805D8D4C
0x1805d8d33  mov     ecx, dword ptr [rsp+120h+var_F0]
0x1805d8d37  or      edx, 0FFFFFFFFh
0x1805d8d3a  lea     eax, [rcx+8]
0x1805d8d3d  cmp     eax, ecx
0x1805d8d3f  cmovnb  edx, eax
0x1805d8d42  sbb     ebx, ebx
0x1805d8d44  and     ebx, 80070216h
0x1805d8d4a  jmp     short loc_1805D8D50
0x1805d8d4c  mov     edx, dword ptr [rsp+120h+var_F0]
0x1805d8d50  xor     edi, edi
0x1805d8d52  mov     [rsp+120h+var_F0], rdi
0x1805d8d57  test    ebx, ebx
0x1805d8d59  js      short loc_1805D8D79
0x1805d8d5b  mov     r8d, edx; unsigned __int64
0x1805d8d5e  lea     r9, [rsp+120h+var_F0]; void **
0x1805d8d63  lea     edx, [rdi+1]; unsigned int
0x1805d8d66  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1805d8d6b  mov     rdi, [rsp+120h+var_F0]
0x1805d8d70  mov     ebx, eax
0x1805d8d72  test    eax, eax
0x1805d8d74  js      short loc_1805D8D79
0x1805d8d76  mov     [rdi], r12d
0x1805d8d79  xorps   xmm0, xmm0
0x1805d8d7c  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x1805d8d80  test    ebx, ebx
0x1805d8d82  js      short loc_1805D8DA1
0x1805d8d84  mov     rdx, rsi; SourceString
0x1805d8d87  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x1805d8d8b  call    cs:__imp_RtlCreateUnicodeString
0x1805d8d92  nop     dword ptr [rax+rax+00h]
0x1805d8d97  test    al, al
0x1805d8d99  mov     ecx, 8007000Eh
0x1805d8d9e  cmovz   ebx, ecx
0x1805d8da1  xor     r14d, r14d
0x1805d8da4  test    ebx, ebx
0x1805d8da6  js      loc_1805D9076
0x1805d8dac  xorps   xmm0, xmm0
0x1805d8daf  mov     [rsp+120h+var_D0], r14
0x1805d8db4  lea     r9, [rbp+47h+PolicyHandle]; PolicyHandle
0x1805d8db8  mov     [rsp+120h+ReferencedDomains], r14
0x1805d8dbd  mov     r8d, 800h; DesiredAccess
0x1805d8dc3  mov     [rbp+47h+PolicyHandle], r14
0x1805d8dc7  lea     rdx, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x1805d8dcb  lea     rcx, [rbp+47h+DestinationString]; SystemName
0x1805d8dcf  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x1805d8dd3  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x1805d8dd7  movups  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x1805d8ddb  call    cs:__imp_LsaOpenPolicy
0x1805d8de2  nop     dword ptr [rax+rax+00h]
0x1805d8de7  mov     ebx, eax
0x1805d8de9  or      ebx, 10000000h
0x1805d8def  jl      loc_1805D9062
0x1805d8df5  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 10h
0x1805d8dfc  jz      short loc_1805D8E1E
0x1805d8dfe  lea     rax, [rbp+47h+var_80]
0x1805d8e02  lea     r9d, [r14+1]
0x1805d8e06  mov     [rsp+120h+Names], rax
0x1805d8e0b  lea     rdx, ResolveUserNames_MultipleSidsToNamesLookup_Start
0x1805d8e12  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1805d8e19  call    McGenEventWrite_EventWriteTransfer
0x1805d8e1e  mov     rcx, [rbp+47h+PolicyHandle]; PolicyHandle
0x1805d8e22  lea     rax, [rsp+120h+var_D0]
0x1805d8e27  lea     r9, [rsp+120h+ReferencedDomains]; ReferencedDomains
0x1805d8e2c  mov     [rsp+120h+Names], rax; Names
0x1805d8e31  mov     r8, r15; Sids
0x1805d8e34  mov     edx, r12d; Count
0x1805d8e37  call    cs:__imp_LsaLookupSids
0x1805d8e3e  nop     dword ptr [rax+rax+00h]
0x1805d8e43  mov     esi, eax
0x1805d8e45  bts     esi, 1Ch
0x1805d8e49  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 10h
0x1805d8e50  jz      short loc_1805D8E74
0x1805d8e52  lea     rax, [rbp+47h+var_80]
0x1805d8e56  mov     r9d, 1
0x1805d8e5c  lea     rdx, ResolveUserNames_MultipleSidsToNamesLookup_Stop
0x1805d8e63  mov     [rsp+120h+Names], rax
0x1805d8e68  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1805d8e6f  call    McGenEventWrite_EventWriteTransfer
0x1805d8e74  mov     ecx, 80000000h
0x1805d8e79  lea     eax, [rsi+rcx]
0x1805d8e7c  test    ecx, eax
0x1805d8e7e  jnz     short loc_1805D8E8F
0x1805d8e80  cmp     esi, 0D0000073h
0x1805d8e86  jz      short loc_1805D8E8F
0x1805d8e88  mov     ebx, esi
0x1805d8e8a  jmp     loc_1805D9030
0x1805d8e8f  mov     r14d, esi
0x1805d8e92  xor     ebx, ebx
0x1805d8e94  not     r14d
0x1805d8e97  xor     r15d, r15d
0x1805d8e9a  shr     r14d, 1Fh
0x1805d8e9e  cmp     r15d, r12d
0x1805d8ea1  jnb     loc_1805D902B
0x1805d8ea7  mov     r8d, [rbp+47h+arg_20]
0x1805d8eab  mov     rax, [rsp+120h+var_E0]
0x1805d8eb0  mov     rcx, [rbp+47h+var_60]
0x1805d8eb4  mov     esi, r15d
0x1805d8eb7  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x1805d8ebb  shl     rsi, 4
0x1805d8ebf  lea     rax, [rax+r15*8]
0x1805d8ec3  mov     edx, r15d
0x1805d8ec6  mov     r9, [rax]; void *
0x1805d8ec9  shl     rdx, 5
0x1805d8ecd  add     rdx, [rsp+120h+var_D0]; struct _LSA_TRANSLATED_NAME *
0x1805d8ed2  lea     r13, [rsi+10h]
0x1805d8ed6  add     r13, rdi
0x1805d8ed9  mov     [rbp+47h+var_80], rax
0x1805d8edd  mov     [rsp+120h+var_F8], r13; unsigned __int16 **
0x1805d8ee2  mov     dword ptr [rsp+120h+Names], r8d; unsigned int
0x1805d8ee7  mov     r8, [rsp+120h+ReferencedDomains]; struct _LSA_REFERENCED_DOMAIN_LIST *
0x1805d8eec  call    ?_GetUserNameFromLsaStructures@CSidResolver@@AEAAJPEAU_LSA_TRANSLATED_NAME@@PEAU_LSA_REFERENCED_DOMAIN_LIST@@PEAXKPEAPEAG@Z; CSidResolver::_GetUserNameFromLsaStructures(_LSA_TRANSLATED_NAME *,_LSA_REFERENCED_DOMAIN_LIST *,void *,ulong,ushort * *)
0x1805d8ef1  mov     ebx, eax
0x1805d8ef3  test    eax, eax
0x1805d8ef5  js      loc_1805D8FEA
0x1805d8efb  mov     rax, [rbp+47h+var_80]
0x1805d8eff  mov     dword ptr [rsi+rdi+8], 1
0x1805d8f07  mov     dword ptr [rsp+120h+var_F0], 0
0x1805d8f0f  mov     word ptr [rsp+120h+var_F0+4], 0B00h
0x1805d8f16  mov     rcx, [rax]; pSid
0x1805d8f19  call    cs:__imp_GetSidIdentifierAuthority
0x1805d8f20  nop     dword ptr [rax+rax+00h]
0x1805d8f25  test    rax, rax
0x1805d8f28  jnz     short loc_1805D8F36
0x1805d8f2a  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1805d8f2f  mov     ebx, eax
0x1805d8f31  jmp     loc_1805D9010
0x1805d8f36  mov     ecx, [rax]
0x1805d8f38  sub     ecx, dword ptr [rsp+120h+var_F0]
0x1805d8f3c  jnz     short loc_1805D8F49
0x1805d8f3e  movzx   ecx, word ptr [rax+4]
0x1805d8f42  movzx   eax, word ptr [rsp+120h+var_F0+4]
0x1805d8f47  sub     ecx, eax
0x1805d8f49  test    ecx, ecx
0x1805d8f4b  jnz     loc_1805D9010
0x1805d8f51  lea     rax, [rsp+120h+ppv]
0x1805d8f56  mov     [rsp+120h+ppv], 0
0x1805d8f5f  lea     r8d, [rcx+1]; dwClsContext
0x1805d8f63  mov     [rsp+120h+Names], rax; ppv
0x1805d8f68  lea     rcx, CLSID_OnlineIdFilter; rclsid
0x1805d8f6f  xor     edx, edx; pUnkOuter
0x1805d8f71  lea     r9, _GUID_e6496873_6ddc_4709_8785_1a5b3267843b; riid
0x1805d8f78  call    cs:__imp_CoCreateInstance
0x1805d8f7f  nop     dword ptr [rax+rax+00h]
0x1805d8f84  mov     ebx, eax
0x1805d8f86  test    eax, eax
0x1805d8f88  js      loc_1805D9010
0x1805d8f8e  mov     rcx, [r13+0]; pv
0x1805d8f92  call    cs:__imp_CoTaskMemFree
0x1805d8f99  nop     dword ptr [rax+rax+00h]
0x1805d8f9e  mov     rcx, [rsp+120h+ppv]
0x1805d8fa3  mov     r8, r13
0x1805d8fa6  mov     rdx, [rbp+47h+var_80]
0x1805d8faa  mov     qword ptr [r13+0], 0
0x1805d8fb2  mov     rax, [rcx]
0x1805d8fb5  mov     rdx, [rdx]
0x1805d8fb8  mov     rax, [rax+38h]
0x1805d8fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805d8fc1  mov     rcx, [rsp+120h+ppv]
0x1805d8fc6  mov     ebx, eax
0x1805d8fc8  mov     rax, [rcx]
0x1805d8fcb  mov     rax, [rax+10h]
0x1805d8fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805d8fd4  test    ebx, ebx
0x1805d8fd6  jns     short loc_1805D9010
0x1805d8fd8  cmp     ebx, 80070490h
0x1805d8fde  jnz     short loc_1805D901D
0x1805d8fe0  xor     ebx, ebx
0x1805d8fe2  inc     r15d
0x1805d8fe5  jmp     loc_1805D8E9E
0x1805d8fea  xor     r14d, r14d
0x1805d8fed  test    [rbp+47h+arg_20], 10000000h
0x1805d8ff4  mov     [rsi+rdi+8], r14d
0x1805d8ff9  jz      short loc_1805D9010
0x1805d8ffb  mov     rax, [rbp+47h+var_80]
0x1805d8fff  mov     r9, r13; unsigned __int16 **
0x1805d9002  mov     rdx, [rax]; void *
0x1805d9005  call    ?_CheckAndConvertToStringSid@CSidResolver@@AEAAJPEAXKPEAPEAG@Z; CSidResolver::_CheckAndConvertToStringSid(void *,ulong,ushort * *)
0x1805d900a  mov     ebx, eax
0x1805d900c  test    eax, eax
0x1805d900e  js      short loc_1805D9027
0x1805d9010  inc     r15d
0x1805d9013  test    ebx, ebx
0x1805d9015  jns     loc_1805D8E9E
0x1805d901b  jmp     short loc_1805D902B
0x1805d901d  xor     r14d, r14d
0x1805d9020  mov     [rsi+rdi+8], r14d
0x1805d9025  jmp     short loc_1805D902B
0x1805d9027  mov     [r13+0], r14
0x1805d902b  mov     r13, [rsp+120h+var_E8]
0x1805d9030  mov     rcx, [rsp+120h+var_D0]; Buffer
0x1805d9035  call    cs:__imp_LsaFreeMemory
0x1805d903c  nop     dword ptr [rax+rax+00h]
0x1805d9041  mov     rcx, [rsp+120h+ReferencedDomains]; Buffer
0x1805d9046  call    cs:__imp_LsaFreeMemory
0x1805d904d  nop     dword ptr [rax+rax+00h]
0x1805d9052  mov     rcx, [rbp+47h+PolicyHandle]; ObjectHandle
0x1805d9056  call    cs:__imp_LsaClose
0x1805d905d  nop     dword ptr [rax+rax+00h]
0x1805d9062  lea     rcx, [rbp+47h+DestinationString]; UnicodeString
0x1805d9066  call    cs:__imp_RtlFreeUnicodeString
0x1805d906d  nop     dword ptr [rax+rax+00h]
0x1805d9072  test    ebx, ebx
0x1805d9074  jns     short loc_1805D9080
0x1805d9076  mov     rcx, rdi; pv
0x1805d9079  call    FreeResolvedUserNameList
0x1805d907e  xor     edi, edi
0x1805d9080  mov     [r13+0], rdi
0x1805d9084  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 10h
0x1805d908b  jz      short loc_1805D90AF
0x1805d908d  lea     rax, [rbp+47h+var_60]
0x1805d9091  mov     r9d, 1
0x1805d9097  lea     rdx, ResolveUserNames_ResolveSids_Stop
0x1805d909e  mov     [rsp+120h+Names], rax
0x1805d90a3  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1805d90aa  call    McGenEventWrite_EventWriteTransfer
0x1805d90af  test    ebx, ebx
0x1805d90b1  js      short loc_1805D90BB
0x1805d90b3  xor     ebx, ebx
0x1805d90b5  test    r14d, r14d
0x1805d90b8  setz    bl
0x1805d90bb  mov     eax, ebx
0x1805d90bd  jmp     short loc_1805D90C4
0x1805d90bf  mov     eax, 80070057h
0x1805d90c4  mov     rcx, [rbp+47h+var_50]
0x1805d90c8  xor     rcx, rsp; StackCookie
0x1805d90cb  call    __security_check_cookie
0x1805d90d0  add     rsp, 0E8h
0x1805d90d7  pop     r15
0x1805d90d9  pop     r14
0x1805d90db  pop     r13
0x1805d90dd  pop     r12
0x1805d90df  pop     rdi
0x1805d90e0  pop     rsi
0x1805d90e1  pop     rbx
0x1805d90e2  pop     rbp
0x1805d90e3  retn
```
