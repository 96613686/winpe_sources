# OneSyncPropToUdmProp(Microsoft::WRL::ComPtr<IInspectable> &,UdmPropertyValue *)

- ea: `0x180029c5c`
- end: `0x180029ff8`
- name: `?OneSyncPropToUdmProp@@YAJAEAV?$ComPtr@UIInspectable@@@WRL@Microsoft@@PEAUUdmPropertyValue@@@Z`
- size: `924`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a000`

## callees

- `0x180004658`
- `0x180008f0c`
- `0x180029c5c`
- `0x18002c31c`
- `0x18012e010`

## import_xrefs

- `UserDataTypeHelperUtil!DupString` at `0x180029d2a`
- `UserDataTypeHelperUtil!DupString` at `0x180029d2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029ce7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029d57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029e17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029e9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029ce7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029d57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029e17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029e9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029d1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029d1d`

## string_xrefs

- `0x180029d40`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x180029df7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x180029e66`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x180029e87`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x180029ee2`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x180029fd5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`

## pseudocode

```c
__int64 __fastcall OneSyncPropToUdmProp(__int64 (__fastcall ****a1)(_QWORD, GUID *, __int64), __int64 a2)
{
  int v4; // edx
  int v5; // edx
  int v6; // edx
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64); // rdi
  int (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  unsigned int v12; // ebx
  HSTRING v13; // rcx
  PCWSTR StringRawBuffer; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64); // rdi
  int (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // rax^4
  __int64 v23; // r9
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // r9
  int v27; // eax
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64); // rdi
  int (__fastcall *v29)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v30; // rdx
  __int64 v31; // rcx
  _QWORD v32[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v33; // [rsp+68h] [rbp+28h] BYREF
  HSTRING string; // [rsp+70h] [rbp+30h] BYREF
  __int64 v35; // [rsp+78h] [rbp+38h] BYREF

  v4 = *(unsigned __int16 *)(a2 + 4) - 1;
  if ( !v4 || (v5 = v4 - 1) == 0 )
  {
    v35 = 0;
    v32[0] = 0;
    if ( (int)Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IReference<unsigned int>>(a1, (__int64)v32) < 0 )
    {
      v28 = *a1;
      v29 = (int (__fastcall *)(_QWORD, GUID *, __int64 *))**v28;
      Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v35);
      if ( v29(v28, &GUID_3c00fd60_2950_5939_a21a_2d12c5a01b8a, &v35) < 0 )
      {
        v12 = -2147024809;
        v26 = 1828;
        v31 = 2147942487LL;
        v30 = 0;
        goto LABEL_40;
      }
      LOBYTE(v33) = 0;
      v25 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 48LL))(v35, &v33);
      v12 = v25;
      if ( v25 < 0 )
      {
        v26 = 1821;
        goto LABEL_36;
      }
      v27 = (unsigned __int8)v33;
    }
    else
    {
      LODWORD(string) = 0;
      v25 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)v32[0] + 48LL))(v32[0], &string);
      v12 = v25;
      if ( v25 < 0 )
      {
        v26 = 1813;
LABEL_36:
        v30 = 1;
        v31 = (unsigned int)v25;
LABEL_40:
        Log_HREvent(
          v31,
          v30,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
          v26);
        Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(v32);
        Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v35);
        return v12;
      }
      v27 = (int)string;
    }
    *(_DWORD *)a2 &= ~0x100u;
    *(_DWORD *)(a2 + 8) = v27;
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(v32);
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v35);
    return 0;
  }
  v6 = v5 - 2;
  if ( !v6 )
  {
    v18 = *a1;
    v33 = 0;
    v19 = (int (__fastcall *)(_QWORD, GUID *, __int64 *))**v18;
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v33);
    if ( v19(v18, &GUID_5541d8a7_497c_5aa4_86fc_7713adbf2a2c, &v33) < 0 )
    {
      v23 = 1847;
      v24 = 0;
      v12 = -2147024809;
    }
    else
    {
      string = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 48LL))(v33, &string);
      if ( (v12 & 0x80000000) != 0 )
      {
        v20 = 1840;
        v21 = 1;
LABEL_16:
        Log_HREvent(
          v12,
          v21,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
          v20);
LABEL_10:
        v16 = v33;
        if ( v33 )
        {
          v33 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
        return v12;
      }
      v22 = HIDWORD(string);
      if ( (__int64)string >= 0 )
      {
        *(_DWORD *)(a2 + 8) = (_DWORD)string;
        *(_DWORD *)(a2 + 12) = v22;
        *(_DWORD *)a2 &= ~0x100u;
        Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v33);
        return 0;
      }
      v23 = 1842;
      v24 = 1;
      v12 = -2147483637;
    }
    Log_HREvent(
      v12,
      v24,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      v23);
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v33);
    return v12;
  }
  if ( v6 != 1 )
  {
    v12 = -2147024809;
    Log_HREvent(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      1879);
    return v12;
  }
  v7 = *a1;
  v33 = 0;
  v8 = (int (__fastcall *)(_QWORD, GUID *, __int64 *))**v7;
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v33);
  if ( v8(v7, &GUID_fd416dfb_2a07_52eb_aae3_dfce14116c05, &v33) < 0 )
  {
    v20 = 1873;
    v21 = 0;
    v12 = -2147024809;
    goto LABEL_16;
  }
  v9 = v33;
  string = 0;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v11 = v10(v9, &string);
  v12 = v11;
  if ( v11 < 0 )
  {
    Log_HREvent(
      (unsigned int)v11,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      1859);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v33);
    return v12;
  }
  v13 = string;
  if ( string )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v15 = DupString(a2 + 8, StringRawBuffer);
    v12 = v15;
    if ( v15 < 0 )
    {
      Log_HREvent(
        (unsigned int)v15,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
        1863);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_10;
    }
    v13 = string;
  }
  else
  {
    *(_QWORD *)(a2 + 8) = 0;
  }
  *(_DWORD *)a2 &= ~0x100u;
  WindowsDeleteString(v13);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v33);
  return 0;
}

```

## disassembly

```asm
0x180029c5c  mov     [rsp-18h+arg_0], rbx
0x180029c61  push    rbp
0x180029c62  push    rdi
0x180029c63  push    r14
0x180029c65  mov     rbp, rsp
0x180029c68  sub     rsp, 40h
0x180029c6c  mov     r14, rdx
0x180029c6f  mov     rdi, rcx
0x180029c72  movzx   edx, word ptr [rdx+4]
0x180029c76  sub     edx, 1
0x180029c79  jz      loc_180029EFE
0x180029c7f  sub     edx, 1
0x180029c82  jz      loc_180029EFE
0x180029c88  sub     edx, 2
0x180029c8b  jz      loc_180029D92
0x180029c91  cmp     edx, 1
0x180029c94  jnz     loc_180029E61
0x180029c9a  mov     rdi, [rcx]
0x180029c9d  lea     rcx, [rbp+arg_8]
0x180029ca1  mov     [rbp+arg_8], 0
0x180029ca9  mov     rax, [rdi]
0x180029cac  mov     rbx, [rax]
0x180029caf  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180029cb4  lea     r8, [rbp+arg_8]
0x180029cb8  mov     rcx, rdi
0x180029cbb  lea     rdx, _GUID_fd416dfb_2a07_52eb_aae3_dfce14116c05
0x180029cc2  mov     rax, rbx
0x180029cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cca  test    eax, eax
0x180029ccc  js      loc_180029E2D
0x180029cd2  mov     rdi, [rbp+arg_8]
0x180029cd6  xor     ecx, ecx; string
0x180029cd8  mov     [rbp+string], 0
0x180029ce0  mov     rax, [rdi]
0x180029ce3  mov     rbx, [rax+30h]
0x180029ce7  call    cs:__imp_WindowsDeleteString
0x180029ced  lea     rdx, [rbp+string]
0x180029cf1  mov     [rbp+string], 0
0x180029cf9  mov     rcx, rdi
0x180029cfc  mov     rax, rbx
0x180029cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d04  mov     ebx, eax
0x180029d06  test    eax, eax
0x180029d08  js      loc_180029E81
0x180029d0e  mov     rcx, [rbp+string]; string
0x180029d12  test    rcx, rcx
0x180029d15  jz      loc_180029E0A
0x180029d1b  xor     edx, edx; length
0x180029d1d  call    cs:__imp_WindowsGetStringRawBuffer
0x180029d23  mov     rdx, rax
0x180029d26  lea     rcx, [r14+8]
0x180029d2a  call    cs:__imp_DupString
0x180029d30  mov     ebx, eax
0x180029d32  test    eax, eax
0x180029d34  jns     loc_180029EBA
0x180029d3a  mov     r9d, 747h
0x180029d40  lea     r8, aOnecoreuapBase_90; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180029d47  mov     edx, 1
0x180029d4c  mov     ecx, eax
0x180029d4e  call    Log_HREvent
0x180029d53  mov     rcx, [rbp+string]; string
0x180029d57  call    cs:__imp_WindowsDeleteString
0x180029d5d  mov     [rbp+string], 0
0x180029d65  mov     rcx, [rbp+arg_8]
0x180029d69  test    rcx, rcx
0x180029d6c  jz      short loc_180029D82
0x180029d6e  mov     [rbp+arg_8], 0
0x180029d76  mov     rax, [rcx]
0x180029d79  mov     rax, [rax+10h]
0x180029d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d82  mov     eax, ebx
0x180029d84  mov     rbx, [rsp+40h+arg_0]
0x180029d89  add     rsp, 40h
0x180029d8d  pop     r14
0x180029d8f  pop     rdi
0x180029d90  pop     rbp
0x180029d91  retn
0x180029d92  mov     rdi, [rcx]
0x180029d95  lea     rcx, [rbp+arg_8]
0x180029d99  mov     [rbp+arg_8], 0
0x180029da1  mov     rax, [rdi]
0x180029da4  mov     rbx, [rax]
0x180029da7  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180029dac  lea     r8, [rbp+arg_8]
0x180029db0  mov     rcx, rdi
0x180029db3  lea     rdx, _GUID_5541d8a7_497c_5aa4_86fc_7713adbf2a2c
0x180029dba  mov     rax, rbx
0x180029dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dc2  test    eax, eax
0x180029dc4  js      loc_180029ED5
0x180029dca  mov     rcx, [rbp+arg_8]
0x180029dce  lea     rdx, [rbp+string]
0x180029dd2  mov     [rbp+string], 0
0x180029dda  mov     rax, [rcx]
0x180029ddd  mov     rax, [rax+30h]
0x180029de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029de6  mov     ebx, eax
0x180029de8  test    eax, eax
0x180029dea  jns     short loc_180029E3C
0x180029dec  mov     r9d, 730h
0x180029df2  mov     edx, 1
0x180029df7  lea     r8, aOnecoreuapBase_90; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180029dfe  mov     ecx, ebx
0x180029e00  call    Log_HREvent
0x180029e05  jmp     loc_180029D65
0x180029e0a  mov     qword ptr [r14+8], 0
0x180029e12  btr     dword ptr [r14], 8
0x180029e17  call    cs:__imp_WindowsDeleteString
0x180029e1d  lea     rcx, [rbp+arg_8]
0x180029e21  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180029e26  xor     eax, eax
0x180029e28  jmp     loc_180029D84
0x180029e2d  mov     r9d, 751h
0x180029e33  xor     edx, edx
0x180029e35  mov     ebx, 80070057h
0x180029e3a  jmp     short loc_180029DF7
0x180029e3c  mov     rax, [rbp+string]
0x180029e40  test    rax, rax
0x180029e43  js      short loc_180029EC3
0x180029e45  mov     [r14+8], eax
0x180029e49  lea     rcx, [rbp+arg_8]
0x180029e4d  sar     rax, 20h
0x180029e51  mov     [r14+0Ch], eax
0x180029e55  btr     dword ptr [r14], 8
0x180029e5a  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180029e5f  jmp     short loc_180029E26
0x180029e61  mov     ebx, 80070057h
0x180029e66  lea     r8, aOnecoreuapBase_90; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180029e6d  mov     ecx, ebx
0x180029e6f  mov     r9d, 757h
0x180029e75  xor     edx, edx
0x180029e77  call    Log_HREvent
0x180029e7c  jmp     loc_180029D82
0x180029e81  mov     r9d, 743h
0x180029e87  lea     r8, aOnecoreuapBase_90; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180029e8e  mov     edx, 1
0x180029e93  mov     ecx, ebx
0x180029e95  call    Log_HREvent
0x180029e9a  mov     rcx, [rbp+string]; string
0x180029e9e  call    cs:__imp_WindowsDeleteString
0x180029ea4  lea     rcx, [rbp+arg_8]
0x180029ea8  mov     [rbp+string], 0
0x180029eb0  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180029eb5  jmp     loc_180029D82
0x180029eba  mov     rcx, [rbp+string]
0x180029ebe  jmp     loc_180029E12
0x180029ec3  mov     r9d, 732h
0x180029ec9  mov     edx, 1
0x180029ece  mov     ebx, 8000000Bh
0x180029ed3  jmp     short loc_180029EE2
0x180029ed5  mov     r9d, 737h
0x180029edb  xor     edx, edx
0x180029edd  mov     ebx, 80070057h
0x180029ee2  lea     r8, aOnecoreuapBase_90; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180029ee9  mov     ecx, ebx
0x180029eeb  call    Log_HREvent
0x180029ef0  lea     rcx, [rbp+arg_8]
0x180029ef4  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180029ef9  jmp     loc_180029D82
0x180029efe  lea     rdx, [rbp+var_10]
0x180029f02  mov     [rbp+arg_18], 0
0x180029f0a  mov     [rbp+var_10], 0
0x180029f12  call    ??$As@U?$IReference@I@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IReference@I@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IReference<uint>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IReference<uint>>>)
0x180029f17  test    eax, eax
0x180029f19  js      short loc_180029F49
0x180029f1b  mov     rcx, [rbp+var_10]
0x180029f1f  lea     rdx, [rbp+string]
0x180029f23  mov     dword ptr [rbp+string], 0
0x180029f2a  mov     rax, [rcx]
0x180029f2d  mov     rax, [rax+30h]
0x180029f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f36  mov     ebx, eax
0x180029f38  test    eax, eax
0x180029f3a  jns     short loc_180029F44
0x180029f3c  mov     r9d, 715h
0x180029f42  jmp     short loc_180029F99
0x180029f44  mov     eax, dword ptr [rbp+string]
0x180029f47  jmp     short loc_180029FA6
0x180029f49  mov     rdi, [rdi]
0x180029f4c  lea     rcx, [rbp+arg_18]
0x180029f50  mov     rax, [rdi]
0x180029f53  mov     rbx, [rax]
0x180029f56  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180029f5b  lea     r8, [rbp+arg_18]
0x180029f5f  mov     rcx, rdi
0x180029f62  lea     rdx, _GUID_3c00fd60_2950_5939_a21a_2d12c5a01b8a
0x180029f69  mov     rax, rbx
0x180029f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f71  test    eax, eax
0x180029f73  js      short loc_180029FC6
0x180029f75  mov     rcx, [rbp+arg_18]
0x180029f79  lea     rdx, [rbp+arg_8]
0x180029f7d  mov     byte ptr [rbp+arg_8], 0
0x180029f81  mov     rax, [rcx]
0x180029f84  mov     rax, [rax+30h]
0x180029f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f8d  mov     ebx, eax
0x180029f8f  test    eax, eax
0x180029f91  jns     short loc_180029FA2
0x180029f93  mov     r9d, 71Dh
0x180029f99  mov     edx, 1
0x180029f9e  mov     ecx, eax
0x180029fa0  jmp     short loc_180029FD5
0x180029fa2  movzx   eax, byte ptr [rbp+arg_8]
0x180029fa6  btr     dword ptr [r14], 8
0x180029fab  lea     rcx, [rbp+var_10]
0x180029faf  mov     [r14+8], eax
0x180029fb3  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180029fb8  lea     rcx, [rbp+arg_18]
0x180029fbc  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180029fc1  jmp     loc_180029E26
0x180029fc6  mov     ebx, 80070057h
0x180029fcb  mov     r9d, 724h
0x180029fd1  mov     ecx, ebx
0x180029fd3  xor     edx, edx
0x180029fd5  lea     r8, aOnecoreuapBase_90; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180029fdc  call    Log_HREvent
0x180029fe1  lea     rcx, [rbp+var_10]
0x180029fe5  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180029fea  lea     rcx, [rbp+arg_18]
0x180029fee  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180029ff3  jmp     loc_180029D82
```
