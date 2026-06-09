# CRenameProfileDlg::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x180011d30`
- end: `0x180011e73`
- name: `?ProcessWindowMessage@CRenameProfileDlg@@UEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `323`
- prototype: `__int64 __fastcall(CRenameProfileDlg *__hidden this, HWND, unsigned int, unsigned __int64, __int64, __int64 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800079b0`
- `0x18000a9fc`
- `0x18001181c`
- `0x180011c5c`
- `0x180011d30`

## import_xrefs

- `USER32!SendMessageW` at `0x180011d94`
- `USER32!SendMessageW` at `0x180011d94`
- `USER32!EndDialog` at `0x180011db8`
- `USER32!EndDialog` at `0x180011e06`
- `USER32!EndDialog` at `0x180011db8`
- `USER32!EndDialog` at `0x180011e06`

## pseudocode

```c
_BOOL8 __fastcall CRenameProfileDlg::ProcessWindowMessage(
        CRenameProfileDlg *this,
        HWND a2,
        unsigned int a3,
        HWND a4,
        __int64 a5,
        __int64 *a6,
        unsigned int a7)
{
  HWND *DlgItem; // rax
  int *v10; // [rsp+20h] [rbp-28h]
  _BYTE v11[24]; // [rsp+30h] [rbp-18h] BYREF

  if ( a7 )
    return 0;
  switch ( a3 )
  {
    case 0x110u:
      ATL::CWindow::CenterWindow((CRenameProfileDlg *)((char *)this + 8), a2);
      if ( !*(_BYTE *)(*((_QWORD *)this + 9) + 83LL) )
      {
        DlgItem = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v11, 1);
        SendMessageW(*DlgItem, 0x160Cu, 0, 1);
      }
      *a6 = 0;
      return 1;
    case 0x10u:
      EndDialog(*((HWND *)this + 1), 0);
      *a6 = 0;
      return 1;
    case 0x111u:
      if ( (_WORD)a4 == 1 )
      {
        *a6 = CRenameProfileDlg::OnOk(this, (unsigned __int16)a2, a3, a4, v10);
        return 1;
      }
      if ( (_WORD)a4 == 2 || (_WORD)a4 == 8 )
      {
        EndDialog(*((HWND *)this + 1), 0);
        *a6 = 0;
        return 1;
      }
      break;
  }
  a7 = 1;
  *a6 = ATL::CWindowImplRoot<WTL::CPropertyPageWindow>::ReflectNotifications(this, a3, a4, a5, &a7);
  return a7 != 0;
}

```

## disassembly

```asm
0x180011d30  mov     [rsp+arg_0], rbx
0x180011d35  mov     [rsp+arg_8], rsi
0x180011d3a  push    rdi
0x180011d3b  sub     rsp, 40h
0x180011d3f  cmp     [rsp+48h+arg_30], 0
0x180011d47  mov     r10, r9
0x180011d4a  mov     eax, r8d
0x180011d4d  mov     rdi, rcx
0x180011d50  jnz     loc_180011E61
0x180011d56  cmp     eax, 110h
0x180011d5b  jnz     short loc_180011DAD
0x180011d5d  add     rcx, 8; this
0x180011d61  call    ?CenterWindow@CWindow@ATL@@QEAAHPEAUHWND__@@@Z; ATL::CWindow::CenterWindow(HWND__ *)
0x180011d66  mov     rax, [rdi+48h]
0x180011d6a  mov     ebx, 1
0x180011d6f  cmp     byte ptr [rax+53h], 0
0x180011d73  jnz     short loc_180011D9A
0x180011d75  mov     r8d, ebx
0x180011d78  lea     rdx, [rsp+48h+var_18]
0x180011d7d  lea     rcx, [rdi+8]
0x180011d81  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180011d86  mov     r9d, ebx; lParam
0x180011d89  xor     r8d, r8d; wParam
0x180011d8c  mov     edx, 160Ch; Msg
0x180011d91  mov     rcx, [rax]; hWnd
0x180011d94  call    cs:__imp_SendMessageW
0x180011d9a  mov     rcx, [rsp+48h+arg_28]
0x180011d9f  mov     qword ptr [rcx], 0
0x180011da6  mov     eax, ebx
0x180011da8  jmp     loc_180011E63
0x180011dad  cmp     eax, 10h
0x180011db0  jnz     short loc_180011DD4
0x180011db2  mov     rcx, [rcx+8]; hDlg
0x180011db6  xor     edx, edx; nResult
0x180011db8  call    cs:__imp_EndDialog
0x180011dbe  mov     rax, [rsp+48h+arg_28]
0x180011dc3  mov     qword ptr [rax], 0
0x180011dca  mov     eax, 1
0x180011dcf  jmp     loc_180011E63
0x180011dd4  mov     ebx, 1
0x180011dd9  cmp     eax, 111h
0x180011dde  jnz     short loc_180011E25
0x180011de0  cmp     bx, r10w
0x180011de4  jnz     short loc_180011DF5
0x180011de6  call    ?OnOk@CRenameProfileDlg@@QEAA_JGGPEAUHWND__@@AEAH@Z; CRenameProfileDlg::OnOk(ushort,ushort,HWND__ *,int &)
0x180011deb  mov     rcx, [rsp+48h+arg_28]
0x180011df0  mov     [rcx], rax
0x180011df3  jmp     short loc_180011DA6
0x180011df5  mov     ecx, 2
0x180011dfa  cmp     cx, r10w
0x180011dfe  jnz     short loc_180011E1A
0x180011e00  mov     rcx, [rdi+8]; hDlg
0x180011e04  xor     edx, edx; nResult
0x180011e06  call    cs:__imp_EndDialog
0x180011e0c  mov     rax, [rsp+48h+arg_28]
0x180011e11  mov     qword ptr [rax], 0
0x180011e18  jmp     short loc_180011DA6
0x180011e1a  mov     ecx, 8
0x180011e1f  cmp     cx, r10w
0x180011e23  jz      short loc_180011E00
0x180011e25  mov     r9, [rsp+48h+arg_20]
0x180011e2a  lea     rcx, [rsp+48h+arg_30]
0x180011e32  mov     [rsp+48h+var_28], rcx
0x180011e37  mov     r8, r10
0x180011e3a  mov     rcx, rdi
0x180011e3d  mov     [rsp+48h+arg_30], ebx
0x180011e44  mov     edx, eax
0x180011e46  call    ?ReflectNotifications@?$CWindowImplRoot@VCPropertyPageWindow@WTL@@@ATL@@QEAA_JI_K_JAEAH@Z; ATL::CWindowImplRoot<WTL::CPropertyPageWindow>::ReflectNotifications(uint,unsigned __int64,__int64,int &)
0x180011e4b  mov     rcx, [rsp+48h+arg_28]
0x180011e50  mov     [rcx], rax
0x180011e53  xor     eax, eax
0x180011e55  cmp     [rsp+48h+arg_30], eax
0x180011e5c  setnz   al
0x180011e5f  jmp     short loc_180011E63
0x180011e61  xor     eax, eax
0x180011e63  mov     rbx, [rsp+48h+arg_0]
0x180011e68  mov     rsi, [rsp+48h+arg_8]
0x180011e6d  add     rsp, 40h
0x180011e71  pop     rdi
0x180011e72  retn
```
