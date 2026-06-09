# CDataPackage::_GetUriFormatAsync__lambda_fba75ebb5f5462bf13cf0990e263d592___

- ea: `0x180010b58`
- end: `0x180010d75`
- name: `CDataPackage::_GetUriFormatAsync__lambda_fba75ebb5f5462bf13cf0990e263d592___`
- size: `541`
- prototype: `__int64 __fastcall(CDataPackage *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800363f0`

## callees

- `0x180002ad0`
- `0x180006914`
- `0x180008a80`
- `0x18000b2a8`
- `0x180010b58`
- `0x180051c68`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180010c0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180010c0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010c2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010c2a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180010d35`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180010d35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010c38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010d44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010c38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010d44`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180010bc7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180010bc7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010d22`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010d22`

## pseudocode

```c
__int64 __fastcall CDataPackage::_GetUriFormatAsync__lambda_fba75ebb5f5462bf13cf0990e263d592___(
        RTL_SRWLOCK *this,
        __int64 a2,
        _QWORD *a3)
{
  HSTRING v5; // r15
  RTL_SRWLOCK *v6; // rbx
  HRESULT v7; // r14d
  _QWORD *v8; // rsi
  HSTRING v9; // rcx
  __int64 v10; // r8
  unsigned int StringW; // eax
  HSTRING newString; // [rsp+20h] [rbp-39h] BYREF
  char v14; // [rsp+28h] [rbp-31h]
  int v15; // [rsp+2Ch] [rbp-2Dh] BYREF
  __int64 v16; // [rsp+30h] [rbp-29h]
  _QWORD *v17; // [rsp+38h] [rbp-21h] BYREF
  RTL_SRWLOCK *v18; // [rsp+40h] [rbp-19h]
  _QWORD *v19; // [rsp+48h] [rbp-11h] BYREF
  RTL_SRWLOCK *v20; // [rsp+50h] [rbp-9h]
  char v21; // [rsp+58h] [rbp-1h]
  HSTRING string[4]; // [rsp+60h] [rbp+7h] BYREF

  newString = (HSTRING)L"UniformResourceLocatorW";
  Windows::Internal::StringReference::StringReference(string, &newString);
  v15 = 5;
  v16 = 4;
  v5 = string[0];
  *a3 = 0;
  v6 = this + 55;
  AcquireSRWLockShared(this + 55);
  v18 = this + 55;
  v7 = CDataPackage::_ContainsDataFormat((CDataPackage *)this, v5);
  if ( v7 < 0 )
  {
    newString = 0;
    StringW = LoadStringW(&_ImageBase, 0x16u, (LPWSTR)&newString, 0);
    if ( StringW )
      RoOriginateErrorW((unsigned int)v7, StringW, newString);
  }
  else
  {
    CreateRefCountedObj<Windows::Internal::String,>(&v17);
    v8 = v17;
    if ( v17 )
    {
      newString = 0;
      v7 = WindowsDuplicateString(v5, &newString);
      if ( v7 >= 0 )
      {
        v9 = (HSTRING)v8[1];
        v8[1] = newString;
        WindowsDeleteString(v9);
        if ( this != (RTL_SRWLOCK *)-440LL )
        {
          ReleaseSRWLockShared(this + 55);
          v6 = 0;
          v18 = 0;
        }
        newString = (HSTRING)this;
        if ( this )
          (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 1))(this);
        v19 = v8;
        if ( v8 )
          (*(void (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
        v20 = this;
        if ( this )
          (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 1))(this);
        v21 = v14;
        v7 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::Foundation::IUriRuntimeClass__Windows::Foundation::Uri___Windows::Internal::ComTaskPoolHandler__lambda_704e55f4472e865df7e6460bc8d28f9f___(
               &v15,
               a3,
               v10,
               &v19,
               newString);
        if ( v20 )
          (*((void (__fastcall **)(RTL_SRWLOCK *))v20->Ptr + 2))(v20);
        if ( v19 )
          (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
        if ( this )
          (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 2))(this);
      }
    }
    else
    {
      v7 = -2147024882;
    }
    if ( v8 )
      (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
  }
  if ( v6 )
    ReleaseSRWLockShared(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180010b58  mov     [rsp-8+arg_8], rbx
0x180010b5d  mov     [rsp-8+arg_18], rsi
0x180010b62  push    rbp
0x180010b63  push    rdi
0x180010b64  push    r12
0x180010b66  push    r14
0x180010b68  push    r15
0x180010b6a  lea     rbp, [rsp-37h]
0x180010b6f  sub     rsp, 90h
0x180010b76  mov     rax, cs:__security_cookie
0x180010b7d  xor     rax, rsp
0x180010b80  mov     [rbp+57h+var_30], rax
0x180010b84  mov     r12, r8
0x180010b87  mov     rdi, rcx
0x180010b8a  lea     rax, aUniformresourc_0; "UniformResourceLocatorW"
0x180010b91  mov     [rbp+57h+newString], rax
0x180010b95  lea     rdx, [rbp+57h+newString]
0x180010b99  lea     rcx, [rbp+57h+string]
0x180010b9d  call    ??$?0PEBG@StringReference@Internal@Windows@@QEAA@AEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x180010ba2  mov     [rbp+57h+var_84], 5
0x180010ba9  mov     [rbp+57h+var_80], 4
0x180010bb1  mov     r15, [rbp+57h+string]
0x180010bb5  mov     qword ptr [r12], 0
0x180010bbd  lea     rbx, [rdi+1B8h]
0x180010bc4  mov     rcx, rbx; SRWLock
0x180010bc7  call    cs:__imp_AcquireSRWLockShared
0x180010bcd  mov     [rbp+57h+var_70], rbx
0x180010bd1  mov     rdx, r15; HSTRING
0x180010bd4  mov     rcx, rdi; this
0x180010bd7  call    ?_ContainsDataFormat@CDataPackage@@AEAAJPEAUHSTRING__@@@Z; CDataPackage::_ContainsDataFormat(HSTRING__ *)
0x180010bdc  mov     r14d, eax
0x180010bdf  test    eax, eax
0x180010be1  js      loc_180010D08
0x180010be7  lea     rcx, [rbp+57h+var_78]
0x180010beb  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180010bf0  nop
0x180010bf1  mov     rsi, [rbp+57h+var_78]
0x180010bf5  test    rsi, rsi
0x180010bf8  jz      loc_180010CEB
0x180010bfe  mov     [rbp+57h+newString], 0
0x180010c06  lea     rdx, [rbp+57h+newString]; newString
0x180010c0a  mov     rcx, r15; string
0x180010c0d  call    cs:__imp_WindowsDuplicateString
0x180010c13  mov     r14d, eax
0x180010c16  test    eax, eax
0x180010c18  js      loc_180010CF1
0x180010c1e  mov     rcx, [rsi+8]; string
0x180010c22  mov     rax, [rbp+57h+newString]
0x180010c26  mov     [rsi+8], rax
0x180010c2a  call    cs:__imp_WindowsDeleteString
0x180010c30  test    rbx, rbx
0x180010c33  jz      short loc_180010C44
0x180010c35  mov     rcx, rbx; SRWLock
0x180010c38  call    cs:__imp_ReleaseSRWLockShared
0x180010c3e  xor     ebx, ebx
0x180010c40  mov     [rbp+57h+var_70], rbx
0x180010c44  mov     [rbp+57h+newString], rdi
0x180010c48  test    rdi, rdi
0x180010c4b  jz      short loc_180010C5D
0x180010c4d  mov     rax, [rdi]
0x180010c50  mov     rcx, rdi
0x180010c53  mov     rax, [rax+8]
0x180010c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c5c  nop
0x180010c5d  mov     [rbp+57h+var_68], rsi
0x180010c61  test    rsi, rsi
0x180010c64  jz      short loc_180010C76
0x180010c66  mov     rax, [rsi]
0x180010c69  mov     rcx, rsi
0x180010c6c  mov     rax, [rax+8]
0x180010c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c75  nop
0x180010c76  mov     [rbp+57h+var_60], rdi
0x180010c7a  test    rdi, rdi
0x180010c7d  jz      short loc_180010C8F
0x180010c7f  mov     rax, [rdi]
0x180010c82  mov     rcx, rdi
0x180010c85  mov     rax, [rax+8]
0x180010c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c8e  nop
0x180010c8f  mov     al, [rbp+57h+var_88]
0x180010c92  mov     [rbp+57h+var_58], al
0x180010c95  lea     r9, [rbp+57h+var_68]
0x180010c99  mov     rdx, r12
0x180010c9c  lea     rcx, [rbp+57h+var_84]
0x180010ca0  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__Foundation__IUriRuntimeClass__Windows__Foundation__Uri___Windows__Internal__ComTaskPoolHandler__lambda_704e55f4472e865df7e6460bc8d28f9f___
0x180010ca5  mov     r14d, eax
0x180010ca8  mov     rcx, [rbp+57h+var_60]
0x180010cac  test    rcx, rcx
0x180010caf  jz      short loc_180010CBE
0x180010cb1  mov     rax, [rcx]
0x180010cb4  mov     rax, [rax+10h]
0x180010cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cbd  nop
0x180010cbe  mov     rcx, [rbp+57h+var_68]
0x180010cc2  test    rcx, rcx
0x180010cc5  jz      short loc_180010CD4
0x180010cc7  mov     rax, [rcx]
0x180010cca  mov     rax, [rax+10h]
0x180010cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cd3  nop
0x180010cd4  test    rdi, rdi
0x180010cd7  jz      short loc_180010CE9
0x180010cd9  mov     rax, [rdi]
0x180010cdc  mov     rcx, rdi
0x180010cdf  mov     rax, [rax+10h]
0x180010ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ce8  nop
0x180010ce9  jmp     short loc_180010CF1
0x180010ceb  mov     r14d, 8007000Eh
0x180010cf1  test    rsi, rsi
0x180010cf4  jz      short loc_180010D06
0x180010cf6  mov     rax, [rsi]
0x180010cf9  mov     rcx, rsi
0x180010cfc  mov     rax, [rax+10h]
0x180010d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d05  nop
0x180010d06  jmp     short loc_180010D3C
0x180010d08  mov     [rbp+57h+newString], 0
0x180010d10  xor     r9d, r9d; cchBufferMax
0x180010d13  lea     r8, [rbp+57h+newString]; lpBuffer
0x180010d17  lea     edx, [r9+16h]; uID
0x180010d1b  lea     rcx, __ImageBase; hInstance
0x180010d22  call    cs:__imp_LoadStringW
0x180010d28  test    eax, eax
0x180010d2a  jz      short loc_180010D3C
0x180010d2c  mov     r8, [rbp+57h+newString]
0x180010d30  mov     edx, eax
0x180010d32  mov     ecx, r14d
0x180010d35  call    cs:__imp_RoOriginateErrorW
0x180010d3b  nop
0x180010d3c  test    rbx, rbx
0x180010d3f  jz      short loc_180010D4A
0x180010d41  mov     rcx, rbx; SRWLock
0x180010d44  call    cs:__imp_ReleaseSRWLockShared
0x180010d4a  mov     eax, r14d
0x180010d4d  mov     rcx, [rbp+57h+var_30]
0x180010d51  xor     rcx, rsp; StackCookie
0x180010d54  call    __security_check_cookie
0x180010d59  lea     r11, [rsp+0B0h+var_20]
0x180010d61  mov     rbx, [r11+38h]
0x180010d65  mov     rsi, [r11+48h]
0x180010d69  mov     rsp, r11
0x180010d6c  pop     r15
0x180010d6e  pop     r14
0x180010d70  pop     r12
0x180010d72  pop     rdi
0x180010d73  pop     rbp
0x180010d74  retn
```
