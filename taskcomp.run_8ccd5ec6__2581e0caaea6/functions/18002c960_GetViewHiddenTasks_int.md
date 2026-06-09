# GetViewHiddenTasks(int *)

- ea: `0x18002c960`
- end: `0x18002ca02`
- name: `?GetViewHiddenTasks@@YAJPEAH@Z`
- size: `162`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ca08`

## callees

- `0x18002c960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c9ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c9ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c9dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c9dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c99c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c99c`

## string_xrefs

- `0x18002c98e`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x18002c9c4`: `ViewHiddenTasks`

## pseudocode

```c
__int64 __fastcall GetViewHiddenTasks(int *a1)
{
  int *cbData; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  cbData = a1;
  *(_DWORD *)&g_fViewHiddenTasks = 0;
  hKey = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SchedulingAgent", 0, 0x20019u, &hKey);
  if ( hKey )
  {
    LODWORD(cbData) = 4;
    RegQueryValueExW(hKey, L"ViewHiddenTasks", 0, 0, &g_fViewHiddenTasks, (LPDWORD)&cbData);
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x18002c960  mov     r11, rsp
0x18002c963  mov     [r11+8], rcx
0x18002c967  sub     rsp, 38h
0x18002c96b  lea     rax, [r11+10h]
0x18002c96f  mov     cs:?g_fViewHiddenTasks@@3HA, 0; int g_fViewHiddenTasks
0x18002c979  mov     r9d, 20019h; samDesired
0x18002c97f  mov     [r11-18h], rax
0x18002c983  xor     r8d, r8d; ulOptions
0x18002c986  mov     qword ptr [r11+10h], 0
0x18002c98e  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x18002c995  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c99c  call    cs:__imp_RegOpenKeyExW
0x18002c9a3  nop     dword ptr [rax+rax+00h]
0x18002c9a8  mov     rcx, [rsp+38h+hKey]; hKey
0x18002c9ad  test    rcx, rcx
0x18002c9b0  jz      short loc_18002C9FA
0x18002c9b2  lea     rax, [rsp+38h+cbData]
0x18002c9b7  mov     dword ptr [rsp+38h+cbData], 4
0x18002c9bf  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002c9c4  lea     rdx, aViewhiddentask; "ViewHiddenTasks"
0x18002c9cb  lea     rax, ?g_fViewHiddenTasks@@3HA; int g_fViewHiddenTasks
0x18002c9d2  xor     r9d, r9d; lpType
0x18002c9d5  xor     r8d, r8d; lpReserved
0x18002c9d8  mov     [rsp+38h+lpData], rax; lpData
0x18002c9dd  call    cs:__imp_RegQueryValueExW
0x18002c9e4  nop     dword ptr [rax+rax+00h]
0x18002c9e9  mov     rcx, [rsp+38h+hKey]; hKey
0x18002c9ee  call    cs:__imp_RegCloseKey
0x18002c9f5  nop     dword ptr [rax+rax+00h]
0x18002c9fa  xor     eax, eax
0x18002c9fc  add     rsp, 38h
0x18002ca00  retn
```
