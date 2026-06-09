# ReportTimeout(void *)

- ea: `0x18003a980`
- end: `0x18003ab87`
- name: `?ReportTimeout@@YAXPEAX@Z`
- size: `519`
- prototype: `void __fastcall(HANDLE hThread)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18001bfe0`
- `0x18002b11c`
- `0x180035830`
- `0x1800364ac`
- `0x18003a07c`
- `0x18003a980`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ab01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ab01`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003a9ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003a9ff`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003aa24`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003aa24`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003aa64`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003aa64`
- `wer!WerReportSubmit` at `0x18003ab52`
- `wer!WerReportSubmit` at `0x18003ab52`
- `wer!WerReportAddDump` at `0x18003ab2f`
- `wer!WerReportAddDump` at `0x18003ab2f`
- `wer!WerReportCreate` at `0x18003aa8e`
- `wer!WerReportCreate` at `0x18003aa8e`
- `wer!WerReportSetParameter` at `0x18003aaad`
- `wer!WerReportSetParameter` at `0x18003aad3`
- `wer!WerReportSetParameter` at `0x18003aaf7`
- `wer!WerReportSetParameter` at `0x18003aaad`
- `wer!WerReportSetParameter` at `0x18003aad3`
- `wer!WerReportSetParameter` at `0x18003aaf7`
- `wer!WerReportCloseHandle` at `0x18003ab5d`
- `wer!WerReportCloseHandle` at `0x18003ab5d`

## string_xrefs

- `0x18003aaee`: `Clsid`

## pseudocode

```c
void __fastcall ReportTimeout(HANDLE hThread, __int64 a2, __int64 a3)
{
  const WCHAR *FileNameW; // rdi
  HANDLE CurrentProcess; // rax
  HREPORT phReportHandle; // [rsp+40h] [rbp-C0h] BYREF
  _WER_SUBMIT_RESULT pSubmitResult; // [rsp+48h] [rbp-B8h] BYREF
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v9[16]; // [rsp+8F0h] [rbp+7F0h] BYREF
  OLECHAR sz[40]; // [rsp+900h] [rbp+800h] BYREF
  WCHAR pwzValue[8]; // [rsp+950h] [rbp+850h] BYREF
  _BYTE v12[192]; // [rsp+960h] [rbp+860h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(hThread, Thumbnails_HostSelfDestruct_Info, a3, 1, v9);
  *(_QWORD *)&pReportInformation.dwSize = 2208;
  memset_0(&pReportInformation.hProcess, 0, 0x898u);
  GetModuleFileNameW(0, pReportInformation.wzApplicationPath, 0x104u);
  StringCchCopyW(pReportInformation.wzApplicationName, 0x80u, L"WindowsExplorer");
  FileNameW = PathFindFileNameW(pReportInformation.wzApplicationPath);
  wcscpy(pwzValue, L"0.0.0.0");
  memset_0(v12, 0, 0xB8u);
  StringFromGUID2(&g_clsidActive, sz, 39);
  ThumbnailCacheTelemetry::GetThumbnailWrapperTimeout<_GUID &>();
  phReportHandle = 0;
  if ( WerReportCreate(L"ShellThumbnailExtractionTimeout", WerReportCritical, &pReportInformation, &phReportHandle) >= 0 )
  {
    if ( WerReportSetParameter(phReportHandle, 0, L"AppName", FileNameW) >= 0
      && WerReportSetParameter(phReportHandle, 1u, L"AppVersion", pwzValue) >= 0
      && WerReportSetParameter(phReportHandle, 2u, L"Clsid", sz) >= 0 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( WerReportAddDump(phReportHandle, CurrentProcess, hThread, WerDumpTypeMiniDump, 0, 0, 0) >= 0 )
      {
        pSubmitResult = 0;
        WerReportSubmit(phReportHandle, WerConsentNotAsked, 0x24u, &pSubmitResult);
      }
    }
    WerReportCloseHandle(phReportHandle);
  }
}

```

## disassembly

```asm
0x18003a980  mov     [rsp-8+arg_8], rbx
0x18003a985  mov     [rsp-8+arg_10], rdi
0x18003a98a  push    rbp
0x18003a98b  lea     rbp, [rsp-930h]
0x18003a993  sub     rsp, 0A30h
0x18003a99a  mov     rax, cs:__security_cookie
0x18003a9a1  xor     rax, rsp
0x18003a9a4  mov     [rbp+930h+var_10], rax
0x18003a9ab  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18003a9b2  mov     rbx, rcx
0x18003a9b5  jz      short loc_18003A9D5
0x18003a9b7  lea     rax, [rbp+930h+var_140]
0x18003a9be  mov     r9d, 1
0x18003a9c4  lea     rdx, Thumbnails_HostSelfDestruct_Info
0x18003a9cb  mov     [rsp+0A30h+pExceptionParam], rax
0x18003a9d0  call    McGenEventWrite_EventWriteTransfer
0x18003a9d5  xor     edx, edx; Val
0x18003a9d7  mov     qword ptr [rsp+0A30h+pReportInformation.dwSize], 8A0h
0x18003a9e0  mov     r8d, 898h; Size
0x18003a9e6  lea     rcx, [rsp+0A30h+pReportInformation.hProcess]; void *
0x18003a9eb  call    memset_0
0x18003a9f0  mov     r8d, 104h; nSize
0x18003a9f6  lea     rdx, [rbp+930h+pReportInformation.wzApplicationPath]; lpFilename
0x18003a9fd  xor     ecx, ecx; hModule
0x18003a9ff  call    cs:__imp_GetModuleFileNameW
0x18003aa05  lea     r8, aWindowsexplore; "WindowsExplorer"
0x18003aa0c  mov     edx, 80h; unsigned __int64
0x18003aa11  lea     rcx, [rbp+930h+pReportInformation.wzApplicationName]; unsigned __int16 *
0x18003aa18  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003aa1d  lea     rcx, [rbp+930h+pReportInformation.wzApplicationPath]; pszPath
0x18003aa24  call    cs:__imp_PathFindFileNameW
0x18003aa2a  movups  xmm0, xmmword ptr cs:a0000; "0.0.0.0"
0x18003aa31  xor     edx, edx; Val
0x18003aa33  lea     rcx, [rbp+930h+var_D0]; void *
0x18003aa3a  mov     r8d, 0B8h; Size
0x18003aa40  mov     rdi, rax
0x18003aa43  movdqu  xmmword ptr [rbp+930h+pwzValue], xmm0
0x18003aa4b  call    memset_0
0x18003aa50  mov     r8d, 27h ; '''; cchMax
0x18003aa56  lea     rdx, [rbp+930h+sz]; lpsz
0x18003aa5d  lea     rcx, ?g_clsidActive@@3U_GUID@@A; rguid
0x18003aa64  call    cs:__imp_StringFromGUID2
0x18003aa6a  call    ??$GetThumbnailWrapperTimeout@AEAU_GUID@@@ThumbnailCacheTelemetry@@SAXAEAU_GUID@@@Z; ThumbnailCacheTelemetry::GetThumbnailWrapperTimeout<_GUID &>(_GUID &)
0x18003aa6f  lea     r9, [rsp+0A30h+phReportHandle]; phReportHandle
0x18003aa74  mov     [rsp+0A30h+phReportHandle], 0
0x18003aa7d  lea     r8, [rsp+0A30h+pReportInformation]; pReportInformation
0x18003aa82  mov     edx, 1; repType
0x18003aa87  lea     rcx, pwzEventType; "ShellThumbnailExtractionTimeout"
0x18003aa8e  call    cs:__imp_WerReportCreate
0x18003aa94  test    eax, eax
0x18003aa96  js      loc_18003AB63
0x18003aa9c  mov     rcx, [rsp+0A30h+phReportHandle]; hReportHandle
0x18003aaa1  lea     r8, pwzName; "AppName"
0x18003aaa8  mov     r9, rdi; pwzValue
0x18003aaab  xor     edx, edx; dwparamID
0x18003aaad  call    cs:__imp_WerReportSetParameter
0x18003aab3  test    eax, eax
0x18003aab5  js      loc_18003AB58
0x18003aabb  mov     rcx, [rsp+0A30h+phReportHandle]; hReportHandle
0x18003aac0  lea     r9, [rbp+930h+pwzValue]; pwzValue
0x18003aac7  lea     r8, aAppversion; "AppVersion"
0x18003aace  mov     edx, 1; dwparamID
0x18003aad3  call    cs:__imp_WerReportSetParameter
0x18003aad9  test    eax, eax
0x18003aadb  js      short loc_18003AB58
0x18003aadd  mov     rcx, [rsp+0A30h+phReportHandle]; hReportHandle
0x18003aae2  lea     r9, [rbp+930h+sz]; pwzValue
0x18003aae9  mov     edi, 2
0x18003aaee  lea     r8, aClsid; "Clsid"
0x18003aaf5  mov     edx, edi; dwparamID
0x18003aaf7  call    cs:__imp_WerReportSetParameter
0x18003aafd  test    eax, eax
0x18003aaff  js      short loc_18003AB58
0x18003ab01  call    cs:__imp_GetCurrentProcess
0x18003ab07  mov     rcx, [rsp+0A30h+phReportHandle]; hReportHandle
0x18003ab0c  mov     r9d, edi; dumpType
0x18003ab0f  mov     [rsp+0A30h+dwFlags], 0; dwFlags
0x18003ab17  mov     rdx, rax; hProcess
0x18003ab1a  mov     [rsp+0A30h+pDumpCustomOptions], 0; pDumpCustomOptions
0x18003ab23  mov     r8, rbx; hThread
0x18003ab26  mov     [rsp+0A30h+pExceptionParam], 0; pExceptionParam
0x18003ab2f  call    cs:__imp_WerReportAddDump
0x18003ab35  test    eax, eax
0x18003ab37  js      short loc_18003AB58
0x18003ab39  mov     rcx, [rsp+0A30h+phReportHandle]; hReportHandle
0x18003ab3e  lea     r9, [rsp+0A30h+pSubmitResult]; pSubmitResult
0x18003ab43  lea     edx, [rdi-1]; consent
0x18003ab46  mov     [rsp+0A30h+pSubmitResult], 0
0x18003ab4e  lea     r8d, [rdi+22h]; dwFlags
0x18003ab52  call    cs:__imp_WerReportSubmit
0x18003ab58  mov     rcx, [rsp+0A30h+phReportHandle]; hReportHandle
0x18003ab5d  call    cs:__imp_WerReportCloseHandle
0x18003ab63  mov     rcx, [rbp+930h+var_10]
0x18003ab6a  xor     rcx, rsp; StackCookie
0x18003ab6d  call    __security_check_cookie
0x18003ab72  lea     r11, [rsp+0A30h+var_s0]
0x18003ab7a  mov     rbx, [r11+18h]
0x18003ab7e  mov     rdi, [r11+20h]
0x18003ab82  mov     rsp, r11
0x18003ab85  pop     rbp
0x18003ab86  retn
```
