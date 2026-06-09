# CheckRegistryForLifeTime(long *)

- ea: `0x180030fd0`
- end: `0x1800310e7`
- name: `?CheckRegistryForLifeTime@@YAHPEAJ@Z`
- size: `279`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037620`
- `0x180037aa0`
- `0x18004f5b0`
- `0x18004ff50`

## callees

- `0x180030fd0`
- `0x18003b1cc`
- `0x18003c018`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003107b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003107b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003102c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003102c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031064`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031064`

## pseudocode

```c
__int64 __fastcall CheckRegistryForLifeTime(unsigned int *a1)
{
  unsigned int v2; // ebx
  __int64 v4; // r9
  unsigned int Data; // [rsp+58h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  cbData = 4;
  Data = 0;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids);
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\MICROSOFT\\UPnP Device Host\\Devices", 0, 1u, &hKey);
  if ( !v2 )
  {
    v2 = RegQueryValueExW(hKey, L"DeviceLifetime", 0, 0, (LPBYTE)&Data, &cbData);
    if ( !v2 )
    {
      v4 = Data;
      *a1 = Data;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids, v4);
    }
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x180030fd0  push    rbx
0x180030fd2  push    rsi
0x180030fd3  push    rdi
0x180030fd4  sub     rsp, 30h
0x180030fd8  mov     rdi, rcx
0x180030fdb  mov     [rsp+48h+hKey], 0
0x180030fe4  mov     [rsp+48h+cbData], 4
0x180030fec  mov     [rsp+48h+Data], 0
0x180030ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ffb  lea     rsi, WPP_GLOBAL_Control
0x180031002  cmp     rcx, rsi
0x180031005  jnz     loc_180031092
0x18003100b  lea     rax, [rsp+48h+hKey]
0x180031010  mov     r9d, 1; samDesired
0x180031016  xor     r8d, r8d; ulOptions
0x180031019  mov     [rsp+48h+phkResult], rax; phkResult
0x18003101e  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\MICROSOFT\\UPnP Device Host\\"...
0x180031025  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003102c  call    cs:__imp_RegOpenKeyExW
0x180031033  nop     dword ptr [rax+rax+00h]
0x180031038  mov     ebx, eax
0x18003103a  test    eax, eax
0x18003103c  jnz     short loc_180031087
0x18003103e  mov     rcx, [rsp+48h+hKey]; hKey
0x180031043  lea     rax, [rsp+48h+cbData]
0x180031048  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18003104d  lea     rdx, aDevicelifetime; "DeviceLifetime"
0x180031054  lea     rax, [rsp+48h+Data]
0x180031059  xor     r9d, r9d; lpType
0x18003105c  xor     r8d, r8d; lpReserved
0x18003105f  mov     [rsp+48h+phkResult], rax; lpData
0x180031064  call    cs:__imp_RegQueryValueExW
0x18003106b  nop     dword ptr [rax+rax+00h]
0x180031070  mov     ebx, eax
0x180031072  test    eax, eax
0x180031074  jz      short loc_1800310B6
0x180031076  mov     rcx, [rsp+48h+hKey]; hKey
0x18003107b  call    cs:__imp_RegCloseKey
0x180031082  nop     dword ptr [rax+rax+00h]
0x180031087  mov     eax, ebx
0x180031089  add     rsp, 30h
0x18003108d  pop     rdi
0x18003108e  pop     rsi
0x18003108f  pop     rbx
0x180031090  retn
0x180031092  test    byte ptr [rcx+1Ch], 40h
0x180031096  jz      loc_18003100B
0x18003109c  mov     rcx, [rcx+10h]
0x1800310a0  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x1800310a7  mov     edx, 0Ah
0x1800310ac  call    WPP_SF_
0x1800310b1  jmp     loc_18003100B
0x1800310b6  mov     r9d, [rsp+48h+Data]
0x1800310bb  mov     [rdi], r9d
0x1800310be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800310c5  cmp     rcx, rsi
0x1800310c8  jz      short loc_180031076
0x1800310ca  test    byte ptr [rcx+1Ch], 40h
0x1800310ce  jz      short loc_180031076
0x1800310d0  mov     rcx, [rcx+10h]
0x1800310d4  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x1800310db  mov     edx, 0Bh
0x1800310e0  call    WPP_SF_d
0x1800310e5  jmp     short loc_180031076
```
