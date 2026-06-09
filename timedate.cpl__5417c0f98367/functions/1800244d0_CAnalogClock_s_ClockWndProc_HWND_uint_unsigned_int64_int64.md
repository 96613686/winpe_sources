# CAnalogClock::s_ClockWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800244d0`
- end: `0x1800247f0`
- name: `?s_ClockWndProc@CAnalogClock@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `800`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, unsigned __int64, struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x180001de4`
- `0x1800024e0`
- `0x1800238a8`
- `0x180023a70`
- `0x180023dec`
- `0x180023f3c`
- `0x180024010`
- `0x1800242b8`
- `0x1800244d0`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800246cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800246cc`
- `gdiplus!GdiplusShutdown` at `0x1800245d9`
- `gdiplus!GdiplusShutdown` at `0x1800245d9`
- `USER32!DefWindowProcW` at `0x180024746`
- `USER32!DefWindowProcW` at `0x180024746`
- `USER32!SetWindowLongPtrW` at `0x1800245c2`
- `USER32!SetWindowLongPtrW` at `0x1800246db`
- `USER32!SetWindowLongPtrW` at `0x1800245c2`
- `USER32!SetWindowLongPtrW` at `0x1800246db`
- `USER32!GetWindowLongPtrW` at `0x1800244fd`
- `USER32!GetWindowLongPtrW` at `0x1800244fd`
- `USER32!BeginPaint` at `0x18002455d`
- `USER32!BeginPaint` at `0x18002455d`
- `USER32!EndPaint` at `0x180024578`
- `USER32!EndPaint` at `0x180024578`

## pseudocode

```c
LRESULT __fastcall CAnalogClock::s_ClockWndProc(HWND hWnd, UINT Msg, WPARAM a3, struct _SYSTEMTIME *a4)
{
  LONG_PTR WindowLongPtrW; // rax
  CAnalogClock *v9; // rbx
  int v10; // r8d
  unsigned __int16 *p_wYear; // rdx
  LRESULT result; // rax
  __int64 v13; // rbp
  char *v14; // rax
  void *v15; // rbx
  int v16; // eax
  tagPAINTSTRUCT Paint; // [rsp+20h] [rbp-88h] BYREF

  WindowLongPtrW = GetWindowLongPtrW(hWnd, -21);
  v9 = (CAnalogClock *)WindowLongPtrW;
  if ( Msg > 0x14 )
  {
    switch ( Msg )
    {
      case 0x15u:
      case 0x31Au:
        if ( WindowLongPtrW )
        {
          CAnalogClock::_DeleteTools((CAnalogClock *)WindowLongPtrW);
          if ( !(unsigned int)CAnalogClock::_CreateTools(v9) )
            CAnalogClock::_DeleteTools(v9);
        }
        return 0;
      case 0x401u:
        if ( !a4 || !WindowLongPtrW )
          return 0;
        LODWORD(result) = CAnalogClock::_ClockSetTime((CAnalogClock *)WindowLongPtrW, a4);
        return (int)result;
      case 0x402u:
        if ( !a4 || !WindowLongPtrW )
          return 0;
        a4->wHour = *(_WORD *)(WindowLongPtrW + 92);
        a4->wMinute = *(_WORD *)(WindowLongPtrW + 96);
        a4->wSecond = *(_WORD *)(WindowLongPtrW + 100);
        a4->wDayOfWeek = *(_WORD *)(WindowLongPtrW + 104);
        break;
      case 0x404u:
        if ( !WindowLongPtrW || !a4 )
          return 0;
        v16 = *(_DWORD *)(WindowLongPtrW + 136);
        *(_DWORD *)&a4->wYear = v16;
        *(_DWORD *)&a4->wDayOfWeek = v16;
        break;
      default:
        return DefWindowProcW(hWnd, Msg, a3, (LPARAM)a4);
    }
    return 1;
  }
  if ( Msg == 20 )
  {
    if ( !WindowLongPtrW || *(_DWORD *)(WindowLongPtrW + 128) )
      return DefWindowProcW(hWnd, Msg, a3, (LPARAM)a4);
    return 1;
  }
  if ( Msg != 1 )
  {
    switch ( Msg )
    {
      case 2u:
        if ( WindowLongPtrW )
        {
          SetWindowLongPtrW(hWnd, -21, 0);
          CAnalogClock::_DeleteTools(v9);
          if ( *((_QWORD *)v9 + 3) )
            GdiplusShutdown();
          operator delete(v9);
        }
        return 0;
      case 0xDu:
        if ( WindowLongPtrW )
        {
          v10 = a3;
          p_wYear = &a4->wYear;
          goto LABEL_14;
        }
        break;
      case 0xEu:
        if ( WindowLongPtrW )
        {
          v10 = 0;
          p_wYear = 0;
LABEL_14:
          LODWORD(result) = CAnalogClock::_GetAccName((CAnalogClock *)WindowLongPtrW, p_wYear, v10);
          return (int)result;
        }
        break;
      case 0xFu:
        if ( WindowLongPtrW )
        {
          memset_0(&Paint, 0, sizeof(Paint));
          BeginPaint(hWnd, &Paint);
          CAnalogClock::_ClockPaint(v9, Paint.hdc);
          EndPaint(hWnd, &Paint);
        }
        return 0;
      default:
        return DefWindowProcW(hWnd, Msg, a3, (LPARAM)a4);
    }
    return 0;
  }
  v13 = -1;
  v14 = (char *)operator new(0xC0u, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v14;
  if ( v14 )
  {
    *(_QWORD *)v14 = 0;
    *((_QWORD *)v14 + 1) = 0;
    *((_QWORD *)v14 + 3) = 0;
    *((_QWORD *)v14 + 4) = 0;
    *((_QWORD *)v14 + 5) = 0;
    *((_QWORD *)v14 + 6) = 0;
    *((_QWORD *)v14 + 7) = 0;
    *((_QWORD *)v14 + 8) = 0;
    *(_OWORD *)(v14 + 72) = 0;
    *((_DWORD *)v14 + 22) = 0;
    *((_DWORD *)v14 + 4) = 1;
    *(_OWORD *)(v14 + 92) = 0;
    *(_OWORD *)(v14 + 108) = 0;
    *(_QWORD *)(v14 + 124) = 0;
    *((_DWORD *)v14 + 33) = 0;
    *(_OWORD *)(v14 + 136) = xmmword_180030770;
    *(_OWORD *)(v14 + 152) = xmmword_180030780;
    *(_OWORD *)(v14 + 168) = xmmword_180030790;
    *((_QWORD *)v14 + 23) = 0x1200000001LL;
    if ( (unsigned int)CAnalogClock::_ClockCreate((CAnalogClock *)v14, hWnd, (struct tagCREATESTRUCTW *const)a4)
      && ((SetLastError(0), SetWindowLongPtrW(hWnd, -21, (LONG_PTR)v15)) || !GetLastError()) )
    {
      return 0;
    }
    else
    {
      operator delete(v15);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x1800244d0  push    rbx
0x1800244d2  push    rbp
0x1800244d3  push    rsi
0x1800244d4  push    rdi
0x1800244d5  push    r14
0x1800244d7  sub     rsp, 80h
0x1800244de  mov     rax, cs:__security_cookie
0x1800244e5  xor     rax, rsp
0x1800244e8  mov     [rsp+0A8h+var_38], rax
0x1800244ed  mov     ebp, edx
0x1800244ef  mov     rdi, r9
0x1800244f2  mov     edx, 0FFFFFFEBh; nIndex
0x1800244f7  mov     r14, r8
0x1800244fa  mov     rsi, rcx
0x1800244fd  call    cs:__imp_GetWindowLongPtrW
0x180024503  mov     rbx, rax
0x180024506  cmp     ebp, 14h
0x180024509  ja      loc_180024714
0x18002450f  jz      loc_180024704
0x180024515  mov     eax, ebp
0x180024517  sub     eax, 1
0x18002451a  jz      loc_1800245EC
0x180024520  sub     eax, 1
0x180024523  jz      loc_1800245AF
0x180024529  sub     eax, 0Bh
0x18002452c  jz      short loc_180024593
0x18002452e  sub     eax, 1
0x180024531  jz      short loc_180024583
0x180024533  cmp     eax, 1
0x180024536  jnz     loc_18002473B
0x18002453c  test    rbx, rbx
0x18002453f  jz      loc_1800247D3
0x180024545  xor     edx, edx; Val
0x180024547  lea     r8d, [rax+47h]; Size
0x18002454b  lea     rcx, [rsp+0A8h+Paint]; void *
0x180024550  call    memset_0
0x180024555  lea     rdx, [rsp+0A8h+Paint]; lpPaint
0x18002455a  mov     rcx, rsi; hWnd
0x18002455d  call    cs:__imp_BeginPaint
0x180024563  mov     rdx, [rsp+0A8h+Paint.hdc]; HDC
0x180024568  mov     rcx, rbx; this
0x18002456b  call    ?_ClockPaint@CAnalogClock@@AEAAXPEAUHDC__@@@Z; CAnalogClock::_ClockPaint(HDC__ *)
0x180024570  lea     rdx, [rsp+0A8h+Paint]; lpPaint
0x180024575  mov     rcx, rsi; hWnd
0x180024578  call    cs:__imp_EndPaint
0x18002457e  jmp     loc_1800247D3
0x180024583  test    rbx, rbx
0x180024586  jz      loc_1800247D3
0x18002458c  xor     r8d, r8d
0x18002458f  xor     edx, edx
0x180024591  jmp     short loc_1800245A2
0x180024593  test    rbx, rbx
0x180024596  jz      loc_1800247D3
0x18002459c  mov     r8d, r14d; int
0x18002459f  mov     rdx, rdi; unsigned __int16 *
0x1800245a2  mov     rcx, rbx; this
0x1800245a5  call    ?_GetAccName@CAnalogClock@@AEAAHPEAGH@Z; CAnalogClock::_GetAccName(ushort *,int)
0x1800245aa  jmp     loc_1800247AE
0x1800245af  test    rbx, rbx
0x1800245b2  jz      loc_1800247D3
0x1800245b8  xor     r8d, r8d; dwNewLong
0x1800245bb  mov     rcx, rsi; hWnd
0x1800245be  lea     edx, [r8-15h]; nIndex
0x1800245c2  call    cs:__imp_SetWindowLongPtrW
0x1800245c8  mov     rcx, rbx; this
0x1800245cb  call    ?_DeleteTools@CAnalogClock@@AEAAXXZ; CAnalogClock::_DeleteTools(void)
0x1800245d0  mov     rcx, [rbx+18h]
0x1800245d4  test    rcx, rcx
0x1800245d7  jz      short loc_1800245DF
0x1800245d9  call    cs:__imp_GdiplusShutdown
0x1800245df  mov     rcx, rbx; Block
0x1800245e2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800245e7  jmp     loc_1800247D3
0x1800245ec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800245f3  mov     ecx, 0C0h; unsigned __int64
0x1800245f8  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800245fc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180024601  mov     rbx, rax
0x180024604  test    rax, rax
0x180024607  jz      loc_1800246FC
0x18002460d  xorps   xmm0, xmm0
0x180024610  mov     qword ptr [rax], 0
0x180024617  mov     qword ptr [rax+8], 0
0x18002461f  xorps   xmm1, xmm1
0x180024622  mov     qword ptr [rax+18h], 0
0x18002462a  mov     r8, rdi; struct tagCREATESTRUCTW *
0x18002462d  mov     qword ptr [rax+20h], 0
0x180024635  mov     rdx, rsi; hWnd
0x180024638  mov     qword ptr [rax+28h], 0
0x180024640  mov     rcx, rax; this
0x180024643  mov     qword ptr [rax+30h], 0
0x18002464b  mov     qword ptr [rax+38h], 0
0x180024653  mov     qword ptr [rax+40h], 0
0x18002465b  movups  xmmword ptr [rax+48h], xmm0
0x18002465f  mov     dword ptr [rax+58h], 0
0x180024666  mov     dword ptr [rax+10h], 1
0x18002466d  movups  xmmword ptr [rax+5Ch], xmm0
0x180024671  movups  xmm0, cs:xmmword_180030770
0x180024678  movups  xmmword ptr [rax+6Ch], xmm1
0x18002467c  mov     qword ptr [rax+7Ch], 0
0x180024684  movups  xmm1, cs:xmmword_180030780
0x18002468b  mov     dword ptr [rax+84h], 0
0x180024695  movups  xmmword ptr [rax+88h], xmm0
0x18002469c  movups  xmm0, cs:xmmword_180030790
0x1800246a3  movups  xmmword ptr [rax+98h], xmm1
0x1800246aa  movsd   xmm1, cs:qword_1800307A0
0x1800246b2  movups  xmmword ptr [rax+0A8h], xmm0
0x1800246b9  movsd   qword ptr [rax+0B8h], xmm1
0x1800246c1  call    ?_ClockCreate@CAnalogClock@@AEAAHPEAUHWND__@@QEAUtagCREATESTRUCTW@@@Z; CAnalogClock::_ClockCreate(HWND__ *,tagCREATESTRUCTW * const)
0x1800246c6  test    eax, eax
0x1800246c8  jz      short loc_1800246F4
0x1800246ca  xor     ecx, ecx; dwErrCode
0x1800246cc  call    cs:__imp_SetLastError
0x1800246d2  mov     r8, rbx; dwNewLong
0x1800246d5  lea     edx, [rbp-14h]; nIndex
0x1800246d8  mov     rcx, rsi; hWnd
0x1800246db  call    cs:__imp_SetWindowLongPtrW
0x1800246e1  test    rax, rax
0x1800246e4  jnz     short loc_1800246F0
0x1800246e6  call    cs:__imp_GetLastError
0x1800246ec  test    eax, eax
0x1800246ee  jnz     short loc_1800246F4
0x1800246f0  xor     ebp, ebp
0x1800246f2  jmp     short loc_1800246FC
0x1800246f4  mov     rcx, rbx; Block
0x1800246f7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800246fc  mov     rax, rbp
0x1800246ff  jmp     loc_1800247D5
0x180024704  test    rbx, rbx
0x180024707  jz      short loc_18002473B
0x180024709  cmp     dword ptr [rax+80h], 0
0x180024710  jnz     short loc_18002473B
0x180024712  jmp     short loc_180024792
0x180024714  mov     eax, ebp
0x180024716  sub     eax, 15h
0x180024719  jz      loc_1800247B2
0x18002471f  sub     eax, 305h
0x180024724  jz      loc_1800247B2
0x18002472a  sub     eax, 0E7h
0x18002472f  jz      short loc_180024799
0x180024731  sub     eax, 1
0x180024734  jz      short loc_180024768
0x180024736  cmp     eax, 2
0x180024739  jz      short loc_180024751
0x18002473b  mov     r9, rdi; lParam
0x18002473e  mov     r8, r14; wParam
0x180024741  mov     edx, ebp; Msg
0x180024743  mov     rcx, rsi; hWnd
0x180024746  call    cs:__imp_DefWindowProcW
0x18002474c  jmp     loc_1800247D5
0x180024751  test    rbx, rbx
0x180024754  jz      short loc_1800247D3
0x180024756  test    rdi, rdi
0x180024759  jz      short loc_1800247D3
0x18002475b  mov     eax, [rbx+88h]
0x180024761  mov     [rdi], eax
0x180024763  mov     [rdi+4], eax
0x180024766  jmp     short loc_180024792
0x180024768  test    rdi, rdi
0x18002476b  jz      short loc_1800247D3
0x18002476d  test    rbx, rbx
0x180024770  jz      short loc_1800247D3
0x180024772  movzx   eax, word ptr [rbx+5Ch]
0x180024776  mov     [rdi+8], ax
0x18002477a  movzx   eax, word ptr [rbx+60h]
0x18002477e  mov     [rdi+0Ah], ax
0x180024782  movzx   eax, word ptr [rbx+64h]
0x180024786  mov     [rdi+0Ch], ax
0x18002478a  movzx   eax, word ptr [rbx+68h]
0x18002478e  mov     [rdi+4], ax
0x180024792  mov     eax, 1
0x180024797  jmp     short loc_1800247D5
0x180024799  test    rdi, rdi
0x18002479c  jz      short loc_1800247D3
0x18002479e  test    rbx, rbx
0x1800247a1  jz      short loc_1800247D3
0x1800247a3  mov     rdx, rdi; struct _SYSTEMTIME *
0x1800247a6  mov     rcx, rbx; this
0x1800247a9  call    ?_ClockSetTime@CAnalogClock@@AEAAHPEBU_SYSTEMTIME@@@Z; CAnalogClock::_ClockSetTime(_SYSTEMTIME const *)
0x1800247ae  cdqe
0x1800247b0  jmp     short loc_1800247D5
0x1800247b2  test    rbx, rbx
0x1800247b5  jz      short loc_1800247D3
0x1800247b7  mov     rcx, rbx; this
0x1800247ba  call    ?_DeleteTools@CAnalogClock@@AEAAXXZ; CAnalogClock::_DeleteTools(void)
0x1800247bf  mov     rcx, rbx; this
0x1800247c2  call    ?_CreateTools@CAnalogClock@@AEAAHXZ; CAnalogClock::_CreateTools(void)
0x1800247c7  test    eax, eax
0x1800247c9  jnz     short loc_1800247D3
0x1800247cb  mov     rcx, rbx; this
0x1800247ce  call    ?_DeleteTools@CAnalogClock@@AEAAXXZ; CAnalogClock::_DeleteTools(void)
0x1800247d3  xor     eax, eax
0x1800247d5  mov     rcx, [rsp+0A8h+var_38]
0x1800247da  xor     rcx, rsp; StackCookie
0x1800247dd  call    __security_check_cookie
0x1800247e2  add     rsp, 80h
0x1800247e9  pop     r14
0x1800247eb  pop     rdi
0x1800247ec  pop     rsi
0x1800247ed  pop     rbp
0x1800247ee  pop     rbx
0x1800247ef  retn
```
