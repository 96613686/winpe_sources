# InputBoxDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180073eb0`
- end: `0x18007400e`
- name: `?InputBoxDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `350`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18003512c`
- `0x180073eb0`
- `0x180074014`
- `0x180074230`
- `0x1800745b4`
- `0x180074688`
- `0x1800767a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180073f67`
- `KERNEL32!GetLastError` at `0x180073f67`
- `KERNEL32!SetLastError` at `0x180073f44`
- `KERNEL32!SetLastError` at `0x180073f44`
- `USER32!EndDialog` at `0x180073fab`
- `USER32!EndDialog` at `0x180073fab`
- `USER32!GetDlgItemTextW` at `0x180073f5d`
- `USER32!GetDlgItemTextW` at `0x180073f5d`
- `USER32!WinHelpW` at `0x180073f37`
- `USER32!WinHelpW` at `0x180073f37`
- `USER32!GetWindowLongPtrA` at `0x180073ef4`
- `USER32!GetWindowLongPtrA` at `0x180073ef4`
- `USER32!SetWindowLongPtrA` at `0x180073fc4`
- `USER32!SetWindowLongPtrA` at `0x180073fc4`
- `GDI32!DeleteObject` at `0x180073f9f`
- `GDI32!DeleteObject` at `0x180073f9f`

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
0x180073eb0  mov     [rsp+arg_8], rbx
0x180073eb5  push    rbp
0x180073eb6  push    rsi
0x180073eb7  push    rdi
0x180073eb8  sub     rsp, 830h
0x180073ebf  mov     rax, cs:__security_cookie
0x180073ec6  xor     rax, rsp
0x180073ec9  mov     [rsp+848h+var_28], rax
0x180073ed1  mov     rbx, r9
0x180073ed4  mov     rbp, r8
0x180073ed7  mov     rsi, rcx
0x180073eda  sub     edx, 110h
0x180073ee0  jz      loc_180073FBC
0x180073ee6  cmp     edx, 1
0x180073ee9  jnz     loc_180073FB8
0x180073eef  mov     edx, 10h; nIndex
0x180073ef4  call    cs:__imp_GetWindowLongPtrA
0x180073efa  movzx   edx, bp
0x180073efd  mov     rdi, rax
0x180073f00  sub     edx, 1
0x180073f03  jz      short loc_180073F3F
0x180073f05  sub     edx, 1
0x180073f08  jz      loc_180073F94
0x180073f0e  cmp     edx, 1
0x180073f11  jnz     loc_180073FB8
0x180073f17  mov     rcx, [rax+20h]
0x180073f1b  lea     rdx, [rsp+848h+String]
0x180073f20  mov     ebx, [rax+28h]
0x180073f23  call    LimitStringW
0x180073f28  mov     r9d, ebx; dwData
0x180073f2b  mov     r8d, 1; uCommand
0x180073f31  mov     rdx, rax; lpszHelp
0x180073f34  mov     rcx, rsi; hWndMain
0x180073f37  call    cs:__imp_WinHelpW
0x180073f3d  jmp     short loc_180073FB1
0x180073f3f  xor     ecx, ecx; dwErrCode
0x180073f41  or      ebx, 0FFFFFFFFh
0x180073f44  call    cs:__imp_SetLastError
0x180073f4a  mov     r9d, 0FFh; cchMax
0x180073f50  lea     r8, [rsp+848h+String]; lpString
0x180073f55  mov     edx, 3E8h; nIDDlgItem
0x180073f5a  mov     rcx, rsi; hDlg
0x180073f5d  call    cs:__imp_GetDlgItemTextW
0x180073f63  test    eax, eax
0x180073f65  jnz     short loc_180073F7B
0x180073f67  call    cs:__imp_GetLastError
0x180073f6d  test    eax, eax
0x180073f6f  jnz     short loc_180073F96
0x180073f71  mov     qword ptr [rdi+48h], 0
0x180073f79  jmp     short loc_180073F8E
0x180073f7b  lea     rcx, [rsp+848h+String]; unsigned __int16 *
0x180073f80  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x180073f85  mov     [rdi+48h], rax
0x180073f89  test    rax, rax
0x180073f8c  jz      short loc_180073F96
0x180073f8e  mov     word ptr [rdi+40h], 8
0x180073f94  xor     ebx, ebx
0x180073f96  mov     rcx, [rdi+58h]; ho
0x180073f9a  test    rcx, rcx
0x180073f9d  jz      short loc_180073FA5
0x180073f9f  call    cs:__imp_DeleteObject
0x180073fa5  movsxd  rdx, ebx; nResult
0x180073fa8  mov     rcx, rsi; hDlg
0x180073fab  call    cs:__imp_EndDialog
0x180073fb1  mov     eax, 1
0x180073fb6  jmp     short loc_180073FEB
0x180073fb8  xor     eax, eax
0x180073fba  jmp     short loc_180073FEB
0x180073fbc  mov     r8, rbx; dwNewLong
0x180073fbf  mov     edx, 10h; nIndex
0x180073fc4  call    cs:__imp_SetWindowLongPtrA
0x180073fca  mov     rdx, rbx
0x180073fcd  mov     rcx, rsi; hDlg
0x180073fd0  call    InputBoxLocalize
0x180073fd5  mov     rdx, rbx
0x180073fd8  mov     rcx, rsi; hDlg
0x180073fdb  call    InputBoxSetFields
0x180073fe0  mov     rdx, rbx
0x180073fe3  mov     rcx, rsi; hWnd
0x180073fe6  call    InputBoxPositionDialog
0x180073feb  mov     rcx, [rsp+848h+var_28]
0x180073ff3  xor     rcx, rsp; StackCookie
0x180073ff6  call    __security_check_cookie
0x180073ffb  mov     rbx, [rsp+848h+arg_8]
0x180074003  add     rsp, 830h
0x18007400a  pop     rdi
0x18007400b  pop     rsi
0x18007400c  pop     rbp
0x18007400d  retn
```
