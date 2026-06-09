# RegisterSystemToast(unsigned __int64)

- ea: `0x180016880`
- end: `0x1800169f0`
- name: `?RegisterSystemToast@@YAJ_K@Z`
- size: `368`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800169f8`

## callees

- `0x180006844`
- `0x18000885c`
- `0x180015b5c`
- `0x180016880`
- `0x18001d010`

## import_xrefs

- `combase!__imp_CoCreateInstanceAsUser` at `0x1800168c6`
- `combase!__imp_CoCreateInstanceAsUser` at `0x1800168c6`

## string_xrefs

- `0x1800168d9`: `onecore\base\win32\winnls\tzautoupdate\timezonetoastnotification.cpp`
- `0x180016927`: `onecore\base\win32\winnls\tzautoupdate\timezonetoastnotification.cpp`
- `0x180016967`: `onecore\base\win32\winnls\tzautoupdate\timezonetoastnotification.cpp`

## pseudocode

```c
__int64 __fastcall RegisterSystemToast(__int64 a1)
{
  int InstanceAsUser; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64 *); // rbx
  int v6; // eax
  int v7; // eax
  __int64 v8; // rdx
  GUID *v10; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v12; // [rsp+68h] [rbp+28h] BYREF
  __int64 v13; // [rsp+70h] [rbp+30h] BYREF
  __int64 v14; // [rsp+78h] [rbp+38h] BYREF

  v14 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v14);
  v10 = &GUID_df8e9480_ca73_448e_b8f0_da000f581428;
  InstanceAsUser = CoCreateInstanceAsUser(&GUID_0c9281f9_6da1_4006_8729_de6e6b61581c, 0, 1048580, a1);
  v3 = InstanceAsUser;
  if ( InstanceAsUser >= 0 )
  {
    v12 = 0;
    v4 = v14;
    v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 40LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12);
    v6 = v5(v4, &v12);
    v3 = v6;
    if ( v6 >= 0 )
    {
      v13 = 0;
      v7 = Microsoft::WRL::ComPtr<IWpnRegistrationEndpoint>::As<IWpnSystemRegistrationEndpoint>(&v12, &v13);
      v3 = v7;
      if ( v7 >= 0 )
      {
        LODWORD(v10) = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64))(*(_QWORD *)v13 + 24LL))(
               v13,
               L"System",
               L"Windows.SystemToast.TimeZoneChange",
               9471);
        v3 = v7;
        if ( v7 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v13);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12);
          v3 = 0;
          goto LABEL_12;
        }
        v8 = 60;
      }
      else
      {
        v8 = 55;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\timezonetoastnotification.cpp",
        (const char *)(unsigned int)v7,
        (int)v10);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v13);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\timezonetoastnotification.cpp",
        (const char *)(unsigned int)v6,
        (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\timezonetoastnotification.cpp",
      (const char *)(unsigned int)InstanceAsUser,
      (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
  }
LABEL_12:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v14);
  return v3;
}

```

## disassembly

```asm
0x180016880  push    rbp
0x180016882  push    rbx
0x180016883  push    rdi
0x180016884  mov     rbp, rsp
0x180016887  sub     rsp, 40h
0x18001688b  mov     rbx, rcx
0x18001688e  mov     [rbp+arg_18], 0
0x180016896  lea     rcx, [rbp+arg_18]
0x18001689a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001689f  lea     rax, [rbp+arg_18]
0x1800168a3  mov     [rsp+40h+var_18], rax
0x1800168a8  lea     rax, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x1800168af  mov     qword ptr [rsp+40h+var_20], rax; int
0x1800168b4  mov     r9, rbx
0x1800168b7  xor     edx, edx
0x1800168b9  mov     r8d, 100004h
0x1800168bf  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x1800168c6  call    cs:__imp_CoCreateInstanceAsUser
0x1800168cc  mov     ebx, eax
0x1800168ce  test    eax, eax
0x1800168d0  jns     short loc_1800168EF
0x1800168d2  mov     rcx, [rbp+18h]; this
0x1800168d6  mov     r9d, eax; char *
0x1800168d9  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x1800168e0  mov     edx, 31h ; '1'; void *
0x1800168e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800168ea  jmp     loc_1800169DD
0x1800168ef  mov     [rbp+arg_8], 0
0x1800168f7  mov     rdi, [rbp+arg_18]
0x1800168fb  mov     rax, [rdi]
0x1800168fe  mov     rbx, [rax+28h]
0x180016902  lea     rcx, [rbp+arg_8]
0x180016906  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001690b  lea     rdx, [rbp+arg_8]
0x18001690f  mov     rcx, rdi
0x180016912  mov     rax, rbx
0x180016915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001691a  mov     ebx, eax
0x18001691c  test    eax, eax
0x18001691e  jns     short loc_180016947
0x180016920  mov     rcx, [rbp+18h]; this
0x180016924  mov     r9d, eax; char *
0x180016927  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18001692e  mov     edx, 34h ; '4'; void *
0x180016933  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016938  nop
0x180016939  lea     rcx, [rbp+arg_8]
0x18001693d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016942  jmp     loc_1800169DD
0x180016947  mov     [rbp+arg_10], 0
0x18001694f  lea     rdx, [rbp+arg_10]
0x180016953  lea     rcx, [rbp+arg_8]
0x180016957  call    ??$As@UIWpnSystemRegistrationEndpoint@@@?$ComPtr@UIWpnRegistrationEndpoint@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWpnSystemRegistrationEndpoint@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IWpnRegistrationEndpoint>::As<IWpnSystemRegistrationEndpoint>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnSystemRegistrationEndpoint>>)
0x18001695c  mov     ebx, eax
0x18001695e  test    eax, eax
0x180016960  jns     short loc_180016986
0x180016962  mov     edx, 37h ; '7'; void *
0x180016967  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18001696e  mov     r9d, eax; char *
0x180016971  mov     rcx, [rbp+18h]; this
0x180016975  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001697a  nop
0x18001697b  lea     rcx, [rbp+arg_10]
0x18001697f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016984  jmp     short loc_180016939
0x180016986  mov     rcx, [rbp+arg_10]
0x18001698a  mov     rax, [rcx]
0x18001698d  mov     [rsp+40h+var_18], 0
0x180016996  mov     [rsp+40h+var_20], 0
0x18001699e  mov     r9d, 24FFh
0x1800169a4  lea     r8, aWindowsSystemt; "Windows.SystemToast.TimeZoneChange"
0x1800169ab  lea     rdx, aSystem; "System"
0x1800169b2  mov     rax, [rax+18h]
0x1800169b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169bb  mov     ebx, eax
0x1800169bd  test    eax, eax
0x1800169bf  jns     short loc_1800169C8
0x1800169c1  mov     edx, 3Ch ; '<'
0x1800169c6  jmp     short loc_180016967
0x1800169c8  lea     rcx, [rbp+arg_10]
0x1800169cc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800169d1  nop
0x1800169d2  lea     rcx, [rbp+arg_8]
0x1800169d6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800169db  xor     ebx, ebx
0x1800169dd  lea     rcx, [rbp+arg_18]
0x1800169e1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800169e6  mov     eax, ebx
0x1800169e8  add     rsp, 40h
0x1800169ec  pop     rdi
0x1800169ed  pop     rbx
0x1800169ee  pop     rbp
0x1800169ef  retn
```
