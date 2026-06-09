# CStorageItemsDataFormat::_CreateStorageItemForContents(IStream *,_FILEDESCRIPTORW const &,ushort const *,Windows::Storage::IStorageItem * *)

- ea: `0x1800522e0`
- end: `0x180052591`
- name: `?_CreateStorageItemForContents@CStorageItemsDataFormat@@AEAAJPEAUIStream@@AEBU_FILEDESCRIPTORW@@PEBGPEAPEAUIStorageItem@Storage@Windows@@@Z`
- size: `689`
- prototype: `__int64 __fastcall(CStorageItemsDataFormat *__hidden this, struct IStream *, const struct _FILEDESCRIPTORW *, const unsigned __int16 *, struct Windows::Storage::IStorageItem **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180052598`

## callees

- `0x180002ad0`
- `0x180006914`
- `0x180006fcc`
- `0x180007084`
- `0x18003bd18`
- `0x18004caac`
- `0x1800522e0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052331`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052331`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180052536`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180052536`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180052524`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180052524`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005234b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005234b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005237d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005237d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStorageItemsDataFormat::_CreateStorageItemForContents(
        CStorageItemsDataFormat *this,
        struct IStream *a2,
        const struct _FILEDESCRIPTORW *a3,
        const unsigned __int16 *a4,
        struct Windows::Storage::IStorageItem **a5)
{
  int ActivationFactory; // ebx
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64, _QWORD, WCHAR *); // rbx
  _QWORD *v11; // rax
  const unsigned __int16 *v12; // rdx
  DWORD dwFileAttributes; // r8d
  struct Windows::Storage::IStorageItem *v14; // rcx
  const unsigned __int16 *v15; // rcx
  __int64 v16; // rcx
  unsigned int StringW; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  WCHAR Buffer[4]; // [rsp+30h] [rbp-41h] BYREF
  __int64 v22; // [rsp+38h] [rbp-39h] BYREF
  const unsigned __int16 *v23; // [rsp+40h] [rbp-31h] BYREF
  struct Windows::Storage::IStorageItem *v24; // [rsp+48h] [rbp-29h] BYREF
  __int64 v25; // [rsp+50h] [rbp-21h] BYREF
  __int64 v26; // [rsp+58h] [rbp-19h] BYREF
  HSTRING string; // [rsp+60h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-9h] BYREF

  v23 = a4;
  *a5 = 0;
  v22 = 0;
  if ( WindowsCreateStringReference(L"Windows.Storage.StorageFile", 0x1Bu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_5984c710_daf2_43c8_8bb4_a4d3eacfd03f, &v22);
  if ( ActivationFactory >= 0 )
  {
    v25 = 0;
    ActivationFactory = CMarshaledInterface::Marshal(&v25, &GUID_0000000c_0000_0000_c000_000000000046, a2, 2);
    if ( ActivationFactory < 0 )
      goto LABEL_28;
    *(_QWORD *)Buffer = v25;
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
    Microsoft::WRL::Callback_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Storage::IStreamedFileDataRequestedHandler_Microsoft::WRL::FtmBase___lambda_1217fab87f23337cb0d882f1f09c4b7d___(
      &v26,
      Buffer);
    if ( *(_QWORD *)Buffer )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)Buffer + 16LL))(*(_QWORD *)Buffer);
    v8 = v26;
    if ( v26 )
    {
      *(_QWORD *)Buffer = 0;
      v9 = v22;
      v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, WCHAR *))(*(_QWORD *)v22 + 64LL);
      v11 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, &v23);
      ActivationFactory = v10(v9, *v11, v8, 0, Buffer);
      if ( ActivationFactory >= 0 )
      {
        v23 = 0;
        ActivationFactory = BlockOnCompletionAndGetResults<Windows::Storage::StorageFile *,Windows::Storage::IStorageFile>(
                              *(_QWORD *)Buffer,
                              &v23);
        if ( ActivationFactory >= 0 )
        {
          v24 = 0;
          ActivationFactory = (**(__int64 (__fastcall ***)(const unsigned __int16 *, GUID *, struct Windows::Storage::IStorageItem **))v23)(
                                v23,
                                &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30,
                                &v24);
          if ( ActivationFactory < 0 )
          {
            v14 = v24;
          }
          else
          {
            if ( (a3->dwFlags & 4) != 0 )
            {
              dwFileAttributes = a3->dwFileAttributes;
              if ( dwFileAttributes )
                SetStorageItemUInt32Property(v24, v12, dwFileAttributes);
            }
            v14 = 0;
            *a5 = v24;
          }
          if ( v14 )
          {
            v24 = 0;
            (*(void (__fastcall **)(struct Windows::Storage::IStorageItem *))(*(_QWORD *)v14 + 16LL))(v14);
          }
        }
        v15 = v23;
        if ( v23 )
        {
          v23 = 0;
          (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v15 + 16LL))(v15);
        }
      }
      v16 = *(_QWORD *)Buffer;
      if ( *(_QWORD *)Buffer )
      {
        *(_QWORD *)Buffer = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
    }
    else
    {
      ActivationFactory = -2147024882;
    }
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    if ( ActivationFactory < 0 )
    {
LABEL_28:
      *(_QWORD *)Buffer = 0;
      StringW = LoadStringW(&_ImageBase, 0x15u, Buffer, 0);
      if ( StringW )
        RoOriginateErrorW((unsigned int)ActivationFactory, StringW, *(_QWORD *)Buffer);
    }
    v18 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
  }
  v19 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800522e0  push    rbp
0x1800522e2  push    rbx
0x1800522e3  push    rsi
0x1800522e4  push    rdi
0x1800522e5  push    r12
0x1800522e7  push    r14
0x1800522e9  push    r15
0x1800522eb  lea     rbp, [rsp-1Fh]
0x1800522f0  sub     rsp, 90h
0x1800522f7  mov     rax, cs:__security_cookie
0x1800522fe  xor     rax, rsp
0x180052301  mov     [rbp+4Fh+var_40], rax
0x180052305  mov     r14, r8
0x180052308  mov     rdi, rdx
0x18005230b  mov     [rbp+4Fh+var_80], r9
0x18005230f  mov     r15, [rbp+4Fh+arg_20]
0x180052313  xor     r12d, r12d
0x180052316  mov     [r15], r12
0x180052319  mov     [rbp+4Fh+var_88], r12
0x18005231d  lea     r9, [rbp+4Fh+string]; string
0x180052321  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180052325  lea     edx, [r12+1Bh]; length
0x18005232a  lea     rcx, ?RuntimeClass_Windows_Storage_StorageFile@@3QBGB; "Windows.Storage.StorageFile"
0x180052331  call    cs:__imp_WindowsCreateStringReference
0x180052337  test    eax, eax
0x180052339  jns     short loc_180052351
0x18005233b  xor     r9d, r9d; lpArguments
0x18005233e  xor     r8d, r8d; nNumberOfArguments
0x180052341  lea     edx, [r12+1]; dwExceptionFlags
0x180052346  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005234b  call    cs:__imp_RaiseException
0x180052351  mov     rbx, [rbp+4Fh+string]
0x180052355  mov     rcx, [rbp+4Fh+var_88]
0x180052359  test    rcx, rcx
0x18005235c  jz      short loc_18005236F
0x18005235e  mov     [rbp+4Fh+var_88], r12
0x180052362  mov     rax, [rcx]
0x180052365  mov     rax, [rax+10h]
0x180052369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005236e  nop
0x18005236f  lea     r8, [rbp+4Fh+var_88]
0x180052373  lea     rdx, _GUID_5984c710_daf2_43c8_8bb4_a4d3eacfd03f
0x18005237a  mov     rcx, rbx
0x18005237d  call    cs:__imp_RoGetActivationFactory
0x180052383  mov     ebx, eax
0x180052385  test    eax, eax
0x180052387  js      loc_180052557
0x18005238d  mov     [rbp+4Fh+var_70], r12
0x180052391  mov     r9d, 2
0x180052397  mov     r8, rdi
0x18005239a  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x1800523a1  lea     rcx, [rbp+4Fh+var_70]
0x1800523a5  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x1800523aa  mov     ebx, eax
0x1800523ac  test    eax, eax
0x1800523ae  js      loc_18005250E
0x1800523b4  mov     rcx, [rbp+4Fh+var_70]
0x1800523b8  mov     qword ptr [rbp+4Fh+Buffer], rcx
0x1800523bc  test    rcx, rcx
0x1800523bf  jz      short loc_1800523CE
0x1800523c1  mov     rax, [rcx]
0x1800523c4  mov     rax, [rax+8]
0x1800523c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523cd  nop
0x1800523ce  lea     rdx, [rbp+4Fh+Buffer]
0x1800523d2  lea     rcx, [rbp+4Fh+var_68]
0x1800523d6  call    Microsoft__WRL__Callback_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Storage__IStreamedFileDataRequestedHandler_Microsoft__WRL__FtmBase___lambda_1217fab87f23337cb0d882f1f09c4b7d___
0x1800523db  nop
0x1800523dc  mov     rcx, qword ptr [rbp+4Fh+Buffer]
0x1800523e0  test    rcx, rcx
0x1800523e3  jz      short loc_1800523F2
0x1800523e5  mov     rax, [rcx]
0x1800523e8  mov     rax, [rax+10h]
0x1800523ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523f1  nop
0x1800523f2  mov     rsi, [rbp+4Fh+var_68]
0x1800523f6  test    rsi, rsi
0x1800523f9  jnz     short loc_180052405
0x1800523fb  mov     ebx, 8007000Eh
0x180052400  jmp     loc_1800524F5
0x180052405  mov     qword ptr [rbp+4Fh+Buffer], r12
0x180052409  mov     rdi, [rbp+4Fh+var_88]
0x18005240d  mov     rax, [rdi]
0x180052410  mov     rbx, [rax+40h]
0x180052414  lea     rdx, [rbp+4Fh+var_80]
0x180052418  lea     rcx, [rbp+4Fh+string]
0x18005241c  call    ??$?0PEBG@StringReference@Internal@Windows@@QEAA@AEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x180052421  lea     rcx, [rbp+4Fh+Buffer]
0x180052425  mov     [rsp+0C0h+var_A0], rcx
0x18005242a  xor     r9d, r9d
0x18005242d  mov     r8, rsi
0x180052430  mov     rdx, [rax]
0x180052433  mov     rcx, rdi
0x180052436  mov     rax, rbx
0x180052439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005243e  mov     ebx, eax
0x180052440  test    eax, eax
0x180052442  js      loc_1800524DB
0x180052448  mov     [rbp+4Fh+var_80], r12
0x18005244c  lea     rdx, [rbp+4Fh+var_80]
0x180052450  mov     rcx, qword ptr [rbp+4Fh+Buffer]
0x180052454  call    ??$BlockOnCompletionAndGetResults@PEAVStorageFile@Storage@Windows@@UIStorageFile@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIStorageFile@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Storage::StorageFile *,Windows::Storage::IStorageFile>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile>>,tagCOWAIT_FLAGS,void *)
0x180052459  mov     ebx, eax
0x18005245b  test    eax, eax
0x18005245d  js      short loc_1800524C1
0x18005245f  mov     [rbp+4Fh+var_78], r12
0x180052463  mov     rcx, [rbp+4Fh+var_80]
0x180052467  mov     rax, [rcx]
0x18005246a  lea     r8, [rbp+4Fh+var_78]
0x18005246e  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x180052475  mov     rax, [rax]
0x180052478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005247d  mov     ebx, eax
0x18005247f  test    eax, eax
0x180052481  js      short loc_1800524A7
0x180052483  test    byte ptr [r14], 4
0x180052487  jz      short loc_18005249B
0x180052489  mov     r8d, [r14+24h]; unsigned int
0x18005248d  test    r8d, r8d
0x180052490  jz      short loc_18005249B
0x180052492  mov     rcx, [rbp+4Fh+var_78]; struct Windows::Storage::IStorageItem *
0x180052496  call    ?SetStorageItemUInt32Property@@YAJPEAUIStorageItem@Storage@Windows@@PEBGI@Z; SetStorageItemUInt32Property(Windows::Storage::IStorageItem *,ushort const *,uint)
0x18005249b  mov     rax, [rbp+4Fh+var_78]
0x18005249f  mov     rcx, r12
0x1800524a2  mov     [r15], rax
0x1800524a5  jmp     short loc_1800524AB
0x1800524a7  mov     rcx, [rbp+4Fh+var_78]
0x1800524ab  test    rcx, rcx
0x1800524ae  jz      short loc_1800524C1
0x1800524b0  mov     [rbp+4Fh+var_78], r12
0x1800524b4  mov     rax, [rcx]
0x1800524b7  mov     rax, [rax+10h]
0x1800524bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524c0  nop
0x1800524c1  mov     rcx, [rbp+4Fh+var_80]
0x1800524c5  test    rcx, rcx
0x1800524c8  jz      short loc_1800524DB
0x1800524ca  mov     [rbp+4Fh+var_80], r12
0x1800524ce  mov     rax, [rcx]
0x1800524d1  mov     rax, [rax+10h]
0x1800524d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524da  nop
0x1800524db  mov     rcx, qword ptr [rbp+4Fh+Buffer]
0x1800524df  test    rcx, rcx
0x1800524e2  jz      short loc_1800524F5
0x1800524e4  mov     qword ptr [rbp+4Fh+Buffer], r12
0x1800524e8  mov     rax, [rcx]
0x1800524eb  mov     rax, [rax+10h]
0x1800524ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524f4  nop
0x1800524f5  test    rsi, rsi
0x1800524f8  jz      short loc_18005250A
0x1800524fa  mov     rax, [rsi]
0x1800524fd  mov     rcx, rsi
0x180052500  mov     rax, [rax+10h]
0x180052504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052509  nop
0x18005250a  test    ebx, ebx
0x18005250c  jns     short loc_18005253D
0x18005250e  mov     qword ptr [rbp+4Fh+Buffer], r12
0x180052512  xor     r9d, r9d; cchBufferMax
0x180052515  lea     r8, [rbp+4Fh+Buffer]; lpBuffer
0x180052519  lea     edx, [r9+15h]; uID
0x18005251d  lea     rcx, __ImageBase; hInstance
0x180052524  call    cs:__imp_LoadStringW
0x18005252a  test    eax, eax
0x18005252c  jz      short loc_18005253D
0x18005252e  mov     r8, qword ptr [rbp+4Fh+Buffer]
0x180052532  mov     edx, eax
0x180052534  mov     ecx, ebx
0x180052536  call    cs:__imp_RoOriginateErrorW
0x18005253c  nop
0x18005253d  mov     rcx, [rbp+4Fh+var_70]
0x180052541  test    rcx, rcx
0x180052544  jz      short loc_180052557
0x180052546  mov     [rbp+4Fh+var_70], r12
0x18005254a  mov     rax, [rcx]
0x18005254d  mov     rax, [rax+10h]
0x180052551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052556  nop
0x180052557  mov     rcx, [rbp+4Fh+var_88]
0x18005255b  test    rcx, rcx
0x18005255e  jz      short loc_180052571
0x180052560  mov     [rbp+4Fh+var_88], r12
0x180052564  mov     rax, [rcx]
0x180052567  mov     rax, [rax+10h]
0x18005256b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052570  nop
0x180052571  mov     eax, ebx
0x180052573  mov     rcx, [rbp+4Fh+var_40]
0x180052577  xor     rcx, rsp; StackCookie
0x18005257a  call    __security_check_cookie
0x18005257f  add     rsp, 90h
0x180052586  pop     r15
0x180052588  pop     r14
0x18005258a  pop     r12
0x18005258c  pop     rdi
0x18005258d  pop     rsi
0x18005258e  pop     rbx
0x18005258f  pop     rbp
0x180052590  retn
```
