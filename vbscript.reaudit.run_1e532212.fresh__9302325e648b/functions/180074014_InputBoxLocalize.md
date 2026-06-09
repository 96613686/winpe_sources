# InputBoxLocalize

- ea: `0x180074014`
- end: `0x180074227`
- name: `InputBoxLocalize`
- size: `531`
- prototype: `__int64 __fastcall(HWND hDlg)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180073eb0`

## callees

- `0x18005443c`
- `0x180074014`
- `0x1800746fc`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1800740d1`
- `KERNEL32!MulDiv` at `0x1800740d1`
- `USER32!SendDlgItemMessageA` at `0x180074188`
- `USER32!SendDlgItemMessageA` at `0x1800741a5`
- `USER32!SendDlgItemMessageA` at `0x180074188`
- `USER32!SendDlgItemMessageA` at `0x1800741a5`
- `USER32!GetDC` at `0x1800740a6`
- `USER32!GetDC` at `0x1800740a6`
- `USER32!SendMessageA` at `0x18007416b`
- `USER32!SendMessageA` at `0x18007416b`
- `USER32!GetDlgItem` at `0x1800741c1`
- `USER32!GetDlgItem` at `0x1800741e2`
- `USER32!GetDlgItem` at `0x180074203`
- `USER32!GetDlgItem` at `0x1800741c1`
- `USER32!GetDlgItem` at `0x1800741e2`
- `USER32!GetDlgItem` at `0x180074203`
- `USER32!ReleaseDC` at `0x1800740e1`
- `USER32!ReleaseDC` at `0x1800740e1`
- `GDI32!GetDeviceCaps` at `0x1800740c0`
- `GDI32!GetDeviceCaps` at `0x1800740c0`
- `GDI32!CreateFontA` at `0x18007414a`
- `GDI32!CreateFontA` at `0x18007414a`

## pseudocode

```c
int __fastcall InputBoxLocalize(HWND hDlg, __int64 a2)
{
  WPARAM v3; // rdi
  __int64 v4; // rcx
  __int64 *v6; // rbx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  HDC DC; // rax
  HDC v11; // rdi
  int DeviceCaps; // eax
  int v13; // ebp
  unsigned int v14; // ebx
  HWND DlgItem; // rax
  HWND v16; // rax
  HWND v17; // rax

  v3 = 0;
  v4 = *(_QWORD *)(a2 + 48);
  if ( *(_DWORD *)(v4 + 232) )
  {
    v7 = *(_DWORD *)(v4 + 236) - 932;
    if ( v7 )
    {
      v8 = v7 - 4;
      if ( v8 )
      {
        v9 = v8 - 13;
        if ( v9 )
        {
          if ( v9 != 1 )
            goto LABEL_19;
          v6 = (__int64 *)&off_18007A570;
        }
        else
        {
          v6 = &off_18007A588;
        }
      }
      else
      {
        v6 = &off_18007A5A0;
      }
    }
    else
    {
      v6 = (__int64 *)&off_18007A530;
    }
  }
  else
  {
    if ( *(_WORD *)(v4 + 184) != 1081 )
    {
      if ( *(_WORD *)(v4 + 184) == 1097 )
      {
        v6 = (__int64 *)&off_18007A550;
        goto LABEL_14;
      }
LABEL_19:
      LODWORD(DC) = COleScript::GetUserLocale();
      v14 = (unsigned int)DC;
      if ( (_DWORD)DC != 1033 )
      {
        DlgItem = GetDlgItem(hDlg, 1);
        SetButtonTitle(DlgItem, 0x8000, v14, v3);
        v16 = GetDlgItem(hDlg, 2);
        SetButtonTitle(v16, 32769, v14, v3);
        v17 = GetDlgItem(hDlg, 3);
        LODWORD(DC) = SetButtonTitle(v17, 32770, v14, v3);
      }
      return (int)DC;
    }
    v6 = (__int64 *)&off_18007A560;
  }
LABEL_14:
  DC = GetDC(hDlg);
  v11 = DC;
  if ( DC )
  {
    DeviceCaps = GetDeviceCaps(DC, 90);
    v13 = -MulDiv(9, DeviceCaps, 72);
    LODWORD(DC) = ReleaseDC(hDlg, v11);
    while ( *v6 )
    {
      DC = (HDC)CreateFontA(v13, 0, 0, 0, 400, 0, 0, 0, 1u, 0, 0, 0, 0, (LPCSTR)*v6);
      v3 = (WPARAM)DC;
      if ( DC )
      {
        *(_QWORD *)(a2 + 88) = DC;
        SendMessageA(hDlg, 0x30u, (WPARAM)DC, 0);
        SendDlgItemMessageA(hDlg, 1001, 0x30u, v3, 0);
        SendDlgItemMessageA(hDlg, 1000, 0x30u, v3, 0);
        goto LABEL_19;
      }
    }
  }
  return (int)DC;
}

```

## disassembly

```asm
0x180074014  push    rbx
0x180074016  push    rbp
0x180074017  push    rsi
0x180074018  push    rdi
0x180074019  push    r14
0x18007401b  sub     rsp, 70h
0x18007401f  mov     rsi, rcx
0x180074022  xor     edi, edi
0x180074024  mov     rcx, [rdx+30h]
0x180074028  mov     r14, rdx
0x18007402b  cmp     [rcx+0E8h], edi
0x180074031  jnz     short loc_180074060
0x180074033  movzx   r8d, word ptr [rcx+0B8h]
0x18007403b  sub     r8d, 439h
0x180074042  jz      short loc_180074057
0x180074044  cmp     r8d, 10h
0x180074048  jnz     loc_1800741AB
0x18007404e  lea     rbx, off_18007A550; "Latha"
0x180074055  jmp     short loc_1800740A3
0x180074057  lea     rbx, off_18007A560; "Mangal"
0x18007405e  jmp     short loc_1800740A3
0x180074060  mov     ecx, [rcx+0ECh]
0x180074066  sub     ecx, 3A4h
0x18007406c  jz      short loc_18007409C
0x18007406e  sub     ecx, 4
0x180074071  jz      short loc_180074093
0x180074073  sub     ecx, 0Dh
0x180074076  jz      short loc_18007408A
0x180074078  cmp     ecx, 1
0x18007407b  jnz     loc_1800741AB
0x180074081  lea     rbx, off_18007A570
0x180074088  jmp     short loc_1800740A3
0x18007408a  lea     rbx, off_18007A588
0x180074091  jmp     short loc_1800740A3
0x180074093  lea     rbx, off_18007A5A0
0x18007409a  jmp     short loc_1800740A3
0x18007409c  lea     rbx, off_18007A530
0x1800740a3  mov     rcx, rsi; hWnd
0x1800740a6  call    cs:__imp_GetDC
0x1800740ac  mov     rdi, rax
0x1800740af  test    rax, rax
0x1800740b2  jz      loc_18007421C
0x1800740b8  mov     edx, 5Ah ; 'Z'; index
0x1800740bd  mov     rcx, rax; hdc
0x1800740c0  call    cs:__imp_GetDeviceCaps
0x1800740c6  mov     ecx, 9; nNumber
0x1800740cb  mov     edx, eax; nNumerator
0x1800740cd  lea     r8d, [rcx+3Fh]; nDenominator
0x1800740d1  call    cs:__imp_MulDiv
0x1800740d7  mov     rdx, rdi; hDC
0x1800740da  mov     rcx, rsi; hWnd
0x1800740dd  mov     ebp, eax
0x1800740df  neg     ebp
0x1800740e1  call    cs:__imp_ReleaseDC
0x1800740e7  mov     rcx, [rbx]
0x1800740ea  test    rcx, rcx
0x1800740ed  jz      loc_18007421C
0x1800740f3  mov     [rsp+98h+pszFaceName], rcx; pszFaceName
0x1800740f8  xor     r9d, r9d; cOrientation
0x1800740fb  mov     [rsp+98h+iPitchAndFamily], 0; iPitchAndFamily
0x180074103  xor     r8d, r8d; cEscapement
0x180074106  mov     [rsp+98h+iQuality], 0; iQuality
0x18007410e  xor     edx, edx; cWidth
0x180074110  mov     [rsp+98h+iClipPrecision], 0; iClipPrecision
0x180074118  mov     ecx, ebp; cHeight
0x18007411a  mov     [rsp+98h+iOutPrecision], 0; iOutPrecision
0x180074122  mov     [rsp+98h+iCharSet], 1; iCharSet
0x18007412a  mov     [rsp+98h+bStrikeOut], 0; bStrikeOut
0x180074132  mov     [rsp+98h+bUnderline], 0; bUnderline
0x18007413a  mov     [rsp+98h+bItalic], 0; bItalic
0x180074142  mov     [rsp+98h+cWeight], 190h; cWeight
0x18007414a  call    cs:__imp_CreateFontA
0x180074150  mov     rdi, rax
0x180074153  test    rax, rax
0x180074156  jz      short loc_1800740E7
0x180074158  xor     r9d, r9d; lParam
0x18007415b  mov     [r14+58h], rax
0x18007415f  mov     r8, rax; wParam
0x180074162  mov     rcx, rsi; hWnd
0x180074165  lea     ebx, [r9+30h]
0x180074169  mov     edx, ebx; Msg
0x18007416b  call    cs:__imp_SendMessageA
0x180074171  mov     r9, rdi; wParam
0x180074174  mov     qword ptr [rsp+98h+cWeight], 0; lParam
0x18007417d  mov     r8d, ebx; Msg
0x180074180  mov     edx, 3E9h; nIDDlgItem
0x180074185  mov     rcx, rsi; hDlg
0x180074188  call    cs:__imp_SendDlgItemMessageA
0x18007418e  mov     r9, rdi; wParam
0x180074191  mov     qword ptr [rsp+98h+cWeight], 0; lParam
0x18007419a  mov     r8d, ebx; Msg
0x18007419d  mov     edx, 3E8h; nIDDlgItem
0x1800741a2  mov     rcx, rsi; hDlg
0x1800741a5  call    cs:__imp_SendDlgItemMessageA
0x1800741ab  call    ?GetUserLocale@COleScript@@SAKXZ; COleScript::GetUserLocale(void)
0x1800741b0  mov     ebx, eax
0x1800741b2  cmp     eax, 409h
0x1800741b7  jz      short loc_18007421C
0x1800741b9  mov     edx, 1; nIDDlgItem
0x1800741be  mov     rcx, rsi; hDlg
0x1800741c1  call    cs:__imp_GetDlgItem
0x1800741c7  mov     r9, rdi; wParam
0x1800741ca  mov     r8d, ebx; unsigned int
0x1800741cd  mov     rcx, rax; hWnd
0x1800741d0  mov     edx, 8000h; int
0x1800741d5  call    SetButtonTitle
0x1800741da  mov     edx, 2; nIDDlgItem
0x1800741df  mov     rcx, rsi; hDlg
0x1800741e2  call    cs:__imp_GetDlgItem
0x1800741e8  mov     r9, rdi; wParam
0x1800741eb  mov     r8d, ebx; unsigned int
0x1800741ee  mov     rcx, rax; hWnd
0x1800741f1  mov     edx, 8001h; int
0x1800741f6  call    SetButtonTitle
0x1800741fb  mov     edx, 3; nIDDlgItem
0x180074200  mov     rcx, rsi; hDlg
0x180074203  call    cs:__imp_GetDlgItem
0x180074209  mov     r9, rdi; wParam
0x18007420c  mov     r8d, ebx; unsigned int
0x18007420f  mov     rcx, rax; hWnd
0x180074212  mov     edx, 8002h; int
0x180074217  call    SetButtonTitle
0x18007421c  add     rsp, 70h
0x180074220  pop     r14
0x180074222  pop     rdi
0x180074223  pop     rsi
0x180074224  pop     rbp
0x180074225  pop     rbx
0x180074226  retn
```
