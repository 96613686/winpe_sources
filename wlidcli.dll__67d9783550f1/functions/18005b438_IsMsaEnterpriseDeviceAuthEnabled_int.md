# IsMsaEnterpriseDeviceAuthEnabled(int *)

- ea: `0x18005b438`
- end: `0x18005b52a`
- name: `?IsMsaEnterpriseDeviceAuthEnabled@@YAJPEAH@Z`
- size: `242`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005b530`

## callees

- `0x18005b438`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005b4de`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005b4de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b50e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b50e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b484`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b484`

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
0x18005b438  mov     [rsp+arg_18], rbx
0x18005b43d  push    rdi
0x18005b43e  sub     rsp, 40h
0x18005b442  mov     rdi, rcx
0x18005b445  test    rcx, rcx
0x18005b448  jnz     short loc_18005B454
0x18005b44a  mov     eax, 80070057h
0x18005b44f  jmp     loc_18005B51F
0x18005b454  mov     dword ptr [rcx], 0
0x18005b45a  lea     rax, [rsp+48h+hkey]
0x18005b45f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005b466  mov     [rsp+48h+phkResult], rax; phkResult
0x18005b46b  mov     r9d, 20019h; samDesired
0x18005b471  mov     [rsp+48h+hkey], 0
0x18005b47a  xor     r8d, r8d; ulOptions
0x18005b47d  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005b484  call    cs:__imp_RegOpenKeyExW
0x18005b48a  mov     ebx, eax
0x18005b48c  test    eax, eax
0x18005b48e  jle     short loc_18005B499
0x18005b490  movzx   ebx, ax
0x18005b493  or      ebx, 80070000h
0x18005b499  test    ebx, ebx
0x18005b49b  js      short loc_18005B504
0x18005b49d  mov     rcx, [rsp+48h+hkey]; hkey
0x18005b4a2  lea     rax, [rsp+48h+arg_8]
0x18005b4a7  mov     [rsp+48h+pcbData], rax; pcbData
0x18005b4ac  lea     r8, Value; "EnterpriseDeviceAuthOnly"
0x18005b4b3  lea     rax, [rsp+48h+arg_0]
0x18005b4b8  mov     [rsp+48h+arg_0], 0
0x18005b4c0  mov     [rsp+48h+pvData], rax; pvData
0x18005b4c5  mov     r9d, 10h; dwFlags
0x18005b4cb  xor     edx, edx; lpSubKey
0x18005b4cd  mov     [rsp+48h+phkResult], 0; pdwType
0x18005b4d6  mov     [rsp+48h+arg_8], 4
0x18005b4de  call    cs:__imp_RegGetValueW
0x18005b4e4  mov     ebx, eax
0x18005b4e6  test    eax, eax
0x18005b4e8  jle     short loc_18005B4F3
0x18005b4ea  movzx   ebx, ax
0x18005b4ed  or      ebx, 80070000h
0x18005b4f3  test    ebx, ebx
0x18005b4f5  js      short loc_18005B504
0x18005b4f7  xor     eax, eax
0x18005b4f9  cmp     [rsp+48h+arg_0], eax
0x18005b4fd  setnz   al
0x18005b500  xor     ebx, ebx
0x18005b502  mov     [rdi], eax
0x18005b504  mov     rcx, [rsp+48h+hkey]; hKey
0x18005b509  test    rcx, rcx
0x18005b50c  jz      short loc_18005B514
0x18005b50e  call    cs:__imp_RegCloseKey
0x18005b514  xor     eax, eax
0x18005b516  cmp     ebx, 80070002h
0x18005b51c  cmovnz  eax, ebx
0x18005b51f  mov     rbx, [rsp+48h+arg_18]
0x18005b524  add     rsp, 40h
0x18005b528  pop     rdi
0x18005b529  retn
```
