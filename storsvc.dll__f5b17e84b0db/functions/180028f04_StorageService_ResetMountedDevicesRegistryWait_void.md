# StorageService::ResetMountedDevicesRegistryWait(void)

- ea: `0x180028f04`
- end: `0x180028fd4`
- name: `?ResetMountedDevicesRegistryWait@StorageService@@QEAAJXZ`
- size: `208`
- prototype: `__int64 __fastcall(StorageService *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180025420`
- `0x180028010`

## callees

- `0x180028f04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028f74`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f86`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180028fc1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180028fc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028f47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028f47`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180028fa6`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180028fa6`

## string_xrefs

- `0x180028f39`: `System\MountedDevices`

## pseudocode

```c
signed int __fastcall StorageService::ResetMountedDevicesRegistryWait(StorageService *this)
{
  HKEY *v2; // rdi
  signed int result; // eax
  bool v4; // cc
  HANDLE EventW; // rax

  if ( *((_DWORD *)this + 425) == 1 )
    return 0;
  v2 = (HKEY *)((char *)this + 1776);
  if ( !*((_QWORD *)this + 222) )
  {
    result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\MountedDevices", 0, 0x20019u, (PHKEY)this + 222);
    v4 = result <= 0;
    if ( result )
      goto LABEL_4;
  }
  EventW = (HANDLE)*((_QWORD *)this + 223);
  if ( EventW == (HANDLE)-1LL )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 223) = EventW;
    if ( !EventW )
    {
      result = GetLastError();
      v4 = result <= 0;
      goto LABEL_4;
    }
  }
  result = RegNotifyChangeKeyValue(*v2, 0, 0x10000004u, EventW, 1);
  v4 = result <= 0;
  if ( !result )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 224), *((HANDLE *)this + 223), 0);
    return 0;
  }
LABEL_4:
  if ( !v4 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180028f04  mov     [rsp+arg_0], rbx
0x180028f09  push    rdi
0x180028f0a  sub     rsp, 30h
0x180028f0e  cmp     dword ptr [rcx+6A4h], 1
0x180028f15  mov     rbx, rcx
0x180028f18  jz      loc_180028FC7
0x180028f1e  lea     rdi, [rcx+6F0h]
0x180028f25  cmp     qword ptr [rdi], 0
0x180028f29  jnz     short loc_180028F5D
0x180028f2b  mov     r9d, 20019h; samDesired
0x180028f31  mov     [rsp+38h+phkResult], rdi; phkResult
0x180028f36  xor     r8d, r8d; ulOptions
0x180028f39  lea     rdx, aSystemMountedd; "System\\MountedDevices"
0x180028f40  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028f47  call    cs:__imp_RegOpenKeyExW
0x180028f4d  test    eax, eax
0x180028f4f  jz      short loc_180028F5D
0x180028f51  jle     short loc_180028FC9
0x180028f53  movzx   eax, ax
0x180028f56  or      eax, 80070000h
0x180028f5b  jmp     short loc_180028FC9
0x180028f5d  mov     rax, [rbx+6F8h]
0x180028f64  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028f68  jnz     short loc_180028F90
0x180028f6a  xor     r9d, r9d; lpName
0x180028f6d  xor     r8d, r8d; bInitialState
0x180028f70  xor     edx, edx; bManualReset
0x180028f72  xor     ecx, ecx; lpEventAttributes
0x180028f74  call    cs:__imp_CreateEventW
0x180028f7a  mov     [rbx+6F8h], rax
0x180028f81  test    rax, rax
0x180028f84  jnz     short loc_180028F90
0x180028f86  call    cs:__imp_GetLastError
0x180028f8c  test    eax, eax
0x180028f8e  jmp     short loc_180028F51
0x180028f90  mov     rcx, [rdi]; hKey
0x180028f93  mov     r9, rax; hEvent
0x180028f96  xor     edx, edx; bWatchSubtree
0x180028f98  mov     dword ptr [rsp+38h+phkResult], 1; fAsynchronous
0x180028fa0  mov     r8d, 10000004h; dwNotifyFilter
0x180028fa6  call    cs:__imp_RegNotifyChangeKeyValue
0x180028fac  test    eax, eax
0x180028fae  jnz     short loc_180028F51
0x180028fb0  mov     rdx, [rbx+6F8h]; h
0x180028fb7  xor     r8d, r8d; pftTimeout
0x180028fba  mov     rcx, [rbx+700h]; pwa
0x180028fc1  call    cs:__imp_SetThreadpoolWait
0x180028fc7  xor     eax, eax
0x180028fc9  mov     rbx, [rsp+38h+arg_0]
0x180028fce  add     rsp, 30h
0x180028fd2  pop     rdi
0x180028fd3  retn
```
