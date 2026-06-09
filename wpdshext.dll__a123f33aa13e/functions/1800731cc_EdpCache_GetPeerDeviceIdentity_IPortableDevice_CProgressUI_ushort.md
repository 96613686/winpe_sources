# EdpCache::_GetPeerDeviceIdentity(IPortableDevice *,CProgressUI *,ushort * *)

- ea: `0x1800731cc`
- end: `0x1800734ea`
- name: `?_GetPeerDeviceIdentity@EdpCache@@AEAAJPEAUIPortableDevice@@PEAVCProgressUI@@PEAPEAG@Z`
- size: `798`
- prototype: `int(EdpCache *__hidden this, struct IPortableDevice *, struct CProgressUI *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180072884`

## callees

- `0x180016260`
- `0x18002beb8`
- `0x18002bee4`
- `0x18002ff5c`
- `0x180054524`
- `0x1800545c8`
- `0x1800731cc`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180073286`
- `KERNEL32!Sleep` at `0x180073406`
- `KERNEL32!Sleep` at `0x180073286`
- `KERNEL32!Sleep` at `0x180073406`
- `ole32!CoTaskMemAlloc` at `0x18007348c`
- `ole32!CoTaskMemAlloc` at `0x18007348c`
- `ole32!CoCreateInstance` at `0x1800732e5`
- `ole32!CoCreateInstance` at `0x1800732e5`

## string_xrefs

- `0x180073228`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x1800732f8`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x180073379`: `multimedia\wpd\ui\shellext\edpcache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EdpCache::_GetPeerDeviceIdentity(
        EdpCache *this,
        struct IPortableDevice *a2,
        struct CProgressUI *a3,
        unsigned __int16 **a4)
{
  _DWORD *v7; // rsi
  int PortableDeviceProperties; // ebx
  int v9; // r14d
  int v10; // edi
  HRESULT v11; // eax
  struct IPortableDeviceProperties *v12; // rdi
  HRESULT (__stdcall *v13)(IPortableDeviceProperties *, LPCWSTR, IPortableDeviceKeyCollection *, IPortableDeviceValues **); // rbx
  __int64 v14; // rdx
  int v15; // r12d
  int v16; // r14d
  struct IPortableDeviceProperties *v17; // rdi
  HRESULT (__stdcall *GetValues)(IPortableDeviceProperties *, LPCWSTR, IPortableDeviceKeyCollection *, IPortableDeviceValues **); // rbx
  int v19; // eax
  unsigned __int16 *v20; // rcx
  int ppv; // [rsp+20h] [rbp-20h]
  int ppva; // [rsp+20h] [rbp-20h]
  struct IPortableDeviceProperties *v24[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  EdpCache *v26; // [rsp+80h] [rbp+40h] BYREF
  LPVOID v27; // [rsp+90h] [rbp+50h] BYREF

  v26 = this;
  v24[0] = 0;
  v7 = (_DWORD *)((char *)a3 + 104);
  if ( a3 )
  {
    v9 = 0;
    v10 = 0;
    while ( !*v7 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
      PortableDeviceProperties = GetPortableDeviceProperties(a2, v24);
      if ( PortableDeviceProperties != -2147024726 )
        goto LABEL_14;
      if ( !v9 )
      {
        v9 = 1;
        v10 = 1;
        CProgressUI::_StartMarquee(a3);
      }
      if ( *v7 )
        break;
      Sleep(0x5DCu);
    }
    PortableDeviceProperties = -2147023673;
LABEL_14:
    if ( v10 )
      CProgressUI::_StopMarquee(a3);
    if ( *v7 )
    {
      PortableDeviceProperties = -2147023673;
      goto LABEL_4;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
    PortableDeviceProperties = GetPortableDeviceProperties(a2, v24);
  }
  if ( PortableDeviceProperties >= 0 )
  {
    v27 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    v11 = CoCreateInstance(&CLSID_PortableDeviceKeyCollection, 0, 1u, &GUID_dada2357_e0ad_492e_98db_dd61c53ba353, &v27);
    PortableDeviceProperties = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
        (const char *)(unsigned int)v11,
        ppva);
LABEL_20:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
      goto LABEL_47;
    }
    (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)v27 + 40LL))(v27, &WPD_DEVICE_EDP_IDENTITY);
    v26 = 0;
    if ( a3 )
    {
      v15 = 0;
      v16 = 0;
      while ( !*v7 )
      {
        v17 = v24[0];
        GetValues = v24[0]->lpVtbl->GetValues;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
        PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDeviceProperties *, const WCHAR *, LPVOID, EdpCache **))GetValues)(
                                     v17,
                                     L"DEVICE",
                                     v27,
                                     &v26);
        if ( PortableDeviceProperties != -2147024726 )
          goto LABEL_35;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
        if ( !v15 )
        {
          v15 = 1;
          v16 = 1;
          CProgressUI::_StartMarquee(a3);
        }
        if ( *v7 )
          break;
        Sleep(0x5DCu);
      }
      PortableDeviceProperties = -2147023673;
LABEL_35:
      if ( v16 )
        CProgressUI::_StopMarquee(a3);
      if ( *v7 )
      {
        PortableDeviceProperties = -2147023673;
        goto LABEL_24;
      }
    }
    else
    {
      v12 = v24[0];
      v13 = v24[0]->lpVtbl->GetValues;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDeviceProperties *, const WCHAR *, LPVOID, EdpCache **))v13)(
                                   v12,
                                   L"DEVICE",
                                   v27,
                                   &v26);
    }
    if ( PortableDeviceProperties >= 0 )
    {
      v19 = (*(__int64 (__fastcall **)(EdpCache *, const PROPERTYKEY *, unsigned __int16 **))(*(_QWORD *)v26 + 64LL))(
              v26,
              &WPD_DEVICE_EDP_IDENTITY,
              a4);
      if ( v19 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            &WPP_26bd9f167370339dad26092ea255962f_Traceguids,
            (unsigned int)v19);
        v20 = (unsigned __int16 *)CoTaskMemAlloc(2u);
        *a4 = v20;
        if ( !v20 )
        {
          PortableDeviceProperties = -2147024882;
          v14 = 249;
          goto LABEL_25;
        }
        *v20 = 0;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
      PortableDeviceProperties = 0;
      goto LABEL_47;
    }
LABEL_24:
    v14 = 240;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
      (const char *)(unsigned int)PortableDeviceProperties,
      ppva);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    goto LABEL_20;
  }
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE6,
    (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
    (const char *)(unsigned int)PortableDeviceProperties,
    ppv);
LABEL_47:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
  return (unsigned int)PortableDeviceProperties;
}

```

## disassembly

```asm
0x1800731cc  mov     [rsp-38h+arg_8], rbx
0x1800731d1  mov     [rsp-38h+arg_0], rcx
0x1800731d6  push    rbp
0x1800731d7  push    rsi
0x1800731d8  push    rdi
0x1800731d9  push    r12
0x1800731db  push    r13
0x1800731dd  push    r14
0x1800731df  push    r15
0x1800731e1  mov     rbp, rsp
0x1800731e4  sub     rsp, 40h
0x1800731e8  mov     r13, r9
0x1800731eb  mov     r15, r8
0x1800731ee  mov     r12, rdx
0x1800731f1  mov     [rbp+var_10], 0
0x1800731f9  lea     rsi, [r8+68h]
0x1800731fd  test    r8, r8
0x180073200  jnz     short loc_18007323E
0x180073202  lea     rcx, [rbp+var_10]
0x180073206  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007320b  lea     rdx, [rbp+var_10]; struct IPortableDeviceProperties **
0x18007320f  mov     rcx, r12; struct IPortableDevice *
0x180073212  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x180073217  mov     ebx, eax
0x180073219  test    ebx, ebx
0x18007321b  jns     loc_1800732B7
0x180073221  mov     rcx, [rbp+38h]; this
0x180073225  mov     r9d, ebx; char *
0x180073228  lea     r8, aMultimediaWpdU_1; "multimedia\\wpd\\ui\\shellext\\edpcache"...
0x18007322f  mov     edx, 0E6h; void *
0x180073234  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073239  jmp     loc_1800734C7
0x18007323e  xor     r14d, r14d
0x180073241  xor     edi, edi
0x180073243  cmp     dword ptr [rsi], 0
0x180073246  jnz     short loc_180073293
0x180073248  lea     rcx, [rbp+var_10]
0x18007324c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180073251  lea     rdx, [rbp+var_10]; struct IPortableDeviceProperties **
0x180073255  mov     rcx, r12; struct IPortableDevice *
0x180073258  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x18007325d  mov     ebx, eax
0x18007325f  cmp     eax, 800700AAh
0x180073264  jnz     short loc_180073298
0x180073266  test    r14d, r14d
0x180073269  jnz     short loc_18007327C
0x18007326b  lea     eax, [r14+1]
0x18007326f  mov     r14d, eax
0x180073272  mov     edi, eax
0x180073274  mov     rcx, r15; this
0x180073277  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18007327c  cmp     dword ptr [rsi], 0
0x18007327f  jnz     short loc_180073293
0x180073281  mov     ecx, 5DCh; dwMilliseconds
0x180073286  call    cs:__imp_Sleep
0x18007328c  test    r14d, r14d
0x18007328f  jz      short loc_180073298
0x180073291  jmp     short loc_180073243
0x180073293  mov     ebx, 800704C7h
0x180073298  test    edi, edi
0x18007329a  jz      short loc_1800732A4
0x18007329c  mov     rcx, r15; this
0x18007329f  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x1800732a4  cmp     dword ptr [rsi], 0
0x1800732a7  jz      loc_180073219
0x1800732ad  mov     ebx, 800704C7h
0x1800732b2  jmp     loc_180073221
0x1800732b7  mov     [rbp+arg_10], 0
0x1800732bf  lea     rcx, [rbp+arg_10]
0x1800732c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800732c8  lea     rax, [rbp+arg_10]
0x1800732cc  mov     qword ptr [rsp+40h+ppv], rax; int
0x1800732d1  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x1800732d8  xor     edx, edx; pUnkOuter
0x1800732da  lea     r8d, [rdx+1]; dwClsContext
0x1800732de  lea     rcx, CLSID_PortableDeviceKeyCollection; rclsid
0x1800732e5  call    cs:__imp_CoCreateInstance
0x1800732eb  mov     ebx, eax
0x1800732ed  test    eax, eax
0x1800732ef  jns     short loc_180073318
0x1800732f1  mov     rcx, [rbp+38h]; this
0x1800732f5  mov     r9d, eax; char *
0x1800732f8  lea     r8, aMultimediaWpdU_1; "multimedia\\wpd\\ui\\shellext\\edpcache"...
0x1800732ff  mov     edx, 0EAh; void *
0x180073304  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073309  nop
0x18007330a  lea     rcx, [rbp+arg_10]
0x18007330e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180073313  jmp     loc_1800734C7
0x180073318  mov     rcx, [rbp+arg_10]
0x18007331c  mov     rax, [rcx]
0x18007331f  lea     rdx, WPD_DEVICE_EDP_IDENTITY
0x180073326  mov     rax, [rax+28h]
0x18007332a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007332f  mov     [rbp+arg_0], 0
0x180073337  test    r15, r15
0x18007333a  jnz     short loc_18007339B
0x18007333c  mov     rdi, [rbp+var_10]
0x180073340  mov     rax, [rdi]
0x180073343  mov     rbx, [rax+28h]
0x180073347  lea     rcx, [rbp+arg_0]
0x18007334b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180073350  lea     r9, [rbp+arg_0]
0x180073354  mov     r8, [rbp+arg_10]
0x180073358  lea     rdx, aDevice_0; "DEVICE"
0x18007335f  mov     rcx, rdi
0x180073362  mov     rax, rbx
0x180073365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007336a  mov     ebx, eax
0x18007336c  test    ebx, ebx
0x18007336e  jns     loc_180073438
0x180073374  mov     edx, 0F0h; void *
0x180073379  lea     r8, aMultimediaWpdU_1; "multimedia\\wpd\\ui\\shellext\\edpcache"...
0x180073380  mov     r9d, ebx; char *
0x180073383  mov     rcx, [rbp+38h]; this
0x180073387  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007338c  nop
0x18007338d  lea     rcx, [rbp+arg_0]
0x180073391  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180073396  jmp     loc_18007330A
0x18007339b  xor     r12d, r12d
0x18007339e  xor     r14d, r14d
0x1800733a1  cmp     dword ptr [rsi], 0
0x1800733a4  jnz     short loc_180073413
0x1800733a6  mov     rdi, [rbp+var_10]
0x1800733aa  mov     rax, [rdi]
0x1800733ad  mov     rbx, [rax+28h]
0x1800733b1  lea     rcx, [rbp+arg_0]
0x1800733b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800733ba  lea     r9, [rbp+arg_0]
0x1800733be  mov     r8, [rbp+arg_10]
0x1800733c2  lea     rdx, aDevice_0; "DEVICE"
0x1800733c9  mov     rcx, rdi
0x1800733cc  mov     rax, rbx
0x1800733cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800733d4  mov     ebx, eax
0x1800733d6  cmp     eax, 800700AAh
0x1800733db  jnz     short loc_180073418
0x1800733dd  lea     rcx, [rbp+arg_0]
0x1800733e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800733e6  test    r12d, r12d
0x1800733e9  jnz     short loc_1800733FC
0x1800733eb  mov     r12d, 1
0x1800733f1  mov     r14d, r12d
0x1800733f4  mov     rcx, r15; this
0x1800733f7  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x1800733fc  cmp     dword ptr [rsi], 0
0x1800733ff  jnz     short loc_180073413
0x180073401  mov     ecx, 5DCh; dwMilliseconds
0x180073406  call    cs:__imp_Sleep
0x18007340c  test    r12d, r12d
0x18007340f  jz      short loc_180073418
0x180073411  jmp     short loc_1800733A1
0x180073413  mov     ebx, 800704C7h
0x180073418  test    r14d, r14d
0x18007341b  jz      short loc_180073425
0x18007341d  mov     rcx, r15; this
0x180073420  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x180073425  cmp     dword ptr [rsi], 0
0x180073428  jz      loc_18007336C
0x18007342e  mov     ebx, 800704C7h
0x180073433  jmp     loc_180073374
0x180073438  mov     rcx, [rbp+arg_0]
0x18007343c  mov     rax, [rcx]
0x18007343f  mov     r8, r13
0x180073442  lea     rdx, WPD_DEVICE_EDP_IDENTITY
0x180073449  mov     rax, [rax+40h]
0x18007344d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073452  test    eax, eax
0x180073454  jns     short loc_1800734B2
0x180073456  lea     rdx, WPP_GLOBAL_Control
0x18007345d  mov     rcx, cs:WPP_GLOBAL_Control
0x180073464  cmp     rcx, rdx
0x180073467  jz      short loc_180073487
0x180073469  test    byte ptr [rcx+1Ch], 40h
0x18007346d  jz      short loc_180073487
0x18007346f  mov     edx, 0Eh
0x180073474  mov     r9d, eax
0x180073477  lea     r8, WPP_26bd9f167370339dad26092ea255962f_Traceguids
0x18007347e  mov     rcx, [rcx+10h]
0x180073482  call    WPP_SF_d
0x180073487  mov     ecx, 2; cb
0x18007348c  call    cs:__imp_CoTaskMemAlloc
0x180073492  mov     rcx, rax
0x180073495  mov     [r13+0], rax
0x180073499  test    rax, rax
0x18007349c  jnz     short loc_1800734AD
0x18007349e  mov     ebx, 8007000Eh
0x1800734a3  mov     edx, 0F9h
0x1800734a8  jmp     loc_180073379
0x1800734ad  xor     eax, eax
0x1800734af  mov     [rcx], ax
0x1800734b2  lea     rcx, [rbp+arg_0]
0x1800734b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800734bb  nop
0x1800734bc  lea     rcx, [rbp+arg_10]
0x1800734c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800734c5  xor     ebx, ebx
0x1800734c7  lea     rcx, [rbp+var_10]
0x1800734cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800734d0  mov     eax, ebx
0x1800734d2  mov     rbx, [rsp+40h+arg_8]
0x1800734da  add     rsp, 40h
0x1800734de  pop     r15
0x1800734e0  pop     r14
0x1800734e2  pop     r13
0x1800734e4  pop     r12
0x1800734e6  pop     rdi
0x1800734e7  pop     rsi
0x1800734e8  pop     rbp
0x1800734e9  retn
```
