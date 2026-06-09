# GetProfileTypeInternal(ulong *)

- ea: `0x180002490`
- end: `0x180002a32`
- name: `?GetProfileTypeInternal@@YAJPEAK@Z`
- size: `1442`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ab30`

## callees

- `0x180002468`
- `0x180002490`
- `0x180002a40`
- `0x180003480`
- `0x1800040b0`
- `0x18000d57c`
- `0x18000dae0`
- `0x18000db08`
- `0x18000dc30`
- `0x180015508`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002547`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800025c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002547`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800025c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002566`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002748`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000286a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800028fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002945`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002566`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002748`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000286a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800028fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002945`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002611`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002671`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002611`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002671`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800024dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800024dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800024be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800024be`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800027a0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800027a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002788`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002759`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002987`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002998`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800029bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800029ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002987`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002998`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800029bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800029ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a21`

## string_xrefs

- `0x1800027b8`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x1800027e8`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x180002822`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x18000287c`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x1800028d0`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x180002926`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x1800029fa`: `DeleteRoamingCache`

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
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
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
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
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
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v34);
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
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
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v34);
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
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
                Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v34);
                Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
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
0x180002490  mov     rax, rsp
0x180002493  push    rbp
0x180002494  push    rbx
0x180002495  lea     rbp, [rax-5Fh]
0x180002499  sub     rsp, 0A8h
0x1800024a0  mov     rbx, rcx
0x1800024a3  test    rcx, rcx
0x1800024a6  jz      loc_180002973
0x1800024ac  mov     [rax-20h], rdi
0x1800024b0  mov     [rax-30h], r15
0x1800024b4  xor     r15d, r15d
0x1800024b7  mov     [rcx], r15d
0x1800024ba  mov     [rbp+57h+TokenHandle], r15
0x1800024be  call    cs:__imp_GetCurrentThread
0x1800024c5  nop     dword ptr [rax+rax+00h]
0x1800024ca  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800024ce  mov     edx, 8; DesiredAccess
0x1800024d3  mov     rcx, rax; ThreadHandle
0x1800024d6  mov     r8d, 1; OpenAsSelf
0x1800024dc  call    cs:__imp_OpenThreadToken
0x1800024e3  nop     dword ptr [rax+rax+00h]
0x1800024e8  test    eax, eax
0x1800024ea  jz      loc_180002759
0x1800024f0  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800024f4  lea     rdx, [rbp+57h+lpSubKey]; unsigned __int16 **
0x1800024f8  mov     [rbp+57h+lpSubKey], r15
0x1800024fc  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFFh
0x180002504  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFFh
0x18000250c  call    ?GetProfileSidString@@YAJPEAXPEAPEAG@Z; GetProfileSidString(void *,ushort * *)
0x180002511  mov     edi, eax
0x180002513  test    eax, eax
0x180002515  js      loc_1800027E4
0x18000251b  lea     rax, [rbp+57h+hKey]
0x18000251f  mov     [rsp+0A0h], rsi
0x180002527  mov     rsi, [rbp+57h+lpSubKey]
0x18000252b  mov     r9d, 20019h; samDesired
0x180002531  mov     rdx, rsi; lpSubKey
0x180002534  mov     [rbp+57h+hKey], r15
0x180002538  xor     r8d, r8d; ulOptions
0x18000253b  mov     [rsp+0B0h+phkResult], rax; int
0x180002540  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180002547  call    cs:__imp_RegOpenKeyExW
0x18000254e  nop     dword ptr [rax+rax+00h]
0x180002553  mov     edi, eax
0x180002555  test    eax, eax
0x180002557  jnz     loc_1800029A9
0x18000255d  mov     rcx, [rbp+57h+hKey]; hKey
0x180002561  test    rcx, rcx
0x180002564  jz      short loc_180002572
0x180002566  call    cs:__imp_RegCloseKey
0x18000256d  nop     dword ptr [rax+rax+00h]
0x180002572  lea     rdx, [rbp+57h+var_50]; unsigned __int16 **
0x180002576  mov     [rbp+57h+var_50], r15
0x18000257a  mov     rcx, rsi; lpString1
0x18000257d  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFFh
0x180002585  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFFh
0x18000258d  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180002592  mov     edi, eax
0x180002594  test    eax, eax
0x180002596  js      loc_180002878
0x18000259c  lea     rax, [rbp+57h+hkey]
0x1800025a0  mov     [rsp+0B0h+var_20], r14
0x1800025a8  mov     r14, [rbp+57h+var_50]
0x1800025ac  mov     r9d, 20019h; samDesired
0x1800025b2  mov     rdx, r14; lpSubKey
0x1800025b5  mov     [rbp+57h+hkey], r15
0x1800025b9  xor     r8d, r8d; ulOptions
0x1800025bc  mov     [rsp+0B0h+phkResult], rax; unsigned int
0x1800025c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800025c8  call    cs:__imp_RegOpenKeyExW
0x1800025cf  nop     dword ptr [rax+rax+00h]
0x1800025d4  test    eax, eax
0x1800025d6  jnz     loc_180002922
0x1800025dc  mov     rcx, [rbp+57h+hkey]; hkey
0x1800025e0  lea     rax, [rbp+57h+hKey]
0x1800025e4  mov     [rsp+30h], rax; pcbData
0x1800025e9  lea     r8, Value; "State"
0x1800025f0  lea     rax, [rbp+57h+arg_0]
0x1800025f4  mov     [rbp+57h+arg_0], r15d
0x1800025f8  mov     [rsp+0B0h+pvData], rax; pvData
0x1800025fd  mov     r9d, 10h; dwFlags
0x180002603  xor     edx, edx; lpSubKey
0x180002605  mov     [rsp+0B0h+phkResult], r15; int
0x18000260a  mov     dword ptr [rbp+57h+hKey], 4
0x180002611  call    cs:__imp_RegGetValueW
0x180002618  nop     dword ptr [rax+rax+00h]
0x18000261d  mov     edi, eax
0x18000261f  test    eax, eax
0x180002621  jle     short loc_18000262C
0x180002623  movzx   edi, ax
0x180002626  or      edi, 80070000h
0x18000262c  test    edi, edi
0x18000262e  js      loc_18000281E
0x180002634  mov     rcx, [rbp+57h+hkey]; hkey
0x180002638  lea     rax, [rbp+57h+hKey]
0x18000263c  mov     [rsp+30h], rax; pcbData
0x180002641  lea     r8, aUserpreference; "UserPreference"
0x180002648  lea     rax, [rbp+57h+arg_8]
0x18000264c  mov     [rbp+57h+arg_8], 63h ; 'c'
0x180002653  mov     [rsp+0B0h+pvData], rax; pvData
0x180002658  lea     rdx, SubKey; "Preference"
0x18000265f  mov     r9d, 10h; dwFlags
0x180002665  mov     [rsp+0B0h+phkResult], r15; pdwType
0x18000266a  mov     dword ptr [rbp+57h+hKey], 4
0x180002671  call    cs:__imp_RegGetValueW
0x180002678  nop     dword ptr [rax+rax+00h]
0x18000267d  mov     eax, [rbp+57h+arg_0]
0x180002680  test    al, al
0x180002682  js      loc_1800029DF
0x180002688  test    al, 1
0x18000268a  jnz     loc_1800029E7
0x180002690  bt      eax, 10h
0x180002694  jb      loc_1800029EF
0x18000269a  cmp     [rbp+57h+arg_8], r15d
0x18000269e  jz      short loc_1800026A8
0x1800026a0  test    al, 18h
0x1800026a2  jnz     loc_1800029F7
0x1800026a8  bt      eax, 0Bh
0x1800026ac  jb      loc_180002A19
0x1800026b2  mov     rcx, [rbp+57h+hkey]; hKey
0x1800026b6  test    rcx, rcx
0x1800026b9  jnz     loc_180002748
0x1800026bf  test    r14, r14
0x1800026c2  jz      short loc_1800026E4
0x1800026c4  call    cs:__imp_GetProcessHeap
0x1800026cb  nop     dword ptr [rax+rax+00h]
0x1800026d0  mov     r8, r14; lpMem
0x1800026d3  xor     edx, edx; dwFlags
0x1800026d5  mov     rcx, rax; hHeap
0x1800026d8  call    cs:__imp_HeapFree
0x1800026df  nop     dword ptr [rax+rax+00h]
0x1800026e4  test    rsi, rsi
0x1800026e7  jz      short loc_180002709
0x1800026e9  call    cs:__imp_GetProcessHeap
0x1800026f0  nop     dword ptr [rax+rax+00h]
0x1800026f5  mov     r8, rsi; lpMem
0x1800026f8  xor     edx, edx; dwFlags
0x1800026fa  mov     rcx, rax; hHeap
0x1800026fd  call    cs:__imp_HeapFree
0x180002704  nop     dword ptr [rax+rax+00h]
0x180002709  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000270d  lea     rax, [rcx-1]
0x180002711  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002715  jbe     loc_180002A21
0x18000271b  xor     eax, eax
0x18000271d  mov     r14, [rsp+0B0h+var_20]
0x180002725  mov     rsi, [rsp+0A0h]
0x18000272d  mov     rdi, [rsp+0B0h+var_18]
0x180002735  mov     r15, [rsp+0B0h+var_28]
0x18000273d  add     rsp, 0A8h
0x180002744  pop     rbx
0x180002745  pop     rbp
0x180002746  retn
0x180002748  call    cs:__imp_RegCloseKey
0x18000274f  nop     dword ptr [rax+rax+00h]
0x180002754  jmp     loc_1800026BF
0x180002759  call    cs:__imp_GetLastError
0x180002760  nop     dword ptr [rax+rax+00h]
0x180002765  mov     edi, eax
0x180002767  cmp     eax, 3F0h
0x18000276c  jnz     loc_1800028BB
0x180002772  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180002776  lea     rax, [rcx-1]
0x18000277a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000277e  jbe     loc_18000297D
0x180002784  mov     [rbp+57h+TokenHandle], r15
0x180002788  call    cs:__imp_GetCurrentProcess
0x18000278f  nop     dword ptr [rax+rax+00h]
0x180002794  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180002798  mov     edx, 8; DesiredAccess
0x18000279d  mov     rcx, rax; ProcessHandle
0x1800027a0  call    cs:__imp_OpenProcessToken
0x1800027a7  nop     dword ptr [rax+rax+00h]
0x1800027ac  test    eax, eax
0x1800027ae  jnz     loc_1800024F0
0x1800027b4  mov     rcx, [rbp+5Fh]; this
0x1800027b8  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800027bf  mov     edx, 1D0h; void *
0x1800027c4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800027c9  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800027cd  mov     ebx, eax
0x1800027cf  lea     rdx, [rcx-1]
0x1800027d3  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800027d7  jbe     loc_180002987
0x1800027dd  mov     eax, ebx
0x1800027df  jmp     loc_18000272D
0x1800027e4  mov     rcx, [rbp+5Fh]; this
0x1800027e8  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800027ef  mov     r9d, edi; char *
0x1800027f2  mov     edx, 1D5h; void *
0x1800027f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800027fc  lea     rcx, [rbp+57h+lpSubKey]
0x180002800  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180002805  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180002809  lea     rdx, [rcx-1]
0x18000280d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180002811  jbe     loc_180002998
0x180002817  mov     eax, edi
0x180002819  jmp     loc_18000272D
0x18000281e  mov     rcx, [rbp+5Fh]; this
0x180002822  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x180002829  mov     r9d, edi; char *
0x18000282c  mov     edx, 1E5h; void *
0x180002831  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002836  mov     rcx, [rbp+57h+hkey]; hKey
0x18000283a  test    rcx, rcx
0x18000283d  jnz     short loc_18000286A
0x18000283f  lea     rcx, [rbp+57h+var_50]
0x180002843  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180002848  lea     rcx, [rbp+57h+lpSubKey]
0x18000284c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180002851  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180002855  lea     rdx, [rcx-1]
0x180002859  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000285d  jbe     loc_1800029CE
0x180002863  mov     eax, edi
0x180002865  jmp     loc_18000271D
0x18000286a  call    cs:__imp_RegCloseKey
0x180002871  nop     dword ptr [rax+rax+00h]
0x180002876  jmp     short loc_18000283F
0x180002878  mov     rcx, [rbp+5Fh]; this
0x18000287c  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x180002883  mov     r9d, edi; char *
0x180002886  mov     edx, 1DFh; void *
0x18000288b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002890  lea     rcx, [rbp+57h+var_50]
0x180002894  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180002899  lea     rcx, [rbp+57h+lpSubKey]
0x18000289d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800028a2  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800028a6  lea     rax, [rcx-1]
0x1800028aa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800028ae  jbe     loc_1800029BD
0x1800028b4  mov     eax, edi
0x1800028b6  jmp     loc_180002725
0x1800028bb  test    eax, eax
0x1800028bd  jle     short loc_1800028C8
0x1800028bf  movzx   edi, ax
0x1800028c2  or      edi, 80070000h
0x1800028c8  test    edi, edi
0x1800028ca  jns     short loc_1800028E4
0x1800028cc  mov     rcx, [rbp+5Fh]; this
0x1800028d0  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800028d7  mov     r9d, edi; char *
0x1800028da  mov     edx, 1CFh; void *
0x1800028df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800028e4  lea     rcx, [rbp+57h+TokenHandle]
0x1800028e8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800028ed  mov     eax, edi
0x1800028ef  jmp     loc_18000272D
0x1800028f4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800028f8  test    rcx, rcx
0x1800028fb  jz      short loc_180002909
0x1800028fd  call    cs:__imp_RegCloseKey
0x180002904  nop     dword ptr [rax+rax+00h]
0x180002909  lea     rcx, [rbp+57h+lpSubKey]
0x18000290d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180002912  lea     rcx, [rbp+57h+TokenHandle]
0x180002916  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000291b  mov     eax, edi
0x18000291d  jmp     loc_180002725
0x180002922  mov     rcx, [rbp+5Fh]; this
0x180002926  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000292d  mov     r9d, eax; char *
0x180002930  mov     edx, 1E2h; void *
0x180002935  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000293a  mov     rcx, [rbp+57h+hkey]; hKey
0x18000293e  mov     ebx, eax
0x180002940  test    rcx, rcx
0x180002943  jz      short loc_180002951
0x180002945  call    cs:__imp_RegCloseKey
0x18000294c  nop     dword ptr [rax+rax+00h]
0x180002951  lea     rcx, [rbp+57h+var_50]
0x180002955  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000295a  lea     rcx, [rbp+57h+lpSubKey]
0x18000295e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180002963  lea     rcx, [rbp+57h+TokenHandle]
0x180002967  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000296c  mov     eax, ebx
0x18000296e  jmp     loc_18000271D
0x180002973  mov     eax, 80070057h
0x180002978  jmp     loc_18000273D
0x18000297d  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180002982  jmp     loc_180002784
0x180002987  call    cs:__imp_CloseHandle
0x18000298e  nop     dword ptr [rax+rax+00h]
0x180002993  jmp     loc_1800027DD
0x180002998  call    cs:__imp_CloseHandle
0x18000299f  nop     dword ptr [rax+rax+00h]
0x1800029a4  jmp     loc_180002817
0x1800029a9  jle     loc_1800028F4
0x1800029af  movzx   edi, ax
0x1800029b2  or      edi, 80070000h
0x1800029b8  jmp     loc_1800028F4
0x1800029bd  call    cs:__imp_CloseHandle
0x1800029c4  nop     dword ptr [rax+rax+00h]
0x1800029c9  jmp     loc_1800028B4
0x1800029ce  call    cs:__imp_CloseHandle
0x1800029d5  nop     dword ptr [rax+rax+00h]
0x1800029da  jmp     loc_180002863
  ... truncated ...
```
