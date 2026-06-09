# CDeleteProfileDlg::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x180011b10`
- end: `0x180011c53`
- name: `?ProcessWindowMessage@CDeleteProfileDlg@@UEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `323`
- prototype: `__int64 __fastcall(CDeleteProfileDlg *__hidden this, HWND, unsigned int, unsigned __int64, __int64, __int64 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800079b0`
- `0x18000a9fc`
- `0x18001181c`
- `0x180011a40`
- `0x180011b10`

## import_xrefs

- `USER32!SendMessageW` at `0x180011b74`
- `USER32!SendMessageW` at `0x180011b74`
- `USER32!EndDialog` at `0x180011b98`
- `USER32!EndDialog` at `0x180011be6`
- `USER32!EndDialog` at `0x180011b98`
- `USER32!EndDialog` at `0x180011be6`

## pseudocode

```c
_BOOL8 __fastcall CDeleteProfileDlg::ProcessWindowMessage(
        CDeleteProfileDlg *this,
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
      ATL::CWindow::CenterWindow((CDeleteProfileDlg *)((char *)this + 8), a2);
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
        *a6 = CDeleteProfileDlg::OnOk(this, (unsigned __int16)a2, a3, a4, v10);
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
0x180011b10  mov     [rsp+arg_0], rbx
0x180011b15  mov     [rsp+arg_8], rsi
0x180011b1a  push    rdi
0x180011b1b  sub     rsp, 40h
0x180011b1f  cmp     [rsp+48h+arg_30], 0
0x180011b27  mov     r10, r9
0x180011b2a  mov     eax, r8d
0x180011b2d  mov     rdi, rcx
0x180011b30  jnz     loc_180011C41
0x180011b36  cmp     eax, 110h
0x180011b3b  jnz     short loc_180011B8D
0x180011b3d  add     rcx, 8; this
0x180011b41  call    ?CenterWindow@CWindow@ATL@@QEAAHPEAUHWND__@@@Z; ATL::CWindow::CenterWindow(HWND__ *)
0x180011b46  mov     rax, [rdi+48h]
0x180011b4a  mov     ebx, 1
0x180011b4f  cmp     byte ptr [rax+53h], 0
0x180011b53  jnz     short loc_180011B7A
0x180011b55  mov     r8d, ebx
0x180011b58  lea     rdx, [rsp+48h+var_18]
0x180011b5d  lea     rcx, [rdi+8]
0x180011b61  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180011b66  mov     r9d, ebx; lParam
0x180011b69  xor     r8d, r8d; wParam
0x180011b6c  mov     edx, 160Ch; Msg
0x180011b71  mov     rcx, [rax]; hWnd
0x180011b74  call    cs:__imp_SendMessageW
0x180011b7a  mov     rcx, [rsp+48h+arg_28]
0x180011b7f  mov     qword ptr [rcx], 0
0x180011b86  mov     eax, ebx
0x180011b88  jmp     loc_180011C43
0x180011b8d  cmp     eax, 10h
0x180011b90  jnz     short loc_180011BB4
0x180011b92  mov     rcx, [rcx+8]; hDlg
0x180011b96  xor     edx, edx; nResult
0x180011b98  call    cs:__imp_EndDialog
0x180011b9e  mov     rax, [rsp+48h+arg_28]
0x180011ba3  mov     qword ptr [rax], 0
0x180011baa  mov     eax, 1
0x180011baf  jmp     loc_180011C43
0x180011bb4  mov     ebx, 1
0x180011bb9  cmp     eax, 111h
0x180011bbe  jnz     short loc_180011C05
0x180011bc0  cmp     bx, r10w
0x180011bc4  jnz     short loc_180011BD5
0x180011bc6  call    ?OnOk@CDeleteProfileDlg@@QEAA_JGGPEAUHWND__@@AEAH@Z; CDeleteProfileDlg::OnOk(ushort,ushort,HWND__ *,int &)
0x180011bcb  mov     rcx, [rsp+48h+arg_28]
0x180011bd0  mov     [rcx], rax
0x180011bd3  jmp     short loc_180011B86
0x180011bd5  mov     ecx, 2
0x180011bda  cmp     cx, r10w
0x180011bde  jnz     short loc_180011BFA
0x180011be0  mov     rcx, [rdi+8]; hDlg
0x180011be4  xor     edx, edx; nResult
0x180011be6  call    cs:__imp_EndDialog
0x180011bec  mov     rax, [rsp+48h+arg_28]
0x180011bf1  mov     qword ptr [rax], 0
0x180011bf8  jmp     short loc_180011B86
0x180011bfa  mov     ecx, 8
0x180011bff  cmp     cx, r10w
0x180011c03  jz      short loc_180011BE0
0x180011c05  mov     r9, [rsp+48h+arg_20]
0x180011c0a  lea     rcx, [rsp+48h+arg_30]
0x180011c12  mov     [rsp+48h+var_28], rcx
0x180011c17  mov     r8, r10
0x180011c1a  mov     rcx, rdi
0x180011c1d  mov     [rsp+48h+arg_30], ebx
0x180011c24  mov     edx, eax
0x180011c26  call    ?ReflectNotifications@?$CWindowImplRoot@VCPropertyPageWindow@WTL@@@ATL@@QEAA_JI_K_JAEAH@Z; ATL::CWindowImplRoot<WTL::CPropertyPageWindow>::ReflectNotifications(uint,unsigned __int64,__int64,int &)
0x180011c2b  mov     rcx, [rsp+48h+arg_28]
0x180011c30  mov     [rcx], rax
0x180011c33  xor     eax, eax
0x180011c35  cmp     [rsp+48h+arg_30], eax
0x180011c3c  setnz   al
0x180011c3f  jmp     short loc_180011C43
0x180011c41  xor     eax, eax
0x180011c43  mov     rbx, [rsp+48h+arg_0]
0x180011c48  mov     rsi, [rsp+48h+arg_8]
0x180011c4d  add     rsp, 40h
0x180011c51  pop     rdi
0x180011c52  retn
```
