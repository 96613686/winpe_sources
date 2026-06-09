# CACSecurityPage::DisplayCiphersForMSAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *)

- ea: `0x180007ae4`
- end: `0x180007dea`
- name: `?DisplayCiphersForMSAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@@Z`
- size: `774`
- prototype: `void __fastcall(CACSecurityPage *__hidden this, struct _AUI_AUTH_INFO *, int, struct _AUI_CIPHER_INFO *)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180008720`
- `0x180009dd0`
- `0x18000b6f8`
- `0x18000bb54`
- `0x18000bd88`

## callees

- `0x180005e64`
- `0x1800060a0`
- `0x1800060d4`
- `0x180006f98`
- `0x180007404`
- `0x1800078f4`
- `0x180007ae4`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180007b4f`
- `KERNEL32!GetProcessHeap` at `0x180007b4f`
- `KERNEL32!HeapFree` at `0x180007b5d`
- `KERNEL32!HeapFree` at `0x180007b5d`
- `USER32!LoadStringW` at `0x180007c22`
- `USER32!LoadStringW` at `0x180007c22`
- `USER32!SendMessageW` at `0x180007b2e`
- `USER32!SendMessageW` at `0x180007b80`
- `USER32!SendMessageW` at `0x180007b2e`
- `USER32!SendMessageW` at `0x180007b80`

## pseudocode

```c
void __fastcall CACSecurityPage::DisplayCiphersForMSAuth(
        CACSecurityPage *this,
        struct _AUI_AUTH_INFO *a2,
        int a3,
        struct _AUI_CIPHER_INFO *a4)
{
  int v5; // r15d
  struct _AUI_AUTH_INFO *v6; // r13
  int v8; // ebx
  int v9; // esi
  int v10; // ebp
  void *ItemDataPtr; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v13; // rcx
  int v14; // ebp
  __int64 v15; // r12
  int v16; // eax
  __int64 v17; // r8
  int v18; // r9d
  unsigned int v19; // ebx
  UINT v20; // edx
  struct _AUI_CIPHER_INFO *CipherInfo; // rax
  int v22; // eax
  __int64 v23; // rax
  BOOL v24; // r8d
  __int64 v25; // r8
  int v26; // edx
  unsigned int v27; // [rsp+30h] [rbp-48h]
  int v28; // [rsp+80h] [rbp+8h]

  v5 = a3;
  v27 = *((_DWORD *)a2 + 1);
  v6 = a2;
  v8 = -1;
  v28 = -1;
  v9 = 0;
  v10 = SendMessageW(*((HWND *)this + 9), 0x146u, 0, 0);
  if ( v10 > 0 )
  {
    do
    {
      ItemDataPtr = ComboBox_GetItemDataPtr(*((HWND *)this + 9), v9);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, ItemDataPtr);
      ++v9;
    }
    while ( v9 < v10 );
    v8 = -1;
  }
  SendMessageW(*((HWND *)this + 9), 0x14Bu, 0, 0);
  if ( **((_DWORD **)this + 3) )
  {
    v14 = 0;
    v15 = 0;
    while ( 1 )
    {
      v16 = CACSecurityPage::AUIAuth2Auth(v13, v27);
      if ( *(_DWORD *)(v17 + 8 * v15 + 4) != v16 )
        goto LABEL_35;
      v19 = *(_DWORD *)(v17 + 8 * v15 + 8);
      v13 = (__int64)hInstance;
      switch ( v19 )
      {
        case 0u:
          v20 = 17200;
          goto LABEL_22;
        case 1u:
          v20 = 17202;
          goto LABEL_22;
        case 2u:
          v20 = 17204;
          goto LABEL_22;
        case 4u:
          goto LABEL_18;
        case 5u:
          v20 = 17203;
          goto LABEL_22;
        case 8u:
LABEL_18:
          v20 = 17205;
          goto LABEL_22;
      }
      if ( v19 == 9 )
        break;
      if ( v19 == 257 )
      {
        v20 = 17201;
LABEL_22:
        LoadStringW(hInstance, v20, (LPWSTR)this + 48, v18);
      }
      if ( this == (CACSecurityPage *)-96LL || v27 == 0x7FFFFFFF && !v19 )
        goto LABEL_34;
      v13 = 1;
      if ( ((unsigned int)(*((_DWORD *)this + 329) - 6) > 1 || *((_DWORD *)this + 330) != 2) && v27 - 6 <= 1 && v19 == 2 )
        goto LABEL_34;
      CipherInfo = CACSecurityPage::CreateCipherInfo((CACSecurityPage *)1, v19, 1);
      v22 = ComboBox_AddItem(*((HWND *)this + 9), (LPARAM)this + 96, (LPARAM)CipherInfo);
      if ( a3 && a4 && v19 == *((_DWORD *)a4 + 1) )
      {
        ComboBox_SetCurSelNotify(*((HWND *)this + 9), v22);
LABEL_34:
        v8 = v28;
        goto LABEL_35;
      }
      v8 = v28;
      v25 = *((_QWORD *)this + 3);
      if ( v28 < 0 )
        goto LABEL_65;
      v13 = *(unsigned int *)(v25 + 8 * v15 + 8);
      if ( (_DWORD)v13 == v14 )
        goto LABEL_35;
      v26 = 0;
      if ( !(_DWORD)v13 )
        goto LABEL_35;
      v13 = (unsigned int)(v13 - 1);
      if ( (_DWORD)v13 )
      {
        v13 = (unsigned int)(v13 - 1);
        if ( (_DWORD)v13 )
        {
          v13 = (unsigned int)(v13 - 2);
          if ( !(_DWORD)v13 )
            goto LABEL_65;
          v13 = (unsigned int)(v13 - 1);
          if ( (_DWORD)v13 )
          {
            if ( (_DWORD)v13 == 252 )
              v26 = v14 != 0 ? -1 : 1;
          }
          else
          {
            if ( ((v14 - 2) & 0xFFFFFFFD) != 0 )
              goto LABEL_65;
            v26 = -1;
          }
        }
        else
        {
          v26 = -1;
          if ( v14 != 4 )
            v26 = 1;
        }
      }
      else
      {
        if ( v14 != 257 && v14 )
          goto LABEL_35;
        v26 = 1;
      }
      if ( v26 > 0 )
      {
LABEL_65:
        v14 = *(_DWORD *)(v25 + 8 * v15 + 8);
        v8 = v22;
        v28 = v22;
      }
LABEL_35:
      v15 = (unsigned int)(v15 + 1);
      if ( (unsigned int)v15 >= **((_DWORD **)this + 3) )
      {
        v6 = a2;
        v5 = a3;
        goto LABEL_37;
      }
    }
    v20 = 17329;
    goto LABEL_22;
  }
LABEL_37:
  v23 = *((_QWORD *)this + 154);
  if ( v23 && *(_DWORD *)(v23 + 52) && *((_DWORD *)v6 + 3) )
  {
    v24 = *(_DWORD *)v6 == 0;
    if ( a4 && !*(_DWORD *)a4 )
      v24 = 1;
    CACSecurityPage::DisplayCiphersForIHVAuth(this, v6, v24, a4, 1);
  }
  if ( !v5 )
    ComboBox_SetCurSelNotify(*((HWND *)this + 9), v8);
}

```

## disassembly

```asm
0x180007ae4  mov     [rsp+arg_18], rbx
0x180007ae9  mov     [rsp+arg_10], r8d
0x180007aee  mov     [rsp+arg_8], rdx
0x180007af3  push    rbp
0x180007af4  push    rsi
0x180007af5  push    rdi
0x180007af6  push    r12
0x180007af8  push    r13
0x180007afa  push    r14
0x180007afc  push    r15
0x180007afe  sub     rsp, 40h
0x180007b02  mov     eax, [rdx+4]
0x180007b05  mov     r14, r9
0x180007b08  mov     r15d, r8d
0x180007b0b  mov     [rsp+78h+var_48], eax
0x180007b0f  mov     r13, rdx
0x180007b12  mov     rdi, rcx
0x180007b15  mov     rcx, [rcx+48h]; hWnd
0x180007b19  or      ebx, 0FFFFFFFFh
0x180007b1c  xor     r9d, r9d; lParam
0x180007b1f  mov     [rsp+78h+arg_0], ebx
0x180007b26  xor     r8d, r8d; wParam
0x180007b29  mov     edx, 146h; Msg
0x180007b2e  call    cs:__imp_SendMessageW
0x180007b34  xor     esi, esi
0x180007b36  lea     r12d, [rbx+2]
0x180007b3a  mov     rbp, rax
0x180007b3d  test    eax, eax
0x180007b3f  jle     short loc_180007B71
0x180007b41  mov     rcx, [rdi+48h]; HWND
0x180007b45  mov     edx, esi; int
0x180007b47  call    ?ComboBox_GetItemDataPtr@@YAPEAXPEAUHWND__@@H@Z; ComboBox_GetItemDataPtr(HWND__ *,int)
0x180007b4c  mov     rbx, rax
0x180007b4f  call    cs:__imp_GetProcessHeap
0x180007b55  mov     r8, rbx; lpMem
0x180007b58  xor     edx, edx; dwFlags
0x180007b5a  mov     rcx, rax; hHeap
0x180007b5d  call    cs:__imp_HeapFree
0x180007b63  add     esi, r12d
0x180007b66  cmp     esi, ebp
0x180007b68  jl      short loc_180007B41
0x180007b6a  mov     ebx, [rsp+78h+arg_0]
0x180007b71  mov     rcx, [rdi+48h]; hWnd
0x180007b75  xor     r9d, r9d; lParam
0x180007b78  xor     r8d, r8d; wParam
0x180007b7b  mov     edx, 14Bh; Msg
0x180007b80  call    cs:__imp_SendMessageW
0x180007b86  mov     r8, [rdi+18h]
0x180007b8a  cmp     dword ptr [r8], 0
0x180007b8e  jbe     loc_180007CE1
0x180007b94  mov     r13d, [rsp+78h+var_48]
0x180007b99  xor     ebp, ebp
0x180007b9b  xor     r12d, r12d
0x180007b9e  mov     r9d, 100h
0x180007ba4  mov     edx, r13d
0x180007ba7  call    ?AUIAuth2Auth@CACSecurityPage@@AEAA?AW4_DOT11_AUTH_ALGORITHM@@W4AUI_DOT11_AUTH_ALGORITHM@@@Z; CACSecurityPage::AUIAuth2Auth(AUI_DOT11_AUTH_ALGORITHM)
0x180007bac  cmp     [r8+r12*8+4], eax
0x180007bb1  jnz     loc_180007CB5
0x180007bb7  mov     ebx, [r8+r12*8+8]
0x180007bbc  mov     edx, ebx
0x180007bbe  mov     rcx, cs:hInstance; hInstance
0x180007bc5  test    ebx, ebx
0x180007bc7  jz      short loc_180007C19
0x180007bc9  sub     edx, 1
0x180007bcc  jz      short loc_180007C12
0x180007bce  sub     edx, 1
0x180007bd1  jz      short loc_180007C0B
0x180007bd3  sub     edx, 2
0x180007bd6  jz      short loc_180007C04
0x180007bd8  sub     edx, 1
0x180007bdb  jz      short loc_180007BFD
0x180007bdd  sub     edx, 3
0x180007be0  jz      short loc_180007C04
0x180007be2  sub     edx, 1
0x180007be5  jz      short loc_180007BF6
0x180007be7  cmp     edx, 0F8h
0x180007bed  jnz     short loc_180007C28
0x180007bef  mov     edx, 4331h
0x180007bf4  jmp     short loc_180007C1E
0x180007bf6  mov     edx, 43B1h
0x180007bfb  jmp     short loc_180007C1E
0x180007bfd  mov     edx, 4333h
0x180007c02  jmp     short loc_180007C1E
0x180007c04  mov     edx, 4335h
0x180007c09  jmp     short loc_180007C1E
0x180007c0b  mov     edx, 4334h
0x180007c10  jmp     short loc_180007C1E
0x180007c12  mov     edx, 4332h
0x180007c17  jmp     short loc_180007C1E
0x180007c19  mov     edx, 4330h; uID
0x180007c1e  lea     r8, [rdi+60h]; lpBuffer
0x180007c22  call    cs:__imp_LoadStringW
0x180007c28  lea     rsi, [rdi+60h]
0x180007c2c  test    rsi, rsi
0x180007c2f  jz      short loc_180007CAE
0x180007c31  cmp     r13d, 7FFFFFFFh
0x180007c38  jnz     short loc_180007C3E
0x180007c3a  test    ebx, ebx
0x180007c3c  jz      short loc_180007CAE
0x180007c3e  mov     eax, [rdi+524h]
0x180007c44  mov     ecx, 1; this
0x180007c49  sub     eax, 6
0x180007c4c  cmp     eax, ecx
0x180007c4e  ja      short loc_180007C59
0x180007c50  cmp     dword ptr [rdi+528h], 2
0x180007c57  jz      short loc_180007C66
0x180007c59  lea     eax, [r13-6]
0x180007c5d  cmp     eax, ecx
0x180007c5f  ja      short loc_180007C66
0x180007c61  cmp     ebx, 2
0x180007c64  jz      short loc_180007CAE
0x180007c66  mov     r8d, ecx; int
0x180007c69  mov     edx, ebx; unsigned int
0x180007c6b  call    ?CreateCipherInfo@CACSecurityPage@@AEAAPEAU_AUI_CIPHER_INFO@@KH@Z; CACSecurityPage::CreateCipherInfo(ulong,int)
0x180007c70  mov     rcx, [rdi+48h]; hWnd
0x180007c74  mov     r8, rax; LPARAM
0x180007c77  mov     rdx, rsi; lParam
0x180007c7a  call    ?ComboBox_AddItem@@YAHPEAUHWND__@@PEBGPEAX@Z; ComboBox_AddItem(HWND__ *,ushort const *,void *)
0x180007c7f  cmp     [rsp+78h+arg_10], 0
0x180007c87  mov     r9d, eax
0x180007c8a  jz      loc_180007D4D
0x180007c90  test    r14, r14
0x180007c93  jz      loc_180007D4D
0x180007c99  cmp     ebx, [r14+4]
0x180007c9d  jnz     loc_180007D4D
0x180007ca3  mov     rcx, [rdi+48h]; hWnd
0x180007ca7  mov     edx, eax; int
0x180007ca9  call    ?ComboBox_SetCurSelNotify@@YAXPEAUHWND__@@H@Z; ComboBox_SetCurSelNotify(HWND__ *,int)
0x180007cae  mov     ebx, [rsp+78h+arg_0]
0x180007cb5  mov     r8, [rdi+18h]
0x180007cb9  inc     r12d
0x180007cbc  mov     r9d, 100h
0x180007cc2  cmp     r12d, [r8]
0x180007cc5  jb      loc_180007BA4
0x180007ccb  mov     r13, [rsp+78h+arg_8]
0x180007cd3  mov     r12d, 1
0x180007cd9  mov     r15d, [rsp+78h+arg_10]
0x180007ce1  mov     rax, [rdi+4D0h]
0x180007ce8  test    rax, rax
0x180007ceb  jz      short loc_180007D25
0x180007ced  cmp     dword ptr [rax+34h], 0
0x180007cf1  jz      short loc_180007D25
0x180007cf3  cmp     dword ptr [r13+0Ch], 0
0x180007cf8  jz      short loc_180007D25
0x180007cfa  xor     r8d, r8d
0x180007cfd  cmp     [r13+0], r8d
0x180007d01  setz    r8b
0x180007d05  test    r14, r14
0x180007d08  jz      short loc_180007D12
0x180007d0a  cmp     dword ptr [r14], 0
0x180007d0e  cmovz   r8d, r12d; int
0x180007d12  mov     r9, r14; struct _AUI_CIPHER_INFO *
0x180007d15  mov     [rsp+78h+var_58], r12d; int
0x180007d1a  mov     rdx, r13; struct _AUI_AUTH_INFO *
0x180007d1d  mov     rcx, rdi; this
0x180007d20  call    ?DisplayCiphersForIHVAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@H@Z; CACSecurityPage::DisplayCiphersForIHVAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *,int)
0x180007d25  test    r15d, r15d
0x180007d28  jnz     short loc_180007D35
0x180007d2a  mov     rcx, [rdi+48h]; hWnd
0x180007d2e  mov     edx, ebx; int
0x180007d30  call    ?ComboBox_SetCurSelNotify@@YAXPEAUHWND__@@H@Z; ComboBox_SetCurSelNotify(HWND__ *,int)
0x180007d35  mov     rbx, [rsp+78h+arg_18]
0x180007d3d  add     rsp, 40h
0x180007d41  pop     r15
0x180007d43  pop     r14
0x180007d45  pop     r13
0x180007d47  pop     r12
0x180007d49  pop     rdi
0x180007d4a  pop     rsi
0x180007d4b  pop     rbp
0x180007d4c  retn
0x180007d4d  mov     ebx, [rsp+78h+arg_0]
0x180007d54  mov     r8, [rdi+18h]
0x180007d58  test    ebx, ebx
0x180007d5a  js      short loc_180007DD6
0x180007d5c  mov     ecx, [r8+r12*8+8]
0x180007d61  cmp     ecx, ebp
0x180007d63  jz      loc_180007CB5
0x180007d69  xor     edx, edx
0x180007d6b  test    ecx, ecx
0x180007d6d  jz      loc_180007CB5
0x180007d73  sub     ecx, 1
0x180007d76  jz      short loc_180007DB9
0x180007d78  sub     ecx, 1
0x180007d7b  jz      short loc_180007DAB
0x180007d7d  sub     ecx, 2
0x180007d80  jz      short loc_180007DD6
0x180007d82  sub     ecx, 1
0x180007d85  jz      short loc_180007D9C
0x180007d87  cmp     ecx, 0FCh
0x180007d8d  jnz     short loc_180007DCE
0x180007d8f  mov     eax, ebp
0x180007d91  neg     eax
0x180007d93  sbb     edx, edx
0x180007d95  and     edx, 0FFFFFFFEh
0x180007d98  inc     edx
0x180007d9a  jmp     short loc_180007DCE
0x180007d9c  lea     eax, [rbp-2]
0x180007d9f  test    eax, 0FFFFFFFDh
0x180007da4  jnz     short loc_180007DD6
0x180007da6  or      edx, 0FFFFFFFFh
0x180007da9  jmp     short loc_180007DCE
0x180007dab  or      edx, 0FFFFFFFFh
0x180007dae  cmp     ebp, 4
0x180007db1  lea     eax, [rdx+2]
0x180007db4  cmovnz  edx, eax
0x180007db7  jmp     short loc_180007DCE
0x180007db9  cmp     ebp, 101h
0x180007dbf  jz      short loc_180007DC9
0x180007dc1  test    ebp, ebp
0x180007dc3  jnz     loc_180007CB5
0x180007dc9  mov     edx, 1
0x180007dce  test    edx, edx
0x180007dd0  jle     loc_180007CB5
0x180007dd6  mov     ebp, [r8+r12*8+8]
0x180007ddb  mov     ebx, r9d
0x180007dde  mov     [rsp+78h+arg_0], ebx
0x180007de5  jmp     loc_180007CB5
```
