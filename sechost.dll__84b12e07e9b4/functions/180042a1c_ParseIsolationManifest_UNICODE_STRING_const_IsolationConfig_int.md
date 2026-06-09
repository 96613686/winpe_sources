# ParseIsolationManifest(_UNICODE_STRING const *,IsolationConfig *,int *)

- ea: `0x180042a1c`
- end: `0x180042b15`
- name: `?ParseIsolationManifest@@YAJPEBU_UNICODE_STRING@@PEAVIsolationConfig@@PEAH@Z`
- size: `249`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, struct IsolationConfig *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180014b70`
- `0x180042ca0`

## callees

- `0x180016a88`
- `0x1800426a0`
- `0x180042990`
- `0x180042a1c`
- `0x180042b1c`
- `0x180042ec8`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042ab4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042abe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042ac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042ab4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042abe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042ac8`

## pseudocode

```c
__int64 __fastcall ParseIsolationManifest(const struct _UNICODE_STRING *a1, struct IsolationConfig *a2, int *a3)
{
  __int64 v5; // rdx
  bool v6; // zf
  int PredefinedIsolationManifest; // ebx
  int v8; // r8d
  __int64 v9; // rdx
  unsigned __int16 v11[8]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v12; // [rsp+30h] [rbp-40h]
  __int64 v13; // [rsp+38h] [rbp-38h]
  WCHAR v14[8]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v15; // [rsp+50h] [rbp-20h]

  v13 = 7;
  v12 = 0;
  v11[0] = 0;
  UnicodeStringToWstring(v14, a1);
  v6 = v15 == 0;
  *a3 = 0;
  if ( v6 )
    goto LABEL_10;
  PredefinedIsolationManifest = LoadPredefinedIsolationManifest((__int64)v14, (__int64)v11, a3);
  if ( PredefinedIsolationManifest >= 0 )
  {
    if ( *a3
      || (PredefinedIsolationManifest = ExtractIsolationManifestFromImage(v14, (__int64)v11, a3),
          PredefinedIsolationManifest >= 0)
      && *a3 )
    {
      if ( !(unsigned int)ParseIsolationConfig(v11, a2, v8) )
      {
        if ( (int)GetLastError() > 0 )
          PredefinedIsolationManifest = (unsigned __int16)GetLastError() | 0xC0070000;
        else
          PredefinedIsolationManifest = GetLastError();
        goto LABEL_11;
      }
LABEL_10:
      PredefinedIsolationManifest = 0;
    }
  }
LABEL_11:
  LOBYTE(v5) = 1;
  std::wstring::_Tidy(v14, v5, 0);
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(v11, v9, 0);
  return (unsigned int)PredefinedIsolationManifest;
}

```

## disassembly

```asm
0x180042a1c  mov     [rsp-18h+arg_18], rbx
0x180042a21  push    rbp
0x180042a22  push    rsi
0x180042a23  push    rdi
0x180042a24  mov     rbp, rsp
0x180042a27  sub     rsp, 70h
0x180042a2b  mov     rax, cs:__security_cookie
0x180042a32  xor     rax, rsp
0x180042a35  mov     [rbp+var_10], rax
0x180042a39  mov     rsi, rdx
0x180042a3c  mov     [rbp+var_38], 7
0x180042a44  mov     rdx, rcx
0x180042a47  mov     [rbp+var_40], 0
0x180042a4f  xor     eax, eax
0x180042a51  lea     rcx, [rbp+var_30]
0x180042a55  mov     rdi, r8
0x180042a58  mov     [rbp+var_50], ax
0x180042a5c  call    ?UnicodeStringToWstring@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_UNICODE_STRING@@@Z; UnicodeStringToWstring(_UNICODE_STRING const *)
0x180042a61  cmp     [rbp+var_20], 0
0x180042a66  mov     dword ptr [rdi], 0
0x180042a6c  jz      short loc_180042AD9
0x180042a6e  mov     r8, rdi
0x180042a71  lea     rdx, [rbp+var_50]
0x180042a75  lea     rcx, [rbp+var_30]
0x180042a79  call    ?LoadPredefinedIsolationManifest@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@PEAH@Z; LoadPredefinedIsolationManifest(std::wstring const &,std::wstring &,int *)
0x180042a7e  mov     ebx, eax
0x180042a80  test    eax, eax
0x180042a82  js      short loc_180042ADB
0x180042a84  cmp     dword ptr [rdi], 0
0x180042a87  jnz     short loc_180042AA4
0x180042a89  mov     r8, rdi
0x180042a8c  lea     rdx, [rbp+var_50]
0x180042a90  lea     rcx, [rbp+var_30]
0x180042a94  call    ?ExtractIsolationManifestFromImage@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@PEAH@Z; ExtractIsolationManifestFromImage(std::wstring const &,std::wstring &,int *)
0x180042a99  mov     ebx, eax
0x180042a9b  test    eax, eax
0x180042a9d  js      short loc_180042ADB
0x180042a9f  cmp     dword ptr [rdi], 0
0x180042aa2  jz      short loc_180042ADB
0x180042aa4  mov     rdx, rsi
0x180042aa7  lea     rcx, [rbp+var_50]; unsigned __int16 *
0x180042aab  call    ?ParseIsolationConfig@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVIsolationConfig@@@Z; ParseIsolationConfig(std::wstring const &,IsolationConfig *)
0x180042ab0  test    eax, eax
0x180042ab2  jnz     short loc_180042AD9
0x180042ab4  call    cs:__imp_GetLastError
0x180042aba  test    eax, eax
0x180042abc  jg      short loc_180042AC8
0x180042abe  call    cs:__imp_GetLastError
0x180042ac4  mov     ebx, eax
0x180042ac6  jmp     short loc_180042ADB
0x180042ac8  call    cs:__imp_GetLastError
0x180042ace  movzx   ebx, ax
0x180042ad1  or      ebx, 0C0070000h
0x180042ad7  jmp     short loc_180042ADB
0x180042ad9  xor     ebx, ebx
0x180042adb  xor     r8d, r8d
0x180042ade  lea     rcx, [rbp+var_30]
0x180042ae2  mov     dl, 1
0x180042ae4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180042ae9  xor     r8d, r8d
0x180042aec  lea     rcx, [rbp+var_50]
0x180042af0  mov     dl, 1
0x180042af2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180042af7  mov     eax, ebx
0x180042af9  mov     rcx, [rbp+var_10]
0x180042afd  xor     rcx, rsp; StackCookie
0x180042b00  call    __security_check_cookie
0x180042b05  mov     rbx, [rsp+70h+arg_18]
0x180042b0d  add     rsp, 70h
0x180042b11  pop     rdi
0x180042b12  pop     rsi
0x180042b13  pop     rbp
0x180042b14  retn
```
