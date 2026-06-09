# HrGetFactoryWrappedInterface(_GUID const *,tagXW_WIZARD_TYPE,_GUID * * const,_GUID * * const)

- ea: `0x18000b4b8`
- end: `0x18000bac2`
- name: `?HrGetFactoryWrappedInterface@@YAJPEBU_GUID@@W4tagXW_WIZARD_TYPE@@QEAPEAU1@2@Z`
- size: `1546`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006b20`

## callees

- `0x180007820`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000b4b8`
- `0x18001230c`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `msvcrt!iswxdigit` at `0x18000b651`
- `msvcrt!iswxdigit` at `0x18000b8aa`
- `msvcrt!iswxdigit` at `0x18000b651`
- `msvcrt!iswxdigit` at `0x18000b8aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b959`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b959`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b6f5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b94a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b6f5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b94a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b6da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b92d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b6da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b92d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000b53c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000b53c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b5b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b832`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b5b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b832`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b78b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b9d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b78b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b9d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b5ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b869`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b5ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b869`

## string_xrefs

- `0x18000b5ce`: `Wrapped CLSID`

## pseudocode

```c
__int64 __fastcall HrGetFactoryWrappedInterface(const GUID *a1, DWORD a2, CLSID **a3, CLSID **a4)
{
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  char v9; // di
  HRESULT v10; // esi
  int v11; // ebx
  wint_t v12; // dx
  BOOL v13; // ecx
  bool v14; // zf
  PVOID *v15; // rcx
  CLSID *v16; // rax
  LPVOID *v17; // rdi
  HRESULT v18; // ebx
  __int64 v19; // rax
  LSTATUS v20; // eax
  LSTATUS v21; // edi
  int v22; // ebx
  wint_t v23; // ax
  BOOL v24; // ecx
  __int16 v25; // r8
  bool v26; // zf
  PVOID *v27; // rcx
  CLSID *v28; // rax
  LPVOID *v29; // rbx
  PVOID *v30; // rcx
  DWORD lpcbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  CLSID **v35; // [rsp+48h] [rbp-B8h]
  CLSID **v36; // [rsp+50h] [rbp-B0h]
  OLECHAR Data[40]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[136]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[40]; // [rsp+1C0h] [rbp+C0h] BYREF

  v35 = a3;
  lpcbData = a2;
  v36 = a4;
  hKey = 0;
  memset_0(Data, 0, sizeof(Data));
  *a3 = 0;
  *a4 = 0;
  memset_0(sz, 0, sizeof(sz));
  StringFromGUID2(a1, sz, 40);
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x87u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x87u, L"Factory");
  StringCchCatW(SubKey, 0x87u, &qword_180016C40);
  StringCchCatW(SubKey, 0x87u, sz);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  if ( v7 )
  {
    v30 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
        (unsigned int)SubKey,
        v7);
      v30 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = 1;
    goto LABEL_79;
  }
  cbData = 80;
  v8 = RegQueryValueExW(hKey, L"Wrapped CLSID", 0, 0, (LPBYTE)Data, &cbData);
  v9 = v8;
  v10 = -2147024882;
  if ( v8 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  v11 = 0;
  while ( 1 )
  {
    v12 = Data[v11];
    if ( !v12 )
      break;
    if ( v11 )
    {
      if ( v11 == 9 || v11 == 14 || v11 == 19 || v11 == 24 )
      {
        v14 = v12 == 45;
        goto LABEL_14;
      }
      if ( v11 == 37 )
      {
        v14 = v12 == 125;
LABEL_14:
        v13 = v14;
        goto LABEL_15;
      }
      v13 = iswxdigit(v12) != 0;
LABEL_15:
      ++v11;
      if ( !v13 )
        break;
    }
    else
    {
      v11 = 1;
      if ( v12 != 123 )
        break;
    }
  }
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_90e98dcb6fd731cfe787e20a7218e05c_Traceguids,
      (unsigned int)Data,
      v11 == 38);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 == 38 )
  {
    v16 = (CLSID *)CoTaskMemAlloc(0x10u);
    v17 = (LPVOID *)v35;
    *v35 = v16;
    if ( v16 )
    {
      v18 = CLSIDFromString(Data, v16);
      if ( v18 < 0 )
      {
        CoTaskMemFree(*v17);
        *v17 = 0;
      }
    }
    else
    {
      v18 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
          (unsigned int)Data,
          14);
    }
    goto LABEL_33;
  }
LABEL_29:
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x10) != 0 )
    WPP_SF_SD(
      (unsigned int)v15[2],
      31,
      (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
      (unsigned int)SubKey,
      v9);
  v18 = 1;
LABEL_33:
  RegCloseKey(hKey);
  if ( v18 )
  {
    v10 = v18;
    goto LABEL_69;
  }
  StringCchCatW(SubKey, 0x87u, &qword_180016C40);
  StringCchCatW(SubKey, 0x87u, L"Wrapped Interfaces");
  StringCchCatW(SubKey, 0x87u, &qword_180016C40);
  v19 = -1;
  do
    ++v19;
  while ( SubKey[v19] );
  swprintf_sfn(&SubKey[v19], 135 - v19, L"%#0*.*lx");
  v20 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  if ( v20 )
  {
    v30 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
        (unsigned int)SubKey,
        v20);
      v30 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = 1;
    goto LABEL_79;
  }
  lpcbData = 80;
  v21 = RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)Data, &lpcbData);
  if ( v21 )
  {
    v27 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_64;
  }
  v22 = 0;
  while ( 2 )
  {
    v23 = Data[v22];
    if ( v23 )
    {
      if ( v22 )
      {
        if ( v22 == 9 || v22 == 14 || v22 == 19 || v22 == 24 )
        {
          v25 = 45;
        }
        else
        {
          if ( v22 != 37 )
          {
            v24 = iswxdigit(v23) != 0;
            goto LABEL_50;
          }
          v25 = 125;
        }
        v24 = v25 == (__int16)v23;
LABEL_50:
        ++v22;
        v26 = v24;
      }
      else
      {
        v22 = 1;
        v26 = v23 == 123;
      }
      if ( !v26 )
        break;
      continue;
    }
    break;
  }
  v27 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_90e98dcb6fd731cfe787e20a7218e05c_Traceguids,
      (unsigned int)Data,
      v22 == 38);
    v27 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v22 == 38 )
  {
    v28 = (CLSID *)CoTaskMemAlloc(0x10u);
    v29 = (LPVOID *)v36;
    *v36 = v28;
    if ( v28 )
    {
      v10 = CLSIDFromString(Data, v28);
      if ( v10 < 0 )
      {
        CoTaskMemFree(*v29);
        *v29 = 0;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
        (unsigned int)Data,
        14);
    }
    goto LABEL_68;
  }
LABEL_64:
  if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 4) != 0 )
    WPP_SF_SD(
      (unsigned int)v27[2],
      34,
      (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
      (unsigned int)SubKey,
      v21);
  v10 = 1;
LABEL_68:
  RegCloseKey(hKey);
LABEL_69:
  v30 = (PVOID *)WPP_GLOBAL_Control;
LABEL_79:
  if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 0x10) != 0 )
    WPP_SF_D(v30[2], 36, WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids, (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000b4b8  push    rbp
0x18000b4ba  push    rbx
0x18000b4bb  push    rsi
0x18000b4bc  push    rdi
0x18000b4bd  push    r12
0x18000b4bf  push    r13
0x18000b4c1  push    r14
0x18000b4c3  lea     rbp, [rsp-120h]
0x18000b4cb  sub     rsp, 220h
0x18000b4d2  mov     rax, cs:__security_cookie
0x18000b4d9  xor     rax, rsp
0x18000b4dc  mov     [rbp+150h+var_40], rax
0x18000b4e3  xor     r12d, r12d
0x18000b4e6  mov     [rsp+250h+var_208], r8
0x18000b4eb  mov     rdi, r8
0x18000b4ee  mov     [rsp+250h+var_220], edx
0x18000b4f2  mov     rbx, rcx
0x18000b4f5  mov     [rsp+250h+var_200], r9
0x18000b4fa  xor     edx, edx; Val
0x18000b4fc  mov     [rsp+250h+hKey], r12
0x18000b501  lea     r14d, [r12+50h]
0x18000b506  mov     rsi, r9
0x18000b509  mov     r8d, r14d; Size
0x18000b50c  lea     rcx, [rsp+250h+Data]; void *
0x18000b511  call    memset_0
0x18000b516  mov     r8d, r14d; Size
0x18000b519  mov     [rdi], r12
0x18000b51c  xor     edx, edx; Val
0x18000b51e  mov     [rsi], r12
0x18000b521  lea     rcx, [rbp+150h+sz]; void *
0x18000b528  call    memset_0
0x18000b52d  lea     r8d, [r12+28h]; cchMax
0x18000b532  mov     rcx, rbx; rguid
0x18000b535  lea     rdx, [rbp+150h+sz]; lpsz
0x18000b53c  call    cs:__imp_StringFromGUID2
0x18000b542  lea     ebx, [r14+37h]
0x18000b546  mov     [rbp+150h+SubKey], r12w
0x18000b54b  mov     edx, ebx; unsigned __int64
0x18000b54d  lea     r8, aSoftwareMicros_0
0x18000b554  lea     rcx, [rbp+150h+SubKey]; unsigned __int16 *
0x18000b558  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z
0x18000b55d  lea     r8, aFactory_0
0x18000b564  mov     edx, ebx; unsigned __int64
0x18000b566  lea     rcx, [rbp+150h+SubKey]; unsigned __int16 *
0x18000b56a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18000b56f  lea     r8, qword_180016C40; unsigned __int16 *
0x18000b576  mov     edx, ebx; unsigned __int64
0x18000b578  lea     rcx, [rbp+150h+SubKey]; unsigned __int16 *
0x18000b57c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18000b581  lea     r8, [rbp+150h+sz]; unsigned __int16 *
0x18000b588  mov     edx, ebx; unsigned __int64
0x18000b58a  lea     rcx, [rbp+150h+SubKey]; unsigned __int16 *
0x18000b58e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18000b593  lea     rax, [rsp+250h+hKey]
0x18000b598  mov     r9d, 20019h; samDesired
0x18000b59e  xor     r8d, r8d; ulOptions
0x18000b5a1  mov     [rsp+250h+phkResult], rax; phkResult
0x18000b5a6  lea     rdx, [rbp+150h+SubKey]; lpSubKey
0x18000b5aa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b5b1  call    cs:__imp_RegOpenKeyExW
0x18000b5b7  test    eax, eax
0x18000b5b9  jnz     loc_18000BA2F
0x18000b5bf  mov     rcx, [rsp+250h+hKey]; hKey
0x18000b5c4  lea     rax, [rsp+250h+cbData]
0x18000b5c9  mov     [rsp+250h+lpcbData], rax; lpcbData
0x18000b5ce  lea     rdx, aWrappedClsid_0
0x18000b5d5  lea     rax, [rsp+250h+Data]
0x18000b5da  mov     [rsp+250h+cbData], r14d
0x18000b5df  xor     r9d, r9d; lpType
0x18000b5e2  mov     [rsp+250h+phkResult], rax; lpData
0x18000b5e7  xor     r8d, r8d; lpReserved
0x18000b5ea  call    cs:__imp_RegQueryValueExW
0x18000b5f0  xor     r8d, r8d
0x18000b5f3  lea     r9d, [r12+7Dh]
0x18000b5f8  lea     r10d, [r12+2Dh]
0x18000b5fd  mov     edi, eax
0x18000b5ff  lea     r12d, [r14-4Fh]
0x18000b603  mov     esi, 8007000Eh
0x18000b608  lea     r13, WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids
0x18000b60f  lea     ecx, [rbx-0Ch]
0x18000b612  lea     r14, WPP_GLOBAL_Control
0x18000b619  test    eax, eax
0x18000b61b  jnz     loc_18000B74B
0x18000b621  mov     ebx, r8d
0x18000b624  movsxd  rax, ebx
0x18000b627  movzx   edx, [rsp+rax*2+250h+Data]
0x18000b62c  test    dx, dx
0x18000b62f  jz      short loc_18000B692
0x18000b631  test    ebx, ebx
0x18000b633  jz      short loc_18000B68B
0x18000b635  cmp     ebx, 9
0x18000b638  jz      short loc_18000B672
0x18000b63a  cmp     ebx, 0Eh
0x18000b63d  jz      short loc_18000B672
0x18000b63f  cmp     ebx, 13h
0x18000b642  jz      short loc_18000B672
0x18000b644  cmp     ebx, 18h
0x18000b647  jz      short loc_18000B672
0x18000b649  cmp     ebx, 25h ; '%'
0x18000b64c  jz      short loc_18000B66C
0x18000b64e  movzx   ecx, dx; C
0x18000b651  call    cs:__imp_iswxdigit
0x18000b657  xor     r8d, r8d
0x18000b65a  test    eax, eax
0x18000b65c  mov     ecx, r8d
0x18000b65f  setnz   cl
0x18000b662  lea     r9d, [r8+7Dh]
0x18000b666  lea     r10d, [r8+2Dh]
0x18000b66a  jmp     short loc_18000B67C
0x18000b66c  cmp     r9w, dx
0x18000b670  jmp     short loc_18000B676
0x18000b672  cmp     r10w, dx
0x18000b676  mov     ecx, r8d
0x18000b679  setz    cl
0x18000b67c  add     ebx, r12d
0x18000b67f  cmp     ecx, r12d
0x18000b682  jnz     short loc_18000B692
0x18000b684  mov     ecx, 7Bh ; '{'
0x18000b689  jmp     short loc_18000B624
0x18000b68b  inc     ebx
0x18000b68d  cmp     cx, dx
0x18000b690  jz      short loc_18000B624
0x18000b692  cmp     ebx, 26h ; '&'
0x18000b695  mov     eax, r8d
0x18000b698  setz    al
0x18000b69b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6a2  cmp     rcx, r14
0x18000b6a5  jz      short loc_18000B6D2
0x18000b6a7  test    byte ptr [rcx+1Ch], 10h
0x18000b6ab  jz      short loc_18000B6D2
0x18000b6ad  mov     rcx, [rcx+10h]
0x18000b6b1  lea     r9, [rsp+250h+Data]
0x18000b6b6  mov     edx, 0Ah
0x18000b6bb  mov     dword ptr [rsp+250h+phkResult], eax
0x18000b6bf  lea     r8, WPP_90e98dcb6fd731cfe787e20a7218e05c_Traceguids
0x18000b6c6  call    WPP_SF_SD
0x18000b6cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6d2  cmp     ebx, 26h ; '&'
0x18000b6d5  jnz     short loc_18000B752
0x18000b6d7  lea     ecx, [rbx-16h]; cb
0x18000b6da  call    cs:__imp_CoTaskMemAlloc
0x18000b6e0  mov     rdi, [rsp+250h+var_208]
0x18000b6e5  mov     [rdi], rax
0x18000b6e8  test    rax, rax
0x18000b6eb  jz      short loc_18000B717
0x18000b6ed  mov     rdx, rax; pclsid
0x18000b6f0  lea     rcx, [rsp+250h+Data]; lpsz
0x18000b6f5  call    cs:__imp_CLSIDFromString
0x18000b6fb  mov     ebx, eax
0x18000b6fd  test    eax, eax
0x18000b6ff  jns     loc_18000B786
0x18000b705  mov     rcx, [rdi]; pv
0x18000b708  call    cs:__imp_CoTaskMemFree
0x18000b70e  mov     qword ptr [rdi], 0
0x18000b715  jmp     short loc_18000B786
0x18000b717  mov     ebx, esi
0x18000b719  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b720  cmp     rcx, r14
0x18000b723  jz      short loc_18000B786
0x18000b725  test    byte ptr [rcx+1Ch], 4
0x18000b729  jz      short loc_18000B786
0x18000b72b  mov     rcx, [rcx+10h]
0x18000b72f  lea     r9, [rsp+250h+Data]
0x18000b734  mov     edx, 1Eh
0x18000b739  mov     dword ptr [rsp+250h+phkResult], 8007000Eh
0x18000b741  mov     r8, r13
0x18000b744  call    WPP_SF_SD
0x18000b749  jmp     short loc_18000B786
0x18000b74b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b752  cmp     rcx, r14
0x18000b755  jz      short loc_18000B783
0x18000b757  test    byte ptr [rcx+1Ch], 10h
0x18000b75b  jz      short loc_18000B783
0x18000b75d  test    edi, edi
0x18000b75f  jle     short loc_18000B76A
0x18000b761  movzx   edi, di
0x18000b764  or      edi, 80070000h
0x18000b76a  mov     rcx, [rcx+10h]
0x18000b76e  lea     r9, [rbp+150h+SubKey]
0x18000b772  mov     edx, 1Fh
0x18000b777  mov     dword ptr [rsp+250h+phkResult], edi
0x18000b77b  mov     r8, r13
0x18000b77e  call    WPP_SF_SD
0x18000b783  mov     ebx, r12d
0x18000b786  mov     rcx, [rsp+250h+hKey]; hKey
0x18000b78b  call    cs:__imp_RegCloseKey
0x18000b791  xor     edi, edi
0x18000b793  test    ebx, ebx
0x18000b795  jnz     loc_18000BA2B
0x18000b79b  mov     ebx, 87h
0x18000b7a0  lea     r8, qword_180016C40; unsigned __int16 *
0x18000b7a7  mov     edx, ebx; unsigned __int64
0x18000b7a9  lea     rcx, [rbp+150h+SubKey]; unsigned __int16 *
0x18000b7ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18000b7b2  lea     r8, aWrappedInterfa
0x18000b7b9  mov     edx, ebx; unsigned __int64
0x18000b7bb  lea     rcx, [rbp+150h+SubKey]; unsigned __int16 *
0x18000b7bf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18000b7c4  lea     r8, qword_180016C40; unsigned __int16 *
0x18000b7cb  mov     edx, ebx; unsigned __int64
0x18000b7cd  lea     rcx, [rbp+150h+SubKey]; unsigned __int16 *
0x18000b7d1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18000b7d6  lea     rcx, [rbp+150h+SubKey]
0x18000b7da  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b7de  inc     rax
0x18000b7e1  cmp     [rcx+rax*2], di
0x18000b7e5  jnz     short loc_18000B7DE
0x18000b7e7  sub     rbx, rax
0x18000b7ea  lea     rcx, [rbp+150h+SubKey]
0x18000b7ee  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18000b7f2  mov     r9d, 8
0x18000b7f8  mov     eax, [rsp+250h+var_220]
0x18000b7fc  lea     r8, a0Lx
0x18000b803  mov     dword ptr [rsp+250h+lpcbData], eax
0x18000b807  mov     rdx, rbx; unsigned __int64
0x18000b80a  mov     dword ptr [rsp+250h+phkResult], r9d
0x18000b80f  call    ?swprintf_sfn@@YAXPEAG_KPEBGZZ
0x18000b814  lea     rax, [rsp+250h+hKey]
0x18000b819  mov     r9d, 20019h; samDesired
0x18000b81f  xor     r8d, r8d; ulOptions
0x18000b822  mov     [rsp+250h+phkResult], rax; phkResult
0x18000b827  lea     rdx, [rbp+150h+SubKey]; lpSubKey
0x18000b82b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b832  call    cs:__imp_RegOpenKeyExW
0x18000b838  test    eax, eax
0x18000b83a  jnz     loc_18000B9E8
0x18000b840  mov     rcx, [rsp+250h+hKey]; hKey
0x18000b845  lea     rax, [rsp+250h+var_220]
0x18000b84a  mov     [rsp+250h+lpcbData], rax; lpcbData
0x18000b84f  xor     r9d, r9d; lpType
0x18000b852  lea     rax, [rsp+250h+Data]
0x18000b857  mov     [rsp+250h+var_220], 50h ; 'P'
0x18000b85f  xor     r8d, r8d; lpReserved
0x18000b862  mov     [rsp+250h+phkResult], rax; lpData
0x18000b867  xor     edx, edx; lpValueName
0x18000b869  call    cs:__imp_RegQueryValueExW
0x18000b86f  xor     edx, edx
0x18000b871  mov     edi, eax
0x18000b873  test    eax, eax
0x18000b875  jnz     loc_18000B996
0x18000b87b  mov     ebx, edx
0x18000b87d  movsxd  rcx, ebx
0x18000b880  movzx   eax, [rsp+rcx*2+250h+Data]
0x18000b885  test    ax, ax
0x18000b888  jz      short loc_18000B8E6
0x18000b88a  test    ebx, ebx
0x18000b88c  jz      short loc_18000B8DA
0x18000b88e  cmp     ebx, 9
0x18000b891  jz      short loc_18000B8C3
0x18000b893  cmp     ebx, 0Eh
0x18000b896  jz      short loc_18000B8C3
0x18000b898  cmp     ebx, 13h
0x18000b89b  jz      short loc_18000B8C3
0x18000b89d  cmp     ebx, 18h
0x18000b8a0  jz      short loc_18000B8C3
0x18000b8a2  cmp     ebx, 25h ; '%'
0x18000b8a5  jz      short loc_18000B8BB
0x18000b8a7  movzx   ecx, ax; C
0x18000b8aa  call    cs:__imp_iswxdigit
0x18000b8b0  xor     edx, edx
0x18000b8b2  test    eax, eax
0x18000b8b4  mov     ecx, edx
0x18000b8b6  setnz   cl
0x18000b8b9  jmp     short loc_18000B8D2
0x18000b8bb  mov     r8d, 7Dh ; '}'
0x18000b8c1  jmp     short loc_18000B8C9
0x18000b8c3  mov     r8d, 2Dh ; '-'
0x18000b8c9  cmp     r8w, ax
0x18000b8cd  mov     ecx, edx
0x18000b8cf  setz    cl
0x18000b8d2  add     ebx, r12d
0x18000b8d5  cmp     ecx, r12d
0x18000b8d8  jmp     short loc_18000B8E4
0x18000b8da  mov     ecx, 7Bh ; '{'
0x18000b8df  inc     ebx
0x18000b8e1  cmp     cx, ax
0x18000b8e4  jz      short loc_18000B87D
0x18000b8e6  cmp     ebx, 26h ; '&'
0x18000b8e9  mov     eax, edx
0x18000b8eb  setz    al
0x18000b8ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8f5  cmp     rcx, r14
0x18000b8f8  jz      short loc_18000B925
0x18000b8fa  test    byte ptr [rcx+1Ch], 10h
0x18000b8fe  jz      short loc_18000B925
0x18000b900  mov     rcx, [rcx+10h]
0x18000b904  lea     r9, [rsp+250h+Data]
0x18000b909  mov     edx, 0Ah
0x18000b90e  mov     dword ptr [rsp+250h+phkResult], eax
0x18000b912  lea     r8, WPP_90e98dcb6fd731cfe787e20a7218e05c_Traceguids
0x18000b919  call    WPP_SF_SD
0x18000b91e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b925  cmp     ebx, 26h ; '&'
0x18000b928  jnz     short loc_18000B99D
0x18000b92a  lea     ecx, [rbx-16h]; cb
0x18000b92d  call    cs:__imp_CoTaskMemAlloc
0x18000b933  mov     rbx, [rsp+250h+var_200]
0x18000b938  xor     edi, edi
0x18000b93a  mov     [rbx], rax
0x18000b93d  test    rax, rax
  ... truncated ...
```
