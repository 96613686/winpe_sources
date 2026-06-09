# _ExecModernErrorDialogThreadProc(void *)

- ea: `0x1802e6500`
- end: `0x1802e68a9`
- name: `?_ExecModernErrorDialogThreadProc@@YAKPEAX@Z`
- size: `937`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000f05c`
- `0x1800b2640`
- `0x180233280`
- `0x1802e5510`
- `0x1802e55a0`
- `0x1802e6500`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1802e65f3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1802e66f8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1802e65f3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1802e66f8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802e6639`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802e6639`
- `DUI70!UnInitThread` at `0x1802e6869`
- `DUI70!UnInitThread` at `0x1802e6869`
- `DUI70!StartMessagePump` at `0x1802e683b`
- `DUI70!StartMessagePump` at `0x1802e683b`
- `DUI70!InitThread` at `0x1802e655d`
- `DUI70!InitThread` at `0x1802e655d`
- `DUI70!UnInitProcessPriv` at `0x1802e6876`
- `DUI70!UnInitProcessPriv` at `0x1802e6876`
- `DUI70!InitProcessPriv` at `0x1802e6548`
- `DUI70!InitProcessPriv` at `0x1802e6548`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetAccessible` at `0x1802e6596`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetAccessible` at `0x1802e6596`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_RichTextCreate` at `0x1802e657f`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_RichTextCreate` at `0x1802e657f`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetID` at `0x1802e65b8`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetID` at `0x1802e65b8`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementDestroy` at `0x1802e6858`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementDestroy` at `0x1802e6858`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetContentString` at `0x1802e6602`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetContentString` at `0x1802e6602`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetContentAlign` at `0x1802e65d8`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetContentAlign` at `0x1802e65d8`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_RichTextSetConstrainLayout` at `0x1802e65c8`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_RichTextSetConstrainLayout` at `0x1802e65c8`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetAccRole` at `0x1802e65a6`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetAccRole` at `0x1802e65a6`
- `Windows.Storage!IsDesktopBandWindow` at `0x1802e6657`
- `Windows.Storage!IsDesktopBandWindow` at `0x1802e6657`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _ExecModernErrorDialogThreadProc(_DWORD *Parameter, __int64 a2, __int64 a3)
{
  HRESULT inited; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // ebx
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, _QWORD, __int64 *); // rbx
  __int64 *v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rsi
  _QWORD v15[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v20[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v21[128]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[256]; // [rsp+170h] [rbp+70h] BYREF

  LOBYTE(a3) = 1;
  inited = InitProcessPriv(14, &_ImageBase, a3);
  if ( inited >= 0 )
  {
    inited = InitThread(65538);
    if ( inited >= 0 )
    {
      v16 = 0;
      inited = DUI70_RichTextCreate(0, 0, &v16);
      if ( inited >= 0 )
      {
        LOBYTE(v5) = 1;
        DUI70_ElementSetAccessible(v16, v5);
        DUI70_ElementSetAccRole(v16, 41);
        DUI70_ElementSetID(v16, L"ExecModernErrorDialogContentElement");
        DUI70_RichTextSetConstrainLayout(v16, 1);
        DUI70_ElementSetContentAlign(v16, 12);
        LoadStringW(g_hinst, Parameter[6], Buffer, 256);
        DUI70_ElementSetContentString(v16, Buffer);
        ppv = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        inited = CoCreateInstance(&CLSID_PopupWindowFactory, 0, 1u, &GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1, &ppv);
        if ( inited >= 0 )
        {
          if ( !*((_QWORD *)Parameter + 1) || (v8 = 1, (unsigned int)IsDesktopBandWindow()) )
            v8 = 9;
          (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, v8);
          v17 = 0;
          v9 = ppv;
          v10 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 72LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
          inited = v10(v9, *((_QWORD *)Parameter + 1), &v17);
          if ( inited >= 0 )
          {
            inited = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 352LL))(v17, v16);
            if ( inited < 0 )
              goto LABEL_24;
            v16 = 0;
            LoadStringW(g_hinst, Parameter[5], v21, 128);
            (*(void (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)v17 + 32LL))(v17, v21);
            v20[0] = Parameter;
            v11 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_IPopupCommandHandler::___IPopupWindow___IPopupCommand____::DelegateInvokeHelper_IPopupCommandHandler__lambda_40a14c19f5373c4d7a131b9477baa70f___1_IPopupWindow___IPopupCommand_____lambda_40a14c19f5373c4d7a131b9477baa70f___(
                               v15,
                               v20);
            v12 = *v11;
            v15[1] = *v11;
            *v11 = 0;
            if ( v15[0] )
            {
              v15[0] = 0;
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release();
            }
            if ( v12 )
            {
              v20[0] = v12;
              LODWORD(v15[0]) = 9740;
              Microsoft::WRL::Details::Make<CModernErrorDialogCommand,int,IPopupCommandHandler *>(&v19, v15, v20);
              v13 = v19;
              if ( v19 )
              {
                v20[0] = v19;
                inited = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v17 + 64LL))(v17, 1, v20);
                if ( inited >= 0 )
                {
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 88LL))(v17, 0);
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 120LL))(v17, 0);
                }
              }
              else
              {
                inited = -2147024882;
              }
              if ( v13 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            }
            else
            {
              inited = -2147024882;
            }
            if ( v12 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            if ( inited < 0 || (inited = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 272LL))(v17), inited < 0) )
LABEL_24:
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 296LL))(v17);
            StartMessagePump();
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
        }
        if ( v16 )
        {
          LOBYTE(v7) = 1;
          DUI70_ElementDestroy(v16, v7);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      }
      UnInitThread(v6);
    }
    UnInitProcessPriv(&_ImageBase);
  }
  Parameter[7] = inited;
  return 0;
}

```

## disassembly

```asm
0x1802e6500  mov     [rsp-8+arg_8], rbx
0x1802e6505  mov     [rsp-8+arg_10], rsi
0x1802e650a  push    rbp
0x1802e650b  push    rdi
0x1802e650c  push    r14
0x1802e650e  lea     rbp, [rsp-280h]
0x1802e6516  sub     rsp, 380h
0x1802e651d  mov     rax, cs:__security_cookie
0x1802e6524  xor     rax, rsp
0x1802e6527  mov     [rbp+290h+var_20], rax
0x1802e652e  mov     r14, rcx
0x1802e6531  mov     byte ptr [rsp+390h+ppv], 1
0x1802e6536  mov     r9b, 1
0x1802e6539  mov     r8b, r9b
0x1802e653c  lea     rdx, __ImageBase
0x1802e6543  mov     ecx, 0Eh
0x1802e6548  call    cs:__imp_InitProcessPriv
0x1802e654e  mov     ebx, eax
0x1802e6550  test    eax, eax
0x1802e6552  js      loc_1802E687C
0x1802e6558  mov     ecx, 10002h
0x1802e655d  call    cs:__imp_InitThread
0x1802e6563  mov     ebx, eax
0x1802e6565  test    eax, eax
0x1802e6567  js      loc_1802E686F
0x1802e656d  mov     [rsp+390h+var_350], 0
0x1802e6576  lea     r8, [rsp+390h+var_350]
0x1802e657b  xor     edx, edx
0x1802e657d  xor     ecx, ecx
0x1802e657f  call    cs:__imp_DUI70_RichTextCreate
0x1802e6585  mov     ebx, eax
0x1802e6587  test    eax, eax
0x1802e6589  js      loc_1802E6869
0x1802e658f  mov     dl, 1
0x1802e6591  mov     rcx, [rsp+390h+var_350]
0x1802e6596  call    cs:__imp_DUI70_ElementSetAccessible
0x1802e659c  mov     edx, 29h ; ')'
0x1802e65a1  mov     rcx, [rsp+390h+var_350]
0x1802e65a6  call    cs:__imp_DUI70_ElementSetAccRole
0x1802e65ac  lea     rdx, aExecmodernerro; "ExecModernErrorDialogContentElement"
0x1802e65b3  mov     rcx, [rsp+390h+var_350]
0x1802e65b8  call    cs:__imp_DUI70_ElementSetID
0x1802e65be  mov     edx, 1
0x1802e65c3  mov     rcx, [rsp+390h+var_350]
0x1802e65c8  call    cs:__imp_DUI70_RichTextSetConstrainLayout
0x1802e65ce  mov     edx, 0Ch
0x1802e65d3  mov     rcx, [rsp+390h+var_350]
0x1802e65d8  call    cs:__imp_DUI70_ElementSetContentAlign
0x1802e65de  mov     r9d, 100h; cchBufferMax
0x1802e65e4  lea     r8, [rbp+290h+Buffer]; lpBuffer
0x1802e65e8  mov     edx, [r14+18h]; uID
0x1802e65ec  mov     rcx, cs:g_hinst; hInstance
0x1802e65f3  call    cs:__imp_LoadStringW
0x1802e65f9  lea     rdx, [rbp+290h+Buffer]
0x1802e65fd  mov     rcx, [rsp+390h+var_350]
0x1802e6602  call    cs:__imp_DUI70_ElementSetContentString
0x1802e6608  mov     [rsp+390h+var_340], 0
0x1802e6611  lea     rcx, [rsp+390h+var_340]
0x1802e6616  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802e661b  lea     rax, [rsp+390h+var_340]
0x1802e6620  mov     [rsp+390h+ppv], rax; ppv
0x1802e6625  lea     r9, _GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1; riid
0x1802e662c  xor     edx, edx; pUnkOuter
0x1802e662e  lea     r8d, [rdx+1]; dwClsContext
0x1802e6632  lea     rcx, CLSID_PopupWindowFactory; rclsid
0x1802e6639  call    cs:__imp_CoCreateInstance
0x1802e663f  mov     ebx, eax
0x1802e6641  test    eax, eax
0x1802e6643  js      loc_1802E684C
0x1802e6649  mov     rcx, [r14+8]
0x1802e664d  test    rcx, rcx
0x1802e6650  jz      short loc_1802E6661
0x1802e6652  mov     ebx, 1
0x1802e6657  call    cs:__imp_IsDesktopBandWindow
0x1802e665d  test    eax, eax
0x1802e665f  jz      short loc_1802E6666
0x1802e6661  mov     ebx, 9
0x1802e6666  mov     rcx, [rsp+390h+var_340]
0x1802e666b  mov     rax, [rcx]
0x1802e666e  mov     edx, ebx
0x1802e6670  mov     rax, [rax+18h]
0x1802e6674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e6679  mov     [rsp+390h+var_348], 0
0x1802e6682  mov     rdi, [rsp+390h+var_340]
0x1802e6687  mov     rax, [rdi]
0x1802e668a  mov     rbx, [rax+48h]
0x1802e668e  lea     rcx, [rsp+390h+var_348]
0x1802e6693  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802e6698  lea     r8, [rsp+390h+var_348]
0x1802e669d  mov     rdx, [r14+8]
0x1802e66a1  mov     rcx, rdi
0x1802e66a4  mov     rax, rbx
0x1802e66a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e66ac  mov     ebx, eax
0x1802e66ae  test    eax, eax
0x1802e66b0  js      loc_1802E6842
0x1802e66b6  mov     rcx, [rsp+390h+var_348]
0x1802e66bb  mov     rax, [rcx]
0x1802e66be  mov     rdx, [rsp+390h+var_350]
0x1802e66c3  mov     rax, [rax+160h]
0x1802e66ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e66cf  mov     ebx, eax
0x1802e66d1  test    eax, eax
0x1802e66d3  js      loc_1802E6827
0x1802e66d9  mov     [rsp+390h+var_350], 0
0x1802e66e2  mov     r9d, 80h; cchBufferMax
0x1802e66e8  lea     r8, [rsp+390h+var_320]; lpBuffer
0x1802e66ed  mov     edx, [r14+14h]; uID
0x1802e66f1  mov     rcx, cs:g_hinst; hInstance
0x1802e66f8  call    cs:__imp_LoadStringW
0x1802e66fe  mov     rcx, [rsp+390h+var_348]
0x1802e6703  mov     rax, [rcx]
0x1802e6706  lea     rdx, [rsp+390h+var_320]
0x1802e670b  mov     rax, [rax+20h]
0x1802e670f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e6714  mov     [rsp+390h+var_330], r14
0x1802e6719  lea     rdx, [rsp+390h+var_330]
0x1802e671e  lea     rcx, [rsp+390h+var_360]
0x1802e6723  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_IPopupCommandHandler_____IPopupWindow___IPopupCommand______DelegateInvokeHelper_IPopupCommandHandler__lambda_40a14c19f5373c4d7a131b9477baa70f___1_IPopupWindow___IPopupCommand_____lambda_40a14c19f5373c4d7a131b9477baa70f___
0x1802e6728  mov     rdi, [rax]
0x1802e672b  mov     [rsp+390h+var_358], rdi
0x1802e6730  mov     qword ptr [rax], 0
0x1802e6737  mov     rcx, [rsp+390h+var_360]
0x1802e673c  test    rcx, rcx
0x1802e673f  jz      short loc_1802E6750
0x1802e6741  mov     [rsp+390h+var_360], 0
0x1802e674a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)
0x1802e674f  nop
0x1802e6750  test    rdi, rdi
0x1802e6753  jnz     short loc_1802E675F
0x1802e6755  mov     ebx, 8007000Eh
0x1802e675a  jmp     loc_1802E67F4
0x1802e675f  mov     [rsp+390h+var_330], rdi
0x1802e6764  mov     dword ptr [rsp+390h+var_360], 260Ch
0x1802e676c  lea     r8, [rsp+390h+var_330]
0x1802e6771  lea     rdx, [rsp+390h+var_360]
0x1802e6776  lea     rcx, [rsp+390h+var_338]
0x1802e677b  call    ??$Make@VCModernErrorDialogCommand@@HPEAUIPopupCommandHandler@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCModernErrorDialogCommand@@@12@$$QEAH$$QEAPEAUIPopupCommandHandler@@@Z; Microsoft::WRL::Details::Make<CModernErrorDialogCommand,int,IPopupCommandHandler *>(int &&,IPopupCommandHandler * &&)
0x1802e6780  nop
0x1802e6781  mov     rsi, [rsp+390h+var_338]
0x1802e6786  test    rsi, rsi
0x1802e6789  jnz     short loc_1802E6792
0x1802e678b  mov     ebx, 8007000Eh
0x1802e6790  jmp     short loc_1802E67DF
0x1802e6792  mov     [rsp+390h+var_330], rsi
0x1802e6797  mov     rcx, [rsp+390h+var_348]
0x1802e679c  mov     rax, [rcx]
0x1802e679f  lea     r8, [rsp+390h+var_330]
0x1802e67a4  mov     edx, 1
0x1802e67a9  mov     rax, [rax+40h]
0x1802e67ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e67b2  mov     ebx, eax
0x1802e67b4  test    eax, eax
0x1802e67b6  js      short loc_1802E67DF
0x1802e67b8  mov     rcx, [rsp+390h+var_348]
0x1802e67bd  mov     rax, [rcx]
0x1802e67c0  xor     edx, edx
0x1802e67c2  mov     rax, [rax+58h]
0x1802e67c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e67cb  mov     rcx, [rsp+390h+var_348]
0x1802e67d0  mov     rax, [rcx]
0x1802e67d3  xor     edx, edx
0x1802e67d5  mov     rax, [rax+78h]
0x1802e67d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e67de  nop
0x1802e67df  test    rsi, rsi
0x1802e67e2  jz      short loc_1802E67F4
0x1802e67e4  mov     rax, [rsi]
0x1802e67e7  mov     rcx, rsi
0x1802e67ea  mov     rax, [rax+10h]
0x1802e67ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e67f3  nop
0x1802e67f4  test    rdi, rdi
0x1802e67f7  jz      short loc_1802E6809
0x1802e67f9  mov     rax, [rdi]
0x1802e67fc  mov     rcx, rdi
0x1802e67ff  mov     rax, [rax+10h]
0x1802e6803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e6808  nop
0x1802e6809  test    ebx, ebx
0x1802e680b  js      short loc_1802E6827
0x1802e680d  mov     rcx, [rsp+390h+var_348]
0x1802e6812  mov     rax, [rcx]
0x1802e6815  mov     rax, [rax+110h]
0x1802e681c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e6821  mov     ebx, eax
0x1802e6823  test    eax, eax
0x1802e6825  jns     short loc_1802E683B
0x1802e6827  mov     rcx, [rsp+390h+var_348]
0x1802e682c  mov     rax, [rcx]
0x1802e682f  mov     rax, [rax+128h]
0x1802e6836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e683b  call    cs:__imp_StartMessagePump
0x1802e6841  nop
0x1802e6842  lea     rcx, [rsp+390h+var_348]
0x1802e6847  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802e684c  mov     rcx, [rsp+390h+var_350]
0x1802e6851  test    rcx, rcx
0x1802e6854  jz      short loc_1802E685F
0x1802e6856  mov     dl, 1
0x1802e6858  call    cs:__imp_DUI70_ElementDestroy
0x1802e685e  nop
0x1802e685f  lea     rcx, [rsp+390h+var_340]
0x1802e6864  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802e6869  call    cs:__imp_UnInitThread
0x1802e686f  lea     rcx, __ImageBase
0x1802e6876  call    cs:__imp_UnInitProcessPriv
0x1802e687c  mov     [r14+1Ch], ebx
0x1802e6880  xor     eax, eax
0x1802e6882  mov     rcx, [rbp+290h+var_20]
0x1802e6889  xor     rcx, rsp; StackCookie
0x1802e688c  call    __security_check_cookie
0x1802e6891  lea     r11, [rsp+390h+var_10]
0x1802e6899  mov     rbx, [r11+28h]
0x1802e689d  mov     rsi, [r11+30h]
0x1802e68a1  mov     rsp, r11
0x1802e68a4  pop     r14
0x1802e68a6  pop     rdi
0x1802e68a7  pop     rbp
0x1802e68a8  retn
```
