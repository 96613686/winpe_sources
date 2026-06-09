# CACSecurityPage::DisplayCiphersForIHVAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *,int)

- ea: `0x1800078f4`
- end: `0x180007adb`
- name: `?DisplayCiphersForIHVAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@H@Z`
- size: `487`
- prototype: `void __fastcall(CACSecurityPage *__hidden this, struct _AUI_AUTH_INFO *, int, struct _AUI_CIPHER_INFO *, int)`
- caller_count: `6`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007ae4`
- `0x180008720`
- `0x180009dd0`
- `0x18000b6f8`
- `0x18000bb54`
- `0x18000bd88`

## callees

- `0x180001d8c`
- `0x180001e26`
- `0x180005e64`
- `0x1800060d4`
- `0x180007404`
- `0x1800078f4`
- `0x18001bf0a`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007a83`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007a83`
- `USER32!SendMessageW` at `0x180007930`
- `USER32!SendMessageW` at `0x180007930`

## pseudocode

```c
void __fastcall CACSecurityPage::DisplayCiphersForIHVAuth(
        HWND *this,
        struct _AUI_AUTH_INFO *a2,
        int a3,
        struct _AUI_CIPHER_INFO *a4,
        int a5)
{
  HWND v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rbx
  unsigned int v13; // r12d
  int v14; // r14d
  struct _AUI_CIPHER_INFO *CipherInfo; // rax
  LPARAM v16; // rsi
  __int64 v17; // rdx
  _WORD *v18; // rdi
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rax
  void *v22; // r15
  __int64 v23; // r8
  __int64 v24; // r8
  int v25; // edx
  unsigned int v26; // ecx
  int v27; // eax

  if ( !a5 )
    SendMessageW(this[9], 0x14Bu, 0, 0);
  v7 = this[154];
  if ( *((_DWORD *)a2 + 2) )
    v8 = *((_QWORD *)v7 + 5);
  else
    v8 = *((_QWORD *)v7 + 4);
  v9 = *((_DWORD *)a2 + 4);
  if ( v9 )
    v10 = (unsigned int)(v9 - *(_DWORD *)(v8 + 36));
  else
    v10 = 0;
  v11 = *(_QWORD *)(v8 + 24);
  if ( v11 )
    v12 = *(_QWORD *)(v11 + 8 * v10);
  else
    v12 = 0;
  if ( v12 )
  {
    v13 = *(_DWORD *)(v12 + 16);
    v14 = 0;
    if ( v13 )
    {
      while ( 1 )
      {
        CipherInfo = CACSecurityPage::CreateCipherInfo((CACSecurityPage *)v8, v14 + *(_DWORD *)(v12 + 24), 0);
        v16 = (LPARAM)CipherInfo;
        if ( !CipherInfo )
          return;
        v8 = (unsigned int)(*((_DWORD *)CipherInfo + 1) - *(_DWORD *)(v12 + 24));
        if ( (unsigned int)v8 < *(_DWORD *)(v12 + 16) )
        {
          v17 = *(_QWORD *)(v12 + 8);
          if ( v17 )
          {
            v18 = *(_WORD **)(v17 + 16LL * (unsigned int)v8 + 8);
            if ( v18 )
            {
              v19 = -1;
              do
                ++v19;
              while ( v18[v19] );
              v20 = v19 + 1;
              v21 = 2 * v20;
              if ( !is_mul_ok(v20, 2u) )
                v21 = -1;
              v22 = operator new[](v21, (const struct std::nothrow_t *)&std::nothrow);
              if ( v22 )
                break;
            }
          }
        }
LABEL_38:
        if ( ++v14 >= v13 )
          return;
      }
      v23 = -1;
      do
        ++v23;
      while ( v18[v23] );
      memset_0(v22, 0, v23 + 1);
      v24 = -1;
      do
        ++v24;
      while ( v18[v24] );
      memcpy_0(v22, v18, 2 * v24 + 2);
      v25 = ComboBox_AddItem(this[9], (LPARAM)v22, v16);
      if ( a3 )
      {
        if ( !a4 || *(_DWORD *)(v16 + 4) != *((_DWORD *)a4 + 1) )
          goto LABEL_31;
      }
      else
      {
        if ( a5 )
          goto LABEL_31;
        v26 = *(_DWORD *)(v12 + 20);
        v27 = v26 < *(_DWORD *)(v12 + 16) ? v26 + *(_DWORD *)(v12 + 24) : 0;
        if ( *(_DWORD *)(v16 + 4) != v27 )
          goto LABEL_31;
      }
      ComboBox_SetCurSelNotify(this[9], v25);
LABEL_31:
      operator delete(v22);
      goto LABEL_38;
    }
  }
}

```

## disassembly

```asm
0x1800078f4  mov     rax, rsp
0x1800078f7  mov     [rax+8], rbx
0x1800078fb  mov     [rax+10h], rbp
0x1800078ff  mov     [rax+20h], r9
0x180007903  mov     [rax+18h], r8d
0x180007907  push    rsi
0x180007908  push    rdi
0x180007909  push    r12
0x18000790b  push    r14
0x18000790d  push    r15
0x18000790f  sub     rsp, 20h
0x180007913  xor     edi, edi
0x180007915  mov     rbx, rdx
0x180007918  mov     rbp, rcx
0x18000791b  cmp     [rsp+48h+arg_20], edi
0x18000791f  jnz     short loc_180007936
0x180007921  mov     rcx, [rcx+48h]; hWnd
0x180007925  xor     r9d, r9d; lParam
0x180007928  xor     r8d, r8d; wParam
0x18000792b  mov     edx, 14Bh; Msg
0x180007930  call    cs:__imp_SendMessageW
0x180007936  mov     rax, [rbp+4D0h]
0x18000793d  cmp     [rbx+8], edi
0x180007940  jz      short loc_180007948
0x180007942  mov     rcx, [rax+28h]
0x180007946  jmp     short loc_18000794C
0x180007948  mov     rcx, [rax+20h]; this
0x18000794c  mov     eax, [rbx+10h]
0x18000794f  test    eax, eax
0x180007951  jz      short loc_180007958
0x180007953  sub     eax, [rcx+24h]
0x180007956  jmp     short loc_18000795A
0x180007958  mov     eax, edi
0x18000795a  mov     rbx, [rcx+18h]
0x18000795e  test    rbx, rbx
0x180007961  jnz     short loc_180007968
0x180007963  mov     rbx, rdi
0x180007966  jmp     short loc_18000796C
0x180007968  mov     rbx, [rbx+rax*8]
0x18000796c  test    rbx, rbx
0x18000796f  jz      loc_180007AC4
0x180007975  mov     r12d, [rbx+10h]
0x180007979  mov     r14d, edi
0x18000797c  test    r12d, r12d
0x18000797f  jz      loc_180007AC4
0x180007985  or      r15, 0FFFFFFFFFFFFFFFFh
0x180007989  mov     edx, [rbx+18h]
0x18000798c  xor     r8d, r8d; int
0x18000798f  add     edx, r14d; unsigned int
0x180007992  call    ?CreateCipherInfo@CACSecurityPage@@AEAAPEAU_AUI_CIPHER_INFO@@KH@Z; CACSecurityPage::CreateCipherInfo(ulong,int)
0x180007997  mov     rsi, rax
0x18000799a  test    rax, rax
0x18000799d  jz      loc_180007AC4
0x1800079a3  mov     ecx, [rax+4]
0x1800079a6  sub     ecx, [rbx+18h]
0x1800079a9  cmp     ecx, [rbx+10h]
0x1800079ac  jnb     loc_180007AB8
0x1800079b2  mov     rdx, [rbx+8]
0x1800079b6  test    rdx, rdx
0x1800079b9  jz      loc_180007AB8
0x1800079bf  mov     eax, ecx
0x1800079c1  add     rax, rax
0x1800079c4  mov     rdi, [rdx+rax*8+8]
0x1800079c9  xor     eax, eax
0x1800079cb  test    rdi, rdi
0x1800079ce  jz      loc_180007AB8
0x1800079d4  mov     rcx, r15
0x1800079d7  inc     rcx
0x1800079da  cmp     [rdi+rcx*2], ax
0x1800079de  jnz     short loc_1800079D7
0x1800079e0  inc     rcx
0x1800079e3  mov     eax, 2
0x1800079e8  mul     rcx
0x1800079eb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800079f2  cmovb   rax, r15
0x1800079f6  mov     rcx, rax; unsigned __int64
0x1800079f9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800079fe  mov     r15, rax
0x180007a01  xor     eax, eax
0x180007a03  test    r15, r15
0x180007a06  jz      loc_180007AB2
0x180007a0c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007a10  inc     r8
0x180007a13  cmp     [rdi+r8*2], ax
0x180007a18  jnz     short loc_180007A10
0x180007a1a  inc     r8; Size
0x180007a1d  xor     edx, edx; Val
0x180007a1f  mov     rcx, r15; void *
0x180007a22  call    memset_0
0x180007a27  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007a2b  xor     eax, eax
0x180007a2d  inc     r8
0x180007a30  cmp     [rdi+r8*2], ax
0x180007a35  jnz     short loc_180007A2D
0x180007a37  lea     r8, ds:2[r8*2]; Size
0x180007a3f  mov     rdx, rdi; Src
0x180007a42  mov     rcx, r15; void *
0x180007a45  call    memcpy_0
0x180007a4a  mov     rcx, [rbp+48h]; hWnd
0x180007a4e  mov     r8, rsi; LPARAM
0x180007a51  mov     rdx, r15; lParam
0x180007a54  call    ?ComboBox_AddItem@@YAHPEAUHWND__@@PEBGPEAX@Z; ComboBox_AddItem(HWND__ *,ushort const *,void *)
0x180007a59  xor     edi, edi
0x180007a5b  mov     edx, eax; int
0x180007a5d  cmp     [rsp+48h+arg_10], edi
0x180007a61  jz      short loc_180007A8B
0x180007a63  mov     rdi, [rsp+48h+arg_18]
0x180007a68  test    rdi, rdi
0x180007a6b  jz      short loc_180007A7E
0x180007a6d  mov     ecx, [rdi+4]
0x180007a70  cmp     [rsi+4], ecx
0x180007a73  jnz     short loc_180007A7E
0x180007a75  mov     rcx, [rbp+48h]; hWnd
0x180007a79  call    ?ComboBox_SetCurSelNotify@@YAXPEAUHWND__@@H@Z; ComboBox_SetCurSelNotify(HWND__ *,int)
0x180007a7e  xor     edi, edi
0x180007a80  mov     rcx, r15
0x180007a83  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007a89  jmp     short loc_180007AB4
0x180007a8b  cmp     [rsp+48h+arg_20], edi
0x180007a8f  jnz     short loc_180007A80
0x180007a91  mov     ecx, [rbx+14h]
0x180007a94  cmp     ecx, [rbx+10h]
0x180007a97  jb      short loc_180007A9D
0x180007a99  mov     eax, edi
0x180007a9b  jmp     short loc_180007AA2
0x180007a9d  mov     eax, [rbx+18h]
0x180007aa0  add     eax, ecx
0x180007aa2  cmp     [rsi+4], eax
0x180007aa5  jnz     short loc_180007A80
0x180007aa7  mov     rcx, [rbp+48h]; hWnd
0x180007aab  call    ?ComboBox_SetCurSelNotify@@YAXPEAUHWND__@@H@Z; ComboBox_SetCurSelNotify(HWND__ *,int)
0x180007ab0  jmp     short loc_180007A80
0x180007ab2  xor     edi, edi
0x180007ab4  or      r15, 0FFFFFFFFFFFFFFFFh
0x180007ab8  inc     r14d
0x180007abb  cmp     r14d, r12d
0x180007abe  jb      loc_180007989
0x180007ac4  mov     rbx, [rsp+48h+arg_0]
0x180007ac9  mov     rbp, [rsp+48h+arg_8]
0x180007ace  add     rsp, 20h
0x180007ad2  pop     r15
0x180007ad4  pop     r14
0x180007ad6  pop     r12
0x180007ad8  pop     rdi
0x180007ad9  pop     rsi
0x180007ada  retn
```
