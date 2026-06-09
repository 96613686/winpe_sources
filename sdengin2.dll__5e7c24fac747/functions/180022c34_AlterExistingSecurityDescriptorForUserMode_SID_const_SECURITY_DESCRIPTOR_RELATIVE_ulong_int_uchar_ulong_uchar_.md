# AlterExistingSecurityDescriptorForUserMode(_SID const *,_SECURITY_DESCRIPTOR_RELATIVE *,ulong,int,uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x180022c34`
- end: `0x1800231ae`
- name: `?AlterExistingSecurityDescriptorForUserMode@@YAJPEBU_SID@@PEAU_SECURITY_DESCRIPTOR_RELATIVE@@KHPEAPEAEPEAK23@Z`
- size: `1402`
- prototype: `__int64 __usercall@<rax>(PSID pSid@<rcx>, PSECURITY_DESCRIPTOR pSecurityDescriptor@<rdx>, ULONG SecurityDescriptorLength@<r8d>, int@<r9d>, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025bb0`

## callees

- `0x180022c34`
- `0x180024478`
- `0x180024d68`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c97c2`

## import_xrefs

- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180022d52`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180022d52`
- `KERNEL32!GetLastError` at `0x180022fbc`
- `KERNEL32!GetLastError` at `0x180022fbc`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180022fb2`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180023023`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180022fb2`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180023023`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180022f34`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180022f34`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180022e4b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180022e88`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180022e4b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180022e88`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180022d84`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180022d84`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180022f6b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18002305a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180022f6b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18002305a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180022dbf`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180022dbf`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180022ec3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180022ec3`
- `ole32!CoTaskMemFree` at `0x180023163`
- `ole32!CoTaskMemFree` at `0x18002316c`
- `ole32!CoTaskMemFree` at `0x180023175`
- `ole32!CoTaskMemFree` at `0x18002317d`
- `ole32!CoTaskMemFree` at `0x180023163`
- `ole32!CoTaskMemFree` at `0x18002316c`
- `ole32!CoTaskMemFree` at `0x180023175`
- `ole32!CoTaskMemFree` at `0x18002317d`
- `ole32!CoTaskMemAlloc` at `0x180022fed`
- `ole32!CoTaskMemAlloc` at `0x1800230f8`
- `ole32!CoTaskMemAlloc` at `0x180022fed`
- `ole32!CoTaskMemAlloc` at `0x1800230f8`

## string_xrefs

- `0x180022c6a`: `AlterExistingSecurityDescriptorForUserMode`

## pseudocode

```c
__int64 __fastcall AlterExistingSecurityDescriptorForUserMode(
        PSID pSid,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        ULONG SecurityDescriptorLength,
        int a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  char *v11; // rbx
  PACL v12; // r13
  PACL v13; // rsi
  unsigned __int8 **v14; // rcx
  unsigned int *v15; // r15
  __int16 v16; // ax
  bool v17; // zf
  __int64 v18; // rcx
  __int64 v19; // rcx
  struct _ACL *v20; // rax
  int v21; // r12d
  __int64 v22; // rcx
  __int16 v23; // ax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  WORD v31; // ax
  void *v32; // rdi
  DWORD v33; // eax
  unsigned int v34; // ebx
  DWORD dwBufferLength; // [rsp+20h] [rbp-99h] BYREF
  int LastFailureAsHRESULT; // [rsp+28h] [rbp-91h] BYREF
  __int16 v38; // [rsp+2Ch] [rbp-8Dh]
  __int16 v39; // [rsp+2Eh] [rbp-8Bh]
  WINBOOL bDaclDefaulted; // [rsp+60h] [rbp-59h] BYREF
  WINBOOL bSaclPresent; // [rsp+64h] [rbp-55h] BYREF
  WINBOOL bDaclPresent; // [rsp+68h] [rbp-51h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+6Ch] [rbp-4Dh] BYREF
  DWORD dwRevision; // [rsp+70h] [rbp-49h] BYREF
  PACL v45; // [rsp+78h] [rbp-41h] BYREF
  PACL pDacl; // [rsp+80h] [rbp-39h] BYREF
  PACL v47; // [rsp+88h] [rbp-31h] BYREF
  PACL pSacl; // [rsp+90h] [rbp-29h] BYREF
  _OWORD pSecurityDescriptora[2]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-1h]
  WORD pControl; // [rsp+100h] [rbp+47h] BYREF
  int v52; // [rsp+118h] [rbp+5Fh]

  v52 = a4;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "AlterExistingSecurityDescriptorForUserMode",
    790,
    1);
  pControl = 0;
  dwRevision = 0;
  memset(pSecurityDescriptora, 0, sizeof(pSecurityDescriptora));
  v50 = 0;
  v11 = 0;
  dwBufferLength = 0;
  pDacl = 0;
  v12 = 0;
  v45 = 0;
  bDaclDefaulted = 0;
  bDaclPresent = 0;
  pSacl = 0;
  v13 = 0;
  v47 = 0;
  bSaclDefaulted = 0;
  bSaclPresent = 0;
  v14 = a5;
  if ( a5 )
    *a5 = 0;
  v15 = a6;
  if ( a6 )
    *a6 = 0;
  v16 = 815;
  if ( !pSid )
    goto LABEL_6;
  v38 = 815;
  v16 = 816;
  if ( !pSecurityDescriptor )
    goto LABEL_6;
  v38 = 816;
  v16 = 817;
  if ( !v14 || (v38 = 817, v16 = 818, !v15) || (v38 = 818, v16 = 819, !a7) || (v38 = 819, v16 = 820, !a8) )
  {
LABEL_6:
    LastFailureAsHRESULT = -2147024809;
LABEL_7:
    v39 = v16;
    goto LABEL_65;
  }
  LastFailureAsHRESULT = 0;
  v38 = 820;
  v17 = RtlValidRelativeSecurityDescriptor(pSecurityDescriptor, SecurityDescriptorLength, 4u) == 0;
  v16 = 822;
  if ( v17 )
  {
    LastFailureAsHRESULT = -2147023558;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v38 = 822;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptora, 1u) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v18);
    v16 = 824;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v38 = 824;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v19);
    v16 = 826;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v38 = 826;
  if ( !bDaclPresent || (v20 = pDacl) == 0 )
  {
    LastFailureAsHRESULT = 1;
    v38 = 830;
    goto LABEL_65;
  }
  v21 = v52;
  if ( !v52 )
    goto LABEL_28;
  LastFailureAsHRESULT = DuplicateRestorerFullAccessDacl(pSid, pDacl, &v45);
  v12 = v45;
  v16 = 835;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_7;
  v38 = 835;
  if ( !v45 )
  {
    v20 = pDacl;
LABEL_28:
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptora, 1, v20, bDaclDefaulted) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v24);
      v16 = 844;
      goto LABEL_7;
    }
    v23 = 844;
    goto LABEL_31;
  }
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptora, 1, v45, bDaclDefaulted) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v22);
    v16 = 840;
    goto LABEL_7;
  }
  v23 = 840;
LABEL_31:
  v38 = v23;
  LastFailureAsHRESULT = 0;
  if ( !GetSecurityDescriptorSacl(pSecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v25);
    v16 = 847;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v38 = 847;
  if ( bSaclPresent && pSacl )
  {
    LastFailureAsHRESULT = DoSaclWorkForUserMode(pSacl, &v47);
    v13 = v47;
    v16 = 851;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_7;
    v38 = 851;
    if ( v47 )
    {
      if ( !SetSecurityDescriptorSacl(pSecurityDescriptora, bSaclPresent, v47, bSaclDefaulted) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v26);
        v16 = 856;
        goto LABEL_7;
      }
      LastFailureAsHRESULT = 0;
      v38 = 856;
    }
  }
  if ( !GetSecurityDescriptorControl(pSecurityDescriptor, &pControl, &dwRevision) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v27);
    v16 = 859;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v38 = 859;
  WORD1(pSecurityDescriptora[0]) |= pControl & 0x7FFF;
  if ( !MakeSelfRelativeSD(pSecurityDescriptora, 0, &dwBufferLength) && GetLastError() != 122 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v28);
    v16 = 863;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v38 = 863;
  v11 = (char *)CoTaskMemAlloc(dwBufferLength);
  v16 = 866;
  if ( !v11 )
  {
LABEL_46:
    LastFailureAsHRESULT = -2147024882;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v38 = 866;
  if ( !MakeSelfRelativeSD(pSecurityDescriptora, v11, &dwBufferLength) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v29);
    v16 = 867;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v38 = 867;
  if ( !GetSecurityDescriptorControl(v11, &pControl, &dwRevision) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v30);
    v16 = 869;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v38 = 869;
  *((_WORD *)v11 + 1) &= 0xFFFCu;
  *(_QWORD *)(v11 + 4) = 0;
  v31 = pControl;
  if ( (pControl & 0x8000u) == 0 )
  {
    LastFailureAsHRESULT = -2147023558;
    v39 = 876;
    goto LABEL_65;
  }
  LastFailureAsHRESULT = 0;
  v38 = 876;
  if ( (pControl & 0x400) != 0 )
  {
    v31 = pControl | 0x100;
    pControl |= 0x100u;
  }
  if ( v13 )
  {
    if ( (v31 & 0x800) == 0 )
      goto LABEL_60;
    v31 |= 0x200u;
  }
  else
  {
    v31 &= 0xDFCFu;
  }
  pControl = v31;
LABEL_60:
  *((_WORD *)v11 + 1) = v31;
  v32 = CoTaskMemAlloc(dwBufferLength);
  v16 = 898;
  if ( !v32 )
    goto LABEL_46;
  LastFailureAsHRESULT = 0;
  v38 = 898;
  memcpy_0(v32, v11, dwBufferLength);
  v33 = dwBufferLength;
  if ( v21 )
  {
    *a5 = (unsigned __int8 *)v11;
    v11 = 0;
    *v15 = v33;
  }
  *a7 = (unsigned __int8 *)v32;
  *a8 = v33;
LABEL_65:
  CoTaskMemFree(v12);
  CoTaskMemFree(v13);
  CoTaskMemFree(v11);
  CoTaskMemFree(0);
  v34 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v34;
}

```

## disassembly

```asm
0x180022c34  mov     [rsp-8+arg_8], rbx
0x180022c39  mov     [rsp-8+arg_18], r9d
0x180022c3e  push    rbp
0x180022c3f  push    rsi
0x180022c40  push    rdi
0x180022c41  push    r12
0x180022c43  push    r13
0x180022c45  push    r14
0x180022c47  push    r15
0x180022c49  lea     rbp, [rsp-7]
0x180022c4e  sub     rsp, 0C0h
0x180022c55  mov     r12d, r8d
0x180022c58  mov     rdi, rdx
0x180022c5b  mov     r14, rcx
0x180022c5e  mov     r9d, 1; unsigned __int16
0x180022c64  mov     r8d, 316h; unsigned __int16
0x180022c6a  lea     rdx, aAlterexistings_0; "AlterExistingSecurityDescriptorForUserM"...
0x180022c71  lea     rcx, [rsp+0F0h+var_C8]; this
0x180022c76  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180022c7b  xor     edx, edx
0x180022c7d  mov     [rbp+37h+pControl], dx
0x180022c81  mov     [rbp+37h+dwRevision], edx
0x180022c84  xorps   xmm0, xmm0
0x180022c87  xor     eax, eax
0x180022c89  movups  [rbp+37h+pSecurityDescriptor], xmm0
0x180022c8d  movups  [rbp+37h+var_48], xmm0
0x180022c91  mov     [rbp+37h+var_38], rax
0x180022c95  mov     ebx, edx
0x180022c97  mov     [rsp+0F0h+dwBufferLength], edx
0x180022c9b  mov     [rbp+37h+pDacl], rdx
0x180022c9f  mov     r13d, edx
0x180022ca2  mov     [rbp+37h+var_78], rdx
0x180022ca6  mov     [rbp+37h+bDaclDefaulted], edx
0x180022ca9  mov     [rbp+37h+bDaclPresent], edx
0x180022cac  mov     [rbp+37h+pSacl], rdx
0x180022cb0  mov     esi, edx
0x180022cb2  mov     [rbp+37h+var_68], rdx
0x180022cb6  mov     [rbp+37h+bSaclDefaulted], edx
0x180022cb9  mov     [rbp+37h+bSaclPresent], edx
0x180022cbc  mov     rcx, [rbp+37h+arg_20]
0x180022cc0  test    rcx, rcx
0x180022cc3  jz      short loc_180022CC8
0x180022cc5  mov     [rcx], rdx
0x180022cc8  mov     r15, [rbp+37h+arg_28]
0x180022ccc  test    r15, r15
0x180022ccf  jz      short loc_180022CD4
0x180022cd1  mov     [r15], edx
0x180022cd4  mov     eax, 32Fh
0x180022cd9  test    r14, r14
0x180022cdc  jnz     short loc_180022CF0
0x180022cde  mov     [rsp+0F0h+var_C8], 80070057h
0x180022ce6  mov     [rsp+0F0h+var_C2], ax
0x180022ceb  jmp     loc_180023160
0x180022cf0  mov     [rsp+0F0h+var_C4], ax
0x180022cf5  mov     eax, 330h
0x180022cfa  test    rdi, rdi
0x180022cfd  jz      short loc_180022CDE
0x180022cff  mov     [rsp+0F0h+var_C4], ax
0x180022d04  mov     eax, 331h
0x180022d09  test    rcx, rcx
0x180022d0c  jz      short loc_180022CDE
0x180022d0e  mov     [rsp+0F0h+var_C4], ax
0x180022d13  mov     eax, 332h
0x180022d18  test    r15, r15
0x180022d1b  jz      short loc_180022CDE
0x180022d1d  mov     [rsp+0F0h+var_C4], ax
0x180022d22  mov     eax, 333h
0x180022d27  cmp     [rbp+37h+arg_30], rdx
0x180022d2b  jz      short loc_180022CDE
0x180022d2d  mov     [rsp+0F0h+var_C4], ax
0x180022d32  mov     eax, 334h
0x180022d37  cmp     [rbp+37h+arg_38], rdx
0x180022d3b  jz      short loc_180022CDE
0x180022d3d  mov     [rsp+0F0h+var_C8], edx
0x180022d41  mov     [rsp+0F0h+var_C4], ax
0x180022d46  mov     r8d, 4; RequiredInformation
0x180022d4c  mov     edx, r12d; SecurityDescriptorLength
0x180022d4f  mov     rcx, rdi; SecurityDescriptorInput
0x180022d52  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x180022d58  xor     r12d, r12d
0x180022d5b  test    al, al
0x180022d5d  mov     eax, 336h
0x180022d62  jnz     short loc_180022D71
0x180022d64  mov     [rsp+0F0h+var_C8], 8007053Ah
0x180022d6c  jmp     loc_180022CE6
0x180022d71  mov     [rsp+0F0h+var_C8], r12d
0x180022d76  mov     [rsp+0F0h+var_C4], ax
0x180022d7b  mov     edx, 1; dwRevision
0x180022d80  lea     rcx, [rbp+37h+pSecurityDescriptor]; pSecurityDescriptor
0x180022d84  call    cs:__imp_InitializeSecurityDescriptor
0x180022d8a  test    eax, eax
0x180022d8c  jnz     short loc_180022DA1
0x180022d8e  call    GetLastFailureAsHRESULT
0x180022d93  mov     [rsp+0F0h+var_C8], eax
0x180022d97  mov     eax, 338h
0x180022d9c  jmp     loc_180022CE6
0x180022da1  mov     [rsp+0F0h+var_C8], r12d
0x180022da6  mov     eax, 338h
0x180022dab  mov     [rsp+0F0h+var_C4], ax
0x180022db0  lea     r9, [rbp+37h+bDaclDefaulted]; lpbDaclDefaulted
0x180022db4  lea     r8, [rbp+37h+pDacl]; pDacl
0x180022db8  lea     rdx, [rbp+37h+bDaclPresent]; lpbDaclPresent
0x180022dbc  mov     rcx, rdi; pSecurityDescriptor
0x180022dbf  call    cs:__imp_GetSecurityDescriptorDacl
0x180022dc5  test    eax, eax
0x180022dc7  jnz     short loc_180022DDC
0x180022dc9  call    GetLastFailureAsHRESULT
0x180022dce  mov     [rsp+0F0h+var_C8], eax
0x180022dd2  mov     eax, 33Ah
0x180022dd7  jmp     loc_180022CE6
0x180022ddc  mov     [rsp+0F0h+var_C8], r12d
0x180022de1  mov     eax, 33Ah
0x180022de6  mov     [rsp+0F0h+var_C4], ax
0x180022deb  cmp     [rbp+37h+bDaclPresent], r12d
0x180022def  jz      loc_18002314E
0x180022df5  mov     rax, [rbp+37h+pDacl]
0x180022df9  test    rax, rax
0x180022dfc  jz      loc_18002314E
0x180022e02  mov     r12d, [rbp+37h+arg_18]
0x180022e06  test    r12d, r12d
0x180022e09  jz      short loc_180022E75
0x180022e0b  lea     r8, [rbp+37h+var_78]; struct _ACL **
0x180022e0f  mov     rdx, rax; pAcl
0x180022e12  mov     rcx, r14; pSid
0x180022e15  call    ?DuplicateRestorerFullAccessDacl@@YAJPEBU_SID@@QEAU_ACL@@PEAPEAU2@@Z; DuplicateRestorerFullAccessDacl(_SID const *,_ACL * const,_ACL * *)
0x180022e1a  mov     [rsp+0F0h+var_C8], eax
0x180022e1e  xor     r14d, r14d
0x180022e21  mov     r13, [rbp+37h+var_78]
0x180022e25  test    eax, eax
0x180022e27  mov     eax, 343h
0x180022e2c  js      loc_180022CE6
0x180022e32  mov     [rsp+0F0h+var_C4], ax
0x180022e37  test    r13, r13
0x180022e3a  jz      short loc_180022E6F
0x180022e3c  mov     r9d, [rbp+37h+bDaclDefaulted]; bDaclDefaulted
0x180022e40  mov     r8, r13; pDacl
0x180022e43  lea     edx, [r14+1]; bDaclPresent
0x180022e47  lea     rcx, [rbp+37h+pSecurityDescriptor]; pSecurityDescriptor
0x180022e4b  call    cs:__imp_SetSecurityDescriptorDacl
0x180022e51  test    eax, eax
0x180022e53  jnz     short loc_180022E68
0x180022e55  call    GetLastFailureAsHRESULT
0x180022e5a  mov     [rsp+0F0h+var_C8], eax
0x180022e5e  mov     eax, 348h
0x180022e63  jmp     loc_180022CE6
0x180022e68  mov     eax, 348h
0x180022e6d  jmp     short loc_180022EAA
0x180022e6f  mov     rax, [rbp+37h+pDacl]
0x180022e73  jmp     short loc_180022E78
0x180022e75  xor     r14d, r14d
0x180022e78  mov     r9d, [rbp+37h+bDaclDefaulted]; bDaclDefaulted
0x180022e7c  mov     r8, rax; pDacl
0x180022e7f  mov     edx, 1; bDaclPresent
0x180022e84  lea     rcx, [rbp+37h+pSecurityDescriptor]; pSecurityDescriptor
0x180022e88  call    cs:__imp_SetSecurityDescriptorDacl
0x180022e8e  test    eax, eax
0x180022e90  jnz     short loc_180022EA5
0x180022e92  call    GetLastFailureAsHRESULT
0x180022e97  mov     [rsp+0F0h+var_C8], eax
0x180022e9b  mov     eax, 34Ch
0x180022ea0  jmp     loc_180022CE6
0x180022ea5  mov     eax, 34Ch
0x180022eaa  mov     [rsp+0F0h+var_C4], ax
0x180022eaf  mov     [rsp+0F0h+var_C8], r14d
0x180022eb4  lea     r9, [rbp+37h+bSaclDefaulted]; lpbSaclDefaulted
0x180022eb8  lea     r8, [rbp+37h+pSacl]; pSacl
0x180022ebc  lea     rdx, [rbp+37h+bSaclPresent]; lpbSaclPresent
0x180022ec0  mov     rcx, rdi; pSecurityDescriptor
0x180022ec3  call    cs:__imp_GetSecurityDescriptorSacl
0x180022ec9  test    eax, eax
0x180022ecb  jnz     short loc_180022EE0
0x180022ecd  call    GetLastFailureAsHRESULT
0x180022ed2  mov     [rsp+0F0h+var_C8], eax
0x180022ed6  mov     eax, 34Fh
0x180022edb  jmp     loc_180022CE6
0x180022ee0  mov     [rsp+0F0h+var_C8], r14d
0x180022ee5  mov     eax, 34Fh
0x180022eea  mov     [rsp+0F0h+var_C4], ax
0x180022eef  cmp     [rbp+37h+bSaclPresent], r14d
0x180022ef3  jz      short loc_180022F60
0x180022ef5  mov     rcx, [rbp+37h+pSacl]; pAcl
0x180022ef9  test    rcx, rcx
0x180022efc  jz      short loc_180022F60
0x180022efe  lea     rdx, [rbp+37h+var_68]; struct _ACL **
0x180022f02  call    ?DoSaclWorkForUserMode@@YAJQEAU_ACL@@PEAPEAU1@@Z; DoSaclWorkForUserMode(_ACL * const,_ACL * *)
0x180022f07  mov     [rsp+0F0h+var_C8], eax
0x180022f0b  mov     rsi, [rbp+37h+var_68]
0x180022f0f  test    eax, eax
0x180022f11  mov     eax, 353h
0x180022f16  js      loc_180022CE6
0x180022f1c  mov     [rsp+0F0h+var_C4], ax
0x180022f21  test    rsi, rsi
0x180022f24  jz      short loc_180022F60
0x180022f26  mov     r9d, [rbp+37h+bSaclDefaulted]; bSaclDefaulted
0x180022f2a  mov     r8, rsi; pSacl
0x180022f2d  mov     edx, [rbp+37h+bSaclPresent]; bSaclPresent
0x180022f30  lea     rcx, [rbp+37h+pSecurityDescriptor]; pSecurityDescriptor
0x180022f34  call    cs:__imp_SetSecurityDescriptorSacl
0x180022f3a  test    eax, eax
0x180022f3c  jnz     short loc_180022F51
0x180022f3e  call    GetLastFailureAsHRESULT
0x180022f43  mov     [rsp+0F0h+var_C8], eax
0x180022f47  mov     eax, 358h
0x180022f4c  jmp     loc_180022CE6
0x180022f51  mov     [rsp+0F0h+var_C8], r14d
0x180022f56  mov     eax, 358h
0x180022f5b  mov     [rsp+0F0h+var_C4], ax
0x180022f60  lea     r8, [rbp+37h+dwRevision]; lpdwRevision
0x180022f64  lea     rdx, [rbp+37h+pControl]; pControl
0x180022f68  mov     rcx, rdi; pSecurityDescriptor
0x180022f6b  call    cs:__imp_GetSecurityDescriptorControl
0x180022f71  test    eax, eax
0x180022f73  jnz     short loc_180022F88
0x180022f75  call    GetLastFailureAsHRESULT
0x180022f7a  mov     [rsp+0F0h+var_C8], eax
0x180022f7e  mov     eax, 35Bh
0x180022f83  jmp     loc_180022CE6
0x180022f88  mov     [rsp+0F0h+var_C8], r14d
0x180022f8d  mov     eax, 35Bh
0x180022f92  mov     [rsp+0F0h+var_C4], ax
0x180022f97  movzx   eax, [rbp+37h+pControl]
0x180022f9b  mov     ecx, 7FFFh
0x180022fa0  and     ax, cx
0x180022fa3  or      word ptr [rbp+37h+pSecurityDescriptor+2], ax
0x180022fa7  lea     r8, [rsp+0F0h+dwBufferLength]; lpdwBufferLength
0x180022fac  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180022fae  lea     rcx, [rbp+37h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180022fb2  call    cs:__imp_MakeSelfRelativeSD
0x180022fb8  test    eax, eax
0x180022fba  jnz     short loc_180022FDA
0x180022fbc  call    cs:__imp_GetLastError
0x180022fc2  cmp     eax, 7Ah ; 'z'
0x180022fc5  jz      short loc_180022FDA
0x180022fc7  call    GetLastFailureAsHRESULT
0x180022fcc  mov     [rsp+0F0h+var_C8], eax
0x180022fd0  mov     eax, 35Fh
0x180022fd5  jmp     loc_180022CE6
0x180022fda  mov     [rsp+0F0h+var_C8], r14d
0x180022fdf  mov     eax, 35Fh
0x180022fe4  mov     [rsp+0F0h+var_C4], ax
0x180022fe9  mov     ecx, [rsp+0F0h+dwBufferLength]; cb
0x180022fed  call    cs:__imp_CoTaskMemAlloc
0x180022ff3  mov     rbx, rax
0x180022ff6  test    rax, rax
0x180022ff9  mov     eax, 362h
0x180022ffe  jnz     short loc_18002300D
0x180023000  mov     [rsp+0F0h+var_C8], 8007000Eh
0x180023008  jmp     loc_180022CE6
0x18002300d  mov     [rsp+0F0h+var_C8], r14d
0x180023012  mov     [rsp+0F0h+var_C4], ax
0x180023017  lea     r8, [rsp+0F0h+dwBufferLength]; lpdwBufferLength
0x18002301c  mov     rdx, rbx; pSelfRelativeSecurityDescriptor
0x18002301f  lea     rcx, [rbp+37h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180023023  call    cs:__imp_MakeSelfRelativeSD
0x180023029  test    eax, eax
0x18002302b  jnz     short loc_180023040
0x18002302d  call    GetLastFailureAsHRESULT
0x180023032  mov     [rsp+0F0h+var_C8], eax
0x180023036  mov     eax, 363h
0x18002303b  jmp     loc_180022CE6
0x180023040  mov     [rsp+0F0h+var_C8], r14d
0x180023045  mov     eax, 363h
0x18002304a  mov     [rsp+0F0h+var_C4], ax
0x18002304f  lea     r8, [rbp+37h+dwRevision]; lpdwRevision
0x180023053  lea     rdx, [rbp+37h+pControl]; pControl
0x180023057  mov     rcx, rbx; pSecurityDescriptor
0x18002305a  call    cs:__imp_GetSecurityDescriptorControl
0x180023060  test    eax, eax
0x180023062  jnz     short loc_180023077
0x180023064  call    GetLastFailureAsHRESULT
0x180023069  mov     [rsp+0F0h+var_C8], eax
0x18002306d  mov     eax, 365h
0x180023072  jmp     loc_180022CE6
0x180023077  mov     [rsp+0F0h+var_C8], r14d
0x18002307c  mov     eax, 365h
0x180023081  mov     [rsp+0F0h+var_C4], ax
0x180023086  mov     eax, 0FFFCh
0x18002308b  and     [rbx+2], ax
0x18002308f  mov     qword ptr [rbx+4], 0
0x180023097  movzx   eax, [rbp+37h+pControl]
0x18002309b  mov     ecx, 36Ch
0x1800230a0  bt      ax, 0Fh
0x1800230a5  jb      short loc_1800230B9
0x1800230a7  mov     [rsp+0F0h+var_C8], 8007053Ah
0x1800230af  mov     [rsp+0F0h+var_C2], cx
0x1800230b4  jmp     loc_180023160
0x1800230b9  mov     [rsp+0F0h+var_C8], r14d
0x1800230be  mov     [rsp+0F0h+var_C4], cx
0x1800230c3  bt      ax, 0Ah
0x1800230c8  jnb     short loc_1800230D2
0x1800230ca  or      ax, 100h
0x1800230ce  mov     [rbp+37h+pControl], ax
0x1800230d2  test    rsi, rsi
0x1800230d5  jz      short loc_1800230E4
0x1800230d7  bt      ax, 0Bh
0x1800230dc  jnb     short loc_1800230F0
0x1800230de  or      ax, 200h
0x1800230e2  jmp     short loc_1800230EC
0x1800230e4  mov     ecx, 0DFCFh
0x1800230e9  and     ax, cx
  ... truncated ...
```
