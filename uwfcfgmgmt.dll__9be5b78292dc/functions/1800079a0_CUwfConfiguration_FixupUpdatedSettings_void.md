# CUwfConfiguration::FixupUpdatedSettings(void)

- ea: `0x1800079a0`
- end: `0x180007abf`
- name: `?FixupUpdatedSettings@CUwfConfiguration@@QEAAJXZ`
- size: `287`
- prototype: `int __fastcall(CUwfConfiguration *this)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005c80`
- `0x180005f00`
- `0x180006c80`
- `0x180007420`
- `0x180008da0`
- `0x180008f60`
- `0x1800091f0`
- `0x18000a150`
- `0x18000a240`
- `0x18000a5f0`
- `0x18000a6e0`

## callees

- `0x1800079a0`
- `0x18000a8c8`
- `0x18000e480`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800079ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007a3e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800079ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007a3e`

## string_xrefs

- `0x180007a29`: `UpdatedSettings`
- `0x180007aa4`: `HKLM\SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Static`

## pseudocode

```c
int __fastcall CUwfConfiguration::FixupUpdatedSettings(CUwfConfiguration *this)
{
  CUwfRegKey *v1; // rbx
  HKEY v3; // rcx
  int result; // eax
  bool v5; // sf
  HKEY v6; // rcx
  bool v7; // sf
  CUwfConfiguration *v8; // rcx
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  unsigned int lpData; // [rsp+60h] [rbp+30h] BYREF
  int Data; // [rsp+68h] [rbp+38h] BYREF

  Data = 0;
  v1 = (CUwfConfiguration *)((char *)this + 32);
  Type = 0;
  v3 = (HKEY)*((_QWORD *)this + 4);
  cbData = 4;
  result = RegQueryValueExW(v3, L"CurrentSettings", 0, &Type, (LPBYTE)&Data, &cbData);
  v5 = result < 0;
  if ( result )
  {
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v5 = result < 0;
    }
    if ( v5 )
      goto LABEL_19;
  }
  else
  {
    if ( Type != 4 )
    {
LABEL_12:
      result = -2147023267;
      goto LABEL_19;
    }
    if ( cbData != 4 )
    {
LABEL_10:
      result = -2147024883;
LABEL_19:
      *((_DWORD *)this + 4) = result;
      return result;
    }
  }
  v6 = *(HKEY *)v1;
  lpData = 0;
  Type = 0;
  cbData = 4;
  result = RegQueryValueExW(v6, L"UpdatedSettings", 0, &Type, (LPBYTE)&lpData, &cbData);
  v7 = result < 0;
  if ( !result )
  {
    if ( Type != 4 )
      goto LABEL_12;
    result = 0;
    if ( cbData == 4 )
      goto LABEL_14;
    goto LABEL_10;
  }
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
LABEL_14:
    v7 = result < 0;
  }
  if ( v7 )
    goto LABEL_19;
  if ( lpData != Data )
  {
    result = CUwfRegKey::SetDWORDValue(v1, L"CurrentSettings", lpData);
    if ( result < 0 )
      goto LABEL_19;
    result = CUwfConfiguration::commitRegKeyValue(
               v8,
               L"HKLM\\SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Static",
               L"CurrentSettings");
    if ( result < 0 )
      goto LABEL_19;
  }
  return result;
}

```

## disassembly

```asm
0x1800079a0  push    rbp
0x1800079a2  push    rbx
0x1800079a3  push    rdi
0x1800079a4  mov     rbp, rsp
0x1800079a7  sub     rsp, 30h
0x1800079ab  lea     rax, [rbp+cbData]
0x1800079af  mov     [rbp+Data], 0
0x1800079b6  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800079bb  lea     rbx, [rcx+20h]
0x1800079bf  lea     rax, [rbp+Data]
0x1800079c3  mov     [rbp+Type], 0
0x1800079ca  mov     rdi, rcx
0x1800079cd  mov     [rsp+30h+lpData], rax; lpData
0x1800079d2  mov     rcx, [rbx]; hKey
0x1800079d5  lea     r9, [rbp+Type]; lpType
0x1800079d9  xor     r8d, r8d; lpReserved
0x1800079dc  mov     [rbp+cbData], 4
0x1800079e3  lea     rdx, aCurrentsetting; "CurrentSettings"
0x1800079ea  call    cs:__imp_RegQueryValueExW
0x1800079f0  test    eax, eax
0x1800079f2  jz      short loc_180007A54
0x1800079f4  jle     short loc_180007A00
0x1800079f6  movzx   eax, ax
0x1800079f9  or      eax, 80070000h
0x1800079fe  test    eax, eax
0x180007a00  js      loc_180007AB4
0x180007a06  mov     rcx, [rbx]; hKey
0x180007a09  lea     rax, [rbp+cbData]
0x180007a0d  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180007a12  lea     r9, [rbp+Type]; lpType
0x180007a16  lea     rax, [rbp+arg_10]
0x180007a1a  mov     [rbp+arg_10], 0
0x180007a21  xor     r8d, r8d; lpReserved
0x180007a24  mov     [rsp+30h+lpData], rax; lpData
0x180007a29  lea     rdx, aUpdatedsetting; "UpdatedSettings"
0x180007a30  mov     [rbp+Type], 0
0x180007a37  mov     [rbp+cbData], 4
0x180007a3e  call    cs:__imp_RegQueryValueExW
0x180007a44  test    eax, eax
0x180007a46  jz      short loc_180007A67
0x180007a48  jle     short loc_180007A7E
0x180007a4a  movzx   eax, ax
0x180007a4d  or      eax, 80070000h
0x180007a52  jmp     short loc_180007A7C
0x180007a54  cmp     [rbp+Type], 4
0x180007a58  jnz     short loc_180007A6D
0x180007a5a  cmp     [rbp+cbData], 4
0x180007a5e  jz      short loc_180007A06
0x180007a60  mov     eax, 8007000Dh
0x180007a65  jmp     short loc_180007AB4
0x180007a67  cmp     [rbp+Type], 4
0x180007a6b  jz      short loc_180007A74
0x180007a6d  mov     eax, 8007065Dh
0x180007a72  jmp     short loc_180007AB4
0x180007a74  xor     eax, eax
0x180007a76  cmp     [rbp+cbData], 4
0x180007a7a  jnz     short loc_180007A60
0x180007a7c  test    eax, eax
0x180007a7e  js      short loc_180007AB4
0x180007a80  mov     r8d, [rbp+arg_10]; unsigned int
0x180007a84  cmp     r8d, [rbp+Data]
0x180007a88  jz      short loc_180007AB7
0x180007a8a  lea     rdx, aCurrentsetting; "CurrentSettings"
0x180007a91  mov     rcx, rbx; this
0x180007a94  call    ?SetDWORDValue@CUwfRegKey@@QEAAJPEBGK@Z; CUwfRegKey::SetDWORDValue(ushort const *,ulong)
0x180007a99  test    eax, eax
0x180007a9b  js      short loc_180007AB4
0x180007a9d  lea     r8, aCurrentsetting; "CurrentSettings"
0x180007aa4  lea     rdx, aHklmSystemCurr; "HKLM\\SYSTEM\\CurrentControlSet\\Servic"...
0x180007aab  call    ?commitRegKeyValue@CUwfConfiguration@@AEAAJPEBG0@Z; CUwfConfiguration::commitRegKeyValue(ushort const *,ushort const *)
0x180007ab0  test    eax, eax
0x180007ab2  jns     short loc_180007AB7
0x180007ab4  mov     [rdi+10h], eax
0x180007ab7  add     rsp, 30h
0x180007abb  pop     rdi
0x180007abc  pop     rbx
0x180007abd  pop     rbp
0x180007abe  retn
```
