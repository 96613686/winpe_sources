# MatchStandardNameEnumProc

- ea: `0x18001a354`
- end: `0x18001a454`
- name: `MatchStandardNameEnumProc`
- size: `256`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017848`

## callees

- `0x180017d24`
- `0x1800189b0`
- `0x180019758`
- `0x18001a354`
- `0x18001b0f6`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001a3fe`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001a3fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a427`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a427`

## pseudocode

```c
__int64 __fastcall MatchStandardNameEnumProc(STRSAFE_LPCWSTR pszSrc, __int64 a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  size_t cchCount2; // [rsp+28h] [rbp-70h]
  HKEY hKey; // [rsp+30h] [rbp-68h] BYREF
  WCHAR String1[32]; // [rsp+40h] [rbp-58h] BYREF

  hKey = 0;
  v4 = 1;
  if ( (int)GetTimeZoneKey(*(HKEY *)(a2 + 32), pszSrc, &hKey) >= 0 )
  {
    memset_0(String1, 0, sizeof(String1));
    LODWORD(cchCount2) = 32;
    if ( (int)GetLocalizedName(hKey, v5, L"MUI_Std", L"Std", String1, cchCount2) >= 0
      && CompareStringW(0x7Fu, 0, String1, -1, *(PCNZWCH *)(a2 + 24), -1) == 2 )
    {
      v4 = 0;
      *(_DWORD *)a2 = StringCchCopyW(*(STRSAFE_LPWSTR *)(a2 + 8), *(int *)(a2 + 16), pszSrc) >= 0;
    }
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x18001a354  mov     r11, rsp
0x18001a357  mov     [r11+18h], rbx
0x18001a35b  mov     [r11+20h], rsi
0x18001a35f  push    rdi
0x18001a360  sub     rsp, 90h
0x18001a367  mov     rax, cs:__security_cookie
0x18001a36e  xor     rax, rsp
0x18001a371  mov     [rsp+98h+var_18], rax
0x18001a379  mov     rbx, rdx
0x18001a37c  mov     qword ptr [r11-68h], 0
0x18001a384  mov     rsi, rcx
0x18001a387  lea     r8, [r11-68h]
0x18001a38b  mov     rdx, rcx
0x18001a38e  mov     edi, 1
0x18001a393  mov     rcx, [rbx+20h]
0x18001a397  call    GetTimeZoneKey
0x18001a39c  test    eax, eax
0x18001a39e  js      loc_18001A42D
0x18001a3a4  xor     edx, edx; Val
0x18001a3a6  lea     r8d, [rdi+3Fh]; Size
0x18001a3aa  lea     rcx, [rsp+98h+String1]; void *
0x18001a3af  call    memset_0
0x18001a3b4  mov     rcx, [rsp+98h+hKey]; hKey
0x18001a3b9  lea     rax, [rsp+98h+String1]
0x18001a3be  mov     dword ptr [rsp+98h+cchCount2], 20h ; ' '; cchDest
0x18001a3c6  lea     r9, aStd; "Std"
0x18001a3cd  lea     r8, aMuiStd; "MUI_Std"
0x18001a3d4  mov     [rsp+98h+lpString2], rax; pszDest
0x18001a3d9  call    GetLocalizedName
0x18001a3de  test    eax, eax
0x18001a3e0  js      short loc_18001A422
0x18001a3e2  mov     rax, [rbx+18h]
0x18001a3e6  lea     r8, [rsp+98h+String1]; lpString1
0x18001a3eb  or      r9d, 0FFFFFFFFh; cchCount1
0x18001a3ef  lea     ecx, [rdi+7Eh]; Locale
0x18001a3f2  mov     dword ptr [rsp+98h+cchCount2], r9d; cchCount2
0x18001a3f7  xor     edx, edx; dwCmpFlags
0x18001a3f9  mov     [rsp+98h+lpString2], rax; lpString2
0x18001a3fe  call    cs:__imp_CompareStringW
0x18001a404  cmp     eax, 2
0x18001a407  jnz     short loc_18001A422
0x18001a409  movsxd  rdx, dword ptr [rbx+10h]; cchDest
0x18001a40d  mov     r8, rsi; pszSrc
0x18001a410  mov     rcx, [rbx+8]; pszDest
0x18001a414  xor     edi, edi
0x18001a416  call    StringCchCopyW
0x18001a41b  not     eax
0x18001a41d  shr     eax, 1Fh
0x18001a420  mov     [rbx], eax
0x18001a422  mov     rcx, [rsp+98h+hKey]; hKey
0x18001a427  call    cs:__imp_RegCloseKey
0x18001a42d  mov     eax, edi
0x18001a42f  mov     rcx, [rsp+98h+var_18]
0x18001a437  xor     rcx, rsp; StackCookie
0x18001a43a  call    __security_check_cookie
0x18001a43f  lea     r11, [rsp+98h+var_8]
0x18001a447  mov     rbx, [r11+20h]
0x18001a44b  mov     rsi, [r11+28h]
0x18001a44f  mov     rsp, r11
0x18001a452  pop     rdi
0x18001a453  retn
```
