# UnregisterSystemToast(unsigned __int64)

- ea: `0x180016bc0`
- end: `0x180016d0f`
- name: `?UnregisterSystemToast@@YAJ_K@Z`
- size: `335`
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
- `0x180016bc0`
- `0x18001d010`

## import_xrefs

- `combase!__imp_CoCreateInstanceAsUser` at `0x180016c06`
- `combase!__imp_CoCreateInstanceAsUser` at `0x180016c06`

## string_xrefs

- `0x180016c19`: `onecore\base\win32\winnls\tzautoupdate\timezonetoastnotification.cpp`
- `0x180016c67`: `onecore\base\win32\winnls\tzautoupdate\timezonetoastnotification.cpp`
- `0x180016ca4`: `onecore\base\win32\winnls\tzautoupdate\timezonetoastnotification.cpp`

## pseudocode

```c
__int64 __fastcall UnregisterSystemToast(__int64 a1)
{
  int InstanceAsUser; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64 *); // rbx
  int v6; // eax
  int v7; // eax
  __int64 v8; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v11; // [rsp+58h] [rbp+28h] BYREF
  __int64 v12; // [rsp+60h] [rbp+30h] BYREF
  __int64 v13; // [rsp+68h] [rbp+38h] BYREF

  v13 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v13);
  InstanceAsUser = CoCreateInstanceAsUser(&GUID_0c9281f9_6da1_4006_8729_de6e6b61581c, 0, 1048580, a1);
  v3 = InstanceAsUser;
  if ( InstanceAsUser >= 0 )
  {
    v11 = 0;
    v4 = v13;
    v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 40LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
    v6 = v5(v4, &v11);
    v3 = v6;
    if ( v6 >= 0 )
    {
      v12 = 0;
      v7 = Microsoft::WRL::ComPtr<IWpnRegistrationEndpoint>::As<IWpnSystemRegistrationEndpoint>(&v11, &v12);
      v3 = v7;
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v12 + 32LL))(
               v12,
               L"Windows.SystemToast.TimeZoneChange");
        v3 = v7;
        if ( v7 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
          v3 = 0;
          goto LABEL_12;
        }
        v8 = 84;
      }
      else
      {
        v8 = 82;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\timezonetoastnotification.cpp",
        (const char *)(unsigned int)v7,
        (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\timezonetoastnotification.cpp",
        (const char *)(unsigned int)v6,
        (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\timezonetoastnotification.cpp",
      (const char *)(unsigned int)InstanceAsUser,
      (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
  }
LABEL_12:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v13);
  return v3;
}

```

## disassembly

```asm
0x180016bc0  push    rbp
0x180016bc2  push    rbx
0x180016bc3  push    rdi
0x180016bc4  mov     rbp, rsp
0x180016bc7  sub     rsp, 30h
0x180016bcb  mov     rbx, rcx
0x180016bce  mov     [rbp+arg_18], 0
0x180016bd6  lea     rcx, [rbp+arg_18]
0x180016bda  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016bdf  lea     rax, [rbp+arg_18]
0x180016be3  mov     [rsp+30h+var_8], rax
0x180016be8  lea     rax, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x180016bef  mov     qword ptr [rsp+30h+var_10], rax; int
0x180016bf4  mov     r9, rbx
0x180016bf7  xor     edx, edx
0x180016bf9  mov     r8d, 100004h
0x180016bff  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x180016c06  call    cs:__imp_CoCreateInstanceAsUser
0x180016c0c  mov     ebx, eax
0x180016c0e  test    eax, eax
0x180016c10  jns     short loc_180016C2F
0x180016c12  mov     rcx, [rbp+18h]; this
0x180016c16  mov     r9d, eax; char *
0x180016c19  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x180016c20  mov     edx, 4Ch ; 'L'; void *
0x180016c25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c2a  jmp     loc_180016CFC
0x180016c2f  mov     [rbp+arg_8], 0
0x180016c37  mov     rdi, [rbp+arg_18]
0x180016c3b  mov     rax, [rdi]
0x180016c3e  mov     rbx, [rax+28h]
0x180016c42  lea     rcx, [rbp+arg_8]
0x180016c46  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016c4b  lea     rdx, [rbp+arg_8]
0x180016c4f  mov     rcx, rdi
0x180016c52  mov     rax, rbx
0x180016c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c5a  mov     ebx, eax
0x180016c5c  test    eax, eax
0x180016c5e  jns     short loc_180016C84
0x180016c60  mov     rcx, [rbp+18h]; this
0x180016c64  mov     r9d, eax; char *
0x180016c67  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x180016c6e  mov     edx, 4Fh ; 'O'; void *
0x180016c73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c78  nop
0x180016c79  lea     rcx, [rbp+arg_8]
0x180016c7d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016c82  jmp     short loc_180016CFC
0x180016c84  mov     [rbp+arg_10], 0
0x180016c8c  lea     rdx, [rbp+arg_10]
0x180016c90  lea     rcx, [rbp+arg_8]
0x180016c94  call    ??$As@UIWpnSystemRegistrationEndpoint@@@?$ComPtr@UIWpnRegistrationEndpoint@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWpnSystemRegistrationEndpoint@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IWpnRegistrationEndpoint>::As<IWpnSystemRegistrationEndpoint>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnSystemRegistrationEndpoint>>)
0x180016c99  mov     ebx, eax
0x180016c9b  test    eax, eax
0x180016c9d  jns     short loc_180016CC3
0x180016c9f  mov     edx, 52h ; 'R'; void *
0x180016ca4  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x180016cab  mov     r9d, eax; char *
0x180016cae  mov     rcx, [rbp+18h]; this
0x180016cb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016cb7  nop
0x180016cb8  lea     rcx, [rbp+arg_10]
0x180016cbc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016cc1  jmp     short loc_180016C79
0x180016cc3  mov     rcx, [rbp+arg_10]
0x180016cc7  mov     rax, [rcx]
0x180016cca  lea     rdx, aWindowsSystemt; "Windows.SystemToast.TimeZoneChange"
0x180016cd1  mov     rax, [rax+20h]
0x180016cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cda  mov     ebx, eax
0x180016cdc  test    eax, eax
0x180016cde  jns     short loc_180016CE7
0x180016ce0  mov     edx, 54h ; 'T'
0x180016ce5  jmp     short loc_180016CA4
0x180016ce7  lea     rcx, [rbp+arg_10]
0x180016ceb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016cf0  nop
0x180016cf1  lea     rcx, [rbp+arg_8]
0x180016cf5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016cfa  xor     ebx, ebx
0x180016cfc  lea     rcx, [rbp+arg_18]
0x180016d00  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016d05  mov     eax, ebx
0x180016d07  add     rsp, 30h
0x180016d0b  pop     rdi
0x180016d0c  pop     rbx
0x180016d0d  pop     rbp
0x180016d0e  retn
```
