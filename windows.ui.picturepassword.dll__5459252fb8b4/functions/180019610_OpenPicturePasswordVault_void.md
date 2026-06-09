# _OpenPicturePasswordVault(void * *)

- ea: `0x180019610`
- end: `0x1800197c4`
- name: `?_OpenPicturePasswordVault@@YAJPEAPEAX@Z`
- size: `436`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018dac`
- `0x180018f10`
- `0x180019274`

## callees

- `0x180002610`
- `0x180019610`

## import_xrefs

- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItemType` at `0x1800196a0`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItemType` at `0x1800196a0`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCloseVault` at `0x18001979b`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCloseVault` at `0x18001979b`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x180019660`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x180019660`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCreateItemType` at `0x180019775`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCreateItemType` at `0x180019775`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x1800196bd`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x1800196bd`

## pseudocode

```c
__int64 __fastcall _OpenPicturePasswordVault(void **a1)
{
  int v2; // eax
  signed int v3; // ebx
  int ItemType; // eax
  int v5; // eax
  void *v7; // [rsp+20h] [rbp-69h] BYREF
  __int64 v8; // [rsp+28h] [rbp-61h] BYREF
  __int128 v9; // [rsp+30h] [rbp-59h] BYREF
  const wchar_t *v10; // [rsp+40h] [rbp-49h]
  int *v11; // [rsp+48h] [rbp-41h]
  int *v12; // [rsp+50h] [rbp-39h]
  int *v13; // [rsp+58h] [rbp-31h]
  __int64 v14; // [rsp+60h] [rbp-29h]
  int *v15; // [rsp+68h] [rbp-21h]
  int v16; // [rsp+70h] [rbp-19h] BYREF
  __int64 v17; // [rsp+74h] [rbp-15h]
  int v18; // [rsp+7Ch] [rbp-Dh]
  int v19; // [rsp+80h] [rbp-9h] BYREF
  __int64 v20; // [rsp+84h] [rbp-5h]
  int v21; // [rsp+8Ch] [rbp+3h]
  int v22; // [rsp+90h] [rbp+7h] BYREF
  __int64 v23; // [rsp+94h] [rbp+Bh]
  int v24; // [rsp+9Ch] [rbp+13h]
  __int128 v25; // [rsp+A0h] [rbp+17h] BYREF
  __int128 v26; // [rsp+B0h] [rbp+27h] BYREF
  int v27; // [rsp+C0h] [rbp+37h] BYREF
  __int64 v28; // [rsp+C4h] [rbp+3Bh]
  int v29; // [rsp+CCh] [rbp+43h]

  *a1 = 0;
  v7 = 0;
  v25 = Vault_DefaultVault_ID;
  v2 = VaultOpenVault(&v25, 0x10000000, &v7);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    v8 = 0;
    v26 = c_guidPicturePasswordVaultSchema;
    ItemType = VaultGetItemType(v7, &v26, 0, &v8);
    v3 = ItemType;
    if ( ItemType > 0 )
      v3 = (unsigned __int16)ItemType | 0x80070000;
    if ( v3 < 0 )
    {
      if ( v3 != -2147023728 )
        goto LABEL_13;
      v17 = 7;
      v13 = &v22;
      v16 = 1;
      v10 = L"Picture Password Vault Resource Schema";
      v11 = &v16;
      v12 = &v19;
      v15 = &v27;
      v18 = 0;
      v19 = 2;
      v20 = 8;
      v21 = 0;
      v22 = 3;
      v23 = 8;
      v24 = 0;
      v27 = 100;
      v28 = 8;
      v29 = 0;
      v9 = c_guidPicturePasswordVaultSchema;
      v14 = 1;
      v5 = VaultCreateItemType(v7, &v9, 0);
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      if ( v3 < 0 )
      {
LABEL_13:
        VaultCloseVault(&v7);
        return (unsigned int)v3;
      }
    }
    else
    {
      VaultFree(v8);
    }
    *a1 = v7;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180019610  mov     [rsp-8+arg_8], rbx
0x180019615  mov     [rsp-8+arg_10], rdi
0x18001961a  push    rbp
0x18001961b  lea     rbp, [rsp-57h]
0x180019620  sub     rsp, 0E0h
0x180019627  mov     rax, cs:__security_cookie
0x18001962e  xor     rax, rsp
0x180019631  mov     [rbp+57h+var_10], rax
0x180019635  movups  xmm0, cs:Vault_DefaultVault_ID
0x18001963c  mov     rdi, rcx
0x18001963f  mov     qword ptr [rcx], 0
0x180019646  lea     r8, [rbp+57h+var_C0]
0x18001964a  mov     [rbp+57h+var_C0], 0
0x180019652  mov     edx, 10000000h
0x180019657  lea     rcx, [rbp+57h+var_40]
0x18001965b  movdqu  [rbp+57h+var_40], xmm0
0x180019660  call    cs:__imp_VaultOpenVault
0x180019666  mov     ebx, eax
0x180019668  test    eax, eax
0x18001966a  jle     short loc_180019675
0x18001966c  movzx   ebx, ax
0x18001966f  or      ebx, 80070000h
0x180019675  test    ebx, ebx
0x180019677  js      loc_1800197A1
0x18001967d  movups  xmm0, cs:c_guidPicturePasswordVaultSchema
0x180019684  mov     rcx, [rbp+57h+var_C0]
0x180019688  lea     r9, [rbp+57h+var_B8]
0x18001968c  xor     r8d, r8d
0x18001968f  mov     [rbp+57h+var_B8], 0
0x180019697  lea     rdx, [rbp+57h+var_30]
0x18001969b  movdqu  [rbp+57h+var_30], xmm0
0x1800196a0  call    cs:__imp_VaultGetItemType
0x1800196a6  mov     ebx, eax
0x1800196a8  test    eax, eax
0x1800196aa  jle     short loc_1800196B5
0x1800196ac  movzx   ebx, ax
0x1800196af  or      ebx, 80070000h
0x1800196b5  test    ebx, ebx
0x1800196b7  js      short loc_1800196C8
0x1800196b9  mov     rcx, [rbp+57h+var_B8]
0x1800196bd  call    cs:__imp_VaultFree
0x1800196c3  jmp     loc_18001978E
0x1800196c8  cmp     ebx, 80070490h
0x1800196ce  jnz     loc_180019797
0x1800196d4  movups  xmm0, cs:c_guidPicturePasswordVaultSchema
0x1800196db  lea     r8, [rbp+57h+var_50]
0x1800196df  mov     [rbp+57h+var_6C], 7
0x1800196e7  mov     r10d, 1
0x1800196ed  mov     [rbp+57h+var_88], r8
0x1800196f1  lea     rax, aPicturePasswor; "Picture Password Vault Resource Schema"
0x1800196f8  mov     [rbp+57h+var_70], r10d
0x1800196fc  lea     rcx, [rbp+57h+var_70]
0x180019700  mov     [rbp+57h+var_A0], rax
0x180019704  lea     rdx, [rbp+57h+var_60]
0x180019708  mov     [rbp+57h+var_98], rcx
0x18001970c  mov     rcx, [rbp+57h+var_C0]
0x180019710  lea     rax, [rbp+57h+var_20]
0x180019714  mov     [rbp+57h+var_90], rdx
0x180019718  xor     r8d, r8d
0x18001971b  lea     rdx, [rbp+57h+var_B0]
0x18001971f  mov     [rbp+57h+var_78], rax
0x180019723  mov     [rbp+57h+var_64], 0
0x18001972a  mov     [rbp+57h+var_60], 2
0x180019731  mov     [rbp+57h+var_5C], 8
0x180019739  mov     [rbp+57h+var_54], 0
0x180019740  mov     [rbp+57h+var_50], 3
0x180019747  mov     [rbp+57h+var_4C], 8
0x18001974f  mov     [rbp+57h+var_44], 0
0x180019756  mov     [rbp+57h+var_20], 64h ; 'd'
0x18001975d  mov     [rbp+57h+var_1C], 8
0x180019765  mov     [rbp+57h+var_14], 0
0x18001976c  movdqu  [rbp+57h+var_B0], xmm0
0x180019771  mov     [rbp+57h+var_80], r10
0x180019775  call    cs:__imp_VaultCreateItemType
0x18001977b  mov     ebx, eax
0x18001977d  test    eax, eax
0x18001977f  jle     short loc_18001978A
0x180019781  movzx   ebx, ax
0x180019784  or      ebx, 80070000h
0x18001978a  test    ebx, ebx
0x18001978c  js      short loc_180019797
0x18001978e  mov     rax, [rbp+57h+var_C0]
0x180019792  mov     [rdi], rax
0x180019795  jmp     short loc_1800197A1
0x180019797  lea     rcx, [rbp+57h+var_C0]
0x18001979b  call    cs:__imp_VaultCloseVault
0x1800197a1  mov     eax, ebx
0x1800197a3  mov     rcx, [rbp+57h+var_10]
0x1800197a7  xor     rcx, rsp; StackCookie
0x1800197aa  call    __security_check_cookie
0x1800197af  lea     r11, [rsp+0E0h+var_s0]
0x1800197b7  mov     rbx, [r11+18h]
0x1800197bb  mov     rdi, [r11+20h]
0x1800197bf  mov     rsp, r11
0x1800197c2  pop     rbp
0x1800197c3  retn
```
