# CDataPackage::GetStorageItemsAsync(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *> * *)

- ea: `0x180034220`
- end: `0x18003446b`
- name: `?GetStorageItemsAsync@CDataPackage@@UEAAJPEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@Z`
- size: `587`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002ad0`
- `0x180008a80`
- `0x18000af2c`
- `0x180034220`
- `0x180051c68`
- `0x18005fa50`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180034312`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180034312`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003432f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003432f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003429e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003429e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18003442c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18003442c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003433d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003443a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003433d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003443a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800342d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800342d1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180034419`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180034419`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800342b5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800342b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDataPackage::GetStorageItemsAsync(__int64 a1, _QWORD *a2, __int64 a3)
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
  HSTRING newString; // [rsp+30h] [rbp-29h] BYREF
  HSTRING v16; // [rsp+38h] [rbp-21h] BYREF
  RTL_SRWLOCK *v17; // [rsp+40h] [rbp-19h]
  HSTRING string; // [rsp+50h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-1h] BYREF
  int v20; // [rsp+70h] [rbp+17h] BYREF
  __int64 v21; // [rsp+74h] [rbp+1Bh]

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    v14 = &v20;
    McGenEventWrite_EventWriteTransfer(a1, DataPackage_GetStorageItemsAsync_Start, a3, 1);
  }
  v5 = (RTL_SRWLOCK *)(a1 - 104);
  v20 = 5;
  v21 = 4;
  if ( WindowsCreateStringReference(L"Shell IDList Array", 0x12u, &hstringHeader, &string) < 0 )
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
        v16 = v9;
        if ( v9 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v9 + 8LL))(v9);
        v17 = v5;
        if ( v5 )
          (*((void (__fastcall **)(RTL_SRWLOCK *))v5->Ptr + 1))(v5);
        v8 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::Foundation::Collections::IVectorView_Windows::Storage::IStorageItem______Windows::Foundation::Collections::IVectorView_Windows::Storage::IStorageItem______Windows::Internal::ComTaskPoolHandler__lambda_7aa40756cecaf2b051326608680426e9___(
               &v20,
               a2,
               v11,
               &v16,
               v14);
        if ( v17 )
          (*((void (__fastcall **)(RTL_SRWLOCK *))v17->Ptr + 2))(v17);
        if ( v16 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v16 + 16LL))(v16);
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
0x180034220  mov     [rsp-8+arg_10], rbx
0x180034225  mov     [rsp-8+arg_18], rsi
0x18003422a  push    rbp
0x18003422b  push    rdi
0x18003422c  push    r12
0x18003422e  push    r14
0x180034230  push    r15
0x180034232  lea     rbp, [rsp-37h]
0x180034237  sub     rsp, 90h
0x18003423e  mov     rax, cs:__security_cookie
0x180034245  xor     rax, rsp
0x180034248  mov     [rbp+57h+var_30], rax
0x18003424c  mov     r12, rdx
0x18003424f  mov     rdi, rcx
0x180034252  mov     ebx, 1
0x180034257  test    cs:Microsoft_Windows_Shell_CoreEnableBits, bl
0x18003425d  jz      short loc_180034277
0x18003425f  lea     rax, [rbp+57h+var_40]
0x180034263  mov     [rsp+0B0h+var_90], rax
0x180034268  mov     r9d, ebx
0x18003426b  lea     rdx, DataPackage_GetStorageItemsAsync_Start
0x180034272  call    McGenEventWrite_EventWriteTransfer
0x180034277  add     rdi, 0FFFFFFFFFFFFFF98h
0x18003427b  mov     [rbp+57h+var_40], 5
0x180034282  mov     [rbp+57h+var_3C], 4
0x18003428a  lea     r9, [rbp+57h+string]; string
0x18003428e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180034292  mov     edx, 12h; length
0x180034297  lea     rcx, aShellIdlistArr; "Shell IDList Array"
0x18003429e  call    cs:__imp_WindowsCreateStringReference
0x1800342a4  test    eax, eax
0x1800342a6  jns     short loc_1800342BB
0x1800342a8  xor     r9d, r9d; lpArguments
0x1800342ab  xor     r8d, r8d; nNumberOfArguments
0x1800342ae  mov     edx, ebx; dwExceptionFlags
0x1800342b0  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800342b5  call    cs:__imp_RaiseException
0x1800342bb  mov     r15, [rbp+57h+string]
0x1800342bf  mov     qword ptr [r12], 0
0x1800342c7  lea     rbx, [rdi+1B8h]
0x1800342ce  mov     rcx, rbx; SRWLock
0x1800342d1  call    cs:__imp_AcquireSRWLockShared
0x1800342d7  mov     rdx, r15; HSTRING
0x1800342da  mov     rcx, rdi; this
0x1800342dd  call    ?_ContainsDataFormat@CDataPackage@@AEAAJPEAUHSTRING__@@@Z; CDataPackage::_ContainsDataFormat(HSTRING__ *)
0x1800342e2  mov     r14d, eax
0x1800342e5  test    eax, eax
0x1800342e7  js      loc_1800343FF
0x1800342ed  lea     rcx, [rbp+57h+newString]
0x1800342f1  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x1800342f6  mov     rsi, [rbp+57h+newString]
0x1800342fa  test    rsi, rsi
0x1800342fd  jz      loc_1800343E2
0x180034303  mov     [rbp+57h+newString], 0
0x18003430b  lea     rdx, [rbp+57h+newString]; newString
0x18003430f  mov     rcx, r15; string
0x180034312  call    cs:__imp_WindowsDuplicateString
0x180034318  mov     r14d, eax
0x18003431b  test    eax, eax
0x18003431d  js      loc_1800343E8
0x180034323  mov     rcx, [rsi+8]; string
0x180034327  mov     rax, [rbp+57h+newString]
0x18003432b  mov     [rsi+8], rax
0x18003432f  call    cs:__imp_WindowsDeleteString
0x180034335  test    rbx, rbx
0x180034338  jz      short loc_180034345
0x18003433a  mov     rcx, rbx; SRWLock
0x18003433d  call    cs:__imp_ReleaseSRWLockShared
0x180034343  xor     ebx, ebx
0x180034345  test    rdi, rdi
0x180034348  jz      short loc_18003435A
0x18003434a  mov     rax, [rdi]
0x18003434d  mov     rcx, rdi
0x180034350  mov     rax, [rax+8]
0x180034354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034359  nop
0x18003435a  mov     [rbp+57h+var_78], rsi
0x18003435e  test    rsi, rsi
0x180034361  jz      short loc_180034373
0x180034363  mov     rax, [rsi]
0x180034366  mov     rcx, rsi
0x180034369  mov     rax, [rax+8]
0x18003436d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034372  nop
0x180034373  mov     [rbp+57h+var_70], rdi
0x180034377  test    rdi, rdi
0x18003437a  jz      short loc_18003438C
0x18003437c  mov     rax, [rdi]
0x18003437f  mov     rcx, rdi
0x180034382  mov     rax, [rax+8]
0x180034386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003438b  nop
0x18003438c  lea     r9, [rbp+57h+var_78]
0x180034390  mov     rdx, r12
0x180034393  lea     rcx, [rbp+57h+var_40]
0x180034397  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__Foundation__Collections__IVectorView_Windows__Storage__IStorageItem______Windows__Foundation__Collections__IVectorView_Windows__Storage__IStorageItem______Windows__Internal__ComTaskPoolHandler__lambda_7aa40756cecaf2b051326608680426e9___
0x18003439c  mov     r14d, eax
0x18003439f  mov     rcx, [rbp+57h+var_70]
0x1800343a3  test    rcx, rcx
0x1800343a6  jz      short loc_1800343B5
0x1800343a8  mov     rax, [rcx]
0x1800343ab  mov     rax, [rax+10h]
0x1800343af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343b4  nop
0x1800343b5  mov     rcx, [rbp+57h+var_78]
0x1800343b9  test    rcx, rcx
0x1800343bc  jz      short loc_1800343CB
0x1800343be  mov     rax, [rcx]
0x1800343c1  mov     rax, [rax+10h]
0x1800343c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343ca  nop
0x1800343cb  test    rdi, rdi
0x1800343ce  jz      short loc_1800343E0
0x1800343d0  mov     rax, [rdi]
0x1800343d3  mov     rcx, rdi
0x1800343d6  mov     rax, [rax+10h]
0x1800343da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343df  nop
0x1800343e0  jmp     short loc_1800343E8
0x1800343e2  mov     r14d, 8007000Eh
0x1800343e8  test    rsi, rsi
0x1800343eb  jz      short loc_1800343FD
0x1800343ed  mov     rax, [rsi]
0x1800343f0  mov     rcx, rsi
0x1800343f3  mov     rax, [rax+10h]
0x1800343f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343fc  nop
0x1800343fd  jmp     short loc_180034432
0x1800343ff  mov     [rbp+57h+newString], 0
0x180034407  xor     r9d, r9d; cchBufferMax
0x18003440a  lea     r8, [rbp+57h+newString]; lpBuffer
0x18003440e  lea     edx, [r9+16h]; uID
0x180034412  lea     rcx, __ImageBase; hInstance
0x180034419  call    cs:__imp_LoadStringW
0x18003441f  test    eax, eax
0x180034421  jz      short loc_180034432
0x180034423  mov     r8, [rbp+57h+newString]
0x180034427  mov     edx, eax
0x180034429  mov     ecx, r14d
0x18003442c  call    cs:__imp_RoOriginateErrorW
0x180034432  test    rbx, rbx
0x180034435  jz      short loc_180034440
0x180034437  mov     rcx, rbx; SRWLock
0x18003443a  call    cs:__imp_ReleaseSRWLockShared
0x180034440  mov     eax, r14d
0x180034443  mov     rcx, [rbp+57h+var_30]
0x180034447  xor     rcx, rsp; StackCookie
0x18003444a  call    __security_check_cookie
0x18003444f  lea     r11, [rsp+0B0h+var_20]
0x180034457  mov     rbx, [r11+40h]
0x18003445b  mov     rsi, [r11+48h]
0x18003445f  mov     rsp, r11
0x180034462  pop     r15
0x180034464  pop     r14
0x180034466  pop     r12
0x180034468  pop     rdi
0x180034469  pop     rbp
0x18003446a  retn
```
