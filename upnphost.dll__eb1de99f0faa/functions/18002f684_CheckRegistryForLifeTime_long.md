# CheckRegistryForLifeTime(long *)

- ea: `0x18002f684`
- end: `0x18002f780`
- name: `?CheckRegistryForLifeTime@@YAHPEAJ@Z`
- size: `252`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035320`
- `0x180035770`
- `0x18004c230`
- `0x18004cb90`

## callees

- `0x18002f684`
- `0x180038ce4`
- `0x180039a84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f71f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f71f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f6dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f6dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f70e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f70e`

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
0x18002f684  push    rbx
0x18002f686  push    rsi
0x18002f687  push    rdi
0x18002f688  sub     rsp, 30h
0x18002f68c  mov     rdi, rcx
0x18002f68f  mov     [rsp+48h+hKey], 0
0x18002f698  mov     [rsp+48h+cbData], 4
0x18002f6a0  mov     [rsp+48h+Data], 0
0x18002f6a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6af  lea     rsi, WPP_GLOBAL_Control
0x18002f6b6  cmp     rcx, rsi
0x18002f6b9  jnz     short loc_18002F72F
0x18002f6bb  lea     rax, [rsp+48h+hKey]
0x18002f6c0  mov     r9d, 1; samDesired
0x18002f6c6  xor     r8d, r8d; ulOptions
0x18002f6c9  mov     [rsp+48h+phkResult], rax; phkResult
0x18002f6ce  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\MICROSOFT\\UPnP Device Host\\"...
0x18002f6d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f6dc  call    cs:__imp_RegOpenKeyExW
0x18002f6e2  mov     ebx, eax
0x18002f6e4  test    eax, eax
0x18002f6e6  jnz     short loc_18002F725
0x18002f6e8  mov     rcx, [rsp+48h+hKey]; hKey
0x18002f6ed  lea     rax, [rsp+48h+cbData]
0x18002f6f2  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002f6f7  lea     rdx, aDevicelifetime; "DeviceLifetime"
0x18002f6fe  lea     rax, [rsp+48h+Data]
0x18002f703  xor     r9d, r9d; lpType
0x18002f706  xor     r8d, r8d; lpReserved
0x18002f709  mov     [rsp+48h+phkResult], rax; lpData
0x18002f70e  call    cs:__imp_RegQueryValueExW
0x18002f714  mov     ebx, eax
0x18002f716  test    eax, eax
0x18002f718  jz      short loc_18002F74F
0x18002f71a  mov     rcx, [rsp+48h+hKey]; hKey
0x18002f71f  call    cs:__imp_RegCloseKey
0x18002f725  mov     eax, ebx
0x18002f727  add     rsp, 30h
0x18002f72b  pop     rdi
0x18002f72c  pop     rsi
0x18002f72d  pop     rbx
0x18002f72e  retn
0x18002f72f  test    byte ptr [rcx+1Ch], 40h
0x18002f733  jz      short loc_18002F6BB
0x18002f735  mov     rcx, [rcx+10h]
0x18002f739  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18002f740  mov     edx, 0Ah
0x18002f745  call    WPP_SF_
0x18002f74a  jmp     loc_18002F6BB
0x18002f74f  mov     r9d, [rsp+48h+Data]
0x18002f754  mov     [rdi], r9d
0x18002f757  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f75e  cmp     rcx, rsi
0x18002f761  jz      short loc_18002F71A
0x18002f763  test    byte ptr [rcx+1Ch], 40h
0x18002f767  jz      short loc_18002F71A
0x18002f769  mov     rcx, [rcx+10h]
0x18002f76d  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18002f774  mov     edx, 0Bh
0x18002f779  call    WPP_SF_d
0x18002f77e  jmp     short loc_18002F71A
```
