# IsMsaEnterpriseDeviceAuthEnabled(int *)

- ea: `0x1800398f8`
- end: `0x1800399ea`
- name: `?IsMsaEnterpriseDeviceAuthEnabled@@YAJPEAH@Z`
- size: `242`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800399f0`

## callees

- `0x1800398f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039944`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039944`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800399ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800399ce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003999e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003999e`

## pseudocode

```c
__int64 __fastcall IsMsaEnterpriseDeviceAuthEnabled(int *a1)
{
  __int64 result; // rax
  LSTATUS v3; // eax
  signed int v4; // ebx
  LSTATUS ValueW; // eax
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  if ( !a1 )
    return 2147942487LL;
  *a1 = 0;
  hkey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
         0,
         0x20019u,
         &hkey);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hkey, 0, L"EnterpriseDeviceAuthOnly", 0x10u, 0, &pvData, &pcbData);
    v4 = ValueW;
    if ( ValueW > 0 )
      v4 = (unsigned __int16)ValueW | 0x80070000;
    if ( v4 >= 0 )
    {
      v4 = 0;
      *a1 = pvData != 0;
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  result = 0;
  if ( v4 != -2147024894 )
    return (unsigned int)v4;
  return result;
}

```

## disassembly

```asm
0x1800398f8  mov     [rsp+arg_18], rbx
0x1800398fd  push    rdi
0x1800398fe  sub     rsp, 40h
0x180039902  mov     rdi, rcx
0x180039905  test    rcx, rcx
0x180039908  jnz     short loc_180039914
0x18003990a  mov     eax, 80070057h
0x18003990f  jmp     loc_1800399DF
0x180039914  mov     dword ptr [rcx], 0
0x18003991a  lea     rax, [rsp+48h+hkey]
0x18003991f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039926  mov     [rsp+48h+phkResult], rax; phkResult
0x18003992b  mov     r9d, 20019h; samDesired
0x180039931  mov     [rsp+48h+hkey], 0
0x18003993a  xor     r8d, r8d; ulOptions
0x18003993d  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039944  call    cs:__imp_RegOpenKeyExW
0x18003994a  mov     ebx, eax
0x18003994c  test    eax, eax
0x18003994e  jle     short loc_180039959
0x180039950  movzx   ebx, ax
0x180039953  or      ebx, 80070000h
0x180039959  test    ebx, ebx
0x18003995b  js      short loc_1800399C4
0x18003995d  mov     rcx, [rsp+48h+hkey]; hkey
0x180039962  lea     rax, [rsp+48h+arg_8]
0x180039967  mov     [rsp+48h+pcbData], rax; pcbData
0x18003996c  lea     r8, Value; "EnterpriseDeviceAuthOnly"
0x180039973  lea     rax, [rsp+48h+arg_0]
0x180039978  mov     [rsp+48h+arg_0], 0
0x180039980  mov     [rsp+48h+pvData], rax; pvData
0x180039985  mov     r9d, 10h; dwFlags
0x18003998b  xor     edx, edx; lpSubKey
0x18003998d  mov     [rsp+48h+phkResult], 0; pdwType
0x180039996  mov     [rsp+48h+arg_8], 4
0x18003999e  call    cs:__imp_RegGetValueW
0x1800399a4  mov     ebx, eax
0x1800399a6  test    eax, eax
0x1800399a8  jle     short loc_1800399B3
0x1800399aa  movzx   ebx, ax
0x1800399ad  or      ebx, 80070000h
0x1800399b3  test    ebx, ebx
0x1800399b5  js      short loc_1800399C4
0x1800399b7  xor     eax, eax
0x1800399b9  cmp     [rsp+48h+arg_0], eax
0x1800399bd  setnz   al
0x1800399c0  xor     ebx, ebx
0x1800399c2  mov     [rdi], eax
0x1800399c4  mov     rcx, [rsp+48h+hkey]; hKey
0x1800399c9  test    rcx, rcx
0x1800399cc  jz      short loc_1800399D4
0x1800399ce  call    cs:__imp_RegCloseKey
0x1800399d4  xor     eax, eax
0x1800399d6  cmp     ebx, 80070002h
0x1800399dc  cmovnz  eax, ebx
0x1800399df  mov     rbx, [rsp+48h+arg_18]
0x1800399e4  add     rsp, 40h
0x1800399e8  pop     rdi
0x1800399e9  retn
```
