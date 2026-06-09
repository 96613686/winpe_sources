# pSetupCreateTextLogSectionA

- ea: `0x1800177e0`
- end: `0x180017d1b`
- name: `pSetupCreateTextLogSectionA`
- size: `1339`
- prototype: `_BOOL8 __fastcall(const char *, __int64, CHAR *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000fc1c`

## callees

- `0x18000b360`
- `0x18000c9d0`
- `0x18000df10`
- `0x18000f5a0`
- `0x18000f82c`
- `0x18000fb9c`
- `0x1800101e8`
- `0x1800104d8`
- `0x180010a58`
- `0x18001621c`
- `0x180016678`
- `0x180016cac`
- `0x180016d84`
- `0x180016ee8`
- `0x180017058`
- `0x1800170f0`
- `0x1800177e0`
- `0x18001817c`
- `0x18001893e`
- `0x180018970`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x180017bd3`
- `ntdll!RtlGetVersion` at `0x180017bd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18001789c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18001789c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017ce3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017ce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017856`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180017a11`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180017a11`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180017a27`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180017a27`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x180017944`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x180017944`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017b3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017ccc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017b3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017ccc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800178ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800178ec`

## string_xrefs

- `0x180017b03`: `     Hardware Configuration: %s`
- `0x180017c2e`: ` os: Version = %d.%d.%d, Service Pack = %d.%d, Suite = 0x%04x, ProductType = %d, Architecture = %s`

## pseudocode

```c
_BOOL8 __fastcall pSetupCreateTextLogSectionA(const char *a1, __int64 a2, CHAR *a3, unsigned __int64 *a4)
{
  CHAR *v4; // rbx
  DWORD LastError; // ebx
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // r12d
  SIZE_T v11; // r14
  char *v12; // rax
  char *v13; // r15
  int v14; // r13d
  HRESULT v15; // eax
  LPSTR CommandLineA; // rax
  int v17; // r8d
  __int64 v18; // rdi
  int LogStatus; // esi
  int IsPortableOS; // eax
  unsigned int v21; // edx
  const char *v22; // rax
  char *v23; // rdi
  int v24; // r14d
  int v25; // r9d
  int v26; // r9d
  int v27; // r9d
  int v28; // esi
  __int64 v29; // rdi
  unsigned int v31; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v32; // [rsp+64h] [rbp-9Ch] BYREF
  _OWORD v33[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  FILETIME FileTime; // [rsp+A0h] [rbp-60h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 *v38; // [rsp+B0h] [rbp-50h]
  struct _SYSTEMTIME SystemTime; // [rsp+B8h] [rbp-48h] BYREF
  int v40; // [rsp+C8h] [rbp-38h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v42; // [rsp+1E4h] [rbp+E4h]
  unsigned __int16 v43; // [rsp+1E6h] [rbp+E6h]
  unsigned __int16 v44; // [rsp+1E8h] [rbp+E8h]
  unsigned __int8 v45; // [rsp+1EAh] [rbp+EAh]
  WCHAR WideCharStr[40]; // [rsp+1F0h] [rbp+F0h] BYREF
  char pszDest[128]; // [rsp+240h] [rbp+140h] BYREF
  char v48[272]; // [rsp+2C0h] [rbp+1C0h] BYREF
  CHAR Filename[528]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v38 = a4;
  v35 = 0;
  v40 = 0;
  memset(v33, 0, sizeof(v33));
  v31 = 0;
  v4 = a3;
  v32 = 0;
  v34 = 0;
  SystemTime = 0;
  if ( (unsigned int)GetTextLogKeyFromStrings(a1, a3, a3, &v32)
    && (g_sputils_LogInitialized || (unsigned int)pSpUtilsLogInitialize()) )
  {
    if ( (_DWORD)GlobalDevLogData )
    {
      if ( !v4 )
      {
        v4 = Filename;
        if ( !GetModuleFileNameA(0, Filename, 0x208u) )
          v4 = "no title";
      }
      v7 = -1;
      v8 = -1;
      do
        ++v8;
      while ( v4[v8] );
      if ( a1 )
      {
        v9 = -1;
        do
          ++v9;
        while ( a1[v9] );
        LODWORD(v8) = v9 + v8;
      }
      v10 = v8 + 16;
      v11 = (unsigned int)(v8 + 16);
      v12 = (char *)HeapAlloc(hHeap, 0, v11);
      v13 = v12;
      if ( v12 )
      {
        v14 = 0;
        if ( a1 )
          v15 = StringCchPrintfA(v12, v11, "[%s - %s]", v4, a1);
        else
          v15 = StringCchPrintfA(v12, v11, "[%s]", v4);
        if ( v15 >= 0 )
        {
          CommandLineA = GetCommandLineA();
          do
            ++v7;
          while ( CommandLineA[v7] );
          LastError = TextLogMapFile(&GlobalDevLogData, v33, (unsigned int)(v7 + v10 + 326), 0);
          if ( !LastError )
          {
            if ( (unsigned int)TextLogFindSection(v33, 3, &SystemTime, &v31) )
            {
              TextLogWriteSectionFooter((unsigned int)v33, (unsigned int)&SystemTime, v17, 0, 0);
              TextLogDeleteCtlTag(v33, v31);
            }
            v18 = v34;
            if ( (*(_DWORD *)(v34 + 12) & 0x1000) == 0 )
            {
              LogStatus = TextLogGetLogStatus(v34);
              if ( (LogStatus & 0x1000) == 0 )
              {
                FileTime = 0;
                LocalFileTime = 0;
                SystemTime = 0;
                v31 = 0;
                if ( (unsigned int)pSetupGetSystemBootTime(&FileTime)
                  && FileTimeToLocalFileTime(&FileTime, &LocalFileTime)
                  && FileTimeToSystemTime(&LocalFileTime, &SystemTime)
                  && StringCchPrintfA(
                       pszDest,
                       0x80u,
                       "[Boot Session: %04d/%02d/%02d %02d:%02d:%02d.%03d]",
                       SystemTime.wYear,
                       SystemTime.wMonth,
                       SystemTime.wDay,
                       SystemTime.wHour,
                       SystemTime.wMinute,
                       SystemTime.wSecond,
                       SystemTime.wMilliseconds) >= 0 )
                {
                  TextLogInsertString(v33, DWORD2(v34), "\r\n");
                  TextLogInsertString(v33, DWORD2(v34), pszDest);
                  IsPortableOS = TextLogIsPortableOS(&v31);
                  v21 = v31;
                  if ( IsPortableOS )
                    v21 = 0;
                  if ( v21 )
                  {
                    if ( (unsigned int)TextLogGetHardwareConfigurationGuid(WideCharStr) )
                      WideCharStr[0] = 0;
                    v22 = (const char *)pSetupUnicodeToMultiByte(WideCharStr);
                    v23 = (char *)v22;
                    if ( v22 )
                    {
                      if ( StringCchPrintfA(pszDest, 0x80u, "     Hardware Configuration: %s", v22) >= 0 )
                        TextLogInsertString(v33, DWORD2(v34), pszDest);
                      HeapFree(hHeap, 0, v23);
                    }
                  }
                  v18 = v34;
                }
                TextLogSetLogStatus(v18, LogStatus | 0x1000u);
              }
              *(_DWORD *)(v18 + 12) |= 0x1000u;
            }
            v14 = 1;
            TextLogInsertString(v33, DWORD2(v34), "\r\n");
            v24 = DWORD2(v34);
            TextLogWriteEntry((unsigned int)v33, DWORD2(v34), (_DWORD)v13, v25, 16);
            TextLogWriteEntry((unsigned int)v33, DWORD2(v34), (unsigned int)"Section start", v26, 65552);
            if ( TextLogOffline )
            {
              memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
              VersionInformation.dwOSVersionInfoSize = 284;
              if ( RtlGetVersion(&VersionInformation) >= 0
                && StringCchPrintfA(
                     v48,
                     0x104u,
                     " os: Version = %d.%d.%d, Service Pack = %d.%d, Suite = 0x%04x, ProductType = %d, Architecture = %s",
                     VersionInformation.dwMajorVersion,
                     VersionInformation.dwMinorVersion,
                     VersionInformation.dwBuildNumber,
                     v42,
                     v43,
                     v44,
                     v45,
                     "amd64") >= 0 )
              {
                TextLogWriteEntry((unsigned int)v33, DWORD2(v34), (unsigned int)v48, v27, 0);
              }
            }
            v28 = DWORD2(v34);
            TextLogInsertString(v33, DWORD2(v34), "<ins>");
            v29 = v32;
            if ( v32 )
            {
              *(_DWORD *)&SystemTime.wYear = -522186479;
              *(_DWORD *)&SystemTime.wDayOfWeek = v32;
              *(_DWORD *)&SystemTime.wHour = v24;
              *(_DWORD *)&SystemTime.wSecond = v28;
              v40 = 0;
              TextLogInsertCtlTag(v33, &SystemTime);
            }
            if ( v38 )
              *v38 = v29 | ((unsigned __int64)(GlobalDevLogData & 0xF) << 32);
          }
        }
        else
        {
          LastError = (unsigned __int16)v15;
        }
        HeapFree(hHeap, 0, v13);
        if ( v14 )
          TextLogUnmapFile(v33);
      }
      else
      {
        LastError = 8;
      }
    }
    else
    {
      LastError = 4309;
    }
  }
  else
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x1800177e0  mov     [rsp-8+arg_8], rbx
0x1800177e5  push    rbp
0x1800177e6  push    rsi
0x1800177e7  push    rdi
0x1800177e8  push    r12
0x1800177ea  push    r13
0x1800177ec  push    r14
0x1800177ee  push    r15
0x1800177f0  lea     rbp, [rsp-4F0h]
0x1800177f8  sub     rsp, 5F0h
0x1800177ff  mov     rax, cs:__security_cookie
0x180017806  xor     rax, rsp
0x180017809  mov     [rbp+520h+var_40], rax
0x180017810  xorps   xmm0, xmm0
0x180017813  mov     [rbp+520h+var_570], r9
0x180017817  xor     eax, eax
0x180017819  lea     r9, [rsp+620h+var_5BC]
0x18001781e  xor     r12d, r12d
0x180017821  mov     [rbp+520h+var_588], rax
0x180017825  mov     rdx, r8
0x180017828  mov     [rbp+520h+var_558], eax
0x18001782b  movups  [rsp+620h+var_5B8], xmm0
0x180017830  mov     [rsp+620h+var_5C0], r12d
0x180017835  mov     rbx, r8
0x180017838  movups  [rsp+620h+var_5A8], xmm0
0x18001783d  mov     [rsp+620h+var_5BC], r12d
0x180017842  mov     rsi, rcx
0x180017845  movups  [rbp+520h+var_598], xmm0
0x180017849  movups  xmmword ptr [rbp+520h+SystemTime.wYear], xmm0
0x18001784d  call    GetTextLogKeyFromStrings
0x180017852  test    eax, eax
0x180017854  jnz     short loc_180017863
0x180017856  call    cs:__imp_GetLastError
0x18001785c  mov     ebx, eax
0x18001785e  jmp     loc_180017CE1
0x180017863  cmp     cs:g_sputils_LogInitialized, r12d
0x18001786a  jnz     short loc_180017875
0x18001786c  call    _pSpUtilsLogInitialize
0x180017871  test    eax, eax
0x180017873  jz      short loc_180017856
0x180017875  cmp     dword ptr cs:GlobalDevLogData, r12d
0x18001787c  jnz     short loc_180017888
0x18001787e  mov     ebx, 10D5h
0x180017883  jmp     loc_180017CE1
0x180017888  test    rbx, rbx
0x18001788b  jnz     short loc_1800178B6
0x18001788d  mov     r8d, 208h; nSize
0x180017893  lea     rdx, [rbp+520h+Filename]; lpFilename
0x18001789a  xor     ecx, ecx; hModule
0x18001789c  call    cs:__imp_GetModuleFileNameA
0x1800178a2  test    eax, eax
0x1800178a4  lea     rbx, [rbp+520h+Filename]
0x1800178ab  lea     rcx, aNoTitle; "no title"
0x1800178b2  cmovz   rbx, rcx
0x1800178b6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800178ba  mov     rax, rdi
0x1800178bd  inc     rax
0x1800178c0  cmp     [rbx+rax], r12b
0x1800178c4  jnz     short loc_1800178BD
0x1800178c6  test    rsi, rsi
0x1800178c9  jz      short loc_1800178D9
0x1800178cb  mov     rcx, rdi
0x1800178ce  inc     rcx
0x1800178d1  cmp     [rsi+rcx], r12b
0x1800178d5  jnz     short loc_1800178CE
0x1800178d7  add     eax, ecx
0x1800178d9  mov     rcx, cs:hHeap; hHeap
0x1800178e0  lea     r12d, [rax+10h]
0x1800178e4  mov     r8d, r12d; dwBytes
0x1800178e7  xor     edx, edx; dwFlags
0x1800178e9  mov     r14d, r12d
0x1800178ec  call    cs:__imp_HeapAlloc
0x1800178f2  mov     r15, rax
0x1800178f5  test    rax, rax
0x1800178f8  jnz     short loc_180017905
0x1800178fa  lea     ebx, [rax+8]
0x1800178fd  xor     r12d, r12d
0x180017900  jmp     loc_180017CE1
0x180017905  xor     r13d, r13d
0x180017908  mov     r9, rbx
0x18001790b  mov     rdx, r14; cchDest
0x18001790e  mov     rcx, r15; pszDest
0x180017911  test    rsi, rsi
0x180017914  jz      short loc_180017929
0x180017916  lea     r8, aSS_0; "[%s - %s]"
0x18001791d  mov     [rsp+620h+var_600], rsi
0x180017922  call    StringCchPrintfA
0x180017927  jmp     short loc_180017935
0x180017929  lea     r8, aS; "[%s]"
0x180017930  call    StringCchPrintfA
0x180017935  test    eax, eax
0x180017937  jns     short loc_180017944
0x180017939  movzx   ebx, ax
0x18001793c  xor     r12d, r12d
0x18001793f  jmp     loc_180017CC0
0x180017944  call    cs:__imp_GetCommandLineA
0x18001794a  inc     rdi
0x18001794d  cmp     [rax+rdi], r13b
0x180017951  jnz     short loc_18001794A
0x180017953  lea     r8d, [r12+146h]
0x18001795b  xor     r9d, r9d
0x18001795e  add     r8d, edi
0x180017961  lea     rdx, [rsp+620h+var_5B8]
0x180017966  lea     rcx, GlobalDevLogData
0x18001796d  call    TextLogMapFile
0x180017972  xor     r12d, r12d
0x180017975  mov     ebx, eax
0x180017977  test    eax, eax
0x180017979  jnz     loc_180017CC0
0x18001797f  lea     r9, [rsp+620h+var_5C0]
0x180017984  lea     r8, [rbp+520h+SystemTime]
0x180017988  lea     edx, [rax+3]
0x18001798b  lea     rcx, [rsp+620h+var_5B8]
0x180017990  call    TextLogFindSection
0x180017995  test    eax, eax
0x180017997  jz      short loc_1800179BD
0x180017999  xor     r9d, r9d
0x18001799c  mov     dword ptr [rsp+620h+var_600], r12d
0x1800179a1  lea     rdx, [rbp+520h+SystemTime]
0x1800179a5  lea     rcx, [rsp+620h+var_5B8]
0x1800179aa  call    TextLogWriteSectionFooter
0x1800179af  mov     edx, [rsp+620h+var_5C0]
0x1800179b3  lea     rcx, [rsp+620h+var_5B8]
0x1800179b8  call    TextLogDeleteCtlTag
0x1800179bd  mov     rdi, qword ptr [rbp+520h+var_598]
0x1800179c1  mov     r14d, 1000h
0x1800179c7  test    [rdi+0Ch], r14d
0x1800179cb  jnz     loc_180017B58
0x1800179d1  mov     rcx, rdi
0x1800179d4  call    TextLogGetLogStatus
0x1800179d9  mov     esi, eax
0x1800179db  test    r14d, eax
0x1800179de  jnz     loc_180017B54
0x1800179e4  xorps   xmm0, xmm0
0x1800179e7  mov     qword ptr [rbp+520h+FileTime.dwLowDateTime], r12
0x1800179eb  lea     rcx, [rbp+520h+FileTime]
0x1800179ef  mov     qword ptr [rbp+520h+LocalFileTime.dwLowDateTime], r12
0x1800179f3  movups  xmmword ptr [rbp+520h+SystemTime.wYear], xmm0
0x1800179f7  mov     [rsp+620h+var_5C0], r12d
0x1800179fc  call    pSetupGetSystemBootTime
0x180017a01  test    eax, eax
0x180017a03  jz      loc_180017B47
0x180017a09  lea     rdx, [rbp+520h+LocalFileTime]; lpLocalFileTime
0x180017a0d  lea     rcx, [rbp+520h+FileTime]; lpFileTime
0x180017a11  call    cs:__imp_FileTimeToLocalFileTime
0x180017a17  test    eax, eax
0x180017a19  jz      loc_180017B47
0x180017a1f  lea     rdx, [rbp+520h+SystemTime]; lpSystemTime
0x180017a23  lea     rcx, [rbp+520h+LocalFileTime]; lpFileTime
0x180017a27  call    cs:__imp_FileTimeToSystemTime
0x180017a2d  test    eax, eax
0x180017a2f  jz      loc_180017B47
0x180017a35  movzx   ecx, [rbp+520h+SystemTime.wSecond]
0x180017a39  mov     r13d, 80h
0x180017a3f  movzx   edx, [rbp+520h+SystemTime.wMinute]
0x180017a43  movzx   r8d, [rbp+520h+SystemTime.wHour]
0x180017a48  movzx   eax, [rbp+520h+SystemTime.wMilliseconds]
0x180017a4c  movzx   r10d, [rbp+520h+SystemTime.wDay]
0x180017a51  movzx   r11d, [rbp+520h+SystemTime.wMonth]
0x180017a56  movzx   r9d, [rbp+520h+SystemTime.wYear]
0x180017a5b  mov     [rsp+620h+var_5D8], eax
0x180017a5f  mov     [rsp+620h+var_5E0], ecx
0x180017a63  lea     rcx, [rbp+520h+pszDest]; pszDest
0x180017a6a  mov     [rsp+620h+var_5E8], edx
0x180017a6e  mov     edx, r13d; cchDest
0x180017a71  mov     [rsp+620h+var_5F0], r8d
0x180017a76  lea     r8, aBootSession04d; "[Boot Session: %04d/%02d/%02d %02d:%02d"...
0x180017a7d  mov     [rsp+620h+var_5F8], r10d
0x180017a82  mov     dword ptr [rsp+620h+var_600], r11d
0x180017a87  call    StringCchPrintfA
0x180017a8c  test    eax, eax
0x180017a8e  js      loc_180017B47
0x180017a94  mov     edx, dword ptr [rbp+520h+var_598+8]
0x180017a97  lea     r8, asc_18001CACC; "\r\n"
0x180017a9e  lea     rcx, [rsp+620h+var_5B8]
0x180017aa3  call    TextLogInsertString
0x180017aa8  mov     edx, dword ptr [rbp+520h+var_598+8]
0x180017aab  lea     r8, [rbp+520h+pszDest]
0x180017ab2  lea     rcx, [rsp+620h+var_5B8]
0x180017ab7  call    TextLogInsertString
0x180017abc  lea     rcx, [rsp+620h+var_5C0]
0x180017ac1  call    TextLogIsPortableOS
0x180017ac6  mov     edx, [rsp+620h+var_5C0]
0x180017aca  test    eax, eax
0x180017acc  cmovnz  edx, r12d
0x180017ad0  test    edx, edx
0x180017ad2  jz      short loc_180017B43
0x180017ad4  lea     rcx, [rbp+520h+WideCharStr]
0x180017adb  call    TextLogGetHardwareConfigurationGuid
0x180017ae0  test    eax, eax
0x180017ae2  jz      short loc_180017AEC
0x180017ae4  mov     [rbp+520h+WideCharStr], r12w
0x180017aec  lea     rcx, [rbp+520h+WideCharStr]; lpWideCharStr
0x180017af3  call    pSetupUnicodeToMultiByte
0x180017af8  mov     rdi, rax
0x180017afb  test    rax, rax
0x180017afe  jz      short loc_180017B43
0x180017b00  mov     r9, rax
0x180017b03  lea     r8, aHardwareConfig; "     Hardware Configuration: %s"
0x180017b0a  mov     rdx, r13; cchDest
0x180017b0d  lea     rcx, [rbp+520h+pszDest]; pszDest
0x180017b14  call    StringCchPrintfA
0x180017b19  test    eax, eax
0x180017b1b  js      short loc_180017B31
0x180017b1d  mov     edx, dword ptr [rbp+520h+var_598+8]
0x180017b20  lea     r8, [rbp+520h+pszDest]
0x180017b27  lea     rcx, [rsp+620h+var_5B8]
0x180017b2c  call    TextLogInsertString
0x180017b31  mov     rcx, cs:hHeap; hHeap
0x180017b38  mov     r8, rdi; lpMem
0x180017b3b  xor     edx, edx; dwFlags
0x180017b3d  call    cs:__imp_HeapFree
0x180017b43  mov     rdi, qword ptr [rbp+520h+var_598]
0x180017b47  or      esi, r14d
0x180017b4a  mov     rcx, rdi
0x180017b4d  mov     edx, esi
0x180017b4f  call    TextLogSetLogStatus
0x180017b54  or      [rdi+0Ch], r14d
0x180017b58  mov     edx, dword ptr [rbp+520h+var_598+8]
0x180017b5b  lea     r8, asc_18001CACC; "\r\n"
0x180017b62  lea     rcx, [rsp+620h+var_5B8]
0x180017b67  mov     r13d, 1
0x180017b6d  call    TextLogInsertString
0x180017b72  mov     r14d, dword ptr [rbp+520h+var_598+8]
0x180017b76  lea     rcx, [rsp+620h+var_5B8]
0x180017b7b  mov     r8, r15
0x180017b7e  mov     dword ptr [rsp+620h+var_600], 10h
0x180017b86  mov     edx, r14d
0x180017b89  call    TextLogWriteEntry
0x180017b8e  mov     edx, dword ptr [rbp+520h+var_598+8]
0x180017b91  lea     r8, aSectionStart; "Section start"
0x180017b98  lea     rcx, [rsp+620h+var_5B8]
0x180017b9d  mov     dword ptr [rsp+620h+var_600], 10010h
0x180017ba5  call    TextLogWriteEntry
0x180017baa  cmp     cs:TextLogOffline, r12d
0x180017bb1  jz      loc_180017C62
0x180017bb7  xor     edx, edx; Val
0x180017bb9  lea     rcx, [rbp+520h+VersionInformation.dwMajorVersion]; void *
0x180017bbd  mov     r8d, 118h; Size
0x180017bc3  call    memset_0
0x180017bc8  lea     rcx, [rbp+520h+VersionInformation]; lpVersionInformation
0x180017bcc  mov     [rbp+520h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180017bd3  call    cs:__imp_RtlGetVersion
0x180017bd9  test    eax, eax
0x180017bdb  js      loc_180017C62
0x180017be1  movzx   eax, [rbp+520h+var_436]
0x180017be8  lea     r9, aAmd64; "amd64"
0x180017bef  movzx   ecx, [rbp+520h+var_438]
0x180017bf6  movzx   edx, [rbp+520h+var_43A]
0x180017bfd  movzx   r8d, [rbp+520h+var_43C]
0x180017c05  mov     [rsp+620h+var_5D0], r9
0x180017c0a  mov     r9d, [rbp+520h+VersionInformation.dwMajorVersion]
0x180017c0e  mov     [rsp+620h+var_5D8], eax
0x180017c12  mov     eax, [rbp+520h+VersionInformation.dwBuildNumber]
0x180017c15  mov     [rsp+620h+var_5E0], ecx
0x180017c19  lea     rcx, [rbp+520h+var_360]; pszDest
0x180017c20  mov     [rsp+620h+var_5E8], edx
0x180017c24  mov     edx, 104h; cchDest
0x180017c29  mov     [rsp+620h+var_5F0], r8d
0x180017c2e  lea     r8, aOsVersionDDDSe; " os: Version = %d.%d.%d, Service Pack ="...
0x180017c35  mov     [rsp+620h+var_5F8], eax
0x180017c39  mov     eax, [rbp+520h+VersionInformation.dwMinorVersion]
0x180017c3c  mov     dword ptr [rsp+620h+var_600], eax
0x180017c40  call    StringCchPrintfA
0x180017c45  test    eax, eax
0x180017c47  js      short loc_180017C62
0x180017c49  mov     edx, dword ptr [rbp+520h+var_598+8]
0x180017c4c  lea     r8, [rbp+520h+var_360]
0x180017c53  lea     rcx, [rsp+620h+var_5B8]
0x180017c58  mov     dword ptr [rsp+620h+var_600], r12d
0x180017c5d  call    TextLogWriteEntry
0x180017c62  mov     esi, dword ptr [rbp+520h+var_598+8]
0x180017c65  lea     r8, aIns; "<ins>"
0x180017c6c  mov     edx, esi
0x180017c6e  lea     rcx, [rsp+620h+var_5B8]
0x180017c73  call    TextLogInsertString
0x180017c78  mov     edi, [rsp+620h+var_5BC]
0x180017c7c  test    edi, edi
0x180017c7e  jz      short loc_180017CA3
0x180017c80  lea     rdx, [rbp+520h+SystemTime]
0x180017c84  mov     dword ptr [rbp+520h+SystemTime.wYear], 0E0E01111h
0x180017c8b  lea     rcx, [rsp+620h+var_5B8]
0x180017c90  mov     dword ptr [rbp+520h+SystemTime.wDayOfWeek], edi
0x180017c93  mov     dword ptr [rbp+520h+SystemTime.wHour], r14d
0x180017c97  mov     dword ptr [rbp+520h+SystemTime.wSecond], esi
0x180017c9a  mov     [rbp+520h+var_558], r12d
0x180017c9e  call    TextLogInsertCtlTag
0x180017ca3  mov     rdx, [rbp+520h+var_570]
0x180017ca7  test    rdx, rdx
0x180017caa  jz      short loc_180017CC0
0x180017cac  mov     rcx, cs:GlobalDevLogData
0x180017cb3  and     ecx, 0Fh
0x180017cb6  shl     rcx, 20h
0x180017cba  or      rcx, rdi
0x180017cbd  mov     [rdx], rcx
0x180017cc0  mov     rcx, cs:hHeap; hHeap
0x180017cc7  mov     r8, r15; lpMem
0x180017cca  xor     edx, edx; dwFlags
0x180017ccc  call    cs:__imp_HeapFree
0x180017cd2  test    r13d, r13d
  ... truncated ...
```
