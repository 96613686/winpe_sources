# GetProfileSidString(void *,ushort * *)

- ea: `0x180002a40`
- end: `0x1800033d4`
- name: `?GetProfileSidString@@YAJPEAXPEAPEAG@Z`
- size: `2452`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180002490`

## callees

- `0x180002a40`
- `0x1800033e0`
- `0x180003910`
- `0x180003e90`
- `0x1800040b0`
- `0x18000438c`
- `0x1800043f0`
- `0x180004470`
- `0x180005690`
- `0x180005900`
- `0x180005b30`
- `0x180008000`
- `0x180008a14`
- `0x18000db08`
- `0x18000efe0`
- `0x18001408c`
- `0x18001b3b4`
- `0x18001c00c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002b7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002bde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002b7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002bde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002aa3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002b25`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002eb1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002fe1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002aa3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002b25`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002eb1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002fe1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002b0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002b68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002bca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002dec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000322e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002b0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002b68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002bca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002dec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000322e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002dd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800031dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002dd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800031dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000319d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003301`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000319d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003301`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800031ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000330f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800031ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000330f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000318c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000318c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002ada`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003108`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002ada`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003108`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180002afd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180002afd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180002b46`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180002b46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fa2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fa2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180002ba7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180002ba7`

## string_xrefs

- `0x180003159`: `OneCore\internal\DS\inc\profiles\sid.h`
- `0x1800032a1`: `OneCore\internal\DS\inc\profiles\sid.h`
- `0x1800033a9`: `OneCore\internal\DS\inc\profiles\sid.h`
- `0x180002e33`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180003213`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180003259`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetProfileSidString(HANDLE TokenHandle, unsigned __int16 **a2)
{
  HANDLE v2; // r13
  WCHAR *v3; // r15
  unsigned __int64 v4; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rdx
  WCHAR *v7; // rsi
  void *v8; // r14
  int Error; // ebx
  DWORD LengthSid; // ebx
  HANDLE v11; // rax
  void *v12; // rax
  void *v13; // r15
  HANDLE v14; // rax
  int v15; // ebx
  HANDLE v16; // rax
  LPWSTR v17; // rsi
  unsigned int v18; // r13d
  __int64 v19; // rbx
  wchar_t *v20; // rax
  wchar_t *v21; // r8
  __int64 v22; // rcx
  const wchar_t *v23; // rdx
  __int64 UserProfileListRootKeyName; // r9
  wchar_t v25; // ax
  int v26; // eax
  WCHAR *v27; // r15
  WCHAR *v28; // r12
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // rbx
  unsigned __int64 v31; // rsi
  int v32; // r14d
  HANDLE v33; // rax
  int v34; // ebx
  HANDLE v35; // rax
  HANDLE v36; // rcx
  unsigned __int16 **v37; // r14
  unsigned __int64 v38; // rbx
  HANDLE v39; // rax
  const size_t *v41; // rcx
  unsigned __int64 v42; // r8
  __int64 v43; // r9
  unsigned __int16 *v44; // r10
  unsigned __int16 v45; // ax
  __int64 v46; // rbx
  bool v47; // cf
  HANDLE v48; // rax
  HANDLE v49; // rax
  WCHAR *v50; // rax
  WCHAR *v51; // rcx
  WCHAR *v52; // rdx
  WCHAR v53; // ax
  int *v54; // rdx
  BOOL TokenInformation; // eax
  HKEY v56; // rsi
  DWORD LastError; // ebx
  int OldSidString; // eax
  HANDLE v59; // rax
  __int64 v60; // rdx
  int v61; // eax
  unsigned int v62; // ebx
  int ReturnLength; // [rsp+20h] [rbp-59h]
  LPVOID lpMem; // [rsp+30h] [rbp-49h] BYREF
  __int64 v65; // [rsp+38h] [rbp-41h]
  __int64 v66; // [rsp+40h] [rbp-39h]
  HLOCAL hMem[3]; // [rsp+48h] [rbp-31h] BYREF
  LPCWSTR lpSubKey[14]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  HKEY TokenInformationLength; // [rsp+F0h] [rbp+77h] BYREF
  LPWSTR StringSid; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = TokenHandle;
  *a2 = 0;
  v3 = 0;
  hMem[0] = 0;
  v4 = -1;
  hMem[1] = (HLOCAL)-1LL;
  hMem[2] = (HLOCAL)-1LL;
  LODWORD(TokenInformationLength) = 200;
  ProcessHeap = GetProcessHeap();
  v7 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0xC8u);
  StringSid = v7;
  if ( !v7 )
  {
    v15 = -2147024882;
    goto LABEL_20;
  }
  v8 = 0;
  if ( GetTokenInformation(v2, TokenUser, v7, (DWORD)TokenInformationLength, (PDWORD)&TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      Error = ResultFromHeapReAlloc(v7, (unsigned int)TokenInformationLength, (void **)&StringSid);
      v7 = StringSid;
      if ( Error < 0 )
        goto LABEL_10;
      TokenInformation = GetTokenInformation(
                           v2,
                           TokenUser,
                           StringSid,
                           (DWORD)TokenInformationLength,
                           (PDWORD)&TokenInformationLength);
      Error = ResultFromWin32Bool(TokenInformation);
    }
  }
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*(PSID *)v7);
    LODWORD(TokenInformationLength) = LengthSid;
    v11 = GetProcessHeap();
    v12 = HeapAlloc(v11, 8u, LengthSid);
    v13 = v12;
    if ( !v12 )
    {
      Error = -2147024882;
      goto LABEL_9;
    }
    if ( CopySid((DWORD)TokenInformationLength, v12, *(PSID *)v7) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        ResultFromHeapFree(v13);
        goto LABEL_9;
      }
    }
    v8 = v13;
LABEL_9:
    v3 = (WCHAR *)hMem[0];
  }
LABEL_10:
  if ( v7 )
  {
    v14 = GetProcessHeap();
    if ( !HeapFree(v14, 0, v7) )
      ResultFromKnownLastError();
  }
  if ( Error < 0 )
    goto LABEL_131;
  StringSid = 0;
  if ( ConvertSidToStringSidW(v8, &StringSid) )
  {
    v15 = 0;
  }
  else
  {
    v15 = ResultFromKnownLastError();
    if ( v15 < 0 )
      goto LABEL_17;
  }
  v3 = StringSid;
  hMem[0] = StringSid;
LABEL_17:
  if ( v8 )
  {
    v16 = GetProcessHeap();
    if ( !HeapFree(v16, 0, v8) )
      ResultFromKnownLastError();
  }
LABEL_20:
  if ( v15 >= 0 )
  {
    lpSubKey[1] = (LPCWSTR)-1LL;
    lpSubKey[2] = (LPCWSTR)-1LL;
    v17 = 0;
    lpMem = 0;
    v65 = 0;
    v66 = 0;
    v18 = -2147024362;
    if ( (unsigned int)IsServiceSid(v3) || (unsigned int)IsContainerSid(v3) )
    {
      TokenInformationLength = 0;
      v19 = 57;
      if ( is_mul_ok(0x39u, 2u) )
      {
        v20 = (wchar_t *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(114);
        v21 = v20;
        if ( v20 )
        {
          v66 = 57;
          lpMem = v20;
          *v20 = 0;
          v22 = 56;
          v23 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList";
          UserProfileListRootKeyName = 0;
          while ( v22 )
          {
            v25 = *v23;
            if ( !*v23 )
              break;
            ++v23;
            *v21++ = v25;
            --v22;
            if ( !--v19 )
            {
              --v21;
              break;
            }
          }
          *v21 = 0;
          v65 = 56;
        }
        else
        {
          UserProfileListRootKeyName = 2147942414LL;
        }
      }
      else
      {
        UserProfileListRootKeyName = 2147942934LL;
      }
    }
    else
    {
      v65 = -1;
      v66 = -1;
      UserProfileListRootKeyName = (unsigned int)GetUserProfileListRootKeyName((unsigned __int16 **)&lpMem, v54);
    }
    if ( (int)UserProfileListRootKeyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"OneCore\\internal\\DS\\inc\\profiles\\sid.h",
        (const char *)UserProfileListRootKeyName,
        ReturnLength);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpMem);
    }
    else
    {
      v26 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
              &lpMem,
              L"\\%s",
              v3);
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x81,
          (unsigned int)"OneCore\\internal\\DS\\inc\\profiles\\sid.h",
          (const char *)(unsigned int)v26,
          ReturnLength);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpMem);
      }
      else
      {
        StringSid = 0;
        lpSubKey[0] = 0;
        v27 = (WCHAR *)lpMem;
        if ( lpMem )
        {
          v28 = 0;
          memset(&lpSubKey[3], 0, 24);
          v29 = v65;
          if ( v65 == -1 )
          {
            v29 = -1;
            do
              ++v29;
            while ( *((_WORD *)lpMem + v29) );
          }
          v30 = -1;
          do
            ++v30;
          while ( *((_WORD *)lpMem + v30) );
          if ( v29 == -1 )
          {
            v29 = v30;
          }
          else if ( v29 < v30 )
          {
            v30 = v29;
          }
          v31 = v29 + 1;
          if ( v29 + 1 >= v29 && (TokenInformationLength = 0, is_mul_ok(v31, 2u)) )
          {
            v49 = GetProcessHeap();
            v50 = (WCHAR *)HeapAlloc(v49, 0, 2 * v31);
            if ( v50 )
            {
              v28 = v50;
              *v50 = 0;
              v32 = 0;
              if ( v31 )
              {
                if ( v31 > 0x7FFFFFFF || v30 > 0x7FFFFFFE )
                {
                  *v50 = 0;
                }
                else
                {
                  v51 = v27;
                  v52 = v50;
                  while ( v30 )
                  {
                    v53 = *v51;
                    if ( !*v51 )
                      break;
                    ++v51;
                    *v52++ = v53;
                    --v30;
                    if ( !--v31 )
                    {
                      --v52;
                      break;
                    }
                  }
                  *v52 = 0;
                }
              }
            }
            else
            {
              v32 = -2147024882;
            }
          }
          else
          {
            v32 = -2147024362;
          }
          if ( v32 >= 0 )
          {
            v34 = v32;
            v17 = v28;
            StringSid = v28;
            lpSubKey[0] = v28;
          }
          else
          {
            if ( v28 )
            {
              v33 = GetProcessHeap();
              HeapFree(v33, 0, v28);
            }
            v34 = v32;
            v17 = StringSid;
          }
          if ( v34 >= 0 )
          {
            v35 = GetProcessHeap();
            HeapFree(v35, 0, v27);
            TokenInformationLength = 0;
            v17 = StringSid;
            if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, StringSid, 0, 0x20019u, &TokenInformationLength) )
            {
LABEL_49:
              v36 = GetProcessHeap();
              v3 = (WCHAR *)hMem[0];
              do
                ++v4;
              while ( *((_WORD *)hMem[0] + v4) );
              v37 = a2;
              *a2 = 0;
              v38 = v4 + 1;
              if ( v4 + 1 < v4 || !is_mul_ok(v38, 2u) )
                goto LABEL_53;
              v6 = (unsigned __int16 *)HeapAlloc(v36, 0, 2 * v38);
              *a2 = v6;
              if ( !v6 )
              {
                v18 = -2147024882;
LABEL_53:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x124,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
                  (const char *)v18,
                  ReturnLength);
                if ( TokenInformationLength )
                  RegCloseKey(TokenInformationLength);
                if ( v17 )
                {
                  v39 = GetProcessHeap();
                  HeapFree(v39, 0, v17);
                }
                if ( v3 )
                  LocalFree(v3);
                return v18;
              }
              if ( v38 > 0x7FFFFFFF )
              {
                *v6 = 0;
              }
              else if ( v4 >= 0x7FFFFFFF )
              {
                if ( v4 != -1 )
                  *v6 = 0;
              }
              else
              {
                v41 = (const size_t *)v3;
                if ( !v3 )
                {
                  v41 = &Format;
                  v4 = 0;
                }
                if ( v38 )
                {
                  v42 = v38;
                  v43 = 0;
                  v44 = v6;
                  while ( v4 )
                  {
                    v45 = *(_WORD *)v41;
                    if ( !*(_WORD *)v41 )
                      break;
                    v41 = (const size_t *)((char *)v41 + 2);
                    *v6++ = v45;
                    --v4;
                    ++v43;
                    if ( !--v42 )
                    {
                      *(v6 - 1) = 0;
                      goto LABEL_73;
                    }
                  }
                  *v6 = 0;
                  v47 = v38 == v43;
                  v46 = v38 - v43;
                  if ( !v47 && v46 != 1 && (unsigned __int64)(2 * v46) > 2 )
                    memset_0(&v44[v43 + 1], 0, 2 * v46 - 2);
                }
              }
              goto LABEL_73;
            }
            if ( (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Concat(
                        lpSubKey,
                        L".bak",
                        4) >= 0 )
            {
              v56 = TokenInformationLength;
              if ( TokenInformationLength )
              {
                LastError = GetLastError();
                RegCloseKey(v56);
                SetLastError(LastError);
              }
              TokenInformationLength = 0;
              v17 = (LPWSTR)lpSubKey[0];
              if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &TokenInformationLength) )
                goto LABEL_49;
            }
            else
            {
              v17 = (LPWSTR)lpSubKey[0];
            }
            v37 = a2;
            v3 = (WCHAR *)hMem[0];
LABEL_73:
            if ( TokenInformationLength )
              RegCloseKey(TokenInformationLength);
            goto LABEL_75;
          }
        }
        else
        {
          v32 = -2147023728;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x82,
          (unsigned int)"OneCore\\internal\\DS\\inc\\profiles\\sid.h",
          (const char *)(unsigned int)v32,
          ReturnLength);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpMem);
        v3 = (WCHAR *)hMem[0];
      }
    }
    v37 = a2;
LABEL_75:
    if ( v17 )
    {
      v48 = GetProcessHeap();
      HeapFree(v48, 0, v17);
    }
    v2 = TokenHandle;
    goto LABEL_78;
  }
LABEL_131:
  v37 = a2;
LABEL_78:
  if ( *v37 )
    goto LABEL_79;
  OldSidString = GetOldSidString(v2, v6, v37);
  if ( OldSidString < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
      (const char *)(unsigned int)OldSidString,
      ReturnLength);
  if ( *v37 || (v59 = GetProcessHeap(), v61 = _AllocString<CTHeapAllocPolicy>(v59, v60, v3, v37), v62 = v61, v61 >= 0) )
  {
LABEL_79:
    if ( v3 )
      LocalFree(v3);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x131,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
      (const char *)(unsigned int)v61,
      ReturnLength);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(hMem);
    return v62;
  }
}

```

## disassembly

```asm
0x180002a40  mov     [rsp-8+arg_8], rdx
0x180002a45  mov     [rsp-8+arg_0], rcx
0x180002a4a  push    rbp
0x180002a4b  push    rbx
0x180002a4c  push    rsi
0x180002a4d  push    rdi
0x180002a4e  push    r12
0x180002a50  push    r13
0x180002a52  push    r14
0x180002a54  push    r15
0x180002a56  lea     rbp, [rsp-1Fh]
0x180002a5b  sub     rsp, 98h
0x180002a62  mov     r13, rcx
0x180002a65  mov     qword ptr [rdx], 0
0x180002a6c  xor     r15d, r15d
0x180002a6f  mov     [rbp+57h+hMem], r15
0x180002a73  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180002a7a  mov     [rbp+57h+var_80], rdi
0x180002a7e  mov     [rbp+57h+var_78], rdi
0x180002a82  mov     dword ptr [rbp+57h+TokenInformationLength], 0C8h
0x180002a89  call    cs:__imp_GetProcessHeap
0x180002a90  nop     dword ptr [rax+rax+00h]
0x180002a95  mov     rcx, rax; hHeap
0x180002a98  mov     edx, 8; dwFlags
0x180002a9d  mov     r8d, 0C8h; dwBytes
0x180002aa3  call    cs:__imp_HeapAlloc
0x180002aaa  nop     dword ptr [rax+rax+00h]
0x180002aaf  mov     rsi, rax
0x180002ab2  mov     [rbp+57h+StringSid], rax
0x180002ab6  test    rax, rax
0x180002ab9  jz      loc_18000309F
0x180002abf  xor     r14d, r14d
0x180002ac2  lea     rax, [rbp+57h+TokenInformationLength]
0x180002ac6  mov     qword ptr [rsp+0D0h+ReturnLength], rax; int
0x180002acb  mov     r9d, dword ptr [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180002acf  mov     r8, rsi; TokenInformation
0x180002ad2  mov     edx, 1; TokenInformationClass
0x180002ad7  mov     rcx, r13; TokenHandle
0x180002ada  call    cs:__imp_GetTokenInformation
0x180002ae1  nop     dword ptr [rax+rax+00h]
0x180002ae6  mov     r12d, 8007000Eh
0x180002aec  test    eax, eax
0x180002aee  jz      loc_1800030C1
0x180002af4  xor     ebx, ebx
0x180002af6  test    ebx, ebx
0x180002af8  js      short loc_180002B63
0x180002afa  mov     rcx, [rsi]; pSid
0x180002afd  call    cs:__imp_GetLengthSid
0x180002b04  nop     dword ptr [rax+rax+00h]
0x180002b09  mov     ebx, eax
0x180002b0b  mov     dword ptr [rbp+57h+TokenInformationLength], ebx
0x180002b0e  call    cs:__imp_GetProcessHeap
0x180002b15  nop     dword ptr [rax+rax+00h]
0x180002b1a  mov     rcx, rax; hHeap
0x180002b1d  mov     r8d, ebx; dwBytes
0x180002b20  mov     edx, 8; dwFlags
0x180002b25  call    cs:__imp_HeapAlloc
0x180002b2c  nop     dword ptr [rax+rax+00h]
0x180002b31  mov     r15, rax
0x180002b34  test    rax, rax
0x180002b37  jz      loc_18000327A
0x180002b3d  mov     r8, [rsi]; pSourceSid
0x180002b40  mov     rdx, rax; pDestinationSid
0x180002b43  mov     ecx, dword ptr [rbp+57h+TokenInformationLength]; nDestinationSidLength
0x180002b46  call    cs:__imp_CopySid
0x180002b4d  nop     dword ptr [rax+rax+00h]
0x180002b52  test    eax, eax
0x180002b54  jz      loc_180003122
0x180002b5a  xor     ebx, ebx
0x180002b5c  mov     r14, r15
0x180002b5f  mov     r15, [rbp+57h+hMem]
0x180002b63  test    rsi, rsi
0x180002b66  jz      short loc_180002B90
0x180002b68  call    cs:__imp_GetProcessHeap
0x180002b6f  nop     dword ptr [rax+rax+00h]
0x180002b74  mov     rcx, rax; hHeap
0x180002b77  mov     r8, rsi; lpMem
0x180002b7a  xor     edx, edx; dwFlags
0x180002b7c  call    cs:__imp_HeapFree
0x180002b83  nop     dword ptr [rax+rax+00h]
0x180002b88  test    eax, eax
0x180002b8a  jz      loc_180003282
0x180002b90  test    ebx, ebx
0x180002b92  js      loc_1800033CB
0x180002b98  mov     [rbp+57h+StringSid], 0
0x180002ba0  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180002ba4  mov     rcx, r14; Sid
0x180002ba7  call    cs:__imp_ConvertSidToStringSidW
0x180002bae  nop     dword ptr [rax+rax+00h]
0x180002bb3  test    eax, eax
0x180002bb5  jz      loc_1800030AD
0x180002bbb  xor     ebx, ebx
0x180002bbd  mov     r15, [rbp+57h+StringSid]
0x180002bc1  mov     [rbp+57h+hMem], r15
0x180002bc5  test    r14, r14
0x180002bc8  jz      short loc_180002BF2
0x180002bca  call    cs:__imp_GetProcessHeap
0x180002bd1  nop     dword ptr [rax+rax+00h]
0x180002bd6  mov     rcx, rax; hHeap
0x180002bd9  mov     r8, r14; lpMem
0x180002bdc  xor     edx, edx; dwFlags
0x180002bde  call    cs:__imp_HeapFree
0x180002be5  nop     dword ptr [rax+rax+00h]
0x180002bea  test    eax, eax
0x180002bec  jz      loc_18000328C
0x180002bf2  test    ebx, ebx
0x180002bf4  js      loc_1800033CB
0x180002bfa  mov     [rbp+57h+var_68], rdi
0x180002bfe  mov     [rbp+57h+var_60], rdi
0x180002c02  xor     r14d, r14d
0x180002c05  mov     esi, r14d
0x180002c08  mov     [rbp+57h+lpMem], r14
0x180002c0c  mov     [rbp+57h+var_98], r14
0x180002c10  mov     [rbp+57h+var_90], r14
0x180002c14  mov     rcx, r15; lpString1
0x180002c17  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x180002c1c  mov     r13d, 80070216h
0x180002c22  test    eax, eax
0x180002c24  jz      loc_180003076
0x180002c2a  mov     [rbp+57h+TokenInformationLength], r14
0x180002c2e  mov     ebx, 39h ; '9'
0x180002c33  mov     eax, 2
0x180002c38  mul     rbx
0x180002c3b  test    rdx, rdx
0x180002c3e  jnz     loc_18000306E
0x180002c44  mov     rcx, rax
0x180002c47  call    ?Alloc@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAPEAG_K@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Alloc(unsigned __int64)
0x180002c4c  mov     r8, rax
0x180002c4f  test    rax, rax
0x180002c52  jz      loc_180003149
0x180002c58  mov     [rbp+57h+var_90], rbx
0x180002c5c  mov     [rbp+57h+lpMem], rax
0x180002c60  mov     [rax], r14w
0x180002c64  mov     ecx, 38h ; '8'
0x180002c69  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x180002c70  mov     r9d, r14d; char *
0x180002c73  test    rcx, rcx
0x180002c76  jz      short loc_180002CA0
0x180002c78  movzx   eax, word ptr [rdx]
0x180002c7b  test    ax, ax
0x180002c7e  jz      short loc_180002C9B
0x180002c80  add     rdx, 2
0x180002c84  mov     [r8], ax
0x180002c88  add     r8, 2
0x180002c8c  dec     rcx
0x180002c8f  sub     rbx, 1
0x180002c93  jnz     short loc_180002C73
0x180002c95  sub     r8, 2
0x180002c99  jmp     short loc_180002CA0
0x180002c9b  test    rbx, rbx
0x180002c9e  jz      short loc_180002C95
0x180002ca0  mov     [r8], r14w
0x180002ca4  mov     [rbp+57h+var_98], 38h ; '8'
0x180002cac  test    r9d, r9d
0x180002caf  js      loc_180003151
0x180002cb5  mov     r8, r15
0x180002cb8  lea     rdx, aS_0; "\\%s"
0x180002cbf  lea     rcx, [rbp+57h+lpMem]
0x180002cc3  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180002cc8  test    eax, eax
0x180002cca  js      loc_180003296
0x180002cd0  mov     [rbp+57h+StringSid], r14
0x180002cd4  mov     [rbp+57h+lpSubKey], r14
0x180002cd8  mov     r15, [rbp+57h+lpMem]
0x180002cdc  test    r15, r15
0x180002cdf  jz      loc_180003398
0x180002ce5  mov     r12, r14
0x180002ce8  mov     [rbp+57h+var_58], r14
0x180002cec  mov     [rbp+57h+var_50], r14
0x180002cf0  mov     [rbp+57h+var_48], r14
0x180002cf4  mov     rax, [rbp+57h+var_98]
0x180002cf8  cmp     rax, rdi
0x180002cfb  jnz     short loc_180002D0A
0x180002cfd  mov     rax, rdi
0x180002d00  inc     rax
0x180002d03  cmp     [r15+rax*2], si
0x180002d08  jnz     short loc_180002D00
0x180002d0a  test    r15, r15
0x180002d0d  jz      loc_1800032D0
0x180002d13  mov     rbx, rdi
0x180002d16  inc     rbx
0x180002d19  cmp     [r15+rbx*2], si
0x180002d1e  jnz     short loc_180002D16
0x180002d20  cmp     rax, rdi
0x180002d23  jz      loc_180003066
0x180002d29  cmp     rax, rbx
0x180002d2c  jb      loc_18000317B
0x180002d32  lea     rsi, [rax+1]
0x180002d36  cmp     rsi, rax
0x180002d39  jnb     loc_180002FB5
0x180002d3f  mov     r14d, r13d
0x180002d42  test    r14d, r14d
0x180002d45  jns     loc_1800032CB
0x180002d4b  test    r12, r12
0x180002d4e  jz      short loc_180002D70
0x180002d50  call    cs:__imp_GetProcessHeap
0x180002d57  nop     dword ptr [rax+rax+00h]
0x180002d5c  mov     rcx, rax; hHeap
0x180002d5f  mov     r8, r12; lpMem
0x180002d62  xor     edx, edx; dwFlags
0x180002d64  call    cs:__imp_HeapFree
0x180002d6b  nop     dword ptr [rax+rax+00h]
0x180002d70  mov     ebx, r14d
0x180002d73  mov     rsi, [rbp+57h+StringSid]
0x180002d77  test    ebx, ebx
0x180002d79  js      loc_18000339E
0x180002d7f  call    cs:__imp_GetProcessHeap
0x180002d86  nop     dword ptr [rax+rax+00h]
0x180002d8b  mov     rcx, rax; hHeap
0x180002d8e  mov     r8, r15; lpMem
0x180002d91  xor     edx, edx; dwFlags
0x180002d93  call    cs:__imp_HeapFree
0x180002d9a  nop     dword ptr [rax+rax+00h]
0x180002d9f  nop
0x180002da0  xor     r12d, r12d
0x180002da3  mov     [rbp+57h+TokenInformationLength], r12
0x180002da7  mov     rsi, [rbp+57h+TokenInformationLength]
0x180002dab  test    rsi, rsi
0x180002dae  jnz     loc_1800032F0
0x180002db4  mov     [rbp+57h+TokenInformationLength], r12
0x180002db8  lea     rax, [rbp+57h+TokenInformationLength]
0x180002dbc  mov     qword ptr [rsp+0D0h+ReturnLength], rax; int
0x180002dc1  mov     r9d, 20019h; samDesired
0x180002dc7  xor     r8d, r8d; ulOptions
0x180002dca  mov     rsi, [rbp+57h+StringSid]
0x180002dce  mov     rdx, rsi; lpSubKey
0x180002dd1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002dd8  call    cs:__imp_RegOpenKeyExW
0x180002ddf  nop     dword ptr [rax+rax+00h]
0x180002de4  test    eax, eax
0x180002de6  jnz     loc_180003321
0x180002dec  call    cs:__imp_GetProcessHeap
0x180002df3  nop     dword ptr [rax+rax+00h]
0x180002df8  mov     rcx, rax; hHeap
0x180002dfb  mov     r15, [rbp+57h+hMem]
0x180002dff  nop
0x180002e00  inc     rdi
0x180002e03  cmp     word ptr [r15+rdi*2], 0
0x180002e09  jnz     short loc_180002E00
0x180002e0b  mov     r14, [rbp+57h+arg_8]
0x180002e0f  mov     [r14], r12
0x180002e12  lea     rbx, [rdi+1]
0x180002e16  cmp     rbx, rdi
0x180002e19  jb      short loc_180002E2C
0x180002e1b  mov     eax, 2
0x180002e20  mul     rbx
0x180002e23  test    rdx, rdx
0x180002e26  jz      loc_180002EAC
0x180002e2c  mov     rcx, [rbp+5Fh]; this
0x180002e30  mov     r9d, r13d; char *
0x180002e33  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x180002e3a  mov     edx, 124h; void *
0x180002e3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002e44  nop
0x180002e45  mov     rcx, [rbp+57h+TokenInformationLength]; hKey
0x180002e49  test    rcx, rcx
0x180002e4c  jz      short loc_180002E5B
0x180002e4e  call    cs:__imp_RegCloseKey
0x180002e55  nop     dword ptr [rax+rax+00h]
0x180002e5a  nop
0x180002e5b  test    rsi, rsi
0x180002e5e  jz      short loc_180002E80
0x180002e60  call    cs:__imp_GetProcessHeap
0x180002e67  nop     dword ptr [rax+rax+00h]
0x180002e6c  mov     rcx, rax; hHeap
0x180002e6f  mov     r8, rsi; lpMem
0x180002e72  xor     edx, edx; dwFlags
0x180002e74  call    cs:__imp_HeapFree
0x180002e7b  nop     dword ptr [rax+rax+00h]
0x180002e80  test    r15, r15
0x180002e83  jz      short loc_180002E94
0x180002e85  mov     rcx, r15; hMem
0x180002e88  call    cs:__imp_LocalFree
0x180002e8f  nop     dword ptr [rax+rax+00h]
0x180002e94  mov     eax, r13d
0x180002e97  add     rsp, 98h
0x180002e9e  pop     r15
0x180002ea0  pop     r14
0x180002ea2  pop     r13
0x180002ea4  pop     r12
0x180002ea6  pop     rdi
0x180002ea7  pop     rsi
0x180002ea8  pop     rbx
0x180002ea9  pop     rbp
0x180002eaa  retn
0x180002eac  mov     r8, rax; dwBytes
0x180002eaf  xor     edx, edx; dwFlags
0x180002eb1  call    cs:__imp_HeapAlloc
0x180002eb8  nop     dword ptr [rax+rax+00h]
0x180002ebd  mov     rdx, rax
0x180002ec0  mov     [r14], rax
0x180002ec3  mov     r13d, r12d
0x180002ec6  test    rax, rax
0x180002ec9  mov     eax, 8007000Eh
0x180002ece  cmovz   r13d, eax
0x180002ed2  test    rdx, rdx
0x180002ed5  jz      loc_180002E2C
0x180002edb  cmp     rbx, 7FFFFFFFh
0x180002ee2  ja      loc_180003348
0x180002ee8  cmp     rdi, 7FFFFFFFh
  ... truncated ...
```
