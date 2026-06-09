# AccessibilityDialog::staticWindowProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x140023370`
- end: `0x1400234df`
- name: `?staticWindowProc@AccessibilityDialog@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `367`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14002116c`
- `0x14002235c`
- `0x140022d64`
- `0x140022dcc`
- `0x140023370`

## import_xrefs

- `USER32!SetWindowPos` at `0x1400234b4`
- `USER32!SetWindowPos` at `0x1400234b4`
- `USER32!GetWindowLongPtrW` at `0x1400233b0`
- `USER32!GetWindowLongPtrW` at `0x1400233b0`
- `USER32!DefWindowProcW` at `0x1400233e7`
- `USER32!DefWindowProcW` at `0x1400233e7`
- `USER32!SetWindowLongPtrW` at `0x14002339d`
- `USER32!SetWindowLongPtrW` at `0x14002339d`
- `USER32!KillTimer` at `0x140023410`
- `USER32!KillTimer` at `0x140023410`
- `USER32!SetFocus` at `0x140023451`
- `USER32!SetFocus` at `0x140023451`
- `USER32!GetFocus` at `0x14002343d`
- `USER32!GetFocus` at `0x14002343d`

## string_xrefs

- `0x140023467`: `enduser\ezap\xamlcommon\xamlui.cpp`
- `0x1400234cd`: `enduser\ezap\xamlcommon\xamlui.cpp`

## pseudocode

```c
LRESULT __fastcall AccessibilityDialog::staticWindowProc(HWND hWnd, UINT Msg, WPARAM wParam, LONG_PTR *lParam)
{
  LONG_PTR WindowLongPtrW; // rax
  AccessibilityDialog *v9; // rdi
  __int64 v10; // rbx
  __int64 v12; // rax
  HWND v13; // rdi
  const char *v14; // r9
  __int64 v15; // rcx
  const char *v16; // r9
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( Msg == 129 )
  {
    if ( *lParam )
      SetWindowLongPtrW(hWnd, -21, *lParam);
    return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
  }
  WindowLongPtrW = GetWindowLongPtrW(hWnd, -21);
  v9 = (AccessibilityDialog *)WindowLongPtrW;
  v10 = 0;
  switch ( Msg )
  {
    case 5u:
      v15 = *(_QWORD *)(WindowLongPtrW + 48);
      if ( v15 && !SetWindowPos(*(HWND *)(v15 + 16), 0, 0, 0, (__int16)lParam, SWORD1(lParam), 0x56u) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x13B,
          (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
          v16);
      break;
    case 7u:
      v12 = *(_QWORD *)(WindowLongPtrW + 48);
      if ( v12 )
      {
        v13 = *(HWND *)(v12 + 16);
        if ( GetFocus() != v13 && !SetFocus(v13) )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x135,
            (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
            v14);
      }
      break;
    case 0x10u:
      AccessibilityDialog::OnClose((AccessibilityDialog *)WindowLongPtrW);
      return v10;
    case 0x113u:
      KillTimer(*(HWND *)(WindowLongPtrW + 40), 0x64u);
      AccessibilityDialog::SetToggleUiStates(v9);
      return v10;
    default:
      return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
  }
  return v10;
}

```

## disassembly

```asm
0x140023370  push    rbx
0x140023372  push    rbp
0x140023373  push    rsi
0x140023374  push    rdi
0x140023375  push    r14
0x140023377  push    r15
0x140023379  sub     rsp, 48h
0x14002337d  mov     r14, r9
0x140023380  mov     r15, r8
0x140023383  mov     esi, edx
0x140023385  mov     rbp, rcx
0x140023388  cmp     edx, 81h
0x14002338e  jnz     short loc_1400233AB
0x140023390  xor     ebx, ebx
0x140023392  cmp     [r9], rbx
0x140023395  jz      short loc_1400233DC
0x140023397  mov     r8, [r9]; dwNewLong
0x14002339a  lea     edx, [rbx-15h]; nIndex
0x14002339d  call    cs:__imp_SetWindowLongPtrW
0x1400233a4  nop     dword ptr [rax+rax+00h]
0x1400233a9  jmp     short loc_1400233DC
0x1400233ab  mov     edx, 0FFFFFFEBh; nIndex
0x1400233b0  call    cs:__imp_GetWindowLongPtrW
0x1400233b7  nop     dword ptr [rax+rax+00h]
0x1400233bc  mov     rdi, rax
0x1400233bf  xor     ebx, ebx
0x1400233c1  cmp     esi, 5
0x1400233c4  jz      loc_14002347D
0x1400233ca  cmp     esi, 7
0x1400233cd  jz      short loc_140023430
0x1400233cf  cmp     esi, 10h
0x1400233d2  jz      short loc_140023426
0x1400233d4  cmp     esi, 113h
0x1400233da  jz      short loc_140023407
0x1400233dc  mov     r9, r14; lParam
0x1400233df  mov     r8, r15; wParam
0x1400233e2  mov     edx, esi; Msg
0x1400233e4  mov     rcx, rbp; hWnd
0x1400233e7  call    cs:__imp_DefWindowProcW
0x1400233ee  nop     dword ptr [rax+rax+00h]
0x1400233f3  mov     rbx, rax
0x1400233f6  mov     rax, rbx
0x1400233f9  add     rsp, 48h
0x1400233fd  pop     r15
0x1400233ff  pop     r14
0x140023401  pop     rdi
0x140023402  pop     rsi
0x140023403  pop     rbp
0x140023404  pop     rbx
0x140023405  retn
0x140023407  mov     edx, 64h ; 'd'; uIDEvent
0x14002340c  mov     rcx, [rax+28h]; hWnd
0x140023410  call    cs:__imp_KillTimer
0x140023417  nop     dword ptr [rax+rax+00h]
0x14002341c  mov     rcx, rdi; this
0x14002341f  call    ?SetToggleUiStates@AccessibilityDialog@@AEAAXXZ; AccessibilityDialog::SetToggleUiStates(void)
0x140023424  jmp     short loc_1400233F6
0x140023426  mov     rcx, rdi; this
0x140023429  call    ?OnClose@AccessibilityDialog@@AEAAXXZ; AccessibilityDialog::OnClose(void)
0x14002342e  jmp     short loc_1400233F6
0x140023430  mov     rax, [rax+30h]
0x140023434  test    rax, rax
0x140023437  jz      short loc_1400233F6
0x140023439  mov     rdi, [rax+10h]
0x14002343d  call    cs:__imp_GetFocus
0x140023444  nop     dword ptr [rax+rax+00h]
0x140023449  cmp     rax, rdi
0x14002344c  jz      short loc_1400233F6
0x14002344e  mov     rcx, rdi; hWnd
0x140023451  call    cs:__imp_SetFocus
0x140023458  nop     dword ptr [rax+rax+00h]
0x14002345d  test    rax, rax
0x140023460  jnz     short loc_1400233F6
0x140023462  mov     rcx, [rsp+78h]; this
0x140023467  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x14002346e  mov     edx, 135h; void *
0x140023473  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x140023478  jmp     loc_1400233F6
0x14002347d  mov     rcx, [rax+30h]
0x140023481  test    rcx, rcx
0x140023484  jz      loc_1400233F6
0x14002348a  mov     rax, r14
0x14002348d  shr     rax, 10h
0x140023491  movsx   edx, ax
0x140023494  movsx   eax, r14w
0x140023498  mov     [rsp+78h+uFlags], 56h ; 'V'; uFlags
0x1400234a0  mov     [rsp+78h+cy], edx; cy
0x1400234a4  mov     [rsp+78h+var_58], eax; cx
0x1400234a8  xor     r9d, r9d; Y
0x1400234ab  xor     r8d, r8d; X
0x1400234ae  xor     edx, edx; hWndInsertAfter
0x1400234b0  mov     rcx, [rcx+10h]; hWnd
0x1400234b4  call    cs:__imp_SetWindowPos
0x1400234bb  nop     dword ptr [rax+rax+00h]
0x1400234c0  test    eax, eax
0x1400234c2  jnz     loc_1400233F6
0x1400234c8  mov     rcx, [rsp+78h]; this
0x1400234cd  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x1400234d4  mov     edx, 13Bh; void *
0x1400234d9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
