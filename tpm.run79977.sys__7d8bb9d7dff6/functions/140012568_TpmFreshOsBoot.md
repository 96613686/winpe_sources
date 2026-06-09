# TpmFreshOsBoot

- ea: `0x140012568`
- end: `0x1400128a2`
- name: `TpmFreshOsBoot`
- size: `826`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x14000660c`
- `0x1400110f0`

## callees

- `0x140009fc8`
- `0x14000b6c8`
- `0x14000b9a4`
- `0x140010eb8`
- `0x140012568`
- `0x14001a2e0`
- `0x14001d1cc`
- `0x14001d4e4`
- `0x14001d63c`
- `0x140039740`
- `0x140039b40`
- `0x140045430`
- `0x1400454a0`

## import_xrefs

- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400126ab`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140012713`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400126ab`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140012713`

## string_xrefs

- `0x14001269d`: `TpmDriverLogPath`
- `0x140012701`: `TpmDriverLogPath`
- `0x14001266a`: `WBCLPath`

## pseudocode

```c
__int64 TpmFreshOsBoot()
{
  NTSTATUS PersistedStateLocation; // ebx
  wchar_t *v1; // rdi
  int v2; // eax
  int Value; // eax
  __int64 v5; // [rsp+20h] [rbp-E0h]
  __int64 v6; // [rsp+20h] [rbp-E0h]
  int v7; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v8; // [rsp+44h] [rbp-BCh] BYREF
  int v9; // [rsp+48h] [rbp-B8h] BYREF
  size_t pcchLength[2]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Dst[280]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t Src[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int64 retaddr; // [rsp+6E8h] [rbp+5E8h]

  PersistedStateLocation = 0;
  memset(Src, 0, 0x208u);
  v7 = 0;
  memset(pszDest, 0, 520);
  pcchLength[0] = 0;
  v8 = 0;
  v1 = 0;
  memset(Dst, 0, sizeof(Dst));
  if ( (unsigned int)TpmRegistry::ValueExists() )
    goto LABEL_21;
  if ( (int)TpmRegistry::QueryValue(0, L"OsBootCount", 4, &v7, 4, 0) < 0 )
    v2 = 1;
  else
    v2 = v7 + 1;
  v7 = v2;
  v9 = v2;
  PersistedStateLocation = TpmRegistry::AssignValue(0, L"OsBootCount", 4, &v9, 4);
  if ( PersistedStateLocation < 0 )
    goto LABEL_22;
  Value = TpmRegistry::QueryValue(0, L"WBCLPath", 1, Src, 520, 0);
  PersistedStateLocation = Value;
  if ( Value != -1073741772 )
  {
    if ( Value >= 0 )
    {
      TpmConvertFilePathToObjectPath(Dst, Src);
      v1 = Dst;
LABEL_14:
      v9 = 0;
      TpmRegistry::AssignValue(1, L"OsResumeCount", 4, &v9, 4);
      LODWORD(v5) = v7;
      PersistedStateLocation = RtlStringCchPrintfW(pszDest, 0x104u, L"%s\\%010u-%010u.log", v1, v5, 0);
      if ( PersistedStateLocation >= 0 )
      {
        PersistedStateLocation = RtlStringCchLengthW(pszDest, 0x104u, pcchLength);
        if ( PersistedStateLocation >= 0 )
        {
          TpmRegistry::AssignValue(1, L"PlatformLogFile", 1, pszDest, 2 * LODWORD(pcchLength[0]) + 2);
          LODWORD(v6) = v7;
          PersistedStateLocation = RtlStringCchPrintfW(pszDest, 0x104u, L"%s\\%010u-%010u-DRTM.log", v1, v6, 0);
          if ( PersistedStateLocation >= 0 )
          {
            PersistedStateLocation = RtlStringCchLengthW(pszDest, 0x104u, pcchLength);
            if ( PersistedStateLocation >= 0 )
            {
              PersistedStateLocation = TpmRegistry::AssignValue(
                                         1,
                                         L"PlatformLogFileDrtm",
                                         1,
                                         pszDest,
                                         2 * LODWORD(pcchLength[0]) + 2);
              if ( PersistedStateLocation >= 0 )
              {
                if ( (unsigned int)Feature_TpmMissingLogsMaa__private_IsEnabledDeviceUsageNoInline() )
                  PersistedStateLocation = TpmAddWbclColdBootRegistryValue();
              }
            }
          }
        }
      }
      goto LABEL_21;
    }
LABEL_22:
    TpmFree(v1);
    return (unsigned int)PersistedStateLocation;
  }
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"TpmDriverLogPath",
                             0,
                             L"\\SystemRoot\\Logs\\MeasuredBoot",
                             1,
                             0,
                             0,
                             &v8);
  if ( PersistedStateLocation != -2147483643 )
    goto LABEL_22;
  v1 = (wchar_t *)TpmAlloc(1, v8, retaddr);
  if ( !v1 )
  {
    PersistedStateLocation = -1073741670;
    goto LABEL_21;
  }
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"TpmDriverLogPath",
                             0,
                             L"\\SystemRoot\\Logs\\MeasuredBoot",
                             1,
                             v1,
                             v8,
                             &v8);
  if ( PersistedStateLocation >= 0 )
    goto LABEL_14;
LABEL_21:
  if ( v1 != Dst )
    goto LABEL_22;
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x140012568  push    rbp
0x14001256a  push    rbx
0x14001256b  push    rdi
0x14001256c  push    r14
0x14001256e  push    r15
0x140012570  lea     rbp, [rsp-5C0h]
0x140012578  sub     rsp, 6C0h
0x14001257f  mov     rax, cs:__security_cookie
0x140012586  xor     rax, rsp
0x140012589  mov     [rbp+5E0h+var_30], rax
0x140012590  xor     edx, edx; Val
0x140012592  lea     rcx, [rbp+5E0h+Src]; void *
0x140012599  mov     r8d, 208h; Size
0x14001259f  xor     ebx, ebx
0x1400125a1  call    memset
0x1400125a6  xor     eax, eax
0x1400125a8  mov     [rsp+6E0h+var_6A0], ebx
0x1400125ac  xor     edx, edx; Val
0x1400125ae  mov     [rsp+6E0h+pszDest], ax
0x1400125b3  mov     r8d, 206h; Size
0x1400125b9  lea     rcx, [rsp+6E0h+var_67E]; void *
0x1400125be  call    memset
0x1400125c3  xor     edx, edx; Val
0x1400125c5  mov     [rsp+6E0h+pcchLength], rbx
0x1400125ca  mov     r8d, 230h; Size
0x1400125d0  mov     dword ptr [rsp+6E0h+var_69C], ebx
0x1400125d4  lea     rcx, [rbp+5E0h+Dst]; void *
0x1400125db  xor     edi, edi
0x1400125dd  call    memset
0x1400125e2  call    ?ValueExists@TpmRegistry@@SAHW4KEY_VALUES@1@PEBG@Z; TpmRegistry::ValueExists(TpmRegistry::KEY_VALUES,ushort const *)
0x1400125e7  test    eax, eax
0x1400125e9  jnz     loc_14001286D
0x1400125ef  lea     r15d, [rbx+4]
0x1400125f3  mov     [rsp+6E0h+var_6B8], rbx
0x1400125f8  mov     r8d, r15d
0x1400125fb  mov     dword ptr [rsp+6E0h+var_6C0], r15d
0x140012600  lea     r9, [rsp+6E0h+var_6A0]
0x140012605  xor     ecx, ecx
0x140012607  lea     rdx, aOsbootcount; "OsBootCount"
0x14001260e  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x140012613  lea     r14d, [rbx+1]
0x140012617  test    eax, eax
0x140012619  js      short loc_140012623
0x14001261b  mov     eax, [rsp+6E0h+var_6A0]
0x14001261f  inc     eax
0x140012621  jmp     short loc_140012626
0x140012623  mov     eax, r14d
0x140012626  lea     r9, [rsp+6E0h+var_69C+4]
0x14001262b  mov     [rsp+6E0h+var_6A0], eax
0x14001262f  mov     r8d, r15d
0x140012632  mov     dword ptr [rsp+6E0h+var_69C+4], eax
0x140012636  lea     rdx, aOsbootcount; "OsBootCount"
0x14001263d  mov     dword ptr [rsp+6E0h+var_6C0], r15d
0x140012642  xor     ecx, ecx
0x140012644  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x140012649  mov     ebx, eax
0x14001264b  test    eax, eax
0x14001264d  js      loc_140012879
0x140012653  mov     [rsp+6E0h+var_6B8], rdi
0x140012658  lea     r9, [rbp+5E0h+Src]
0x14001265f  mov     r8d, r14d
0x140012662  mov     dword ptr [rsp+6E0h+var_6C0], 208h
0x14001266a  lea     rdx, aWbclpath; "WBCLPath"
0x140012671  xor     ecx, ecx
0x140012673  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x140012678  mov     ebx, eax
0x14001267a  cmp     eax, 0C0000034h
0x14001267f  jnz     loc_14001272B
0x140012685  lea     rax, [rsp+6E0h+var_69C]
0x14001268a  mov     r9d, r14d
0x14001268d  mov     [rsp+6E0h+var_6B0], rax
0x140012692  lea     r8, aSystemrootLogs; "\\SystemRoot\\Logs\\MeasuredBoot"
0x140012699  mov     dword ptr [rsp+6E0h+var_6B8], edi
0x14001269d  lea     rcx, aTpmdriverlogpa; "TpmDriverLogPath"
0x1400126a4  xor     edx, edx
0x1400126a6  mov     [rsp+6E0h+var_6C0], rdi
0x1400126ab  call    cs:__imp_RtlGetPersistedStateLocation
0x1400126b2  nop     dword ptr [rax+rax+00h]
0x1400126b7  mov     ebx, eax
0x1400126b9  cmp     eax, 80000005h
0x1400126be  jnz     loc_140012879
0x1400126c4  mov     r8, [rbp+5E8h]; unsigned __int64
0x1400126cb  mov     cl, r14b; bool
0x1400126ce  mov     edx, dword ptr [rsp+6E0h+var_69C]; unsigned __int64
0x1400126d2  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x1400126d7  mov     rdi, rax
0x1400126da  test    rax, rax
0x1400126dd  jnz     short loc_1400126E9
0x1400126df  mov     ebx, 0C000009Ah
0x1400126e4  jmp     loc_14001286D
0x1400126e9  lea     rax, [rsp+6E0h+var_69C]
0x1400126ee  mov     r9d, r14d
0x1400126f1  mov     [rsp+6E0h+var_6B0], rax
0x1400126f6  lea     r8, aSystemrootLogs; "\\SystemRoot\\Logs\\MeasuredBoot"
0x1400126fd  mov     eax, dword ptr [rsp+6E0h+var_69C]
0x140012701  lea     rcx, aTpmdriverlogpa; "TpmDriverLogPath"
0x140012708  mov     dword ptr [rsp+6E0h+var_6B8], eax
0x14001270c  xor     edx, edx
0x14001270e  mov     [rsp+6E0h+var_6C0], rdi
0x140012713  call    cs:__imp_RtlGetPersistedStateLocation
0x14001271a  nop     dword ptr [rax+rax+00h]
0x14001271f  mov     ebx, eax
0x140012721  test    eax, eax
0x140012723  js      loc_14001286D
0x140012729  jmp     short loc_14001274D
0x14001272b  test    eax, eax
0x14001272d  js      loc_140012879
0x140012733  lea     rdx, [rbp+5E0h+Src]; Src
0x14001273a  lea     rcx, [rbp+5E0h+Dst]; Dst
0x140012741  call    TpmConvertFilePathToObjectPath
0x140012746  lea     rdi, [rbp+5E0h+Dst]
0x14001274d  lea     r9, [rsp+6E0h+var_69C+4]
0x140012752  mov     dword ptr [rsp+6E0h+var_69C+4], 0
0x14001275a  mov     r8d, r15d
0x14001275d  mov     dword ptr [rsp+6E0h+var_6C0], r15d
0x140012762  lea     rdx, aOsresumecount; "OsResumeCount"
0x140012769  mov     ecx, r14d
0x14001276c  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x140012771  mov     eax, [rsp+6E0h+var_6A0]
0x140012775  lea     r8, aS010u010uLog; "%s\\%010u-%010u.log"
0x14001277c  mov     r15d, 104h
0x140012782  mov     [rsp+6E0h+var_6B8], 0
0x14001278b  mov     edx, r15d; cchDest
0x14001278e  mov     dword ptr [rsp+6E0h+var_6C0], eax
0x140012792  mov     r9, rdi
0x140012795  lea     rcx, [rsp+6E0h+pszDest]; pszDest
0x14001279a  call    RtlStringCchPrintfW
0x14001279f  mov     ebx, eax
0x1400127a1  test    eax, eax
0x1400127a3  js      loc_14001286D
0x1400127a9  lea     r8, [rsp+6E0h+pcchLength]; pcchLength
0x1400127ae  mov     edx, r15d; cchMax
0x1400127b1  lea     rcx, [rsp+6E0h+pszDest]; psz
0x1400127b6  call    RtlStringCchLengthW
0x1400127bb  mov     ebx, eax
0x1400127bd  test    eax, eax
0x1400127bf  js      loc_14001286D
0x1400127c5  mov     eax, dword ptr [rsp+6E0h+pcchLength]
0x1400127c9  lea     r9, [rsp+6E0h+pszDest]
0x1400127ce  mov     r8d, r14d
0x1400127d1  lea     rdx, aPlatformlogfil; "PlatformLogFile"
0x1400127d8  mov     ecx, r14d
0x1400127db  lea     eax, ds:2[rax*2]
0x1400127e2  mov     dword ptr [rsp+6E0h+var_6C0], eax
0x1400127e6  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x1400127eb  mov     eax, [rsp+6E0h+var_6A0]
0x1400127ef  lea     r8, aS010u010uDrtmL; "%s\\%010u-%010u-DRTM.log"
0x1400127f6  mov     r9, rdi
0x1400127f9  mov     [rsp+6E0h+var_6B8], 0
0x140012802  mov     edx, r15d; cchDest
0x140012805  mov     dword ptr [rsp+6E0h+var_6C0], eax
0x140012809  lea     rcx, [rsp+6E0h+pszDest]; pszDest
0x14001280e  call    RtlStringCchPrintfW
0x140012813  mov     ebx, eax
0x140012815  test    eax, eax
0x140012817  js      short loc_14001286D
0x140012819  lea     r8, [rsp+6E0h+pcchLength]; pcchLength
0x14001281e  mov     edx, r15d; cchMax
0x140012821  lea     rcx, [rsp+6E0h+pszDest]; psz
0x140012826  call    RtlStringCchLengthW
0x14001282b  mov     ebx, eax
0x14001282d  test    eax, eax
0x14001282f  js      short loc_14001286D
0x140012831  mov     eax, dword ptr [rsp+6E0h+pcchLength]
0x140012835  lea     r9, [rsp+6E0h+pszDest]
0x14001283a  mov     r8d, r14d
0x14001283d  lea     rdx, aPlatformlogfil_0; "PlatformLogFileDrtm"
0x140012844  mov     ecx, r14d
0x140012847  lea     eax, ds:2[rax*2]
0x14001284e  mov     dword ptr [rsp+6E0h+var_6C0], eax
0x140012852  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x140012857  mov     ebx, eax
0x140012859  test    eax, eax
0x14001285b  js      short loc_14001286D
0x14001285d  call    Feature_TpmMissingLogsMaa__private_IsEnabledDeviceUsageNoInline
0x140012862  test    eax, eax
0x140012864  jz      short loc_14001286D
0x140012866  call    TpmAddWbclColdBootRegistryValue
0x14001286b  mov     ebx, eax
0x14001286d  lea     rax, [rbp+5E0h+Dst]
0x140012874  cmp     rdi, rax
0x140012877  jz      short loc_140012881
0x140012879  mov     rcx, rdi; void *
0x14001287c  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140012881  mov     eax, ebx
0x140012883  mov     rcx, [rbp+5E0h+var_30]
0x14001288a  xor     rcx, rsp; StackCookie
0x14001288d  call    __security_check_cookie
0x140012892  add     rsp, 6C0h
0x140012899  pop     r15
0x14001289b  pop     r14
0x14001289d  pop     rdi
0x14001289e  pop     rbx
0x14001289f  pop     rbp
0x1400128a0  retn
```
