# SCRIPTMAP_REGISTER_MANAGER::DetectNetFx35Installation(void)

- ea: `0x180034708`
- end: `0x1800347c0`
- name: `?DetectNetFx35Installation@SCRIPTMAP_REGISTER_MANAGER@@AEAAJXZ`
- size: `184`
- prototype: `__int64 __fastcall(SCRIPTMAP_REGISTER_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180035eac`

## callees

- `0x180034708`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800347ad`
- `ADVAPI32!RegCloseKey` at `0x1800347ad`
- `ADVAPI32!RegOpenKeyExW` at `0x180034738`
- `ADVAPI32!RegOpenKeyExW` at `0x180034738`
- `ADVAPI32!RegQueryValueExW` at `0x180034789`
- `ADVAPI32!RegQueryValueExW` at `0x180034789`

## string_xrefs

- `0x180034765`: `Install`

## pseudocode

```c
__int64 __fastcall SCRIPTMAP_REGISTER_MANAGER::DetectNetFx35Installation(SCRIPTMAP_REGISTER_MANAGER *this)
{
  unsigned int v2; // ebx
  LSTATUS v3; // eax
  int Data; // [rsp+48h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v2 = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, c_WCF35SetupKeyName, 0, 0x20019u, &hKey);
  if ( v3 != 2 )
  {
    if ( v3 )
    {
      v2 = (unsigned __int16)v3 | 0x80070000;
      if ( v3 <= 0 )
        v2 = v3;
    }
    else
    {
      Data = 0;
      cbData = 4;
      if ( (RegQueryValueExW(hKey, L"Install", 0, 0, (LPBYTE)&Data, &cbData) & 0xFFFFFFFD) == 0 )
        *((_DWORD *)this + 29) = Data == 1;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180034708  mov     [rsp+arg_0], rbx
0x18003470d  push    rdi
0x18003470e  sub     rsp, 30h
0x180034712  mov     rdx, cs:?c_WCF35SetupKeyName@@3PEBGEB; lpSubKey
0x180034719  lea     rax, [rsp+38h+hKey]
0x18003471e  mov     rdi, rcx
0x180034721  mov     [rsp+38h+phkResult], rax; phkResult
0x180034726  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003472d  mov     r9d, 20019h; samDesired
0x180034733  xor     r8d, r8d; ulOptions
0x180034736  xor     ebx, ebx
0x180034738  call    cs:__imp_RegOpenKeyExW
0x18003473e  cmp     eax, 2
0x180034741  jz      short loc_1800347A3
0x180034743  test    eax, eax
0x180034745  jz      short loc_180034757
0x180034747  movzx   ebx, ax
0x18003474a  or      ebx, 80070000h
0x180034750  test    eax, eax
0x180034752  cmovle  ebx, eax
0x180034755  jmp     short loc_1800347A3
0x180034757  mov     rcx, [rsp+38h+hKey]; hKey
0x18003475c  lea     rax, [rsp+38h+cbData]
0x180034761  and     [rsp+38h+Data], ebx
0x180034765  lea     rdx, aInstall; "Install"
0x18003476c  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180034771  xor     r9d, r9d; lpType
0x180034774  lea     rax, [rsp+38h+Data]
0x180034779  mov     [rsp+38h+cbData], 4
0x180034781  xor     r8d, r8d; lpReserved
0x180034784  mov     [rsp+38h+phkResult], rax; lpData
0x180034789  call    cs:__imp_RegQueryValueExW
0x18003478f  test    eax, 0FFFFFFFDh
0x180034794  jnz     short loc_1800347A3
0x180034796  xor     ecx, ecx
0x180034798  cmp     [rsp+38h+Data], 1
0x18003479d  setz    cl
0x1800347a0  mov     [rdi+74h], ecx
0x1800347a3  mov     rcx, [rsp+38h+hKey]; hKey
0x1800347a8  test    rcx, rcx
0x1800347ab  jz      short loc_1800347B3
0x1800347ad  call    cs:__imp_RegCloseKey
0x1800347b3  mov     eax, ebx
0x1800347b5  mov     rbx, [rsp+38h+arg_0]
0x1800347ba  add     rsp, 30h
0x1800347be  pop     rdi
0x1800347bf  retn
```
