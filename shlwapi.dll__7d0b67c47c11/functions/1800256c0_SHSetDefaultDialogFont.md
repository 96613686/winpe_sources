# SHSetDefaultDialogFont

- ea: `0x1800256c0`
- end: `0x1800257e6`
- name: `SHSetDefaultDialogFont`
- size: `294`
- prototype: `__int64 __fastcall(HWND hDlg, int nIDDlgItem)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180012550`
- `0x180013066`
- `0x1800256c0`

## import_xrefs

- `GDI32!GetObjectW` at `0x18002571d`
- `GDI32!GetObjectW` at `0x18002571d`
- `GDI32!CreateFontIndirectW` at `0x18002577a`
- `GDI32!CreateFontIndirectW` at `0x18002577a`
- `USER32!GetDlgItem` at `0x1800257aa`
- `USER32!GetDlgItem` at `0x1800257aa`
- `USER32!GetPropW` at `0x18002575c`
- `USER32!GetPropW` at `0x18002575c`
- `USER32!SystemParametersInfoW` at `0x18002573f`
- `USER32!SystemParametersInfoW` at `0x18002573f`
- `USER32!SendMessageW` at `0x1800256f0`
- `USER32!SendMessageW` at `0x1800257bd`
- `USER32!SendMessageW` at `0x1800256f0`
- `USER32!SendMessageW` at `0x1800257bd`
- `USER32!SetPropW` at `0x18002579f`
- `USER32!SetPropW` at `0x18002579f`

## pseudocode

```c
char __fastcall SHSetDefaultDialogFont(HWND hDlg, int nIDDlgItem)
{
  HFONT v4; // rsi
  char result; // al
  HANDLE PropW; // rbx
  HFONT v7; // rax
  HWND DlgItem; // rax
  LOGFONTW pvParam; // [rsp+20h] [rbp-E8h] BYREF
  _DWORD pv[5]; // [rsp+80h] [rbp-88h] BYREF
  char v11; // [rsp+97h] [rbp-71h]

  v4 = (HFONT)SendMessageW(hDlg, 0x31u, 0, 0);
  memset_0(pv, 0, 0x5Cu);
  GetObjectW(v4, 92, pv);
  memset_0(&pvParam, 0, sizeof(pvParam));
  SystemParametersInfoW(0x1Fu, 0x5Cu, &pvParam, 0);
  result = v11;
  if ( pvParam.lfCharSet != v11 )
  {
    PropW = GetPropW(hDlg, L"PropDlgFont");
    if ( !PropW )
    {
      pvParam.lfHeight = pv[0];
      v7 = CreateFontIndirectW(&pvParam);
      PropW = v7;
      if ( v7 )
      {
        if ( v7 != v4 )
          SetPropW(hDlg, L"PropDlgFont", v7);
      }
      else
      {
        PropW = v4;
      }
    }
    DlgItem = GetDlgItem(hDlg, nIDDlgItem);
    return SendMessageW(DlgItem, 0x30u, (WPARAM)PropW, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800256c0  mov     [rsp+arg_10], rbx
0x1800256c5  push    rbp
0x1800256c6  push    rsi
0x1800256c7  push    rdi
0x1800256c8  sub     rsp, 0F0h
0x1800256cf  mov     rax, cs:__security_cookie
0x1800256d6  xor     rax, rsp
0x1800256d9  mov     [rsp+108h+var_28], rax
0x1800256e1  xor     r9d, r9d; lParam
0x1800256e4  mov     ebp, edx
0x1800256e6  xor     r8d, r8d; wParam
0x1800256e9  mov     rdi, rcx
0x1800256ec  lea     edx, [r9+31h]; Msg
0x1800256f0  call    cs:__imp_SendMessageW
0x1800256f6  mov     ebx, 5Ch ; '\'
0x1800256fb  lea     rcx, [rsp+108h+pv]; void *
0x180025703  mov     r8d, ebx; Size
0x180025706  xor     edx, edx; Val
0x180025708  mov     rsi, rax
0x18002570b  call    memset_0
0x180025710  lea     r8, [rsp+108h+pv]; pv
0x180025718  mov     edx, ebx; c
0x18002571a  mov     rcx, rsi; h
0x18002571d  call    cs:__imp_GetObjectW
0x180025723  mov     r8d, ebx; Size
0x180025726  lea     rcx, [rsp+108h+pvParam]; void *
0x18002572b  xor     edx, edx; Val
0x18002572d  call    memset_0
0x180025732  xor     r9d, r9d; fWinIni
0x180025735  lea     r8, [rsp+108h+pvParam]; pvParam
0x18002573a  mov     edx, ebx; uiParam
0x18002573c  lea     ecx, [rbx-3Dh]; uiAction
0x18002573f  call    cs:__imp_SystemParametersInfoW
0x180025745  mov     al, [rsp+108h+var_71]
0x18002574c  cmp     [rsp+108h+var_D1], al
0x180025750  jz      short loc_1800257C3
0x180025752  lea     rdx, aPropdlgfont; "PropDlgFont"
0x180025759  mov     rcx, rdi; hWnd
0x18002575c  call    cs:__imp_GetPropW
0x180025762  mov     rbx, rax
0x180025765  test    rax, rax
0x180025768  jnz     short loc_1800257A5
0x18002576a  mov     eax, [rsp+108h+pv]
0x180025771  lea     rcx, [rsp+108h+pvParam]; lplf
0x180025776  mov     [rsp+108h+pvParam], eax
0x18002577a  call    cs:__imp_CreateFontIndirectW
0x180025780  mov     rbx, rax
0x180025783  test    rax, rax
0x180025786  jnz     short loc_18002578D
0x180025788  mov     rbx, rsi
0x18002578b  jmp     short loc_1800257A5
0x18002578d  cmp     rax, rsi
0x180025790  jz      short loc_1800257A5
0x180025792  mov     r8, rax; hData
0x180025795  lea     rdx, aPropdlgfont; "PropDlgFont"
0x18002579c  mov     rcx, rdi; hWnd
0x18002579f  call    cs:__imp_SetPropW
0x1800257a5  mov     edx, ebp; nIDDlgItem
0x1800257a7  mov     rcx, rdi; hDlg
0x1800257aa  call    cs:__imp_GetDlgItem
0x1800257b0  xor     r9d, r9d; lParam
0x1800257b3  mov     r8, rbx; wParam
0x1800257b6  mov     rcx, rax; hWnd
0x1800257b9  lea     edx, [r9+30h]; Msg
0x1800257bd  call    cs:__imp_SendMessageW
0x1800257c3  mov     rcx, [rsp+108h+var_28]
0x1800257cb  xor     rcx, rsp; StackCookie
0x1800257ce  call    __security_check_cookie
0x1800257d3  mov     rbx, [rsp+108h+arg_10]
0x1800257db  add     rsp, 0F0h
0x1800257e2  pop     rdi
0x1800257e3  pop     rsi
0x1800257e4  pop     rbp
0x1800257e5  retn
```
