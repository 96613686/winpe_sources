# OsEventsPublish6005

- ea: `0x1800c2410`
- end: `0x1800c2520`
- name: `OsEventsPublish6005`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18005e4e4`

## callees

- `0x1800771dc`
- `0x18009aee0`
- `0x1800c2410`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1800c2457`
- `ntdll!NtQuerySystemInformation` at `0x1800c2457`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c2490`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c2490`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800c24c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800c24c3`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x1800c24d6`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x1800c24d6`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800c24b7`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800c24b7`

## pseudocode

```c
PVOID *OsEventsPublish6005()
{
  NTSTATUS v0; // eax
  int v1; // ebx
  __int64 v2; // r8
  size_t v4; // [rsp+30h] [rbp-19h]
  FILETIME FileTime; // [rsp+40h] [rbp-9h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-1h] BYREF
  __int64 v7; // [rsp+58h] [rbp+Fh] BYREF
  _OWORD SystemInformation[3]; // [rsp+60h] [rbp+17h] BYREF

  memset(SystemInformation, 0, sizeof(SystemInformation));
  v7 = 0;
  SystemTime = 0;
  v0 = NtQuerySystemInformation(SystemTimeOfDayInformation, SystemInformation, 0x30u, 0);
  v1 = v0;
  if ( qword_180111DC8 && v0 >= 0 )
    RegSetValueExW(qword_180111DC8, L"6005BT", 0, 3u, (const BYTE *)SystemInformation, 8u);
  if ( dword_18010F6B4 )
  {
    if ( v1 >= 0 )
    {
      FileTime = *(FILETIME *)&SystemInformation[0];
      FileTimeToSystemTime(&FileTime, &SystemTime);
    }
  }
  else
  {
    GetSystemTime(&SystemTime);
  }
  LODWORD(v7) = dword_18010F6B4;
  GetOsSafeBootMode((char *)&v7 + 4);
  LODWORD(v4) = 24;
  return LogElfEvent(0x80001775, 4, v2, 0, 0, &SystemTime, v4);
}

```

## disassembly

```asm
0x1800c2410  mov     [rsp-8+arg_0], rbx
0x1800c2415  push    rbp
0x1800c2416  lea     rbp, [rsp-57h]
0x1800c241b  sub     rsp, 0A0h
0x1800c2422  mov     rax, cs:__security_cookie
0x1800c2429  xor     rax, rsp
0x1800c242c  mov     [rbp+57h+var_10], rax
0x1800c2430  xorps   xmm0, xmm0
0x1800c2433  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x1800c2437  xor     eax, eax
0x1800c2439  xor     r9d, r9d; ReturnLength
0x1800c243c  movups  [rbp+57h+SystemInformation], xmm0
0x1800c2440  mov     [rbp+57h+var_48], rax
0x1800c2444  movups  [rbp+57h+var_30], xmm0
0x1800c2448  lea     r8d, [rax+30h]; SystemInformationLength
0x1800c244c  lea     ecx, [rax+3]; SystemInformationClass
0x1800c244f  movups  [rbp+57h+var_20], xmm0
0x1800c2453  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800c2457  call    cs:__imp_NtQuerySystemInformation
0x1800c245d  mov     rcx, cs:qword_180111DC8; hKey
0x1800c2464  mov     ebx, eax
0x1800c2466  test    rcx, rcx
0x1800c2469  jz      short loc_1800C2496
0x1800c246b  test    eax, eax
0x1800c246d  js      short loc_1800C2496
0x1800c246f  lea     rax, [rbp+57h+SystemInformation]
0x1800c2473  mov     [rsp+0A0h+cbData], 8; cbData
0x1800c247b  mov     r9d, 3; dwType
0x1800c2481  mov     [rsp+0A0h+lpData], rax; lpData
0x1800c2486  xor     r8d, r8d; Reserved
0x1800c2489  lea     rdx, a6005bt; "6005BT"
0x1800c2490  call    cs:__imp_RegSetValueExW
0x1800c2496  cmp     cs:dword_18010F6B4, 0
0x1800c249d  jz      short loc_1800C24BF
0x1800c249f  test    ebx, ebx
0x1800c24a1  js      short loc_1800C24C9
0x1800c24a3  mov     eax, dword ptr [rbp+57h+SystemInformation+4]
0x1800c24a6  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x1800c24aa  mov     [rbp+57h+FileTime.dwHighDateTime], eax
0x1800c24ad  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x1800c24b1  mov     eax, dword ptr [rbp+57h+SystemInformation]
0x1800c24b4  mov     [rbp+57h+FileTime.dwLowDateTime], eax
0x1800c24b7  call    cs:__imp_FileTimeToSystemTime
0x1800c24bd  jmp     short loc_1800C24C9
0x1800c24bf  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800c24c3  call    cs:__imp_GetSystemTime
0x1800c24c9  mov     eax, cs:dword_18010F6B4
0x1800c24cf  lea     rcx, [rbp+57h+var_48+4]
0x1800c24d3  mov     dword ptr [rbp+57h+var_48], eax
0x1800c24d6  call    cs:__imp_GetOsSafeBootMode
0x1800c24dc  xor     r9d, r9d; int
0x1800c24df  mov     dword ptr [rsp+0A0h+var_70], 18h; size_t
0x1800c24e7  lea     rax, [rbp+57h+SystemTime]
0x1800c24eb  mov     ecx, 80001775h; int
0x1800c24f0  mov     qword ptr [rsp+0A0h+cbData], rax; Src
0x1800c24f5  mov     [rsp+0A0h+lpData], r9; __int64
0x1800c24fa  lea     edx, [r9+4]; int
0x1800c24fe  call    LogElfEvent
0x1800c2503  mov     rcx, [rbp+57h+var_10]
0x1800c2507  xor     rcx, rsp; StackCookie
0x1800c250a  call    __security_check_cookie
0x1800c250f  mov     rbx, [rsp+0A0h+arg_0]
0x1800c2517  add     rsp, 0A0h
0x1800c251e  pop     rbp
0x1800c251f  retn
```
