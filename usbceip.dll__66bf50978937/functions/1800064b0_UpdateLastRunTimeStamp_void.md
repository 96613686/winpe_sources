# UpdateLastRunTimeStamp(void)

- ea: `0x1800064b0`
- end: `0x18000653e`
- name: `?UpdateLastRunTimeStamp@@YAXXZ`
- size: `142`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180003b40`

## callees

- `0x1800064b0`
- `0x180008020`
- `0x18000bc7c`
- `0x18000bd24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006518`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006518`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800064e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800064e1`

## string_xrefs

- `0x18000650c`: `UsbCeipTaskLastRunTimestamp`

## pseudocode

```c
void UpdateLastRunTimeStamp(void)
{
  unsigned int v0; // eax
  HKEY hKey[5]; // [rsp+30h] [rbp-28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+8h] BYREF
  struct _FILETIME Data; // [rsp+68h] [rbp+10h] BYREF

  CRegistryKey::CRegistryKey(hKey, HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Usb\\Ceip");
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  Data = SystemTimeAsFileTime;
  v0 = RegSetValueExW(hKey[0], L"UsbCeipTaskLastRunTimestamp", 0, 0xBu, (const BYTE *)&Data, 8u);
  if ( v0 )
    CException::ThrowException(v0, 0, 0);
  CRegistryKey::~CRegistryKey((CRegistryKey *)hKey);
}

```

## disassembly

```asm
0x1800064b0  sub     rsp, 58h
0x1800064b4  mov     r9d, 2; unsigned int
0x1800064ba  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Usb"...
0x1800064c1  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800064c8  lea     rcx, [rsp+58h+hKey]; phkResult
0x1800064cd  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegistryKey::CRegistryKey(HKEY__ *,ushort const *,ulong)
0x1800064d2  nop
0x1800064d3  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800064dc  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800064e1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800064e7  mov     rax, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x1800064ec  mov     [rsp+58h+Data], rax
0x1800064f1  mov     [rsp+58h+cbData], 8; cbData
0x1800064f9  lea     rax, [rsp+58h+Data]
0x1800064fe  mov     [rsp+58h+lpData], rax; lpData
0x180006503  mov     r9d, 0Bh; dwType
0x180006509  xor     r8d, r8d; Reserved
0x18000650c  lea     rdx, aUsbceiptasklas; "UsbCeipTaskLastRunTimestamp"
0x180006513  mov     rcx, [rsp+58h+hKey]; hKey
0x180006518  call    cs:__imp_RegSetValueExW
0x18000651e  test    eax, eax
0x180006520  jz      short loc_18000652F
0x180006522  xor     r8d, r8d
0x180006525  xor     edx, edx
0x180006527  mov     ecx, eax
0x180006529  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000652f  lea     rcx, [rsp+58h+hKey]; this
0x180006534  call    ??1CRegistryKey@@QEAA@XZ; CRegistryKey::~CRegistryKey(void)
0x180006539  add     rsp, 58h
0x18000653d  retn
```
