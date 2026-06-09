# ResolveUri_AppX(unsigned __int64,ushort const *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR *,RESOURCE_CONTRAST *,ushort * *)

- ea: `0x180006ad0`
- end: `0x180006d21`
- name: `?ResolveUri_AppX@@YAJ_KPEBG11PEAW4DEVICE_SCALE_FACTOR@@PEAW4RESOURCE_CONTRAST@@PEAPEAG@Z`
- size: `593`
- prototype: `__int64 __fastcall(unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum DEVICE_SCALE_FACTOR *, enum RESOURCE_CONTRAST *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000bbf0`

## callees

- `0x180005670`
- `0x180006ad0`
- `0x1800070e8`
- `0x18000710c`
- `0x180015204`
- `0x18001b848`
- `0x18001cd2c`
- `0x180032010`

## import_xrefs

- `combase!__imp_CoCreateInstanceAsUser` at `0x180006b2e`
- `combase!__imp_CoCreateInstanceAsUser` at `0x180006b2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ResolveUri_AppX(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        enum DEVICE_SCALE_FACTOR *a5,
        enum RESOURCE_CONTRAST *a6,
        unsigned __int16 **a7)
{
  int InstanceAsUser; // eax
  int v12; // ebx
  unsigned __int16 **v13; // rcx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *); // rdi
  int v16; // edx
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  unsigned __int16 **v23; // rdi
  __int64 (__fastcall *v24)(unsigned __int16 **, __int64 *); // rbx
  int v25; // eax
  int v26; // eax
  GUID *v27; // [rsp+20h] [rbp-48h]
  int v28; // [rsp+20h] [rbp-48h]
  __int64 v29; // [rsp+40h] [rbp-28h] BYREF
  __int64 v30; // [rsp+48h] [rbp-20h]
  _QWORD v31[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  *a7 = 0;
  v30 = 0;
  a7 = 0;
  IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWpnPlatform>>(&a7);
  v27 = &GUID_df8e9480_ca73_448e_b8f0_da000f581428;
  InstanceAsUser = CoCreateInstanceAsUser(&GUID_0c9281f9_6da1_4006_8729_de6e6b61581c, 0, 1028, a1);
  v12 = InstanceAsUser;
  if ( InstanceAsUser < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)InstanceAsUser,
      (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
    v13 = a7;
    if ( a7 )
    {
      a7 = 0;
      (*((void (__fastcall **)(unsigned __int16 **))*v13 + 2))(v13);
    }
    goto LABEL_4;
  }
  v29 = 0;
  v23 = a7;
  v24 = (__int64 (__fastcall *)(unsigned __int16 **, __int64 *))*((_QWORD *)*a7 + 4);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  v25 = v24(v23, &v29);
  v12 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x258,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v25,
      (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
LABEL_20:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&a7);
    goto LABEL_4;
  }
  v31[0] = 0;
  v26 = Microsoft::WRL::ComPtr<IWpnPresentationEndpoint>::As<IWpnMrtHelper>(&v29, v31);
  v12 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v26,
      (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v31);
    goto LABEL_20;
  }
  v22 = v31[0];
  if ( v31[0] )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31[0] + 8LL))(v31[0]);
    v22 = v31[0];
  }
  v30 = v22;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v31);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&a7);
  v12 = 0;
LABEL_4:
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v12,
      (int)v27);
  v14 = v30;
  v15 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v30 + 40LL);
  ToWPNContrast(a6);
  if ( a5 )
    v16 = *a5;
  else
    v16 = 0;
  v28 = v16;
  v17 = v15(v14, a2, a3, a4);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x114,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v17,
      v28);
    v21 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    return v18;
  }
  else
  {
    v19 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180006ad0  push    rbp
0x180006ad2  push    rbx
0x180006ad3  push    rsi
0x180006ad4  push    rdi
0x180006ad5  push    r12
0x180006ad7  push    r13
0x180006ad9  push    r14
0x180006adb  push    r15
0x180006add  mov     rbp, rsp
0x180006ae0  sub     rsp, 68h
0x180006ae4  mov     r14, r9
0x180006ae7  mov     r15, r8
0x180006aea  mov     r12, rdx
0x180006aed  mov     rbx, rcx
0x180006af0  xor     r13d, r13d
0x180006af3  mov     rsi, [rbp+arg_30]
0x180006af7  mov     [rsi], r13
0x180006afa  mov     [rbp+var_20], r13
0x180006afe  mov     [rbp+arg_30], r13
0x180006b02  lea     rcx, [rbp+arg_30]
0x180006b06  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWpnPlatform>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnPlatform>>)
0x180006b0b  mov     [rsp+68h+var_40], rax
0x180006b10  lea     rax, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x180006b17  mov     qword ptr [rsp+68h+var_48], rax; int
0x180006b1c  mov     r9, rbx
0x180006b1f  xor     edx, edx
0x180006b21  mov     r8d, 404h
0x180006b27  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x180006b2e  call    cs:__imp_CoCreateInstanceAsUser
0x180006b34  mov     ebx, eax
0x180006b36  test    eax, eax
0x180006b38  jns     loc_180006C6E
0x180006b3e  mov     rcx, [rbp+40h]; this
0x180006b42  mov     r9d, eax; char *
0x180006b45  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006b4c  mov     edx, 255h; void *
0x180006b51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b56  nop
0x180006b57  mov     rcx, [rbp+arg_30]
0x180006b5b  test    rcx, rcx
0x180006b5e  jz      short loc_180006B71
0x180006b60  mov     [rbp+arg_30], r13
0x180006b64  mov     rax, [rcx]
0x180006b67  mov     rax, [rax+10h]
0x180006b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b70  nop
0x180006b71  mov     rcx, [rbp+40h]; this
0x180006b75  test    ebx, ebx
0x180006b77  js      loc_180006D0C
0x180006b7d  mov     rbx, [rbp+var_20]
0x180006b81  mov     rax, [rbx]
0x180006b84  mov     rdi, [rax+28h]
0x180006b88  mov     rcx, [rbp+arg_28]
0x180006b8c  call    ?ToWPNContrast@@YA?AW4__MIDL___MIDL_itf_wpnplatform_0000_0028_0001@@PEAW4RESOURCE_CONTRAST@@@Z; ToWPNContrast(RESOURCE_CONTRAST *)
0x180006b91  mov     rcx, [rbp+arg_20]
0x180006b95  test    rcx, rcx
0x180006b98  jz      short loc_180006BF0
0x180006b9a  mov     edx, [rcx]
0x180006b9c  mov     [rsp+68h+var_38], rsi
0x180006ba1  mov     dword ptr [rsp+68h+var_40], eax
0x180006ba5  mov     [rsp+68h+var_48], edx; int
0x180006ba9  mov     r9, r14
0x180006bac  mov     r8, r15
0x180006baf  mov     rdx, r12
0x180006bb2  mov     rcx, rbx
0x180006bb5  mov     rax, rdi
0x180006bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bbd  mov     ebx, eax
0x180006bbf  test    eax, eax
0x180006bc1  js      short loc_180006BF5
0x180006bc3  mov     rcx, [rbp+var_20]
0x180006bc7  test    rcx, rcx
0x180006bca  jz      short loc_180006BDD
0x180006bcc  mov     [rbp+var_20], r13
0x180006bd0  mov     rax, [rcx]
0x180006bd3  mov     rax, [rax+10h]
0x180006bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bdc  nop
0x180006bdd  xor     eax, eax
0x180006bdf  add     rsp, 68h
0x180006be3  pop     r15
0x180006be5  pop     r14
0x180006be7  pop     r13
0x180006be9  pop     r12
0x180006beb  pop     rdi
0x180006bec  pop     rsi
0x180006bed  pop     rbx
0x180006bee  pop     rbp
0x180006bef  retn
0x180006bf0  mov     edx, r13d
0x180006bf3  jmp     short loc_180006B9C
0x180006bf5  mov     rcx, [rbp+40h]; this
0x180006bf9  mov     r9d, ebx; char *
0x180006bfc  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006c03  mov     edx, 114h; void *
0x180006c08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c0d  nop
0x180006c0e  mov     rcx, [rbp+var_20]
0x180006c12  test    rcx, rcx
0x180006c15  jz      short loc_180006C28
0x180006c17  mov     [rbp+var_20], r13
0x180006c1b  mov     rax, [rcx]
0x180006c1e  mov     rax, [rax+10h]
0x180006c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c27  nop
0x180006c28  mov     eax, ebx
0x180006c2a  jmp     short loc_180006BDF
0x180006c2c  mov     rcx, [rbp+var_18]
0x180006c30  test    rcx, rcx
0x180006c33  jz      short loc_180006C45
0x180006c35  mov     rax, [rcx]
0x180006c38  mov     rax, [rax+8]
0x180006c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c41  mov     rcx, [rbp+var_18]
0x180006c45  mov     [rbp+var_20], rcx
0x180006c49  lea     rcx, [rbp+var_18]
0x180006c4d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006c52  nop
0x180006c53  lea     rcx, [rbp+var_28]
0x180006c57  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006c5c  nop
0x180006c5d  lea     rcx, [rbp+arg_30]
0x180006c61  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006c66  mov     ebx, r13d
0x180006c69  jmp     loc_180006B71
0x180006c6e  mov     [rbp+var_28], r13
0x180006c72  mov     rdi, [rbp+arg_30]
0x180006c76  mov     rax, [rdi]
0x180006c79  mov     rbx, [rax+20h]
0x180006c7d  lea     rcx, [rbp+var_28]
0x180006c81  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006c86  lea     rdx, [rbp+var_28]
0x180006c8a  mov     rcx, rdi
0x180006c8d  mov     rax, rbx
0x180006c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c95  mov     ebx, eax
0x180006c97  test    eax, eax
0x180006c99  jns     short loc_180006CEF
0x180006c9b  mov     rcx, [rbp+40h]; this
0x180006c9f  mov     r9d, eax; char *
0x180006ca2  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006ca9  mov     edx, 258h; void *
0x180006cae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006cb3  jmp     short loc_180006CD7
0x180006cb5  mov     rcx, [rbp+40h]; this
0x180006cb9  mov     r9d, eax; char *
0x180006cbc  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006cc3  mov     edx, 25Bh; void *
0x180006cc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ccd  lea     rcx, [rbp+var_18]
0x180006cd1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006cd6  nop
0x180006cd7  lea     rcx, [rbp+var_28]
0x180006cdb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006ce0  nop
0x180006ce1  lea     rcx, [rbp+arg_30]
0x180006ce5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006cea  jmp     loc_180006B71
0x180006cef  mov     [rbp+var_18], r13
0x180006cf3  lea     rdx, [rbp+var_18]
0x180006cf7  lea     rcx, [rbp+var_28]
0x180006cfb  call    ??$As@UIWpnMrtHelper@@@?$ComPtr@UIWpnPresentationEndpoint@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWpnMrtHelper@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IWpnPresentationEndpoint>::As<IWpnMrtHelper>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnMrtHelper>>)
0x180006d00  mov     ebx, eax
0x180006d02  test    eax, eax
0x180006d04  jns     loc_180006C2C
0x180006d0a  jmp     short loc_180006CB5
0x180006d0c  mov     r9d, ebx; char *
0x180006d0f  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006d16  mov     edx, 10Ch; void *
0x180006d1b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
