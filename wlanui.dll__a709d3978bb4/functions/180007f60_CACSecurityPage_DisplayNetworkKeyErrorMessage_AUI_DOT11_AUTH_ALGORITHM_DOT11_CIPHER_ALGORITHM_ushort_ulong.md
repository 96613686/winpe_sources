# CACSecurityPage::DisplayNetworkKeyErrorMessage(AUI_DOT11_AUTH_ALGORITHM,_DOT11_CIPHER_ALGORITHM,ushort *,ulong)

- ea: `0x180007f60`
- end: `0x18000806b`
- name: `?DisplayNetworkKeyErrorMessage@CACSecurityPage@@AEAAXW4AUI_DOT11_AUTH_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@PEAGK@Z`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009380`

## callees

- `0x180007f60`
- `0x18000d390`

## import_xrefs

- `USER32!SetTimer` at `0x180008064`
- `USER32!SetDlgItemTextW` at `0x180008011`
- `USER32!SetDlgItemTextW` at `0x180008011`
- `USER32!SetFocus` at `0x18000803d`
- `USER32!SetFocus` at `0x18000803d`
- `USER32!GetDlgItem` at `0x180007fe8`
- `USER32!GetDlgItem` at `0x180008034`
- `USER32!GetDlgItem` at `0x180007fe8`
- `USER32!GetDlgItem` at `0x180008034`

## pseudocode

```c
UINT_PTR __fastcall CACSecurityPage::DisplayNetworkKeyErrorMessage(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  int v5; // r8d
  __int64 v6; // r10
  __int16 v8; // cx
  int v9; // eax
  unsigned int v10; // edi
  int v11; // ebx
  HWND DlgItem; // rax

  v5 = 1;
  v6 = 0;
  if ( a5 )
  {
    while ( 1 )
    {
      v8 = *(_WORD *)(a4 + 2 * v6);
      if ( (unsigned __int16)(v8 - 48) > 9u && (unsigned __int16)(v8 - 65) > 5u && (unsigned __int16)(v8 - 97) > 5u )
        break;
      v6 = (unsigned int)(v6 + 1);
      if ( (unsigned int)v6 >= a5 )
        goto LABEL_8;
    }
    v5 = 0;
  }
LABEL_8:
  if ( a2 <= 9 && (v9 = 656, _bittest(&v9, a2)) )
    v10 = 17306 - (a5 < 8);
  else
    v10 = (v5 != 0) + 17303;
  v11 = (*(_QWORD *)(*(_QWORD *)(a1 + 1328) + 40LL) != (_QWORD)GetDlgItem(*(HWND *)(a1 + 8), 1115)) + 1115;
  SetDlgItemTextW(*(HWND *)(a1 + 8), v11, &String);
  CTooltip::ShowErrBalloon((CTooltip *)(a1 + 608), v11, 0x4394u, v10);
  DlgItem = GetDlgItem(*(HWND *)(a1 + 8), v11);
  SetFocus(DlgItem);
  return SetTimer(*(HWND *)(a1 + 8), 0x3EBu, 0x2710u, 0);
}

```

## disassembly

```asm
0x180007f60  mov     [rsp+arg_0], rbx
0x180007f65  mov     [rsp+arg_8], rsi
0x180007f6a  push    rdi
0x180007f6b  sub     rsp, 20h
0x180007f6f  mov     r11d, [rsp+28h+arg_20]
0x180007f74  mov     r8d, 1
0x180007f7a  xor     r10d, r10d
0x180007f7d  mov     rsi, rcx
0x180007f80  lea     ebx, [r8+8]
0x180007f84  test    r11d, r11d
0x180007f87  jz      short loc_180007FB6
0x180007f89  movzx   ecx, word ptr [r9+r10*2]
0x180007f8e  lea     eax, [rcx-30h]
0x180007f91  cmp     ax, bx
0x180007f94  jbe     short loc_180007FA9
0x180007f96  lea     eax, [rcx-41h]
0x180007f99  cmp     ax, 5
0x180007f9d  jbe     short loc_180007FA9
0x180007f9f  sub     cx, 61h ; 'a'
0x180007fa3  cmp     cx, 5
0x180007fa7  ja      short loc_180007FB3
0x180007fa9  add     r10d, r8d
0x180007fac  cmp     r10d, r11d
0x180007faf  jb      short loc_180007F89
0x180007fb1  jmp     short loc_180007FB6
0x180007fb3  xor     r8d, r8d
0x180007fb6  cmp     edx, ebx
0x180007fb8  ja      short loc_180007FD2
0x180007fba  mov     eax, 290h
0x180007fbf  bt      eax, edx
0x180007fc2  jnb     short loc_180007FD2
0x180007fc4  cmp     r11d, 8
0x180007fc8  sbb     edi, edi
0x180007fca  add     edi, 439Ah
0x180007fd0  jmp     short loc_180007FDF
0x180007fd2  neg     r8d
0x180007fd5  sbb     edi, edi
0x180007fd7  neg     edi
0x180007fd9  add     edi, 4397h
0x180007fdf  mov     rcx, [rsi+8]; hDlg
0x180007fe3  mov     edx, 45Bh; nIDDlgItem
0x180007fe8  call    cs:__imp_GetDlgItem
0x180007fee  mov     rcx, [rsi+530h]
0x180007ff5  lea     r8, String; lpString
0x180007ffc  xor     ebx, ebx
0x180007ffe  cmp     [rcx+28h], rax
0x180008002  mov     rcx, [rsi+8]; hDlg
0x180008006  setnz   bl
0x180008009  add     ebx, 45Bh
0x18000800f  mov     edx, ebx; nIDDlgItem
0x180008011  call    cs:__imp_SetDlgItemTextW
0x180008017  lea     rcx, [rsi+260h]; this
0x18000801e  mov     r9d, edi; unsigned int
0x180008021  mov     r8d, 4394h; unsigned int
0x180008027  mov     edx, ebx; unsigned int
0x180008029  call    ?ShowErrBalloon@CTooltip@@QEAAXIIIZZ; CTooltip::ShowErrBalloon(uint,uint,uint,...)
0x18000802e  mov     rcx, [rsi+8]; hDlg
0x180008032  mov     edx, ebx; nIDDlgItem
0x180008034  call    cs:__imp_GetDlgItem
0x18000803a  mov     rcx, rax; hWnd
0x18000803d  call    cs:__imp_SetFocus
0x180008043  mov     rcx, [rsi+8]
0x180008047  xor     r9d, r9d
0x18000804a  mov     edx, 3EBh
0x18000804f  mov     r8d, 2710h
0x180008055  mov     rbx, [rsp+28h+arg_0]
0x18000805a  mov     rsi, [rsp+28h+arg_8]
0x18000805f  add     rsp, 20h
0x180008063  pop     rdi
0x180008064  jmp     cs:__imp_SetTimer
```
