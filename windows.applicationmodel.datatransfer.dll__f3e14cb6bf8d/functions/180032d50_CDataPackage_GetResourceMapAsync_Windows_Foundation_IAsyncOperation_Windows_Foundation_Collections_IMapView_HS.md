# CDataPackage::GetResourceMapAsync(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *> *> * *)

- ea: `0x180032d50`
- end: `0x180032f30`
- name: `?GetResourceMapAsync@CDataPackage@@UEAAJPEAPEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@Z`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002ad0`
- `0x180005504`
- `0x18000564c`
- `0x18000b708`
- `0x180032d50`
- `0x180051c68`
- `0x18005fa50`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180032dd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180032dd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180032e13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180032e13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180032da0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180032da0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180032dec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180032dec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDataPackage::GetResourceMapAsync(RTL_SRWLOCK *a1, __int64 a2, __int64 a3)
{
  RTL_SRWLOCK *v5; // rdi
  RTL_SRWLOCK *v6; // rbx
  char v7; // si
  char *v8; // rax
  __int64 v9; // r8
  char *v10; // rdi
  char *v11; // rax
  RTL_SRWLOCK *v12; // rsi
  unsigned int v13; // edi
  char v15; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR string[2]; // [rsp+40h] [rbp-48h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (__int64)a1,
      (const EVENT_DESCRIPTOR *)DataPackage_GetResourceMapAsync_Start,
      a3,
      1u,
      string);
  v5 = a1 + 42;
  AcquireSRWLockShared(a1 + 42);
  v6 = a1 - 13;
  if ( !v6[34].Ptr || LOBYTE(v6[35].Ptr) )
    goto LABEL_9;
  if ( WindowsCreateStringReference(L"HTML Format", 0xBu, (HSTRING_HEADER *)&string[0].Size, (HSTRING *)string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( CDataPackage::_ContainsDataFormat((CDataPackage *)v6, (HSTRING)string[0].Ptr) < 0 )
LABEL_9:
    v7 = 0;
  else
    v7 = 1;
  if ( v5 )
    ReleaseSRWLockShared(v5);
  if ( v6 )
  {
    (*((void (__fastcall **)(RTL_SRWLOCK *))v6->Ptr + 1))(v6);
    (*((void (__fastcall **)(RTL_SRWLOCK *))v6->Ptr + 1))(v6);
  }
  LODWORD(string[0].Ptr) = 5;
  *(ULONGLONG *)((char *)&string[0].Ptr + 4) = 4;
  v8 = (char *)operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v10 = v8;
  if ( v8 )
  {
    v8[8] = v7;
    v11 = v8 + 16;
    *(_QWORD *)v11 = 0;
    if ( v11 == &v15 )
    {
      v12 = v6;
    }
    else
    {
      *(_QWORD *)v11 = v6;
      v12 = 0;
    }
    *(_QWORD *)v10 = &off_1800868D8;
    *((_DWORD *)v10 + 6) = 0;
    `eh vector constructor iterator'(
      v10 + 32,
      8u,
      1u,
      (void (*)(void *))Microsoft::WRL::AgileRef::AgileRef,
      Microsoft::WRL::ComPtr<Windows::Storage::IStreamedFileDataRequestedHandler>::~ComPtr<Windows::Storage::IStreamedFileDataRequestedHandler>);
    *((_DWORD *)v10 + 6) = 0;
  }
  else
  {
    v10 = 0;
    v12 = v6;
  }
  v13 = Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *>>,Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *> *,Windows::Internal::ComTaskPoolHandler>(
          string,
          a2,
          v9,
          v10);
  if ( v12 )
    (*((void (__fastcall **)(RTL_SRWLOCK *))v12->Ptr + 2))(v12);
  if ( v6 )
    (*((void (__fastcall **)(RTL_SRWLOCK *))v6->Ptr + 2))(v6);
  return v13;
}

```

## disassembly

```asm
0x180032d50  mov     [rsp+arg_10], rbx
0x180032d55  push    rbp
0x180032d56  push    rsi
0x180032d57  push    rdi
0x180032d58  sub     rsp, 70h
0x180032d5c  mov     rax, cs:__security_cookie
0x180032d63  xor     rax, rsp
0x180032d66  mov     [rsp+88h+var_28], rax
0x180032d6b  mov     rbp, rdx
0x180032d6e  mov     rbx, rcx
0x180032d71  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180032d78  jz      short loc_180032D96
0x180032d7a  lea     rax, [rsp+88h+string]
0x180032d7f  mov     [rsp+88h+var_68], rax
0x180032d84  mov     r9d, 1
0x180032d8a  lea     rdx, DataPackage_GetResourceMapAsync_Start
0x180032d91  call    McGenEventWrite_EventWriteTransfer
0x180032d96  lea     rdi, [rbx+150h]
0x180032d9d  mov     rcx, rdi; SRWLock
0x180032da0  call    cs:__imp_AcquireSRWLockShared
0x180032da6  add     rbx, 0FFFFFFFFFFFFFF98h
0x180032daa  cmp     qword ptr [rbx+110h], 0
0x180032db2  jz      short loc_180032E08
0x180032db4  cmp     byte ptr [rbx+118h], 0
0x180032dbb  jnz     short loc_180032E08
0x180032dbd  lea     r9, [rsp+88h+string]; string
0x180032dc2  lea     r8, [rsp+88h+hstringHeader]; hstringHeader
0x180032dc7  mov     edx, 0Bh; length
0x180032dcc  lea     rcx, aHtmlFormat; "HTML Format"
0x180032dd3  call    cs:__imp_WindowsCreateStringReference
0x180032dd9  test    eax, eax
0x180032ddb  jns     short loc_180032DF2
0x180032ddd  xor     r9d, r9d; lpArguments
0x180032de0  xor     r8d, r8d; nNumberOfArguments
0x180032de3  lea     edx, [r9+1]; dwExceptionFlags
0x180032de7  mov     ecx, 0C000000Dh; dwExceptionCode
0x180032dec  call    cs:__imp_RaiseException
0x180032df2  mov     rdx, [rsp+88h+string]; HSTRING
0x180032df7  mov     rcx, rbx; this
0x180032dfa  call    ?_ContainsDataFormat@CDataPackage@@AEAAJPEAUHSTRING__@@@Z; CDataPackage::_ContainsDataFormat(HSTRING__ *)
0x180032dff  test    eax, eax
0x180032e01  js      short loc_180032E08
0x180032e03  mov     sil, 1
0x180032e06  jmp     short loc_180032E0B
0x180032e08  xor     sil, sil
0x180032e0b  test    rdi, rdi
0x180032e0e  jz      short loc_180032E1A
0x180032e10  mov     rcx, rdi; SRWLock
0x180032e13  call    cs:__imp_ReleaseSRWLockShared
0x180032e19  nop
0x180032e1a  test    rbx, rbx
0x180032e1d  jz      short loc_180032E2F
0x180032e1f  mov     rax, [rbx]
0x180032e22  mov     rcx, rbx
0x180032e25  mov     rax, [rax+8]
0x180032e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e2e  nop
0x180032e2f  test    rbx, rbx
0x180032e32  jz      short loc_180032E44
0x180032e34  mov     rax, [rbx]
0x180032e37  mov     rcx, rbx
0x180032e3a  mov     rax, [rax+8]
0x180032e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e43  nop
0x180032e44  mov     dword ptr [rsp+88h+string], 5
0x180032e4c  mov     [rsp+88h+string+4], 4
0x180032e55  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180032e5c  mov     ecx, 28h ; '('; unsigned __int64
0x180032e61  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180032e66  mov     rdi, rax
0x180032e69  test    rax, rax
0x180032e6c  jz      short loc_180032ED0
0x180032e6e  mov     [rax+8], sil
0x180032e72  add     rax, 10h
0x180032e76  mov     qword ptr [rax], 0
0x180032e7d  lea     rcx, [rsp+88h+var_50]
0x180032e82  cmp     rax, rcx
0x180032e85  jz      short loc_180032E8E
0x180032e87  mov     [rax], rbx
0x180032e8a  xor     esi, esi
0x180032e8c  jmp     short loc_180032E91
0x180032e8e  mov     rsi, rbx
0x180032e91  lea     rax, off_1800868D8
0x180032e98  mov     [rdi], rax
0x180032e9b  mov     dword ptr [rdi+18h], 0
0x180032ea2  lea     rcx, [rdi+20h]; void *
0x180032ea6  lea     rax, ??1?$ComPtr@UIStreamedFileDataRequestedHandler@Storage@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Storage::IStreamedFileDataRequestedHandler>::~ComPtr<Windows::Storage::IStreamedFileDataRequestedHandler>(void)
0x180032ead  mov     [rsp+88h+var_68], rax; void (*)(void *)
0x180032eb2  lea     r9, ??0AgileRef@WRL@Microsoft@@QEAA@XZ; void (*)(void *)
0x180032eb9  mov     edx, 8; unsigned __int64
0x180032ebe  lea     r8d, [rdx-7]; unsigned __int64
0x180032ec2  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180032ec7  mov     dword ptr [rdi+18h], 0
0x180032ece  jmp     short loc_180032ED5
0x180032ed0  xor     edi, edi
0x180032ed2  mov     rsi, rbx
0x180032ed5  mov     r9, rdi
0x180032ed8  mov     rdx, rbp
0x180032edb  lea     rcx, [rsp+88h+string]
0x180032ee0  call    ??$MakeAsyncOperationHelper@V?$CMarshaledInterfaceResult@U?$IMapView@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Collections@Foundation@Windows@@@Internal@Windows@@PEAU?$IMapView@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Collections@Foundation@3@VComTaskPoolHandler@23@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CMarshaledInterfaceResult@U?$IMapView@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Collections@Foundation@Windows@@@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *>>,Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *> *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *> *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *>>> *)
0x180032ee5  mov     edi, eax
0x180032ee7  test    rsi, rsi
0x180032eea  jz      short loc_180032EFC
0x180032eec  mov     rdx, [rsi]
0x180032eef  mov     rcx, rsi
0x180032ef2  mov     rax, [rdx+10h]
0x180032ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032efb  nop
0x180032efc  test    rbx, rbx
0x180032eff  jz      short loc_180032F11
0x180032f01  mov     rax, [rbx]
0x180032f04  mov     rcx, rbx
0x180032f07  mov     rax, [rax+10h]
0x180032f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f10  nop
0x180032f11  mov     eax, edi
0x180032f13  mov     rcx, [rsp+88h+var_28]
0x180032f18  xor     rcx, rsp; StackCookie
0x180032f1b  call    __security_check_cookie
0x180032f20  mov     rbx, [rsp+88h+arg_10]
0x180032f28  add     rsp, 70h
0x180032f2c  pop     rdi
0x180032f2d  pop     rsi
0x180032f2e  pop     rbp
0x180032f2f  retn
```
