# CRegInfo::CheckIIS7ASPNETKey(ulong)

- ea: `0x18000c5c0`
- end: `0x18000c66a`
- name: `?CheckIIS7ASPNETKey@CRegInfo@@AEAAJK@Z`
- size: `170`
- prototype: `__int64 __fastcall(CRegInfo *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c978`

## callees

- `0x18000c5c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000c65c`
- `ADVAPI32!RegCloseKey` at `0x18000c65c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000c5f8`
- `ADVAPI32!RegOpenKeyExW` at `0x18000c5f8`
- `ADVAPI32!RegQueryValueExW` at `0x18000c638`
- `ADVAPI32!RegQueryValueExW` at `0x18000c638`

## string_xrefs

- `0x18000c5e7`: `Software\Microsoft\INETSTP\Components`

## pseudocode

```c
__int64 __fastcall CRegInfo::CheckIIS7ASPNETKey(CRegInfo *this, int a2)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  int Data; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  cbData = 4;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\INETSTP\\Components", 0, a2 | 0x20119, &hKey);
  if ( v2 || (v2 = RegQueryValueExW(hKey, L"ASPNET", 0, 0, (LPBYTE)&Data, &cbData)) != 0 )
  {
    v3 = (unsigned __int16)v2 | 0x80070000;
    if ( v2 <= 0 )
      v3 = v2;
  }
  else
  {
    v3 = Data != 1 ? 0x80070490 : 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18000c5c0  push    rbx
0x18000c5c2  sub     rsp, 30h
0x18000c5c6  and     [rsp+38h+hKey], 0
0x18000c5cc  lea     rax, [rsp+38h+hKey]
0x18000c5d1  or      edx, 20119h
0x18000c5d7  mov     [rsp+38h+cbData], 4
0x18000c5df  mov     r9d, edx; samDesired
0x18000c5e2  mov     [rsp+38h+phkResult], rax; phkResult
0x18000c5e7  lea     rdx, SubKey; "Software\\Microsoft\\INETSTP\\Component"...
0x18000c5ee  xor     r8d, r8d; ulOptions
0x18000c5f1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c5f8  call    cs:__imp_RegOpenKeyExW
0x18000c5fe  test    eax, eax
0x18000c600  jz      short loc_18000C612
0x18000c602  movzx   ebx, ax
0x18000c605  or      ebx, 80070000h
0x18000c60b  test    eax, eax
0x18000c60d  cmovle  ebx, eax
0x18000c610  jmp     short loc_18000C652
0x18000c612  mov     rcx, [rsp+38h+hKey]; hKey
0x18000c617  lea     rax, [rsp+38h+cbData]
0x18000c61c  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000c621  lea     rdx, aAspnet; "ASPNET"
0x18000c628  lea     rax, [rsp+38h+Data]
0x18000c62d  xor     r9d, r9d; lpType
0x18000c630  xor     r8d, r8d; lpReserved
0x18000c633  mov     [rsp+38h+phkResult], rax; lpData
0x18000c638  call    cs:__imp_RegQueryValueExW
0x18000c63e  test    eax, eax
0x18000c640  jnz     short loc_18000C602
0x18000c642  mov     eax, [rsp+38h+Data]
0x18000c646  dec     eax
0x18000c648  neg     eax
0x18000c64a  sbb     ebx, ebx
0x18000c64c  and     ebx, 80070490h
0x18000c652  mov     rcx, [rsp+38h+hKey]; hKey
0x18000c657  test    rcx, rcx
0x18000c65a  jz      short loc_18000C662
0x18000c65c  call    cs:__imp_RegCloseKey
0x18000c662  mov     eax, ebx
0x18000c664  add     rsp, 30h
0x18000c668  pop     rbx
0x18000c669  retn
```
