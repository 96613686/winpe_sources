# CSetImageFeedDialog::CreateAndShow(void)

- ea: `0x1800d596c`
- end: `0x1800d5d3f`
- name: `?CreateAndShow@CSetImageFeedDialog@@QEAAJXZ`
- size: `979`
- prototype: `__int64 __fastcall(CSetImageFeedDialog *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d68d0`

## callees

- `0x18000af00`
- `0x180013f14`
- `0x1800343ec`
- `0x18003f720`
- `0x180050fc0`
- `0x180054130`
- `0x180085690`
- `0x180088914`
- `0x1800d596c`
- `0x1800d6a90`
- `0x1800d6b9c`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d5b60`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d5b60`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d5a7f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d5a7f`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800d59bb`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800d59bb`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800d5d05`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800d5d05`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800d59e6`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800d59e6`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800d5a22`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800d5a22`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d5cf4`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d5cf4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSetImageFeedDialog::CreateAndShow(CSetImageFeedDialog *this)
{
  HRESULT v2; // ebx
  LPVOID v3; // rdi
  __int64 (__fastcall *v4)(LPVOID, _QWORD, struct IPopupWindow **); // rbx
  UINT v5; // edx
  __int64 v6; // rbx
  int v7; // eax
  struct IPopupWindow *v8; // rbx
  __int64 (__fastcall *v9)(struct IPopupWindow *, CSetImageFeedDialog *); // r14
  CSetImageFeedDialog **v10; // rax
  CSetImageFeedDialog *v11; // rdi
  struct IPopupWindow *v13; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v14[2]; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  CSetImageFeedDialog *v16; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B0h]
  __int64 v18; // [rsp+58h] [rbp-A8h]
  struct DirectUI::Element *v19; // [rsp+60h] [rbp-A0h] BYREF
  struct DirectUI::DUIXmlParser *v20; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  v20 = 0;
  v2 = DirectUI::DUIXmlParser::Create(&v20, 0, 0, 0, 0);
  if ( v2 >= 0 )
  {
    v2 = DirectUI::DUIXmlParser::SetXMLFromResource(v20, *((_DWORD *)this + 6), &_ImageBase, &_ImageBase);
    if ( v2 < 0 )
      goto LABEL_27;
    v19 = 0;
    v2 = DirectUI::DUIXmlParser::CreateElement(v20, L"main", 0, 0, 0, &v19);
    if ( v2 < 0 )
      goto LABEL_27;
    v2 = CSetImageFeedDialog::_SetDialogDUI(this, v19);
    if ( v2 < 0 )
      goto LABEL_26;
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v2 = CoCreateInstance(&CLSID_PopupWindowFactory, 0, 1u, &GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1, &ppv);
    if ( v2 < 0 )
    {
LABEL_25:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      if ( v2 >= 0 )
      {
LABEL_27:
        DirectUI::DUIXmlParser::Destroy(v20);
        return (unsigned int)v2;
      }
LABEL_26:
      DirectUI::Element::Destroy(v19, 0);
      goto LABEL_27;
    }
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1);
    v13 = 0;
    v3 = ppv;
    v4 = *(__int64 (__fastcall **)(LPVOID, _QWORD, struct IPopupWindow **))(*(_QWORD *)ppv + 72LL);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v13);
    v2 = v4(v3, *((_QWORD *)this + 6), &v13);
    if ( v2 >= 0 )
    {
      v5 = *((_DWORD *)this + 8);
      if ( v5 == 38326 )
      {
        v16 = 0;
        v17 = 0;
        v18 = 0;
        v6 = *((_QWORD *)this + 7);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
        v17 = -1;
        v18 = -1;
        if ( (int)ResourceStringCoAllocFormatMessage(&_ImageBase, 38326, &v16, v6) >= 0 )
          (*(void (__fastcall **)(struct IPopupWindow *, CSetImageFeedDialog *))(*(_QWORD *)v13 + 32LL))(v13, v16);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
      }
      else if ( LoadStringW(&_ImageBase, v5, Buffer, 260) > 0 )
      {
        (*(void (__fastcall **)(struct IPopupWindow *, WCHAR *))(*(_QWORD *)v13 + 32LL))(v13, Buffer);
      }
      v2 = (*(__int64 (__fastcall **)(struct IPopupWindow *, struct DirectUI::Element *))(*(_QWORD *)v13 + 352LL))(
             v13,
             v19);
      if ( v2 >= 0 )
      {
        if ( *((_DWORD *)this + 6) != 38918 )
        {
          v14[0] = 38337;
          v7 = CSetImageFeedDialog::_SetCommands(this, v13, v14, 1u);
LABEL_19:
          v2 = v7;
          if ( v7 >= 0 )
          {
            v8 = v13;
            v9 = *(__int64 (__fastcall **)(struct IPopupWindow *, CSetImageFeedDialog *))(*(_QWORD *)v13 + 168LL);
            v16 = this;
            v17 = (__int64)CSetImageFeedDialog::OnDismissCommand;
            LODWORD(v18) = 0;
            HIDWORD(v18) = (unsigned __int64)CSetImageFeedDialog::OnDismissCommand >> 32;
            v10 = (CSetImageFeedDialog **)Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_74447f3d681dc015fa527b5932f57c48_,-1,IPopupWindow *>,_lambda_74447f3d681dc015fa527b5932f57c48_>(
                                            v14,
                                            &v16);
            v11 = *v10;
            v16 = *v10;
            *v10 = 0;
            if ( *(_QWORD *)v14 )
            {
              *(_QWORD *)v14 = 0;
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release();
            }
            v2 = v9(v8, v11);
            Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v16);
            if ( v2 >= 0 )
            {
              Microsoft::WRL::ComPtr<IPopupWindow>::operator=((char *)this + 16, &v13);
              v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 272LL))(*((_QWORD *)this + 2));
            }
          }
          goto LABEL_24;
        }
        v14[0] = 38330;
        v14[1] = 38329;
        v2 = CSetImageFeedDialog::_SetCommands(this, v13, v14, 2u);
        if ( v2 >= 0 )
        {
          v2 = (*(__int64 (__fastcall **)(struct IPopupWindow *, __int64))(*(_QWORD *)v13 + 88LL))(v13, 1);
          if ( v2 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(struct IPopupWindow *, __int64))(*(_QWORD *)v13 + 120LL))(v13, 1);
            goto LABEL_19;
          }
        }
      }
    }
LABEL_24:
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v13);
    goto LABEL_25;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800d596c  mov     [rsp-8+arg_8], rbx
0x1800d5971  mov     [rsp-8+arg_10], rsi
0x1800d5976  push    rbp
0x1800d5977  push    rdi
0x1800d5978  push    r12
0x1800d597a  push    r14
0x1800d597c  push    r15
0x1800d597e  lea     rbp, [rsp-190h]
0x1800d5986  sub     rsp, 290h
0x1800d598d  mov     rax, cs:__security_cookie
0x1800d5994  xor     rax, rsp
0x1800d5997  mov     [rbp+1B0h+var_30], rax
0x1800d599e  mov     rsi, rcx
0x1800d59a1  xor     r15d, r15d
0x1800d59a4  mov     [rsp+2B0h+var_248], r15
0x1800d59a9  mov     [rsp+2B0h+ppv], r15
0x1800d59ae  xor     r9d, r9d
0x1800d59b1  xor     r8d, r8d
0x1800d59b4  xor     edx, edx
0x1800d59b6  lea     rcx, [rsp+2B0h+var_248]
0x1800d59bb  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x1800d59c2  nop     dword ptr [rax+rax+00h]
0x1800d59c7  mov     ebx, eax
0x1800d59c9  test    eax, eax
0x1800d59cb  js      loc_1800D5D11
0x1800d59d1  lea     r14, __ImageBase
0x1800d59d8  mov     r9, r14
0x1800d59db  mov     r8, r14
0x1800d59de  mov     edx, [rsi+18h]
0x1800d59e1  mov     rcx, [rsp+2B0h+var_248]
0x1800d59e6  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x1800d59ed  nop     dword ptr [rax+rax+00h]
0x1800d59f2  mov     ebx, eax
0x1800d59f4  test    eax, eax
0x1800d59f6  js      loc_1800D5D00
0x1800d59fc  mov     [rsp+2B0h+var_250], r15
0x1800d5a01  lea     rax, [rsp+2B0h+var_250]
0x1800d5a06  mov     [rsp+2B0h+var_288], rax
0x1800d5a0b  mov     [rsp+2B0h+ppv], r15
0x1800d5a10  xor     r9d, r9d
0x1800d5a13  xor     r8d, r8d
0x1800d5a16  lea     rdx, aMain; "main"
0x1800d5a1d  mov     rcx, [rsp+2B0h+var_248]
0x1800d5a22  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1800d5a29  nop     dword ptr [rax+rax+00h]
0x1800d5a2e  mov     ebx, eax
0x1800d5a30  test    eax, eax
0x1800d5a32  js      loc_1800D5D00
0x1800d5a38  mov     rdx, [rsp+2B0h+var_250]; struct DirectUI::Element *
0x1800d5a3d  mov     rcx, rsi; this
0x1800d5a40  call    ?_SetDialogDUI@CSetImageFeedDialog@@AEAAJPEAVElement@DirectUI@@@Z; CSetImageFeedDialog::_SetDialogDUI(DirectUI::Element *)
0x1800d5a45  mov     ebx, eax
0x1800d5a47  test    eax, eax
0x1800d5a49  js      loc_1800D5CED
0x1800d5a4f  mov     [rsp+2B0h+var_270], r15
0x1800d5a54  lea     rcx, [rsp+2B0h+var_270]
0x1800d5a59  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d5a5e  lea     rax, [rsp+2B0h+var_270]
0x1800d5a63  mov     [rsp+2B0h+ppv], rax; ppv
0x1800d5a68  lea     r9, _GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1; riid
0x1800d5a6f  lea     r12d, [r15+1]
0x1800d5a73  mov     r8d, r12d; dwClsContext
0x1800d5a76  xor     edx, edx; pUnkOuter
0x1800d5a78  lea     rcx, CLSID_PopupWindowFactory; rclsid
0x1800d5a7f  call    cs:__imp_CoCreateInstance
0x1800d5a86  nop     dword ptr [rax+rax+00h]
0x1800d5a8b  mov     ebx, eax
0x1800d5a8d  test    eax, eax
0x1800d5a8f  js      loc_1800D5CDF
0x1800d5a95  mov     rcx, [rsp+2B0h+var_270]
0x1800d5a9a  mov     rax, [rcx]
0x1800d5a9d  mov     edx, r12d
0x1800d5aa0  mov     rax, [rax+18h]
0x1800d5aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5aa9  mov     [rsp+2B0h+var_280], r15
0x1800d5aae  mov     rdi, [rsp+2B0h+var_270]
0x1800d5ab3  mov     rax, [rdi]
0x1800d5ab6  mov     rbx, [rax+48h]
0x1800d5aba  lea     rcx, [rsp+2B0h+var_280]
0x1800d5abf  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800d5ac4  lea     r8, [rsp+2B0h+var_280]
0x1800d5ac9  mov     rdx, [rsi+30h]
0x1800d5acd  mov     rcx, rdi
0x1800d5ad0  mov     rax, rbx
0x1800d5ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5ad8  mov     ebx, eax
0x1800d5ada  test    eax, eax
0x1800d5adc  js      loc_1800D5CD4
0x1800d5ae2  mov     edx, [rsi+20h]; uID
0x1800d5ae5  mov     edi, 95B6h
0x1800d5aea  cmp     edx, edi
0x1800d5aec  jnz     short loc_1800D5B52
0x1800d5aee  mov     [rsp+2B0h+var_268], r15
0x1800d5af3  mov     [rsp+2B0h+var_260], r15
0x1800d5af8  mov     [rsp+2B0h+var_258], r15
0x1800d5afd  mov     rbx, [rsi+38h]
0x1800d5b01  lea     rcx, [rsp+2B0h+var_268]
0x1800d5b06  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800d5b0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d5b0f  mov     [rsp+2B0h+var_260], rax
0x1800d5b14  mov     [rsp+2B0h+var_258], rax
0x1800d5b19  mov     r9, rbx
0x1800d5b1c  lea     r8, [rsp+2B0h+var_268]
0x1800d5b21  mov     edx, edi
0x1800d5b23  mov     rcx, r14
0x1800d5b26  call    ResourceStringCoAllocFormatMessage
0x1800d5b2b  test    eax, eax
0x1800d5b2d  js      short loc_1800D5B46
0x1800d5b2f  mov     rcx, [rsp+2B0h+var_280]
0x1800d5b34  mov     rax, [rcx]
0x1800d5b37  mov     rdx, [rsp+2B0h+var_268]
0x1800d5b3c  mov     rax, [rax+20h]
0x1800d5b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5b45  nop
0x1800d5b46  lea     rcx, [rsp+2B0h+var_268]
0x1800d5b4b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800d5b50  jmp     short loc_1800D5B86
0x1800d5b52  mov     r9d, 104h; cchBufferMax
0x1800d5b58  lea     r8, [rsp+2B0h+Buffer]; lpBuffer
0x1800d5b5d  mov     rcx, r14; hInstance
0x1800d5b60  call    cs:__imp_LoadStringW
0x1800d5b67  nop     dword ptr [rax+rax+00h]
0x1800d5b6c  test    eax, eax
0x1800d5b6e  jle     short loc_1800D5B86
0x1800d5b70  mov     rcx, [rsp+2B0h+var_280]
0x1800d5b75  mov     rax, [rcx]
0x1800d5b78  lea     rdx, [rsp+2B0h+Buffer]
0x1800d5b7d  mov     rax, [rax+20h]
0x1800d5b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5b86  mov     rcx, [rsp+2B0h+var_280]
0x1800d5b8b  mov     rax, [rcx]
0x1800d5b8e  mov     rdx, [rsp+2B0h+var_250]
0x1800d5b93  mov     rax, [rax+160h]
0x1800d5b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5b9f  mov     ebx, eax
0x1800d5ba1  test    eax, eax
0x1800d5ba3  js      loc_1800D5CD4
0x1800d5ba9  mov     rdx, [rsp+2B0h+var_280]; struct IPopupWindow *
0x1800d5bae  mov     rcx, rsi; this
0x1800d5bb1  cmp     dword ptr [rsi+18h], 9806h
0x1800d5bb8  jnz     short loc_1800D5C18
0x1800d5bba  mov     [rsp+2B0h+var_278], 95BAh
0x1800d5bc2  mov     [rsp+2B0h+var_278+4], 95B9h
0x1800d5bca  mov     r9d, 2; unsigned int
0x1800d5bd0  lea     r8, [rsp+2B0h+var_278]; unsigned int *
0x1800d5bd5  call    ?_SetCommands@CSetImageFeedDialog@@AEAAJPEAUIPopupWindow@@PEAII@Z; CSetImageFeedDialog::_SetCommands(IPopupWindow *,uint *,uint)
0x1800d5bda  mov     ebx, eax
0x1800d5bdc  test    eax, eax
0x1800d5bde  js      loc_1800D5CD4
0x1800d5be4  mov     rcx, [rsp+2B0h+var_280]
0x1800d5be9  mov     rax, [rcx]
0x1800d5bec  mov     edx, r12d
0x1800d5bef  mov     rax, [rax+58h]
0x1800d5bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5bf8  mov     ebx, eax
0x1800d5bfa  test    eax, eax
0x1800d5bfc  js      loc_1800D5CD4
0x1800d5c02  mov     rcx, [rsp+2B0h+var_280]
0x1800d5c07  mov     rax, [rcx]
0x1800d5c0a  mov     edx, r12d
0x1800d5c0d  mov     rax, [rax+78h]
0x1800d5c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5c16  jmp     short loc_1800D5C2D
0x1800d5c18  mov     [rsp+2B0h+var_278], 95C1h
0x1800d5c20  mov     r9d, r12d; unsigned int
0x1800d5c23  lea     r8, [rsp+2B0h+var_278]; unsigned int *
0x1800d5c28  call    ?_SetCommands@CSetImageFeedDialog@@AEAAJPEAUIPopupWindow@@PEAII@Z; CSetImageFeedDialog::_SetCommands(IPopupWindow *,uint *,uint)
0x1800d5c2d  mov     ebx, eax
0x1800d5c2f  test    eax, eax
0x1800d5c31  js      loc_1800D5CD4
0x1800d5c37  mov     rbx, [rsp+2B0h+var_280]
0x1800d5c3c  mov     rax, [rbx]
0x1800d5c3f  mov     r14, [rax+0A8h]
0x1800d5c46  mov     [rsp+2B0h+var_268], rsi
0x1800d5c4b  lea     rax, ?OnDismissCommand@CSetImageFeedDialog@@QEAAJPEAUIPopupWindow@@@Z; CSetImageFeedDialog::OnDismissCommand(IPopupWindow *)
0x1800d5c52  mov     [rsp+2B0h+var_260], rax
0x1800d5c57  mov     dword ptr [rsp+2B0h+var_258], r15d
0x1800d5c5c  mov     eax, dword ptr [rsp+2B0h+var_260+4]
0x1800d5c60  mov     dword ptr [rsp+2B0h+var_258+4], eax
0x1800d5c64  lea     rdx, [rsp+2B0h+var_268]
0x1800d5c69  lea     rcx, [rsp+2B0h+var_278]
0x1800d5c6e  call    ??$Make@U?$DelegateInvokeHelper@UIPopupEventHandler@@V_lambda_74447f3d681dc015fa527b5932f57c48_@@$0?0PEAUIPopupWindow@@@?$DelegateArgTraits@P8IPopupEventHandler@@EAAJPEAUIPopupWindow@@@Z@Details@WRL@Microsoft@@V_lambda_74447f3d681dc015fa527b5932f57c48_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@UIPopupEventHandler@@V_lambda_74447f3d681dc015fa527b5932f57c48_@@$0?0PEAUIPopupWindow@@@?$DelegateArgTraits@P8IPopupEventHandler@@EAAJPEAUIPopupWindow@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_74447f3d681dc015fa527b5932f57c48_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_74447f3d681dc015fa527b5932f57c48_,-1,IPopupWindow *>,_lambda_74447f3d681dc015fa527b5932f57c48_>(_lambda_74447f3d681dc015fa527b5932f57c48_ &&)
0x1800d5c73  mov     rdi, [rax]
0x1800d5c76  mov     [rsp+2B0h+var_268], rdi
0x1800d5c7b  mov     [rax], r15
0x1800d5c7e  mov     rcx, qword ptr [rsp+2B0h+var_278]
0x1800d5c83  test    rcx, rcx
0x1800d5c86  jz      short loc_1800D5C93
0x1800d5c88  mov     qword ptr [rsp+2B0h+var_278], r15
0x1800d5c8d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDialogFirstFrameRenderedHandler@Dialogs@UI@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release(void)
0x1800d5c92  nop
0x1800d5c93  mov     rdx, rdi
0x1800d5c96  mov     rcx, rbx
0x1800d5c99  mov     rax, r14
0x1800d5c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5ca1  mov     ebx, eax
0x1800d5ca3  lea     rcx, [rsp+2B0h+var_268]
0x1800d5ca8  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800d5cad  test    ebx, ebx
0x1800d5caf  js      short loc_1800D5CD4
0x1800d5cb1  lea     rdx, [rsp+2B0h+var_280]
0x1800d5cb6  lea     rcx, [rsi+10h]
0x1800d5cba  call    ??4?$ComPtr@UIPopupWindow@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IPopupWindow>::operator=(Microsoft::WRL::ComPtr<IPopupWindow> const &)
0x1800d5cbf  mov     rcx, [rsi+10h]
0x1800d5cc3  mov     rax, [rcx]
0x1800d5cc6  mov     rax, [rax+110h]
0x1800d5ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5cd2  mov     ebx, eax
0x1800d5cd4  lea     rcx, [rsp+2B0h+var_280]
0x1800d5cd9  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800d5cde  nop
0x1800d5cdf  lea     rcx, [rsp+2B0h+var_270]
0x1800d5ce4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d5ce9  test    ebx, ebx
0x1800d5ceb  jns     short loc_1800D5D00
0x1800d5ced  xor     edx, edx
0x1800d5cef  mov     rcx, [rsp+2B0h+var_250]
0x1800d5cf4  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800d5cfb  nop     dword ptr [rax+rax+00h]
0x1800d5d00  mov     rcx, [rsp+2B0h+var_248]
0x1800d5d05  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1800d5d0c  nop     dword ptr [rax+rax+00h]
0x1800d5d11  mov     eax, ebx
0x1800d5d13  mov     rcx, [rbp+1B0h+var_30]
0x1800d5d1a  xor     rcx, rsp; StackCookie
0x1800d5d1d  call    __security_check_cookie
0x1800d5d22  lea     r11, [rsp+2B0h+var_20]
0x1800d5d2a  mov     rbx, [r11+38h]
0x1800d5d2e  mov     rsi, [r11+40h]
0x1800d5d32  mov     rsp, r11
0x1800d5d35  pop     r15
0x1800d5d37  pop     r14
0x1800d5d39  pop     r12
0x1800d5d3b  pop     rdi
0x1800d5d3c  pop     rbp
0x1800d5d3d  retn
```
