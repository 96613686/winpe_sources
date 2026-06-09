# SetExtraTzInformation(uint,EXTRATZINFO const *)

- ea: `0x18000f70c`
- end: `0x18000f8d9`
- name: `?SetExtraTzInformation@@YAHIPEBUEXTRATZINFO@@@Z`
- size: `461`
- prototype: `int(unsigned int, const struct EXTRATZINFO *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800100c4`

## callees

- `0x180006dd8`
- `0x180008a0c`
- `0x1800092c4`
- `0x18000f67c`
- `0x18000f6a8`
- `0x18000f70c`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f89b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f89b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f79d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f79d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f7d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f7d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f86b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f86b`

## pseudocode

```c
__int64 __fastcall SetExtraTzInformation(unsigned int a1, const struct EXTRATZINFO *a2)
{
  unsigned int v2; // ebx
  unsigned int v4; // eax
  unsigned int v5; // r8d
  int v6; // eax
  const unsigned __int16 *v7; // rdx
  bool v8; // sf
  __int64 v9; // rdx
  const unsigned __int16 *v10; // rdx
  unsigned int v11; // r8d
  unsigned int dwOptions; // [rsp+20h] [rbp-258h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-258h]
  int dwOptionsb; // [rsp+20h] [rbp-258h]
  HKEY hKey; // [rsp+50h] [rbp-228h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-220h] BYREF
  WCHAR SubKey[256]; // [rsp+60h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v2 = 0;
  if ( a1 - 1 > 1 || !a2 )
  {
    SetLastError(0x57u);
    wil::details::in1diag3::Log_Win32(retaddr, (void *)0xE2, v11, (const char *)0x57, dwOptions);
    return v2;
  }
  if ( StringCchPrintfW(SubKey, 0x100u, L"Control Panel\\TimeDate\\AdditionalClocks\\%u", a1) < 0 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"shell\\cpls\\utc\\etzstorage.cpp",
      (const char *)0x80004005LL,
      dwOptions);
    return v2;
  }
  hKey = 0;
  v4 = RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v4 )
  {
    wil::details::in1diag3::Log_Win32(retaddr, (void *)0xD5, v5, (const char *)v4, dwOptionsa);
    goto LABEL_16;
  }
  *(_DWORD *)Data = *((_DWORD *)a2 + 8) != 0;
  v6 = RegSetValueExW(hKey, L"Enable", 0, 4u, Data, 4u);
  v8 = v6 < 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    v8 = v6 < 0;
  }
  if ( v8 )
  {
    v9 = 197;
  }
  else
  {
    v6 = SHRegSetString(hKey, v7, L"DisplayName", (const unsigned __int16 *)a2);
    if ( v6 >= 0 )
    {
      v6 = SHRegSetString(hKey, v10, L"TzRegKeyName", (const unsigned __int16 *)a2 + 18);
      if ( v6 >= 0 )
      {
        v2 = 1;
        goto LABEL_16;
      }
      v9 = 208;
    }
    else
    {
      v9 = 202;
    }
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"shell\\cpls\\utc\\etzstorage.cpp",
    (const char *)(unsigned int)v6,
    dwOptionsb);
LABEL_16:
  RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x18000f70c  mov     [rsp+arg_10], rbx
0x18000f711  push    rdi
0x18000f712  sub     rsp, 270h
0x18000f719  mov     rax, cs:__security_cookie
0x18000f720  xor     rax, rsp
0x18000f723  mov     [rsp+278h+var_18], rax
0x18000f72b  xor     ebx, ebx
0x18000f72d  lea     eax, [rcx-1]
0x18000f730  mov     rdi, rdx
0x18000f733  cmp     eax, 1
0x18000f736  ja      loc_18000F894
0x18000f73c  test    rdx, rdx
0x18000f73f  jz      loc_18000F894
0x18000f745  mov     r9d, ecx
0x18000f748  lea     r8, aControlPanelTi; "Control Panel\\TimeDate\\AdditionalCloc"...
0x18000f74f  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x18000f754  mov     edx, 100h; unsigned __int64
0x18000f759  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f75e  test    eax, eax
0x18000f760  js      loc_18000F873
0x18000f766  mov     [rsp+278h+lpdwDisposition], rbx; lpdwDisposition
0x18000f76b  lea     rax, [rsp+278h+hKey]
0x18000f770  mov     [rsp+278h+phkResult], rax; phkResult
0x18000f775  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x18000f77a  mov     [rsp+278h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18000f77f  xor     r9d, r9d; lpClass
0x18000f782  mov     [rsp+278h+samDesired], 20006h; samDesired
0x18000f78a  xor     r8d, r8d; Reserved
0x18000f78d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000f794  mov     [rsp+278h+dwOptions], ebx; unsigned int
0x18000f798  mov     [rsp+278h+hKey], rbx
0x18000f79d  call    cs:__imp_RegCreateKeyExW
0x18000f7a3  test    eax, eax
0x18000f7a5  jnz     loc_18000F851
0x18000f7ab  cmp     [rdi+20h], eax
0x18000f7ae  lea     r9d, [rbx+4]; dwType
0x18000f7b2  mov     rcx, [rsp+278h+hKey]; hKey
0x18000f7b7  lea     rdx, ValueName; "Enable"
0x18000f7be  setnz   al
0x18000f7c1  mov     [rsp+278h+samDesired], r9d; cbData
0x18000f7c6  mov     dword ptr [rsp+278h+Data], eax
0x18000f7ca  xor     r8d, r8d; Reserved
0x18000f7cd  lea     rax, [rsp+278h+Data]
0x18000f7d2  mov     qword ptr [rsp+278h+dwOptions], rax; int
0x18000f7d7  call    cs:__imp_RegSetValueExW
0x18000f7dd  test    eax, eax
0x18000f7df  jle     short loc_18000F7EB
0x18000f7e1  movzx   eax, ax
0x18000f7e4  or      eax, 80070000h
0x18000f7e9  test    eax, eax
0x18000f7eb  jns     short loc_18000F7F4
0x18000f7ed  mov     edx, 0C5h
0x18000f7f2  jmp     short loc_18000F831
0x18000f7f4  mov     rcx, [rsp+278h+hKey]; HKEY
0x18000f7f9  lea     r8, aDisplayname; "DisplayName"
0x18000f800  mov     r9, rdi; unsigned __int16 *
0x18000f803  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18000f808  test    eax, eax
0x18000f80a  jns     short loc_18000F813
0x18000f80c  mov     edx, 0CAh
0x18000f811  jmp     short loc_18000F831
0x18000f813  mov     rcx, [rsp+278h+hKey]; HKEY
0x18000f818  lea     r9, [rdi+24h]; unsigned __int16 *
0x18000f81c  lea     r8, aTzregkeyname; "TzRegKeyName"
0x18000f823  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18000f828  test    eax, eax
0x18000f82a  jns     short loc_18000F84A
0x18000f82c  mov     edx, 0D0h; void *
0x18000f831  mov     rcx, [rsp+278h]; this
0x18000f839  lea     r8, aShellCplsUtcEt; "shell\\cpls\\utc\\etzstorage.cpp"
0x18000f840  mov     r9d, eax; char *
0x18000f843  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f848  jmp     short loc_18000F866
0x18000f84a  mov     ebx, 1
0x18000f84f  jmp     short loc_18000F866
0x18000f851  mov     rcx, [rsp+278h]; this
0x18000f859  mov     r9d, eax; char *
0x18000f85c  mov     edx, 0D5h; void *
0x18000f861  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000f866  mov     rcx, [rsp+278h+hKey]; hKey
0x18000f86b  call    cs:__imp_RegCloseKey
0x18000f871  jmp     short loc_18000F8B6
0x18000f873  mov     rcx, [rsp+278h]; this
0x18000f87b  lea     r8, aShellCplsUtcEt; "shell\\cpls\\utc\\etzstorage.cpp"
0x18000f882  mov     r9d, 80004005h; char *
0x18000f888  mov     edx, 0DCh; void *
0x18000f88d  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000f892  jmp     short loc_18000F8B6
0x18000f894  mov     edi, 57h ; 'W'
0x18000f899  mov     ecx, edi; dwErrCode
0x18000f89b  call    cs:__imp_SetLastError
0x18000f8a1  mov     rcx, [rsp+278h]; this
0x18000f8a9  mov     r9d, edi; char *
0x18000f8ac  mov     edx, 0E2h; void *
0x18000f8b1  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000f8b6  mov     eax, ebx
0x18000f8b8  mov     rcx, [rsp+278h+var_18]
0x18000f8c0  xor     rcx, rsp; StackCookie
0x18000f8c3  call    __security_check_cookie
0x18000f8c8  mov     rbx, [rsp+278h+arg_10]
0x18000f8d0  add     rsp, 270h
0x18000f8d7  pop     rdi
0x18000f8d8  retn
```
