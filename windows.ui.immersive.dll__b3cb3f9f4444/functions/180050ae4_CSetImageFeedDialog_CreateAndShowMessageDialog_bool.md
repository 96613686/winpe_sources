# CSetImageFeedDialog::CreateAndShowMessageDialog(bool *)

- ea: `0x180050ae4`
- end: `0x180050fb7`
- name: `?CreateAndShowMessageDialog@CSetImageFeedDialog@@QEAAJPEA_N@Z`
- size: `1235`
- prototype: `__int64 __fastcall(CSetImageFeedDialog *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800d68d0`

## callees

- `0x18000af00`
- `0x18002bd44`
- `0x1800343ec`
- `0x18003729c`
- `0x18003d244`
- `0x18003ff34`
- `0x180040690`
- `0x180050ae4`
- `0x180050fc0`
- `0x180050fec`
- `0x180054130`
- `0x1800d4efc`
- `0x1800d546c`
- `0x1800d576c`
- `0x1800d6368`
- `0x1800d63d4`
- `0x1800d643c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180050c08`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180050d71`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180050c08`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180050d71`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180050e5f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180050e5f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180050eac`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180050eac`
- `USER32!GetWindowThreadProcessId` at `0x180050e48`
- `USER32!GetWindowThreadProcessId` at `0x180050e48`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSetImageFeedDialog::CreateAndShowMessageDialog(CSetImageFeedDialog *this, bool *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rbx
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  __int64 *v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  __int64 *v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  HANDLE v16; // rbx
  PVOID v17; // rdi
  enum tagCOWAIT_FLAGS v18; // edx
  int Error; // eax
  __int64 v20; // rdx
  __int64 v21; // r9
  int v22; // ecx
  ULONG dwMilliseconds; // [rsp+20h] [rbp-E0h]
  ULONG dwMillisecondsa; // [rsp+20h] [rbp-E0h]
  char v26[8]; // [rsp+30h] [rbp-D0h] BYREF
  PVOID Context; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h]
  __int64 v30; // [rsp+50h] [rbp-B0h]
  void *phNewWaitObject; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v32; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  DWORD dwProcessId; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v37[3]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  if ( a2 )
    *a2 = 0;
  Context = 0;
  v26[0] = 1;
  LODWORD(v32) = 1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Context);
  v4 = Microsoft::WRL::Details::MakeAndInitialize<CMessageDialogHelper,CMessageDialogHelper,HWND__ * &,enum CMessageDialogHelper::ActivationType,bool>(
         &Context,
         (char *)this + 48,
         &v32,
         v26);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v6 = *((_QWORD *)this + 7);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v28);
    v29 = -1;
    v30 = -1;
    v7 = ResourceStringCoAllocFormatMessage(&_ImageBase, *((unsigned int *)this + 8), &v28, v6);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
        (const char *)(unsigned int)v7,
        dwMilliseconds);
    if ( *((_DWORD *)this + 8) == 38326 )
    {
      if ( LoadStringW(&_ImageBase, 0x95B7u, Buffer, 260) <= 0 )
      {
        v8 = 201;
LABEL_10:
        v5 = -2147467259;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
          (const char *)0x80004005LL,
          dwMilliseconds);
LABEL_11:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v28);
        goto LABEL_50;
      }
      memset(v37, 0, sizeof(v37));
      v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
             v37,
             &_ImageBase,
             38329);
      v5 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCD,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
          (const char *)(unsigned int)v9,
          dwMilliseconds);
LABEL_14:
        v10 = v37;
LABEL_15:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v10);
        goto LABEL_11;
      }
      v33 = 0;
      v34 = 0;
      v35 = 0;
      v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
              &v33,
              &_ImageBase,
              38330);
      v5 = v11;
      if ( v11 < 0 )
      {
        v12 = 207;
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
          (const char *)(unsigned int)v11,
          dwMilliseconds);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
        goto LABEL_14;
      }
      v11 = CMessageDialogHelper::SetTitle((CMessageDialogHelper *)Context, v28);
      v5 = v11;
      if ( v11 < 0 )
      {
        v12 = 209;
        goto LABEL_18;
      }
      v11 = CMessageDialogHelper::SetContent((CMessageDialogHelper *)Context, Buffer);
      v5 = v11;
      if ( v11 < 0 )
      {
        v12 = 210;
        goto LABEL_18;
      }
      v11 = CMessageDialogHelper::AddButton(Context, 38329, v37[0], 0);
      v5 = v11;
      if ( v11 < 0 )
      {
        v12 = 213;
        goto LABEL_18;
      }
      v11 = CMessageDialogHelper::AddButton(Context, 38330, v33, 1);
      v5 = v11;
      if ( v11 < 0 )
      {
        v12 = 214;
        goto LABEL_18;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
      v13 = v37;
LABEL_40:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v13);
      dwProcessId = 0;
      GetWindowThreadProcessId(*((HWND *)this + 6), &dwProcessId);
      v16 = OpenProcess(0x100000u, 0, dwProcessId);
      v32 = v16;
      phNewWaitObject = 0;
      v17 = Context;
      wil::details::unique_storage_wil::details::handle_null_resource_policy_void____cdecl___void______anonymous_namespace_::UnregisterProcessExitWait___::reset(
        &phNewWaitObject,
        0);
      if ( RegisterWaitForSingleObject(
             &phNewWaitObject,
             v16,
             lambda_64d41ede1ce24ee49d935c7f611bcae6_::_lambda_invoker_cdecl_,
             v17,
             0xFFFFFFFF,
             8u)
        || (Error = ResultFromKnownLastError(), v5 = Error, Error >= 0) )
      {
        Error = CMessageDialogHelper::ShowMessageDialogAndWait((CMessageDialogHelper *)Context, v18);
        v5 = Error;
        if ( Error >= 0 )
        {
          wil::details::unique_storage_wil::details::handle_null_resource_policy_void____cdecl___void______anonymous_namespace_::UnregisterProcessExitWait___::reset(
            &phNewWaitObject,
            0);
          v22 = *((_DWORD *)Context + 20);
          switch ( v22 )
          {
            case 38329:
              *a2 = 1;
              break;
            case 38330:
              *a2 = 0;
              break;
            case -1:
            case 38337:
              break;
            default:
              v5 = -2147418113;
              v21 = 2147549183LL;
              v20 = 265;
              goto LABEL_44;
          }
          wil::details::unique_storage_wil::details::handle_null_resource_policy_void____cdecl___void______anonymous_namespace_::UnregisterProcessExitWait___::_unique_storage_wil::details::handle_null_resource_policy_void____cdecl___void______anonymous_namespace_::UnregisterProcessExitWait___(&phNewWaitObject);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v32);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v28);
          v5 = 0;
          goto LABEL_50;
        }
        v20 = 247;
      }
      else
      {
        v20 = 245;
      }
      v21 = (unsigned int)Error;
LABEL_44:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
        (const char *)v21,
        dwMillisecondsa);
      wil::details::unique_storage_wil::details::handle_null_resource_policy_void____cdecl___void______anonymous_namespace_::UnregisterProcessExitWait___::_unique_storage_wil::details::handle_null_resource_policy_void____cdecl___void______anonymous_namespace_::UnregisterProcessExitWait___(&phNewWaitObject);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v32);
      goto LABEL_11;
    }
    if ( LoadStringW(&_ImageBase, *((_DWORD *)this + 9), Buffer, 260) <= 0 )
    {
      v8 = 218;
      goto LABEL_10;
    }
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
            &v33,
            &_ImageBase,
            38337);
    v5 = v14;
    if ( v14 >= 0 )
    {
      v14 = CMessageDialogHelper::SetTitle((CMessageDialogHelper *)Context, v28);
      v5 = v14;
      if ( v14 >= 0 )
      {
        v14 = CMessageDialogHelper::SetContent((CMessageDialogHelper *)Context, Buffer);
        v5 = v14;
        if ( v14 >= 0 )
        {
          v14 = CMessageDialogHelper::AddButton(Context, 38337, v33, 1);
          v5 = v14;
          if ( v14 >= 0 )
          {
            v13 = &v33;
            goto LABEL_40;
          }
          v15 = 227;
        }
        else
        {
          v15 = 225;
        }
      }
      else
      {
        v15 = 224;
      }
    }
    else
    {
      v15 = 222;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
      (const char *)(unsigned int)v14,
      dwMilliseconds);
    v10 = &v33;
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC0,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
    (const char *)(unsigned int)v4,
    dwMilliseconds);
LABEL_50:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Context);
  return v5;
}

```

## disassembly

```asm
0x180050ae4  mov     [rsp-8+arg_10], rbx
0x180050ae9  push    rbp
0x180050aea  push    rsi
0x180050aeb  push    rdi
0x180050aec  push    r12
0x180050aee  push    r13
0x180050af0  push    r14
0x180050af2  push    r15
0x180050af4  lea     rbp, [rsp-1C0h]
0x180050afc  sub     rsp, 2C0h
0x180050b03  mov     rax, cs:__security_cookie
0x180050b0a  xor     rax, rsp
0x180050b0d  mov     [rbp+1F0h+var_40], rax
0x180050b14  mov     r14, rdx
0x180050b17  mov     rdi, rcx
0x180050b1a  xor     r12d, r12d
0x180050b1d  test    rdx, rdx
0x180050b20  jz      short loc_180050B25
0x180050b22  mov     [rdx], r12b
0x180050b25  mov     [rsp+2F0h+Context], r12
0x180050b2a  mov     [rsp+2F0h+var_2C0], 1
0x180050b2f  mov     dword ptr [rsp+2F0h+var_290], 1
0x180050b37  lea     rcx, [rsp+2F0h+Context]
0x180050b3c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050b41  lea     r15, [rdi+30h]
0x180050b45  lea     r9, [rsp+2F0h+var_2C0]
0x180050b4a  lea     r8, [rsp+2F0h+var_290]
0x180050b4f  mov     rdx, r15
0x180050b52  lea     rcx, [rsp+2F0h+Context]
0x180050b57  call    ??$MakeAndInitialize@VCMessageDialogHelper@@V1@AEAPEAUHWND__@@W4ActivationType@1@_N@Details@WRL@Microsoft@@YAJPEAPEAVCMessageDialogHelper@@AEAPEAUHWND__@@$$QEAW4ActivationType@3@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<CMessageDialogHelper,CMessageDialogHelper,HWND__ * &,CMessageDialogHelper::ActivationType,bool>(CMessageDialogHelper * *,HWND__ * &,CMessageDialogHelper::ActivationType &&,bool &&)
0x180050b5c  mov     ebx, eax
0x180050b5e  test    eax, eax
0x180050b60  jns     short loc_180050B82
0x180050b62  mov     rcx, [rbp+1F8h]; this
0x180050b69  mov     r9d, eax; char *
0x180050b6c  lea     r8, aShellWindowsui_1; "shell\\windowsuiimmersive\\userinfo\\se"...
0x180050b73  mov     edx, 0C0h; void *
0x180050b78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050b7d  jmp     loc_180050F53
0x180050b82  mov     [rsp+2F0h+var_2B0], r12
0x180050b87  mov     [rsp+2F0h+var_2A8], r12
0x180050b8c  mov     [rsp+2F0h+var_2A0], r12
0x180050b91  mov     rbx, [rdi+38h]
0x180050b95  lea     rcx, [rsp+2F0h+var_2B0]
0x180050b9a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180050b9f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180050ba3  mov     [rsp+2F0h+var_2A8], rax
0x180050ba8  mov     [rsp+2F0h+var_2A0], rax
0x180050bad  mov     r9, rbx
0x180050bb0  lea     r8, [rsp+2F0h+var_2B0]
0x180050bb5  mov     edx, [rdi+20h]
0x180050bb8  lea     r13, __ImageBase
0x180050bbf  mov     rcx, r13
0x180050bc2  call    ResourceStringCoAllocFormatMessage
0x180050bc7  mov     rcx, [rbp+1F8h]; this
0x180050bce  lea     rsi, aShellWindowsui_1; "shell\\windowsuiimmersive\\userinfo\\se"...
0x180050bd5  test    eax, eax
0x180050bd7  jns     short loc_180050BE9
0x180050bd9  mov     r9d, eax; char *
0x180050bdc  mov     r8, rsi; unsigned int
0x180050bdf  mov     edx, 0C3h; void *
0x180050be4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050be9  mov     r9d, 104h; cchBufferMax
0x180050bef  lea     r8, [rbp+1F0h+Buffer]; lpBuffer
0x180050bf3  mov     rcx, r13; hInstance
0x180050bf6  cmp     dword ptr [rdi+20h], 95B6h
0x180050bfd  jnz     loc_180050D6E
0x180050c03  mov     edx, 95B7h; uID
0x180050c08  call    cs:__imp_LoadStringW
0x180050c0f  nop     dword ptr [rax+rax+00h]
0x180050c14  test    eax, eax
0x180050c16  jg      short loc_180050C44
0x180050c18  mov     edx, 0C9h; void *
0x180050c1d  mov     ebx, 80004005h
0x180050c22  mov     r8, rsi; unsigned int
0x180050c25  mov     r9d, ebx; char *
0x180050c28  mov     rcx, [rbp+1F8h]; this
0x180050c2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050c34  nop
0x180050c35  lea     rcx, [rsp+2F0h+var_2B0]
0x180050c3a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180050c3f  jmp     loc_180050F53
0x180050c44  mov     [rbp+1F0h+var_268], r12
0x180050c48  mov     [rbp+1F0h+var_260], r12
0x180050c4c  mov     [rbp+1F0h+var_258], r12
0x180050c50  mov     r8d, 95B9h
0x180050c56  mov     rdx, r13
0x180050c59  lea     rcx, [rbp+1F0h+var_268]
0x180050c5d  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x180050c62  mov     ebx, eax
0x180050c64  test    eax, eax
0x180050c66  jns     short loc_180050C8B
0x180050c68  mov     rcx, [rbp+1F8h]; this
0x180050c6f  mov     r9d, eax; char *
0x180050c72  mov     r8, rsi; unsigned int
0x180050c75  mov     edx, 0CDh; void *
0x180050c7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050c7f  nop
0x180050c80  lea     rcx, [rbp+1F0h+var_268]
0x180050c84  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180050c89  jmp     short loc_180050C35
0x180050c8b  mov     [rsp+2F0h+var_288], r12
0x180050c90  mov     [rsp+2F0h+var_280], r12
0x180050c95  mov     [rsp+2F0h+var_278], r12
0x180050c9a  mov     edi, 95BAh
0x180050c9f  mov     r8d, edi
0x180050ca2  mov     rdx, r13
0x180050ca5  lea     rcx, [rsp+2F0h+var_288]
0x180050caa  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x180050caf  mov     ebx, eax
0x180050cb1  test    eax, eax
0x180050cb3  jns     short loc_180050CD9
0x180050cb5  mov     edx, 0CFh; void *
0x180050cba  mov     rcx, [rbp+1F8h]; this
0x180050cc1  mov     r9d, eax; char *
0x180050cc4  mov     r8, rsi; unsigned int
0x180050cc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050ccc  nop
0x180050ccd  lea     rcx, [rsp+2F0h+var_288]
0x180050cd2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180050cd7  jmp     short loc_180050C80
0x180050cd9  mov     rdx, [rsp+2F0h+var_2B0]; unsigned __int16 *
0x180050cde  mov     rcx, [rsp+2F0h+Context]; this
0x180050ce3  call    ?SetTitle@CMessageDialogHelper@@QEAAJPEBG@Z; CMessageDialogHelper::SetTitle(ushort const *)
0x180050ce8  mov     ebx, eax
0x180050cea  test    eax, eax
0x180050cec  jns     short loc_180050CF5
0x180050cee  mov     edx, 0D1h
0x180050cf3  jmp     short loc_180050CBA
0x180050cf5  lea     rdx, [rbp+1F0h+Buffer]; unsigned __int16 *
0x180050cf9  mov     rcx, [rsp+2F0h+Context]; this
0x180050cfe  call    ?SetContent@CMessageDialogHelper@@QEAAJPEBG@Z; CMessageDialogHelper::SetContent(ushort const *)
0x180050d03  mov     ebx, eax
0x180050d05  test    eax, eax
0x180050d07  jns     short loc_180050D10
0x180050d09  mov     edx, 0D2h
0x180050d0e  jmp     short loc_180050CBA
0x180050d10  xor     r9d, r9d
0x180050d13  mov     r8, [rbp+1F0h+var_268]
0x180050d17  mov     edx, 95B9h
0x180050d1c  mov     rcx, [rsp+2F0h+Context]
0x180050d21  call    ?AddButton@CMessageDialogHelper@@QEAAJIPEBGW4MessageDialogButtonOptions@@@Z; CMessageDialogHelper::AddButton(uint,ushort const *,MessageDialogButtonOptions)
0x180050d26  mov     ebx, eax
0x180050d28  test    eax, eax
0x180050d2a  jns     short loc_180050D33
0x180050d2c  mov     edx, 0D5h
0x180050d31  jmp     short loc_180050CBA
0x180050d33  mov     r9d, 1
0x180050d39  mov     r8, [rsp+2F0h+var_288]
0x180050d3e  mov     edx, edi
0x180050d40  mov     rcx, [rsp+2F0h+Context]
0x180050d45  call    ?AddButton@CMessageDialogHelper@@QEAAJIPEBGW4MessageDialogButtonOptions@@@Z; CMessageDialogHelper::AddButton(uint,ushort const *,MessageDialogButtonOptions)
0x180050d4a  mov     ebx, eax
0x180050d4c  test    eax, eax
0x180050d4e  jns     short loc_180050D5A
0x180050d50  mov     edx, 0D6h
0x180050d55  jmp     loc_180050CBA
0x180050d5a  lea     rcx, [rsp+2F0h+var_288]
0x180050d5f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180050d64  nop
0x180050d65  lea     rcx, [rbp+1F0h+var_268]
0x180050d69  jmp     loc_180050E38
0x180050d6e  mov     edx, [rdi+24h]; uID
0x180050d71  call    cs:__imp_LoadStringW
0x180050d78  nop     dword ptr [rax+rax+00h]
0x180050d7d  test    eax, eax
0x180050d7f  jg      short loc_180050D8B
0x180050d81  mov     edx, 0DAh
0x180050d86  jmp     loc_180050C1D
0x180050d8b  mov     [rsp+2F0h+var_288], r12
0x180050d90  mov     [rsp+2F0h+var_280], r12
0x180050d95  mov     [rsp+2F0h+var_278], r12
0x180050d9a  mov     r8d, 95C1h
0x180050da0  mov     rdx, r13
0x180050da3  lea     rcx, [rsp+2F0h+var_288]
0x180050da8  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x180050dad  mov     ebx, eax
0x180050daf  test    eax, eax
0x180050db1  jns     short loc_180050DD5
0x180050db3  mov     edx, 0DEh; void *
0x180050db8  mov     r8, rsi; unsigned int
0x180050dbb  mov     r9d, eax; char *
0x180050dbe  mov     rcx, [rbp+1F8h]; this
0x180050dc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050dca  nop
0x180050dcb  lea     rcx, [rsp+2F0h+var_288]
0x180050dd0  jmp     loc_180050C84
0x180050dd5  mov     rdx, [rsp+2F0h+var_2B0]; unsigned __int16 *
0x180050dda  mov     rcx, [rsp+2F0h+Context]; this
0x180050ddf  call    ?SetTitle@CMessageDialogHelper@@QEAAJPEBG@Z; CMessageDialogHelper::SetTitle(ushort const *)
0x180050de4  mov     ebx, eax
0x180050de6  test    eax, eax
0x180050de8  jns     short loc_180050DF1
0x180050dea  mov     edx, 0E0h
0x180050def  jmp     short loc_180050DB8
0x180050df1  lea     rdx, [rbp+1F0h+Buffer]; unsigned __int16 *
0x180050df5  mov     rcx, [rsp+2F0h+Context]; this
0x180050dfa  call    ?SetContent@CMessageDialogHelper@@QEAAJPEBG@Z; CMessageDialogHelper::SetContent(ushort const *)
0x180050dff  mov     ebx, eax
0x180050e01  test    eax, eax
0x180050e03  jns     short loc_180050E0C
0x180050e05  mov     edx, 0E1h
0x180050e0a  jmp     short loc_180050DB8
0x180050e0c  mov     r9d, 1
0x180050e12  mov     r8, [rsp+2F0h+var_288]
0x180050e17  mov     edx, 95C1h
0x180050e1c  mov     rcx, [rsp+2F0h+Context]
0x180050e21  call    ?AddButton@CMessageDialogHelper@@QEAAJIPEBGW4MessageDialogButtonOptions@@@Z; CMessageDialogHelper::AddButton(uint,ushort const *,MessageDialogButtonOptions)
0x180050e26  mov     ebx, eax
0x180050e28  test    eax, eax
0x180050e2a  jns     short loc_180050E33
0x180050e2c  mov     edx, 0E3h
0x180050e31  jmp     short loc_180050DB8
0x180050e33  lea     rcx, [rsp+2F0h+var_288]
0x180050e38  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180050e3d  mov     [rbp+1F0h+dwProcessId], r12d
0x180050e41  lea     rdx, [rbp+1F0h+dwProcessId]; lpdwProcessId
0x180050e45  mov     rcx, [r15]; hWnd
0x180050e48  call    cs:__imp_GetWindowThreadProcessId
0x180050e4f  nop     dword ptr [rax+rax+00h]
0x180050e54  mov     r8d, [rbp+1F0h+dwProcessId]; dwProcessId
0x180050e58  xor     edx, edx; bInheritHandle
0x180050e5a  mov     ecx, 100000h; dwDesiredAccess
0x180050e5f  call    cs:__imp_OpenProcess
0x180050e66  nop     dword ptr [rax+rax+00h]
0x180050e6b  mov     rbx, rax
0x180050e6e  mov     [rsp+2F0h+var_290], rax
0x180050e73  mov     [rsp+2F0h+phNewWaitObject], r12
0x180050e78  mov     rdi, [rsp+2F0h+Context]
0x180050e7d  xor     edx, edx
0x180050e7f  lea     rcx, [rsp+2F0h+phNewWaitObject]
0x180050e84  call    wil__details__unique_storage_wil__details__handle_null_resource_policy_void____cdecl___void______anonymous_namespace___UnregisterProcessExitWait_____reset
0x180050e89  mov     [rsp+2F0h+dwFlags], 8; dwFlags
0x180050e91  or      r15d, 0FFFFFFFFh
0x180050e95  mov     [rsp+2F0h+dwMilliseconds], r15d; int
0x180050e9a  mov     r9, rdi; Context
0x180050e9d  lea     r8, _lambda_64d41ede1ce24ee49d935c7f611bcae6____lambda_invoker_cdecl_; Callback
0x180050ea4  mov     rdx, rbx; hObject
0x180050ea7  lea     rcx, [rsp+2F0h+phNewWaitObject]; phNewWaitObject
0x180050eac  call    cs:__imp_RegisterWaitForSingleObject
0x180050eb3  nop     dword ptr [rax+rax+00h]
0x180050eb8  test    eax, eax
0x180050eba  jnz     short loc_180050EF9
0x180050ebc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180050ec1  mov     ebx, eax
0x180050ec3  test    eax, eax
0x180050ec5  jns     short loc_180050EF9
0x180050ec7  mov     edx, 0F5h; void *
0x180050ecc  mov     r9d, eax; char *
0x180050ecf  mov     rcx, [rbp+1F8h]; this
0x180050ed6  mov     r8, rsi; unsigned int
0x180050ed9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050ede  nop
0x180050edf  lea     rcx, [rsp+2F0h+phNewWaitObject]
0x180050ee4  call    wil__details__unique_storage_wil__details__handle_null_resource_policy_void____cdecl___void______anonymous_namespace___UnregisterProcessExitWait______unique_storage_wil__details__handle_null_resource_policy_void____cdecl___void______anonymous_namespace___UnregisterProcessExitWait___
0x180050ee9  nop
0x180050eea  lea     rcx, [rsp+2F0h+var_290]
0x180050eef  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180050ef4  jmp     loc_180050C35
0x180050ef9  mov     rcx, [rsp+2F0h+Context]; this
0x180050efe  call    ?ShowMessageDialogAndWait@CMessageDialogHelper@@QEAAJW4tagCOWAIT_FLAGS@@@Z; CMessageDialogHelper::ShowMessageDialogAndWait(tagCOWAIT_FLAGS)
0x180050f03  mov     ebx, eax
0x180050f05  test    eax, eax
0x180050f07  jns     short loc_180050F10
0x180050f09  mov     edx, 0F7h
0x180050f0e  jmp     short loc_180050ECC
0x180050f10  xor     edx, edx
0x180050f12  lea     rcx, [rsp+2F0h+phNewWaitObject]
0x180050f17  call    wil__details__unique_storage_wil__details__handle_null_resource_policy_void____cdecl___void______anonymous_namespace___UnregisterProcessExitWait_____reset
0x180050f1c  mov     rax, [rsp+2F0h+Context]
0x180050f21  mov     ecx, [rax+50h]
0x180050f24  cmp     ecx, 95B9h
0x180050f2a  jnz     short loc_180050F8A
0x180050f2c  mov     byte ptr [r14], 1
0x180050f30  lea     rcx, [rsp+2F0h+phNewWaitObject]
0x180050f35  call    wil__details__unique_storage_wil__details__handle_null_resource_policy_void____cdecl___void______anonymous_namespace___UnregisterProcessExitWait______unique_storage_wil__details__handle_null_resource_policy_void____cdecl___void______anonymous_namespace___UnregisterProcessExitWait___
0x180050f3a  nop
0x180050f3b  lea     rcx, [rsp+2F0h+var_290]
0x180050f40  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180050f45  nop
0x180050f46  lea     rcx, [rsp+2F0h+var_2B0]
0x180050f4b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180050f50  mov     ebx, r12d
0x180050f53  lea     rcx, [rsp+2F0h+Context]
0x180050f58  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050f5d  mov     eax, ebx
0x180050f5f  mov     rcx, [rbp+1F0h+var_40]
0x180050f66  xor     rcx, rsp; StackCookie
0x180050f69  call    __security_check_cookie
0x180050f6e  mov     rbx, [rsp+2F0h+arg_10]
0x180050f76  add     rsp, 2C0h
0x180050f7d  pop     r15
0x180050f7f  pop     r14
0x180050f81  pop     r13
0x180050f83  pop     r12
0x180050f85  pop     rdi
0x180050f86  pop     rsi
0x180050f87  pop     rbp
0x180050f88  retn
0x180050f8a  cmp     ecx, 95BAh
  ... truncated ...
```
