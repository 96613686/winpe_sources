# CCredProvVault::RemoveAllCredentials(void)

- ea: `0x1800bdd90`
- end: `0x1800bde71`
- name: `?RemoveAllCredentials@CCredProvVault@@QEAAKXZ`
- size: `225`
- prototype: `unsigned int __fastcall(CCredProvVault *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800bc7e0`

## callees

- `0x1800bdd90`
- `0x1800bf974`

## import_xrefs

- `ext-ms-win-security-vaultcli-l1-1-0!VaultRemoveItem` at `0x1800bde28`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultRemoveItem` at `0x1800bde28`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x1800bde52`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x1800bde52`
- `ext-ms-win-security-vaultcli-l1-1-1!VaultEnumerateItems` at `0x1800bddc6`
- `ext-ms-win-security-vaultcli-l1-1-1!VaultEnumerateItems` at `0x1800bddc6`

## pseudocode

```c
__int64 __fastcall CCredProvVault::RemoveAllCredentials(CCredProvVault *this)
{
  __int64 v2; // rcx
  unsigned int v3; // ebp
  unsigned int v4; // esi
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // r15
  __int64 v9; // [rsp+30h] [rbp-28h]
  __int64 v10; // [rsp+38h] [rbp-20h]
  unsigned int v11; // [rsp+60h] [rbp+8h] BYREF
  __int64 v12; // [rsp+68h] [rbp+10h] BYREF

  v12 = 0;
  v2 = *(_QWORD *)this;
  v11 = 0;
  v3 = VaultEnumerateItems(v2, 0, &v11, &v12);
  if ( v3 || (v4 = v11, v5 = 0, !v11) )
  {
LABEL_10:
    v6 = v12;
  }
  else
  {
    v6 = v12;
    do
    {
      v7 = *(_QWORD *)(v6 + 80 * v5 + 24);
      if ( *(_DWORD *)(v7 + 8) == 7 && !wcscmp_0(*(const wchar_t **)(v7 + 16), L"WinBio CredProv Resource") )
      {
        v3 = VaultRemoveItem(
               *(_QWORD *)this,
               &CCredProvVault::_guidSchema,
               v7,
               *(_QWORD *)(v6 + 80 * v5 + 32),
               0,
               0,
               v9,
               v10);
        if ( v3 )
          goto LABEL_10;
        v6 = v12;
        v4 = v11;
      }
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (unsigned int)v5 < v4 );
  }
  if ( v6 )
    VaultFree(v6);
  return v3;
}

```

## disassembly

```asm
0x1800bdd90  mov     rax, rsp
0x1800bdd93  mov     [rax+18h], rbx
0x1800bdd97  mov     [rax+20h], rbp
0x1800bdd9b  push    rsi
0x1800bdd9c  push    rdi
0x1800bdd9d  push    r12
0x1800bdd9f  push    r14
0x1800bdda1  push    r15
0x1800bdda3  sub     rsp, 30h
0x1800bdda7  mov     r12, rcx
0x1800bddaa  mov     qword ptr [rax+10h], 0
0x1800bddb2  mov     rcx, [rcx]
0x1800bddb5  lea     r9, [rax+10h]
0x1800bddb9  lea     r8, [rax+8]
0x1800bddbd  mov     dword ptr [rax+8], 0
0x1800bddc4  xor     edx, edx
0x1800bddc6  call    cs:__imp_VaultEnumerateItems
0x1800bddcc  mov     ebp, eax
0x1800bddce  test    eax, eax
0x1800bddd0  jnz     short loc_1800BDE45
0x1800bddd2  mov     esi, [rsp+58h+arg_0]
0x1800bddd6  xor     edi, edi
0x1800bddd8  test    esi, esi
0x1800bddda  jz      short loc_1800BDE45
0x1800bdddc  mov     rbx, [rsp+58h+arg_8]
0x1800bdde1  lea     r14, [rdi+rdi*4]
0x1800bdde5  add     r14, r14
0x1800bdde8  mov     r15, [rbx+r14*8+18h]
0x1800bdded  cmp     dword ptr [r15+8], 7
0x1800bddf2  jnz     short loc_1800BDE3D
0x1800bddf4  mov     rcx, [r15+10h]; String1
0x1800bddf8  lea     rdx, aWinbioCredprov; "WinBio CredProv Resource"
0x1800bddff  call    wcscmp_0
0x1800bde04  test    eax, eax
0x1800bde06  jnz     short loc_1800BDE3D
0x1800bde08  mov     r9, [rbx+r14*8+20h]
0x1800bde0d  lea     rdx, ?_guidSchema@CCredProvVault@@0U_GUID@@A; _GUID CCredProvVault::_guidSchema
0x1800bde14  mov     rcx, [r12]
0x1800bde18  mov     r8, r15
0x1800bde1b  mov     [rsp+58h+var_30], eax
0x1800bde1f  mov     [rsp+58h+var_38], 0
0x1800bde28  call    cs:__imp_VaultRemoveItem
0x1800bde2e  mov     ebp, eax
0x1800bde30  test    eax, eax
0x1800bde32  jnz     short loc_1800BDE45
0x1800bde34  mov     rbx, [rsp+58h+arg_8]
0x1800bde39  mov     esi, [rsp+58h+arg_0]
0x1800bde3d  inc     edi
0x1800bde3f  cmp     edi, esi
0x1800bde41  jb      short loc_1800BDDE1
0x1800bde43  jmp     short loc_1800BDE4A
0x1800bde45  mov     rbx, [rsp+58h+arg_8]
0x1800bde4a  test    rbx, rbx
0x1800bde4d  jz      short loc_1800BDE58
0x1800bde4f  mov     rcx, rbx
0x1800bde52  call    cs:__imp_VaultFree
0x1800bde58  mov     rbx, [rsp+58h+arg_10]
0x1800bde5d  mov     eax, ebp
0x1800bde5f  mov     rbp, [rsp+58h+arg_18]
0x1800bde64  add     rsp, 30h
0x1800bde68  pop     r15
0x1800bde6a  pop     r14
0x1800bde6c  pop     r12
0x1800bde6e  pop     rdi
0x1800bde6f  pop     rsi
0x1800bde70  retn
```
