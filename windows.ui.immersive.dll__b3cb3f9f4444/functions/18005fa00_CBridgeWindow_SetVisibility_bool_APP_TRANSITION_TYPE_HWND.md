# CBridgeWindow::_SetVisibility(bool,APP_TRANSITION_TYPE,HWND__ *)

- ea: `0x18005fa00`
- end: `0x18005fd06`
- name: `?_SetVisibility@CBridgeWindow@@AEAAX_NW4APP_TRANSITION_TYPE@@PEAUHWND__@@@Z`
- size: `774`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005d980`
- `0x18005f758`

## callees

- `0x180019390`
- `0x180023f60`
- `0x180028c08`
- `0x18002da84`
- `0x18005d040`
- `0x18005ecdc`
- `0x18005eed0`
- `0x18005f6d4`
- `0x18005f828`
- `0x18005f938`
- `0x18005fa00`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x18005fc40`
- `USER32!SystemParametersInfoW` at `0x18005fc40`
- `USER32!SendMessageW` at `0x18005fbb4`
- `USER32!SendMessageW` at `0x18005fbb4`
- `USER32!PostMessageW` at `0x18005fcd9`
- `USER32!PostMessageW` at `0x18005fcd9`
- `ext-ms-win-ntuser-windowstation-l1-1-1!OpenInputDesktop` at `0x18005fa4b`
- `ext-ms-win-ntuser-windowstation-l1-1-1!OpenInputDesktop` at `0x18005fa4b`
- `dwmapi!__imp_DwmpTransitionWindow` at `0x18005fb75`
- `dwmapi!__imp_DwmpTransitionWindow` at `0x18005fb94`
- `dwmapi!__imp_DwmpTransitionWindow` at `0x18005fb75`
- `dwmapi!__imp_DwmpTransitionWindow` at `0x18005fb94`
- `dwmapi!__imp_DwmpEndTransitionRequest` at `0x18005fbe5`
- `dwmapi!__imp_DwmpEndTransitionRequest` at `0x18005fbe5`
- `dwmapi!__imp_DwmpBeginTransitionRequestWithGUID` at `0x18005fafe`
- `dwmapi!__imp_DwmpBeginTransitionRequestWithGUID` at `0x18005fafe`

## pseudocode

```c
void __fastcall CBridgeWindow::_SetVisibility(__int64 a1, unsigned __int8 a2, int a3, HWND a4)
{
  char v4; // r13
  int v5; // r14d
  char v9; // di
  HWND v10; // r8
  char v11; // al
  unsigned int v12; // esi
  __int64 *v13; // rdx
  int v14; // ebp
  int v15; // ecx
  char v16; // al
  int v17; // edx
  char v18; // r12
  int v19; // r15d
  bool v20; // r15
  HWND v21; // rcx
  _BYTE v22[88]; // [rsp+20h] [rbp-58h] BYREF
  int pvParam; // [rsp+80h] [rbp+8h] BYREF
  char v24; // [rsp+88h] [rbp+10h]
  int v25; // [rsp+90h] [rbp+18h]
  HDESK v26; // [rsp+98h] [rbp+20h] BYREF

  v25 = a3;
  v4 = 0;
  v5 = a2;
  v9 = 1;
  if ( *(_QWORD *)(a1 + 240) )
  {
    wil::AcquireSRWLockExclusive(v22, &g_desktopSwitchLock);
    v26 = OpenInputDesktop(0, 0, 1u);
    g_trackedDesktopStateEverEnteredSecureDesktop = v26 == 0;
    wil::details::unique_storage<wil::details::resource_policy<HDESK__ *,int (*)(HDESK__ *),&int CloseDesktop(HDESK__ *),wistd::integral_constant<unsigned __int64,0>,HDESK__ *,HDESK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HDESK__ *,int (*)(HDESK__ *),&int CloseDesktop(HDESK__ *),wistd::integral_constant<unsigned __int64,0>,HDESK__ *,HDESK__ *,0,std::nullptr_t>>(&v26);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v22);
  }
  if ( (_BYTE)v5 )
  {
    if ( (int)_SetOwnerWindow(*(HWND *)(a1 + 112), *(HWND *)(a1 + 176)) >= 0 )
    {
      v10 = *(HWND *)(a1 + 192);
      if ( v10 )
      {
        if ( *(_BYTE *)(a1 + 147) )
          CBridgeWindow::_AttachOrDetachInputQueues((CBridgeWindow *)a1, 1, v10, 0);
      }
    }
  }
  if ( *(_BYTE *)(a1 + 142) || (v11 = 1, a3) )
    v11 = 0;
  v24 = v11;
  if ( a4 )
  {
    v12 = 75;
    v13 = qword_180109A50;
  }
  else
  {
    v13 = 0;
    v12 = (v5 ^ 1) + 4;
  }
  if ( v11 )
  {
    v14 = DwmpBeginTransitionRequestWithGUID(v12, v13);
    if ( v14 >= 0 )
    {
      switch ( v12 )
      {
        case 4u:
          v15 = 25;
          break;
        case 5u:
          v15 = 26;
          break;
        case 0x4Bu:
          v15 = v5 + 18;
          break;
        default:
          v15 = 4095;
          break;
      }
      *(_BYTE *)(a1 + 144) = v5 ^ 1;
      if ( !(_BYTE)v5 || (v16 = 1, v12 != 4) )
        v16 = 0;
      *(_BYTE *)(a1 + 145) = v16;
      v17 = 272760832;
      if ( v15 != 25 )
        v17 = 272629760;
      v14 = DwmpTransitionWindow(*(_QWORD *)(a1 + 112), v15 | (unsigned int)v17);
      if ( v14 >= 0 )
      {
        if ( a4 )
        {
          v14 = DwmpTransitionWindow(a4, 272629778);
          if ( v14 >= 0 )
            SendMessageW(a4, 0x404u, 0, 0);
        }
      }
    }
  }
  else
  {
    v14 = -2147467259;
  }
  v18 = v5 ^ 1;
  v19 = CBridgeWindow::_CloakWindow((CBridgeWindow *)a1, (unsigned __int8)v5 ^ 1u);
  if ( v14 >= 0 )
    DwmpEndTransitionRequest(v12);
  if ( !(_BYTE)v5 && (v24 && v14 < 0 || v25 == 1 || v19 < 0) )
  {
    *(_BYTE *)(a1 + 144) = 0;
    v4 = 1;
    CBridgeWindow::_RemoveOwner((CBridgeWindow *)a1, v19);
  }
  pvParam = 1;
  SystemParametersInfoW(0x1042u, 0, &pvParam, 0);
  if ( *(_QWORD *)(a1 + 240) )
  {
    Microsoft::WRL::Wrappers::SRWLock::LockShared(&v26, &g_desktopSwitchLock);
    v20 = g_trackedDesktopStateEverEnteredSecureDesktop;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
  }
  else
  {
    v20 = 0;
  }
  if ( v24 && (!pvParam && v14 < 0 || v20) )
  {
    if ( v4 )
      v18 = *(_BYTE *)(a1 + 144);
    *(_BYTE *)(a1 + 144) = v18;
    if ( !(_BYTE)v5 || v12 != 4 )
      v9 = 0;
    v21 = *(HWND *)(a1 + 112);
    *(_BYTE *)(a1 + 145) = v9;
    PostMessageW(v21, 0x32Au, 0, 2);
  }
  *(_BYTE *)(a1 + 142) = 0;
  CBridgeWindow::_MaybeNotifySplashScreenDismissed((CBridgeWindow *)a1);
}

```

## disassembly

```asm
0x18005fa00  mov     [rsp+arg_10], r8d
0x18005fa05  push    rbx
0x18005fa06  push    rbp
0x18005fa07  push    rsi
0x18005fa08  push    rdi
0x18005fa09  push    r12
0x18005fa0b  push    r13
0x18005fa0d  push    r14
0x18005fa0f  push    r15
0x18005fa11  sub     rsp, 38h
0x18005fa15  xor     r13d, r13d
0x18005fa18  movzx   r14d, dl
0x18005fa1c  mov     r15, r9
0x18005fa1f  mov     esi, r8d
0x18005fa22  mov     rbx, rcx
0x18005fa25  mov     edi, 1
0x18005fa2a  cmp     [rcx+0F0h], r13
0x18005fa31  jz      short loc_18005FA80
0x18005fa33  lea     rdx, ?g_desktopSwitchLock@@3Vsrwlock@wil@@A; wil::srwlock g_desktopSwitchLock
0x18005fa3a  lea     rcx, [rsp+78h+var_58]
0x18005fa3f  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18005fa44  mov     r8d, edi; dwDesiredAccess
0x18005fa47  xor     edx, edx; fInherit
0x18005fa49  xor     ecx, ecx; dwFlags
0x18005fa4b  call    cs:__imp_OpenInputDesktop
0x18005fa52  nop     dword ptr [rax+rax+00h]
0x18005fa57  test    rax, rax
0x18005fa5a  mov     [rsp+78h+arg_18], rax
0x18005fa62  lea     rcx, [rsp+78h+arg_18]
0x18005fa6a  setz    cs:?g_trackedDesktopStateEverEnteredSecureDesktop@@3_NA; bool g_trackedDesktopStateEverEnteredSecureDesktop
0x18005fa71  call    ??1?$unique_storage@U?$resource_policy@PEAUHDESK__@@P6AHPEAU1@@Z$1?CloseDesktop@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HDESK__ *,int (*)(HDESK__ *),&CloseDesktop(HDESK__ *),wistd::integral_constant<unsigned __int64,0>,HDESK__ *,HDESK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HDESK__ *,int (*)(HDESK__ *),&CloseDesktop(HDESK__ *),wistd::integral_constant<unsigned __int64,0>,HDESK__ *,HDESK__ *,0,std::nullptr_t>>(void)
0x18005fa76  lea     rcx, [rsp+78h+var_58]
0x18005fa7b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18005fa80  test    r14b, r14b
0x18005fa83  jz      short loc_18005FABC
0x18005fa85  mov     rdx, [rbx+0B0h]; hWnd
0x18005fa8c  mov     rcx, [rbx+70h]; hWndInsertAfter
0x18005fa90  call    ?_SetOwnerWindow@@YAJPEAUHWND__@@0@Z; _SetOwnerWindow(HWND__ *,HWND__ *)
0x18005fa95  test    eax, eax
0x18005fa97  js      short loc_18005FABC
0x18005fa99  mov     r8, [rbx+0C0h]; HWND
0x18005faa0  test    r8, r8
0x18005faa3  jz      short loc_18005FABC
0x18005faa5  cmp     [rbx+93h], r13b
0x18005faac  jz      short loc_18005FABC
0x18005faae  xor     r9d, r9d; bool
0x18005fab1  mov     dl, dil; bool
0x18005fab4  mov     rcx, rbx; this
0x18005fab7  call    ?_AttachOrDetachInputQueues@CBridgeWindow@@AEAAJ_NPEAUHWND__@@0@Z; CBridgeWindow::_AttachOrDetachInputQueues(bool,HWND__ *,bool)
0x18005fabc  cmp     [rbx+8Eh], r13b
0x18005fac3  jnz     short loc_18005FACC
0x18005fac5  mov     al, dil
0x18005fac8  test    esi, esi
0x18005faca  jz      short loc_18005FACF
0x18005facc  mov     al, r13b
0x18005facf  mov     [rsp+78h+arg_8], al
0x18005fad6  test    r15, r15
0x18005fad9  jz      short loc_18005FAE9
0x18005fadb  mov     esi, 4Bh ; 'K'
0x18005fae0  lea     rdx, qword_180109A50
0x18005fae7  jmp     short loc_18005FAF4
0x18005fae9  mov     esi, r14d
0x18005faec  mov     rdx, r13
0x18005faef  xor     esi, edi
0x18005faf1  add     esi, 4
0x18005faf4  test    al, al
0x18005faf6  jz      loc_18005FBC2
0x18005fafc  mov     ecx, esi
0x18005fafe  call    cs:__imp_DwmpBeginTransitionRequestWithGUID
0x18005fb05  nop     dword ptr [rax+rax+00h]
0x18005fb0a  mov     ebp, eax
0x18005fb0c  test    eax, eax
0x18005fb0e  js      loc_18005FBC7
0x18005fb14  mov     ecx, esi
0x18005fb16  sub     ecx, 4
0x18005fb19  jz      short loc_18005FB38
0x18005fb1b  sub     ecx, edi
0x18005fb1d  jz      short loc_18005FB31
0x18005fb1f  cmp     ecx, 46h ; 'F'
0x18005fb22  jz      short loc_18005FB2B
0x18005fb24  mov     ecx, 0FFFh
0x18005fb29  jmp     short loc_18005FB3D
0x18005fb2b  lea     ecx, [r14+12h]
0x18005fb2f  jmp     short loc_18005FB3D
0x18005fb31  mov     ecx, 1Ah
0x18005fb36  jmp     short loc_18005FB3D
0x18005fb38  mov     ecx, 19h
0x18005fb3d  mov     al, r14b
0x18005fb40  xor     al, dil
0x18005fb43  mov     [rbx+90h], al
0x18005fb49  test    r14b, r14b
0x18005fb4c  jz      short loc_18005FB56
0x18005fb4e  mov     al, dil
0x18005fb51  cmp     esi, 4
0x18005fb54  jz      short loc_18005FB59
0x18005fb56  mov     al, r13b
0x18005fb59  cmp     ecx, 19h
0x18005fb5c  mov     [rbx+91h], al
0x18005fb62  mov     eax, 10400000h
0x18005fb67  mov     edx, 10420000h
0x18005fb6c  cmovnz  edx, eax
0x18005fb6f  or      edx, ecx
0x18005fb71  mov     rcx, [rbx+70h]
0x18005fb75  call    cs:__imp_DwmpTransitionWindow
0x18005fb7c  nop     dword ptr [rax+rax+00h]
0x18005fb81  mov     ebp, eax
0x18005fb83  test    eax, eax
0x18005fb85  js      short loc_18005FBC7
0x18005fb87  test    r15, r15
0x18005fb8a  jz      short loc_18005FBC7
0x18005fb8c  mov     edx, 10400012h
0x18005fb91  mov     rcx, r15
0x18005fb94  call    cs:__imp_DwmpTransitionWindow
0x18005fb9b  nop     dword ptr [rax+rax+00h]
0x18005fba0  mov     ebp, eax
0x18005fba2  test    eax, eax
0x18005fba4  js      short loc_18005FBC7
0x18005fba6  xor     r9d, r9d; lParam
0x18005fba9  xor     r8d, r8d; wParam
0x18005fbac  mov     edx, 404h; Msg
0x18005fbb1  mov     rcx, r15; hWnd
0x18005fbb4  call    cs:__imp_SendMessageW
0x18005fbbb  nop     dword ptr [rax+rax+00h]
0x18005fbc0  jmp     short loc_18005FBC7
0x18005fbc2  mov     ebp, 80004005h
0x18005fbc7  mov     al, r14b
0x18005fbca  mov     rcx, rbx; this
0x18005fbcd  xor     al, dil
0x18005fbd0  movzx   r12d, al
0x18005fbd4  mov     edx, r12d; int
0x18005fbd7  call    ?_CloakWindow@CBridgeWindow@@AEAAJH@Z; CBridgeWindow::_CloakWindow(int)
0x18005fbdc  mov     r15d, eax
0x18005fbdf  test    ebp, ebp
0x18005fbe1  js      short loc_18005FBF1
0x18005fbe3  mov     ecx, esi
0x18005fbe5  call    cs:__imp_DwmpEndTransitionRequest
0x18005fbec  nop     dword ptr [rax+rax+00h]
0x18005fbf1  test    r14b, r14b
0x18005fbf4  jnz     short loc_18005FC27
0x18005fbf6  cmp     [rsp+78h+arg_8], r13b
0x18005fbfe  jz      short loc_18005FC04
0x18005fc00  test    ebp, ebp
0x18005fc02  js      short loc_18005FC12
0x18005fc04  cmp     [rsp+78h+arg_10], edi
0x18005fc0b  jz      short loc_18005FC12
0x18005fc0d  test    r15d, r15d
0x18005fc10  jns     short loc_18005FC27
0x18005fc12  mov     edx, r15d; int
0x18005fc15  mov     byte ptr [rbx+90h], 0
0x18005fc1c  mov     rcx, rbx; this
0x18005fc1f  mov     r13b, dil
0x18005fc22  call    ?_RemoveOwner@CBridgeWindow@@AEAAXJ@Z; CBridgeWindow::_RemoveOwner(long)
0x18005fc27  xor     r9d, r9d; fWinIni
0x18005fc2a  mov     [rsp+78h+pvParam], edi
0x18005fc31  lea     r8, [rsp+78h+pvParam]; pvParam
0x18005fc39  xor     edx, edx; uiParam
0x18005fc3b  mov     ecx, 1042h; uiAction
0x18005fc40  call    cs:__imp_SystemParametersInfoW
0x18005fc47  nop     dword ptr [rax+rax+00h]
0x18005fc4c  cmp     qword ptr [rbx+0F0h], 0
0x18005fc54  jz      short loc_18005FC80
0x18005fc56  lea     rdx, ?g_desktopSwitchLock@@3Vsrwlock@wil@@A; wil::srwlock g_desktopSwitchLock
0x18005fc5d  lea     rcx, [rsp+78h+arg_18]
0x18005fc65  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x18005fc6a  mov     r15b, cs:?g_trackedDesktopStateEverEnteredSecureDesktop@@3_NA; bool g_trackedDesktopStateEverEnteredSecureDesktop
0x18005fc71  lea     rcx, [rsp+78h+arg_18]
0x18005fc79  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005fc7e  jmp     short loc_18005FC83
0x18005fc80  xor     r15b, r15b
0x18005fc83  cmp     [rsp+78h+arg_8], 0
0x18005fc8b  jz      short loc_18005FCE5
0x18005fc8d  cmp     [rsp+78h+pvParam], 0
0x18005fc95  jnz     short loc_18005FC9B
0x18005fc97  test    ebp, ebp
0x18005fc99  js      short loc_18005FCA0
0x18005fc9b  test    r15b, r15b
0x18005fc9e  jz      short loc_18005FCE5
0x18005fca0  test    r13b, r13b
0x18005fca3  jz      short loc_18005FCAC
0x18005fca5  mov     r12b, [rbx+90h]
0x18005fcac  mov     [rbx+90h], r12b
0x18005fcb3  test    r14b, r14b
0x18005fcb6  jz      short loc_18005FCBD
0x18005fcb8  cmp     esi, 4
0x18005fcbb  jz      short loc_18005FCC0
0x18005fcbd  xor     dil, dil
0x18005fcc0  mov     rcx, [rbx+70h]; hWnd
0x18005fcc4  mov     r9d, 2; lParam
0x18005fcca  xor     r8d, r8d; wParam
0x18005fccd  mov     [rbx+91h], dil
0x18005fcd4  mov     edx, 32Ah; Msg
0x18005fcd9  call    cs:__imp_PostMessageW
0x18005fce0  nop     dword ptr [rax+rax+00h]
0x18005fce5  mov     rcx, rbx; this
0x18005fce8  mov     byte ptr [rbx+8Eh], 0
0x18005fcef  call    ?_MaybeNotifySplashScreenDismissed@CBridgeWindow@@AEAAXXZ; CBridgeWindow::_MaybeNotifySplashScreenDismissed(void)
0x18005fcf4  add     rsp, 38h
0x18005fcf8  pop     r15
0x18005fcfa  pop     r14
0x18005fcfc  pop     r13
0x18005fcfe  pop     r12
0x18005fd00  pop     rdi
0x18005fd01  pop     rsi
0x18005fd02  pop     rbp
0x18005fd03  pop     rbx
0x18005fd04  retn
```
