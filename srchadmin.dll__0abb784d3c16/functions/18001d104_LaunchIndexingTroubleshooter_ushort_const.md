# LaunchIndexingTroubleshooter(ushort const *)

- ea: `0x18001d104`
- end: `0x18001d207`
- name: `?LaunchIndexingTroubleshooter@@YAJPEBG@Z`
- size: `259`
- prototype: `__int64 __fastcall(LPCWSTR lpString)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800192dc`
- `0x180027ef8`

## callees

- `0x18000687c`
- `0x1800095c0`
- `0x18000d4dc`
- `0x18001a220`
- `0x18001d104`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x18001d1d2`
- `SHELL32!ShellExecuteExW` at `0x18001d1d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d1ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d1ea`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001d129`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001d134`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001d129`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001d134`

## string_xrefs

- `0x18001d1b1`: `%windir%\System32\msdt.exe`

## pseudocode

```c
__int64 __fastcall LaunchIndexingTroubleshooter(LPCWSTR lpString)
{
  int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rsi
  __int64 v5; // rcx
  int Error; // ebx
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-78h] BYREF

  v2 = lstrlenW(L"-skip TRUE -id SearchDiagnostic -ep %s");
  v3 = (unsigned int)(v2 + lstrlenW(lpString) - 2);
  v4 = (int)v3;
  Error = _AllocStringWorker<CTCoAllocPolicy>(v5, v3, 0, (int)v3);
  if ( Error >= 0 )
  {
    Error = StringCchPrintfW(0, v4 + 1, L"-skip TRUE -id SearchDiagnostic -ep %s", lpString);
    if ( Error >= 0 )
    {
      memset_0(&pExecInfo, 0, sizeof(pExecInfo));
      pExecInfo.cbSize = 112;
      pExecInfo.lpVerb = L"open";
      pExecInfo.fMask = 512;
      pExecInfo.lpFile = L"%windir%\\System32\\msdt.exe";
      pExecInfo.lpParameters = 0;
      pExecInfo.nShow = 5;
      if ( ShellExecuteExW(&pExecInfo) )
        Error = 0;
      else
        Error = ResultFromKnownLastError();
    }
    CoTaskMemFree(0);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001d104  mov     rax, rsp
0x18001d107  mov     [rax+8], rbx
0x18001d10b  mov     [rax+18h], rsi
0x18001d10f  push    rdi
0x18001d110  sub     rsp, 0A0h
0x18001d117  mov     rdi, rcx
0x18001d11a  mov     qword ptr [rax+10h], 0
0x18001d122  lea     rcx, aSkipTrueIdSear; "-skip TRUE -id SearchDiagnostic -ep %s"
0x18001d129  call    cs:__imp_lstrlenW
0x18001d12f  mov     rcx, rdi; lpString
0x18001d132  mov     ebx, eax
0x18001d134  call    cs:__imp_lstrlenW
0x18001d13a  xor     r8d, r8d
0x18001d13d  lea     edx, [rax-2]
0x18001d140  add     edx, ebx
0x18001d142  lea     rax, [rsp+0A8h+pv]
0x18001d14a  movsxd  rsi, edx
0x18001d14d  mov     r9, rsi
0x18001d150  mov     [rsp+0A8h+var_80], rax
0x18001d155  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18001d15a  mov     ebx, eax
0x18001d15c  test    eax, eax
0x18001d15e  js      loc_18001D1F0
0x18001d164  mov     r9, rdi
0x18001d167  lea     rdx, [rsi+1]; unsigned __int64
0x18001d16b  mov     rdi, [rsp+0A8h+pv]
0x18001d173  lea     r8, aSkipTrueIdSear; "-skip TRUE -id SearchDiagnostic -ep %s"
0x18001d17a  mov     rcx, rdi; unsigned __int16 *
0x18001d17d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d182  mov     ebx, eax
0x18001d184  test    eax, eax
0x18001d186  js      short loc_18001D1E7
0x18001d188  mov     ebx, 70h ; 'p'
0x18001d18d  lea     rcx, [rsp+0A8h+pExecInfo]; void *
0x18001d192  mov     r8d, ebx; Size
0x18001d195  xor     edx, edx; Val
0x18001d197  call    memset_0
0x18001d19c  lea     rax, aOpen; "open"
0x18001d1a3  mov     [rsp+0A8h+pExecInfo.cbSize], ebx
0x18001d1a7  mov     [rsp+0A8h+pExecInfo.lpVerb], rax
0x18001d1ac  lea     rcx, [rsp+0A8h+pExecInfo]; pExecInfo
0x18001d1b1  lea     rax, aWindirSystem32; "%windir%\\System32\\msdt.exe"
0x18001d1b8  mov     [rsp+0A8h+pExecInfo.fMask], 200h
0x18001d1c0  mov     [rsp+0A8h+pExecInfo.lpFile], rax
0x18001d1c5  mov     [rsp+0A8h+pExecInfo.lpParameters], rdi
0x18001d1ca  mov     [rsp+0A8h+pExecInfo.nShow], 5
0x18001d1d2  call    cs:__imp_ShellExecuteExW
0x18001d1d8  test    eax, eax
0x18001d1da  jz      short loc_18001D1E0
0x18001d1dc  xor     ebx, ebx
0x18001d1de  jmp     short loc_18001D1E7
0x18001d1e0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001d1e5  mov     ebx, eax
0x18001d1e7  mov     rcx, rdi; pv
0x18001d1ea  call    cs:__imp_CoTaskMemFree
0x18001d1f0  lea     r11, [rsp+0A8h+var_8]
0x18001d1f8  mov     eax, ebx
0x18001d1fa  mov     rbx, [r11+10h]
0x18001d1fe  mov     rsi, [r11+20h]
0x18001d202  mov     rsp, r11
0x18001d205  pop     rdi
0x18001d206  retn
```
