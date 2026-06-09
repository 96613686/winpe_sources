# SetDeviceInstallDate

- ea: `0x180009ab0`
- end: `0x180009bbb`
- name: `SetDeviceInstallDate`
- size: `267`
- prototype: `__int64 __fastcall(DEVINSTID_W pDeviceID)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800056d0`

## callees

- `0x180008220`
- `0x180008bf0`
- `0x180009ab0`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180009af7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180009af7`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180009b05`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180009b05`

## pseudocode

```c
__int64 __fastcall SetDeviceInstallDate(DEVINSTID_W pDeviceID)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  ULONG v9; // [rsp+40h] [rbp-30h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+44h] [rbp-2Ch] BYREF
  struct _FILETIME FileTime; // [rsp+48h] [rbp-28h] BYREF
  BYTE PropertyBuffer[8]; // [rsp+50h] [rbp-20h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-18h] BYREF

  FileTime = 0;
  *(_QWORD *)PropertyBuffer = 0;
  PropertyType = 0;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  PnpSetObjectProp(pDeviceID, v2, v3, &DEVPKEY_Device_InstallDate, 0x10u, (PBYTE)&FileTime, 8u);
  v9 = 8;
  result = PnpGetObjectProp(pDeviceID, v4, v5, &DEVPKEY_Device_FirstInstallDate, &PropertyType, PropertyBuffer, &v9);
  if ( (_DWORD)result == 37 || !(_DWORD)result && (PropertyType != 16 || v9 != 8) )
    return PnpSetObjectProp(pDeviceID, v7, v8, &DEVPKEY_Device_FirstInstallDate, 0x10u, (PBYTE)&FileTime, 8u);
  return result;
}

```

## disassembly

```asm
0x180009ab0  mov     [rsp-8+arg_8], rbx
0x180009ab5  push    rbp
0x180009ab6  mov     rbp, rsp
0x180009ab9  sub     rsp, 70h
0x180009abd  mov     rax, cs:__security_cookie
0x180009ac4  xor     rax, rsp
0x180009ac7  mov     [rbp+var_8], rax
0x180009acb  mov     rbx, rcx
0x180009ace  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x180009ad6  xorps   xmm0, xmm0
0x180009ad9  mov     qword ptr [rbp+var_20], 0
0x180009ae1  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180009ae5  mov     [rbp+var_2C], 0
0x180009aec  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180009af0  mov     [rbp+var_30], 0
0x180009af7  call    cs:__imp_GetSystemTime
0x180009afd  lea     rdx, [rbp+FileTime]; lpFileTime
0x180009b01  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180009b05  call    cs:__imp_SystemTimeToFileTime
0x180009b0b  lea     rax, [rbp+FileTime]
0x180009b0f  mov     [rsp+70h+var_40], 8; ULONG
0x180009b17  mov     [rsp+70h+PropertyBuffer], rax; PropertyBuffer
0x180009b1c  lea     r9, DEVPKEY_Device_InstallDate
0x180009b23  mov     rcx, rbx; pDeviceID
0x180009b26  mov     [rsp+70h+PropertyType], 10h; PropertyType
0x180009b2e  call    PnpSetObjectProp
0x180009b33  lea     rax, [rbp+var_30]
0x180009b37  mov     [rbp+var_30], 8
0x180009b3e  mov     qword ptr [rsp+70h+var_40], rax; PULONG
0x180009b43  lea     r9, DEVPKEY_Device_FirstInstallDate
0x180009b4a  lea     rax, [rbp+var_20]
0x180009b4e  mov     rcx, rbx; pDeviceID
0x180009b51  mov     [rsp+70h+PropertyBuffer], rax; PropertyBuffer
0x180009b56  lea     rax, [rbp+var_2C]
0x180009b5a  mov     qword ptr [rsp+70h+PropertyType], rax; PropertyType
0x180009b5f  call    PnpGetObjectProp
0x180009b64  cmp     eax, 25h ; '%'
0x180009b67  jz      short loc_180009B79
0x180009b69  test    eax, eax
0x180009b6b  jnz     short loc_180009BA1
0x180009b6d  cmp     [rbp+var_2C], 10h
0x180009b71  jnz     short loc_180009B79
0x180009b73  cmp     [rbp+var_30], 8
0x180009b77  jz      short loc_180009BA1
0x180009b79  lea     rax, [rbp+FileTime]
0x180009b7d  mov     [rsp+70h+var_40], 8; ULONG
0x180009b85  mov     [rsp+70h+PropertyBuffer], rax; PropertyBuffer
0x180009b8a  lea     r9, DEVPKEY_Device_FirstInstallDate
0x180009b91  mov     rcx, rbx; pDeviceID
0x180009b94  mov     [rsp+70h+PropertyType], 10h; PropertyType
0x180009b9c  call    PnpSetObjectProp
0x180009ba1  mov     rcx, [rbp+var_8]
0x180009ba5  xor     rcx, rsp; StackCookie
0x180009ba8  call    __security_check_cookie
0x180009bad  mov     rbx, [rsp+70h+arg_8]
0x180009bb5  add     rsp, 70h
0x180009bb9  pop     rbp
0x180009bba  retn
```
