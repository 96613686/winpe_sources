# GetViewHiddenTasks(int *)

- ea: `0x18002adcc`
- end: `0x18002ae5b`
- name: `?GetViewHiddenTasks@@YAJPEAH@Z`
- size: `143`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ae64`

## callees

- `0x18002adcc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ae4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ae4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ae43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ae43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ae08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ae08`

## string_xrefs

- `0x18002adfa`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x18002ae2a`: `ViewHiddenTasks`

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
0x18002adcc  mov     r11, rsp
0x18002adcf  mov     [r11+8], rcx
0x18002add3  sub     rsp, 38h
0x18002add7  lea     rax, [r11+10h]
0x18002addb  mov     cs:?g_fViewHiddenTasks@@3HA, 0; int g_fViewHiddenTasks
0x18002ade5  mov     r9d, 20019h; samDesired
0x18002adeb  mov     [r11-18h], rax
0x18002adef  xor     r8d, r8d; ulOptions
0x18002adf2  mov     qword ptr [r11+10h], 0
0x18002adfa  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x18002ae01  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ae08  call    cs:__imp_RegOpenKeyExW
0x18002ae0e  mov     rcx, [rsp+38h+hKey]; hKey
0x18002ae13  test    rcx, rcx
0x18002ae16  jz      short loc_18002AE54
0x18002ae18  lea     rax, [rsp+38h+cbData]
0x18002ae1d  mov     dword ptr [rsp+38h+cbData], 4
0x18002ae25  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002ae2a  lea     rdx, aViewhiddentask; "ViewHiddenTasks"
0x18002ae31  lea     rax, ?g_fViewHiddenTasks@@3HA; int g_fViewHiddenTasks
0x18002ae38  xor     r9d, r9d; lpType
0x18002ae3b  xor     r8d, r8d; lpReserved
0x18002ae3e  mov     [rsp+38h+lpData], rax; lpData
0x18002ae43  call    cs:__imp_RegQueryValueExW
0x18002ae49  mov     rcx, [rsp+38h+hKey]; hKey
0x18002ae4e  call    cs:__imp_RegCloseKey
0x18002ae54  xor     eax, eax
0x18002ae56  add     rsp, 38h
0x18002ae5a  retn
```
