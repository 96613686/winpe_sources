# Windows::Internal::CustomPopupWindowOperation::InitializeBridgeToCoreWindow(Windows::Internal::GitEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::CoreWindowPopupShowingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *,IPopupWindow *)

- ea: `0x18004d028`
- end: `0x18004d30e`
- name: `?InitializeBridgeToCoreWindow@CustomPopupWindowOperation@Internal@Windows@@QEAAJPEAV?$GitEventSource@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVCoreWindowPopupShowingEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@23@PEAUIPopupWindow@@@Z`
- size: `742`
- prototype: `__int64 __fastcall(Windows::Internal::CustomPopupWindowOperation *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18008cbbc`

## callees

- `0x1800343ec`
- `0x18004d028`
- `0x180054130`
- `0x180059b4c`
- `0x18007846c`
- `0x1800848b8`
- `0x1800856e0`
- `0x18008911c`
- `0x180089788`
- `0x18008a404`
- `0x18008c6ac`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d1ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d1ed`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18004d1dd`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18004d1dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d0cc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d0cc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004d210`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004d210`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18004d262`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18004d262`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x18004d274`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x18004d274`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18004d24d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18004d24d`
- `DUI70!StrToID` at `0x18004d23b`
- `DUI70!StrToID` at `0x18004d23b`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18004d225`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18004d225`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18004d1b0`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18004d1b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::CustomPopupWindowOperation::InitializeBridgeToCoreWindow(
        void **this,
        __int64 a2,
        IUnknown *a3)
{
  __int64 v6; // rax
  int Window; // ebx
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  signed int LastError; // eax
  DirectUI::Element *Root; // rbx
  unsigned __int16 v12; // ax
  DirectUI::Element *Descendent; // rbx
  int v14; // eax
  __int64 v15; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-40h] BYREF
  __int64 v18; // [rsp+38h] [rbp-38h] BYREF
  __int64 *v19; // [rsp+40h] [rbp-30h] BYREF
  HWND v20; // [rsp+48h] [rbp-28h] BYREF
  struct DirectUI::Element *v21; // [rsp+50h] [rbp-20h] BYREF
  __int128 v22; // [rsp+58h] [rbp-18h] BYREF

  v18 = 0;
  v19 = &v18;
  v6 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v19);
  Window = Microsoft::WRL::AsWeak<IPopupCoreWindowCallback>(this, v6);
  if ( Window >= 0 )
  {
    v20 = 0;
    Window = Windows::Internal::CustomPopupWindowOperation::CreateFrameWindow(
               (Windows::Internal::CustomPopupWindowOperation *)this,
               &v20);
    if ( Window >= 0 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      Window = CoCreateInstance(&CLSID_HostedWindowFactory, 0, 1u, &GUID_9dce39e2_e7d3_46bc_b1b8_1f0d0803da3d, &ppv);
      if ( Window >= 0 )
      {
        v22 = 0;
        Window = (*(__int64 (__fastcall **)(LPVOID, __int64, __int128 *, HWND, GUID *))(*(_QWORD *)ppv + 24LL))(
                   ppv,
                   v18,
                   &v22,
                   v20,
                   &GUID_NULL);
        if ( Window >= 0 )
        {
          v21 = 0;
          Window = Windows::Internal::CustomPopupWindowOperation::SetUpHostDUI(
                     (Windows::Internal::CustomPopupWindowOperation *)this,
                     &v21);
          if ( Window >= 0 )
          {
            v8 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
            v9 = v8;
            if ( v8 )
            {
              *v8 = 0;
              v8[1] = 0;
              v8[3] = 0;
            }
            else
            {
              v9 = 0;
            }
            v19 = v9;
            if ( v9 )
            {
              v9[5] = 0;
              Window = CMarshaledInterface::Marshal(v9, &GUID_cd292360_2763_4085_8a9f_74b224a29175, ppv, 1);
              if ( Window >= 0 )
              {
                v9[4] = a2;
                Window = IUnknown_GetWindow(a3, (HWND *)v9 + 2);
                if ( Window >= 0 )
                {
                  if ( SHCreateThread(
                         Windows::Internal::CustomPopupWindowOperation::s_CoreWindowThreadProc,
                         v9,
                         0x40u,
                         Windows::Internal::CustomPopupWindowOperation::s_CoreWindowInitThreadProc) )
                  {
                    goto LABEL_17;
                  }
                  LastError = GetLastError();
                  Window = LastError;
                  if ( LastError > 0 )
                    Window = (unsigned __int16)LastError | 0x80070000;
                  if ( Window >= 0 )
                  {
LABEL_17:
                    Root = DirectUI::Element::GetRoot(v21);
                    v12 = StrToID(L"ContentArea");
                    Descendent = DirectUI::Element::FindDescendent(Root, v12);
                    DirectUI::Element::SetWidth(Descendent, *((_DWORD *)v9 + 10));
                    DirectUI::Element::SetHeight(Descendent, *((_DWORD *)v9 + 11));
                    v14 = CMarshaledInterface::Unmarshal<Windows::UI::Core::ICoreWindow>(
                            (CMarshaledInterface *)(v9 + 1),
                            this + 19);
                    Window = v14;
                    if ( v14 >= 0 )
                      (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)this[20] + 56LL))(this[20], (unsigned int)v14);
                    v19 = 0;
                  }
                  else
                  {
                    RoOriginateError((unsigned int)Window, 0);
                  }
                }
              }
            }
            else
            {
              Window = -2147024882;
            }
            CAutoMemPtr<Windows::Internal::CUSTOM_POPUP_CORE_WINDOW_THREAD_PARA>::~CAutoMemPtr<Windows::Internal::CUSTOM_POPUP_CORE_WINDOW_THREAD_PARA>(&v19);
          }
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    }
  }
  v15 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return (unsigned int)Window;
}

```

## disassembly

```asm
0x18004d028  mov     [rsp-28h+arg_8], rbx
0x18004d02d  push    rbp
0x18004d02e  push    rsi
0x18004d02f  push    rdi
0x18004d030  push    r14
0x18004d032  push    r15
0x18004d034  mov     rbp, rsp
0x18004d037  sub     rsp, 70h
0x18004d03b  mov     rax, cs:__security_cookie
0x18004d042  xor     rax, rsp
0x18004d045  mov     [rbp+var_8], rax
0x18004d049  mov     r15, r8
0x18004d04c  mov     r14, rdx
0x18004d04f  mov     rsi, rcx
0x18004d052  mov     [rbp+var_38], 0
0x18004d05a  lea     rax, [rbp+var_38]
0x18004d05e  mov     [rbp+var_30], rax
0x18004d062  lea     rcx, [rbp+var_30]
0x18004d066  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18004d06b  mov     rdx, rax
0x18004d06e  mov     rcx, rsi
0x18004d071  call    ??$AsWeak@UIPopupCoreWindowCallback@@@WRL@Microsoft@@YAJPEAUIPopupCoreWindowCallback@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<IPopupCoreWindowCallback>(IPopupCoreWindowCallback *,Microsoft::WRL::WeakRef *)
0x18004d076  mov     ebx, eax
0x18004d078  test    eax, eax
0x18004d07a  js      loc_18004D2CE
0x18004d080  mov     [rbp+var_28], 0
0x18004d088  lea     rdx, [rbp+var_28]; HWND *
0x18004d08c  mov     rcx, rsi; this
0x18004d08f  call    ?CreateFrameWindow@CustomPopupWindowOperation@Internal@Windows@@QEAAJPEAPEAUHWND__@@@Z; Windows::Internal::CustomPopupWindowOperation::CreateFrameWindow(HWND__ * *)
0x18004d094  mov     ebx, eax
0x18004d096  test    eax, eax
0x18004d098  js      loc_18004D2CE
0x18004d09e  mov     [rbp+var_40], 0
0x18004d0a6  lea     rcx, [rbp+var_40]
0x18004d0aa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d0af  lea     rax, [rbp+var_40]
0x18004d0b3  mov     [rsp+70h+ppv], rax; ppv
0x18004d0b8  lea     r9, _GUID_9dce39e2_e7d3_46bc_b1b8_1f0d0803da3d; riid
0x18004d0bf  xor     edx, edx; pUnkOuter
0x18004d0c1  lea     r8d, [rdx+1]; dwClsContext
0x18004d0c5  lea     rcx, CLSID_HostedWindowFactory; rclsid
0x18004d0cc  call    cs:__imp_CoCreateInstance
0x18004d0d3  nop     dword ptr [rax+rax+00h]
0x18004d0d8  mov     ebx, eax
0x18004d0da  test    eax, eax
0x18004d0dc  js      loc_18004D2C4
0x18004d0e2  xorps   xmm0, xmm0
0x18004d0e5  movups  [rbp+var_18], xmm0
0x18004d0e9  mov     rcx, [rbp+var_40]
0x18004d0ed  mov     rax, [rcx]
0x18004d0f0  lea     rdx, GUID_NULL
0x18004d0f7  mov     [rsp+70h+ppv], rdx
0x18004d0fc  mov     r9, [rbp+var_28]
0x18004d100  lea     r8, [rbp+var_18]
0x18004d104  mov     rdx, [rbp+var_38]
0x18004d108  mov     rax, [rax+18h]
0x18004d10c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d111  mov     ebx, eax
0x18004d113  test    eax, eax
0x18004d115  js      loc_18004D2C4
0x18004d11b  mov     [rbp+var_20], 0
0x18004d123  lea     rdx, [rbp+var_20]; struct DirectUI::Element **
0x18004d127  mov     rcx, rsi; this
0x18004d12a  call    ?SetUpHostDUI@CustomPopupWindowOperation@Internal@Windows@@QEAAJPEAPEAVElement@DirectUI@@@Z; Windows::Internal::CustomPopupWindowOperation::SetUpHostDUI(DirectUI::Element * *)
0x18004d12f  mov     ebx, eax
0x18004d131  test    eax, eax
0x18004d133  js      loc_18004D2C4
0x18004d139  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004d140  mov     ecx, 38h ; '8'; unsigned __int64
0x18004d145  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004d14a  mov     rdi, rax
0x18004d14d  test    rax, rax
0x18004d150  jz      short loc_18004D16B
0x18004d152  mov     qword ptr [rax], 0
0x18004d159  mov     qword ptr [rax+8], 0
0x18004d161  mov     qword ptr [rax+18h], 0
0x18004d169  jmp     short loc_18004D16D
0x18004d16b  xor     edi, edi
0x18004d16d  mov     [rbp+var_30], rdi
0x18004d171  test    rdi, rdi
0x18004d174  jz      loc_18004D2B5
0x18004d17a  mov     qword ptr [rdi+28h], 0
0x18004d182  mov     r9d, 1
0x18004d188  mov     r8, [rbp+var_40]
0x18004d18c  lea     rdx, _GUID_cd292360_2763_4085_8a9f_74b224a29175
0x18004d193  mov     rcx, rdi
0x18004d196  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x18004d19b  mov     ebx, eax
0x18004d19d  test    eax, eax
0x18004d19f  js      loc_18004D2BA
0x18004d1a5  mov     [rdi+20h], r14
0x18004d1a9  lea     rdx, [rdi+10h]; phwnd
0x18004d1ad  mov     rcx, r15; punk
0x18004d1b0  call    cs:__imp_IUnknown_GetWindow
0x18004d1b7  nop     dword ptr [rax+rax+00h]
0x18004d1bc  mov     ebx, eax
0x18004d1be  test    eax, eax
0x18004d1c0  js      loc_18004D2BA
0x18004d1c6  lea     r9, ?s_CoreWindowInitThreadProc@CustomPopupWindowOperation@Internal@Windows@@CAKPEAX@Z; pfnCallback
0x18004d1cd  mov     r8d, 40h ; '@'; flags
0x18004d1d3  mov     rdx, rdi; pData
0x18004d1d6  lea     rcx, ?s_CoreWindowThreadProc@CustomPopupWindowOperation@Internal@Windows@@CAKPEAX@Z; pfnThreadProc
0x18004d1dd  call    cs:__imp_SHCreateThread
0x18004d1e4  nop     dword ptr [rax+rax+00h]
0x18004d1e9  test    eax, eax
0x18004d1eb  jnz     short loc_18004D221
0x18004d1ed  call    cs:__imp_GetLastError
0x18004d1f4  nop     dword ptr [rax+rax+00h]
0x18004d1f9  mov     ebx, eax
0x18004d1fb  test    eax, eax
0x18004d1fd  jle     short loc_18004D208
0x18004d1ff  movzx   ebx, ax
0x18004d202  or      ebx, 80070000h
0x18004d208  test    ebx, ebx
0x18004d20a  jns     short loc_18004D221
0x18004d20c  xor     edx, edx
0x18004d20e  mov     ecx, ebx
0x18004d210  call    cs:__imp_RoOriginateError
0x18004d217  nop     dword ptr [rax+rax+00h]
0x18004d21c  jmp     loc_18004D2BA
0x18004d221  mov     rcx, [rbp+var_20]
0x18004d225  call    cs:__imp_?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetRoot(void)
0x18004d22c  nop     dword ptr [rax+rax+00h]
0x18004d231  mov     rbx, rax
0x18004d234  lea     rcx, aContentarea; "ContentArea"
0x18004d23b  call    cs:__imp_StrToID
0x18004d242  nop     dword ptr [rax+rax+00h]
0x18004d247  movzx   edx, ax
0x18004d24a  mov     rcx, rbx
0x18004d24d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18004d254  nop     dword ptr [rax+rax+00h]
0x18004d259  mov     rbx, rax
0x18004d25c  mov     edx, [rdi+28h]
0x18004d25f  mov     rcx, rax
0x18004d262  call    cs:__imp_?SetWidth@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetWidth(int)
0x18004d269  nop     dword ptr [rax+rax+00h]
0x18004d26e  mov     edx, [rdi+2Ch]
0x18004d271  mov     rcx, rbx
0x18004d274  call    cs:__imp_?SetHeight@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetHeight(int)
0x18004d27b  nop     dword ptr [rax+rax+00h]
0x18004d280  lea     rdx, [rsi+98h]; void **
0x18004d287  lea     rcx, [rdi+8]; this
0x18004d28b  call    ??$Unmarshal@UICoreWindow@Core@UI@Windows@@@CMarshaledInterface@@QEAAJV?$ComPtrRef@V?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; CMarshaledInterface::Unmarshal<Windows::UI::Core::ICoreWindow>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>>)
0x18004d290  mov     ebx, eax
0x18004d292  test    eax, eax
0x18004d294  js      short loc_18004D2AB
0x18004d296  mov     rcx, [rsi+0A0h]
0x18004d29d  mov     rax, [rcx]
0x18004d2a0  mov     edx, ebx
0x18004d2a2  mov     rax, [rax+38h]
0x18004d2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2ab  mov     [rbp+var_30], 0
0x18004d2b3  jmp     short loc_18004D2BA
0x18004d2b5  mov     ebx, 8007000Eh
0x18004d2ba  lea     rcx, [rbp+var_30]
0x18004d2be  call    ??1?$CAutoMemPtr@UCUSTOM_POPUP_CORE_WINDOW_THREAD_PARA@Internal@Windows@@@@QEAA@XZ; CAutoMemPtr<Windows::Internal::CUSTOM_POPUP_CORE_WINDOW_THREAD_PARA>::~CAutoMemPtr<Windows::Internal::CUSTOM_POPUP_CORE_WINDOW_THREAD_PARA>(void)
0x18004d2c3  nop
0x18004d2c4  lea     rcx, [rbp+var_40]
0x18004d2c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d2cd  nop
0x18004d2ce  mov     rcx, [rbp+var_38]
0x18004d2d2  test    rcx, rcx
0x18004d2d5  jz      short loc_18004D2EB
0x18004d2d7  mov     [rbp+var_38], 0
0x18004d2df  mov     rax, [rcx]
0x18004d2e2  mov     rax, [rax+10h]
0x18004d2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2eb  mov     eax, ebx
0x18004d2ed  mov     rcx, [rbp+var_8]
0x18004d2f1  xor     rcx, rsp; StackCookie
0x18004d2f4  call    __security_check_cookie
0x18004d2f9  mov     rbx, [rsp+70h+arg_8]
0x18004d301  add     rsp, 70h
0x18004d305  pop     r15
0x18004d307  pop     r14
0x18004d309  pop     rdi
0x18004d30a  pop     rsi
0x18004d30b  pop     rbp
0x18004d30c  retn
```
