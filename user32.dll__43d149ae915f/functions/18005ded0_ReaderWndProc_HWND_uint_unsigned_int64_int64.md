# ReaderWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18005ded0`
- end: `0x18005e0b3`
- name: `?ReaderWndProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `483`
- prototype: `__int64 __fastcall(HWND, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d210`
- `0x180010980`
- `0x180016310`
- `0x18002f198`
- `0x18003b270`
- `0x180044150`
- `0x18004dce4`
- `0x180057150`
- `0x18005ded0`
- `0x18005f978`
- `0x180089b38`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserGetCursorPos` at `0x1800a0250`
- `win32u!NtUserGetCursorPos` at `0x1800a0250`
- `win32u!NtUserReleaseCapture` at `0x18005e09f`
- `win32u!NtUserReleaseCapture` at `0x18005e09f`
- `win32u!NtUserSetWindowPos` at `0x1800a02ad`
- `win32u!NtUserSetWindowPos` at `0x1800a02ad`
- `win32u!NtUserSetFocus` at `0x1800a02bf`
- `win32u!NtUserSetFocus` at `0x1800a02bf`
- `win32u!NtUserSetTimer` at `0x1800a02d8`
- `win32u!NtUserSetTimer` at `0x1800a02d8`
- `win32u!NtUserSetCapture` at `0x1800a02b6`
- `win32u!NtUserSetCapture` at `0x1800a02b6`
- `win32u!NtUserKillTimer` at `0x1800a010f`
- `win32u!NtUserKillTimer` at `0x1800a010f`
- `win32u!NtUserDestroyWindow` at `0x1800a032b`
- `win32u!NtUserDestroyWindow` at `0x1800a032b`
- `ntdll!RtlFreeHeap` at `0x1800a0147`
- `ntdll!RtlFreeHeap` at `0x1800a0147`
- `ntdll!RtlAllocateHeap` at `0x1800a0163`
- `ntdll!RtlAllocateHeap` at `0x1800a0163`
- `GDI32!SelectObject` at `0x18005df71`
- `GDI32!SelectObject` at `0x18005df8f`
- `GDI32!SelectObject` at `0x18005dfa9`
- `GDI32!SelectObject` at `0x18005e009`
- `GDI32!SelectObject` at `0x18005e015`
- `GDI32!SelectObject` at `0x18005df71`
- `GDI32!SelectObject` at `0x18005df8f`
- `GDI32!SelectObject` at `0x18005dfa9`
- `GDI32!SelectObject` at `0x18005e009`
- `GDI32!SelectObject` at `0x18005e015`
- `GDI32!GetStockObject` at `0x18005df9d`
- `GDI32!GetStockObject` at `0x18005df9d`
- `GDI32!GetObjectW` at `0x1800a0208`
- `GDI32!GetObjectW` at `0x1800a0208`
- `GDI32!Ellipse` at `0x18005dffd`
- `GDI32!Ellipse` at `0x18005dffd`
- `GDI32!CreateEllipticRgn` at `0x1800a0275`
- `GDI32!CreateEllipticRgn` at `0x1800a0275`
- `GDI32!CreatePen` at `0x18005df80`
- `GDI32!CreatePen` at `0x18005df80`
- `GDI32!BitBlt` at `0x18005dfe3`
- `GDI32!BitBlt` at `0x18005dfe3`
- `GDI32!CreateCompatibleDC` at `0x18005df58`
- `GDI32!CreateCompatibleDC` at `0x18005df58`
- `GDI32!DeleteObject` at `0x18005e01e`
- `GDI32!DeleteObject` at `0x18005e027`
- `GDI32!DeleteObject` at `0x1800a0135`
- `GDI32!DeleteObject` at `0x18005e01e`
- `GDI32!DeleteObject` at `0x18005e027`
- `GDI32!DeleteObject` at `0x1800a0135`

## pseudocode

```c
LRESULT __fastcall ReaderWndProc(HWND a1, UINT Msg, HDC wParam, _OWORD **lParam)
{
  struct tagWND *v8; // rax
  __int64 v9; // r14
  HDC CompatibleDC; // rax
  HDC hdcSrc; // r13
  HPEN Pen; // rsi
  HGDIOBJ v13; // rdi
  HGDIOBJ StockObject; // rax
  HGDIOBJ v15; // rbx
  __int64 v17; // rsi
  void *v18; // rcx
  _QWORD *Heap; // rax
  _QWORD *v20; // rdi
  _OWORD *v21; // rcx
  HBITMAP Bmp; // rax
  int v23; // edi
  int v24; // esi
  HRGN EllipticRgn; // rax
  POINT pt; // [rsp+50h] [rbp-19h] BYREF
  struct tagRECT pv[2]; // [rsp+58h] [rbp-11h] BYREF
  struct tagRECT Rect; // [rsp+78h] [rbp+Fh] BYREF

  Rect = 0;
  pt = 0;
  memset(pv, 0, sizeof(pv));
  v8 = ValidateHwnd(a1);
  if ( !v8 )
    return 0;
  if ( Msg > 0x204 )
  {
    switch ( Msg )
    {
      case 0x205u:
      case 0x207u:
        goto LABEL_16;
      case 0x208u:
        pt.x = (__int16)lParam;
        pt.y = SWORD1(lParam);
        GetClientRect(a1, &Rect);
        if ( PtInRect(&Rect, pt) )
          return 0;
        goto LABEL_16;
      case 0x20Au:
      case 0x20Bu:
      case 0x20Cu:
      case 0x20Eu:
LABEL_16:
        NtUserReleaseCapture();
        return 0;
      case 0x215u:
        NtUserDestroyWindow(a1);
        return 0;
    }
    return DefWindowProcW_0(a1, Msg, (WPARAM)wParam, (LPARAM)lParam);
  }
  if ( Msg == 516 )
    goto LABEL_16;
  v9 = **((_QWORD **)v8 + 37);
  switch ( Msg )
  {
    case 1u:
      Heap = RtlAllocateHeap(pUserHeap, 8u, 0x38u);
      v20 = Heap;
      if ( !Heap )
        return -1;
      v21 = *lParam;
      *(_OWORD *)Heap = **lParam;
      Heap[2] = *((_QWORD *)v21 + 2);
      SetWindowLongPtrW(a1, 0, (LONG_PTR)Heap);
      if ( !v20[1] )
        return -1;
      if ( (*((_BYTE *)v20 + 4) & 3) == 3 )
      {
        v17 = 32661;
      }
      else if ( (*((_BYTE *)v20 + 4) & 1) != 0 )
      {
        v17 = 32559;
      }
      else
      {
        if ( (*((_BYTE *)v20 + 4) & 2) == 0 )
          return -1;
        v17 = 32660;
      }
      _SetWindowLong(a1, -20, 128, 0);
      _SetWindowLong(a1, -16, -2080374784, 0);
      Bmp = LoadBmp(hmodUser, (const unsigned __int16 *)v17, 0, 0, 0);
      v20[5] = Bmp;
      if ( Bmp
        && GetObjectW(Bmp, 32, pv)
        && ((unsigned int (__fastcall *)(_QWORD, __int64, _QWORD))v20[1])(v20[2], 1, 0) )
      {
        v20[6] = *(_QWORD *)&pv[0].top;
        v23 = pv[0].top + 1;
        v24 = pv[0].right + 1;
        NtUserGetCursorPos(&pt, 1);
        pt.x += v23 / -2;
        pt.y += v24 / -2;
        EllipticRgn = CreateEllipticRgn(0, 0, v23, v24);
        if ( EllipticRgn )
          SetWindowRgn(a1, EllipticRgn, 0);
        NtUserSetWindowPos(a1, -1, (unsigned int)pt.x, (unsigned int)pt.y, v23, v24, 80);
        NtUserSetCapture(a1);
        NtUserSetFocus(a1);
        NtUserSetTimer(a1, 1, 10);
        return 0;
      }
      return -1;
    case 0x14u:
      CompatibleDC = CreateCompatibleDC(wParam);
      hdcSrc = CompatibleDC;
      if ( CompatibleDC )
      {
        SelectObject(CompatibleDC, *(HGDIOBJ *)(v9 + 40));
        Pen = CreatePen(0, 1, 0);
        v13 = SelectObject(wParam, Pen);
        StockObject = GetStockObject(5);
        v15 = SelectObject(wParam, StockObject);
        BitBlt(wParam, 0, 0, *(_DWORD *)(v9 + 48), *(_DWORD *)(v9 + 52), hdcSrc, 0, 0, 0xCC0020u);
        Ellipse(wParam, 0, 0, *(_DWORD *)(v9 + 48), *(_DWORD *)(v9 + 52));
        SelectObject(wParam, v13);
        SelectObject(wParam, v15);
        DeleteObject(Pen);
        DeleteObject(hdcSrc);
        return 1;
      }
      return 0;
    case 0x82u:
      NtUserKillTimer(a1, 1);
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(v9 + 8))(*(_QWORD *)(v9 + 16), 3, 0);
      v18 = *(void **)(v9 + 40);
      if ( v18 )
        DeleteObject(v18);
      RtlFreeHeap(pUserHeap, 0, (PVOID)v9);
      return 0;
    case 0x100u:
      goto LABEL_16;
    case 0x113u:
      ReaderFeedback(v8, **((struct tagREADERINFO ***)v8 + 37));
      return 0;
    case 0x200u:
      ReaderMouseMove(v8, **((struct tagREADERINFO ***)v8 + 37), (__int64)lParam);
      return 0;
  }
  if ( Msg - 513 <= 1 )
    goto LABEL_16;
  return DefWindowProcW_0(a1, Msg, (WPARAM)wParam, (LPARAM)lParam);
}

```

## disassembly

```asm
0x18005ded0  push    rbp
0x18005ded2  push    rbx
0x18005ded3  push    rsi
0x18005ded4  push    rdi
0x18005ded5  push    r12
0x18005ded7  push    r13
0x18005ded9  push    r14
0x18005dedb  lea     rbp, [rsp-27h]
0x18005dee0  sub     rsp, 90h
0x18005dee7  mov     rax, cs:__security_cookie
0x18005deee  xor     rax, rsp
0x18005def1  mov     [rbp+57h+var_38], rax
0x18005def5  xorps   xmm0, xmm0
0x18005def8  xor     r13d, r13d
0x18005defb  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18005deff  mov     qword ptr [rbp+57h+pt.x], r13
0x18005df03  mov     rsi, r9
0x18005df06  movups  [rbp+57h+pv], xmm0
0x18005df0a  mov     r12, r8
0x18005df0d  mov     edi, edx
0x18005df0f  movups  [rbp+57h+var_58], xmm0
0x18005df13  mov     rbx, rcx
0x18005df16  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x18005df1b  test    rax, rax
0x18005df1e  jz      loc_18005E0A5
0x18005df24  mov     ecx, 204h
0x18005df29  cmp     edi, ecx
0x18005df2b  ja      loc_1800A02E4
0x18005df31  jz      loc_18005E09F
0x18005df37  mov     rcx, [rax+128h]
0x18005df3e  mov     r14, [rcx]
0x18005df41  mov     ecx, edi
0x18005df43  sub     ecx, 1
0x18005df46  jz      loc_1800A0153
0x18005df4c  sub     ecx, 13h
0x18005df4f  jnz     loc_18005E06E
0x18005df55  mov     rcx, r12; hdc
0x18005df58  call    cs:__imp_CreateCompatibleDC
0x18005df5e  mov     r13, rax
0x18005df61  test    rax, rax
0x18005df64  jz      loc_18005E0A5
0x18005df6a  mov     rdx, [r14+28h]; h
0x18005df6e  mov     rcx, rax; hdc
0x18005df71  call    cs:__imp_SelectObject
0x18005df77  xor     r8d, r8d; color
0x18005df7a  xor     ecx, ecx; iStyle
0x18005df7c  lea     edx, [r8+1]; cWidth
0x18005df80  call    cs:__imp_CreatePen
0x18005df86  mov     rdx, rax; h
0x18005df89  mov     rcx, r12; hdc
0x18005df8c  mov     rsi, rax
0x18005df8f  call    cs:__imp_SelectObject
0x18005df95  mov     ecx, 5; i
0x18005df9a  mov     rdi, rax
0x18005df9d  call    cs:__imp_GetStockObject
0x18005dfa3  mov     rdx, rax; h
0x18005dfa6  mov     rcx, r12; hdc
0x18005dfa9  call    cs:__imp_SelectObject
0x18005dfaf  mov     ecx, [r14+34h]
0x18005dfb3  xor     r8d, r8d; y
0x18005dfb6  mov     r9d, [r14+30h]; cx
0x18005dfba  xor     edx, edx; x
0x18005dfbc  mov     [rsp+0C0h+rop], 0CC0020h; rop
0x18005dfc4  mov     rbx, rax
0x18005dfc7  mov     [rsp+0C0h+y1], 0; y1
0x18005dfcf  mov     [rsp+0C0h+x1], 0; x1
0x18005dfd7  mov     [rsp+0C0h+hdcSrc], r13; hdcSrc
0x18005dfdc  mov     [rsp+0C0h+cy], ecx; cy
0x18005dfe0  mov     rcx, r12; hdc
0x18005dfe3  call    cs:__imp_BitBlt
0x18005dfe9  mov     ecx, [r14+34h]
0x18005dfed  xor     r8d, r8d; top
0x18005dff0  mov     r9d, [r14+30h]; right
0x18005dff4  xor     edx, edx; left
0x18005dff6  mov     [rsp+0C0h+cy], ecx; bottom
0x18005dffa  mov     rcx, r12; hdc
0x18005dffd  call    cs:__imp_Ellipse
0x18005e003  mov     rdx, rdi; h
0x18005e006  mov     rcx, r12; hdc
0x18005e009  call    cs:__imp_SelectObject
0x18005e00f  mov     rdx, rbx; h
0x18005e012  mov     rcx, r12; hdc
0x18005e015  call    cs:__imp_SelectObject
0x18005e01b  mov     rcx, rsi; ho
0x18005e01e  call    cs:__imp_DeleteObject
0x18005e024  mov     rcx, r13; ho
0x18005e027  call    cs:__imp_DeleteObject
0x18005e02d  mov     eax, 1
0x18005e032  mov     rcx, [rbp+57h+var_38]
0x18005e036  xor     rcx, rsp; StackCookie
0x18005e039  call    __security_check_cookie
0x18005e03e  add     rsp, 90h
0x18005e045  pop     r14
0x18005e047  pop     r13
0x18005e049  pop     r12
0x18005e04b  pop     rdi
0x18005e04c  pop     rsi
0x18005e04d  pop     rbx
0x18005e04e  pop     rbp
0x18005e04f  retn
0x18005e050  mov     eax, [rdi+4]
0x18005e053  and     eax, 3
0x18005e056  cmp     al, 3
0x18005e058  jz      short loc_18005E0A9
0x18005e05a  test    byte ptr [rdi+4], 1
0x18005e05e  jz      loc_1800A01A4
0x18005e064  mov     esi, 7F2Fh
0x18005e069  jmp     loc_1800A01AF
0x18005e06e  sub     ecx, 6Eh ; 'n'
0x18005e071  jz      loc_1800A0107
0x18005e077  sub     ecx, 7Eh ; '~'
0x18005e07a  jz      short loc_18005E09F
0x18005e07c  sub     ecx, 13h
0x18005e07f  jz      loc_1800A00F6
0x18005e085  sub     ecx, 0EDh
0x18005e08b  jz      loc_1800A00E2
0x18005e091  sub     ecx, 1
0x18005e094  jz      short loc_18005E09F
0x18005e096  cmp     ecx, 1
0x18005e099  jnz     loc_1800A0337
0x18005e09f  call    cs:__imp_NtUserReleaseCapture
0x18005e0a5  xor     eax, eax
0x18005e0a7  jmp     short loc_18005E032
0x18005e0a9  mov     esi, 7F95h
0x18005e0ae  jmp     loc_1800A01AF
0x1800a00e2  mov     r8, rsi; __int64
0x1800a00e5  mov     rdx, r14; struct tagREADERINFO *
0x1800a00e8  mov     rcx, rax; struct tagWND *
0x1800a00eb  call    ?ReaderMouseMove@@YAXPEAUtagWND@@PEAUtagREADERINFO@@_J@Z; ReaderMouseMove(tagWND *,tagREADERINFO *,__int64)
0x1800a00f0  nop
0x1800a00f1  jmp     loc_18005E0A5
0x1800a00f6  mov     rdx, r14; struct tagREADERINFO *
0x1800a00f9  mov     rcx, rax; struct tagWND *
0x1800a00fc  call    ?ReaderFeedback@@YAXPEAUtagWND@@PEAUtagREADERINFO@@@Z; ReaderFeedback(tagWND *,tagREADERINFO *)
0x1800a0101  nop
0x1800a0102  jmp     loc_18005E0A5
0x1800a0107  mov     edx, 1
0x1800a010c  mov     rcx, rbx
0x1800a010f  call    cs:__imp_NtUserKillTimer
0x1800a0115  mov     rcx, [r14+10h]
0x1800a0119  xor     r9d, r9d
0x1800a011c  mov     rax, [r14+8]
0x1800a0120  xor     r8d, r8d
0x1800a0123  lea     edx, [r9+3]
0x1800a0127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a012c  mov     rcx, [r14+28h]; ho
0x1800a0130  test    rcx, rcx
0x1800a0133  jz      short loc_1800A013B
0x1800a0135  call    cs:__imp_DeleteObject
0x1800a013b  mov     rcx, cs:pUserHeap; HeapHandle
0x1800a0142  mov     r8, r14; P
0x1800a0145  xor     edx, edx; Flags
0x1800a0147  call    cs:__imp_RtlFreeHeap
0x1800a014d  nop
0x1800a014e  jmp     loc_18005E0A5
0x1800a0153  mov     rcx, cs:pUserHeap; HeapHandle
0x1800a015a  mov     edx, 8; Flags
0x1800a015f  lea     r8d, [rdx+30h]; Size
0x1800a0163  call    cs:__imp_RtlAllocateHeap
0x1800a0169  mov     rdi, rax
0x1800a016c  test    rax, rax
0x1800a016f  jz      short loc_1800A019B
0x1800a0171  mov     rcx, [rsi]
0x1800a0174  mov     r8, rax; dwNewLong
0x1800a0177  xor     edx, edx; nIndex
0x1800a0179  movups  xmm0, xmmword ptr [rcx]
0x1800a017c  movups  xmmword ptr [rax], xmm0
0x1800a017f  movsd   xmm1, qword ptr [rcx+10h]
0x1800a0184  mov     rcx, rbx; hWnd
0x1800a0187  movsd   qword ptr [rax+10h], xmm1
0x1800a018c  call    SetWindowLongPtrW
0x1800a0191  cmp     [rdi+8], r13
0x1800a0195  jnz     loc_18005E050
0x1800a019b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a019f  jmp     loc_18005E032
0x1800a01a4  test    byte ptr [rdi+4], 2
0x1800a01a8  jz      short loc_1800A019B
0x1800a01aa  mov     esi, 7F94h
0x1800a01af  xor     r9d, r9d; int
0x1800a01b2  mov     r8d, 80h; int
0x1800a01b8  mov     rcx, rbx; HWND
0x1800a01bb  lea     edx, [r9-14h]; int
0x1800a01bf  call    ?_SetWindowLong@@YAJPEAUHWND__@@HJH@Z; _SetWindowLong(HWND__ *,int,long,int)
0x1800a01c4  xor     r9d, r9d; int
0x1800a01c7  mov     r8d, 84000000h; int
0x1800a01cd  mov     rcx, rbx; HWND
0x1800a01d0  lea     edx, [r9-10h]; int
0x1800a01d4  call    ?_SetWindowLong@@YAJPEAUHWND__@@HJH@Z; _SetWindowLong(HWND__ *,int,long,int)
0x1800a01d9  mov     rcx, cs:hmodUser; HINSTANCE
0x1800a01e0  xor     r9d, r9d; unsigned int
0x1800a01e3  xor     r8d, r8d; nWidth
0x1800a01e6  mov     [rsp+0C0h+cy], r13d; unsigned int
0x1800a01eb  mov     rdx, rsi; unsigned __int16 *
0x1800a01ee  call    ?LoadBmp@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEBGHHI@Z; LoadBmp(HINSTANCE__ *,ushort const *,int,int,uint)
0x1800a01f3  mov     [rdi+28h], rax
0x1800a01f7  test    rax, rax
0x1800a01fa  jz      short loc_1800A019B
0x1800a01fc  lea     r8, [rbp+57h+pv]; pv
0x1800a0200  mov     edx, 20h ; ' '; c
0x1800a0205  mov     rcx, rax; h
0x1800a0208  call    cs:__imp_GetObjectW
0x1800a020e  test    eax, eax
0x1800a0210  jz      short loc_1800A019B
0x1800a0212  mov     rcx, [rdi+10h]
0x1800a0216  xor     r9d, r9d
0x1800a0219  mov     rax, [rdi+8]
0x1800a021d  xor     r8d, r8d
0x1800a0220  lea     edx, [r9+1]
0x1800a0224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0229  test    eax, eax
0x1800a022b  jz      loc_1800A019B
0x1800a0231  mov     eax, dword ptr [rbp+57h+pv+4]
0x1800a0234  lea     rcx, [rbp+57h+pt]
0x1800a0238  mov     [rdi+30h], eax
0x1800a023b  mov     edx, 1
0x1800a0240  mov     eax, dword ptr [rbp+57h+pv+8]
0x1800a0243  mov     [rdi+34h], eax
0x1800a0246  mov     edi, dword ptr [rbp+57h+pv+4]
0x1800a0249  mov     esi, dword ptr [rbp+57h+pv+8]
0x1800a024c  inc     edi
0x1800a024e  inc     esi
0x1800a0250  call    cs:__imp_NtUserGetCursorPos
0x1800a0256  mov     ecx, 0FFFFFFFEh
0x1800a025b  mov     eax, edi
0x1800a025d  cdq
0x1800a025e  mov     r9d, esi; y2
0x1800a0261  idiv    ecx
0x1800a0263  mov     r8d, edi; x2
0x1800a0266  add     [rbp+57h+pt.x], eax
0x1800a0269  mov     eax, esi
0x1800a026b  cdq
0x1800a026c  idiv    ecx
0x1800a026e  xor     edx, edx; y1
0x1800a0270  xor     ecx, ecx; x1
0x1800a0272  add     [rbp+57h+pt.y], eax
0x1800a0275  call    cs:__imp_CreateEllipticRgn
0x1800a027b  test    rax, rax
0x1800a027e  jz      short loc_1800A028E
0x1800a0280  xor     r8d, r8d; bRedraw
0x1800a0283  mov     rdx, rax; hRgn
0x1800a0286  mov     rcx, rbx; hWnd
0x1800a0289  call    SetWindowRgn
0x1800a028e  mov     r9d, [rbp+57h+pt.y]
0x1800a0292  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800a0296  mov     r8d, [rbp+57h+pt.x]
0x1800a029a  mov     rcx, rbx
0x1800a029d  mov     [rsp+0C0h+x1], 50h ; 'P'
0x1800a02a5  mov     dword ptr [rsp+0C0h+hdcSrc], esi
0x1800a02a9  mov     [rsp+0C0h+cy], edi
0x1800a02ad  call    cs:__imp_NtUserSetWindowPos
0x1800a02b3  mov     rcx, rbx
0x1800a02b6  call    cs:__imp_NtUserSetCapture
0x1800a02bc  mov     rcx, rbx
0x1800a02bf  call    cs:__imp_NtUserSetFocus
0x1800a02c5  xor     r9d, r9d
0x1800a02c8  mov     [rsp+0C0h+cy], r13d
0x1800a02cd  mov     rcx, rbx
0x1800a02d0  lea     edx, [r9+1]
0x1800a02d4  lea     r8d, [r9+0Ah]
0x1800a02d8  call    cs:__imp_NtUserSetTimer
0x1800a02de  nop
0x1800a02df  jmp     loc_18005E0A5
0x1800a02e4  mov     eax, edi
0x1800a02e6  sub     eax, 205h
0x1800a02eb  jz      loc_18005E09F
0x1800a02f1  sub     eax, 2
0x1800a02f4  jz      loc_18005E09F
0x1800a02fa  sub     eax, 1
0x1800a02fd  jz      short loc_1800A034D
0x1800a02ff  sub     eax, 2
0x1800a0302  jz      loc_18005E09F
0x1800a0308  sub     eax, 1
0x1800a030b  jz      loc_18005E09F
0x1800a0311  sub     eax, 1
0x1800a0314  jz      loc_18005E09F
0x1800a031a  sub     eax, 2
0x1800a031d  jz      loc_18005E09F
0x1800a0323  cmp     eax, 7
0x1800a0326  jnz     short loc_1800A0337
0x1800a0328  mov     rcx, rbx
0x1800a032b  call    cs:__imp_NtUserDestroyWindow
0x1800a0331  nop
0x1800a0332  jmp     loc_18005E0A5
0x1800a0337  mov     r9, rsi; lParam
0x1800a033a  mov     r8, r12; wParam
0x1800a033d  mov     edx, edi; Msg
0x1800a033f  mov     rcx, rbx; hWnd
0x1800a0342  call    DefWindowProcW_0
0x1800a0347  nop
0x1800a0348  jmp     loc_18005E032
0x1800a034d  movsx   eax, si
0x1800a0350  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800a0354  mov     [rbp+57h+pt.x], eax
0x1800a0357  mov     rcx, rbx; hWnd
0x1800a035a  shr     rsi, 10h
0x1800a035e  movsx   eax, si
0x1800a0361  mov     [rbp+57h+pt.y], eax
0x1800a0364  call    GetClientRect
0x1800a0369  mov     rdx, qword ptr [rbp+57h+pt.x]; pt
0x1800a036d  lea     rcx, [rbp+57h+Rect]; lprc
  ... truncated ...
```
