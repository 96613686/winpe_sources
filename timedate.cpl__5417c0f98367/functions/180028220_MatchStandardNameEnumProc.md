# MatchStandardNameEnumProc

- ea: `0x180028220`
- end: `0x180028320`
- name: `MatchStandardNameEnumProc`
- size: `256`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180024910`
- `0x180026854`
- `0x1800275e8`
- `0x180028220`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800282f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800282f3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800282ca`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800282ca`

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
0x180028220  mov     r11, rsp
0x180028223  mov     [r11+18h], rbx
0x180028227  mov     [r11+20h], rsi
0x18002822b  push    rdi
0x18002822c  sub     rsp, 90h
0x180028233  mov     rax, cs:__security_cookie
0x18002823a  xor     rax, rsp
0x18002823d  mov     [rsp+98h+var_18], rax
0x180028245  mov     rbx, rdx
0x180028248  mov     qword ptr [r11-68h], 0
0x180028250  mov     rsi, rcx
0x180028253  lea     r8, [r11-68h]
0x180028257  mov     rdx, rcx
0x18002825a  mov     edi, 1
0x18002825f  mov     rcx, [rbx+20h]
0x180028263  call    GetTimeZoneKey
0x180028268  test    eax, eax
0x18002826a  js      loc_1800282F9
0x180028270  xor     edx, edx; Val
0x180028272  lea     r8d, [rdi+3Fh]; Size
0x180028276  lea     rcx, [rsp+98h+String1]; void *
0x18002827b  call    memset_0
0x180028280  mov     rcx, [rsp+98h+hKey]; hKey
0x180028285  lea     rax, [rsp+98h+String1]
0x18002828a  mov     dword ptr [rsp+98h+cchCount2], 20h ; ' '; cchDest
0x180028292  lea     r9, aStd; "Std"
0x180028299  lea     r8, aMuiStd; "MUI_Std"
0x1800282a0  mov     [rsp+98h+lpString2], rax; pszDest
0x1800282a5  call    GetLocalizedName
0x1800282aa  test    eax, eax
0x1800282ac  js      short loc_1800282EE
0x1800282ae  mov     rax, [rbx+18h]
0x1800282b2  lea     r8, [rsp+98h+String1]; lpString1
0x1800282b7  or      r9d, 0FFFFFFFFh; cchCount1
0x1800282bb  lea     ecx, [rdi+7Eh]; Locale
0x1800282be  mov     dword ptr [rsp+98h+cchCount2], r9d; cchCount2
0x1800282c3  xor     edx, edx; dwCmpFlags
0x1800282c5  mov     [rsp+98h+lpString2], rax; lpString2
0x1800282ca  call    cs:__imp_CompareStringW
0x1800282d0  cmp     eax, 2
0x1800282d3  jnz     short loc_1800282EE
0x1800282d5  movsxd  rdx, dword ptr [rbx+10h]; cchDest
0x1800282d9  mov     r8, rsi; pszSrc
0x1800282dc  mov     rcx, [rbx+8]; pszDest
0x1800282e0  xor     edi, edi
0x1800282e2  call    StringCchCopyW
0x1800282e7  not     eax
0x1800282e9  shr     eax, 1Fh
0x1800282ec  mov     [rbx], eax
0x1800282ee  mov     rcx, [rsp+98h+hKey]; hKey
0x1800282f3  call    cs:__imp_RegCloseKey
0x1800282f9  mov     eax, edi
0x1800282fb  mov     rcx, [rsp+98h+var_18]
0x180028303  xor     rcx, rsp; StackCookie
0x180028306  call    __security_check_cookie
0x18002830b  lea     r11, [rsp+98h+var_8]
0x180028313  mov     rbx, [r11+20h]
0x180028317  mov     rsi, [r11+28h]
0x18002831b  mov     rsp, r11
0x18002831e  pop     rdi
0x18002831f  retn
```
