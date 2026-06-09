# CInitialConsentUI::TaskDialogSubclassProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000df18`
- end: `0x18000e113`
- name: `?TaskDialogSubclassProc@CInitialConsentUI@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `507`
- prototype: `__int64 __fastcall(CInitialConsentUI *__hidden this, HWND lParam, UINT uMsg, unsigned __int64, LPARAM)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000de00`

## callees

- `0x1800035dc`
- `0x180004808`
- `0x1800098b8`
- `0x18000c8a0`
- `0x18000cb5c`
- `0x18000df18`

## import_xrefs

- `COMCTL32!__imp_RemoveWindowSubclass` at `0x18000e0e1`
- `COMCTL32!__imp_RemoveWindowSubclass` at `0x18000e0e1`
- `COMCTL32!__imp_DefSubclassProc` at `0x18000e0ff`
- `COMCTL32!__imp_DefSubclassProc` at `0x18000e0ff`
- `USER32!EndDialog` at `0x18000dfb0`
- `USER32!EndDialog` at `0x18000dfb0`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x18000e0c3`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x18000e0c3`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x18000e00d`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x18000e00d`

## pseudocode

```c
LRESULT __fastcall CInitialConsentUI::TaskDialogSubclassProc(
        CInitialConsentUI *this,
        HWND lParam,
        UINT uMsg,
        WPARAM a4,
        HWND lParama)
{
  bool v10; // zf
  HWND Window; // rbx
  PVOID *v12; // rcx

  if ( !g_uHangrepMsg || uMsg != g_uHangrepMsg )
  {
    if ( uMsg == 2 )
    {
      if ( *((_DWORD *)this + 87) )
      {
        RemoveWindowSubclass(lParam, CInitialConsentUI::Static_TaskDialogSubclassProc, 0);
        *((_DWORD *)this + 87) = 0;
      }
      return DefSubclassProc(lParam, uMsg, a4, (LPARAM)lParama);
    }
    if ( uMsg != 6 )
    {
      if ( uMsg == 273 )
      {
        v10 = (_WORD)a4 == 2;
      }
      else
      {
        if ( uMsg != 274 )
        {
          if ( uMsg == 1025 )
            EndDialog(lParam, 0);
          return DefSubclassProc(lParam, uMsg, a4, (LPARAM)lParama);
        }
        v10 = (a4 & 0xFFF0) == 61536;
      }
      if ( v10 && (unsigned int)CInitialConsentUI::HandleCancellation(this) )
        return 0;
      return DefSubclassProc(lParam, uMsg, a4, (LPARAM)lParama);
    }
    if ( !(_WORD)a4 && g_uHangrepMsg && *(_DWORD *)this == 3 )
    {
      Window = GetWindow(lParam, 4u);
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids, lParama);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
        {
          WPP_SF_q(v12[2], 13, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids, Window);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
      if ( Window && Window != lParama )
      {
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
          WPP_SF_(v12[2], 14, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids);
        PostMessageW(Window, g_uHangrepMsg, 3u, (LPARAM)lParama);
      }
    }
    return DefSubclassProc(lParam, uMsg, a4, (LPARAM)lParama);
  }
  if ( a4 == 6 )
    CUIDlgBase::UICallback(this, 8 - (unsigned int)(lParama != 0));
  return (int)UIHandleWERWindowMsg(lParam, a4, (__int64)lParama);
}

```

## disassembly

```asm
0x18000df18  push    rbx
0x18000df1a  push    rsi
0x18000df1b  push    rdi
0x18000df1c  push    r12
0x18000df1e  push    r14
0x18000df20  push    r15
0x18000df22  sub     rsp, 28h
0x18000df26  mov     rbx, rcx
0x18000df29  xor     r15d, r15d
0x18000df2c  mov     ecx, cs:?g_uHangrepMsg@@3IA; uint g_uHangrepMsg
0x18000df32  mov     rdi, r9
0x18000df35  mov     r14d, r8d
0x18000df38  mov     rsi, rdx
0x18000df3b  test    ecx, ecx
0x18000df3d  jz      short loc_18000DF7F
0x18000df3f  cmp     r8d, ecx
0x18000df42  jnz     short loc_18000DF7F
0x18000df44  cmp     r9, 6
0x18000df48  jnz     short loc_18000DF65
0x18000df4a  mov     rax, [rsp+58h+lParam]
0x18000df52  mov     rcx, rbx
0x18000df55  neg     rax
0x18000df58  sbb     edx, edx
0x18000df5a  xor     r8d, r8d
0x18000df5d  add     edx, 8
0x18000df60  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x18000df65  mov     r8, [rsp+58h+lParam]; __int64
0x18000df6d  mov     rdx, rdi; unsigned __int64
0x18000df70  mov     rcx, rsi; lParam
0x18000df73  call    ?UIHandleWERWindowMsg@@YAHPEAUHWND__@@_K_J@Z; UIHandleWERWindowMsg(HWND__ *,unsigned __int64,__int64)
0x18000df78  cdqe
0x18000df7a  jmp     loc_18000E105
0x18000df7f  mov     eax, r14d
0x18000df82  mov     edx, 2
0x18000df87  sub     eax, edx
0x18000df89  jz      loc_18000E0CB
0x18000df8f  sub     eax, 4
0x18000df92  jz      short loc_18000DFEB
0x18000df94  sub     eax, 10Bh
0x18000df99  jz      short loc_18000DFE6
0x18000df9b  sub     eax, 1
0x18000df9e  jz      short loc_18000DFBB
0x18000dfa0  cmp     eax, 2EFh
0x18000dfa5  jnz     loc_18000E0EE
0x18000dfab  xor     edx, edx; nResult
0x18000dfad  mov     rcx, rsi; hDlg
0x18000dfb0  call    cs:__imp_EndDialog
0x18000dfb6  jmp     loc_18000E0EE
0x18000dfbb  mov     rax, rdi
0x18000dfbe  and     eax, 0FFF0h
0x18000dfc3  cmp     rax, 0F060h
0x18000dfc9  jnz     loc_18000E0EE
0x18000dfcf  mov     rcx, rbx; this
0x18000dfd2  call    ?HandleCancellation@CInitialConsentUI@@AEAAHXZ; CInitialConsentUI::HandleCancellation(void)
0x18000dfd7  test    eax, eax
0x18000dfd9  jz      loc_18000E0EE
0x18000dfdf  xor     eax, eax
0x18000dfe1  jmp     loc_18000E105
0x18000dfe6  cmp     di, dx
0x18000dfe9  jmp     short loc_18000DFC9
0x18000dfeb  test    di, di
0x18000dfee  jnz     loc_18000E0EE
0x18000dff4  test    ecx, ecx
0x18000dff6  jz      loc_18000E0EE
0x18000dffc  cmp     dword ptr [rbx], 3
0x18000dfff  jnz     loc_18000E0EE
0x18000e005  mov     edx, 4; uCmd
0x18000e00a  mov     rcx, rsi; hWnd
0x18000e00d  call    cs:__imp_GetWindow
0x18000e013  mov     rbx, rax
0x18000e016  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e01d  lea     r12, WPP_GLOBAL_Control
0x18000e024  cmp     rcx, r12
0x18000e027  jz      short loc_18000E07D
0x18000e029  test    byte ptr [rcx+1Ch], 8
0x18000e02d  jz      short loc_18000E053
0x18000e02f  mov     r9, [rsp+58h+lParam]
0x18000e037  lea     r8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids
0x18000e03e  mov     rcx, [rcx+10h]
0x18000e042  mov     edx, 0Ch
0x18000e047  call    WPP_SF_q
0x18000e04c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e053  cmp     rcx, r12
0x18000e056  jz      short loc_18000E07D
0x18000e058  test    byte ptr [rcx+1Ch], 8
0x18000e05c  jz      short loc_18000E07D
0x18000e05e  mov     rcx, [rcx+10h]
0x18000e062  lea     r8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids
0x18000e069  mov     edx, 0Dh
0x18000e06e  mov     r9, rbx
0x18000e071  call    WPP_SF_q
0x18000e076  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e07d  test    rbx, rbx
0x18000e080  jz      short loc_18000E0EE
0x18000e082  cmp     rbx, [rsp+58h+lParam]
0x18000e08a  jz      short loc_18000E0EE
0x18000e08c  cmp     rcx, r12
0x18000e08f  jz      short loc_18000E0AC
0x18000e091  test    byte ptr [rcx+1Ch], 8
0x18000e095  jz      short loc_18000E0AC
0x18000e097  mov     rcx, [rcx+10h]
0x18000e09b  lea     r8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids
0x18000e0a2  mov     edx, 0Eh
0x18000e0a7  call    WPP_SF_
0x18000e0ac  mov     r9, [rsp+58h+lParam]; lParam
0x18000e0b4  mov     r8d, 3; wParam
0x18000e0ba  mov     edx, cs:?g_uHangrepMsg@@3IA; Msg
0x18000e0c0  mov     rcx, rbx; hWnd
0x18000e0c3  call    cs:__imp_PostMessageW
0x18000e0c9  jmp     short loc_18000E0EE
0x18000e0cb  cmp     [rbx+15Ch], r15d
0x18000e0d2  jz      short loc_18000E0EE
0x18000e0d4  xor     r8d, r8d; uIdSubclass
0x18000e0d7  lea     rdx, ?Static_TaskDialogSubclassProc@CInitialConsentUI@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x18000e0de  mov     rcx, rsi; hWnd
0x18000e0e1  call    cs:__imp_RemoveWindowSubclass
0x18000e0e7  mov     [rbx+15Ch], r15d
0x18000e0ee  mov     r9, [rsp+58h+lParam]; lParam
0x18000e0f6  mov     r8, rdi; wParam
0x18000e0f9  mov     edx, r14d; uMsg
0x18000e0fc  mov     rcx, rsi; hWnd
0x18000e0ff  call    cs:__imp_DefSubclassProc
0x18000e105  add     rsp, 28h
0x18000e109  pop     r15
0x18000e10b  pop     r14
0x18000e10d  pop     r12
0x18000e10f  pop     rdi
0x18000e110  pop     rsi
0x18000e111  pop     rbx
0x18000e112  retn
```
