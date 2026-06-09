# OpenReadyBoostPerfData

- ea: `0x180063a70`
- end: `0x180063b6d`
- name: `OpenReadyBoostPerfData`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x1800382e0`
- `0x180063a70`
- `0x180064b20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063a96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063a96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063b4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063b4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063b5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063b5f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063acb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063acb`

## string_xrefs

- `0x180063abd`: `SYSTEM\CurrentControlSet\Services\rdyboost\Performance`

## pseudocode

```c
__int64 OpenReadyBoostPerfData()
{
  unsigned int Value; // ebx
  unsigned int v2; // [rsp+48h] [rbp+10h] BYREF
  unsigned int v3; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v3 = 0;
  v2 = 0;
  hKey = 0;
  EnterCriticalSection(&SmPcGlobals);
  if ( dword_1800D3FE8 )
    goto LABEL_6;
  Value = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Services\\rdyboost\\Performance",
            0,
            0x20019u,
            &hKey);
  if ( !Value )
  {
    Value = PfsRegQueryValue((_DWORD)hKey, (unsigned int)L"First Counter", 4, 4, (__int64)&v3);
    if ( !Value )
    {
      Value = PfsRegQueryValue((_DWORD)hKey, (unsigned int)L"First Help", 4, 4, (__int64)&v2);
      if ( !Value )
      {
        SmPcObjectInitialize(qword_1800D3FF0, v3, v2);
        dword_1800D3FE8 = 1;
LABEL_6:
        Value = 0;
      }
    }
  }
  LeaveCriticalSection(&SmPcGlobals);
  if ( hKey )
    RegCloseKey(hKey);
  return Value;
}

```

## disassembly

```asm
0x180063a70  push    rbx
0x180063a72  sub     rsp, 30h
0x180063a76  lea     rcx, SmPcGlobals; lpCriticalSection
0x180063a7d  mov     [rsp+38h+arg_10], 0
0x180063a85  mov     [rsp+38h+arg_8], 0
0x180063a8d  mov     [rsp+38h+hKey], 0
0x180063a96  call    cs:__imp_EnterCriticalSection
0x180063a9c  mov     eax, cs:dword_1800D3FE8
0x180063aa2  test    eax, eax
0x180063aa4  jnz     loc_180063B46
0x180063aaa  lea     rax, [rsp+38h+hKey]
0x180063aaf  mov     r9d, 20019h; samDesired
0x180063ab5  xor     r8d, r8d; ulOptions
0x180063ab8  mov     [rsp+38h+phkResult], rax; phkResult
0x180063abd  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\rd"...
0x180063ac4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180063acb  call    cs:__imp_RegOpenKeyExW
0x180063ad1  mov     ebx, eax
0x180063ad3  test    eax, eax
0x180063ad5  jnz     short loc_180063B48
0x180063ad7  mov     rcx, [rsp+38h+hKey]
0x180063adc  lea     r9d, [rbx+4]
0x180063ae0  lea     rax, [rsp+38h+arg_10]
0x180063ae5  mov     r8d, r9d
0x180063ae8  lea     rdx, aFirstCounter; "First Counter"
0x180063aef  mov     [rsp+38h+phkResult], rax
0x180063af4  call    PfsRegQueryValue
0x180063af9  mov     ebx, eax
0x180063afb  test    eax, eax
0x180063afd  jnz     short loc_180063B48
0x180063aff  mov     rcx, [rsp+38h+hKey]
0x180063b04  lea     r9d, [rbx+4]
0x180063b08  lea     rax, [rsp+38h+arg_8]
0x180063b0d  mov     r8d, r9d
0x180063b10  lea     rdx, aFirstHelp; "First Help"
0x180063b17  mov     [rsp+38h+phkResult], rax
0x180063b1c  call    PfsRegQueryValue
0x180063b21  mov     ebx, eax
0x180063b23  test    eax, eax
0x180063b25  jnz     short loc_180063B48
0x180063b27  mov     r8d, [rsp+38h+arg_8]
0x180063b2c  lea     rcx, qword_1800D3FF0
0x180063b33  mov     edx, [rsp+38h+arg_10]
0x180063b37  call    SmPcObjectInitialize
0x180063b3c  mov     cs:dword_1800D3FE8, 1
0x180063b46  xor     ebx, ebx
0x180063b48  lea     rcx, SmPcGlobals; lpCriticalSection
0x180063b4f  call    cs:__imp_LeaveCriticalSection
0x180063b55  mov     rcx, [rsp+38h+hKey]; hKey
0x180063b5a  test    rcx, rcx
0x180063b5d  jz      short loc_180063B65
0x180063b5f  call    cs:__imp_RegCloseKey
0x180063b65  mov     eax, ebx
0x180063b67  add     rsp, 30h
0x180063b6b  pop     rbx
0x180063b6c  retn
```
