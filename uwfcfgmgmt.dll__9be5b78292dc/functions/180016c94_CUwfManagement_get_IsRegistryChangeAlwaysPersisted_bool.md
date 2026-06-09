# CUwfManagement::get_IsRegistryChangeAlwaysPersisted(bool *)

- ea: `0x180016c94`
- end: `0x180016d7e`
- name: `?get_IsRegistryChangeAlwaysPersisted@CUwfManagement@@AEAAJPEA_N@Z`
- size: `234`
- prototype: `__int64 __fastcall(CUwfManagement *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1800155f0`
- `0x180015870`

## callees

- `0x180012084`
- `0x180016c94`
- `0x180016d84`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180016d6d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180016d6d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016cf1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016cf1`

## pseudocode

```c
__int64 __fastcall CUwfManagement::get_IsRegistryChangeAlwaysPersisted(CUwfManagement *this, bool *a2)
{
  HKEY v4; // rcx
  LSTATUS v5; // eax
  int IsSystemVolumeProtected; // ebx
  bool v7; // dl
  unsigned __int16 *v9; // [rsp+30h] [rbp-18h] BYREF
  bool v10; // [rsp+70h] [rbp+28h] BYREF
  DWORD Type; // [rsp+78h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+38h] BYREF
  int Data; // [rsp+88h] [rbp+40h] BYREF

  *a2 = 0;
  v9 = 0;
  v10 = 0;
  v4 = (HKEY)*((_QWORD *)this + 17);
  Data = 0;
  Type = 0;
  cbData = 4;
  v5 = RegQueryValueExW(v4, L"UWFEnabled", 0, &Type, (LPBYTE)&Data, &cbData);
  IsSystemVolumeProtected = v5;
  if ( !v5 )
  {
    if ( Type != 4 )
    {
      IsSystemVolumeProtected = -2147023267;
      goto LABEL_15;
    }
    IsSystemVolumeProtected = 0;
    if ( cbData != 4 )
    {
      IsSystemVolumeProtected = -2147024883;
      goto LABEL_15;
    }
    goto LABEL_10;
  }
  if ( v5 > 0 )
    IsSystemVolumeProtected = (unsigned __int16)v5 | 0x80070000;
  if ( IsSystemVolumeProtected >= 0 )
  {
LABEL_10:
    if ( !Data
      || (IsSystemVolumeProtected = ExpandEnvironmentStringsHelper(L"%SystemDrive%", &v9, 0),
          IsSystemVolumeProtected >= 0)
      && (IsSystemVolumeProtected = CUwfManagement::get_IsSystemVolumeProtected(this, v7, &v10),
          IsSystemVolumeProtected >= 0)
      && !v10 )
    {
      *a2 = 1;
    }
  }
LABEL_15:
  operator delete[](v9);
  return (unsigned int)IsSystemVolumeProtected;
}

```

## disassembly

```asm
0x180016c94  push    rbp
0x180016c96  push    rbx
0x180016c97  push    rsi
0x180016c98  push    rdi
0x180016c99  mov     rbp, rsp
0x180016c9c  sub     rsp, 48h
0x180016ca0  lea     rax, [rbp+cbData]
0x180016ca4  mov     byte ptr [rdx], 0
0x180016ca7  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180016cac  lea     r9, [rbp+Type]; lpType
0x180016cb0  lea     rax, [rbp+Data]
0x180016cb4  mov     [rbp+var_18], 0
0x180016cbc  mov     rdi, rdx
0x180016cbf  mov     [rsp+48h+lpData], rax; lpData
0x180016cc4  mov     rsi, rcx
0x180016cc7  mov     [rbp+arg_0], 0
0x180016ccb  mov     rcx, [rcx+88h]; hKey
0x180016cd2  lea     rdx, aUwfenabled; "UWFEnabled"
0x180016cd9  xor     r8d, r8d; lpReserved
0x180016cdc  mov     [rbp+Data], 0
0x180016ce3  mov     [rbp+Type], 0
0x180016cea  mov     [rbp+cbData], 4
0x180016cf1  call    cs:__imp_RegQueryValueExW
0x180016cf7  mov     ebx, eax
0x180016cf9  test    eax, eax
0x180016cfb  jz      short loc_180016D0E
0x180016cfd  jle     short loc_180016D08
0x180016cff  movzx   ebx, ax
0x180016d02  or      ebx, 80070000h
0x180016d08  test    ebx, ebx
0x180016d0a  jns     short loc_180016D2A
0x180016d0c  jmp     short loc_180016D69
0x180016d0e  cmp     [rbp+Type], 4
0x180016d12  jz      short loc_180016D1B
0x180016d14  mov     ebx, 8007065Dh
0x180016d19  jmp     short loc_180016D69
0x180016d1b  xor     ebx, ebx
0x180016d1d  cmp     [rbp+cbData], 4
0x180016d21  jz      short loc_180016D2A
0x180016d23  mov     ebx, 8007000Dh
0x180016d28  jmp     short loc_180016D69
0x180016d2a  cmp     [rbp+Data], 0
0x180016d2e  setnz   al
0x180016d31  test    al, al
0x180016d33  jz      short loc_180016D66
0x180016d35  xor     r8d, r8d; unsigned int *
0x180016d38  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x180016d3c  lea     rcx, Src; "%SystemDrive%"
0x180016d43  call    ?ExpandEnvironmentStringsHelper@@YAJPEBGPEAPEAGPEAK@Z; ExpandEnvironmentStringsHelper(ushort const *,ushort * *,ulong *)
0x180016d48  mov     ebx, eax
0x180016d4a  test    eax, eax
0x180016d4c  js      short loc_180016D69
0x180016d4e  lea     r8, [rbp+arg_0]; bool *
0x180016d52  mov     rcx, rsi; this
0x180016d55  call    ?get_IsSystemVolumeProtected@CUwfManagement@@AEAAJ_NPEA_N@Z; CUwfManagement::get_IsSystemVolumeProtected(bool,bool *)
0x180016d5a  mov     ebx, eax
0x180016d5c  test    eax, eax
0x180016d5e  js      short loc_180016D69
0x180016d60  cmp     [rbp+arg_0], 0
0x180016d64  jnz     short loc_180016D69
0x180016d66  mov     byte ptr [rdi], 1
0x180016d69  mov     rcx, [rbp+var_18]
0x180016d6d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180016d73  mov     eax, ebx
0x180016d75  add     rsp, 48h
0x180016d79  pop     rdi
0x180016d7a  pop     rsi
0x180016d7b  pop     rbx
0x180016d7c  pop     rbp
0x180016d7d  retn
```
