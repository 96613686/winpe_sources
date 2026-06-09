# CDigitalClock::_InitializeSettings(void)

- ea: `0x1800222a8`
- end: `0x18002249b`
- name: `?_InitializeSettings@CDigitalClock@@AEAAXXZ`
- size: `499`
- prototype: `void __fastcall(CDigitalClock *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180021310`
- `0x180023070`

## callees

- `0x180020adc`
- `0x180020dd4`
- `0x180021d28`
- `0x180021ea4`
- `0x180022050`
- `0x180022114`
- `0x1800222a8`

## import_xrefs

- `USER32!UpdateWindow` at `0x18002247b`
- `USER32!UpdateWindow` at `0x18002247b`
- `USER32!SetWindowTextW` at `0x1800223b2`
- `USER32!SetWindowTextW` at `0x1800223c3`
- `USER32!SetWindowTextW` at `0x1800223b2`
- `USER32!SetWindowTextW` at `0x1800223c3`
- `USER32!InvalidateRect` at `0x180022472`
- `USER32!InvalidateRect` at `0x180022472`
- `USER32!SendMessageW` at `0x1800223eb`
- `USER32!SendMessageW` at `0x18002241d`
- `USER32!SendMessageW` at `0x180022433`
- `USER32!SendMessageW` at `0x1800223eb`
- `USER32!SendMessageW` at `0x18002241d`
- `USER32!SendMessageW` at `0x180022433`

## pseudocode

```c
void __fastcall CDigitalClock::_InitializeSettings(CDigitalClock *this)
{
  int v1; // edi
  int v3; // eax
  int v4; // ebp
  int v5; // esi
  int v6; // ecx
  int v7; // eax
  int *v8; // rdi
  int v9; // ecx
  HWND v10; // rcx
  LPARAM lParam; // [rsp+20h] [rbp-28h] BYREF
  int v12; // [rsp+28h] [rbp-20h]
  int v13; // [rsp+2Ch] [rbp-1Ch]
  struct HWND__ v14; // [rsp+50h] [rbp+8h] BYREF
  int v15; // [rsp+54h] [rbp+Ch]

  v1 = 0;
  *((_QWORD *)this + 17) = 0;
  *((_DWORD *)this + 24) = 1;
  if ( !CDigitalClock::_s_Settings )
  {
    v1 = 1;
    CDigitalClock::_InitializeCommonSettings(this);
  }
  if ( !*((_DWORD *)this + 22) )
  {
    CDigitalClock::_AdjustAMPMPosition(this);
    v3 = *((_DWORD *)this + 43);
    *((_DWORD *)this + 40) = *((_DWORD *)this + 42) + 1 + *((_DWORD *)this + 48);
    *((_DWORD *)this + 41) = v3;
    if ( v1 )
    {
      v4 = 0;
      v5 = 0;
      if ( *((_DWORD *)this + 50) )
      {
        v6 = *(_DWORD *)CDigitalClock::_GetAMPMSize(this).cx;
        v7 = *((_DWORD *)this + 46);
        if ( v6 != v7 )
        {
          *((_DWORD *)this + 46) = v6;
          v5 = v6 - v7;
        }
      }
      v8 = (int *)((char *)this + 176);
      if ( dword_18003A9F4 || (v9 = *v8, *((_DWORD *)this + 26)) )
      {
        *((_DWORD *)this + 26) = dword_18003A9F4;
        CDigitalClock::_GetMaxNumSize(this, &v14);
        v9 = 2 * v14.unused + 3;
        *((_DWORD *)this + 45) = v15;
      }
      if ( v9 != *v8 )
      {
        v4 = v9 - *v8;
        *v8 = v9;
LABEL_14:
        CDigitalClock::_ArrangeClockItems(this, v4, v5);
        goto LABEL_15;
      }
      if ( v5 )
        goto LABEL_14;
    }
LABEL_15:
    SetWindowTextW(*((HWND *)this + 6), &word_18003A9C0);
    SetWindowTextW(*((HWND *)this + 7), &word_18003A9C0);
    SendMessageW(
      *((HWND *)this + 9),
      0x465u,
      0,
      (unsigned __int16)qword_18003A9C8 | ((unsigned __int64)WORD2(qword_18003A9C8) << 16));
    v10 = (HWND)*((_QWORD *)this + 9);
    lParam = 0x100000000LL;
    v12 = 2;
    v13 = 1;
    SendMessageW(v10, 0x46Bu, 2u, (LPARAM)&lParam);
    SendMessageW(*((HWND *)this + 9), 0x469u, *((_QWORD *)this + 3), 0);
    CDigitalClock::_DrawItem(this, 0, 1, 0);
    CDigitalClock::_DrawItem(this, 1, 1, 0);
    CDigitalClock::_DrawItem(this, 2, 1, 0);
    InvalidateRect(*(HWND *)this, 0, 1);
    UpdateWindow(*(HWND *)this);
  }
  *((_DWORD *)this + 34) = 1;
}

```

## disassembly

```asm
0x1800222a8  mov     [rsp+arg_8], rbx
0x1800222ad  mov     [rsp+arg_10], rbp
0x1800222b2  push    rsi
0x1800222b3  push    rdi
0x1800222b4  push    r15
0x1800222b6  sub     rsp, 30h
0x1800222ba  xor     edi, edi
0x1800222bc  mov     rbx, rcx
0x1800222bf  mov     [rcx+88h], rdi
0x1800222c6  lea     r15d, [rdi+1]
0x1800222ca  mov     [rcx+60h], r15d
0x1800222ce  cmp     cs:?_s_Settings@CDigitalClock@@0UDIGITALCLOCKCOMMONSETTINGS@@A, edi; DIGITALCLOCKCOMMONSETTINGS CDigitalClock::_s_Settings
0x1800222d4  jnz     short loc_1800222DE
0x1800222d6  mov     edi, r15d
0x1800222d9  call    ?_InitializeCommonSettings@CDigitalClock@@AEAAXXZ; CDigitalClock::_InitializeCommonSettings(void)
0x1800222de  cmp     dword ptr [rbx+58h], 0
0x1800222e2  jnz     loc_180022481
0x1800222e8  mov     rcx, rbx; this
0x1800222eb  call    ?_AdjustAMPMPosition@CDigitalClock@@AEAAXXZ; CDigitalClock::_AdjustAMPMPosition(void)
0x1800222f0  mov     eax, [rbx+0A8h]
0x1800222f6  mov     ecx, [rbx+0C0h]
0x1800222fc  inc     eax
0x1800222fe  add     ecx, eax
0x180022300  mov     eax, [rbx+0ACh]
0x180022306  mov     [rbx+0A0h], ecx
0x18002230c  mov     [rbx+0A4h], eax
0x180022312  test    edi, edi
0x180022314  jz      loc_1800223A7
0x18002231a  xor     ebp, ebp
0x18002231c  xor     esi, esi
0x18002231e  cmp     [rbx+0C8h], esi
0x180022324  jz      short loc_180022349
0x180022326  lea     rdx, [rsp+48h+arg_0]
0x18002232b  mov     rcx, rbx; this
0x18002232e  call    ?_GetAMPMSize@CDigitalClock@@AEAA?AUtagSIZE@@XZ; CDigitalClock::_GetAMPMSize(void)
0x180022333  mov     ecx, [rax]
0x180022335  mov     eax, [rbx+0B8h]
0x18002233b  cmp     ecx, eax
0x18002233d  jz      short loc_180022349
0x18002233f  mov     esi, ecx
0x180022341  mov     [rbx+0B8h], ecx
0x180022347  sub     esi, eax
0x180022349  mov     eax, cs:dword_18003A9F4
0x18002234f  lea     rdi, [rbx+0B0h]
0x180022356  test    eax, eax
0x180022358  jnz     short loc_180022361
0x18002235a  mov     ecx, [rdi]
0x18002235c  cmp     [rbx+68h], ebp
0x18002235f  jz      short loc_18002238A
0x180022361  mov     r8, [rbx+18h]
0x180022365  lea     rdx, [rsp+48h+arg_0]; HWND
0x18002236a  mov     rcx, rbx; this
0x18002236d  mov     [rbx+68h], eax
0x180022370  call    ?_GetMaxNumSize@CDigitalClock@@AEAA?AUtagSIZE@@PEAUHWND__@@@Z; CDigitalClock::_GetMaxNumSize(HWND__ *)
0x180022375  mov     eax, [rsp+48h+arg_0.unused]
0x180022379  lea     ecx, ds:3[rax*2]
0x180022380  mov     eax, [rsp+48h+arg_4]
0x180022384  mov     [rbx+0B4h], eax
0x18002238a  cmp     ecx, [rdi]
0x18002238c  jz      short loc_180022396
0x18002238e  mov     ebp, ecx
0x180022390  sub     ebp, [rdi]
0x180022392  mov     [rdi], ecx
0x180022394  jnz     short loc_18002239A
0x180022396  test    esi, esi
0x180022398  jz      short loc_1800223A7
0x18002239a  mov     r8d, esi; int
0x18002239d  mov     edx, ebp; int
0x18002239f  mov     rcx, rbx; this
0x1800223a2  call    ?_ArrangeClockItems@CDigitalClock@@AEAAXHH@Z; CDigitalClock::_ArrangeClockItems(int,int)
0x1800223a7  mov     rcx, [rbx+30h]; hWnd
0x1800223ab  lea     rdx, word_18003A9C0; lpString
0x1800223b2  call    cs:__imp_SetWindowTextW
0x1800223b8  mov     rcx, [rbx+38h]; hWnd
0x1800223bc  lea     rdx, word_18003A9C0; lpString
0x1800223c3  call    cs:__imp_SetWindowTextW
0x1800223c9  movzx   r9d, word ptr cs:qword_18003A9C8+4
0x1800223d1  xor     r8d, r8d; wParam
0x1800223d4  movzx   eax, word ptr cs:qword_18003A9C8
0x1800223db  mov     edx, 465h; Msg
0x1800223e0  mov     rcx, [rbx+48h]; hWnd
0x1800223e4  shl     r9, 10h
0x1800223e8  or      r9, rax; lParam
0x1800223eb  call    cs:__imp_SendMessageW
0x1800223f1  mov     rcx, [rbx+48h]; hWnd
0x1800223f5  lea     r9, [rsp+48h+lParam]; lParam
0x1800223fa  mov     edi, 2
0x1800223ff  mov     dword ptr [rsp+48h+lParam], 0
0x180022407  mov     r8d, edi; wParam
0x18002240a  mov     dword ptr [rsp+48h+lParam+4], r15d
0x18002240f  mov     edx, 46Bh; Msg
0x180022414  mov     [rsp+48h+var_20], edi
0x180022418  mov     [rsp+48h+var_1C], r15d
0x18002241d  call    cs:__imp_SendMessageW
0x180022423  mov     r8, [rbx+18h]; wParam
0x180022427  xor     r9d, r9d; lParam
0x18002242a  mov     rcx, [rbx+48h]; hWnd
0x18002242e  mov     edx, 469h; Msg
0x180022433  call    cs:__imp_SendMessageW
0x180022439  xor     r9d, r9d; int
0x18002243c  mov     r8d, r15d; int
0x18002243f  xor     edx, edx; int
0x180022441  mov     rcx, rbx; this
0x180022444  call    ?_DrawItem@CDigitalClock@@AEAAXHHH@Z; CDigitalClock::_DrawItem(int,int,int)
0x180022449  xor     r9d, r9d; int
0x18002244c  mov     r8d, r15d; int
0x18002244f  mov     edx, r15d; int
0x180022452  mov     rcx, rbx; this
0x180022455  call    ?_DrawItem@CDigitalClock@@AEAAXHHH@Z; CDigitalClock::_DrawItem(int,int,int)
0x18002245a  xor     r9d, r9d; int
0x18002245d  mov     r8d, r15d; int
0x180022460  mov     edx, edi; int
0x180022462  mov     rcx, rbx; this
0x180022465  call    ?_DrawItem@CDigitalClock@@AEAAXHHH@Z; CDigitalClock::_DrawItem(int,int,int)
0x18002246a  mov     rcx, [rbx]; hWnd
0x18002246d  mov     r8d, r15d; bErase
0x180022470  xor     edx, edx; lpRect
0x180022472  call    cs:__imp_InvalidateRect
0x180022478  mov     rcx, [rbx]; hWnd
0x18002247b  call    cs:__imp_UpdateWindow
0x180022481  mov     rbp, [rsp+48h+arg_10]
0x180022486  mov     [rbx+88h], r15d
0x18002248d  mov     rbx, [rsp+48h+arg_8]
0x180022492  add     rsp, 30h
0x180022496  pop     r15
0x180022498  pop     rdi
0x180022499  pop     rsi
0x18002249a  retn
```
