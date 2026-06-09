# CreateRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x18000b574`
- end: `0x18000b6c9`
- name: `?CreateRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `341`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000adfc`
- `0x18000af74`

## callees

- `0x18000b574`
- `0x18000d1c0`
- `0x18000d250`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000b620`
- `KERNEL32!GetLastError` at `0x18000b620`
- `KERNEL32!WideCharToMultiByte` at `0x18000b613`
- `KERNEL32!WideCharToMultiByte` at `0x18000b673`
- `KERNEL32!WideCharToMultiByte` at `0x18000b613`
- `KERNEL32!WideCharToMultiByte` at `0x18000b673`
- `ADVAPI32!RegCreateKeyExW` at `0x18000b5cf`
- `ADVAPI32!RegCreateKeyExW` at `0x18000b5cf`
- `ADVAPI32!RegCreateKeyExA` at `0x18000b6a5`
- `ADVAPI32!RegCreateKeyExA` at `0x18000b6a5`

## pseudocode

```c
int __fastcall CreateRegSettings(HKEY a1, const unsigned __int16 *a2, REGSAM samDesired, HKEY *a4)
{
  int result; // eax
  bool v7; // cc
  int v8; // eax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  CHAR MultiByteStr[48]; // [rsp+50h] [rbp+0h] BYREF

  if ( Global::g_fWindowsNT )
  {
    result = RegCreateKeyExW(
               HKEY_CURRENT_USER,
               L"Software\\Microsoft\\Windows Script Host\\Settings",
               0,
               0,
               0,
               samDesired,
               0,
               a4,
               0);
  }
  else
  {
    v8 = WideCharToMultiByte(0, 0, L"Software\\Microsoft\\Windows Script Host\\Settings", -1, 0, 0, 0, 0);
    if ( !v8 )
      goto LABEL_7;
    v9 = v8 + 15LL;
    if ( v9 < v8 )
      v9 = 0xFFFFFFFFFFFFFF0LL;
    v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
    v11 = alloca(v10);
    v12 = alloca(v10);
    if ( !WideCharToMultiByte(0, 0, L"Software\\Microsoft\\Windows Script Host\\Settings", -1, MultiByteStr, v8, 0, 0) )
    {
LABEL_7:
      result = GetLastError();
      v7 = result <= 0;
      goto LABEL_4;
    }
    result = RegCreateKeyExA(HKEY_CURRENT_USER, MultiByteStr, 0, 0, 0, samDesired, 0, a4, 0);
  }
  v7 = result <= 0;
  if ( !result )
    return 0;
LABEL_4:
  if ( !v7 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000b574  mov     r11, rsp
0x18000b577  push    rbp
0x18000b578  push    rbx
0x18000b579  push    rsi
0x18000b57a  push    rdi
0x18000b57b  push    r14
0x18000b57d  sub     rsp, 60h
0x18000b581  lea     rbp, [rsp+50h]
0x18000b586  mov     rax, cs:__security_cookie
0x18000b58d  xor     rax, rbp
0x18000b590  mov     qword ptr [rbp+30h+MultiByteStr], rax
0x18000b594  xor     r14d, r14d
0x18000b597  mov     rbx, r9
0x18000b59a  cmp     cs:?g_fWindowsNT@Global@@2_NA, r14b; bool Global::g_fWindowsNT
0x18000b5a1  mov     edi, r8d
0x18000b5a4  jz      short loc_18000B5F0
0x18000b5a6  mov     [r11-48h], r14
0x18000b5aa  lea     rdx, WideCharStr; "Software\\Microsoft\\Windows Script Hos"...
0x18000b5b1  mov     [r11-50h], rbx
0x18000b5b5  xor     r9d, r9d; lpClass
0x18000b5b8  mov     [r11-58h], r14
0x18000b5bc  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000b5c3  mov     [rsp+80h+samDesired], r8d; samDesired
0x18000b5c8  xor     r8d, r8d; Reserved
0x18000b5cb  mov     [r11-68h], r14d
0x18000b5cf  call    cs:__imp_RegCreateKeyExW
0x18000b5d5  test    eax, eax
0x18000b5d7  jz      loc_18000B6B0
0x18000b5dd  jle     loc_18000B6B2
0x18000b5e3  movzx   eax, ax
0x18000b5e6  or      eax, 80070000h
0x18000b5eb  jmp     loc_18000B6B2
0x18000b5f0  mov     [rsp+80h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18000b5f5  lea     r8, WideCharStr; "Software\\Microsoft\\Windows Script Hos"...
0x18000b5fc  mov     [rsp+80h+lpDefaultChar], r14; lpDefaultChar
0x18000b601  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000b605  mov     [rsp+80h+samDesired], r14d; cbMultiByte
0x18000b60a  xor     edx, edx; dwFlags
0x18000b60c  xor     ecx, ecx; CodePage
0x18000b60e  mov     [rsp+80h+lpMultiByteStr], r14; lpMultiByteStr
0x18000b613  call    cs:__imp_WideCharToMultiByte
0x18000b619  movsxd  rdx, eax
0x18000b61c  test    eax, eax
0x18000b61e  jnz     short loc_18000B62A
0x18000b620  call    cs:__imp_GetLastError
0x18000b626  test    eax, eax
0x18000b628  jmp     short loc_18000B5DD
0x18000b62a  lea     rcx, [rdx+0Fh]
0x18000b62e  cmp     rcx, rdx
0x18000b631  ja      short loc_18000B63D
0x18000b633  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000b63d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000b641  mov     rax, rcx
0x18000b644  call    _alloca_probe
0x18000b649  sub     rsp, rcx
0x18000b64c  lea     r8, WideCharStr; "Software\\Microsoft\\Windows Script Hos"...
0x18000b653  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000b657  xor     ecx, ecx; CodePage
0x18000b659  mov     [rsp+80h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18000b65e  lea     rsi, [rsp+80h+MultiByteStr]
0x18000b663  mov     [rsp+80h+lpDefaultChar], r14; lpDefaultChar
0x18000b668  mov     [rsp+80h+samDesired], edx; cbMultiByte
0x18000b66c  xor     edx, edx; dwFlags
0x18000b66e  mov     [rsp+80h+lpMultiByteStr], rsi; lpMultiByteStr
0x18000b673  call    cs:__imp_WideCharToMultiByte
0x18000b679  test    eax, eax
0x18000b67b  jz      short loc_18000B620
0x18000b67d  mov     [rsp+80h+lpdwDisposition], r14; lpdwDisposition
0x18000b682  xor     r9d, r9d; lpClass
0x18000b685  mov     [rsp+80h+lpUsedDefaultChar], rbx; phkResult
0x18000b68a  xor     r8d, r8d; Reserved
0x18000b68d  mov     [rsp+80h+lpDefaultChar], r14; lpSecurityAttributes
0x18000b692  mov     rdx, rsi; lpSubKey
0x18000b695  mov     [rsp+80h+samDesired], edi; samDesired
0x18000b699  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000b6a0  mov     dword ptr [rsp+80h+lpMultiByteStr], r14d; dwOptions
0x18000b6a5  call    cs:__imp_RegCreateKeyExA
0x18000b6ab  jmp     loc_18000B5D5
0x18000b6b0  xor     eax, eax
0x18000b6b2  mov     rcx, qword ptr [rbp+30h+MultiByteStr]
0x18000b6b6  xor     rcx, rbp; StackCookie
0x18000b6b9  call    __security_check_cookie
0x18000b6be  lea     rsp, [rbp+10h]
0x18000b6c2  pop     r14
0x18000b6c4  pop     rdi
0x18000b6c5  pop     rsi
0x18000b6c6  pop     rbx
0x18000b6c7  pop     rbp
0x18000b6c8  retn
```
