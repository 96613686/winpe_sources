# CVersionManagerServer::_LogAuditEvent(ushort *,ushort const *,ulong,ulong,ulong,ulong,EXT_SQM_VERSION_STATE,EXT_SQM_VERSION_REASON,int)

- ea: `0x1800a68b8`
- end: `0x1800a6e62`
- name: `?_LogAuditEvent@CVersionManagerServer@@AEAAJPEAGPEBGKKKKW4EXT_SQM_VERSION_STATE@@W4EXT_SQM_VERSION_REASON@@H@Z`
- size: `1450`
- prototype: `int __high(unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, enum EXT_SQM_VERSION_STATE, enum EXT_SQM_VERSION_REASON, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1801046f0`

## callees

- `0x18004d7f0`
- `0x18005789c`
- `0x1800a68b8`
- `0x1800a6e68`
- `0x18010107c`
- `0x1801018e0`
- `0x180103db0`
- `0x1801044f8`
- `0x18011a1bc`
- `0x18012738c`
- `0x180128660`

## import_xrefs

- `msvcrt!strnlen` at `0x1800a6abe`
- `msvcrt!strnlen` at `0x1800a6ad3`
- `msvcrt!strnlen` at `0x1800a6ae8`
- `msvcrt!strnlen` at `0x1800a6b02`
- `msvcrt!strnlen` at `0x1800a6b19`
- `msvcrt!strnlen` at `0x1800a6abe`
- `msvcrt!strnlen` at `0x1800a6ad3`
- `msvcrt!strnlen` at `0x1800a6ae8`
- `msvcrt!strnlen` at `0x1800a6b02`
- `msvcrt!strnlen` at `0x1800a6b19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a6e21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a6e21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a6cb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a6cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6c52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6d26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6d64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6dd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6df9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6c52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6d26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6d64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6dd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6df9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a6deb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a6deb`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800a6c2a`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800a6c2a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a6d53`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a6d53`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a6da1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a6da1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a6c44`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a6c44`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a6d0d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a6d0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a6b44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a6b44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a6bc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a6bcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a6e30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a6bc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a6bcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a6e30`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a692a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a692a`

## string_xrefs

- `0x1800a6a0f`: `EPM Compatible`
- `0x1800a6a08`: `Not EPM Compatible`

## pseudocode

```c
__int64 __fastcall CVersionManagerServer::_LogAuditEvent(
        __int64 a1,
        OLECHAR *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        unsigned int a9,
        int a10)
{
  char *v14; // r12
  SIZE_T v15; // r14
  char *v16; // r15
  unsigned int v17; // r13d
  CVersionManagerServer *v18; // rcx
  int LocalDirectory; // ebx
  int v20; // eax
  unsigned __int64 v21; // rax
  __int64 v22; // rcx
  const char *v23; // r8
  unsigned int v24; // r10d
  const char *v25; // r8
  int v26; // r10d
  int v27; // eax
  unsigned int v28; // r9d
  unsigned int v29; // esi
  unsigned int v30; // ebx
  size_t v31; // r14
  size_t v32; // rsi
  unsigned int v33; // r12d
  size_t v34; // rdi
  size_t v35; // rbx
  size_t v36; // rax
  const char *v37; // r9
  size_t v38; // rdx
  DWORD FileAttributesW; // ebx
  DWORD LastError; // eax
  CVersionManagerServer *v41; // rcx
  __int64 v42; // rbx
  struct _RTL_CRITICAL_SECTION *v43; // r15
  HANDLE FileW; // rsi
  signed int v45; // eax
  SIZE_T v46; // r14
  signed int v47; // eax
  signed int v48; // eax
  bool v49; // [rsp+50h] [rbp-B0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+54h] [rbp-ACh] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v52; // [rsp+60h] [rbp-A0h] BYREF
  char *v53; // [rsp+68h] [rbp-98h] BYREF
  __int64 v54; // [rsp+70h] [rbp-90h]
  char v55[40]; // [rsp+78h] [rbp-88h] BYREF
  char v56[40]; // [rsp+A0h] [rbp-60h] BYREF
  char v57[56]; // [rsp+C8h] [rbp-38h] BYREF
  char String[56]; // [rsp+100h] [rbp+0h] BYREF
  char v59[56]; // [rsp+138h] [rbp+38h] BYREF
  WCHAR pszPath[264]; // [rsp+170h] [rbp+70h] BYREF

  v54 = a1;
  if ( !a3 )
    return 2147942487LL;
  pv = 0;
  v14 = 0;
  NumberOfBytesWritten = 0;
  v15 = 0;
  v53 = 0;
  v16 = 0;
  v52 = 0;
  v17 = 0;
  if ( a2 )
  {
    if ( SysStringLen(a2) > 0x824 )
    {
LABEL_5:
      LocalDirectory = -2147024785;
      goto LABEL_31;
    }
    v20 = CVersionManagerServer::_WideToAnsi(v18, a2, &v53, &v52);
    v16 = v53;
    LocalDirectory = v20;
    if ( v20 < 0 )
      goto LABEL_31;
    v17 = v52;
  }
  v21 = -1;
  do
    ++v21;
  while ( a3[v21] );
  if ( v21 > 0x104 )
    goto LABEL_5;
  LocalDirectory = CVersionManagerServer::_WideToAnsi(0, a3, (char **)&pv, &NumberOfBytesWritten);
  if ( LocalDirectory >= 0 )
  {
    LocalDirectory = CVersionManagerServer::_SqmReasonToString(v22, a9, String);
    if ( LocalDirectory >= 0 )
    {
      if ( a8 )
      {
        if ( a8 == 1 )
        {
          v23 = "Blocked";
          goto LABEL_20;
        }
        if ( a8 == 2 )
        {
          v23 = "Allowed";
          goto LABEL_20;
        }
      }
      v23 = "Unknown";
LABEL_20:
      LocalDirectory = StringCchCopyA(v59, 0x32u, v23);
      if ( LocalDirectory >= 0 )
      {
        v25 = "EPM Compatible";
        if ( !a10 )
          v25 = "Not EPM Compatible";
        LocalDirectory = StringCchCopyA(v57, v24, v25);
        if ( LocalDirectory >= 0 )
        {
          v27 = (unsigned __int16)a4;
          v28 = HIWORD(a4);
          v29 = v26 - 10;
          LocalDirectory = StringCchPrintfA(
                             v56,
                             (unsigned int)(v26 - 10),
                             "%d.%d.%d.%d",
                             v28,
                             v27,
                             HIWORD(a5),
                             (unsigned __int16)a5);
          if ( LocalDirectory >= 0 )
          {
            LocalDirectory = StringCchPrintfA(
                               v55,
                               v29,
                               "%d.%d.%d.%d",
                               HIWORD(a6),
                               (unsigned __int16)a6,
                               HIWORD(a7),
                               (unsigned __int16)a7);
            if ( LocalDirectory >= 0 )
            {
              v30 = v29 + 10;
              v31 = strnlen(String, v29 + 10);
              v32 = strnlen(v59, v29 + 10);
              v33 = v30 - 10;
              v34 = strnlen(v57, v30);
              v35 = strnlen(v56, v30 - 10);
              v36 = strnlen(v55, v33);
              v15 = v32 + v34 + v35 + v36 + v17 + NumberOfBytesWritten + v31 + 9;
              v14 = (char *)CoTaskMemAlloc(v15);
              if ( v14 )
              {
                v37 = (const char *)&Default;
                if ( v16 )
                  v37 = v16;
                LocalDirectory = StringCbPrintfA(
                                   v14,
                                   v15,
                                   "%s,%s,%s,%s,%s,%s,%s\r\n",
                                   v37,
                                   (const char *)pv,
                                   v56,
                                   v55,
                                   v59,
                                   String,
                                   v57);
              }
              else
              {
                LocalDirectory = -2147024882;
              }
            }
          }
        }
      }
    }
  }
LABEL_31:
  CoTaskMemFree(pv);
  CoTaskMemFree(v16);
  if ( LocalDirectory >= 0 )
  {
    if ( v14 )
    {
      if ( v15 )
      {
        LocalDirectory = GetString(SettingStore::IEVALUE_urlmon_ExtVerAuditModeFilePath, pszPath, 260);
        if ( LocalDirectory >= 0 )
        {
          v38 = -1;
          do
            ++v38;
          while ( pszPath[v38] );
          LocalDirectory = PathCchRemoveFileSpec(pszPath, v38);
          if ( LocalDirectory >= 0 )
          {
            FileAttributesW = GetFileAttributesW(pszPath);
            LastError = GetLastError();
            if ( FileAttributesW == -1 )
            {
              if ( LastError != 2
                || (LocalDirectory = CVersionManagerServer::_CreateLocalDirectory(v41, pszPath), LocalDirectory >= 0) )
              {
LABEL_41:
                LocalDirectory = GetString(SettingStore::IEVALUE_urlmon_ExtVerAuditModeFilePath, pszPath, 260);
                if ( LocalDirectory >= 0 )
                {
                  v42 = v54;
                  v49 = 0;
                  v43 = (struct _RTL_CRITICAL_SECTION *)(v54 + 1888);
                  EnterCriticalSection((LPCRITICAL_SECTION)(v54 + 1888));
                  pv = (LPVOID)(v42 + 2056);
                  LocalDirectory = MutexUtils::CAutoMutex::Lock((MutexUtils::CAutoMutex *)&pv, &v49);
                  if ( LocalDirectory >= 0 )
                  {
                    FileW = CreateFileW(pszPath, 0x40000000u, 3u, 0, 4u, 0x80u, 0);
                    if ( FileW == (HANDLE)-1LL )
                    {
                      v48 = GetLastError();
                      LocalDirectory = v48;
                      if ( v48 > 0 )
                        LocalDirectory = (unsigned __int16)v48 | 0x80070000;
                    }
                    else
                    {
                      if ( GetLastError() != 183 || v49 || SetFilePointer(FileW, 0, 0, 2u) != -1 )
                        goto LABEL_50;
                      v45 = GetLastError();
                      LocalDirectory = v45;
                      if ( v45 > 0 )
                        LocalDirectory = (unsigned __int16)v45 | 0x80070000;
                      if ( LocalDirectory >= 0 )
                      {
LABEL_50:
                        v46 = v15 - 1;
                        NumberOfBytesWritten = 0;
                        if ( WriteFile(FileW, v14, v46, &NumberOfBytesWritten, 0) )
                        {
                          if ( NumberOfBytesWritten != v46 )
                            LocalDirectory = -2147024867;
                        }
                        else
                        {
                          v47 = GetLastError();
                          LocalDirectory = v47;
                          if ( v47 > 0 )
                            LocalDirectory = (unsigned __int16)v47 | 0x80070000;
                        }
                      }
                      CloseHandle(FileW);
                    }
                  }
                  MutexUtils::CAutoMutex::~CAutoMutex((MutexUtils::CAutoMutex *)&pv);
                  LeaveCriticalSection(v43);
                }
              }
            }
            else
            {
              if ( (FileAttributesW & 0x10) != 0 )
                goto LABEL_41;
              LocalDirectory = -2147024735;
            }
          }
        }
      }
    }
  }
  CoTaskMemFree(v14);
  return (unsigned int)LocalDirectory;
}

```

## disassembly

```asm
0x1800a68b8  push    rbp
0x1800a68ba  push    rbx
0x1800a68bb  push    rsi
0x1800a68bc  push    rdi
0x1800a68bd  push    r12
0x1800a68bf  push    r13
0x1800a68c1  push    r14
0x1800a68c3  push    r15
0x1800a68c5  lea     rbp, [rsp-298h]
0x1800a68cd  sub     rsp, 398h
0x1800a68d4  mov     rax, cs:__security_cookie
0x1800a68db  xor     rax, rsp
0x1800a68de  mov     [rbp+2D0h+var_50], rax
0x1800a68e5  mov     [rsp+3D0h+var_360], rcx
0x1800a68ea  mov     esi, r9d
0x1800a68ed  xor     ecx, ecx
0x1800a68ef  mov     rdi, r8
0x1800a68f2  mov     rbx, rdx
0x1800a68f5  test    r8, r8
0x1800a68f8  jnz     short loc_1800A6904
0x1800a68fa  mov     eax, 80070057h
0x1800a68ff  jmp     loc_1800A6E3E
0x1800a6904  mov     [rsp+3D0h+pv], rcx
0x1800a6909  mov     r12, rcx
0x1800a690c  mov     [rsp+3D0h+NumberOfBytesWritten], ecx
0x1800a6910  mov     r14, rcx
0x1800a6913  mov     [rsp+3D0h+var_368], rcx
0x1800a6918  mov     r15, rcx
0x1800a691b  mov     [rsp+3D0h+var_370], ecx
0x1800a691f  mov     r13d, ecx
0x1800a6922  test    rbx, rbx
0x1800a6925  jz      short loc_1800A696D
0x1800a6927  mov     rcx, rbx; pbstr
0x1800a692a  call    cs:__imp_SysStringLen
0x1800a6931  nop     dword ptr [rax+rax+00h]
0x1800a6936  cmp     eax, 824h
0x1800a693b  jbe     short loc_1800A6949
0x1800a693d  mov     ebx, 8007006Fh
0x1800a6942  xor     edi, edi
0x1800a6944  jmp     loc_1800A6BBB
0x1800a6949  lea     r9, [rsp+3D0h+var_370]; unsigned int *
0x1800a694e  mov     rdx, rbx; unsigned __int16 *
0x1800a6951  lea     r8, [rsp+3D0h+var_368]; char **
0x1800a6956  call    ?_WideToAnsi@CVersionManagerServer@@AEAAJPEBGPEAPEADPEAK@Z; CVersionManagerServer::_WideToAnsi(ushort const *,char * *,ulong *)
0x1800a695b  mov     r15, [rsp+3D0h+var_368]
0x1800a6960  xor     ecx, ecx; this
0x1800a6962  mov     ebx, eax
0x1800a6964  test    eax, eax
0x1800a6966  js      short loc_1800A6942
0x1800a6968  mov     r13d, [rsp+3D0h+var_370]
0x1800a696d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a6971  inc     rax
0x1800a6974  cmp     [rdi+rax*2], cx
0x1800a6978  jnz     short loc_1800A6971
0x1800a697a  cmp     rax, 104h
0x1800a6980  ja      short loc_1800A693D
0x1800a6982  lea     r9, [rsp+3D0h+NumberOfBytesWritten]; unsigned int *
0x1800a6987  mov     rdx, rdi; unsigned __int16 *
0x1800a698a  lea     r8, [rsp+3D0h+pv]; char **
0x1800a698f  call    ?_WideToAnsi@CVersionManagerServer@@AEAAJPEBGPEAPEADPEAK@Z; CVersionManagerServer::_WideToAnsi(ushort const *,char * *,ulong *)
0x1800a6994  xor     edi, edi
0x1800a6996  mov     ebx, eax
0x1800a6998  test    eax, eax
0x1800a699a  js      loc_1800A6BBB
0x1800a69a0  mov     edx, [rbp+2D0h+arg_40]
0x1800a69a6  lea     r8, [rbp+2D0h+String]
0x1800a69aa  call    ?_SqmReasonToString@CVersionManagerServer@@AEAAJW4EXT_SQM_VERSION_REASON@@PEAD_K@Z; CVersionManagerServer::_SqmReasonToString(EXT_SQM_VERSION_REASON,char *,unsigned __int64)
0x1800a69af  mov     ebx, eax
0x1800a69b1  test    eax, eax
0x1800a69b3  js      loc_1800A6BBB
0x1800a69b9  mov     ecx, [rbp+2D0h+arg_38]
0x1800a69bf  test    ecx, ecx
0x1800a69c1  jz      short loc_1800A69DF
0x1800a69c3  sub     ecx, 1
0x1800a69c6  jz      short loc_1800A69D6
0x1800a69c8  cmp     ecx, 1
0x1800a69cb  jnz     short loc_1800A69DF
0x1800a69cd  lea     r8, aAllowed; "Allowed"
0x1800a69d4  jmp     short loc_1800A69E6
0x1800a69d6  lea     r8, aBlocked_0; "Blocked"
0x1800a69dd  jmp     short loc_1800A69E6
0x1800a69df  lea     r8, aUnknown; "Unknown"
0x1800a69e6  mov     r10d, 32h ; '2'
0x1800a69ec  lea     rcx, [rbp+2D0h+var_298]; char *
0x1800a69f0  mov     edx, r10d; unsigned __int64
0x1800a69f3  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800a69f8  mov     ebx, eax
0x1800a69fa  test    eax, eax
0x1800a69fc  js      loc_1800A6BBB
0x1800a6a02  cmp     [rbp+2D0h+arg_48], edi
0x1800a6a08  lea     rax, aNotEpmCompatib; "Not EPM Compatible"
0x1800a6a0f  lea     r8, aEpmCompatible; "EPM Compatible"
0x1800a6a16  mov     edx, r10d; unsigned __int64
0x1800a6a19  cmovz   r8, rax; char *
0x1800a6a1d  lea     rcx, [rbp+2D0h+var_308]; char *
0x1800a6a21  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800a6a26  mov     ebx, eax
0x1800a6a28  test    eax, eax
0x1800a6a2a  js      loc_1800A6BBB
0x1800a6a30  mov     edx, [rbp+2D0h+arg_20]
0x1800a6a36  lea     r8, aDDDD; "%d.%d.%d.%d"
0x1800a6a3d  movzx   ecx, dx
0x1800a6a40  movzx   eax, si
0x1800a6a43  mov     dword ptr [rsp+3D0h+hTemplateFile], ecx
0x1800a6a47  lea     rcx, [rbp+2D0h+var_330]; char *
0x1800a6a4b  shr     esi, 10h
0x1800a6a4e  shr     edx, 10h
0x1800a6a51  mov     r9d, esi
0x1800a6a54  mov     [rsp+3D0h+dwFlagsAndAttributes], edx
0x1800a6a58  lea     esi, [r10-0Ah]
0x1800a6a5c  mov     edx, esi; unsigned __int64
0x1800a6a5e  mov     [rsp+3D0h+dwCreationDisposition], eax
0x1800a6a62  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800a6a67  mov     ebx, eax
0x1800a6a69  test    eax, eax
0x1800a6a6b  js      loc_1800A6BBB
0x1800a6a71  mov     edx, [rbp+2D0h+arg_30]
0x1800a6a77  lea     r8, aDDDD; "%d.%d.%d.%d"
0x1800a6a7e  mov     r9d, [rbp+2D0h+arg_28]
0x1800a6a85  movzx   ecx, dx
0x1800a6a88  mov     dword ptr [rsp+3D0h+hTemplateFile], ecx
0x1800a6a8c  lea     rcx, [rsp+3D0h+var_358]; char *
0x1800a6a91  shr     edx, 10h
0x1800a6a94  mov     [rsp+3D0h+dwFlagsAndAttributes], edx
0x1800a6a98  mov     edx, esi; unsigned __int64
0x1800a6a9a  movzx   eax, r9w
0x1800a6a9e  shr     r9d, 10h
0x1800a6aa2  mov     [rsp+3D0h+dwCreationDisposition], eax
0x1800a6aa6  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800a6aab  mov     ebx, eax
0x1800a6aad  test    eax, eax
0x1800a6aaf  js      loc_1800A6BBB
0x1800a6ab5  lea     ebx, [rsi+0Ah]
0x1800a6ab8  mov     edx, ebx; MaxCount
0x1800a6aba  lea     rcx, [rbp+2D0h+String]; String
0x1800a6abe  call    cs:__imp_strnlen
0x1800a6ac5  nop     dword ptr [rax+rax+00h]
0x1800a6aca  mov     edx, ebx; MaxCount
0x1800a6acc  lea     rcx, [rbp+2D0h+var_298]; String
0x1800a6ad0  mov     r14, rax
0x1800a6ad3  call    cs:__imp_strnlen
0x1800a6ada  nop     dword ptr [rax+rax+00h]
0x1800a6adf  mov     edx, ebx; MaxCount
0x1800a6ae1  lea     rcx, [rbp+2D0h+var_308]; String
0x1800a6ae5  mov     rsi, rax
0x1800a6ae8  call    cs:__imp_strnlen
0x1800a6aef  nop     dword ptr [rax+rax+00h]
0x1800a6af4  lea     r12d, [rbx-0Ah]
0x1800a6af8  mov     rdi, rax
0x1800a6afb  mov     edx, r12d; MaxCount
0x1800a6afe  lea     rcx, [rbp+2D0h+var_330]; String
0x1800a6b02  call    cs:__imp_strnlen
0x1800a6b09  nop     dword ptr [rax+rax+00h]
0x1800a6b0e  mov     edx, r12d; MaxCount
0x1800a6b11  lea     rcx, [rsp+3D0h+var_358]; String
0x1800a6b16  mov     rbx, rax
0x1800a6b19  call    cs:__imp_strnlen
0x1800a6b20  nop     dword ptr [rax+rax+00h]
0x1800a6b25  mov     r8d, [rsp+3D0h+NumberOfBytesWritten]
0x1800a6b2a  add     r14, 9
0x1800a6b2e  add     r8d, r13d
0x1800a6b31  lea     rcx, [rbx+rax]
0x1800a6b35  add     r8, rcx
0x1800a6b38  add     r8, rdi
0x1800a6b3b  add     r8, rsi
0x1800a6b3e  add     r14, r8
0x1800a6b41  mov     rcx, r14; cb
0x1800a6b44  call    cs:__imp_CoTaskMemAlloc
0x1800a6b4b  nop     dword ptr [rax+rax+00h]
0x1800a6b50  xor     edi, edi
0x1800a6b52  mov     r12, rax
0x1800a6b55  test    rax, rax
0x1800a6b58  jnz     short loc_1800A6B61
0x1800a6b5a  mov     ebx, 8007000Eh
0x1800a6b5f  jmp     short loc_1800A6BBB
0x1800a6b61  lea     rax, [rbp+2D0h+var_308]
0x1800a6b65  test    r15, r15
0x1800a6b68  mov     [rsp+3D0h+var_388], rax
0x1800a6b6d  lea     r9, Default
0x1800a6b74  lea     rax, [rbp+2D0h+String]
0x1800a6b78  cmovnz  r9, r15
0x1800a6b7c  mov     [rsp+3D0h+var_390], rax
0x1800a6b81  lea     r8, aSSSSSSS; "%s,%s,%s,%s,%s,%s,%s\r\n"
0x1800a6b88  lea     rax, [rbp+2D0h+var_298]
0x1800a6b8c  mov     rdx, r14; unsigned __int64
0x1800a6b8f  mov     [rsp+3D0h+var_398], rax
0x1800a6b94  mov     rcx, r12; char *
0x1800a6b97  lea     rax, [rsp+3D0h+var_358]
0x1800a6b9c  mov     [rsp+3D0h+hTemplateFile], rax
0x1800a6ba1  lea     rax, [rbp+2D0h+var_330]
0x1800a6ba5  mov     qword ptr [rsp+3D0h+dwFlagsAndAttributes], rax
0x1800a6baa  mov     rax, [rsp+3D0h+pv]
0x1800a6baf  mov     qword ptr [rsp+3D0h+dwCreationDisposition], rax
0x1800a6bb4  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x1800a6bb9  mov     ebx, eax
0x1800a6bbb  mov     rcx, [rsp+3D0h+pv]; pv
0x1800a6bc0  call    cs:__imp_CoTaskMemFree
0x1800a6bc7  nop     dword ptr [rax+rax+00h]
0x1800a6bcc  mov     rcx, r15; pv
0x1800a6bcf  call    cs:__imp_CoTaskMemFree
0x1800a6bd6  nop     dword ptr [rax+rax+00h]
0x1800a6bdb  test    ebx, ebx
0x1800a6bdd  js      loc_1800A6E2D
0x1800a6be3  test    r12, r12
0x1800a6be6  jz      loc_1800A6E2D
0x1800a6bec  test    r14, r14
0x1800a6bef  jz      loc_1800A6E2D
0x1800a6bf5  mov     rcx, cs:?IEVALUE_urlmon_ExtVerAuditModeFilePath@SettingStore@@3U?$VALUEID@PEAG@1@B; SettingStore::VALUEID<ushort *> const SettingStore::IEVALUE_urlmon_ExtVerAuditModeFilePath
0x1800a6bfc  lea     rdx, [rbp+2D0h+pszPath]
0x1800a6c00  mov     r8d, 104h
0x1800a6c06  call    GetString
0x1800a6c0b  mov     ebx, eax
0x1800a6c0d  test    eax, eax
0x1800a6c0f  js      loc_1800A6E2D
0x1800a6c15  lea     rax, [rbp+2D0h+pszPath]
0x1800a6c19  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800a6c1d  inc     rdx; cchPath
0x1800a6c20  cmp     [rax+rdx*2], di
0x1800a6c24  jnz     short loc_1800A6C1D
0x1800a6c26  lea     rcx, [rbp+2D0h+pszPath]; pszPath
0x1800a6c2a  call    cs:__imp_PathCchRemoveFileSpec
0x1800a6c31  nop     dword ptr [rax+rax+00h]
0x1800a6c36  mov     ebx, eax
0x1800a6c38  test    eax, eax
0x1800a6c3a  js      loc_1800A6E2D
0x1800a6c40  lea     rcx, [rbp+2D0h+pszPath]; lpFileName
0x1800a6c44  call    cs:__imp_GetFileAttributesW
0x1800a6c4b  nop     dword ptr [rax+rax+00h]
0x1800a6c50  mov     ebx, eax
0x1800a6c52  call    cs:__imp_GetLastError
0x1800a6c59  nop     dword ptr [rax+rax+00h]
0x1800a6c5e  or      r13d, 0FFFFFFFFh
0x1800a6c62  cmp     ebx, r13d
0x1800a6c65  jnz     loc_1800A6DC1
0x1800a6c6b  cmp     eax, 2
0x1800a6c6e  jnz     short loc_1800A6C83
0x1800a6c70  lea     rdx, [rbp+2D0h+pszPath]; unsigned __int16 *
0x1800a6c74  call    ?_CreateLocalDirectory@CVersionManagerServer@@AEAAJPEBG@Z; CVersionManagerServer::_CreateLocalDirectory(ushort const *)
0x1800a6c79  mov     ebx, eax
0x1800a6c7b  test    eax, eax
0x1800a6c7d  js      loc_1800A6E2D
0x1800a6c83  mov     rcx, cs:?IEVALUE_urlmon_ExtVerAuditModeFilePath@SettingStore@@3U?$VALUEID@PEAG@1@B; SettingStore::VALUEID<ushort *> const SettingStore::IEVALUE_urlmon_ExtVerAuditModeFilePath
0x1800a6c8a  lea     rdx, [rbp+2D0h+pszPath]
0x1800a6c8e  mov     r8d, 104h
0x1800a6c94  call    GetString
0x1800a6c99  mov     ebx, eax
0x1800a6c9b  test    eax, eax
0x1800a6c9d  js      loc_1800A6E2D
0x1800a6ca3  mov     rbx, [rsp+3D0h+var_360]
0x1800a6ca8  mov     [rsp+3D0h+var_380], dil
0x1800a6cad  lea     r15, [rbx+760h]
0x1800a6cb4  mov     rcx, r15; lpCriticalSection
0x1800a6cb7  call    cs:__imp_EnterCriticalSection
0x1800a6cbe  nop     dword ptr [rax+rax+00h]
0x1800a6cc3  lea     rax, [rbx+808h]
0x1800a6cca  lea     rdx, [rsp+3D0h+var_380]; bool *
0x1800a6ccf  mov     [rsp+3D0h+pv], rax
0x1800a6cd4  lea     rcx, [rsp+3D0h+pv]; this
0x1800a6cd9  call    ?Lock@CAutoMutex@MutexUtils@@QEAAJPEA_N@Z; MutexUtils::CAutoMutex::Lock(bool *)
0x1800a6cde  mov     ebx, eax
0x1800a6ce0  test    eax, eax
0x1800a6ce2  js      loc_1800A6E14
0x1800a6ce8  xor     r9d, r9d; lpSecurityAttributes
0x1800a6ceb  mov     [rsp+3D0h+hTemplateFile], rdi; hTemplateFile
0x1800a6cf0  mov     [rsp+3D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a6cf8  lea     rcx, [rbp+2D0h+pszPath]; lpFileName
0x1800a6cfc  mov     edx, 40000000h; dwDesiredAccess
0x1800a6d01  mov     [rsp+3D0h+dwCreationDisposition], 4; dwCreationDisposition
0x1800a6d09  lea     r8d, [r9+3]; dwShareMode
0x1800a6d0d  call    cs:__imp_CreateFileW
0x1800a6d14  nop     dword ptr [rax+rax+00h]
0x1800a6d19  mov     rsi, rax
0x1800a6d1c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a6d20  jz      loc_1800A6DF9
0x1800a6d26  call    cs:__imp_GetLastError
0x1800a6d2d  nop     dword ptr [rax+rax+00h]
0x1800a6d32  mov     edi, 80070000h
0x1800a6d37  cmp     eax, 0B7h
0x1800a6d3c  jnz     short loc_1800A6D7F
0x1800a6d3e  cmp     [rsp+3D0h+var_380], 0
0x1800a6d43  jnz     short loc_1800A6D7F
0x1800a6d45  mov     r9d, 2; dwMoveMethod
0x1800a6d4b  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800a6d4e  xor     edx, edx; lDistanceToMove
0x1800a6d50  mov     rcx, rsi; hFile
0x1800a6d53  call    cs:__imp_SetFilePointer
0x1800a6d5a  nop     dword ptr [rax+rax+00h]
0x1800a6d5f  cmp     eax, r13d
0x1800a6d62  jnz     short loc_1800A6D7F
0x1800a6d64  call    cs:__imp_GetLastError
0x1800a6d6b  nop     dword ptr [rax+rax+00h]
0x1800a6d70  mov     ebx, eax
0x1800a6d72  test    eax, eax
0x1800a6d74  jle     short loc_1800A6D7B
0x1800a6d76  movzx   ebx, ax
0x1800a6d79  or      ebx, edi
0x1800a6d7b  test    ebx, ebx
0x1800a6d7d  js      short loc_1800A6DE8
0x1800a6d7f  dec     r14
0x1800a6d82  mov     [rsp+3D0h+NumberOfBytesWritten], 0
  ... truncated ...
```
