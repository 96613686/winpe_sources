# UmpoSetActiveScheme

- ea: `0x180001980`
- end: `0x180001ad7`
- name: `UmpoSetActiveScheme`
- size: `343`
- prototype: `__int64 __fastcall(_QWORD *, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002530`

## callees

- `0x180001980`
- `0x180003370`
- `0x180003560`
- `0x18000f3dc`
- `0x180010070`
- `0x180012864`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180001a81`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180001a81`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180001a96`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180001a96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001a3a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001a3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001ab3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001ab3`

## pseudocode

```c
__int64 __fastcall UmpoSetActiveScheme(_QWORD *a1, char a2)
{
  __int64 v2; // rbx
  unsigned int v5; // ebx
  HKEY v7; // rdi
  HKEY hKey; // [rsp+30h] [rbp-49h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-41h] BYREF
  WCHAR SubKey[40]; // [rsp+40h] [rbp-39h] BYREF

  v2 = -1;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( !UmpoFullPowerPlanSupportDisabled
    || *a1 == *(_QWORD *)&GUID_TYPICAL_POWER_SAVINGS.Data1 && a1[1] == *(_QWORD *)GUID_TYPICAL_POWER_SAVINGS.Data4 )
  {
    if ( UmpoInternalOpenUserPowerKey(&hKey, 131079, 0) )
      return 259;
    v7 = hKey;
    if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v7 = hKey;
    }
    UmpoInternalConvertGuidToStringBuffer((__int64)a1, SubKey);
    if ( RegOpenKeyExW(v7, SubKey, 0, 0x20019u, &phkResult) )
    {
      v5 = 87;
    }
    else
    {
      do
        ++v2;
      while ( SubKey[v2] );
      v5 = RegSetValueExW(hKey, L"ActivePowerScheme", 0, 1u, (const BYTE *)SubKey, 2 * v2 + 2);
      if ( !v5 && a2 )
        RegFlushKey(hKey);
    }
  }
  else
  {
    v5 = 50;
  }
  UmpoInternalCloseUserPowerKey(hKey);
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  return v5;
}

```

## disassembly

```asm
0x180001980  push    rbp
0x180001982  push    rbx
0x180001983  push    rsi
0x180001984  push    rdi
0x180001985  push    r14
0x180001987  push    r15
0x180001989  lea     rbp, [rsp-2Fh]
0x18000198e  sub     rsp, 0A8h
0x180001995  mov     rax, cs:__security_cookie
0x18000199c  xor     rax, rsp
0x18000199f  mov     [rbp+57h+var_40], rax
0x1800019a3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800019a7  xor     r15d, r15d
0x1800019aa  cmp     cs:UmpoFullPowerPlanSupportDisabled, r15b
0x1800019b1  mov     r14b, dl
0x1800019b4  mov     rsi, rcx
0x1800019b7  mov     [rbp+57h+var_98], rbx
0x1800019bb  mov     [rbp+57h+hKey], rbx
0x1800019bf  jz      short loc_1800019E4
0x1800019c1  mov     rax, [rcx]
0x1800019c4  cmp     rax, qword ptr cs:GUID_TYPICAL_POWER_SAVINGS.Data1
0x1800019cb  jnz     short loc_1800019DA
0x1800019cd  mov     rax, [rcx+8]
0x1800019d1  cmp     rax, qword ptr cs:GUID_TYPICAL_POWER_SAVINGS.Data4
0x1800019d8  jz      short loc_1800019E4
0x1800019da  mov     ebx, 32h ; '2'
0x1800019df  jmp     loc_180001A9C
0x1800019e4  xor     r8d, r8d
0x1800019e7  lea     rcx, [rbp+57h+hKey]; phkResult
0x1800019eb  mov     edx, 20007h; samDesired
0x1800019f0  call    UmpoInternalOpenUserPowerKey
0x1800019f5  test    eax, eax
0x1800019f7  jz      short loc_180001A03
0x1800019f9  mov     eax, 103h
0x1800019fe  jmp     loc_180001ABB
0x180001a03  mov     rdi, [rbp+57h+hKey]
0x180001a07  cmp     rdi, rbx
0x180001a0a  jnz     short loc_180001A15
0x180001a0c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180001a11  mov     rdi, [rbp+57h+hKey]
0x180001a15  lea     rdx, [rbp+57h+SubKey]
0x180001a19  mov     rcx, rsi
0x180001a1c  call    UmpoInternalConvertGuidToStringBuffer
0x180001a21  lea     rdx, [rbp+57h+var_98]
0x180001a25  mov     r9d, 20019h; samDesired
0x180001a2b  mov     [rsp+0D0h+phkResult], rdx; phkResult
0x180001a30  xor     r8d, r8d; ulOptions
0x180001a33  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180001a37  mov     rcx, rdi; hKey
0x180001a3a  call    cs:__imp_RegOpenKeyExW
0x180001a40  test    eax, eax
0x180001a42  jz      short loc_180001A4B
0x180001a44  mov     ebx, 57h ; 'W'
0x180001a49  jmp     short loc_180001A9C
0x180001a4b  lea     rax, [rbp+57h+SubKey]
0x180001a4f  inc     rbx
0x180001a52  cmp     [rax+rbx*2], r15w
0x180001a57  jnz     short loc_180001A4F
0x180001a59  mov     rcx, [rbp+57h+hKey]; hKey
0x180001a5d  lea     eax, ds:2[rbx*2]
0x180001a64  mov     [rsp+0D0h+cbData], eax; cbData
0x180001a68  lea     rdx, ValueName; "ActivePowerScheme"
0x180001a6f  lea     rax, [rbp+57h+SubKey]
0x180001a73  mov     r9d, 1; dwType
0x180001a79  xor     r8d, r8d; Reserved
0x180001a7c  mov     [rsp+0D0h+phkResult], rax; lpData
0x180001a81  call    cs:__imp_RegSetValueExW
0x180001a87  mov     ebx, eax
0x180001a89  test    eax, eax
0x180001a8b  jnz     short loc_180001A9C
0x180001a8d  test    r14b, r14b
0x180001a90  jz      short loc_180001A9C
0x180001a92  mov     rcx, [rbp+57h+hKey]; hKey
0x180001a96  call    cs:__imp_RegFlushKey
0x180001a9c  mov     rcx, [rbp+57h+hKey]
0x180001aa0  call    UmpoInternalCloseUserPowerKey
0x180001aa5  mov     rcx, [rbp+57h+var_98]; hKey
0x180001aa9  lea     rdx, [rcx-1]
0x180001aad  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180001ab1  ja      short loc_180001AB9
0x180001ab3  call    cs:__imp_RegCloseKey
0x180001ab9  mov     eax, ebx
0x180001abb  mov     rcx, [rbp+57h+var_40]
0x180001abf  xor     rcx, rsp; StackCookie
0x180001ac2  call    __security_check_cookie
0x180001ac7  add     rsp, 0A8h
0x180001ace  pop     r15
0x180001ad0  pop     r14
0x180001ad2  pop     rdi
0x180001ad3  pop     rsi
0x180001ad4  pop     rbx
0x180001ad5  pop     rbp
0x180001ad6  retn
```
