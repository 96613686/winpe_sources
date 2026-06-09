# ServerInstallUpdateStatus

- ea: `0x18000a9e0`
- end: `0x18000ab93`
- name: `ServerInstallUpdateStatus`
- size: `435`
- prototype: `LSTATUS()`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008d20`
- `0x180009d70`
- `0x18000a3a0`
- `0x18000a6b0`
- `0x18000aba0`
- `0x180012dac`

## callees

- `0x18000a9e0`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ab33`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ab72`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ab33`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ab72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab88`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000aaec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000aaec`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000aaa9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000aaa9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aa4a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aa4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000ab06`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000ab06`

## string_xrefs

- `0x18000aa15`: `Software\Microsoft\Windows\CurrentVersion\Device Installer`

## pseudocode

```c
LSTATUS ServerInstallUpdateStatus()
{
  int v0; // edi
  int v1; // ebx
  LSTATUS result; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-48h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-40h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-28h] BYREF

  v0 = ServerInstallBatchTotal;
  v1 = ServerInstallBatchComplete;
  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  *(_QWORD *)Data = 0;
  SystemTime = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Device Installer",
             0,
             0x2000000u,
             &hKey);
  if ( !result )
  {
    if ( v1 || v0 )
    {
      result = RegCreateKeyExW(hKey, L"CurrentStatus", 0, 0, 1u, 2u, 0, &phkResult, &dwDisposition);
      if ( !result )
      {
        if ( dwDisposition == 1 )
        {
          GetSystemTime(&SystemTime);
          RegSetValueExW(phkResult, L"StartTime", 0, 3u, (const BYTE *)&SystemTime, 0x10u);
        }
        *(_DWORD *)&Data[4] = v0;
        *(_DWORD *)Data = v1;
        result = RegSetValueExW(phkResult, L"Progress", 0, 0xBu, Data, 8u);
      }
    }
    else
    {
      result = RegDeleteTreeW(hKey, L"CurrentStatus");
    }
  }
  if ( phkResult )
    result = RegCloseKey(phkResult);
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x18000a9e0  mov     r11, rsp
0x18000a9e3  mov     [r11+8], rbx
0x18000a9e7  mov     [r11+10h], rsi
0x18000a9eb  push    rdi
0x18000a9ec  sub     rsp, 90h
0x18000a9f3  mov     rax, cs:__security_cookie
0x18000a9fa  xor     rax, rsp
0x18000a9fd  mov     [rsp+98h+var_18], rax
0x18000aa05  mov     edi, cs:ServerInstallBatchTotal
0x18000aa0b  lea     rax, [r11-30h]
0x18000aa0f  mov     ebx, cs:ServerInstallBatchComplete
0x18000aa15  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000aa1c  xor     esi, esi
0x18000aa1e  mov     [r11-78h], rax
0x18000aa22  xorps   xmm0, xmm0
0x18000aa25  mov     [rsp+98h+dwDisposition], esi
0x18000aa29  mov     r9d, 2000000h; samDesired
0x18000aa2f  mov     [r11-30h], rsi
0x18000aa33  xor     r8d, r8d; ulOptions
0x18000aa36  mov     [r11-38h], rsi
0x18000aa3a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000aa41  mov     [r11-40h], rsi
0x18000aa45  movups  xmmword ptr [rsp+98h+SystemTime.wYear], xmm0
0x18000aa4a  call    cs:__imp_RegOpenKeyExW
0x18000aa50  test    eax, eax
0x18000aa52  jz      short loc_18000AA95
0x18000aa54  mov     rcx, [rsp+98h+var_38]; hKey
0x18000aa59  test    rcx, rcx
0x18000aa5c  jnz     loc_18000AB7D
0x18000aa62  mov     rcx, [rsp+98h+hKey]; hKey
0x18000aa67  test    rcx, rcx
0x18000aa6a  jnz     loc_18000AB88
0x18000aa70  mov     rcx, [rsp+98h+var_18]
0x18000aa78  xor     rcx, rsp; StackCookie
0x18000aa7b  call    __security_check_cookie
0x18000aa80  lea     r11, [rsp+98h+var_8]
0x18000aa88  mov     rbx, [r11+10h]
0x18000aa8c  mov     rsi, [r11+18h]
0x18000aa90  mov     rsp, r11
0x18000aa93  pop     rdi
0x18000aa94  retn
0x18000aa95  test    ebx, ebx
0x18000aa97  jnz     short loc_18000AAB1
0x18000aa99  test    edi, edi
0x18000aa9b  jnz     short loc_18000AAB1
0x18000aa9d  mov     rcx, [rsp+98h+hKey]; hKey
0x18000aaa2  lea     rdx, aCurrentstatus; "CurrentStatus"
0x18000aaa9  call    cs:__imp_RegDeleteTreeW
0x18000aaaf  jmp     short loc_18000AA54
0x18000aab1  mov     rcx, [rsp+98h+hKey]; hKey
0x18000aab6  lea     rax, [rsp+98h+dwDisposition]
0x18000aabb  mov     [rsp+98h+lpdwDisposition], rax; lpdwDisposition
0x18000aac0  lea     rdx, aCurrentstatus; "CurrentStatus"
0x18000aac7  lea     rax, [rsp+98h+var_38]
0x18000aacc  xor     r9d, r9d; lpClass
0x18000aacf  mov     [rsp+98h+phkResult], rax; phkResult
0x18000aad4  xor     r8d, r8d; Reserved
0x18000aad7  mov     [rsp+98h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000aadc  mov     [rsp+98h+samDesired], 2; samDesired
0x18000aae4  mov     [rsp+98h+dwOptions], 1; dwOptions
0x18000aaec  call    cs:__imp_RegCreateKeyExW
0x18000aaf2  test    eax, eax
0x18000aaf4  jnz     loc_18000AA54
0x18000aafa  cmp     [rsp+98h+dwDisposition], 1
0x18000aaff  jnz     short loc_18000AB39
0x18000ab01  lea     rcx, [rsp+98h+SystemTime]; lpSystemTime
0x18000ab06  call    cs:__imp_GetSystemTime
0x18000ab0c  mov     rcx, [rsp+98h+var_38]; hKey
0x18000ab11  lea     rax, [rsp+98h+SystemTime]
0x18000ab16  mov     [rsp+98h+samDesired], 10h; cbData
0x18000ab1e  lea     rdx, ValueName; "StartTime"
0x18000ab25  mov     r9d, 3; dwType
0x18000ab2b  mov     qword ptr [rsp+98h+dwOptions], rax; lpData
0x18000ab30  xor     r8d, r8d; Reserved
0x18000ab33  call    cs:__imp_RegSetValueExW
0x18000ab39  mov     rcx, [rsp+98h+var_38]; hKey
0x18000ab3e  lea     rdx, aProgress; "Progress"
0x18000ab45  mov     dword ptr [rsp+98h+Data+4], edi
0x18000ab49  mov     r9d, 0Bh; dwType
0x18000ab4f  mov     dword ptr [rsp+98h+Data], ebx
0x18000ab53  xor     r8d, r8d; Reserved
0x18000ab56  mov     rax, qword ptr [rsp+98h+Data]
0x18000ab5b  mov     qword ptr [rsp+98h+Data], rax
0x18000ab60  lea     rax, [rsp+98h+Data]
0x18000ab65  mov     [rsp+98h+samDesired], 8; cbData
0x18000ab6d  mov     qword ptr [rsp+98h+dwOptions], rax; lpData
0x18000ab72  call    cs:__imp_RegSetValueExW
0x18000ab78  jmp     loc_18000AA54
0x18000ab7d  call    cs:__imp_RegCloseKey
0x18000ab83  jmp     loc_18000AA62
0x18000ab88  call    cs:__imp_RegCloseKey
0x18000ab8e  jmp     loc_18000AA70
```
