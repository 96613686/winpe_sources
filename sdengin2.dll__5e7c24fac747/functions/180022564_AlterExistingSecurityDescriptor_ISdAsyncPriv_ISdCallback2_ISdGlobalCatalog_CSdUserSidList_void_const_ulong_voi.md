# AlterExistingSecurityDescriptor(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,void * const,ulong,void * *,ulong *)

- ea: `0x180022564`
- end: `0x180022c2b`
- name: `?AlterExistingSecurityDescriptor@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAXKPEAPEAXPEAK@Z`
- size: `1735`
- prototype: `__int64 __fastcall(struct ISdAsyncPriv *, struct ISdCallback2 *, struct ISdGlobalCatalog *, struct CSdUserSidList *, PSECURITY_DESCRIPTOR SecurityDescriptorInput, ULONG SecurityDescriptorLength, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025794`

## callees

- `0x180022564`
- `0x1800240ac`
- `0x180024724`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c9830`

## import_xrefs

- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800226be`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800226be`
- `KERNEL32!GetLastError` at `0x180022b21`
- `KERNEL32!GetLastError` at `0x180022b21`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180022b19`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180022b80`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180022b19`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180022b80`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180022a78`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180022a9c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180022a78`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180022a9c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002298f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800229b3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002298f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800229b3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800228a2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800228ca`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800228a2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800228ca`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800227b3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800227db`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800227b3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800227db`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800226ec`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800226ec`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180022ad3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180022ad3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180022904`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180022904`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800229ed`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800229ed`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180022811`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180022811`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180022722`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180022722`
- `ole32!CoTaskMemFree` at `0x180022bc8`
- `ole32!CoTaskMemFree` at `0x180022bdf`
- `ole32!CoTaskMemFree` at `0x180022bf5`
- `ole32!CoTaskMemFree` at `0x180022bc8`
- `ole32!CoTaskMemFree` at `0x180022bdf`
- `ole32!CoTaskMemFree` at `0x180022bf5`
- `ole32!CoTaskMemAlloc` at `0x180022b46`
- `ole32!CoTaskMemAlloc` at `0x180022b46`

## string_xrefs

- `0x1800225be`: `AlterExistingSecurityDescriptor`

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
    267,
    1);
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
0x180022564  push    rbp
0x180022566  push    rbx
0x180022567  push    rsi
0x180022568  push    rdi
0x180022569  push    r12
0x18002256b  push    r13
0x18002256d  push    r14
0x18002256f  push    r15
0x180022571  lea     rbp, [rsp-78h]
0x180022576  sub     rsp, 178h
0x18002257d  mov     rax, cs:__security_cookie
0x180022584  xor     rax, rsp
0x180022587  mov     [rbp+0B0h+var_50], rax
0x18002258b  mov     r12, r9
0x18002258e  mov     r15, r8
0x180022591  mov     r14, rdx
0x180022594  mov     rsi, rcx
0x180022597  mov     rbx, [rbp+0B0h+SecurityDescriptorInput]
0x18002259e  mov     rax, [rbp+0B0h+arg_30]
0x1800225a5  mov     [rbp+0B0h+var_B0], rax
0x1800225a9  mov     r13, [rbp+0B0h+arg_38]
0x1800225b0  mov     edi, 1
0x1800225b5  mov     r9d, edi; unsigned __int16
0x1800225b8  mov     r8d, 10Bh; unsigned __int16
0x1800225be  lea     rdx, aAlterexistings; "AlterExistingSecurityDescriptor"
0x1800225c5  lea     rcx, [rsp+1B0h+var_170]; this
0x1800225ca  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800225cf  mov     [rsp+1B0h+var_134], edi
0x1800225d3  xor     eax, eax
0x1800225d5  mov     [rsp+1B0h+pControl], ax
0x1800225da  mov     [rbp+0B0h+dwRevision], eax
0x1800225dd  xorps   xmm0, xmm0
0x1800225e0  movups  [rbp+0B0h+pSecurityDescriptor], xmm0
0x1800225e4  movups  [rbp+0B0h+var_C8], xmm0
0x1800225e8  mov     [rbp+0B0h+var_B8], rax
0x1800225ec  xor     edi, edi
0x1800225ee  mov     [rbp+0B0h+dwBufferLength], eax
0x1800225f1  mov     [rbp+0B0h+pDacl], rax
0x1800225f5  mov     [rbp+0B0h+pSacl], rax
0x1800225f9  mov     [rbp+0B0h+var_100], rax
0x1800225fd  mov     [rbp+0B0h+var_F8], rax
0x180022601  mov     [rbp+0B0h+pOwner], rax
0x180022605  mov     [rbp+0B0h+pGroup], rax
0x180022609  mov     [rbp+0B0h+bOwnerDefaulted], eax
0x18002260c  mov     [rbp+0B0h+bGroupDefaulted], eax
0x18002260f  mov     [rbp+0B0h+bDaclDefaulted], eax
0x180022612  mov     [rbp+0B0h+bSaclDefaulted], eax
0x180022615  mov     [rbp+0B0h+bDaclPresent], eax
0x180022618  mov     [rbp+0B0h+bSaclPresent], eax
0x18002261b  mov     rcx, [rbp+0B0h+var_B0]
0x18002261f  test    rcx, rcx
0x180022622  jz      short loc_180022627
0x180022624  mov     [rcx], rax
0x180022627  test    r13, r13
0x18002262a  jz      short loc_180022630
0x18002262c  mov     [r13+0], eax
0x180022630  mov     eax, 12Eh
0x180022635  test    rsi, rsi
0x180022638  jnz     short loc_18002264C
0x18002263a  mov     [rsp+1B0h+var_170], 80070057h
0x180022642  mov     [rsp+1B0h+var_16A], ax
0x180022647  jmp     loc_180022BBF
0x18002264c  mov     [rsp+1B0h+var_16C], ax
0x180022651  mov     eax, 12Fh
0x180022656  test    r14, r14
0x180022659  jz      short loc_18002263A
0x18002265b  mov     [rsp+1B0h+var_16C], ax
0x180022660  mov     eax, 130h
0x180022665  test    r15, r15
0x180022668  jz      short loc_18002263A
0x18002266a  mov     [rsp+1B0h+var_16C], ax
0x18002266f  mov     eax, 131h
0x180022674  test    r12, r12
0x180022677  jz      short loc_18002263A
0x180022679  mov     [rsp+1B0h+var_16C], ax
0x18002267e  mov     eax, 132h
0x180022683  test    rbx, rbx
0x180022686  jz      short loc_18002263A
0x180022688  mov     [rsp+1B0h+var_16C], ax
0x18002268d  mov     eax, 133h
0x180022692  test    rcx, rcx
0x180022695  jz      short loc_18002263A
0x180022697  mov     [rsp+1B0h+var_16C], ax
0x18002269c  mov     eax, 134h
0x1800226a1  test    r13, r13
0x1800226a4  jz      short loc_18002263A
0x1800226a6  mov     [rsp+1B0h+var_170], edi
0x1800226aa  mov     [rsp+1B0h+var_16C], ax
0x1800226af  mov     r8d, 0Fh; RequiredInformation
0x1800226b5  mov     edx, [rbp+0B0h+SecurityDescriptorLength]; SecurityDescriptorLength
0x1800226bb  mov     rcx, rbx; SecurityDescriptorInput
0x1800226be  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1800226c4  test    al, al
0x1800226c6  mov     eax, 136h
0x1800226cb  jnz     short loc_1800226DA
0x1800226cd  mov     [rsp+1B0h+var_170], 8007053Ah
0x1800226d5  jmp     loc_180022642
0x1800226da  mov     [rsp+1B0h+var_170], edi
0x1800226de  mov     [rsp+1B0h+var_16C], ax
0x1800226e3  mov     edx, 1; dwRevision
0x1800226e8  lea     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x1800226ec  call    cs:__imp_InitializeSecurityDescriptor
0x1800226f2  test    eax, eax
0x1800226f4  jnz     short loc_180022709
0x1800226f6  call    GetLastFailureAsHRESULT
0x1800226fb  mov     [rsp+1B0h+var_170], eax
0x1800226ff  mov     eax, 138h
0x180022704  jmp     loc_180022642
0x180022709  mov     [rsp+1B0h+var_170], edi
0x18002270d  mov     eax, 138h
0x180022712  mov     [rsp+1B0h+var_16C], ax
0x180022717  lea     r8, [rbp+0B0h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18002271b  lea     rdx, [rbp+0B0h+pOwner]; pOwner
0x18002271f  mov     rcx, rbx; pSecurityDescriptor
0x180022722  call    cs:__imp_GetSecurityDescriptorOwner
0x180022728  test    eax, eax
0x18002272a  jnz     short loc_18002273F
0x18002272c  call    GetLastFailureAsHRESULT
0x180022731  mov     [rsp+1B0h+var_170], eax
0x180022735  mov     eax, 13Bh
0x18002273a  jmp     loc_180022642
0x18002273f  mov     [rsp+1B0h+var_170], edi
0x180022743  mov     eax, 13Bh
0x180022748  mov     [rsp+1B0h+var_16C], ax
0x18002274d  mov     rax, [rbp+0B0h+pOwner]
0x180022751  test    rax, rax
0x180022754  jz      loc_180022806
0x18002275a  lea     rcx, [rsp+1B0h+var_134]
0x18002275f  mov     [rsp+1B0h+var_178], rcx; int *
0x180022764  mov     [rsp+1B0h+var_180], 44h ; 'D'; unsigned int
0x18002276c  lea     rcx, [rbp+0B0h+var_A0]
0x180022770  mov     [rsp+1B0h+var_188], rcx; void *
0x180022775  mov     [rsp+1B0h+pSid], rax; pSid
0x18002277a  mov     r9, r12; struct CSdUserSidList *
0x18002277d  mov     r8, r15; struct ISdGlobalCatalog *
0x180022780  mov     rdx, r14; struct ISdCallback2 *
0x180022783  mov     rcx, rsi; struct ISdAsyncPriv *
0x180022786  call    ?DoSidWork@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAXPEAXKPEAH@Z; DoSidWork(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,void * const,void *,ulong,int *)
0x18002278b  mov     [rsp+1B0h+var_170], eax
0x18002278f  test    eax, eax
0x180022791  mov     eax, 13Eh
0x180022796  js      loc_180022642
0x18002279c  mov     [rsp+1B0h+var_16C], ax
0x1800227a1  mov     r8d, [rbp+0B0h+bOwnerDefaulted]; bOwnerDefaulted
0x1800227a5  lea     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x1800227a9  cmp     [rsp+1B0h+var_134], edi
0x1800227ad  jz      short loc_1800227D7
0x1800227af  lea     rdx, [rbp+0B0h+var_A0]; pOwner
0x1800227b3  call    cs:__imp_SetSecurityDescriptorOwner
0x1800227b9  test    eax, eax
0x1800227bb  jnz     short loc_1800227D0
0x1800227bd  call    GetLastFailureAsHRESULT
0x1800227c2  mov     [rsp+1B0h+var_170], eax
0x1800227c6  mov     eax, 141h
0x1800227cb  jmp     loc_180022642
0x1800227d0  mov     eax, 141h
0x1800227d5  jmp     short loc_1800227FD
0x1800227d7  mov     rdx, [rbp+0B0h+pOwner]; pOwner
0x1800227db  call    cs:__imp_SetSecurityDescriptorOwner
0x1800227e1  test    eax, eax
0x1800227e3  jnz     short loc_1800227F8
0x1800227e5  call    GetLastFailureAsHRESULT
0x1800227ea  mov     [rsp+1B0h+var_170], eax
0x1800227ee  mov     eax, 145h
0x1800227f3  jmp     loc_180022642
0x1800227f8  mov     eax, 145h
0x1800227fd  mov     [rsp+1B0h+var_16C], ax
0x180022802  mov     [rsp+1B0h+var_170], edi
0x180022806  lea     r8, [rbp+0B0h+bGroupDefaulted]; lpbGroupDefaulted
0x18002280a  lea     rdx, [rbp+0B0h+pGroup]; pGroup
0x18002280e  mov     rcx, rbx; pSecurityDescriptor
0x180022811  call    cs:__imp_GetSecurityDescriptorGroup
0x180022817  test    eax, eax
0x180022819  jnz     short loc_18002282E
0x18002281b  call    GetLastFailureAsHRESULT
0x180022820  mov     [rsp+1B0h+var_170], eax
0x180022824  mov     eax, 14Ah
0x180022829  jmp     loc_180022642
0x18002282e  mov     [rsp+1B0h+var_170], edi
0x180022832  mov     eax, 14Ah
0x180022837  mov     [rsp+1B0h+var_16C], ax
0x18002283c  mov     rax, [rbp+0B0h+pGroup]
0x180022840  test    rax, rax
0x180022843  jz      loc_1800228F5
0x180022849  lea     rcx, [rsp+1B0h+var_134]
0x18002284e  mov     [rsp+1B0h+var_178], rcx; int *
0x180022853  mov     [rsp+1B0h+var_180], 44h ; 'D'; unsigned int
0x18002285b  lea     rcx, [rbp+0B0h+var_A0]
0x18002285f  mov     [rsp+1B0h+var_188], rcx; void *
0x180022864  mov     [rsp+1B0h+pSid], rax; pSid
0x180022869  mov     r9, r12; struct CSdUserSidList *
0x18002286c  mov     r8, r15; struct ISdGlobalCatalog *
0x18002286f  mov     rdx, r14; struct ISdCallback2 *
0x180022872  mov     rcx, rsi; struct ISdAsyncPriv *
0x180022875  call    ?DoSidWork@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAXPEAXKPEAH@Z; DoSidWork(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,void * const,void *,ulong,int *)
0x18002287a  mov     [rsp+1B0h+var_170], eax
0x18002287e  test    eax, eax
0x180022880  mov     eax, 14Dh
0x180022885  js      loc_180022642
0x18002288b  mov     [rsp+1B0h+var_16C], ax
0x180022890  mov     r8d, [rbp+0B0h+bGroupDefaulted]; bGroupDefaulted
0x180022894  lea     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x180022898  cmp     [rsp+1B0h+var_134], edi
0x18002289c  jz      short loc_1800228C6
0x18002289e  lea     rdx, [rbp+0B0h+var_A0]; pGroup
0x1800228a2  call    cs:__imp_SetSecurityDescriptorGroup
0x1800228a8  test    eax, eax
0x1800228aa  jnz     short loc_1800228BF
0x1800228ac  call    GetLastFailureAsHRESULT
0x1800228b1  mov     [rsp+1B0h+var_170], eax
0x1800228b5  mov     eax, 150h
0x1800228ba  jmp     loc_180022642
0x1800228bf  mov     eax, 150h
0x1800228c4  jmp     short loc_1800228EC
0x1800228c6  mov     rdx, [rbp+0B0h+pGroup]; pGroup
0x1800228ca  call    cs:__imp_SetSecurityDescriptorGroup
0x1800228d0  test    eax, eax
0x1800228d2  jnz     short loc_1800228E7
0x1800228d4  call    GetLastFailureAsHRESULT
0x1800228d9  mov     [rsp+1B0h+var_170], eax
0x1800228dd  mov     eax, 154h
0x1800228e2  jmp     loc_180022642
0x1800228e7  mov     eax, 154h
0x1800228ec  mov     [rsp+1B0h+var_16C], ax
0x1800228f1  mov     [rsp+1B0h+var_170], edi
0x1800228f5  lea     r9, [rbp+0B0h+bDaclDefaulted]; lpbDaclDefaulted
0x1800228f9  lea     r8, [rbp+0B0h+pDacl]; pDacl
0x1800228fd  lea     rdx, [rbp+0B0h+bDaclPresent]; lpbDaclPresent
0x180022901  mov     rcx, rbx; pSecurityDescriptor
0x180022904  call    cs:__imp_GetSecurityDescriptorDacl
0x18002290a  test    eax, eax
0x18002290c  jnz     short loc_180022921
0x18002290e  call    GetLastFailureAsHRESULT
0x180022913  mov     [rsp+1B0h+var_170], eax
0x180022917  mov     eax, 158h
0x18002291c  jmp     loc_180022642
0x180022921  mov     [rsp+1B0h+var_170], edi
0x180022925  mov     eax, 158h
0x18002292a  mov     [rsp+1B0h+var_16C], ax
0x18002292f  mov     edx, [rbp+0B0h+bDaclPresent]
0x180022932  mov     r8, [rbp+0B0h+pDacl]
0x180022936  test    edx, edx
0x180022938  jz      short loc_18002297B
0x18002293a  test    r8, r8
0x18002293d  jz      short loc_18002297B
0x18002293f  lea     rax, [rbp+0B0h+var_100]
0x180022943  mov     [rsp+1B0h+var_188], rax; struct _ACL **
0x180022948  mov     [rsp+1B0h+pSid], r8; pAcl
0x18002294d  mov     r9, r12; struct CSdUserSidList *
0x180022950  mov     r8, r15; struct ISdGlobalCatalog *
0x180022953  mov     rdx, r14; struct ISdCallback2 *
0x180022956  mov     rcx, rsi; struct ISdAsyncPriv *
0x180022959  call    ?DoAclWork@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAU_ACL@@PEAPEAU5@@Z; DoAclWork(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,_ACL * const,_ACL * *)
0x18002295e  mov     [rsp+1B0h+var_170], eax
0x180022962  test    eax, eax
0x180022964  mov     eax, 15Ch
0x180022969  js      loc_180022642
0x18002296f  mov     [rsp+1B0h+var_16C], ax
0x180022974  mov     r8, [rbp+0B0h+pDacl]; pDacl
0x180022978  mov     edx, [rbp+0B0h+bDaclPresent]; bDaclPresent
0x18002297b  mov     rax, [rbp+0B0h+var_100]
0x18002297f  mov     r9d, [rbp+0B0h+bDaclDefaulted]; bDaclDefaulted
0x180022983  lea     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x180022987  test    rax, rax
0x18002298a  jz      short loc_1800229B3
0x18002298c  mov     r8, rax; pDacl
0x18002298f  call    cs:__imp_SetSecurityDescriptorDacl
0x180022995  test    eax, eax
0x180022997  jnz     short loc_1800229AC
0x180022999  call    GetLastFailureAsHRESULT
0x18002299e  mov     [rsp+1B0h+var_170], eax
0x1800229a2  mov     eax, 161h
0x1800229a7  jmp     loc_180022642
0x1800229ac  mov     eax, 161h
0x1800229b1  jmp     short loc_1800229D5
0x1800229b3  call    cs:__imp_SetSecurityDescriptorDacl
0x1800229b9  test    eax, eax
0x1800229bb  jnz     short loc_1800229D0
0x1800229bd  call    GetLastFailureAsHRESULT
0x1800229c2  mov     [rsp+1B0h+var_170], eax
0x1800229c6  mov     eax, 165h
0x1800229cb  jmp     loc_180022642
0x1800229d0  mov     eax, 165h
0x1800229d5  mov     [rsp+1B0h+var_16C], ax
0x1800229da  mov     [rsp+1B0h+var_170], edi
0x1800229de  lea     r9, [rbp+0B0h+bSaclDefaulted]; lpbSaclDefaulted
0x1800229e2  lea     r8, [rbp+0B0h+pSacl]; pSacl
0x1800229e6  lea     rdx, [rbp+0B0h+bSaclPresent]; lpbSaclPresent
0x1800229ea  mov     rcx, rbx; pSecurityDescriptor
0x1800229ed  call    cs:__imp_GetSecurityDescriptorSacl
0x1800229f3  test    eax, eax
0x1800229f5  jnz     short loc_180022A0A
0x1800229f7  call    GetLastFailureAsHRESULT
0x1800229fc  mov     [rsp+1B0h+var_170], eax
0x180022a00  mov     eax, 168h
0x180022a05  jmp     loc_180022642
0x180022a0a  mov     [rsp+1B0h+var_170], edi
0x180022a0e  mov     eax, 168h
0x180022a13  mov     [rsp+1B0h+var_16C], ax
0x180022a18  mov     edx, [rbp+0B0h+bSaclPresent]
  ... truncated ...
```
