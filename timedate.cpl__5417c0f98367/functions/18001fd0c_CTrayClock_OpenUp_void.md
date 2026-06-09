# CTrayClock::_OpenUp(void)

- ea: `0x18001fd0c`
- end: `0x18001fefb`
- name: `?_OpenUp@CTrayClock@@AEAAJXZ`
- size: `495`
- prototype: `__int64 __fastcall(CTrayClock *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180020150`

## callees

- `0x180004368`
- `0x18000ed64`
- `0x18000f32c`
- `0x18001263c`
- `0x180014db0`
- `0x18001f48c`
- `0x18001fae0`
- `0x18001fd0c`

## import_xrefs

- `dwmapi!DwmSetWindowAttribute` at `0x18001fe56`
- `dwmapi!DwmSetWindowAttribute` at `0x18001fe56`
- `dwmapi!DwmIsCompositionEnabled` at `0x18001fe2b`
- `dwmapi!DwmIsCompositionEnabled` at `0x18001fe2b`
- `USER32!SetForegroundWindow` at `0x18001fe9a`
- `USER32!SetForegroundWindow` at `0x18001fe9a`
- `USER32!DestroyWindow` at `0x18001fdd3`
- `USER32!DestroyWindow` at `0x18001fdd3`
- `USER32!SetWindowLongPtrW` at `0x18001fe6f`
- `USER32!SetWindowLongPtrW` at `0x18001fe6f`
- `USER32!ShowWindow` at `0x18001fe90`
- `USER32!ShowWindow` at `0x18001fe90`
- `USER32!SetTimer` at `0x18001febb`
- `USER32!SetTimer` at `0x18001febb`
- `USER32!CreateWindowInBand` at `0x18001fd8c`
- `USER32!CreateWindowInBand` at `0x18001fd8c`

## pseudocode

```c
__int64 __fastcall CTrayClock::_OpenUp(CTrayClock *this)
{
  __int64 WindowInBand; // rax
  __int64 v3; // rcx
  __int64 v4; // r8
  HWND Window; // rsi
  HWND v6; // rcx
  int v8; // edi
  unsigned int ExtraTzCount; // eax
  int Tree; // eax
  _DWORD *v11; // rdi
  HWND v12; // rcx
  int pvAttribute; // [rsp+80h] [rbp+8h] BYREF

  DateTimeEventWrite(&DATETIME_PERFTRACK_DISPLAYCLOCKFLYOUT_START, 0, 0);
  WindowInBand = CreateWindowInBand(0, L"ClockFlyoutWindow", 0, 0, 0, 0, 0, 0, 0, 0, g_hInst, 0, *((_DWORD *)this + 16));
  *((_QWORD *)this + 4) = WindowInBand;
  Window = (HWND)IsolationAwareCreateWindowExW(
                   v3,
                   L"ClockFlyoutWindow",
                   v4,
                   2155872256LL,
                   0x80000000,
                   0x80000000,
                   0x80000000,
                   0x80000000,
                   WindowInBand);
  if ( Window )
  {
    v8 = -2147024882;
    ExtraTzCount = GetExtraTzCount();
    if ( (unsigned int)InitialiseClockSync(2 * ExtraTzCount + 2) )
    {
      Tree = CTrayClock::_CreateTree(this, Window);
      *((_QWORD *)this + 2) = Window;
      v8 = Tree;
      if ( Tree >= 0 )
      {
        v11 = (_DWORD *)((char *)this + 80);
        *((_DWORD *)this + 20) = 0;
        if ( DwmIsCompositionEnabled((BOOL *)this + 20) >= 0 && *v11 )
        {
          v12 = (HWND)*((_QWORD *)this + 2);
          pvAttribute = 2;
          *v11 = DwmSetWindowAttribute(v12, 2u, &pvAttribute, 4u) >= 0;
        }
        SetWindowLongPtrW(*((HWND *)this + 2), -21, (LONG_PTR)this);
        v8 = CTrayClock::_MoveWnd(this, *((HWND *)this + 2));
        if ( v8 >= 0 )
        {
          ShowWindow(*((HWND *)this + 2), 1);
          SetForegroundWindow(*((HWND *)this + 2));
          if ( uIDEvent || (uIDEvent = SetTimer(0, 0, 0xFAu, ClockSyncTimerProc)) != 0 )
            v8 = 0;
          else
            v8 = -2147467259;
        }
      }
    }
    DateTimeEventWrite(&DATETIME_PERFTRACK_DISPLAYCLOCKFLYOUT_STOP, 0, 0);
    return (unsigned int)v8;
  }
  else
  {
    v6 = (HWND)*((_QWORD *)this + 4);
    if ( v6 )
    {
      DestroyWindow(v6);
      *((_QWORD *)this + 4) = 0;
    }
    return ResultFromLastError();
  }
}

```

## disassembly

```asm
0x18001fd0c  mov     [rsp+arg_8], rbx
0x18001fd11  mov     [rsp+arg_10], rsi
0x18001fd16  push    rdi
0x18001fd17  sub     rsp, 70h
0x18001fd1b  mov     rbx, rcx
0x18001fd1e  xor     r8d, r8d; struct _EVENT_DATA_DESCRIPTOR *
0x18001fd21  lea     rcx, DATETIME_PERFTRACK_DISPLAYCLOCKFLYOUT_START; struct _EVENT_DESCRIPTOR *
0x18001fd28  xor     edx, edx; unsigned int
0x18001fd2a  call    ?DateTimeEventWrite@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; DateTimeEventWrite(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18001fd2f  mov     eax, [rbx+40h]
0x18001fd32  lea     rdx, aClockflyoutwin; "ClockFlyoutWindow"
0x18001fd39  mov     [rsp+78h+var_18], eax
0x18001fd3d  xor     r9d, r9d
0x18001fd40  mov     rax, cs:g_hInst
0x18001fd47  xor     r8d, r8d
0x18001fd4a  mov     [rsp+78h+var_20], 0
0x18001fd53  xor     ecx, ecx
0x18001fd55  mov     [rsp+78h+var_28], rax
0x18001fd5a  mov     [rsp+78h+var_30], 0
0x18001fd63  mov     [rsp+78h+var_38], 0
0x18001fd6c  mov     [rsp+78h+var_40], 0
0x18001fd74  mov     [rsp+78h+var_48], 0
0x18001fd7c  mov     [rsp+78h+var_50], 0
0x18001fd84  mov     [rsp+78h+var_58], 0
0x18001fd8c  call    cs:__imp_CreateWindowInBand
0x18001fd92  mov     [rsp+78h+var_38], rax
0x18001fd97  mov     r9d, 80800000h
0x18001fd9d  mov     [rbx+20h], rax
0x18001fda1  lea     rdx, aClockflyoutwin; "ClockFlyoutWindow"
0x18001fda8  mov     eax, 80000000h
0x18001fdad  mov     [rsp+78h+var_40], eax
0x18001fdb1  mov     [rsp+78h+var_48], eax
0x18001fdb5  mov     [rsp+78h+var_50], eax
0x18001fdb9  mov     [rsp+78h+var_58], eax
0x18001fdbd  call    IsolationAwareCreateWindowExW
0x18001fdc2  mov     rsi, rax
0x18001fdc5  test    rax, rax
0x18001fdc8  jnz     short loc_18001FDE7
0x18001fdca  mov     rcx, [rbx+20h]; hWnd
0x18001fdce  test    rcx, rcx
0x18001fdd1  jz      short loc_18001FDDD
0x18001fdd3  call    cs:__imp_DestroyWindow
0x18001fdd9  mov     [rbx+20h], rsi
0x18001fddd  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001fde2  jmp     loc_18001FEE9
0x18001fde7  mov     edi, 8007000Eh
0x18001fdec  call    ?GetExtraTzCount@@YAIXZ; GetExtraTzCount(void)
0x18001fdf1  lea     ecx, ds:2[rax*2]; unsigned int
0x18001fdf8  call    ?InitialiseClockSync@@YAHI@Z; InitialiseClockSync(uint)
0x18001fdfd  test    eax, eax
0x18001fdff  jz      loc_18001FED6
0x18001fe05  mov     rdx, rsi; HWND
0x18001fe08  mov     rcx, rbx; this
0x18001fe0b  call    ?_CreateTree@CTrayClock@@AEAAJPEAUHWND__@@@Z; CTrayClock::_CreateTree(HWND__ *)
0x18001fe10  mov     [rbx+10h], rsi
0x18001fe14  mov     edi, eax
0x18001fe16  test    eax, eax
0x18001fe18  js      loc_18001FED6
0x18001fe1e  lea     rdi, [rbx+50h]
0x18001fe22  mov     rcx, rdi; pfEnabled
0x18001fe25  mov     dword ptr [rdi], 0
0x18001fe2b  call    cs:__imp_DwmIsCompositionEnabled
0x18001fe31  test    eax, eax
0x18001fe33  js      short loc_18001FE63
0x18001fe35  cmp     dword ptr [rdi], 0
0x18001fe38  jz      short loc_18001FE63
0x18001fe3a  mov     rcx, [rbx+10h]; hwnd
0x18001fe3e  lea     r8, [rsp+78h+pvAttribute]; pvAttribute
0x18001fe46  mov     edx, 2; dwAttribute
0x18001fe4b  mov     [rsp+78h+pvAttribute], edx
0x18001fe52  lea     r9d, [rdx+2]; cbAttribute
0x18001fe56  call    cs:__imp_DwmSetWindowAttribute
0x18001fe5c  not     eax
0x18001fe5e  shr     eax, 1Fh
0x18001fe61  mov     [rdi], eax
0x18001fe63  mov     rcx, [rbx+10h]; hWnd
0x18001fe67  mov     r8, rbx; dwNewLong
0x18001fe6a  mov     edx, 0FFFFFFEBh; nIndex
0x18001fe6f  call    cs:__imp_SetWindowLongPtrW
0x18001fe75  mov     rdx, [rbx+10h]; HWND
0x18001fe79  mov     rcx, rbx; this
0x18001fe7c  call    ?_MoveWnd@CTrayClock@@AEAAJPEAUHWND__@@@Z; CTrayClock::_MoveWnd(HWND__ *)
0x18001fe81  mov     edi, eax
0x18001fe83  test    eax, eax
0x18001fe85  js      short loc_18001FED6
0x18001fe87  mov     rcx, [rbx+10h]; hWnd
0x18001fe8b  mov     edx, 1; nCmdShow
0x18001fe90  call    cs:__imp_ShowWindow
0x18001fe96  mov     rcx, [rbx+10h]; hWnd
0x18001fe9a  call    cs:__imp_SetForegroundWindow
0x18001fea0  cmp     cs:uIDEvent, 0
0x18001fea8  jnz     short loc_18001FED4
0x18001feaa  lea     r9, ?ClockSyncTimerProc@@YAXPEAUHWND__@@I_KK@Z; lpTimerFunc
0x18001feb1  xor     edx, edx; nIDEvent
0x18001feb3  xor     ecx, ecx; hWnd
0x18001feb5  mov     r8d, 0FAh; uElapse
0x18001febb  call    cs:__imp_SetTimer
0x18001fec1  mov     cs:uIDEvent, rax
0x18001fec8  test    rax, rax
0x18001fecb  jnz     short loc_18001FED4
0x18001fecd  mov     edi, 80004005h
0x18001fed2  jmp     short loc_18001FED6
0x18001fed4  xor     edi, edi
0x18001fed6  xor     r8d, r8d; struct _EVENT_DATA_DESCRIPTOR *
0x18001fed9  lea     rcx, DATETIME_PERFTRACK_DISPLAYCLOCKFLYOUT_STOP; struct _EVENT_DESCRIPTOR *
0x18001fee0  xor     edx, edx; unsigned int
0x18001fee2  call    ?DateTimeEventWrite@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; DateTimeEventWrite(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18001fee7  mov     eax, edi
0x18001fee9  lea     r11, [rsp+78h+var_8]
0x18001feee  mov     rbx, [r11+18h]
0x18001fef2  mov     rsi, [r11+20h]
0x18001fef6  mov     rsp, r11
0x18001fef9  pop     rdi
0x18001fefa  retn
```
