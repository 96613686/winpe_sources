# CMsgrWndBase::DestroyMsgrWindow(void)

- ea: `0x180030d10`
- end: `0x180031074`
- name: `?DestroyMsgrWindow@CMsgrWndBase@@UEAAHXZ`
- size: `868`
- prototype: `__int64 __fastcall(CMsgrWndBase *__hidden this)`
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023c34`
- `0x180030488`
- `0x1800339ac`
- `0x18005097c`
- `0x180060518`
- `0x180063954`

## callees

- `0x180001afc`
- `0x180002038`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001349c`
- `0x18001c06c`
- `0x18002f808`
- `0x18003058c`
- `0x180030d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030fc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030fc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030e1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030e1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180030dae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180030dae`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x180030d6d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x180030d6d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180030da6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180030da6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180030e66`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180030f8e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180030e66`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180030f8e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageTimeoutW` at `0x180030e98`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageTimeoutW` at `0x180030e98`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180030f98`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180030f98`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall CMsgrWndBase::DestroyMsgrWindow(CMsgrWndBase *this)
{
  unsigned int v2; // esi
  __int64 v3; // r9
  __int64 v4; // rcx
  HWND v5; // rcx
  DWORD WindowThreadProcessId; // ebp
  __int64 v7; // rcx
  __int64 v8; // r9
  int v9; // ecx
  int v10; // r8d
  PVOID v11; // rcx
  signed int LastError; // eax
  DWORD dwProcessId; // [rsp+80h] [rbp+8h] BYREF
  ULONG_PTR dwResult; // [rsp+88h] [rbp+10h] BYREF
  __int64 v16; // [rsp+90h] [rbp+18h] BYREF
  __int64 v17; // [rsp+98h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids);
  }
  v2 = 0;
  dwResult = 0;
  *((_BYTE *)this + 16) = 1;
  if ( IsWindow(*((HWND *)this + 3)) )
  {
    CaptureStack(this);
    *((_BYTE *)this + 10) = 1;
    if ( !*((_QWORD *)this + 3) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v4);
    v5 = (HWND)*((_QWORD *)this + 3);
    dwProcessId = 0;
    WindowThreadProcessId = GetWindowThreadProcessId(v5, &dwProcessId);
    if ( GetCurrentProcessId() != dwProcessId )
      MicrosoftTelemetryAssertTriggeredNoArgs(v7);
    v8 = *((_QWORD *)this + 5);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids, v8);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids);
    }
    if ( GetCurrentThreadId() == WindowThreadProcessId )
    {
      *((_BYTE *)this + 12) = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids);
      }
      SetWindowLongPtrW(*((HWND *)this + 3), -21, 0);
      v2 = DestroyWindow(*((HWND *)this + 3));
      if ( !v2 )
      {
        *((_BYTE *)this + 14) = 1;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids,
            (unsigned int)LastError);
        }
      }
      *((_QWORD *)this + 3) = 0;
      *((_QWORD *)this + 4) = 0;
      if ( !v2 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v11);
    }
    else
    {
      *((_BYTE *)this + 11) = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids);
      }
      SetWindowLongPtrW(*((HWND *)this + 3), -21, 0);
      *((_BYTE *)this + 8) = 1;
      *((_QWORD *)this + 7) = SendMessageTimeoutW(*((HWND *)this + 3), 0x10u, 0, 0, 1u, 0x493E0u, &dwResult);
      *((_BYTE *)this + 9) = 1;
      if ( !*((_QWORD *)this + 7) )
      {
        *((_BYTE *)this + 13) = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids);
        }
        *((_DWORD *)this + 12) = GetLastError();
        if ( (unsigned int)dword_1800AF0C0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800AF0C0, 0x400000000000LL) )
        {
          v16 = *((_QWORD *)this + 7);
          v17 = *((unsigned int *)this + 12);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            v9,
            (unsigned int)word_1800A097A,
            v10,
            v3,
            (__int64)&v17,
            (__int64)&v16);
        }
      }
      *((_QWORD *)this + 3) = 0;
      *((_QWORD *)this + 4) = 0;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids);
  }
  *((_BYTE *)this + 15) = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(v3) = v2 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids, v3);
  }
  return v2;
}

```

## disassembly

```asm
0x180030d10  push    rbx
0x180030d12  push    rbp
0x180030d13  push    rsi
0x180030d14  push    rdi
0x180030d15  push    r12
0x180030d17  push    r13
0x180030d19  sub     rsp, 48h
0x180030d1d  mov     rbx, rcx
0x180030d20  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d27  lea     r12, WPP_GLOBAL_Control
0x180030d2e  lea     r13, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids
0x180030d35  cmp     rcx, r12
0x180030d38  jz      short loc_180030D57
0x180030d3a  test    byte ptr [rcx+1Ch], 4
0x180030d3e  jz      short loc_180030D57
0x180030d40  cmp     byte ptr [rcx+19h], 6
0x180030d44  jb      short loc_180030D57
0x180030d46  mov     rcx, [rcx+10h]
0x180030d4a  mov     edx, 13h
0x180030d4f  mov     r8, r13
0x180030d52  call    WPP_SF_
0x180030d57  xor     esi, esi
0x180030d59  mov     [rsp+78h+dwResult], rsi
0x180030d61  lea     edi, [rsi+1]
0x180030d64  mov     eax, edi
0x180030d66  xchg    al, [rbx+10h]
0x180030d69  mov     rcx, [rbx+18h]; hWnd
0x180030d6d  call    cs:__imp_IsWindow
0x180030d73  test    eax, eax
0x180030d75  jz      loc_180031009
0x180030d7b  mov     rcx, rbx; struct CMsgrWndBase *
0x180030d7e  call    ?CaptureStack@@YAXPEAVCMsgrWndBase@@@Z; CaptureStack(CMsgrWndBase *)
0x180030d83  mov     eax, edi
0x180030d85  xchg    al, [rbx+0Ah]
0x180030d88  cmp     [rbx+18h], rsi
0x180030d8c  jnz     short loc_180030D93
0x180030d8e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180030d93  mov     rcx, [rbx+18h]; hWnd
0x180030d97  lea     rdx, [rsp+78h+dwProcessId]; lpdwProcessId
0x180030d9f  mov     [rsp+78h+dwProcessId], esi
0x180030da6  call    cs:__imp_GetWindowThreadProcessId
0x180030dac  mov     ebp, eax
0x180030dae  call    cs:__imp_GetCurrentProcessId
0x180030db4  cmp     eax, [rsp+78h+dwProcessId]
0x180030dbb  jz      short loc_180030DC2
0x180030dbd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180030dc2  mov     r9, [rbx+28h]
0x180030dc6  test    r9, r9
0x180030dc9  jz      short loc_180030DF6
0x180030dcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180030dd2  cmp     rcx, r12
0x180030dd5  jz      short loc_180030E1F
0x180030dd7  test    byte ptr [rcx+1Ch], 4
0x180030ddb  jz      short loc_180030E1F
0x180030ddd  cmp     byte ptr [rcx+19h], 5
0x180030de1  jb      short loc_180030E1F
0x180030de3  mov     rcx, [rcx+10h]
0x180030de7  mov     edx, 14h
0x180030dec  mov     r8, r13
0x180030def  call    WPP_SF_S
0x180030df4  jmp     short loc_180030E1F
0x180030df6  mov     rcx, cs:WPP_GLOBAL_Control
0x180030dfd  cmp     rcx, r12
0x180030e00  jz      short loc_180030E1F
0x180030e02  test    byte ptr [rcx+1Ch], 4
0x180030e06  jz      short loc_180030E1F
0x180030e08  cmp     byte ptr [rcx+19h], 5
0x180030e0c  jb      short loc_180030E1F
0x180030e0e  mov     rcx, [rcx+10h]
0x180030e12  mov     edx, 15h
0x180030e17  mov     r8, r13
0x180030e1a  call    WPP_SF_
0x180030e1f  call    cs:__imp_GetCurrentThreadId
0x180030e25  cmp     eax, ebp
0x180030e27  mov     eax, edi
0x180030e29  jz      loc_180030F57
0x180030e2f  xchg    al, [rbx+0Bh]
0x180030e32  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e39  cmp     rcx, r12
0x180030e3c  jz      short loc_180030E5B
0x180030e3e  test    byte ptr [rcx+1Ch], 4
0x180030e42  jz      short loc_180030E5B
0x180030e44  cmp     byte ptr [rcx+19h], 5
0x180030e48  jb      short loc_180030E5B
0x180030e4a  mov     rcx, [rcx+10h]
0x180030e4e  mov     edx, 16h
0x180030e53  mov     r8, r13
0x180030e56  call    WPP_SF_
0x180030e5b  mov     rcx, [rbx+18h]; hWnd
0x180030e5f  xor     r8d, r8d; dwNewLong
0x180030e62  lea     edx, [r8-15h]; nIndex
0x180030e66  call    cs:__imp_SetWindowLongPtrW
0x180030e6c  mov     eax, edi
0x180030e6e  xor     r9d, r9d; lParam
0x180030e71  xchg    al, [rbx+8]
0x180030e74  mov     rcx, [rbx+18h]; hWnd
0x180030e78  lea     rax, [rsp+78h+dwResult]
0x180030e80  mov     [rsp+78h+lpdwResult], rax; lpdwResult
0x180030e85  xor     r8d, r8d; wParam
0x180030e88  mov     [rsp+78h+uTimeout], 493E0h; uTimeout
0x180030e90  lea     edx, [r9+10h]; Msg
0x180030e94  mov     [rsp+78h+fuFlags], edi; fuFlags
0x180030e98  call    cs:__imp_SendMessageTimeoutW
0x180030e9e  mov     [rbx+38h], rax
0x180030ea2  mov     eax, edi
0x180030ea4  xchg    al, [rbx+9]
0x180030ea7  cmp     [rbx+38h], rsi
0x180030eab  jnz     loc_180030F4A
0x180030eb1  mov     eax, edi
0x180030eb3  xchg    al, [rbx+0Dh]
0x180030eb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ebd  cmp     rcx, r12
0x180030ec0  jz      short loc_180030EDF
0x180030ec2  test    byte ptr [rcx+1Ch], 4
0x180030ec6  jz      short loc_180030EDF
0x180030ec8  cmp     byte ptr [rcx+19h], 5
0x180030ecc  jb      short loc_180030EDF
0x180030ece  mov     rcx, [rcx+10h]
0x180030ed2  mov     edx, 17h
0x180030ed7  mov     r8, r13
0x180030eda  call    WPP_SF_
0x180030edf  call    cs:__imp_GetLastError
0x180030ee5  mov     [rbx+30h], eax
0x180030ee8  mov     eax, cs:dword_1800AF0C0
0x180030eee  cmp     eax, 5
0x180030ef1  jbe     short loc_180030F4A
0x180030ef3  mov     rdx, 400000000000h
0x180030efd  lea     rcx, dword_1800AF0C0
0x180030f04  call    _tlgKeywordOn
0x180030f09  test    al, al
0x180030f0b  jz      short loc_180030F4A
0x180030f0d  mov     rax, [rbx+38h]
0x180030f11  lea     rdx, word_1800A097A
0x180030f18  mov     [rsp+78h+arg_10], rax
0x180030f20  mov     eax, [rbx+30h]
0x180030f23  mov     [rsp+78h+arg_18], rax
0x180030f2b  lea     rax, [rsp+78h+arg_10]
0x180030f33  mov     qword ptr [rsp+78h+uTimeout], rax
0x180030f38  lea     rax, [rsp+78h+arg_18]
0x180030f40  mov     qword ptr [rsp+78h+fuFlags], rax
0x180030f45  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180030f4a  mov     [rbx+18h], rsi
0x180030f4e  mov     [rbx+20h], rsi
0x180030f52  jmp     loc_180031032
0x180030f57  xchg    al, [rbx+0Ch]
0x180030f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030f61  cmp     rcx, r12
0x180030f64  jz      short loc_180030F83
0x180030f66  test    byte ptr [rcx+1Ch], 4
0x180030f6a  jz      short loc_180030F83
0x180030f6c  cmp     byte ptr [rcx+19h], 5
0x180030f70  jb      short loc_180030F83
0x180030f72  mov     rcx, [rcx+10h]
0x180030f76  mov     edx, 18h
0x180030f7b  mov     r8, r13
0x180030f7e  call    WPP_SF_
0x180030f83  mov     rcx, [rbx+18h]; hWnd
0x180030f87  xor     r8d, r8d; dwNewLong
0x180030f8a  lea     edx, [r8-15h]; nIndex
0x180030f8e  call    cs:__imp_SetWindowLongPtrW
0x180030f94  mov     rcx, [rbx+18h]; hWnd
0x180030f98  call    cs:__imp_DestroyWindow
0x180030f9e  mov     esi, eax
0x180030fa0  test    eax, eax
0x180030fa2  jnz     short loc_180030FEE
0x180030fa4  mov     ecx, edi
0x180030fa6  xchg    cl, [rbx+0Eh]
0x180030fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180030fb0  cmp     rcx, r12
0x180030fb3  jz      short loc_180030FEE
0x180030fb5  test    byte ptr [rcx+1Ch], 4
0x180030fb9  jz      short loc_180030FEE
0x180030fbb  cmp     [rcx+19h], dil
0x180030fbf  jb      short loc_180030FEE
0x180030fc1  call    cs:__imp_GetLastError
0x180030fc7  test    eax, eax
0x180030fc9  jle     short loc_180030FD3
0x180030fcb  movzx   eax, ax
0x180030fce  or      eax, 80070000h
0x180030fd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180030fda  mov     edx, 19h
0x180030fdf  mov     r9d, eax
0x180030fe2  mov     r8, r13
0x180030fe5  mov     rcx, [rcx+10h]
0x180030fe9  call    WPP_SF_d
0x180030fee  mov     qword ptr [rbx+18h], 0
0x180030ff6  mov     qword ptr [rbx+20h], 0
0x180030ffe  test    esi, esi
0x180031000  jnz     short loc_180031032
0x180031002  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031007  jmp     short loc_180031032
0x180031009  mov     rcx, cs:WPP_GLOBAL_Control
0x180031010  cmp     rcx, r12
0x180031013  jz      short loc_180031032
0x180031015  test    byte ptr [rcx+1Ch], 4
0x180031019  jz      short loc_180031032
0x18003101b  cmp     byte ptr [rcx+19h], 5
0x18003101f  jb      short loc_180031032
0x180031021  mov     rcx, [rcx+10h]
0x180031025  mov     edx, 1Ah
0x18003102a  mov     r8, r13
0x18003102d  call    WPP_SF_
0x180031032  xchg    dil, [rbx+0Fh]
0x180031036  mov     rcx, cs:WPP_GLOBAL_Control
0x18003103d  cmp     rcx, r12
0x180031040  jz      short loc_180031065
0x180031042  test    byte ptr [rcx+1Ch], 4
0x180031046  jz      short loc_180031065
0x180031048  cmp     byte ptr [rcx+19h], 6
0x18003104c  jb      short loc_180031065
0x18003104e  mov     rcx, [rcx+10h]
0x180031052  test    esi, esi
0x180031054  mov     edx, 1Bh
0x180031059  mov     r8, r13
0x18003105c  setnz   r9b
0x180031060  call    WPP_SF_c
0x180031065  mov     eax, esi
0x180031067  add     rsp, 48h
0x18003106b  pop     r13
0x18003106d  pop     r12
0x18003106f  pop     rdi
0x180031070  pop     rsi
0x180031071  pop     rbp
0x180031072  pop     rbx
0x180031073  retn
```
