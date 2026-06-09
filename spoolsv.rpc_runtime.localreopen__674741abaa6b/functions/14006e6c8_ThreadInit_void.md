# ThreadInit(void)

- ea: `0x14006e6c8`
- end: `0x14006e830`
- name: `?ThreadInit@@YAHXZ`
- size: `360`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14006e138`

## callees

- `0x14006e6c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14006e6f5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14006e6f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006e754`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006e754`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006e78f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006e7c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006e803`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006e78f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006e7c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006e803`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006e813`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006e813`

## string_xrefs

- `0x14006e7c2`: `ThreadNotifyIdleLife`
- `0x14006e781`: `ThreadNotifyMax`
- `0x14006e7fc`: `ThreadNotifySleep`

## pseudocode

```c
__int64 ThreadInit(void)
{
  __int64 result; // rax
  DWORD cbData; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF

  hKey = 0;
  Type = 4;
  cbData = 0;
  result = (__int64)CreateEventW(0, 0, 0, 0);
  qword_1400D2ABC = 0;
  hObject = (HANDLE)result;
  dword_1400D2AB8 = 0;
  tmStateVar = &tmStateStatic;
  if ( result )
  {
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Print", 0, 0x20019u, &hKey) )
    {
      cbData = 4;
      RegQueryValueExW(hKey, L"ThreadNotifyMax", 0, &Type, &tmStateStatic, &cbData);
      cbData = 4;
      RegQueryValueExW(hKey, L"ThreadNotifyIdleLife", 0, &Type, &Data, &cbData);
      cbData = 4;
      RegQueryValueExW(hKey, L"ThreadNotifySleep", 0, &Type, &dwThreadNotifySleep, &cbData);
      RegCloseKey(hKey);
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x14006e6c8  mov     [rsp-8+arg_18], rsi
0x14006e6cd  push    rbp
0x14006e6ce  mov     rbp, rsp
0x14006e6d1  sub     rsp, 30h
0x14006e6d5  xor     r9d, r9d; lpName
0x14006e6d8  mov     [rbp+hKey], 0
0x14006e6e0  xor     r8d, r8d; bInitialState
0x14006e6e3  mov     [rbp+Type], 4
0x14006e6ea  xor     edx, edx; bManualReset
0x14006e6ec  mov     [rbp+cbData], 0
0x14006e6f3  xor     ecx, ecx; lpEventAttributes
0x14006e6f5  call    cs:__imp_CreateEventW
0x14006e6fc  nop     dword ptr [rax+rax+00h]
0x14006e701  lea     rsi, ?tmStateStatic@@3U_TMSTATESTATIC@@A; _TMSTATESTATIC tmStateStatic
0x14006e708  mov     cs:qword_1400D2ABC, 0
0x14006e713  mov     cs:hObject, rax
0x14006e71a  mov     cs:dword_1400D2AB8, 0
0x14006e724  mov     cs:?tmStateVar@@3U_TMSTATEVAR@@A, rsi; _TMSTATEVAR tmStateVar
0x14006e72b  test    rax, rax
0x14006e72e  jz      loc_14006E824
0x14006e734  lea     rax, [rbp+hKey]
0x14006e738  mov     r9d, 20019h; samDesired
0x14006e73e  xor     r8d, r8d; ulOptions
0x14006e741  mov     [rsp+30h+phkResult], rax; phkResult
0x14006e746  lea     rdx, szPrintKey; "System\\CurrentControlSet\\Control\\Pri"...
0x14006e74d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14006e754  call    cs:__imp_RegOpenKeyExW
0x14006e75b  nop     dword ptr [rax+rax+00h]
0x14006e760  test    eax, eax
0x14006e762  jnz     loc_14006E81F
0x14006e768  mov     rcx, [rbp+hKey]; hKey
0x14006e76c  lea     rax, [rbp+cbData]
0x14006e770  mov     [rsp+30h+lpcbData], rax; lpcbData
0x14006e775  lea     r9, [rbp+Type]; lpType
0x14006e779  xor     r8d, r8d; lpReserved
0x14006e77c  mov     [rsp+30h+phkResult], rsi; lpData
0x14006e781  lea     rdx, szThreadMax; "ThreadNotifyMax"
0x14006e788  mov     [rbp+cbData], 4
0x14006e78f  call    cs:__imp_RegQueryValueExW
0x14006e796  nop     dword ptr [rax+rax+00h]
0x14006e79b  mov     rcx, [rbp+hKey]; hKey
0x14006e79f  lea     rax, [rbp+cbData]
0x14006e7a3  mov     [rsp+30h+lpcbData], rax; lpcbData
0x14006e7a8  lea     r9, [rbp+Type]; lpType
0x14006e7ac  lea     rax, Data
0x14006e7b3  mov     [rbp+cbData], 4
0x14006e7ba  xor     r8d, r8d; lpReserved
0x14006e7bd  mov     [rsp+30h+phkResult], rax; lpData
0x14006e7c2  lea     rdx, szThreadIdleLife; "ThreadNotifyIdleLife"
0x14006e7c9  call    cs:__imp_RegQueryValueExW
0x14006e7d0  nop     dword ptr [rax+rax+00h]
0x14006e7d5  mov     rcx, [rbp+hKey]; hKey
0x14006e7d9  lea     rax, [rbp+cbData]
0x14006e7dd  mov     [rsp+30h+lpcbData], rax; lpcbData
0x14006e7e2  lea     r9, [rbp+Type]; lpType
0x14006e7e6  lea     rax, ?dwThreadNotifySleep@@3KA; ulong dwThreadNotifySleep
0x14006e7ed  mov     [rbp+cbData], 4
0x14006e7f4  xor     r8d, r8d; lpReserved
0x14006e7f7  mov     [rsp+30h+phkResult], rax; lpData
0x14006e7fc  lea     rdx, szThreadNotifySleep; "ThreadNotifySleep"
0x14006e803  call    cs:__imp_RegQueryValueExW
0x14006e80a  nop     dword ptr [rax+rax+00h]
0x14006e80f  mov     rcx, [rbp+hKey]; hKey
0x14006e813  call    cs:__imp_RegCloseKey
0x14006e81a  nop     dword ptr [rax+rax+00h]
0x14006e81f  mov     eax, 1
0x14006e824  mov     rsi, [rsp+30h+arg_18]
0x14006e829  add     rsp, 30h
0x14006e82d  pop     rbp
0x14006e82e  retn
```
