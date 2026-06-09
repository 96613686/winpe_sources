# CDataPackage::_GetUriFormatAsync__lambda_69ad6b3c163ac00b6b08ee8f2415c60d___

- ea: `0x180010934`
- end: `0x180010b51`
- name: `CDataPackage::_GetUriFormatAsync__lambda_69ad6b3c163ac00b6b08ee8f2415c60d___`
- size: `541`
- prototype: `__int64 __fastcall(CDataPackage *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002c320`

## callees

- `0x180002ad0`
- `0x180006914`
- `0x180008a80`
- `0x18000b1c8`
- `0x180010934`
- `0x180051c68`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800109e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800109e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010a06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010a06`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180010b11`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180010b11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010a14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010b20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010a14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010b20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800109a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800109a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010afe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010afe`

## string_xrefs

- `0x180010966`: `ApplicationLink`

## pseudocode

```c
__int64 __fastcall CDataPackage::_GetUriFormatAsync__lambda_69ad6b3c163ac00b6b08ee8f2415c60d___(
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

  newString = (HSTRING)L"ApplicationLink";
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
        v7 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::Foundation::IUriRuntimeClass__Windows::Foundation::Uri___Windows::Internal::ComTaskPoolHandler__lambda_36e93f74a14b329ac04202e0e25393a2___(
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
0x180010934  mov     [rsp-8+arg_8], rbx
0x180010939  mov     [rsp-8+arg_18], rsi
0x18001093e  push    rbp
0x18001093f  push    rdi
0x180010940  push    r12
0x180010942  push    r14
0x180010944  push    r15
0x180010946  lea     rbp, [rsp-37h]
0x18001094b  sub     rsp, 90h
0x180010952  mov     rax, cs:__security_cookie
0x180010959  xor     rax, rsp
0x18001095c  mov     [rbp+57h+var_30], rax
0x180010960  mov     r12, r8
0x180010963  mov     rdi, rcx
0x180010966  lea     rax, aApplicationlin; "ApplicationLink"
0x18001096d  mov     [rbp+57h+newString], rax
0x180010971  lea     rdx, [rbp+57h+newString]
0x180010975  lea     rcx, [rbp+57h+string]
0x180010979  call    ??$?0PEBG@StringReference@Internal@Windows@@QEAA@AEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x18001097e  mov     [rbp+57h+var_84], 5
0x180010985  mov     [rbp+57h+var_80], 4
0x18001098d  mov     r15, [rbp+57h+string]
0x180010991  mov     qword ptr [r12], 0
0x180010999  lea     rbx, [rdi+1B8h]
0x1800109a0  mov     rcx, rbx; SRWLock
0x1800109a3  call    cs:__imp_AcquireSRWLockShared
0x1800109a9  mov     [rbp+57h+var_70], rbx
0x1800109ad  mov     rdx, r15; HSTRING
0x1800109b0  mov     rcx, rdi; this
0x1800109b3  call    ?_ContainsDataFormat@CDataPackage@@AEAAJPEAUHSTRING__@@@Z; CDataPackage::_ContainsDataFormat(HSTRING__ *)
0x1800109b8  mov     r14d, eax
0x1800109bb  test    eax, eax
0x1800109bd  js      loc_180010AE4
0x1800109c3  lea     rcx, [rbp+57h+var_78]
0x1800109c7  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x1800109cc  nop
0x1800109cd  mov     rsi, [rbp+57h+var_78]
0x1800109d1  test    rsi, rsi
0x1800109d4  jz      loc_180010AC7
0x1800109da  mov     [rbp+57h+newString], 0
0x1800109e2  lea     rdx, [rbp+57h+newString]; newString
0x1800109e6  mov     rcx, r15; string
0x1800109e9  call    cs:__imp_WindowsDuplicateString
0x1800109ef  mov     r14d, eax
0x1800109f2  test    eax, eax
0x1800109f4  js      loc_180010ACD
0x1800109fa  mov     rcx, [rsi+8]; string
0x1800109fe  mov     rax, [rbp+57h+newString]
0x180010a02  mov     [rsi+8], rax
0x180010a06  call    cs:__imp_WindowsDeleteString
0x180010a0c  test    rbx, rbx
0x180010a0f  jz      short loc_180010A20
0x180010a11  mov     rcx, rbx; SRWLock
0x180010a14  call    cs:__imp_ReleaseSRWLockShared
0x180010a1a  xor     ebx, ebx
0x180010a1c  mov     [rbp+57h+var_70], rbx
0x180010a20  mov     [rbp+57h+newString], rdi
0x180010a24  test    rdi, rdi
0x180010a27  jz      short loc_180010A39
0x180010a29  mov     rax, [rdi]
0x180010a2c  mov     rcx, rdi
0x180010a2f  mov     rax, [rax+8]
0x180010a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a38  nop
0x180010a39  mov     [rbp+57h+var_68], rsi
0x180010a3d  test    rsi, rsi
0x180010a40  jz      short loc_180010A52
0x180010a42  mov     rax, [rsi]
0x180010a45  mov     rcx, rsi
0x180010a48  mov     rax, [rax+8]
0x180010a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a51  nop
0x180010a52  mov     [rbp+57h+var_60], rdi
0x180010a56  test    rdi, rdi
0x180010a59  jz      short loc_180010A6B
0x180010a5b  mov     rax, [rdi]
0x180010a5e  mov     rcx, rdi
0x180010a61  mov     rax, [rax+8]
0x180010a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a6a  nop
0x180010a6b  mov     al, [rbp+57h+var_88]
0x180010a6e  mov     [rbp+57h+var_58], al
0x180010a71  lea     r9, [rbp+57h+var_68]
0x180010a75  mov     rdx, r12
0x180010a78  lea     rcx, [rbp+57h+var_84]
0x180010a7c  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__Foundation__IUriRuntimeClass__Windows__Foundation__Uri___Windows__Internal__ComTaskPoolHandler__lambda_36e93f74a14b329ac04202e0e25393a2___
0x180010a81  mov     r14d, eax
0x180010a84  mov     rcx, [rbp+57h+var_60]
0x180010a88  test    rcx, rcx
0x180010a8b  jz      short loc_180010A9A
0x180010a8d  mov     rax, [rcx]
0x180010a90  mov     rax, [rax+10h]
0x180010a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a99  nop
0x180010a9a  mov     rcx, [rbp+57h+var_68]
0x180010a9e  test    rcx, rcx
0x180010aa1  jz      short loc_180010AB0
0x180010aa3  mov     rax, [rcx]
0x180010aa6  mov     rax, [rax+10h]
0x180010aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aaf  nop
0x180010ab0  test    rdi, rdi
0x180010ab3  jz      short loc_180010AC5
0x180010ab5  mov     rax, [rdi]
0x180010ab8  mov     rcx, rdi
0x180010abb  mov     rax, [rax+10h]
0x180010abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ac4  nop
0x180010ac5  jmp     short loc_180010ACD
0x180010ac7  mov     r14d, 8007000Eh
0x180010acd  test    rsi, rsi
0x180010ad0  jz      short loc_180010AE2
0x180010ad2  mov     rax, [rsi]
0x180010ad5  mov     rcx, rsi
0x180010ad8  mov     rax, [rax+10h]
0x180010adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ae1  nop
0x180010ae2  jmp     short loc_180010B18
0x180010ae4  mov     [rbp+57h+newString], 0
0x180010aec  xor     r9d, r9d; cchBufferMax
0x180010aef  lea     r8, [rbp+57h+newString]; lpBuffer
0x180010af3  lea     edx, [r9+16h]; uID
0x180010af7  lea     rcx, __ImageBase; hInstance
0x180010afe  call    cs:__imp_LoadStringW
0x180010b04  test    eax, eax
0x180010b06  jz      short loc_180010B18
0x180010b08  mov     r8, [rbp+57h+newString]
0x180010b0c  mov     edx, eax
0x180010b0e  mov     ecx, r14d
0x180010b11  call    cs:__imp_RoOriginateErrorW
0x180010b17  nop
0x180010b18  test    rbx, rbx
0x180010b1b  jz      short loc_180010B26
0x180010b1d  mov     rcx, rbx; SRWLock
0x180010b20  call    cs:__imp_ReleaseSRWLockShared
0x180010b26  mov     eax, r14d
0x180010b29  mov     rcx, [rbp+57h+var_30]
0x180010b2d  xor     rcx, rsp; StackCookie
0x180010b30  call    __security_check_cookie
0x180010b35  lea     r11, [rsp+0B0h+var_20]
0x180010b3d  mov     rbx, [r11+38h]
0x180010b41  mov     rsi, [r11+48h]
0x180010b45  mov     rsp, r11
0x180010b48  pop     r15
0x180010b4a  pop     r14
0x180010b4c  pop     r12
0x180010b4e  pop     rdi
0x180010b4f  pop     rbp
0x180010b50  retn
```
