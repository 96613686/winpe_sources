# CSwitchDlg::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x180014f54`
- end: `0x1800150b3`
- name: `?OnInitDialog@CSwitchDlg@@QEAA_JI_K_JAEAH@Z`
- size: `351`
- prototype: `__int64 __fastcall(CSwitchDlg *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180015280`

## callees

- `0x1800079b0`
- `0x18001181c`
- `0x180014f54`
- `0x18002d80e`
- `0x18002d840`

## import_xrefs

- `GDI32!CreateFontIndirectW` at `0x180014fed`
- `GDI32!CreateFontIndirectW` at `0x180014fed`
- `GDI32!GetObjectW` at `0x180014fd8`
- `GDI32!GetObjectW` at `0x180014fd8`
- `USER32!SendMessageW` at `0x180014fa8`
- `USER32!SendMessageW` at `0x180015001`
- `USER32!SendMessageW` at `0x180014fa8`
- `USER32!SendMessageW` at `0x180015001`
- `USER32!EnableWindow` at `0x180015087`
- `USER32!EnableWindow` at `0x180015087`
- `USER32!CheckDlgButton` at `0x180015052`
- `USER32!CheckDlgButton` at `0x180015052`
- `wlanapi!WlanQueryCreateAllUserProfileRestricted` at `0x18001501a`
- `wlanapi!WlanQueryCreateAllUserProfileRestricted` at `0x18001501a`

## pseudocode

```c
__int64 __fastcall CSwitchDlg::OnInitDialog(CSwitchDlg *this, HWND a2)
{
  HWND *v2; // rdi
  HWND v4; // rsi
  void *v5; // r14
  HFONT v6; // rax
  bool v7; // zf
  int v8; // edx
  unsigned int v9; // ebx
  HWND *DlgItem; // rax
  int v12; // [rsp+20h] [rbp-71h] BYREF
  int v13; // [rsp+24h] [rbp-6Dh] BYREF
  _DWORD v14[4]; // [rsp+28h] [rbp-69h]
  _BYTE v15[8]; // [rsp+38h] [rbp-59h] BYREF
  LOGFONTW pv; // [rsp+40h] [rbp-51h] BYREF

  v2 = (HWND *)((char *)this + 8);
  ATL::CWindow::CenterWindow((CSwitchDlg *)((char *)this + 8), a2);
  v4 = *(HWND *)ATL::CWindow::GetDlgItem(v2, v15, 20069);
  v5 = (void *)SendMessageW(v4, 0x31u, 0, 0);
  if ( v5 )
  {
    memset_0(&pv, 0, sizeof(pv));
    if ( GetObjectW(v5, 92, &pv) )
    {
      pv.lfHeight = -16;
      v6 = CreateFontIndirectW(&pv);
      SendMessageW(v4, 0x30u, (WPARAM)v6, 1);
    }
  }
  v12 = 1;
  v13 = 0;
  if ( !(unsigned int)WlanQueryCreateAllUserProfileRestricted(&v12, &v13) )
  {
    v7 = v13 == 1;
    *((_BYTE *)this + 65) = v12 == 1;
    *((_BYTE *)this + 64) = v7;
  }
  v8 = 20076;
  if ( !*((_BYTE *)this + 65) )
    v8 = 20075;
  CheckDlgButton(*v2, v8, 1u);
  if ( *((_BYTE *)this + 64) )
  {
    v14[0] = 20075;
    v9 = 0;
    v14[1] = 20076;
    v14[2] = 20071;
    do
    {
      DlgItem = (HWND *)ATL::CWindow::GetDlgItem(v2, v15, (unsigned int)v14[v9]);
      EnableWindow(*DlgItem, 0);
      ++v9;
    }
    while ( v9 < 3 );
  }
  return 0;
}

```

## disassembly

```asm
0x180014f54  push    rbp
0x180014f56  push    rbx
0x180014f57  push    rsi
0x180014f58  push    rdi
0x180014f59  push    r12
0x180014f5b  push    r14
0x180014f5d  lea     rbp, [rsp-27h]
0x180014f62  sub     rsp, 0B8h
0x180014f69  mov     rax, cs:__security_cookie
0x180014f70  xor     rax, rsp
0x180014f73  mov     [rbp+4Fh+var_40], rax
0x180014f77  lea     rdi, [rcx+8]
0x180014f7b  mov     rbx, rcx
0x180014f7e  mov     rcx, rdi; this
0x180014f81  call    ?CenterWindow@CWindow@ATL@@QEAAHPEAUHWND__@@@Z; ATL::CWindow::CenterWindow(HWND__ *)
0x180014f86  mov     r8d, 4E65h
0x180014f8c  lea     rdx, [rbp+4Fh+var_A8]
0x180014f90  mov     rcx, rdi
0x180014f93  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180014f98  xor     r9d, r9d; lParam
0x180014f9b  xor     r8d, r8d; wParam
0x180014f9e  mov     rsi, [rax]
0x180014fa1  lea     edx, [r9+31h]; Msg
0x180014fa5  mov     rcx, rsi; hWnd
0x180014fa8  call    cs:__imp_SendMessageW
0x180014fae  mov     r14, rax
0x180014fb1  mov     r12d, 1
0x180014fb7  test    rax, rax
0x180014fba  jz      short loc_180015007
0x180014fbc  xor     edx, edx; Val
0x180014fbe  lea     r8d, [r12+5Bh]; Size
0x180014fc3  lea     rcx, [rbp+4Fh+pv]; void *
0x180014fc7  call    memset_0
0x180014fcc  lea     r8, [rbp+4Fh+pv]; pv
0x180014fd0  mov     rcx, r14; h
0x180014fd3  lea     edx, [r12+5Bh]; c
0x180014fd8  call    cs:__imp_GetObjectW
0x180014fde  test    eax, eax
0x180014fe0  jz      short loc_180015007
0x180014fe2  lea     rcx, [rbp+4Fh+pv]; lplf
0x180014fe6  mov     [rbp+4Fh+pv.lfHeight], 0FFFFFFF0h
0x180014fed  call    cs:__imp_CreateFontIndirectW
0x180014ff3  mov     r9d, r12d; lParam
0x180014ff6  lea     edx, [r12+2Fh]; Msg
0x180014ffb  mov     r8, rax; wParam
0x180014ffe  mov     rcx, rsi; hWnd
0x180015001  call    cs:__imp_SendMessageW
0x180015007  lea     rdx, [rbp+4Fh+var_BC]
0x18001500b  mov     [rbp+4Fh+var_C0], r12d
0x18001500f  lea     rcx, [rbp+4Fh+var_C0]
0x180015013  mov     [rbp+4Fh+var_BC], 0
0x18001501a  call    cs:__imp_WlanQueryCreateAllUserProfileRestricted
0x180015020  test    eax, eax
0x180015022  jnz     short loc_180015038
0x180015024  cmp     [rbp+4Fh+var_C0], r12d
0x180015028  setz    al
0x18001502b  cmp     [rbp+4Fh+var_BC], r12d
0x18001502f  mov     [rbx+41h], al
0x180015032  setz    al
0x180015035  mov     [rbx+40h], al
0x180015038  cmp     byte ptr [rbx+41h], 0
0x18001503c  mov     esi, 4E6Bh
0x180015041  mov     rcx, [rdi]; hDlg
0x180015044  mov     r8d, r12d; uCheck
0x180015047  lea     r14d, [rsi+1]
0x18001504b  mov     edx, r14d
0x18001504e  jnz     short loc_180015052
0x180015050  mov     edx, esi; nIDButton
0x180015052  call    cs:__imp_CheckDlgButton
0x180015058  cmp     byte ptr [rbx+40h], 0
0x18001505c  jz      short loc_180015095
0x18001505e  mov     [rbp+4Fh+var_B8], esi
0x180015061  xor     ebx, ebx
0x180015063  mov     [rbp+4Fh+var_B4], r14d
0x180015067  mov     [rbp+4Fh+var_B0], 4E67h
0x18001506e  movsxd  r8, ebx
0x180015071  lea     rdx, [rbp+4Fh+var_A8]
0x180015075  mov     rcx, rdi
0x180015078  mov     r8d, [rbp+r8*4+4Fh+var_B8]
0x18001507d  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180015082  xor     edx, edx; bEnable
0x180015084  mov     rcx, [rax]; hWnd
0x180015087  call    cs:__imp_EnableWindow
0x18001508d  add     ebx, r12d
0x180015090  cmp     ebx, 3
0x180015093  jb      short loc_18001506E
0x180015095  xor     eax, eax
0x180015097  mov     rcx, [rbp+4Fh+var_40]
0x18001509b  xor     rcx, rsp; StackCookie
0x18001509e  call    __security_check_cookie
0x1800150a3  add     rsp, 0B8h
0x1800150aa  pop     r14
0x1800150ac  pop     r12
0x1800150ae  pop     rdi
0x1800150af  pop     rsi
0x1800150b0  pop     rbx
0x1800150b1  pop     rbp
0x1800150b2  retn
```
