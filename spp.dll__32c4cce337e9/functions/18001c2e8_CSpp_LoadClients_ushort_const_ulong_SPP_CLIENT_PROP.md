# CSpp::_LoadClients(ushort const *,ulong *,_SPP_CLIENT_PROP * *)

- ea: `0x18001c2e8`
- end: `0x18001c938`
- name: `?_LoadClients@CSpp@@AEAAJPEBGPEAKPEAPEAU_SPP_CLIENT_PROP@@@Z`
- size: `1616`
- prototype: `__int64 __fastcall(CSpp *this, const unsigned __int16 *, unsigned int *, struct _SPP_CLIENT_PROP **)`
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800083e0`
- `0x180017dfc`
- `0x18001ac40`

## callees

- `0x180003850`
- `0x18000702c`
- `0x18000dd80`
- `0x18000f8ac`
- `0x18001be74`
- `0x18001c2e8`
- `0x180020710`
- `0x1800217d8`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002b6ec`
- `0x18002b8cc`
- `0x18002d408`
- `0x1800346c0`
- `0x180034ed4`
- `0x180034fe4`
- `0x180035390`
- `0x180035b00`
- `0x180035b76`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001c8c5`
- `KERNEL32!CloseHandle` at `0x18001c8c5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001c725`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001c725`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c67f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c8af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c67f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c8af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c5ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c687`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c5ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c687`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c558`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c874`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c902`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c558`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c874`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c902`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001c654`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001c654`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c581`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c581`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18001c4b0`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18001c4b0`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18001c469`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18001c891`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18001c469`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18001c891`

## string_xrefs

- `0x18001c47b`: `System32\Config`
- `0x18001c457`: `SPP-Temp`
- `0x18001c49e`: `SPP-Temp`
- `0x18001c4ec`: `SPP-Temp`
- `0x18001c883`: `SPP-Temp`

## pseudocode

```c
__int64 __fastcall CSpp::_LoadClients(
        CSpp *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        struct _SPP_CLIENT_PROP **a4)
{
  char *v7; // rbx
  __int64 v8; // rsi
  BYTE *v9; // r12
  __int16 v10; // ax
  int v11; // eax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // r9d
  bool v14; // sf
  int v15; // edi
  int KeyW; // eax
  DWORD v17; // r13d
  int v18; // eax
  DWORD v19; // edx
  unsigned int v20; // edi
  signed int v21; // r10d
  unsigned int v22; // edi
  DWORD v23; // edx
  HRESULT v24; // eax
  int v25; // eax
  struct _SPP_CLIENT_PROP *v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // edi
  __int64 v29; // r8
  char *v30; // rdx
  const unsigned __int16 *lpType; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *lpTypea; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *lpData; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *lpDataa; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *lpcbData; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *lpcbDataa; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v38; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v39; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v40; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v41; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v42; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v43; // [rsp+50h] [rbp-B0h]
  int v44; // [rsp+60h] [rbp-A0h]
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  int v48; // [rsp+80h] [rbp-80h] BYREF
  __int16 v49; // [rsp+84h] [rbp-7Ch]
  __int16 v50; // [rsp+86h] [rbp-7Ah]
  DWORD cchValueName; // [rsp+B8h] [rbp-48h] BYREF
  DWORD Type; // [rsp+BCh] [rbp-44h] BYREF
  LPWSTR lpValueName; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v54[2]; // [rsp+C8h] [rbp-38h]
  struct _GUID v55; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+E0h] [rbp-20h] BYREF
  LPCWSTR lpFile[2]; // [rsp+F0h] [rbp-10h] BYREF
  CSpp *v58; // [rsp+100h] [rbp+0h]
  GUID pclsid; // [rsp+110h] [rbp+10h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+120h] [rbp+20h] BYREF
  int v61; // [rsp+130h] [rbp+30h] BYREF
  __int128 v62; // [rsp+134h] [rbp+34h]
  _BYTE v63[28]; // [rsp+144h] [rbp+44h] BYREF

  v58 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, a3, a4, a3);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v48, "CSpp::_LoadClients", 3312, 1);
  hKey = 0;
  lpSubKey[0] = &FileName;
  v7 = 0;
  lpSubKey[1] = 0;
  v8 = 0;
  lpFile[0] = &FileName;
  v9 = 0;
  lpFile[1] = 0;
  v61 = 0;
  *(_QWORD *)&v55.Data1 = 0;
  lpValueName = (LPWSTR)&FileName;
  *(_QWORD *)v54 = 0;
  Type = 0;
  cbData = 0;
  cchValueName = 0;
  hObject = 0;
  v44 = 0;
  memset(v63, 0, sizeof(v63));
  v62 = 0;
  pclsid = GUID_NULL;
  NewState = 0;
  if ( a4 )
    *a4 = 0;
  if ( a3 )
    *a3 = 0;
  v10 = 3338;
  if ( !a4 || (v49 = 3338, v10 = 3339, !a3) )
  {
    v48 = -2147024809;
    goto LABEL_59;
  }
  v48 = 0;
  v49 = 3339;
  if ( a2 )
  {
    v11 = SxOpenThreadOrProcessToken((unsigned int)&FileName, &hObject);
    v7 = (char *)hObject;
    v14 = v11 < 0;
    v48 = v11;
    v10 = 3347;
    if ( v14 )
      goto LABEL_12;
    v49 = 3347;
    v48 = AssertPrivilegeOnTokenPreserveOrig(hObject, v12, &NewState, v13);
    v10 = 3351;
    if ( v48 < 0 )
      goto LABEL_12;
    v49 = 3351;
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"SPP-Temp");
    v48 = CBsString::SetPath(
            (CBsString *)lpFile,
            a2,
            L"System32\\Config",
            L"SOFTWARE",
            0,
            lpType,
            lpData,
            lpcbData,
            v38,
            v40,
            v42);
    v10 = 3354;
    if ( v48 < 0 )
      goto LABEL_12;
    v49 = 3354;
    KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"SPP-Temp", lpFile[0]);
    if ( KeyW > 0 )
      KeyW = (unsigned __int16)KeyW | 0x80070000;
    v48 = KeyW;
    v14 = KeyW < 0;
    v10 = 3355;
    if ( v14 )
    {
LABEL_12:
      v15 = 0;
      goto LABEL_60;
    }
    v49 = 3355;
    v44 = 1;
    v48 = CBsString::SetPath(
            (CBsString *)lpSubKey,
            L"SPP-Temp",
            L"Microsoft\\Windows NT\\CurrentVersion\\SPP",
            L"Clients",
            0,
            lpTypea,
            lpDataa,
            lpcbDataa,
            v39,
            v41,
            v43);
    v10 = 3357;
    if ( v48 < 0 )
    {
LABEL_19:
      v15 = v44;
      goto LABEL_60;
    }
    goto LABEL_21;
  }
  v48 = CBsString::SetPath(
          (CBsString *)lpSubKey,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SPP",
          L"Clients",
          0,
          0,
          lpType,
          lpData,
          lpcbData,
          v38,
          v40,
          v42);
  v10 = 3361;
  if ( v48 < 0 )
  {
LABEL_59:
    v15 = 0;
    goto LABEL_60;
  }
LABEL_21:
  v49 = v10;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey) )
  {
    v48 = 1;
    v49 = 3367;
LABEL_25:
    v15 = v44;
    goto LABEL_61;
  }
  v17 = 1024;
  v9 = (BYTE *)CoTaskMemAlloc(0x400u);
  if ( !v9 )
  {
    v15 = v44;
    v48 = -2147024882;
    v50 = 3372;
    goto LABEL_61;
  }
  v49 = 3372;
  v48 = 0;
  v48 = CBsString::ExtendBuffer((CBsString *)&lpValueName, 0x4000u);
  v10 = 3374;
  if ( v48 < 0 )
    goto LABEL_28;
  v49 = 3374;
  v18 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::CreateInstance(&v55);
  v8 = *(_QWORD *)&v55.Data1;
  v14 = v18 < 0;
  v48 = v18;
  v10 = 3376;
  if ( v14 )
    goto LABEL_28;
  v19 = 0;
  v49 = 3376;
  LODWORD(hObject) = 0;
  while ( 1 )
  {
    v20 = v54[1];
    cbData = v17;
    cchValueName = v54[1] + 1;
    RegEnumValueW(hKey, v19, lpValueName, &cchValueName, 0, &Type, v9, &cbData);
    CBsString::BoundUpdateLength((CBsString *)&lpValueName, v20);
    if ( v21 == 234 )
    {
      v22 = SxScaledGrowth(cbData);
      CoTaskMemFree(v9);
      v9 = (BYTE *)CoTaskMemAlloc(v22);
      v10 = 3400;
      if ( !v9 )
      {
        v48 = -2147024882;
        goto LABEL_19;
      }
      v17 = v22;
      v48 = 0;
      goto LABEL_53;
    }
    if ( v21 == 259 )
    {
      v26 = *(struct _SPP_CLIENT_PROP **)(v8 + 8);
      v27 = *(_DWORD *)(v8 + 16);
      *(_QWORD *)(v8 + 8) = 0;
      *(_QWORD *)(v8 + 16) = 0;
      *a4 = v26;
      *a3 = v27;
      goto LABEL_25;
    }
    if ( v21 )
      break;
    v19 = (_DWORD)hObject + 1;
    LODWORD(hObject) = (_DWORD)hObject + 1;
    if ( Type == 7 )
    {
      if ( (cbData & 1) != 0
        || (v23 = cbData >> 1, cbData >> 1 < 3)
        || *(_WORD *)&v9[2 * v23 - 2]
        || *(_WORD *)&v9[2 * v23 - 4] )
      {
LABEL_54:
        v19 = (unsigned int)hObject;
      }
      else
      {
        CBsString::BoundUpdateLength((CBsString *)&lpValueName, v54[1]);
        v24 = CLSIDFromString(lpValueName, &pclsid);
        v19 = (unsigned int)hObject;
        if ( v24 >= 0 )
        {
          if ( !memcmp_0(&pclsid, &unk_18003BA18, 0x10u) )
          {
            v19 = (unsigned int)hObject;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
              v19 = (unsigned int)hObject;
            }
          }
          else
          {
            v15 = v44;
            v55 = pclsid;
            v25 = CSpp::_LoadClient(v58, v44, &v55, (struct _SPP_CLIENT_PROP *)&v61);
            v19 = (unsigned int)hObject;
            if ( v25 >= 0 )
            {
              v48 = CSxArrayBuilder<_SPP_CLIENT_PROP,&void Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *),&void SxDefaultInit<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *),&void SxDefaultTransfer<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *,_SPP_CLIENT_PROP *)>::Append(
                      v8,
                      &v61,
                      0);
              v10 = 3464;
              if ( v48 < 0 )
                goto LABEL_60;
LABEL_53:
              v49 = v10;
              goto LABEL_54;
            }
          }
        }
      }
    }
  }
  if ( v21 > 0 )
    v21 = (unsigned __int16)v21 | 0x80070000;
  v48 = v21;
  v10 = 3468;
LABEL_28:
  v15 = v44;
LABEL_60:
  v50 = v10;
LABEL_61:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v15 )
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"SPP-Temp");
  RestoreOrigPrivilegeOnToken(v7, &NewState);
  Free_SPP_CLIENT_PROP((struct _SPP_CLIENT_PROP *)&v61);
  CoTaskMemFree(v9);
  v28 = v48;
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  CBsString::_Release((CBsString *)&lpValueName);
  if ( v8 )
    CSxArrayBuilder<_SPP_CLIENT_PROP,&void Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *),&void SxDefaultInit<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *),&void SxDefaultTransfer<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *,_SPP_CLIENT_PROP *)>::Release((void *)v8);
  CBsString::_Release((CBsString *)lpFile);
  CBsString::_Release((CBsString *)lpSubKey);
  v30 = (char *)hKey - 1;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v48, (__int64)v30, v29);
  return v28;
}

```

## disassembly

```asm
0x18001c2e8  push    rbp
0x18001c2ea  push    rbx
0x18001c2eb  push    rsi
0x18001c2ec  push    rdi
0x18001c2ed  push    r12
0x18001c2ef  push    r13
0x18001c2f1  push    r14
0x18001c2f3  push    r15
0x18001c2f5  lea     rbp, [rsp-78h]
0x18001c2fa  sub     rsp, 178h
0x18001c301  mov     rax, cs:__security_cookie
0x18001c308  xor     rax, rsp
0x18001c30b  mov     [rbp+0B0h+var_50], rax
0x18001c30f  mov     r15, r9
0x18001c312  mov     [rbp+0B0h+var_B0], rcx
0x18001c316  mov     r14, r8
0x18001c319  mov     rdi, rdx
0x18001c31c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c323  lea     rax, WPP_GLOBAL_Control
0x18001c32a  cmp     rcx, rax
0x18001c32d  jz      short loc_18001C34B
0x18001c32f  test    dword ptr [rcx+1Ch], 20000000h
0x18001c336  jz      short loc_18001C34B
0x18001c338  mov     rcx, [rcx+10h]
0x18001c33c  mov     edx, 25h ; '%'
0x18001c341  mov     [rsp+1B0h+phkResult], r8
0x18001c346  call    WPP_SF_qq
0x18001c34b  mov     r9d, 1; unsigned __int16
0x18001c351  lea     rdx, aCsppLoadclient; "CSpp::_LoadClients"
0x18001c358  mov     r8d, 0CF0h; unsigned __int16
0x18001c35e  lea     rcx, [rbp+0B0h+var_130]; this
0x18001c362  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001c367  xor     r13d, r13d
0x18001c36a  lea     rcx, FileName; unsigned int
0x18001c371  mov     [rsp+1B0h+hKey], r13
0x18001c376  xorps   xmm0, xmm0
0x18001c379  mov     [rbp+0B0h+lpSubKey], rcx
0x18001c37d  mov     ebx, r13d
0x18001c380  mov     [rbp+0B0h+var_C8], r13
0x18001c384  mov     esi, r13d
0x18001c387  mov     [rbp+0B0h+lpFile], rcx
0x18001c38b  mov     r12d, r13d
0x18001c38e  mov     [rbp+0B0h+var_B8], r13
0x18001c392  mov     [rbp+0B0h+var_80], r13d
0x18001c396  mov     qword ptr [rbp+0B0h+var_E0.Data1], r13
0x18001c39a  mov     [rbp+0B0h+lpValueName], rcx
0x18001c39e  mov     qword ptr [rbp+0B0h+var_E8], r13
0x18001c3a2  mov     [rbp+0B0h+Type], r13d
0x18001c3a6  mov     [rsp+1B0h+cbData], r13d
0x18001c3ab  mov     [rbp+0B0h+cchValueName], r13d
0x18001c3af  mov     [rsp+1B0h+hObject], rbx
0x18001c3b4  mov     [rsp+1B0h+var_150], r13d
0x18001c3b9  movups  xmmword ptr [rbp+0B0h+var_6C], xmm0
0x18001c3bd  movups  xmmword ptr [rbp+0B0h+var_6C+0Ch], xmm0
0x18001c3c1  movups  [rbp+0B0h+var_7C], xmm0
0x18001c3c5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001c3cc  movdqu  xmmword ptr [rbp+0B0h+pclsid.Data1], xmm0
0x18001c3d1  xorps   xmm0, xmm0
0x18001c3d4  movups  xmmword ptr [rbp+0B0h+NewState.PrivilegeCount], xmm0
0x18001c3d8  test    r15, r15
0x18001c3db  jz      short loc_18001C3E0
0x18001c3dd  mov     [r15], r13
0x18001c3e0  test    r14, r14
0x18001c3e3  jz      short loc_18001C3E8
0x18001c3e5  mov     [r14], r13d
0x18001c3e8  mov     eax, 0D0Ah
0x18001c3ed  test    r15, r15
0x18001c3f0  jz      loc_18001C858
0x18001c3f6  mov     [rbp+0B0h+var_12C], ax
0x18001c3fa  mov     eax, 0D0Bh
0x18001c3ff  test    r14, r14
0x18001c402  jz      loc_18001C858
0x18001c408  mov     [rbp+0B0h+var_130], r13d
0x18001c40c  mov     [rbp+0B0h+var_12C], ax
0x18001c410  test    rdi, rdi
0x18001c413  jz      loc_18001C516
0x18001c419  lea     rdx, [rsp+1B0h+hObject]; void **
0x18001c41e  call    ?SxOpenThreadOrProcessToken@@YAJKPEAPEAX@Z; SxOpenThreadOrProcessToken(ulong,void * *)
0x18001c423  mov     rbx, [rsp+1B0h+hObject]
0x18001c428  test    eax, eax
0x18001c42a  mov     [rbp+0B0h+var_130], eax
0x18001c42d  mov     eax, 0D13h
0x18001c432  jns     short loc_18001C43B
0x18001c434  mov     edi, esi
0x18001c436  jmp     loc_18001C861
0x18001c43b  lea     r8, [rbp+0B0h+NewState]; struct _TOKEN_PRIVILEGES *
0x18001c43f  mov     [rbp+0B0h+var_12C], ax
0x18001c443  mov     rcx, rbx; TokenHandle
0x18001c446  call    ?AssertPrivilegeOnTokenPreserveOrig@@YAJPEAXPEBGPEAU_TOKEN_PRIVILEGES@@K@Z; AssertPrivilegeOnTokenPreserveOrig(void *,ushort const *,_TOKEN_PRIVILEGES *,ulong)
0x18001c44b  mov     [rbp+0B0h+var_130], eax
0x18001c44e  test    eax, eax
0x18001c450  mov     eax, 0D17h
0x18001c455  js      short loc_18001C434
0x18001c457  lea     rdx, SubKey; "SPP-Temp"
0x18001c45e  mov     [rbp+0B0h+var_12C], ax
0x18001c462  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c469  call    cs:__imp_RegUnLoadKeyW
0x18001c46f  lea     r9, aSoftware; "SOFTWARE"
0x18001c476  mov     [rsp+1B0h+phkResult], r13; unsigned __int16 *
0x18001c47b  lea     r8, aSystem32Config; "System32\\Config"
0x18001c482  mov     rdx, rdi; unsigned __int16 *
0x18001c485  lea     rcx, [rbp+0B0h+lpFile]; this
0x18001c489  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001c48e  mov     [rbp+0B0h+var_130], eax
0x18001c491  test    eax, eax
0x18001c493  mov     eax, 0D1Ah
0x18001c498  js      short loc_18001C434
0x18001c49a  mov     r8, [rbp+0B0h+lpFile]; lpFile
0x18001c49e  lea     rdx, SubKey; "SPP-Temp"
0x18001c4a5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c4ac  mov     [rbp+0B0h+var_12C], ax
0x18001c4b0  call    cs:__imp_RegLoadKeyW
0x18001c4b6  test    eax, eax
0x18001c4b8  jle     short loc_18001C4C2
0x18001c4ba  movzx   eax, ax
0x18001c4bd  or      eax, 80070000h
0x18001c4c2  mov     [rbp+0B0h+var_130], eax
0x18001c4c5  test    eax, eax
0x18001c4c7  mov     eax, 0D1Bh
0x18001c4cc  js      loc_18001C434
0x18001c4d2  lea     r9, aClients; "Clients"
0x18001c4d9  mov     [rbp+0B0h+var_12C], ax
0x18001c4dd  lea     r8, aMicrosoftWindo_0; "Microsoft\\Windows NT\\CurrentVersion\\"...
0x18001c4e4  mov     [rsp+1B0h+var_150], 1
0x18001c4ec  lea     rdx, SubKey; "SPP-Temp"
0x18001c4f3  mov     [rsp+1B0h+phkResult], r13; unsigned __int16 *
0x18001c4f8  lea     rcx, [rbp+0B0h+lpSubKey]; this
0x18001c4fc  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001c501  mov     [rbp+0B0h+var_130], eax
0x18001c504  test    eax, eax
0x18001c506  mov     eax, 0D1Dh
0x18001c50b  jns     short loc_18001C545
0x18001c50d  mov     edi, [rsp+1B0h+var_150]
0x18001c511  jmp     loc_18001C861
0x18001c516  xor     r9d, r9d; unsigned __int16 *
0x18001c519  mov     [rsp+1B0h+phkResult], r13; unsigned __int16 *
0x18001c51e  lea     r8, aClients; "Clients"
0x18001c525  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001c52c  lea     rcx, [rbp+0B0h+lpSubKey]; this
0x18001c530  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001c535  mov     [rbp+0B0h+var_130], eax
0x18001c538  test    eax, eax
0x18001c53a  mov     eax, 0D21h
0x18001c53f  js      loc_18001C85F
0x18001c545  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18001c54a  mov     [rbp+0B0h+var_12C], ax
0x18001c54e  lea     rax, [rcx-1]
0x18001c552  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c556  ja      short loc_18001C563
0x18001c558  call    cs:__imp_RegCloseKey
0x18001c55e  mov     [rsp+1B0h+hKey], r13
0x18001c563  mov     rdx, [rbp+0B0h+lpSubKey]; lpSubKey
0x18001c567  lea     rax, [rsp+1B0h+hKey]
0x18001c56c  mov     r9d, 20019h; samDesired
0x18001c572  mov     [rsp+1B0h+phkResult], rax; phkResult
0x18001c577  xor     r8d, r8d; ulOptions
0x18001c57a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c581  call    cs:__imp_RegOpenKeyExW
0x18001c587  test    eax, eax
0x18001c589  jz      short loc_18001C5A4
0x18001c58b  mov     eax, 0D27h
0x18001c590  mov     [rbp+0B0h+var_130], 1
0x18001c597  mov     [rbp+0B0h+var_12C], ax
0x18001c59b  mov     edi, [rsp+1B0h+var_150]
0x18001c59f  jmp     loc_18001C865
0x18001c5a4  mov     r13d, 400h
0x18001c5aa  mov     ecx, r13d; cb
0x18001c5ad  call    cs:__imp_CoTaskMemAlloc
0x18001c5b3  mov     r12, rax
0x18001c5b6  mov     ecx, 0D2Ch
0x18001c5bb  test    rax, rax
0x18001c5be  jz      loc_18001C844
0x18001c5c4  mov     [rbp+0B0h+var_12C], cx
0x18001c5c8  mov     edx, 4000h; unsigned int
0x18001c5cd  lea     rcx, [rbp+0B0h+lpValueName]; this
0x18001c5d1  mov     [rbp+0B0h+var_130], esi
0x18001c5d4  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x18001c5d9  mov     [rbp+0B0h+var_130], eax
0x18001c5dc  test    eax, eax
0x18001c5de  mov     eax, 0D2Eh
0x18001c5e3  jns     short loc_18001C5F1
0x18001c5e5  mov     edi, [rsp+1B0h+var_150]
0x18001c5e9  xor     r13d, r13d
0x18001c5ec  jmp     loc_18001C861
0x18001c5f1  lea     rcx, [rbp+0B0h+var_E0]
0x18001c5f5  mov     [rbp+0B0h+var_12C], ax
0x18001c5f9  call    ?CreateInstance@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@SAJPEAPEAV1@@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::CreateInstance(CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)> * *)
0x18001c5fe  mov     rsi, qword ptr [rbp+0B0h+var_E0.Data1]
0x18001c602  xor     r8d, r8d
0x18001c605  test    eax, eax
0x18001c607  mov     [rbp+0B0h+var_130], eax
0x18001c60a  mov     eax, 0D30h
0x18001c60f  js      short loc_18001C5E5
0x18001c611  mov     edx, r8d; dwIndex
0x18001c614  mov     [rbp+0B0h+var_12C], ax
0x18001c618  mov     dword ptr [rsp+1B0h+hObject], edx
0x18001c61c  mov     edi, [rbp+0B0h+var_E8+4]
0x18001c61f  lea     r9, [rbp+0B0h+cchValueName]; lpcchValueName
0x18001c623  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18001c628  mov     [rsp+1B0h+cbData], r13d
0x18001c62d  lea     eax, [rdi+1]
0x18001c630  mov     [rbp+0B0h+cchValueName], eax
0x18001c633  lea     rax, [rsp+1B0h+cbData]
0x18001c638  mov     [rsp+1B0h+lpcbData], rax; lpcbData
0x18001c63d  lea     rax, [rbp+0B0h+Type]
0x18001c641  mov     [rsp+1B0h+lpData], r12; lpData
0x18001c646  mov     [rsp+1B0h+lpType], rax; lpType
0x18001c64b  mov     [rsp+1B0h+phkResult], r8; lpReserved
0x18001c650  mov     r8, [rbp+0B0h+lpValueName]; lpValueName
0x18001c654  call    cs:__imp_RegEnumValueW
0x18001c65a  mov     edx, edi; unsigned int
0x18001c65c  lea     rcx, [rbp+0B0h+lpValueName]; this
0x18001c660  mov     r10d, eax
0x18001c663  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x18001c668  cmp     r10d, 0EAh
0x18001c66f  jnz     short loc_18001C6B0
0x18001c671  mov     ecx, [rsp+1B0h+cbData]; unsigned int
0x18001c675  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x18001c67a  mov     rcx, r12; pv
0x18001c67d  mov     edi, eax
0x18001c67f  call    cs:__imp_CoTaskMemFree
0x18001c685  mov     ecx, edi; cb
0x18001c687  call    cs:__imp_CoTaskMemAlloc
0x18001c68d  xor     r13d, r13d
0x18001c690  mov     r12, rax
0x18001c693  test    rax, rax
0x18001c696  mov     eax, 0D48h
0x18001c69b  jz      loc_18001C81B
0x18001c6a1  xor     r8d, r8d
0x18001c6a4  mov     r13d, edi
0x18001c6a7  mov     [rbp+0B0h+var_130], r8d
0x18001c6ab  jmp     loc_18001C80E
0x18001c6b0  cmp     r10d, 103h
0x18001c6b7  jz      loc_18001C827
0x18001c6bd  xor     r8d, r8d
0x18001c6c0  test    r10d, r10d
0x18001c6c3  jnz     loc_18001C7EF
0x18001c6c9  mov     edx, dword ptr [rsp+1B0h+hObject]
0x18001c6cd  inc     edx
0x18001c6cf  cmp     [rbp+0B0h+Type], 7
0x18001c6d3  mov     dword ptr [rsp+1B0h+hObject], edx
0x18001c6d7  jnz     loc_18001C61C
0x18001c6dd  mov     edx, [rsp+1B0h+cbData]
0x18001c6e1  test    dl, 1
0x18001c6e4  jnz     loc_18001C812
0x18001c6ea  shr     edx, 1
0x18001c6ec  cmp     edx, 3
0x18001c6ef  jb      loc_18001C812
0x18001c6f5  lea     eax, [rdx-1]
0x18001c6f8  cmp     [r12+rax*2], r8w
0x18001c6fd  jnz     loc_18001C812
0x18001c703  lea     eax, [rdx-2]
0x18001c706  cmp     [r12+rax*2], r8w
0x18001c70b  jnz     loc_18001C812
0x18001c711  mov     edx, [rbp+0B0h+var_E8+4]; unsigned int
0x18001c714  lea     rcx, [rbp+0B0h+lpValueName]; this
0x18001c718  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x18001c71d  mov     rcx, [rbp+0B0h+lpValueName]; lpsz
0x18001c721  lea     rdx, [rbp+0B0h+pclsid]; pclsid
0x18001c725  call    cs:__imp_CLSIDFromString
0x18001c72b  mov     edx, dword ptr [rsp+1B0h+hObject]
0x18001c72f  xor     r8d, r8d
0x18001c732  test    eax, eax
0x18001c734  js      loc_18001C61C
0x18001c73a  mov     r8d, 10h; Size
0x18001c740  lea     rdx, unk_18003BA18; Buf2
0x18001c747  lea     rcx, [rbp+0B0h+pclsid]; Buf1
0x18001c74b  call    memcmp_0
0x18001c750  xor     r8d, r8d
0x18001c753  test    eax, eax
0x18001c755  jnz     short loc_18001C79F
0x18001c757  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c75e  lea     rax, WPP_GLOBAL_Control
0x18001c765  mov     edx, dword ptr [rsp+1B0h+hObject]
0x18001c769  cmp     rcx, rax
0x18001c76c  jz      loc_18001C61C
0x18001c772  test    dword ptr [rcx+1Ch], 4000000h
0x18001c779  jz      loc_18001C61C
0x18001c77f  mov     rcx, [rcx+10h]
0x18001c783  lea     edx, [r8+26h]
0x18001c787  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001c78e  call    WPP_SF_
0x18001c793  mov     edx, dword ptr [rsp+1B0h+hObject]
0x18001c797  xor     r8d, r8d
0x18001c79a  jmp     loc_18001C61C
0x18001c79f  movaps  xmm0, xmmword ptr [rbp+0B0h+pclsid.Data1]
0x18001c7a3  lea     r9, [rbp+0B0h+var_80]; struct _SPP_CLIENT_PROP *
0x18001c7a7  mov     edi, [rsp+1B0h+var_150]
0x18001c7ab  lea     r8, [rbp+0B0h+var_E0]; struct _GUID
0x18001c7af  mov     rcx, [rbp+0B0h+var_B0]; this
0x18001c7b3  mov     edx, edi; int
0x18001c7b5  movdqa  xmmword ptr [rbp+0B0h+var_E0.Data1], xmm0
0x18001c7ba  call    ?_LoadClient@CSpp@@AEAAJHU_GUID@@PEAU_SPP_CLIENT_PROP@@@Z; CSpp::_LoadClient(int,_GUID,_SPP_CLIENT_PROP *)
0x18001c7bf  mov     edx, dword ptr [rsp+1B0h+hObject]
0x18001c7c3  xor     r8d, r8d
0x18001c7c6  test    eax, eax
0x18001c7c8  js      loc_18001C61C
0x18001c7ce  lea     rdx, [rbp+0B0h+var_80]
0x18001c7d2  mov     rcx, rsi
0x18001c7d5  call    ?Append@?$CSxArrayBuilder@U_SPP_CLIENT_PROP@@$1?Free_SPP_CLIENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_CLIENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_CLIENT_PROP@@@@YAX00@Z@@QEAAJPEAU_SPP_CLIENT_PROP@@@Z; CSxArrayBuilder<_SPP_CLIENT_PROP,&Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *),&SxDefaultInit<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *),&SxDefaultTransfer<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *,_SPP_CLIENT_PROP *)>::Append(_SPP_CLIENT_PROP *)
  ... truncated ...
```
