# WdipGetServerPortName

- ea: `0x180007160`
- end: `0x180007279`
- name: `WdipGetServerPortName`
- size: `281`
- prototype: `__int64 __fastcall(LPBYTE lpData)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009f18`

## callees

- `0x180002ba0`
- `0x180007160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000721c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000721c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000726b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000726b`

## string_xrefs

- `0x180007250`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`
- `0x1800071b2`: `System\CurrentControlSet\Control\WDI\Config`

## pseudocode

```c
__int64 __fastcall WdipGetServerPortName(LPBYTE lpData)
{
  signed int v2; // ebx
  LSTATUS v3; // eax
  int v4; // r8d
  LSTATUS v5; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  cbData = 256;
  if ( !lpData )
  {
    v2 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
      (int)L"WdipGetServerPortName",
      701,
      (int)L"Error = %d",
      87);
    goto LABEL_14;
  }
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\WDI\\Config", 0, 0x20019u, &hKey);
  v2 = v3;
  if ( v3 > 0 )
    v2 = (unsigned __int16)v3 | 0x80070000;
  if ( v2 < 0 )
  {
    v4 = 718;
LABEL_13:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
      (int)L"WdipGetServerPortName",
      v4,
      (int)L"Error = %d",
      v2);
    goto LABEL_14;
  }
  if ( !hKey )
  {
    v2 = -2147467259;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
      (int)L"WdipGetServerPortName",
      720,
      (int)L"Error = %d",
      5);
    goto LABEL_14;
  }
  v5 = RegQueryValueExW(hKey, L"ServerName", 0, 0, lpData, &cbData);
  v2 = v5;
  if ( v5 > 0 )
    v2 = (unsigned __int16)v5 | 0x80070000;
  if ( v2 < 0 )
  {
    v4 = 730;
    goto LABEL_13;
  }
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180007160  mov     [rsp+cbData], edx
0x180007164  push    rbx
0x180007165  sub     rsp, 30h
0x180007169  mov     [rsp+38h+arg_10], rdi
0x18000716e  mov     rdi, rcx
0x180007171  mov     [rsp+38h+hKey], 0
0x18000717a  mov     [rsp+38h+cbData], 100h
0x180007182  test    rcx, rcx
0x180007185  jnz     short loc_18000719F
0x180007187  mov     ebx, 80070057h
0x18000718c  mov     dword ptr [rsp+38h+phkResult], 57h ; 'W'
0x180007194  mov     r8d, 2BDh
0x18000719a  jmp     loc_180007242
0x18000719f  lea     rax, [rsp+38h+hKey]
0x1800071a4  mov     r9d, 20019h; samDesired
0x1800071aa  xor     r8d, r8d; ulOptions
0x1800071ad  mov     [rsp+38h+phkResult], rax; phkResult
0x1800071b2  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\WDI"...
0x1800071b9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800071c0  call    cs:__imp_RegOpenKeyExW
0x1800071c6  mov     ebx, eax
0x1800071c8  test    eax, eax
0x1800071ca  jle     short loc_1800071D5
0x1800071cc  movzx   ebx, ax
0x1800071cf  or      ebx, 80070000h
0x1800071d5  test    ebx, ebx
0x1800071d7  jns     short loc_1800071E1
0x1800071d9  mov     r8d, 2CEh
0x1800071df  jmp     short loc_18000723B
0x1800071e1  mov     rcx, [rsp+38h+hKey]; hKey
0x1800071e6  test    rcx, rcx
0x1800071e9  jnz     short loc_180007200
0x1800071eb  mov     ebx, 80004005h
0x1800071f0  mov     dword ptr [rsp+38h+phkResult], 4005h
0x1800071f8  mov     r8d, 2D0h
0x1800071fe  jmp     short loc_180007242
0x180007200  lea     rax, [rsp+38h+cbData]
0x180007205  xor     r9d, r9d; lpType
0x180007208  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000720d  lea     rdx, aServername; "ServerName"
0x180007214  xor     r8d, r8d; lpReserved
0x180007217  mov     [rsp+38h+phkResult], rdi; lpData
0x18000721c  call    cs:__imp_RegQueryValueExW
0x180007222  mov     ebx, eax
0x180007224  test    eax, eax
0x180007226  jle     short loc_180007231
0x180007228  movzx   ebx, ax
0x18000722b  or      ebx, 80070000h
0x180007231  test    ebx, ebx
0x180007233  jns     short loc_18000725C
0x180007235  mov     r8d, 2DAh; int
0x18000723b  movzx   eax, bx
0x18000723e  mov     dword ptr [rsp+38h+phkResult], eax; Args
0x180007242  lea     r9, aErrorD_0; "Error = %d"
0x180007249  lea     rdx, aWdipgetserverp; "WdipGetServerPortName"
0x180007250  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007257  call    WdipTraceError
0x18000725c  mov     rcx, [rsp+38h+hKey]; hKey
0x180007261  mov     rdi, [rsp+38h+arg_10]
0x180007266  test    rcx, rcx
0x180007269  jz      short loc_180007271
0x18000726b  call    cs:__imp_RegCloseKey
0x180007271  mov     eax, ebx
0x180007273  add     rsp, 30h
0x180007277  pop     rbx
0x180007278  retn
```
