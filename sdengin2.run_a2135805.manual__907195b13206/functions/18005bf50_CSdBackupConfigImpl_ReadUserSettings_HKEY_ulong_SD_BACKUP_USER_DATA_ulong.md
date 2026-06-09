# CSdBackupConfigImpl::_ReadUserSettings(HKEY__ *,ulong *,_SD_BACKUP_USER_DATA * *,ulong *)

- ea: `0x18005bf50`
- end: `0x18005c55f`
- name: `?_ReadUserSettings@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEAKPEAPEAU_SD_BACKUP_USER_DATA@@1@Z`
- size: `1551`
- prototype: `int(CSdBackupConfigImpl *__hidden this, HKEY, unsigned int *, struct _SD_BACKUP_USER_DATA **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18005b46c`

## callees

- `0x18005bf50`
- `0x180072e08`
- `0x180072f14`
- `0x1800739f8`
- `0x180091d64`
- `0x180098a5c`
- `0x180098bc8`
- `0x1800cf56a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c205`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c443`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c511`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c52f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c205`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c443`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c511`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c52f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c026`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c22e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c026`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c22e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005c1be`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005c1be`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005c090`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005c090`
- `ole32!CoTaskMemFree` at `0x18005c422`
- `ole32!CoTaskMemFree` at `0x18005c4d6`
- `ole32!CoTaskMemFree` at `0x18005c4e5`
- `ole32!CoTaskMemFree` at `0x18005c4f4`
- `ole32!CoTaskMemFree` at `0x18005c422`
- `ole32!CoTaskMemFree` at `0x18005c4d6`
- `ole32!CoTaskMemFree` at `0x18005c4e5`
- `ole32!CoTaskMemFree` at `0x18005c4f4`
- `ole32!CoTaskMemAlloc` at `0x18005c104`
- `ole32!CoTaskMemAlloc` at `0x18005c148`
- `ole32!CoTaskMemAlloc` at `0x18005c3a0`
- `ole32!CoTaskMemAlloc` at `0x18005c104`
- `ole32!CoTaskMemAlloc` at `0x18005c148`
- `ole32!CoTaskMemAlloc` at `0x18005c3a0`

## string_xrefs

- `0x18005bf82`: `CSdBackupConfigImpl::_ReadUserSettings`

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
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&DWORD,
    "CSdBackupConfigImpl::_ReadUserSettings",
    0x145u,
    1u);
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
0x18005bf50  mov     [rsp-8+cSubKeys], rcx
0x18005bf55  push    rbp
0x18005bf56  push    rbx
0x18005bf57  push    rsi
0x18005bf58  push    rdi
0x18005bf59  push    r12
0x18005bf5b  push    r13
0x18005bf5d  push    r14
0x18005bf5f  push    r15
0x18005bf61  lea     rbp, [rsp-17h]
0x18005bf66  sub     rsp, 0C8h
0x18005bf6d  mov     r12, r9
0x18005bf70  mov     r13, r8
0x18005bf73  mov     rdi, rdx
0x18005bf76  mov     r9d, 1; unsigned __int16
0x18005bf7c  mov     r8d, 145h; unsigned __int16
0x18005bf82  lea     rdx, aCsdbackupconfi_22; "CSdBackupConfigImpl::_ReadUserSettings"
0x18005bf89  lea     rcx, [rbp+4Fh+var_80]; this
0x18005bf8d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005bf92  xor     edx, edx
0x18005bf94  mov     [rbp+4Fh+hKey], rdx
0x18005bf98  mov     [rbp+4Fh+var_98], rdx
0x18005bf9c  mov     dword ptr [rbp+4Fh+cSubKeys], edx
0x18005bf9f  mov     [rbp+4Fh+cbMaxSubKeyLen], edx
0x18005bfa2  mov     [rbp+4Fh+cchName], edx
0x18005bfa5  mov     esi, edx
0x18005bfa7  mov     r14d, edx
0x18005bfaa  mov     [rbp+4Fh+pv], rdx
0x18005bfae  mov     r15d, edx
0x18005bfb1  mov     [rbp+4Fh+arg_10], edx
0x18005bfb4  test    r13, r13
0x18005bfb7  jz      short loc_18005BFBD
0x18005bfb9  mov     [r13+0], edx
0x18005bfbd  test    r12, r12
0x18005bfc0  jz      short loc_18005BFC6
0x18005bfc2  mov     [r12], rdx
0x18005bfc6  mov     rbx, [rbp+4Fh+arg_20]
0x18005bfca  test    rbx, rbx
0x18005bfcd  jz      short loc_18005BFD1
0x18005bfcf  mov     [rbx], edx
0x18005bfd1  mov     eax, 15Bh
0x18005bfd6  test    rdi, rdi
0x18005bfd9  jz      loc_18005C4BB
0x18005bfdf  mov     [rbp+4Fh+var_7C], ax
0x18005bfe3  mov     eax, 15Ch
0x18005bfe8  test    r13, r13
0x18005bfeb  jz      loc_18005C4BB
0x18005bff1  mov     [rbp+4Fh+var_7C], ax
0x18005bff5  mov     eax, 15Dh
0x18005bffa  test    r12, r12
0x18005bffd  jz      loc_18005C4BB
0x18005c003  mov     [rbp+4Fh+var_80], edx
0x18005c006  mov     [rbp+4Fh+var_7C], ax
0x18005c00a  lea     rax, [rbp+4Fh+hKey]
0x18005c00e  mov     [rsp+100h+phkResult], rax; phkResult
0x18005c013  mov     r9d, 20019h; samDesired
0x18005c019  xor     r8d, r8d; ulOptions
0x18005c01c  lea     rdx, c_wszSafedocsScheduleUsers; "UserDataExclusions"
0x18005c023  mov     rcx, rdi; hKey
0x18005c026  call    cs:__imp_RegOpenKeyExW
0x18005c02d  nop     dword ptr [rax+rax+00h]
0x18005c032  xor     edi, edi
0x18005c034  test    eax, eax
0x18005c036  jle     short loc_18005C040
0x18005c038  movzx   eax, ax
0x18005c03b  or      eax, 80070000h
0x18005c040  mov     [rbp+4Fh+var_80], eax
0x18005c043  test    eax, eax
0x18005c045  mov     eax, 15Fh
0x18005c04a  js      loc_18005C4C4
0x18005c050  mov     [rbp+4Fh+var_7C], ax
0x18005c054  mov     [rsp+100h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18005c059  mov     [rsp+100h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x18005c05e  mov     [rsp+100h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x18005c063  mov     [rsp+100h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x18005c068  mov     [rsp+100h+lpcValues], rdi; lpcValues
0x18005c06d  mov     [rsp+100h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x18005c072  lea     rax, [rbp+4Fh+cbMaxSubKeyLen]
0x18005c076  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18005c07b  lea     rax, [rbp+4Fh+cSubKeys]
0x18005c07f  mov     [rsp+100h+phkResult], rax; lpcSubKeys
0x18005c084  xor     r9d, r9d; lpReserved
0x18005c087  xor     r8d, r8d; lpcchClass
0x18005c08a  xor     edx, edx; lpClass
0x18005c08c  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18005c090  call    cs:__imp_RegQueryInfoKeyW
0x18005c097  nop     dword ptr [rax+rax+00h]
0x18005c09c  test    eax, eax
0x18005c09e  jle     short loc_18005C0A8
0x18005c0a0  movzx   eax, ax
0x18005c0a3  or      eax, 80070000h
0x18005c0a8  mov     [rbp+4Fh+var_80], eax
0x18005c0ab  test    eax, eax
0x18005c0ad  mov     eax, 160h
0x18005c0b2  js      loc_18005C4C4
0x18005c0b8  mov     [rbp+4Fh+var_7C], ax
0x18005c0bc  xor     r9d, r9d; int
0x18005c0bf  mov     r8, rbx; unsigned int *
0x18005c0c2  lea     rdx, c_wszSafedocsScheduleUsersFullyExcluded; "UsersFullyExcluded"
0x18005c0c9  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18005c0cd  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18005c0d2  mov     [rbp+4Fh+var_80], eax
0x18005c0d5  test    eax, eax
0x18005c0d7  mov     eax, 162h
0x18005c0dc  js      loc_18005C4C4
0x18005c0e2  mov     [rbp+4Fh+var_7C], ax
0x18005c0e6  cmp     dword ptr [rbp+4Fh+cSubKeys], edi
0x18005c0e9  jnz     short loc_18005C0FC
0x18005c0eb  mov     [rbp+4Fh+var_80], edi
0x18005c0ee  mov     eax, 166h
0x18005c0f3  mov     [rbp+4Fh+var_7C], ax
0x18005c0f7  jmp     loc_18005C4C8
0x18005c0fc  mov     ecx, [rbp+4Fh+cbMaxSubKeyLen]
0x18005c0ff  inc     ecx
0x18005c101  add     rcx, rcx; cb
0x18005c104  call    cs:__imp_CoTaskMemAlloc
0x18005c10b  nop     dword ptr [rax+rax+00h]
0x18005c110  mov     [rbp+4Fh+lpName], rax
0x18005c114  mov     ecx, 16Ah
0x18005c119  test    rax, rax
0x18005c11c  jz      loc_18005C4AB
0x18005c122  mov     [rbp+4Fh+var_80], edi
0x18005c125  mov     [rbp+4Fh+var_7C], cx
0x18005c129  mov     r8d, [rbp+4Fh+cbMaxSubKeyLen]
0x18005c12d  inc     r8d
0x18005c130  add     r8, r8; Size
0x18005c133  xor     edx, edx; Val
0x18005c135  mov     rcx, rax; void *
0x18005c138  call    memset_0
0x18005c13d  mov     eax, dword ptr [rbp+4Fh+cSubKeys]
0x18005c140  lea     rcx, [rax+rax*4]
0x18005c144  shl     rcx, 3; cb
0x18005c148  call    cs:__imp_CoTaskMemAlloc
0x18005c14f  nop     dword ptr [rax+rax+00h]
0x18005c154  mov     r15, rax
0x18005c157  mov     ecx, 16Eh
0x18005c15c  test    rax, rax
0x18005c15f  jz      loc_18005C49A
0x18005c165  mov     [rbp+4Fh+var_80], edi
0x18005c168  mov     [rbp+4Fh+var_7C], cx
0x18005c16c  mov     ecx, dword ptr [rbp+4Fh+cSubKeys]
0x18005c16f  lea     r8, [rcx+rcx*4]
0x18005c173  shl     r8, 3; Size
0x18005c177  xor     edx, edx; Val
0x18005c179  mov     rcx, rax; void *
0x18005c17c  call    memset_0
0x18005c181  mov     ebx, edi
0x18005c183  mov     dword ptr [rbp+4Fh+arg_20], ebx
0x18005c186  mov     eax, dword ptr [rbp+4Fh+cSubKeys]
0x18005c189  cmp     ebx, eax
0x18005c18b  jnb     loc_18005C48A
0x18005c191  mov     eax, [rbp+4Fh+cbMaxSubKeyLen]
0x18005c194  inc     eax
0x18005c196  mov     [rbp+4Fh+cchName], eax
0x18005c199  mov     [rsp+100h+lpcValues], rdi; lpftLastWriteTime
0x18005c19e  mov     [rsp+100h+lpcbMaxClassLen], rdi; lpcchClass
0x18005c1a3  mov     [rsp+100h+lpcbMaxSubKeyLen], rdi; lpClass
0x18005c1a8  mov     [rsp+100h+phkResult], rdi; lpReserved
0x18005c1ad  lea     r9, [rbp+4Fh+cchName]; lpcchName
0x18005c1b1  mov     rdi, [rbp+4Fh+lpName]
0x18005c1b5  mov     r8, rdi; lpName
0x18005c1b8  mov     edx, ebx; dwIndex
0x18005c1ba  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18005c1be  call    cs:__imp_RegEnumKeyExW
0x18005c1c5  nop     dword ptr [rax+rax+00h]
0x18005c1ca  cmp     eax, 103h
0x18005c1cf  jz      loc_18005C485
0x18005c1d5  xor     esi, esi
0x18005c1d7  test    eax, eax
0x18005c1d9  jle     short loc_18005C1E3
0x18005c1db  movzx   eax, ax
0x18005c1de  or      eax, 80070000h
0x18005c1e3  mov     [rbp+4Fh+var_80], eax
0x18005c1e6  test    eax, eax
0x18005c1e8  mov     eax, 17Dh
0x18005c1ed  js      loc_18005C480
0x18005c1f3  mov     [rbp+4Fh+var_7C], ax
0x18005c1f7  mov     rcx, [rbp+4Fh+var_98]; hKey
0x18005c1fb  lea     rax, [rcx-1]
0x18005c1ff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005c203  ja      short loc_18005C215
0x18005c205  call    cs:__imp_RegCloseKey
0x18005c20c  nop     dword ptr [rax+rax+00h]
0x18005c211  mov     [rbp+4Fh+var_98], rsi
0x18005c215  lea     rax, [rbp+4Fh+var_98]
0x18005c219  mov     [rsp+100h+phkResult], rax; phkResult
0x18005c21e  mov     r9d, 20019h; samDesired
0x18005c224  xor     r8d, r8d; ulOptions
0x18005c227  mov     rdx, rdi; lpSubKey
0x18005c22a  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18005c22e  call    cs:__imp_RegOpenKeyExW
0x18005c235  nop     dword ptr [rax+rax+00h]
0x18005c23a  test    eax, eax
0x18005c23c  jle     short loc_18005C246
0x18005c23e  movzx   eax, ax
0x18005c241  or      eax, 80070000h
0x18005c246  mov     [rbp+4Fh+var_80], eax
0x18005c249  test    eax, eax
0x18005c24b  js      loc_18005C47B
0x18005c251  mov     eax, ebx
0x18005c253  lea     rcx, [rax+rax*4]
0x18005c257  lea     rsi, [r15+rcx*8]
0x18005c25b  mov     eax, 181h
0x18005c260  mov     [rbp+4Fh+var_7C], ax
0x18005c264  mov     rdx, rdi; unsigned __int16 *
0x18005c267  mov     rcx, rsi; unsigned __int16 **
0x18005c26a  call    ?SdSafeDuplicateStr@@YAJPEAPEAGPEBG@Z; SdSafeDuplicateStr(ushort * *,ushort const *)
0x18005c26f  mov     [rbp+4Fh+var_80], eax
0x18005c272  xor     edi, edi
0x18005c274  test    eax, eax
0x18005c276  mov     eax, 183h
0x18005c27b  js      loc_18005C466
0x18005c281  mov     [rbp+4Fh+var_7C], ax
0x18005c285  lea     r8, [rsi+18h]; unsigned int *
0x18005c289  xor     r9d, r9d; int
0x18005c28c  lea     rdx, c_wszSafedocsScheduleUserFoldersNotToBackup; "FoldersNotToBackup"
0x18005c293  mov     rcx, [rbp+4Fh+var_98]; hKey
0x18005c297  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18005c29c  mov     [rbp+4Fh+var_80], eax
0x18005c29f  test    eax, eax
0x18005c2a1  mov     eax, 185h
0x18005c2a6  js      loc_18005C466
0x18005c2ac  mov     [rbp+4Fh+var_7C], ax
0x18005c2b0  xor     r9d, r9d; int
0x18005c2b3  lea     r8, [rbp+4Fh+arg_10]; unsigned int *
0x18005c2b7  lea     rdx, c_wszSafedocsScheduleUserFullyExcluded; "FullyExcluded"
0x18005c2be  mov     rcx, [rbp+4Fh+var_98]; hKey
0x18005c2c2  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18005c2c7  mov     [rbp+4Fh+var_80], eax
0x18005c2ca  test    eax, eax
0x18005c2cc  mov     eax, 187h
0x18005c2d1  js      loc_18005C466
0x18005c2d7  mov     [rbp+4Fh+var_7C], ax
0x18005c2db  mov     eax, edi
0x18005c2dd  cmp     [rbp+4Fh+arg_10], 1
0x18005c2e1  setz    al
0x18005c2e4  mov     [rsi+20h], eax
0x18005c2e7  xor     r9d, r9d; int
0x18005c2ea  lea     r8, [rbp+4Fh+arg_10]; unsigned int *
0x18005c2ee  lea     rdx, c_wszSafedocsScheduleUserAllLibsExcluded; "AllLibsExcluded"
0x18005c2f5  mov     rcx, [rbp+4Fh+var_98]; hKey
0x18005c2f9  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18005c2fe  mov     [rbp+4Fh+var_80], eax
0x18005c301  test    eax, eax
0x18005c303  mov     eax, 18Ah
0x18005c308  js      loc_18005C466
0x18005c30e  mov     [rbp+4Fh+var_7C], ax
0x18005c312  mov     eax, edi
0x18005c314  cmp     [rbp+4Fh+arg_10], 1
0x18005c318  setz    al
0x18005c31b  mov     [rsi+1Ch], eax
0x18005c31e  lea     r8, [rbp+4Fh+pv]; unsigned __int16 **
0x18005c322  lea     rdx, c_wszSafedocsScheduleUserLibrariesNotToBackup; "LibrariesNotToBackup"
0x18005c329  mov     rcx, [rbp+4Fh+var_98]; hKey
0x18005c32d  call    ?SxRegReadMultiString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; SxRegReadMultiString(HKEY__ *,ushort const *,ushort * *)
0x18005c332  mov     edx, 80000000h
0x18005c337  lea     ecx, [rax+rdx]
0x18005c33a  test    edx, ecx
0x18005c33c  jnz     short loc_18005C349
0x18005c33e  cmp     eax, 80070002h
0x18005c343  jnz     loc_18005C45A
0x18005c349  mov     [rbp+4Fh+var_80], edi
0x18005c34c  mov     ecx, 18Fh
0x18005c351  mov     [rbp+4Fh+var_7C], cx
0x18005c355  mov     r14, [rbp+4Fh+pv]
0x18005c359  test    eax, eax
0x18005c35b  js      loc_18005C435
0x18005c361  mov     rax, r14
0x18005c364  cmp     [r14], di
0x18005c368  jz      loc_18005C41F
0x18005c36e  mov     ecx, edi
0x18005c370  inc     ecx
0x18005c372  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005c376  inc     rdx
0x18005c379  cmp     [rax+rdx*2], di
0x18005c37d  jnz     short loc_18005C376
0x18005c37f  lea     rax, [rax+rdx*2]
0x18005c383  add     rax, 2
0x18005c387  cmp     [rax], di
0x18005c38a  jnz     short loc_18005C370
0x18005c38c  test    ecx, ecx
0x18005c38e  jz      loc_18005C41F
0x18005c394  mov     [rsi+8], ecx
0x18005c397  mov     ebx, ecx
0x18005c399  shl     rbx, 3
0x18005c39d  mov     rcx, rbx; cb
0x18005c3a0  call    cs:__imp_CoTaskMemAlloc
0x18005c3a7  nop     dword ptr [rax+rax+00h]
0x18005c3ac  mov     [rsi+10h], rax
0x18005c3b0  test    rax, rax
0x18005c3b3  mov     eax, 1A0h
0x18005c3b8  jz      loc_18005C472
0x18005c3be  mov     [rbp+4Fh+var_80], edi
0x18005c3c1  mov     [rbp+4Fh+var_7C], ax
0x18005c3c5  mov     r8, rbx; Size
0x18005c3c8  xor     edx, edx; Val
0x18005c3ca  mov     rcx, [rsi+10h]; void *
0x18005c3ce  call    memset_0
0x18005c3d3  mov     rbx, r14
0x18005c3d6  xor     ecx, ecx
  ... truncated ...
```
