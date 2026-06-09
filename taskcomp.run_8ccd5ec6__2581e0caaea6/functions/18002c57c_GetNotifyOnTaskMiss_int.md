# GetNotifyOnTaskMiss(int *)

- ea: `0x18002c57c`
- end: `0x18002c61e`
- name: `?GetNotifyOnTaskMiss@@YAJPEAH@Z`
- size: `162`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ca08`

## callees

- `0x18002c57c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c60a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c60a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c5f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c5f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c5b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c5b8`

## string_xrefs

- `0x18002c5aa`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x18002c5e0`: `NotifyOnTaskMiss`

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
0x18002c57c  mov     r11, rsp
0x18002c57f  mov     [r11+8], rcx
0x18002c583  sub     rsp, 38h
0x18002c587  lea     rax, [r11+10h]
0x18002c58b  mov     cs:?g_fNotifyMiss@@3HA, 0; int g_fNotifyMiss
0x18002c595  mov     r9d, 20019h; samDesired
0x18002c59b  mov     [r11-18h], rax
0x18002c59f  xor     r8d, r8d; ulOptions
0x18002c5a2  mov     qword ptr [r11+10h], 0
0x18002c5aa  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x18002c5b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c5b8  call    cs:__imp_RegOpenKeyExW
0x18002c5bf  nop     dword ptr [rax+rax+00h]
0x18002c5c4  mov     rcx, [rsp+38h+hKey]; hKey
0x18002c5c9  test    rcx, rcx
0x18002c5cc  jz      short loc_18002C616
0x18002c5ce  lea     rax, [rsp+38h+cbData]
0x18002c5d3  mov     dword ptr [rsp+38h+cbData], 4
0x18002c5db  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002c5e0  lea     rdx, aNotifyontaskmi; "NotifyOnTaskMiss"
0x18002c5e7  lea     rax, ?g_fNotifyMiss@@3HA; int g_fNotifyMiss
0x18002c5ee  xor     r9d, r9d; lpType
0x18002c5f1  xor     r8d, r8d; lpReserved
0x18002c5f4  mov     [rsp+38h+lpData], rax; lpData
0x18002c5f9  call    cs:__imp_RegQueryValueExW
0x18002c600  nop     dword ptr [rax+rax+00h]
0x18002c605  mov     rcx, [rsp+38h+hKey]; hKey
0x18002c60a  call    cs:__imp_RegCloseKey
0x18002c611  nop     dword ptr [rax+rax+00h]
0x18002c616  xor     eax, eax
0x18002c618  add     rsp, 38h
0x18002c61c  retn
```
