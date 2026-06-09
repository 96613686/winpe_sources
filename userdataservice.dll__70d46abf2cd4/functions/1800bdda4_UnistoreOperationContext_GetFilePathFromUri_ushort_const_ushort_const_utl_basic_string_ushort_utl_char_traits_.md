# UnistoreOperationContext::GetFilePathFromUri(ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x1800bdda4`
- end: `0x1800be1f9`
- name: `?GetFilePathFromUri@UnistoreOperationContext@@QEAAJPEBG0PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `1109`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800ea77c`

## callees

- `0x180004658`
- `0x180008f0c`
- `0x180035c40`
- `0x180042d18`
- `0x18005e048`
- `0x1800977ac`
- `0x1800977b8`
- `0x1800bd69c`
- `0x1800bdda4`
- `0x1800becb8`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdfca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdfca`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bde77`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bde77`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bdefb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bdefb`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x1800bdf46`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x1800bdfc0`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x1800bdf46`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x1800bdfc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bde8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bde8b`

## string_xrefs

- `0x1800bde19`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\unistorecontext.cpp`
- `0x1800bdeb0`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\unistorecontext.cpp`
- `0x1800bdf14`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\unistorecontext.cpp`
- `0x1800bdfe5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\unistorecontext.cpp`
- `0x1800be092`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\unistorecontext.cpp`
- `0x1800be123`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\unistorecontext.cpp`
- `0x1800be164`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\unistorecontext.cpp`
- `0x1800be1a8`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\unistorecontext.cpp`
- `0x1800bddde`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall UnistoreOperationContext::GetFilePathFromUri(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        __int64 a4)
{
  _WORD *v4; // rcx
  UINT32 v5; // r12d
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, HSTRING, __int64 *); // r14
  unsigned __int64 v13; // rcx
  int v14; // eax
  HRESULT v15; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rcx
  void *v19; // rbx
  WCHAR *v20; // rax
  WCHAR *v21; // rdi
  signed int LastError; // eax
  unsigned int v23; // esi
  UINT32 v24; // eax
  LPVOID v25; // r14
  int (__fastcall *v26)(LPVOID, __int64, _QWORD, HSTRING *); // rsi
  __int64 v28; // [rsp+30h] [rbp-50h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-48h] BYREF
  UINT32 count; // [rsp+40h] [rbp-40h] BYREF
  UINT32 bufferLength; // [rsp+44h] [rbp-3Ch] BYREF
  UINT32 length; // [rsp+48h] [rbp-38h] BYREF
  __int64 v33; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-20h] BYREF

  v4 = *(_WORD **)a4;
  v5 = 0;
  *(_QWORD *)(a4 + 8) = *(_QWORD *)a4;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  *v4 = 0;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    (HSTRING_HEADER *)&string,
    L"Windows.Foundation.Uri",
    0x17u,
    0x16u);
  v9 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
         *(_QWORD *)&hstringHeader.Reserved.Reserved2[16],
         &v33);
  v10 = v9;
  if ( v9 < 0 )
  {
    Log_HREvent(
      (unsigned int)v9,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\unistorecontext.cpp",
      753);
    goto LABEL_33;
  }
  v11 = v33;
  v28 = 0;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v33 + 48LL);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v28);
  v13 = -1;
  length = 0;
  do
    ++v13;
  while ( a2[v13] );
  if ( (int)ULongLongToULong(v13, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(a2, length, &hstringHeader, &string);
  v14 = v12(v11, string, &v28);
  v10 = v14;
  if ( v14 < 0 )
  {
    Log_HREvent(
      (unsigned int)v14,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\unistorecontext.cpp",
      756);
LABEL_9:
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v28);
    goto LABEL_33;
  }
  ppv = 0;
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&ppv);
  v15 = CoCreateInstance(
          &GUID_a8ca4495_65ab_4333_9ff9_4feb6fbf5169,
          0,
          1u,
          &GUID_428bb582_2a87_4ea0_b529_30067cc4a4d7,
          &ppv);
  v10 = v15;
  if ( v15 < 0 )
  {
    v16 = 759;
    v17 = 1;
    v18 = (unsigned int)v15;
LABEL_12:
    Log_HREvent(
      v18,
      v17,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\unistorecontext.cpp",
      v16);
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&ppv);
    goto LABEL_9;
  }
  count = 0;
  bufferLength = 0;
  if ( GetPackagesByPackageFamily(a3, &count, 0, &bufferLength, 0) != 122 )
  {
    v10 = -2147418113;
    v16 = 771;
    v18 = 2147549183LL;
    v17 = 0;
    goto LABEL_12;
  }
  v19 = operator new[](saturated_mul(count, 8u));
  if ( v19 )
  {
    v20 = (WCHAR *)operator new[](saturated_mul(bufferLength, 2u));
    v21 = v20;
    if ( v20 )
    {
      if ( !GetPackagesByPackageFamily(a3, &count, (PWSTR *)v19, &bufferLength, v20) )
      {
        v24 = count;
        if ( count )
        {
          while ( 1 )
          {
            if ( v5 >= v24 )
            {
              operator delete(v21);
              operator delete(v19);
              Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&ppv);
              Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v28);
              Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v33);
              return 2147943568LL;
            }
            v25 = ppv;
            string = 0;
            *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0u;
            v26 = *(int (__fastcall **)(LPVOID, __int64, _QWORD, HSTRING *))(*(_QWORD *)ppv + 40LL);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
            hstringHeader.Reserved.Reserved1 = (PVOID)-1LL;
            *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
            if ( v26(v25, v28, *((_QWORD *)v19 + v5), &string) >= 0 )
              break;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
            v24 = count;
            ++v5;
          }
          if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                   a4,
                                   string) )
          {
            v23 = -2147024882;
            Log_HREvent(
              2147942414LL,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\unistorecontext.cpp",
              793);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
            goto LABEL_21;
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
          operator delete(v21);
          operator delete(v19);
          Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&ppv);
          Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v28);
          v10 = 0;
        }
        else
        {
          Log_HREvent(
            2147943568LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\unistorecontext.cpp",
            786);
          operator delete(v21);
          operator delete(v19);
          Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&ppv);
          Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v28);
          v10 = -2147023728;
        }
        goto LABEL_33;
      }
      LastError = GetLastError();
      v23 = LastError;
      if ( LastError > 0 )
        v23 = (unsigned __int16)LastError | 0x80070000;
      Log_HREvent(
        v23,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\unistorecontext.cpp",
        784);
LABEL_21:
      operator delete(v21);
    }
    else
    {
      v23 = -2147024882;
      Log_HREvent(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\unistorecontext.cpp",
        777);
    }
    operator delete(v19);
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&ppv);
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v28);
    v10 = v23;
LABEL_33:
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v33);
    return v10;
  }
  Log_HREvent(
    2147942414LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\unistorecontext.cpp",
    774);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&ppv);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v33);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800bdda4  push    rbp
0x1800bdda6  push    rbx
0x1800bdda7  push    rsi
0x1800bdda8  push    rdi
0x1800bdda9  push    r12
0x1800bddab  push    r13
0x1800bddad  push    r14
0x1800bddaf  mov     rbp, rsp
0x1800bddb2  sub     rsp, 80h
0x1800bddb9  mov     rax, cs:__security_cookie
0x1800bddc0  xor     rax, rsp
0x1800bddc3  mov     [rbp+var_8], rax
0x1800bddc7  mov     rcx, [r9]
0x1800bddca  xor     r12d, r12d
0x1800bddcd  mov     [r9+8], rcx
0x1800bddd1  mov     r13, r9
0x1800bddd4  mov     rsi, r8
0x1800bddd7  mov     qword ptr [rbp+hstringHeader.Reserved+10h], r12
0x1800bdddb  mov     rdi, rdx
0x1800bddde  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800bdde5  mov     [rcx], r12w
0x1800bdde9  lea     r9d, [r12+16h]; unsigned int
0x1800bddee  lea     rcx, [rbp+string]; hstringHeader
0x1800bddf2  mov     [rbp+var_30], r12
0x1800bddf6  lea     r8d, [r12+17h]; unsigned int
0x1800bddfb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800bde00  mov     rcx, qword ptr [rbp+hstringHeader.Reserved+10h]
0x1800bde04  lea     rdx, [rbp+var_30]
0x1800bde08  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x1800bde0d  mov     ebx, eax
0x1800bde0f  test    eax, eax
0x1800bde11  jns     short loc_1800BDE31
0x1800bde13  mov     r9d, 2F1h
0x1800bde19  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800bde20  lea     edx, [r12+1]
0x1800bde25  mov     ecx, eax
0x1800bde27  call    Log_HREvent
0x1800bde2c  jmp     loc_1800BE196
0x1800bde31  mov     rbx, [rbp+var_30]
0x1800bde35  lea     rcx, [rbp+var_50]
0x1800bde39  mov     [rbp+var_50], r12
0x1800bde3d  mov     rax, [rbx]
0x1800bde40  mov     r14, [rax+30h]
0x1800bde44  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800bde49  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800bde4d  mov     [rbp+length], r12d
0x1800bde51  inc     rcx; unsigned __int64
0x1800bde54  cmp     [rdi+rcx*2], r12w
0x1800bde59  jnz     short loc_1800BDE51
0x1800bde5b  lea     rdx, [rbp+length]; unsigned int *
0x1800bde5f  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800bde64  test    eax, eax
0x1800bde66  jns     short loc_1800BDE7D
0x1800bde68  xor     r9d, r9d; lpArguments
0x1800bde6b  xor     r8d, r8d; nNumberOfArguments
0x1800bde6e  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bde73  lea     edx, [r9+1]; dwExceptionFlags
0x1800bde77  call    cs:__imp_RaiseException
0x1800bde7d  mov     edx, [rbp+length]; length
0x1800bde80  lea     r9, [rbp+string]; string
0x1800bde84  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800bde88  mov     rcx, rdi; sourceString
0x1800bde8b  call    cs:__imp_WindowsCreateStringReference
0x1800bde91  mov     rdx, [rbp+string]
0x1800bde95  lea     r8, [rbp+var_50]
0x1800bde99  mov     rcx, rbx
0x1800bde9c  mov     rax, r14
0x1800bde9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdea4  mov     ebx, eax
0x1800bdea6  test    eax, eax
0x1800bdea8  jns     short loc_1800BDED1
0x1800bdeaa  mov     r9d, 2F4h
0x1800bdeb0  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800bdeb7  mov     edx, 1
0x1800bdebc  mov     ecx, eax
0x1800bdebe  call    Log_HREvent
0x1800bdec3  lea     rcx, [rbp+var_50]
0x1800bdec7  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800bdecc  jmp     loc_1800BE196
0x1800bded1  lea     rcx, [rbp+var_48]
0x1800bded5  mov     [rbp+var_48], r12
0x1800bded9  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800bdede  xor     edx, edx; pUnkOuter
0x1800bdee0  lea     rax, [rbp+var_48]
0x1800bdee4  lea     r9, _GUID_428bb582_2a87_4ea0_b529_30067cc4a4d7; riid
0x1800bdeeb  mov     [rsp+80h+ppv], rax; ppv
0x1800bdef0  lea     rcx, _GUID_a8ca4495_65ab_4333_9ff9_4feb6fbf5169; rclsid
0x1800bdef7  lea     r8d, [rdx+1]; dwClsContext
0x1800bdefb  call    cs:__imp_CoCreateInstance
0x1800bdf01  mov     ebx, eax
0x1800bdf03  test    eax, eax
0x1800bdf05  jns     short loc_1800BDF2B
0x1800bdf07  mov     r9d, 2F7h
0x1800bdf0d  mov     edx, 1
0x1800bdf12  mov     ecx, eax
0x1800bdf14  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800bdf1b  call    Log_HREvent
0x1800bdf20  lea     rcx, [rbp+var_48]
0x1800bdf24  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800bdf29  jmp     short loc_1800BDEC3
0x1800bdf2b  lea     r9, [rbp+bufferLength]; bufferLength
0x1800bdf2f  mov     [rbp+count], r12d
0x1800bdf33  xor     r8d, r8d; packageFullNames
0x1800bdf36  mov     [rbp+bufferLength], r12d
0x1800bdf3a  lea     rdx, [rbp+count]; count
0x1800bdf3e  mov     [rsp+80h+ppv], r12; buffer
0x1800bdf43  mov     rcx, rsi; packageFamilyName
0x1800bdf46  call    cs:__imp_GetPackagesByPackageFamily
0x1800bdf4c  cmp     eax, 7Ah ; 'z'
0x1800bdf4f  jz      short loc_1800BDF62
0x1800bdf51  mov     ebx, 8000FFFFh
0x1800bdf56  mov     r9d, 303h
0x1800bdf5c  mov     ecx, ebx
0x1800bdf5e  xor     edx, edx
0x1800bdf60  jmp     short loc_1800BDF14
0x1800bdf62  mov     ecx, [rbp+count]
0x1800bdf65  mov     eax, 8
0x1800bdf6a  mul     rcx
0x1800bdf6d  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800bdf74  cmovb   rax, rdi
0x1800bdf78  mov     rcx, rax; unsigned __int64
0x1800bdf7b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800bdf80  mov     rbx, rax
0x1800bdf83  test    rax, rax
0x1800bdf86  jz      loc_1800BE1A3
0x1800bdf8c  mov     ecx, [rbp+bufferLength]
0x1800bdf8f  lea     eax, [rdi+3]
0x1800bdf92  mul     rcx
0x1800bdf95  cmovb   rax, rdi
0x1800bdf99  mov     rcx, rax; unsigned __int64
0x1800bdf9c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800bdfa1  mov     rdi, rax
0x1800bdfa4  test    rax, rax
0x1800bdfa7  jz      loc_1800BE15F
0x1800bdfad  lea     r9, [rbp+bufferLength]; bufferLength
0x1800bdfb1  mov     [rsp+80h+ppv], rax; buffer
0x1800bdfb6  mov     r8, rbx; packageFullNames
0x1800bdfb9  lea     rdx, [rbp+count]; count
0x1800bdfbd  mov     rcx, rsi; packageFamilyName
0x1800bdfc0  call    cs:__imp_GetPackagesByPackageFamily
0x1800bdfc6  test    eax, eax
0x1800bdfc8  jz      short loc_1800BE002
0x1800bdfca  call    cs:__imp_GetLastError
0x1800bdfd0  mov     esi, eax
0x1800bdfd2  test    eax, eax
0x1800bdfd4  jle     short loc_1800BDFDF
0x1800bdfd6  movzx   esi, ax
0x1800bdfd9  or      esi, 80070000h
0x1800bdfdf  mov     r9d, 310h
0x1800bdfe5  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800bdfec  xor     edx, edx
0x1800bdfee  mov     ecx, esi
0x1800bdff0  call    Log_HREvent
0x1800bdff5  mov     rcx, rdi; Block
0x1800bdff8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bdffd  jmp     loc_1800BE17A
0x1800be002  mov     eax, [rbp+count]
0x1800be005  test    eax, eax
0x1800be007  jz      loc_1800BE11D
0x1800be00d  cmp     r12d, eax
0x1800be010  jnb     loc_1800BE0E8
0x1800be016  mov     r14, [rbp+var_48]
0x1800be01a  lea     rcx, [rbp+string]
0x1800be01e  mov     [rbp+string], 0
0x1800be026  mov     qword ptr [rbp+hstringHeader.Reserved], 0
0x1800be02e  mov     qword ptr [rbp+hstringHeader.Reserved+8], 0
0x1800be036  mov     rax, [r14]
0x1800be039  mov     rsi, [rax+28h]
0x1800be03d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800be042  mov     rdx, [rbp+var_50]
0x1800be046  lea     r9, [rbp+string]
0x1800be04a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800be04e  mov     r8d, r12d
0x1800be051  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x1800be055  mov     rcx, r14
0x1800be058  mov     qword ptr [rbp+hstringHeader.Reserved+8], rax
0x1800be05c  mov     rax, rsi
0x1800be05f  mov     r8, [rbx+r8*8]
0x1800be063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be068  test    eax, eax
0x1800be06a  jns     short loc_1800BE07D
0x1800be06c  lea     rcx, [rbp+string]
0x1800be070  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800be075  mov     eax, [rbp+count]
0x1800be078  inc     r12d
0x1800be07b  jmp     short loc_1800BE00D
0x1800be07d  mov     rdx, [rbp+string]
0x1800be081  mov     rcx, r13
0x1800be084  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800be089  test    al, al
0x1800be08b  jnz     short loc_1800BE0B6
0x1800be08d  mov     esi, 8007000Eh
0x1800be092  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800be099  mov     ecx, esi
0x1800be09b  mov     r9d, 319h
0x1800be0a1  xor     edx, edx
0x1800be0a3  call    Log_HREvent
0x1800be0a8  lea     rcx, [rbp+string]
0x1800be0ac  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800be0b1  jmp     loc_1800BDFF5
0x1800be0b6  lea     rcx, [rbp+string]
0x1800be0ba  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800be0bf  mov     rcx, rdi; Block
0x1800be0c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800be0c7  mov     rcx, rbx; Block
0x1800be0ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800be0cf  lea     rcx, [rbp+var_48]
0x1800be0d3  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800be0d8  lea     rcx, [rbp+var_50]
0x1800be0dc  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800be0e1  xor     ebx, ebx
0x1800be0e3  jmp     loc_1800BE196
0x1800be0e8  mov     rcx, rdi; Block
0x1800be0eb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800be0f0  mov     rcx, rbx; Block
0x1800be0f3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800be0f8  lea     rcx, [rbp+var_48]
0x1800be0fc  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800be101  lea     rcx, [rbp+var_50]
0x1800be105  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800be10a  lea     rcx, [rbp+var_30]
0x1800be10e  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800be113  mov     eax, 80070490h
0x1800be118  jmp     loc_1800BE1DB
0x1800be11d  mov     r9d, 312h
0x1800be123  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800be12a  xor     edx, edx
0x1800be12c  mov     ecx, 80070490h
0x1800be131  call    Log_HREvent
0x1800be136  mov     rcx, rdi; Block
0x1800be139  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800be13e  mov     rcx, rbx; Block
0x1800be141  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800be146  lea     rcx, [rbp+var_48]
0x1800be14a  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800be14f  lea     rcx, [rbp+var_50]
0x1800be153  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800be158  mov     ebx, 80070490h
0x1800be15d  jmp     short loc_1800BE196
0x1800be15f  mov     esi, 8007000Eh
0x1800be164  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800be16b  mov     ecx, esi
0x1800be16d  mov     r9d, 309h
0x1800be173  xor     edx, edx
0x1800be175  call    Log_HREvent
0x1800be17a  mov     rcx, rbx; Block
0x1800be17d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800be182  lea     rcx, [rbp+var_48]
0x1800be186  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800be18b  lea     rcx, [rbp+var_50]
0x1800be18f  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800be194  mov     ebx, esi
0x1800be196  lea     rcx, [rbp+var_30]
0x1800be19a  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800be19f  mov     eax, ebx
0x1800be1a1  jmp     short loc_1800BE1DB
0x1800be1a3  mov     esi, 8007000Eh
0x1800be1a8  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800be1af  mov     ecx, esi
0x1800be1b1  mov     r9d, 306h
0x1800be1b7  xor     edx, edx
0x1800be1b9  call    Log_HREvent
0x1800be1be  lea     rcx, [rbp+var_48]
0x1800be1c2  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800be1c7  lea     rcx, [rbp+var_50]
0x1800be1cb  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800be1d0  lea     rcx, [rbp+var_30]
0x1800be1d4  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800be1d9  mov     eax, esi
0x1800be1db  mov     rcx, [rbp+var_8]
0x1800be1df  xor     rcx, rsp; StackCookie
0x1800be1e2  call    __security_check_cookie
0x1800be1e7  add     rsp, 80h
0x1800be1ee  pop     r14
0x1800be1f0  pop     r13
0x1800be1f2  pop     r12
0x1800be1f4  pop     rdi
0x1800be1f5  pop     rsi
0x1800be1f6  pop     rbx
0x1800be1f7  pop     rbp
0x1800be1f8  retn
```
