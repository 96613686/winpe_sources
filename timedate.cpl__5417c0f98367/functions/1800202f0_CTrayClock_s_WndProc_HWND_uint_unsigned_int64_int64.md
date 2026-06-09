# CTrayClock::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800202f0`
- end: `0x180020405`
- name: `?s_WndProc@CTrayClock@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `277`
- prototype: `__int64 __fastcall(HWND, UINT Msg, unsigned __int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180011774`
- `0x180016e28`
- `0x18001f808`
- `0x18001fae0`
- `0x1800202f0`
- `0x18002a010`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x1800203e4`
- `USER32!PostThreadMessageW` at `0x1800203e4`
- `USER32!DefWindowProcW` at `0x180020346`
- `USER32!DefWindowProcW` at `0x180020346`
- `USER32!GetWindowLongPtrW` at `0x180020309`
- `USER32!GetWindowLongPtrW` at `0x180020309`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18002037c`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18002037c`

## pseudocode

```c
LRESULT __fastcall CTrayClock::s_WndProc(HWND a1, UINT Msg, WPARAM a3, unsigned __int16 *a4)
{
  LONG_PTR WindowLongPtrW; // rax
  CTrayClock *v9; // rcx
  DirectUI::Element *v11; // rcx
  CFlyout *Parent; // rax
  CFlyout *v13; // rbx
  int v14; // r8d
  unsigned __int16 *v15; // rdx

  WindowLongPtrW = GetWindowLongPtrW(a1, -21);
  switch ( Msg )
  {
    case 6u:
      if ( !a3 )
      {
        if ( WindowLongPtrW && !PostThreadMessageW(*(_DWORD *)(WindowLongPtrW + 68), 0x12u, 0, 0) )
          ResultFromKnownLastError();
        return 1;
      }
      return 0;
    case 0xDu:
      if ( !WindowLongPtrW )
        return 0;
      v14 = a3;
      v15 = a4;
      return CTrayClock::_GetAccName(v9, v15, v14, 0x140u);
    case 0xEu:
      if ( !WindowLongPtrW )
        return 0;
      v14 = 0;
      v15 = 0;
      return CTrayClock::_GetAccName(v9, v15, v14, 0x140u);
    case 0x402u:
      if ( WindowLongPtrW )
      {
        v11 = *(DirectUI::Element **)(WindowLongPtrW + 96);
        if ( v11 )
        {
          Parent = DirectUI::Element::GetParent(v11);
          v13 = Parent;
          if ( Parent )
          {
            CFlyout::ResetCalendar(Parent, 0);
            (*(void (__fastcall **)(CFlyout *))(*(_QWORD *)v13 + 488LL))(v13);
          }
        }
      }
      return 1;
  }
  if ( Msg != 1027 )
    return DefWindowProcW(a1, Msg, a3, (LPARAM)a4);
  if ( WindowLongPtrW )
  {
    CTrayClock::_MoveWnd((CTrayClock *)WindowLongPtrW, a1);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800202f0  push    rbx
0x1800202f2  push    rbp
0x1800202f3  push    rsi
0x1800202f4  push    rdi
0x1800202f5  sub     rsp, 28h
0x1800202f9  mov     ebp, edx
0x1800202fb  mov     rsi, r9
0x1800202fe  mov     edx, 0FFFFFFEBh; nIndex
0x180020303  mov     rbx, r8
0x180020306  mov     rdi, rcx
0x180020309  call    cs:__imp_GetWindowLongPtrW
0x18002030f  mov     r10d, ebp
0x180020312  sub     r10d, 6
0x180020316  jz      loc_1800203CE
0x18002031c  sub     r10d, 7
0x180020320  jz      loc_1800203B4
0x180020326  sub     r10d, 1
0x18002032a  jz      short loc_1800203A8
0x18002032c  sub     r10d, 3F4h
0x180020333  jz      short loc_18002036A
0x180020335  cmp     r10d, 1
0x180020339  jz      short loc_180020351
0x18002033b  mov     r9, rsi; lParam
0x18002033e  mov     r8, rbx; wParam
0x180020341  mov     edx, ebp; Msg
0x180020343  mov     rcx, rdi; hWnd
0x180020346  call    cs:__imp_DefWindowProcW
0x18002034c  jmp     loc_1800203FC
0x180020351  test    rax, rax
0x180020354  jz      loc_1800203FA
0x18002035a  mov     rdx, rdi; HWND
0x18002035d  mov     rcx, rax; this
0x180020360  call    ?_MoveWnd@CTrayClock@@AEAAJPEAUHWND__@@@Z; CTrayClock::_MoveWnd(HWND__ *)
0x180020365  jmp     loc_1800203F3
0x18002036a  test    rax, rax
0x18002036d  jz      loc_1800203F3
0x180020373  mov     rcx, [rax+60h]
0x180020377  test    rcx, rcx
0x18002037a  jz      short loc_1800203F3
0x18002037c  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x180020382  mov     rbx, rax
0x180020385  test    rax, rax
0x180020388  jz      short loc_1800203F3
0x18002038a  xor     edx, edx; int
0x18002038c  mov     rcx, rax; this
0x18002038f  call    ?ResetCalendar@CFlyout@@QEAAXH@Z; CFlyout::ResetCalendar(int)
0x180020394  mov     rcx, [rbx]
0x180020397  mov     rax, [rcx+1E8h]
0x18002039e  mov     rcx, rbx
0x1800203a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203a6  jmp     short loc_1800203F3
0x1800203a8  test    rax, rax
0x1800203ab  jz      short loc_1800203FA
0x1800203ad  xor     r8d, r8d
0x1800203b0  xor     edx, edx
0x1800203b2  jmp     short loc_1800203BF
0x1800203b4  test    rax, rax
0x1800203b7  jz      short loc_1800203FA
0x1800203b9  mov     r8d, ebx; int
0x1800203bc  mov     rdx, rsi; unsigned __int16 *
0x1800203bf  mov     r9d, 140h; unsigned int
0x1800203c5  call    ?_GetAccName@CTrayClock@@AEAAHPEAGHI@Z; CTrayClock::_GetAccName(ushort *,int,uint)
0x1800203ca  cdqe
0x1800203cc  jmp     short loc_1800203FC
0x1800203ce  test    rbx, rbx
0x1800203d1  jnz     short loc_1800203FA
0x1800203d3  test    rax, rax
0x1800203d6  jz      short loc_1800203F3
0x1800203d8  mov     ecx, [rax+44h]; idThread
0x1800203db  lea     edx, [rbx+12h]; Msg
0x1800203de  xor     r9d, r9d; lParam
0x1800203e1  xor     r8d, r8d; wParam
0x1800203e4  call    cs:__imp_PostThreadMessageW
0x1800203ea  test    eax, eax
0x1800203ec  jnz     short loc_1800203F3
0x1800203ee  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800203f3  mov     eax, 1
0x1800203f8  jmp     short loc_1800203FC
0x1800203fa  xor     eax, eax
0x1800203fc  add     rsp, 28h
0x180020400  pop     rdi
0x180020401  pop     rsi
0x180020402  pop     rbp
0x180020403  pop     rbx
0x180020404  retn
```
