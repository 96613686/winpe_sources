# SsLoadShareProviders

- ea: `0x1800131dc`
- end: `0x180013509`
- name: `SsLoadShareProviders`
- size: `813`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180014880`
- `0x18001da40`

## callees

- `0x1800131dc`
- `0x18001deb0`
- `0x18001e80c`
- `0x180020de8`
- `0x180022eb8`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013440`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800134e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800134e4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800132ae`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800132ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013245`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013245`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001330a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013334`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001330a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013334`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800134b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800134c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800134b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800134c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013353`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013353`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800134aa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800134aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013370`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013385`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001339a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800133af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800133c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013370`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013385`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001339a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800133af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800133c4`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001325e`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001325e`
- `ntdll!RtlReleaseResource` at `0x1800134d4`
- `ntdll!RtlReleaseResource` at `0x1800134d4`

## string_xrefs

- `0x180013227`: `SYSTEM\CurrentControlSet\Services\LanmanServer\ShareProviders`
- `0x18001338f`: `ShareProviderShareAdd`

## pseudocode

```c
__int64 SsLoadShareProviders()
{
  DWORD LastError; // esi
  DWORD v1; // edi
  int v2; // r14d
  _QWORD *v3; // rbx
  LSTATUS v4; // eax
  _QWORD *v5; // rax
  HLOCAL v6; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v9; // rcx
  FARPROC v10; // rax
  HMODULE v11; // rcx
  FARPROC v12; // rax
  HMODULE v13; // rcx
  FARPROC v14; // rax
  HMODULE v15; // rcx
  FARPROC v16; // rax
  bool v17; // zf
  _QWORD *v18; // rax
  unsigned int v19; // edi
  HMODULE v20; // rcx
  void *v21; // rcx
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Data[264]; // [rsp+270h] [rbp+170h] BYREF

  hKey = 0;
  cchValueName = 262;
  cbData = 524;
  Type = 0;
  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\ShareProviders",
                0,
                0x20019u,
                &hKey);
  if ( LastError )
  {
    v3 = 0;
    v2 = 0;
  }
  else
  {
    RtlAcquireResourceExclusive(&stru_18005CE48, 1u);
    v1 = 0;
    v2 = 1;
    while ( 1 )
    {
      v3 = 0;
      if ( LastError == 259 )
        break;
      v4 = RegEnumValueW(hKey, v1, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
      LastError = v4;
      if ( v4 != 234 )
      {
        if ( v4 )
          break;
        if ( Type == 1 && cbData <= 0x20C && cchValueName <= 0x106 && !SsFindShareProvider(ValueName) )
        {
          v5 = LocalAlloc(0, 0x48u);
          v3 = v5;
          if ( !v5 || (memset_0(v5, 0, 0x48u), v6 = LocalAlloc(0, 2LL * (cchValueName + 1)), (v3[2] = v6) == 0) )
          {
            v19 = 14;
            goto LABEL_29;
          }
          Library = LoadLibraryExW(Data, 0, 0);
          v3[3] = Library;
          if ( !Library )
            goto LABEL_23;
          ProcAddress = GetProcAddress(Library, "ShareProviderInitialize");
          v9 = (HMODULE)v3[3];
          v3[4] = ProcAddress;
          v10 = GetProcAddress(v9, "ShareProviderUninitialize");
          v11 = (HMODULE)v3[3];
          v3[5] = v10;
          v12 = GetProcAddress(v11, "ShareProviderShareAdd");
          v13 = (HMODULE)v3[3];
          v3[6] = v12;
          v14 = GetProcAddress(v13, "ShareProviderShareSetInfo");
          v15 = (HMODULE)v3[3];
          v3[7] = v14;
          v16 = GetProcAddress(v15, "ShareProviderShareDel");
          v17 = v3[4] == 0;
          v3[8] = v16;
          if ( v17 || !v3[5] || !v3[6] || !v3[7] || !v16 )
          {
LABEL_23:
            LastError = GetLastError();
            break;
          }
          LastError = ((__int64 (*)(void))v3[4])();
          if ( LastError )
            break;
          v18 = (_QWORD *)qword_18005CE40;
          if ( *(HLOCAL **)qword_18005CE40 != &qword_18005CE38 )
            __fastfail(3u);
          *v3 = &qword_18005CE38;
          v3[1] = v18;
          *v18 = v3;
          qword_18005CE40 = (__int64)v3;
        }
      }
      ++v1;
      cbData = 524;
      cchValueName = 262;
    }
  }
  v19 = 0;
  if ( LastError != 259 )
    v19 = LastError;
  if ( v19 )
  {
LABEL_29:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_8813eb76767d3cf2a080da74da1f2781_Traceguids, v19);
    }
    if ( v3 )
    {
      v20 = (HMODULE)v3[3];
      if ( v20 )
        FreeLibrary(v20);
      v21 = (void *)v3[2];
      if ( v21 )
        LocalFree(v21);
      LocalFree(v3);
    }
  }
  if ( v2 )
    RtlReleaseResource(&stru_18005CE48);
  if ( hKey )
    RegCloseKey(hKey);
  return v19;
}

```

## disassembly

```asm
0x1800131dc  push    rbp
0x1800131de  push    rbx
0x1800131df  push    rsi
0x1800131e0  push    rdi
0x1800131e1  push    r14
0x1800131e3  lea     rbp, [rsp-390h]
0x1800131eb  sub     rsp, 490h
0x1800131f2  mov     rax, cs:__security_cookie
0x1800131f9  xor     rax, rsp
0x1800131fc  mov     [rbp+3B0h+var_30], rax
0x180013203  lea     rax, [rsp+4B0h+hKey]
0x180013208  mov     [rsp+4B0h+hKey], 0
0x180013211  mov     r9d, 20019h; samDesired
0x180013217  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18001321c  xor     r8d, r8d; ulOptions
0x18001321f  mov     [rsp+4B0h+cchValueName], 106h
0x180013227  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\La"...
0x18001322e  mov     [rsp+4B0h+cbData], 20Ch
0x180013236  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001323d  mov     [rsp+4B0h+Type], 0
0x180013245  call    cs:__imp_RegOpenKeyExW
0x18001324b  mov     esi, eax
0x18001324d  test    eax, eax
0x18001324f  jnz     loc_180013451
0x180013255  mov     dl, 1; Wait
0x180013257  lea     rcx, stru_18005CE48; Resource
0x18001325e  call    cs:__imp_RtlAcquireResourceExclusive
0x180013264  xor     edi, edi
0x180013266  lea     r14d, [rsi+1]
0x18001326a  xor     ebx, ebx
0x18001326c  cmp     esi, 103h
0x180013272  jz      loc_180013456
0x180013278  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18001327d  lea     rax, [rsp+4B0h+cbData]
0x180013282  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x180013287  lea     r9, [rsp+4B0h+cchValueName]; lpcchValueName
0x18001328c  lea     rax, [rbp+3B0h+Data]
0x180013293  mov     edx, edi; dwIndex
0x180013295  mov     [rsp+4B0h+lpData], rax; lpData
0x18001329a  lea     r8, [rsp+4B0h+ValueName]; lpValueName
0x18001329f  lea     rax, [rsp+4B0h+Type]
0x1800132a4  mov     [rsp+4B0h+lpType], rax; lpType
0x1800132a9  mov     [rsp+4B0h+phkResult], rbx; lpReserved
0x1800132ae  call    cs:__imp_RegEnumValueW
0x1800132b4  mov     esi, eax
0x1800132b6  cmp     eax, 0EAh
0x1800132bb  jz      loc_180013422
0x1800132c1  test    eax, eax
0x1800132c3  jnz     loc_180013456
0x1800132c9  cmp     [rsp+4B0h+Type], r14d
0x1800132ce  jnz     loc_180013422
0x1800132d4  cmp     [rsp+4B0h+cbData], 20Ch
0x1800132dc  ja      loc_180013422
0x1800132e2  cmp     [rsp+4B0h+cchValueName], 106h
0x1800132ea  ja      loc_180013422
0x1800132f0  lea     rcx, [rsp+4B0h+ValueName]
0x1800132f5  call    SsFindShareProvider
0x1800132fa  test    rax, rax
0x1800132fd  jnz     loc_180013422
0x180013303  lea     esi, [rbx+48h]
0x180013306  xor     ecx, ecx; uFlags
0x180013308  mov     edx, esi; uBytes
0x18001330a  call    cs:__imp_LocalAlloc
0x180013310  mov     rbx, rax
0x180013313  test    rax, rax
0x180013316  jz      loc_18001344A
0x18001331c  mov     r8d, esi; Size
0x18001331f  xor     edx, edx; Val
0x180013321  mov     rcx, rax; void *
0x180013324  call    memset_0
0x180013329  mov     edx, [rsp+4B0h+cchValueName]
0x18001332d  xor     ecx, ecx; uFlags
0x18001332f  inc     edx
0x180013331  add     rdx, rdx; uBytes
0x180013334  call    cs:__imp_LocalAlloc
0x18001333a  mov     [rbx+10h], rax
0x18001333e  test    rax, rax
0x180013341  jz      loc_18001344A
0x180013347  xor     r8d, r8d; dwFlags
0x18001334a  lea     rcx, [rbp+3B0h+Data]; lpLibFileName
0x180013351  xor     edx, edx; hFile
0x180013353  call    cs:__imp_LoadLibraryExW
0x180013359  mov     [rbx+18h], rax
0x18001335d  test    rax, rax
0x180013360  jz      loc_180013440
0x180013366  lea     rdx, aShareprovideri; "ShareProviderInitialize"
0x18001336d  mov     rcx, rax; hModule
0x180013370  call    cs:__imp_GetProcAddress
0x180013376  mov     rcx, [rbx+18h]; hModule
0x18001337a  lea     rdx, aShareprovideru; "ShareProviderUninitialize"
0x180013381  mov     [rbx+20h], rax
0x180013385  call    cs:__imp_GetProcAddress
0x18001338b  mov     rcx, [rbx+18h]; hModule
0x18001338f  lea     rdx, aShareproviders_1; "ShareProviderShareAdd"
0x180013396  mov     [rbx+28h], rax
0x18001339a  call    cs:__imp_GetProcAddress
0x1800133a0  mov     rcx, [rbx+18h]; hModule
0x1800133a4  lea     rdx, aShareproviders_0; "ShareProviderShareSetInfo"
0x1800133ab  mov     [rbx+30h], rax
0x1800133af  call    cs:__imp_GetProcAddress
0x1800133b5  mov     rcx, [rbx+18h]; hModule
0x1800133b9  lea     rdx, aShareproviders; "ShareProviderShareDel"
0x1800133c0  mov     [rbx+38h], rax
0x1800133c4  call    cs:__imp_GetProcAddress
0x1800133ca  cmp     qword ptr [rbx+20h], 0
0x1800133cf  mov     [rbx+40h], rax
0x1800133d3  jz      short loc_180013440
0x1800133d5  cmp     qword ptr [rbx+28h], 0
0x1800133da  jz      short loc_180013440
0x1800133dc  cmp     qword ptr [rbx+30h], 0
0x1800133e1  jz      short loc_180013440
0x1800133e3  cmp     qword ptr [rbx+38h], 0
0x1800133e8  jz      short loc_180013440
0x1800133ea  test    rax, rax
0x1800133ed  jz      short loc_180013440
0x1800133ef  mov     rax, [rbx+20h]
0x1800133f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133f8  mov     esi, eax
0x1800133fa  test    eax, eax
0x1800133fc  jnz     short loc_180013456
0x1800133fe  mov     rax, cs:qword_18005CE40
0x180013405  lea     rcx, qword_18005CE38
0x18001340c  cmp     [rax], rcx
0x18001340f  jnz     short loc_180013439
0x180013411  mov     [rbx], rcx
0x180013414  mov     [rbx+8], rax
0x180013418  mov     [rax], rbx
0x18001341b  mov     cs:qword_18005CE40, rbx
0x180013422  inc     edi
0x180013424  mov     [rsp+4B0h+cbData], 20Ch
0x18001342c  mov     [rsp+4B0h+cchValueName], 106h
0x180013434  jmp     loc_18001326A
0x180013439  mov     ecx, 3
0x18001343e  int     29h; Win8: RtlFailFast(ecx)
0x180013440  call    cs:__imp_GetLastError
0x180013446  mov     esi, eax
0x180013448  jmp     short loc_180013456
0x18001344a  mov     edi, 0Eh
0x18001344f  jmp     short loc_180013465
0x180013451  xor     ebx, ebx
0x180013453  xor     r14d, r14d
0x180013456  xor     edi, edi
0x180013458  cmp     esi, 103h
0x18001345e  cmovnz  edi, esi
0x180013461  test    edi, edi
0x180013463  jz      short loc_1800134C8
0x180013465  mov     rcx, cs:WPP_GLOBAL_Control
0x18001346c  lea     rax, WPP_GLOBAL_Control
0x180013473  cmp     rcx, rax
0x180013476  jz      short loc_18001349C
0x180013478  test    byte ptr [rcx+1Ch], 1
0x18001347c  jz      short loc_18001349C
0x18001347e  cmp     byte ptr [rcx+19h], 1
0x180013482  jb      short loc_18001349C
0x180013484  mov     rcx, [rcx+10h]
0x180013488  lea     r8, WPP_8813eb76767d3cf2a080da74da1f2781_Traceguids
0x18001348f  mov     edx, 0Ah
0x180013494  mov     r9d, edi
0x180013497  call    WPP_SF_d
0x18001349c  test    rbx, rbx
0x18001349f  jz      short loc_1800134C8
0x1800134a1  mov     rcx, [rbx+18h]; hLibModule
0x1800134a5  test    rcx, rcx
0x1800134a8  jz      short loc_1800134B0
0x1800134aa  call    cs:__imp_FreeLibrary
0x1800134b0  mov     rcx, [rbx+10h]; hMem
0x1800134b4  test    rcx, rcx
0x1800134b7  jz      short loc_1800134BF
0x1800134b9  call    cs:__imp_LocalFree
0x1800134bf  mov     rcx, rbx; hMem
0x1800134c2  call    cs:__imp_LocalFree
0x1800134c8  test    r14d, r14d
0x1800134cb  jz      short loc_1800134DA
0x1800134cd  lea     rcx, stru_18005CE48; Resource
0x1800134d4  call    cs:__imp_RtlReleaseResource
0x1800134da  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800134df  test    rcx, rcx
0x1800134e2  jz      short loc_1800134EA
0x1800134e4  call    cs:__imp_RegCloseKey
0x1800134ea  mov     eax, edi
0x1800134ec  mov     rcx, [rbp+3B0h+var_30]
0x1800134f3  xor     rcx, rsp; StackCookie
0x1800134f6  call    __security_check_cookie
0x1800134fb  add     rsp, 490h
0x180013502  pop     r14
0x180013504  pop     rdi
0x180013505  pop     rsi
0x180013506  pop     rbx
0x180013507  pop     rbp
0x180013508  retn
```
