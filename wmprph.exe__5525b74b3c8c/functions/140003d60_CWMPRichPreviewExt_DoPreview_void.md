# CWMPRichPreviewExt::DoPreview(void)

- ea: `0x140003d60`
- end: `0x14000431b`
- name: `?DoPreview@CWMPRichPreviewExt@@UEAAJXZ`
- size: `1467`
- prototype: `__int64 __fastcall(CWMPRichPreviewExt *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400039b0`
- `0x140003d60`
- `0x140008a74`
- `0x1400098d8`
- `0x1400099e0`
- `0x140009a08`
- `0x14000f010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x140003ff0`
- `KERNEL32!RaiseException` at `0x1400040eb`
- `KERNEL32!RaiseException` at `0x140003ff0`
- `KERNEL32!RaiseException` at `0x1400040eb`
- `USER32!PostMessageW` at `0x14000420d`
- `USER32!PostMessageW` at `0x14000420d`
- `USER32!GetThreadDpiAwarenessContext` at `0x140003dea`
- `USER32!GetThreadDpiAwarenessContext` at `0x140003dea`
- `USER32!DestroyWindow` at `0x140003de4`
- `USER32!DestroyWindow` at `0x140003de4`
- `USER32!CreateWindowExW` at `0x140003e8b`
- `USER32!CreateWindowExW` at `0x140003e8b`
- `USER32!SendMessageW` at `0x140003eaf`
- `USER32!SendMessageW` at `0x140003f0a`
- `USER32!SendMessageW` at `0x140004041`
- `USER32!SendMessageW` at `0x140003eaf`
- `USER32!SendMessageW` at `0x140003f0a`
- `USER32!SendMessageW` at `0x140004041`
- `USER32!ShowWindow` at `0x1400041e8`
- `USER32!ShowWindow` at `0x1400041e8`
- `USER32!GetDesktopWindow` at `0x140003e2d`
- `USER32!GetDesktopWindow` at `0x140003e2d`
- `USER32!GetWindowDpiAwarenessContext` at `0x140003e03`
- `USER32!GetWindowDpiAwarenessContext` at `0x140003e03`
- `USER32!SetParent` at `0x1400041d2`
- `USER32!SetParent` at `0x1400041d2`
- `USER32!AreDpiAwarenessContextsEqual` at `0x140003e12`
- `USER32!AreDpiAwarenessContextsEqual` at `0x140003e12`
- `USER32!SetThreadDpiAwarenessContext` at `0x140003e1f`
- `USER32!SetThreadDpiAwarenessContext` at `0x1400041b5`
- `USER32!SetThreadDpiAwarenessContext` at `0x140003e1f`
- `USER32!SetThreadDpiAwarenessContext` at `0x1400041b5`
- `OLEAUT32!__imp_SysAllocString` at `0x140003fcc`
- `OLEAUT32!__imp_SysAllocString` at `0x1400040cc`
- `OLEAUT32!__imp_SysAllocString` at `0x14000421f`
- `OLEAUT32!__imp_SysAllocString` at `0x140003fcc`
- `OLEAUT32!__imp_SysAllocString` at `0x1400040cc`
- `OLEAUT32!__imp_SysAllocString` at `0x14000421f`
- `OLEAUT32!__imp_SysFreeString` at `0x14000401c`
- `OLEAUT32!__imp_SysFreeString` at `0x14000410f`
- `OLEAUT32!__imp_SysFreeString` at `0x140004243`
- `OLEAUT32!__imp_SysFreeString` at `0x14000401c`
- `OLEAUT32!__imp_SysFreeString` at `0x14000410f`
- `OLEAUT32!__imp_SysFreeString` at `0x140004243`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewExt::DoPreview(CWMPRichPreviewExt *this)
{
  int Instance; // ebx
  __int64 ThreadDpiAwarenessContext; // rax
  __int64 v4; // rcx
  char v5; // r13
  __int64 v6; // rsi
  __int64 WindowDpiAwarenessContext; // rbx
  HWND hWndParent; // rax
  HWND Window; // rax
  UINT v10; // edx
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v12; // r8
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rsi
  HWND v14; // rcx
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rax
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rsi
  _QWORD *v17; // rsi
  __int64 v18; // rbx
  __int64 v19; // r15
  __int64 (__fastcall *v20)(__int64, const WCHAR *, __int64, _QWORD); // r12
  BSTR v21; // rax
  const WCHAR *v22; // r14
  OLECHAR *v23; // rsi
  const WCHAR *v24; // rdx
  HWND v25; // rcx
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rax
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 v28; // rsi
  void (__fastcall *v29)(__int64, const WCHAR *); // r15
  BSTR v30; // rax
  OLECHAR *v31; // rbx
  __int64 v32; // rsi
  __int64 v33; // rcx
  OLECHAR *v34; // rsi
  __int64 v36; // [rsp+60h] [rbp-9h] BYREF
  __int64 v37; // [rsp+68h] [rbp-1h] BYREF
  ULONG_PTR Arguments; // [rsp+70h] [rbp+7h] BYREF
  __int64 v39; // [rsp+78h] [rbp+Fh]
  __int64 v40; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v41; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v42; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v43; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_a1620705688d36e506283508f1a041e6_Traceguids);
  }
  *((_BYTE *)this + 153) = 1;
  v42 = 0;
  v41 = 0;
  v37 = 0;
  v40 = 0;
  v36 = 0;
  v43 = 0;
  if ( *((_QWORD *)this + 6) )
  {
    Instance = 0;
LABEL_43:
    SetParent(*(HWND *)(*((_QWORD *)this + 17) + 8LL), *((HWND *)this + 12));
    ShowWindow(*(HWND *)(*((_QWORD *)this + 17) + 8LL), 1);
    if ( *((_BYTE *)this + 152) )
    {
      PostMessageW(*(HWND *)(*((_QWORD *)this + 17) + 8LL), 0x400u, 0, 0);
    }
    else if ( *((_QWORD *)this + 6) )
    {
      v34 = SysAllocString(*((const OLECHAR **)this + 7));
      if ( v34 )
      {
        (*(void (__fastcall **)(_QWORD, OLECHAR *))(**((_QWORD **)this + 6) + 72LL))(*((_QWORD *)this + 6), v34);
        SysFreeString(v34);
      }
      else
      {
        Instance = -2147024882;
      }
    }
    goto LABEL_49;
  }
  DestroyWindow(*((HWND *)this + 10));
  ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext();
  v4 = *((_QWORD *)this + 12);
  v5 = 0;
  v39 = ThreadDpiAwarenessContext;
  v6 = ThreadDpiAwarenessContext;
  if ( v4 )
  {
    WindowDpiAwarenessContext = GetWindowDpiAwarenessContext();
    if ( !(unsigned int)AreDpiAwarenessContextsEqual(WindowDpiAwarenessContext, v6) )
    {
      SetThreadDpiAwarenessContext(WindowDpiAwarenessContext);
      v5 = 1;
    }
  }
  AtlAxWinInit();
  hWndParent = GetDesktopWindow();
  Window = CreateWindowExW(
             8u,
             L"AtlAxWin",
             0,
             0x46000000u,
             *((_DWORD *)this + 26),
             *((_DWORD *)this + 27),
             *((_DWORD *)this + 28) - *((_DWORD *)this + 26),
             *((_DWORD *)this + 29) - *((_DWORD *)this + 27),
             hWndParent,
             0,
             hInstance,
             0);
  v10 = ATL::WM_ATLGETHOST;
  *((_QWORD *)this + 16) = Window;
  *((_QWORD *)this + 10) = Window;
  v42 = 0;
  v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))SendMessageW(Window, v10, 0, 0);
  v13 = v11;
  if ( !v11 )
    goto LABEL_39;
  Instance = (**v11)(v11, &GUID_b6ea2050_048a_11d1_82b9_00c04fb9942e, &v42);
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v13)[2])(v13);
  if ( Instance < 0 )
    goto LABEL_40;
  v14 = (HWND)*((_QWORD *)this + 16);
  v41 = 0;
  v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))SendMessageW(v14, ATL::WM_ATLGETHOST, 0, 0);
  v16 = v15;
  if ( !v15 )
    goto LABEL_39;
  Instance = (**v15)(v15, &GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352, &v41);
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v16)[2])(v16);
  if ( Instance >= 0 )
  {
    v17 = (_QWORD *)((char *)this + 120);
    *((_QWORD *)this + 15) = 0;
    Instance = ATL::CComObject<CWMPRichPreviewRemoteService>::CreateInstance((char *)this + 120);
    if ( Instance >= 0 )
    {
      *(_QWORD *)(*v17 + 32LL) = this;
      Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v17)(*v17, &IID_IUnknown, &v37);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 24LL))(v41, v37);
        if ( Instance >= 0 )
        {
          v18 = v42;
          v19 = *((_QWORD *)this + 16);
          Arguments = (ULONG_PTR)L"{6BF52A52-394A-11d3-B153-00C04F79FAA6}";
          v20 = *(__int64 (__fastcall **)(__int64, const WCHAR *, __int64, _QWORD))(*(_QWORD *)v42 + 24LL);
          v21 = SysAllocString(L"{6BF52A52-394A-11d3-B153-00C04F79FAA6}");
          v22 = &WindowName;
          v23 = v21;
          if ( v21 )
          {
            v24 = v21;
          }
          else
          {
            RaiseException(0x8007000E, 1u, 1u, &Arguments);
            v24 = &WindowName;
          }
          Instance = v20(v18, v24, v19, 0);
          if ( v23 )
            SysFreeString(v23);
          if ( Instance >= 0 )
          {
            v25 = (HWND)*((_QWORD *)this + 16);
            v40 = 0;
            v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))SendMessageW(v25, ATL::WM_ATLGETCONTROL, 0, 0);
            v27 = v26;
            if ( v26 )
            {
              Instance = (**v26)(v26, &GUID_6c497d62_8919_413c_82db_e935fb3ec584, &v40);
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v27)[2])(v27);
              if ( Instance >= 0 )
              {
                if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 104LL))(v40, &v36) >= 0 )
                {
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v36 + 72LL))(v36, 0);
                  v28 = v40;
                  Arguments = (ULONG_PTR)L"custom";
                  v29 = *(void (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)v40 + 296LL);
                  v30 = SysAllocString(L"custom");
                  v31 = v30;
                  if ( v30 )
                  {
                    v22 = v30;
                  }
                  else
                  {
                    RaiseException(0x8007000E, 1u, 1u, &Arguments);
                    v31 = 0;
                  }
                  v29(v28, v22);
                  if ( v31 )
                    SysFreeString(v31);
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v40 + 288LL))(v40, 0);
                  Instance = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v40)(
                               v40,
                               &GUID_3608a1bb_1883_4cc0_9da8_b4cf25943842,
                               &v43);
                  if ( Instance >= 0 )
                    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 184LL))(v43, 0xFFFFFFFFLL);
                }
                v32 = v40;
                if ( v40 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
                v33 = *((_QWORD *)this + 6);
                if ( v33 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                *((_QWORD *)this + 6) = v32;
                if ( Instance >= 0 )
                  ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::SubclassWindow(
                    *((_QWORD *)this + 17),
                    *((HWND *)this + 10));
              }
              goto LABEL_40;
            }
LABEL_39:
            Instance = -2147467259;
          }
        }
      }
    }
  }
LABEL_40:
  if ( v5 )
    SetThreadDpiAwarenessContext(v39);
  if ( Instance >= 0 )
    goto LABEL_43;
LABEL_49:
  *((_BYTE *)this + 153) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v12, (unsigned int)Instance);
  }
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140003d60  push    rbp
0x140003d62  push    rbx
0x140003d63  push    rsi
0x140003d64  push    rdi
0x140003d65  push    r12
0x140003d67  push    r13
0x140003d69  push    r14
0x140003d6b  push    r15
0x140003d6d  lea     rbp, [rsp-1Fh]
0x140003d72  sub     rsp, 88h
0x140003d79  mov     rdi, rcx
0x140003d7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d83  lea     rax, WPP_GLOBAL_Control
0x140003d8a  cmp     rcx, rax
0x140003d8d  jz      short loc_140003DB0
0x140003d8f  test    byte ptr [rcx+1Ch], 1
0x140003d93  jz      short loc_140003DB0
0x140003d95  cmp     byte ptr [rcx+19h], 5
0x140003d99  jb      short loc_140003DB0
0x140003d9b  mov     rcx, [rcx+10h]
0x140003d9f  lea     r8, WPP_a1620705688d36e506283508f1a041e6_Traceguids
0x140003da6  mov     edx, 18h
0x140003dab  call    WPP_SF_
0x140003db0  xor     r12d, r12d
0x140003db3  mov     byte ptr [rdi+99h], 1
0x140003dba  mov     [rbp+57h+arg_10], r12
0x140003dbe  mov     [rbp+57h+arg_8], r12
0x140003dc2  mov     [rbp+57h+var_58], r12
0x140003dc6  mov     [rbp+57h+arg_0], r12
0x140003dca  mov     [rbp+57h+var_60], r12
0x140003dce  mov     [rbp+57h+arg_18], r12
0x140003dd2  cmp     [rdi+30h], r12
0x140003dd6  jz      short loc_140003DE0
0x140003dd8  mov     ebx, r12d
0x140003ddb  jmp     loc_1400041C3
0x140003de0  mov     rcx, [rdi+50h]; hWnd
0x140003de4  call    cs:__imp_DestroyWindow
0x140003dea  call    cs:__imp_GetThreadDpiAwarenessContext
0x140003df0  mov     rcx, [rdi+60h]
0x140003df4  mov     r13b, r12b
0x140003df7  mov     [rbp+57h+var_48], rax
0x140003dfb  mov     rsi, rax
0x140003dfe  test    rcx, rcx
0x140003e01  jz      short loc_140003E28
0x140003e03  call    cs:__imp_GetWindowDpiAwarenessContext
0x140003e09  mov     rcx, rax
0x140003e0c  mov     rdx, rsi
0x140003e0f  mov     rbx, rax
0x140003e12  call    cs:__imp_AreDpiAwarenessContextsEqual
0x140003e18  test    eax, eax
0x140003e1a  jnz     short loc_140003E28
0x140003e1c  mov     rcx, rbx
0x140003e1f  call    cs:__imp_SetThreadDpiAwarenessContext
0x140003e25  mov     r13b, 1
0x140003e28  call    AtlAxWinInit
0x140003e2d  call    cs:__imp_GetDesktopWindow
0x140003e33  mov     r9d, [rdi+6Ch]
0x140003e37  mov     r8, rax
0x140003e3a  mov     edx, [rdi+74h]
0x140003e3d  mov     r10d, [rdi+68h]
0x140003e41  sub     edx, r9d
0x140003e44  mov     rax, cs:hInstance
0x140003e4b  mov     ecx, [rdi+70h]
0x140003e4e  mov     [rsp+0C0h+lpParam], r12; lpParam
0x140003e53  sub     ecx, r10d
0x140003e56  mov     [rsp+0C0h+hInstance], rax; hInstance
0x140003e5b  mov     [rsp+0C0h+hMenu], r12; hMenu
0x140003e60  mov     [rsp+0C0h+hWndParent], r8; hWndParent
0x140003e65  xor     r8d, r8d; lpWindowName
0x140003e68  mov     [rsp+0C0h+nHeight], edx; nHeight
0x140003e6c  lea     rdx, ClassName; "AtlAxWin"
0x140003e73  mov     [rsp+0C0h+nWidth], ecx; nWidth
0x140003e77  mov     [rsp+0C0h+Y], r9d; Y
0x140003e7c  mov     r9d, 46000000h; dwStyle
0x140003e82  lea     ecx, [r8+8]; dwExStyle
0x140003e86  mov     [rsp+0C0h+X], r10d; X
0x140003e8b  call    cs:__imp_CreateWindowExW
0x140003e91  mov     edx, cs:?WM_ATLGETHOST@ATL@@3IA; Msg
0x140003e97  xor     r9d, r9d; lParam
0x140003e9a  mov     [rdi+80h], rax
0x140003ea1  mov     rcx, rax; hWnd
0x140003ea4  xor     r8d, r8d; wParam
0x140003ea7  mov     [rdi+50h], rax
0x140003eab  mov     [rbp+57h+arg_10], r12
0x140003eaf  call    cs:__imp_SendMessageW
0x140003eb5  mov     rsi, rax
0x140003eb8  test    rax, rax
0x140003ebb  jz      loc_1400041A7
0x140003ec1  mov     rax, [rax]
0x140003ec4  lea     r8, [rbp+57h+arg_10]
0x140003ec8  lea     rdx, _GUID_b6ea2050_048a_11d1_82b9_00c04fb9942e
0x140003ecf  mov     rcx, rsi
0x140003ed2  mov     rax, [rax]
0x140003ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003eda  mov     ebx, eax
0x140003edc  mov     rcx, rsi
0x140003edf  mov     rax, [rsi]
0x140003ee2  mov     rax, [rax+10h]
0x140003ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003eeb  test    ebx, ebx
0x140003eed  js      loc_1400041AC
0x140003ef3  mov     edx, cs:?WM_ATLGETHOST@ATL@@3IA; Msg
0x140003ef9  xor     r9d, r9d; lParam
0x140003efc  mov     rcx, [rdi+80h]; hWnd
0x140003f03  xor     r8d, r8d; wParam
0x140003f06  mov     [rbp+57h+arg_8], r12
0x140003f0a  call    cs:__imp_SendMessageW
0x140003f10  mov     rsi, rax
0x140003f13  test    rax, rax
0x140003f16  jz      loc_1400041A7
0x140003f1c  mov     rax, [rax]
0x140003f1f  lea     r8, [rbp+57h+arg_8]
0x140003f23  lea     rdx, _GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352
0x140003f2a  mov     rcx, rsi
0x140003f2d  mov     rax, [rax]
0x140003f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f35  mov     ebx, eax
0x140003f37  mov     rcx, rsi
0x140003f3a  mov     rax, [rsi]
0x140003f3d  mov     rax, [rax+10h]
0x140003f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f46  test    ebx, ebx
0x140003f48  js      loc_1400041AC
0x140003f4e  lea     rsi, [rdi+78h]
0x140003f52  mov     rcx, rsi
0x140003f55  mov     [rsi], r12
0x140003f58  call    ?CreateInstance@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWMPRichPreviewRemoteService>::CreateInstance(ATL::CComObject<CWMPRichPreviewRemoteService> * *)
0x140003f5d  mov     ebx, eax
0x140003f5f  test    eax, eax
0x140003f61  js      loc_1400041AC
0x140003f67  mov     rax, [rsi]
0x140003f6a  lea     r8, [rbp+57h+var_58]
0x140003f6e  lea     rdx, IID_IUnknown
0x140003f75  mov     [rax+20h], rdi
0x140003f79  mov     rcx, [rsi]
0x140003f7c  mov     rax, [rcx]
0x140003f7f  mov     rax, [rax]
0x140003f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f87  mov     ebx, eax
0x140003f89  test    eax, eax
0x140003f8b  js      loc_1400041AC
0x140003f91  mov     rcx, [rbp+57h+arg_8]
0x140003f95  mov     rdx, [rbp+57h+var_58]
0x140003f99  mov     rax, [rcx]
0x140003f9c  mov     rax, [rax+18h]
0x140003fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fa5  mov     ebx, eax
0x140003fa7  test    eax, eax
0x140003fa9  js      loc_1400041AC
0x140003faf  mov     rbx, [rbp+57h+arg_10]
0x140003fb3  lea     rcx, a6bf52a52394a11; "{6BF52A52-394A-11d3-B153-00C04F79FAA6}"
0x140003fba  mov     r15, [rdi+80h]
0x140003fc1  mov     [rbp+57h+Arguments], rcx
0x140003fc5  mov     rax, [rbx]
0x140003fc8  mov     r12, [rax+18h]
0x140003fcc  call    cs:__imp_SysAllocString
0x140003fd2  lea     r14, WindowName
0x140003fd9  mov     rsi, rax
0x140003fdc  test    rax, rax
0x140003fdf  jnz     short loc_140003FFB
0x140003fe1  lea     edx, [rax+1]; dwExceptionFlags
0x140003fe4  mov     ecx, 8007000Eh; dwExceptionCode
0x140003fe9  mov     r8d, edx; nNumberOfArguments
0x140003fec  lea     r9, [rbp+57h+Arguments]; lpArguments
0x140003ff0  call    cs:__imp_RaiseException
0x140003ff6  mov     rdx, r14
0x140003ff9  jmp     short loc_140003FFE
0x140003ffb  mov     rdx, rax
0x140003ffe  xor     r9d, r9d
0x140004001  mov     r8, r15
0x140004004  mov     rcx, rbx
0x140004007  mov     rax, r12
0x14000400a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000400f  xor     r12d, r12d
0x140004012  mov     ebx, eax
0x140004014  test    rsi, rsi
0x140004017  jz      short loc_140004022
0x140004019  mov     rcx, rsi; bstrString
0x14000401c  call    cs:__imp_SysFreeString
0x140004022  test    ebx, ebx
0x140004024  js      loc_1400041AC
0x14000402a  mov     edx, cs:?WM_ATLGETCONTROL@ATL@@3IA; Msg
0x140004030  xor     r9d, r9d; lParam
0x140004033  mov     rcx, [rdi+80h]; hWnd
0x14000403a  xor     r8d, r8d; wParam
0x14000403d  mov     [rbp+57h+arg_0], r12
0x140004041  call    cs:__imp_SendMessageW
0x140004047  mov     rsi, rax
0x14000404a  test    rax, rax
0x14000404d  jz      loc_1400041A7
0x140004053  mov     rcx, [rax]
0x140004056  lea     r8, [rbp+57h+arg_0]
0x14000405a  lea     rdx, _GUID_6c497d62_8919_413c_82db_e935fb3ec584
0x140004061  mov     rax, [rcx]
0x140004064  mov     rcx, rsi
0x140004067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000406c  mov     rcx, [rsi]
0x14000406f  mov     ebx, eax
0x140004071  mov     rax, [rcx+10h]
0x140004075  mov     rcx, rsi
0x140004078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000407d  test    ebx, ebx
0x14000407f  js      loc_1400041AC
0x140004085  mov     rcx, [rbp+57h+arg_0]
0x140004089  lea     rdx, [rbp+57h+var_60]
0x14000408d  mov     rax, [rcx]
0x140004090  mov     rax, [rax+68h]
0x140004094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004099  test    eax, eax
0x14000409b  js      loc_140004160
0x1400040a1  mov     rcx, [rbp+57h+var_60]
0x1400040a5  xor     edx, edx
0x1400040a7  mov     rax, [rcx]
0x1400040aa  mov     rax, [rax+48h]
0x1400040ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040b3  mov     rsi, [rbp+57h+arg_0]
0x1400040b7  lea     rcx, aCustom; "custom"
0x1400040be  mov     [rbp+57h+Arguments], rcx
0x1400040c2  mov     rax, [rsi]
0x1400040c5  mov     r15, [rax+128h]
0x1400040cc  call    cs:__imp_SysAllocString
0x1400040d2  mov     rbx, rax
0x1400040d5  test    rax, rax
0x1400040d8  jnz     short loc_1400040F6
0x1400040da  lea     eax, [rbx+1]
0x1400040dd  mov     ecx, 8007000Eh; dwExceptionCode
0x1400040e2  mov     r8d, eax; nNumberOfArguments
0x1400040e5  lea     r9, [rbp+57h+Arguments]; lpArguments
0x1400040e9  mov     edx, eax; dwExceptionFlags
0x1400040eb  call    cs:__imp_RaiseException
0x1400040f1  mov     rbx, r12
0x1400040f4  jmp     short loc_1400040F9
0x1400040f6  mov     r14, rax
0x1400040f9  mov     rdx, r14
0x1400040fc  mov     rcx, rsi
0x1400040ff  mov     rax, r15
0x140004102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004107  test    rbx, rbx
0x14000410a  jz      short loc_140004115
0x14000410c  mov     rcx, rbx; bstrString
0x14000410f  call    cs:__imp_SysFreeString
0x140004115  mov     rcx, [rbp+57h+arg_0]
0x140004119  xor     edx, edx
0x14000411b  mov     rax, [rcx]
0x14000411e  mov     rax, [rax+120h]
0x140004125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000412a  mov     rcx, [rbp+57h+arg_0]
0x14000412e  lea     r8, [rbp+57h+arg_18]
0x140004132  lea     rdx, _GUID_3608a1bb_1883_4cc0_9da8_b4cf25943842
0x140004139  mov     rax, [rcx]
0x14000413c  mov     rax, [rax]
0x14000413f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004144  mov     ebx, eax
0x140004146  test    eax, eax
0x140004148  js      short loc_140004160
0x14000414a  mov     rcx, [rbp+57h+arg_18]
0x14000414e  or      edx, 0FFFFFFFFh
0x140004151  mov     rax, [rcx]
0x140004154  mov     rax, [rax+0B8h]
0x14000415b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004160  mov     rsi, [rbp+57h+arg_0]
0x140004164  test    rsi, rsi
0x140004167  jz      short loc_140004178
0x140004169  mov     rax, [rsi]
0x14000416c  mov     rcx, rsi
0x14000416f  mov     rax, [rax+8]
0x140004173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004178  mov     rcx, [rdi+30h]
0x14000417c  test    rcx, rcx
0x14000417f  jz      short loc_14000418D
0x140004181  mov     rax, [rcx]
0x140004184  mov     rax, [rax+10h]
0x140004188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000418d  mov     [rdi+30h], rsi
0x140004191  test    ebx, ebx
0x140004193  js      short loc_1400041AC
0x140004195  mov     rdx, [rdi+50h]; hWnd
0x140004199  mov     rcx, [rdi+88h]; FirstParameter
0x1400041a0  call    ?SubclassWindow@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAHPEAUHWND__@@@Z; ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::SubclassWindow(HWND__ *)
0x1400041a5  jmp     short loc_1400041AC
0x1400041a7  mov     ebx, 80004005h
0x1400041ac  test    r13b, r13b
0x1400041af  jz      short loc_1400041BB
0x1400041b1  mov     rcx, [rbp+57h+var_48]
0x1400041b5  call    cs:__imp_SetThreadDpiAwarenessContext
0x1400041bb  test    ebx, ebx
0x1400041bd  js      loc_140004250
0x1400041c3  mov     rcx, [rdi+88h]
0x1400041ca  mov     rdx, [rdi+60h]; hWndNewParent
0x1400041ce  mov     rcx, [rcx+8]; hWndChild
0x1400041d2  call    cs:__imp_SetParent
0x1400041d8  mov     rcx, [rdi+88h]
0x1400041df  mov     edx, 1; nCmdShow
0x1400041e4  mov     rcx, [rcx+8]; hWnd
0x1400041e8  call    cs:__imp_ShowWindow
0x1400041ee  cmp     [rdi+98h], r12b
0x1400041f5  jz      short loc_140004215
0x1400041f7  mov     rcx, [rdi+88h]
0x1400041fe  xor     r9d, r9d; lParam
0x140004201  xor     r8d, r8d; wParam
  ... truncated ...
```
