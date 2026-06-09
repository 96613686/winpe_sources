# InputBoxDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800766f0`
- end: `0x180076882`
- name: `?InputBoxDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `402`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18001199c`
- `0x1800766f0`
- `0x180076888`
- `0x180076ae4`
- `0x180076eec`
- `0x180076fdc`
- `0x180079490`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800767c2`
- `KERNEL32!GetLastError` at `0x1800767c2`
- `KERNEL32!SetLastError` at `0x180076793`
- `KERNEL32!SetLastError` at `0x180076793`
- `USER32!EndDialog` at `0x180076812`
- `USER32!EndDialog` at `0x180076812`
- `USER32!GetDlgItemTextW` at `0x1800767b2`
- `USER32!GetDlgItemTextW` at `0x1800767b2`
- `USER32!WinHelpW` at `0x18007677d`
- `USER32!WinHelpW` at `0x18007677d`
- `USER32!GetWindowLongPtrA` at `0x180076734`
- `USER32!GetWindowLongPtrA` at `0x180076734`
- `USER32!SetWindowLongPtrA` at `0x180076831`
- `USER32!SetWindowLongPtrA` at `0x180076831`
- `GDI32!DeleteObject` at `0x180076800`
- `GDI32!DeleteObject` at `0x180076800`

## pseudocode

```c
INT_PTR __fastcall InputBoxDlgProc(HWND a1, int a2, __int16 a3, LONG_PTR a4)
{
  int v7; // edx
  LONG_PTR WindowLongPtrA; // rax
  LONG_PTR v9; // rdi
  unsigned int v10; // ebx
  const WCHAR *v11; // rax
  int v12; // ebx
  unsigned __int16 *v13; // rax
  void *v14; // rcx
  WCHAR String[1024]; // [rsp+20h] [rbp-828h] BYREF

  v7 = a2 - 272;
  if ( v7 )
  {
    if ( v7 != 1 )
      return 0;
    WindowLongPtrA = GetWindowLongPtrA(a1, 16);
    v9 = WindowLongPtrA;
    if ( a3 != 1 )
    {
      if ( a3 != 2 )
      {
        if ( a3 == 3 )
        {
          v10 = *(_DWORD *)(WindowLongPtrA + 40);
          v11 = (const WCHAR *)LimitStringW(*(_QWORD *)(WindowLongPtrA + 32), String);
          WinHelpW(a1, v11, 1u, v10);
          return 1;
        }
        return 0;
      }
      goto LABEL_12;
    }
    v12 = -1;
    SetLastError(0);
    if ( GetDlgItemTextW(a1, 1000, String, 255) )
    {
      v13 = _SysAllocString(String);
      *(_QWORD *)(v9 + 72) = v13;
      if ( v13 )
        goto LABEL_11;
    }
    else if ( !GetLastError() )
    {
      *(_QWORD *)(v9 + 72) = 0;
LABEL_11:
      *(_WORD *)(v9 + 64) = 8;
LABEL_12:
      v12 = 0;
    }
    v14 = *(void **)(v9 + 88);
    if ( v14 )
      DeleteObject(v14);
    EndDialog(a1, v12);
    return 1;
  }
  SetWindowLongPtrA(a1, 16, a4);
  InputBoxLocalize(a1);
  InputBoxSetFields(a1);
  return InputBoxPositionDialog(a1, a4);
}

```

## disassembly

```asm
0x1800766f0  mov     [rsp+arg_8], rbx
0x1800766f5  push    rbp
0x1800766f6  push    rsi
0x1800766f7  push    rdi
0x1800766f8  sub     rsp, 830h
0x1800766ff  mov     rax, cs:__security_cookie
0x180076706  xor     rax, rsp
0x180076709  mov     [rsp+848h+var_28], rax
0x180076711  mov     rbx, r9
0x180076714  mov     rbp, r8
0x180076717  mov     rsi, rcx
0x18007671a  sub     edx, 110h
0x180076720  jz      loc_180076829
0x180076726  cmp     edx, 1
0x180076729  jnz     loc_180076825
0x18007672f  mov     edx, 10h; nIndex
0x180076734  call    cs:__imp_GetWindowLongPtrA
0x18007673b  nop     dword ptr [rax+rax+00h]
0x180076740  movzx   edx, bp
0x180076743  mov     rdi, rax
0x180076746  sub     edx, 1
0x180076749  jz      short loc_18007678E
0x18007674b  sub     edx, 1
0x18007674e  jz      loc_1800767F5
0x180076754  cmp     edx, 1
0x180076757  jnz     loc_180076825
0x18007675d  mov     rcx, [rax+20h]
0x180076761  lea     rdx, [rsp+848h+String]
0x180076766  mov     ebx, [rax+28h]
0x180076769  call    LimitStringW
0x18007676e  mov     r9d, ebx; dwData
0x180076771  mov     r8d, 1; uCommand
0x180076777  mov     rdx, rax; lpszHelp
0x18007677a  mov     rcx, rsi; hWndMain
0x18007677d  call    cs:__imp_WinHelpW
0x180076784  nop     dword ptr [rax+rax+00h]
0x180076789  jmp     loc_18007681E
0x18007678e  xor     ecx, ecx; dwErrCode
0x180076790  or      ebx, 0FFFFFFFFh
0x180076793  call    cs:__imp_SetLastError
0x18007679a  nop     dword ptr [rax+rax+00h]
0x18007679f  mov     r9d, 0FFh; cchMax
0x1800767a5  lea     r8, [rsp+848h+String]; lpString
0x1800767aa  mov     edx, 3E8h; nIDDlgItem
0x1800767af  mov     rcx, rsi; hDlg
0x1800767b2  call    cs:__imp_GetDlgItemTextW
0x1800767b9  nop     dword ptr [rax+rax+00h]
0x1800767be  test    eax, eax
0x1800767c0  jnz     short loc_1800767DC
0x1800767c2  call    cs:__imp_GetLastError
0x1800767c9  nop     dword ptr [rax+rax+00h]
0x1800767ce  test    eax, eax
0x1800767d0  jnz     short loc_1800767F7
0x1800767d2  mov     qword ptr [rdi+48h], 0
0x1800767da  jmp     short loc_1800767EF
0x1800767dc  lea     rcx, [rsp+848h+String]; unsigned __int16 *
0x1800767e1  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x1800767e6  mov     [rdi+48h], rax
0x1800767ea  test    rax, rax
0x1800767ed  jz      short loc_1800767F7
0x1800767ef  mov     word ptr [rdi+40h], 8
0x1800767f5  xor     ebx, ebx
0x1800767f7  mov     rcx, [rdi+58h]; ho
0x1800767fb  test    rcx, rcx
0x1800767fe  jz      short loc_18007680C
0x180076800  call    cs:__imp_DeleteObject
0x180076807  nop     dword ptr [rax+rax+00h]
0x18007680c  movsxd  rdx, ebx; nResult
0x18007680f  mov     rcx, rsi; hDlg
0x180076812  call    cs:__imp_EndDialog
0x180076819  nop     dword ptr [rax+rax+00h]
0x18007681e  mov     eax, 1
0x180076823  jmp     short loc_18007685E
0x180076825  xor     eax, eax
0x180076827  jmp     short loc_18007685E
0x180076829  mov     r8, rbx; dwNewLong
0x18007682c  mov     edx, 10h; nIndex
0x180076831  call    cs:__imp_SetWindowLongPtrA
0x180076838  nop     dword ptr [rax+rax+00h]
0x18007683d  mov     rdx, rbx
0x180076840  mov     rcx, rsi; hDlg
0x180076843  call    InputBoxLocalize
0x180076848  mov     rdx, rbx
0x18007684b  mov     rcx, rsi; hDlg
0x18007684e  call    InputBoxSetFields
0x180076853  mov     rdx, rbx
0x180076856  mov     rcx, rsi; hWnd
0x180076859  call    InputBoxPositionDialog
0x18007685e  mov     rcx, [rsp+848h+var_28]
0x180076866  xor     rcx, rsp; StackCookie
0x180076869  call    __security_check_cookie
0x18007686e  mov     rbx, [rsp+848h+arg_8]
0x180076876  add     rsp, 830h
0x18007687d  pop     rdi
0x18007687e  pop     rsi
0x18007687f  pop     rbp
0x180076880  retn
```
