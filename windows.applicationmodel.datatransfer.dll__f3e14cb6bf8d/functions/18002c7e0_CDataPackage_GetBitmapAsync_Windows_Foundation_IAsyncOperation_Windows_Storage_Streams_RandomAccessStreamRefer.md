# CDataPackage::GetBitmapAsync(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::RandomAccessStreamReference *> * *)

- ea: `0x18002c7e0`
- end: `0x18002ca31`
- name: `?GetBitmapAsync@CDataPackage@@UEAAJPEAPEAU?$IAsyncOperation@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Foundation@Windows@@@Z`
- size: `593`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002ad0`
- `0x180008a80`
- `0x18000b0e8`
- `0x18002c7e0`
- `0x180051c68`
- `0x18005fa50`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002c8d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002c8d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c8ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c8ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c85e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c85e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18002c9f2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18002c9f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002c8fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002ca00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002c8fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002ca00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002c891`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002c891`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002c9df`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002c9df`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c875`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c875`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDataPackage::GetBitmapAsync(__int64 a1, _QWORD *a2, __int64 a3)
{
  RTL_SRWLOCK *v5; // rdi
  HSTRING v6; // r15
  RTL_SRWLOCK *v7; // rbx
  HRESULT v8; // r14d
  HSTRING v9; // rsi
  HSTRING v10; // rcx
  __int64 v11; // r8
  unsigned int StringW; // eax
  int *v14; // [rsp+20h] [rbp-39h]
  char v15; // [rsp+30h] [rbp-29h]
  HSTRING newString; // [rsp+38h] [rbp-21h] BYREF
  HSTRING v17; // [rsp+40h] [rbp-19h] BYREF
  RTL_SRWLOCK *v18; // [rsp+48h] [rbp-11h]
  char v19; // [rsp+50h] [rbp-9h]
  HSTRING string; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  int v22; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v23; // [rsp+7Ch] [rbp+23h]

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    v14 = &v22;
    McGenEventWrite_EventWriteTransfer(a1, DataPackage_GetBitmap_Start, a3, 1);
  }
  v5 = (RTL_SRWLOCK *)(a1 - 104);
  v22 = 5;
  v23 = 4;
  if ( WindowsCreateStringReference(L"Bitmap", 6u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = string;
  *a2 = 0;
  v7 = v5 + 55;
  AcquireSRWLockShared(v5 + 55);
  v8 = CDataPackage::_ContainsDataFormat((CDataPackage *)v5, v6);
  if ( v8 < 0 )
  {
    newString = 0;
    StringW = LoadStringW(&_ImageBase, 0x16u, (LPWSTR)&newString, 0);
    if ( StringW )
      RoOriginateErrorW((unsigned int)v8, StringW, newString);
  }
  else
  {
    CreateRefCountedObj<Windows::Internal::String,>(&newString);
    v9 = newString;
    if ( newString )
    {
      newString = 0;
      v8 = WindowsDuplicateString(v6, &newString);
      if ( v8 >= 0 )
      {
        v10 = (HSTRING)*((_QWORD *)v9 + 1);
        *((_QWORD *)v9 + 1) = newString;
        WindowsDeleteString(v10);
        if ( v5 != (RTL_SRWLOCK *)-440LL )
        {
          ReleaseSRWLockShared(v5 + 55);
          v7 = 0;
        }
        if ( v5 )
          (*((void (__fastcall **)(RTL_SRWLOCK *))v5->Ptr + 1))(v5);
        v17 = v9;
        if ( v9 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v9 + 8LL))(v9);
        v18 = v5;
        if ( v5 )
          (*((void (__fastcall **)(RTL_SRWLOCK *))v5->Ptr + 1))(v5);
        v19 = v15;
        v8 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::Storage::Streams::IRandomAccessStreamReference__Windows::Storage::Streams::RandomAccessStreamReference___Windows::Internal::ComTaskPoolHandler__lambda_c31da8dae0d8c84a0ad2483b5ff63901___(
               &v22,
               a2,
               v11,
               &v17,
               v14);
        if ( v18 )
          (*((void (__fastcall **)(RTL_SRWLOCK *))v18->Ptr + 2))(v18);
        if ( v17 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v17 + 16LL))(v17);
        if ( v5 )
          (*((void (__fastcall **)(RTL_SRWLOCK *))v5->Ptr + 2))(v5);
      }
    }
    else
    {
      v8 = -2147024882;
    }
    if ( v9 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v9 + 16LL))(v9);
  }
  if ( v7 )
    ReleaseSRWLockShared(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002c7e0  mov     [rsp-8+arg_10], rbx
0x18002c7e5  mov     [rsp-8+arg_18], rsi
0x18002c7ea  push    rbp
0x18002c7eb  push    rdi
0x18002c7ec  push    r12
0x18002c7ee  push    r14
0x18002c7f0  push    r15
0x18002c7f2  lea     rbp, [rsp-37h]
0x18002c7f7  sub     rsp, 90h
0x18002c7fe  mov     rax, cs:__security_cookie
0x18002c805  xor     rax, rsp
0x18002c808  mov     [rbp+57h+var_28], rax
0x18002c80c  mov     r12, rdx
0x18002c80f  mov     rdi, rcx
0x18002c812  mov     ebx, 1
0x18002c817  test    cs:Microsoft_Windows_Shell_CoreEnableBits, bl
0x18002c81d  jz      short loc_18002C837
0x18002c81f  lea     rax, [rbp+57h+var_38]
0x18002c823  mov     [rsp+0B0h+var_90], rax
0x18002c828  mov     r9d, ebx
0x18002c82b  lea     rdx, DataPackage_GetBitmap_Start
0x18002c832  call    McGenEventWrite_EventWriteTransfer
0x18002c837  add     rdi, 0FFFFFFFFFFFFFF98h
0x18002c83b  mov     [rbp+57h+var_38], 5
0x18002c842  mov     [rbp+57h+var_34], 4
0x18002c84a  lea     r9, [rbp+57h+string]; string
0x18002c84e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18002c852  mov     edx, 6; length
0x18002c857  lea     rcx, aBitmap; "Bitmap"
0x18002c85e  call    cs:__imp_WindowsCreateStringReference
0x18002c864  test    eax, eax
0x18002c866  jns     short loc_18002C87B
0x18002c868  xor     r9d, r9d; lpArguments
0x18002c86b  xor     r8d, r8d; nNumberOfArguments
0x18002c86e  mov     edx, ebx; dwExceptionFlags
0x18002c870  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002c875  call    cs:__imp_RaiseException
0x18002c87b  mov     r15, [rbp+57h+string]
0x18002c87f  mov     qword ptr [r12], 0
0x18002c887  lea     rbx, [rdi+1B8h]
0x18002c88e  mov     rcx, rbx; SRWLock
0x18002c891  call    cs:__imp_AcquireSRWLockShared
0x18002c897  mov     rdx, r15; HSTRING
0x18002c89a  mov     rcx, rdi; this
0x18002c89d  call    ?_ContainsDataFormat@CDataPackage@@AEAAJPEAUHSTRING__@@@Z; CDataPackage::_ContainsDataFormat(HSTRING__ *)
0x18002c8a2  mov     r14d, eax
0x18002c8a5  test    eax, eax
0x18002c8a7  js      loc_18002C9C5
0x18002c8ad  lea     rcx, [rbp+57h+newString]
0x18002c8b1  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x18002c8b6  mov     rsi, [rbp+57h+newString]
0x18002c8ba  test    rsi, rsi
0x18002c8bd  jz      loc_18002C9A8
0x18002c8c3  mov     [rbp+57h+newString], 0
0x18002c8cb  lea     rdx, [rbp+57h+newString]; newString
0x18002c8cf  mov     rcx, r15; string
0x18002c8d2  call    cs:__imp_WindowsDuplicateString
0x18002c8d8  mov     r14d, eax
0x18002c8db  test    eax, eax
0x18002c8dd  js      loc_18002C9AE
0x18002c8e3  mov     rcx, [rsi+8]; string
0x18002c8e7  mov     rax, [rbp+57h+newString]
0x18002c8eb  mov     [rsi+8], rax
0x18002c8ef  call    cs:__imp_WindowsDeleteString
0x18002c8f5  test    rbx, rbx
0x18002c8f8  jz      short loc_18002C905
0x18002c8fa  mov     rcx, rbx; SRWLock
0x18002c8fd  call    cs:__imp_ReleaseSRWLockShared
0x18002c903  xor     ebx, ebx
0x18002c905  test    rdi, rdi
0x18002c908  jz      short loc_18002C91A
0x18002c90a  mov     rax, [rdi]
0x18002c90d  mov     rcx, rdi
0x18002c910  mov     rax, [rax+8]
0x18002c914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c919  nop
0x18002c91a  mov     [rbp+57h+var_70], rsi
0x18002c91e  test    rsi, rsi
0x18002c921  jz      short loc_18002C933
0x18002c923  mov     rax, [rsi]
0x18002c926  mov     rcx, rsi
0x18002c929  mov     rax, [rax+8]
0x18002c92d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c932  nop
0x18002c933  mov     [rbp+57h+var_68], rdi
0x18002c937  test    rdi, rdi
0x18002c93a  jz      short loc_18002C94C
0x18002c93c  mov     rax, [rdi]
0x18002c93f  mov     rcx, rdi
0x18002c942  mov     rax, [rax+8]
0x18002c946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c94b  nop
0x18002c94c  mov     al, [rbp+57h+var_80]
0x18002c94f  mov     [rbp+57h+var_60], al
0x18002c952  lea     r9, [rbp+57h+var_70]
0x18002c956  mov     rdx, r12
0x18002c959  lea     rcx, [rbp+57h+var_38]
0x18002c95d  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__Storage__Streams__IRandomAccessStreamReference__Windows__Storage__Streams__RandomAccessStreamReference___Windows__Internal__ComTaskPoolHandler__lambda_c31da8dae0d8c84a0ad2483b5ff63901___
0x18002c962  mov     r14d, eax
0x18002c965  mov     rcx, [rbp+57h+var_68]
0x18002c969  test    rcx, rcx
0x18002c96c  jz      short loc_18002C97B
0x18002c96e  mov     rax, [rcx]
0x18002c971  mov     rax, [rax+10h]
0x18002c975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c97a  nop
0x18002c97b  mov     rcx, [rbp+57h+var_70]
0x18002c97f  test    rcx, rcx
0x18002c982  jz      short loc_18002C991
0x18002c984  mov     rax, [rcx]
0x18002c987  mov     rax, [rax+10h]
0x18002c98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c990  nop
0x18002c991  test    rdi, rdi
0x18002c994  jz      short loc_18002C9A6
0x18002c996  mov     rax, [rdi]
0x18002c999  mov     rcx, rdi
0x18002c99c  mov     rax, [rax+10h]
0x18002c9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9a5  nop
0x18002c9a6  jmp     short loc_18002C9AE
0x18002c9a8  mov     r14d, 8007000Eh
0x18002c9ae  test    rsi, rsi
0x18002c9b1  jz      short loc_18002C9C3
0x18002c9b3  mov     rax, [rsi]
0x18002c9b6  mov     rcx, rsi
0x18002c9b9  mov     rax, [rax+10h]
0x18002c9bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9c2  nop
0x18002c9c3  jmp     short loc_18002C9F8
0x18002c9c5  mov     [rbp+57h+newString], 0
0x18002c9cd  xor     r9d, r9d; cchBufferMax
0x18002c9d0  lea     r8, [rbp+57h+newString]; lpBuffer
0x18002c9d4  lea     edx, [r9+16h]; uID
0x18002c9d8  lea     rcx, __ImageBase; hInstance
0x18002c9df  call    cs:__imp_LoadStringW
0x18002c9e5  test    eax, eax
0x18002c9e7  jz      short loc_18002C9F8
0x18002c9e9  mov     r8, [rbp+57h+newString]
0x18002c9ed  mov     edx, eax
0x18002c9ef  mov     ecx, r14d
0x18002c9f2  call    cs:__imp_RoOriginateErrorW
0x18002c9f8  test    rbx, rbx
0x18002c9fb  jz      short loc_18002CA06
0x18002c9fd  mov     rcx, rbx; SRWLock
0x18002ca00  call    cs:__imp_ReleaseSRWLockShared
0x18002ca06  mov     eax, r14d
0x18002ca09  mov     rcx, [rbp+57h+var_28]
0x18002ca0d  xor     rcx, rsp; StackCookie
0x18002ca10  call    __security_check_cookie
0x18002ca15  lea     r11, [rsp+0B0h+var_20]
0x18002ca1d  mov     rbx, [r11+40h]
0x18002ca21  mov     rsi, [r11+48h]
0x18002ca25  mov     rsp, r11
0x18002ca28  pop     r15
0x18002ca2a  pop     r14
0x18002ca2c  pop     r12
0x18002ca2e  pop     rdi
0x18002ca2f  pop     rbp
0x18002ca30  retn
```
