# _ExecSimpleDialogThreadProc(void *)

- ea: `0x1805755e0`
- end: `0x1805759a8`
- name: `?_ExecSimpleDialogThreadProc@@YAKPEAX@Z`
- size: `968`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000f6cc`
- `0x18002843c`
- `0x1800463c8`
- `0x180558730`
- `0x180574fd0`
- `0x18057519c`
- `0x1805752d8`
- `0x1805755e0`
- `0x1805b2010`

## import_xrefs

- `USER32!DestroyWindow` at `0x18057593d`
- `USER32!DestroyWindow` at `0x18057593d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180575721`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180575721`
- `DUI70!?SetContentAlign@Element@DirectUI@@QEAAJH@Z` at `0x1805756d3`
- `DUI70!?SetContentAlign@Element@DirectUI@@QEAAJH@Z` at `0x1805756d3`
- `DUI70!?Create@RichText@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z` at `0x180575654`
- `DUI70!?Create@RichText@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z` at `0x180575654`
- `DUI70!?SetConstrainLayout@RichText@DirectUI@@QEAAJH@Z` at `0x1805756af`
- `DUI70!?SetConstrainLayout@RichText@DirectUI@@QEAAJH@Z` at `0x1805756af`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1805756e7`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1805756e7`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18057569a`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18057569a`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x18057566e`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x18057566e`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x180575683`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x180575683`
- `DUI70!UnInitThread` at `0x180575972`
- `DUI70!UnInitThread` at `0x180575972`
- `DUI70!StartMessagePump` at `0x180575929`
- `DUI70!StartMessagePump` at `0x180575929`
- `DUI70!InitThread` at `0x180575630`
- `DUI70!InitThread` at `0x180575630`
- `DUI70!UnInitProcessPriv` at `0x180575985`
- `DUI70!UnInitProcessPriv` at `0x180575985`
- `DUI70!InitProcessPriv` at `0x180575617`
- `DUI70!InitProcessPriv` at `0x180575617`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18057595d`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18057595d`

## pseudocode

```c
__int64 __fastcall _ExecSimpleDialogThreadProc(_QWORD *Parameter, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  DirectUI::Element *v4; // rbx
  __int64 v5; // rdx
  int v6; // eax
  HWND DummyWindow; // r14
  bool v8; // r13
  LPVOID v9; // rdi
  int (__fastcall *v10)(LPVOID, HWND, __int64 *); // rbx
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 v14; // r15
  __int64 v15; // r12
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // r8
  __int64 v19; // r9
  _QWORD *v20; // rcx
  int v21; // eax
  _QWORD *v22; // rax
  __int64 v23; // rcx
  __int64 v25; // [rsp+30h] [rbp-39h] BYREF
  struct DirectUI::Element *v26; // [rsp+38h] [rbp-31h] BYREF
  _QWORD *v27; // [rsp+40h] [rbp-29h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-21h] BYREF
  _QWORD *v29; // [rsp+50h] [rbp-19h] BYREF
  _QWORD *v30; // [rsp+58h] [rbp-11h]
  __int64 v31; // [rsp+60h] [rbp-9h] BYREF
  __int64 v32; // [rsp+68h] [rbp-1h]
  __int64 v33; // [rsp+70h] [rbp+7h]
  __int64 v34; // [rsp+78h] [rbp+Fh]

  v3 = *Parameter;
  v30 = Parameter;
  LOBYTE(a3) = 1;
  if ( (int)InitProcessPriv(14, &_ImageBase, a3) < 0 )
    return 0;
  if ( (int)InitThread(65538) < 0 )
    goto LABEL_34;
  v26 = 0;
  if ( (int)DirectUI::RichText::Create(0, 0, &v26) < 0 )
    goto LABEL_33;
  DirectUI::Element::SetAccessible(v26, 1);
  DirectUI::Element::SetAccRole(v26, 41);
  DirectUI::Element::SetID(v26, L"ExecSimpleDialogContentElement");
  DirectUI::RichText::SetConstrainLayout(v26, 1);
  v4 = v26;
  v6 = DUI_TransformContentAlign(v26, v5, 12);
  DirectUI::Element::SetContentAlign(v4, v6);
  DirectUI::Element::SetContentString(v26, *(const unsigned __int16 **)(v3 + 24));
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  if ( CoCreateInstance(&CLSID_PopupWindowFactory, 0, 1u, &GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1, &ppv) < 0 )
    goto LABEL_30;
  DummyWindow = *(HWND *)v3;
  if ( *(_QWORD *)v3 )
  {
    v8 = 0;
  }
  else
  {
    DummyWindow = CreateDummyWindow();
    v8 = DummyWindow != 0;
  }
  (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 9);
  v9 = ppv;
  v25 = 0;
  v10 = *(int (__fastcall **)(LPVOID, HWND, __int64 *))(*(_QWORD *)ppv + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  if ( v10(v9, DummyWindow, &v25) < 0 )
    goto LABEL_29;
  v11 = (*(__int64 (__fastcall **)(__int64, struct DirectUI::Element *))(*(_QWORD *)v25 + 352LL))(v25, v26);
  if ( v11 < 0 )
    goto LABEL_26;
  v12 = *(_QWORD *)(v3 + 16);
  v26 = 0;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 32LL))(v25, v12);
  v13 = 0;
  v14 = 0;
  v31 = 0;
  v15 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  while ( (unsigned int)v15 < *(_DWORD *)(v3 + 40) )
  {
    v29 = v30;
    v16 = *(_QWORD *)(v3 + 32);
    v27 = 0;
    v17 = v16 + 4 * v15;
    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v27);
    v11 = Microsoft::WRL::Details::MakeAndInitialize_CLambdaCommandHandler_IPopupCommand_unsigned_int_const___unsigned_int_const____lambda_ec1faf3780b50c0982032afb3f78ef2c___(
            &v27,
            v17,
            v17,
            &v29);
    if ( v11 >= 0 )
    {
      v20 = v27;
      v11 = 0;
      v29 = v27;
      if ( v13 == v34 )
      {
        v21 = CTSimpleArray<_ITEMIDLIST_ABSOLUTE *,4294967294,CTPolicyCoTaskMem<_ITEMIDLIST_ABSOLUTE *>,CSimpleArrayStandardCompareHelper<_ITEMIDLIST_ABSOLUTE *>,CSimpleArrayStandardMergeHelper<_ITEMIDLIST_ABSOLUTE *>>::_EnsureCapacity(
                &v31,
                v13 + 1,
                v18,
                v19);
        v13 = v32;
        v11 = v21;
        v14 = v31;
        if ( v21 >= 0 )
        {
          v20 = v29;
          goto LABEL_16;
        }
      }
      else
      {
LABEL_16:
        v32 = ++v13;
        v22 = (_QWORD *)(v14 + 8 * (v13 - 1));
        if ( v22 )
          *v22 = v20;
      }
      if ( v11 >= 0 )
        v27 = 0;
    }
    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v27);
    v15 = (unsigned int)(v15 + 1);
    if ( v11 < 0 )
      goto LABEL_24;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v25 + 64LL))(
          v25,
          *(unsigned int *)(v3 + 40),
          v14);
  if ( v11 >= 0 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 88LL))(
      v25,
      (unsigned int)(*(_DWORD *)(v3 + 40) - *(_DWORD *)(v3 + 44) - 1));
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 120LL))(
      v25,
      (unsigned int)(*(_DWORD *)(v3 + 40) - *(_DWORD *)(v3 + 48) - 1));
  }
LABEL_24:
  CSimplePointerArray<IPopupCommand,CTContainer_PolicyRelease<IPopupCommand>,CSimpleArrayStandardCompareHelper<IPopupCommand *>>::~CSimplePointerArray<IPopupCommand,CTContainer_PolicyRelease<IPopupCommand>,CSimpleArrayStandardCompareHelper<IPopupCommand *>>(&v31);
  if ( v11 < 0 || (v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 272LL))(v25), v11 < 0) )
  {
LABEL_26:
    v23 = v25;
    *((_DWORD *)v30 + 2) = v11;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 296LL))(v23);
  }
  StartMessagePump();
  if ( v8 )
    DestroyWindow(DummyWindow);
LABEL_29:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
LABEL_30:
  if ( v26 )
    DirectUI::Element::Destroy(v26, 1);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
LABEL_33:
  UnInitThread();
LABEL_34:
  UnInitProcessPriv(&_ImageBase);
  return 0;
}

```

## disassembly

```asm
0x1805755e0  push    rbp
0x1805755e2  push    rbx
0x1805755e3  push    rsi
0x1805755e4  push    rdi
0x1805755e5  push    r12
0x1805755e7  push    r13
0x1805755e9  push    r14
0x1805755eb  push    r15
0x1805755ed  lea     rbp, [rsp-1Fh]
0x1805755f2  sub     rsp, 88h
0x1805755f9  mov     rsi, [rcx]
0x1805755fc  lea     rdx, __ImageBase
0x180575603  mov     r9b, 1
0x180575606  mov     [rbp+57h+var_68], rcx
0x18057560a  mov     r8b, r9b
0x18057560d  mov     byte ptr [rsp+0C0h+ppv], 1
0x180575612  mov     ecx, 0Eh
0x180575617  call    cs:__imp_InitProcessPriv
0x18057561e  nop     dword ptr [rax+rax+00h]
0x180575623  test    eax, eax
0x180575625  js      loc_180575991
0x18057562b  mov     ecx, 10002h
0x180575630  call    cs:__imp_InitThread
0x180575637  nop     dword ptr [rax+rax+00h]
0x18057563c  test    eax, eax
0x18057563e  js      loc_18057597E
0x180575644  lea     r8, [rbp+57h+var_88]
0x180575648  mov     [rbp+57h+var_88], 0
0x180575650  xor     edx, edx
0x180575652  xor     ecx, ecx
0x180575654  call    cs:__imp_?Create@RichText@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z; DirectUI::RichText::Create(DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18057565b  nop     dword ptr [rax+rax+00h]
0x180575660  test    eax, eax
0x180575662  js      loc_180575972
0x180575668  mov     rcx, [rbp+57h+var_88]
0x18057566c  mov     dl, 1
0x18057566e  call    cs:__imp_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetAccessible(bool)
0x180575675  nop     dword ptr [rax+rax+00h]
0x18057567a  mov     rcx, [rbp+57h+var_88]
0x18057567e  mov     edx, 29h ; ')'
0x180575683  call    cs:__imp_?SetAccRole@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAccRole(int)
0x18057568a  nop     dword ptr [rax+rax+00h]
0x18057568f  mov     rcx, [rbp+57h+var_88]
0x180575693  lea     rdx, aExecsimpledial; "ExecSimpleDialogContentElement"
0x18057569a  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x1805756a1  nop     dword ptr [rax+rax+00h]
0x1805756a6  mov     rcx, [rbp+57h+var_88]
0x1805756aa  mov     edx, 1
0x1805756af  call    cs:__imp_?SetConstrainLayout@RichText@DirectUI@@QEAAJH@Z; DirectUI::RichText::SetConstrainLayout(int)
0x1805756b6  nop     dword ptr [rax+rax+00h]
0x1805756bb  mov     rbx, [rbp+57h+var_88]
0x1805756bf  xor     r9d, r9d
0x1805756c2  mov     rcx, rbx
0x1805756c5  lea     r8d, [r9+0Ch]
0x1805756c9  call    ?DUI_TransformContentAlign@@YAHPEAVElement@DirectUI@@W4DUI_COORDINATES_SYSTEM@@H1@Z; DUI_TransformContentAlign(DirectUI::Element *,DUI_COORDINATES_SYSTEM,int,DUI_COORDINATES_SYSTEM)
0x1805756ce  mov     edx, eax
0x1805756d0  mov     rcx, rbx
0x1805756d3  call    cs:__imp_?SetContentAlign@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetContentAlign(int)
0x1805756da  nop     dword ptr [rax+rax+00h]
0x1805756df  mov     rdx, [rsi+18h]
0x1805756e3  mov     rcx, [rbp+57h+var_88]
0x1805756e7  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1805756ee  nop     dword ptr [rax+rax+00h]
0x1805756f3  lea     rcx, [rbp+57h+var_78]
0x1805756f7  mov     [rbp+57h+var_78], 0
0x1805756ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180575704  xor     edx, edx; pUnkOuter
0x180575706  lea     rax, [rbp+57h+var_78]
0x18057570a  lea     r9, _GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1; riid
0x180575711  mov     [rsp+0C0h+ppv], rax; ppv
0x180575716  lea     rcx, CLSID_PopupWindowFactory; rclsid
0x18057571d  lea     r8d, [rdx+1]; dwClsContext
0x180575721  call    cs:__imp_CoCreateInstance
0x180575728  nop     dword ptr [rax+rax+00h]
0x18057572d  test    eax, eax
0x18057572f  js      loc_180575952
0x180575735  mov     r14, [rsi]
0x180575738  test    r14, r14
0x18057573b  jnz     short loc_18057574E
0x18057573d  call    ?CreateDummyWindow@@YAPEAUHWND__@@XZ; CreateDummyWindow(void)
0x180575742  test    rax, rax
0x180575745  mov     r14, rax
0x180575748  setnz   r13b
0x18057574c  jmp     short loc_180575751
0x18057574e  xor     r13b, r13b
0x180575751  mov     rcx, [rbp+57h+var_78]
0x180575755  mov     edx, 9
0x18057575a  mov     rax, [rcx]
0x18057575d  mov     rax, [rax+18h]
0x180575761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180575766  mov     rdi, [rbp+57h+var_78]
0x18057576a  lea     rcx, [rbp+57h+var_90]
0x18057576e  mov     [rbp+57h+var_90], 0
0x180575776  mov     rax, [rdi]
0x180575779  mov     rbx, [rax+48h]
0x18057577d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180575782  lea     r8, [rbp+57h+var_90]
0x180575786  mov     rdx, r14
0x180575789  mov     rcx, rdi
0x18057578c  mov     rax, rbx
0x18057578f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180575794  test    eax, eax
0x180575796  js      loc_180575949
0x18057579c  mov     rcx, [rbp+57h+var_90]
0x1805757a0  mov     rdx, [rbp+57h+var_88]
0x1805757a4  mov     rax, [rcx]
0x1805757a7  mov     rax, [rax+160h]
0x1805757ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805757b3  mov     ebx, eax
0x1805757b5  test    eax, eax
0x1805757b7  js      loc_18057590F
0x1805757bd  mov     rcx, [rbp+57h+var_90]
0x1805757c1  mov     rdx, [rsi+10h]
0x1805757c5  mov     [rbp+57h+var_88], 0
0x1805757cd  mov     rax, [rcx]
0x1805757d0  mov     rax, [rax+20h]
0x1805757d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805757d9  xor     edi, edi
0x1805757db  xor     r15d, r15d
0x1805757de  mov     [rbp+57h+var_60], r15
0x1805757e2  xor     r12d, r12d
0x1805757e5  mov     [rbp+57h+var_58], rdi
0x1805757e9  mov     [rbp+57h+var_50], rdi
0x1805757ed  mov     [rbp+57h+var_48], rdi
0x1805757f1  cmp     r12d, [rsi+28h]
0x1805757f5  jnb     loc_18057589D
0x1805757fb  mov     rax, [rbp+57h+var_68]
0x1805757ff  lea     rcx, [rbp+57h+var_80]
0x180575803  mov     [rbp+57h+var_70], rax
0x180575807  mov     rax, [rsi+20h]
0x18057580b  mov     [rbp+57h+var_80], 0
0x180575813  lea     rbx, [rax+r12*4]
0x180575817  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18057581c  lea     r9, [rbp+57h+var_70]
0x180575820  mov     r8, rbx
0x180575823  mov     rdx, rbx
0x180575826  lea     rcx, [rbp+57h+var_80]
0x18057582a  call    Microsoft__WRL__Details__MakeAndInitialize_CLambdaCommandHandler_IPopupCommand_unsigned_int_const___unsigned_int_const____lambda_ec1faf3780b50c0982032afb3f78ef2c___
0x18057582f  mov     ebx, eax
0x180575831  test    eax, eax
0x180575833  js      short loc_180575887
0x180575835  mov     rcx, [rbp+57h+var_80]
0x180575839  xor     ebx, ebx
0x18057583b  mov     [rbp+57h+var_70], rcx
0x18057583f  cmp     rdi, [rbp+57h+var_48]
0x180575843  jnz     short loc_180575864
0x180575845  lea     rdx, [rdi+1]
0x180575849  lea     rcx, [rbp+57h+var_60]
0x18057584d  call    ?_EnsureCapacity@?$CTSimpleArray@PEAU_ITEMIDLIST_ABSOLUTE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAU_ITEMIDLIST_ABSOLUTE@@@@V?$CSimpleArrayStandardCompareHelper@PEAU_ITEMIDLIST_ABSOLUTE@@@@V?$CSimpleArrayStandardMergeHelper@PEAU_ITEMIDLIST_ABSOLUTE@@@@@@QEAAJ_K0@Z; CTSimpleArray<_ITEMIDLIST_ABSOLUTE *,4294967294,CTPolicyCoTaskMem<_ITEMIDLIST_ABSOLUTE *>,CSimpleArrayStandardCompareHelper<_ITEMIDLIST_ABSOLUTE *>,CSimpleArrayStandardMergeHelper<_ITEMIDLIST_ABSOLUTE *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180575852  mov     rdi, [rbp+57h+var_58]
0x180575856  mov     ebx, eax
0x180575858  mov     r15, [rbp+57h+var_60]
0x18057585c  test    eax, eax
0x18057585e  js      short loc_18057587B
0x180575860  mov     rcx, [rbp+57h+var_70]
0x180575864  inc     rdi
0x180575867  mov     [rbp+57h+var_58], rdi
0x18057586b  lea     rax, [rdi-1]
0x18057586f  lea     rax, [r15+rax*8]
0x180575873  test    rax, rax
0x180575876  jz      short loc_18057587B
0x180575878  mov     [rax], rcx
0x18057587b  test    ebx, ebx
0x18057587d  js      short loc_180575887
0x18057587f  mov     [rbp+57h+var_80], 0
0x180575887  lea     rcx, [rbp+57h+var_80]
0x18057588b  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x180575890  inc     r12d
0x180575893  test    ebx, ebx
0x180575895  jns     loc_1805757F1
0x18057589b  jmp     short loc_1805758E9
0x18057589d  mov     rcx, [rbp+57h+var_90]
0x1805758a1  mov     r8, r15
0x1805758a4  mov     edx, [rsi+28h]
0x1805758a7  mov     rax, [rcx]
0x1805758aa  mov     rax, [rax+40h]
0x1805758ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805758b3  mov     ebx, eax
0x1805758b5  test    eax, eax
0x1805758b7  js      short loc_1805758E9
0x1805758b9  mov     rcx, [rbp+57h+var_90]
0x1805758bd  mov     edx, [rsi+28h]
0x1805758c0  sub     edx, [rsi+2Ch]
0x1805758c3  dec     edx
0x1805758c5  mov     rax, [rcx]
0x1805758c8  mov     rax, [rax+58h]
0x1805758cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805758d1  mov     rcx, [rbp+57h+var_90]
0x1805758d5  mov     edx, [rsi+28h]
0x1805758d8  sub     edx, [rsi+30h]
0x1805758db  dec     edx
0x1805758dd  mov     rax, [rcx]
0x1805758e0  mov     rax, [rax+78h]
0x1805758e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805758e9  lea     rcx, [rbp+57h+var_60]
0x1805758ed  call    ??1?$CSimplePointerArray@UIPopupCommand@@V?$CTContainer_PolicyRelease@UIPopupCommand@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIPopupCommand@@@@@@QEAA@XZ; CSimplePointerArray<IPopupCommand,CTContainer_PolicyRelease<IPopupCommand>,CSimpleArrayStandardCompareHelper<IPopupCommand *>>::~CSimplePointerArray<IPopupCommand,CTContainer_PolicyRelease<IPopupCommand>,CSimpleArrayStandardCompareHelper<IPopupCommand *>>(void)
0x1805758f2  test    ebx, ebx
0x1805758f4  js      short loc_18057590F
0x1805758f6  mov     rcx, [rbp+57h+var_90]
0x1805758fa  mov     rax, [rcx]
0x1805758fd  mov     rax, [rax+110h]
0x180575904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180575909  mov     ebx, eax
0x18057590b  test    eax, eax
0x18057590d  jns     short loc_180575929
0x18057590f  mov     rax, [rbp+57h+var_68]
0x180575913  mov     rcx, [rbp+57h+var_90]
0x180575917  mov     [rax+8], ebx
0x18057591a  mov     rax, [rcx]
0x18057591d  mov     rax, [rax+128h]
0x180575924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180575929  call    cs:__imp_StartMessagePump
0x180575930  nop     dword ptr [rax+rax+00h]
0x180575935  test    r13b, r13b
0x180575938  jz      short loc_180575949
0x18057593a  mov     rcx, r14; hWnd
0x18057593d  call    cs:__imp_DestroyWindow
0x180575944  nop     dword ptr [rax+rax+00h]
0x180575949  lea     rcx, [rbp+57h+var_90]
0x18057594d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180575952  mov     rcx, [rbp+57h+var_88]
0x180575956  test    rcx, rcx
0x180575959  jz      short loc_180575969
0x18057595b  mov     dl, 1
0x18057595d  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180575964  nop     dword ptr [rax+rax+00h]
0x180575969  lea     rcx, [rbp+57h+var_78]
0x18057596d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180575972  call    cs:__imp_UnInitThread
0x180575979  nop     dword ptr [rax+rax+00h]
0x18057597e  lea     rcx, __ImageBase
0x180575985  call    cs:__imp_UnInitProcessPriv
0x18057598c  nop     dword ptr [rax+rax+00h]
0x180575991  xor     eax, eax
0x180575993  add     rsp, 88h
0x18057599a  pop     r15
0x18057599c  pop     r14
0x18057599e  pop     r13
0x1805759a0  pop     r12
0x1805759a2  pop     rdi
0x1805759a3  pop     rsi
0x1805759a4  pop     rbx
0x1805759a5  pop     rbp
0x1805759a6  retn
```
