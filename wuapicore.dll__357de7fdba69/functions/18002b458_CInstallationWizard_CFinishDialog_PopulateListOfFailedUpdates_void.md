# CInstallationWizard::CFinishDialog::PopulateListOfFailedUpdates(void)

- ea: `0x18002b458`
- end: `0x18002b6d7`
- name: `?PopulateListOfFailedUpdates@CFinishDialog@CInstallationWizard@@AEAAXXZ`
- size: `639`
- prototype: `void __fastcall(CInstallationWizard::CFinishDialog *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18002b1a0`

## callees

- `0x18002b458`
- `0x18002de68`
- `0x180095a88`
- `0x18009ae75`
- `0x18009b050`
- `0x18009b0b8`
- `0x18009b640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5a6`
- `USER32!GetDlgItem` at `0x18002b495`
- `USER32!GetDlgItem` at `0x18002b4a7`
- `USER32!GetDlgItem` at `0x18002b495`
- `USER32!GetDlgItem` at `0x18002b4a7`
- `USER32!SendMessageW` at `0x18002b657`
- `USER32!SendMessageW` at `0x18002b669`
- `USER32!SendMessageW` at `0x18002b6a0`
- `USER32!SendMessageW` at `0x18002b657`
- `USER32!SendMessageW` at `0x18002b669`
- `USER32!SendMessageW` at `0x18002b6a0`
- `USER32!GetWindowTextLengthW` at `0x18002b518`
- `USER32!GetWindowTextLengthW` at `0x18002b518`
- `USER32!ShowWindow` at `0x18002b5e6`
- `USER32!ShowWindow` at `0x18002b5f1`
- `USER32!ShowWindow` at `0x18002b5e6`
- `USER32!ShowWindow` at `0x18002b5f1`
- `USER32!GetWindowLongW` at `0x18002b679`
- `USER32!GetWindowLongW` at `0x18002b679`
- `USER32!SetWindowLongW` at `0x18002b68b`
- `USER32!SetWindowLongW` at `0x18002b68b`
- `USER32!GetWindowTextW` at `0x18002b55e`
- `USER32!GetWindowTextW` at `0x18002b55e`
- `USER32!SetWindowTextW` at `0x18002b59c`
- `USER32!SetWindowTextW` at `0x18002b59c`
- `GDI32!CreateFontIndirectW` at `0x18002b636`
- `GDI32!CreateFontIndirectW` at `0x18002b636`

## pseudocode

```c
void __fastcall CInstallationWizard::CFinishDialog::PopulateListOfFailedUpdates(
        CInstallationWizard::CFinishDialog *this)
{
  HWND DlgItem; // rdi
  HWND v3; // rbp
  int v4; // r12d
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rbp
  __int64 v8; // rax
  const wchar_t *v9; // rax
  const wchar_t *v10; // r13
  __int64 v11; // r14
  int WindowTextLengthW; // eax
  __int64 v13; // rbx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // kr00_8
  WCHAR *v16; // rax
  WCHAR *v17; // r15
  HFONT v18; // rbx
  LONG WindowLongW; // eax
  int v20; // [rsp+20h] [rbp-B8h]
  __int64 v21; // [rsp+28h] [rbp-B0h]
  HWND v22; // [rsp+30h] [rbp-A8h]
  LOGFONTW lf; // [rsp+40h] [rbp-98h] BYREF

  DlgItem = GetDlgItem(*((HWND *)this + 1), 64429);
  v3 = GetDlgItem(*((HWND *)this + 1), 64428);
  v22 = v3;
  v4 = 0;
  v20 = *(_DWORD *)(*((_QWORD *)this + 10) + 8LL);
  v5 = v20;
  v6 = v20;
  v21 = v20;
  if ( v20 > 0 )
  {
    v7 = 0;
    do
    {
      v8 = **((_QWORD **)this + 10);
      if ( *(_DWORD *)(v8 + v7 + 76) )
      {
        ++v4;
      }
      else
      {
        v9 = *(const wchar_t **)(v8 + v7 + 56);
        v10 = &szDataDescr;
        v11 = -1;
        if ( v9 )
          v10 = v9;
        do
          ++v11;
        while ( v10[v11] );
        WindowTextLengthW = GetWindowTextLengthW(DlgItem);
        v13 = WindowTextLengthW;
        v15 = (int)v11 + WindowTextLengthW + 3;
        v14 = 2 * v15;
        if ( !is_mul_ok(v15, 2u) )
          v14 = -1;
        v16 = (WCHAR *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
        v17 = v16;
        if ( v16 )
        {
          if ( (_DWORD)v13 != GetWindowTextW(DlgItem, v16, v13 + 1)
            || (StringCchCopyW(&v17[v13], (int)v11 + 1, v10),
                StringCchCopyW(&v17[v13 + (int)v11], 3u, L"\r\n"),
                !SetWindowTextW(DlgItem, v17)) )
          {
            GetLastError();
          }
        }
        operator delete(v17);
        v6 = v21;
      }
      v7 += 88;
      v21 = --v6;
    }
    while ( v6 );
    v3 = v22;
    v5 = v20;
  }
  if ( v4 == v5 )
  {
    ShowWindow(DlgItem, 0);
    ShowWindow(v3, 0);
  }
  else
  {
    v18 = (HFONT)*((_QWORD *)this + 13);
    if ( v18 )
      goto LABEL_23;
    v18 = 0;
    memset_0(&lf, 0, sizeof(lf));
    if ( (int)GetWindowLogFont(v3, &lf) >= 0 )
    {
      lf.lfWeight = 700;
      v18 = CreateFontIndirectW(&lf);
    }
    *((_QWORD *)this + 13) = v18;
    if ( v18 )
    {
LABEL_23:
      SendMessageW(DlgItem, 0x30u, (WPARAM)v18, 0);
      SendMessageW(v3, 0x30u, *((_QWORD *)this + 13), 0);
    }
    WindowLongW = GetWindowLongW(DlgItem, -16);
    SetWindowLongW(DlgItem, -16, WindowLongW & 0xFF7FFFFF);
    SendMessageW(DlgItem, 0xD3u, 1u, 0);
  }
}

```

## disassembly

```asm
0x18002b458  mov     [rsp+arg_8], rbx
0x18002b45d  mov     [rsp+arg_10], rbp
0x18002b462  mov     [rsp+arg_18], rsi
0x18002b467  push    rdi
0x18002b468  push    r12
0x18002b46a  push    r13
0x18002b46c  push    r14
0x18002b46e  push    r15
0x18002b470  sub     rsp, 0B0h
0x18002b477  mov     rax, cs:__security_cookie
0x18002b47e  xor     rax, rsp
0x18002b481  mov     [rsp+0D8h+var_38], rax
0x18002b489  mov     rsi, rcx
0x18002b48c  mov     edx, 0FBADh; nIDDlgItem
0x18002b491  mov     rcx, [rcx+8]; hDlg
0x18002b495  call    cs:__imp_GetDlgItem
0x18002b49b  mov     rcx, [rsi+8]; hDlg
0x18002b49f  mov     edx, 0FBACh; nIDDlgItem
0x18002b4a4  mov     rdi, rax
0x18002b4a7  call    cs:__imp_GetDlgItem
0x18002b4ad  mov     rcx, [rsi+50h]
0x18002b4b1  xor     r15d, r15d
0x18002b4b4  mov     rbp, rax
0x18002b4b7  mov     [rsp+0D8h+var_A8], rax
0x18002b4bc  mov     r12d, r15d
0x18002b4bf  movsxd  rax, dword ptr [rcx+8]
0x18002b4c3  mov     [rsp+0D8h+var_B8], eax
0x18002b4c7  mov     rcx, rax
0x18002b4ca  mov     [rsp+0D8h+var_B0], rax
0x18002b4cf  test    eax, eax
0x18002b4d1  jle     loc_18002B5DC
0x18002b4d7  mov     ebp, r15d
0x18002b4da  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002b4de  mov     rax, [rsi+50h]
0x18002b4e2  mov     rax, [rax]
0x18002b4e5  cmp     [rax+rbp+4Ch], r15d
0x18002b4ea  jz      short loc_18002B4F4
0x18002b4ec  inc     r12d
0x18002b4ef  jmp     loc_18002B5C0
0x18002b4f4  mov     rax, [rax+rbp+38h]
0x18002b4f9  lea     r13, szDataDescr
0x18002b500  test    rax, rax
0x18002b503  mov     r14, rdx
0x18002b506  cmovnz  r13, rax
0x18002b50a  inc     r14
0x18002b50d  cmp     [r13+r14*2+0], r15w
0x18002b513  jnz     short loc_18002B50A
0x18002b515  mov     rcx, rdi; hWnd
0x18002b518  call    cs:__imp_GetWindowTextLengthW
0x18002b51e  movsxd  rbx, eax
0x18002b521  mov     eax, 2
0x18002b526  lea     ecx, [rbx+3]
0x18002b529  add     ecx, r14d
0x18002b52c  movsxd  rdx, ecx
0x18002b52f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002b536  mul     rdx
0x18002b539  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b540  cmovb   rax, rcx
0x18002b544  mov     rcx, rax; unsigned __int64
0x18002b547  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002b54c  mov     r15, rax
0x18002b54f  test    rax, rax
0x18002b552  jz      short loc_18002B5AC
0x18002b554  lea     r8d, [rbx+1]; nMaxCount
0x18002b558  mov     rdx, rax; lpString
0x18002b55b  mov     rcx, rdi; hWnd
0x18002b55e  call    cs:__imp_GetWindowTextW
0x18002b564  cmp     ebx, eax
0x18002b566  jnz     short loc_18002B5A6
0x18002b568  lea     ecx, [r14+1]
0x18002b56c  mov     r8, r13; wchar_t *
0x18002b56f  movsxd  rdx, ecx; unsigned __int64
0x18002b572  lea     rcx, [r15+rbx*2]; wchar_t *
0x18002b576  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002b57b  movsxd  r11, r14d
0x18002b57e  lea     r8, asc_1800B58D4; "\r\n"
0x18002b585  add     r11, rbx
0x18002b588  mov     edx, 3; unsigned __int64
0x18002b58d  lea     rcx, [r15+r11*2]; wchar_t *
0x18002b591  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002b596  mov     rdx, r15; lpString
0x18002b599  mov     rcx, rdi; hWnd
0x18002b59c  call    cs:__imp_SetWindowTextW
0x18002b5a2  test    eax, eax
0x18002b5a4  jnz     short loc_18002B5AC
0x18002b5a6  call    cs:__imp_GetLastError
0x18002b5ac  mov     rcx, r15; Block
0x18002b5af  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b5b4  mov     rcx, [rsp+0D8h+var_B0]
0x18002b5b9  xor     r15d, r15d
0x18002b5bc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002b5c0  add     rbp, 58h ; 'X'
0x18002b5c4  sub     rcx, 1
0x18002b5c8  mov     [rsp+0D8h+var_B0], rcx
0x18002b5cd  jnz     loc_18002B4DE
0x18002b5d3  mov     rbp, [rsp+0D8h+var_A8]
0x18002b5d8  mov     eax, [rsp+0D8h+var_B8]
0x18002b5dc  cmp     r12d, eax
0x18002b5df  jnz     short loc_18002B5FC
0x18002b5e1  xor     edx, edx; nCmdShow
0x18002b5e3  mov     rcx, rdi; hWnd
0x18002b5e6  call    cs:__imp_ShowWindow
0x18002b5ec  xor     edx, edx; nCmdShow
0x18002b5ee  mov     rcx, rbp; hWnd
0x18002b5f1  call    cs:__imp_ShowWindow
0x18002b5f7  jmp     loc_18002B6A6
0x18002b5fc  mov     rbx, [rsi+68h]
0x18002b600  test    rbx, rbx
0x18002b603  jnz     short loc_18002B648
0x18002b605  xor     edx, edx; Val
0x18002b607  lea     rcx, [rsp+0D8h+lf]; void *
0x18002b60c  mov     rbx, r15
0x18002b60f  lea     r8d, [rdx+5Ch]; Size
0x18002b613  call    memset_0
0x18002b618  lea     rdx, [rsp+0D8h+lf]; pv
0x18002b61d  mov     rcx, rbp; hWnd
0x18002b620  call    ?GetWindowLogFont@@YAJPEAUHWND__@@PEAUtagLOGFONTW@@@Z; GetWindowLogFont(HWND__ *,tagLOGFONTW *)
0x18002b625  test    eax, eax
0x18002b627  js      short loc_18002B63F
0x18002b629  lea     rcx, [rsp+0D8h+lf]; lplf
0x18002b62e  mov     [rsp+0D8h+lf.lfWeight], 2BCh
0x18002b636  call    cs:__imp_CreateFontIndirectW
0x18002b63c  mov     rbx, rax
0x18002b63f  mov     [rsi+68h], rbx
0x18002b643  test    rbx, rbx
0x18002b646  jz      short loc_18002B66F
0x18002b648  xor     r9d, r9d; lParam
0x18002b64b  mov     r8, rbx; wParam
0x18002b64e  mov     rcx, rdi; hWnd
0x18002b651  lea     ebx, [r9+30h]
0x18002b655  mov     edx, ebx; Msg
0x18002b657  call    cs:__imp_SendMessageW
0x18002b65d  mov     r8, [rsi+68h]; wParam
0x18002b661  xor     r9d, r9d; lParam
0x18002b664  mov     edx, ebx; Msg
0x18002b666  mov     rcx, rbp; hWnd
0x18002b669  call    cs:__imp_SendMessageW
0x18002b66f  mov     ebx, 0FFFFFFF0h
0x18002b674  mov     rcx, rdi; hWnd
0x18002b677  mov     edx, ebx; nIndex
0x18002b679  call    cs:__imp_GetWindowLongW
0x18002b67f  mov     edx, ebx; nIndex
0x18002b681  mov     rcx, rdi; hWnd
0x18002b684  btr     eax, 17h
0x18002b688  mov     r8d, eax; dwNewLong
0x18002b68b  call    cs:__imp_SetWindowLongW
0x18002b691  xor     r9d, r9d; lParam
0x18002b694  lea     r8d, [rbx+11h]; wParam
0x18002b698  mov     edx, 0D3h; Msg
0x18002b69d  mov     rcx, rdi; hWnd
0x18002b6a0  call    cs:__imp_SendMessageW
0x18002b6a6  mov     rcx, [rsp+0D8h+var_38]
0x18002b6ae  xor     rcx, rsp; StackCookie
0x18002b6b1  call    __security_check_cookie
0x18002b6b6  lea     r11, [rsp+0D8h+var_28]
0x18002b6be  mov     rbx, [r11+38h]
0x18002b6c2  mov     rbp, [r11+40h]
0x18002b6c6  mov     rsi, [r11+48h]
0x18002b6ca  mov     rsp, r11
0x18002b6cd  pop     r15
0x18002b6cf  pop     r14
0x18002b6d1  pop     r13
0x18002b6d3  pop     r12
0x18002b6d5  pop     rdi
0x18002b6d6  retn
```
