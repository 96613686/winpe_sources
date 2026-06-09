# LoadMpClientHelper(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &)

- ea: `0x18002b438`
- end: `0x18002b5ec`
- name: `?LoadMpClientHelper@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180040550`

## callees

- `0x18002b438`
- `0x18002b5f4`
- `0x18004deb0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18002b519`
- `msvcrt!wcscat_s` at `0x18002b551`
- `msvcrt!wcscat_s` at `0x18002b583`
- `msvcrt!wcscat_s` at `0x18002b519`
- `msvcrt!wcscat_s` at `0x18002b551`
- `msvcrt!wcscat_s` at `0x18002b583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002b480`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002b480`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18002b4fe`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18002b56a`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18002b4fe`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18002b56a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002b599`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002b599`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b4d9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b4d9`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18002b493`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18002b493`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18002b52f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18002b52f`

## string_xrefs

- `0x18002b4b5`: `InstallLocation`
- `0x18002b539`: `X86\MpClient.dll`
- `0x18002b542`: `MpClient.dll`
- `0x18002b574`: `\Windows Defender\MpClient.dll`

## pseudocode

```c
signed int __fastcall LoadMpClientHelper(_QWORD *a1)
{
  bool v1; // bl
  HANDLE CurrentProcess; // rax
  const wchar_t *v4; // r8
  signed int result; // eax
  HMODULE LibraryW; // rax
  _WORD v7[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v8; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String1[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+260h] [rbp+160h] BYREF

  pcbData = 520;
  v7[0] = 0;
  v1 = 0;
  v8 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (unsigned int)IsWow64Process2(CurrentProcess, v7, &v8) )
    v1 = v7[0] != 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows Defender",
          L"InstallLocation",
          0x10002u,
          0,
          String1,
          &pcbData) )
  {
    if ( !v1 )
    {
      v4 = L"MpClient.dll";
LABEL_10:
      if ( !wcscat_s(String1, 0x104u, v4) )
        goto LABEL_14;
      goto LABEL_11;
    }
    if ( !GetEnvironmentVariableW(L"ProgramW6432", Buffer, 0x104u)
      || wcscat_s(Buffer, 0x104u, L"\\Windows Defender\\")
      || lstrcmpW(String1, Buffer) )
    {
      v4 = L"X86\\MpClient.dll";
      goto LABEL_10;
    }
  }
LABEL_11:
  if ( !GetEnvironmentVariableW(L"ProgramFiles", String1, 0x104u) )
    goto LABEL_16;
  if ( wcscat_s(String1, 0x104u, L"\\Windows Defender\\MpClient.dll") )
    return -2147024846;
LABEL_14:
  LibraryW = LoadLibraryW(String1);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    a1,
    LibraryW);
  if ( *a1 )
    return 0;
LABEL_16:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002b438  mov     [rsp-8+arg_8], rbx
0x18002b43d  mov     [rsp-8+arg_10], rsi
0x18002b442  push    rbp
0x18002b443  push    rdi
0x18002b444  push    r14
0x18002b446  lea     rbp, [rsp-380h]
0x18002b44e  sub     rsp, 480h
0x18002b455  mov     rax, cs:__security_cookie
0x18002b45c  xor     rax, rsp
0x18002b45f  mov     [rbp+390h+var_20], rax
0x18002b466  xor     esi, esi
0x18002b468  mov     [rsp+490h+var_448], 208h
0x18002b470  mov     [rsp+490h+var_450], si
0x18002b475  mov     bl, sil
0x18002b478  mov     [rsp+490h+var_44C], si
0x18002b47d  mov     rdi, rcx
0x18002b480  call    cs:__imp_GetCurrentProcess
0x18002b486  mov     rcx, rax
0x18002b489  lea     r8, [rsp+490h+var_44C]
0x18002b48e  lea     rdx, [rsp+490h+var_450]
0x18002b493  call    cs:__imp_IsWow64Process2
0x18002b499  test    eax, eax
0x18002b49b  jz      short loc_18002B4A5
0x18002b49d  cmp     [rsp+490h+var_450], si
0x18002b4a2  setnz   bl
0x18002b4a5  lea     rax, [rsp+490h+var_448]
0x18002b4aa  mov     r9d, 10002h; dwFlags
0x18002b4b0  mov     [rsp+490h+pcbData], rax; pcbData
0x18002b4b5  lea     r8, aInstalllocatio; "InstallLocation"
0x18002b4bc  lea     rax, [rsp+490h+String1]
0x18002b4c1  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002b4c8  mov     [rsp+490h+pvData], rax; pvData
0x18002b4cd  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows Defender"
0x18002b4d4  mov     [rsp+490h+pdwType], rsi; pdwType
0x18002b4d9  call    cs:__imp_RegGetValueW
0x18002b4df  mov     r14d, 104h
0x18002b4e5  test    eax, eax
0x18002b4e7  jnz     short loc_18002B55B
0x18002b4e9  test    bl, bl
0x18002b4eb  jz      short loc_18002B542
0x18002b4ed  mov     r8d, r14d; nSize
0x18002b4f0  lea     rdx, [rbp+390h+Buffer]; lpBuffer
0x18002b4f7  lea     rcx, aProgramw6432; "ProgramW6432"
0x18002b4fe  call    cs:__imp_GetEnvironmentVariableW
0x18002b504  test    eax, eax
0x18002b506  jz      short loc_18002B539
0x18002b508  lea     r8, aWindowsDefende; "\\Windows Defender\\"
0x18002b50f  mov     edx, r14d; SizeInWords
0x18002b512  lea     rcx, [rbp+390h+Buffer]; Destination
0x18002b519  call    cs:__imp_wcscat_s
0x18002b51f  test    eax, eax
0x18002b521  jnz     short loc_18002B539
0x18002b523  lea     rdx, [rbp+390h+Buffer]; lpString2
0x18002b52a  lea     rcx, [rsp+490h+String1]; lpString1
0x18002b52f  call    cs:__imp_lstrcmpW
0x18002b535  test    eax, eax
0x18002b537  jz      short loc_18002B55B
0x18002b539  lea     r8, aX86MpclientDll; "X86\\MpClient.dll"
0x18002b540  jmp     short loc_18002B549
0x18002b542  lea     r8, aMpclientDll; "MpClient.dll"
0x18002b549  mov     rdx, r14; SizeInWords
0x18002b54c  lea     rcx, [rsp+490h+String1]; Destination
0x18002b551  call    cs:__imp_wcscat_s
0x18002b557  test    eax, eax
0x18002b559  jz      short loc_18002B594
0x18002b55b  mov     r8d, r14d; nSize
0x18002b55e  lea     rdx, [rsp+490h+String1]; lpBuffer
0x18002b563  lea     rcx, aProgramfiles; "ProgramFiles"
0x18002b56a  call    cs:__imp_GetEnvironmentVariableW
0x18002b570  test    eax, eax
0x18002b572  jz      short loc_18002B5B3
0x18002b574  lea     r8, aWindowsDefende_0; "\\Windows Defender\\MpClient.dll"
0x18002b57b  mov     rdx, r14; SizeInWords
0x18002b57e  lea     rcx, [rsp+490h+String1]; Destination
0x18002b583  call    cs:__imp_wcscat_s
0x18002b589  test    eax, eax
0x18002b58b  jz      short loc_18002B594
0x18002b58d  mov     eax, 80070032h
0x18002b592  jmp     short loc_18002B5C5
0x18002b594  lea     rcx, [rsp+490h+String1]; lpLibFileName
0x18002b599  call    cs:__imp_LoadLibraryW
0x18002b59f  mov     rdx, rax
0x18002b5a2  mov     rcx, rdi
0x18002b5a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18002b5aa  cmp     [rdi], rsi
0x18002b5ad  jz      short loc_18002B5B3
0x18002b5af  mov     eax, esi
0x18002b5b1  jmp     short loc_18002B5C5
0x18002b5b3  call    cs:__imp_GetLastError
0x18002b5b9  test    eax, eax
0x18002b5bb  jle     short loc_18002B5C5
0x18002b5bd  movzx   eax, ax
0x18002b5c0  or      eax, 80070000h
0x18002b5c5  mov     rcx, [rbp+390h+var_20]
0x18002b5cc  xor     rcx, rsp; StackCookie
0x18002b5cf  call    __security_check_cookie
0x18002b5d4  lea     r11, [rsp+490h+var_10]
0x18002b5dc  mov     rbx, [r11+28h]
0x18002b5e0  mov     rsi, [r11+30h]
0x18002b5e4  mov     rsp, r11
0x18002b5e7  pop     r14
0x18002b5e9  pop     rdi
0x18002b5ea  pop     rbp
0x18002b5eb  retn
```
