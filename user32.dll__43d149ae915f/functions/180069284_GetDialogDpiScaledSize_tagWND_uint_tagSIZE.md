# GetDialogDpiScaledSize(tagWND *,uint,tagSIZE *)

- ea: `0x180069284`
- end: `0x1800694da`
- name: `?GetDialogDpiScaledSize@@YAHPEAUtagWND@@IPEAUtagSIZE@@@Z`
- size: `598`
- prototype: `int(struct tagWND *, unsigned int, struct tagSIZE *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180008ab0`
- `0x18006eda8`

## callees

- `0x180029aac`
- `0x1800374d0`
- `0x18004c590`
- `0x180069284`
- `0x180078860`
- `0x1800788f4`
- `0x180078970`
- `0x1800968f4`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserGetDC` at `0x1800693c1`
- `win32u!NtUserGetDC` at `0x1800693c1`
- `GDI32!SelectObject` at `0x1800693d5`
- `GDI32!SelectObject` at `0x1800693f6`
- `GDI32!SelectObject` at `0x1800693d5`
- `GDI32!SelectObject` at `0x1800693f6`
- `GDI32!GetObjectW` at `0x180069375`
- `GDI32!GetObjectW` at `0x180069375`
- `GDI32!CreateFontIndirectW` at `0x1800693a5`
- `GDI32!CreateFontIndirectW` at `0x1800693a5`
- `GDI32!GdiGetCharDimensions` at `0x1800693e7`
- `GDI32!GdiGetCharDimensions` at `0x1800693e7`
- `GDI32!DeleteObject` at `0x180069346`
- `GDI32!DeleteObject` at `0x180069346`

## pseudocode

```c
__int64 __fastcall GetDialogDpiScaledSize(struct tagWND *a1, unsigned int a2, struct tagSIZE *a3)
{
  __int64 v3; // rax
  struct tagSIZE *v4; // rbx
  __int64 v7; // rdi
  unsigned int DpiForWindow; // eax
  LONG v9; // eax
  void *v10; // rcx
  HFONT MessageBoxFontForDpi; // rax
  HFONT v12; // rbx
  HWND v13; // r12
  HDC DC; // rax
  HDC v15; // rsi
  HGDIOBJ v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rcx
  struct tagRECT v20; // [rsp+20h] [rbp-89h] BYREF
  struct tagSIZE v21[2]; // [rsp+30h] [rbp-79h] BYREF
  struct tagRECT v22; // [rsp+40h] [rbp-69h] BYREF
  struct tagRECT v23; // [rsp+50h] [rbp-59h] BYREF
  LOGFONTW pv; // [rsp+60h] [rbp-49h] BYREF

  v3 = *((_QWORD *)a1 + 37);
  v4 = a3;
  *(_QWORD *)&v22.left = a3;
  v7 = *(_QWORD *)(v3 + 8);
  if ( (*(_BYTE *)(v7 + 24) & 8) == 0 || !*(_QWORD *)(v7 + 48) || (*(_BYTE *)(v7 + 56) & 1) != 0 )
    return 0;
  DpiForWindow = GetDpiForWindow(*(_QWORD *)a1);
  *(_OWORD *)&v21[0].cx = 0;
  ExpandRectByNonClientSize(a1, DpiForWindow, (struct tagRECT *)v21);
  v20.right = v21[0].cx + v4->cx - v21[1].cx;
  v9 = v21[0].cy + v4->cy - v21[1].cy;
  *(_QWORD *)&v20.left = 0;
  v20.bottom = v9;
  if ( *(_DWORD *)(v7 + 60) != a2 )
  {
    memset_0(&pv, 0, sizeof(pv));
    v10 = *(void **)(v7 + 64);
    if ( v10 )
    {
      DeleteObject(v10);
      *(_QWORD *)(v7 + 64) = 0;
      *(_QWORD *)(v7 + 72) = 0;
      *(_DWORD *)(v7 + 60) = 0;
    }
    if ( *(_DWORD *)(v7 + 80) == 0x7FFF )
    {
      MessageBoxFontForDpi = GetMessageBoxFontForDpi(a2);
      goto LABEL_11;
    }
    if ( GetObjectW(*(HANDLE *)(v7 + 48), 92, &pv) )
    {
      pv.lfHeight = (int)(*(_DWORD *)(v7 + 80) * a2 + 36) / -72;
      MessageBoxFontForDpi = CreateFontIndirectW(&pv);
LABEL_11:
      v12 = MessageBoxFontForDpi;
      if ( MessageBoxFontForDpi )
      {
        *(_QWORD *)(v7 + 64) = MessageBoxFontForDpi;
        *(_DWORD *)(v7 + 60) = a2;
        v13 = *(HWND *)a1;
        DC = (HDC)NtUserGetDC(*(_QWORD *)a1);
        v15 = DC;
        if ( DC )
        {
          v16 = SelectObject(DC, v12);
          *(_DWORD *)(v7 + 72) = GdiGetCharDimensions(v15, 0, (LONG *)(v7 + 76));
          SelectObject(v15, v16);
          if ( !*(_DWORD *)(v7 + 72) )
          {
            v18 = *(unsigned int *)(GetDpiServerInfoForCurrentThread(v17) + 32);
            *(_DWORD *)(v7 + 72) = v18;
            *(_DWORD *)(v7 + 76) = *(_DWORD *)(GetDpiServerInfoForCurrentThread(v18) + 36);
          }
          ReleaseDC(v13, v15);
        }
      }
      v4 = *(struct tagSIZE **)&v22.left;
    }
  }
  if ( *(_QWORD *)(v7 + 64) )
  {
    *(_QWORD *)&v22.left = *(_QWORD *)(v7 + 8);
    v21[0] = *(struct tagSIZE *)(v7 + 72);
    v20 = *DLURectFromRect(&v22, &v20, *(struct tagSIZE *)&v22.left);
    v20 = *RectFromDLURect(&v23, &v20, v21[0]);
    ExpandRectByNonClientSize(a1, a2, &v20);
    v4->cx = v20.right - v20.left;
    v4->cy = v20.bottom - v20.top;
  }
  return 1;
}

```

## disassembly

```asm
0x180069284  mov     [rsp-8+arg_18], rbx
0x180069289  push    rbp
0x18006928a  push    rsi
0x18006928b  push    rdi
0x18006928c  push    r12
0x18006928e  push    r13
0x180069290  push    r14
0x180069292  push    r15
0x180069294  lea     rbp, [rsp-27h]
0x180069299  sub     rsp, 0D0h
0x1800692a0  mov     rax, cs:__security_cookie
0x1800692a7  xor     rax, rsp
0x1800692aa  mov     [rbp+57h+var_40], rax
0x1800692ae  mov     rax, [rcx+128h]
0x1800692b5  mov     rbx, r8
0x1800692b8  mov     qword ptr [rbp+57h+var_C0], rbx
0x1800692bc  mov     r14d, edx
0x1800692bf  mov     r15, rcx
0x1800692c2  mov     rdi, [rax+8]
0x1800692c6  test    byte ptr [rdi+18h], 8
0x1800692ca  jz      loc_1800694B1
0x1800692d0  xor     r13d, r13d
0x1800692d3  cmp     [rdi+30h], r13
0x1800692d7  jz      loc_1800694B1
0x1800692dd  test    byte ptr [rdi+38h], 1
0x1800692e1  jnz     loc_1800694B1
0x1800692e7  mov     rcx, [rcx]
0x1800692ea  call    GetDpiForWindow
0x1800692ef  xorps   xmm0, xmm0
0x1800692f2  lea     r8, [rbp+57h+var_D0]; struct tagRECT *
0x1800692f6  mov     edx, eax; unsigned int
0x1800692f8  mov     rcx, r15; struct tagWND *
0x1800692fb  movups  xmmword ptr [rbp+57h+var_D0.cx], xmm0
0x1800692ff  call    ?ExpandRectByNonClientSize@@YAXPEBUtagWND@@IPEAUtagRECT@@@Z; ExpandRectByNonClientSize(tagWND const *,uint,tagRECT *)
0x180069304  mov     eax, [rbx]
0x180069306  sub     eax, [rbp+57h+var_D0.cx+8]
0x180069309  add     eax, [rbp+57h+var_D0.cx]
0x18006930c  mov     [rsp+100h+var_E0.right], eax
0x180069310  mov     eax, [rbx+4]
0x180069313  sub     eax, [rbp+57h+var_D0.cy+8]
0x180069316  add     eax, [rbp+57h+var_D0.cy]
0x180069319  mov     qword ptr [rsp+100h+var_E0.left], r13
0x18006931e  mov     [rbp+57h+var_E0.bottom], eax
0x180069321  cmp     [rdi+3Ch], r14d
0x180069325  jz      loc_180069427
0x18006932b  lea     esi, [r13+5Ch]
0x18006932f  xor     edx, edx; Val
0x180069331  mov     r8d, esi; Size
0x180069334  lea     rcx, [rbp+57h+pv]; void *
0x180069338  call    memset_0
0x18006933d  mov     rcx, [rdi+40h]; ho
0x180069341  test    rcx, rcx
0x180069344  jz      short loc_180069358
0x180069346  call    cs:__imp_DeleteObject
0x18006934c  mov     [rdi+40h], r13
0x180069350  mov     [rdi+48h], r13
0x180069354  mov     [rdi+3Ch], r13d
0x180069358  cmp     dword ptr [rdi+50h], 7FFFh
0x18006935f  jnz     short loc_18006936B
0x180069361  mov     ecx, r14d; unsigned int
0x180069364  call    ?GetMessageBoxFontForDpi@@YAPEAUHFONT__@@I@Z; GetMessageBoxFontForDpi(uint)
0x180069369  jmp     short loc_1800693AB
0x18006936b  mov     rcx, [rdi+30h]; h
0x18006936f  lea     r8, [rbp+57h+pv]; pv
0x180069373  mov     edx, esi; c
0x180069375  call    cs:__imp_GetObjectW
0x18006937b  test    eax, eax
0x18006937d  jz      loc_180069427
0x180069383  mov     ecx, r14d
0x180069386  mov     eax, 0C71C71C7h
0x18006938b  imul    ecx, [rdi+50h]
0x18006938f  add     ecx, 24h ; '$'
0x180069392  imul    ecx
0x180069394  lea     rcx, [rbp+57h+pv]; lplf
0x180069398  sar     edx, 4
0x18006939b  mov     eax, edx
0x18006939d  shr     eax, 1Fh
0x1800693a0  add     edx, eax
0x1800693a2  mov     [rbp+57h+pv.lfHeight], edx
0x1800693a5  call    cs:__imp_CreateFontIndirectW
0x1800693ab  mov     rbx, rax
0x1800693ae  test    rax, rax
0x1800693b1  jz      short loc_180069423
0x1800693b3  mov     [rdi+40h], rax
0x1800693b7  mov     [rdi+3Ch], r14d
0x1800693bb  mov     r12, [r15]
0x1800693be  mov     rcx, r12
0x1800693c1  call    cs:__imp_NtUserGetDC
0x1800693c7  mov     rsi, rax
0x1800693ca  test    rax, rax
0x1800693cd  jz      short loc_180069423
0x1800693cf  mov     rdx, rbx; h
0x1800693d2  mov     rcx, rax; hdc
0x1800693d5  call    cs:__imp_SelectObject
0x1800693db  lea     r8, [rdi+4Ch]; LONG *
0x1800693df  xor     edx, edx; LPTEXTMETRICW
0x1800693e1  mov     rcx, rsi; HDC
0x1800693e4  mov     rbx, rax
0x1800693e7  call    cs:__imp_GdiGetCharDimensions
0x1800693ed  mov     rdx, rbx; h
0x1800693f0  mov     rcx, rsi; hdc
0x1800693f3  mov     [rdi+48h], eax
0x1800693f6  call    cs:__imp_SelectObject
0x1800693fc  cmp     [rdi+48h], r13d
0x180069400  jnz     short loc_180069418
0x180069402  call    GetDpiServerInfoForCurrentThread
0x180069407  mov     ecx, [rax+20h]
0x18006940a  mov     [rdi+48h], ecx
0x18006940d  call    GetDpiServerInfoForCurrentThread
0x180069412  mov     ecx, [rax+24h]
0x180069415  mov     [rdi+4Ch], ecx
0x180069418  mov     rdx, rsi; hDC
0x18006941b  mov     rcx, r12; hWnd
0x18006941e  call    ReleaseDC
0x180069423  mov     rbx, qword ptr [rbp+57h+var_C0]
0x180069427  cmp     [rdi+40h], r13
0x18006942b  jz      short loc_1800694AA
0x18006942d  mov     eax, [rdi+8]
0x180069430  lea     rdx, [rsp+100h+var_E0]; struct tagRECT
0x180069435  movaps  xmm0, xmmword ptr [rsp+100h+var_E0.left]
0x18006943a  lea     rcx, [rbp+57h+var_C0]; retstr
0x18006943e  mov     dword ptr [rbp+57h+var_C0], eax
0x180069441  mov     eax, [rdi+0Ch]
0x180069444  mov     dword ptr [rbp+57h+var_C0+4], eax
0x180069447  mov     eax, [rdi+48h]
0x18006944a  mov     r8, qword ptr [rbp+57h+var_C0]; struct tagSIZE
0x18006944e  mov     [rbp+57h+var_D0.cx], eax
0x180069451  mov     eax, [rdi+4Ch]
0x180069454  mov     [rbp+57h+var_D0.cy], eax
0x180069457  movdqa  xmmword ptr [rsp+100h+var_E0.left], xmm0
0x18006945d  call    ?DLURectFromRect@@YA?AUtagRECT@@U1@UtagSIZE@@@Z; DLURectFromRect(tagRECT,tagSIZE)
0x180069462  mov     r8, qword ptr [rbp+57h+var_D0.cx]; struct tagSIZE
0x180069466  lea     rdx, [rsp+100h+var_E0]; struct tagRECT
0x18006946b  lea     rcx, [rbp+57h+var_B0]; retstr
0x18006946f  movups  xmm0, xmmword ptr [rax]
0x180069472  movdqu  xmmword ptr [rsp+100h+var_E0.left], xmm0
0x180069478  call    ?RectFromDLURect@@YA?AUtagRECT@@U1@UtagSIZE@@@Z; RectFromDLURect(tagRECT,tagSIZE)
0x18006947d  lea     r8, [rsp+100h+var_E0]; struct tagRECT *
0x180069482  mov     edx, r14d; unsigned int
0x180069485  mov     rcx, r15; struct tagWND *
0x180069488  movups  xmm0, xmmword ptr [rax]
0x18006948b  movdqu  xmmword ptr [rsp+100h+var_E0.left], xmm0
0x180069491  call    ?ExpandRectByNonClientSize@@YAXPEBUtagWND@@IPEAUtagRECT@@@Z; ExpandRectByNonClientSize(tagWND const *,uint,tagRECT *)
0x180069496  mov     ecx, [rsp+100h+var_E0.right]
0x18006949a  sub     ecx, [rsp+100h+var_E0.left]
0x18006949e  mov     [rbx], ecx
0x1800694a0  mov     ecx, [rbp+57h+var_E0.bottom]
0x1800694a3  sub     ecx, [rsp+100h+var_E0.top]
0x1800694a7  mov     [rbx+4], ecx
0x1800694aa  mov     eax, 1
0x1800694af  jmp     short loc_1800694B3
0x1800694b1  xor     eax, eax
0x1800694b3  mov     rcx, [rbp+57h+var_40]
0x1800694b7  xor     rcx, rsp; StackCookie
0x1800694ba  call    __security_check_cookie
0x1800694bf  mov     rbx, [rsp+100h+arg_18]
0x1800694c7  add     rsp, 0D0h
0x1800694ce  pop     r15
0x1800694d0  pop     r14
0x1800694d2  pop     r13
0x1800694d4  pop     r12
0x1800694d6  pop     rdi
0x1800694d7  pop     rsi
0x1800694d8  pop     rbp
0x1800694d9  retn
```
