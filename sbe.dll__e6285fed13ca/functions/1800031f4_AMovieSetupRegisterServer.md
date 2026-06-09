# AMovieSetupRegisterServer

- ea: `0x1800031f4`
- end: `0x1800034cc`
- name: `AMovieSetupRegisterServer`
- size: `728`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800036a0`

## callees

- `0x180001c00`
- `0x180002e68`
- `0x180002ed4`
- `0x1800031f4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000331d`
- `ADVAPI32!RegCloseKey` at `0x180003407`
- `ADVAPI32!RegCloseKey` at `0x180003489`
- `ADVAPI32!RegCloseKey` at `0x180003494`
- `ADVAPI32!RegCloseKey` at `0x18000331d`
- `ADVAPI32!RegCloseKey` at `0x180003407`
- `ADVAPI32!RegCloseKey` at `0x180003489`
- `ADVAPI32!RegCloseKey` at `0x180003494`
- `ADVAPI32!RegCreateKeyExW` at `0x180003298`
- `ADVAPI32!RegCreateKeyExW` at `0x18000338c`
- `ADVAPI32!RegCreateKeyExW` at `0x180003298`
- `ADVAPI32!RegCreateKeyExW` at `0x18000338c`
- `ADVAPI32!RegSetValueExW` at `0x18000330c`
- `ADVAPI32!RegSetValueExW` at `0x1800033f6`
- `ADVAPI32!RegSetValueExW` at `0x18000347c`
- `ADVAPI32!RegSetValueExW` at `0x18000330c`
- `ADVAPI32!RegSetValueExW` at `0x1800033f6`
- `ADVAPI32!RegSetValueExW` at `0x18000347c`
- `ole32!StringFromGUID2` at `0x18000322e`
- `ole32!StringFromGUID2` at `0x18000322e`

## string_xrefs

- `0x18000324b`: `CLSID\%ls`
- `0x180003453`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall AMovieSetupRegisterServer(const GUID *a1, __int64 a2, __int64 a3)
{
  LSTATUS v5; // eax
  __int64 result; // rax
  LSTATUS v7; // ebx
  HKEY v8; // rcx
  LSTATUS v9; // ebx
  unsigned __int64 v10; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF

  StringFromGUID2(a1, sz, 39);
  hKey = 0;
  StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%ls", sz);
  v5 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0);
  if ( v5 )
    return v5 | 0x80070000;
  StringCchPrintfW(SubKey, 0x104u, L"%ls", a2);
  v10 = 0;
  result = StringCchLengthW(SubKey, 0x104u, &v10);
  if ( (int)result >= 0 )
  {
    v7 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)SubKey, 2 * v10 + 2);
    if ( v7
      || (phkResult = 0,
          StringCchPrintfW(SubKey, 0x104u, L"%ls", L"InprocServer32"),
          (v7 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2000000u, 0, &phkResult, 0)) != 0) )
    {
      v8 = hKey;
    }
    else
    {
      StringCchPrintfW(SubKey, 0x104u, L"%ls", a3);
      v10 = 0;
      result = StringCchLengthW(SubKey, 0x104u, &v10);
      if ( (int)result < 0 )
        return result;
      v7 = RegSetValueExW(phkResult, 0, 0, v7 + 1, (const BYTE *)SubKey, 2 * v10 + 2);
      if ( !v7 )
      {
        StringCchPrintfW(SubKey, 0x104u, L"%ls", L"Both");
        v10 = 0;
        result = StringCchLengthW(SubKey, 0x104u, &v10);
        if ( (int)result < 0 )
          return result;
        v9 = RegSetValueExW(phkResult, L"ThreadingModel", 0, 1u, (const BYTE *)SubKey, 2 * v10 + 2);
        RegCloseKey(hKey);
        RegCloseKey(phkResult);
        if ( v9 > 0 )
          return (unsigned __int16)v9 | 0x80070000;
        return (unsigned int)v9;
      }
      RegCloseKey(hKey);
      v8 = phkResult;
    }
    RegCloseKey(v8);
    return v7 | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800031f4  mov     [rsp-8+arg_18], rbx
0x1800031f9  push    rbp
0x1800031fa  push    rdi
0x1800031fb  push    r14
0x1800031fd  lea     rbp, [rsp-1E0h]
0x180003205  sub     rsp, 2E0h
0x18000320c  mov     rax, cs:__security_cookie
0x180003213  xor     rax, rsp
0x180003216  mov     [rbp+1F0h+var_20], rax
0x18000321d  mov     rdi, r8
0x180003220  mov     rbx, rdx
0x180003223  mov     r8d, 27h ; '''; cchMax
0x180003229  lea     rdx, [rsp+2F0h+sz]; lpsz
0x18000322e  call    cs:__imp_StringFromGUID2
0x180003234  mov     r14d, 104h
0x18000323a  mov     [rsp+2F0h+hKey], 0
0x180003243  mov     edx, r14d; unsigned __int64
0x180003246  lea     r9, [rsp+2F0h+sz]
0x18000324b  lea     r8, aClsidLs; "CLSID\\%ls"
0x180003252  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x180003256  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000325b  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x180003264  lea     rax, [rsp+2F0h+hKey]
0x180003269  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18000326e  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180003272  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000327b  xor     r9d, r9d; lpClass
0x18000327e  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x180003286  xor     r8d, r8d; Reserved
0x180003289  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180003290  mov     [rsp+2F0h+dwOptions], 0; dwOptions
0x180003298  call    cs:__imp_RegCreateKeyExW
0x18000329e  test    eax, eax
0x1800032a0  jz      short loc_1800032AC
0x1800032a2  or      eax, 80070000h
0x1800032a7  jmp     loc_1800034A9
0x1800032ac  mov     r9, rbx
0x1800032af  lea     r8, aLs; "%ls"
0x1800032b6  mov     rdx, r14; unsigned __int64
0x1800032b9  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x1800032bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800032c2  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x1800032c7  mov     [rsp+2F0h+var_2A0], 0
0x1800032d0  mov     rdx, r14; unsigned __int64
0x1800032d3  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x1800032d7  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800032dc  test    eax, eax
0x1800032de  js      loc_1800034A9
0x1800032e4  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x1800032e8  mov     r9d, 1; dwType
0x1800032ee  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800032f3  xor     r8d, r8d; Reserved
0x1800032f6  xor     edx, edx; lpValueName
0x1800032f8  lea     eax, ds:2[rax*2]
0x1800032ff  mov     [rsp+2F0h+samDesired], eax; cbData
0x180003303  lea     rax, [rbp+1F0h+SubKey]
0x180003307  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x18000330c  call    cs:__imp_RegSetValueExW
0x180003312  mov     ebx, eax
0x180003314  test    eax, eax
0x180003316  jz      short loc_18000332E
0x180003318  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18000331d  call    cs:__imp_RegCloseKey
0x180003323  or      ebx, 80070000h
0x180003329  jmp     loc_1800034A7
0x18000332e  lea     r9, aInprocserver32; "InprocServer32"
0x180003335  mov     [rsp+2F0h+var_290], 0
0x18000333e  lea     r8, aLs; "%ls"
0x180003345  mov     rdx, r14; unsigned __int64
0x180003348  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x18000334c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003351  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180003356  lea     rax, [rsp+2F0h+var_290]
0x18000335b  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x180003364  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180003368  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18000336d  xor     r9d, r9d; lpClass
0x180003370  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180003379  xor     r8d, r8d; Reserved
0x18000337c  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x180003384  mov     [rsp+2F0h+dwOptions], 0; dwOptions
0x18000338c  call    cs:__imp_RegCreateKeyExW
0x180003392  mov     ebx, eax
0x180003394  test    eax, eax
0x180003396  jnz     short loc_180003318
0x180003398  mov     r9, rdi
0x18000339b  lea     r8, aLs; "%ls"
0x1800033a2  mov     rdx, r14; unsigned __int64
0x1800033a5  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x1800033a9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800033ae  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x1800033b3  mov     [rsp+2F0h+var_2A0], 0
0x1800033bc  mov     rdx, r14; unsigned __int64
0x1800033bf  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x1800033c3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800033c8  test    eax, eax
0x1800033ca  js      loc_1800034A9
0x1800033d0  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x1800033d4  lea     r9d, [rbx+1]; dwType
0x1800033d8  mov     rcx, [rsp+2F0h+var_290]; hKey
0x1800033dd  xor     r8d, r8d; Reserved
0x1800033e0  xor     edx, edx; lpValueName
0x1800033e2  lea     eax, ds:2[rax*2]
0x1800033e9  mov     [rsp+2F0h+samDesired], eax; cbData
0x1800033ed  lea     rax, [rbp+1F0h+SubKey]
0x1800033f1  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x1800033f6  call    cs:__imp_RegSetValueExW
0x1800033fc  mov     ebx, eax
0x1800033fe  test    eax, eax
0x180003400  jz      short loc_180003417
0x180003402  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180003407  call    cs:__imp_RegCloseKey
0x18000340d  mov     rcx, [rsp+2F0h+var_290]
0x180003412  jmp     loc_18000331D
0x180003417  lea     r9, aBoth; "Both"
0x18000341e  mov     rdx, r14; unsigned __int64
0x180003421  lea     r8, aLs; "%ls"
0x180003428  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x18000342c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003431  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x180003436  mov     [rsp+2F0h+var_2A0], 0
0x18000343f  mov     rdx, r14; unsigned __int64
0x180003442  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180003446  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000344b  test    eax, eax
0x18000344d  js      short loc_1800034A9
0x18000344f  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x180003453  lea     rdx, ValueName; "ThreadingModel"
0x18000345a  mov     rcx, [rsp+2F0h+var_290]; hKey
0x18000345f  mov     r9d, 1; dwType
0x180003465  xor     r8d, r8d; Reserved
0x180003468  lea     eax, ds:2[rax*2]
0x18000346f  mov     [rsp+2F0h+samDesired], eax; cbData
0x180003473  lea     rax, [rbp+1F0h+SubKey]
0x180003477  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x18000347c  call    cs:__imp_RegSetValueExW
0x180003482  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180003487  mov     ebx, eax
0x180003489  call    cs:__imp_RegCloseKey
0x18000348f  mov     rcx, [rsp+2F0h+var_290]; hKey
0x180003494  call    cs:__imp_RegCloseKey
0x18000349a  test    ebx, ebx
0x18000349c  jle     short loc_1800034A7
0x18000349e  movzx   ebx, bx
0x1800034a1  or      ebx, 80070000h
0x1800034a7  mov     eax, ebx
0x1800034a9  mov     rcx, [rbp+1F0h+var_20]
0x1800034b0  xor     rcx, rsp; StackCookie
0x1800034b3  call    __security_check_cookie
0x1800034b8  mov     rbx, [rsp+2F0h+arg_18]
0x1800034c0  add     rsp, 2E0h
0x1800034c7  pop     r14
0x1800034c9  pop     rdi
0x1800034ca  pop     rbp
0x1800034cb  retn
```
