# ClientDeviceIdHelpers::IsLoggedInUserMatchSID(ATL::CHandle &,uchar,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int &)

- ea: `0x18001be78`
- end: `0x18001c1da`
- name: `?IsLoggedInUserMatchSID@ClientDeviceIdHelpers@@CAJAEAVCHandle@ATL@@EKKKKKKKKAEAH@Z`
- size: `866`
- prototype: `static int(struct ATL::CHandle *, unsigned __int8, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bd34`

## callees

- `0x180002da0`
- `0x18000cc9c`
- `0x18000e870`
- `0x18001be78`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c03f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c11d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c03f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c11d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bf96`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c00d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bf96`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c00d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c18e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c197`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c18e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c197`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001c035`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001c035`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001c087`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001c087`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001c0c2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001c0c2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18001c0fa`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18001c0fa`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18001c10a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18001c10a`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18001c113`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18001c113`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001c17e`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001c17e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001c1a6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001c1a6`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001bfb8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001bfb8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001bffe`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001bffe`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001bf4a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001bf4a`

## string_xrefs

- `0x18001bee8`: `ClientDeviceIdHelpers::IsLoggedInUserMatchSID`
- `0x18001bf66`: `AllocateAndInitializeSid failed with hr = 0x%x`
- `0x18001bfd4`: `InitializeSecurityDescriptor failed with hr = 0x%x`
- `0x18001c051`: `InitializeAcl failed with hr = 0x%x`
- `0x18001c0a3`: `AddAccessAllowedAce failed with hr = 0x%x`
- `0x18001c0de`: `SetSecurityDescriptorDacl failed with hr = 0x%x`
- `0x18001c12f`: `IsValidSecurityDescriptor failed with hr = 0x%x`

## pseudocode

```c
__int64 __fastcall ClientDeviceIdHelpers::IsLoggedInUserMatchSID(
        void **a1,
        BYTE a2,
        DWORD a3,
        DWORD a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10,
        int *AccessStatus)
{
  signed int v15; // eax
  HLOCAL v16; // rax
  void *v17; // rdi
  signed int LastError; // eax
  SIZE_T v19; // r14
  ACL *v20; // rax
  ACL *v21; // rsi
  signed int v22; // eax
  const unsigned __int16 *v23; // r9
  unsigned int v24; // r8d
  void *v25; // rdx
  unsigned int v26; // ebx
  const unsigned __int16 *nSubAuthority2; // [rsp+20h] [rbp-B1h]
  DWORD nSubAuthority2a[2]; // [rsp+20h] [rbp-B1h]
  int v30; // [rsp+60h] [rbp-71h] BYREF
  PSID pGroup; // [rsp+68h] [rbp-69h] BYREF
  DWORD GrantedAccess; // [rsp+70h] [rbp-61h] BYREF
  DWORD PrivilegeSetLength; // [rsp+74h] [rbp-5Dh] BYREF
  _QWORD v34[4]; // [rsp+78h] [rbp-59h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp-39h] BYREF
  GENERIC_MAPPING GenericMapping; // [rsp+A0h] [rbp-31h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+B0h] [rbp-21h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v30 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  GrantedAccess = 0;
  v34[1] = &v30;
  PrivilegeSetLength = 20;
  pGroup = 0;
  v34[2] = 0;
  v34[0] = "ClientDeviceIdHelpers::IsLoggedInUserMatchSID";
  v34[3] = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GenericMapping = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrldevicehelpers.cpp",
    "ClientDeviceIdHelpers::IsLoggedInUserMatchSID",
    (const char *)0xFC,
    0,
    nSubAuthority2);
  *AccessStatus = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, a2, a3, a4, 0, 0, 0, 0, 0, 0, &pGroup) )
  {
    v16 = LocalAlloc(0x40u, 0x28u);
    v17 = v16;
    if ( !v16 )
    {
      v30 = -2147024882;
      goto LABEL_34;
    }
    if ( !InitializeSecurityDescriptor(v16, 1u) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v30 = LastError;
      nSubAuthority2a[0] = LastError;
      TracePrintW(
        2u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrldevicehelpers.cpp",
        0x12Eu,
        L"InitializeSecurityDescriptor failed with hr = 0x%x",
        *(_QWORD *)nSubAuthority2a);
      goto LABEL_33;
    }
    v19 = GetLengthSid(pGroup) + 16;
    v20 = (ACL *)LocalAlloc(0x40u, v19);
    v21 = v20;
    if ( !v20 )
    {
      v30 = -2147024882;
LABEL_33:
      LocalFree(v17);
      goto LABEL_34;
    }
    if ( InitializeAcl(v20, v19, 2u) )
    {
      if ( AddAccessAllowedAce(v21, 2u, 3u, pGroup) )
      {
        if ( SetSecurityDescriptorDacl(v17, 1, v21, 0) )
        {
          SetSecurityDescriptorGroup(v17, pGroup, 0);
          SetSecurityDescriptorOwner(v17, pGroup, 0);
          if ( IsValidSecurityDescriptor(v17) )
          {
            v25 = *a1;
            GenericMapping.GenericRead = 1;
            *(_QWORD *)&GenericMapping.GenericWrite = 2;
            GenericMapping.GenericAll = 3;
            if ( !AccessCheck(
                    v17,
                    v25,
                    1u,
                    &GenericMapping,
                    &PrivilegeSet,
                    &PrivilegeSetLength,
                    &GrantedAccess,
                    AccessStatus) )
              *AccessStatus = 0;
            goto LABEL_32;
          }
          v22 = GetLastError();
          if ( v22 > 0 )
            v22 = (unsigned __int16)v22 | 0x80070000;
          v23 = L"IsValidSecurityDescriptor failed with hr = 0x%x";
          v24 = 350;
        }
        else
        {
          v22 = GetLastError();
          if ( v22 > 0 )
            v22 = (unsigned __int16)v22 | 0x80070000;
          v23 = L"SetSecurityDescriptorDacl failed with hr = 0x%x";
          v24 = 336;
        }
      }
      else
      {
        v22 = GetLastError();
        if ( v22 > 0 )
          v22 = (unsigned __int16)v22 | 0x80070000;
        v23 = L"AddAccessAllowedAce failed with hr = 0x%x";
        v24 = 329;
      }
    }
    else
    {
      v22 = GetLastError();
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      v23 = L"InitializeAcl failed with hr = 0x%x";
      v24 = 320;
    }
    nSubAuthority2a[0] = v22;
    v30 = v22;
    TracePrintW(
      2u,
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrldevicehelpers.cpp",
      v24,
      v23,
      *(_QWORD *)nSubAuthority2a);
LABEL_32:
    LocalFree(v21);
    goto LABEL_33;
  }
  v15 = GetLastError();
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x80070000;
  v30 = v15;
  nSubAuthority2a[0] = v15;
  TracePrintW(
    2u,
    "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrldevicehelpers.cpp",
    0x120u,
    L"AllocateAndInitializeSid failed with hr = 0x%x",
    *(_QWORD *)nSubAuthority2a);
LABEL_34:
  if ( pGroup )
    FreeSid(pGroup);
  v26 = v30;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v34);
  return v26;
}

```

## disassembly

```asm
0x18001be78  push    rbp
0x18001be7a  push    rbx
0x18001be7b  push    rsi
0x18001be7c  push    rdi
0x18001be7d  push    r12
0x18001be7f  push    r13
0x18001be81  push    r14
0x18001be83  push    r15
0x18001be85  lea     rbp, [rsp-7]
0x18001be8a  sub     rsp, 0D8h
0x18001be91  mov     rax, cs:__security_cookie
0x18001be98  xor     rax, rsp
0x18001be9b  mov     [rbp+3Fh+var_48], rax
0x18001be9f  mov     r15, [rbp+3Fh+AccessStatus]
0x18001bea6  lea     r14, aClientcoreDsEx_9; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001bead  xor     r13d, r13d
0x18001beb0  mov     word ptr [rbp+3Fh+pIdentifierAuthority.Value+4], 500h
0x18001beb6  xor     eax, eax
0x18001beb8  mov     [rbp+3Fh+var_B0], r13d
0x18001bebc  xorps   xmm0, xmm0
0x18001bebf  mov     [rbp+3Fh+PrivilegeSet.Privilege.Attributes], eax
0x18001bec2  mov     bl, dl
0x18001bec4  mov     dword ptr [rbp+3Fh+pIdentifierAuthority.Value], r13d
0x18001bec8  lea     rax, [rbp+3Fh+var_B0]
0x18001becc  mov     [rbp+3Fh+GrantedAccess], r13d
0x18001bed0  mov     esi, r9d
0x18001bed3  mov     [rbp+3Fh+var_90], rax
0x18001bed7  mov     edi, r8d
0x18001beda  mov     [rbp+3Fh+PrivilegeSetLength], 14h
0x18001bee1  mov     r12, rcx
0x18001bee4  mov     [rbp+3Fh+pGroup], r13
0x18001bee8  lea     rdx, aClientdeviceid; "ClientDeviceIdHelpers::IsLoggedInUserMa"...
0x18001beef  mov     [rbp+3Fh+var_88], r13
0x18001bef3  xor     r9d, r9d; unsigned int
0x18001bef6  mov     [rbp+3Fh+var_98], rdx
0x18001befa  mov     r8d, 0FCh; char *
0x18001bf00  mov     [rbp+3Fh+var_80], r13
0x18001bf04  mov     rcx, r14; this
0x18001bf07  movups  xmmword ptr [rbp+3Fh+PrivilegeSet.PrivilegeCount], xmm0
0x18001bf0b  movups  xmmword ptr [rbp+3Fh+GenericMapping.GenericRead], xmm0
0x18001bf0f  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001bf14  lea     rax, [rbp+3Fh+pGroup]
0x18001bf18  mov     [r15], r13d
0x18001bf1b  mov     [rsp+110h+pSid], rax; pSid
0x18001bf20  lea     rcx, [rbp+3Fh+pIdentifierAuthority]; pIdentifierAuthority
0x18001bf24  mov     [rsp+110h+nSubAuthority7], r13d; nSubAuthority7
0x18001bf29  mov     r9d, esi; nSubAuthority1
0x18001bf2c  mov     [rsp+110h+nSubAuthority6], r13d; nSubAuthority6
0x18001bf31  mov     r8d, edi; nSubAuthority0
0x18001bf34  mov     [rsp+110h+nSubAuthority5], r13d; nSubAuthority5
0x18001bf39  mov     dl, bl; nSubAuthorityCount
0x18001bf3b  mov     [rsp+110h+nSubAuthority4], r13d; nSubAuthority4
0x18001bf40  mov     [rsp+110h+nSubAuthority3], r13d; nSubAuthority3
0x18001bf45  mov     [rsp+110h+nSubAuthority2], r13d; nSubAuthority2
0x18001bf4a  call    cs:__imp_AllocateAndInitializeSid
0x18001bf50  test    eax, eax
0x18001bf52  jnz     short loc_18001BF8C
0x18001bf54  call    cs:__imp_GetLastError
0x18001bf5a  test    eax, eax
0x18001bf5c  jle     short loc_18001BF66
0x18001bf5e  movzx   eax, ax
0x18001bf61  or      eax, 80070000h
0x18001bf66  lea     r9, aAllocateandini; "AllocateAndInitializeSid failed with hr"...
0x18001bf6d  mov     [rbp+3Fh+var_B0], eax
0x18001bf70  mov     r8d, 120h; unsigned int
0x18001bf76  mov     [rsp+110h+nSubAuthority2], eax
0x18001bf7a  mov     rdx, r14; char *
0x18001bf7d  mov     ecx, 2; unsigned __int8
0x18001bf82  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001bf87  jmp     loc_18001C19D
0x18001bf8c  mov     edx, 28h ; '('; uBytes
0x18001bf91  lea     ebx, [rdx+18h]
0x18001bf94  mov     ecx, ebx; uFlags
0x18001bf96  call    cs:__imp_LocalAlloc
0x18001bf9c  mov     rdi, rax
0x18001bf9f  test    rax, rax
0x18001bfa2  jnz     short loc_18001BFB0
0x18001bfa4  mov     [rbp+3Fh+var_B0], 8007000Eh
0x18001bfab  jmp     loc_18001C19D
0x18001bfb0  mov     edx, 1; dwRevision
0x18001bfb5  mov     rcx, rdi; pSecurityDescriptor
0x18001bfb8  call    cs:__imp_InitializeSecurityDescriptor
0x18001bfbe  test    eax, eax
0x18001bfc0  jnz     short loc_18001BFFA
0x18001bfc2  call    cs:__imp_GetLastError
0x18001bfc8  test    eax, eax
0x18001bfca  jle     short loc_18001BFD4
0x18001bfcc  movzx   eax, ax
0x18001bfcf  or      eax, 80070000h
0x18001bfd4  lea     r9, aInitializesecu; "InitializeSecurityDescriptor failed wit"...
0x18001bfdb  mov     [rbp+3Fh+var_B0], eax
0x18001bfde  mov     r8d, 12Eh; unsigned int
0x18001bfe4  mov     [rsp+110h+nSubAuthority2], eax
0x18001bfe8  mov     rdx, r14; char *
0x18001bfeb  mov     ecx, 2; unsigned __int8
0x18001bff0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001bff5  jmp     loc_18001C194
0x18001bffa  mov     rcx, [rbp+3Fh+pGroup]; pSid
0x18001bffe  call    cs:__imp_GetLengthSid
0x18001c004  mov     ecx, ebx; uFlags
0x18001c006  lea     r14d, [rax+10h]
0x18001c00a  mov     edx, r14d; uBytes
0x18001c00d  call    cs:__imp_LocalAlloc
0x18001c013  mov     rsi, rax
0x18001c016  test    rax, rax
0x18001c019  jnz     short loc_18001C027
0x18001c01b  mov     [rbp+3Fh+var_B0], 8007000Eh
0x18001c022  jmp     loc_18001C194
0x18001c027  mov     ebx, 2
0x18001c02c  mov     edx, r14d; nAclLength
0x18001c02f  mov     r8d, ebx; dwAclRevision
0x18001c032  mov     rcx, rsi; pAcl
0x18001c035  call    cs:__imp_InitializeAcl
0x18001c03b  test    eax, eax
0x18001c03d  jnz     short loc_18001C078
0x18001c03f  call    cs:__imp_GetLastError
0x18001c045  test    eax, eax
0x18001c047  jle     short loc_18001C051
0x18001c049  movzx   eax, ax
0x18001c04c  or      eax, 80070000h
0x18001c051  lea     r9, aInitializeaclF; "InitializeAcl failed with hr = 0x%x"
0x18001c058  mov     r8d, 140h; unsigned int
0x18001c05e  lea     rdx, aClientcoreDsEx_9; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001c065  mov     [rsp+110h+nSubAuthority2], eax
0x18001c069  mov     ecx, ebx; unsigned __int8
0x18001c06b  mov     [rbp+3Fh+var_B0], eax
0x18001c06e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001c073  jmp     loc_18001C18B
0x18001c078  mov     r9, [rbp+3Fh+pGroup]; pSid
0x18001c07c  mov     r8d, 3; AccessMask
0x18001c082  mov     edx, ebx; dwAceRevision
0x18001c084  mov     rcx, rsi; pAcl
0x18001c087  call    cs:__imp_AddAccessAllowedAce
0x18001c08d  test    eax, eax
0x18001c08f  jnz     short loc_18001C0B2
0x18001c091  call    cs:__imp_GetLastError
0x18001c097  test    eax, eax
0x18001c099  jle     short loc_18001C0A3
0x18001c09b  movzx   eax, ax
0x18001c09e  or      eax, 80070000h
0x18001c0a3  lea     r9, aAddaccessallow; "AddAccessAllowedAce failed with hr = 0x"...
0x18001c0aa  mov     r8d, 149h
0x18001c0b0  jmp     short loc_18001C05E
0x18001c0b2  xor     r9d, r9d; bDaclDefaulted
0x18001c0b5  mov     r8, rsi; pDacl
0x18001c0b8  mov     rcx, rdi; pSecurityDescriptor
0x18001c0bb  lea     r14d, [r9+1]
0x18001c0bf  mov     edx, r14d; bDaclPresent
0x18001c0c2  call    cs:__imp_SetSecurityDescriptorDacl
0x18001c0c8  test    eax, eax
0x18001c0ca  jnz     short loc_18001C0F0
0x18001c0cc  call    cs:__imp_GetLastError
0x18001c0d2  test    eax, eax
0x18001c0d4  jle     short loc_18001C0DE
0x18001c0d6  movzx   eax, ax
0x18001c0d9  or      eax, 80070000h
0x18001c0de  lea     r9, aSetsecuritydes; "SetSecurityDescriptorDacl failed with h"...
0x18001c0e5  mov     r8d, 150h
0x18001c0eb  jmp     loc_18001C05E
0x18001c0f0  mov     rdx, [rbp+3Fh+pGroup]; pGroup
0x18001c0f4  xor     r8d, r8d; bGroupDefaulted
0x18001c0f7  mov     rcx, rdi; pSecurityDescriptor
0x18001c0fa  call    cs:__imp_SetSecurityDescriptorGroup
0x18001c100  mov     rdx, [rbp+3Fh+pGroup]; pOwner
0x18001c104  xor     r8d, r8d; bOwnerDefaulted
0x18001c107  mov     rcx, rdi; pSecurityDescriptor
0x18001c10a  call    cs:__imp_SetSecurityDescriptorOwner
0x18001c110  mov     rcx, rdi; pSecurityDescriptor
0x18001c113  call    cs:__imp_IsValidSecurityDescriptor
0x18001c119  test    eax, eax
0x18001c11b  jnz     short loc_18001C141
0x18001c11d  call    cs:__imp_GetLastError
0x18001c123  test    eax, eax
0x18001c125  jle     short loc_18001C12F
0x18001c127  movzx   eax, ax
0x18001c12a  or      eax, 80070000h
0x18001c12f  lea     r9, aIsvalidsecurit; "IsValidSecurityDescriptor failed with h"...
0x18001c136  mov     r8d, 15Eh
0x18001c13c  jmp     loc_18001C05E
0x18001c141  mov     rdx, [r12]; ClientToken
0x18001c145  lea     rax, [rbp+3Fh+GrantedAccess]
0x18001c149  mov     qword ptr [rsp+110h+nSubAuthority5], r15; AccessStatus
0x18001c14e  lea     r9, [rbp+3Fh+GenericMapping]; GenericMapping
0x18001c152  mov     qword ptr [rsp+110h+nSubAuthority4], rax; GrantedAccess
0x18001c157  mov     r8d, r14d; DesiredAccess
0x18001c15a  lea     rax, [rbp+3Fh+PrivilegeSetLength]
0x18001c15e  mov     [rbp+3Fh+GenericMapping.GenericRead], r14d
0x18001c162  mov     qword ptr [rsp+110h+nSubAuthority3], rax; PrivilegeSetLength
0x18001c167  mov     rcx, rdi; pSecurityDescriptor
0x18001c16a  lea     rax, [rbp+3Fh+PrivilegeSet]
0x18001c16e  mov     qword ptr [rbp+3Fh+GenericMapping.GenericWrite], rbx
0x18001c172  mov     qword ptr [rsp+110h+nSubAuthority2], rax; PrivilegeSet
0x18001c177  mov     [rbp+3Fh+GenericMapping.GenericAll], 3
0x18001c17e  call    cs:__imp_AccessCheck
0x18001c184  test    eax, eax
0x18001c186  jnz     short loc_18001C18B
0x18001c188  mov     [r15], r13d
0x18001c18b  mov     rcx, rsi; hMem
0x18001c18e  call    cs:__imp_LocalFree
0x18001c194  mov     rcx, rdi; hMem
0x18001c197  call    cs:__imp_LocalFree
0x18001c19d  mov     rcx, [rbp+3Fh+pGroup]; pSid
0x18001c1a1  test    rcx, rcx
0x18001c1a4  jz      short loc_18001C1AC
0x18001c1a6  call    cs:__imp_FreeSid
0x18001c1ac  mov     ebx, [rbp+3Fh+var_B0]
0x18001c1af  lea     rcx, [rbp+3Fh+var_98]
0x18001c1b3  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001c1b8  mov     eax, ebx
0x18001c1ba  mov     rcx, [rbp+3Fh+var_48]
0x18001c1be  xor     rcx, rsp; StackCookie
0x18001c1c1  call    __security_check_cookie
0x18001c1c6  add     rsp, 0D8h
0x18001c1cd  pop     r15
0x18001c1cf  pop     r14
0x18001c1d1  pop     r13
0x18001c1d3  pop     r12
0x18001c1d5  pop     rdi
0x18001c1d6  pop     rsi
0x18001c1d7  pop     rbx
0x18001c1d8  pop     rbp
0x18001c1d9  retn
```
