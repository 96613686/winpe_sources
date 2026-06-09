# CACSecurityPage::ShowAddlSettingButton(void)

- ea: `0x18000cf08`
- end: `0x18000cfaf`
- name: `?ShowAddlSettingButton@CACSecurityPage@@AEAAHXZ`
- size: `167`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c824`

## callees

- `0x18000833c`
- `0x180008388`
- `0x18000cf08`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::ShowAddlSettingButton(HWND *this)
{
  unsigned int v2; // esi
  struct _AUI_AUTH_INFO *CurrentlySelectedAuth; // rdi
  struct _AUI_CIPHER_INFO *CurrentlySelectedCipher; // rdx
  int v5; // eax

  v2 = 0;
  CurrentlySelectedAuth = CACSecurityPage::GetCurrentlySelectedAuth(this);
  CurrentlySelectedCipher = CACSecurityPage::GetCurrentlySelectedCipher(this);
  if ( *(_DWORD *)(*((_QWORD *)this[5] + 69) + 16LL) != 1 || !CurrentlySelectedAuth || !CurrentlySelectedCipher )
    return v2;
  if ( *((_DWORD *)CurrentlySelectedAuth + 2) )
    return 1;
  v5 = *((_DWORD *)CurrentlySelectedAuth + 1);
  if ( v5 == 6 )
    return 1;
  if ( v5 == 7 )
  {
    if ( *((_DWORD *)CurrentlySelectedCipher + 1) == 4 || *((_DWORD *)CurrentlySelectedCipher + 1) == 8 )
      return 1;
    goto LABEL_9;
  }
  if ( v5 != 11 )
  {
LABEL_9:
    if ( v5 == 8 )
    {
      if ( *((_DWORD *)CurrentlySelectedCipher + 1) != 9 )
        return v2;
      return 1;
    }
    goto LABEL_15;
  }
  if ( *((_DWORD *)CurrentlySelectedCipher + 1) == 4 || *((_DWORD *)CurrentlySelectedCipher + 1) == 8 )
    return 1;
LABEL_15:
  if ( v5 == 9 && ((*((_DWORD *)CurrentlySelectedCipher + 1) - 4) & 0xFFFFFFFB) == 0 )
    return 1;
  return v2;
}

```

## disassembly

```asm
0x18000cf08  mov     [rsp+arg_0], rbx
0x18000cf0d  mov     [rsp+arg_8], rsi
0x18000cf12  push    rdi
0x18000cf13  sub     rsp, 20h
0x18000cf17  mov     rbx, rcx
0x18000cf1a  xor     esi, esi
0x18000cf1c  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x18000cf21  mov     rcx, rbx; this
0x18000cf24  mov     rdi, rax
0x18000cf27  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x18000cf2c  mov     rdx, rax
0x18000cf2f  mov     rax, [rbx+28h]
0x18000cf33  mov     rcx, [rax+228h]
0x18000cf3a  cmp     dword ptr [rcx+10h], 1
0x18000cf3e  jnz     short loc_18000CF9D
0x18000cf40  test    rdi, rdi
0x18000cf43  jz      short loc_18000CF9D
0x18000cf45  test    rdx, rdx
0x18000cf48  jz      short loc_18000CF9D
0x18000cf4a  cmp     [rdi+8], esi
0x18000cf4d  jnz     short loc_18000CF98
0x18000cf4f  mov     eax, [rdi+4]
0x18000cf52  cmp     eax, 6
0x18000cf55  jz      short loc_18000CF98
0x18000cf57  cmp     eax, 7
0x18000cf5a  jnz     short loc_18000CF75
0x18000cf5c  cmp     dword ptr [rdx+4], 4
0x18000cf60  jz      short loc_18000CF98
0x18000cf62  cmp     dword ptr [rdx+4], 8
0x18000cf66  jz      short loc_18000CF98
0x18000cf68  cmp     eax, 8
0x18000cf6b  jnz     short loc_18000CF86
0x18000cf6d  cmp     dword ptr [rdx+4], 9
0x18000cf71  jz      short loc_18000CF98
0x18000cf73  jmp     short loc_18000CF9D
0x18000cf75  cmp     eax, 0Bh
0x18000cf78  jnz     short loc_18000CF68
0x18000cf7a  cmp     dword ptr [rdx+4], 4
0x18000cf7e  jz      short loc_18000CF98
0x18000cf80  cmp     dword ptr [rdx+4], 8
0x18000cf84  jz      short loc_18000CF98
0x18000cf86  cmp     eax, 9
0x18000cf89  jnz     short loc_18000CF9D
0x18000cf8b  mov     eax, [rdx+4]
0x18000cf8e  sub     eax, 4
0x18000cf91  test    eax, 0FFFFFFFBh
0x18000cf96  jnz     short loc_18000CF9D
0x18000cf98  mov     esi, 1
0x18000cf9d  mov     rbx, [rsp+28h+arg_0]
0x18000cfa2  mov     eax, esi
0x18000cfa4  mov     rsi, [rsp+28h+arg_8]
0x18000cfa9  add     rsp, 20h
0x18000cfad  pop     rdi
0x18000cfae  retn
```
