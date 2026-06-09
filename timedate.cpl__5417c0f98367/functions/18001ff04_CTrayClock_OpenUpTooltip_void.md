# CTrayClock::_OpenUpTooltip(void)

- ea: `0x18001ff04`
- end: `0x18002008c`
- name: `?_OpenUpTooltip@CTrayClock@@AEAAJXZ`
- size: `392`
- prototype: `__int64 __fastcall(CTrayClock *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001f360`

## callees

- `0x180014db0`
- `0x18001f3f4`
- `0x18001f48c`
- `0x18001fae0`
- `0x18001ff04`
- `0x180020094`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x180020054`
- `USER32!SystemParametersInfoW` at `0x180020054`
- `USER32!SetWindowLongPtrW` at `0x18001ffbc`
- `USER32!SetWindowLongPtrW` at `0x18001ffbc`
- `USER32!ShowWindow` at `0x18001ffe5`
- `USER32!ShowWindow` at `0x18001ffe5`
- `USER32!SetTimer` at `0x180020006`
- `USER32!SetTimer` at `0x180020084`
- `USER32!SetTimer` at `0x180020006`
- `USER32!SetTimer` at `0x180020084`
- `USER32!CreateWindowInBand` at `0x18001ff6b`
- `USER32!CreateWindowInBand` at `0x18001ff6b`
- `UxTheme!OpenThemeData` at `0x18001ffa6`
- `UxTheme!OpenThemeData` at `0x18001ffa6`

## pseudocode

```c
__int64 __fastcall CTrayClock::_OpenUpTooltip(CTrayClock *this)
{
  HWND WindowInBand; // rax
  HWND v3; // rsi
  int Tree; // eax
  int v6; // edi
  HTHEME v7; // rax
  HWND v8; // rcx
  int v9; // eax
  int pvParam; // [rsp+80h] [rbp+8h] BYREF

  WindowInBand = (HWND)CreateWindowInBand(
                         128,
                         L"ClockTooltipWindow",
                         0,
                         0x80000000LL,
                         0x80000000,
                         0x80000000,
                         0x80000000,
                         0x80000000,
                         0,
                         0,
                         g_hInst,
                         0,
                         *((_DWORD *)this + 16));
  v3 = WindowInBand;
  if ( !WindowInBand )
    return ResultFromLastError();
  Tree = CTrayClock::_CreateTree(this, WindowInBand);
  *((_QWORD *)this + 3) = v3;
  v6 = Tree;
  if ( Tree >= 0 )
  {
    v7 = OpenThemeData(v3, L"Tooltip");
    v8 = (HWND)*((_QWORD *)this + 3);
    *((_QWORD *)this + 5) = v7;
    SetWindowLongPtrW(v8, -21, (LONG_PTR)this);
    CTrayClock::_SetWindowRegion(this);
    v6 = CTrayClock::_MoveWnd(this, *((HWND *)this + 3));
    if ( v6 >= 0 )
    {
      ShowWindow(*((HWND *)this + 3), 4);
      if ( uIDEvent || (uIDEvent = SetTimer(0, 0, 0xFAu, ClockSyncTimerProc)) != 0 )
      {
        v6 = 0;
        pvParam = 0;
        if ( SystemParametersInfoW(0x2016u, 0, &pvParam, 0) )
        {
          v9 = pvParam;
        }
        else
        {
          v9 = 10;
          pvParam = 10;
        }
        SetTimer(*((HWND *)this + 3), 0xCBu, 1000 * v9, 0);
        return (unsigned int)v6;
      }
      v6 = -2147467259;
    }
  }
  CTrayClock::_CloseUpTooltip(this);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001ff04  mov     r11, rsp
0x18001ff07  mov     [r11+10h], rbx
0x18001ff0b  mov     [r11+18h], rsi
0x18001ff0f  push    rdi
0x18001ff10  sub     rsp, 70h
0x18001ff14  mov     eax, [rcx+40h]
0x18001ff17  lea     rdx, aClocktooltipwi; "ClockTooltipWindow"
0x18001ff1e  mov     [rsp+78h+var_18], eax
0x18001ff22  mov     rbx, rcx
0x18001ff25  mov     rax, cs:g_hInst
0x18001ff2c  mov     r9d, 80000000h
0x18001ff32  mov     qword ptr [r11-20h], 0
0x18001ff3a  xor     r8d, r8d
0x18001ff3d  mov     [r11-28h], rax
0x18001ff41  mov     ecx, 80h
0x18001ff46  mov     qword ptr [r11-30h], 0
0x18001ff4e  mov     eax, 80000000h
0x18001ff53  mov     qword ptr [r11-38h], 0
0x18001ff5b  mov     [rsp+78h+var_40], eax
0x18001ff5f  mov     [rsp+78h+var_48], eax
0x18001ff63  mov     [rsp+78h+var_50], eax
0x18001ff67  mov     [rsp+78h+var_58], eax
0x18001ff6b  call    cs:__imp_CreateWindowInBand
0x18001ff71  mov     rsi, rax
0x18001ff74  test    rax, rax
0x18001ff77  jnz     short loc_18001FF83
0x18001ff79  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001ff7e  jmp     loc_180020027
0x18001ff83  mov     rdx, rsi; HWND
0x18001ff86  mov     rcx, rbx; this
0x18001ff89  call    ?_CreateTree@CTrayClock@@AEAAJPEAUHWND__@@@Z; CTrayClock::_CreateTree(HWND__ *)
0x18001ff8e  mov     [rbx+18h], rsi
0x18001ff92  mov     edi, eax
0x18001ff94  test    eax, eax
0x18001ff96  js      loc_18002001D
0x18001ff9c  lea     rdx, pszClassList; "Tooltip"
0x18001ffa3  mov     rcx, rsi; hwnd
0x18001ffa6  call    cs:__imp_OpenThemeData
0x18001ffac  mov     rcx, [rbx+18h]; hWnd
0x18001ffb0  mov     r8, rbx; dwNewLong
0x18001ffb3  mov     edx, 0FFFFFFEBh; nIndex
0x18001ffb8  mov     [rbx+28h], rax
0x18001ffbc  call    cs:__imp_SetWindowLongPtrW
0x18001ffc2  mov     rcx, rbx; this
0x18001ffc5  call    ?_SetWindowRegion@CTrayClock@@AEAAJXZ; CTrayClock::_SetWindowRegion(void)
0x18001ffca  mov     rdx, [rbx+18h]; HWND
0x18001ffce  mov     rcx, rbx; this
0x18001ffd1  call    ?_MoveWnd@CTrayClock@@AEAAJPEAUHWND__@@@Z; CTrayClock::_MoveWnd(HWND__ *)
0x18001ffd6  mov     edi, eax
0x18001ffd8  test    eax, eax
0x18001ffda  js      short loc_18002001D
0x18001ffdc  mov     rcx, [rbx+18h]; hWnd
0x18001ffe0  mov     edx, 4; nCmdShow
0x18001ffe5  call    cs:__imp_ShowWindow
0x18001ffeb  cmp     cs:uIDEvent, 0
0x18001fff3  jnz     short loc_180020039
0x18001fff5  lea     r9, ?ClockSyncTimerProc@@YAXPEAUHWND__@@I_KK@Z; lpTimerFunc
0x18001fffc  xor     edx, edx; nIDEvent
0x18001fffe  xor     ecx, ecx; hWnd
0x180020000  mov     r8d, 0FAh; uElapse
0x180020006  call    cs:__imp_SetTimer
0x18002000c  mov     cs:uIDEvent, rax
0x180020013  test    rax, rax
0x180020016  jnz     short loc_180020039
0x180020018  mov     edi, 80004005h
0x18002001d  mov     rcx, rbx; this
0x180020020  call    ?_CloseUpTooltip@CTrayClock@@AEAAJXZ; CTrayClock::_CloseUpTooltip(void)
0x180020025  mov     eax, edi
0x180020027  lea     r11, [rsp+78h+var_8]
0x18002002c  mov     rbx, [r11+18h]
0x180020030  mov     rsi, [r11+20h]
0x180020034  mov     rsp, r11
0x180020037  pop     rdi
0x180020038  retn
0x180020039  xor     edi, edi
0x18002003b  lea     r8, [rsp+78h+pvParam]; pvParam
0x180020043  xor     r9d, r9d; fWinIni
0x180020046  mov     [rsp+78h+pvParam], edi
0x18002004d  xor     edx, edx; uiParam
0x18002004f  mov     ecx, 2016h; uiAction
0x180020054  call    cs:__imp_SystemParametersInfoW
0x18002005a  test    eax, eax
0x18002005c  jnz     short loc_18002006A
0x18002005e  lea     eax, [rdi+0Ah]
0x180020061  mov     [rsp+78h+pvParam], eax
0x180020068  jmp     short loc_180020071
0x18002006a  mov     eax, [rsp+78h+pvParam]
0x180020071  mov     rcx, [rbx+18h]; hWnd
0x180020075  xor     r9d, r9d; lpTimerFunc
0x180020078  imul    r8d, eax, 3E8h; uElapse
0x18002007f  mov     edx, 0CBh; nIDEvent
0x180020084  call    cs:__imp_SetTimer
0x18002008a  jmp     short loc_180020025
```
