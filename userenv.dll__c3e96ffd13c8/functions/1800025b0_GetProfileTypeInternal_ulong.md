# GetProfileTypeInternal(ulong *)

- ea: `0x1800025b0`
- end: `0x180002ac0`
- name: `?GetProfileTypeInternal@@YAJPEAK@Z`
- size: `1296`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a1b0`

## callees

- `0x180002418`
- `0x1800025b0`
- `0x180002ad0`
- `0x180003410`
- `0x180003f60`
- `0x18000c97c`
- `0x18000ce7c`
- `0x18000cea0`
- `0x18000cfc4`
- `0x18001437c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800027c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800027dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800027c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800027dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000265b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800026d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000265b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800026d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002674`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002821`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002928`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800029b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800029f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002674`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002821`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002928`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800029b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800029f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002713`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000276d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002713`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000276d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800025f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800025f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800025de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800025de`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002864`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002864`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002852`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002ab5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002ab5`

## string_xrefs

- `0x180002876`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x1800028a6`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x1800028e0`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x180002934`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x180002988`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x1800029d8`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x180002a8e`: `DeleteRoamingCache`

## pseudocode

```c
__int64 __fastcall GetProfileTypeInternal(unsigned int *a1)
{
  HANDLE CurrentThread; // rax
  int ProfileSidString; // eax
  unsigned int v4; // edi
  WCHAR *v5; // rsi
  LSTATUS v6; // eax
  int *v7; // r8
  unsigned int v8; // edi
  int ProfileListKeyNameFromSid; // eax
  unsigned int v10; // edi
  WCHAR *v11; // r14
  unsigned int v12; // eax
  LSTATUS ValueW; // eax
  unsigned int v14; // edi
  HKEY v15; // rcx
  int v16; // r8d
  int v17; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax
  signed int LastError; // eax
  unsigned int v22; // edi
  HANDLE CurrentProcess; // rax
  const char *v24; // r9
  unsigned int v25; // ebx
  unsigned int v26; // ebx
  bool v27; // zf
  int phkResult; // [rsp+28h] [rbp-39h]
  int phkResulta; // [rsp+28h] [rbp-39h]
  unsigned int phkResultb; // [rsp+28h] [rbp-39h]
  int phkResultc; // [rsp+28h] [rbp-39h]
  HKEY hkey; // [rsp+48h] [rbp-19h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+50h] [rbp-11h] BYREF
  LPCWSTR v34[4]; // [rsp+68h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]
  int pvData; // [rsp+C8h] [rbp+67h] BYREF
  int v37; // [rsp+D0h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+D8h] [rbp+77h] BYREF
  void *TokenHandle; // [rsp+E0h] [rbp+7Fh] BYREF

  if ( !a1 )
    return 2147942487LL;
  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_3;
  LastError = GetLastError();
  v22 = LastError;
  if ( LastError == 1008 )
  {
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(TokenHandle);
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
LABEL_3:
      lpSubKey[0] = 0;
      lpSubKey[1] = (LPCWSTR)-1LL;
      lpSubKey[2] = (LPCWSTR)-1LL;
      ProfileSidString = GetProfileSidString(TokenHandle, (unsigned __int16 **)lpSubKey);
      v4 = ProfileSidString;
      if ( ProfileSidString < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D5,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\util.cpp",
          (const char *)(unsigned int)ProfileSidString,
          phkResult);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(TokenHandle);
        return v4;
      }
      else
      {
        v5 = (WCHAR *)lpSubKey[0];
        hKey = 0;
        v6 = RegOpenKeyExW(HKEY_USERS, lpSubKey[0], 0, 0x20019u, &hKey);
        v8 = v6;
        if ( v6 )
        {
          if ( v6 > 0 )
            v8 = (unsigned __int16)v6 | 0x80070000;
          if ( hKey )
            RegCloseKey(hKey);
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          return v8;
        }
        else
        {
          if ( hKey )
            RegCloseKey(hKey);
          v34[0] = 0;
          v34[1] = (LPCWSTR)-1LL;
          v34[2] = (LPCWSTR)-1LL;
          ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(v5, (unsigned __int16 **)v34, v7);
          v10 = ProfileListKeyNameFromSid;
          if ( ProfileListKeyNameFromSid < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1DF,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\util.cpp",
              (const char *)(unsigned int)ProfileListKeyNameFromSid,
              phkResulta);
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v34);
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
            if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(TokenHandle);
            return v10;
          }
          else
          {
            v11 = (WCHAR *)v34[0];
            hkey = 0;
            v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v34[0], 0, 0x20019u, &hkey);
            if ( v12 )
            {
              v26 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x1E2,
                      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\util.cpp",
                      (const char *)v12,
                      phkResultb);
              if ( hkey )
                RegCloseKey(hkey);
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v34);
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
              return v26;
            }
            else
            {
              pvData = 0;
              LODWORD(hKey) = 4;
              ValueW = RegGetValueW(hkey, 0, L"State", 0x10u, 0, &pvData, (LPDWORD)&hKey);
              v14 = ValueW;
              if ( ValueW > 0 )
                v14 = (unsigned __int16)ValueW | 0x80070000;
              if ( (v14 & 0x80000000) != 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1E5,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\util.cpp",
                  (const char *)v14,
                  phkResultc);
                if ( hkey )
                  RegCloseKey(hkey);
                Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v34);
                Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
                if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                  CloseHandle(TokenHandle);
                return v14;
              }
              else
              {
                v37 = 99;
                LODWORD(hKey) = 4;
                RegGetValueW(hkey, L"Preference", L"UserPreference", 0x10u, 0, &v37, (LPDWORD)&hKey);
                v17 = pvData;
                if ( (pvData & 0x80u) != 0 )
                  *a1 |= 1u;
                if ( (v17 & 1) != 0 )
                  *a1 |= 4u;
                if ( (v17 & 0x10000) != 0 )
                  *a1 |= 4u;
                if ( v37 )
                {
                  if ( (v17 & 0x18) != 0 )
                  {
                    *a1 |= 2u;
                    v27 = CheckPolicy(v15, L"DeleteRoamingCache", v16) == 0;
                    LOWORD(v17) = pvData;
                    if ( !v27 )
                      *a1 |= 1u;
                  }
                }
                if ( (v17 & 0x800) != 0 )
                  *a1 |= 1u;
                if ( hkey )
                  RegCloseKey(hkey);
                if ( v11 )
                {
                  ProcessHeap = GetProcessHeap();
                  HeapFree(ProcessHeap, 0, v11);
                }
                if ( v5 )
                {
                  v19 = GetProcessHeap();
                  HeapFree(v19, 0, v5);
                }
                if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                  CloseHandle(TokenHandle);
                return 0;
              }
            }
          }
        }
      }
    }
    v25 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x1D0,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\util.cpp",
            v24);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v25;
  }
  else
  {
    if ( LastError > 0 )
      v22 = (unsigned __int16)LastError | 0x80070000;
    if ( (v22 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CF,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\util.cpp",
        (const char *)v22,
        phkResult);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v22;
  }
}

```

## disassembly

```asm
0x1800025b0  mov     rax, rsp
0x1800025b3  push    rbp
0x1800025b4  push    rbx
0x1800025b5  lea     rbp, [rax-5Fh]
0x1800025b9  sub     rsp, 0A8h
0x1800025c0  mov     rbx, rcx
0x1800025c3  test    rcx, rcx
0x1800025c6  jz      loc_180002A1F
0x1800025cc  mov     [rax-20h], rdi
0x1800025d0  mov     [rax-30h], r15
0x1800025d4  xor     r15d, r15d
0x1800025d7  mov     [rcx], r15d
0x1800025da  mov     [rbp+57h+TokenHandle], r15
0x1800025de  call    cs:__imp_GetCurrentThread
0x1800025e4  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800025e8  mov     edx, 8; DesiredAccess
0x1800025ed  mov     rcx, rax; ThreadHandle
0x1800025f0  mov     r8d, 1; OpenAsSelf
0x1800025f6  call    cs:__imp_OpenThreadToken
0x1800025fc  test    eax, eax
0x1800025fe  jz      loc_180002829
0x180002604  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180002608  lea     rdx, [rbp+57h+lpSubKey]; unsigned __int16 **
0x18000260c  mov     [rbp+57h+lpSubKey], r15
0x180002610  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFFh
0x180002618  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFFh
0x180002620  call    ?GetProfileSidString@@YAJPEAXPEAPEAG@Z; GetProfileSidString(void *,ushort * *)
0x180002625  mov     edi, eax
0x180002627  test    eax, eax
0x180002629  js      loc_1800028A2
0x18000262f  lea     rax, [rbp+57h+hKey]
0x180002633  mov     [rsp+0A0h], rsi
0x18000263b  mov     rsi, [rbp+57h+lpSubKey]
0x18000263f  mov     r9d, 20019h; samDesired
0x180002645  mov     rdx, rsi; lpSubKey
0x180002648  mov     [rbp+57h+hKey], r15
0x18000264c  xor     r8d, r8d; ulOptions
0x18000264f  mov     [rsp+0B0h+phkResult], rax; int
0x180002654  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000265b  call    cs:__imp_RegOpenKeyExW
0x180002661  mov     edi, eax
0x180002663  test    eax, eax
0x180002665  jnz     loc_180002A49
0x18000266b  mov     rcx, [rbp+57h+hKey]; hKey
0x18000266f  test    rcx, rcx
0x180002672  jz      short loc_18000267A
0x180002674  call    cs:__imp_RegCloseKey
0x18000267a  lea     rdx, [rbp+57h+var_50]; unsigned __int16 **
0x18000267e  mov     [rbp+57h+var_50], r15
0x180002682  mov     rcx, rsi; lpString1
0x180002685  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFFh
0x18000268d  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFFh
0x180002695  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18000269a  mov     edi, eax
0x18000269c  test    eax, eax
0x18000269e  js      loc_180002930
0x1800026a4  lea     rax, [rbp+57h+hkey]
0x1800026a8  mov     [rsp+0B0h+var_20], r14
0x1800026b0  mov     r14, [rbp+57h+var_50]
0x1800026b4  mov     r9d, 20019h; samDesired
0x1800026ba  mov     rdx, r14; lpSubKey
0x1800026bd  mov     [rbp+57h+hkey], r15
0x1800026c1  xor     r8d, r8d; ulOptions
0x1800026c4  mov     [rsp+0B0h+phkResult], rax; unsigned int
0x1800026c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800026d0  call    cs:__imp_RegOpenKeyExW
0x1800026d6  test    eax, eax
0x1800026d8  jnz     loc_1800029D4
0x1800026de  mov     rcx, [rbp+57h+hkey]; hkey
0x1800026e2  lea     rax, [rbp+57h+hKey]
0x1800026e6  mov     [rsp+30h], rax; pcbData
0x1800026eb  lea     r8, Value; "State"
0x1800026f2  lea     rax, [rbp+57h+arg_0]
0x1800026f6  mov     [rbp+57h+arg_0], r15d
0x1800026fa  mov     [rsp+0B0h+pvData], rax; pvData
0x1800026ff  mov     r9d, 10h; dwFlags
0x180002705  xor     edx, edx; lpSubKey
0x180002707  mov     [rsp+0B0h+phkResult], r15; int
0x18000270c  mov     dword ptr [rbp+57h+hKey], 4
0x180002713  call    cs:__imp_RegGetValueW
0x180002719  mov     edi, eax
0x18000271b  test    eax, eax
0x18000271d  jle     short loc_180002728
0x18000271f  movzx   edi, ax
0x180002722  or      edi, 80070000h
0x180002728  test    edi, edi
0x18000272a  js      loc_1800028DC
0x180002730  mov     rcx, [rbp+57h+hkey]; hkey
0x180002734  lea     rax, [rbp+57h+hKey]
0x180002738  mov     [rsp+30h], rax; pcbData
0x18000273d  lea     r8, aUserpreference; "UserPreference"
0x180002744  lea     rax, [rbp+57h+arg_8]
0x180002748  mov     [rbp+57h+arg_8], 63h ; 'c'
0x18000274f  mov     [rsp+0B0h+pvData], rax; pvData
0x180002754  lea     rdx, SubKey; "Preference"
0x18000275b  mov     r9d, 10h; dwFlags
0x180002761  mov     [rsp+0B0h+phkResult], r15; pdwType
0x180002766  mov     dword ptr [rbp+57h+hKey], 4
0x18000276d  call    cs:__imp_RegGetValueW
0x180002773  mov     eax, [rbp+57h+arg_0]
0x180002776  test    al, al
0x180002778  js      loc_180002A73
0x18000277e  test    al, 1
0x180002780  jnz     loc_180002A7B
0x180002786  bt      eax, 10h
0x18000278a  jb      loc_180002A83
0x180002790  cmp     [rbp+57h+arg_8], r15d
0x180002794  jz      short loc_18000279E
0x180002796  test    al, 18h
0x180002798  jnz     loc_180002A8B
0x18000279e  bt      eax, 0Bh
0x1800027a2  jb      loc_180002AAD
0x1800027a8  mov     rcx, [rbp+57h+hkey]; hKey
0x1800027ac  test    rcx, rcx
0x1800027af  jnz     short loc_180002821
0x1800027b1  test    r14, r14
0x1800027b4  jz      short loc_1800027CA
0x1800027b6  call    cs:__imp_GetProcessHeap
0x1800027bc  mov     r8, r14; lpMem
0x1800027bf  xor     edx, edx; dwFlags
0x1800027c1  mov     rcx, rax; hHeap
0x1800027c4  call    cs:__imp_HeapFree
0x1800027ca  test    rsi, rsi
0x1800027cd  jz      short loc_1800027E3
0x1800027cf  call    cs:__imp_GetProcessHeap
0x1800027d5  mov     r8, rsi; lpMem
0x1800027d8  xor     edx, edx; dwFlags
0x1800027da  mov     rcx, rax; hHeap
0x1800027dd  call    cs:__imp_HeapFree
0x1800027e3  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800027e7  lea     rax, [rcx-1]
0x1800027eb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800027ef  jbe     loc_180002AB5
0x1800027f5  xor     eax, eax
0x1800027f7  mov     r14, [rsp+0B0h+var_20]
0x1800027ff  mov     rsi, [rsp+0A0h]
0x180002807  mov     rdi, [rsp+0B0h+var_18]
0x18000280f  mov     r15, [rsp+0B0h+var_28]
0x180002817  add     rsp, 0A8h
0x18000281e  pop     rbx
0x18000281f  pop     rbp
0x180002820  retn
0x180002821  call    cs:__imp_RegCloseKey
0x180002827  jmp     short loc_1800027B1
0x180002829  call    cs:__imp_GetLastError
0x18000282f  mov     edi, eax
0x180002831  cmp     eax, 3F0h
0x180002836  jnz     loc_180002973
0x18000283c  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180002840  lea     rax, [rcx-1]
0x180002844  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002848  jbe     loc_180002A29
0x18000284e  mov     [rbp+57h+TokenHandle], r15
0x180002852  call    cs:__imp_GetCurrentProcess
0x180002858  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000285c  mov     edx, 8; DesiredAccess
0x180002861  mov     rcx, rax; ProcessHandle
0x180002864  call    cs:__imp_OpenProcessToken
0x18000286a  test    eax, eax
0x18000286c  jnz     loc_180002604
0x180002872  mov     rcx, [rbp+5Fh]; this
0x180002876  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000287d  mov     edx, 1D0h; void *
0x180002882  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180002887  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000288b  mov     ebx, eax
0x18000288d  lea     rdx, [rcx-1]
0x180002891  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180002895  jbe     loc_180002A33
0x18000289b  mov     eax, ebx
0x18000289d  jmp     loc_180002807
0x1800028a2  mov     rcx, [rbp+5Fh]; this
0x1800028a6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800028ad  mov     r9d, edi; char *
0x1800028b0  mov     edx, 1D5h; void *
0x1800028b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800028ba  lea     rcx, [rbp+57h+lpSubKey]
0x1800028be  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800028c3  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800028c7  lea     rdx, [rcx-1]
0x1800028cb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800028cf  jbe     loc_180002A3E
0x1800028d5  mov     eax, edi
0x1800028d7  jmp     loc_180002807
0x1800028dc  mov     rcx, [rbp+5Fh]; this
0x1800028e0  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800028e7  mov     r9d, edi; char *
0x1800028ea  mov     edx, 1E5h; void *
0x1800028ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800028f4  mov     rcx, [rbp+57h+hkey]; hKey
0x1800028f8  test    rcx, rcx
0x1800028fb  jnz     short loc_180002928
0x1800028fd  lea     rcx, [rbp+57h+var_50]
0x180002901  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180002906  lea     rcx, [rbp+57h+lpSubKey]
0x18000290a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000290f  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180002913  lea     rdx, [rcx-1]
0x180002917  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000291b  jbe     loc_180002A68
0x180002921  mov     eax, edi
0x180002923  jmp     loc_1800027F7
0x180002928  call    cs:__imp_RegCloseKey
0x18000292e  jmp     short loc_1800028FD
0x180002930  mov     rcx, [rbp+5Fh]; this
0x180002934  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000293b  mov     r9d, edi; char *
0x18000293e  mov     edx, 1DFh; void *
0x180002943  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002948  lea     rcx, [rbp+57h+var_50]
0x18000294c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180002951  lea     rcx, [rbp+57h+lpSubKey]
0x180002955  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000295a  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000295e  lea     rax, [rcx-1]
0x180002962  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002966  jbe     loc_180002A5D
0x18000296c  mov     eax, edi
0x18000296e  jmp     loc_1800027FF
0x180002973  test    eax, eax
0x180002975  jle     short loc_180002980
0x180002977  movzx   edi, ax
0x18000297a  or      edi, 80070000h
0x180002980  test    edi, edi
0x180002982  jns     short loc_18000299C
0x180002984  mov     rcx, [rbp+5Fh]; this
0x180002988  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000298f  mov     r9d, edi; char *
0x180002992  mov     edx, 1CFh; void *
0x180002997  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000299c  lea     rcx, [rbp+57h+TokenHandle]
0x1800029a0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800029a5  mov     eax, edi
0x1800029a7  jmp     loc_180002807
0x1800029ac  mov     rcx, [rbp+57h+hKey]; hKey
0x1800029b0  test    rcx, rcx
0x1800029b3  jz      short loc_1800029BB
0x1800029b5  call    cs:__imp_RegCloseKey
0x1800029bb  lea     rcx, [rbp+57h+lpSubKey]
0x1800029bf  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800029c4  lea     rcx, [rbp+57h+TokenHandle]
0x1800029c8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800029cd  mov     eax, edi
0x1800029cf  jmp     loc_1800027FF
0x1800029d4  mov     rcx, [rbp+5Fh]; this
0x1800029d8  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800029df  mov     r9d, eax; char *
0x1800029e2  mov     edx, 1E2h; void *
0x1800029e7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800029ec  mov     rcx, [rbp+57h+hkey]; hKey
0x1800029f0  mov     ebx, eax
0x1800029f2  test    rcx, rcx
0x1800029f5  jz      short loc_1800029FD
0x1800029f7  call    cs:__imp_RegCloseKey
0x1800029fd  lea     rcx, [rbp+57h+var_50]
0x180002a01  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180002a06  lea     rcx, [rbp+57h+lpSubKey]
0x180002a0a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180002a0f  lea     rcx, [rbp+57h+TokenHandle]
0x180002a13  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180002a18  mov     eax, ebx
0x180002a1a  jmp     loc_1800027F7
0x180002a1f  mov     eax, 80070057h
0x180002a24  jmp     loc_180002817
0x180002a29  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180002a2e  jmp     loc_18000284E
0x180002a33  call    cs:__imp_CloseHandle
0x180002a39  jmp     loc_18000289B
0x180002a3e  call    cs:__imp_CloseHandle
0x180002a44  jmp     loc_1800028D5
0x180002a49  jle     loc_1800029AC
0x180002a4f  movzx   edi, ax
0x180002a52  or      edi, 80070000h
0x180002a58  jmp     loc_1800029AC
0x180002a5d  call    cs:__imp_CloseHandle
0x180002a63  jmp     loc_18000296C
0x180002a68  call    cs:__imp_CloseHandle
0x180002a6e  jmp     loc_180002921
0x180002a73  or      dword ptr [rbx], 1
0x180002a76  jmp     loc_18000277E
0x180002a7b  or      dword ptr [rbx], 4
0x180002a7e  jmp     loc_180002786
0x180002a83  or      dword ptr [rbx], 4
0x180002a86  jmp     loc_180002790
0x180002a8b  or      dword ptr [rbx], 2
0x180002a8e  lea     rdx, aDeleteroamingc; "DeleteRoamingCache"
0x180002a95  call    ?CheckPolicy@@YAHPEAUHKEY__@@PEBGH@Z; CheckPolicy(HKEY__ *,ushort const *,int)
0x180002a9a  test    eax, eax
0x180002a9c  mov     eax, [rbp+57h+arg_0]
0x180002a9f  jz      loc_18000279E
0x180002aa5  or      dword ptr [rbx], 1
0x180002aa8  jmp     loc_18000279E
0x180002aad  or      dword ptr [rbx], 1
0x180002ab0  jmp     loc_1800027A8
0x180002ab5  call    cs:__imp_CloseHandle
0x180002abb  jmp     loc_1800027F5
```
