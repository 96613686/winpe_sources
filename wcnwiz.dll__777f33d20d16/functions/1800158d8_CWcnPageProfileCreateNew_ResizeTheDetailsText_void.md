# CWcnPageProfileCreateNew::ResizeTheDetailsText(void)

- ea: `0x1800158d8`
- end: `0x180015b13`
- name: `?ResizeTheDetailsText@CWcnPageProfileCreateNew@@AEAAXXZ`
- size: `571`
- prototype: `void __fastcall(CWcnPageProfileCreateNew *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180014fe8`

## callees

- `0x180001820`
- `0x180001844`
- `0x1800028c4`
- `0x18000d630`
- `0x18000e1dc`
- `0x1800158d8`
- `0x18002de1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180015a09`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180015a09`
- `USER32!SetWindowPos` at `0x180015a89`
- `USER32!SetWindowPos` at `0x180015a89`
- `USER32!GetDC` at `0x180015958`
- `USER32!GetDC` at `0x180015958`
- `USER32!GetWindowRect` at `0x180015a45`
- `USER32!GetWindowRect` at `0x180015a45`
- `USER32!ReleaseDC` at `0x180015aa7`
- `USER32!ReleaseDC` at `0x180015aa7`
- `USER32!GetWindowTextLengthW` at `0x1800159ab`
- `USER32!GetWindowTextLengthW` at `0x1800159ab`
- `USER32!SendMessageW` at `0x18001597d`
- `USER32!SendMessageW` at `0x18001597d`
- `USER32!GetDlgItem` at `0x180015943`
- `USER32!GetDlgItem` at `0x180015943`
- `USER32!GetWindowTextW` at `0x1800159ee`
- `USER32!GetWindowTextW` at `0x1800159ee`
- `GDI32!SelectObject` at `0x180015996`
- `GDI32!SelectObject` at `0x180015a97`
- `GDI32!SelectObject` at `0x180015996`
- `GDI32!SelectObject` at `0x180015a97`
- `GDI32!GetTextExtentPoint32W` at `0x180015a2b`
- `GDI32!GetTextExtentPoint32W` at `0x180015a2b`

## pseudocode

```c
void __fastcall CWcnPageProfileCreateNew::ResizeTheDetailsText(HWND *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  HWND DlgItem; // rax
  HWND v5; // rbx
  HDC DC; // rdi
  WCHAR *v7; // rsi
  int v8; // ebp
  void *v9; // rax
  HGDIOBJ v10; // r15
  int v11; // r14d
  unsigned __int64 v12; // rax
  unsigned int v13; // eax
  __int64 v14; // r10
  tagSIZE psizl; // [rsp+40h] [rbp-68h] BYREF
  struct tagRECT Rect; // [rsp+48h] [rbp-60h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 58, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, Indent);
  }
  DlgItem = GetDlgItem(this[21], 2916);
  v5 = DlgItem;
  if ( DlgItem )
  {
    DC = GetDC(DlgItem);
    if ( DC )
    {
      v7 = 0;
      v8 = -2147418113;
      v9 = (void *)SendMessageW(v5, 0x31u, 0, 0);
      if ( v9 )
      {
        v10 = SelectObject(DC, v9);
        if ( v10 )
        {
          v11 = GetWindowTextLengthW(v5) + 3;
          if ( v11 <= 1024 )
          {
            v12 = 2LL * v11;
            if ( !is_mul_ok(v11, 2u) )
              v12 = -1;
            v7 = (WCHAR *)operator new[](v12, (const struct std::nothrow_t *)std::nothrow);
            if ( GetWindowTextW(v5, v7, v11) )
            {
              if ( !(unsigned int)_o_wcscat_s(v7, v11, L"  ") )
              {
                psizl = 0;
                if ( GetTextExtentPoint32W(DC, v7, v11 - 1, &psizl) )
                {
                  Rect = 0;
                  if ( GetWindowRect(v5, &Rect) )
                  {
                    if ( psizl.cx < Rect.right - Rect.left && psizl.cx >= 10 )
                    {
                      SetWindowPos(v5, (HWND)0xFFFFFFFFFFFFFFFELL, 0, 0, psizl.cx, Rect.bottom - Rect.top, 0x206u);
                      v8 = 0;
                    }
                  }
                }
              }
            }
          }
          SelectObject(DC, v10);
        }
      }
      ReleaseDC(v5, DC);
      if ( v7 )
        operator delete(v7);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (v8 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
      {
        v13 = (unsigned int)GetIndent(-1);
        WPP_SF_sd(*(_QWORD *)(v14 + 16), 59, (unsigned int)WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, v13, v8);
      }
    }
  }
}

```

## disassembly

```asm
0x1800158d8  push    rbx
0x1800158da  push    rbp
0x1800158db  push    rsi
0x1800158dc  push    rdi
0x1800158dd  push    r12
0x1800158df  push    r13
0x1800158e1  push    r14
0x1800158e3  push    r15
0x1800158e5  sub     rsp, 68h
0x1800158e9  mov     rax, cs:__security_cookie
0x1800158f0  xor     rax, rsp
0x1800158f3  mov     [rsp+0A8h+var_50], rax
0x1800158f8  mov     rbx, rcx
0x1800158fb  mov     r10, cs:WPP_GLOBAL_Control
0x180015902  lea     r13, WPP_GLOBAL_Control
0x180015909  cmp     r10, r13
0x18001590c  jz      short loc_180015937
0x18001590e  cmp     byte ptr [r10+19h], 6
0x180015913  jb      short loc_180015937
0x180015915  mov     ecx, 1; int
0x18001591a  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001591f  mov     rcx, [r10+10h]
0x180015923  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x18001592a  mov     edx, 3Ah ; ':'
0x18001592f  mov     r9, rax
0x180015932  call    WPP_SF_s
0x180015937  mov     rcx, [rbx+0A8h]; hDlg
0x18001593e  mov     edx, 0B64h; nIDDlgItem
0x180015943  call    cs:__imp_GetDlgItem
0x180015949  mov     rbx, rax
0x18001594c  test    rax, rax
0x18001594f  jz      loc_180015AF5
0x180015955  mov     rcx, rax; hWnd
0x180015958  call    cs:__imp_GetDC
0x18001595e  mov     rdi, rax
0x180015961  test    rax, rax
0x180015964  jz      loc_180015AF5
0x18001596a  xor     esi, esi
0x18001596c  xor     r9d, r9d; lParam
0x18001596f  xor     r8d, r8d; wParam
0x180015972  mov     rcx, rbx; hWnd
0x180015975  mov     ebp, 8000FFFFh
0x18001597a  lea     edx, [rsi+31h]; Msg
0x18001597d  call    cs:__imp_SendMessageW
0x180015983  or      r14, 0FFFFFFFFFFFFFFFFh
0x180015987  test    rax, rax
0x18001598a  jz      loc_180015AA1
0x180015990  mov     rdx, rax; h
0x180015993  mov     rcx, rdi; hdc
0x180015996  call    cs:__imp_SelectObject
0x18001599c  mov     r15, rax
0x18001599f  test    rax, rax
0x1800159a2  jz      loc_180015AA1
0x1800159a8  mov     rcx, rbx; hWnd
0x1800159ab  call    cs:__imp_GetWindowTextLengthW
0x1800159b1  lea     r14d, [rax+3]
0x1800159b5  cmp     r14d, 400h
0x1800159bc  jg      loc_180015A91
0x1800159c2  lea     rcx, [rsi-1]
0x1800159c6  movsxd  r12, r14d
0x1800159c9  lea     eax, [rsi+2]
0x1800159cc  mul     r12
0x1800159cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800159d6  cmovb   rax, rcx
0x1800159da  mov     rcx, rax; unsigned __int64
0x1800159dd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800159e2  mov     r8d, r14d; nMaxCount
0x1800159e5  mov     rdx, rax; lpString
0x1800159e8  mov     rcx, rbx; hWnd
0x1800159eb  mov     rsi, rax
0x1800159ee  call    cs:__imp_GetWindowTextW
0x1800159f4  test    eax, eax
0x1800159f6  jz      loc_180015A91
0x1800159fc  lea     r8, asc_1800369B8; "  "
0x180015a03  mov     rdx, r12
0x180015a06  mov     rcx, rsi
0x180015a09  call    cs:__imp__o_wcscat_s
0x180015a0f  test    eax, eax
0x180015a11  jnz     short loc_180015A91
0x180015a13  lea     r8d, [r14-1]; c
0x180015a17  mov     qword ptr [rsp+0A8h+psizl.cx], 0
0x180015a20  lea     r9, [rsp+0A8h+psizl]; psizl
0x180015a25  mov     rdx, rsi; lpString
0x180015a28  mov     rcx, rdi; hdc
0x180015a2b  call    cs:__imp_GetTextExtentPoint32W
0x180015a31  test    eax, eax
0x180015a33  jz      short loc_180015A91
0x180015a35  xorps   xmm0, xmm0
0x180015a38  lea     rdx, [rsp+0A8h+Rect]; lpRect
0x180015a3d  mov     rcx, rbx; hWnd
0x180015a40  movups  xmmword ptr [rsp+0A8h+Rect.left], xmm0
0x180015a45  call    cs:__imp_GetWindowRect
0x180015a4b  test    eax, eax
0x180015a4d  jz      short loc_180015A91
0x180015a4f  mov     eax, [rsp+0A8h+Rect.right]
0x180015a53  sub     eax, [rsp+0A8h+Rect.left]
0x180015a57  mov     ecx, [rsp+0A8h+psizl.cx]
0x180015a5b  cmp     ecx, eax
0x180015a5d  jge     short loc_180015A91
0x180015a5f  cmp     ecx, 0Ah
0x180015a62  jl      short loc_180015A91
0x180015a64  mov     eax, [rsp+0A8h+Rect.bottom]
0x180015a68  xor     r9d, r9d; Y
0x180015a6b  sub     eax, [rsp+0A8h+Rect.top]
0x180015a6f  xor     r8d, r8d; X
0x180015a72  mov     [rsp+0A8h+uFlags], 206h; uFlags
0x180015a7a  mov     [rsp+0A8h+cy], eax; cy
0x180015a7e  mov     [rsp+0A8h+var_88], ecx; cx
0x180015a82  lea     rdx, [r9-2]; hWndInsertAfter
0x180015a86  mov     rcx, rbx; hWnd
0x180015a89  call    cs:__imp_SetWindowPos
0x180015a8f  xor     ebp, ebp
0x180015a91  mov     rdx, r15; h
0x180015a94  mov     rcx, rdi; hdc
0x180015a97  call    cs:__imp_SelectObject
0x180015a9d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180015aa1  mov     rdx, rdi; hDC
0x180015aa4  mov     rcx, rbx; hWnd
0x180015aa7  call    cs:__imp_ReleaseDC
0x180015aad  test    rsi, rsi
0x180015ab0  jz      short loc_180015ABA
0x180015ab2  mov     rcx, rsi; Block
0x180015ab5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015aba  mov     r10, cs:WPP_GLOBAL_Control
0x180015ac1  cmp     r10, r13
0x180015ac4  jz      short loc_180015AF5
0x180015ac6  test    ebp, ebp
0x180015ac8  js      short loc_180015AD1
0x180015aca  cmp     byte ptr [r10+19h], 6
0x180015acf  jb      short loc_180015AF5
0x180015ad1  mov     ecx, r14d; int
0x180015ad4  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180015ad9  mov     rcx, [r10+10h]
0x180015add  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x180015ae4  mov     edx, 3Bh ; ';'
0x180015ae9  mov     [rsp+0A8h+var_88], ebp
0x180015aed  mov     r9, rax
0x180015af0  call    WPP_SF_sd
0x180015af5  mov     rcx, [rsp+0A8h+var_50]
0x180015afa  xor     rcx, rsp; StackCookie
0x180015afd  call    __security_check_cookie
0x180015b02  add     rsp, 68h
0x180015b06  pop     r15
0x180015b08  pop     r14
0x180015b0a  pop     r13
0x180015b0c  pop     r12
0x180015b0e  pop     rdi
0x180015b0f  pop     rsi
0x180015b10  pop     rbp
0x180015b11  pop     rbx
0x180015b12  retn
```
