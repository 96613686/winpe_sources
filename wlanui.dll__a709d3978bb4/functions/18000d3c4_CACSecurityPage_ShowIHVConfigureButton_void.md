# CACSecurityPage::ShowIHVConfigureButton(void)

- ea: `0x18000d3c4`
- end: `0x18000d45c`
- name: `?ShowIHVConfigureButton@CACSecurityPage@@AEAAHXZ`
- size: `152`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c824`

## callees

- `0x18000833c`
- `0x180008388`
- `0x18000d3c4`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::ShowIHVConfigureButton(HWND *this)
{
  unsigned int v2; // edi
  struct _AUI_AUTH_INFO *CurrentlySelectedAuth; // rbx
  struct _AUI_CIPHER_INFO *CurrentlySelectedCipher; // rax
  struct _AUI_CIPHER_INFO *v5; // rdx
  BOOL v6; // eax
  HWND v7; // rdx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rax
  _QWORD *v11; // rcx

  v2 = 0;
  CurrentlySelectedAuth = CACSecurityPage::GetCurrentlySelectedAuth(this);
  CurrentlySelectedCipher = CACSecurityPage::GetCurrentlySelectedCipher(this);
  v5 = CurrentlySelectedCipher;
  if ( CurrentlySelectedAuth && CurrentlySelectedCipher )
  {
    v6 = 0;
    if ( *((_DWORD *)CurrentlySelectedAuth + 3) )
      v6 = *(_DWORD *)CurrentlySelectedAuth == 0;
    if ( !*(_DWORD *)v5 || v6 )
    {
      v7 = this[154];
      if ( v7 )
      {
        v8 = *((_DWORD *)CurrentlySelectedAuth + 4);
        v9 = *(_QWORD *)((char *)v7 + (*((_DWORD *)CurrentlySelectedAuth + 2) != 0 ? 8 : 0) + 32);
        if ( v8 )
          v10 = (unsigned int)(v8 - *(_DWORD *)(v9 + 36));
        else
          v10 = 0;
        v11 = *(_QWORD **)(v9 + 24);
        if ( v11 && *v11 )
          return *(unsigned int *)v11[v10];
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000d3c4  mov     [rsp+arg_0], rbx
0x18000d3c9  mov     [rsp+arg_8], rsi
0x18000d3ce  push    rdi
0x18000d3cf  sub     rsp, 20h
0x18000d3d3  mov     rsi, rcx
0x18000d3d6  xor     edi, edi
0x18000d3d8  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x18000d3dd  mov     rcx, rsi; this
0x18000d3e0  mov     rbx, rax
0x18000d3e3  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x18000d3e8  mov     rdx, rax
0x18000d3eb  test    rbx, rbx
0x18000d3ee  jz      short loc_18000D44A
0x18000d3f0  test    rax, rax
0x18000d3f3  jz      short loc_18000D44A
0x18000d3f5  xor     eax, eax
0x18000d3f7  cmp     [rbx+0Ch], eax
0x18000d3fa  jz      short loc_18000D404
0x18000d3fc  cmp     [rbx], eax
0x18000d3fe  lea     ecx, [rdi+1]
0x18000d401  cmovz   eax, ecx
0x18000d404  cmp     [rdx], edi
0x18000d406  jz      short loc_18000D40C
0x18000d408  test    eax, eax
0x18000d40a  jz      short loc_18000D44A
0x18000d40c  mov     rdx, [rsi+4D0h]
0x18000d413  test    rdx, rdx
0x18000d416  jz      short loc_18000D44A
0x18000d418  mov     eax, [rbx+8]
0x18000d41b  neg     eax
0x18000d41d  mov     eax, [rbx+10h]
0x18000d420  sbb     rcx, rcx
0x18000d423  and     ecx, 8
0x18000d426  mov     rcx, [rcx+rdx+20h]
0x18000d42b  test    eax, eax
0x18000d42d  jz      short loc_18000D434
0x18000d42f  sub     eax, [rcx+24h]
0x18000d432  jmp     short loc_18000D436
0x18000d434  xor     eax, eax
0x18000d436  mov     rcx, [rcx+18h]
0x18000d43a  test    rcx, rcx
0x18000d43d  jz      short loc_18000D44A
0x18000d43f  cmp     [rcx], rdi
0x18000d442  jz      short loc_18000D44A
0x18000d444  mov     rcx, [rcx+rax*8]
0x18000d448  mov     edi, [rcx]
0x18000d44a  mov     rbx, [rsp+28h+arg_0]
0x18000d44f  mov     eax, edi
0x18000d451  mov     rsi, [rsp+28h+arg_8]
0x18000d456  add     rsp, 20h
0x18000d45a  pop     rdi
0x18000d45b  retn
```
