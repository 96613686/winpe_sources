# CUmRdpPrn::DeleteSerialLink(uchar *,ushort *,ushort *)

- ea: `0x180006480`
- end: `0x1800065c9`
- name: `?DeleteSerialLink@CUmRdpPrn@@QEAAHPEAEPEAG1@Z`
- size: `329`
- prototype: `__int64 __fastcall(CUmRdpPrn *__hidden this, LPCCH lpMultiByteStr, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010848`
- `0x1800117a0`

## callees

- `0x180006480`
- `0x180014d04`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006537`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006594`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006594`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180006506`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180006506`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000657f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000657f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000656b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000656b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000658a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000658a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800064cd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800064cd`
- `ntdll!NtQueryInformationProcess` at `0x1800064ef`
- `ntdll!NtQueryInformationProcess` at `0x1800064ef`

## string_xrefs

- `0x18000655d`: `HARDWARE\DEVICEMAP\SERIALCOMM`

## pseudocode

```c
_BOOL8 __fastcall CUmRdpPrn::DeleteSerialLink(
        HANDLE *this,
        LPCCH lpMultiByteStr,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  BOOL v5; // ebx
  int ProcessInformation; // [rsp+30h] [rbp-38h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-30h] BYREF
  WCHAR WideCharStr[8]; // [rsp+40h] [rbp-28h] BYREF

  ProcessInformation = 0;
  WideCharStr[0] = 0;
  v5 = 0;
  MultiByteToWideChar(0, 0, lpMultiByteStr, -1, WideCharStr, 8);
  if ( NtQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessLUIDDeviceMapsEnabled, &ProcessInformation, 4u, 0) < 0
    || !ProcessInformation
    || (v5 = ImpersonateLoggedOnUser(this[23])) )
  {
    if ( WideCharStr[0] && !CUmRdpPrn::DeleteSymLink((CUmRdpPrn *)this, WideCharStr) )
      GetLastError();
    if ( fRunningOnPTS )
    {
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"HARDWARE\\DEVICEMAP\\SERIALCOMM", 0, 0xF003Fu, &phkResult) )
      {
        RegDeleteValueW(phkResult, WideCharStr);
        RegCloseKey(phkResult);
      }
    }
    return !v5 || RevertToSelf();
  }
  else
  {
    GetLastError();
    return 0;
  }
}

```

## disassembly

```asm
0x180006480  mov     [rsp+arg_10], rbx
0x180006485  mov     [rsp+arg_18], rsi
0x18000648a  push    rdi
0x18000648b  sub     rsp, 60h
0x18000648f  mov     rax, cs:__security_cookie
0x180006496  xor     rax, rsp
0x180006499  mov     [rsp+68h+var_18], rax
0x18000649e  xor     esi, esi
0x1800064a0  mov     [rsp+68h+cchWideChar], 8; cchWideChar
0x1800064a8  mov     rdi, rcx
0x1800064ab  mov     [rsp+68h+ProcessInformation], esi
0x1800064af  lea     rax, [rsp+68h+WideCharStr]
0x1800064b4  mov     [rsp+68h+WideCharStr], si
0x1800064b9  mov     r8, rdx; lpMultiByteStr
0x1800064bc  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x1800064c1  xor     edx, edx; dwFlags
0x1800064c3  xor     ecx, ecx; CodePage
0x1800064c5  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1800064cb  mov     ebx, esi
0x1800064cd  call    cs:__imp_MultiByteToWideChar
0x1800064d3  mov     r9d, 4; ProcessInformationLength
0x1800064d9  mov     [rsp+68h+lpWideCharStr], rsi; ReturnLength
0x1800064de  lea     r8, [rsp+68h+ProcessInformation]; ProcessInformation
0x1800064e3  mov     edx, 1Ch; ProcessInformationClass
0x1800064e8  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800064ef  call    cs:__imp_NtQueryInformationProcess
0x1800064f5  test    eax, eax
0x1800064f7  js      short loc_18000651F
0x1800064f9  cmp     [rsp+68h+ProcessInformation], ebx
0x1800064fd  jz      short loc_18000651F
0x1800064ff  mov     rcx, [rdi+0B8h]; hToken
0x180006506  call    cs:__imp_ImpersonateLoggedOnUser
0x18000650c  mov     ebx, eax
0x18000650e  test    eax, eax
0x180006510  jnz     short loc_18000651F
0x180006512  call    cs:__imp_GetLastError
0x180006518  xor     eax, eax
0x18000651a  jmp     loc_1800065AA
0x18000651f  cmp     [rsp+68h+WideCharStr], si
0x180006524  jz      short loc_18000653D
0x180006526  lea     rdx, [rsp+68h+WideCharStr]; unsigned __int16 *
0x18000652b  mov     rcx, rdi; this
0x18000652e  call    ?DeleteSymLink@CUmRdpPrn@@AEAAHPEBG@Z; CUmRdpPrn::DeleteSymLink(ushort const *)
0x180006533  test    eax, eax
0x180006535  jnz     short loc_18000653D
0x180006537  call    cs:__imp_GetLastError
0x18000653d  cmp     cs:?fRunningOnPTS@@3HA, esi; int fRunningOnPTS
0x180006543  jz      short loc_180006590
0x180006545  lea     rax, [rsp+68h+phkResult]
0x18000654a  mov     [rsp+68h+phkResult], rsi
0x18000654f  mov     r9d, 0F003Fh; samDesired
0x180006555  mov     [rsp+68h+lpWideCharStr], rax; phkResult
0x18000655a  xor     r8d, r8d; ulOptions
0x18000655d  lea     rdx, SubKey; "HARDWARE\\DEVICEMAP\\SERIALCOMM"
0x180006564  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000656b  call    cs:__imp_RegOpenKeyExW
0x180006571  test    eax, eax
0x180006573  jnz     short loc_180006590
0x180006575  mov     rcx, [rsp+68h+phkResult]; hKey
0x18000657a  lea     rdx, [rsp+68h+WideCharStr]; lpValueName
0x18000657f  call    cs:__imp_RegDeleteValueW
0x180006585  mov     rcx, [rsp+68h+phkResult]; hKey
0x18000658a  call    cs:__imp_RegCloseKey
0x180006590  test    ebx, ebx
0x180006592  jz      short loc_1800065A5
0x180006594  call    cs:__imp_RevertToSelf
0x18000659a  test    eax, eax
0x18000659c  mov     ecx, esi
0x18000659e  setnz   cl
0x1800065a1  mov     eax, ecx
0x1800065a3  jmp     short loc_1800065AA
0x1800065a5  mov     eax, 1
0x1800065aa  mov     rcx, [rsp+68h+var_18]
0x1800065af  xor     rcx, rsp; StackCookie
0x1800065b2  call    __security_check_cookie
0x1800065b7  lea     r11, [rsp+68h+var_8]
0x1800065bc  mov     rbx, [r11+20h]
0x1800065c0  mov     rsi, [r11+28h]
0x1800065c4  mov     rsp, r11
0x1800065c7  pop     rdi
0x1800065c8  retn
```
