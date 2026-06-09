# CBridgeWindow::v_WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180060760`
- end: `0x180060e1b`
- name: `?v_WndProc@CBridgeWindow@@EEAA_JPEAUHWND__@@I_K_J@Z`
- size: `1723`
- prototype: `__int64(CBridgeWindow *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013f14`
- `0x180041704`
- `0x180052dfc`
- `0x180054130`
- `0x18005cb3c`
- `0x18005dcc0`
- `0x18005eed0`
- `0x18005f6d4`
- `0x18005f828`
- `0x18005fd0c`
- `0x1800601a4`
- `0x180060760`
- `0x180060e68`
- `0x180064e10`
- `0x180065070`
- `0x180065698`
- `0x1800d8854`
- `0x1800e1df4`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006086d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180060dc4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006086d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180060dc4`
- `USER32!RemovePropW` at `0x180060a27`
- `USER32!RemovePropW` at `0x180060a27`
- `USER32!ChangeWindowMessageFilterEx` at `0x180060bab`
- `USER32!ChangeWindowMessageFilterEx` at `0x180060bc6`
- `USER32!ChangeWindowMessageFilterEx` at `0x180060be1`
- `USER32!ChangeWindowMessageFilterEx` at `0x180060bab`
- `USER32!ChangeWindowMessageFilterEx` at `0x180060bc6`
- `USER32!ChangeWindowMessageFilterEx` at `0x180060be1`
- `USER32!SetPropW` at `0x180060b5d`
- `USER32!SetPropW` at `0x180060b5d`
- `USER32!GetAncestor` at `0x180060acf`
- `USER32!GetAncestor` at `0x180060acf`
- `USER32!GetWindow` at `0x180060b44`
- `USER32!GetWindow` at `0x180060b44`
- `USER32!SetWindowPos` at `0x180060918`
- `USER32!SetWindowPos` at `0x180060918`
- `USER32!ShowWindow` at `0x180060b85`
- `USER32!ShowWindow` at `0x180060b85`
- `USER32!DestroyWindow` at `0x180060d6e`
- `USER32!DestroyWindow` at `0x180060d6e`
- `USER32!DefWindowProcW` at `0x180060885`
- `USER32!DefWindowProcW` at `0x180060885`
- `SHELL32!SHGetPropertyStoreForWindow` at `0x180060a6f`
- `SHELL32!SHGetPropertyStoreForWindow` at `0x180060b06`
- `SHELL32!SHGetPropertyStoreForWindow` at `0x180060a6f`
- `SHELL32!SHGetPropertyStoreForWindow` at `0x180060b06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060abb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060b30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060abb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060b30`
- `UIAutomationCore!UiaReturnRawElementProvider` at `0x18006099c`
- `UIAutomationCore!UiaReturnRawElementProvider` at `0x18006099c`
- `DUI70!?DestroyMsg@NativeHWNDHost@DirectUI@@SAIXZ` at `0x180060c69`
- `DUI70!?DestroyMsg@NativeHWNDHost@DirectUI@@SAIXZ` at `0x180060c69`

## pseudocode

```c
LRESULT __fastcall CBridgeWindow::v_WndProc(CBridgeWindow *this, HWND a2, UINT a3, unsigned __int64 a4, LPARAM lParam)
{
  LONG_PTR v5; // rbx
  CBridgeWindow *v10; // rcx
  __int64 v11; // rcx
  void *v12; // rcx
  __int64 v13; // r8
  int v14; // edx
  int v15; // ecx
  HWND v16; // rcx
  const struct tagWINDOWPOS *const v17; // r8
  UIBridgeWindow *v18; // rax
  char v19; // r14
  UIBridgeWindow *v20; // rcx
  CallerIdentity *Ancestor; // rax
  unsigned __int16 **v22; // r8
  __int64 v23; // rdx
  HWND Window; // rax
  int v25; // ebx
  UIBridgeWindow *v26; // rcx
  unsigned int v27; // r15d
  UIBridgeWindow *v28; // rcx
  void *v29; // rcx
  unsigned int v30; // edx
  void *ppv; // [rsp+40h] [rbp-31h] BYREF
  IRawElementProviderSimple *el; // [rsp+48h] [rbp-29h] BYREF
  unsigned __int64 v34; // [rsp+50h] [rbp-21h] BYREF
  UIBridgeWindow *v35[2]; // [rsp+58h] [rbp-19h] BYREF
  __int64 v36; // [rsp+68h] [rbp-9h]

  v5 = 0;
  v34 = -1;
  if ( a3 > 0x32A )
  {
    switch ( a3 )
    {
      case 0x400u:
        v30 = 256;
        break;
      case 0x401u:
        v30 = 260;
        break;
      case 0x402u:
        v30 = 274;
        break;
      case 0x403u:
        v27 = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_bb6e679c4fb53f067d151a3e1aef5ec7_Traceguids,
            a2,
            *((_QWORD *)this + 20) != 0);
        }
        if ( *((_QWORD *)this + 12) && (int)CBridgeWindow::_GetHostId((CBridgeWindow *)((char *)this - 104), &v34) >= 0 )
          (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int64, _QWORD, int))(**((_QWORD **)this + 28) + 24LL))(
            *((_QWORD *)this + 28),
            *((_QWORD *)this + 12),
            v34,
            *((_QWORD *)this + 11),
            1);
        v28 = (UIBridgeWindow *)*((_QWORD *)this + 20);
        *((_QWORD *)this + 11) = 0;
        if ( v28 )
          UIBridgeWindow::HideSplashScreen(v28);
        if ( !*((_BYTE *)this + 42) )
        {
          v27 = 1;
          CBridgeWindow::_ShowCrashText((CBridgeWindow *)((char *)this - 104));
        }
        DestroyWindow(*((HWND *)this + 1));
        ppv = 0;
        if ( *((_QWORD *)this + 25)
          && (int)WeakRefAs<Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IHostedApplicationEventSink>>>(
                    (char *)this + 200,
                    &ppv) >= 0
          && ppv )
        {
          (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppv + 40LL))(ppv, v27);
        }
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
        v29 = (void *)*((_QWORD *)this + 34);
        if ( v29 )
          SetEvent(v29);
        return v5;
      case 0x404u:
        CBridgeWindow::_CloakWindow((CBridgeWindow *)((char *)this - 104), 1);
        *((_BYTE *)this + 38) = 1;
        return v5;
      default:
        goto LABEL_56;
    }
    return (int)CBridgeWindow::_TranslateAcceleratorFromHostedWindow(
                  (CBridgeWindow *)((char *)this - 104),
                  v30,
                  a4,
                  lParam);
  }
  switch ( a3 )
  {
    case 0x32Au:
      if ( lParam != 3 )
      {
        if ( *((_BYTE *)this + 40) )
        {
          CBridgeWindow::_RemoveOwner((CBridgeWindow *)((char *)this - 104), 0);
          *((_BYTE *)this + 40) = 0;
        }
        else if ( *((_BYTE *)this + 41) )
        {
          v26 = (UIBridgeWindow *)*((_QWORD *)this + 20);
          if ( v26 )
            UIBridgeWindow::HideSplashScreen(v26);
          *((_BYTE *)this + 41) = 0;
          CBridgeWindow::_MaybeNotifySplashScreenDismissed((CBridgeWindow *)((char *)this - 104));
        }
      }
      return DefWindowProcW(a2, a3, a4, lParam);
    case 1u:
      el = 0;
      CoTaskMemFree(0);
      Ancestor = (CallerIdentity *)GetAncestor(a2, 3u);
      if ( CallerIdentity::GetImmersiveAppIdFromWindow(Ancestor, (HWND)&el, v22) >= 0 )
      {
        ppv = 0;
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
        if ( SHGetPropertyStoreForWindow(a2, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv) >= 0 )
          IPropertyStore_SetString(ppv, v23, el);
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
      }
      CoTaskMemFree(el);
      Window = GetWindow(a2, 4u);
      SetPropW(a2, L"Shell_Logical_Owner_Window_Prop", Window);
      v25 = CBridgeWindow::_CloakWindow((CBridgeWindow *)((char *)this - 104), 1);
      ShowWindow(*((HWND *)this + 1), 4);
      CBridgeWindow::_RemoveOwner((CBridgeWindow *)((char *)this - 104), v25);
      ChangeWindowMessageFilterEx(*((HWND *)this + 1), 0x400u, 1u, 0);
      ChangeWindowMessageFilterEx(*((HWND *)this + 1), 0x401u, 1u, 0);
      ChangeWindowMessageFilterEx(*((HWND *)this + 1), 0x402u, 1u, 0);
      return DefWindowProcW(a2, a3, a4, lParam);
    case 2u:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_bb6e679c4fb53f067d151a3e1aef5ec7_Traceguids,
          a2,
          *((_QWORD *)this + 20) != 0);
      }
      RemovePropW(a2, L"Shell_Logical_Owner_Window_Prop");
      v20 = (UIBridgeWindow *)*((_QWORD *)this + 20);
      if ( v20 )
        UIBridgeWindow::SetBridgeWindow(v20, 0);
      if ( *((_QWORD *)this + 10) == *((_QWORD *)this + 1) )
        *((_QWORD *)this + 10) = 0;
      ppv = 0;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
      if ( SHGetPropertyStoreForWindow(a2, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv) >= 0 )
      {
        v36 = 0;
        *(_OWORD *)v35 = 0;
        (*(void (__fastcall **)(void *, const PROPERTYKEY *, UIBridgeWindow **))(*(_QWORD *)ppv + 48LL))(
          ppv,
          &PKEY_AppUserModel_ID,
          v35);
      }
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
      return DefWindowProcW(a2, a3, a4, lParam);
    case 0x3Du:
      v18 = (UIBridgeWindow *)*((_QWORD *)this + 20);
      v19 = 0;
      ppv = 0;
      el = 0;
      v35[0] = v18;
      if ( v18 )
      {
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
        if ( (int)UIBridgeWindow::GetElementProvider(v35[0], (struct IRawElementProviderFragment **)&ppv) >= 0 )
        {
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&el);
          if ( (int)CBridgeWindowRawElementProvider::Make(
                      (struct IRawElementProviderFragment *)ppv,
                      *((HWND *)this + 1),
                      &GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c,
                      (void **)&el) >= 0 )
          {
            v5 = UiaReturnRawElementProvider(a2, a4, lParam, el);
            v19 = 1;
          }
        }
      }
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&el);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
      if ( !v19 )
        return DefWindowProcW(a2, a3, a4, lParam);
      return v5;
    case 0x46u:
      v13 = *((_QWORD *)this + 30);
      if ( v13 )
      {
        if ( (*(_BYTE *)(lParam + 32) & 3) != 3 )
        {
          v14 = *(_DWORD *)(lParam + 20);
          LODWORD(v35[0]) = *(_DWORD *)(lParam + 16);
          LODWORD(v35[1]) = *(_DWORD *)(lParam + 24) + LODWORD(v35[0]);
          v15 = *(_DWORD *)(lParam + 28);
          HIDWORD(v35[0]) = v14;
          HIDWORD(v35[1]) = v14 + v15;
          (*(void (__fastcall **)(__int64, UIBridgeWindow **))(*(_QWORD *)v13 + 24LL))(v13, v35);
        }
      }
      else
      {
        v16 = (HWND)*((_QWORD *)this + 11);
        if ( v16 )
        {
          SetWindowPos(
            v16,
            *(HWND *)(lParam + 8),
            *(_DWORD *)(lParam + 16),
            *(_DWORD *)(lParam + 20),
            *(_DWORD *)(lParam + 24),
            *(_DWORD *)(lParam + 28),
            *(_DWORD *)(lParam + 32) & 3 | 0x4454);
          ImmersiveOwnedWindowHelper::RepositionOwnedWindows(
            *((ImmersiveOwnedWindowHelper **)this + 11),
            (HWND)lParam,
            v17);
        }
      }
      return DefWindowProcW(a2, a3, a4, lParam);
    case 0x270u:
      v10 = (CBridgeWindow *)((char *)this - 104);
      if ( *((_QWORD *)v10 + 25) )
      {
        if ( (lParam & 8) == 0 && (int)CBridgeWindow::_GetHostId(v10, &v34) >= 0 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int64, _QWORD, int))(**((_QWORD **)this + 28) + 24LL))(
            *((_QWORD *)this + 28),
            *((_QWORD *)this + 12),
            v34,
            *((_QWORD *)this + 11),
            !(lParam & 1) + 2);
          v11 = *((_QWORD *)this + 30);
          if ( v11 )
            (*(void (__fastcall **)(__int64, LPARAM))(*(_QWORD *)v11 + 32LL))(v11, lParam & 1);
        }
      }
      if ( (lParam & 1) == 0 )
      {
        v12 = (void *)*((_QWORD *)this + 35);
        if ( v12 )
          SetEvent(v12);
      }
      return DefWindowProcW(a2, a3, a4, lParam);
  }
LABEL_56:
  if ( a3 != (unsigned int)DirectUI::NativeHWNDHost::DestroyMsg() )
    return DefWindowProcW(a2, a3, a4, lParam);
  if ( *((_BYTE *)this + 36) )
    (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this - 7) + 112LL))((char *)this - 56, 1);
  return v5;
}

```

## disassembly

```asm
0x180060760  push    rbp
0x180060762  push    rbx
0x180060763  push    rsi
0x180060764  push    rdi
0x180060765  push    r12
0x180060767  push    r13
0x180060769  push    r14
0x18006076b  push    r15
0x18006076d  lea     rbp, [rsp-17h]
0x180060772  sub     rsp, 88h
0x180060779  mov     rax, cs:__security_cookie
0x180060780  xor     rax, rsp
0x180060783  mov     [rbp+4Fh+var_50], rax
0x180060787  mov     r15, [rbp+4Fh+lParam]
0x18006078b  xor     ebx, ebx
0x18006078d  mov     eax, 32Ah
0x180060792  mov     [rbp+4Fh+var_70], 0FFFFFFFFFFFFFFFFh
0x18006079a  mov     rdi, r9
0x18006079d  mov     r13d, r8d
0x1800607a0  mov     r12, rdx
0x1800607a3  mov     rsi, rcx
0x1800607a6  cmp     r8d, eax
0x1800607a9  ja      loc_180060C3F
0x1800607af  jz      loc_180060BF2
0x1800607b5  mov     eax, r8d
0x1800607b8  sub     eax, 1
0x1800607bb  jz      loc_180060AB5
0x1800607c1  sub     eax, 1
0x1800607c4  jz      loc_1800609D1
0x1800607ca  sub     eax, 3Bh ; ';'
0x1800607cd  jz      loc_180060935
0x1800607d3  sub     eax, 9
0x1800607d6  jz      loc_180060899
0x1800607dc  cmp     eax, 22Ah
0x1800607e1  jnz     loc_180060C69
0x1800607e7  add     rcx, 0FFFFFFFFFFFFFF98h; this
0x1800607eb  lea     r14d, [rbx+1]
0x1800607ef  cmp     [rcx+0C8h], rbx
0x1800607f6  jz      short loc_18006085C
0x1800607f8  test    r15b, 8
0x1800607fc  jnz     short loc_18006085C
0x1800607fe  lea     rdx, [rbp+4Fh+var_70]; unsigned __int64 *
0x180060802  call    ?_GetHostId@CBridgeWindow@@AEAAJPEA_K@Z; CBridgeWindow::_GetHostId(unsigned __int64 *)
0x180060807  test    eax, eax
0x180060809  js      short loc_18006085C
0x18006080b  mov     r10, [rsi+0E0h]
0x180060812  mov     al, r15b
0x180060815  mov     r9, [rsi+58h]
0x180060819  and     al, r14b
0x18006081c  mov     r8, [rbp+4Fh+var_70]
0x180060820  mov     rdx, [rsi+60h]
0x180060824  movzx   ebx, al
0x180060827  mov     rax, [r10]
0x18006082a  mov     ecx, ebx
0x18006082c  xor     ecx, r14d
0x18006082f  add     ecx, 2
0x180060832  mov     [rsp+0C0h+var_A0], ecx
0x180060836  mov     rcx, r10
0x180060839  mov     rax, [rax+18h]
0x18006083d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060842  mov     rcx, [rsi+0F0h]
0x180060849  test    rcx, rcx
0x18006084c  jz      short loc_18006085C
0x18006084e  mov     rax, [rcx]
0x180060851  mov     edx, ebx
0x180060853  mov     rax, [rax+20h]
0x180060857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006085c  test    r14b, r15b
0x18006085f  jnz     short loc_180060879
0x180060861  mov     rcx, [rsi+118h]; hEvent
0x180060868  test    rcx, rcx
0x18006086b  jz      short loc_180060879
0x18006086d  call    cs:__imp_SetEvent
0x180060874  nop     dword ptr [rax+rax+00h]
0x180060879  mov     r9, r15; lParam
0x18006087c  mov     r8, rdi; wParam
0x18006087f  mov     edx, r13d; Msg
0x180060882  mov     rcx, r12; hWnd
0x180060885  call    cs:__imp_DefWindowProcW
0x18006088c  nop     dword ptr [rax+rax+00h]
0x180060891  mov     rbx, rax
0x180060894  jmp     loc_180060DF7
0x180060899  mov     r8, [rcx+0F0h]
0x1800608a0  test    r8, r8
0x1800608a3  jz      short loc_1800608E3
0x1800608a5  mov     eax, [r15+20h]
0x1800608a9  and     eax, 3
0x1800608ac  cmp     al, 3
0x1800608ae  jz      short loc_180060879
0x1800608b0  mov     ecx, [r15+10h]
0x1800608b4  mov     edx, [r15+14h]
0x1800608b8  mov     dword ptr [rbp+4Fh+var_68], ecx
0x1800608bb  add     ecx, [r15+18h]
0x1800608bf  mov     dword ptr [rbp+4Fh+var_68+8], ecx
0x1800608c2  mov     ecx, [r15+1Ch]
0x1800608c6  add     ecx, edx
0x1800608c8  mov     dword ptr [rbp+4Fh+var_68+4], edx
0x1800608cb  mov     dword ptr [rbp+4Fh+var_68+0Ch], ecx
0x1800608ce  lea     rdx, [rbp+4Fh+var_68]
0x1800608d2  mov     rax, [r8]
0x1800608d5  mov     rcx, r8
0x1800608d8  mov     rax, [rax+18h]
0x1800608dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800608e1  jmp     short loc_180060879
0x1800608e3  mov     rcx, [rcx+58h]; hWnd
0x1800608e7  test    rcx, rcx
0x1800608ea  jz      short loc_180060879
0x1800608ec  mov     eax, [r15+20h]
0x1800608f0  mov     r9d, [r15+14h]; Y
0x1800608f4  and     eax, 3
0x1800608f7  mov     r8d, [r15+10h]; X
0x1800608fb  or      eax, 4454h
0x180060900  mov     rdx, [r15+8]; hWndInsertAfter
0x180060904  mov     [rsp+0C0h+uFlags], eax; uFlags
0x180060908  mov     eax, [r15+1Ch]
0x18006090c  mov     [rsp+0C0h+cy], eax; cy
0x180060910  mov     eax, [r15+18h]
0x180060914  mov     [rsp+0C0h+var_A0], eax; cx
0x180060918  call    cs:__imp_SetWindowPos
0x18006091f  nop     dword ptr [rax+rax+00h]
0x180060924  mov     rcx, [rsi+58h]; this
0x180060928  mov     rdx, r15; HWND
0x18006092b  call    ?RepositionOwnedWindows@ImmersiveOwnedWindowHelper@@YAJPEAUHWND__@@QEBUtagWINDOWPOS@@@Z; ImmersiveOwnedWindowHelper::RepositionOwnedWindows(HWND__ *,tagWINDOWPOS const * const)
0x180060930  jmp     loc_180060879
0x180060935  mov     rax, [rcx+0A0h]
0x18006093c  xor     r14b, r14b
0x18006093f  mov     [rbp+4Fh+ppv], rbx
0x180060943  mov     [rbp+4Fh+el], rbx
0x180060947  mov     [rbp+4Fh+var_68], rax
0x18006094b  test    rax, rax
0x18006094e  jz      short loc_1800609B1
0x180060950  lea     rcx, [rbp+4Fh+ppv]
0x180060954  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180060959  mov     rcx, [rbp+4Fh+var_68]; this
0x18006095d  lea     rdx, [rbp+4Fh+ppv]; struct IRawElementProviderFragment **
0x180060961  call    ?GetElementProvider@UIBridgeWindow@@QEAAJPEAPEAUIRawElementProviderFragment@@@Z; UIBridgeWindow::GetElementProvider(IRawElementProviderFragment * *)
0x180060966  test    eax, eax
0x180060968  js      short loc_1800609B1
0x18006096a  lea     rcx, [rbp+4Fh+el]
0x18006096e  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180060973  mov     rdx, [rsi+8]; HWND
0x180060977  lea     r9, [rbp+4Fh+el]; void **
0x18006097b  mov     rcx, [rbp+4Fh+ppv]; struct IRawElementProviderFragment *
0x18006097f  lea     r8, _GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c; struct _GUID *
0x180060986  call    ?Make@CBridgeWindowRawElementProvider@@SAJPEAUIRawElementProviderFragment@@PEAUHWND__@@AEBU_GUID@@PEAPEAX@Z; CBridgeWindowRawElementProvider::Make(IRawElementProviderFragment *,HWND__ *,_GUID const &,void * *)
0x18006098b  test    eax, eax
0x18006098d  js      short loc_1800609B1
0x18006098f  mov     r9, [rbp+4Fh+el]; el
0x180060993  mov     r8, r15; lParam
0x180060996  mov     rdx, rdi; wParam
0x180060999  mov     rcx, r12; hwnd
0x18006099c  call    cs:__imp_UiaReturnRawElementProvider
0x1800609a3  nop     dword ptr [rax+rax+00h]
0x1800609a8  mov     rbx, rax
0x1800609ab  mov     r14d, 1
0x1800609b1  lea     rcx, [rbp+4Fh+el]
0x1800609b5  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800609ba  lea     rcx, [rbp+4Fh+ppv]
0x1800609be  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800609c3  test    r14b, r14b
0x1800609c6  jnz     loc_180060DF7
0x1800609cc  jmp     loc_180060879
0x1800609d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800609d8  lea     rax, WPP_GLOBAL_Control
0x1800609df  cmp     rcx, rax
0x1800609e2  jz      short loc_180060A1D
0x1800609e4  mov     r14d, 1
0x1800609ea  test    [rcx+1Ch], r14b
0x1800609ee  jz      short loc_180060A1D
0x1800609f0  cmp     byte ptr [rcx+19h], 4
0x1800609f4  jb      short loc_180060A1D
0x1800609f6  mov     rcx, [rcx+10h]
0x1800609fa  lea     edx, [r14+12h]
0x1800609fe  xor     eax, eax
0x180060a00  lea     r8, WPP_bb6e679c4fb53f067d151a3e1aef5ec7_Traceguids
0x180060a07  cmp     [rsi+0A0h], rax
0x180060a0e  mov     r9, r12
0x180060a11  setnz   al
0x180060a14  mov     [rsp+0C0h+var_A0], eax
0x180060a18  call    WPP_SF_qd
0x180060a1d  lea     rdx, String; "Shell_Logical_Owner_Window_Prop"
0x180060a24  mov     rcx, r12; hWnd
0x180060a27  call    cs:__imp_RemovePropW
0x180060a2e  nop     dword ptr [rax+rax+00h]
0x180060a33  mov     rcx, [rsi+0A0h]; this
0x180060a3a  test    rcx, rcx
0x180060a3d  jz      short loc_180060A46
0x180060a3f  xor     edx, edx; HWND
0x180060a41  call    ?SetBridgeWindow@UIBridgeWindow@@QEAAXPEAUHWND__@@@Z; UIBridgeWindow::SetBridgeWindow(HWND__ *)
0x180060a46  mov     rax, [rsi+8]
0x180060a4a  cmp     [rsi+50h], rax
0x180060a4e  jnz     short loc_180060A54
0x180060a50  mov     [rsi+50h], rbx
0x180060a54  lea     rcx, [rbp+4Fh+ppv]
0x180060a58  mov     [rbp+4Fh+ppv], rbx
0x180060a5c  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180060a61  lea     r8, [rbp+4Fh+ppv]; ppv
0x180060a65  mov     rcx, r12; hwnd
0x180060a68  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180060a6f  call    cs:__imp_SHGetPropertyStoreForWindow
0x180060a76  nop     dword ptr [rax+rax+00h]
0x180060a7b  test    eax, eax
0x180060a7d  js      short loc_180060AA7
0x180060a7f  mov     rcx, [rbp+4Fh+ppv]
0x180060a83  lea     r8, [rbp+4Fh+var_68]
0x180060a87  xor     eax, eax
0x180060a89  lea     rdx, PKEY_AppUserModel_ID
0x180060a90  mov     [rbp+4Fh+var_58], rax
0x180060a94  xorps   xmm0, xmm0
0x180060a97  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x180060a9b  mov     rax, [rcx]
0x180060a9e  mov     rax, [rax+30h]
0x180060aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060aa7  lea     rcx, [rbp+4Fh+ppv]
0x180060aab  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180060ab0  jmp     loc_180060879
0x180060ab5  xor     ecx, ecx; pv
0x180060ab7  mov     [rbp+4Fh+el], rbx
0x180060abb  call    cs:__imp_CoTaskMemFree
0x180060ac2  nop     dword ptr [rax+rax+00h]
0x180060ac7  mov     edx, 3; gaFlags
0x180060acc  mov     rcx, r12; hwnd
0x180060acf  call    cs:__imp_GetAncestor
0x180060ad6  nop     dword ptr [rax+rax+00h]
0x180060adb  mov     rcx, rax; this
0x180060ade  lea     rdx, [rbp+4Fh+el]; HWND
0x180060ae2  call    ?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)
0x180060ae7  test    eax, eax
0x180060ae9  js      short loc_180060B2C
0x180060aeb  lea     rcx, [rbp+4Fh+ppv]
0x180060aef  mov     [rbp+4Fh+ppv], rbx
0x180060af3  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180060af8  lea     r8, [rbp+4Fh+ppv]; ppv
0x180060afc  mov     rcx, r12; hwnd
0x180060aff  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180060b06  call    cs:__imp_SHGetPropertyStoreForWindow
0x180060b0d  nop     dword ptr [rax+rax+00h]
0x180060b12  test    eax, eax
0x180060b14  js      short loc_180060B23
0x180060b16  mov     r8, [rbp+4Fh+el]
0x180060b1a  mov     rcx, [rbp+4Fh+ppv]
0x180060b1e  call    IPropertyStore_SetString
0x180060b23  lea     rcx, [rbp+4Fh+ppv]
0x180060b27  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180060b2c  mov     rcx, [rbp+4Fh+el]; pv
0x180060b30  call    cs:__imp_CoTaskMemFree
0x180060b37  nop     dword ptr [rax+rax+00h]
0x180060b3c  mov     edx, 4; uCmd
0x180060b41  mov     rcx, r12; hWnd
0x180060b44  call    cs:__imp_GetWindow
0x180060b4b  nop     dword ptr [rax+rax+00h]
0x180060b50  lea     rdx, String; "Shell_Logical_Owner_Window_Prop"
0x180060b57  mov     rcx, r12; hWnd
0x180060b5a  mov     r8, rax; hData
0x180060b5d  call    cs:__imp_SetPropW
0x180060b64  nop     dword ptr [rax+rax+00h]
0x180060b69  mov     r14d, 1
0x180060b6f  lea     rcx, [rsi-68h]; this
0x180060b73  mov     edx, r14d; int
0x180060b76  call    ?_CloakWindow@CBridgeWindow@@AEAAJH@Z; CBridgeWindow::_CloakWindow(int)
0x180060b7b  mov     rcx, [rsi+8]; hWnd
0x180060b7f  lea     edx, [r14+3]; nCmdShow
0x180060b83  mov     ebx, eax
0x180060b85  call    cs:__imp_ShowWindow
0x180060b8c  nop     dword ptr [rax+rax+00h]
0x180060b91  mov     edx, ebx; int
0x180060b93  lea     rcx, [rsi-68h]; this
0x180060b97  call    ?_RemoveOwner@CBridgeWindow@@AEAAXJ@Z; CBridgeWindow::_RemoveOwner(long)
0x180060b9c  mov     rcx, [rsi+8]; hwnd
0x180060ba0  xor     r9d, r9d; pChangeFilterStruct
0x180060ba3  mov     r8d, r14d; action
0x180060ba6  mov     edx, 400h; message
0x180060bab  call    cs:__imp_ChangeWindowMessageFilterEx
0x180060bb2  nop     dword ptr [rax+rax+00h]
0x180060bb7  mov     rcx, [rsi+8]; hwnd
0x180060bbb  xor     r9d, r9d; pChangeFilterStruct
0x180060bbe  mov     r8d, r14d; action
0x180060bc1  mov     edx, 401h; message
0x180060bc6  call    cs:__imp_ChangeWindowMessageFilterEx
0x180060bcd  nop     dword ptr [rax+rax+00h]
0x180060bd2  mov     rcx, [rsi+8]; hwnd
0x180060bd6  xor     r9d, r9d; pChangeFilterStruct
0x180060bd9  mov     r8d, r14d; action
0x180060bdc  mov     edx, 402h; message
0x180060be1  call    cs:__imp_ChangeWindowMessageFilterEx
0x180060be8  nop     dword ptr [rax+rax+00h]
0x180060bed  jmp     loc_180060879
0x180060bf2  cmp     r15, 3
0x180060bf6  jz      loc_180060879
0x180060bfc  cmp     [rcx+28h], bl
0x180060bff  jz      short loc_180060C14
0x180060c01  xor     edx, edx; int
0x180060c03  add     rcx, 0FFFFFFFFFFFFFF98h; this
0x180060c07  call    ?_RemoveOwner@CBridgeWindow@@AEAAXJ@Z; CBridgeWindow::_RemoveOwner(long)
0x180060c0c  mov     [rsi+28h], bl
0x180060c0f  jmp     loc_180060879
0x180060c14  cmp     [rcx+29h], bl
0x180060c17  jz      loc_180060879
0x180060c1d  mov     rcx, [rcx+0A0h]; this
0x180060c24  test    rcx, rcx
  ... truncated ...
```
