# CUserInfoDialog::_CreateAndShow(void)

- ea: `0x1800d3ea0`
- end: `0x1800d4210`
- name: `?_CreateAndShow@CUserInfoDialog@@AEAAJXZ`
- size: `880`
- prototype: `__int64 __fastcall(CUserInfoDialog *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d3d00`
- `0x1800d3da0`

## callees

- `0x180013f14`
- `0x1800343ec`
- `0x18003f720`
- `0x180054130`
- `0x180085690`
- `0x180088914`
- `0x1800d3ea0`
- `0x1800d436c`
- `0x1800d4464`
- `0x1800ddf58`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d407b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d407b`
- `USER32!GetWindowBand` at `0x1800d3ffa`
- `USER32!GetWindowBand` at `0x1800d3ffa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d3fcb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d3fcb`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800d3f00`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800d3f00`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800d41dd`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800d41dd`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800d3f2b`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800d3f2b`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800d3f6c`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800d3f6c`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d41cd`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d41cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CUserInfoDialog::_CreateAndShow(CUserInfoDialog *this)
{
  HRESULT v2; // ebx
  __int64 v3; // rcx
  BOOL v4; // ebx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, _QWORD, struct IPopupWindow **); // rbx
  unsigned int v7; // r9d
  struct IPopupWindow *v8; // rbx
  __int64 (__fastcall *v9)(struct IPopupWindow *, __int64); // r14
  __int64 *v10; // rax
  __int64 v11; // rdi
  unsigned int v13[2]; // [rsp+30h] [rbp-89h] BYREF
  struct IPopupWindow *v14; // [rsp+38h] [rbp-81h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-79h] BYREF
  struct DirectUI::Element *v16; // [rsp+48h] [rbp-71h] BYREF
  struct DirectUI::DUIXmlParser *v17; // [rsp+50h] [rbp-69h] BYREF
  _QWORD v18[2]; // [rsp+58h] [rbp-61h] BYREF
  int v19; // [rsp+68h] [rbp-51h]
  int v20; // [rsp+6Ch] [rbp-4Dh]
  WCHAR Buffer[64]; // [rsp+70h] [rbp-49h] BYREF

  if ( *((_DWORD *)this + 6) != 38913
    || (v2 = DirectUI::ClassInfo<UserTile,DirectUI::Element,DirectUI::StandardCreator<UserTile>>::Register(), v2 >= 0) )
  {
    v17 = 0;
    v2 = DirectUI::DUIXmlParser::Create(&v17, 0, 0, 0, 0);
    if ( v2 >= 0 )
    {
      v2 = DirectUI::DUIXmlParser::SetXMLFromResource(v17, *((_DWORD *)this + 6), &_ImageBase, &_ImageBase);
      if ( v2 >= 0 )
      {
        v16 = 0;
        v2 = DirectUI::DUIXmlParser::CreateElement(v17, L"main", 0, 0, 0, &v16);
        if ( v2 >= 0 )
        {
          v2 = CUserInfoDialog::_SetDialogDUI(this, v16);
          if ( v2 < 0 )
            goto LABEL_25;
          ppv = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
          v2 = CoCreateInstance(&CLSID_PopupWindowFactory, 0, 1u, &GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1, &ppv);
          if ( v2 >= 0 )
          {
            v3 = *((_QWORD *)this + 7);
            v13[0] = 0;
            v4 = 1;
            if ( v3 && (unsigned int)GetWindowBand(v3, v13) )
              v4 = v13[0] == 1;
            (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, (unsigned int)(8 * v4 + 1));
            v14 = 0;
            v5 = ppv;
            v6 = *(__int64 (__fastcall **)(LPVOID, _QWORD, struct IPopupWindow **))(*(_QWORD *)ppv + 72LL);
            Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v14);
            v2 = v6(v5, *((_QWORD *)this + 7), &v14);
            if ( v2 >= 0 )
            {
              if ( LoadStringW(&_ImageBase, *((_DWORD *)this + 7), Buffer, 64) > 0 )
                (*(void (__fastcall **)(struct IPopupWindow *, WCHAR *))(*(_QWORD *)v14 + 32LL))(v14, Buffer);
              v2 = (*(__int64 (__fastcall **)(struct IPopupWindow *, struct DirectUI::Element *))(*(_QWORD *)v14 + 352LL))(
                     v14,
                     v16);
              if ( v2 >= 0 )
              {
                if ( *((_DWORD *)this + 6) == 38913 )
                {
                  v13[0] = 38322;
                  v13[1] = 38321;
                  v7 = 2;
                }
                else
                {
                  v13[0] = 38337;
                  v7 = 1;
                }
                v2 = CUserInfoDialog::_SetCommands(this, v14, v13, v7);
                if ( v2 >= 0 )
                {
                  v8 = v14;
                  v9 = *(__int64 (__fastcall **)(struct IPopupWindow *, __int64))(*(_QWORD *)v14 + 168LL);
                  v18[0] = this;
                  v18[1] = CUserInfoDialog::CancelDialog;
                  v19 = 0;
                  v20 = (unsigned __int64)CUserInfoDialog::CancelDialog >> 32;
                  v10 = (__int64 *)Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_74447f3d681dc015fa527b5932f57c48_,-1,IPopupWindow *>,_lambda_74447f3d681dc015fa527b5932f57c48_>(
                                     v13,
                                     v18);
                  v11 = *v10;
                  v18[0] = *v10;
                  *v10 = 0;
                  if ( *(_QWORD *)v13 )
                  {
                    *(_QWORD *)v13 = 0;
                    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release();
                  }
                  v2 = v9(v8, v11);
                  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v18);
                  if ( v2 >= 0 )
                  {
                    Microsoft::WRL::ComPtr<IPopupWindow>::operator=((char *)this + 16, &v14);
                    v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 272LL))(*((_QWORD *)this + 2));
                  }
                }
              }
            }
            Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v14);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
          if ( v2 < 0 )
LABEL_25:
            DirectUI::Element::Destroy(v16, 0);
        }
      }
      DirectUI::DUIXmlParser::Destroy(v17);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800d3ea0  mov     [rsp-8+arg_8], rbx
0x1800d3ea5  mov     [rsp-8+arg_10], rsi
0x1800d3eaa  push    rbp
0x1800d3eab  push    rdi
0x1800d3eac  push    r14
0x1800d3eae  lea     rbp, [rsp-47h]
0x1800d3eb3  sub     rsp, 100h
0x1800d3eba  mov     rax, cs:__security_cookie
0x1800d3ec1  xor     rax, rsp
0x1800d3ec4  mov     [rbp+57h+var_20], rax
0x1800d3ec8  mov     rsi, rcx
0x1800d3ecb  cmp     dword ptr [rcx+18h], 9801h
0x1800d3ed2  jnz     short loc_1800D3EE3
0x1800d3ed4  call    ?Register@?$ClassInfo@VUserTile@@VElement@DirectUI@@V?$StandardCreator@VUserTile@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<UserTile,DirectUI::Element,DirectUI::StandardCreator<UserTile>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x1800d3ed9  mov     ebx, eax
0x1800d3edb  test    eax, eax
0x1800d3edd  js      loc_1800D41E9
0x1800d3ee3  mov     [rbp+57h+var_C0], 0
0x1800d3eeb  mov     [rsp+110h+ppv], 0
0x1800d3ef4  xor     r9d, r9d
0x1800d3ef7  xor     r8d, r8d
0x1800d3efa  xor     edx, edx
0x1800d3efc  lea     rcx, [rbp+57h+var_C0]
0x1800d3f00  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x1800d3f07  nop     dword ptr [rax+rax+00h]
0x1800d3f0c  mov     ebx, eax
0x1800d3f0e  test    eax, eax
0x1800d3f10  js      loc_1800D41E9
0x1800d3f16  lea     r9, __ImageBase
0x1800d3f1d  lea     r8, __ImageBase
0x1800d3f24  mov     edx, [rsi+18h]
0x1800d3f27  mov     rcx, [rbp+57h+var_C0]
0x1800d3f2b  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x1800d3f32  nop     dword ptr [rax+rax+00h]
0x1800d3f37  mov     ebx, eax
0x1800d3f39  test    eax, eax
0x1800d3f3b  js      loc_1800D41D9
0x1800d3f41  mov     [rbp+57h+var_C8], 0
0x1800d3f49  lea     rax, [rbp+57h+var_C8]
0x1800d3f4d  mov     [rsp+110h+var_E8], rax
0x1800d3f52  mov     [rsp+110h+ppv], 0
0x1800d3f5b  xor     r9d, r9d
0x1800d3f5e  xor     r8d, r8d
0x1800d3f61  lea     rdx, aMain; "main"
0x1800d3f68  mov     rcx, [rbp+57h+var_C0]
0x1800d3f6c  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1800d3f73  nop     dword ptr [rax+rax+00h]
0x1800d3f78  mov     ebx, eax
0x1800d3f7a  test    eax, eax
0x1800d3f7c  js      loc_1800D41D9
0x1800d3f82  mov     rdx, [rbp+57h+var_C8]; struct DirectUI::Element *
0x1800d3f86  mov     rcx, rsi; this
0x1800d3f89  call    ?_SetDialogDUI@CUserInfoDialog@@AEAAJPEAVElement@DirectUI@@@Z; CUserInfoDialog::_SetDialogDUI(DirectUI::Element *)
0x1800d3f8e  mov     ebx, eax
0x1800d3f90  test    eax, eax
0x1800d3f92  js      loc_1800D41C7
0x1800d3f98  mov     [rbp+57h+var_D0], 0
0x1800d3fa0  lea     rcx, [rbp+57h+var_D0]
0x1800d3fa4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d3fa9  lea     rax, [rbp+57h+var_D0]
0x1800d3fad  mov     [rsp+110h+ppv], rax; ppv
0x1800d3fb2  lea     r9, _GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1; riid
0x1800d3fb9  mov     r14d, 1
0x1800d3fbf  mov     r8d, r14d; dwClsContext
0x1800d3fc2  xor     edx, edx; pUnkOuter
0x1800d3fc4  lea     rcx, CLSID_PopupWindowFactory; rclsid
0x1800d3fcb  call    cs:__imp_CoCreateInstance
0x1800d3fd2  nop     dword ptr [rax+rax+00h]
0x1800d3fd7  mov     ebx, eax
0x1800d3fd9  test    eax, eax
0x1800d3fdb  js      loc_1800D41BA
0x1800d3fe1  mov     rcx, [rsi+38h]
0x1800d3fe5  mov     [rsp+110h+var_E0], 0
0x1800d3fed  mov     ebx, r14d
0x1800d3ff0  test    rcx, rcx
0x1800d3ff3  jz      short loc_1800D4014
0x1800d3ff5  lea     rdx, [rsp+110h+var_E0]
0x1800d3ffa  call    cs:__imp_GetWindowBand
0x1800d4001  nop     dword ptr [rax+rax+00h]
0x1800d4006  test    eax, eax
0x1800d4008  jz      short loc_1800D4014
0x1800d400a  xor     ebx, ebx
0x1800d400c  cmp     [rsp+110h+var_E0], r14d
0x1800d4011  setz    bl
0x1800d4014  mov     rcx, [rbp+57h+var_D0]
0x1800d4018  mov     rax, [rcx]
0x1800d401b  lea     edx, ds:1[rbx*8]
0x1800d4022  mov     rax, [rax+18h]
0x1800d4026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d402b  mov     [rsp+110h+var_D8], 0
0x1800d4034  mov     rdi, [rbp+57h+var_D0]
0x1800d4038  mov     rax, [rdi]
0x1800d403b  mov     rbx, [rax+48h]
0x1800d403f  lea     rcx, [rsp+110h+var_D8]
0x1800d4044  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800d4049  lea     r8, [rsp+110h+var_D8]
0x1800d404e  mov     rdx, [rsi+38h]
0x1800d4052  mov     rcx, rdi
0x1800d4055  mov     rax, rbx
0x1800d4058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d405d  mov     ebx, eax
0x1800d405f  test    eax, eax
0x1800d4061  js      loc_1800D41AF
0x1800d4067  mov     r9d, 40h ; '@'; cchBufferMax
0x1800d406d  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800d4071  mov     edx, [rsi+1Ch]; uID
0x1800d4074  lea     rcx, __ImageBase; hInstance
0x1800d407b  call    cs:__imp_LoadStringW
0x1800d4082  nop     dword ptr [rax+rax+00h]
0x1800d4087  test    eax, eax
0x1800d4089  jle     short loc_1800D40A0
0x1800d408b  mov     rcx, [rsp+110h+var_D8]
0x1800d4090  mov     rax, [rcx]
0x1800d4093  lea     rdx, [rbp+57h+Buffer]
0x1800d4097  mov     rax, [rax+20h]
0x1800d409b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d40a0  mov     rcx, [rsp+110h+var_D8]
0x1800d40a5  mov     rax, [rcx]
0x1800d40a8  mov     rdx, [rbp+57h+var_C8]
0x1800d40ac  mov     rax, [rax+160h]
0x1800d40b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d40b8  mov     ebx, eax
0x1800d40ba  test    eax, eax
0x1800d40bc  js      loc_1800D41AF
0x1800d40c2  mov     rdx, [rsp+110h+var_D8]; struct IPopupWindow *
0x1800d40c7  mov     rcx, rsi; this
0x1800d40ca  cmp     dword ptr [rsi+18h], 9801h
0x1800d40d1  jnz     short loc_1800D40F0
0x1800d40d3  mov     [rsp+110h+var_E0], 95B2h
0x1800d40db  mov     [rsp+110h+var_E0+4], 95B1h
0x1800d40e3  mov     r9d, 2
0x1800d40e9  lea     r8, [rsp+110h+var_E0]
0x1800d40ee  jmp     short loc_1800D4100
0x1800d40f0  mov     [rsp+110h+var_E0], 95C1h
0x1800d40f8  mov     r9d, r14d; unsigned int
0x1800d40fb  lea     r8, [rsp+110h+var_E0]; unsigned int *
0x1800d4100  call    ?_SetCommands@CUserInfoDialog@@AEAAJPEAUIPopupWindow@@PEAII@Z; CUserInfoDialog::_SetCommands(IPopupWindow *,uint *,uint)
0x1800d4105  mov     ebx, eax
0x1800d4107  test    eax, eax
0x1800d4109  js      loc_1800D41AF
0x1800d410f  mov     rbx, [rsp+110h+var_D8]
0x1800d4114  mov     rax, [rbx]
0x1800d4117  mov     r14, [rax+0A8h]
0x1800d411e  mov     [rbp+57h+var_B8], rsi
0x1800d4122  lea     rax, ?CancelDialog@CUserInfoDialog@@UEAAJXZ; CUserInfoDialog::CancelDialog(void)
0x1800d4129  mov     [rbp+57h+var_B0], rax
0x1800d412d  mov     [rbp+57h+var_A8], 0
0x1800d4134  mov     eax, dword ptr [rbp+57h+var_B0+4]
0x1800d4137  mov     [rbp+57h+var_A4], eax
0x1800d413a  lea     rdx, [rbp+57h+var_B8]
0x1800d413e  lea     rcx, [rsp+110h+var_E0]
0x1800d4143  call    ??$Make@U?$DelegateInvokeHelper@UIPopupEventHandler@@V_lambda_74447f3d681dc015fa527b5932f57c48_@@$0?0PEAUIPopupWindow@@@?$DelegateArgTraits@P8IPopupEventHandler@@EAAJPEAUIPopupWindow@@@Z@Details@WRL@Microsoft@@V_lambda_74447f3d681dc015fa527b5932f57c48_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@UIPopupEventHandler@@V_lambda_74447f3d681dc015fa527b5932f57c48_@@$0?0PEAUIPopupWindow@@@?$DelegateArgTraits@P8IPopupEventHandler@@EAAJPEAUIPopupWindow@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_74447f3d681dc015fa527b5932f57c48_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_74447f3d681dc015fa527b5932f57c48_,-1,IPopupWindow *>,_lambda_74447f3d681dc015fa527b5932f57c48_>(_lambda_74447f3d681dc015fa527b5932f57c48_ &&)
0x1800d4148  mov     rdi, [rax]
0x1800d414b  mov     [rbp+57h+var_B8], rdi
0x1800d414f  mov     qword ptr [rax], 0
0x1800d4156  mov     rcx, qword ptr [rsp+110h+var_E0]
0x1800d415b  test    rcx, rcx
0x1800d415e  jz      short loc_1800D416F
0x1800d4160  mov     qword ptr [rsp+110h+var_E0], 0
0x1800d4169  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDialogFirstFrameRenderedHandler@Dialogs@UI@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release(void)
0x1800d416e  nop
0x1800d416f  mov     rdx, rdi
0x1800d4172  mov     rcx, rbx
0x1800d4175  mov     rax, r14
0x1800d4178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d417d  mov     ebx, eax
0x1800d417f  lea     rcx, [rbp+57h+var_B8]
0x1800d4183  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800d4188  test    ebx, ebx
0x1800d418a  js      short loc_1800D41AF
0x1800d418c  lea     rdx, [rsp+110h+var_D8]
0x1800d4191  lea     rcx, [rsi+10h]
0x1800d4195  call    ??4?$ComPtr@UIPopupWindow@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IPopupWindow>::operator=(Microsoft::WRL::ComPtr<IPopupWindow> const &)
0x1800d419a  mov     rcx, [rsi+10h]
0x1800d419e  mov     rax, [rcx]
0x1800d41a1  mov     rax, [rax+110h]
0x1800d41a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d41ad  mov     ebx, eax
0x1800d41af  lea     rcx, [rsp+110h+var_D8]
0x1800d41b4  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800d41b9  nop
0x1800d41ba  lea     rcx, [rbp+57h+var_D0]
0x1800d41be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d41c3  test    ebx, ebx
0x1800d41c5  jns     short loc_1800D41D9
0x1800d41c7  xor     edx, edx
0x1800d41c9  mov     rcx, [rbp+57h+var_C8]
0x1800d41cd  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800d41d4  nop     dword ptr [rax+rax+00h]
0x1800d41d9  mov     rcx, [rbp+57h+var_C0]
0x1800d41dd  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1800d41e4  nop     dword ptr [rax+rax+00h]
0x1800d41e9  mov     eax, ebx
0x1800d41eb  mov     rcx, [rbp+57h+var_20]
0x1800d41ef  xor     rcx, rsp; StackCookie
0x1800d41f2  call    __security_check_cookie
0x1800d41f7  lea     r11, [rsp+110h+var_10]
0x1800d41ff  mov     rbx, [r11+28h]
0x1800d4203  mov     rsi, [r11+30h]
0x1800d4207  mov     rsp, r11
0x1800d420a  pop     r14
0x1800d420c  pop     rdi
0x1800d420d  pop     rbp
0x1800d420e  retn
```
