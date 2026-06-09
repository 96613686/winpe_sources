# _ExecSimpleDialogThreadProc(void *)

- ea: `0x180536d00`
- end: `0x18053706d`
- name: `?_ExecSimpleDialogThreadProc@@YAKPEAX@Z`
- size: `877`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000f05c`
- `0x18004a500`
- `0x1800657d4`
- `0x18051ad8c`
- `0x18053672c`
- `0x1805368f0`
- `0x180536a28`
- `0x180536d00`
- `0x180571010`

## import_xrefs

- `USER32!DestroyWindow` at `0x18053701b`
- `USER32!DestroyWindow` at `0x18053701b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180536e0b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180536e0b`
- `DUI70!?SetContentAlign@Element@DirectUI@@QEAAJH@Z` at `0x180536dc9`
- `DUI70!?SetContentAlign@Element@DirectUI@@QEAAJH@Z` at `0x180536dc9`
- `DUI70!?Create@RichText@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z` at `0x180536d68`
- `DUI70!?Create@RichText@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z` at `0x180536d68`
- `DUI70!?SetConstrainLayout@RichText@DirectUI@@QEAAJH@Z` at `0x180536dab`
- `DUI70!?SetConstrainLayout@RichText@DirectUI@@QEAAJH@Z` at `0x180536dab`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180536dd7`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180536dd7`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x180536d9c`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x180536d9c`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x180536d7c`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x180536d7c`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x180536d8b`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x180536d8b`
- `DUI70!UnInitThread` at `0x180537044`
- `DUI70!UnInitThread` at `0x180537044`
- `DUI70!StartMessagePump` at `0x18053700d`
- `DUI70!StartMessagePump` at `0x18053700d`
- `DUI70!InitThread` at `0x180536d4a`
- `DUI70!InitThread` at `0x180536d4a`
- `DUI70!UnInitProcessPriv` at `0x180537051`
- `DUI70!UnInitProcessPriv` at `0x180537051`
- `DUI70!InitProcessPriv` at `0x180536d37`
- `DUI70!InitProcessPriv` at `0x180536d37`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180537035`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180537035`

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
0x180536d00  push    rbp
0x180536d02  push    rbx
0x180536d03  push    rsi
0x180536d04  push    rdi
0x180536d05  push    r12
0x180536d07  push    r13
0x180536d09  push    r14
0x180536d0b  push    r15
0x180536d0d  lea     rbp, [rsp-1Fh]
0x180536d12  sub     rsp, 88h
0x180536d19  mov     rsi, [rcx]
0x180536d1c  lea     rdx, __ImageBase
0x180536d23  mov     r9b, 1
0x180536d26  mov     [rbp+57h+var_68], rcx
0x180536d2a  mov     r8b, r9b
0x180536d2d  mov     byte ptr [rsp+0C0h+ppv], 1
0x180536d32  mov     ecx, 0Eh
0x180536d37  call    cs:__imp_InitProcessPriv
0x180536d3d  test    eax, eax
0x180536d3f  js      loc_180537057
0x180536d45  mov     ecx, 10002h
0x180536d4a  call    cs:__imp_InitThread
0x180536d50  test    eax, eax
0x180536d52  js      loc_18053704A
0x180536d58  lea     r8, [rbp+57h+var_88]
0x180536d5c  mov     [rbp+57h+var_88], 0
0x180536d64  xor     edx, edx
0x180536d66  xor     ecx, ecx
0x180536d68  call    cs:__imp_?Create@RichText@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z; DirectUI::RichText::Create(DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180536d6e  test    eax, eax
0x180536d70  js      loc_180537044
0x180536d76  mov     rcx, [rbp+57h+var_88]
0x180536d7a  mov     dl, 1
0x180536d7c  call    cs:__imp_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetAccessible(bool)
0x180536d82  mov     rcx, [rbp+57h+var_88]
0x180536d86  mov     edx, 29h ; ')'
0x180536d8b  call    cs:__imp_?SetAccRole@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAccRole(int)
0x180536d91  mov     rcx, [rbp+57h+var_88]
0x180536d95  lea     rdx, aExecsimpledial; "ExecSimpleDialogContentElement"
0x180536d9c  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x180536da2  mov     rcx, [rbp+57h+var_88]
0x180536da6  mov     edx, 1
0x180536dab  call    cs:__imp_?SetConstrainLayout@RichText@DirectUI@@QEAAJH@Z; DirectUI::RichText::SetConstrainLayout(int)
0x180536db1  mov     rbx, [rbp+57h+var_88]
0x180536db5  xor     r9d, r9d
0x180536db8  mov     rcx, rbx
0x180536dbb  lea     r8d, [r9+0Ch]
0x180536dbf  call    ?DUI_TransformContentAlign@@YAHPEAVElement@DirectUI@@W4DUI_COORDINATES_SYSTEM@@H1@Z; DUI_TransformContentAlign(DirectUI::Element *,DUI_COORDINATES_SYSTEM,int,DUI_COORDINATES_SYSTEM)
0x180536dc4  mov     edx, eax
0x180536dc6  mov     rcx, rbx
0x180536dc9  call    cs:__imp_?SetContentAlign@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetContentAlign(int)
0x180536dcf  mov     rdx, [rsi+18h]
0x180536dd3  mov     rcx, [rbp+57h+var_88]
0x180536dd7  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180536ddd  lea     rcx, [rbp+57h+var_78]
0x180536de1  mov     [rbp+57h+var_78], 0
0x180536de9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180536dee  xor     edx, edx; pUnkOuter
0x180536df0  lea     rax, [rbp+57h+var_78]
0x180536df4  lea     r9, _GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1; riid
0x180536dfb  mov     [rsp+0C0h+ppv], rax; ppv
0x180536e00  lea     rcx, CLSID_PopupWindowFactory; rclsid
0x180536e07  lea     r8d, [rdx+1]; dwClsContext
0x180536e0b  call    cs:__imp_CoCreateInstance
0x180536e11  test    eax, eax
0x180536e13  js      loc_18053702A
0x180536e19  mov     r14, [rsi]
0x180536e1c  test    r14, r14
0x180536e1f  jnz     short loc_180536E32
0x180536e21  call    ?CreateDummyWindow@@YAPEAUHWND__@@XZ; CreateDummyWindow(void)
0x180536e26  test    rax, rax
0x180536e29  mov     r14, rax
0x180536e2c  setnz   r13b
0x180536e30  jmp     short loc_180536E35
0x180536e32  xor     r13b, r13b
0x180536e35  mov     rcx, [rbp+57h+var_78]
0x180536e39  mov     edx, 9
0x180536e3e  mov     rax, [rcx]
0x180536e41  mov     rax, [rax+18h]
0x180536e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180536e4a  mov     rdi, [rbp+57h+var_78]
0x180536e4e  lea     rcx, [rbp+57h+var_90]
0x180536e52  mov     [rbp+57h+var_90], 0
0x180536e5a  mov     rax, [rdi]
0x180536e5d  mov     rbx, [rax+48h]
0x180536e61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180536e66  lea     r8, [rbp+57h+var_90]
0x180536e6a  mov     rdx, r14
0x180536e6d  mov     rcx, rdi
0x180536e70  mov     rax, rbx
0x180536e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180536e78  test    eax, eax
0x180536e7a  js      loc_180537021
0x180536e80  mov     rcx, [rbp+57h+var_90]
0x180536e84  mov     rdx, [rbp+57h+var_88]
0x180536e88  mov     rax, [rcx]
0x180536e8b  mov     rax, [rax+160h]
0x180536e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180536e97  mov     ebx, eax
0x180536e99  test    eax, eax
0x180536e9b  js      loc_180536FF3
0x180536ea1  mov     rcx, [rbp+57h+var_90]
0x180536ea5  mov     rdx, [rsi+10h]
0x180536ea9  mov     [rbp+57h+var_88], 0
0x180536eb1  mov     rax, [rcx]
0x180536eb4  mov     rax, [rax+20h]
0x180536eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180536ebd  xor     edi, edi
0x180536ebf  xor     r15d, r15d
0x180536ec2  mov     [rbp+57h+var_60], r15
0x180536ec6  xor     r12d, r12d
0x180536ec9  mov     [rbp+57h+var_58], rdi
0x180536ecd  mov     [rbp+57h+var_50], rdi
0x180536ed1  mov     [rbp+57h+var_48], rdi
0x180536ed5  cmp     r12d, [rsi+28h]
0x180536ed9  jnb     loc_180536F81
0x180536edf  mov     rax, [rbp+57h+var_68]
0x180536ee3  lea     rcx, [rbp+57h+var_80]
0x180536ee7  mov     [rbp+57h+var_70], rax
0x180536eeb  mov     rax, [rsi+20h]
0x180536eef  mov     [rbp+57h+var_80], 0
0x180536ef7  lea     rbx, [rax+r12*4]
0x180536efb  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x180536f00  lea     r9, [rbp+57h+var_70]
0x180536f04  mov     r8, rbx
0x180536f07  mov     rdx, rbx
0x180536f0a  lea     rcx, [rbp+57h+var_80]
0x180536f0e  call    Microsoft__WRL__Details__MakeAndInitialize_CLambdaCommandHandler_IPopupCommand_unsigned_int_const___unsigned_int_const____lambda_ec1faf3780b50c0982032afb3f78ef2c___
0x180536f13  mov     ebx, eax
0x180536f15  test    eax, eax
0x180536f17  js      short loc_180536F6B
0x180536f19  mov     rcx, [rbp+57h+var_80]
0x180536f1d  xor     ebx, ebx
0x180536f1f  mov     [rbp+57h+var_70], rcx
0x180536f23  cmp     rdi, [rbp+57h+var_48]
0x180536f27  jnz     short loc_180536F48
0x180536f29  lea     rdx, [rdi+1]
0x180536f2d  lea     rcx, [rbp+57h+var_60]
0x180536f31  call    ?_EnsureCapacity@?$CTSimpleArray@PEAU_ITEMIDLIST_ABSOLUTE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAU_ITEMIDLIST_ABSOLUTE@@@@V?$CSimpleArrayStandardCompareHelper@PEAU_ITEMIDLIST_ABSOLUTE@@@@V?$CSimpleArrayStandardMergeHelper@PEAU_ITEMIDLIST_ABSOLUTE@@@@@@QEAAJ_K0@Z; CTSimpleArray<_ITEMIDLIST_ABSOLUTE *,4294967294,CTPolicyCoTaskMem<_ITEMIDLIST_ABSOLUTE *>,CSimpleArrayStandardCompareHelper<_ITEMIDLIST_ABSOLUTE *>,CSimpleArrayStandardMergeHelper<_ITEMIDLIST_ABSOLUTE *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180536f36  mov     rdi, [rbp+57h+var_58]
0x180536f3a  mov     ebx, eax
0x180536f3c  mov     r15, [rbp+57h+var_60]
0x180536f40  test    eax, eax
0x180536f42  js      short loc_180536F5F
0x180536f44  mov     rcx, [rbp+57h+var_70]
0x180536f48  inc     rdi
0x180536f4b  mov     [rbp+57h+var_58], rdi
0x180536f4f  lea     rax, [rdi-1]
0x180536f53  lea     rax, [r15+rax*8]
0x180536f57  test    rax, rax
0x180536f5a  jz      short loc_180536F5F
0x180536f5c  mov     [rax], rcx
0x180536f5f  test    ebx, ebx
0x180536f61  js      short loc_180536F6B
0x180536f63  mov     [rbp+57h+var_80], 0
0x180536f6b  lea     rcx, [rbp+57h+var_80]
0x180536f6f  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x180536f74  inc     r12d
0x180536f77  test    ebx, ebx
0x180536f79  jns     loc_180536ED5
0x180536f7f  jmp     short loc_180536FCD
0x180536f81  mov     rcx, [rbp+57h+var_90]
0x180536f85  mov     r8, r15
0x180536f88  mov     edx, [rsi+28h]
0x180536f8b  mov     rax, [rcx]
0x180536f8e  mov     rax, [rax+40h]
0x180536f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180536f97  mov     ebx, eax
0x180536f99  test    eax, eax
0x180536f9b  js      short loc_180536FCD
0x180536f9d  mov     rcx, [rbp+57h+var_90]
0x180536fa1  mov     edx, [rsi+28h]
0x180536fa4  sub     edx, [rsi+2Ch]
0x180536fa7  dec     edx
0x180536fa9  mov     rax, [rcx]
0x180536fac  mov     rax, [rax+58h]
0x180536fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180536fb5  mov     rcx, [rbp+57h+var_90]
0x180536fb9  mov     edx, [rsi+28h]
0x180536fbc  sub     edx, [rsi+30h]
0x180536fbf  dec     edx
0x180536fc1  mov     rax, [rcx]
0x180536fc4  mov     rax, [rax+78h]
0x180536fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180536fcd  lea     rcx, [rbp+57h+var_60]
0x180536fd1  call    ??1?$CSimplePointerArray@UIPopupCommand@@V?$CTContainer_PolicyRelease@UIPopupCommand@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIPopupCommand@@@@@@QEAA@XZ; CSimplePointerArray<IPopupCommand,CTContainer_PolicyRelease<IPopupCommand>,CSimpleArrayStandardCompareHelper<IPopupCommand *>>::~CSimplePointerArray<IPopupCommand,CTContainer_PolicyRelease<IPopupCommand>,CSimpleArrayStandardCompareHelper<IPopupCommand *>>(void)
0x180536fd6  test    ebx, ebx
0x180536fd8  js      short loc_180536FF3
0x180536fda  mov     rcx, [rbp+57h+var_90]
0x180536fde  mov     rax, [rcx]
0x180536fe1  mov     rax, [rax+110h]
0x180536fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180536fed  mov     ebx, eax
0x180536fef  test    eax, eax
0x180536ff1  jns     short loc_18053700D
0x180536ff3  mov     rax, [rbp+57h+var_68]
0x180536ff7  mov     rcx, [rbp+57h+var_90]
0x180536ffb  mov     [rax+8], ebx
0x180536ffe  mov     rax, [rcx]
0x180537001  mov     rax, [rax+128h]
0x180537008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18053700d  call    cs:__imp_StartMessagePump
0x180537013  test    r13b, r13b
0x180537016  jz      short loc_180537021
0x180537018  mov     rcx, r14; hWnd
0x18053701b  call    cs:__imp_DestroyWindow
0x180537021  lea     rcx, [rbp+57h+var_90]
0x180537025  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18053702a  mov     rcx, [rbp+57h+var_88]
0x18053702e  test    rcx, rcx
0x180537031  jz      short loc_18053703B
0x180537033  mov     dl, 1
0x180537035  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18053703b  lea     rcx, [rbp+57h+var_78]
0x18053703f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180537044  call    cs:__imp_UnInitThread
0x18053704a  lea     rcx, __ImageBase
0x180537051  call    cs:__imp_UnInitProcessPriv
0x180537057  xor     eax, eax
0x180537059  add     rsp, 88h
0x180537060  pop     r15
0x180537062  pop     r14
0x180537064  pop     r13
0x180537066  pop     r12
0x180537068  pop     rdi
0x180537069  pop     rsi
0x18053706a  pop     rbx
0x18053706b  pop     rbp
0x18053706c  retn
```
