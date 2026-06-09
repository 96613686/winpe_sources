# xxxDesktopWndProcWorker(tagWND *,uint,unsigned __int64,__int64)

- ea: `0x140084578`
- end: `0x140084a14`
- name: `?xxxDesktopWndProcWorker@@YA_JPEAUtagWND@@I_K_J@Z`
- size: `1180`
- prototype: `__int64 __fastcall(struct tagWND *, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400844b0`

## callees

- `0x140005a18`
- `0x14001bf34`
- `0x14001e950`
- `0x14002362c`
- `0x140032784`
- `0x14003824c`
- `0x14004cd80`
- `0x140084578`
- `0x140084a1c`
- `0x140085ba8`
- `0x14008f164`
- `0x1400b8c90`
- `0x1400cf1d0`
- `0x1400d0ac8`
- `0x1400db6d4`
- `0x1401fc8c0`
- `0x14021f99c`
- `0x14022e5e4`
- `0x14023412c`
- `0x14024a87c`
- `0x1402938dc`
- `0x1402b1ba0`
- `0x140342fa0`
- `0x140343500`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400848aa`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400848aa`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400848ce`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400848ce`
- `ntoskrnl!KeBugCheckEx` at `0x14008470c`
- `ntoskrnl!KeBugCheckEx` at `0x14008470c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14008468d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14008468d`
- `win32kbase!?CreateProfileUserName@@YAPEAU_UNICODE_STRING@@PEAU?$Win32RawOptionalLockedItemAlways@UtagPROFILEUSERNAME@@$1?Win32FreePool@@YAXPEAX@Z@@@Z` at `0x140084865`
- `win32kbase!?CreateProfileUserName@@YAPEAU_UNICODE_STRING@@PEAU?$Win32RawOptionalLockedItemAlways@UtagPROFILEUSERNAME@@$1?Win32FreePool@@YAXPEAX@Z@@@Z` at `0x140084865`
- `win32kbase!IsWindowDesktopComposed` at `0x14008480f`
- `win32kbase!IsWindowDesktopComposed` at `0x14008480f`
- `WIN32K!W32GetUserSessionState` at `0x140084672`
- `WIN32K!W32GetUserSessionState` at `0x140084728`
- `WIN32K!W32GetUserSessionState` at `0x140084742`
- `WIN32K!W32GetUserSessionState` at `0x140084763`
- `WIN32K!W32GetUserSessionState` at `0x14008477f`
- `WIN32K!W32GetUserSessionState` at `0x1400847b7`
- `WIN32K!W32GetUserSessionState` at `0x14008494f`
- `WIN32K!W32GetUserSessionState` at `0x140084968`
- `WIN32K!W32GetUserSessionState` at `0x140084982`
- `WIN32K!W32GetUserSessionState` at `0x1400849ab`
- `WIN32K!W32GetUserSessionState` at `0x140084672`
- `WIN32K!W32GetUserSessionState` at `0x140084728`
- `WIN32K!W32GetUserSessionState` at `0x140084742`
- `WIN32K!W32GetUserSessionState` at `0x140084763`
- `WIN32K!W32GetUserSessionState` at `0x14008477f`
- `WIN32K!W32GetUserSessionState` at `0x1400847b7`
- `WIN32K!W32GetUserSessionState` at `0x14008494f`
- `WIN32K!W32GetUserSessionState` at `0x140084968`
- `WIN32K!W32GetUserSessionState` at `0x140084982`
- `WIN32K!W32GetUserSessionState` at `0x1400849ab`

## pseudocode

```c
__int64 __fastcall xxxDesktopWndProcWorker(struct tagWND *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned __int64 v11; // r8
  unsigned int v12; // edx
  __int64 v13; // rcx
  __int64 i; // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 UserSessionState; // rax
  __int64 v27; // rbx
  __int64 v28; // rcx
  __int128 v29; // [rsp+40h] [rbp-59h] BYREF
  __int64 v30; // [rsp+50h] [rbp-49h]
  _BYTE v31[80]; // [rsp+60h] [rbp-39h] BYREF

  memset_0(v31, 0, 0x48u);
  *(_QWORD *)&v29 = 0;
  if ( !(unsigned int)xxxValidateClassAndSize((_DWORD)a1, a2, a3, a4, 669, 1, (__int64)&v29) )
    return v29;
  if ( !*((_QWORD *)a1 + 13) )
  {
    if ( a2 != 128 )
    {
LABEL_5:
      v11 = a3;
      v12 = a2;
      return xxxDefWindowProc(a1, v12, v11, a4);
    }
    return 0;
  }
  if ( a2 > 0x80 )
  {
    if ( a2 != 161 )
    {
      switch ( a2 )
      {
        case 0x112u:
          v11 = 61760;
          if ( a3 == 61760 )
          {
            v12 = 274;
            return xxxDefWindowProc(a1, v12, v11, a4);
          }
          break;
        case 0x128u:
          return xxxDWP_UpdateUIState(a1, a3, a4);
        case 0x203u:
          a2 = 274;
          a3 = 61744;
          goto LABEL_5;
        case 0x30Fu:
          goto LABEL_52;
        case 0x311u:
          if ( *(_QWORD *)a1 != a3 )
LABEL_52:
            xxxRealizeDesktop(a1);
          break;
        case 0x401u:
          if ( !(unsigned int)IsRemoteConnection(v9, v8)
            && *(_DWORD *)(W32GetUserSessionState(v23) + 16240)
            && !*(_QWORD *)(W32GetUserSessionState(v24) + 16248) )
          {
            UserSessionState = W32GetUserSessionState(v25);
            v27 = SetRITTimer(*(_QWORD *)(UserSessionState + 16248), 20, HideMouseTrails);
            *(_QWORD *)(W32GetUserSessionState(v28) + 16248) = v27;
          }
          return 0;
        default:
          goto LABEL_5;
      }
    }
    return 0;
  }
  switch ( a2 )
  {
    case 0x80u:
      return 0;
    case 1u:
      v30 = -1;
      v29 = 0;
      v22 = CreateProfileUserName(&v29);
      SetDesktopPattern(v22, 0);
      if ( v30 != -1 )
        PopAndFreeAlwaysW32ThreadLock(&v29);
      xxxSendNotifyMessage(a1, 21, 0, 0, 1);
      xxxRealizeDesktop(a1);
      PsGetCurrentProcessId();
      xxxSetWindowLong(a1, 0);
      PsGetCurrentThreadId();
      xxxSetWindowLong(a1, 0);
      return 0;
    case 0xFu:
      xxxBeginPaint((unsigned int **)a1, (__int64)v31);
      xxxEndPaint(a1);
      return 0;
    case 0x10u:
      return 0;
  }
  if ( a2 != 20 )
  {
    switch ( a2 )
    {
      case 0x15u:
        xxxRedrawWindow(a1, 0, 0, 133);
        break;
      case 0x3Au:
        LODWORD(v29) = 0x20000;
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1394);
        break;
      case 0x46u:
        if ( (*(_DWORD *)(a4 + 32) & 4) == 0 && !*(_QWORD *)(a4 + 8) )
        {
          v15 = W32GetUserSessionState(v9);
          xxxSetThreadDesktop(0, *(_QWORD *)(v15 + 19216));
          v17 = W32GetUserSessionState(v16);
          if ( (unsigned int)GreGetSystemPaletteUse(*(HDC *)(*(_QWORD *)(v17 + 56744) + 56LL)) != 1 )
          {
            v19 = W32GetUserSessionState(v18);
            GreRealizeDefaultPalette(*(HDC *)(*(_QWORD *)(v19 + 56744) + 56LL));
          }
          if ( (*(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v18) + 19216) + 48LL) & 1) != 0 )
          {
            xxxSendNotifyMessage(-1, 785, *(_QWORD *)a1, 0, 1);
            v21 = W32GetUserSessionState(v20);
            *(_DWORD *)(*(_QWORD *)(v21 + 19216) + 48LL) &= ~1u;
          }
        }
        break;
      case 0x51u:
        if ( !*(_QWORD *)W32GetUserSessionState(v9) || !IS_USERCRIT_OWNED_AT_ALL() )
          KeBugCheckEx(0x164u, 0x2Au, 0, 0, 0);
        *((_QWORD *)&v29 + 1) = PsGetCurrentThreadWin32Thread(v13);
        LOBYTE(v29) = 1;
        ++*(_DWORD *)(*((_QWORD *)&v29 + 1) + 28LL);
        for ( i = *((_QWORD *)a1 + 14); i; i = *(_QWORD *)(i + 88) )
          SendNotifyMessageAlways(i, 81, a3, a4, 1);
        AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)&v29);
        break;
      default:
        goto LABEL_5;
    }
    return 0;
  }
  if ( !(unsigned int)IsWindowDesktopComposed(a1) )
    xxxInternalPaintDesktop(a1, a3, 1);
  return 1;
}

```

## disassembly

```asm
0x140084578  push    rbp
0x14008457a  push    rbx
0x14008457b  push    rsi
0x14008457c  push    rdi
0x14008457d  push    r12
0x14008457f  push    r14
0x140084581  lea     rbp, [rsp-2Fh]
0x140084586  sub     rsp, 0C8h
0x14008458d  mov     rax, cs:__security_cookie
0x140084594  xor     rax, rsp
0x140084597  mov     [rbp+57h+var_40], rax
0x14008459b  mov     edi, edx
0x14008459d  mov     rsi, r8
0x1400845a0  xor     edx, edx; Val
0x1400845a2  mov     rbx, rcx
0x1400845a5  lea     rcx, [rbp+57h+var_90]; void *
0x1400845a9  mov     r14, r9
0x1400845ac  lea     r8d, [rdx+48h]; Size
0x1400845b0  call    memset_0
0x1400845b5  lea     rax, [rbp+57h+var_B0]
0x1400845b9  mov     qword ptr [rbp+57h+var_B0], 0
0x1400845c1  mov     [rsp+0F0h+var_C0], rax
0x1400845c6  mov     r12d, 1
0x1400845cc  mov     [rsp+0F0h+var_C8], r12d
0x1400845d1  mov     r9, r14
0x1400845d4  mov     r8, rsi
0x1400845d7  mov     word ptr [rsp+0F0h+BugCheckParameter4], 29Dh
0x1400845de  mov     edx, edi
0x1400845e0  mov     rcx, rbx
0x1400845e3  call    xxxValidateClassAndSize
0x1400845e8  test    eax, eax
0x1400845ea  jnz     short loc_1400845F5
0x1400845ec  mov     rax, qword ptr [rbp+57h+var_B0]
0x1400845f0  jmp     loc_1400846D7
0x1400845f5  cmp     qword ptr [rbx+68h], 0
0x1400845fa  mov     eax, 80h
0x1400845ff  jnz     short loc_14008461E
0x140084601  cmp     edi, eax
0x140084603  jz      loc_1400846D5
0x140084609  mov     r8, rsi
0x14008460c  mov     edx, edi
0x14008460e  mov     r9, r14
0x140084611  mov     rcx, rbx
0x140084614  call    xxxDefWindowProc
0x140084619  jmp     loc_1400846D7
0x14008461e  cmp     edi, eax
0x140084620  ja      loc_1400848F9
0x140084626  jz      loc_1400846D5
0x14008462c  mov     eax, edi
0x14008462e  sub     eax, r12d
0x140084631  jz      loc_140084852
0x140084637  sub     eax, 0Eh
0x14008463a  jz      loc_140084835
0x140084640  sub     eax, r12d
0x140084643  jz      loc_1400846D5
0x140084649  sub     eax, 4
0x14008464c  jz      loc_14008480C
0x140084652  sub     eax, r12d
0x140084655  jz      loc_1400847F4
0x14008465b  sub     eax, 25h ; '%'
0x14008465e  jz      loc_1400847D3
0x140084664  sub     eax, 0Ch
0x140084667  jz      loc_140084719
0x14008466d  cmp     eax, 0Bh
0x140084670  jnz     short loc_140084609
0x140084672  call    cs:__imp_W32GetUserSessionState
0x140084679  nop     dword ptr [rax+rax+00h]
0x14008467e  cmp     qword ptr [rax], 0
0x140084682  jz      short loc_1400846F4
0x140084684  call    ?IS_USERCRIT_OWNED_AT_ALL@@YA_NXZ; IS_USERCRIT_OWNED_AT_ALL(void)
0x140084689  test    al, al
0x14008468b  jz      short loc_1400846F4
0x14008468d  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140084694  nop     dword ptr [rax+rax+00h]
0x140084699  mov     qword ptr [rbp+57h+var_B0+8], rax
0x14008469d  mov     byte ptr [rbp+57h+var_B0], r12b
0x1400846a1  add     [rax+1Ch], r12d
0x1400846a5  mov     rbx, [rbx+70h]
0x1400846a9  jmp     short loc_1400846C7
0x1400846ab  mov     r9, r14
0x1400846ae  mov     dword ptr [rsp+0F0h+BugCheckParameter4], r12d
0x1400846b3  mov     r8, rsi
0x1400846b6  mov     edx, 51h ; 'Q'
0x1400846bb  mov     rcx, rbx
0x1400846be  call    ?SendNotifyMessageAlways@@YA_NPEAUtagWND@@I_K_JW4SNMAOptions@@@Z; SendNotifyMessageAlways(tagWND *,uint,unsigned __int64,__int64,SNMAOptions)
0x1400846c3  mov     rbx, [rbx+58h]
0x1400846c7  test    rbx, rbx
0x1400846ca  jnz     short loc_1400846AB
0x1400846cc  lea     rcx, [rbp+57h+var_B0]; this
0x1400846d0  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1400846d5  xor     eax, eax
0x1400846d7  mov     rcx, [rbp+57h+var_40]
0x1400846db  xor     rcx, rsp; StackCookie
0x1400846de  call    __security_check_cookie
0x1400846e3  add     rsp, 0C8h
0x1400846ea  pop     r14
0x1400846ec  pop     r12
0x1400846ee  pop     rdi
0x1400846ef  pop     rsi
0x1400846f0  pop     rbx
0x1400846f1  pop     rbp
0x1400846f2  retn
0x1400846f4  xor     r9d, r9d; BugCheckParameter3
0x1400846f7  mov     [rsp+0F0h+BugCheckParameter4], 0; BugCheckParameter4
0x140084700  xor     r8d, r8d; BugCheckParameter2
0x140084703  mov     ecx, 164h; BugCheckCode
0x140084708  lea     edx, [r9+2Ah]; BugCheckParameter1
0x14008470c  call    cs:__imp_KeBugCheckEx
0x140084719  mov     eax, [r14+20h]
0x14008471d  test    al, 4
0x14008471f  jnz     short loc_1400846D5
0x140084721  cmp     qword ptr [r14+8], 0
0x140084726  jnz     short loc_1400846D5
0x140084728  call    cs:__imp_W32GetUserSessionState
0x14008472f  nop     dword ptr [rax+rax+00h]
0x140084734  xor     ecx, ecx
0x140084736  mov     rdx, [rax+4B10h]
0x14008473d  call    xxxSetThreadDesktop
0x140084742  call    cs:__imp_W32GetUserSessionState
0x140084749  nop     dword ptr [rax+rax+00h]
0x14008474e  mov     rcx, [rax+0DDA8h]
0x140084755  mov     rcx, [rcx+38h]; HDC
0x140084759  call    GreGetSystemPaletteUse
0x14008475e  cmp     eax, r12d
0x140084761  jz      short loc_14008477F
0x140084763  call    cs:__imp_W32GetUserSessionState
0x14008476a  nop     dword ptr [rax+rax+00h]
0x14008476f  mov     rcx, [rax+0DDA8h]
0x140084776  mov     rcx, [rcx+38h]; HDC
0x14008477a  call    GreRealizeDefaultPalette
0x14008477f  call    cs:__imp_W32GetUserSessionState
0x140084786  nop     dword ptr [rax+rax+00h]
0x14008478b  mov     rcx, [rax+4B10h]
0x140084792  mov     eax, [rcx+30h]
0x140084795  test    r12b, al
0x140084798  jz      loc_1400846D5
0x14008479e  mov     r8, [rbx]
0x1400847a1  xor     r9d, r9d
0x1400847a4  mov     edx, 311h
0x1400847a9  mov     dword ptr [rsp+0F0h+BugCheckParameter4], r12d
0x1400847ae  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400847b2  call    xxxSendNotifyMessage
0x1400847b7  call    cs:__imp_W32GetUserSessionState
0x1400847be  nop     dword ptr [rax+rax+00h]
0x1400847c3  mov     rcx, [rax+4B10h]
0x1400847ca  and     dword ptr [rcx+30h], 0FFFFFFFEh
0x1400847ce  jmp     loc_1400846D5
0x1400847d3  mov     dword ptr [rbp+57h+var_B0], 20000h
0x1400847da  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1400847e1  mov     edx, dword ptr [rbp+57h+var_B0]
0x1400847e4  mov     r8d, 572h
0x1400847ea  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1400847ef  jmp     loc_1400846D5
0x1400847f4  mov     r9d, 85h
0x1400847fa  xor     r8d, r8d
0x1400847fd  xor     edx, edx
0x1400847ff  mov     rcx, rbx
0x140084802  call    xxxRedrawWindow
0x140084807  jmp     loc_1400846D5
0x14008480c  mov     rcx, rbx
0x14008480f  call    cs:__imp_IsWindowDesktopComposed
0x140084816  nop     dword ptr [rax+rax+00h]
0x14008481b  test    eax, eax
0x14008481d  jnz     short loc_14008482D
0x14008481f  mov     r8d, r12d
0x140084822  mov     rdx, rsi
0x140084825  mov     rcx, rbx
0x140084828  call    xxxInternalPaintDesktop
0x14008482d  mov     rax, r12
0x140084830  jmp     loc_1400846D7
0x140084835  lea     rdx, [rbp+57h+var_90]
0x140084839  mov     rcx, rbx; struct tagWND *
0x14008483c  call    xxxBeginPaint
0x140084841  lea     rdx, [rbp+57h+var_90]
0x140084845  mov     rcx, rbx; struct tagWND *
0x140084848  call    xxxEndPaint
0x14008484d  jmp     loc_1400846D5
0x140084852  xorps   xmm0, xmm0
0x140084855  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFFh
0x14008485d  lea     rcx, [rbp+57h+var_B0]
0x140084861  movups  [rbp+57h+var_B0], xmm0
0x140084865  call    cs:__imp_?CreateProfileUserName@@YAPEAU_UNICODE_STRING@@PEAU?$Win32RawOptionalLockedItemAlways@UtagPROFILEUSERNAME@@$1?Win32FreePool@@YAXPEAX@Z@@@Z; CreateProfileUserName(Win32RawOptionalLockedItemAlways<tagPROFILEUSERNAME,&Win32FreePool(void *)> *)
0x14008486c  nop     dword ptr [rax+rax+00h]
0x140084871  mov     rcx, rax
0x140084874  xor     edx, edx
0x140084876  call    SetDesktopPattern
0x14008487b  cmp     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFFh
0x140084880  jz      short loc_14008488B
0x140084882  lea     rcx, [rbp+57h+var_B0]
0x140084886  call    PopAndFreeAlwaysW32ThreadLock
0x14008488b  xor     r9d, r9d
0x14008488e  mov     dword ptr [rsp+0F0h+BugCheckParameter4], r12d
0x140084893  xor     r8d, r8d
0x140084896  mov     rcx, rbx
0x140084899  lea     edx, [r9+15h]
0x14008489d  call    xxxSendNotifyMessage
0x1400848a2  mov     rcx, rbx
0x1400848a5  call    xxxRealizeDesktop
0x1400848aa  call    cs:__imp_PsGetCurrentProcessId
0x1400848b1  nop     dword ptr [rax+rax+00h]
0x1400848b6  xor     r9d, r9d
0x1400848b9  mov     dword ptr [rsp+0F0h+BugCheckParameter4], 0
0x1400848c1  mov     r8d, eax
0x1400848c4  xor     edx, edx
0x1400848c6  mov     rcx, rbx
0x1400848c9  call    xxxSetWindowLong
0x1400848ce  call    cs:__imp_PsGetCurrentThreadId
0x1400848d5  nop     dword ptr [rax+rax+00h]
0x1400848da  xor     r9d, r9d
0x1400848dd  mov     dword ptr [rsp+0F0h+BugCheckParameter4], 0
0x1400848e5  mov     r8d, eax
0x1400848e8  mov     rcx, rbx
0x1400848eb  lea     edx, [r9+4]
0x1400848ef  call    xxxSetWindowLong
0x1400848f4  jmp     loc_1400846D5
0x1400848f9  mov     eax, edi
0x1400848fb  sub     eax, 0A1h
0x140084900  jz      loc_1400846D5
0x140084906  sub     eax, 71h ; 'q'
0x140084909  jz      loc_1400849FB
0x14008490f  sub     eax, 16h
0x140084912  jz      loc_1400849E8
0x140084918  sub     eax, 0DBh
0x14008491d  jz      loc_1400849D9
0x140084923  sub     eax, 10Ch
0x140084928  jz      loc_1400849CC
0x14008492e  sub     eax, 2
0x140084931  jz      loc_1400849C3
0x140084937  cmp     eax, 0F0h
0x14008493c  jnz     loc_140084609
0x140084942  call    IsRemoteConnection
0x140084947  test    eax, eax
0x140084949  jnz     loc_1400846D5
0x14008494f  call    cs:__imp_W32GetUserSessionState
0x140084956  nop     dword ptr [rax+rax+00h]
0x14008495b  cmp     dword ptr [rax+3F70h], 0
0x140084962  jz      loc_1400846D5
0x140084968  call    cs:__imp_W32GetUserSessionState
0x14008496f  nop     dword ptr [rax+rax+00h]
0x140084974  cmp     qword ptr [rax+3F78h], 0
0x14008497c  jnz     loc_1400846D5
0x140084982  call    cs:__imp_W32GetUserSessionState
0x140084989  nop     dword ptr [rax+rax+00h]
0x14008498e  xor     r9d, r9d
0x140084991  lea     r8, HideMouseTrails
0x140084998  mov     rcx, [rax+3F78h]
0x14008499f  lea     edx, [r9+14h]
0x1400849a3  call    SetRITTimer
0x1400849a8  mov     rbx, rax
0x1400849ab  call    cs:__imp_W32GetUserSessionState
0x1400849b2  nop     dword ptr [rax+rax+00h]
0x1400849b7  mov     [rax+3F78h], rbx
0x1400849be  jmp     loc_1400846D5
0x1400849c3  cmp     [rbx], rsi
0x1400849c6  jz      loc_1400846D5
0x1400849cc  mov     rcx, rbx
0x1400849cf  call    xxxRealizeDesktop
0x1400849d4  jmp     loc_1400846D5
0x1400849d9  mov     edi, 112h
0x1400849de  mov     esi, 0F130h
0x1400849e3  jmp     loc_140084609
0x1400849e8  mov     r8, r14
0x1400849eb  mov     rdx, rsi
0x1400849ee  mov     rcx, rbx
0x1400849f1  call    xxxDWP_UpdateUIState
0x1400849f6  jmp     loc_1400846D7
0x1400849fb  mov     r8d, 0F140h
0x140084a01  cmp     rsi, r8
0x140084a04  jnz     loc_1400846D5
0x140084a0a  mov     edx, 112h
0x140084a0f  jmp     loc_14008460E
```
