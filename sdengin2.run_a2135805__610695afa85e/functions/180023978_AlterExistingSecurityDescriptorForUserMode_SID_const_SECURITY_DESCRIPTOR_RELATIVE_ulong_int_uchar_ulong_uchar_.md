# AlterExistingSecurityDescriptorForUserMode(_SID const *,_SECURITY_DESCRIPTOR_RELATIVE *,ulong,int,uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x180023978`
- end: `0x180023f5f`
- name: `?AlterExistingSecurityDescriptorForUserMode@@YAJPEBU_SID@@PEAU_SECURITY_DESCRIPTOR_RELATIVE@@KHPEAPEAEPEAK23@Z`
- size: `1511`
- prototype: `__int64 __usercall@<rax>(PSID pSid@<rcx>, PSECURITY_DESCRIPTOR pSecurityDescriptor@<rdx>, ULONG SecurityDescriptorLength@<r8d>, int@<r9d>, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180026b6c`

## callees

- `0x180023978`
- `0x1800252f0`
- `0x180025c68`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800cf552`

## import_xrefs

- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180023a96`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180023a96`
- `KERNEL32!GetLastError` at `0x180023d36`
- `KERNEL32!GetLastError` at `0x180023d36`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180023d26`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180023da9`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180023d26`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180023da9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180023c9c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180023c9c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180023ba1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180023be4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180023ba1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180023be4`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180023ace`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180023ace`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180023cd9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180023de6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180023cd9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180023de6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180023b0f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180023b0f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180023c25`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180023c25`
- `ole32!CoTaskMemFree` at `0x180023efb`
- `ole32!CoTaskMemFree` at `0x180023f0a`
- `ole32!CoTaskMemFree` at `0x180023f19`
- `ole32!CoTaskMemFree` at `0x180023f27`
- `ole32!CoTaskMemFree` at `0x180023efb`
- `ole32!CoTaskMemFree` at `0x180023f0a`
- `ole32!CoTaskMemFree` at `0x180023f19`
- `ole32!CoTaskMemFree` at `0x180023f27`
- `ole32!CoTaskMemAlloc` at `0x180023d6d`
- `ole32!CoTaskMemAlloc` at `0x180023e8a`
- `ole32!CoTaskMemAlloc` at `0x180023d6d`
- `ole32!CoTaskMemAlloc` at `0x180023e8a`

## string_xrefs

- `0x1800239ae`: `AlterExistingSecurityDescriptorForUserMode`

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
    0x316u,
    1u);
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
0x180023978  mov     [rsp-8+arg_8], rbx
0x18002397d  mov     [rsp-8+arg_18], r9d
0x180023982  push    rbp
0x180023983  push    rsi
0x180023984  push    rdi
0x180023985  push    r12
0x180023987  push    r13
0x180023989  push    r14
0x18002398b  push    r15
0x18002398d  lea     rbp, [rsp-7]
0x180023992  sub     rsp, 0C0h
0x180023999  mov     r12d, r8d
0x18002399c  mov     rdi, rdx
0x18002399f  mov     r14, rcx
0x1800239a2  mov     r9d, 1; unsigned __int16
0x1800239a8  mov     r8d, 316h; unsigned __int16
0x1800239ae  lea     rdx, aAlterexistings_0; "AlterExistingSecurityDescriptorForUserM"...
0x1800239b5  lea     rcx, [rsp+0F0h+var_C8]; this
0x1800239ba  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800239bf  xor     edx, edx
0x1800239c1  mov     [rbp+37h+pControl], dx
0x1800239c5  mov     [rbp+37h+dwRevision], edx
0x1800239c8  xorps   xmm0, xmm0
0x1800239cb  xor     eax, eax
0x1800239cd  movups  [rbp+37h+pSecurityDescriptor], xmm0
0x1800239d1  movups  [rbp+37h+var_48], xmm0
0x1800239d5  mov     [rbp+37h+var_38], rax
0x1800239d9  mov     ebx, edx
0x1800239db  mov     [rsp+0F0h+dwBufferLength], edx
0x1800239df  mov     [rbp+37h+pDacl], rdx
0x1800239e3  mov     r13d, edx
0x1800239e6  mov     [rbp+37h+var_78], rdx
0x1800239ea  mov     [rbp+37h+bDaclDefaulted], edx
0x1800239ed  mov     [rbp+37h+bDaclPresent], edx
0x1800239f0  mov     [rbp+37h+pSacl], rdx
0x1800239f4  mov     esi, edx
0x1800239f6  mov     [rbp+37h+var_68], rdx
0x1800239fa  mov     [rbp+37h+bSaclDefaulted], edx
0x1800239fd  mov     [rbp+37h+bSaclPresent], edx
0x180023a00  mov     rcx, [rbp+37h+arg_20]
0x180023a04  test    rcx, rcx
0x180023a07  jz      short loc_180023A0C
0x180023a09  mov     [rcx], rdx
0x180023a0c  mov     r15, [rbp+37h+arg_28]
0x180023a10  test    r15, r15
0x180023a13  jz      short loc_180023A18
0x180023a15  mov     [r15], edx
0x180023a18  mov     eax, 32Fh
0x180023a1d  test    r14, r14
0x180023a20  jnz     short loc_180023A34
0x180023a22  mov     [rsp+0F0h+var_C8], 80070057h
0x180023a2a  mov     [rsp+0F0h+var_C2], ax
0x180023a2f  jmp     loc_180023EF8
0x180023a34  mov     [rsp+0F0h+var_C4], ax
0x180023a39  mov     eax, 330h
0x180023a3e  test    rdi, rdi
0x180023a41  jz      short loc_180023A22
0x180023a43  mov     [rsp+0F0h+var_C4], ax
0x180023a48  mov     eax, 331h
0x180023a4d  test    rcx, rcx
0x180023a50  jz      short loc_180023A22
0x180023a52  mov     [rsp+0F0h+var_C4], ax
0x180023a57  mov     eax, 332h
0x180023a5c  test    r15, r15
0x180023a5f  jz      short loc_180023A22
0x180023a61  mov     [rsp+0F0h+var_C4], ax
0x180023a66  mov     eax, 333h
0x180023a6b  cmp     [rbp+37h+arg_30], rdx
0x180023a6f  jz      short loc_180023A22
0x180023a71  mov     [rsp+0F0h+var_C4], ax
0x180023a76  mov     eax, 334h
0x180023a7b  cmp     [rbp+37h+arg_38], rdx
0x180023a7f  jz      short loc_180023A22
0x180023a81  mov     [rsp+0F0h+var_C8], edx
0x180023a85  mov     [rsp+0F0h+var_C4], ax
0x180023a8a  mov     r8d, 4; RequiredInformation
0x180023a90  mov     edx, r12d; SecurityDescriptorLength
0x180023a93  mov     rcx, rdi; SecurityDescriptorInput
0x180023a96  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x180023a9d  nop     dword ptr [rax+rax+00h]
0x180023aa2  xor     r12d, r12d
0x180023aa5  test    al, al
0x180023aa7  mov     eax, 336h
0x180023aac  jnz     short loc_180023ABB
0x180023aae  mov     [rsp+0F0h+var_C8], 8007053Ah
0x180023ab6  jmp     loc_180023A2A
0x180023abb  mov     [rsp+0F0h+var_C8], r12d
0x180023ac0  mov     [rsp+0F0h+var_C4], ax
0x180023ac5  mov     edx, 1; dwRevision
0x180023aca  lea     rcx, [rbp+37h+pSecurityDescriptor]; pSecurityDescriptor
0x180023ace  call    cs:__imp_InitializeSecurityDescriptor
0x180023ad5  nop     dword ptr [rax+rax+00h]
0x180023ada  test    eax, eax
0x180023adc  jnz     short loc_180023AF1
0x180023ade  call    GetLastFailureAsHRESULT
0x180023ae3  mov     [rsp+0F0h+var_C8], eax
0x180023ae7  mov     eax, 338h
0x180023aec  jmp     loc_180023A2A
0x180023af1  mov     [rsp+0F0h+var_C8], r12d
0x180023af6  mov     eax, 338h
0x180023afb  mov     [rsp+0F0h+var_C4], ax
0x180023b00  lea     r9, [rbp+37h+bDaclDefaulted]; lpbDaclDefaulted
0x180023b04  lea     r8, [rbp+37h+pDacl]; pDacl
0x180023b08  lea     rdx, [rbp+37h+bDaclPresent]; lpbDaclPresent
0x180023b0c  mov     rcx, rdi; pSecurityDescriptor
0x180023b0f  call    cs:__imp_GetSecurityDescriptorDacl
0x180023b16  nop     dword ptr [rax+rax+00h]
0x180023b1b  test    eax, eax
0x180023b1d  jnz     short loc_180023B32
0x180023b1f  call    GetLastFailureAsHRESULT
0x180023b24  mov     [rsp+0F0h+var_C8], eax
0x180023b28  mov     eax, 33Ah
0x180023b2d  jmp     loc_180023A2A
0x180023b32  mov     [rsp+0F0h+var_C8], r12d
0x180023b37  mov     eax, 33Ah
0x180023b3c  mov     [rsp+0F0h+var_C4], ax
0x180023b41  cmp     [rbp+37h+bDaclPresent], r12d
0x180023b45  jz      loc_180023EE6
0x180023b4b  mov     rax, [rbp+37h+pDacl]
0x180023b4f  test    rax, rax
0x180023b52  jz      loc_180023EE6
0x180023b58  mov     r12d, [rbp+37h+arg_18]
0x180023b5c  test    r12d, r12d
0x180023b5f  jz      short loc_180023BD1
0x180023b61  lea     r8, [rbp+37h+var_78]; struct _ACL **
0x180023b65  mov     rdx, rax; pAcl
0x180023b68  mov     rcx, r14; pSid
0x180023b6b  call    ?DuplicateRestorerFullAccessDacl@@YAJPEBU_SID@@QEAU_ACL@@PEAPEAU2@@Z; DuplicateRestorerFullAccessDacl(_SID const *,_ACL * const,_ACL * *)
0x180023b70  mov     [rsp+0F0h+var_C8], eax
0x180023b74  xor     r14d, r14d
0x180023b77  mov     r13, [rbp+37h+var_78]
0x180023b7b  test    eax, eax
0x180023b7d  mov     eax, 343h
0x180023b82  js      loc_180023A2A
0x180023b88  mov     [rsp+0F0h+var_C4], ax
0x180023b8d  test    r13, r13
0x180023b90  jz      short loc_180023BCB
0x180023b92  mov     r9d, [rbp+37h+bDaclDefaulted]; bDaclDefaulted
0x180023b96  mov     r8, r13; pDacl
0x180023b99  lea     edx, [r14+1]; bDaclPresent
0x180023b9d  lea     rcx, [rbp+37h+pSecurityDescriptor]; pSecurityDescriptor
0x180023ba1  call    cs:__imp_SetSecurityDescriptorDacl
0x180023ba8  nop     dword ptr [rax+rax+00h]
0x180023bad  test    eax, eax
0x180023baf  jnz     short loc_180023BC4
0x180023bb1  call    GetLastFailureAsHRESULT
0x180023bb6  mov     [rsp+0F0h+var_C8], eax
0x180023bba  mov     eax, 348h
0x180023bbf  jmp     loc_180023A2A
0x180023bc4  mov     eax, 348h
0x180023bc9  jmp     short loc_180023C0C
0x180023bcb  mov     rax, [rbp+37h+pDacl]
0x180023bcf  jmp     short loc_180023BD4
0x180023bd1  xor     r14d, r14d
0x180023bd4  mov     r9d, [rbp+37h+bDaclDefaulted]; bDaclDefaulted
0x180023bd8  mov     r8, rax; pDacl
0x180023bdb  mov     edx, 1; bDaclPresent
0x180023be0  lea     rcx, [rbp+37h+pSecurityDescriptor]; pSecurityDescriptor
0x180023be4  call    cs:__imp_SetSecurityDescriptorDacl
0x180023beb  nop     dword ptr [rax+rax+00h]
0x180023bf0  test    eax, eax
0x180023bf2  jnz     short loc_180023C07
0x180023bf4  call    GetLastFailureAsHRESULT
0x180023bf9  mov     [rsp+0F0h+var_C8], eax
0x180023bfd  mov     eax, 34Ch
0x180023c02  jmp     loc_180023A2A
0x180023c07  mov     eax, 34Ch
0x180023c0c  mov     [rsp+0F0h+var_C4], ax
0x180023c11  mov     [rsp+0F0h+var_C8], r14d
0x180023c16  lea     r9, [rbp+37h+bSaclDefaulted]; lpbSaclDefaulted
0x180023c1a  lea     r8, [rbp+37h+pSacl]; pSacl
0x180023c1e  lea     rdx, [rbp+37h+bSaclPresent]; lpbSaclPresent
0x180023c22  mov     rcx, rdi; pSecurityDescriptor
0x180023c25  call    cs:__imp_GetSecurityDescriptorSacl
0x180023c2c  nop     dword ptr [rax+rax+00h]
0x180023c31  test    eax, eax
0x180023c33  jnz     short loc_180023C48
0x180023c35  call    GetLastFailureAsHRESULT
0x180023c3a  mov     [rsp+0F0h+var_C8], eax
0x180023c3e  mov     eax, 34Fh
0x180023c43  jmp     loc_180023A2A
0x180023c48  mov     [rsp+0F0h+var_C8], r14d
0x180023c4d  mov     eax, 34Fh
0x180023c52  mov     [rsp+0F0h+var_C4], ax
0x180023c57  cmp     [rbp+37h+bSaclPresent], r14d
0x180023c5b  jz      short loc_180023CCE
0x180023c5d  mov     rcx, [rbp+37h+pSacl]; pAcl
0x180023c61  test    rcx, rcx
0x180023c64  jz      short loc_180023CCE
0x180023c66  lea     rdx, [rbp+37h+var_68]; struct _ACL **
0x180023c6a  call    ?DoSaclWorkForUserMode@@YAJQEAU_ACL@@PEAPEAU1@@Z; DoSaclWorkForUserMode(_ACL * const,_ACL * *)
0x180023c6f  mov     [rsp+0F0h+var_C8], eax
0x180023c73  mov     rsi, [rbp+37h+var_68]
0x180023c77  test    eax, eax
0x180023c79  mov     eax, 353h
0x180023c7e  js      loc_180023A2A
0x180023c84  mov     [rsp+0F0h+var_C4], ax
0x180023c89  test    rsi, rsi
0x180023c8c  jz      short loc_180023CCE
0x180023c8e  mov     r9d, [rbp+37h+bSaclDefaulted]; bSaclDefaulted
0x180023c92  mov     r8, rsi; pSacl
0x180023c95  mov     edx, [rbp+37h+bSaclPresent]; bSaclPresent
0x180023c98  lea     rcx, [rbp+37h+pSecurityDescriptor]; pSecurityDescriptor
0x180023c9c  call    cs:__imp_SetSecurityDescriptorSacl
0x180023ca3  nop     dword ptr [rax+rax+00h]
0x180023ca8  test    eax, eax
0x180023caa  jnz     short loc_180023CBF
0x180023cac  call    GetLastFailureAsHRESULT
0x180023cb1  mov     [rsp+0F0h+var_C8], eax
0x180023cb5  mov     eax, 358h
0x180023cba  jmp     loc_180023A2A
0x180023cbf  mov     [rsp+0F0h+var_C8], r14d
0x180023cc4  mov     eax, 358h
0x180023cc9  mov     [rsp+0F0h+var_C4], ax
0x180023cce  lea     r8, [rbp+37h+dwRevision]; lpdwRevision
0x180023cd2  lea     rdx, [rbp+37h+pControl]; pControl
0x180023cd6  mov     rcx, rdi; pSecurityDescriptor
0x180023cd9  call    cs:__imp_GetSecurityDescriptorControl
0x180023ce0  nop     dword ptr [rax+rax+00h]
0x180023ce5  test    eax, eax
0x180023ce7  jnz     short loc_180023CFC
0x180023ce9  call    GetLastFailureAsHRESULT
0x180023cee  mov     [rsp+0F0h+var_C8], eax
0x180023cf2  mov     eax, 35Bh
0x180023cf7  jmp     loc_180023A2A
0x180023cfc  mov     [rsp+0F0h+var_C8], r14d
0x180023d01  mov     eax, 35Bh
0x180023d06  mov     [rsp+0F0h+var_C4], ax
0x180023d0b  movzx   eax, [rbp+37h+pControl]
0x180023d0f  mov     ecx, 7FFFh
0x180023d14  and     ax, cx
0x180023d17  or      word ptr [rbp+37h+pSecurityDescriptor+2], ax
0x180023d1b  lea     r8, [rsp+0F0h+dwBufferLength]; lpdwBufferLength
0x180023d20  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180023d22  lea     rcx, [rbp+37h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180023d26  call    cs:__imp_MakeSelfRelativeSD
0x180023d2d  nop     dword ptr [rax+rax+00h]
0x180023d32  test    eax, eax
0x180023d34  jnz     short loc_180023D5A
0x180023d36  call    cs:__imp_GetLastError
0x180023d3d  nop     dword ptr [rax+rax+00h]
0x180023d42  cmp     eax, 7Ah ; 'z'
0x180023d45  jz      short loc_180023D5A
0x180023d47  call    GetLastFailureAsHRESULT
0x180023d4c  mov     [rsp+0F0h+var_C8], eax
0x180023d50  mov     eax, 35Fh
0x180023d55  jmp     loc_180023A2A
0x180023d5a  mov     [rsp+0F0h+var_C8], r14d
0x180023d5f  mov     eax, 35Fh
0x180023d64  mov     [rsp+0F0h+var_C4], ax
0x180023d69  mov     ecx, [rsp+0F0h+dwBufferLength]; cb
0x180023d6d  call    cs:__imp_CoTaskMemAlloc
0x180023d74  nop     dword ptr [rax+rax+00h]
0x180023d79  mov     rbx, rax
0x180023d7c  test    rax, rax
0x180023d7f  mov     eax, 362h
0x180023d84  jnz     short loc_180023D93
0x180023d86  mov     [rsp+0F0h+var_C8], 8007000Eh
0x180023d8e  jmp     loc_180023A2A
0x180023d93  mov     [rsp+0F0h+var_C8], r14d
0x180023d98  mov     [rsp+0F0h+var_C4], ax
0x180023d9d  lea     r8, [rsp+0F0h+dwBufferLength]; lpdwBufferLength
0x180023da2  mov     rdx, rbx; pSelfRelativeSecurityDescriptor
0x180023da5  lea     rcx, [rbp+37h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180023da9  call    cs:__imp_MakeSelfRelativeSD
0x180023db0  nop     dword ptr [rax+rax+00h]
0x180023db5  test    eax, eax
0x180023db7  jnz     short loc_180023DCC
0x180023db9  call    GetLastFailureAsHRESULT
0x180023dbe  mov     [rsp+0F0h+var_C8], eax
0x180023dc2  mov     eax, 363h
0x180023dc7  jmp     loc_180023A2A
0x180023dcc  mov     [rsp+0F0h+var_C8], r14d
0x180023dd1  mov     eax, 363h
0x180023dd6  mov     [rsp+0F0h+var_C4], ax
0x180023ddb  lea     r8, [rbp+37h+dwRevision]; lpdwRevision
0x180023ddf  lea     rdx, [rbp+37h+pControl]; pControl
0x180023de3  mov     rcx, rbx; pSecurityDescriptor
0x180023de6  call    cs:__imp_GetSecurityDescriptorControl
0x180023ded  nop     dword ptr [rax+rax+00h]
0x180023df2  test    eax, eax
0x180023df4  jnz     short loc_180023E09
0x180023df6  call    GetLastFailureAsHRESULT
0x180023dfb  mov     [rsp+0F0h+var_C8], eax
0x180023dff  mov     eax, 365h
0x180023e04  jmp     loc_180023A2A
0x180023e09  mov     [rsp+0F0h+var_C8], r14d
0x180023e0e  mov     eax, 365h
0x180023e13  mov     [rsp+0F0h+var_C4], ax
0x180023e18  mov     eax, 0FFFCh
0x180023e1d  and     [rbx+2], ax
0x180023e21  mov     qword ptr [rbx+4], 0
0x180023e29  movzx   eax, [rbp+37h+pControl]
0x180023e2d  mov     ecx, 36Ch
0x180023e32  bt      ax, 0Fh
0x180023e37  jb      short loc_180023E4B
0x180023e39  mov     [rsp+0F0h+var_C8], 8007053Ah
0x180023e41  mov     [rsp+0F0h+var_C2], cx
0x180023e46  jmp     loc_180023EF8
0x180023e4b  mov     [rsp+0F0h+var_C8], r14d
  ... truncated ...
```
