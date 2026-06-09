# CSdBackupConfigImpl::_ReadUserSettings(HKEY__ *,ulong *,_SD_BACKUP_USER_DATA * *,ulong *)

- ea: `0x180059924`
- end: `0x180059ed8`
- name: `?_ReadUserSettings@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEAKPEAPEAU_SD_BACKUP_USER_DATA@@1@Z`
- size: `1460`
- prototype: `int(CSdBackupConfigImpl *__hidden this, HKEY, unsigned int *, struct _SD_BACKUP_USER_DATA **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180058eb4`

## callees

- `0x180059924`
- `0x18006fe84`
- `0x18006ff8c`
- `0x1800709ec`
- `0x18008de44`
- `0x180094758`
- `0x1800948bc`
- `0x1800c97da`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059bbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059de1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059e97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059eaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059bbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059de1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059e97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059eaf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800599fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059bde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800599fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059bde`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180059b7a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180059b7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180059a5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180059a5e`
- `ole32!CoTaskMemFree` at `0x180059dc6`
- `ole32!CoTaskMemFree` at `0x180059e6e`
- `ole32!CoTaskMemFree` at `0x180059e77`
- `ole32!CoTaskMemFree` at `0x180059e80`
- `ole32!CoTaskMemFree` at `0x180059dc6`
- `ole32!CoTaskMemFree` at `0x180059e6e`
- `ole32!CoTaskMemFree` at `0x180059e77`
- `ole32!CoTaskMemFree` at `0x180059e80`
- `ole32!CoTaskMemAlloc` at `0x180059acc`
- `ole32!CoTaskMemAlloc` at `0x180059b0a`
- `ole32!CoTaskMemAlloc` at `0x180059d4a`
- `ole32!CoTaskMemAlloc` at `0x180059acc`
- `ole32!CoTaskMemAlloc` at `0x180059b0a`
- `ole32!CoTaskMemAlloc` at `0x180059d4a`

## string_xrefs

- `0x180059956`: `CSdBackupConfigImpl::_ReadUserSettings`

## pseudocode

```c
__int64 __fastcall CSdBackupConfigImpl::_ReadUserSettings(
        CSdBackupConfigImpl *this,
        HKEY a2,
        unsigned int *a3,
        struct _SD_BACKUP_USER_DATA **a4,
        unsigned int *a5)
{
  WCHAR *v8; // rsi
  unsigned __int16 *v9; // r14
  struct _SD_BACKUP_USER_DATA *v10; // r15
  unsigned int *v11; // rbx
  __int16 v12; // ax
  int v13; // eax
  bool v14; // sf
  int v15; // eax
  WCHAR *v16; // rax
  struct _SD_BACKUP_USER_DATA *v17; // rax
  DWORD i; // ebx
  unsigned int v19; // eax
  int v20; // eax
  int v21; // eax
  char *v22; // rsi
  unsigned int v23; // edi
  int MultiString; // eax
  _WORD *v25; // rax
  unsigned int v26; // ecx
  __int64 v27; // rdx
  SIZE_T v28; // rbx
  LPVOID v29; // rax
  bool v30; // zf
  const unsigned __int16 *v31; // rbx
  __int64 v32; // rax
  unsigned int v33; // ebx
  WCHAR *lpName; // [rsp+60h] [rbp-51h]
  HKEY phkResult; // [rsp+68h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-39h] BYREF
  int DWORD; // [rsp+80h] [rbp-31h] BYREF
  __int16 v40; // [rsp+84h] [rbp-2Dh]
  __int16 v41; // [rsp+86h] [rbp-2Bh]
  CSdBackupConfigImpl *cSubKeys; // [rsp+110h] [rbp+5Fh] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+118h] [rbp+67h] BYREF
  unsigned int v44; // [rsp+120h] [rbp+6Fh] BYREF
  DWORD cchName; // [rsp+128h] [rbp+77h] BYREF

  cSubKeys = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&DWORD, "CSdBackupConfigImpl::_ReadUserSettings", 325, 1);
  hKey = 0;
  phkResult = 0;
  LODWORD(cSubKeys) = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  v8 = 0;
  v9 = 0;
  pv = 0;
  v10 = 0;
  v44 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v11 = a5;
  if ( a5 )
    *a5 = 0;
  v12 = 347;
  if ( !a2 || (v40 = 347, v12 = 348, !a3) || (v40 = 348, v12 = 349, !a4) )
  {
    DWORD = -2147024809;
    goto LABEL_69;
  }
  DWORD = 0;
  v40 = 349;
  v13 = RegOpenKeyExW(a2, L"UserDataExclusions", 0, 0x20019u, &hKey);
  if ( v13 > 0 )
    v13 = (unsigned __int16)v13 | 0x80070000;
  DWORD = v13;
  v14 = v13 < 0;
  v12 = 351;
  if ( v14 )
    goto LABEL_69;
  v40 = 351;
  v15 = RegQueryInfoKeyW(hKey, 0, 0, 0, (LPDWORD)&cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x80070000;
  DWORD = v15;
  v14 = v15 < 0;
  v12 = 352;
  if ( v14 || (v40 = 352, DWORD = SxRegReadDWORD(hKey, L"UsersFullyExcluded", v11, 0), v12 = 354, DWORD < 0) )
  {
LABEL_69:
    v41 = v12;
  }
  else
  {
    v40 = 354;
    if ( (_DWORD)cSubKeys )
    {
      v16 = (WCHAR *)CoTaskMemAlloc(2LL * (cbMaxSubKeyLen + 1));
      lpName = v16;
      if ( v16 )
      {
        DWORD = 0;
        v40 = 362;
        memset_0(v16, 0, 2LL * (cbMaxSubKeyLen + 1));
        v17 = (struct _SD_BACKUP_USER_DATA *)CoTaskMemAlloc(40LL * (unsigned int)cSubKeys);
        v10 = v17;
        if ( v17 )
        {
          DWORD = 0;
          v40 = 366;
          memset_0(v17, 0, 40LL * (unsigned int)cSubKeys);
          for ( i = 0; ; ++i )
          {
            LODWORD(a5) = i;
            v19 = (unsigned int)cSubKeys;
            if ( i >= (unsigned int)cSubKeys )
              goto LABEL_64;
            cchName = cbMaxSubKeyLen + 1;
            v20 = RegEnumKeyExW(hKey, i, lpName, &cchName, 0, 0, 0, 0);
            if ( v20 == 259 )
              break;
            if ( v20 > 0 )
              v20 = (unsigned __int16)v20 | 0x80070000;
            DWORD = v20;
            v14 = v20 < 0;
            v12 = 381;
            if ( v14 )
              goto LABEL_62;
            v40 = 381;
            if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              RegCloseKey(phkResult);
              phkResult = 0;
            }
            v21 = RegOpenKeyExW(hKey, lpName, 0, 0x20019u, &phkResult);
            if ( v21 > 0 )
              v21 = (unsigned __int16)v21 | 0x80070000;
            DWORD = v21;
            if ( v21 < 0 )
            {
              v12 = 385;
LABEL_62:
              v8 = lpName;
              goto LABEL_69;
            }
            v22 = (char *)v10 + 40 * i;
            v40 = 385;
            DWORD = SdSafeDuplicateStr((unsigned __int16 **)v22, lpName);
            v23 = 0;
            v12 = 387;
            if ( DWORD < 0 )
              goto LABEL_58;
            v40 = 387;
            DWORD = SxRegReadDWORD(phkResult, L"FoldersNotToBackup", (unsigned int *)v22 + 6, 0);
            v12 = 389;
            if ( DWORD < 0 )
              goto LABEL_58;
            v40 = 389;
            DWORD = SxRegReadDWORD(phkResult, L"FullyExcluded", &v44, 0);
            v12 = 391;
            if ( DWORD < 0 )
              goto LABEL_58;
            v40 = 391;
            *((_DWORD *)v22 + 8) = v44 == 1;
            DWORD = SxRegReadDWORD(phkResult, L"AllLibsExcluded", &v44, 0);
            v12 = 394;
            if ( DWORD < 0 )
              goto LABEL_58;
            v40 = 394;
            *((_DWORD *)v22 + 7) = v44 == 1;
            MultiString = SxRegReadMultiString(phkResult, L"LibrariesNotToBackup", (unsigned __int16 **)&pv);
            if ( (int)(MultiString + 0x80000000) >= 0 && MultiString != -2147024894 )
            {
              DWORD = MultiString;
              v12 = 399;
              v9 = (unsigned __int16 *)pv;
              goto LABEL_58;
            }
            DWORD = 0;
            v40 = 399;
            v9 = (unsigned __int16 *)pv;
            if ( MultiString >= 0 )
            {
              v25 = pv;
              if ( *(_WORD *)pv )
              {
                v26 = 0;
                do
                {
                  ++v26;
                  v27 = -1;
                  do
                    ++v27;
                  while ( v25[v27] );
                  v25 += v27 + 1;
                }
                while ( *v25 );
                if ( v26 )
                {
                  *((_DWORD *)v22 + 2) = v26;
                  v28 = 8LL * v26;
                  v29 = CoTaskMemAlloc(v28);
                  *((_QWORD *)v22 + 2) = v29;
                  v30 = v29 == 0;
                  v12 = 416;
                  if ( !v30 )
                  {
                    DWORD = 0;
                    v40 = 416;
                    memset_0(*((void **)v22 + 2), 0, v28);
                    v31 = v9;
                    while ( 1 )
                    {
                      if ( !*v31 )
                      {
                        i = (unsigned int)a5;
                        goto LABEL_53;
                      }
                      DWORD = SdSafeDuplicateStr((unsigned __int16 **)(*((_QWORD *)v22 + 2) + 8LL * v23), v31);
                      v12 = 424;
                      if ( DWORD < 0 )
                        break;
                      v40 = 424;
                      v32 = -1;
                      do
                        ++v32;
                      while ( v31[v32] );
                      v31 += v32 + 1;
                      ++v23;
                    }
                    v8 = lpName;
                    goto LABEL_69;
                  }
                  DWORD = -2147024882;
LABEL_58:
                  v8 = lpName;
                  goto LABEL_69;
                }
              }
LABEL_53:
              CoTaskMemFree(v9);
              v9 = 0;
              pv = 0;
            }
            if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              RegCloseKey(phkResult);
              phkResult = 0;
            }
          }
          v19 = (unsigned int)cSubKeys;
LABEL_64:
          *a3 = v19;
          *a4 = v10;
          v10 = 0;
          LODWORD(cSubKeys) = 0;
        }
        else
        {
          DWORD = -2147024882;
          v41 = 366;
        }
        v8 = lpName;
      }
      else
      {
        DWORD = -2147024882;
        v41 = 362;
        v8 = 0;
      }
    }
    else
    {
      DWORD = 0;
      v40 = 358;
    }
  }
  CleanupBackupUsers((unsigned int)cSubKeys, v10);
  CoTaskMemFree(v10);
  CoTaskMemFree(v8);
  CoTaskMemFree(v9);
  v33 = DWORD;
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&DWORD);
  return v33;
}

```

## disassembly

```asm
0x180059924  mov     [rsp-8+cSubKeys], rcx
0x180059929  push    rbp
0x18005992a  push    rbx
0x18005992b  push    rsi
0x18005992c  push    rdi
0x18005992d  push    r12
0x18005992f  push    r13
0x180059931  push    r14
0x180059933  push    r15
0x180059935  lea     rbp, [rsp-17h]
0x18005993a  sub     rsp, 0C8h
0x180059941  mov     r12, r9
0x180059944  mov     r13, r8
0x180059947  mov     rdi, rdx
0x18005994a  mov     r9d, 1; unsigned __int16
0x180059950  mov     r8d, 145h; unsigned __int16
0x180059956  lea     rdx, aCsdbackupconfi_22; "CSdBackupConfigImpl::_ReadUserSettings"
0x18005995d  lea     rcx, [rbp+4Fh+var_80]; this
0x180059961  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180059966  xor     edx, edx
0x180059968  mov     [rbp+4Fh+hKey], rdx
0x18005996c  mov     [rbp+4Fh+var_98], rdx
0x180059970  mov     dword ptr [rbp+4Fh+cSubKeys], edx
0x180059973  mov     [rbp+4Fh+cbMaxSubKeyLen], edx
0x180059976  mov     [rbp+4Fh+cchName], edx
0x180059979  mov     esi, edx
0x18005997b  mov     r14d, edx
0x18005997e  mov     [rbp+4Fh+pv], rdx
0x180059982  mov     r15d, edx
0x180059985  mov     [rbp+4Fh+arg_10], edx
0x180059988  test    r13, r13
0x18005998b  jz      short loc_180059991
0x18005998d  mov     [r13+0], edx
0x180059991  test    r12, r12
0x180059994  jz      short loc_18005999A
0x180059996  mov     [r12], rdx
0x18005999a  mov     rbx, [rbp+4Fh+arg_20]
0x18005999e  test    rbx, rbx
0x1800599a1  jz      short loc_1800599A5
0x1800599a3  mov     [rbx], edx
0x1800599a5  mov     eax, 15Bh
0x1800599aa  test    rdi, rdi
0x1800599ad  jz      loc_180059E53
0x1800599b3  mov     [rbp+4Fh+var_7C], ax
0x1800599b7  mov     eax, 15Ch
0x1800599bc  test    r13, r13
0x1800599bf  jz      loc_180059E53
0x1800599c5  mov     [rbp+4Fh+var_7C], ax
0x1800599c9  mov     eax, 15Dh
0x1800599ce  test    r12, r12
0x1800599d1  jz      loc_180059E53
0x1800599d7  mov     [rbp+4Fh+var_80], edx
0x1800599da  mov     [rbp+4Fh+var_7C], ax
0x1800599de  lea     rax, [rbp+4Fh+hKey]
0x1800599e2  mov     [rsp+100h+phkResult], rax; phkResult
0x1800599e7  mov     r9d, 20019h; samDesired
0x1800599ed  xor     r8d, r8d; ulOptions
0x1800599f0  lea     rdx, c_wszSafedocsScheduleUsers; "UserDataExclusions"
0x1800599f7  mov     rcx, rdi; hKey
0x1800599fa  call    cs:__imp_RegOpenKeyExW
0x180059a00  xor     edi, edi
0x180059a02  test    eax, eax
0x180059a04  jle     short loc_180059A0E
0x180059a06  movzx   eax, ax
0x180059a09  or      eax, 80070000h
0x180059a0e  mov     [rbp+4Fh+var_80], eax
0x180059a11  test    eax, eax
0x180059a13  mov     eax, 15Fh
0x180059a18  js      loc_180059E5C
0x180059a1e  mov     [rbp+4Fh+var_7C], ax
0x180059a22  mov     [rsp+100h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180059a27  mov     [rsp+100h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180059a2c  mov     [rsp+100h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x180059a31  mov     [rsp+100h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x180059a36  mov     [rsp+100h+lpcValues], rdi; lpcValues
0x180059a3b  mov     [rsp+100h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180059a40  lea     rax, [rbp+4Fh+cbMaxSubKeyLen]
0x180059a44  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180059a49  lea     rax, [rbp+4Fh+cSubKeys]
0x180059a4d  mov     [rsp+100h+phkResult], rax; lpcSubKeys
0x180059a52  xor     r9d, r9d; lpReserved
0x180059a55  xor     r8d, r8d; lpcchClass
0x180059a58  xor     edx, edx; lpClass
0x180059a5a  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180059a5e  call    cs:__imp_RegQueryInfoKeyW
0x180059a64  test    eax, eax
0x180059a66  jle     short loc_180059A70
0x180059a68  movzx   eax, ax
0x180059a6b  or      eax, 80070000h
0x180059a70  mov     [rbp+4Fh+var_80], eax
0x180059a73  test    eax, eax
0x180059a75  mov     eax, 160h
0x180059a7a  js      loc_180059E5C
0x180059a80  mov     [rbp+4Fh+var_7C], ax
0x180059a84  xor     r9d, r9d; int
0x180059a87  mov     r8, rbx; unsigned int *
0x180059a8a  lea     rdx, c_wszSafedocsScheduleUsersFullyExcluded; "UsersFullyExcluded"
0x180059a91  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180059a95  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x180059a9a  mov     [rbp+4Fh+var_80], eax
0x180059a9d  test    eax, eax
0x180059a9f  mov     eax, 162h
0x180059aa4  js      loc_180059E5C
0x180059aaa  mov     [rbp+4Fh+var_7C], ax
0x180059aae  cmp     dword ptr [rbp+4Fh+cSubKeys], edi
0x180059ab1  jnz     short loc_180059AC4
0x180059ab3  mov     [rbp+4Fh+var_80], edi
0x180059ab6  mov     eax, 166h
0x180059abb  mov     [rbp+4Fh+var_7C], ax
0x180059abf  jmp     loc_180059E60
0x180059ac4  mov     ecx, [rbp+4Fh+cbMaxSubKeyLen]
0x180059ac7  inc     ecx
0x180059ac9  add     rcx, rcx; cb
0x180059acc  call    cs:__imp_CoTaskMemAlloc
0x180059ad2  mov     [rbp+4Fh+lpName], rax
0x180059ad6  mov     ecx, 16Ah
0x180059adb  test    rax, rax
0x180059ade  jz      loc_180059E43
0x180059ae4  mov     [rbp+4Fh+var_80], edi
0x180059ae7  mov     [rbp+4Fh+var_7C], cx
0x180059aeb  mov     r8d, [rbp+4Fh+cbMaxSubKeyLen]
0x180059aef  inc     r8d
0x180059af2  add     r8, r8; Size
0x180059af5  xor     edx, edx; Val
0x180059af7  mov     rcx, rax; void *
0x180059afa  call    memset_0
0x180059aff  mov     eax, dword ptr [rbp+4Fh+cSubKeys]
0x180059b02  lea     rcx, [rax+rax*4]
0x180059b06  shl     rcx, 3; cb
0x180059b0a  call    cs:__imp_CoTaskMemAlloc
0x180059b10  mov     r15, rax
0x180059b13  mov     ecx, 16Eh
0x180059b18  test    rax, rax
0x180059b1b  jz      loc_180059E32
0x180059b21  mov     [rbp+4Fh+var_80], edi
0x180059b24  mov     [rbp+4Fh+var_7C], cx
0x180059b28  mov     ecx, dword ptr [rbp+4Fh+cSubKeys]
0x180059b2b  lea     r8, [rcx+rcx*4]
0x180059b2f  shl     r8, 3; Size
0x180059b33  xor     edx, edx; Val
0x180059b35  mov     rcx, rax; void *
0x180059b38  call    memset_0
0x180059b3d  mov     ebx, edi
0x180059b3f  mov     dword ptr [rbp+4Fh+arg_20], ebx
0x180059b42  mov     eax, dword ptr [rbp+4Fh+cSubKeys]
0x180059b45  cmp     ebx, eax
0x180059b47  jnb     loc_180059E22
0x180059b4d  mov     eax, [rbp+4Fh+cbMaxSubKeyLen]
0x180059b50  inc     eax
0x180059b52  mov     [rbp+4Fh+cchName], eax
0x180059b55  mov     [rsp+100h+lpcValues], rdi; lpftLastWriteTime
0x180059b5a  mov     [rsp+100h+lpcbMaxClassLen], rdi; lpcchClass
0x180059b5f  mov     [rsp+100h+lpcbMaxSubKeyLen], rdi; lpClass
0x180059b64  mov     [rsp+100h+phkResult], rdi; lpReserved
0x180059b69  lea     r9, [rbp+4Fh+cchName]; lpcchName
0x180059b6d  mov     rdi, [rbp+4Fh+lpName]
0x180059b71  mov     r8, rdi; lpName
0x180059b74  mov     edx, ebx; dwIndex
0x180059b76  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180059b7a  call    cs:__imp_RegEnumKeyExW
0x180059b80  cmp     eax, 103h
0x180059b85  jz      loc_180059E1D
0x180059b8b  xor     esi, esi
0x180059b8d  test    eax, eax
0x180059b8f  jle     short loc_180059B99
0x180059b91  movzx   eax, ax
0x180059b94  or      eax, 80070000h
0x180059b99  mov     [rbp+4Fh+var_80], eax
0x180059b9c  test    eax, eax
0x180059b9e  mov     eax, 17Dh
0x180059ba3  js      loc_180059E18
0x180059ba9  mov     [rbp+4Fh+var_7C], ax
0x180059bad  mov     rcx, [rbp+4Fh+var_98]; hKey
0x180059bb1  lea     rax, [rcx-1]
0x180059bb5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180059bb9  ja      short loc_180059BC5
0x180059bbb  call    cs:__imp_RegCloseKey
0x180059bc1  mov     [rbp+4Fh+var_98], rsi
0x180059bc5  lea     rax, [rbp+4Fh+var_98]
0x180059bc9  mov     [rsp+100h+phkResult], rax; phkResult
0x180059bce  mov     r9d, 20019h; samDesired
0x180059bd4  xor     r8d, r8d; ulOptions
0x180059bd7  mov     rdx, rdi; lpSubKey
0x180059bda  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180059bde  call    cs:__imp_RegOpenKeyExW
0x180059be4  test    eax, eax
0x180059be6  jle     short loc_180059BF0
0x180059be8  movzx   eax, ax
0x180059beb  or      eax, 80070000h
0x180059bf0  mov     [rbp+4Fh+var_80], eax
0x180059bf3  test    eax, eax
0x180059bf5  js      loc_180059E13
0x180059bfb  mov     eax, ebx
0x180059bfd  lea     rcx, [rax+rax*4]
0x180059c01  lea     rsi, [r15+rcx*8]
0x180059c05  mov     eax, 181h
0x180059c0a  mov     [rbp+4Fh+var_7C], ax
0x180059c0e  mov     rdx, rdi; unsigned __int16 *
0x180059c11  mov     rcx, rsi; unsigned __int16 **
0x180059c14  call    ?SdSafeDuplicateStr@@YAJPEAPEAGPEBG@Z; SdSafeDuplicateStr(ushort * *,ushort const *)
0x180059c19  mov     [rbp+4Fh+var_80], eax
0x180059c1c  xor     edi, edi
0x180059c1e  test    eax, eax
0x180059c20  mov     eax, 183h
0x180059c25  js      loc_180059DFE
0x180059c2b  mov     [rbp+4Fh+var_7C], ax
0x180059c2f  lea     r8, [rsi+18h]; unsigned int *
0x180059c33  xor     r9d, r9d; int
0x180059c36  lea     rdx, c_wszSafedocsScheduleUserFoldersNotToBackup; "FoldersNotToBackup"
0x180059c3d  mov     rcx, [rbp+4Fh+var_98]; hKey
0x180059c41  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x180059c46  mov     [rbp+4Fh+var_80], eax
0x180059c49  test    eax, eax
0x180059c4b  mov     eax, 185h
0x180059c50  js      loc_180059DFE
0x180059c56  mov     [rbp+4Fh+var_7C], ax
0x180059c5a  xor     r9d, r9d; int
0x180059c5d  lea     r8, [rbp+4Fh+arg_10]; unsigned int *
0x180059c61  lea     rdx, c_wszSafedocsScheduleUserFullyExcluded; "FullyExcluded"
0x180059c68  mov     rcx, [rbp+4Fh+var_98]; hKey
0x180059c6c  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x180059c71  mov     [rbp+4Fh+var_80], eax
0x180059c74  test    eax, eax
0x180059c76  mov     eax, 187h
0x180059c7b  js      loc_180059DFE
0x180059c81  mov     [rbp+4Fh+var_7C], ax
0x180059c85  mov     eax, edi
0x180059c87  cmp     [rbp+4Fh+arg_10], 1
0x180059c8b  setz    al
0x180059c8e  mov     [rsi+20h], eax
0x180059c91  xor     r9d, r9d; int
0x180059c94  lea     r8, [rbp+4Fh+arg_10]; unsigned int *
0x180059c98  lea     rdx, c_wszSafedocsScheduleUserAllLibsExcluded; "AllLibsExcluded"
0x180059c9f  mov     rcx, [rbp+4Fh+var_98]; hKey
0x180059ca3  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x180059ca8  mov     [rbp+4Fh+var_80], eax
0x180059cab  test    eax, eax
0x180059cad  mov     eax, 18Ah
0x180059cb2  js      loc_180059DFE
0x180059cb8  mov     [rbp+4Fh+var_7C], ax
0x180059cbc  mov     eax, edi
0x180059cbe  cmp     [rbp+4Fh+arg_10], 1
0x180059cc2  setz    al
0x180059cc5  mov     [rsi+1Ch], eax
0x180059cc8  lea     r8, [rbp+4Fh+pv]; unsigned __int16 **
0x180059ccc  lea     rdx, c_wszSafedocsScheduleUserLibrariesNotToBackup; "LibrariesNotToBackup"
0x180059cd3  mov     rcx, [rbp+4Fh+var_98]; hKey
0x180059cd7  call    ?SxRegReadMultiString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; SxRegReadMultiString(HKEY__ *,ushort const *,ushort * *)
0x180059cdc  mov     edx, 80000000h
0x180059ce1  lea     ecx, [rax+rdx]
0x180059ce4  test    edx, ecx
0x180059ce6  jnz     short loc_180059CF3
0x180059ce8  cmp     eax, 80070002h
0x180059ced  jnz     loc_180059DF2
0x180059cf3  mov     [rbp+4Fh+var_80], edi
0x180059cf6  mov     ecx, 18Fh
0x180059cfb  mov     [rbp+4Fh+var_7C], cx
0x180059cff  mov     r14, [rbp+4Fh+pv]
0x180059d03  test    eax, eax
0x180059d05  js      loc_180059DD3
0x180059d0b  mov     rax, r14
0x180059d0e  cmp     [r14], di
0x180059d12  jz      loc_180059DC3
0x180059d18  mov     ecx, edi
0x180059d1a  inc     ecx
0x180059d1c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180059d20  inc     rdx
0x180059d23  cmp     [rax+rdx*2], di
0x180059d27  jnz     short loc_180059D20
0x180059d29  lea     rax, [rax+rdx*2]
0x180059d2d  add     rax, 2
0x180059d31  cmp     [rax], di
0x180059d34  jnz     short loc_180059D1A
0x180059d36  test    ecx, ecx
0x180059d38  jz      loc_180059DC3
0x180059d3e  mov     [rsi+8], ecx
0x180059d41  mov     ebx, ecx
0x180059d43  shl     rbx, 3
0x180059d47  mov     rcx, rbx; cb
0x180059d4a  call    cs:__imp_CoTaskMemAlloc
0x180059d50  mov     [rsi+10h], rax
0x180059d54  test    rax, rax
0x180059d57  mov     eax, 1A0h
0x180059d5c  jz      loc_180059E0A
0x180059d62  mov     [rbp+4Fh+var_80], edi
0x180059d65  mov     [rbp+4Fh+var_7C], ax
0x180059d69  mov     r8, rbx; Size
0x180059d6c  xor     edx, edx; Val
0x180059d6e  mov     rcx, [rsi+10h]; void *
0x180059d72  call    memset_0
0x180059d77  mov     rbx, r14
0x180059d7a  xor     ecx, ecx
0x180059d7c  cmp     [rbx], cx
0x180059d7f  jz      short loc_180059DBE
0x180059d81  mov     ecx, edi
0x180059d83  mov     rax, [rsi+10h]
0x180059d87  lea     rcx, [rax+rcx*8]; unsigned __int16 **
0x180059d8b  mov     rdx, rbx; unsigned __int16 *
0x180059d8e  call    ?SdSafeDuplicateStr@@YAJPEAPEAGPEBG@Z; SdSafeDuplicateStr(ushort * *,ushort const *)
0x180059d93  mov     [rbp+4Fh+var_80], eax
  ... truncated ...
```
