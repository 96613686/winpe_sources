# ThreadInit(void)

- ea: `0x140067f10`
- end: `0x140068053`
- name: `?ThreadInit@@YAHXZ`
- size: `323`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400679f4`

## callees

- `0x140067f10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140067f3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140067f3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140067f96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140067f96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140067fcb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140067fff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140068033`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140067fcb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140067fff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140068033`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006803d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006803d`

## string_xrefs

- `0x140067ff8`: `ThreadNotifyIdleLife`
- `0x140067fbd`: `ThreadNotifyMax`
- `0x14006802c`: `ThreadNotifySleep`

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
  qword_1400CB94C = 0;
  hObject = (HANDLE)result;
  dword_1400CB948 = 0;
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
0x140067f10  mov     [rsp-8+arg_18], rsi
0x140067f15  push    rbp
0x140067f16  mov     rbp, rsp
0x140067f19  sub     rsp, 30h
0x140067f1d  xor     r9d, r9d; lpName
0x140067f20  mov     [rbp+hKey], 0
0x140067f28  xor     r8d, r8d; bInitialState
0x140067f2b  mov     [rbp+Type], 4
0x140067f32  xor     edx, edx; bManualReset
0x140067f34  mov     [rbp+cbData], 0
0x140067f3b  xor     ecx, ecx; lpEventAttributes
0x140067f3d  call    cs:__imp_CreateEventW
0x140067f43  lea     rsi, ?tmStateStatic@@3U_TMSTATESTATIC@@A; _TMSTATESTATIC tmStateStatic
0x140067f4a  mov     cs:qword_1400CB94C, 0
0x140067f55  mov     cs:hObject, rax
0x140067f5c  mov     cs:dword_1400CB948, 0
0x140067f66  mov     cs:?tmStateVar@@3U_TMSTATEVAR@@A, rsi; _TMSTATEVAR tmStateVar
0x140067f6d  test    rax, rax
0x140067f70  jz      loc_140068048
0x140067f76  lea     rax, [rbp+hKey]
0x140067f7a  mov     r9d, 20019h; samDesired
0x140067f80  xor     r8d, r8d; ulOptions
0x140067f83  mov     [rsp+30h+phkResult], rax; phkResult
0x140067f88  lea     rdx, szPrintKey; "System\\CurrentControlSet\\Control\\Pri"...
0x140067f8f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140067f96  call    cs:__imp_RegOpenKeyExW
0x140067f9c  test    eax, eax
0x140067f9e  jnz     loc_140068043
0x140067fa4  mov     rcx, [rbp+hKey]; hKey
0x140067fa8  lea     rax, [rbp+cbData]
0x140067fac  mov     [rsp+30h+lpcbData], rax; lpcbData
0x140067fb1  lea     r9, [rbp+Type]; lpType
0x140067fb5  xor     r8d, r8d; lpReserved
0x140067fb8  mov     [rsp+30h+phkResult], rsi; lpData
0x140067fbd  lea     rdx, szThreadMax; "ThreadNotifyMax"
0x140067fc4  mov     [rbp+cbData], 4
0x140067fcb  call    cs:__imp_RegQueryValueExW
0x140067fd1  mov     rcx, [rbp+hKey]; hKey
0x140067fd5  lea     rax, [rbp+cbData]
0x140067fd9  mov     [rsp+30h+lpcbData], rax; lpcbData
0x140067fde  lea     r9, [rbp+Type]; lpType
0x140067fe2  lea     rax, Data
0x140067fe9  mov     [rbp+cbData], 4
0x140067ff0  xor     r8d, r8d; lpReserved
0x140067ff3  mov     [rsp+30h+phkResult], rax; lpData
0x140067ff8  lea     rdx, szThreadIdleLife; "ThreadNotifyIdleLife"
0x140067fff  call    cs:__imp_RegQueryValueExW
0x140068005  mov     rcx, [rbp+hKey]; hKey
0x140068009  lea     rax, [rbp+cbData]
0x14006800d  mov     [rsp+30h+lpcbData], rax; lpcbData
0x140068012  lea     r9, [rbp+Type]; lpType
0x140068016  lea     rax, ?dwThreadNotifySleep@@3KA; ulong dwThreadNotifySleep
0x14006801d  mov     [rbp+cbData], 4
0x140068024  xor     r8d, r8d; lpReserved
0x140068027  mov     [rsp+30h+phkResult], rax; lpData
0x14006802c  lea     rdx, szThreadNotifySleep; "ThreadNotifySleep"
0x140068033  call    cs:__imp_RegQueryValueExW
0x140068039  mov     rcx, [rbp+hKey]; hKey
0x14006803d  call    cs:__imp_RegCloseKey
0x140068043  mov     eax, 1
0x140068048  mov     rsi, [rsp+30h+arg_18]
0x14006804d  add     rsp, 30h
0x140068051  pop     rbp
0x140068052  retn
```
