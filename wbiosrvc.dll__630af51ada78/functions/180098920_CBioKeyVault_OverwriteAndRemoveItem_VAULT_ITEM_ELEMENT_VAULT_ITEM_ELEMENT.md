# CBioKeyVault::_OverwriteAndRemoveItem(_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *)

- ea: `0x180098920`
- end: `0x180098a93`
- name: `?_OverwriteAndRemoveItem@CBioKeyVault@@AEAAJPEAU_VAULT_ITEM_ELEMENT@@0@Z`
- size: `371`
- prototype: `__int64 __fastcall(CBioKeyVault *__hidden this, struct _VAULT_ITEM_ELEMENT *, struct _VAULT_ITEM_ELEMENT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180098854`

## callees

- `0x180011d90`
- `0x18005388c`
- `0x1800538b0`
- `0x180098920`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x1800989b1`
- `bcrypt!BCryptGenRandom` at `0x1800989b1`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultAddItem` at `0x1800989fd`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultAddItem` at `0x1800989fd`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItem` at `0x180098971`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItem` at `0x180098971`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultRemoveItem` at `0x180098a43`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultRemoveItem` at `0x180098a43`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x180098a7b`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x180098a7b`

## string_xrefs

- `0x1800989c0`: `onecore\ds\security\biometrics\service\server\biokeyvault.cpp`
- `0x180098a11`: `onecore\ds\security\biometrics\service\server\biokeyvault.cpp`
- `0x180098a5d`: `onecore\ds\security\biometrics\service\server\biokeyvault.cpp`

## pseudocode

```c
__int64 __fastcall CBioKeyVault::_OverwriteAndRemoveItem(
        CBioKeyVault *this,
        struct _VAULT_ITEM_ELEMENT *a2,
        struct _VAULT_ITEM_ELEMENT *a3)
{
  unsigned int Item; // eax
  __int64 v7; // rdx
  __int64 v8; // rdx
  NTSTATUS v9; // eax
  int v10; // eax
  unsigned int v11; // ebx
  unsigned int v13; // [rsp+20h] [rbp-28h]
  __int64 v14; // [rsp+30h] [rbp-18h]
  __int64 v15; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v17; // [rsp+50h] [rbp+8h] BYREF

  v17 = 0;
  Item = VaultGetItem(*(_QWORD *)this, &CBioKeyVault::_guidSchema, a2, a3, 0, 0, 0, &v17);
  if ( Item )
  {
    v7 = 599;
LABEL_10:
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v7,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biokeyvault.cpp",
            (const char *)Item,
            v13);
    goto LABEL_7;
  }
  v8 = *(_QWORD *)(v17 + 40);
  if ( !v8 || *(_DWORD *)(v8 + 8) != 8 )
  {
    v11 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25C,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biokeyvault.cpp",
      (const char *)0x8000FFFFLL,
      v13);
    goto LABEL_15;
  }
  v9 = BCryptGenRandom(0, *(PUCHAR *)(v8 + 24), *(_DWORD *)(v8 + 16), 2u);
  if ( v9 >= 0 )
  {
    *(_DWORD *)(v17 + 64) = 0;
    Item = VaultAddItem(*(_QWORD *)this, v17, 0, 0, 0);
    if ( Item )
    {
      v7 = 621;
    }
    else
    {
      Item = VaultRemoveItem(*(_QWORD *)this, &CBioKeyVault::_guidSchema, a2, a3, 0, 0, v14, v15);
      if ( !Item )
      {
        v11 = 0;
        goto LABEL_15;
      }
      v7 = 630;
    }
    goto LABEL_10;
  }
  v10 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x263,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biokeyvault.cpp",
          (const char *)(unsigned int)v9,
          v13);
LABEL_7:
  v11 = v10;
LABEL_15:
  VaultFree(v17);
  return v11;
}

```

## disassembly

```asm
0x180098920  mov     r11, rsp
0x180098923  mov     [r11+10h], rbx
0x180098927  mov     [r11+18h], rsi
0x18009892b  push    rdi
0x18009892c  sub     rsp, 40h
0x180098930  lea     rax, [r11+8]
0x180098934  mov     qword ptr [r11+8], 0
0x18009893c  mov     [r11-10h], rax
0x180098940  mov     rdi, r8
0x180098943  mov     r9, r8
0x180098946  mov     dword ptr [rsp+48h+var_18], 0
0x18009894e  mov     rsi, rdx
0x180098951  mov     qword ptr [r11-20h], 0
0x180098959  mov     rbx, rcx
0x18009895c  mov     qword ptr [r11-28h], 0
0x180098964  mov     rcx, [rcx]
0x180098967  mov     r8, rdx
0x18009896a  lea     rdx, ?_guidSchema@CBioKeyVault@@0U_GUID@@A; _GUID CBioKeyVault::_guidSchema
0x180098971  call    cs:__imp_VaultGetItem
0x180098977  test    eax, eax
0x180098979  jz      short loc_180098985
0x18009897b  mov     edx, 257h
0x180098980  jmp     loc_180098A0C
0x180098985  mov     rax, [rsp+48h+arg_0]
0x18009898a  mov     rdx, [rax+28h]
0x18009898e  test    rdx, rdx
0x180098991  jz      loc_180098A58
0x180098997  cmp     dword ptr [rdx+8], 8
0x18009899b  jnz     loc_180098A58
0x1800989a1  mov     r8d, [rdx+10h]; cbBuffer
0x1800989a5  mov     r9d, 2; dwFlags
0x1800989ab  mov     rdx, [rdx+18h]; pbBuffer
0x1800989af  xor     ecx, ecx; hAlgorithm
0x1800989b1  call    cs:__imp_BCryptGenRandom
0x1800989b7  test    eax, eax
0x1800989b9  jns     short loc_1800989DB
0x1800989bb  mov     rcx, [rsp+48h]; this
0x1800989c0  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\biometrics\\serv"...
0x1800989c7  mov     r9d, eax; char *
0x1800989ca  mov     edx, 263h; void *
0x1800989cf  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800989d4  mov     ebx, eax
0x1800989d6  jmp     loc_180098A76
0x1800989db  mov     rax, [rsp+48h+arg_0]
0x1800989e0  xor     r9d, r9d
0x1800989e3  xor     r8d, r8d
0x1800989e6  mov     [rsp+48h+var_28], 0; unsigned int
0x1800989ee  mov     dword ptr [rax+40h], 0
0x1800989f5  mov     rdx, [rsp+48h+arg_0]
0x1800989fa  mov     rcx, [rbx]
0x1800989fd  call    cs:__imp_VaultAddItem
0x180098a03  test    eax, eax
0x180098a05  jz      short loc_180098A22
0x180098a07  mov     edx, 26Dh; void *
0x180098a0c  mov     rcx, [rsp+48h]; this
0x180098a11  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\biometrics\\serv"...
0x180098a18  mov     r9d, eax; char *
0x180098a1b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180098a20  jmp     short loc_1800989D4
0x180098a22  mov     rcx, [rbx]
0x180098a25  lea     rdx, ?_guidSchema@CBioKeyVault@@0U_GUID@@A; _GUID CBioKeyVault::_guidSchema
0x180098a2c  mov     [rsp+48h+var_20], 0
0x180098a34  mov     r9, rdi
0x180098a37  mov     r8, rsi
0x180098a3a  mov     qword ptr [rsp+48h+var_28], 0
0x180098a43  call    cs:__imp_VaultRemoveItem
0x180098a49  test    eax, eax
0x180098a4b  jz      short loc_180098A54
0x180098a4d  mov     edx, 276h
0x180098a52  jmp     short loc_180098A0C
0x180098a54  xor     ebx, ebx
0x180098a56  jmp     short loc_180098A76
0x180098a58  mov     rcx, [rsp+48h]; this
0x180098a5d  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\biometrics\\serv"...
0x180098a64  mov     ebx, 8000FFFFh
0x180098a69  mov     edx, 25Ch; void *
0x180098a6e  mov     r9d, ebx; char *
0x180098a71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098a76  mov     rcx, [rsp+48h+arg_0]
0x180098a7b  call    cs:__imp_VaultFree
0x180098a81  mov     rsi, [rsp+48h+arg_10]
0x180098a86  mov     eax, ebx
0x180098a88  mov     rbx, [rsp+48h+arg_8]
0x180098a8d  add     rsp, 40h
0x180098a91  pop     rdi
0x180098a92  retn
```
