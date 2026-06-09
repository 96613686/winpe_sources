# TouchEditContextMenuBehavior::_DisplayContextMenu(DirectUI::TouchEdit2 *,tagRECT const &)

- ea: `0x180071b88`
- end: `0x180072175`
- name: `?_DisplayContextMenu@TouchEditContextMenuBehavior@@AEAAJPEAVTouchEdit2@DirectUI@@AEBUtagRECT@@@Z`
- size: `1517`
- prototype: `__int64 __fastcall(TouchEditContextMenuBehavior *__hidden this, struct DirectUI::TouchEdit2 *, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800717d0`

## callees

- `0x180013f14`
- `0x18003f720`
- `0x18004f9bc`
- `0x180054130`
- `0x180064738`
- `0x180070e84`
- `0x180070f84`
- `0x18007101c`
- `0x1800710b4`
- `0x18007114c`
- `0x1800711e4`
- `0x1800715a4`
- `0x180071a3c`
- `0x180071b88`
- `0x1800ed010`

## import_xrefs

- `SHCORE!__imp_RelativeRectFromPhysicalRectWithScale` at `0x1800720ea`
- `SHCORE!__imp_RelativeRectFromPhysicalRectWithScale` at `0x1800720ea`
- `DUI70!?GetIgnoredKeyCombos@TouchEditBase@DirectUI@@QEAA?AW4TouchEditFilteredKeyComboFlags@2@XZ` at `0x180071bf6`
- `DUI70!?GetIgnoredKeyCombos@TouchEditBase@DirectUI@@QEAA?AW4TouchEditFilteredKeyComboFlags@2@XZ` at `0x180071bf6`
- `DUI70!?GetReadOnly@TouchEditBase@DirectUI@@QEAA_NXZ` at `0x180071bd2`
- `DUI70!?GetReadOnly@TouchEditBase@DirectUI@@QEAA_NXZ` at `0x180071bd2`
- `DUI70!?HasSelection@TouchEdit2@DirectUI@@QEAA_NXZ` at `0x180071bc0`
- `DUI70!?HasSelection@TouchEdit2@DirectUI@@QEAA_NXZ` at `0x180071bc0`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180072075`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180072075`

## pseudocode

```c
__int64 __fastcall TouchEditContextMenuBehavior::_DisplayContextMenu(
        TouchEditContextMenuBehavior *this,
        struct DirectUI::TouchEdit2 *a2,
        const struct tagRECT *a3)
{
  char v4; // r12
  char IgnoredKeyCombos; // al
  __int64 v6; // rcx
  char v7; // r14
  __int64 (__fastcall *v8)(struct DirectUI::TouchEdit2 *, __int64 *); // rbx
  int v9; // edi
  char v10; // si
  bool v11; // r15
  _QWORD *v12; // rax
  struct Windows::UI::Popups::IPopupMenu *v13; // rbx
  __int64 (__fastcall *v14)(struct Windows::UI::Popups::IPopupMenu *, GUID *, __int64 *); // rdi
  bool v15; // al
  struct Windows::UI::Popups::IUICommandInvokedHandler **v16; // rax
  struct Windows::UI::Popups::IUICommandInvokedHandler *v17; // rbx
  TouchEditContextMenuBehavior *v18; // rcx
  struct Windows::UI::Popups::IUICommandInvokedHandler **v19; // rax
  struct Windows::UI::Popups::IUICommandInvokedHandler *v20; // rbx
  TouchEditContextMenuBehavior *v21; // rcx
  struct Windows::UI::Popups::IUICommandInvokedHandler **v22; // rax
  struct Windows::UI::Popups::IUICommandInvokedHandler *v23; // rbx
  TouchEditContextMenuBehavior *v24; // rcx
  struct Windows::UI::Popups::IUICommandInvokedHandler **v25; // rax
  struct Windows::UI::Popups::IUICommandInvokedHandler *v26; // rbx
  TouchEditContextMenuBehavior *v27; // rcx
  struct Windows::UI::Popups::IPopupMenu *v28; // rbx
  HWND v29; // rsi
  __int64 (__fastcall *v30)(struct Windows::UI::Popups::IPopupMenu *, GUID *, __int64 *); // rdi
  struct DirectUI::Element *Root; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  enum DEVICE_SCALE_FACTOR v34; // eax
  struct Windows::UI::Popups::IPopupMenu *v35; // rdi
  __int64 (__fastcall *v36)(struct Windows::UI::Popups::IPopupMenu *, __int128 *, TouchEditContextMenuBehavior **); // rbx
  bool Only; // [rsp+30h] [rbp-69h]
  __int64 v39; // [rsp+38h] [rbp-61h] BYREF
  bool HasSelection; // [rsp+40h] [rbp-59h]
  TouchEditContextMenuBehavior *v41; // [rsp+48h] [rbp-51h] BYREF
  struct Windows::UI::Popups::IPopupMenu *v42; // [rsp+50h] [rbp-49h] BYREF
  __int64 v43; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v44[2]; // [rsp+60h] [rbp-39h] BYREF
  __int128 v45; // [rsp+70h] [rbp-29h] BYREF
  __int128 v46; // [rsp+80h] [rbp-19h] BYREF
  HSTRING string; // [rsp+90h] [rbp-9h] BYREF

  *(_QWORD *)&v45 = a3;
  *(_QWORD *)&v46 = a2;
  HasSelection = DirectUI::TouchEdit2::HasSelection(a2);
  Only = DirectUI::TouchEditBase::GetReadOnly(a2);
  v4 = (*(__int64 (__fastcall **)(struct DirectUI::TouchEdit2 *))(*(_QWORD *)a2 + 16LL))(a2);
  IgnoredKeyCombos = DirectUI::TouchEditBase::GetIgnoredKeyCombos(a2);
  v6 = *(_QWORD *)a2;
  v7 = IgnoredKeyCombos;
  v43 = 0;
  v8 = *(__int64 (__fastcall **)(struct DirectUI::TouchEdit2 *, __int64 *))(v6 + 368);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
  v9 = v8(a2, &v43);
  if ( v9 < 0 )
  {
    v11 = 0;
LABEL_11:
    v10 = 0;
    goto LABEL_12;
  }
  v39 = 0;
  v10 = 1;
  (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v43 + 24LL))(v43, 14, 0);
  v11 = (*(int (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v43 + 24LL))(
          v43,
          1074,
          0,
          0,
          &v39) >= 0
     && v39;
  if ( v4
    || (*(int (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v43 + 24LL))(
         v43,
         198,
         0,
         0,
         &v39) < 0
    || !v39 )
  {
    goto LABEL_11;
  }
LABEL_12:
  v42 = 0;
  if ( v9 < 0 )
    goto LABEL_57;
  v12 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, L"Windows.UI.Popups.PopupMenu");
  v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>>(*v12, &v42);
  if ( v9 >= 0 )
  {
    v39 = 0;
    v13 = v42;
    v14 = **(__int64 (__fastcall ***)(struct Windows::UI::Popups::IPopupMenu *, GUID *, __int64 *))v42;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
    v9 = v14(v13, &GUID_181e01e5_f091_4d6b_85d4_a35a1191709c, &v39);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
    if ( v9 >= 0 )
    {
      v15 = Only;
      if ( HasSelection )
      {
        if ( Only )
        {
          if ( !v4 )
          {
LABEL_26:
            if ( (v7 & 0x11) != 0x11 )
            {
              v39 = v43;
              if ( v43 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
              v19 = (struct Windows::UI::Popups::IUICommandInvokedHandler **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::UI::Popups::IUICommandInvokedHandler::___Windows::UI::Popups::IUICommand____::DelegateInvokeHelper_Windows::UI::Popups::IUICommandInvokedHandler__lambda_e33c50f189b7423db4a6233779417bb5___1_Windows::UI::Popups::IUICommand_____lambda_e33c50f189b7423db4a6233779417bb5___(
                                                                               &v41,
                                                                               &v39);
              v20 = *v19;
              *v19 = 0;
              v21 = v41;
              v44[0] = v20;
              if ( v41 )
              {
                v41 = 0;
                Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release();
              }
              v9 = TouchEditContextMenuBehavior::_AddCommand(v21, v42, 0x2262u, v20);
              Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v44);
              Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
              if ( v9 < 0 )
                goto LABEL_49;
            }
            v15 = Only;
          }
        }
        else if ( !v4 )
        {
          if ( (v7 & 0x24) != 0x24 )
          {
            v39 = v43;
            if ( v43 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
            v16 = (struct Windows::UI::Popups::IUICommandInvokedHandler **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::UI::Popups::IUICommandInvokedHandler::___Windows::UI::Popups::IUICommand____::DelegateInvokeHelper_Windows::UI::Popups::IUICommandInvokedHandler__lambda_407fe2a523d125ac0dfc12da008f27b8___1_Windows::UI::Popups::IUICommand_____lambda_407fe2a523d125ac0dfc12da008f27b8___(
                                                                             &v41,
                                                                             &v39);
            v17 = *v16;
            *v16 = 0;
            v18 = v41;
            v44[0] = v17;
            if ( v41 )
            {
              v41 = 0;
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release();
            }
            v9 = TouchEditContextMenuBehavior::_AddCommand(v18, v42, 0x2261u, v17);
            Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v44);
            Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
            if ( v9 < 0 )
              goto LABEL_49;
          }
          goto LABEL_26;
        }
      }
      if ( !v11 || v15 || (v7 & 0xA) == 0xA )
        goto LABEL_43;
      v39 = v43;
      if ( v43 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
      v22 = (struct Windows::UI::Popups::IUICommandInvokedHandler **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::UI::Popups::IUICommandInvokedHandler::___Windows::UI::Popups::IUICommand____::DelegateInvokeHelper_Windows::UI::Popups::IUICommandInvokedHandler__lambda_6b207a4fc27e98e6a7c835da50fdbaa1___1_Windows::UI::Popups::IUICommand_____lambda_6b207a4fc27e98e6a7c835da50fdbaa1___(
                                                                       &v41,
                                                                       &v39);
      v23 = *v22;
      *v22 = 0;
      v24 = v41;
      v44[0] = v23;
      if ( v41 )
      {
        v41 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release();
      }
      v9 = TouchEditContextMenuBehavior::_AddCommand(v24, v42, 0x2263u, v23);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v44);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
      if ( v9 >= 0 )
      {
LABEL_43:
        if ( !HasSelection && !Only && v10 )
        {
          v39 = v43;
          if ( v43 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
          v25 = (struct Windows::UI::Popups::IUICommandInvokedHandler **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::UI::Popups::IUICommandInvokedHandler::___Windows::UI::Popups::IUICommand____::DelegateInvokeHelper_Windows::UI::Popups::IUICommandInvokedHandler__lambda_fb36a96919ef6648cbdefe112dbccf5d___1_Windows::UI::Popups::IUICommand_____lambda_fb36a96919ef6648cbdefe112dbccf5d___(
                                                                           &v41,
                                                                           &v39);
          v26 = *v25;
          *v25 = 0;
          v27 = v41;
          v44[0] = v26;
          if ( v41 )
          {
            v41 = 0;
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release();
          }
          v9 = TouchEditContextMenuBehavior::_AddCommand(v27, v42, 0x2264u, v26);
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v44);
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
        }
      }
    }
  }
LABEL_49:
  v28 = v42;
  if ( v9 >= 0 )
  {
    v29 = 0;
    v39 = 0;
    v30 = **(__int64 (__fastcall ***)(struct Windows::UI::Popups::IPopupMenu *, GUID *, __int64 *))v42;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
    v9 = v30(v28, &GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1, &v39);
    if ( v9 >= 0 )
    {
      Root = DirectUI::Element::GetRoot((DirectUI::Element *)v46);
      v32 = element_cast<DirectUI::HWNDElement>(Root);
      if ( v32 && (v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 360LL))(v32), (v29 = (HWND)v33) != 0) )
        v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 24LL))(v39, v33);
      else
        v9 = -2147418113;
    }
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
    if ( v9 >= 0 )
    {
      v34 = DUIGetScaleFactorForWindow(v29);
      v46 = 0;
      RelativeRectFromPhysicalRectWithScale((unsigned int)v34, v45, &v46);
      v35 = v42;
      v41 = 0;
      v36 = *(__int64 (__fastcall **)(struct Windows::UI::Popups::IPopupMenu *, __int128 *, TouchEditContextMenuBehavior **))(*(_QWORD *)v42 + 64LL);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v41);
      v45 = v46;
      v9 = v36(v35, &v45, &v41);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v41);
    }
  }
LABEL_57:
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v42);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180071b88  mov     [rsp-8+arg_0], rbx
0x180071b8d  push    rbp
0x180071b8e  push    rsi
0x180071b8f  push    rdi
0x180071b90  push    r12
0x180071b92  push    r13
0x180071b94  push    r14
0x180071b96  push    r15
0x180071b98  lea     rbp, [rsp-27h]
0x180071b9d  sub     rsp, 0C0h
0x180071ba4  mov     rax, cs:__security_cookie
0x180071bab  xor     rax, rsp
0x180071bae  mov     [rbp+57h+var_40], rax
0x180071bb2  mov     rcx, rdx
0x180071bb5  mov     qword ptr [rbp+57h+var_80], r8
0x180071bb9  mov     rdi, rdx
0x180071bbc  mov     qword ptr [rbp+57h+var_70], rdx
0x180071bc0  call    cs:__imp_?HasSelection@TouchEdit2@DirectUI@@QEAA_NXZ; DirectUI::TouchEdit2::HasSelection(void)
0x180071bc7  nop     dword ptr [rax+rax+00h]
0x180071bcc  mov     rcx, rdi
0x180071bcf  mov     [rbp+57h+var_B0], al
0x180071bd2  call    cs:__imp_?GetReadOnly@TouchEditBase@DirectUI@@QEAA_NXZ; DirectUI::TouchEditBase::GetReadOnly(void)
0x180071bd9  nop     dword ptr [rax+rax+00h]
0x180071bde  mov     rcx, [rdi]
0x180071be1  mov     [rbp+57h+var_C0], al
0x180071be4  mov     rax, [rcx+10h]
0x180071be8  mov     rcx, rdi
0x180071beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071bf0  mov     rcx, rdi
0x180071bf3  mov     r12b, al
0x180071bf6  call    cs:__imp_?GetIgnoredKeyCombos@TouchEditBase@DirectUI@@QEAA?AW4TouchEditFilteredKeyComboFlags@2@XZ; DirectUI::TouchEditBase::GetIgnoredKeyCombos(void)
0x180071bfd  nop     dword ptr [rax+rax+00h]
0x180071c02  mov     rcx, [rdi]
0x180071c05  mov     r14d, eax
0x180071c08  mov     [rbp+57h+var_98], 0
0x180071c10  mov     rbx, [rcx+170h]
0x180071c17  lea     rcx, [rbp+57h+var_98]
0x180071c1b  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180071c20  lea     rdx, [rbp+57h+var_98]
0x180071c24  mov     rcx, rdi
0x180071c27  mov     rax, rbx
0x180071c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071c2f  mov     edi, eax
0x180071c31  test    eax, eax
0x180071c33  js      loc_180071CEA
0x180071c39  mov     r10, [rbp+57h+var_98]
0x180071c3d  xor     r9d, r9d
0x180071c40  mov     [rbp+57h+var_B8], 0
0x180071c48  xor     r8d, r8d
0x180071c4b  mov     rcx, [r10]
0x180071c4e  lea     edx, [r9+0Eh]
0x180071c52  mov     rax, [rcx+18h]
0x180071c56  lea     rcx, [rbp+57h+var_B8]
0x180071c5a  mov     [rsp+0F0h+var_D0], rcx
0x180071c5f  mov     rcx, r10
0x180071c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071c67  mov     sil, 1
0x180071c6a  test    eax, eax
0x180071c6c  js      short loc_180071C7A
0x180071c6e  cmp     [rbp+57h+var_B8], 0
0x180071c73  jle     short loc_180071C7A
0x180071c75  mov     r13b, sil
0x180071c78  jmp     short loc_180071C7D
0x180071c7a  xor     r13b, r13b
0x180071c7d  mov     rcx, [rbp+57h+var_98]
0x180071c81  lea     rdx, [rbp+57h+var_B8]
0x180071c85  mov     [rsp+0F0h+var_D0], rdx
0x180071c8a  xor     r9d, r9d
0x180071c8d  xor     r8d, r8d
0x180071c90  mov     edx, 432h
0x180071c95  mov     rax, [rcx]
0x180071c98  mov     rax, [rax+18h]
0x180071c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ca1  test    eax, eax
0x180071ca3  js      short loc_180071CB1
0x180071ca5  cmp     [rbp+57h+var_B8], 0
0x180071caa  jz      short loc_180071CB1
0x180071cac  mov     r15b, sil
0x180071caf  jmp     short loc_180071CB4
0x180071cb1  xor     r15b, r15b
0x180071cb4  test    r12b, r12b
0x180071cb7  jnz     short loc_180071CF0
0x180071cb9  mov     rcx, [rbp+57h+var_98]
0x180071cbd  lea     rdx, [rbp+57h+var_B8]
0x180071cc1  mov     [rsp+0F0h+var_D0], rdx
0x180071cc6  xor     r9d, r9d
0x180071cc9  xor     r8d, r8d
0x180071ccc  mov     edx, 0C6h
0x180071cd1  mov     rax, [rcx]
0x180071cd4  mov     rax, [rax+18h]
0x180071cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071cdd  test    eax, eax
0x180071cdf  js      short loc_180071CF0
0x180071ce1  cmp     [rbp+57h+var_B8], 0
0x180071ce6  jnz     short loc_180071CF3
0x180071ce8  jmp     short loc_180071CF0
0x180071cea  xor     r13b, r13b
0x180071ced  xor     r15b, r15b
0x180071cf0  xor     sil, sil
0x180071cf3  xor     ebx, ebx
0x180071cf5  mov     [rbp+57h+var_A0], rbx
0x180071cf9  test    edi, edi
0x180071cfb  js      loc_180072139
0x180071d01  lea     rdx, ?RuntimeClass_Windows_UI_Popups_PopupMenu@@3QBGB; "Windows.UI.Popups.PopupMenu"
0x180071d08  lea     rcx, [rbp+57h+string]; string
0x180071d0c  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x180071d11  lea     rdx, [rbp+57h+var_A0]
0x180071d15  mov     rcx, [rax]
0x180071d18  call    ??$ActivateInstance@V?$ComPtr@UIPopupMenu@Popups@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPopupMenu@Popups@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>>)
0x180071d1d  mov     edi, eax
0x180071d1f  test    eax, eax
0x180071d21  js      loc_180072034
0x180071d27  mov     [rbp+57h+var_B8], rbx
0x180071d2b  lea     rcx, [rbp+57h+var_B8]
0x180071d2f  mov     rbx, [rbp+57h+var_A0]
0x180071d33  mov     rax, [rbx]
0x180071d36  mov     rdi, [rax]
0x180071d39  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180071d3e  lea     r8, [rbp+57h+var_B8]
0x180071d42  mov     rcx, rbx
0x180071d45  lea     rdx, _GUID_181e01e5_f091_4d6b_85d4_a35a1191709c
0x180071d4c  mov     rax, rdi
0x180071d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071d54  lea     rcx, [rbp+57h+var_B8]
0x180071d58  mov     edi, eax
0x180071d5a  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180071d5f  test    edi, edi
0x180071d61  js      loc_180072034
0x180071d67  cmp     [rbp+57h+var_B0], 0
0x180071d6b  mov     al, [rbp+57h+var_C0]
0x180071d6e  jz      loc_180071E9B
0x180071d74  test    al, al
0x180071d76  jnz     loc_180071E0D
0x180071d7c  test    r12b, r12b
0x180071d7f  jnz     loc_180071E9B
0x180071d85  mov     eax, r14d
0x180071d88  and     eax, 24h
0x180071d8b  cmp     al, 24h ; '$'
0x180071d8d  jz      loc_180071E16
0x180071d93  mov     rcx, [rbp+57h+var_98]
0x180071d97  mov     [rbp+57h+var_B8], rcx
0x180071d9b  test    rcx, rcx
0x180071d9e  jz      short loc_180071DAC
0x180071da0  mov     rax, [rcx]
0x180071da3  mov     rax, [rax+8]
0x180071da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071dac  lea     rdx, [rbp+57h+var_B8]
0x180071db0  lea     rcx, [rbp+57h+var_A8]
0x180071db4  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Popups__IUICommandInvokedHandler_____Windows__UI__Popups__IUICommand______DelegateInvokeHelper_Windows__UI__Popups__IUICommandInvokedHandler__lambda_407fe2a523d125ac0dfc12da008f27b8___1_Windows__UI__Popups__IUICommand_____lambda_407fe2a523d125ac0dfc12da008f27b8___
0x180071db9  mov     rbx, [rax]
0x180071dbc  mov     qword ptr [rax], 0
0x180071dc3  mov     rcx, [rbp+57h+var_A8]
0x180071dc7  mov     [rbp+57h+var_90], rbx
0x180071dcb  test    rcx, rcx
0x180071dce  jz      short loc_180071DDD
0x180071dd0  mov     [rbp+57h+var_A8], 0
0x180071dd8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDialogFirstFrameRenderedHandler@Dialogs@UI@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release(void)
0x180071ddd  mov     rdx, [rbp+57h+var_A0]; struct Windows::UI::Popups::IPopupMenu *
0x180071de1  mov     r9, rbx; struct Windows::UI::Popups::IUICommandInvokedHandler *
0x180071de4  mov     r8d, 2261h; unsigned int
0x180071dea  call    ?_AddCommand@TouchEditContextMenuBehavior@@AEAAJPEAUIPopupMenu@Popups@UI@Windows@@IPEAUIUICommandInvokedHandler@345@@Z; TouchEditContextMenuBehavior::_AddCommand(Windows::UI::Popups::IPopupMenu *,uint,Windows::UI::Popups::IUICommandInvokedHandler *)
0x180071def  lea     rcx, [rbp+57h+var_90]
0x180071df3  mov     edi, eax
0x180071df5  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180071dfa  lea     rcx, [rbp+57h+var_B8]
0x180071dfe  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180071e03  test    edi, edi
0x180071e05  js      loc_180072034
0x180071e0b  jmp     short loc_180071E16
0x180071e0d  test    r12b, r12b
0x180071e10  jnz     loc_180071E9B
0x180071e16  mov     eax, r14d
0x180071e19  and     eax, 11h
0x180071e1c  cmp     al, 11h
0x180071e1e  jz      short loc_180071E98
0x180071e20  mov     rcx, [rbp+57h+var_98]
0x180071e24  mov     [rbp+57h+var_B8], rcx
0x180071e28  test    rcx, rcx
0x180071e2b  jz      short loc_180071E39
0x180071e2d  mov     rax, [rcx]
0x180071e30  mov     rax, [rax+8]
0x180071e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e39  lea     rdx, [rbp+57h+var_B8]
0x180071e3d  lea     rcx, [rbp+57h+var_A8]
0x180071e41  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Popups__IUICommandInvokedHandler_____Windows__UI__Popups__IUICommand______DelegateInvokeHelper_Windows__UI__Popups__IUICommandInvokedHandler__lambda_e33c50f189b7423db4a6233779417bb5___1_Windows__UI__Popups__IUICommand_____lambda_e33c50f189b7423db4a6233779417bb5___
0x180071e46  mov     rbx, [rax]
0x180071e49  mov     qword ptr [rax], 0
0x180071e50  mov     rcx, [rbp+57h+var_A8]
0x180071e54  mov     [rbp+57h+var_90], rbx
0x180071e58  test    rcx, rcx
0x180071e5b  jz      short loc_180071E6A
0x180071e5d  mov     [rbp+57h+var_A8], 0
0x180071e65  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDialogFirstFrameRenderedHandler@Dialogs@UI@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release(void)
0x180071e6a  mov     rdx, [rbp+57h+var_A0]; struct Windows::UI::Popups::IPopupMenu *
0x180071e6e  mov     r9, rbx; struct Windows::UI::Popups::IUICommandInvokedHandler *
0x180071e71  mov     r8d, 2262h; unsigned int
0x180071e77  call    ?_AddCommand@TouchEditContextMenuBehavior@@AEAAJPEAUIPopupMenu@Popups@UI@Windows@@IPEAUIUICommandInvokedHandler@345@@Z; TouchEditContextMenuBehavior::_AddCommand(Windows::UI::Popups::IPopupMenu *,uint,Windows::UI::Popups::IUICommandInvokedHandler *)
0x180071e7c  lea     rcx, [rbp+57h+var_90]
0x180071e80  mov     edi, eax
0x180071e82  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180071e87  lea     rcx, [rbp+57h+var_B8]
0x180071e8b  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180071e90  test    edi, edi
0x180071e92  js      loc_180072034
0x180071e98  mov     al, [rbp+57h+var_C0]
0x180071e9b  test    r15b, r15b
0x180071e9e  jz      loc_180071F2E
0x180071ea4  test    al, al
0x180071ea6  jnz     loc_180071F2E
0x180071eac  and     r14d, 0Ah
0x180071eb0  cmp     r14b, 0Ah
0x180071eb4  jz      short loc_180071F2E
0x180071eb6  mov     rcx, [rbp+57h+var_98]
0x180071eba  mov     [rbp+57h+var_B8], rcx
0x180071ebe  test    rcx, rcx
0x180071ec1  jz      short loc_180071ECF
0x180071ec3  mov     rax, [rcx]
0x180071ec6  mov     rax, [rax+8]
0x180071eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ecf  lea     rdx, [rbp+57h+var_B8]
0x180071ed3  lea     rcx, [rbp+57h+var_A8]
0x180071ed7  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Popups__IUICommandInvokedHandler_____Windows__UI__Popups__IUICommand______DelegateInvokeHelper_Windows__UI__Popups__IUICommandInvokedHandler__lambda_6b207a4fc27e98e6a7c835da50fdbaa1___1_Windows__UI__Popups__IUICommand_____lambda_6b207a4fc27e98e6a7c835da50fdbaa1___
0x180071edc  mov     rbx, [rax]
0x180071edf  mov     qword ptr [rax], 0
0x180071ee6  mov     rcx, [rbp+57h+var_A8]
0x180071eea  mov     [rbp+57h+var_90], rbx
0x180071eee  test    rcx, rcx
0x180071ef1  jz      short loc_180071F00
0x180071ef3  mov     [rbp+57h+var_A8], 0
0x180071efb  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDialogFirstFrameRenderedHandler@Dialogs@UI@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release(void)
0x180071f00  mov     rdx, [rbp+57h+var_A0]; struct Windows::UI::Popups::IPopupMenu *
0x180071f04  mov     r9, rbx; struct Windows::UI::Popups::IUICommandInvokedHandler *
0x180071f07  mov     r8d, 2263h; unsigned int
0x180071f0d  call    ?_AddCommand@TouchEditContextMenuBehavior@@AEAAJPEAUIPopupMenu@Popups@UI@Windows@@IPEAUIUICommandInvokedHandler@345@@Z; TouchEditContextMenuBehavior::_AddCommand(Windows::UI::Popups::IPopupMenu *,uint,Windows::UI::Popups::IUICommandInvokedHandler *)
0x180071f12  lea     rcx, [rbp+57h+var_90]
0x180071f16  mov     edi, eax
0x180071f18  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180071f1d  lea     rcx, [rbp+57h+var_B8]
0x180071f21  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180071f26  test    edi, edi
0x180071f28  js      loc_180072034
0x180071f2e  mov     r14b, [rbp+57h+var_B0]
0x180071f32  test    r14b, r14b
0x180071f35  jnz     loc_180072034
0x180071f3b  cmp     [rbp+57h+var_C0], r14b
0x180071f3f  jnz     short loc_180071FBF
0x180071f41  test    sil, sil
0x180071f44  jz      short loc_180071FBF
0x180071f46  mov     rcx, [rbp+57h+var_98]
0x180071f4a  mov     [rbp+57h+var_B8], rcx
0x180071f4e  test    rcx, rcx
0x180071f51  jz      short loc_180071F5F
0x180071f53  mov     rax, [rcx]
0x180071f56  mov     rax, [rax+8]
0x180071f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f5f  lea     rdx, [rbp+57h+var_B8]
0x180071f63  lea     rcx, [rbp+57h+var_A8]
0x180071f67  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Popups__IUICommandInvokedHandler_____Windows__UI__Popups__IUICommand______DelegateInvokeHelper_Windows__UI__Popups__IUICommandInvokedHandler__lambda_fb36a96919ef6648cbdefe112dbccf5d___1_Windows__UI__Popups__IUICommand_____lambda_fb36a96919ef6648cbdefe112dbccf5d___
0x180071f6c  mov     rbx, [rax]
0x180071f6f  mov     qword ptr [rax], 0
0x180071f76  mov     rcx, [rbp+57h+var_A8]
0x180071f7a  mov     [rbp+57h+var_90], rbx
0x180071f7e  test    rcx, rcx
0x180071f81  jz      short loc_180071F90
0x180071f83  mov     [rbp+57h+var_A8], 0
0x180071f8b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDialogFirstFrameRenderedHandler@Dialogs@UI@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release(void)
0x180071f90  mov     rdx, [rbp+57h+var_A0]; struct Windows::UI::Popups::IPopupMenu *
0x180071f94  mov     r9, rbx; struct Windows::UI::Popups::IUICommandInvokedHandler *
0x180071f97  mov     r8d, 2264h; unsigned int
0x180071f9d  call    ?_AddCommand@TouchEditContextMenuBehavior@@AEAAJPEAUIPopupMenu@Popups@UI@Windows@@IPEAUIUICommandInvokedHandler@345@@Z; TouchEditContextMenuBehavior::_AddCommand(Windows::UI::Popups::IPopupMenu *,uint,Windows::UI::Popups::IUICommandInvokedHandler *)
0x180071fa2  lea     rcx, [rbp+57h+var_90]
0x180071fa6  mov     edi, eax
0x180071fa8  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180071fad  lea     rcx, [rbp+57h+var_B8]
0x180071fb1  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180071fb6  test    edi, edi
0x180071fb8  js      short loc_180072034
0x180071fba  test    r14b, r14b
0x180071fbd  jnz     short loc_180072034
0x180071fbf  test    r13b, r13b
0x180071fc2  jz      short loc_180072034
0x180071fc4  mov     rcx, [rbp+57h+var_98]
0x180071fc8  mov     [rbp+57h+var_B8], rcx
0x180071fcc  test    rcx, rcx
0x180071fcf  jz      short loc_180071FDD
0x180071fd1  mov     rax, [rcx]
0x180071fd4  mov     rax, [rax+8]
0x180071fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071fdd  lea     rdx, [rbp+57h+var_B8]
0x180071fe1  lea     rcx, [rbp+57h+var_A8]
0x180071fe5  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Popups__IUICommandInvokedHandler_____Windows__UI__Popups__IUICommand______DelegateInvokeHelper_Windows__UI__Popups__IUICommandInvokedHandler__lambda_86143fd989600146d21f638323ca6ae2___1_Windows__UI__Popups__IUICommand_____lambda_86143fd989600146d21f638323ca6ae2___
0x180071fea  mov     rbx, [rax]
0x180071fed  mov     qword ptr [rax], 0
0x180071ff4  mov     rcx, [rbp+57h+var_A8]
0x180071ff8  mov     [rbp+57h+var_90], rbx
0x180071ffc  test    rcx, rcx
0x180071fff  jz      short loc_18007200E
0x180072001  mov     [rbp+57h+var_A8], 0
0x180072009  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDialogFirstFrameRenderedHandler@Dialogs@UI@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release(void)
0x18007200e  mov     rdx, [rbp+57h+var_A0]; struct Windows::UI::Popups::IPopupMenu *
  ... truncated ...
```
