# CPackageManagerWrapper::GetApplicability(AppxPackage const *,GetApplicabilityFlags,bool,void * const,wchar_t const *,char const *,wchar_t * *,ApplicabilityState *)

- ea: `0x180218d20`
- end: `0x1802194a0`
- name: `?GetApplicability@CPackageManagerWrapper@@QEAAJPEBVAppxPackage@@W4GetApplicabilityFlags@@_NQEAXPEB_WPEBDPEAPEA_WPEAW4ApplicabilityState@@@Z`
- size: `1920`
- prototype: `int __high(const struct AppxPackage *, enum GetApplicabilityFlags, bool, void *const, const wchar_t *, const char *, wchar_t **, enum ApplicabilityState *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180204e18`

## callees

- `0x180038d00`
- `0x18010e88c`
- `0x18010f004`
- `0x180113a3c`
- `0x180113ae8`
- `0x180113b9c`
- `0x18012b618`
- `0x1801f2984`
- `0x180218aa8`
- `0x180218d20`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180218dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180218dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180218e17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180218e2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180218e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180218f9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180218fb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180218fc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180219305`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180219318`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021932b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180218e17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180218e2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180218e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180218f9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180218fb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180218fc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180219305`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180219318`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021932b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180218dc3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180218dc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802192d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802192d5`
- `OLEAUT32!__imp_SysFreeString` at `0x1802190e1`
- `OLEAUT32!__imp_SysFreeString` at `0x180219338`
- `OLEAUT32!__imp_SysFreeString` at `0x1802190e1`
- `OLEAUT32!__imp_SysFreeString` at `0x180219338`
- `OLEAUT32!__imp_SysStringLen` at `0x180219202`
- `OLEAUT32!__imp_SysStringLen` at `0x18021927d`
- `OLEAUT32!__imp_SysStringLen` at `0x180219202`
- `OLEAUT32!__imp_SysStringLen` at `0x18021927d`

## string_xrefs

- `0x1802193ec`: `Installed`
- `0x1802193f5`: `Installable`
- `0x1802193fe`: `NotInstallable`
- `0x18021916a`: `CoServicing: Non-required installable package (%ws) found! Marking as NotInstallable.`
- `0x180219150`: `CoServicing: Required package (%ws) is already installed! Marking as NotInstallable.`
- `0x1802193e3`: `RequiresReinstall`
- `0x180218f6f`: `Calling GetApplicability5(package: %ws; flags: %lu; cIntentPFNs: %lu, userSid: %ws)`
- `0x180219436`: `GetApplicability for package '%ws' (CoServiced: %ws; Intent: %ws) = '%ws'`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CPackageManagerWrapper::GetApplicability(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        char a4,
        PSID Sid,
        wchar_t *a6,
        wchar_t **a7,
        OLECHAR **a8,
        unsigned int *a9)
{
  const wchar_t *v11; // r10
  const wchar_t **v12; // rsi
  unsigned int v13; // r15d
  _QWORD *v14; // rdi
  OLECHAR *v15; // rbx
  void *v16; // rcx
  wchar_t **v17; // rax
  signed int LastError; // eax
  signed int AppxPackageApplicability; // esi
  int v20; // eax
  __int64 v21; // r14
  _QWORD *v22; // rcx
  char *v23; // rdx
  unsigned int v24; // r14d
  int v25; // r8d
  wchar_t **v26; // rax
  _QWORD *v27; // rcx
  const wchar_t *v28; // rsi
  __int64 v29; // r15
  char v30; // r12
  int v31; // edx
  int v32; // eax
  const wchar_t *v33; // rdx
  __int64 v34; // r8
  wchar_t **v35; // rcx
  wchar_t **v36; // rcx
  OLECHAR *v38; // rax
  OLECHAR **v39; // r15
  unsigned int v40; // r14d
  unsigned int v41; // r14d
  unsigned int v42; // r14d
  const wchar_t *v43; // rcx
  const wchar_t *v44; // rax
  wchar_t *v45; // [rsp+20h] [rbp-B9h]
  wchar_t *v46; // [rsp+20h] [rbp-B9h]
  char *v47; // [rsp+38h] [rbp-A1h]
  unsigned int *v48; // [rsp+40h] [rbp-99h]
  int **v49; // [rsp+58h] [rbp-81h]
  OLECHAR *v51; // [rsp+68h] [rbp-71h] BYREF
  wchar_t v52; // [rsp+70h] [rbp-69h] BYREF
  unsigned int v53[2]; // [rsp+78h] [rbp-61h] BYREF
  void *lpMem; // [rsp+80h] [rbp-59h] BYREF
  wchar_t **v55; // [rsp+88h] [rbp-51h]
  wchar_t *v56; // [rsp+90h] [rbp-49h]
  _QWORD *v57; // [rsp+98h] [rbp-41h]
  OLECHAR **v58; // [rsp+A0h] [rbp-39h]
  unsigned int *v59; // [rsp+A8h] [rbp-31h]
  LPWSTR StringSid; // [rsp+B0h] [rbp-29h] BYREF
  char v61[4]; // [rsp+B8h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp-19h] BYREF
  wchar_t **v63; // [rsp+C8h] [rbp-11h] BYREF
  wchar_t **v64; // [rsp+D0h] [rbp-9h] BYREF

  v11 = a6;
  v56 = a6;
  v12 = (const wchar_t **)a7;
  v55 = a7;
  v58 = a8;
  v59 = a9;
  StringSid = 0;
  lpMem = 0;
  v13 = 0;
  v53[0] = 0;
  v14 = 0;
  v57 = 0;
  *(_DWORD *)v61 = 0;
  v15 = 0;
  v51 = 0;
  v63 = 0;
  v16 = 0;
  pv = 0;
  v17 = 0;
  v64 = 0;
  *a8 = 0;
  *a9 = 0;
  if ( Sid )
  {
    if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    {
      LastError = GetLastError();
      AppxPackageApplicability = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        AppxPackageApplicability = LastError;
      if ( AppxPackageApplicability >= 0 )
        AppxPackageApplicability = -2147418113;
      goto LABEL_103;
    }
    v16 = pv;
    v17 = v64;
    v11 = v56;
  }
  if ( *(_QWORD *)(a2 + 48) )
  {
    if ( v11 )
    {
      AppxPackageApplicability = StringArrayFromDelimitedString(v11, 0x3Bu, (wchar_t ***)&lpMem, v53);
      if ( AppxPackageApplicability < 0 )
        goto LABEL_76;
      v13 = v53[0];
      if ( v53[0] )
      {
        v21 = v53[0];
        v14 = SafeSusAllocArray(v53[0], 8u);
        v57 = v14;
        AppxPackageApplicability = v14 == 0 ? 0x8007000E : 0;
        if ( !v14 )
          goto LABEL_76;
        if ( v13 )
        {
          v22 = v14;
          v23 = (char *)((_BYTE *)lpMem - (_BYTE *)v14);
          do
          {
            *v22 = *(_QWORD *)((char *)v22 + (_QWORD)v23);
            ++v22;
            --v21;
          }
          while ( v21 );
        }
      }
      v12 = (const wchar_t **)v55;
    }
    WUTrace(
      0,
      0,
      4096,
      5,
      0,
      L"Calling GetApplicability5(package: %ws; flags: %lu; cIntentPFNs: %lu, userSid: %ws)",
      *(_QWORD *)(a2 + 8),
      a3,
      v13,
      StringSid);
    v24 = 0;
    if ( v64 )
    {
      CoTaskMemFree(v64);
      v64 = 0;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    if ( v63 )
    {
      CoTaskMemFree(v63);
      v63 = 0;
    }
    LODWORD(v46) = v13;
    AppxPackageApplicability = WUSystemInterfaceHelper::GetAppxPackageApplicability(
                                 (WUSystemInterfaceHelper *)a3,
                                 (unsigned int)StringSid,
                                 *(const wchar_t **)(a2 + 8),
                                 *(const wchar_t **)(a2 + 48),
                                 v46,
                                 (unsigned int)v14,
                                 v12,
                                 v61,
                                 (unsigned int *)&v63,
                                 (wchar_t ***)&pv,
                                 &v64,
                                 v49);
    if ( AppxPackageApplicability < 0 )
    {
      if ( AppxPackageApplicability == -2147024769 )
        AppxPackageApplicability = -2145116130;
      LODWORD(v48) = v13;
      LODWORD(v47) = a3;
      WUTrace(
        0,
        0,
        4096,
        3,
        AppxPackageApplicability,
        L"GetApplicability5(package: %ws; flags: %lu; cIntentPFNs: %lu)",
        *(_QWORD *)(a2 + 8),
        v47,
        v48);
      goto LABEL_103;
    }
    v25 = *(_DWORD *)v61;
    if ( !*(_DWORD *)v61 || (v26 = v63) == 0 || (v27 = pv) == 0 || !v64 )
    {
      WUTrace(0, 0, 4096, 1, 0, L"GetApplicability5 returned no AppxApplicabilityInfo data!");
      goto LABEL_87;
    }
    if ( *(_DWORD *)a2 == 3 && !*(_QWORD *)(a2 + 8) )
    {
      v24 = ApplicabilityStateFromString(*v63);
LABEL_87:
      v30 = a4;
      goto LABEL_88;
    }
    if ( *(_DWORD *)v61 != 1 )
    {
      while ( 1 )
      {
        LODWORD(v48) = v25;
        LODWORD(v47) = v24;
        WUTrace(
          0,
          0,
          4096,
          5,
          0,
          L"GetApplicability for package \"%ws\" (%lu/%lu) returned \"%ws\"",
          v27[v24],
          v47,
          v48,
          v26[v24]);
        v32 = ApplicabilityStateFromString(v63[v24]) - 1;
        if ( !v32 || v32 == 2 )
        {
          if ( SysStringLen(v15) )
          {
            v52 = 59;
            AppxPackageApplicability = CSusBSTR::Append((CSusBSTR *)&v51, &v52, 1u);
            if ( AppxPackageApplicability < 0 )
              goto LABEL_75;
          }
          v33 = (const wchar_t *)*((_QWORD *)pv + v24);
          if ( v33 )
          {
            v34 = -1;
            do
              ++v34;
            while ( v33[v34] );
          }
          else
          {
            LODWORD(v34) = 0;
          }
          AppxPackageApplicability = CSusBSTR::Append((CSusBSTR *)&v51, v33, v34);
          if ( AppxPackageApplicability < 0 )
          {
LABEL_75:
            v15 = v51;
            goto LABEL_76;
          }
          v15 = v51;
        }
        ++v24;
        v25 = *(_DWORD *)v61;
        if ( v24 >= *(_DWORD *)v61 )
        {
          v24 = 2 - (SysStringLen(v15) != 0);
          goto LABEL_87;
        }
        v26 = v63;
        v27 = pv;
      }
    }
    v24 = ApplicabilityStateFromString(*v63);
    v28 = *(const wchar_t **)pv;
    if ( *(_QWORD *)pv )
    {
      SysFreeString(0);
      v51 = 0;
      v29 = -1;
      do
        ++v29;
      while ( v28[v29] );
      AppxPackageApplicability = CSusBSTR::Append((CSusBSTR *)&v51, v28, v29);
      v15 = v51;
      if ( AppxPackageApplicability < 0 )
        goto LABEL_76;
    }
    else
    {
      AppxPackageApplicability = 0;
    }
    v30 = a4;
    if ( !a4 )
      goto LABEL_88;
    v31 = *(_DWORD *)v64;
    if ( v24 == 1 )
    {
      if ( !v31 )
      {
        WUTrace(
          0,
          0,
          4096,
          3,
          0,
          L"CoServicing: Non-required installable package (%ws) found! Marking as NotInstallable.",
          *(_QWORD *)(a2 + 8));
        goto LABEL_60;
      }
    }
    else if ( v24 == 2 && v31 )
    {
      WUTrace(
        0,
        0,
        4096,
        3,
        0,
        L"CoServicing: Required package (%ws) is already installed! Marking as NotInstallable.",
        *(_QWORD *)(a2 + 8));
LABEL_60:
      v24 = 0;
    }
LABEL_88:
    v38 = v15;
    v15 = 0;
    v39 = v58;
    *v58 = v38;
    *v59 = v24;
    if ( v24 )
    {
      v40 = v24 - 1;
      if ( v40 )
      {
        v41 = v40 - 1;
        if ( v41 )
        {
          v42 = v41 - 1;
          if ( v42 )
          {
            if ( v42 == 1 )
              v43 = L"Offline";
            else
              v43 = L"Unknown";
          }
          else
          {
            v43 = L"RequiresReinstall";
          }
        }
        else
        {
          v43 = L"Installed";
        }
      }
      else
      {
        v43 = L"Installable";
      }
    }
    else
    {
      v43 = L"NotInstallable";
    }
    v44 = L"False";
    if ( v30 )
      v44 = L"True";
    WUTrace(
      0,
      0,
      4096,
      5,
      0,
      L"GetApplicability for package '%ws' (CoServiced: %ws; Intent: %ws) = '%ws'",
      *(_QWORD *)(a2 + 8),
      v44,
      v56,
      v43);
    if ( *v39 )
      WUTrace(0, 0, 4096, 5, 0, L"GetApplicability evaluation data = '%ws'", *v39);
    goto LABEL_103;
  }
  if ( v17 )
  {
    CoTaskMemFree(v17);
    v64 = 0;
    v16 = pv;
  }
  if ( v16 )
  {
    CoTaskMemFree(v16);
    pv = 0;
  }
  if ( v63 )
  {
    CoTaskMemFree(v63);
    v63 = 0;
  }
  LODWORD(v45) = 0;
  v20 = WUSystemInterfaceHelper::GetAppxPackageApplicability(
          0,
          (unsigned int)StringSid,
          *(const wchar_t **)(a2 + 8),
          0,
          v45,
          0,
          (const wchar_t **)a7,
          v61,
          (unsigned int *)&v63,
          (wchar_t ***)&pv,
          &v64,
          v49);
  AppxPackageApplicability = v20;
  if ( v20 >= 0 )
  {
    if ( *(_DWORD *)v61 != 1 )
    {
      AppxPackageApplicability = -2145120257;
      goto LABEL_76;
    }
    *a9 = ApplicabilityStateFromString(*v63);
  }
  else if ( v20 == -2147024769 )
  {
    AppxPackageApplicability = -2145116130;
  }
LABEL_103:
  if ( AppxPackageApplicability < 0 )
LABEL_76:
    WUTrace("CPackageManagerWrapper::GetApplicability", 614, 4096, 3, AppxPackageApplicability, L"Method failed");
  SusFreePtrArray(lpMem, v53[0]);
  LocalFree(StringSid);
  v35 = v63;
  v63 = 0;
  CoFreeStringArray(v35, *(unsigned int *)v61);
  v36 = (wchar_t **)pv;
  pv = 0;
  CoFreeStringArray(v36, *(unsigned int *)v61);
  if ( v64 )
  {
    CoTaskMemFree(v64);
    v64 = 0;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v63 )
  {
    CoTaskMemFree(v63);
    v63 = 0;
  }
  SysFreeString(v15);
  if ( v14 )
    SusFree(v14);
  return (unsigned int)AppxPackageApplicability;
}

```

## disassembly

```asm
0x180218d20  mov     [rsp-8+arg_0], rbx
0x180218d25  push    rbp
0x180218d26  push    rsi
0x180218d27  push    rdi
0x180218d28  push    r12
0x180218d2a  push    r13
0x180218d2c  push    r14
0x180218d2e  push    r15
0x180218d30  lea     rbp, [rsp-7]
0x180218d35  sub     rsp, 0E0h
0x180218d3c  mov     rax, cs:__security_cookie
0x180218d43  xor     rax, rsp
0x180218d46  mov     [rbp+37h+var_38], rax
0x180218d4a  mov     [rbp+37h+var_B0], r9b
0x180218d4e  mov     r12d, r8d
0x180218d51  mov     r13, rdx
0x180218d54  mov     r8, [rbp+37h+Sid]
0x180218d58  mov     r10, [rbp+37h+arg_28]
0x180218d5c  mov     [rbp+37h+var_80], r10
0x180218d60  mov     rsi, [rbp+37h+arg_30]
0x180218d64  mov     [rbp+37h+var_88], rsi
0x180218d68  mov     rdx, [rbp+37h+arg_38]
0x180218d6c  mov     [rbp+37h+var_70], rdx
0x180218d70  mov     r14, [rbp+37h+arg_40]
0x180218d77  mov     [rbp+37h+var_68], r14
0x180218d7b  xor     r9d, r9d
0x180218d7e  mov     [rbp+37h+StringSid], r9
0x180218d82  mov     [rbp+37h+lpMem], r9
0x180218d86  mov     r15d, r9d
0x180218d89  mov     [rbp+37h+var_98], r9d
0x180218d8d  mov     edi, r9d
0x180218d90  mov     [rbp+37h+var_78], r9
0x180218d94  mov     dword ptr [rbp+37h+var_58], r9d
0x180218d98  mov     ebx, r9d
0x180218d9b  mov     [rbp+37h+var_A8], rbx
0x180218d9f  mov     [rbp+37h+var_48], r9
0x180218da3  mov     ecx, r9d
0x180218da6  mov     [rbp+37h+pv], rcx
0x180218daa  mov     eax, r9d
0x180218dad  mov     [rbp+37h+var_40], rax
0x180218db1  mov     [rdx], r9
0x180218db4  mov     [r14], r9d
0x180218db7  test    r8, r8
0x180218dba  jz      short loc_180218E02
0x180218dbc  lea     rdx, [rbp+37h+StringSid]; StringSid
0x180218dc0  mov     rcx, r8; Sid
0x180218dc3  call    cs:__imp_ConvertSidToStringSidW
0x180218dc9  xor     r9d, r9d
0x180218dcc  test    eax, eax
0x180218dce  jnz     short loc_180218DF6
0x180218dd0  call    cs:__imp_GetLastError
0x180218dd6  movzx   esi, ax
0x180218dd9  or      esi, 80070000h
0x180218ddf  xor     r15d, r15d
0x180218de2  test    eax, eax
0x180218de4  cmovle  esi, eax
0x180218de7  mov     eax, 8000FFFFh
0x180218dec  test    esi, esi
0x180218dee  cmovns  esi, eax
0x180218df1  jmp     loc_180219492
0x180218df6  mov     rcx, [rbp+37h+pv]
0x180218dfa  mov     rax, [rbp+37h+var_40]
0x180218dfe  mov     r10, [rbp+37h+var_80]
0x180218e02  cmp     [r13+30h], r9
0x180218e06  jnz     loc_180218ECB
0x180218e0c  xor     r15d, r15d
0x180218e0f  test    rax, rax
0x180218e12  jz      short loc_180218E25
0x180218e14  mov     rcx, rax; pv
0x180218e17  call    cs:__imp_CoTaskMemFree
0x180218e1d  mov     [rbp+37h+var_40], r15
0x180218e21  mov     rcx, [rbp+37h+pv]; pv
0x180218e25  test    rcx, rcx
0x180218e28  jz      short loc_180218E34
0x180218e2a  call    cs:__imp_CoTaskMemFree
0x180218e30  mov     [rbp+37h+pv], r15
0x180218e34  mov     rcx, [rbp+37h+var_48]; pv
0x180218e38  test    rcx, rcx
0x180218e3b  jz      short loc_180218E47
0x180218e3d  call    cs:__imp_CoTaskMemFree
0x180218e43  mov     [rbp+37h+var_48], r15
0x180218e47  lea     rax, [rbp+37h+var_40]
0x180218e4b  mov     [rsp+110h+var_C0], rax; wchar_t ***
0x180218e50  lea     rax, [rbp+37h+pv]
0x180218e54  mov     [rsp+110h+var_C8], rax; wchar_t ***
0x180218e59  lea     rax, [rbp+37h+var_48]
0x180218e5d  mov     [rsp+110h+var_D0], rax; unsigned int *
0x180218e62  lea     rax, [rbp+37h+var_58]
0x180218e66  mov     [rsp+110h+var_D8], rax; char *
0x180218e6b  mov     [rsp+110h+var_E0], rsi; wchar_t **
0x180218e70  mov     qword ptr [rsp+110h+var_E8], r15; unsigned int
0x180218e75  mov     dword ptr [rsp+110h+var_F0], r15d; wchar_t *
0x180218e7a  xor     r9d, r9d; wchar_t *
0x180218e7d  mov     r8, [r13+8]; wchar_t *
0x180218e81  mov     rdx, [rbp+37h+StringSid]; unsigned int
0x180218e85  xor     ecx, ecx; this
0x180218e87  call    ?GetAppxPackageApplicability@WUSystemInterfaceHelper@@YAJKPEB_W00KPEAPEB_WPEBDPEAKPEAPEAPEA_W4PEAPEAH@Z; WUSystemInterfaceHelper::GetAppxPackageApplicability(ulong,wchar_t const *,wchar_t const *,wchar_t const *,ulong,wchar_t const * *,char const *,ulong *,wchar_t * * *,wchar_t * * *,int * *)
0x180218e8c  mov     esi, eax
0x180218e8e  test    eax, eax
0x180218e90  jns     short loc_180218EA7
0x180218e92  cmp     eax, 8007007Fh
0x180218e97  jnz     loc_180219492
0x180218e9d  mov     esi, 8024201Eh
0x180218ea2  jmp     loc_180219492
0x180218ea7  cmp     dword ptr [rbp+37h+var_58], 1
0x180218eab  jz      short loc_180218EB7
0x180218ead  mov     esi, 80240FFFh
0x180218eb2  jmp     loc_180219298
0x180218eb7  mov     rcx, [rbp+37h+var_48]
0x180218ebb  mov     rcx, [rcx]
0x180218ebe  call    ?ApplicabilityStateFromString@@YA?BW4ApplicabilityState@@PEB_W@Z; ApplicabilityStateFromString(wchar_t const *)
0x180218ec3  mov     [r14], eax
0x180218ec6  jmp     loc_180219492
0x180218ecb  mov     eax, 3Bh ; ';'
0x180218ed0  test    r10, r10
0x180218ed3  jz      short loc_180218F53
0x180218ed5  mov     edx, eax; wchar_t
0x180218ed7  lea     r9, [rbp+37h+var_98]; unsigned int *
0x180218edb  lea     r8, [rbp+37h+lpMem]; wchar_t ***
0x180218edf  mov     rcx, r10; wchar_t *
0x180218ee2  call    ?StringArrayFromDelimitedString@@YAJPEB_W_WPEAPEAPEA_WPEAK@Z; StringArrayFromDelimitedString(wchar_t const *,wchar_t,wchar_t * * *,ulong *)
0x180218ee7  mov     esi, eax
0x180218ee9  xor     r15d, r15d
0x180218eec  test    eax, eax
0x180218eee  js      loc_180219298
0x180218ef4  mov     r15d, [rbp+37h+var_98]
0x180218ef8  xor     r9d, r9d
0x180218efb  test    r15d, r15d
0x180218efe  jz      short loc_180218F4F
0x180218f00  mov     r14d, r15d
0x180218f03  lea     edx, [r9+8]; unsigned __int64
0x180218f07  mov     ecx, r15d; unsigned __int64
0x180218f0a  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180218f0f  mov     rdi, rax
0x180218f12  mov     [rbp+37h+var_78], rax
0x180218f16  neg     rax
0x180218f19  sbb     esi, esi
0x180218f1b  not     esi
0x180218f1d  and     esi, 8007000Eh
0x180218f23  xor     r9d, r9d
0x180218f26  test    rdi, rdi
0x180218f29  jz      loc_180219295
0x180218f2f  test    r15d, r15d
0x180218f32  jz      short loc_180218F4F
0x180218f34  mov     rcx, rdi
0x180218f37  mov     rdx, [rbp+37h+lpMem]
0x180218f3b  sub     rdx, rdi
0x180218f3e  mov     rax, [rdx+rcx]
0x180218f42  mov     [rcx], rax
0x180218f45  lea     rcx, [rcx+8]
0x180218f49  sub     r14, 1
0x180218f4d  jnz     short loc_180218F3E
0x180218f4f  mov     rsi, [rbp+37h+var_88]
0x180218f53  mov     rax, [rbp+37h+StringSid]
0x180218f57  mov     [rsp+110h+var_C8], rax
0x180218f5c  mov     dword ptr [rsp+110h+var_D0], r15d
0x180218f61  mov     dword ptr [rsp+110h+var_D8], r12d
0x180218f66  mov     rax, [r13+8]
0x180218f6a  mov     [rsp+110h+var_E0], rax
0x180218f6f  lea     rax, aCallingGetappl; "Calling GetApplicability5(package: %ws;"...
0x180218f76  mov     qword ptr [rsp+110h+var_E8], rax
0x180218f7b  mov     [rsp+110h+var_F0], r9
0x180218f80  xor     edx, edx
0x180218f82  xor     ecx, ecx
0x180218f84  lea     r9d, [rdx+5]
0x180218f88  mov     r8d, 1000h
0x180218f8e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180218f93  mov     rcx, [rbp+37h+var_40]; pv
0x180218f97  xor     r14d, r14d
0x180218f9a  test    rcx, rcx
0x180218f9d  jz      short loc_180218FA9
0x180218f9f  call    cs:__imp_CoTaskMemFree
0x180218fa5  mov     [rbp+37h+var_40], r14
0x180218fa9  mov     rcx, [rbp+37h+pv]; pv
0x180218fad  test    rcx, rcx
0x180218fb0  jz      short loc_180218FBC
0x180218fb2  call    cs:__imp_CoTaskMemFree
0x180218fb8  mov     [rbp+37h+pv], r14
0x180218fbc  mov     rcx, [rbp+37h+var_48]; pv
0x180218fc0  test    rcx, rcx
0x180218fc3  jz      short loc_180218FCF
0x180218fc5  call    cs:__imp_CoTaskMemFree
0x180218fcb  mov     [rbp+37h+var_48], r14
0x180218fcf  lea     rax, [rbp+37h+var_40]
0x180218fd3  mov     [rsp+110h+var_C0], rax; wchar_t ***
0x180218fd8  lea     rax, [rbp+37h+pv]
0x180218fdc  mov     [rsp+110h+var_C8], rax; wchar_t ***
0x180218fe1  lea     rax, [rbp+37h+var_48]
0x180218fe5  mov     [rsp+110h+var_D0], rax; unsigned int *
0x180218fea  lea     rax, [rbp+37h+var_58]
0x180218fee  mov     [rsp+110h+var_D8], rax; char *
0x180218ff3  mov     [rsp+110h+var_E0], rsi; wchar_t **
0x180218ff8  mov     qword ptr [rsp+110h+var_E8], rdi; unsigned int
0x180218ffd  mov     dword ptr [rsp+110h+var_F0], r15d; wchar_t *
0x180219002  mov     r9, [r13+30h]; wchar_t *
0x180219006  mov     r8, [r13+8]; wchar_t *
0x18021900a  mov     rdx, [rbp+37h+StringSid]; unsigned int
0x18021900e  mov     ecx, r12d; this
0x180219011  call    ?GetAppxPackageApplicability@WUSystemInterfaceHelper@@YAJKPEB_W00KPEAPEB_WPEBDPEAKPEAPEAPEA_W4PEAPEAH@Z; WUSystemInterfaceHelper::GetAppxPackageApplicability(ulong,wchar_t const *,wchar_t const *,wchar_t const *,ulong,wchar_t const * *,char const *,ulong *,wchar_t * * *,wchar_t * * *,int * *)
0x180219016  mov     esi, eax
0x180219018  test    eax, eax
0x18021901a  jns     short loc_180219068
0x18021901c  mov     eax, 8024201Eh
0x180219021  cmp     esi, 8007007Fh
0x180219027  cmovz   esi, eax
0x18021902a  mov     dword ptr [rsp+110h+var_D0], r15d
0x18021902f  mov     dword ptr [rsp+110h+var_D8], r12d
0x180219034  mov     rax, [r13+8]
0x180219038  mov     [rsp+110h+var_E0], rax
0x18021903d  lea     rax, aGetapplicabili_1; "GetApplicability5(package: %ws; flags: "...
0x180219044  mov     qword ptr [rsp+110h+var_E8], rax
0x180219049  mov     dword ptr [rsp+110h+var_F0], esi
0x18021904d  xor     edx, edx
0x18021904f  xor     ecx, ecx
0x180219051  lea     r9d, [rdx+3]
0x180219055  mov     r8d, 1000h
0x18021905b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180219060  xor     r15d, r15d
0x180219063  jmp     loc_180219492
0x180219068  mov     r8d, dword ptr [rbp+37h+var_58]
0x18021906c  xor     r15d, r15d
0x18021906f  test    r8d, r8d
0x180219072  jz      loc_180219375
0x180219078  mov     rax, [rbp+37h+var_48]
0x18021907c  test    rax, rax
0x18021907f  jz      loc_180219375
0x180219085  mov     rcx, [rbp+37h+pv]
0x180219089  test    rcx, rcx
0x18021908c  jz      loc_180219375
0x180219092  cmp     [rbp+37h+var_40], r15
0x180219096  jz      loc_180219375
0x18021909c  cmp     dword ptr [r13+0], 3
0x1802190a1  jnz     short loc_1802190B9
0x1802190a3  cmp     [r13+8], r15
0x1802190a7  jnz     short loc_1802190B9
0x1802190a9  mov     rcx, [rax]
0x1802190ac  call    ?ApplicabilityStateFromString@@YA?BW4ApplicabilityState@@PEB_W@Z; ApplicabilityStateFromString(wchar_t const *)
0x1802190b1  mov     r14d, eax
0x1802190b4  jmp     loc_180219399
0x1802190b9  cmp     r8d, 1
0x1802190bd  jnz     loc_180219196
0x1802190c3  mov     rcx, [rax]
0x1802190c6  call    ?ApplicabilityStateFromString@@YA?BW4ApplicabilityState@@PEB_W@Z; ApplicabilityStateFromString(wchar_t const *)
0x1802190cb  mov     r14d, eax
0x1802190ce  mov     rax, [rbp+37h+pv]
0x1802190d2  mov     rsi, [rax]
0x1802190d5  test    rsi, rsi
0x1802190d8  jnz     short loc_1802190DF
0x1802190da  mov     esi, r15d
0x1802190dd  jmp     short loc_18021911B
0x1802190df  xor     ecx, ecx; bstrString
0x1802190e1  call    cs:__imp_SysFreeString
0x1802190e7  mov     [rbp+37h+var_A8], r15
0x1802190eb  or      r15, 0FFFFFFFFFFFFFFFFh
0x1802190ef  xor     eax, eax
0x1802190f1  inc     r15
0x1802190f4  cmp     [rsi+r15*2], ax
0x1802190f9  jnz     short loc_1802190F1
0x1802190fb  mov     r8d, r15d; unsigned int
0x1802190fe  mov     rdx, rsi; wchar_t *
0x180219101  lea     rcx, [rbp+37h+var_A8]; this
0x180219105  call    ?Append@CSusBSTR@@QEAAJPEB_WK@Z; CSusBSTR::Append(wchar_t const *,ulong)
0x18021910a  mov     esi, eax
0x18021910c  xor     r15d, r15d
0x18021910f  mov     rbx, [rbp+37h+var_A8]
0x180219113  test    eax, eax
0x180219115  js      loc_180219298
0x18021911b  mov     r12b, [rbp+37h+var_B0]
0x18021911f  test    r12b, r12b
0x180219122  jz      loc_18021939D
0x180219128  mov     rax, [rbp+37h+var_40]
0x18021912c  mov     edx, [rax]
0x18021912e  mov     ecx, r14d
0x180219131  sub     ecx, 1
0x180219134  jz      short loc_180219159
0x180219136  cmp     ecx, 1
0x180219139  jnz     loc_18021939D
0x18021913f  test    edx, edx
0x180219141  jz      loc_18021939D
0x180219147  mov     rax, [r13+8]
0x18021914b  mov     [rsp+110h+var_E0], rax
0x180219150  lea     rax, aCoservicingReq; "CoServicing: Required package (%ws) is "...
0x180219157  jmp     short loc_180219171
0x180219159  test    edx, edx
0x18021915b  jnz     loc_18021939D
0x180219161  mov     rax, [r13+8]
0x180219165  mov     [rsp+110h+var_E0], rax
0x18021916a  lea     rax, aCoservicingNon; "CoServicing: Non-required installable p"...
0x180219171  mov     qword ptr [rsp+110h+var_E8], rax
0x180219176  mov     [rsp+110h+var_F0], r15
0x18021917b  xor     edx, edx
0x18021917d  xor     ecx, ecx
0x18021917f  lea     r9d, [rdx+3]
0x180219183  mov     r8d, 1000h
0x180219189  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18021918e  mov     r14d, r15d
0x180219191  jmp     loc_18021939D
0x180219196  test    r8d, r8d
0x180219199  jz      loc_18021927A
0x18021919f  or      r15, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
