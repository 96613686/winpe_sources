# WlidsvcUtil::IsLoggedInUserMatchSID(ATL::CHandle &,uchar,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int &)

- ea: `0x1800f410c`
- end: `0x1800f44aa`
- name: `?IsLoggedInUserMatchSID@WlidsvcUtil@@SAJAEAVCHandle@ATL@@EKKKKKKKKAEAH@Z`
- size: `926`
- prototype: `__int64 __fastcall(void **, BYTE, DWORD, DWORD, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, int *AccessStatus)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003ad50`
- `0x1800f3db8`

## callees

- `0x18000c050`
- `0x18001a9c0`
- `0x18001ad00`
- `0x1800a3b60`
- `0x1800f410c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f445e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f4467`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f445e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f4467`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f4238`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f42bb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f4238`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f42bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f41ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f42ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f438d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f43e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f41ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f42ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f438d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f43e2`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800f42e0`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800f42e0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800f43cf`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800f43cf`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800f41de`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800f41de`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800f4347`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800f4347`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800f43bf`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800f43bf`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800f43d8`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800f43d8`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800f444e`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800f444e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f4476`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f4476`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800f425a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800f425a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800f4383`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800f4383`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800f42ab`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800f42ab`

## string_xrefs

- `0x1800f4194`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\wlidsvcutil.cpp`
- `0x1800f421f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\wlidsvcutil.cpp`
- `0x1800f4296`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\wlidsvcutil.cpp`
- `0x1800f431c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\wlidsvcutil.cpp`
- `0x1800f413a`: `WlidsvcUtil::IsLoggedInUserMatchSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=72
__int64 __fastcall WlidsvcUtil::IsLoggedInUserMatchSID(
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
  signed int LastError; // eax
  signed int v16; // r9d
  HLOCAL v17; // rax
  void *v18; // rbx
  signed int v19; // eax
  signed int v20; // r9d
  DWORD v21; // esi
  struct _ACL *v22; // rax
  struct _ACL *v23; // rdi
  signed int v24; // eax
  signed int v25; // r9d
  unsigned int v26; // r8d
  signed int v27; // eax
  signed int v28; // eax
  signed int v29; // eax
  void *v30; // rdx
  unsigned int v31; // ebx
  const unsigned __int16 *nSubAuthority2; // [rsp+20h] [rbp-B1h]
  int v34; // [rsp+60h] [rbp-71h] BYREF
  PSID pGroup; // [rsp+68h] [rbp-69h] BYREF
  DWORD GrantedAccess; // [rsp+70h] [rbp-61h] BYREF
  DWORD PrivilegeSetLength; // [rsp+74h] [rbp-5Dh] BYREF
  _QWORD v38[4]; // [rsp+78h] [rbp-59h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp-39h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+A0h] [rbp-31h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+B0h] [rbp-21h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v34 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v38[1] = &v34;
  GrantedAccess = 0;
  PrivilegeSetLength = 20;
  pGroup = 0;
  v38[0] = "WlidsvcUtil::IsLoggedInUserMatchSID";
  v38[2] = 0;
  v38[3] = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GenericMapping = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\wlidsvcutil.cpp",
    "WlidsvcUtil::IsLoggedInUserMatchSID",
    (const char *)0x217,
    0,
    nSubAuthority2);
  *AccessStatus = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, a2, a3, a4, 0, 0, 0, 0, 0, 0, &pGroup) )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    v34 = v16;
    if ( v16 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\wlidsvcutil.cpp",
        "WlidsvcUtil::IsLoggedInUserMatchSID",
        0x238u,
        v16,
        "hr = HRESULT_FROM_WIN32(GetLastError())");
      goto LABEL_40;
    }
  }
  v17 = LocalAlloc(0x40u, 0x28u);
  v18 = v17;
  if ( !v17 )
  {
    v34 = -2147024882;
    goto LABEL_40;
  }
  if ( InitializeSecurityDescriptor(v17, 1u) )
    goto LABEL_13;
  v19 = GetLastError();
  v20 = v19;
  if ( v19 > 0 )
    v20 = (unsigned __int16)v19 | 0x80070000;
  v34 = v20;
  if ( v20 >= 0 )
  {
LABEL_13:
    v21 = GetLengthSid(pGroup) + 16;
    v22 = (struct _ACL *)LocalAlloc(0x40u, v21);
    v23 = v22;
    if ( !v22 )
    {
      v34 = -2147024882;
      goto LABEL_39;
    }
    if ( InitializeAcl(v22, v21, 2u) )
      goto LABEL_45;
    v24 = GetLastError();
    v25 = v24;
    if ( v24 > 0 )
      v25 = (unsigned __int16)v24 | 0x80070000;
    v34 = v25;
    if ( v25 >= 0 )
    {
LABEL_45:
      if ( AddAccessAllowedAce(v23, 2u, 3u, pGroup) )
        goto LABEL_46;
      v27 = GetLastError();
      v25 = v27;
      if ( v27 > 0 )
        v25 = (unsigned __int16)v27 | 0x80070000;
      v34 = v25;
      if ( v25 >= 0 )
      {
LABEL_46:
        if ( SetSecurityDescriptorDacl(v18, 1, v23, 0) )
          goto LABEL_31;
        v28 = GetLastError();
        v25 = v28;
        if ( v28 > 0 )
          v25 = (unsigned __int16)v28 | 0x80070000;
        v34 = v25;
        if ( v25 >= 0 )
        {
LABEL_31:
          SetSecurityDescriptorGroup(v18, pGroup, 0);
          SetSecurityDescriptorOwner(v18, pGroup, 0);
          if ( IsValidSecurityDescriptor(v18) )
            goto LABEL_36;
          v29 = GetLastError();
          v25 = v29;
          if ( v29 > 0 )
            v25 = (unsigned __int16)v29 | 0x80070000;
          v34 = v25;
          if ( v25 >= 0 )
          {
LABEL_36:
            v30 = *a1;
            GenericMapping.GenericRead = 1;
            *(_QWORD *)&GenericMapping.GenericWrite = 2;
            GenericMapping.GenericAll = 3;
            if ( !AccessCheck(
                    v18,
                    v30,
                    1u,
                    &GenericMapping,
                    &PrivilegeSet,
                    &PrivilegeSetLength,
                    &GrantedAccess,
                    AccessStatus) )
              *AccessStatus = 0;
            goto LABEL_38;
          }
          v26 = 595;
        }
        else
        {
          v26 = 586;
        }
      }
      else
      {
        v26 = 584;
      }
    }
    else
    {
      v26 = 580;
    }
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\wlidsvcutil.cpp",
      "WlidsvcUtil::IsLoggedInUserMatchSID",
      v26,
      v25,
      "hr = HRESULT_FROM_WIN32(GetLastError())");
LABEL_38:
    LocalFree(v23);
    goto LABEL_39;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\wlidsvcutil.cpp",
    "WlidsvcUtil::IsLoggedInUserMatchSID",
    0x23Cu,
    v20,
    "hr = HRESULT_FROM_WIN32(GetLastError())");
LABEL_39:
  LocalFree(v18);
LABEL_40:
  if ( pGroup )
    FreeSid(pGroup);
  v31 = v34;
  CTraceFuncW<long>::~CTraceFuncW<long>(v38);
  return v31;
}

```

## disassembly

```asm
0x1800f410c  push    rbp
0x1800f410e  push    rbx
0x1800f410f  push    rsi
0x1800f4110  push    rdi
0x1800f4111  push    r12
0x1800f4113  push    r13
0x1800f4115  push    r14
0x1800f4117  push    r15
0x1800f4119  lea     rbp, [rsp-7]
0x1800f411e  sub     rsp, 0D8h
0x1800f4125  mov     rax, cs:__security_cookie
0x1800f412c  xor     rax, rsp
0x1800f412f  mov     [rbp+3Fh+var_48], rax
0x1800f4133  mov     r14, [rbp+3Fh+AccessStatus]
0x1800f413a  lea     r13, aWlidsvcutilIsl; "WlidsvcUtil::IsLoggedInUserMatchSID"
0x1800f4141  xor     r12d, r12d
0x1800f4144  mov     word ptr [rbp+3Fh+pIdentifierAuthority.Value+4], 500h
0x1800f414a  xor     eax, eax
0x1800f414c  mov     [rbp+3Fh+var_B0], r12d
0x1800f4150  xorps   xmm0, xmm0
0x1800f4153  mov     [rbp+3Fh+PrivilegeSet.Privilege.Attributes], eax
0x1800f4156  lea     rax, [rbp+3Fh+var_B0]
0x1800f415a  mov     dword ptr [rbp+3Fh+pIdentifierAuthority.Value], r12d
0x1800f415e  mov     esi, r9d
0x1800f4161  mov     [rbp+3Fh+var_90], rax
0x1800f4165  mov     edi, r8d
0x1800f4168  mov     [rbp+3Fh+GrantedAccess], r12d
0x1800f416c  mov     bl, dl
0x1800f416e  mov     [rbp+3Fh+PrivilegeSetLength], 14h
0x1800f4175  mov     r15, rcx
0x1800f4178  mov     [rbp+3Fh+pGroup], r12
0x1800f417c  xor     r9d, r9d; unsigned int
0x1800f417f  mov     [rbp+3Fh+var_98], r13
0x1800f4183  mov     r8d, 217h; char *
0x1800f4189  mov     [rbp+3Fh+var_88], r12
0x1800f418d  mov     rdx, r13; char *
0x1800f4190  mov     [rbp+3Fh+var_80], r12
0x1800f4194  lea     rcx, aOnecoreuapDsEx_84; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f419b  movups  xmmword ptr [rbp+3Fh+PrivilegeSet.PrivilegeCount], xmm0
0x1800f419f  movups  xmmword ptr [rbp+3Fh+GenericMapping.GenericRead], xmm0
0x1800f41a3  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800f41a8  lea     rax, [rbp+3Fh+pGroup]
0x1800f41ac  mov     [r14], r12d
0x1800f41af  mov     [rsp+110h+pSid], rax; pSid
0x1800f41b4  lea     rcx, [rbp+3Fh+pIdentifierAuthority]; pIdentifierAuthority
0x1800f41b8  mov     [rsp+110h+nSubAuthority7], r12d; nSubAuthority7
0x1800f41bd  mov     r9d, esi; nSubAuthority1
0x1800f41c0  mov     [rsp+110h+nSubAuthority6], r12d; nSubAuthority6
0x1800f41c5  mov     r8d, edi; nSubAuthority0
0x1800f41c8  mov     [rsp+110h+nSubAuthority5], r12d; nSubAuthority5
0x1800f41cd  mov     dl, bl; nSubAuthorityCount
0x1800f41cf  mov     [rsp+110h+nSubAuthority4], r12d; nSubAuthority4
0x1800f41d4  mov     [rsp+110h+nSubAuthority3], r12d; nSubAuthority3
0x1800f41d9  mov     [rsp+110h+nSubAuthority2], r12d; nSubAuthority2
0x1800f41de  call    cs:__imp_AllocateAndInitializeSid
0x1800f41e4  mov     edi, 80070000h
0x1800f41e9  test    eax, eax
0x1800f41eb  jnz     short loc_1800F4230
0x1800f41ed  call    cs:__imp_GetLastError
0x1800f41f3  mov     r9d, eax
0x1800f41f6  test    eax, eax
0x1800f41f8  jle     short loc_1800F4201
0x1800f41fa  movzx   r9d, ax
0x1800f41fe  or      r9d, edi; int
0x1800f4201  mov     [rbp+3Fh+var_B0], r9d
0x1800f4205  test    r9d, r9d
0x1800f4208  jns     short loc_1800F4230
0x1800f420a  lea     rax, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800f4211  mov     r8d, 238h; unsigned int
0x1800f4217  mov     rdx, r13; char *
0x1800f421a  mov     qword ptr [rsp+110h+nSubAuthority2], rax; char *
0x1800f421f  lea     rcx, aOnecoreuapDsEx_84; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f4226  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800f422b  jmp     loc_1800F446D
0x1800f4230  mov     edx, 28h ; '('; uBytes
0x1800f4235  lea     ecx, [rdx+18h]; uFlags
0x1800f4238  call    cs:__imp_LocalAlloc
0x1800f423e  mov     rbx, rax
0x1800f4241  test    rax, rax
0x1800f4244  jnz     short loc_1800F4252
0x1800f4246  mov     [rbp+3Fh+var_B0], 8007000Eh
0x1800f424d  jmp     loc_1800F446D
0x1800f4252  mov     edx, 1; dwRevision
0x1800f4257  mov     rcx, rbx; pSecurityDescriptor
0x1800f425a  call    cs:__imp_InitializeSecurityDescriptor
0x1800f4260  test    eax, eax
0x1800f4262  jnz     short loc_1800F42A7
0x1800f4264  call    cs:__imp_GetLastError
0x1800f426a  mov     r9d, eax
0x1800f426d  test    eax, eax
0x1800f426f  jle     short loc_1800F4278
0x1800f4271  movzx   r9d, ax
0x1800f4275  or      r9d, edi; int
0x1800f4278  mov     [rbp+3Fh+var_B0], r9d
0x1800f427c  test    r9d, r9d
0x1800f427f  jns     short loc_1800F42A7
0x1800f4281  lea     rax, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800f4288  mov     r8d, 23Ch; unsigned int
0x1800f428e  mov     rdx, r13; char *
0x1800f4291  mov     qword ptr [rsp+110h+nSubAuthority2], rax; char *
0x1800f4296  lea     rcx, aOnecoreuapDsEx_84; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f429d  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800f42a2  jmp     loc_1800F4464
0x1800f42a7  mov     rcx, [rbp+3Fh+pGroup]; pSid
0x1800f42ab  call    cs:__imp_GetLengthSid
0x1800f42b1  mov     ecx, 40h ; '@'; uFlags
0x1800f42b6  lea     esi, [rax+10h]
0x1800f42b9  mov     edx, esi; uBytes
0x1800f42bb  call    cs:__imp_LocalAlloc
0x1800f42c1  mov     rdi, rax
0x1800f42c4  test    rax, rax
0x1800f42c7  jnz     short loc_1800F42D5
0x1800f42c9  mov     [rbp+3Fh+var_B0], 8007000Eh
0x1800f42d0  jmp     loc_1800F4464
0x1800f42d5  mov     r8d, 2; dwAclRevision
0x1800f42db  mov     edx, esi; nAclLength
0x1800f42dd  mov     rcx, rdi; pAcl
0x1800f42e0  call    cs:__imp_InitializeAcl
0x1800f42e6  test    eax, eax
0x1800f42e8  jnz     short loc_1800F4332
0x1800f42ea  call    cs:__imp_GetLastError
0x1800f42f0  mov     r9d, eax
0x1800f42f3  mov     esi, 80070000h
0x1800f42f8  test    eax, eax
0x1800f42fa  jle     short loc_1800F4303
0x1800f42fc  movzx   r9d, ax
0x1800f4300  or      r9d, esi; int
0x1800f4303  mov     [rbp+3Fh+var_B0], r9d
0x1800f4307  test    r9d, r9d
0x1800f430a  jns     short loc_1800F4337
0x1800f430c  mov     r8d, 244h; unsigned int
0x1800f4312  lea     rax, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800f4319  mov     rdx, r13; char *
0x1800f431c  lea     rcx, aOnecoreuapDsEx_84; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f4323  mov     qword ptr [rsp+110h+nSubAuthority2], rax; char *
0x1800f4328  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800f432d  jmp     loc_1800F445B
0x1800f4332  mov     esi, 80070000h
0x1800f4337  mov     r9, [rbp+3Fh+pGroup]; pSid
0x1800f433b  mov     edx, 2; dwAceRevision
0x1800f4340  mov     rcx, rdi; pAcl
0x1800f4343  lea     r8d, [rdx+1]; AccessMask
0x1800f4347  call    cs:__imp_AddAccessAllowedAce
0x1800f434d  test    eax, eax
0x1800f434f  jnz     short loc_1800F4376
0x1800f4351  call    cs:__imp_GetLastError
0x1800f4357  mov     r9d, eax
0x1800f435a  test    eax, eax
0x1800f435c  jle     short loc_1800F4365
0x1800f435e  movzx   r9d, ax
0x1800f4362  or      r9d, esi
0x1800f4365  mov     [rbp+3Fh+var_B0], r9d
0x1800f4369  test    r9d, r9d
0x1800f436c  jns     short loc_1800F4376
0x1800f436e  mov     r8d, 248h
0x1800f4374  jmp     short loc_1800F4312
0x1800f4376  xor     r9d, r9d; bDaclDefaulted
0x1800f4379  mov     r8, rdi; pDacl
0x1800f437c  mov     rcx, rbx; pSecurityDescriptor
0x1800f437f  lea     edx, [r9+1]; bDaclPresent
0x1800f4383  call    cs:__imp_SetSecurityDescriptorDacl
0x1800f4389  test    eax, eax
0x1800f438b  jnz     short loc_1800F43B5
0x1800f438d  call    cs:__imp_GetLastError
0x1800f4393  mov     r9d, eax
0x1800f4396  test    eax, eax
0x1800f4398  jle     short loc_1800F43A1
0x1800f439a  movzx   r9d, ax
0x1800f439e  or      r9d, esi
0x1800f43a1  mov     [rbp+3Fh+var_B0], r9d
0x1800f43a5  test    r9d, r9d
0x1800f43a8  jns     short loc_1800F43B5
0x1800f43aa  mov     r8d, 24Ah
0x1800f43b0  jmp     loc_1800F4312
0x1800f43b5  mov     rdx, [rbp+3Fh+pGroup]; pGroup
0x1800f43b9  xor     r8d, r8d; bGroupDefaulted
0x1800f43bc  mov     rcx, rbx; pSecurityDescriptor
0x1800f43bf  call    cs:__imp_SetSecurityDescriptorGroup
0x1800f43c5  mov     rdx, [rbp+3Fh+pGroup]; pOwner
0x1800f43c9  xor     r8d, r8d; bOwnerDefaulted
0x1800f43cc  mov     rcx, rbx; pSecurityDescriptor
0x1800f43cf  call    cs:__imp_SetSecurityDescriptorOwner
0x1800f43d5  mov     rcx, rbx; pSecurityDescriptor
0x1800f43d8  call    cs:__imp_IsValidSecurityDescriptor
0x1800f43de  test    eax, eax
0x1800f43e0  jnz     short loc_1800F440A
0x1800f43e2  call    cs:__imp_GetLastError
0x1800f43e8  mov     r9d, eax
0x1800f43eb  test    eax, eax
0x1800f43ed  jle     short loc_1800F43F6
0x1800f43ef  movzx   r9d, ax
0x1800f43f3  or      r9d, esi
0x1800f43f6  mov     [rbp+3Fh+var_B0], r9d
0x1800f43fa  test    r9d, r9d
0x1800f43fd  jns     short loc_1800F440A
0x1800f43ff  mov     r8d, 253h
0x1800f4405  jmp     loc_1800F4312
0x1800f440a  mov     rdx, [r15]; ClientToken
0x1800f440d  lea     rax, [rbp+3Fh+GrantedAccess]
0x1800f4411  mov     qword ptr [rsp+110h+nSubAuthority5], r14; AccessStatus
0x1800f4416  lea     r9, [rbp+3Fh+GenericMapping]; GenericMapping
0x1800f441a  mov     qword ptr [rsp+110h+nSubAuthority4], rax; GrantedAccess
0x1800f441f  mov     ecx, 1
0x1800f4424  lea     rax, [rbp+3Fh+PrivilegeSetLength]
0x1800f4428  mov     [rbp+3Fh+GenericMapping.GenericRead], ecx
0x1800f442b  mov     qword ptr [rsp+110h+nSubAuthority3], rax; PrivilegeSetLength
0x1800f4430  mov     r8d, ecx; DesiredAccess
0x1800f4433  lea     rax, [rbp+3Fh+PrivilegeSet]
0x1800f4437  mov     qword ptr [rbp+3Fh+GenericMapping.GenericWrite], 2
0x1800f443f  mov     rcx, rbx; pSecurityDescriptor
0x1800f4442  mov     qword ptr [rsp+110h+nSubAuthority2], rax; PrivilegeSet
0x1800f4447  mov     [rbp+3Fh+GenericMapping.GenericAll], 3
0x1800f444e  call    cs:__imp_AccessCheck
0x1800f4454  test    eax, eax
0x1800f4456  jnz     short loc_1800F445B
0x1800f4458  mov     [r14], r12d
0x1800f445b  mov     rcx, rdi; hMem
0x1800f445e  call    cs:__imp_LocalFree
0x1800f4464  mov     rcx, rbx; hMem
0x1800f4467  call    cs:__imp_LocalFree
0x1800f446d  mov     rcx, [rbp+3Fh+pGroup]; pSid
0x1800f4471  test    rcx, rcx
0x1800f4474  jz      short loc_1800F447C
0x1800f4476  call    cs:__imp_FreeSid
0x1800f447c  mov     ebx, [rbp+3Fh+var_B0]
0x1800f447f  lea     rcx, [rbp+3Fh+var_98]
0x1800f4483  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800f4488  mov     eax, ebx
0x1800f448a  mov     rcx, [rbp+3Fh+var_48]
0x1800f448e  xor     rcx, rsp; StackCookie
0x1800f4491  call    __security_check_cookie
0x1800f4496  add     rsp, 0D8h
0x1800f449d  pop     r15
0x1800f449f  pop     r14
0x1800f44a1  pop     r13
0x1800f44a3  pop     r12
0x1800f44a5  pop     rdi
0x1800f44a6  pop     rsi
0x1800f44a7  pop     rbx
0x1800f44a8  pop     rbp
0x1800f44a9  retn
```
