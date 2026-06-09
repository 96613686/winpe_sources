# CSdRestoreServiceModule::_InitComSecurity(void)

- ea: `0x18000e108`
- end: `0x18000e41a`
- name: `?_InitComSecurity@CSdRestoreServiceModule@@AEAAJXZ`
- size: `786`
- prototype: `__int64 __fastcall(CSdRestoreServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ac34`

## callees

- `0x18000e108`
- `0x18001586c`
- `0x180015974`
- `0x18001c58c`
- `0x18002170a`
- `0x180021740`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e1e5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e221`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e1e5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e221`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000e1a1`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000e1a1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000e357`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000e357`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18000e31a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18000e31a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18000e2e2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18000e2e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e3db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e3db`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18000e284`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18000e284`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18000e3b3`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18000e3b3`

## string_xrefs

- `0x18000e139`: `CSdRestoreServiceModule::_InitComSecurity`

## pseudocode

```c
__int64 __fastcall CSdRestoreServiceModule::_InitComSecurity(CSdRestoreServiceModule *this)
{
  int LastFailureAsHRESULT; // ebx
  __int16 v2; // ax
  signed int v3; // eax
  DWORD cbSid; // [rsp+50h] [rbp-B0h] BYREF
  PACL NewAcl; // [rsp+58h] [rbp-A8h] BYREF
  int v7; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v8; // [rsp+64h] [rbp-9Ch]
  __int16 v9; // [rsp+66h] [rbp-9Ah]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+98h] [rbp-68h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v12; // [rsp+E8h] [rbp-18h]
  _BYTE pOwner[80]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE pSid[80]; // [rsp+140h] [rbp+40h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v7,
    "CSdRestoreServiceModule::_InitComSecurity",
    0x237u,
    1u);
  v12 = 0;
  NewAcl = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  memset_0(pOwner, 0, 0x48u);
  memset_0(pSid, 0, 0x48u);
  cbSid = 0;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v7 = LastFailureAsHRESULT;
    v2 = 577;
LABEL_3:
    v9 = v2;
    goto LABEL_21;
  }
  v7 = 0;
  cbSid = 72;
  v8 = 577;
  if ( !CreateWellKnownSid(WinAuthenticatedUserSid, 0, pSid, &cbSid) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v7 = LastFailureAsHRESULT;
    v2 = 581;
    goto LABEL_3;
  }
  v7 = 0;
  cbSid = 72;
  v8 = 581;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pOwner, &cbSid) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v7 = LastFailureAsHRESULT;
    v2 = 585;
    goto LABEL_3;
  }
  v7 = 0;
  pListOfExplicitEntries.grfAccessPermissions = 11;
  v8 = 585;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
  *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
  v3 = SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl);
  LastFailureAsHRESULT = v3;
  if ( v3 > 0 )
    LastFailureAsHRESULT = (unsigned __int16)v3 | 0x80070000;
  v7 = LastFailureAsHRESULT;
  v2 = 598;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v8 = 598;
  if ( !NewAcl )
  {
    LastFailureAsHRESULT = -2147024882;
    v9 = 599;
    v7 = -2147024882;
    goto LABEL_23;
  }
  v7 = 0;
  v8 = 599;
  if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v7 = LastFailureAsHRESULT;
    v2 = 602;
    goto LABEL_3;
  }
  v7 = 0;
  v8 = 602;
  if ( !SetSecurityDescriptorGroup(pSecurityDescriptor, pOwner, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v7 = LastFailureAsHRESULT;
    v2 = 605;
    goto LABEL_3;
  }
  v7 = 0;
  v8 = 605;
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v7 = LastFailureAsHRESULT;
    v2 = 608;
    goto LABEL_3;
  }
  v7 = 0;
  v8 = 608;
  LastFailureAsHRESULT = CoInitializeSecurity(pSecurityDescriptor, -1, 0, 0, 6u, 2u, 0, 0x3040u, 0);
  v7 = LastFailureAsHRESULT;
  v2 = 612;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v8 = 612;
LABEL_21:
  if ( NewAcl )
  {
    LocalFree(NewAcl);
    LastFailureAsHRESULT = v7;
    NewAcl = 0;
  }
LABEL_23:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v7);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18000e108  mov     [rsp-8+arg_0], rbx
0x18000e10d  mov     [rsp-8+arg_8], rdi
0x18000e112  push    rbp
0x18000e113  lea     rbp, [rsp-0A0h]
0x18000e11b  sub     rsp, 1A0h
0x18000e122  mov     rax, cs:__security_cookie
0x18000e129  xor     rax, rsp
0x18000e12c  mov     [rbp+0A0h+var_10], rax
0x18000e133  mov     r9d, 1; unsigned __int16
0x18000e139  lea     rdx, aCsdrestoreserv_4; "CSdRestoreServiceModule::_InitComSecuri"...
0x18000e140  mov     r8d, 237h; unsigned __int16
0x18000e146  lea     rcx, [rsp+1A0h+var_140]; this
0x18000e14b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e150  xorps   xmm1, xmm1
0x18000e153  lea     rcx, [rbp+0A0h+pOwner]; void *
0x18000e157  xor     eax, eax
0x18000e159  xorps   xmm0, xmm0
0x18000e15c  xor     edi, edi
0x18000e15e  mov     [rbp+0A0h+var_B8], rax
0x18000e162  xor     edx, edx; Val
0x18000e164  mov     [rsp+1A0h+NewAcl], rdi
0x18000e169  movups  [rbp+0A0h+pSecurityDescriptor], xmm0
0x18000e16d  lea     ebx, [rax+48h]
0x18000e170  mov     r8d, ebx; Size
0x18000e173  movups  [rbp+0A0h+var_C8], xmm0
0x18000e177  movups  xmmword ptr [rbp+0A0h+pListOfExplicitEntries.grfAccessPermissions], xmm1
0x18000e17b  movups  xmmword ptr [rbp+0A0h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm1
0x18000e17f  movups  xmmword ptr [rbp+0A0h+pListOfExplicitEntries.Trustee.TrusteeType], xmm1
0x18000e183  call    memset_0
0x18000e188  mov     r8d, ebx; Size
0x18000e18b  lea     rcx, [rbp+0A0h+pSid]; void *
0x18000e18f  xor     edx, edx; Val
0x18000e191  call    memset_0
0x18000e196  lea     edx, [rdi+1]; dwRevision
0x18000e199  mov     [rsp+1A0h+cbSid], edi
0x18000e19d  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18000e1a1  call    cs:__imp_InitializeSecurityDescriptor
0x18000e1a7  test    eax, eax
0x18000e1a9  jnz     short loc_18000E1C5
0x18000e1ab  call    GetLastFailureAsHRESULT
0x18000e1b0  mov     ebx, eax
0x18000e1b2  mov     [rsp+1A0h+var_140], eax
0x18000e1b6  mov     eax, 241h
0x18000e1bb  mov     [rsp+1A0h+var_13A], ax
0x18000e1c0  jmp     loc_18000E3D1
0x18000e1c5  xor     edx, edx; DomainSid
0x18000e1c7  mov     [rsp+1A0h+var_140], edi
0x18000e1cb  mov     eax, 241h
0x18000e1d0  mov     [rsp+1A0h+cbSid], ebx
0x18000e1d4  lea     r9, [rsp+1A0h+cbSid]; cbSid
0x18000e1d9  mov     [rsp+1A0h+var_13C], ax
0x18000e1de  lea     r8, [rbp+0A0h+pSid]; pSid
0x18000e1e2  lea     ecx, [rdx+11h]; WellKnownSidType
0x18000e1e5  call    cs:__imp_CreateWellKnownSid
0x18000e1eb  test    eax, eax
0x18000e1ed  jnz     short loc_18000E201
0x18000e1ef  call    GetLastFailureAsHRESULT
0x18000e1f4  mov     ebx, eax
0x18000e1f6  mov     [rsp+1A0h+var_140], eax
0x18000e1fa  mov     eax, 245h
0x18000e1ff  jmp     short loc_18000E1BB
0x18000e201  xor     edx, edx; DomainSid
0x18000e203  mov     [rsp+1A0h+var_140], edi
0x18000e207  mov     eax, 245h
0x18000e20c  mov     [rsp+1A0h+cbSid], ebx
0x18000e210  lea     r9, [rsp+1A0h+cbSid]; cbSid
0x18000e215  mov     [rsp+1A0h+var_13C], ax
0x18000e21a  lea     r8, [rbp+0A0h+pOwner]; pSid
0x18000e21e  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18000e221  call    cs:__imp_CreateWellKnownSid
0x18000e227  test    eax, eax
0x18000e229  jnz     short loc_18000E240
0x18000e22b  call    GetLastFailureAsHRESULT
0x18000e230  mov     ebx, eax
0x18000e232  mov     [rsp+1A0h+var_140], eax
0x18000e236  mov     eax, 249h
0x18000e23b  jmp     loc_18000E1BB
0x18000e240  xor     r8d, r8d; OldAcl
0x18000e243  mov     [rsp+1A0h+var_140], edi
0x18000e247  mov     eax, 249h
0x18000e24c  mov     [rbp+0A0h+pListOfExplicitEntries.grfAccessPermissions], 0Bh
0x18000e253  mov     [rsp+1A0h+var_13C], ax
0x18000e258  lea     r9, [rsp+1A0h+NewAcl]; NewAcl
0x18000e25d  lea     rax, [rbp+0A0h+pSid]
0x18000e261  mov     qword ptr [rbp+0A0h+pListOfExplicitEntries.grfAccessMode], 2
0x18000e269  lea     ecx, [r8+1]; cCountOfExplicitEntries
0x18000e26d  mov     [rbp+0A0h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rdi
0x18000e271  lea     rdx, [rbp+0A0h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18000e275  mov     qword ptr [rbp+0A0h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], rdi
0x18000e279  mov     [rbp+0A0h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x18000e280  mov     [rbp+0A0h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18000e284  call    cs:__imp_SetEntriesInAclW
0x18000e28a  mov     ebx, eax
0x18000e28c  test    eax, eax
0x18000e28e  jle     short loc_18000E299
0x18000e290  movzx   ebx, ax
0x18000e293  or      ebx, 80070000h
0x18000e299  mov     [rsp+1A0h+var_140], ebx
0x18000e29d  mov     eax, 256h
0x18000e2a2  test    ebx, ebx
0x18000e2a4  js      loc_18000E1BB
0x18000e2aa  mov     [rsp+1A0h+var_13C], ax
0x18000e2af  mov     eax, 257h
0x18000e2b4  cmp     [rsp+1A0h+NewAcl], rdi
0x18000e2b9  jnz     short loc_18000E2CE
0x18000e2bb  mov     ebx, 8007000Eh
0x18000e2c0  mov     [rsp+1A0h+var_13A], ax
0x18000e2c5  mov     [rsp+1A0h+var_140], ebx
0x18000e2c9  jmp     loc_18000E3EA
0x18000e2ce  xor     r8d, r8d; bOwnerDefaulted
0x18000e2d1  mov     [rsp+1A0h+var_140], edi
0x18000e2d5  lea     rdx, [rbp+0A0h+pOwner]; pOwner
0x18000e2d9  mov     [rsp+1A0h+var_13C], ax
0x18000e2de  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18000e2e2  call    cs:__imp_SetSecurityDescriptorOwner
0x18000e2e8  test    eax, eax
0x18000e2ea  jnz     short loc_18000E301
0x18000e2ec  call    GetLastFailureAsHRESULT
0x18000e2f1  mov     ebx, eax
0x18000e2f3  mov     [rsp+1A0h+var_140], eax
0x18000e2f7  mov     eax, 25Ah
0x18000e2fc  jmp     loc_18000E1BB
0x18000e301  mov     eax, 25Ah
0x18000e306  mov     [rsp+1A0h+var_140], edi
0x18000e30a  xor     r8d, r8d; bGroupDefaulted
0x18000e30d  mov     [rsp+1A0h+var_13C], ax
0x18000e312  lea     rdx, [rbp+0A0h+pOwner]; pGroup
0x18000e316  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18000e31a  call    cs:__imp_SetSecurityDescriptorGroup
0x18000e320  test    eax, eax
0x18000e322  jnz     short loc_18000E339
0x18000e324  call    GetLastFailureAsHRESULT
0x18000e329  mov     ebx, eax
0x18000e32b  mov     [rsp+1A0h+var_140], eax
0x18000e32f  mov     eax, 25Dh
0x18000e334  jmp     loc_18000E1BB
0x18000e339  mov     r8, [rsp+1A0h+NewAcl]; pDacl
0x18000e33e  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18000e342  xor     r9d, r9d; bDaclDefaulted
0x18000e345  mov     [rsp+1A0h+var_140], edi
0x18000e349  mov     eax, 25Dh
0x18000e34e  mov     [rsp+1A0h+var_13C], ax
0x18000e353  lea     edx, [r9+1]; bDaclPresent
0x18000e357  call    cs:__imp_SetSecurityDescriptorDacl
0x18000e35d  test    eax, eax
0x18000e35f  jnz     short loc_18000E376
0x18000e361  call    GetLastFailureAsHRESULT
0x18000e366  mov     ebx, eax
0x18000e368  mov     [rsp+1A0h+var_140], eax
0x18000e36c  mov     eax, 260h
0x18000e371  jmp     loc_18000E1BB
0x18000e376  mov     [rsp+1A0h+pReserved3], rdi; pReserved3
0x18000e37b  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecDesc
0x18000e37f  mov     [rsp+1A0h+dwCapabilities], 3040h; dwCapabilities
0x18000e387  mov     eax, 260h
0x18000e38c  mov     [rsp+1A0h+pAuthList], rdi; pAuthList
0x18000e391  xor     r9d, r9d; pReserved1
0x18000e394  mov     [rsp+1A0h+dwImpLevel], 2; dwImpLevel
0x18000e39c  xor     r8d, r8d; asAuthSvc
0x18000e39f  or      edx, 0FFFFFFFFh; cAuthSvc
0x18000e3a2  mov     [rsp+1A0h+dwAuthnLevel], 6; dwAuthnLevel
0x18000e3aa  mov     [rsp+1A0h+var_140], edi
0x18000e3ae  mov     [rsp+1A0h+var_13C], ax
0x18000e3b3  call    cs:__imp_CoInitializeSecurity
0x18000e3b9  mov     ebx, eax
0x18000e3bb  mov     [rsp+1A0h+var_140], eax
0x18000e3bf  test    eax, eax
0x18000e3c1  mov     eax, 264h
0x18000e3c6  js      loc_18000E1BB
0x18000e3cc  mov     [rsp+1A0h+var_13C], ax
0x18000e3d1  mov     rcx, [rsp+1A0h+NewAcl]; hMem
0x18000e3d6  test    rcx, rcx
0x18000e3d9  jz      short loc_18000E3EA
0x18000e3db  call    cs:__imp_LocalFree
0x18000e3e1  mov     ebx, [rsp+1A0h+var_140]
0x18000e3e5  mov     [rsp+1A0h+NewAcl], rdi
0x18000e3ea  lea     rcx, [rsp+1A0h+var_140]; this
0x18000e3ef  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e3f4  mov     eax, ebx
0x18000e3f6  mov     rcx, [rbp+0A0h+var_10]
0x18000e3fd  xor     rcx, rsp; StackCookie
0x18000e400  call    __security_check_cookie
0x18000e405  lea     r11, [rsp+1A0h+var_s0]
0x18000e40d  mov     rbx, [r11+10h]
0x18000e411  mov     rdi, [r11+18h]
0x18000e415  mov     rsp, r11
0x18000e418  pop     rbp
0x18000e419  retn
```
