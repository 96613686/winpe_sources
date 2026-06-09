# IsRemoveTSUSBPhantomDevnodesEnabled(void)

- ea: `0x18002db68`
- end: `0x18002dc55`
- name: `?IsRemoveTSUSBPhantomDevnodesEnabled@@YAHXZ`
- size: `237`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e8f0`
- `0x18002fd30`

## callees

- `0x18000b8f8`
- `0x18000f79c`
- `0x18002db68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002db9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002db9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002dbde`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002dbde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dc46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dc46`

## string_xrefs

- `0x18002dbb8`: `RemoveTSUSBDeviceNode`

## pseudocode

```c
_BOOL8 IsRemoveTSUSBPhantomDevnodesEnabled(void)
{
  BOOL v0; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  v0 = 1;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
          0,
          0x20019u,
          &hKey) )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"RemoveTSUSBDeviceNode", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    {
      v0 = Data != 0;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          25,
          &WPP_6d35608225a031b6e1549a53bee401ae_Traceguids,
          CurrentThreadActivityIdPrefix,
          v0);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18002db68  push    rbp
0x18002db6a  push    rbx
0x18002db6b  mov     rbp, rsp
0x18002db6e  sub     rsp, 38h
0x18002db72  lea     rax, [rbp+hKey]
0x18002db76  mov     [rbp+hKey], 0
0x18002db7e  mov     r9d, 20019h; samDesired
0x18002db84  mov     [rsp+38h+phkResult], rax; phkResult
0x18002db89  xor     r8d, r8d; ulOptions
0x18002db8c  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18002db93  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002db9a  mov     ebx, 1
0x18002db9f  call    cs:__imp_RegOpenKeyExW
0x18002dba5  test    eax, eax
0x18002dba7  jnz     loc_18002DC3D
0x18002dbad  mov     rcx, [rbp+hKey]; hKey
0x18002dbb1  lea     r9, [rbp+Type]; lpType
0x18002dbb5  mov     [rbp+Data], eax
0x18002dbb8  lea     rdx, aRemovetsusbdev; "RemoveTSUSBDeviceNode"
0x18002dbbf  mov     [rbp+Type], eax
0x18002dbc2  xor     r8d, r8d; lpReserved
0x18002dbc5  lea     rax, [rbp+cbData]
0x18002dbc9  mov     [rbp+cbData], 4
0x18002dbd0  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002dbd5  lea     rax, [rbp+Data]
0x18002dbd9  mov     [rsp+38h+phkResult], rax; lpData
0x18002dbde  call    cs:__imp_RegQueryValueExW
0x18002dbe4  test    eax, eax
0x18002dbe6  jnz     short loc_18002DC3D
0x18002dbe8  cmp     [rbp+Type], 4
0x18002dbec  jnz     short loc_18002DC3D
0x18002dbee  xor     ebx, ebx
0x18002dbf0  cmp     [rbp+Data], ebx
0x18002dbf3  setnz   bl
0x18002dbf6  mov     rax, cs:WPP_GLOBAL_Control
0x18002dbfd  lea     rcx, WPP_GLOBAL_Control
0x18002dc04  cmp     rax, rcx
0x18002dc07  jz      short loc_18002DC3D
0x18002dc09  test    byte ptr [rax+1Ch], 1
0x18002dc0d  jz      short loc_18002DC3D
0x18002dc0f  cmp     byte ptr [rax+19h], 4
0x18002dc13  jb      short loc_18002DC3D
0x18002dc15  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002dc1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc21  lea     r8, WPP_6d35608225a031b6e1549a53bee401ae_Traceguids
0x18002dc28  mov     edx, 19h
0x18002dc2d  mov     dword ptr [rsp+38h+phkResult], ebx
0x18002dc31  mov     r9d, eax
0x18002dc34  mov     rcx, [rcx+10h]
0x18002dc38  call    WPP_SF_Dd
0x18002dc3d  mov     rcx, [rbp+hKey]; hKey
0x18002dc41  test    rcx, rcx
0x18002dc44  jz      short loc_18002DC4C
0x18002dc46  call    cs:__imp_RegCloseKey
0x18002dc4c  mov     eax, ebx
0x18002dc4e  add     rsp, 38h
0x18002dc52  pop     rbx
0x18002dc53  pop     rbp
0x18002dc54  retn
```
