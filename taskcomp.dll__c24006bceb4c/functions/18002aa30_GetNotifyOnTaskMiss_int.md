# GetNotifyOnTaskMiss(int *)

- ea: `0x18002aa30`
- end: `0x18002aabf`
- name: `?GetNotifyOnTaskMiss@@YAJPEAH@Z`
- size: `143`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ae64`

## callees

- `0x18002aa30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002aab2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002aab2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aaa7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aaa7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002aa6c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002aa6c`

## string_xrefs

- `0x18002aa5e`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x18002aa8e`: `NotifyOnTaskMiss`

## pseudocode

```c
__int64 __fastcall GetNotifyOnTaskMiss(int *a1)
{
  int *cbData; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  cbData = a1;
  *(_DWORD *)&g_fNotifyMiss = 0;
  hKey = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SchedulingAgent", 0, 0x20019u, &hKey);
  if ( hKey )
  {
    LODWORD(cbData) = 4;
    RegQueryValueExW(hKey, L"NotifyOnTaskMiss", 0, 0, &g_fNotifyMiss, (LPDWORD)&cbData);
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x18002aa30  mov     r11, rsp
0x18002aa33  mov     [r11+8], rcx
0x18002aa37  sub     rsp, 38h
0x18002aa3b  lea     rax, [r11+10h]
0x18002aa3f  mov     cs:?g_fNotifyMiss@@3HA, 0; int g_fNotifyMiss
0x18002aa49  mov     r9d, 20019h; samDesired
0x18002aa4f  mov     [r11-18h], rax
0x18002aa53  xor     r8d, r8d; ulOptions
0x18002aa56  mov     qword ptr [r11+10h], 0
0x18002aa5e  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x18002aa65  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002aa6c  call    cs:__imp_RegOpenKeyExW
0x18002aa72  mov     rcx, [rsp+38h+hKey]; hKey
0x18002aa77  test    rcx, rcx
0x18002aa7a  jz      short loc_18002AAB8
0x18002aa7c  lea     rax, [rsp+38h+cbData]
0x18002aa81  mov     dword ptr [rsp+38h+cbData], 4
0x18002aa89  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002aa8e  lea     rdx, aNotifyontaskmi; "NotifyOnTaskMiss"
0x18002aa95  lea     rax, ?g_fNotifyMiss@@3HA; int g_fNotifyMiss
0x18002aa9c  xor     r9d, r9d; lpType
0x18002aa9f  xor     r8d, r8d; lpReserved
0x18002aaa2  mov     [rsp+38h+lpData], rax; lpData
0x18002aaa7  call    cs:__imp_RegQueryValueExW
0x18002aaad  mov     rcx, [rsp+38h+hKey]; hKey
0x18002aab2  call    cs:__imp_RegCloseKey
0x18002aab8  xor     eax, eax
0x18002aaba  add     rsp, 38h
0x18002aabe  retn
```
