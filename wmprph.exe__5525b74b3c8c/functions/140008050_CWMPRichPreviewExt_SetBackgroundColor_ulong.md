# CWMPRichPreviewExt::SetBackgroundColor(ulong)

- ea: `0x140008050`
- end: `0x140008116`
- name: `?SetBackgroundColor@CWMPRichPreviewExt@@UEAAJK@Z`
- size: `198`
- prototype: `__int64 __fastcall(CWMPRichPreviewExt *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140008050`
- `0x1400099e0`
- `0x140009a08`

## import_xrefs

- `GDI32!DeleteObject` at `0x1400080a0`
- `GDI32!DeleteObject` at `0x1400080a0`
- `GDI32!CreateSolidBrush` at `0x1400080b1`
- `GDI32!CreateSolidBrush` at `0x1400080b1`
- `USER32!SetClassLongPtrW` at `0x1400080d1`
- `USER32!SetClassLongPtrW` at `0x1400080d1`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewExt::SetBackgroundColor(CWMPRichPreviewExt *this, unsigned int a2, __int64 a3)
{
  void *v5; // rcx
  HBRUSH SolidBrush; // rax
  HWND v7; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, a3, a2);
  }
  v5 = (void *)*((_QWORD *)this + 15);
  *((_DWORD *)this + 12) = a2;
  if ( v5 )
  {
    DeleteObject(v5);
    *((_QWORD *)this + 15) = 0;
  }
  SolidBrush = CreateSolidBrush(*((_DWORD *)this + 12));
  v7 = (HWND)*((_QWORD *)this + 9);
  *((_QWORD *)this + 15) = SolidBrush;
  if ( v7 && SolidBrush )
    SetClassLongPtrW(v7, -10, (LONG_PTR)SolidBrush);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_a1620705688d36e506283508f1a041e6_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140008050  mov     [rsp+arg_0], rbx
0x140008055  mov     [rsp+arg_8], rsi
0x14000805a  push    rdi
0x14000805b  sub     rsp, 20h
0x14000805f  mov     edi, edx
0x140008061  mov     rbx, rcx
0x140008064  mov     rcx, cs:WPP_GLOBAL_Control
0x14000806b  lea     rsi, WPP_GLOBAL_Control
0x140008072  cmp     rcx, rsi
0x140008075  jz      short loc_140008094
0x140008077  test    byte ptr [rcx+1Ch], 1
0x14000807b  jz      short loc_140008094
0x14000807d  cmp     byte ptr [rcx+19h], 5
0x140008081  jb      short loc_140008094
0x140008083  mov     rcx, [rcx+10h]
0x140008087  mov     edx, 20h ; ' '
0x14000808c  mov     r9d, edi
0x14000808f  call    WPP_SF_D
0x140008094  mov     rcx, [rbx+78h]; ho
0x140008098  mov     [rbx+30h], edi
0x14000809b  test    rcx, rcx
0x14000809e  jz      short loc_1400080AE
0x1400080a0  call    cs:__imp_DeleteObject
0x1400080a6  mov     qword ptr [rbx+78h], 0
0x1400080ae  mov     ecx, [rbx+30h]; color
0x1400080b1  call    cs:__imp_CreateSolidBrush
0x1400080b7  mov     rcx, [rbx+48h]; hWnd
0x1400080bb  mov     [rbx+78h], rax
0x1400080bf  test    rcx, rcx
0x1400080c2  jz      short loc_1400080D7
0x1400080c4  test    rax, rax
0x1400080c7  jz      short loc_1400080D7
0x1400080c9  mov     r8, rax; dwNewLong
0x1400080cc  mov     edx, 0FFFFFFF6h; nIndex
0x1400080d1  call    cs:__imp_SetClassLongPtrW
0x1400080d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400080de  cmp     rcx, rsi
0x1400080e1  jz      short loc_140008104
0x1400080e3  test    byte ptr [rcx+1Ch], 1
0x1400080e7  jz      short loc_140008104
0x1400080e9  cmp     byte ptr [rcx+19h], 5
0x1400080ed  jb      short loc_140008104
0x1400080ef  mov     rcx, [rcx+10h]
0x1400080f3  lea     r8, WPP_a1620705688d36e506283508f1a041e6_Traceguids
0x1400080fa  mov     edx, 21h ; '!'
0x1400080ff  call    WPP_SF_
0x140008104  mov     rbx, [rsp+28h+arg_0]
0x140008109  xor     eax, eax
0x14000810b  mov     rsi, [rsp+28h+arg_8]
0x140008110  add     rsp, 20h
0x140008114  pop     rdi
0x140008115  retn
```
