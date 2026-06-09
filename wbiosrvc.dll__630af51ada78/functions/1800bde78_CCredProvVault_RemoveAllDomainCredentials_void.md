# CCredProvVault::RemoveAllDomainCredentials(void)

- ea: `0x1800bde78`
- end: `0x1800bdf97`
- name: `?RemoveAllDomainCredentials@CCredProvVault@@QEAAKXZ`
- size: `287`
- prototype: `unsigned int __fastcall(CCredProvVault *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800bc920`

## callees

- `0x180040600`
- `0x1800bbc20`
- `0x1800bde78`
- `0x1800bf974`

## import_xrefs

- `ext-ms-win-security-vaultcli-l1-1-0!VaultRemoveItem` at `0x1800bdf43`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultRemoveItem` at `0x1800bdf43`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x1800bdf6b`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x1800bdf6b`
- `ext-ms-win-security-vaultcli-l1-1-1!VaultEnumerateItems` at `0x1800bdebf`
- `ext-ms-win-security-vaultcli-l1-1-1!VaultEnumerateItems` at `0x1800bdebf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCredProvVault::RemoveAllDomainCredentials(CCredProvVault *this)
{
  unsigned int v2; // r15d
  __int64 v3; // rdi
  unsigned int v4; // esi
  __int64 v5; // rbx
  __int64 v6; // rcx
  CUserContext *v7; // rcx
  __int128 v9; // [rsp+30h] [rbp-20h] BYREF
  int v10; // [rsp+40h] [rbp-10h]
  unsigned int v11; // [rsp+80h] [rbp+30h] BYREF
  __int64 v12; // [rsp+88h] [rbp+38h] BYREF

  v9 = 0;
  v10 = 0;
  v12 = 0;
  v11 = 0;
  v2 = VaultEnumerateItems(*(_QWORD *)this, 0, &v11, &v12);
  if ( !v2 )
  {
    v3 = 0;
    v4 = v11;
    if ( v11 )
    {
      v5 = v12;
      while ( 1 )
      {
        v6 = *(_QWORD *)(v5 + 80 * v3 + 24);
        if ( *(_DWORD *)(v6 + 8) == 7 && !wcscmp_0(*(const wchar_t **)(v6 + 16), L"WinBio CredProv Resource") )
        {
          if ( CUserContext::IsDomainUser(v7, *(void **)(*(_QWORD *)(v5 + 80 * v3 + 32) + 24LL)) )
          {
            v2 = VaultRemoveItem(
                   *(_QWORD *)this,
                   &CCredProvVault::_guidSchema,
                   *(_QWORD *)(v12 + 80 * v3 + 24),
                   *(_QWORD *)(v12 + 80 * v3 + 32),
                   0,
                   0,
                   v9,
                   *((_QWORD *)&v9 + 1));
            if ( v2 )
              break;
          }
          v5 = v12;
          v4 = v11;
        }
        v3 = (unsigned int)(v3 + 1);
        if ( (unsigned int)v3 >= v4 )
          goto LABEL_12;
      }
    }
  }
  v5 = v12;
LABEL_12:
  if ( v5 )
    VaultFree(v5);
  CUserContext::~CUserContext((CUserContext *)&v9);
  return v2;
}

```

## disassembly

```asm
0x1800bde78  mov     [rsp-28h+arg_10], rbx
0x1800bde7d  mov     [rsp-28h+arg_18], rsi
0x1800bde82  push    rbp
0x1800bde83  push    rdi
0x1800bde84  push    r12
0x1800bde86  push    r14
0x1800bde88  push    r15
0x1800bde8a  mov     rbp, rsp
0x1800bde8d  sub     rsp, 50h
0x1800bde91  mov     r12, rcx
0x1800bde94  xorps   xmm0, xmm0
0x1800bde97  movdqu  [rbp+var_20], xmm0
0x1800bde9c  mov     [rbp+var_10], 0
0x1800bdea3  mov     [rbp+arg_8], 0
0x1800bdeab  mov     [rbp+arg_0], 0
0x1800bdeb2  lea     r9, [rbp+arg_8]
0x1800bdeb6  lea     r8, [rbp+arg_0]
0x1800bdeba  xor     edx, edx
0x1800bdebc  mov     rcx, [rcx]
0x1800bdebf  call    cs:__imp_VaultEnumerateItems
0x1800bdec5  mov     r15d, eax
0x1800bdec8  test    eax, eax
0x1800bdeca  jnz     loc_1800BDF5F
0x1800bded0  xor     edi, edi
0x1800bded2  mov     esi, [rbp+arg_0]
0x1800bded5  test    esi, esi
0x1800bded7  jz      loc_1800BDF5F
0x1800bdedd  mov     rbx, [rbp+arg_8]
0x1800bdee1  lea     r14, [rdi+rdi*4]
0x1800bdee5  add     r14, r14
0x1800bdee8  mov     rcx, [rbx+r14*8+18h]
0x1800bdeed  cmp     dword ptr [rcx+8], 7
0x1800bdef1  jnz     short loc_1800BDF57
0x1800bdef3  lea     rdx, aWinbioCredprov; "WinBio CredProv Resource"
0x1800bdefa  mov     rcx, [rcx+10h]; String1
0x1800bdefe  call    wcscmp_0
0x1800bdf03  test    eax, eax
0x1800bdf05  jnz     short loc_1800BDF57
0x1800bdf07  mov     rdx, [rbx+r14*8+20h]
0x1800bdf0c  mov     rdx, [rdx+18h]; void *
0x1800bdf10  call    ?IsDomainUser@CUserContext@@QEBAHPEAX@Z; CUserContext::IsDomainUser(void *)
0x1800bdf15  test    eax, eax
0x1800bdf17  jz      short loc_1800BDF50
0x1800bdf19  mov     r8, [rbp+arg_8]
0x1800bdf1d  mov     [rsp+50h+var_28], 0
0x1800bdf25  mov     [rsp+50h+var_30], 0
0x1800bdf2e  mov     r9, [r8+r14*8+20h]
0x1800bdf33  mov     r8, [r8+r14*8+18h]
0x1800bdf38  lea     rdx, ?_guidSchema@CCredProvVault@@0U_GUID@@A; _GUID CCredProvVault::_guidSchema
0x1800bdf3f  mov     rcx, [r12]
0x1800bdf43  call    cs:__imp_VaultRemoveItem
0x1800bdf49  mov     r15d, eax
0x1800bdf4c  test    eax, eax
0x1800bdf4e  jnz     short loc_1800BDF5F
0x1800bdf50  mov     rbx, [rbp+arg_8]
0x1800bdf54  mov     esi, [rbp+arg_0]
0x1800bdf57  inc     edi
0x1800bdf59  cmp     edi, esi
0x1800bdf5b  jb      short loc_1800BDEE1
0x1800bdf5d  jmp     short loc_1800BDF63
0x1800bdf5f  mov     rbx, [rbp+arg_8]
0x1800bdf63  test    rbx, rbx
0x1800bdf66  jz      short loc_1800BDF72
0x1800bdf68  mov     rcx, rbx
0x1800bdf6b  call    cs:__imp_VaultFree
0x1800bdf71  nop
0x1800bdf72  lea     rcx, [rbp+var_20]; this
0x1800bdf76  call    ??1CUserContext@@QEAA@XZ; CUserContext::~CUserContext(void)
0x1800bdf7b  mov     eax, r15d
0x1800bdf7e  lea     r11, [rsp+50h+var_s0]
0x1800bdf83  mov     rbx, [r11+40h]
0x1800bdf87  mov     rsi, [r11+48h]
0x1800bdf8b  mov     rsp, r11
0x1800bdf8e  pop     r15
0x1800bdf90  pop     r14
0x1800bdf92  pop     r12
0x1800bdf94  pop     rdi
0x1800bdf95  pop     rbp
0x1800bdf96  retn
```
