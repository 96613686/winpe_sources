# AssociationLaunchExecuteCommandBase::GetSerializedPropertySetForActivationFromShellItemArray(HSTRING__ *,Windows::Storage::Streams::IBuffer * *)

- ea: `0x1800f09e0`
- end: `0x1800f0e07`
- name: `?GetSerializedPropertySetForActivationFromShellItemArray@AssociationLaunchExecuteCommandBase@@EEAAJPEAUHSTRING__@@PEAPEAUIBuffer@Streams@Storage@Windows@@@Z`
- size: `1063`
- prototype: `int(AssociationLaunchExecuteCommandBase *__hidden this, HSTRING, struct Windows::Storage::Streams::IBuffer **)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180026ea4`
- `0x180027108`
- `0x18002cec0`
- `0x180041eb4`
- `0x1800603f0`
- `0x180074e7c`
- `0x18008a030`
- `0x1800f09e0`
- `0x1800f1ad0`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f0bec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f0c39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f0da4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f0bec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f0c39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f0da4`

## string_xrefs

- `0x1800f0a39`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x1800f0a8b`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x1800f0ac8`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x1800f0b23`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x1800f0bd0`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x1800f0b41`: `LauncherPluginActivationType`
- `0x1800f0ca0`: `RawURI`

## pseudocode

```c
__int64 __fastcall AssociationLaunchExecuteCommandBase::GetSerializedPropertySetForActivationFromShellItemArray(
        AssociationLaunchExecuteCommandBase *this,
        const unsigned __int16 *a2,
        struct Windows::Storage::Streams::IBuffer **a3)
{
  HSTRING *v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdx
  _QWORD *v15; // rsi
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 (__fastcall *v18)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, struct IShellItem **); // rbx
  int v21; // eax
  __int64 v22; // rdx
  struct Windows::Foundation::IUriRuntimeClass *v23; // rdi
  __int64 (__fastcall *v24)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING, __int64 *); // rbx
  _QWORD *v27; // rsi
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 (__fastcall *v30)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, const unsigned __int16 *, __int64 *); // rbx
  _QWORD *v33; // rsi
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 (__fastcall *v36)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  AssociationLaunchExecuteCommandBase *v37; // rcx
  int v39; // [rsp+20h] [rbp-59h]
  _BYTE v40[8]; // [rsp+30h] [rbp-49h] BYREF
  HSTRING string; // [rsp+38h] [rbp-41h] BYREF
  __int64 v42; // [rsp+40h] [rbp-39h] BYREF
  _QWORD *v43; // [rsp+48h] [rbp-31h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v44; // [rsp+50h] [rbp-29h] BYREF
  struct IShellItem *v45; // [rsp+58h] [rbp-21h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v46; // [rsp+60h] [rbp-19h] BYREF
  __int64 v47; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  __int64 v49; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v47 = 0;
  v6 = Windows::Internal::StringReference::StringReference(
         (HSTRING *)&hstringHeader,
         (const unsigned __int16 (*)[33])a2);
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
         *v6,
         &v47);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v44 = 0;
    v49 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.Collections.ValueSet",
      0x28u,
      0x27u);
    v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
           v49,
           &v44);
    v8 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
        (const char *)(unsigned int)v9,
        v39);
LABEL_5:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      goto LABEL_33;
    }
    v43 = 0;
    v10 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v44,
            (__int64)&v43);
    v8 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x171,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
        (const char *)(unsigned int)v10,
        v39);
LABEL_8:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      goto LABEL_5;
    }
    v11 = v47;
    v40[0] = 0;
    v42 = 0;
    v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v47 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    v13 = v12(v11, 0, &v42);
    v8 = v13;
    if ( v13 >= 0 )
    {
      v15 = v43;
      v16 = v42;
      v17 = *v43;
      v49 = 0;
      v18 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v17 + 80);
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"LauncherPluginActivationType",
        0x1Du,
        0x1Cu);
      v13 = v18(v15, v49, v16, v40);
      v8 = v13;
      if ( v13 >= 0 )
      {
        v19 = *((_QWORD *)this + 20);
        v46 = 0;
        string = 0;
        v45 = 0;
        v20 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IShellItem **))(*(_QWORD *)v19 + 64LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        v21 = v20(v19, 0, &v45);
        v8 = v21;
        if ( v21 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
          v21 = CreateUriRuntimeClassFromShellItem(v45, &v46);
          v8 = v21;
          if ( v21 >= 0 )
          {
            v23 = v46;
            v24 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)v46 + 128LL);
            WindowsDeleteString(string);
            string = 0;
            v21 = v24(v23, &string);
            v8 = v21;
            if ( v21 >= 0 )
            {
              v25 = v47;
              v26 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v47 + 144LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
              v21 = v26(v25, string, &v42);
              v8 = v21;
              if ( v21 >= 0 )
              {
                v27 = v43;
                v28 = v42;
                v29 = *v43;
                v49 = 0;
                v30 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v29 + 80);
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"RawURI", 7u, 6u);
                v21 = v30(v27, v49, v28, v40);
                v8 = v21;
                if ( v21 >= 0 )
                {
                  v31 = v47;
                  v32 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v47 + 144LL);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                  v21 = v32(v31, a2, &v42);
                  v8 = v21;
                  if ( v21 >= 0 )
                  {
                    v33 = v43;
                    v34 = v42;
                    v35 = *v43;
                    v49 = 0;
                    v36 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v35 + 80);
                    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                      &hstringHeader,
                      L"CallerPackageFamilyName",
                      0x18u,
                      0x17u);
                    v21 = v36(v33, v49, v34, v40);
                    v8 = v21;
                    if ( v21 >= 0 )
                    {
                      v21 = AssociationLaunchExecuteCommandBase::SerializePropertySet(v37, v44, a3);
                      v8 = v21;
                      if ( v21 >= 0 )
                      {
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                        WindowsDeleteString(string);
                        string = 0;
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                        v8 = 0;
                        goto LABEL_33;
                      }
                      v22 = 387;
                    }
                    else
                    {
                      v22 = 385;
                    }
                  }
                  else
                  {
                    v22 = 384;
                  }
                }
                else
                {
                  v22 = 382;
                }
              }
              else
              {
                v22 = 381;
              }
            }
            else
            {
              v22 = 380;
            }
          }
          else
          {
            v22 = 379;
          }
        }
        else
        {
          v22 = 378;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
          (const char *)(unsigned int)v21,
          v39);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        goto LABEL_12;
      }
      v14 = 373;
    }
    else
    {
      v14 = 372;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
      (const char *)(unsigned int)v13,
      v39);
LABEL_12:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16C,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
    (const char *)(unsigned int)v7,
    v39);
LABEL_33:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  return v8;
}

```

## disassembly

```asm
0x1800f09e0  mov     [rsp-8+arg_18], rbx
0x1800f09e5  push    rbp
0x1800f09e6  push    rsi
0x1800f09e7  push    rdi
0x1800f09e8  push    r12
0x1800f09ea  push    r13
0x1800f09ec  push    r14
0x1800f09ee  push    r15
0x1800f09f0  lea     rbp, [rsp-27h]
0x1800f09f5  sub     rsp, 0A0h
0x1800f09fc  mov     rax, cs:__security_cookie
0x1800f0a03  xor     rax, rsp
0x1800f0a06  mov     [rbp+57h+var_40], rax
0x1800f0a0a  mov     r14, rcx
0x1800f0a0d  xor     r13d, r13d
0x1800f0a10  lea     rcx, [rbp+57h+hstringHeader]; string
0x1800f0a14  mov     [rbp+57h+var_68], r13
0x1800f0a18  mov     r15, r8
0x1800f0a1b  mov     r12, rdx
0x1800f0a1e  call    ??$?0$0CB@@StringReference@Internal@Windows@@QEAA@AEAY0CB@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[33])
0x1800f0a23  lea     rdx, [rbp+57h+var_68]
0x1800f0a27  mov     rcx, [rax]
0x1800f0a2a  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x1800f0a2f  mov     ebx, eax
0x1800f0a31  test    eax, eax
0x1800f0a33  jns     short loc_1800F0A52
0x1800f0a35  mov     rcx, [rbp+5Fh]; this
0x1800f0a39  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x1800f0a40  mov     r9d, eax; char *
0x1800f0a43  mov     edx, 16Ch; void *
0x1800f0a48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0a4d  jmp     loc_1800F0DD5
0x1800f0a52  mov     r9d, 27h ; '''; unsigned int
0x1800f0a58  mov     [rbp+57h+var_80], r13
0x1800f0a5c  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x1800f0a63  mov     [rbp+57h+var_48], r13
0x1800f0a67  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800f0a6b  lea     r8d, [r9+1]; unsigned int
0x1800f0a6f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800f0a74  mov     rcx, [rbp+57h+var_48]
0x1800f0a78  lea     rdx, [rbp+57h+var_80]
0x1800f0a7c  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x1800f0a81  mov     ebx, eax
0x1800f0a83  test    eax, eax
0x1800f0a85  jns     short loc_1800F0AAD
0x1800f0a87  mov     rcx, [rbp+5Fh]; this
0x1800f0a8b  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x1800f0a92  mov     r9d, eax; char *
0x1800f0a95  mov     edx, 16Eh; void *
0x1800f0a9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0a9f  lea     rcx, [rbp+57h+var_80]
0x1800f0aa3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0aa8  jmp     loc_1800F0DD5
0x1800f0aad  lea     rdx, [rbp+57h+var_88]
0x1800f0ab1  mov     [rbp+57h+var_88], r13
0x1800f0ab5  lea     rcx, [rbp+57h+var_80]
0x1800f0ab9  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800f0abe  mov     ebx, eax
0x1800f0ac0  test    eax, eax
0x1800f0ac2  jns     short loc_1800F0AE7
0x1800f0ac4  mov     rcx, [rbp+5Fh]; this
0x1800f0ac8  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x1800f0acf  mov     r9d, eax; char *
0x1800f0ad2  mov     edx, 171h; void *
0x1800f0ad7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0adc  lea     rcx, [rbp+57h+var_88]
0x1800f0ae0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0ae5  jmp     short loc_1800F0A9F
0x1800f0ae7  mov     rdi, [rbp+57h+var_68]
0x1800f0aeb  lea     rcx, [rbp+57h+var_90]
0x1800f0aef  mov     [rbp+57h+var_A0], r13b
0x1800f0af3  mov     [rbp+57h+var_90], r13
0x1800f0af7  mov     rax, [rdi]
0x1800f0afa  mov     rbx, [rax+50h]
0x1800f0afe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0b03  lea     r8, [rbp+57h+var_90]
0x1800f0b07  xor     edx, edx
0x1800f0b09  mov     rcx, rdi
0x1800f0b0c  mov     rax, rbx
0x1800f0b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0b14  mov     ebx, eax
0x1800f0b16  test    eax, eax
0x1800f0b18  jns     short loc_1800F0B3D
0x1800f0b1a  mov     edx, 174h; void *
0x1800f0b1f  mov     rcx, [rbp+5Fh]; this
0x1800f0b23  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x1800f0b2a  mov     r9d, eax; char *
0x1800f0b2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0b32  lea     rcx, [rbp+57h+var_90]
0x1800f0b36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0b3b  jmp     short loc_1800F0ADC
0x1800f0b3d  mov     rsi, [rbp+57h+var_88]
0x1800f0b41  lea     rdx, aLauncherplugin; "LauncherPluginActivationType"
0x1800f0b48  mov     rbx, [rbp+57h+var_90]
0x1800f0b4c  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800f0b50  mov     r9d, 1Ch; unsigned int
0x1800f0b56  mov     rax, [rsi]
0x1800f0b59  mov     [rbp+57h+var_48], r13
0x1800f0b5d  lea     r8d, [r9+1]; unsigned int
0x1800f0b61  mov     rdi, [rax+50h]
0x1800f0b65  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800f0b6a  mov     rdx, [rbp+57h+var_48]
0x1800f0b6e  lea     r9, [rbp+57h+var_A0]
0x1800f0b72  mov     r8, rbx
0x1800f0b75  mov     rcx, rsi
0x1800f0b78  mov     rax, rdi
0x1800f0b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0b80  mov     ebx, eax
0x1800f0b82  test    eax, eax
0x1800f0b84  jns     short loc_1800F0B8D
0x1800f0b86  mov     edx, 175h
0x1800f0b8b  jmp     short loc_1800F0B1F
0x1800f0b8d  mov     rdi, [r14+0A0h]
0x1800f0b94  lea     rcx, [rbp+57h+var_78]
0x1800f0b98  mov     [rbp+57h+var_70], r13
0x1800f0b9c  mov     [rbp+57h+string], r13
0x1800f0ba0  mov     [rbp+57h+var_78], r13
0x1800f0ba4  mov     rax, [rdi]
0x1800f0ba7  mov     rbx, [rax+40h]
0x1800f0bab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0bb0  lea     r8, [rbp+57h+var_78]
0x1800f0bb4  xor     edx, edx
0x1800f0bb6  mov     rcx, rdi
0x1800f0bb9  mov     rax, rbx
0x1800f0bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0bc1  mov     ebx, eax
0x1800f0bc3  test    eax, eax
0x1800f0bc5  jns     short loc_1800F0C04
0x1800f0bc7  mov     edx, 17Ah; void *
0x1800f0bcc  mov     rcx, [rbp+5Fh]; this
0x1800f0bd0  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x1800f0bd7  mov     r9d, eax; char *
0x1800f0bda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0bdf  lea     rcx, [rbp+57h+var_78]
0x1800f0be3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0be8  mov     rcx, [rbp+57h+string]; string
0x1800f0bec  call    cs:__imp_WindowsDeleteString
0x1800f0bf2  lea     rcx, [rbp+57h+var_70]
0x1800f0bf6  mov     [rbp+57h+string], r13
0x1800f0bfa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0bff  jmp     loc_1800F0B32
0x1800f0c04  lea     rcx, [rbp+57h+var_70]
0x1800f0c08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0c0d  mov     rcx, [rbp+57h+var_78]; struct IShellItem *
0x1800f0c11  lea     rdx, [rbp+57h+var_70]; struct Windows::Foundation::IUriRuntimeClass **
0x1800f0c15  call    ?CreateUriRuntimeClassFromShellItem@@YAJPEAUIShellItem@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; CreateUriRuntimeClassFromShellItem(IShellItem *,Windows::Foundation::IUriRuntimeClass * *)
0x1800f0c1a  mov     ebx, eax
0x1800f0c1c  test    eax, eax
0x1800f0c1e  jns     short loc_1800F0C27
0x1800f0c20  mov     edx, 17Bh
0x1800f0c25  jmp     short loc_1800F0BCC
0x1800f0c27  mov     rdi, [rbp+57h+var_70]
0x1800f0c2b  mov     rcx, [rbp+57h+string]; string
0x1800f0c2f  mov     rax, [rdi]
0x1800f0c32  mov     rbx, [rax+80h]
0x1800f0c39  call    cs:__imp_WindowsDeleteString
0x1800f0c3f  lea     rdx, [rbp+57h+string]
0x1800f0c43  mov     [rbp+57h+string], r13
0x1800f0c47  mov     rcx, rdi
0x1800f0c4a  mov     rax, rbx
0x1800f0c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0c52  mov     ebx, eax
0x1800f0c54  test    eax, eax
0x1800f0c56  jns     short loc_1800F0C62
0x1800f0c58  mov     edx, 17Ch
0x1800f0c5d  jmp     loc_1800F0BCC
0x1800f0c62  mov     rdi, [rbp+57h+var_68]
0x1800f0c66  lea     rcx, [rbp+57h+var_90]
0x1800f0c6a  mov     rax, [rdi]
0x1800f0c6d  mov     rbx, [rax+90h]
0x1800f0c74  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0c79  mov     rdx, [rbp+57h+string]
0x1800f0c7d  lea     r8, [rbp+57h+var_90]
0x1800f0c81  mov     rcx, rdi
0x1800f0c84  mov     rax, rbx
0x1800f0c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0c8c  mov     ebx, eax
0x1800f0c8e  test    eax, eax
0x1800f0c90  jns     short loc_1800F0C9C
0x1800f0c92  mov     edx, 17Dh
0x1800f0c97  jmp     loc_1800F0BCC
0x1800f0c9c  mov     rsi, [rbp+57h+var_88]
0x1800f0ca0  lea     rdx, aRawuri; "RawURI"
0x1800f0ca7  mov     rbx, [rbp+57h+var_90]
0x1800f0cab  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800f0caf  mov     r9d, 6; unsigned int
0x1800f0cb5  mov     rax, [rsi]
0x1800f0cb8  mov     [rbp+57h+var_48], r13
0x1800f0cbc  lea     r8d, [r9+1]; unsigned int
0x1800f0cc0  mov     rdi, [rax+50h]
0x1800f0cc4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800f0cc9  mov     rdx, [rbp+57h+var_48]
0x1800f0ccd  lea     r9, [rbp+57h+var_A0]
0x1800f0cd1  mov     r8, rbx
0x1800f0cd4  mov     rcx, rsi
0x1800f0cd7  mov     rax, rdi
0x1800f0cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0cdf  mov     ebx, eax
0x1800f0ce1  test    eax, eax
0x1800f0ce3  jns     short loc_1800F0CEF
0x1800f0ce5  mov     edx, 17Eh
0x1800f0cea  jmp     loc_1800F0BCC
0x1800f0cef  mov     rdi, [rbp+57h+var_68]
0x1800f0cf3  lea     rcx, [rbp+57h+var_90]
0x1800f0cf7  mov     rax, [rdi]
0x1800f0cfa  mov     rbx, [rax+90h]
0x1800f0d01  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0d06  lea     r8, [rbp+57h+var_90]
0x1800f0d0a  mov     rdx, r12
0x1800f0d0d  mov     rcx, rdi
0x1800f0d10  mov     rax, rbx
0x1800f0d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0d18  mov     ebx, eax
0x1800f0d1a  test    eax, eax
0x1800f0d1c  jns     short loc_1800F0D28
0x1800f0d1e  mov     edx, 180h
0x1800f0d23  jmp     loc_1800F0BCC
0x1800f0d28  mov     rsi, [rbp+57h+var_88]
0x1800f0d2c  lea     rdx, aCallerpackagef; "CallerPackageFamilyName"
0x1800f0d33  mov     rbx, [rbp+57h+var_90]
0x1800f0d37  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800f0d3b  mov     r9d, 17h; unsigned int
0x1800f0d41  mov     rax, [rsi]
0x1800f0d44  mov     [rbp+57h+var_48], r13
0x1800f0d48  lea     r8d, [r9+1]; unsigned int
0x1800f0d4c  mov     rdi, [rax+50h]
0x1800f0d50  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800f0d55  mov     rdx, [rbp+57h+var_48]
0x1800f0d59  lea     r9, [rbp+57h+var_A0]
0x1800f0d5d  mov     r8, rbx
0x1800f0d60  mov     rcx, rsi
0x1800f0d63  mov     rax, rdi
0x1800f0d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0d6b  mov     ebx, eax
0x1800f0d6d  test    eax, eax
0x1800f0d6f  jns     short loc_1800F0D7B
0x1800f0d71  mov     edx, 181h
0x1800f0d76  jmp     loc_1800F0BCC
0x1800f0d7b  mov     rdx, [rbp+57h+var_80]; struct Windows::Foundation::Collections::IPropertySet *
0x1800f0d7f  mov     r8, r15; struct Windows::Storage::Streams::IBuffer **
0x1800f0d82  call    ?SerializePropertySet@AssociationLaunchExecuteCommandBase@@AEAAJPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAUIBuffer@Streams@Storage@5@@Z; AssociationLaunchExecuteCommandBase::SerializePropertySet(Windows::Foundation::Collections::IPropertySet *,Windows::Storage::Streams::IBuffer * *)
0x1800f0d87  mov     ebx, eax
0x1800f0d89  test    eax, eax
0x1800f0d8b  jns     short loc_1800F0D97
0x1800f0d8d  mov     edx, 183h
0x1800f0d92  jmp     loc_1800F0BCC
0x1800f0d97  lea     rcx, [rbp+57h+var_78]
0x1800f0d9b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0da0  mov     rcx, [rbp+57h+string]; string
0x1800f0da4  call    cs:__imp_WindowsDeleteString
0x1800f0daa  lea     rcx, [rbp+57h+var_70]
0x1800f0dae  mov     [rbp+57h+string], r13
0x1800f0db2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0db7  lea     rcx, [rbp+57h+var_90]
0x1800f0dbb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0dc0  lea     rcx, [rbp+57h+var_88]
0x1800f0dc4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0dc9  lea     rcx, [rbp+57h+var_80]
0x1800f0dcd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0dd2  mov     ebx, r13d
0x1800f0dd5  lea     rcx, [rbp+57h+var_68]
0x1800f0dd9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0dde  mov     eax, ebx
0x1800f0de0  mov     rcx, [rbp+57h+var_40]
0x1800f0de4  xor     rcx, rsp; StackCookie
0x1800f0de7  call    __security_check_cookie
0x1800f0dec  mov     rbx, [rsp+0D0h+arg_18]
0x1800f0df4  add     rsp, 0A0h
0x1800f0dfb  pop     r15
0x1800f0dfd  pop     r14
0x1800f0dff  pop     r13
0x1800f0e01  pop     r12
0x1800f0e03  pop     rdi
0x1800f0e04  pop     rsi
0x1800f0e05  pop     rbp
0x1800f0e06  retn
```
