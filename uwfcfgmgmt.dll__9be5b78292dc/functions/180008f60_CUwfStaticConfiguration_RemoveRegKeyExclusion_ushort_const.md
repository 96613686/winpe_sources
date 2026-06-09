# CUwfStaticConfiguration::RemoveRegKeyExclusion(ushort const *)

- ea: `0x180008f60`
- end: `0x1800090f4`
- name: `?RemoveRegKeyExclusion@CUwfStaticConfiguration@@QEAAJPEBG@Z`
- size: `404`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180019730`

## callees

- `0x180001384`
- `0x1800079a0`
- `0x180008f60`
- `0x18000e4d0`
- `0x180011a30`
- `0x180011d20`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180009084`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800090d0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009084`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800090d0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008fd4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180009057`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008fd4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180009057`

## string_xrefs

- `0x180008fbc`: `RegistryExceptionsUserDefined`
- `0x180009036`: `RegistryExceptionsUserDefined`
- `0x1800090bc`: `RegistryExceptionsUserDefined`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::RemoveRegKeyExclusion(
        CUwfStaticConfiguration *this,
        const unsigned __int16 *a2)
{
  struct _MULTISZ *v2; // rsi
  int v5; // ebx
  HKEY *v6; // r15
  HKEY v7; // rcx
  LSTATUS ValueW; // eax
  void *pvData; // rbp
  bool v10; // cc
  int v11; // eax
  DWORD pcbData; // [rsp+78h] [rbp+10h] BYREF
  DWORD pdwType; // [rsp+80h] [rbp+18h] BYREF

  v2 = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
    goto LABEL_20;
  }
  if ( *((_BYTE *)this + 9) )
  {
    v5 = -2147024891;
    goto LABEL_20;
  }
  pdwType = 0;
  v6 = (HKEY *)((char *)this + 16);
  v7 = (HKEY)*((_QWORD *)this + 2);
  pcbData = 0;
  ValueW = RegGetValueW(v7, 0, L"RegistryExceptionsUserDefined", 0x20u, &pdwType, 0, &pcbData);
  v5 = ValueW;
  if ( ValueW )
  {
    pvData = 0;
    v10 = ValueW <= 0;
LABEL_7:
    if ( !v10 )
      v5 = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_14;
  }
  pvData = operator new[](saturated_mul((unsigned __int64)pcbData >> 1, 2u));
  if ( pvData )
  {
    ValueW = RegGetValueW(*v6, 0, L"RegistryExceptionsUserDefined", 0x20u, &pdwType, pvData, &pcbData);
    v5 = ValueW;
    v10 = ValueW <= 0;
    if ( !ValueW )
    {
      v2 = (struct _MULTISZ *)MultiSzAlloc(pvData);
      v5 = -2147024882;
      if ( v2 )
        v5 = 0;
      goto LABEL_14;
    }
    goto LABEL_7;
  }
  v5 = -2147024882;
LABEL_14:
  operator delete[](pvData);
  if ( v5 >= 0 )
  {
    v11 = MultiSzRemove(a2, v2);
    v5 = v11;
    if ( v11 == -2147023728 )
    {
      v5 = 0;
    }
    else if ( v11 >= 0 )
    {
      v5 = CUwfConfiguration::FixupUpdatedSettings(*((CUwfConfiguration **)this + 4));
      if ( v5 >= 0 )
        v5 = CUwfRegKey::SetMultiSzValue((CUwfRegKey *)v6, L"RegistryExceptionsUserDefined", v2);
    }
  }
LABEL_20:
  operator delete[](v2);
  if ( v5 < 0 )
    *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008f60  mov     [rsp+arg_0], rbx
0x180008f65  push    rbp
0x180008f66  push    rsi
0x180008f67  push    rdi
0x180008f68  push    r14
0x180008f6a  push    r15
0x180008f6c  sub     rsp, 40h
0x180008f70  xor     esi, esi
0x180008f72  mov     r14, rdx
0x180008f75  mov     rdi, rcx
0x180008f78  test    rdx, rdx
0x180008f7b  jnz     short loc_180008F87
0x180008f7d  mov     ebx, 80004003h
0x180008f82  jmp     loc_1800090CD
0x180008f87  cmp     [rcx+9], sil
0x180008f8b  jz      short loc_180008F97
0x180008f8d  mov     ebx, 80070005h
0x180008f92  jmp     loc_1800090CD
0x180008f97  lea     rax, [rsp+68h+arg_8]
0x180008f9c  mov     [rsp+68h+arg_10], esi
0x180008fa3  mov     [rsp+68h+pcbData], rax; pcbData
0x180008fa8  lea     r15, [rcx+10h]
0x180008fac  mov     rcx, [r15]; hkey
0x180008faf  lea     rax, [rsp+68h+arg_10]
0x180008fb7  mov     [rsp+68h+pvData], rsi; pvData
0x180008fbc  lea     r8, aRegistryexcept_0; "RegistryExceptionsUserDefined"
0x180008fc3  mov     r9d, 20h ; ' '; dwFlags
0x180008fc9  mov     [rsp+68h+pdwType], rax; pdwType
0x180008fce  xor     edx, edx; lpSubKey
0x180008fd0  mov     [rsp+68h+arg_8], esi
0x180008fd4  call    cs:__imp_RegGetValueW
0x180008fda  mov     ebx, eax
0x180008fdc  test    eax, eax
0x180008fde  jz      short loc_180008FF8
0x180008fe0  xor     ebp, ebp
0x180008fe2  test    eax, eax
0x180008fe4  jle     loc_180009081
0x180008fea  movzx   ebx, ax
0x180008fed  or      ebx, 80070000h
0x180008ff3  jmp     loc_180009081
0x180008ff8  mov     ecx, [rsp+68h+arg_8]
0x180008ffc  mov     eax, 2
0x180009001  shr     rcx, 1
0x180009004  mul     rcx
0x180009007  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000900e  cmovb   rax, rcx
0x180009012  mov     rcx, rax; unsigned __int64
0x180009015  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000901a  mov     rbp, rax
0x18000901d  test    rax, rax
0x180009020  jnz     short loc_180009029
0x180009022  mov     ebx, 8007000Eh
0x180009027  jmp     short loc_180009081
0x180009029  mov     rcx, [r15]; hkey
0x18000902c  lea     rax, [rsp+68h+arg_8]
0x180009031  mov     [rsp+68h+pcbData], rax; pcbData
0x180009036  lea     r8, aRegistryexcept_0; "RegistryExceptionsUserDefined"
0x18000903d  lea     rax, [rsp+68h+arg_10]
0x180009045  mov     [rsp+68h+pvData], rbp; pvData
0x18000904a  mov     r9d, 20h ; ' '; dwFlags
0x180009050  mov     [rsp+68h+pdwType], rax; pdwType
0x180009055  xor     edx, edx; lpSubKey
0x180009057  call    cs:__imp_RegGetValueW
0x18000905d  mov     ebx, eax
0x18000905f  test    eax, eax
0x180009061  jnz     short loc_180008FE4
0x180009063  mov     edx, [rsp+68h+arg_8]
0x180009067  mov     rcx, rbp; Src
0x18000906a  shr     edx, 1
0x18000906c  call    MultiSzAlloc
0x180009071  mov     rsi, rax
0x180009074  mov     ebx, 8007000Eh
0x180009079  xor     eax, eax
0x18000907b  test    rsi, rsi
0x18000907e  cmovnz  ebx, eax
0x180009081  mov     rcx, rbp
0x180009084  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000908a  test    ebx, ebx
0x18000908c  js      short loc_1800090CD
0x18000908e  mov     rdx, rsi
0x180009091  mov     rcx, r14
0x180009094  call    MultiSzRemove
0x180009099  mov     ebx, eax
0x18000909b  cmp     eax, 80070490h
0x1800090a0  jnz     short loc_1800090A6
0x1800090a2  xor     ebx, ebx
0x1800090a4  jmp     short loc_1800090CD
0x1800090a6  test    eax, eax
0x1800090a8  js      short loc_1800090CD
0x1800090aa  mov     rcx, [rdi+20h]; this
0x1800090ae  call    ?FixupUpdatedSettings@CUwfConfiguration@@QEAAJXZ; CUwfConfiguration::FixupUpdatedSettings(void)
0x1800090b3  mov     ebx, eax
0x1800090b5  test    eax, eax
0x1800090b7  js      short loc_1800090CD
0x1800090b9  mov     r8, rsi; struct _MULTISZ *
0x1800090bc  lea     rdx, aRegistryexcept_0; "RegistryExceptionsUserDefined"
0x1800090c3  mov     rcx, r15; this
0x1800090c6  call    ?SetMultiSzValue@CUwfRegKey@@QEAAJPEBGQEAU_MULTISZ@@@Z; CUwfRegKey::SetMultiSzValue(ushort const *,_MULTISZ * const)
0x1800090cb  mov     ebx, eax
0x1800090cd  mov     rcx, rsi
0x1800090d0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800090d6  test    ebx, ebx
0x1800090d8  jns     short loc_1800090E1
0x1800090da  mov     rax, [rdi+20h]
0x1800090de  mov     [rax+10h], ebx
0x1800090e1  mov     eax, ebx
0x1800090e3  mov     rbx, [rsp+68h+arg_0]
0x1800090e8  add     rsp, 40h
0x1800090ec  pop     r15
0x1800090ee  pop     r14
0x1800090f0  pop     rdi
0x1800090f1  pop     rsi
0x1800090f2  pop     rbp
0x1800090f3  retn
```
