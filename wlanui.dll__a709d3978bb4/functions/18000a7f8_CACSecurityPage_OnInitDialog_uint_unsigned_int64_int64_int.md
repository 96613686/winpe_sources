# CACSecurityPage::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x18000a7f8`
- end: `0x18000ac14`
- name: `?OnInitDialog@CACSecurityPage@@QEAA_JI_K_JAEAH@Z`
- size: `1052`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000c290`

## callees

- `0x180001d98`
- `0x180006134`
- `0x180007448`
- `0x180008720`
- `0x180008b0c`
- `0x180008cdc`
- `0x180008e80`
- `0x18000a7f8`
- `0x18000ac1c`
- `0x18000b514`
- `0x18000c824`
- `0x18001bf0a`
- `0x18001bf40`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x18000ab07`
- `GDI32!GetDeviceCaps` at `0x18000ab07`
- `KERNEL32!GetLastError` at `0x18000a8a9`
- `KERNEL32!GetLastError` at `0x18000a8a9`
- `USER32!GetDlgItem` at `0x18000a96f`
- `USER32!GetDlgItem` at `0x18000a982`
- `USER32!GetDlgItem` at `0x18000a995`
- `USER32!GetDlgItem` at `0x18000a9bf`
- `USER32!GetDlgItem` at `0x18000a9d1`
- `USER32!GetDlgItem` at `0x18000aa2c`
- `USER32!GetDlgItem` at `0x18000aa3e`
- `USER32!GetDlgItem` at `0x18000aa50`
- `USER32!GetDlgItem` at `0x18000aa62`
- `USER32!GetDlgItem` at `0x18000a96f`
- `USER32!GetDlgItem` at `0x18000a982`
- `USER32!GetDlgItem` at `0x18000a995`
- `USER32!GetDlgItem` at `0x18000a9bf`
- `USER32!GetDlgItem` at `0x18000a9d1`
- `USER32!GetDlgItem` at `0x18000aa2c`
- `USER32!GetDlgItem` at `0x18000aa3e`
- `USER32!GetDlgItem` at `0x18000aa50`
- `USER32!GetDlgItem` at `0x18000aa62`
- `USER32!SetClassLongPtrW` at `0x18000a948`
- `USER32!SetClassLongPtrW` at `0x18000a960`
- `USER32!SetClassLongPtrW` at `0x18000a948`
- `USER32!SetClassLongPtrW` at `0x18000a960`
- `USER32!GetDoubleClickTime` at `0x18000a910`
- `USER32!GetDoubleClickTime` at `0x18000a910`
- `USER32!EnumChildWindows` at `0x18000aba4`
- `USER32!EnumChildWindows` at `0x18000aba4`
- `USER32!GetWindowLongW` at `0x18000ab89`
- `USER32!GetWindowLongW` at `0x18000ab89`
- `USER32!ReleaseDC` at `0x18000ab2f`
- `USER32!ReleaseDC` at `0x18000ab2f`
- `USER32!GetDC` at `0x18000aaf6`
- `USER32!GetDC` at `0x18000aaf6`
- `USER32!SendMessageW` at `0x18000a8ff`
- `USER32!SendMessageW` at `0x18000a935`
- `USER32!SendMessageW` at `0x18000abdc`
- `USER32!SendMessageW` at `0x18000a8ff`
- `USER32!SendMessageW` at `0x18000a935`
- `USER32!SendMessageW` at `0x18000abdc`
- `USER32!GetParent` at `0x18000a952`
- `USER32!GetParent` at `0x18000a952`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::OnInitDialog(CACSecurityPage *this)
{
  __int64 v1; // rax
  __int64 v3; // r12
  __int64 v4; // rbx
  __int64 v5; // rcx
  HWND v6; // rcx
  HWND TooltipWnd; // rax
  int v8; // eax
  HWND Parent; // rax
  _QWORD *v10; // rdi
  HWND DlgItem; // rbx
  _QWORD *v12; // r15
  HWND v13; // rsi
  HWND v14; // rbx
  HWND v15; // rdi
  int inited; // edi
  HDC DC; // rbx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  double v21; // xmm0_8
  HWND v22; // rcx
  LONG WindowLongW; // eax
  HWND v24; // rcx
  int v26[4]; // [rsp+30h] [rbp-61h] BYREF
  LPARAM lParam[10]; // [rsp+40h] [rbp-51h] BYREF

  v1 = *((_QWORD *)this + 5);
  v26[0] = 0;
  v3 = 0;
  v4 = *(_QWORD *)(v1 + 552);
  v5 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + 424LL);
  if ( !v5 )
  {
    CACSecurityPage::InitMSMSecConnectionProfile(this);
    v5 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + 424LL);
  }
  if ( *(_DWORD *)(v5 + 32) && *(_DWORD *)(v5 + 40) )
    v3 = *(_QWORD *)(v5 + 48);
  memset_0(lParam, 0, 0x48u);
  if ( !*((_QWORD *)this + 76) )
  {
    v6 = (HWND)*((_QWORD *)this + 1);
    *((_QWORD *)this + 77) = v6;
    TooltipWnd = CreateTooltipWnd(v6);
    *((_QWORD *)this + 76) = TooltipWnd;
    if ( TooltipWnd )
    {
      lParam[1] = *((_QWORD *)this + 77);
      lParam[5] = (LPARAM)hInstance;
      lParam[6] = (LPARAM)&String;
      lParam[7] = 0;
      lParam[8] = 0;
      lParam[0] = 0x1A000000048LL;
      memset(&lParam[2], 0, 24);
      v8 = SendMessageW(TooltipWnd, 0x415u, 2u, 0);
      *((_DWORD *)this + 157) = v8;
      if ( !v8 )
        *((_DWORD *)this + 157) = 10 * GetDoubleClickTime();
      SendMessageW(*((HWND *)this + 76), 0x432u, 0, (LPARAM)lParam);
    }
    else
    {
      GetLastError();
    }
  }
  SetClassLongPtrW(*((HWND *)this + 1), -12, 0);
  Parent = GetParent(*((HWND *)this + 1));
  SetClassLongPtrW(Parent, -12, 0);
  *((_QWORD *)this + 8) = GetDlgItem(*((HWND *)this + 1), 1111);
  *((_QWORD *)this + 9) = GetDlgItem(*((HWND *)this + 1), 1112);
  *((_QWORD *)this + 10) = GetDlgItem(*((HWND *)this + 1), 1129);
  v10 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v10 )
  {
    DlgItem = GetDlgItem(*((HWND *)this + 1), 1121);
    v10[4] = GetDlgItem(*((HWND *)this + 1), 1119);
    v10[5] = DlgItem;
    *((_DWORD *)v10 + 6) = 0;
    *v10 = this;
    v10[1] = *((_QWORD *)this + 5);
    v10[2] = *((_QWORD *)this + 1);
    v10[6] = 0;
  }
  else
  {
    v10 = 0;
  }
  *((_QWORD *)this + 167) = v10;
  v12 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v12 )
  {
    v13 = GetDlgItem(*((HWND *)this + 1), 1125);
    v14 = GetDlgItem(*((HWND *)this + 1), 1116);
    v15 = GetDlgItem(*((HWND *)this + 1), 1115);
    v12[3] = GetDlgItem(*((HWND *)this + 1), 1117);
    v12[4] = v15;
    v12[6] = v14;
    v12[7] = v13;
    *((_DWORD *)v12 + 16) = 0;
    *(_QWORD *)((char *)v12 + 68) = 1;
    v12[5] = v15;
    *v12 = this;
    v12[1] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 552LL) + 32LL) + 424LL);
    v12[2] = *((_QWORD *)this + 1);
  }
  else
  {
    v12 = 0;
  }
  *((_QWORD *)this + 166) = v12;
  inited = CACSecurityPage::InitAuthCipherData(this);
  if ( inited >= 0 )
  {
    NetworkKeyControls::OnInitDialog(*((NetworkKeyControls **)this + 166));
    if ( !v3 || (inited = EapControls::InitOneXUIControls(*((EapControls **)this + 167)), inited >= 0) )
    {
      DC = GetDC(*((HWND *)this + 1));
      *((double *)this + 163) = (float)((float)GetDeviceCaps(DC, 88) / 96.0);
      ReleaseDC(*((HWND *)this + 1), DC);
      CACSecurityPage::OnThemeChange(this, v18, v19, v20, v26);
      if ( *((_DWORD *)this + 23) )
      {
        v21 = *((double *)this + 163) * 60.0;
        v22 = (HWND)*((_QWORD *)this + 1);
        *((_QWORD *)this + 159) = v22;
        *((_DWORD *)this + 320) = 0;
        *((_QWORD *)this + 161) = 0;
        *((_DWORD *)this + 321) = (int)v21;
        WindowLongW = GetWindowLongW(v22, -20);
        v24 = (HWND)*((_QWORD *)this + 159);
        *((_DWORD *)this + 324) = WindowLongW & 0x400000;
        EnumChildWindows(v24, (WNDENUMPROC)MoveControlsCallback, (LPARAM)this + 1272);
        if ( *((_DWORD *)this + 23) )
          CACSecurityPage::InitReadOnlyProfile(this);
      }
      CACSecurityPage::RefreshControls(this);
      if ( *((_DWORD *)this + 314) == 2 )
        SendMessageW(*((HWND *)this + 1), 0x111u, 0x469u, *((_QWORD *)this + 1));
      *((_DWORD *)this + 328) = 1;
    }
  }
  return LresFromHr(inited);
}

```

## disassembly

```asm
0x18000a7f8  push    rbp
0x18000a7fa  push    rbx
0x18000a7fb  push    rsi
0x18000a7fc  push    rdi
0x18000a7fd  push    r12
0x18000a7ff  push    r13
0x18000a801  push    r14
0x18000a803  push    r15
0x18000a805  lea     rbp, [rsp-17h]
0x18000a80a  sub     rsp, 0A8h
0x18000a811  mov     rax, cs:__security_cookie
0x18000a818  xor     rax, rsp
0x18000a81b  mov     [rbp+4Fh+var_50], rax
0x18000a81f  mov     rax, [rcx+28h]
0x18000a823  xor     r13d, r13d
0x18000a826  mov     r14, rcx
0x18000a829  mov     [rbp+4Fh+var_B0], r13d
0x18000a82d  mov     r12d, r13d
0x18000a830  mov     rbx, [rax+228h]
0x18000a837  mov     rax, [rbx+20h]
0x18000a83b  mov     rcx, [rax+1A8h]
0x18000a842  test    rcx, rcx
0x18000a845  jnz     short loc_18000A85A
0x18000a847  mov     rcx, r14; this
0x18000a84a  call    ?InitMSMSecConnectionProfile@CACSecurityPage@@AEAAJXZ; CACSecurityPage::InitMSMSecConnectionProfile(void)
0x18000a84f  mov     rax, [rbx+20h]
0x18000a853  mov     rcx, [rax+1A8h]
0x18000a85a  cmp     [rcx+20h], r13d
0x18000a85e  jz      short loc_18000A86A
0x18000a860  cmp     [rcx+28h], r13d
0x18000a864  jz      short loc_18000A86A
0x18000a866  mov     r12, [rcx+30h]
0x18000a86a  mov     ebx, 48h ; 'H'
0x18000a86f  lea     rcx, [rbp+4Fh+lParam]; void *
0x18000a873  mov     r8d, ebx; Size
0x18000a876  xor     edx, edx; Val
0x18000a878  call    memset_0
0x18000a87d  cmp     [r14+260h], r13
0x18000a884  jnz     loc_18000A93B
0x18000a88a  mov     rcx, [r14+8]; hWndParent
0x18000a88e  mov     [r14+268h], rcx
0x18000a895  call    ?CreateTooltipWnd@@YAPEAUHWND__@@PEAU1@H@Z; CreateTooltipWnd(HWND__ *,int)
0x18000a89a  mov     [r14+260h], rax
0x18000a8a1  mov     rcx, rax; hWnd
0x18000a8a4  test    rax, rax
0x18000a8a7  jnz     short loc_18000A8B4
0x18000a8a9  call    cs:__imp_GetLastError
0x18000a8af  jmp     loc_18000A93B
0x18000a8b4  mov     rax, [r14+268h]
0x18000a8bb  xor     r9d, r9d; lParam
0x18000a8be  mov     [rbp+4Fh+var_98], rax
0x18000a8c2  mov     edx, 415h; Msg
0x18000a8c7  mov     rax, cs:hInstance
0x18000a8ce  mov     [rbp+4Fh+var_78], rax
0x18000a8d2  lea     rax, String
0x18000a8d9  lea     r8d, [r9+2]; wParam
0x18000a8dd  mov     [rbp+4Fh+var_70], rax
0x18000a8e1  mov     [rbp+4Fh+var_88], r13
0x18000a8e5  mov     [rbp+4Fh+var_80], r13
0x18000a8e9  mov     [rbp+4Fh+var_68], r13
0x18000a8ed  mov     [rbp+4Fh+var_60], r13
0x18000a8f1  mov     dword ptr [rbp+4Fh+lParam], ebx
0x18000a8f4  mov     dword ptr [rbp+4Fh+lParam+4], 1A0h
0x18000a8fb  mov     [rbp+4Fh+var_90], r13
0x18000a8ff  call    cs:__imp_SendMessageW
0x18000a905  mov     [r14+274h], eax
0x18000a90c  test    eax, eax
0x18000a90e  jnz     short loc_18000A922
0x18000a910  call    cs:__imp_GetDoubleClickTime
0x18000a916  lea     ecx, [rax+rax*4]
0x18000a919  add     ecx, ecx
0x18000a91b  mov     [r14+274h], ecx
0x18000a922  mov     rcx, [r14+260h]; hWnd
0x18000a929  lea     r9, [rbp+4Fh+lParam]; lParam
0x18000a92d  xor     r8d, r8d; wParam
0x18000a930  mov     edx, 432h; Msg
0x18000a935  call    cs:__imp_SendMessageW
0x18000a93b  mov     rcx, [r14+8]; hWnd
0x18000a93f  xor     r8d, r8d; dwNewLong
0x18000a942  lea     ebx, [r8-0Ch]
0x18000a946  mov     edx, ebx; nIndex
0x18000a948  call    cs:__imp_SetClassLongPtrW
0x18000a94e  mov     rcx, [r14+8]; hWnd
0x18000a952  call    cs:__imp_GetParent
0x18000a958  xor     r8d, r8d; dwNewLong
0x18000a95b  mov     edx, ebx; nIndex
0x18000a95d  mov     rcx, rax; hWnd
0x18000a960  call    cs:__imp_SetClassLongPtrW
0x18000a966  mov     rcx, [r14+8]; hDlg
0x18000a96a  mov     edx, 457h; nIDDlgItem
0x18000a96f  call    cs:__imp_GetDlgItem
0x18000a975  mov     [r14+40h], rax
0x18000a979  mov     edx, 458h; nIDDlgItem
0x18000a97e  mov     rcx, [r14+8]; hDlg
0x18000a982  call    cs:__imp_GetDlgItem
0x18000a988  mov     [r14+48h], rax
0x18000a98c  mov     edx, 469h; nIDDlgItem
0x18000a991  mov     rcx, [r14+8]; hDlg
0x18000a995  call    cs:__imp_GetDlgItem
0x18000a99b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a9a2  mov     [r14+50h], rax
0x18000a9a6  lea     ecx, [rbx+44h]; unsigned __int64
0x18000a9a9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a9ae  mov     rdi, rax
0x18000a9b1  test    rax, rax
0x18000a9b4  jz      short loc_18000A9FC
0x18000a9b6  mov     rcx, [r14+8]; hDlg
0x18000a9ba  mov     edx, 461h; nIDDlgItem
0x18000a9bf  call    cs:__imp_GetDlgItem
0x18000a9c5  mov     rcx, [r14+8]; hDlg
0x18000a9c9  mov     edx, 45Fh; nIDDlgItem
0x18000a9ce  mov     rbx, rax
0x18000a9d1  call    cs:__imp_GetDlgItem
0x18000a9d7  mov     [rdi+20h], rax
0x18000a9db  mov     [rdi+28h], rbx
0x18000a9df  mov     [rdi+18h], r13d
0x18000a9e3  mov     [rdi], r14
0x18000a9e6  mov     rax, [r14+28h]
0x18000a9ea  mov     [rdi+8], rax
0x18000a9ee  mov     rax, [r14+8]
0x18000a9f2  mov     [rdi+10h], rax
0x18000a9f6  mov     [rdi+30h], r13
0x18000a9fa  jmp     short loc_18000A9FF
0x18000a9fc  mov     rdi, r13
0x18000a9ff  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000aa06  mov     [r14+538h], rdi
0x18000aa0d  mov     ecx, 50h ; 'P'; unsigned __int64
0x18000aa12  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000aa17  mov     r15, rax
0x18000aa1a  test    rax, rax
0x18000aa1d  jz      loc_18000AAAF
0x18000aa23  mov     rcx, [r14+8]; hDlg
0x18000aa27  mov     edx, 465h; nIDDlgItem
0x18000aa2c  call    cs:__imp_GetDlgItem
0x18000aa32  mov     rcx, [r14+8]; hDlg
0x18000aa36  mov     edx, 45Ch; nIDDlgItem
0x18000aa3b  mov     rsi, rax
0x18000aa3e  call    cs:__imp_GetDlgItem
0x18000aa44  mov     rcx, [r14+8]; hDlg
0x18000aa48  mov     edx, 45Bh; nIDDlgItem
0x18000aa4d  mov     rbx, rax
0x18000aa50  call    cs:__imp_GetDlgItem
0x18000aa56  mov     rcx, [r14+8]; hDlg
0x18000aa5a  mov     edx, 45Dh; nIDDlgItem
0x18000aa5f  mov     rdi, rax
0x18000aa62  call    cs:__imp_GetDlgItem
0x18000aa68  mov     [r15+18h], rax
0x18000aa6c  mov     [r15+20h], rdi
0x18000aa70  mov     [r15+30h], rbx
0x18000aa74  mov     [r15+38h], rsi
0x18000aa78  mov     [r15+40h], r13d
0x18000aa7c  mov     qword ptr [r15+44h], 1
0x18000aa84  mov     [r15+28h], rdi
0x18000aa88  mov     [r15], r14
0x18000aa8b  mov     rax, [r14+28h]
0x18000aa8f  mov     rcx, [rax+228h]
0x18000aa96  mov     rax, [rcx+20h]
0x18000aa9a  mov     rcx, [rax+1A8h]
0x18000aaa1  mov     [r15+8], rcx
0x18000aaa5  mov     rax, [r14+8]
0x18000aaa9  mov     [r15+10h], rax
0x18000aaad  jmp     short loc_18000AAB2
0x18000aaaf  mov     r15, r13
0x18000aab2  mov     rcx, r14; this
0x18000aab5  mov     [r14+530h], r15
0x18000aabc  call    ?InitAuthCipherData@CACSecurityPage@@AEAAJXZ; CACSecurityPage::InitAuthCipherData(void)
0x18000aac1  mov     edi, eax
0x18000aac3  test    eax, eax
0x18000aac5  js      loc_18000ABED
0x18000aacb  mov     rcx, [r14+530h]; this
0x18000aad2  call    ?OnInitDialog@NetworkKeyControls@@QEAAXXZ; NetworkKeyControls::OnInitDialog(void)
0x18000aad7  test    r12, r12
0x18000aada  jz      short loc_18000AAF2
0x18000aadc  mov     rcx, [r14+538h]; this
0x18000aae3  call    ?InitOneXUIControls@EapControls@@QEAAJXZ; EapControls::InitOneXUIControls(void)
0x18000aae8  mov     edi, eax
0x18000aaea  test    eax, eax
0x18000aaec  js      loc_18000ABED
0x18000aaf2  mov     rcx, [r14+8]; hWnd
0x18000aaf6  call    cs:__imp_GetDC
0x18000aafc  mov     rcx, rax; hdc
0x18000aaff  mov     edx, 58h ; 'X'; index
0x18000ab04  mov     rbx, rax
0x18000ab07  call    cs:__imp_GetDeviceCaps
0x18000ab0d  mov     rdx, rbx; hDC
0x18000ab10  movd    xmm0, eax
0x18000ab14  cvtdq2ps xmm0, xmm0
0x18000ab17  divss   xmm0, cs:__real@42c00000
0x18000ab1f  cvtps2pd xmm0, xmm0
0x18000ab22  movsd   qword ptr [r14+518h], xmm0
0x18000ab2b  mov     rcx, [r14+8]; hWnd
0x18000ab2f  call    cs:__imp_ReleaseDC
0x18000ab35  lea     rax, [rbp+4Fh+var_B0]
0x18000ab39  mov     rcx, r14; this
0x18000ab3c  mov     [rsp+0E0h+var_C0], rax; int *
0x18000ab41  call    ?OnThemeChange@CACSecurityPage@@QEAA_JI_K_JAEAH@Z; CACSecurityPage::OnThemeChange(uint,unsigned __int64,__int64,int &)
0x18000ab46  cmp     [r14+5Ch], r13d
0x18000ab4a  jz      short loc_18000ABB8
0x18000ab4c  movsd   xmm0, qword ptr [r14+518h]
0x18000ab55  lea     rbx, [r14+4F8h]
0x18000ab5c  mulsd   xmm0, cs:__real@404e000000000000
0x18000ab64  mov     edx, 0FFFFFFECh; nIndex
0x18000ab69  mov     rcx, [r14+8]; hWnd
0x18000ab6d  mov     [rbx], rcx
0x18000ab70  mov     [r14+500h], r13d
0x18000ab77  mov     [r14+508h], r13
0x18000ab7e  cvttsd2si eax, xmm0
0x18000ab82  mov     [r14+504h], eax
0x18000ab89  call    cs:__imp_GetWindowLongW
0x18000ab8f  mov     rcx, [rbx]; hWndParent
0x18000ab92  lea     rdx, ?MoveControlsCallback@@YAHPEAUHWND__@@_J@Z; lpEnumFunc
0x18000ab99  and     eax, 400000h
0x18000ab9e  mov     r8, rbx; lParam
0x18000aba1  mov     [rbx+18h], eax
0x18000aba4  call    cs:__imp_EnumChildWindows
0x18000abaa  cmp     [r14+5Ch], r13d
0x18000abae  jz      short loc_18000ABB8
0x18000abb0  mov     rcx, r14; this
0x18000abb3  call    ?InitReadOnlyProfile@CACSecurityPage@@AEAAXXZ; CACSecurityPage::InitReadOnlyProfile(void)
0x18000abb8  mov     rcx, r14; this
0x18000abbb  call    ?RefreshControls@CACSecurityPage@@AEAA_JXZ; CACSecurityPage::RefreshControls(void)
0x18000abc0  cmp     dword ptr [r14+4E8h], 2
0x18000abc8  jnz     short loc_18000ABE2
0x18000abca  mov     rcx, [r14+8]; hWnd
0x18000abce  mov     edx, 111h; Msg
0x18000abd3  mov     r9, rcx; lParam
0x18000abd6  mov     r8d, 469h; wParam
0x18000abdc  call    cs:__imp_SendMessageW
0x18000abe2  mov     dword ptr [r14+520h], 1
0x18000abed  mov     ecx, edi; int
0x18000abef  call    ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
0x18000abf4  mov     rcx, [rbp+4Fh+var_50]
0x18000abf8  xor     rcx, rsp; StackCookie
0x18000abfb  call    __security_check_cookie
0x18000ac00  add     rsp, 0A8h
0x18000ac07  pop     r15
0x18000ac09  pop     r14
0x18000ac0b  pop     r13
0x18000ac0d  pop     r12
0x18000ac0f  pop     rdi
0x18000ac10  pop     rsi
0x18000ac11  pop     rbx
0x18000ac12  pop     rbp
0x18000ac13  retn
```
