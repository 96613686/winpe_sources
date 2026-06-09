# SetEndTaskDlgStatus

- ea: `0x1800079d4`
- end: `0x180007e88`
- name: `SetEndTaskDlgStatus`
- size: `1204`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180005b70`

## callees

- `0x1800079d4`
- `0x18000daf0`
- `0x1800138f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a5b`
- `USER32!SetForegroundWindow` at `0x180007e54`
- `USER32!SetForegroundWindow` at `0x180007e54`
- `USER32!SetDlgItemTextW` at `0x180007a4c`
- `USER32!SetDlgItemTextW` at `0x180007a4c`
- `USER32!SetTimer` at `0x180007a86`
- `USER32!SetTimer` at `0x180007d7a`
- `USER32!SetTimer` at `0x180007a86`
- `USER32!SetTimer` at `0x180007d7a`
- `USER32!GetDlgItem` at `0x180007ab1`
- `USER32!GetDlgItem` at `0x180007ac9`
- `USER32!GetDlgItem` at `0x180007ae4`
- `USER32!GetDlgItem` at `0x180007ab1`
- `USER32!GetDlgItem` at `0x180007ac9`
- `USER32!GetDlgItem` at `0x180007ae4`
- `USER32!SendMessageW` at `0x180007b17`
- `USER32!SendMessageW` at `0x180007b96`
- `USER32!SendMessageW` at `0x180007b17`
- `USER32!SendMessageW` at `0x180007b96`
- `USER32!SetFocus` at `0x180007b26`
- `USER32!SetFocus` at `0x180007ba5`
- `USER32!SetFocus` at `0x180007b26`
- `USER32!SetFocus` at `0x180007ba5`
- `USER32!SetWindowPos` at `0x180007b52`
- `USER32!SetWindowPos` at `0x180007b77`
- `USER32!SetWindowPos` at `0x180007df6`
- `USER32!SetWindowPos` at `0x180007e40`
- `USER32!SetWindowPos` at `0x180007b52`
- `USER32!SetWindowPos` at `0x180007b77`
- `USER32!SetWindowPos` at `0x180007df6`
- `USER32!SetWindowPos` at `0x180007e40`
- `USER32!GetClientRect` at `0x180007bf6`
- `USER32!GetClientRect` at `0x180007bf6`
- `USER32!InflateRect` at `0x180007c2f`
- `USER32!InflateRect` at `0x180007caf`
- `USER32!InflateRect` at `0x180007c2f`
- `USER32!InflateRect` at `0x180007caf`
- `USER32!OffsetRect` at `0x180007c4c`
- `USER32!OffsetRect` at `0x180007c4c`
- `USER32!MapWindowPoints` at `0x180007c68`
- `USER32!MapWindowPoints` at `0x180007d33`
- `USER32!MapWindowPoints` at `0x180007dc7`
- `USER32!MapWindowPoints` at `0x180007c68`
- `USER32!MapWindowPoints` at `0x180007d33`
- `USER32!MapWindowPoints` at `0x180007dc7`
- `USER32!GetSysColor` at `0x180007cee`
- `USER32!GetSysColor` at `0x180007cee`
- `USER32!GetWindowRect` at `0x180007d19`
- `USER32!GetWindowRect` at `0x180007d8d`
- `USER32!GetWindowRect` at `0x180007da0`
- `USER32!GetWindowRect` at `0x180007d19`
- `USER32!GetWindowRect` at `0x180007d8d`
- `USER32!GetWindowRect` at `0x180007da0`
- `USER32!KillTimer` at `0x180007bc3`
- `USER32!KillTimer` at `0x180007bc3`
- `USER32!InvalidateRect` at `0x180007e11`
- `USER32!InvalidateRect` at `0x180007e11`
- `USER32!GetSystemMetrics` at `0x180007c19`
- `USER32!GetSystemMetrics` at `0x180007c84`
- `USER32!GetSystemMetrics` at `0x180007c99`
- `USER32!GetSystemMetrics` at `0x180007c19`
- `USER32!GetSystemMetrics` at `0x180007c84`
- `USER32!GetSystemMetrics` at `0x180007c99`
- `GDI32!CreateSolidBrush` at `0x180007cfc`
- `GDI32!CreateSolidBrush` at `0x180007cfc`

## pseudocode

```c
int __fastcall SetEndTaskDlgStatus(struct tagRECT *a1, HWND a2, unsigned int a3, int a4)
{
  __int64 bottom; // rcx
  LONG left; // edi
  BOOL v9; // esi
  int v10; // edi
  const WCHAR *StringOrError; // rax
  WCHAR *v12; // rbx
  HWND DlgItem; // rsi
  HWND v14; // r13
  int v15; // ebx
  int SystemMetrics; // eax
  int v17; // ebx
  int v18; // eax
  int v19; // ecx
  unsigned int v20; // edx
  int v21; // ecx
  unsigned int v22; // edx
  DWORD SysColor; // eax
  unsigned int v24; // ecx
  int v26; // [rsp+40h] [rbp-40h]
  HWND hWnd; // [rsp+48h] [rbp-38h]
  struct tagRECT Rect; // [rsp+50h] [rbp-30h] BYREF
  struct tagRECT v29; // [rsp+60h] [rbp-20h] BYREF

  bottom = (unsigned int)a1->bottom;
  v26 = bottom;
  left = a1->left;
  v9 = bottom == 20;
  a1->bottom = a3;
  v10 = left & 8;
  StringOrError = (const WCHAR *)RtlLoadStringOrError(bottom, a3, 0);
  v12 = (WCHAR *)StringOrError;
  if ( StringOrError )
  {
    SetDlgItemTextW(a2, 257, StringOrError);
    LODWORD(StringOrError) = (unsigned int)LocalFree(v12);
  }
  if ( (a1->left & 4) == 0 && (a1->top & 0x20) == 0 )
    LODWORD(StringOrError) = SetTimer(a2, 0x300u, gCmsHungAppTimeout, 0);
  if ( !a4 && v9 == (v10 != 0) )
  {
LABEL_19:
    if ( (a1->left & 4) == 0 )
      return (int)StringOrError;
    goto LABEL_20;
  }
  Rect = 0;
  hWnd = GetDlgItem(a2, 258);
  DlgItem = GetDlgItem(a2, 2);
  *(_QWORD *)&v29.left = DlgItem;
  v14 = GetDlgItem(a2, 259);
  if ( v10 )
  {
    SendMessageW(a2, 0x401u, 0x103u, 0);
    SetFocus(v14);
  }
  SetWindowPos(hWnd, 0, 0, 0, 0, 0, v10 != 0 ? 1183 : 1119);
  SetWindowPos(DlgItem, 0, 0, 0, 0, 0, v10 != 0 ? 1183 : 1119);
  if ( v10 )
  {
    if ( !*(_QWORD *)&a1[7].right )
    {
      GetClientRect(hWnd, a1 + 5);
      v15 = (a1[5].bottom - a1[5].top) / 4;
      SystemMetrics = GetSystemMetrics(46);
      InflateRect(a1 + 5, 0, SystemMetrics - v15);
      a1[5].right += -5 * v15;
      OffsetRect(a1 + 5, 0, -v15);
      MapWindowPoints(hWnd, a2, (LPPOINT)&a1[5], 2u);
      a1[6] = a1[5];
      v17 = -GetSystemMetrics(46);
      v18 = GetSystemMetrics(45);
      InflateRect(a1 + 6, -v18, v17);
      v19 = 2 * (a1[6].bottom - a1[6].top);
      a1[7].left = a1[6].right;
      v20 = (unsigned __int64)(1431655766LL * v19) >> 32;
      v21 = a1[6].left - 1;
      v22 = (v20 >> 31) + v20;
      a1[7].top = v22;
      a1[6].right = v22 + v21;
      SysColor = GetSysColor(2);
      *(_QWORD *)&a1[7].right = CreateSolidBrush(SysColor);
      GetWindowRect(v14, a1 + 8);
      MapWindowPoints(0, a2, (LPPOINT)&a1[8], 2u);
      DlgItem = *(HWND *)&v29.left;
    }
    v24 = (a1[7].left - a1[6].left) / a1[7].top;
    v29 = 0;
    SetTimer(a2, 0x301u, gCmsHungAppTimeout * gdwHungToKillCount / v24, 0);
    GetWindowRect(DlgItem, &Rect);
    GetWindowRect(v14, &v29);
    Rect.left = Rect.right + v29.left - v29.right;
    MapWindowPoints(0, a2, (LPPOINT)&Rect, 2u);
  }
  else
  {
    SendMessageW(a2, 0x401u, 2u, 0);
    SetFocus(DlgItem);
    if ( v26 != 20 )
      goto LABEL_17;
    KillTimer(a2, 0x301u);
    Rect = a1[8];
  }
  SetWindowPos(v14, 0, Rect.left, Rect.top, 0, 0, 0x41Du);
LABEL_17:
  if ( !a4 )
  {
    LODWORD(StringOrError) = InvalidateRect(a2, 0, 1);
    goto LABEL_19;
  }
LABEL_20:
  LODWORD(StringOrError) = SetWindowPos(a2, HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 0x453u);
  if ( a4 )
    LODWORD(StringOrError) = SetForegroundWindow(a2);
  return (int)StringOrError;
}

```

## disassembly

```asm
0x1800079d4  mov     [rsp-38h+arg_18], rbx
0x1800079d9  push    rbp
0x1800079da  push    rsi
0x1800079db  push    rdi
0x1800079dc  push    r12
0x1800079de  push    r13
0x1800079e0  push    r14
0x1800079e2  push    r15
0x1800079e4  mov     rbp, rsp
0x1800079e7  sub     rsp, 80h
0x1800079ee  mov     rax, cs:__security_cookie
0x1800079f5  xor     rax, rsp
0x1800079f8  mov     [rbp+var_10], rax
0x1800079fc  mov     r15, rcx
0x1800079ff  mov     eax, r8d
0x180007a02  mov     ecx, [rcx+0Ch]
0x180007a05  xor     esi, esi
0x180007a07  cmp     ecx, 14h
0x180007a0a  mov     [rbp+var_40], ecx
0x180007a0d  mov     r12d, r9d
0x180007a10  mov     r14, rdx
0x180007a13  mov     edi, [r15]
0x180007a16  lea     r9, [rbp+hWnd]
0x180007a1a  setz    sil
0x180007a1e  mov     [r15+0Ch], eax
0x180007a22  and     edi, 8
0x180007a25  mov     r13d, 0
0x180007a2b  mov     edx, eax
0x180007a2d  setnz   r13b
0x180007a31  xor     r8d, r8d
0x180007a34  call    RtlLoadStringOrError
0x180007a39  mov     rbx, rax
0x180007a3c  test    rax, rax
0x180007a3f  jz      short loc_180007A67
0x180007a41  mov     r8, rax; lpString
0x180007a44  mov     edx, 101h; nIDDlgItem
0x180007a49  mov     rcx, r14; hDlg
0x180007a4c  call    cs:__imp_SetDlgItemTextW
0x180007a53  nop     dword ptr [rax+rax+00h]
0x180007a58  mov     rcx, rbx; hMem
0x180007a5b  call    cs:__imp_LocalFree
0x180007a62  nop     dword ptr [rax+rax+00h]
0x180007a67  test    byte ptr [r15], 4
0x180007a6b  jnz     short loc_180007A92
0x180007a6d  test    byte ptr [r15+4], 20h
0x180007a72  jnz     short loc_180007A92
0x180007a74  mov     r8d, cs:gCmsHungAppTimeout; uElapse
0x180007a7b  xor     r9d, r9d; lpTimerFunc
0x180007a7e  mov     edx, 300h; nIDEvent
0x180007a83  mov     rcx, r14; hWnd
0x180007a86  call    cs:__imp_SetTimer
0x180007a8d  nop     dword ptr [rax+rax+00h]
0x180007a92  xor     ebx, ebx
0x180007a94  test    r12d, r12d
0x180007a97  jnz     short loc_180007AA2
0x180007a99  cmp     esi, r13d
0x180007a9c  jz      loc_180007E1D
0x180007aa2  xorps   xmm0, xmm0
0x180007aa5  mov     edx, 102h; nIDDlgItem
0x180007aaa  mov     rcx, r14; hDlg
0x180007aad  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180007ab1  call    cs:__imp_GetDlgItem
0x180007ab8  nop     dword ptr [rax+rax+00h]
0x180007abd  mov     edx, 2; nIDDlgItem
0x180007ac2  mov     rcx, r14; hDlg
0x180007ac5  mov     [rbp+hWnd], rax
0x180007ac9  call    cs:__imp_GetDlgItem
0x180007ad0  nop     dword ptr [rax+rax+00h]
0x180007ad5  mov     edx, 103h; nIDDlgItem
0x180007ada  mov     rcx, r14; hDlg
0x180007add  mov     rsi, rax
0x180007ae0  mov     qword ptr [rbp+var_20.left], rax
0x180007ae4  call    cs:__imp_GetDlgItem
0x180007aeb  nop     dword ptr [rax+rax+00h]
0x180007af0  mov     ecx, edi
0x180007af2  mov     r13, rax
0x180007af5  neg     ecx
0x180007af7  sbb     ebx, ebx
0x180007af9  and     ebx, 40h
0x180007afc  add     ebx, 45Fh
0x180007b02  test    edi, edi
0x180007b04  jz      short loc_180007B32
0x180007b06  xor     r9d, r9d; lParam
0x180007b09  mov     edx, 401h; Msg
0x180007b0e  mov     r8d, 103h; wParam
0x180007b14  mov     rcx, r14; hWnd
0x180007b17  call    cs:__imp_SendMessageW
0x180007b1e  nop     dword ptr [rax+rax+00h]
0x180007b23  mov     rcx, r13; hWnd
0x180007b26  call    cs:__imp_SetFocus
0x180007b2d  nop     dword ptr [rax+rax+00h]
0x180007b32  mov     rcx, [rbp+hWnd]; hWnd
0x180007b36  xor     r9d, r9d; Y
0x180007b39  mov     [rsp+80h+uFlags], ebx; uFlags
0x180007b3d  xor     r8d, r8d; X
0x180007b40  mov     [rsp+80h+cy], 0; cy
0x180007b48  xor     edx, edx; hWndInsertAfter
0x180007b4a  mov     [rsp+80h+var_60], 0; cx
0x180007b52  call    cs:__imp_SetWindowPos
0x180007b59  nop     dword ptr [rax+rax+00h]
0x180007b5e  mov     [rsp+80h+uFlags], ebx; uFlags
0x180007b62  xor     r9d, r9d; Y
0x180007b65  xor     ebx, ebx
0x180007b67  xor     r8d, r8d; X
0x180007b6a  mov     [rsp+80h+cy], ebx; cy
0x180007b6e  xor     edx, edx; hWndInsertAfter
0x180007b70  mov     rcx, rsi; hWnd
0x180007b73  mov     [rsp+80h+var_60], ebx; cx
0x180007b77  call    cs:__imp_SetWindowPos
0x180007b7e  nop     dword ptr [rax+rax+00h]
0x180007b83  test    edi, edi
0x180007b85  jnz     short loc_180007BE1
0x180007b87  xor     r9d, r9d; lParam
0x180007b8a  lea     r8d, [rbx+2]; wParam
0x180007b8e  mov     edx, 401h; Msg
0x180007b93  mov     rcx, r14; hWnd
0x180007b96  call    cs:__imp_SendMessageW
0x180007b9d  nop     dword ptr [rax+rax+00h]
0x180007ba2  mov     rcx, rsi; hWnd
0x180007ba5  call    cs:__imp_SetFocus
0x180007bac  nop     dword ptr [rax+rax+00h]
0x180007bb1  cmp     [rbp+var_40], 14h
0x180007bb5  jnz     loc_180007E02
0x180007bbb  mov     edx, 301h; uIDEvent
0x180007bc0  mov     rcx, r14; hWnd
0x180007bc3  call    cs:__imp_KillTimer
0x180007bca  nop     dword ptr [rax+rax+00h]
0x180007bcf  movups  xmm0, xmmword ptr [r15+80h]
0x180007bd7  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x180007bdc  jmp     loc_180007DD3
0x180007be1  cmp     [r15+78h], rbx
0x180007be5  jnz     loc_180007D45
0x180007beb  mov     rcx, [rbp+hWnd]; hWnd
0x180007bef  lea     rsi, [r15+50h]
0x180007bf3  mov     rdx, rsi; lpRect
0x180007bf6  call    cs:__imp_GetClientRect
0x180007bfd  nop     dword ptr [rax+rax+00h]
0x180007c02  mov     eax, [r15+5Ch]
0x180007c06  mov     ecx, 2Eh ; '.'; nIndex
0x180007c0b  sub     eax, [r15+54h]
0x180007c0f  cdq
0x180007c10  and     edx, 3
0x180007c13  lea     ebx, [rdx+rax]
0x180007c16  sar     ebx, 2
0x180007c19  call    cs:__imp_GetSystemMetrics
0x180007c20  nop     dword ptr [rax+rax+00h]
0x180007c25  xor     edx, edx; dx
0x180007c27  mov     rcx, rsi; lprc
0x180007c2a  sub     eax, ebx
0x180007c2c  mov     r8d, eax; dy
0x180007c2f  call    cs:__imp_InflateRect
0x180007c36  nop     dword ptr [rax+rax+00h]
0x180007c3b  imul    eax, ebx, -5
0x180007c3e  xor     edx, edx; dx
0x180007c40  neg     ebx
0x180007c42  mov     rcx, rsi; lprc
0x180007c45  mov     r8d, ebx; dy
0x180007c48  add     [r15+58h], eax
0x180007c4c  call    cs:__imp_OffsetRect
0x180007c53  nop     dword ptr [rax+rax+00h]
0x180007c58  mov     rcx, [rbp+hWnd]; hWndFrom
0x180007c5c  mov     r9d, 2; cPoints
0x180007c62  mov     r8, rsi; lpPoints
0x180007c65  mov     rdx, r14; hWndTo
0x180007c68  call    cs:__imp_MapWindowPoints
0x180007c6f  nop     dword ptr [rax+rax+00h]
0x180007c74  movups  xmm0, xmmword ptr [rsi]
0x180007c77  lea     rdi, [r15+60h]
0x180007c7b  mov     ecx, 2Eh ; '.'; nIndex
0x180007c80  movdqu  xmmword ptr [rdi], xmm0
0x180007c84  call    cs:__imp_GetSystemMetrics
0x180007c8b  nop     dword ptr [rax+rax+00h]
0x180007c90  mov     ebx, eax
0x180007c92  mov     ecx, 2Dh ; '-'; nIndex
0x180007c97  neg     ebx
0x180007c99  call    cs:__imp_GetSystemMetrics
0x180007ca0  nop     dword ptr [rax+rax+00h]
0x180007ca5  mov     r8d, ebx; dy
0x180007ca8  mov     rcx, rdi; lprc
0x180007cab  neg     eax
0x180007cad  mov     edx, eax; dx
0x180007caf  call    cs:__imp_InflateRect
0x180007cb6  nop     dword ptr [rax+rax+00h]
0x180007cbb  mov     eax, [r15+68h]
0x180007cbf  mov     ecx, [r15+6Ch]
0x180007cc3  sub     ecx, [r15+64h]
0x180007cc7  add     ecx, ecx
0x180007cc9  mov     [r15+70h], eax
0x180007ccd  mov     eax, 55555556h
0x180007cd2  imul    ecx
0x180007cd4  mov     ecx, [rdi]
0x180007cd6  mov     eax, edx
0x180007cd8  dec     ecx
0x180007cda  shr     eax, 1Fh
0x180007cdd  add     edx, eax
0x180007cdf  add     ecx, edx
0x180007ce1  mov     [r15+74h], edx
0x180007ce5  mov     [r15+68h], ecx
0x180007ce9  mov     ecx, 2; nIndex
0x180007cee  call    cs:__imp_GetSysColor
0x180007cf5  nop     dword ptr [rax+rax+00h]
0x180007cfa  mov     ecx, eax; color
0x180007cfc  call    cs:__imp_CreateSolidBrush
0x180007d03  nop     dword ptr [rax+rax+00h]
0x180007d08  lea     rbx, [r15+80h]
0x180007d0f  mov     rcx, r13; hWnd
0x180007d12  mov     rdx, rbx; lpRect
0x180007d15  mov     [r15+78h], rax
0x180007d19  call    cs:__imp_GetWindowRect
0x180007d20  nop     dword ptr [rax+rax+00h]
0x180007d25  mov     r9d, 2; cPoints
0x180007d2b  mov     r8, rbx; lpPoints
0x180007d2e  mov     rdx, r14; hWndTo
0x180007d31  xor     ecx, ecx; hWndFrom
0x180007d33  call    cs:__imp_MapWindowPoints
0x180007d3a  nop     dword ptr [rax+rax+00h]
0x180007d3f  mov     rsi, qword ptr [rbp+var_20.left]
0x180007d43  xor     ebx, ebx
0x180007d45  mov     eax, [r15+70h]
0x180007d49  xorps   xmm0, xmm0
0x180007d4c  sub     eax, [r15+60h]
0x180007d50  xor     r9d, r9d; lpTimerFunc
0x180007d53  cdq
0x180007d54  idiv    dword ptr [r15+74h]
0x180007d58  xor     edx, edx
0x180007d5a  mov     ecx, eax
0x180007d5c  mov     eax, cs:gdwHungToKillCount
0x180007d62  imul    eax, cs:gCmsHungAppTimeout
0x180007d69  movups  xmmword ptr [rbp+var_20.left], xmm0
0x180007d6d  div     ecx
0x180007d6f  mov     edx, 301h; nIDEvent
0x180007d74  mov     rcx, r14; hWnd
0x180007d77  mov     r8d, eax; uElapse
0x180007d7a  call    cs:__imp_SetTimer
0x180007d81  nop     dword ptr [rax+rax+00h]
0x180007d86  lea     rdx, [rbp+Rect]; lpRect
0x180007d8a  mov     rcx, rsi; hWnd
0x180007d8d  call    cs:__imp_GetWindowRect
0x180007d94  nop     dword ptr [rax+rax+00h]
0x180007d99  lea     rdx, [rbp+var_20]; lpRect
0x180007d9d  mov     rcx, r13; hWnd
0x180007da0  call    cs:__imp_GetWindowRect
0x180007da7  nop     dword ptr [rax+rax+00h]
0x180007dac  mov     eax, [rbp+var_20.left]
0x180007daf  lea     r8, [rbp+Rect]; lpPoints
0x180007db3  sub     eax, [rbp+var_20.right]
0x180007db6  mov     r9d, 2; cPoints
0x180007dbc  add     eax, [rbp+Rect.right]
0x180007dbf  mov     rdx, r14; hWndTo
0x180007dc2  xor     ecx, ecx; hWndFrom
0x180007dc4  mov     [rbp+Rect.left], eax
0x180007dc7  call    cs:__imp_MapWindowPoints
0x180007dce  nop     dword ptr [rax+rax+00h]
0x180007dd3  mov     rax, qword ptr [rbp+Rect.left]
0x180007dd7  xor     edx, edx; hWndInsertAfter
0x180007dd9  mov     r9, rax
0x180007ddc  mov     [rsp+80h+uFlags], 41Dh; uFlags
0x180007de4  shr     r9, 20h; Y
0x180007de8  mov     r8d, eax; X
0x180007deb  mov     [rsp+80h+cy], ebx; cy
0x180007def  mov     rcx, r13; hWnd
0x180007df2  mov     [rsp+80h+var_60], ebx; cx
0x180007df6  call    cs:__imp_SetWindowPos
0x180007dfd  nop     dword ptr [rax+rax+00h]
0x180007e02  test    r12d, r12d
0x180007e05  jnz     short loc_180007E23
0x180007e07  xor     edx, edx; lpRect
0x180007e09  lea     r8d, [r12+1]; bErase
0x180007e0e  mov     rcx, r14; hWnd
0x180007e11  call    cs:__imp_InvalidateRect
0x180007e18  nop     dword ptr [rax+rax+00h]
0x180007e1d  test    byte ptr [r15], 4
0x180007e21  jz      short loc_180007E60
0x180007e23  mov     [rsp+80h+uFlags], 453h; uFlags
0x180007e2b  xor     r9d, r9d; Y
0x180007e2e  mov     [rsp+80h+cy], ebx; cy
0x180007e32  xor     r8d, r8d; X
0x180007e35  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x180007e39  mov     [rsp+80h+var_60], ebx; cx
0x180007e3d  mov     rcx, r14; hWnd
0x180007e40  call    cs:__imp_SetWindowPos
0x180007e47  nop     dword ptr [rax+rax+00h]
0x180007e4c  test    r12d, r12d
0x180007e4f  jz      short loc_180007E60
0x180007e51  mov     rcx, r14; hWnd
0x180007e54  call    cs:__imp_SetForegroundWindow
0x180007e5b  nop     dword ptr [rax+rax+00h]
0x180007e60  mov     rcx, [rbp+var_10]
0x180007e64  xor     rcx, rsp; StackCookie
0x180007e67  call    __security_check_cookie
0x180007e6c  mov     rbx, [rsp+80h+arg_18]
0x180007e74  add     rsp, 80h
0x180007e7b  pop     r15
0x180007e7d  pop     r14
0x180007e7f  pop     r13
0x180007e81  pop     r12
0x180007e83  pop     rdi
0x180007e84  pop     rsi
0x180007e85  pop     rbp
0x180007e86  retn
  ... truncated ...
```
