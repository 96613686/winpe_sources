# _QueryClassInterfaceAndOrLogData(ushort const *,ushort const *,ulong,ushort const *,QCI_BEHAVIOR)

- ea: `0x1801cf0b0`
- end: `0x1801cf555`
- name: `?_QueryClassInterfaceAndOrLogData@@YAHPEBG0K0W4QCI_BEHAVIOR@@@Z`
- size: `1189`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801ce8ec`

## callees

- `0x180094c70`
- `0x1800a0ff0`
- `0x1800a3080`
- `0x180120c90`
- `0x180121230`
- `0x1801cf0b0`
- `0x18026f1f0`
- `0x18026f214`
- `0x18026f2e4`
- `0x1802a2fc8`
- `0x1802ff81c`
- `0x1803588b8`
- `0x18035dd34`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1805c23a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801cf3cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801cf3cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801cf41b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801cf426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801cf41b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801cf426`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1801cf3fd`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1801cf3fd`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1801cf3df`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1801cf3df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801cf408`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801cf413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801cf408`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801cf413`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801cf112`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801cf131`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801cf112`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801cf131`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801cf1ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801cf1ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801cf1dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801cf1dc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801cf26c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801cf496`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801cf26c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801cf496`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801cf30d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801cf30d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1801cf32b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1801cf32b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1801cf50e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1801cf50e`

## string_xrefs

- `0x1801cf25e`: `Software\Microsoft\Windows\CurrentVersion\Shell Extensions\Cached`
- `0x1801cf294`: `Software\Microsoft\Windows\CurrentVersion\Shell Extensions\Cached`
- `0x1801cf518`: `Software\Microsoft\Windows\CurrentVersion\Shell Extensions\Cached`
- `0x1801cf2b6`: `Software\Microsoft\Internet Explorer\LowRegistry\Shell Extensions\Cached`
- `0x1801cf524`: `Software\Microsoft\Internet Explorer\LowRegistry\Shell Extensions\Cached`
- `0x1801cf161`: `Software\Classes\CLSID\`
- `0x1801cf47e`: `HasFlushedShellExtCache`
- `0x1801cf4fd`: `HasFlushedShellExtCache`
- `0x1801cf31b`: `verclsid.exe`
- `0x1801cf485`: `Software\Microsoft\Windows\CurrentVersion\Shell Extensions`
- `0x1801cf504`: `Software\Microsoft\Windows\CurrentVersion\Shell Extensions`
- `0x1801cf15a`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _QueryClassInterfaceAndOrLogData(
        const unsigned __int16 *a1,
        const WCHAR *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        BOOL a5)
{
  unsigned int v9; // ebx
  BOOL v10; // edi
  bool v11; // al
  _BOOL8 v12; // rsi
  const unsigned __int16 *v13; // r8
  unsigned int v14; // r10d
  unsigned int v15; // esi
  unsigned __int64 v16; // rdx
  unsigned __int8 v17; // cl
  unsigned int hProcess; // eax
  int v19; // edx
  struct _SECURITY_ATTRIBUTES *v20; // r8
  struct _SECURITY_ATTRIBUTES *v21; // r9
  unsigned __int64 v22; // rdx
  unsigned __int8 v23; // cl
  __int64 v24; // rcx
  Shell32LoggingTelemetry *v25; // rcx
  LPDWORD pcbData; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v28; // [rsp+38h] [rbp-C8h]
  struct _PROCESS_INFORMATION phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD ExitCode; // [rsp+68h] [rbp-98h] BYREF
  int pvData; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD v32; // [rsp+70h] [rbp-90h] BYREF
  DWORD v33[3]; // [rsp+74h] [rbp-8Ch] BYREF
  struct _STARTUPINFOW v34; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Value[96]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR SubKey[264]; // [rsp+1B0h] [rbp+B0h] BYREF
  WCHAR CommandLine[368]; // [rsp+3C0h] [rbp+2C0h] BYREF

  v9 = 0;
  v10 = a5;
  if ( !a5 )
  {
    if ( CompareStringOrdinal(a2, -1, L"{000214E6-0000-0000-C000-000000000046}", -1, 1) == 2
      || CompareStringOrdinal(a2, -1, L"{ADD8BA80-002B-11D0-8F0F-00C04FD7D062}", -1, 1) == 2 )
    {
      phkResult.hProcess = 0;
      v11 = IsWUDFHostProcess();
      v12 = v11;
      v13 = L"Software\\Classes\\CLSID\\";
      if ( !v11 )
        v13 = L"CLSID\\";
      if ( (int)StringCchCopyW(SubKey, 0xA7u, v13) >= 0
        && (int)StringCchCatW(SubKey, v14, a1) >= 0
        && (int)StringCchCatW(SubKey, 0xA7u, L"\\ShellFolder") >= 0
        && !RegOpenKeyExW((HKEY)(2 * v12 - 0x80000000LL), SubKey, 0, 0x20019u, (PHKEY)&phkResult) )
      {
        v10 = 1;
        RegCloseKey((HKEY)phkResult.hProcess);
      }
    }
    else
    {
      v10 = a3 == 4;
    }
  }
  v15 = 0xFFFF;
  if ( !v10 )
    v15 = a3;
  if ( (int)StringCchPrintfW(Value, 0x5Cu, L"%s %s 0x%X", a1, a2, v15) >= 0 )
  {
    pvData = 0;
    v32 = 4;
    if ( !v10
      && !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell Extensions\\Cached",
            Value,
            0x10u,
            0,
            &pvData,
            &v32) )
    {
      LOBYTE(v9) = pvData != 0;
      goto LABEL_41;
    }
    *(_OWORD *)&phkResult.hProcess = 0;
    if ( !(unsigned int)GetQICacheEntry(
                          L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell Extensions\\Cached",
                          Value,
                          (struct QICACHEENTRY *)&phkResult)
      && ((unsigned int)IsEffectiveLowIL()
       || !(unsigned int)GetQICacheEntry(
                           L"Software\\Microsoft\\Internet Explorer\\LowRegistry\\Shell Extensions\\Cached",
                           Value,
                           (struct QICACHEENTRY *)&phkResult)) )
    {
      goto LABEL_23;
    }
    hProcess = (unsigned int)phkResult.hProcess;
    if ( !LODWORD(phkResult.hProcess) )
    {
      if ( !(unsigned int)_CacheTimeValid((union _ULARGE_INTEGER)phkResult.hThread) )
      {
LABEL_23:
        if ( v10 )
        {
          v9 = 1;
          v19 = 1;
LABEL_25:
          _CacheEntry(Value, v19);
          goto LABEL_41;
        }
        if ( GetSystemDirectoryW(SubKey, 0x104u) && PathCchAppend(SubKey, 0x104u, L"verclsid.exe") >= 0 )
        {
          LODWORD(pcbData) = v15;
          if ( (int)StringCchPrintfW(CommandLine, 0x16Cu, L"\"%s\" /S /C %s /I %s /X 0x%X", SubKey) >= 0 )
          {
            *(_QWORD *)&v34.cb = 104;
            memset_0(&v34.lpReserved, 0, 0x60u);
            memset(&phkResult, 0, sizeof(phkResult));
            if ( (unsigned int)CreateProcessWithImpersonation(
                                 SubKey,
                                 CommandLine,
                                 v20,
                                 v21,
                                 (int)a1,
                                 (unsigned int)a2,
                                 pcbData,
                                 v28,
                                 &v34,
                                 &phkResult) )
            {
              ExitCode = 0;
              if ( WaitForSingleObject(phkResult.hProcess, 0x3A98u)
                || !GetExitCodeProcess(phkResult.hProcess, &ExitCode) )
              {
                TerminateProcess(phkResult.hProcess, 2u);
              }
              else
              {
                LOBYTE(v9) = ExitCode == 0;
              }
              CloseHandle(phkResult.hThread);
              CloseHandle(phkResult.hProcess);
            }
            else if ( GetLastError() == 2 || GetLastError() == 1816 )
            {
              v9 = 1;
            }
          }
          v19 = v9;
          goto LABEL_25;
        }
LABEL_41:
        if ( Shell32LoggingTelemetry::IsEnabled(v17, v16) )
        {
          ExitCode = 0;
          v33[0] = 4;
          if ( RegGetValueW(
                 HKEY_CURRENT_USER,
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell Extensions",
                 L"HasFlushedShellExtCache",
                 0x10u,
                 0,
                 &ExitCode,
                 v33)
            || !ExitCode )
          {
            LODWORD(phkResult.hProcess) = 1;
            if ( !RegSetKeyValueW(
                    HKEY_CURRENT_USER,
                    L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell Extensions",
                    L"HasFlushedShellExtCache",
                    4u,
                    &phkResult,
                    4u) )
            {
              _PumpForCache(L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell Extensions\\Cached");
              _PumpForCache(L"Software\\Microsoft\\Internet Explorer\\LowRegistry\\Shell Extensions\\Cached");
            }
          }
          else if ( v9 && Shell32LoggingTelemetry::IsEnabled(v23, v22) )
          {
            wil::details::static_lazy<Shell32LoggingTelemetry>::get(
              v24,
              _lambda_24fe894bbe862470a274f72532562200_::_lambda_invoker_cdecl_);
            Shell32LoggingTelemetry::ShellExtensionList_(v25, a1, a2, v15, a4, 0);
          }
        }
        return v9;
      }
      hProcess = (unsigned int)phkResult.hProcess;
    }
    v9 = hProcess;
    goto LABEL_41;
  }
  return v9;
}

```

## disassembly

```asm
0x1801cf0b0  push    rbp
0x1801cf0b2  push    rbx
0x1801cf0b3  push    rsi
0x1801cf0b4  push    rdi
0x1801cf0b5  push    r12
0x1801cf0b7  push    r13
0x1801cf0b9  push    r14
0x1801cf0bb  push    r15
0x1801cf0bd  lea     rbp, [rsp-5B8h]
0x1801cf0c5  sub     rsp, 6B8h
0x1801cf0cc  mov     rax, cs:__security_cookie
0x1801cf0d3  xor     rax, rsp
0x1801cf0d6  mov     [rbp+5F0h+var_50], rax
0x1801cf0dd  mov     r13, r9
0x1801cf0e0  mov     r14d, r8d
0x1801cf0e3  mov     r15, rdx
0x1801cf0e6  mov     r12, rcx
0x1801cf0e9  xor     ebx, ebx
0x1801cf0eb  lea     esi, [rbx+1]
0x1801cf0ee  mov     edi, [rbp+5F0h+arg_20]
0x1801cf0f4  test    edi, edi
0x1801cf0f6  jnz     loc_1801CF1F4
0x1801cf0fc  mov     [rsp+6F0h+bIgnoreCase], esi; bIgnoreCase
0x1801cf100  or      eax, 0FFFFFFFFh
0x1801cf103  mov     r9d, eax; cchCount2
0x1801cf106  lea     r8, a000214e6000000; "{000214E6-0000-0000-C000-000000000046}"
0x1801cf10d  mov     edx, eax; cchCount1
0x1801cf10f  mov     rcx, r15; lpString1
0x1801cf112  call    cs:__imp_CompareStringOrdinal
0x1801cf118  cmp     eax, 2
0x1801cf11b  jz      short loc_1801CF14D
0x1801cf11d  mov     [rsp+6F0h+bIgnoreCase], esi; bIgnoreCase
0x1801cf121  or      edx, 0FFFFFFFFh; cchCount1
0x1801cf124  mov     r9d, edx; cchCount2
0x1801cf127  lea     r8, aAdd8ba80002b11; "{ADD8BA80-002B-11D0-8F0F-00C04FD7D062}"
0x1801cf12e  mov     rcx, r15; lpString1
0x1801cf131  call    cs:__imp_CompareStringOrdinal
0x1801cf137  cmp     eax, 2
0x1801cf13a  jz      short loc_1801CF14D
0x1801cf13c  cmp     r14d, 4
0x1801cf140  jnz     loc_1801CF1F4
0x1801cf146  mov     edi, esi
0x1801cf148  jmp     loc_1801CF1F4
0x1801cf14d  mov     [rsp+6F0h+phkResult], rbx
0x1801cf152  call    ?IsWUDFHostProcess@@YA_NXZ; IsWUDFHostProcess(void)
0x1801cf157  movzx   esi, al
0x1801cf15a  lea     rax, aClsid_2; "CLSID\\"
0x1801cf161  lea     r8, aSoftwareClasse_4; "Software\\Classes\\CLSID\\"
0x1801cf168  test    sil, sil
0x1801cf16b  cmovz   r8, rax; unsigned __int16 *
0x1801cf16f  mov     r10d, 0A7h
0x1801cf175  mov     edx, r10d; unsigned __int64
0x1801cf178  lea     rcx, [rbp+5F0h+SubKey]; unsigned __int16 *
0x1801cf17f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801cf184  test    eax, eax
0x1801cf186  js      short loc_1801CF1F4
0x1801cf188  mov     r8, r12; unsigned __int16 *
0x1801cf18b  mov     edx, r10d; unsigned __int64
0x1801cf18e  lea     rcx, [rbp+5F0h+SubKey]; unsigned __int16 *
0x1801cf195  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801cf19a  test    eax, eax
0x1801cf19c  js      short loc_1801CF1F4
0x1801cf19e  lea     r8, aShellfolder_1; "\\ShellFolder"
0x1801cf1a5  mov     edx, 0A7h; unsigned __int64
0x1801cf1aa  lea     rcx, [rbp+5F0h+SubKey]; unsigned __int16 *
0x1801cf1b1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801cf1b6  test    eax, eax
0x1801cf1b8  js      short loc_1801CF1F4
0x1801cf1ba  lea     rcx, ds:0FFFFFFFF80000000h[rsi*2]; hKey
0x1801cf1c2  lea     rax, [rsp+6F0h+phkResult]
0x1801cf1c7  mov     qword ptr [rsp+6F0h+bIgnoreCase], rax; phkResult
0x1801cf1cc  mov     r9d, 20019h; samDesired
0x1801cf1d2  xor     r8d, r8d; ulOptions
0x1801cf1d5  lea     rdx, [rbp+5F0h+SubKey]; lpSubKey
0x1801cf1dc  call    cs:__imp_RegOpenKeyExW
0x1801cf1e2  test    eax, eax
0x1801cf1e4  jnz     short loc_1801CF1F4
0x1801cf1e6  lea     edi, [rax+1]
0x1801cf1e9  mov     rcx, [rsp+6F0h+phkResult]; hKey
0x1801cf1ee  call    cs:__imp_RegCloseKey
0x1801cf1f4  mov     esi, 0FFFFh
0x1801cf1f9  cmp     edi, 1
0x1801cf1fc  cmovnz  esi, r14d
0x1801cf200  mov     dword ptr [rsp+6F0h+pvData], esi
0x1801cf204  mov     qword ptr [rsp+6F0h+bIgnoreCase], r15
0x1801cf209  mov     r9, r12
0x1801cf20c  lea     r8, aSS0xX; "%s %s 0x%X"
0x1801cf213  mov     edx, 5Ch ; '\'; unsigned __int64
0x1801cf218  lea     rcx, [rbp+5F0h+Value]; unsigned __int16 *
0x1801cf21c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801cf221  xor     r14d, r14d
0x1801cf224  test    eax, eax
0x1801cf226  js      loc_1801CF530
0x1801cf22c  mov     [rsp+6F0h+var_684], r14d
0x1801cf231  mov     [rsp+6F0h+var_680], 4
0x1801cf239  test    edi, edi
0x1801cf23b  jnz     short loc_1801CF283
0x1801cf23d  lea     rax, [rsp+6F0h+var_680]
0x1801cf242  mov     [rsp+6F0h+pcbData], rax; pcbData
0x1801cf247  lea     rax, [rsp+6F0h+var_684]
0x1801cf24c  mov     [rsp+6F0h+pvData], rax; pvData
0x1801cf251  mov     qword ptr [rsp+6F0h+bIgnoreCase], r14; pdwType
0x1801cf256  lea     r9d, [r14+10h]; dwFlags
0x1801cf25a  lea     r8, [rbp+5F0h+Value]; lpValue
0x1801cf25e  lea     rdx, aSoftwareMicros_66; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801cf265  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1801cf26c  call    cs:__imp_RegGetValueW
0x1801cf272  test    eax, eax
0x1801cf274  jnz     short loc_1801CF283
0x1801cf276  cmp     [rsp+6F0h+var_684], r14d
0x1801cf27b  setnz   bl
0x1801cf27e  jmp     loc_1801CF445
0x1801cf283  xorps   xmm0, xmm0
0x1801cf286  movups  xmmword ptr [rsp+6F0h+phkResult], xmm0
0x1801cf28b  lea     r8, [rsp+6F0h+phkResult]; struct QICACHEENTRY *
0x1801cf290  lea     rdx, [rbp+5F0h+Value]; lpValue
0x1801cf294  lea     rcx, aSoftwareMicros_66; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801cf29b  call    ?GetQICacheEntry@@YAHPEBG0PEAUQICACHEENTRY@@@Z; GetQICacheEntry(ushort const *,ushort const *,QICACHEENTRY *)
0x1801cf2a0  test    eax, eax
0x1801cf2a2  jnz     short loc_1801CF2C6
0x1801cf2a4  call    ?IsEffectiveLowIL@@YAJXZ; IsEffectiveLowIL(void)
0x1801cf2a9  test    eax, eax
0x1801cf2ab  jnz     short loc_1801CF2E4
0x1801cf2ad  lea     r8, [rsp+6F0h+phkResult]; struct QICACHEENTRY *
0x1801cf2b2  lea     rdx, [rbp+5F0h+Value]; lpValue
0x1801cf2b6  lea     rcx, aSoftwareMicros_83; "Software\\Microsoft\\Internet Explorer"...
0x1801cf2bd  call    ?GetQICacheEntry@@YAHPEBG0PEAUQICACHEENTRY@@@Z; GetQICacheEntry(ushort const *,ushort const *,QICACHEENTRY *)
0x1801cf2c2  test    eax, eax
0x1801cf2c4  jz      short loc_1801CF2E4
0x1801cf2c6  mov     eax, dword ptr [rsp+6F0h+phkResult]
0x1801cf2ca  test    eax, eax
0x1801cf2cc  jnz     loc_1801CF443
0x1801cf2d2  mov     rcx, [rsp+6F0h+phkResult+8]; union _ULARGE_INTEGER
0x1801cf2d7  call    ?_CacheTimeValid@@YAHT_ULARGE_INTEGER@@@Z; _CacheTimeValid(_ULARGE_INTEGER)
0x1801cf2dc  test    eax, eax
0x1801cf2de  jnz     loc_1801CF43F
0x1801cf2e4  mov     eax, 1
0x1801cf2e9  cmp     edi, eax
0x1801cf2eb  jnz     short loc_1801CF2FF
0x1801cf2ed  mov     ebx, eax
0x1801cf2ef  mov     edx, eax; int
0x1801cf2f1  lea     rcx, [rbp+5F0h+Value]; lpValueName
0x1801cf2f5  call    ?_CacheEntry@@YAXPEBGH@Z; _CacheEntry(ushort const *,int)
0x1801cf2fa  jmp     loc_1801CF445
0x1801cf2ff  mov     edi, 104h
0x1801cf304  mov     edx, edi; uSize
0x1801cf306  lea     rcx, [rbp+5F0h+SubKey]; lpBuffer
0x1801cf30d  call    cs:__imp_GetSystemDirectoryW
0x1801cf313  test    eax, eax
0x1801cf315  jz      loc_1801CF445
0x1801cf31b  lea     r8, aVerclsidExe; "verclsid.exe"
0x1801cf322  mov     edx, edi; cchPath
0x1801cf324  lea     rcx, [rbp+5F0h+SubKey]; pszPath
0x1801cf32b  call    cs:__imp_PathCchAppend
0x1801cf331  test    eax, eax
0x1801cf333  js      loc_1801CF445
0x1801cf339  mov     dword ptr [rsp+6F0h+pcbData], esi; void *
0x1801cf33d  mov     [rsp+6F0h+pvData], r15; unsigned int
0x1801cf342  mov     qword ptr [rsp+6F0h+bIgnoreCase], r12; int
0x1801cf347  lea     r9, [rbp+5F0h+SubKey]
0x1801cf34e  lea     r8, aSSCSISX0xX; "\"%s\" /S /C %s /I %s /X 0x%X"
0x1801cf355  lea     edx, [rdi+68h]; unsigned __int64
0x1801cf358  lea     rcx, [rbp+5F0h+CommandLine]; unsigned __int16 *
0x1801cf35f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801cf364  test    eax, eax
0x1801cf366  js      loc_1801CF438
0x1801cf36c  mov     qword ptr [rbp+5F0h+var_670.cb], 68h ; 'h'
0x1801cf374  xor     edx, edx; Val
0x1801cf376  lea     r8d, [rdx+60h]; Size
0x1801cf37a  lea     rcx, [rbp+5F0h+var_670.lpReserved]; void *
0x1801cf37e  call    memset_0
0x1801cf383  xorps   xmm0, xmm0
0x1801cf386  xor     eax, eax
0x1801cf388  movups  xmmword ptr [rsp+6F0h+phkResult], xmm0
0x1801cf38d  mov     [rsp+6F0h+var_690], rax
0x1801cf392  lea     rax, [rsp+6F0h+phkResult]
0x1801cf397  mov     [rsp+6F0h+var_6A8], rax; struct _PROCESS_INFORMATION *
0x1801cf39c  lea     rax, [rbp+5F0h+var_670]
0x1801cf3a0  mov     [rsp+6F0h+var_6B0], rax; struct _STARTUPINFOW *
0x1801cf3a5  lea     rdx, [rbp+5F0h+CommandLine]; lpCommandLine
0x1801cf3ac  lea     rcx, [rbp+5F0h+SubKey]; lpApplicationName
0x1801cf3b3  call    ?CreateProcessWithImpersonation@@YAHPEBGPEAGPEAU_SECURITY_ATTRIBUTES@@2HKPEAX0PEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@@Z; CreateProcessWithImpersonation(ushort const *,ushort *,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES *,int,ulong,void *,ushort const *,_STARTUPINFOW *,_PROCESS_INFORMATION *)
0x1801cf3b8  test    eax, eax
0x1801cf3ba  jz      short loc_1801CF41B
0x1801cf3bc  mov     [rsp+6F0h+ExitCode], r14d
0x1801cf3c1  mov     edx, 3A98h; dwMilliseconds
0x1801cf3c6  mov     rcx, [rsp+6F0h+phkResult]; hHandle
0x1801cf3cb  call    cs:__imp_WaitForSingleObject
0x1801cf3d1  test    eax, eax
0x1801cf3d3  jnz     short loc_1801CF3F3
0x1801cf3d5  lea     rdx, [rsp+6F0h+ExitCode]; lpExitCode
0x1801cf3da  mov     rcx, [rsp+6F0h+phkResult]; hProcess
0x1801cf3df  call    cs:__imp_GetExitCodeProcess
0x1801cf3e5  test    eax, eax
0x1801cf3e7  jz      short loc_1801CF3F3
0x1801cf3e9  cmp     [rsp+6F0h+ExitCode], r14d
0x1801cf3ee  setz    bl
0x1801cf3f1  jmp     short loc_1801CF403
0x1801cf3f3  mov     edx, 2; uExitCode
0x1801cf3f8  mov     rcx, [rsp+6F0h+phkResult]; hProcess
0x1801cf3fd  call    cs:__imp_TerminateProcess
0x1801cf403  mov     rcx, [rsp+6F0h+phkResult+8]; hObject
0x1801cf408  call    cs:__imp_CloseHandle
0x1801cf40e  mov     rcx, [rsp+6F0h+phkResult]; hObject
0x1801cf413  call    cs:__imp_CloseHandle
0x1801cf419  jmp     short loc_1801CF438
0x1801cf41b  call    cs:__imp_GetLastError
0x1801cf421  cmp     eax, 2
0x1801cf424  jz      short loc_1801CF433
0x1801cf426  call    cs:__imp_GetLastError
0x1801cf42c  cmp     eax, 718h
0x1801cf431  jnz     short loc_1801CF438
0x1801cf433  mov     ebx, 1
0x1801cf438  mov     edx, ebx
0x1801cf43a  jmp     loc_1801CF2F1
0x1801cf43f  mov     eax, dword ptr [rsp+6F0h+phkResult]
0x1801cf443  mov     ebx, eax
0x1801cf445  call    ?IsEnabled@Shell32LoggingTelemetry@@SA_NE_K@Z; Shell32LoggingTelemetry::IsEnabled(uchar,unsigned __int64)
0x1801cf44a  test    al, al
0x1801cf44c  jz      loc_1801CF530
0x1801cf452  mov     [rsp+6F0h+ExitCode], r14d
0x1801cf457  mov     [rsp+6F0h+var_67C], 4
0x1801cf45f  lea     rax, [rsp+6F0h+var_67C]
0x1801cf464  mov     [rsp+6F0h+pcbData], rax; pcbData
0x1801cf469  lea     rax, [rsp+6F0h+ExitCode]
0x1801cf46e  mov     [rsp+6F0h+pvData], rax; pvData
0x1801cf473  mov     qword ptr [rsp+6F0h+bIgnoreCase], r14; pdwType
0x1801cf478  mov     r9d, 10h; dwFlags
0x1801cf47e  lea     r8, aHasflushedshel; "HasFlushedShellExtCache"
0x1801cf485  lea     rdx, aSoftwareMicros_36; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801cf48c  mov     rdi, 0FFFFFFFF80000001h
0x1801cf493  mov     rcx, rdi; hkey
0x1801cf496  call    cs:__imp_RegGetValueW
0x1801cf49c  test    eax, eax
0x1801cf49e  jnz     short loc_1801CF4DF
0x1801cf4a0  cmp     [rsp+6F0h+ExitCode], r14d
0x1801cf4a5  jz      short loc_1801CF4DF
0x1801cf4a7  test    ebx, ebx
0x1801cf4a9  jz      loc_1801CF530
0x1801cf4af  call    ?IsEnabled@Shell32LoggingTelemetry@@SA_NE_K@Z; Shell32LoggingTelemetry::IsEnabled(uchar,unsigned __int64)
0x1801cf4b4  test    al, al
0x1801cf4b6  jz      short loc_1801CF4DD
0x1801cf4b8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_24fe894bbe862470a274f72532562200_@@CA@XZ; _lambda_24fe894bbe862470a274f72532562200_::_lambda_invoker_cdecl_(void)
0x1801cf4bf  call    ?get@?$static_lazy@VShell32LoggingTelemetry@@@details@wil@@QEAAPEAVShell32LoggingTelemetry@@P6AXXZ@Z; wil::details::static_lazy<Shell32LoggingTelemetry>::get(void (*)(void))
0x1801cf4c4  mov     dword ptr [rsp+6F0h+pvData], r14d; int
0x1801cf4c9  mov     qword ptr [rsp+6F0h+bIgnoreCase], r13; unsigned __int16 *
0x1801cf4ce  mov     r9d, esi; unsigned int
0x1801cf4d1  mov     r8, r15; unsigned __int16 *
0x1801cf4d4  mov     rdx, r12; unsigned __int16 *
0x1801cf4d7  call    ?ShellExtensionList_@Shell32LoggingTelemetry@@QEAAXPEBG0K0H@Z; Shell32LoggingTelemetry::ShellExtensionList_(ushort const *,ushort const *,ulong,ushort const *,int)
0x1801cf4dc  nop
0x1801cf4dd  jmp     short loc_1801CF530
0x1801cf4df  mov     dword ptr [rsp+6F0h+phkResult], 1
0x1801cf4e7  mov     ecx, 4
0x1801cf4ec  mov     dword ptr [rsp+6F0h+pvData], ecx; cbData
0x1801cf4f0  lea     rax, [rsp+6F0h+phkResult]
0x1801cf4f5  mov     qword ptr [rsp+6F0h+bIgnoreCase], rax; lpData
0x1801cf4fa  mov     r9d, ecx; dwType
0x1801cf4fd  lea     r8, aHasflushedshel; "HasFlushedShellExtCache"
0x1801cf504  lea     rdx, aSoftwareMicros_36; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801cf50b  mov     rcx, rdi; hKey
0x1801cf50e  call    cs:__imp_RegSetKeyValueW
0x1801cf514  test    eax, eax
0x1801cf516  jnz     short loc_1801CF530
0x1801cf518  lea     rcx, aSoftwareMicros_66; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801cf51f  call    ?_PumpForCache@@YAXPEBG@Z; _PumpForCache(ushort const *)
0x1801cf524  lea     rcx, aSoftwareMicros_83; "Software\\Microsoft\\Internet Explorer"...
0x1801cf52b  call    ?_PumpForCache@@YAXPEBG@Z; _PumpForCache(ushort const *)
0x1801cf530  mov     eax, ebx
0x1801cf532  mov     rcx, [rbp+5F0h+var_50]
0x1801cf539  xor     rcx, rsp; StackCookie
0x1801cf53c  call    __security_check_cookie
0x1801cf541  add     rsp, 6B8h
0x1801cf548  pop     r15
0x1801cf54a  pop     r14
0x1801cf54c  pop     r13
0x1801cf54e  pop     r12
0x1801cf550  pop     rdi
0x1801cf551  pop     rsi
0x1801cf552  pop     rbx
0x1801cf553  pop     rbp
0x1801cf554  retn
```
