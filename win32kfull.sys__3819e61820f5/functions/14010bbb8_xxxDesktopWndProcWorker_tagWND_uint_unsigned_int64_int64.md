# xxxDesktopWndProcWorker(tagWND *,uint,unsigned __int64,__int64)

- ea: `0x14010bbb8`
- end: `0x14010c054`
- name: `?xxxDesktopWndProcWorker@@YA_JPEAUtagWND@@I_K_J@Z`
- size: `1180`
- prototype: `__int64 __fastcall(struct tagWND *, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14010baf0`

## callees

- `0x14000b0f0`
- `0x14000ca28`
- `0x140016fe4`
- `0x140020d74`
- `0x140023ac0`
- `0x14002871c`
- `0x140036e04`
- `0x1400b5444`
- `0x1400d0a70`
- `0x1400d62b4`
- `0x14010bbb8`
- `0x14010c05c`
- `0x14010c598`
- `0x14010cb90`
- `0x1401939d0`
- `0x140198928`
- `0x1401fae30`
- `0x14021e38c`
- `0x14022d2d4`
- `0x14024950c`
- `0x1402913f0`
- `0x1402b01f0`
- `0x140341ff0`
- `0x140342540`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14010beea`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14010beea`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14010bf0e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14010bf0e`
- `ntoskrnl!KeBugCheckEx` at `0x14010bd4c`
- `ntoskrnl!KeBugCheckEx` at `0x14010bd4c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14010bccd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14010bccd`
- `win32kbase!?CreateProfileUserName@@YAPEAU_UNICODE_STRING@@PEAU?$Win32RawOptionalLockedItemAlways@UtagPROFILEUSERNAME@@$1?Win32FreePool@@YAXPEAX@Z@@@Z` at `0x14010bea5`
- `win32kbase!?CreateProfileUserName@@YAPEAU_UNICODE_STRING@@PEAU?$Win32RawOptionalLockedItemAlways@UtagPROFILEUSERNAME@@$1?Win32FreePool@@YAXPEAX@Z@@@Z` at `0x14010bea5`
- `win32kbase!IsWindowDesktopComposed` at `0x14010be4f`
- `win32kbase!IsWindowDesktopComposed` at `0x14010be4f`
- `WIN32K!W32GetUserSessionState` at `0x14010bcb2`
- `WIN32K!W32GetUserSessionState` at `0x14010bd68`
- `WIN32K!W32GetUserSessionState` at `0x14010bd82`
- `WIN32K!W32GetUserSessionState` at `0x14010bda3`
- `WIN32K!W32GetUserSessionState` at `0x14010bdbf`
- `WIN32K!W32GetUserSessionState` at `0x14010bdf7`
- `WIN32K!W32GetUserSessionState` at `0x14010bf8f`
- `WIN32K!W32GetUserSessionState` at `0x14010bfa8`
- `WIN32K!W32GetUserSessionState` at `0x14010bfc2`
- `WIN32K!W32GetUserSessionState` at `0x14010bfeb`
- `WIN32K!W32GetUserSessionState` at `0x14010bcb2`
- `WIN32K!W32GetUserSessionState` at `0x14010bd68`
- `WIN32K!W32GetUserSessionState` at `0x14010bd82`
- `WIN32K!W32GetUserSessionState` at `0x14010bda3`
- `WIN32K!W32GetUserSessionState` at `0x14010bdbf`
- `WIN32K!W32GetUserSessionState` at `0x14010bdf7`
- `WIN32K!W32GetUserSessionState` at `0x14010bf8f`
- `WIN32K!W32GetUserSessionState` at `0x14010bfa8`
- `WIN32K!W32GetUserSessionState` at `0x14010bfc2`
- `WIN32K!W32GetUserSessionState` at `0x14010bfeb`

## pseudocode

```c
__int64 __fastcall xxxDesktopWndProcWorker(struct tagWND *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned __int64 v13; // r8
  unsigned int v14; // edx
  __int64 v15; // rcx
  __int64 i; // rbx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 UserSessionState; // rax
  __int64 v47; // rbx
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  __int64 v51; // r9
  __int128 v52; // [rsp+40h] [rbp-59h] BYREF
  __int64 v53; // [rsp+50h] [rbp-49h]
  _BYTE v54[80]; // [rsp+60h] [rbp-39h] BYREF

  memset_0(v54, 0, 0x48u);
  *(_QWORD *)&v52 = 0;
  if ( !(unsigned int)xxxValidateClassAndSize((_DWORD)a1, a2, a3, a4, 669, 1, (__int64)&v52) )
    return v52;
  if ( !*((_QWORD *)a1 + 13) )
  {
    if ( a2 != 128 )
    {
LABEL_5:
      v13 = a3;
      v14 = a2;
      return xxxDefWindowProc(a1, v14, v13, a4);
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
          v13 = 61760;
          if ( a3 == 61760 )
          {
            v14 = 274;
            return xxxDefWindowProc(a1, v14, v13, a4);
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
            && *(_DWORD *)(W32GetUserSessionState(v35, v34, v36, v37) + 16240)
            && !*(_QWORD *)(W32GetUserSessionState(v39, v38, v40, v41) + 16248) )
          {
            UserSessionState = W32GetUserSessionState(v43, v42, v44, v45);
            v47 = SetRITTimer(*(_QWORD *)(UserSessionState + 16248), 20, HideMouseTrails);
            *(_QWORD *)(W32GetUserSessionState(v49, v48, v50, v51) + 16248) = v47;
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
      v53 = -1;
      v52 = 0;
      v33 = CreateProfileUserName(&v52);
      SetDesktopPattern(v33, 0);
      if ( v53 != -1 )
        PopAndFreeAlwaysW32ThreadLock(&v52);
      xxxSendNotifyMessage(a1, 21, 0, 0, 1);
      xxxRealizeDesktop(a1);
      PsGetCurrentProcessId();
      xxxSetWindowLong(a1, 0);
      PsGetCurrentThreadId();
      xxxSetWindowLong(a1, 0);
      return 0;
    case 0xFu:
      xxxBeginPaint(a1, (__int64)v54, v10, v11);
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
        LODWORD(v52) = 0x20000;
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1394);
        break;
      case 0x46u:
        if ( (*(_DWORD *)(a4 + 32) & 4) == 0 && !*(_QWORD *)(a4 + 8) )
        {
          v17 = W32GetUserSessionState(v9, v8, v10, v11);
          xxxSetThreadDesktop(0, *(_QWORD *)(v17 + 19216));
          v22 = W32GetUserSessionState(v19, v18, v20, v21);
          if ( (unsigned int)GreGetSystemPaletteUse(*(HDC *)(*(_QWORD *)(v22 + 56744) + 56LL)) != 1 )
          {
            v27 = W32GetUserSessionState(v24, v23, v25, v26);
            GreRealizeDefaultPalette(*(HDC *)(*(_QWORD *)(v27 + 56744) + 56LL));
          }
          if ( (*(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v24, v23, v25, v26) + 19216) + 48LL) & 1) != 0 )
          {
            xxxSendNotifyMessage(-1, 785, *(_QWORD *)a1, 0, 1);
            v32 = W32GetUserSessionState(v29, v28, v30, v31);
            *(_DWORD *)(*(_QWORD *)(v32 + 19216) + 48LL) &= ~1u;
          }
        }
        break;
      case 0x51u:
        if ( !*(_QWORD *)W32GetUserSessionState(v9, v8, v10, v11) || !IS_USERCRIT_OWNED_AT_ALL() )
          KeBugCheckEx(0x164u, 0x2Au, 0, 0, 0);
        *((_QWORD *)&v52 + 1) = PsGetCurrentThreadWin32Thread(v15);
        LOBYTE(v52) = 1;
        ++*(_DWORD *)(*((_QWORD *)&v52 + 1) + 28LL);
        for ( i = *((_QWORD *)a1 + 14); i; i = *(_QWORD *)(i + 88) )
          SendNotifyMessageAlways(i, 81, a3, a4, 1);
        AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)&v52);
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
0x14010bbb8  push    rbp
0x14010bbba  push    rbx
0x14010bbbb  push    rsi
0x14010bbbc  push    rdi
0x14010bbbd  push    r12
0x14010bbbf  push    r14
0x14010bbc1  lea     rbp, [rsp-2Fh]
0x14010bbc6  sub     rsp, 0C8h
0x14010bbcd  mov     rax, cs:__security_cookie
0x14010bbd4  xor     rax, rsp
0x14010bbd7  mov     [rbp+57h+var_40], rax
0x14010bbdb  mov     edi, edx
0x14010bbdd  mov     rsi, r8
0x14010bbe0  xor     edx, edx; Val
0x14010bbe2  mov     rbx, rcx
0x14010bbe5  lea     rcx, [rbp+57h+var_90]; void *
0x14010bbe9  mov     r14, r9
0x14010bbec  lea     r8d, [rdx+48h]; Size
0x14010bbf0  call    memset_0
0x14010bbf5  lea     rax, [rbp+57h+var_B0]
0x14010bbf9  mov     qword ptr [rbp+57h+var_B0], 0
0x14010bc01  mov     [rsp+0F0h+var_C0], rax
0x14010bc06  mov     r12d, 1
0x14010bc0c  mov     [rsp+0F0h+var_C8], r12d
0x14010bc11  mov     r9, r14
0x14010bc14  mov     r8, rsi
0x14010bc17  mov     word ptr [rsp+0F0h+BugCheckParameter4], 29Dh
0x14010bc1e  mov     edx, edi
0x14010bc20  mov     rcx, rbx
0x14010bc23  call    xxxValidateClassAndSize
0x14010bc28  test    eax, eax
0x14010bc2a  jnz     short loc_14010BC35
0x14010bc2c  mov     rax, qword ptr [rbp+57h+var_B0]
0x14010bc30  jmp     loc_14010BD17
0x14010bc35  cmp     qword ptr [rbx+68h], 0
0x14010bc3a  mov     eax, 80h
0x14010bc3f  jnz     short loc_14010BC5E
0x14010bc41  cmp     edi, eax
0x14010bc43  jz      loc_14010BD15
0x14010bc49  mov     r8, rsi
0x14010bc4c  mov     edx, edi
0x14010bc4e  mov     r9, r14
0x14010bc51  mov     rcx, rbx
0x14010bc54  call    xxxDefWindowProc
0x14010bc59  jmp     loc_14010BD17
0x14010bc5e  cmp     edi, eax
0x14010bc60  ja      loc_14010BF39
0x14010bc66  jz      loc_14010BD15
0x14010bc6c  mov     eax, edi
0x14010bc6e  sub     eax, r12d
0x14010bc71  jz      loc_14010BE92
0x14010bc77  sub     eax, 0Eh
0x14010bc7a  jz      loc_14010BE75
0x14010bc80  sub     eax, r12d
0x14010bc83  jz      loc_14010BD15
0x14010bc89  sub     eax, 4
0x14010bc8c  jz      loc_14010BE4C
0x14010bc92  sub     eax, r12d
0x14010bc95  jz      loc_14010BE34
0x14010bc9b  sub     eax, 25h ; '%'
0x14010bc9e  jz      loc_14010BE13
0x14010bca4  sub     eax, 0Ch
0x14010bca7  jz      loc_14010BD59
0x14010bcad  cmp     eax, 0Bh
0x14010bcb0  jnz     short loc_14010BC49
0x14010bcb2  call    cs:__imp_W32GetUserSessionState
0x14010bcb9  nop     dword ptr [rax+rax+00h]
0x14010bcbe  cmp     qword ptr [rax], 0
0x14010bcc2  jz      short loc_14010BD34
0x14010bcc4  call    ?IS_USERCRIT_OWNED_AT_ALL@@YA_NXZ; IS_USERCRIT_OWNED_AT_ALL(void)
0x14010bcc9  test    al, al
0x14010bccb  jz      short loc_14010BD34
0x14010bccd  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14010bcd4  nop     dword ptr [rax+rax+00h]
0x14010bcd9  mov     qword ptr [rbp+57h+var_B0+8], rax
0x14010bcdd  mov     byte ptr [rbp+57h+var_B0], r12b
0x14010bce1  add     [rax+1Ch], r12d
0x14010bce5  mov     rbx, [rbx+70h]
0x14010bce9  jmp     short loc_14010BD07
0x14010bceb  mov     r9, r14
0x14010bcee  mov     dword ptr [rsp+0F0h+BugCheckParameter4], r12d
0x14010bcf3  mov     r8, rsi
0x14010bcf6  mov     edx, 51h ; 'Q'
0x14010bcfb  mov     rcx, rbx
0x14010bcfe  call    ?SendNotifyMessageAlways@@YA_NPEAUtagWND@@I_K_JW4SNMAOptions@@@Z; SendNotifyMessageAlways(tagWND *,uint,unsigned __int64,__int64,SNMAOptions)
0x14010bd03  mov     rbx, [rbx+58h]
0x14010bd07  test    rbx, rbx
0x14010bd0a  jnz     short loc_14010BCEB
0x14010bd0c  lea     rcx, [rbp+57h+var_B0]; this
0x14010bd10  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x14010bd15  xor     eax, eax
0x14010bd17  mov     rcx, [rbp+57h+var_40]
0x14010bd1b  xor     rcx, rsp; StackCookie
0x14010bd1e  call    __security_check_cookie
0x14010bd23  add     rsp, 0C8h
0x14010bd2a  pop     r14
0x14010bd2c  pop     r12
0x14010bd2e  pop     rdi
0x14010bd2f  pop     rsi
0x14010bd30  pop     rbx
0x14010bd31  pop     rbp
0x14010bd32  retn
0x14010bd34  xor     r9d, r9d; BugCheckParameter3
0x14010bd37  mov     [rsp+0F0h+BugCheckParameter4], 0; BugCheckParameter4
0x14010bd40  xor     r8d, r8d; BugCheckParameter2
0x14010bd43  mov     ecx, 164h; BugCheckCode
0x14010bd48  lea     edx, [r9+2Ah]; BugCheckParameter1
0x14010bd4c  call    cs:__imp_KeBugCheckEx
0x14010bd59  mov     eax, [r14+20h]
0x14010bd5d  test    al, 4
0x14010bd5f  jnz     short loc_14010BD15
0x14010bd61  cmp     qword ptr [r14+8], 0
0x14010bd66  jnz     short loc_14010BD15
0x14010bd68  call    cs:__imp_W32GetUserSessionState
0x14010bd6f  nop     dword ptr [rax+rax+00h]
0x14010bd74  xor     ecx, ecx
0x14010bd76  mov     rdx, [rax+4B10h]
0x14010bd7d  call    xxxSetThreadDesktop
0x14010bd82  call    cs:__imp_W32GetUserSessionState
0x14010bd89  nop     dword ptr [rax+rax+00h]
0x14010bd8e  mov     rcx, [rax+0DDA8h]
0x14010bd95  mov     rcx, [rcx+38h]; HDC
0x14010bd99  call    GreGetSystemPaletteUse
0x14010bd9e  cmp     eax, r12d
0x14010bda1  jz      short loc_14010BDBF
0x14010bda3  call    cs:__imp_W32GetUserSessionState
0x14010bdaa  nop     dword ptr [rax+rax+00h]
0x14010bdaf  mov     rcx, [rax+0DDA8h]
0x14010bdb6  mov     rcx, [rcx+38h]; HDC
0x14010bdba  call    GreRealizeDefaultPalette
0x14010bdbf  call    cs:__imp_W32GetUserSessionState
0x14010bdc6  nop     dword ptr [rax+rax+00h]
0x14010bdcb  mov     rcx, [rax+4B10h]
0x14010bdd2  mov     eax, [rcx+30h]
0x14010bdd5  test    r12b, al
0x14010bdd8  jz      loc_14010BD15
0x14010bdde  mov     r8, [rbx]
0x14010bde1  xor     r9d, r9d
0x14010bde4  mov     edx, 311h
0x14010bde9  mov     dword ptr [rsp+0F0h+BugCheckParameter4], r12d
0x14010bdee  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14010bdf2  call    xxxSendNotifyMessage
0x14010bdf7  call    cs:__imp_W32GetUserSessionState
0x14010bdfe  nop     dword ptr [rax+rax+00h]
0x14010be03  mov     rcx, [rax+4B10h]
0x14010be0a  and     dword ptr [rcx+30h], 0FFFFFFFEh
0x14010be0e  jmp     loc_14010BD15
0x14010be13  mov     dword ptr [rbp+57h+var_B0], 20000h
0x14010be1a  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14010be21  mov     edx, dword ptr [rbp+57h+var_B0]
0x14010be24  mov     r8d, 572h
0x14010be2a  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14010be2f  jmp     loc_14010BD15
0x14010be34  mov     r9d, 85h
0x14010be3a  xor     r8d, r8d
0x14010be3d  xor     edx, edx
0x14010be3f  mov     rcx, rbx
0x14010be42  call    xxxRedrawWindow
0x14010be47  jmp     loc_14010BD15
0x14010be4c  mov     rcx, rbx
0x14010be4f  call    cs:__imp_IsWindowDesktopComposed
0x14010be56  nop     dword ptr [rax+rax+00h]
0x14010be5b  test    eax, eax
0x14010be5d  jnz     short loc_14010BE6D
0x14010be5f  mov     r8d, r12d
0x14010be62  mov     rdx, rsi
0x14010be65  mov     rcx, rbx
0x14010be68  call    xxxInternalPaintDesktop
0x14010be6d  mov     rax, r12
0x14010be70  jmp     loc_14010BD17
0x14010be75  lea     rdx, [rbp+57h+var_90]
0x14010be79  mov     rcx, rbx; struct tagWND *
0x14010be7c  call    xxxBeginPaint
0x14010be81  lea     rdx, [rbp+57h+var_90]
0x14010be85  mov     rcx, rbx; struct tagWND *
0x14010be88  call    xxxEndPaint
0x14010be8d  jmp     loc_14010BD15
0x14010be92  xorps   xmm0, xmm0
0x14010be95  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFFh
0x14010be9d  lea     rcx, [rbp+57h+var_B0]
0x14010bea1  movups  [rbp+57h+var_B0], xmm0
0x14010bea5  call    cs:__imp_?CreateProfileUserName@@YAPEAU_UNICODE_STRING@@PEAU?$Win32RawOptionalLockedItemAlways@UtagPROFILEUSERNAME@@$1?Win32FreePool@@YAXPEAX@Z@@@Z; CreateProfileUserName(Win32RawOptionalLockedItemAlways<tagPROFILEUSERNAME,&Win32FreePool(void *)> *)
0x14010beac  nop     dword ptr [rax+rax+00h]
0x14010beb1  mov     rcx, rax
0x14010beb4  xor     edx, edx
0x14010beb6  call    SetDesktopPattern
0x14010bebb  cmp     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFFh
0x14010bec0  jz      short loc_14010BECB
0x14010bec2  lea     rcx, [rbp+57h+var_B0]
0x14010bec6  call    PopAndFreeAlwaysW32ThreadLock
0x14010becb  xor     r9d, r9d
0x14010bece  mov     dword ptr [rsp+0F0h+BugCheckParameter4], r12d
0x14010bed3  xor     r8d, r8d
0x14010bed6  mov     rcx, rbx
0x14010bed9  lea     edx, [r9+15h]
0x14010bedd  call    xxxSendNotifyMessage
0x14010bee2  mov     rcx, rbx
0x14010bee5  call    xxxRealizeDesktop
0x14010beea  call    cs:__imp_PsGetCurrentProcessId
0x14010bef1  nop     dword ptr [rax+rax+00h]
0x14010bef6  xor     r9d, r9d
0x14010bef9  mov     dword ptr [rsp+0F0h+BugCheckParameter4], 0; int
0x14010bf01  mov     r8d, eax
0x14010bf04  xor     edx, edx
0x14010bf06  mov     rcx, rbx; struct tagWND *
0x14010bf09  call    xxxSetWindowLong
0x14010bf0e  call    cs:__imp_PsGetCurrentThreadId
0x14010bf15  nop     dword ptr [rax+rax+00h]
0x14010bf1a  xor     r9d, r9d
0x14010bf1d  mov     dword ptr [rsp+0F0h+BugCheckParameter4], 0; int
0x14010bf25  mov     r8d, eax
0x14010bf28  mov     rcx, rbx; struct tagWND *
0x14010bf2b  lea     edx, [r9+4]
0x14010bf2f  call    xxxSetWindowLong
0x14010bf34  jmp     loc_14010BD15
0x14010bf39  mov     eax, edi
0x14010bf3b  sub     eax, 0A1h
0x14010bf40  jz      loc_14010BD15
0x14010bf46  sub     eax, 71h ; 'q'
0x14010bf49  jz      loc_14010C03B
0x14010bf4f  sub     eax, 16h
0x14010bf52  jz      loc_14010C028
0x14010bf58  sub     eax, 0DBh
0x14010bf5d  jz      loc_14010C019
0x14010bf63  sub     eax, 10Ch
0x14010bf68  jz      loc_14010C00C
0x14010bf6e  sub     eax, 2
0x14010bf71  jz      loc_14010C003
0x14010bf77  cmp     eax, 0F0h
0x14010bf7c  jnz     loc_14010BC49
0x14010bf82  call    IsRemoteConnection
0x14010bf87  test    eax, eax
0x14010bf89  jnz     loc_14010BD15
0x14010bf8f  call    cs:__imp_W32GetUserSessionState
0x14010bf96  nop     dword ptr [rax+rax+00h]
0x14010bf9b  cmp     dword ptr [rax+3F70h], 0
0x14010bfa2  jz      loc_14010BD15
0x14010bfa8  call    cs:__imp_W32GetUserSessionState
0x14010bfaf  nop     dword ptr [rax+rax+00h]
0x14010bfb4  cmp     qword ptr [rax+3F78h], 0
0x14010bfbc  jnz     loc_14010BD15
0x14010bfc2  call    cs:__imp_W32GetUserSessionState
0x14010bfc9  nop     dword ptr [rax+rax+00h]
0x14010bfce  xor     r9d, r9d
0x14010bfd1  lea     r8, HideMouseTrails
0x14010bfd8  mov     rcx, [rax+3F78h]
0x14010bfdf  lea     edx, [r9+14h]
0x14010bfe3  call    SetRITTimer
0x14010bfe8  mov     rbx, rax
0x14010bfeb  call    cs:__imp_W32GetUserSessionState
0x14010bff2  nop     dword ptr [rax+rax+00h]
0x14010bff7  mov     [rax+3F78h], rbx
0x14010bffe  jmp     loc_14010BD15
0x14010c003  cmp     [rbx], rsi
0x14010c006  jz      loc_14010BD15
0x14010c00c  mov     rcx, rbx
0x14010c00f  call    xxxRealizeDesktop
0x14010c014  jmp     loc_14010BD15
0x14010c019  mov     edi, 112h
0x14010c01e  mov     esi, 0F130h
0x14010c023  jmp     loc_14010BC49
0x14010c028  mov     r8, r14
0x14010c02b  mov     rdx, rsi
0x14010c02e  mov     rcx, rbx
0x14010c031  call    xxxDWP_UpdateUIState
0x14010c036  jmp     loc_14010BD17
0x14010c03b  mov     r8d, 0F140h
0x14010c041  cmp     rsi, r8
0x14010c044  jnz     loc_14010BD15
0x14010c04a  mov     edx, 112h
0x14010c04f  jmp     loc_14010BC4E
```
