# _ExecModernErrorDialogThreadProc(void *)

- ea: `0x180305050`
- end: `0x180305460`
- name: `?_ExecModernErrorDialogThreadProc@@YAKPEAX@Z`
- size: `1040`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000f6cc`
- `0x1800250e0`
- `0x180249490`
- `0x180304004`
- `0x180304094`
- `0x180305050`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180305173`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180305290`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180305173`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180305290`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1803051c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1803051c5`
- `DUI70!UnInitThread` at `0x180305413`
- `DUI70!UnInitThread` at `0x180305413`
- `DUI70!StartMessagePump` at `0x1803053d9`
- `DUI70!StartMessagePump` at `0x1803053d9`
- `DUI70!InitThread` at `0x1803050b3`
- `DUI70!InitThread` at `0x1803050b3`
- `DUI70!UnInitProcessPriv` at `0x180305426`
- `DUI70!UnInitProcessPriv` at `0x180305426`
- `DUI70!InitProcessPriv` at `0x180305098`
- `DUI70!InitProcessPriv` at `0x180305098`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetAccRole` at `0x18030510e`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetAccRole` at `0x18030510e`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_RichTextCreate` at `0x1803050db`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_RichTextCreate` at `0x1803050db`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementDestroy` at `0x1803053fc`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementDestroy` at `0x1803053fc`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetContentString` at `0x180305188`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetContentString` at `0x180305188`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetContentAlign` at `0x180305152`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetContentAlign` at `0x180305152`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_RichTextSetConstrainLayout` at `0x18030513c`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_RichTextSetConstrainLayout` at `0x18030513c`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetID` at `0x180305126`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetID` at `0x180305126`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetAccessible` at `0x1803050f8`
- `ext-ms-win-gui-dui70-l1-1-0!DUI70_ElementSetAccessible` at `0x1803050f8`
- `Windows.Storage!IsDesktopBandWindow` at `0x1803051e9`
- `Windows.Storage!IsDesktopBandWindow` at `0x1803051e9`

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
0x180305050  mov     [rsp-8+arg_8], rbx
0x180305055  mov     [rsp-8+arg_10], rsi
0x18030505a  push    rbp
0x18030505b  push    rdi
0x18030505c  push    r14
0x18030505e  lea     rbp, [rsp-280h]
0x180305066  sub     rsp, 380h
0x18030506d  mov     rax, cs:__security_cookie
0x180305074  xor     rax, rsp
0x180305077  mov     [rbp+290h+var_20], rax
0x18030507e  mov     r14, rcx
0x180305081  mov     byte ptr [rsp+390h+ppv], 1
0x180305086  mov     r9b, 1
0x180305089  mov     r8b, r9b
0x18030508c  lea     rdx, __ImageBase
0x180305093  mov     ecx, 0Eh
0x180305098  call    cs:__imp_InitProcessPriv
0x18030509f  nop     dword ptr [rax+rax+00h]
0x1803050a4  mov     ebx, eax
0x1803050a6  test    eax, eax
0x1803050a8  js      loc_180305432
0x1803050ae  mov     ecx, 10002h
0x1803050b3  call    cs:__imp_InitThread
0x1803050ba  nop     dword ptr [rax+rax+00h]
0x1803050bf  mov     ebx, eax
0x1803050c1  test    eax, eax
0x1803050c3  js      loc_18030541F
0x1803050c9  mov     [rsp+390h+var_350], 0
0x1803050d2  lea     r8, [rsp+390h+var_350]
0x1803050d7  xor     edx, edx
0x1803050d9  xor     ecx, ecx
0x1803050db  call    cs:__imp_DUI70_RichTextCreate
0x1803050e2  nop     dword ptr [rax+rax+00h]
0x1803050e7  mov     ebx, eax
0x1803050e9  test    eax, eax
0x1803050eb  js      loc_180305413
0x1803050f1  mov     dl, 1
0x1803050f3  mov     rcx, [rsp+390h+var_350]
0x1803050f8  call    cs:__imp_DUI70_ElementSetAccessible
0x1803050ff  nop     dword ptr [rax+rax+00h]
0x180305104  mov     edx, 29h ; ')'
0x180305109  mov     rcx, [rsp+390h+var_350]
0x18030510e  call    cs:__imp_DUI70_ElementSetAccRole
0x180305115  nop     dword ptr [rax+rax+00h]
0x18030511a  lea     rdx, aExecmodernerro; "ExecModernErrorDialogContentElement"
0x180305121  mov     rcx, [rsp+390h+var_350]
0x180305126  call    cs:__imp_DUI70_ElementSetID
0x18030512d  nop     dword ptr [rax+rax+00h]
0x180305132  mov     edx, 1
0x180305137  mov     rcx, [rsp+390h+var_350]
0x18030513c  call    cs:__imp_DUI70_RichTextSetConstrainLayout
0x180305143  nop     dword ptr [rax+rax+00h]
0x180305148  mov     edx, 0Ch
0x18030514d  mov     rcx, [rsp+390h+var_350]
0x180305152  call    cs:__imp_DUI70_ElementSetContentAlign
0x180305159  nop     dword ptr [rax+rax+00h]
0x18030515e  mov     r9d, 100h; cchBufferMax
0x180305164  lea     r8, [rbp+290h+Buffer]; lpBuffer
0x180305168  mov     edx, [r14+18h]; uID
0x18030516c  mov     rcx, cs:g_hinst; hInstance
0x180305173  call    cs:__imp_LoadStringW
0x18030517a  nop     dword ptr [rax+rax+00h]
0x18030517f  lea     rdx, [rbp+290h+Buffer]
0x180305183  mov     rcx, [rsp+390h+var_350]
0x180305188  call    cs:__imp_DUI70_ElementSetContentString
0x18030518f  nop     dword ptr [rax+rax+00h]
0x180305194  mov     [rsp+390h+var_340], 0
0x18030519d  lea     rcx, [rsp+390h+var_340]
0x1803051a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803051a7  lea     rax, [rsp+390h+var_340]
0x1803051ac  mov     [rsp+390h+ppv], rax; ppv
0x1803051b1  lea     r9, _GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1; riid
0x1803051b8  xor     edx, edx; pUnkOuter
0x1803051ba  lea     r8d, [rdx+1]; dwClsContext
0x1803051be  lea     rcx, CLSID_PopupWindowFactory; rclsid
0x1803051c5  call    cs:__imp_CoCreateInstance
0x1803051cc  nop     dword ptr [rax+rax+00h]
0x1803051d1  mov     ebx, eax
0x1803051d3  test    eax, eax
0x1803051d5  js      loc_1803053F0
0x1803051db  mov     rcx, [r14+8]
0x1803051df  test    rcx, rcx
0x1803051e2  jz      short loc_1803051F9
0x1803051e4  mov     ebx, 1
0x1803051e9  call    cs:__imp_IsDesktopBandWindow
0x1803051f0  nop     dword ptr [rax+rax+00h]
0x1803051f5  test    eax, eax
0x1803051f7  jz      short loc_1803051FE
0x1803051f9  mov     ebx, 9
0x1803051fe  mov     rcx, [rsp+390h+var_340]
0x180305203  mov     rax, [rcx]
0x180305206  mov     edx, ebx
0x180305208  mov     rax, [rax+18h]
0x18030520c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305211  mov     [rsp+390h+var_348], 0
0x18030521a  mov     rdi, [rsp+390h+var_340]
0x18030521f  mov     rax, [rdi]
0x180305222  mov     rbx, [rax+48h]
0x180305226  lea     rcx, [rsp+390h+var_348]
0x18030522b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180305230  lea     r8, [rsp+390h+var_348]
0x180305235  mov     rdx, [r14+8]
0x180305239  mov     rcx, rdi
0x18030523c  mov     rax, rbx
0x18030523f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305244  mov     ebx, eax
0x180305246  test    eax, eax
0x180305248  js      loc_1803053E6
0x18030524e  mov     rcx, [rsp+390h+var_348]
0x180305253  mov     rax, [rcx]
0x180305256  mov     rdx, [rsp+390h+var_350]
0x18030525b  mov     rax, [rax+160h]
0x180305262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305267  mov     ebx, eax
0x180305269  test    eax, eax
0x18030526b  js      loc_1803053C5
0x180305271  mov     [rsp+390h+var_350], 0
0x18030527a  mov     r9d, 80h; cchBufferMax
0x180305280  lea     r8, [rsp+390h+var_320]; lpBuffer
0x180305285  mov     edx, [r14+14h]; uID
0x180305289  mov     rcx, cs:g_hinst; hInstance
0x180305290  call    cs:__imp_LoadStringW
0x180305297  nop     dword ptr [rax+rax+00h]
0x18030529c  mov     rcx, [rsp+390h+var_348]
0x1803052a1  mov     rax, [rcx]
0x1803052a4  lea     rdx, [rsp+390h+var_320]
0x1803052a9  mov     rax, [rax+20h]
0x1803052ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803052b2  mov     [rsp+390h+var_330], r14
0x1803052b7  lea     rdx, [rsp+390h+var_330]
0x1803052bc  lea     rcx, [rsp+390h+var_360]
0x1803052c1  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_IPopupCommandHandler_____IPopupWindow___IPopupCommand______DelegateInvokeHelper_IPopupCommandHandler__lambda_40a14c19f5373c4d7a131b9477baa70f___1_IPopupWindow___IPopupCommand_____lambda_40a14c19f5373c4d7a131b9477baa70f___
0x1803052c6  mov     rdi, [rax]
0x1803052c9  mov     [rsp+390h+var_358], rdi
0x1803052ce  mov     qword ptr [rax], 0
0x1803052d5  mov     rcx, [rsp+390h+var_360]
0x1803052da  test    rcx, rcx
0x1803052dd  jz      short loc_1803052EE
0x1803052df  mov     [rsp+390h+var_360], 0
0x1803052e8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)
0x1803052ed  nop
0x1803052ee  test    rdi, rdi
0x1803052f1  jnz     short loc_1803052FD
0x1803052f3  mov     ebx, 8007000Eh
0x1803052f8  jmp     loc_180305392
0x1803052fd  mov     [rsp+390h+var_330], rdi
0x180305302  mov     dword ptr [rsp+390h+var_360], 260Ch
0x18030530a  lea     r8, [rsp+390h+var_330]
0x18030530f  lea     rdx, [rsp+390h+var_360]
0x180305314  lea     rcx, [rsp+390h+var_338]
0x180305319  call    ??$Make@VCModernErrorDialogCommand@@HPEAUIPopupCommandHandler@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCModernErrorDialogCommand@@@12@$$QEAH$$QEAPEAUIPopupCommandHandler@@@Z; Microsoft::WRL::Details::Make<CModernErrorDialogCommand,int,IPopupCommandHandler *>(int &&,IPopupCommandHandler * &&)
0x18030531e  nop
0x18030531f  mov     rsi, [rsp+390h+var_338]
0x180305324  test    rsi, rsi
0x180305327  jnz     short loc_180305330
0x180305329  mov     ebx, 8007000Eh
0x18030532e  jmp     short loc_18030537D
0x180305330  mov     [rsp+390h+var_330], rsi
0x180305335  mov     rcx, [rsp+390h+var_348]
0x18030533a  mov     rax, [rcx]
0x18030533d  lea     r8, [rsp+390h+var_330]
0x180305342  mov     edx, 1
0x180305347  mov     rax, [rax+40h]
0x18030534b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305350  mov     ebx, eax
0x180305352  test    eax, eax
0x180305354  js      short loc_18030537D
0x180305356  mov     rcx, [rsp+390h+var_348]
0x18030535b  mov     rax, [rcx]
0x18030535e  xor     edx, edx
0x180305360  mov     rax, [rax+58h]
0x180305364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305369  mov     rcx, [rsp+390h+var_348]
0x18030536e  mov     rax, [rcx]
0x180305371  xor     edx, edx
0x180305373  mov     rax, [rax+78h]
0x180305377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030537c  nop
0x18030537d  test    rsi, rsi
0x180305380  jz      short loc_180305392
0x180305382  mov     rax, [rsi]
0x180305385  mov     rcx, rsi
0x180305388  mov     rax, [rax+10h]
0x18030538c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305391  nop
0x180305392  test    rdi, rdi
0x180305395  jz      short loc_1803053A7
0x180305397  mov     rax, [rdi]
0x18030539a  mov     rcx, rdi
0x18030539d  mov     rax, [rax+10h]
0x1803053a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803053a6  nop
0x1803053a7  test    ebx, ebx
0x1803053a9  js      short loc_1803053C5
0x1803053ab  mov     rcx, [rsp+390h+var_348]
0x1803053b0  mov     rax, [rcx]
0x1803053b3  mov     rax, [rax+110h]
0x1803053ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803053bf  mov     ebx, eax
0x1803053c1  test    eax, eax
0x1803053c3  jns     short loc_1803053D9
0x1803053c5  mov     rcx, [rsp+390h+var_348]
0x1803053ca  mov     rax, [rcx]
0x1803053cd  mov     rax, [rax+128h]
0x1803053d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803053d9  call    cs:__imp_StartMessagePump
0x1803053e0  nop     dword ptr [rax+rax+00h]
0x1803053e5  nop
0x1803053e6  lea     rcx, [rsp+390h+var_348]
0x1803053eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803053f0  mov     rcx, [rsp+390h+var_350]
0x1803053f5  test    rcx, rcx
0x1803053f8  jz      short loc_180305409
0x1803053fa  mov     dl, 1
0x1803053fc  call    cs:__imp_DUI70_ElementDestroy
0x180305403  nop     dword ptr [rax+rax+00h]
0x180305408  nop
0x180305409  lea     rcx, [rsp+390h+var_340]
0x18030540e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180305413  call    cs:__imp_UnInitThread
0x18030541a  nop     dword ptr [rax+rax+00h]
0x18030541f  lea     rcx, __ImageBase
0x180305426  call    cs:__imp_UnInitProcessPriv
0x18030542d  nop     dword ptr [rax+rax+00h]
0x180305432  mov     [r14+1Ch], ebx
0x180305436  xor     eax, eax
0x180305438  mov     rcx, [rbp+290h+var_20]
0x18030543f  xor     rcx, rsp; StackCookie
0x180305442  call    __security_check_cookie
0x180305447  lea     r11, [rsp+390h+var_10]
0x18030544f  mov     rbx, [r11+28h]
0x180305453  mov     rsi, [r11+30h]
0x180305457  mov     rsp, r11
0x18030545a  pop     r14
0x18030545c  pop     rdi
0x18030545d  pop     rbp
0x18030545e  retn
```
