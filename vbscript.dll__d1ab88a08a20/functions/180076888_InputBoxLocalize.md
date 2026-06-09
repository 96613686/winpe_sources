# InputBoxLocalize

- ea: `0x180076888`
- end: `0x180076ade`
- name: `InputBoxLocalize`
- size: `598`
- prototype: `__int64 __fastcall(HWND hDlg)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800766f0`

## callees

- `0x180055d3c`
- `0x180076888`
- `0x180077050`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180076951`
- `KERNEL32!MulDiv` at `0x180076951`
- `USER32!SendDlgItemMessageA` at `0x180076a20`
- `USER32!SendDlgItemMessageA` at `0x180076a43`
- `USER32!SendDlgItemMessageA` at `0x180076a20`
- `USER32!SendDlgItemMessageA` at `0x180076a43`
- `USER32!GetDC` at `0x18007691a`
- `USER32!GetDC` at `0x18007691a`
- `USER32!SendMessageA` at `0x1800769fd`
- `USER32!SendMessageA` at `0x1800769fd`
- `USER32!GetDlgItem` at `0x180076a65`
- `USER32!GetDlgItem` at `0x180076a8c`
- `USER32!GetDlgItem` at `0x180076ab3`
- `USER32!GetDlgItem` at `0x180076a65`
- `USER32!GetDlgItem` at `0x180076a8c`
- `USER32!GetDlgItem` at `0x180076ab3`
- `USER32!ReleaseDC` at `0x180076967`
- `USER32!ReleaseDC` at `0x180076967`
- `GDI32!GetDeviceCaps` at `0x18007693a`
- `GDI32!GetDeviceCaps` at `0x18007693a`
- `GDI32!CreateFontA` at `0x1800769d6`
- `GDI32!CreateFontA` at `0x1800769d6`

## pseudocode

```c
int __fastcall InputBoxLocalize(HWND hDlg, __int64 a2)
{
  WPARAM v3; // rdi
  __int64 v4; // rcx
  __int64 *v6; // rbx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  HDC DC; // rax
  HDC v11; // rdi
  int DeviceCaps; // eax
  int v13; // ebp
  unsigned int v14; // ebx
  HWND DlgItem; // rax
  HWND v16; // rax
  HWND v17; // rax

  v3 = 0;
  v4 = *(_QWORD *)(a2 + 48);
  if ( *(_DWORD *)(v4 + 232) )
  {
    v7 = *(_DWORD *)(v4 + 236) - 932;
    if ( v7 )
    {
      v8 = v7 - 4;
      if ( v8 )
      {
        v9 = v8 - 13;
        if ( v9 )
        {
          if ( v9 != 1 )
            goto LABEL_19;
          v6 = (__int64 *)&off_18007D570;
        }
        else
        {
          v6 = &off_18007D5A0;
        }
      }
      else
      {
        v6 = &off_18007D588;
      }
    }
    else
    {
      v6 = (__int64 *)&off_18007D530;
    }
  }
  else
  {
    if ( *(_WORD *)(v4 + 184) != 1081 )
    {
      if ( *(_WORD *)(v4 + 184) == 1097 )
      {
        v6 = (__int64 *)&off_18007D550;
        goto LABEL_14;
      }
LABEL_19:
      LODWORD(DC) = COleScript::GetUserLocale();
      v14 = (unsigned int)DC;
      if ( (_DWORD)DC != 1033 )
      {
        DlgItem = GetDlgItem(hDlg, 1);
        SetButtonTitle(DlgItem, 0x8000, v14, v3);
        v16 = GetDlgItem(hDlg, 2);
        SetButtonTitle(v16, 32769, v14, v3);
        v17 = GetDlgItem(hDlg, 3);
        LODWORD(DC) = SetButtonTitle(v17, 32770, v14, v3);
      }
      return (int)DC;
    }
    v6 = (__int64 *)&off_18007D560;
  }
LABEL_14:
  DC = GetDC(hDlg);
  v11 = DC;
  if ( DC )
  {
    DeviceCaps = GetDeviceCaps(DC, 90);
    v13 = -MulDiv(9, DeviceCaps, 72);
    LODWORD(DC) = ReleaseDC(hDlg, v11);
    while ( *v6 )
    {
      DC = (HDC)CreateFontA(v13, 0, 0, 0, 400, 0, 0, 0, 1u, 0, 0, 0, 0, (LPCSTR)*v6);
      v3 = (WPARAM)DC;
      if ( DC )
      {
        *(_QWORD *)(a2 + 88) = DC;
        SendMessageA(hDlg, 0x30u, (WPARAM)DC, 0);
        SendDlgItemMessageA(hDlg, 1001, 0x30u, v3, 0);
        SendDlgItemMessageA(hDlg, 1000, 0x30u, v3, 0);
        goto LABEL_19;
      }
    }
  }
  return (int)DC;
}

```

## disassembly

```asm
0x180076888  push    rbx
0x18007688a  push    rbp
0x18007688b  push    rsi
0x18007688c  push    rdi
0x18007688d  push    r14
0x18007688f  sub     rsp, 70h
0x180076893  mov     rsi, rcx
0x180076896  xor     edi, edi
0x180076898  mov     rcx, [rdx+30h]
0x18007689c  mov     r14, rdx
0x18007689f  cmp     [rcx+0E8h], edi
0x1800768a5  jnz     short loc_1800768D4
0x1800768a7  movzx   r8d, word ptr [rcx+0B8h]
0x1800768af  sub     r8d, 439h
0x1800768b6  jz      short loc_1800768CB
0x1800768b8  cmp     r8d, 10h
0x1800768bc  jnz     loc_180076A4F
0x1800768c2  lea     rbx, off_18007D550; "Latha"
0x1800768c9  jmp     short loc_180076917
0x1800768cb  lea     rbx, off_18007D560; "Mangal"
0x1800768d2  jmp     short loc_180076917
0x1800768d4  mov     ecx, [rcx+0ECh]
0x1800768da  sub     ecx, 3A4h
0x1800768e0  jz      short loc_180076910
0x1800768e2  sub     ecx, 4
0x1800768e5  jz      short loc_180076907
0x1800768e7  sub     ecx, 0Dh
0x1800768ea  jz      short loc_1800768FE
0x1800768ec  cmp     ecx, 1
0x1800768ef  jnz     loc_180076A4F
0x1800768f5  lea     rbx, off_18007D570
0x1800768fc  jmp     short loc_180076917
0x1800768fe  lea     rbx, off_18007D5A0
0x180076905  jmp     short loc_180076917
0x180076907  lea     rbx, off_18007D588
0x18007690e  jmp     short loc_180076917
0x180076910  lea     rbx, off_18007D530
0x180076917  mov     rcx, rsi; hWnd
0x18007691a  call    cs:__imp_GetDC
0x180076921  nop     dword ptr [rax+rax+00h]
0x180076926  mov     rdi, rax
0x180076929  test    rax, rax
0x18007692c  jz      loc_180076AD2
0x180076932  mov     edx, 5Ah ; 'Z'; index
0x180076937  mov     rcx, rax; hdc
0x18007693a  call    cs:__imp_GetDeviceCaps
0x180076941  nop     dword ptr [rax+rax+00h]
0x180076946  mov     ecx, 9; nNumber
0x18007694b  mov     edx, eax; nNumerator
0x18007694d  lea     r8d, [rcx+3Fh]; nDenominator
0x180076951  call    cs:__imp_MulDiv
0x180076958  nop     dword ptr [rax+rax+00h]
0x18007695d  mov     rdx, rdi; hDC
0x180076960  mov     rcx, rsi; hWnd
0x180076963  mov     ebp, eax
0x180076965  neg     ebp
0x180076967  call    cs:__imp_ReleaseDC
0x18007696e  nop     dword ptr [rax+rax+00h]
0x180076973  mov     rcx, [rbx]
0x180076976  test    rcx, rcx
0x180076979  jz      loc_180076AD2
0x18007697f  mov     [rsp+98h+pszFaceName], rcx; pszFaceName
0x180076984  xor     r9d, r9d; cOrientation
0x180076987  mov     [rsp+98h+iPitchAndFamily], 0; iPitchAndFamily
0x18007698f  xor     r8d, r8d; cEscapement
0x180076992  mov     [rsp+98h+iQuality], 0; iQuality
0x18007699a  xor     edx, edx; cWidth
0x18007699c  mov     [rsp+98h+iClipPrecision], 0; iClipPrecision
0x1800769a4  mov     ecx, ebp; cHeight
0x1800769a6  mov     [rsp+98h+iOutPrecision], 0; iOutPrecision
0x1800769ae  mov     [rsp+98h+iCharSet], 1; iCharSet
0x1800769b6  mov     [rsp+98h+bStrikeOut], 0; bStrikeOut
0x1800769be  mov     [rsp+98h+bUnderline], 0; bUnderline
0x1800769c6  mov     [rsp+98h+bItalic], 0; bItalic
0x1800769ce  mov     [rsp+98h+cWeight], 190h; cWeight
0x1800769d6  call    cs:__imp_CreateFontA
0x1800769dd  nop     dword ptr [rax+rax+00h]
0x1800769e2  mov     rdi, rax
0x1800769e5  test    rax, rax
0x1800769e8  jz      short loc_180076973
0x1800769ea  xor     r9d, r9d; lParam
0x1800769ed  mov     [r14+58h], rax
0x1800769f1  mov     r8, rax; wParam
0x1800769f4  mov     rcx, rsi; hWnd
0x1800769f7  lea     ebx, [r9+30h]
0x1800769fb  mov     edx, ebx; Msg
0x1800769fd  call    cs:__imp_SendMessageA
0x180076a04  nop     dword ptr [rax+rax+00h]
0x180076a09  mov     r9, rdi; wParam
0x180076a0c  mov     qword ptr [rsp+98h+cWeight], 0; lParam
0x180076a15  mov     r8d, ebx; Msg
0x180076a18  mov     edx, 3E9h; nIDDlgItem
0x180076a1d  mov     rcx, rsi; hDlg
0x180076a20  call    cs:__imp_SendDlgItemMessageA
0x180076a27  nop     dword ptr [rax+rax+00h]
0x180076a2c  mov     r9, rdi; wParam
0x180076a2f  mov     qword ptr [rsp+98h+cWeight], 0; lParam
0x180076a38  mov     r8d, ebx; Msg
0x180076a3b  mov     edx, 3E8h; nIDDlgItem
0x180076a40  mov     rcx, rsi; hDlg
0x180076a43  call    cs:__imp_SendDlgItemMessageA
0x180076a4a  nop     dword ptr [rax+rax+00h]
0x180076a4f  call    ?GetUserLocale@COleScript@@SAKXZ; COleScript::GetUserLocale(void)
0x180076a54  mov     ebx, eax
0x180076a56  cmp     eax, 409h
0x180076a5b  jz      short loc_180076AD2
0x180076a5d  mov     edx, 1; nIDDlgItem
0x180076a62  mov     rcx, rsi; hDlg
0x180076a65  call    cs:__imp_GetDlgItem
0x180076a6c  nop     dword ptr [rax+rax+00h]
0x180076a71  mov     r9, rdi; wParam
0x180076a74  mov     r8d, ebx; unsigned int
0x180076a77  mov     rcx, rax; hWnd
0x180076a7a  mov     edx, 8000h; int
0x180076a7f  call    SetButtonTitle
0x180076a84  mov     edx, 2; nIDDlgItem
0x180076a89  mov     rcx, rsi; hDlg
0x180076a8c  call    cs:__imp_GetDlgItem
0x180076a93  nop     dword ptr [rax+rax+00h]
0x180076a98  mov     r9, rdi; wParam
0x180076a9b  mov     r8d, ebx; unsigned int
0x180076a9e  mov     rcx, rax; hWnd
0x180076aa1  mov     edx, 8001h; int
0x180076aa6  call    SetButtonTitle
0x180076aab  mov     edx, 3; nIDDlgItem
0x180076ab0  mov     rcx, rsi; hDlg
0x180076ab3  call    cs:__imp_GetDlgItem
0x180076aba  nop     dword ptr [rax+rax+00h]
0x180076abf  mov     r9, rdi; wParam
0x180076ac2  mov     r8d, ebx; unsigned int
0x180076ac5  mov     rcx, rax; hWnd
0x180076ac8  mov     edx, 8002h; int
0x180076acd  call    SetButtonTitle
0x180076ad2  add     rsp, 70h
0x180076ad6  pop     r14
0x180076ad8  pop     rdi
0x180076ad9  pop     rsi
0x180076ada  pop     rbp
0x180076adb  pop     rbx
0x180076adc  retn
```
