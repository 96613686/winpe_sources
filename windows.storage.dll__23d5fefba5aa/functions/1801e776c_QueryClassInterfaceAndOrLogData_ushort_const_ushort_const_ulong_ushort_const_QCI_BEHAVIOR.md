# _QueryClassInterfaceAndOrLogData(ushort const *,ushort const *,ulong,ushort const *,QCI_BEHAVIOR)

- ea: `0x1801e776c`
- end: `0x1801e7c72`
- name: `?_QueryClassInterfaceAndOrLogData@@YAHPEBG0K0W4QCI_BEHAVIOR@@@Z`
- size: `1286`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801e6f50`

## callees

- `0x180045bd0`
- `0x180133f50`
- `0x180135090`
- `0x1801be7cc`
- `0x1801c0464`
- `0x1801e776c`
- `0x18027c814`
- `0x18027c838`
- `0x18027c90c`
- `0x1802b0438`
- `0x1803103ec`
- `0x18036a670`
- `0x18036f7d0`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1805df8a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801e7ab1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801e7ab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e7b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e7b30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e7b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e7b30`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1801e7aef`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1801e7aef`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1801e7acb`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1801e7acb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801e7b00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801e7b11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801e7b00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801e7b11`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e77ce`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e77f3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e77ce`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e77f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801e78bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801e78bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801e78a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801e78a4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801e7940`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801e7ba6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801e7940`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801e7ba6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801e79e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801e79e7`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1801e7a0b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1801e7a0b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1801e7c24`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1801e7c24`

## string_xrefs

- `0x1801e7932`: `Software\Microsoft\Windows\CurrentVersion\Shell Extensions\Cached`
- `0x1801e796e`: `Software\Microsoft\Windows\CurrentVersion\Shell Extensions\Cached`
- `0x1801e7c34`: `Software\Microsoft\Windows\CurrentVersion\Shell Extensions\Cached`
- `0x1801e7990`: `Software\Microsoft\Internet Explorer\LowRegistry\Shell Extensions\Cached`
- `0x1801e7c40`: `Software\Microsoft\Internet Explorer\LowRegistry\Shell Extensions\Cached`
- `0x1801e7829`: `Software\Classes\CLSID\`
- `0x1801e7b8e`: `HasFlushedShellExtCache`
- `0x1801e7c13`: `HasFlushedShellExtCache`
- `0x1801e7b95`: `Software\Microsoft\Windows\CurrentVersion\Shell Extensions`
- `0x1801e7c1a`: `Software\Microsoft\Windows\CurrentVersion\Shell Extensions`
- `0x1801e79fb`: `verclsid.exe`
- `0x1801e7822`: `CLSID\`

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
0x1801e776c  push    rbp
0x1801e776e  push    rbx
0x1801e776f  push    rsi
0x1801e7770  push    rdi
0x1801e7771  push    r12
0x1801e7773  push    r13
0x1801e7775  push    r14
0x1801e7777  push    r15
0x1801e7779  lea     rbp, [rsp-5B8h]
0x1801e7781  sub     rsp, 6B8h
0x1801e7788  mov     rax, cs:__security_cookie
0x1801e778f  xor     rax, rsp
0x1801e7792  mov     [rbp+5F0h+var_50], rax
0x1801e7799  mov     r13, r9
0x1801e779c  mov     r14d, r8d
0x1801e779f  mov     r15, rdx
0x1801e77a2  mov     r12, rcx
0x1801e77a5  xor     ebx, ebx
0x1801e77a7  lea     esi, [rbx+1]
0x1801e77aa  mov     edi, [rbp+5F0h+arg_20]
0x1801e77b0  test    edi, edi
0x1801e77b2  jnz     loc_1801E78C8
0x1801e77b8  mov     [rsp+6F0h+bIgnoreCase], esi; bIgnoreCase
0x1801e77bc  or      eax, 0FFFFFFFFh
0x1801e77bf  mov     r9d, eax; cchCount2
0x1801e77c2  lea     r8, a000214e6000000; "{000214E6-0000-0000-C000-000000000046}"
0x1801e77c9  mov     edx, eax; cchCount1
0x1801e77cb  mov     rcx, r15; lpString1
0x1801e77ce  call    cs:__imp_CompareStringOrdinal
0x1801e77d5  nop     dword ptr [rax+rax+00h]
0x1801e77da  cmp     eax, 2
0x1801e77dd  jz      short loc_1801E7815
0x1801e77df  mov     [rsp+6F0h+bIgnoreCase], esi; bIgnoreCase
0x1801e77e3  or      edx, 0FFFFFFFFh; cchCount1
0x1801e77e6  mov     r9d, edx; cchCount2
0x1801e77e9  lea     r8, aAdd8ba80002b11; "{ADD8BA80-002B-11D0-8F0F-00C04FD7D062}"
0x1801e77f0  mov     rcx, r15; lpString1
0x1801e77f3  call    cs:__imp_CompareStringOrdinal
0x1801e77fa  nop     dword ptr [rax+rax+00h]
0x1801e77ff  cmp     eax, 2
0x1801e7802  jz      short loc_1801E7815
0x1801e7804  cmp     r14d, 4
0x1801e7808  jnz     loc_1801E78C8
0x1801e780e  mov     edi, esi
0x1801e7810  jmp     loc_1801E78C8
0x1801e7815  mov     [rsp+6F0h+phkResult], rbx
0x1801e781a  call    ?IsWUDFHostProcess@@YA_NXZ; IsWUDFHostProcess(void)
0x1801e781f  movzx   esi, al
0x1801e7822  lea     rax, aClsid_2; "CLSID\\"
0x1801e7829  lea     r8, aSoftwareClasse_4; "Software\\Classes\\CLSID\\"
0x1801e7830  test    sil, sil
0x1801e7833  cmovz   r8, rax; unsigned __int16 *
0x1801e7837  mov     r10d, 0A7h
0x1801e783d  mov     edx, r10d; unsigned __int64
0x1801e7840  lea     rcx, [rbp+5F0h+SubKey]; unsigned __int16 *
0x1801e7847  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801e784c  test    eax, eax
0x1801e784e  js      short loc_1801E78C8
0x1801e7850  mov     r8, r12; unsigned __int16 *
0x1801e7853  mov     edx, r10d; unsigned __int64
0x1801e7856  lea     rcx, [rbp+5F0h+SubKey]; unsigned __int16 *
0x1801e785d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801e7862  test    eax, eax
0x1801e7864  js      short loc_1801E78C8
0x1801e7866  lea     r8, aShellfolder_1; "\\ShellFolder"
0x1801e786d  mov     edx, 0A7h; unsigned __int64
0x1801e7872  lea     rcx, [rbp+5F0h+SubKey]; unsigned __int16 *
0x1801e7879  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801e787e  test    eax, eax
0x1801e7880  js      short loc_1801E78C8
0x1801e7882  lea     rcx, ds:0FFFFFFFF80000000h[rsi*2]; hKey
0x1801e788a  lea     rax, [rsp+6F0h+phkResult]
0x1801e788f  mov     qword ptr [rsp+6F0h+bIgnoreCase], rax; phkResult
0x1801e7894  mov     r9d, 20019h; samDesired
0x1801e789a  xor     r8d, r8d; ulOptions
0x1801e789d  lea     rdx, [rbp+5F0h+SubKey]; lpSubKey
0x1801e78a4  call    cs:__imp_RegOpenKeyExW
0x1801e78ab  nop     dword ptr [rax+rax+00h]
0x1801e78b0  test    eax, eax
0x1801e78b2  jnz     short loc_1801E78C8
0x1801e78b4  lea     edi, [rax+1]
0x1801e78b7  mov     rcx, [rsp+6F0h+phkResult]; hKey
0x1801e78bc  call    cs:__imp_RegCloseKey
0x1801e78c3  nop     dword ptr [rax+rax+00h]
0x1801e78c8  mov     esi, 0FFFFh
0x1801e78cd  cmp     edi, 1
0x1801e78d0  cmovnz  esi, r14d
0x1801e78d4  mov     dword ptr [rsp+6F0h+pvData], esi
0x1801e78d8  mov     qword ptr [rsp+6F0h+bIgnoreCase], r15
0x1801e78dd  mov     r9, r12
0x1801e78e0  lea     r8, aSS0xX; "%s %s 0x%X"
0x1801e78e7  mov     edx, 5Ch ; '\'; unsigned __int64
0x1801e78ec  lea     rcx, [rbp+5F0h+Value]; unsigned __int16 *
0x1801e78f0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801e78f5  xor     r14d, r14d
0x1801e78f8  test    eax, eax
0x1801e78fa  js      loc_1801E7C4C
0x1801e7900  mov     [rsp+6F0h+var_684], r14d
0x1801e7905  mov     [rsp+6F0h+var_680], 4
0x1801e790d  test    edi, edi
0x1801e790f  jnz     short loc_1801E795D
0x1801e7911  lea     rax, [rsp+6F0h+var_680]
0x1801e7916  mov     [rsp+6F0h+pcbData], rax; pcbData
0x1801e791b  lea     rax, [rsp+6F0h+var_684]
0x1801e7920  mov     [rsp+6F0h+pvData], rax; pvData
0x1801e7925  mov     qword ptr [rsp+6F0h+bIgnoreCase], r14; pdwType
0x1801e792a  lea     r9d, [r14+10h]; dwFlags
0x1801e792e  lea     r8, [rbp+5F0h+Value]; lpValue
0x1801e7932  lea     rdx, aSoftwareMicros_66; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801e7939  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1801e7940  call    cs:__imp_RegGetValueW
0x1801e7947  nop     dword ptr [rax+rax+00h]
0x1801e794c  test    eax, eax
0x1801e794e  jnz     short loc_1801E795D
0x1801e7950  cmp     [rsp+6F0h+var_684], r14d
0x1801e7955  setnz   bl
0x1801e7958  jmp     loc_1801E7B55
0x1801e795d  xorps   xmm0, xmm0
0x1801e7960  movups  xmmword ptr [rsp+6F0h+phkResult], xmm0
0x1801e7965  lea     r8, [rsp+6F0h+phkResult]; struct QICACHEENTRY *
0x1801e796a  lea     rdx, [rbp+5F0h+Value]; lpValue
0x1801e796e  lea     rcx, aSoftwareMicros_66; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801e7975  call    ?GetQICacheEntry@@YAHPEBG0PEAUQICACHEENTRY@@@Z; GetQICacheEntry(ushort const *,ushort const *,QICACHEENTRY *)
0x1801e797a  test    eax, eax
0x1801e797c  jnz     short loc_1801E79A0
0x1801e797e  call    ?IsEffectiveLowIL@@YAJXZ; IsEffectiveLowIL(void)
0x1801e7983  test    eax, eax
0x1801e7985  jnz     short loc_1801E79BE
0x1801e7987  lea     r8, [rsp+6F0h+phkResult]; struct QICACHEENTRY *
0x1801e798c  lea     rdx, [rbp+5F0h+Value]; lpValue
0x1801e7990  lea     rcx, aSoftwareMicros_83; "Software\\Microsoft\\Internet Explorer"...
0x1801e7997  call    ?GetQICacheEntry@@YAHPEBG0PEAUQICACHEENTRY@@@Z; GetQICacheEntry(ushort const *,ushort const *,QICACHEENTRY *)
0x1801e799c  test    eax, eax
0x1801e799e  jz      short loc_1801E79BE
0x1801e79a0  mov     eax, dword ptr [rsp+6F0h+phkResult]
0x1801e79a4  test    eax, eax
0x1801e79a6  jnz     loc_1801E7B53
0x1801e79ac  mov     rcx, [rsp+6F0h+phkResult+8]; union _ULARGE_INTEGER
0x1801e79b1  call    ?_CacheTimeValid@@YAHT_ULARGE_INTEGER@@@Z; _CacheTimeValid(_ULARGE_INTEGER)
0x1801e79b6  test    eax, eax
0x1801e79b8  jnz     loc_1801E7B4F
0x1801e79be  mov     eax, 1
0x1801e79c3  cmp     edi, eax
0x1801e79c5  jnz     short loc_1801E79D9
0x1801e79c7  mov     ebx, eax
0x1801e79c9  mov     edx, eax; int
0x1801e79cb  lea     rcx, [rbp+5F0h+Value]; lpValueName
0x1801e79cf  call    ?_CacheEntry@@YAXPEBGH@Z; _CacheEntry(ushort const *,int)
0x1801e79d4  jmp     loc_1801E7B55
0x1801e79d9  mov     edi, 104h
0x1801e79de  mov     edx, edi; uSize
0x1801e79e0  lea     rcx, [rbp+5F0h+SubKey]; lpBuffer
0x1801e79e7  call    cs:__imp_GetSystemDirectoryW
0x1801e79ee  nop     dword ptr [rax+rax+00h]
0x1801e79f3  test    eax, eax
0x1801e79f5  jz      loc_1801E7B55
0x1801e79fb  lea     r8, aVerclsidExe; "verclsid.exe"
0x1801e7a02  mov     edx, edi; cchPath
0x1801e7a04  lea     rcx, [rbp+5F0h+SubKey]; pszPath
0x1801e7a0b  call    cs:__imp_PathCchAppend
0x1801e7a12  nop     dword ptr [rax+rax+00h]
0x1801e7a17  test    eax, eax
0x1801e7a19  js      loc_1801E7B55
0x1801e7a1f  mov     dword ptr [rsp+6F0h+pcbData], esi; void *
0x1801e7a23  mov     [rsp+6F0h+pvData], r15; unsigned int
0x1801e7a28  mov     qword ptr [rsp+6F0h+bIgnoreCase], r12; int
0x1801e7a2d  lea     r9, [rbp+5F0h+SubKey]
0x1801e7a34  lea     r8, aSSCSISX0xX; "\"%s\" /S /C %s /I %s /X 0x%X"
0x1801e7a3b  lea     edx, [rdi+68h]; unsigned __int64
0x1801e7a3e  lea     rcx, [rbp+5F0h+CommandLine]; unsigned __int16 *
0x1801e7a45  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801e7a4a  test    eax, eax
0x1801e7a4c  js      loc_1801E7B48
0x1801e7a52  mov     qword ptr [rbp+5F0h+var_670.cb], 68h ; 'h'
0x1801e7a5a  xor     edx, edx; Val
0x1801e7a5c  lea     r8d, [rdx+60h]; Size
0x1801e7a60  lea     rcx, [rbp+5F0h+var_670.lpReserved]; void *
0x1801e7a64  call    memset_0
0x1801e7a69  xorps   xmm0, xmm0
0x1801e7a6c  xor     eax, eax
0x1801e7a6e  movups  xmmword ptr [rsp+6F0h+phkResult], xmm0
0x1801e7a73  mov     [rsp+6F0h+var_690], rax
0x1801e7a78  lea     rax, [rsp+6F0h+phkResult]
0x1801e7a7d  mov     [rsp+6F0h+var_6A8], rax; struct _PROCESS_INFORMATION *
0x1801e7a82  lea     rax, [rbp+5F0h+var_670]
0x1801e7a86  mov     [rsp+6F0h+var_6B0], rax; struct _STARTUPINFOW *
0x1801e7a8b  lea     rdx, [rbp+5F0h+CommandLine]; lpCommandLine
0x1801e7a92  lea     rcx, [rbp+5F0h+SubKey]; lpApplicationName
0x1801e7a99  call    ?CreateProcessWithImpersonation@@YAHPEBGPEAGPEAU_SECURITY_ATTRIBUTES@@2HKPEAX0PEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@@Z; CreateProcessWithImpersonation(ushort const *,ushort *,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES *,int,ulong,void *,ushort const *,_STARTUPINFOW *,_PROCESS_INFORMATION *)
0x1801e7a9e  test    eax, eax
0x1801e7aa0  jz      short loc_1801E7B1F
0x1801e7aa2  mov     [rsp+6F0h+ExitCode], r14d
0x1801e7aa7  mov     edx, 3A98h; dwMilliseconds
0x1801e7aac  mov     rcx, [rsp+6F0h+phkResult]; hHandle
0x1801e7ab1  call    cs:__imp_WaitForSingleObject
0x1801e7ab8  nop     dword ptr [rax+rax+00h]
0x1801e7abd  test    eax, eax
0x1801e7abf  jnz     short loc_1801E7AE5
0x1801e7ac1  lea     rdx, [rsp+6F0h+ExitCode]; lpExitCode
0x1801e7ac6  mov     rcx, [rsp+6F0h+phkResult]; hProcess
0x1801e7acb  call    cs:__imp_GetExitCodeProcess
0x1801e7ad2  nop     dword ptr [rax+rax+00h]
0x1801e7ad7  test    eax, eax
0x1801e7ad9  jz      short loc_1801E7AE5
0x1801e7adb  cmp     [rsp+6F0h+ExitCode], r14d
0x1801e7ae0  setz    bl
0x1801e7ae3  jmp     short loc_1801E7AFB
0x1801e7ae5  mov     edx, 2; uExitCode
0x1801e7aea  mov     rcx, [rsp+6F0h+phkResult]; hProcess
0x1801e7aef  call    cs:__imp_TerminateProcess
0x1801e7af6  nop     dword ptr [rax+rax+00h]
0x1801e7afb  mov     rcx, [rsp+6F0h+phkResult+8]; hObject
0x1801e7b00  call    cs:__imp_CloseHandle
0x1801e7b07  nop     dword ptr [rax+rax+00h]
0x1801e7b0c  mov     rcx, [rsp+6F0h+phkResult]; hObject
0x1801e7b11  call    cs:__imp_CloseHandle
0x1801e7b18  nop     dword ptr [rax+rax+00h]
0x1801e7b1d  jmp     short loc_1801E7B48
0x1801e7b1f  call    cs:__imp_GetLastError
0x1801e7b26  nop     dword ptr [rax+rax+00h]
0x1801e7b2b  cmp     eax, 2
0x1801e7b2e  jz      short loc_1801E7B43
0x1801e7b30  call    cs:__imp_GetLastError
0x1801e7b37  nop     dword ptr [rax+rax+00h]
0x1801e7b3c  cmp     eax, 718h
0x1801e7b41  jnz     short loc_1801E7B48
0x1801e7b43  mov     ebx, 1
0x1801e7b48  mov     edx, ebx
0x1801e7b4a  jmp     loc_1801E79CB
0x1801e7b4f  mov     eax, dword ptr [rsp+6F0h+phkResult]
0x1801e7b53  mov     ebx, eax
0x1801e7b55  call    ?IsEnabled@Shell32LoggingTelemetry@@SA_NE_K@Z; Shell32LoggingTelemetry::IsEnabled(uchar,unsigned __int64)
0x1801e7b5a  test    al, al
0x1801e7b5c  jz      loc_1801E7C4C
0x1801e7b62  mov     [rsp+6F0h+ExitCode], r14d
0x1801e7b67  mov     [rsp+6F0h+var_67C], 4
0x1801e7b6f  lea     rax, [rsp+6F0h+var_67C]
0x1801e7b74  mov     [rsp+6F0h+pcbData], rax; pcbData
0x1801e7b79  lea     rax, [rsp+6F0h+ExitCode]
0x1801e7b7e  mov     [rsp+6F0h+pvData], rax; pvData
0x1801e7b83  mov     qword ptr [rsp+6F0h+bIgnoreCase], r14; pdwType
0x1801e7b88  mov     r9d, 10h; dwFlags
0x1801e7b8e  lea     r8, aHasflushedshel; "HasFlushedShellExtCache"
0x1801e7b95  lea     rdx, aSoftwareMicros_36; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801e7b9c  mov     rdi, 0FFFFFFFF80000001h
0x1801e7ba3  mov     rcx, rdi; hkey
0x1801e7ba6  call    cs:__imp_RegGetValueW
0x1801e7bad  nop     dword ptr [rax+rax+00h]
0x1801e7bb2  test    eax, eax
0x1801e7bb4  jnz     short loc_1801E7BF5
0x1801e7bb6  cmp     [rsp+6F0h+ExitCode], r14d
0x1801e7bbb  jz      short loc_1801E7BF5
0x1801e7bbd  test    ebx, ebx
0x1801e7bbf  jz      loc_1801E7C4C
0x1801e7bc5  call    ?IsEnabled@Shell32LoggingTelemetry@@SA_NE_K@Z; Shell32LoggingTelemetry::IsEnabled(uchar,unsigned __int64)
0x1801e7bca  test    al, al
0x1801e7bcc  jz      short loc_1801E7BF3
0x1801e7bce  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_24fe894bbe862470a274f72532562200_@@CA@XZ; _lambda_24fe894bbe862470a274f72532562200_::_lambda_invoker_cdecl_(void)
0x1801e7bd5  call    ?get@?$static_lazy@VShell32LoggingTelemetry@@@details@wil@@QEAAPEAVShell32LoggingTelemetry@@P6AXXZ@Z; wil::details::static_lazy<Shell32LoggingTelemetry>::get(void (*)(void))
0x1801e7bda  mov     dword ptr [rsp+6F0h+pvData], r14d; int
0x1801e7bdf  mov     qword ptr [rsp+6F0h+bIgnoreCase], r13; unsigned __int16 *
0x1801e7be4  mov     r9d, esi; unsigned int
0x1801e7be7  mov     r8, r15; unsigned __int16 *
0x1801e7bea  mov     rdx, r12; unsigned __int16 *
0x1801e7bed  call    ?ShellExtensionList_@Shell32LoggingTelemetry@@QEAAXPEBG0K0H@Z; Shell32LoggingTelemetry::ShellExtensionList_(ushort const *,ushort const *,ulong,ushort const *,int)
0x1801e7bf2  nop
0x1801e7bf3  jmp     short loc_1801E7C4C
0x1801e7bf5  mov     dword ptr [rsp+6F0h+phkResult], 1
0x1801e7bfd  mov     ecx, 4
0x1801e7c02  mov     dword ptr [rsp+6F0h+pvData], ecx; cbData
0x1801e7c06  lea     rax, [rsp+6F0h+phkResult]
0x1801e7c0b  mov     qword ptr [rsp+6F0h+bIgnoreCase], rax; lpData
0x1801e7c10  mov     r9d, ecx; dwType
0x1801e7c13  lea     r8, aHasflushedshel; "HasFlushedShellExtCache"
0x1801e7c1a  lea     rdx, aSoftwareMicros_36; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801e7c21  mov     rcx, rdi; hKey
0x1801e7c24  call    cs:__imp_RegSetKeyValueW
0x1801e7c2b  nop     dword ptr [rax+rax+00h]
0x1801e7c30  test    eax, eax
0x1801e7c32  jnz     short loc_1801E7C4C
0x1801e7c34  lea     rcx, aSoftwareMicros_66; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801e7c3b  call    ?_PumpForCache@@YAXPEBG@Z; _PumpForCache(ushort const *)
0x1801e7c40  lea     rcx, aSoftwareMicros_83; "Software\\Microsoft\\Internet Explorer"...
0x1801e7c47  call    ?_PumpForCache@@YAXPEBG@Z; _PumpForCache(ushort const *)
0x1801e7c4c  mov     eax, ebx
0x1801e7c4e  mov     rcx, [rbp+5F0h+var_50]
0x1801e7c55  xor     rcx, rsp; StackCookie
0x1801e7c58  call    __security_check_cookie
0x1801e7c5d  add     rsp, 6B8h
0x1801e7c64  pop     r15
0x1801e7c66  pop     r14
0x1801e7c68  pop     r13
0x1801e7c6a  pop     r12
0x1801e7c6c  pop     rdi
0x1801e7c6d  pop     rsi
0x1801e7c6e  pop     rbx
0x1801e7c6f  pop     rbp
0x1801e7c70  retn
```
