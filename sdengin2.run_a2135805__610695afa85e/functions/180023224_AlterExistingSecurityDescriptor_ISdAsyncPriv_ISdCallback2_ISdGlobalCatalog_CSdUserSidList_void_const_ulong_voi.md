# AlterExistingSecurityDescriptor(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,void * const,ulong,void * *,ulong *)

- ea: `0x180023224`
- end: `0x180023970`
- name: `?AlterExistingSecurityDescriptor@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAXKPEAPEAXPEAK@Z`
- size: `1868`
- prototype: `__int64 __fastcall(struct ISdAsyncPriv *, struct ISdCallback2 *, struct ISdGlobalCatalog *, struct CSdUserSidList *, PSECURITY_DESCRIPTOR SecurityDescriptorInput, ULONG SecurityDescriptorLength, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180026738`

## callees

- `0x180023224`
- `0x180024f08`
- `0x1800255bc`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800cf5c0`

## import_xrefs

- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18002337e`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18002337e`
- `KERNEL32!GetLastError` at `0x180023841`
- `KERNEL32!GetLastError` at `0x180023841`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180023833`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800238ac`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180023833`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800238ac`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180023780`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1800237aa`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180023780`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1800237aa`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180023685`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800236af`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180023685`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800236af`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180023586`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800235b4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180023586`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800235b4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180023485`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800234b3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180023485`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800234b3`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800233b2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800233b2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800237e7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800237e7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800235f4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800235f4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800236ef`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800236ef`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800234ef`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800234ef`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800233ee`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800233ee`
- `ole32!CoTaskMemFree` at `0x1800238fa`
- `ole32!CoTaskMemFree` at `0x180023917`
- `ole32!CoTaskMemFree` at `0x180023933`
- `ole32!CoTaskMemFree` at `0x1800238fa`
- `ole32!CoTaskMemFree` at `0x180023917`
- `ole32!CoTaskMemFree` at `0x180023933`
- `ole32!CoTaskMemAlloc` at `0x18002386c`
- `ole32!CoTaskMemAlloc` at `0x18002386c`

## string_xrefs

- `0x18002327e`: `AlterExistingSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall AlterExistingSecurityDescriptor(
        struct ISdAsyncPriv *a1,
        struct ISdCallback2 *a2,
        struct ISdGlobalCatalog *a3,
        struct CSdUserSidList *a4,
        PSECURITY_DESCRIPTOR SecurityDescriptorInput,
        ULONG SecurityDescriptorLength,
        void **a7,
        unsigned int *a8)
{
  void *v12; // rdi
  void **v13; // rcx
  __int16 v14; // ax
  bool v15; // zf
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int16 v19; // ax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int16 v23; // ax
  __int64 v24; // rcx
  __int64 v25; // rcx
  WINBOOL v26; // edx
  struct _ACL *v27; // r8
  __int64 v28; // rcx
  __int16 v29; // ax
  __int64 v30; // rcx
  __int64 v31; // rcx
  WINBOOL v32; // edx
  struct _ACL *v33; // r8
  __int64 v34; // rcx
  __int16 v35; // ax
  __int64 v36; // rcx
  __int64 v37; // rcx
  BOOL SelfRelativeSD; // ebx
  DWORD LastError; // eax
  __int64 v40; // rcx
  void *v41; // rax
  __int64 v42; // rcx
  unsigned int v43; // ebx
  int LastFailureAsHRESULT; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v46; // [rsp+44h] [rbp-BCh]
  __int16 v47; // [rsp+46h] [rbp-BAh]
  WORD pControl[2]; // [rsp+78h] [rbp-88h] BYREF
  int v49; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD dwBufferLength; // [rsp+80h] [rbp-80h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+84h] [rbp-7Ch] BYREF
  WINBOOL bGroupDefaulted; // [rsp+88h] [rbp-78h] BYREF
  WINBOOL bDaclPresent; // [rsp+8Ch] [rbp-74h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+90h] [rbp-70h] BYREF
  WINBOOL bSaclPresent; // [rsp+94h] [rbp-6Ch] BYREF
  WINBOOL bSaclDefaulted; // [rsp+98h] [rbp-68h] BYREF
  PACL pDacl; // [rsp+A0h] [rbp-60h] BYREF
  PACL pSacl; // [rsp+A8h] [rbp-58h] BYREF
  PACL v59; // [rsp+B0h] [rbp-50h] BYREF
  PACL v60; // [rsp+B8h] [rbp-48h] BYREF
  DWORD dwRevision; // [rsp+C0h] [rbp-40h] BYREF
  PSID pOwner; // [rsp+C8h] [rbp-38h] BYREF
  PSID pGroup; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v65; // [rsp+F8h] [rbp-8h]
  void **v66; // [rsp+100h] [rbp+0h]
  _BYTE v67[80]; // [rsp+110h] [rbp+10h] BYREF

  v66 = a7;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "AlterExistingSecurityDescriptor",
    0x10Bu,
    1u);
  v49 = 1;
  pControl[0] = 0;
  dwRevision = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v65 = 0;
  v12 = 0;
  dwBufferLength = 0;
  pDacl = 0;
  pSacl = 0;
  v59 = 0;
  v60 = 0;
  pOwner = 0;
  pGroup = 0;
  bOwnerDefaulted = 0;
  bGroupDefaulted = 0;
  bDaclDefaulted = 0;
  bSaclDefaulted = 0;
  bDaclPresent = 0;
  bSaclPresent = 0;
  v13 = v66;
  if ( v66 )
    *v66 = 0;
  if ( a8 )
    *a8 = 0;
  v14 = 302;
  if ( !a1 )
    goto LABEL_6;
  v46 = 302;
  v14 = 303;
  if ( !a2 )
    goto LABEL_6;
  v46 = 303;
  v14 = 304;
  if ( !a3 )
    goto LABEL_6;
  v46 = 304;
  v14 = 305;
  if ( !a4
    || (v46 = 305, v14 = 306, !SecurityDescriptorInput)
    || (v46 = 306, v14 = 307, !v13)
    || (v46 = 307, v14 = 308, !a8) )
  {
LABEL_6:
    LastFailureAsHRESULT = -2147024809;
LABEL_7:
    v47 = v14;
    goto LABEL_78;
  }
  LastFailureAsHRESULT = 0;
  v46 = 308;
  v15 = RtlValidRelativeSecurityDescriptor(SecurityDescriptorInput, SecurityDescriptorLength, 0xFu) == 0;
  v14 = 310;
  if ( v15 )
  {
    LastFailureAsHRESULT = -2147023558;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v46 = 310;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v16);
    v14 = 312;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v46 = 312;
  if ( !GetSecurityDescriptorOwner(SecurityDescriptorInput, &pOwner, &bOwnerDefaulted) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v17);
    v14 = 315;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v46 = 315;
  if ( pOwner )
  {
    LastFailureAsHRESULT = DoSidWork(a1, a2, a3, a4, pOwner, v67, 0x44u, &v49);
    v14 = 318;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_7;
    v46 = 318;
    if ( v49 )
    {
      if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, v67, bOwnerDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v18);
        v14 = 321;
        goto LABEL_7;
      }
      v19 = 321;
    }
    else
    {
      if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, bOwnerDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v20);
        v14 = 325;
        goto LABEL_7;
      }
      v19 = 325;
    }
    v46 = v19;
    LastFailureAsHRESULT = 0;
  }
  if ( !GetSecurityDescriptorGroup(SecurityDescriptorInput, &pGroup, &bGroupDefaulted) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v21);
    v14 = 330;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v46 = 330;
  if ( pGroup )
  {
    LastFailureAsHRESULT = DoSidWork(a1, a2, a3, a4, pGroup, v67, 0x44u, &v49);
    v14 = 333;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_7;
    v46 = 333;
    if ( v49 )
    {
      if ( !SetSecurityDescriptorGroup(pSecurityDescriptor, v67, bGroupDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v22);
        v14 = 336;
        goto LABEL_7;
      }
      v23 = 336;
    }
    else
    {
      if ( !SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, bGroupDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v24);
        v14 = 340;
        goto LABEL_7;
      }
      v23 = 340;
    }
    v46 = v23;
    LastFailureAsHRESULT = 0;
  }
  if ( !GetSecurityDescriptorDacl(SecurityDescriptorInput, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v25);
    v14 = 344;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v46 = 344;
  v26 = bDaclPresent;
  v27 = pDacl;
  if ( bDaclPresent && pDacl )
  {
    LastFailureAsHRESULT = DoAclWork(a1, a2, a3, a4, pDacl, &v59);
    v14 = 348;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_7;
    v46 = 348;
    v27 = pDacl;
    v26 = bDaclPresent;
  }
  if ( v59 )
  {
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, v26, v59, bDaclDefaulted) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v28);
      v14 = 353;
      goto LABEL_7;
    }
    v29 = 353;
  }
  else
  {
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, v26, v27, bDaclDefaulted) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v30);
      v14 = 357;
      goto LABEL_7;
    }
    v29 = 357;
  }
  v46 = v29;
  LastFailureAsHRESULT = 0;
  if ( !GetSecurityDescriptorSacl(SecurityDescriptorInput, &bSaclPresent, &pSacl, &bSaclDefaulted) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v31);
    v14 = 360;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v46 = 360;
  v32 = bSaclPresent;
  v33 = pSacl;
  if ( bSaclPresent && pSacl )
  {
    LastFailureAsHRESULT = DoAclWork(a1, a2, a3, a4, pSacl, &v60);
    v14 = 363;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_7;
    v46 = 363;
    v33 = pSacl;
    v32 = bSaclPresent;
  }
  if ( v60 )
  {
    if ( !SetSecurityDescriptorSacl(pSecurityDescriptor, v32, v60, bSaclDefaulted) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v34);
      v14 = 368;
      goto LABEL_7;
    }
    v35 = 368;
  }
  else
  {
    if ( !SetSecurityDescriptorSacl(pSecurityDescriptor, v32, v33, bSaclDefaulted) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v36);
      v14 = 372;
      goto LABEL_7;
    }
    v35 = 372;
  }
  v46 = v35;
  LastFailureAsHRESULT = 0;
  if ( !GetSecurityDescriptorControl(SecurityDescriptorInput, pControl, &dwRevision) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v37);
    v14 = 375;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v46 = 375;
  WORD1(pSecurityDescriptor[0]) |= pControl[0] & 0x3FC0;
  SelfRelativeSD = MakeSelfRelativeSD(pSecurityDescriptor, 0, &dwBufferLength);
  LastError = GetLastError();
  if ( !SelfRelativeSD && LastError != 122 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v40);
    v14 = 383;
    goto LABEL_7;
  }
  v41 = CoTaskMemAlloc(dwBufferLength);
  v12 = v41;
  if ( v41 )
  {
    LastFailureAsHRESULT = 0;
    v46 = 387;
    if ( !MakeSelfRelativeSD(pSecurityDescriptor, v41, &dwBufferLength) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v42);
      v14 = 389;
      goto LABEL_7;
    }
    LastFailureAsHRESULT = 0;
    v46 = 389;
    *v66 = v12;
    v12 = 0;
    *a8 = dwBufferLength;
  }
  else
  {
    LastFailureAsHRESULT = -2147024882;
    v47 = 387;
  }
LABEL_78:
  if ( v59 )
  {
    CoTaskMemFree(v59);
    v59 = 0;
  }
  if ( v60 )
  {
    CoTaskMemFree(v60);
    v60 = 0;
  }
  if ( v12 )
    CoTaskMemFree(v12);
  v43 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v43;
}

```

## disassembly

```asm
0x180023224  push    rbp
0x180023226  push    rbx
0x180023227  push    rsi
0x180023228  push    rdi
0x180023229  push    r12
0x18002322b  push    r13
0x18002322d  push    r14
0x18002322f  push    r15
0x180023231  lea     rbp, [rsp-78h]
0x180023236  sub     rsp, 178h
0x18002323d  mov     rax, cs:__security_cookie
0x180023244  xor     rax, rsp
0x180023247  mov     [rbp+0B0h+var_50], rax
0x18002324b  mov     r12, r9
0x18002324e  mov     r15, r8
0x180023251  mov     r14, rdx
0x180023254  mov     rsi, rcx
0x180023257  mov     rbx, [rbp+0B0h+SecurityDescriptorInput]
0x18002325e  mov     rax, [rbp+0B0h+arg_30]
0x180023265  mov     [rbp+0B0h+var_B0], rax
0x180023269  mov     r13, [rbp+0B0h+arg_38]
0x180023270  mov     edi, 1
0x180023275  mov     r9d, edi; unsigned __int16
0x180023278  mov     r8d, 10Bh; unsigned __int16
0x18002327e  lea     rdx, aAlterexistings; "AlterExistingSecurityDescriptor"
0x180023285  lea     rcx, [rsp+1B0h+var_170]; this
0x18002328a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002328f  mov     [rsp+1B0h+var_134], edi
0x180023293  xor     eax, eax
0x180023295  mov     [rsp+1B0h+pControl], ax
0x18002329a  mov     [rbp+0B0h+dwRevision], eax
0x18002329d  xorps   xmm0, xmm0
0x1800232a0  movups  [rbp+0B0h+pSecurityDescriptor], xmm0
0x1800232a4  movups  [rbp+0B0h+var_C8], xmm0
0x1800232a8  mov     [rbp+0B0h+var_B8], rax
0x1800232ac  xor     edi, edi
0x1800232ae  mov     [rbp+0B0h+dwBufferLength], eax
0x1800232b1  mov     [rbp+0B0h+pDacl], rax
0x1800232b5  mov     [rbp+0B0h+pSacl], rax
0x1800232b9  mov     [rbp+0B0h+var_100], rax
0x1800232bd  mov     [rbp+0B0h+var_F8], rax
0x1800232c1  mov     [rbp+0B0h+pOwner], rax
0x1800232c5  mov     [rbp+0B0h+pGroup], rax
0x1800232c9  mov     [rbp+0B0h+bOwnerDefaulted], eax
0x1800232cc  mov     [rbp+0B0h+bGroupDefaulted], eax
0x1800232cf  mov     [rbp+0B0h+bDaclDefaulted], eax
0x1800232d2  mov     [rbp+0B0h+bSaclDefaulted], eax
0x1800232d5  mov     [rbp+0B0h+bDaclPresent], eax
0x1800232d8  mov     [rbp+0B0h+bSaclPresent], eax
0x1800232db  mov     rcx, [rbp+0B0h+var_B0]
0x1800232df  test    rcx, rcx
0x1800232e2  jz      short loc_1800232E7
0x1800232e4  mov     [rcx], rax
0x1800232e7  test    r13, r13
0x1800232ea  jz      short loc_1800232F0
0x1800232ec  mov     [r13+0], eax
0x1800232f0  mov     eax, 12Eh
0x1800232f5  test    rsi, rsi
0x1800232f8  jnz     short loc_18002330C
0x1800232fa  mov     [rsp+1B0h+var_170], 80070057h
0x180023302  mov     [rsp+1B0h+var_16A], ax
0x180023307  jmp     loc_1800238F1
0x18002330c  mov     [rsp+1B0h+var_16C], ax
0x180023311  mov     eax, 12Fh
0x180023316  test    r14, r14
0x180023319  jz      short loc_1800232FA
0x18002331b  mov     [rsp+1B0h+var_16C], ax
0x180023320  mov     eax, 130h
0x180023325  test    r15, r15
0x180023328  jz      short loc_1800232FA
0x18002332a  mov     [rsp+1B0h+var_16C], ax
0x18002332f  mov     eax, 131h
0x180023334  test    r12, r12
0x180023337  jz      short loc_1800232FA
0x180023339  mov     [rsp+1B0h+var_16C], ax
0x18002333e  mov     eax, 132h
0x180023343  test    rbx, rbx
0x180023346  jz      short loc_1800232FA
0x180023348  mov     [rsp+1B0h+var_16C], ax
0x18002334d  mov     eax, 133h
0x180023352  test    rcx, rcx
0x180023355  jz      short loc_1800232FA
0x180023357  mov     [rsp+1B0h+var_16C], ax
0x18002335c  mov     eax, 134h
0x180023361  test    r13, r13
0x180023364  jz      short loc_1800232FA
0x180023366  mov     [rsp+1B0h+var_170], edi
0x18002336a  mov     [rsp+1B0h+var_16C], ax
0x18002336f  mov     r8d, 0Fh; RequiredInformation
0x180023375  mov     edx, [rbp+0B0h+SecurityDescriptorLength]; SecurityDescriptorLength
0x18002337b  mov     rcx, rbx; SecurityDescriptorInput
0x18002337e  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x180023385  nop     dword ptr [rax+rax+00h]
0x18002338a  test    al, al
0x18002338c  mov     eax, 136h
0x180023391  jnz     short loc_1800233A0
0x180023393  mov     [rsp+1B0h+var_170], 8007053Ah
0x18002339b  jmp     loc_180023302
0x1800233a0  mov     [rsp+1B0h+var_170], edi
0x1800233a4  mov     [rsp+1B0h+var_16C], ax
0x1800233a9  mov     edx, 1; dwRevision
0x1800233ae  lea     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x1800233b2  call    cs:__imp_InitializeSecurityDescriptor
0x1800233b9  nop     dword ptr [rax+rax+00h]
0x1800233be  test    eax, eax
0x1800233c0  jnz     short loc_1800233D5
0x1800233c2  call    GetLastFailureAsHRESULT
0x1800233c7  mov     [rsp+1B0h+var_170], eax
0x1800233cb  mov     eax, 138h
0x1800233d0  jmp     loc_180023302
0x1800233d5  mov     [rsp+1B0h+var_170], edi
0x1800233d9  mov     eax, 138h
0x1800233de  mov     [rsp+1B0h+var_16C], ax
0x1800233e3  lea     r8, [rbp+0B0h+bOwnerDefaulted]; lpbOwnerDefaulted
0x1800233e7  lea     rdx, [rbp+0B0h+pOwner]; pOwner
0x1800233eb  mov     rcx, rbx; pSecurityDescriptor
0x1800233ee  call    cs:__imp_GetSecurityDescriptorOwner
0x1800233f5  nop     dword ptr [rax+rax+00h]
0x1800233fa  test    eax, eax
0x1800233fc  jnz     short loc_180023411
0x1800233fe  call    GetLastFailureAsHRESULT
0x180023403  mov     [rsp+1B0h+var_170], eax
0x180023407  mov     eax, 13Bh
0x18002340c  jmp     loc_180023302
0x180023411  mov     [rsp+1B0h+var_170], edi
0x180023415  mov     eax, 13Bh
0x18002341a  mov     [rsp+1B0h+var_16C], ax
0x18002341f  mov     rax, [rbp+0B0h+pOwner]
0x180023423  test    rax, rax
0x180023426  jz      loc_1800234E4
0x18002342c  lea     rcx, [rsp+1B0h+var_134]
0x180023431  mov     [rsp+1B0h+var_178], rcx; int *
0x180023436  mov     [rsp+1B0h+var_180], 44h ; 'D'; unsigned int
0x18002343e  lea     rcx, [rbp+0B0h+var_A0]
0x180023442  mov     [rsp+1B0h+var_188], rcx; void *
0x180023447  mov     [rsp+1B0h+pSid], rax; pSid
0x18002344c  mov     r9, r12; struct CSdUserSidList *
0x18002344f  mov     r8, r15; struct ISdGlobalCatalog *
0x180023452  mov     rdx, r14; struct ISdCallback2 *
0x180023455  mov     rcx, rsi; struct ISdAsyncPriv *
0x180023458  call    ?DoSidWork@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAXPEAXKPEAH@Z; DoSidWork(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,void * const,void *,ulong,int *)
0x18002345d  mov     [rsp+1B0h+var_170], eax
0x180023461  test    eax, eax
0x180023463  mov     eax, 13Eh
0x180023468  js      loc_180023302
0x18002346e  mov     [rsp+1B0h+var_16C], ax
0x180023473  mov     r8d, [rbp+0B0h+bOwnerDefaulted]; bOwnerDefaulted
0x180023477  lea     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x18002347b  cmp     [rsp+1B0h+var_134], edi
0x18002347f  jz      short loc_1800234AF
0x180023481  lea     rdx, [rbp+0B0h+var_A0]; pOwner
0x180023485  call    cs:__imp_SetSecurityDescriptorOwner
0x18002348c  nop     dword ptr [rax+rax+00h]
0x180023491  test    eax, eax
0x180023493  jnz     short loc_1800234A8
0x180023495  call    GetLastFailureAsHRESULT
0x18002349a  mov     [rsp+1B0h+var_170], eax
0x18002349e  mov     eax, 141h
0x1800234a3  jmp     loc_180023302
0x1800234a8  mov     eax, 141h
0x1800234ad  jmp     short loc_1800234DB
0x1800234af  mov     rdx, [rbp+0B0h+pOwner]; pOwner
0x1800234b3  call    cs:__imp_SetSecurityDescriptorOwner
0x1800234ba  nop     dword ptr [rax+rax+00h]
0x1800234bf  test    eax, eax
0x1800234c1  jnz     short loc_1800234D6
0x1800234c3  call    GetLastFailureAsHRESULT
0x1800234c8  mov     [rsp+1B0h+var_170], eax
0x1800234cc  mov     eax, 145h
0x1800234d1  jmp     loc_180023302
0x1800234d6  mov     eax, 145h
0x1800234db  mov     [rsp+1B0h+var_16C], ax
0x1800234e0  mov     [rsp+1B0h+var_170], edi
0x1800234e4  lea     r8, [rbp+0B0h+bGroupDefaulted]; lpbGroupDefaulted
0x1800234e8  lea     rdx, [rbp+0B0h+pGroup]; pGroup
0x1800234ec  mov     rcx, rbx; pSecurityDescriptor
0x1800234ef  call    cs:__imp_GetSecurityDescriptorGroup
0x1800234f6  nop     dword ptr [rax+rax+00h]
0x1800234fb  test    eax, eax
0x1800234fd  jnz     short loc_180023512
0x1800234ff  call    GetLastFailureAsHRESULT
0x180023504  mov     [rsp+1B0h+var_170], eax
0x180023508  mov     eax, 14Ah
0x18002350d  jmp     loc_180023302
0x180023512  mov     [rsp+1B0h+var_170], edi
0x180023516  mov     eax, 14Ah
0x18002351b  mov     [rsp+1B0h+var_16C], ax
0x180023520  mov     rax, [rbp+0B0h+pGroup]
0x180023524  test    rax, rax
0x180023527  jz      loc_1800235E5
0x18002352d  lea     rcx, [rsp+1B0h+var_134]
0x180023532  mov     [rsp+1B0h+var_178], rcx; int *
0x180023537  mov     [rsp+1B0h+var_180], 44h ; 'D'; unsigned int
0x18002353f  lea     rcx, [rbp+0B0h+var_A0]
0x180023543  mov     [rsp+1B0h+var_188], rcx; void *
0x180023548  mov     [rsp+1B0h+pSid], rax; pSid
0x18002354d  mov     r9, r12; struct CSdUserSidList *
0x180023550  mov     r8, r15; struct ISdGlobalCatalog *
0x180023553  mov     rdx, r14; struct ISdCallback2 *
0x180023556  mov     rcx, rsi; struct ISdAsyncPriv *
0x180023559  call    ?DoSidWork@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAXPEAXKPEAH@Z; DoSidWork(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,void * const,void *,ulong,int *)
0x18002355e  mov     [rsp+1B0h+var_170], eax
0x180023562  test    eax, eax
0x180023564  mov     eax, 14Dh
0x180023569  js      loc_180023302
0x18002356f  mov     [rsp+1B0h+var_16C], ax
0x180023574  mov     r8d, [rbp+0B0h+bGroupDefaulted]; bGroupDefaulted
0x180023578  lea     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x18002357c  cmp     [rsp+1B0h+var_134], edi
0x180023580  jz      short loc_1800235B0
0x180023582  lea     rdx, [rbp+0B0h+var_A0]; pGroup
0x180023586  call    cs:__imp_SetSecurityDescriptorGroup
0x18002358d  nop     dword ptr [rax+rax+00h]
0x180023592  test    eax, eax
0x180023594  jnz     short loc_1800235A9
0x180023596  call    GetLastFailureAsHRESULT
0x18002359b  mov     [rsp+1B0h+var_170], eax
0x18002359f  mov     eax, 150h
0x1800235a4  jmp     loc_180023302
0x1800235a9  mov     eax, 150h
0x1800235ae  jmp     short loc_1800235DC
0x1800235b0  mov     rdx, [rbp+0B0h+pGroup]; pGroup
0x1800235b4  call    cs:__imp_SetSecurityDescriptorGroup
0x1800235bb  nop     dword ptr [rax+rax+00h]
0x1800235c0  test    eax, eax
0x1800235c2  jnz     short loc_1800235D7
0x1800235c4  call    GetLastFailureAsHRESULT
0x1800235c9  mov     [rsp+1B0h+var_170], eax
0x1800235cd  mov     eax, 154h
0x1800235d2  jmp     loc_180023302
0x1800235d7  mov     eax, 154h
0x1800235dc  mov     [rsp+1B0h+var_16C], ax
0x1800235e1  mov     [rsp+1B0h+var_170], edi
0x1800235e5  lea     r9, [rbp+0B0h+bDaclDefaulted]; lpbDaclDefaulted
0x1800235e9  lea     r8, [rbp+0B0h+pDacl]; pDacl
0x1800235ed  lea     rdx, [rbp+0B0h+bDaclPresent]; lpbDaclPresent
0x1800235f1  mov     rcx, rbx; pSecurityDescriptor
0x1800235f4  call    cs:__imp_GetSecurityDescriptorDacl
0x1800235fb  nop     dword ptr [rax+rax+00h]
0x180023600  test    eax, eax
0x180023602  jnz     short loc_180023617
0x180023604  call    GetLastFailureAsHRESULT
0x180023609  mov     [rsp+1B0h+var_170], eax
0x18002360d  mov     eax, 158h
0x180023612  jmp     loc_180023302
0x180023617  mov     [rsp+1B0h+var_170], edi
0x18002361b  mov     eax, 158h
0x180023620  mov     [rsp+1B0h+var_16C], ax
0x180023625  mov     edx, [rbp+0B0h+bDaclPresent]
0x180023628  mov     r8, [rbp+0B0h+pDacl]
0x18002362c  test    edx, edx
0x18002362e  jz      short loc_180023671
0x180023630  test    r8, r8
0x180023633  jz      short loc_180023671
0x180023635  lea     rax, [rbp+0B0h+var_100]
0x180023639  mov     [rsp+1B0h+var_188], rax; struct _ACL **
0x18002363e  mov     [rsp+1B0h+pSid], r8; pAcl
0x180023643  mov     r9, r12; struct CSdUserSidList *
0x180023646  mov     r8, r15; struct ISdGlobalCatalog *
0x180023649  mov     rdx, r14; struct ISdCallback2 *
0x18002364c  mov     rcx, rsi; struct ISdAsyncPriv *
0x18002364f  call    ?DoAclWork@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAU_ACL@@PEAPEAU5@@Z; DoAclWork(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,_ACL * const,_ACL * *)
0x180023654  mov     [rsp+1B0h+var_170], eax
0x180023658  test    eax, eax
0x18002365a  mov     eax, 15Ch
0x18002365f  js      loc_180023302
0x180023665  mov     [rsp+1B0h+var_16C], ax
0x18002366a  mov     r8, [rbp+0B0h+pDacl]; pDacl
0x18002366e  mov     edx, [rbp+0B0h+bDaclPresent]; bDaclPresent
0x180023671  mov     rax, [rbp+0B0h+var_100]
0x180023675  mov     r9d, [rbp+0B0h+bDaclDefaulted]; bDaclDefaulted
0x180023679  lea     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x18002367d  test    rax, rax
0x180023680  jz      short loc_1800236AF
0x180023682  mov     r8, rax; pDacl
0x180023685  call    cs:__imp_SetSecurityDescriptorDacl
0x18002368c  nop     dword ptr [rax+rax+00h]
0x180023691  test    eax, eax
0x180023693  jnz     short loc_1800236A8
0x180023695  call    GetLastFailureAsHRESULT
0x18002369a  mov     [rsp+1B0h+var_170], eax
0x18002369e  mov     eax, 161h
0x1800236a3  jmp     loc_180023302
0x1800236a8  mov     eax, 161h
0x1800236ad  jmp     short loc_1800236D7
0x1800236af  call    cs:__imp_SetSecurityDescriptorDacl
0x1800236b6  nop     dword ptr [rax+rax+00h]
0x1800236bb  test    eax, eax
0x1800236bd  jnz     short loc_1800236D2
0x1800236bf  call    GetLastFailureAsHRESULT
0x1800236c4  mov     [rsp+1B0h+var_170], eax
0x1800236c8  mov     eax, 165h
0x1800236cd  jmp     loc_180023302
0x1800236d2  mov     eax, 165h
0x1800236d7  mov     [rsp+1B0h+var_16C], ax
0x1800236dc  mov     [rsp+1B0h+var_170], edi
0x1800236e0  lea     r9, [rbp+0B0h+bSaclDefaulted]; lpbSaclDefaulted
0x1800236e4  lea     r8, [rbp+0B0h+pSacl]; pSacl
0x1800236e8  lea     rdx, [rbp+0B0h+bSaclPresent]; lpbSaclPresent
0x1800236ec  mov     rcx, rbx; pSecurityDescriptor
  ... truncated ...
```
