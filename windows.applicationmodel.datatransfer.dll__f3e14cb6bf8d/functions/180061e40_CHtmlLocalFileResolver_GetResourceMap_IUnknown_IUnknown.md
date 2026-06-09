# CHtmlLocalFileResolver::GetResourceMap(IUnknown *,IUnknown * *)

- ea: `0x180061e40`
- end: `0x180062178`
- name: `?GetResourceMap@CHtmlLocalFileResolver@@UEAAJPEAUIUnknown@@PEAPEAU2@@Z`
- size: `824`
- prototype: `__int64 __fastcall(CHtmlLocalFileResolver *__hidden this, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002ad0`
- `0x180005504`
- `0x18003f950`
- `0x180045a60`
- `0x18004ebbc`
- `0x180060a1c`
- `0x180060c4c`
- `0x180061e40`
- `0x180062c2c`
- `0x18006556c`
- `0x18007e450`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061fd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061fd6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180061fed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180061fed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062048`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800620cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800620f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800620cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800620f8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180062022`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180062022`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800620d8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800620d8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18006206e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18006206e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006203a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006203a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006210c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006210c`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x180062118`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x180062118`

## string_xrefs

- `0x180061fcf`: `Windows.Storage.Streams.RandomAccessStreamReference`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CHtmlLocalFileResolver::GetResourceMap(
        CHtmlLocalFileResolver *this,
        struct IUnknown *a2,
        struct IUnknown **a3)
{
  int ActivationFactory; // ebx
  void *v5; // rax
  __int64 v6; // rdi
  _DWORD *v7; // rax
  LPVOID v8; // rax
  char *v9; // rdi
  HSTRING v10; // rbx
  __int64 v11; // rcx
  HBITMAP hBitmap; // rsi
  const char *v13; // rbx
  signed int LastError; // eax
  SIZE_T v15; // rax
  unsigned __int64 v16; // rax
  struct IDataObject *v17; // rcx
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h]
  struct IDataObject *v21; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v22[3]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  STGMEDIUM v24; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v25[3]; // [rsp+80h] [rbp-80h] BYREF
  HSTRING string; // [rsp+98h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v28; // [rsp+C0h] [rbp-40h] BYREF
  char v29; // [rsp+C8h] [rbp-38h]
  __int16 v30; // [rsp+CAh] [rbp-36h]

  *a3 = 0;
  v21 = 0;
  ActivationFactory = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IDataObject **))a2->lpVtbl->QueryInterface)(
                        a2,
                        &GUID_0000010e_0000_0000_c000_000000000046,
                        &v21);
  if ( ActivationFactory < 0 )
    goto LABEL_38;
  v20 = 0;
  v5 = operator new(0xC0u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v5 )
  {
    v6 = 0;
    goto LABEL_8;
  }
  v6 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>(v5);
  if ( !v6 )
  {
LABEL_8:
    ActivationFactory = -2147024882;
    goto LABEL_9;
  }
  v7 = operator new(4u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v7 )
  {
    *(_QWORD *)(v6 + 176) = 0;
    goto LABEL_8;
  }
  *v7 = 1;
  *(_QWORD *)(v6 + 176) = v7;
  *(_BYTE *)(v6 + 184) = 1;
  v20 = v6;
  v6 = 0;
  ActivationFactory = 0;
LABEL_9:
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( ActivationFactory >= 0 )
  {
    v24.tymed = 0;
    *(_OWORD *)&v24.hBitmap = 0;
    pv = 0;
    v25[0] = 0;
    v25[1] = (unsigned __int16 *)-1LL;
    v25[2] = (unsigned __int16 *)-1LL;
    ActivationFactory = CHtmlLocalFileResolver::s_ValidateCallerAndClipboardContent(v21, word_1800AA626, &pv, v25, &v24);
    if ( ActivationFactory < 0 )
    {
      v9 = (char *)pv;
    }
    else
    {
      v22[0] = &CLocalFileResMapGenerator::`vftable';
      v8 = pv;
      v9 = 0;
      pv = 0;
      v22[1] = v8;
      v22[2] = v20;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
      v23 = 0;
      if ( WindowsCreateStringReference(
             L"Windows.Storage.Streams.RandomAccessStreamReference",
             0x33u,
             &hstringHeader,
             &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v10 = string;
      v11 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      ActivationFactory = RoGetActivationFactory(v10, &GUID_857309dc_3fbf_4e7d_986f_ef3b1a07a964, &v23);
      if ( ActivationFactory >= 0 )
      {
        hBitmap = v24.hBitmap;
        v13 = (const char *)GlobalLock(v24.hBitmap);
        if ( v13 )
        {
          v15 = GlobalSize(v24.hBitmap);
          v16 = StringNzCbSize(v13, v15);
          v28 = v22;
          v29 = 0;
          v30 = 48;
          pv = 0;
          ActivationFactory = CHtmlProcessor::ProcessHtml((CHtmlProcessor *)&v28, v13, v16, (char **)&pv);
          if ( ActivationFactory >= 0 )
            ActivationFactory = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *> *>,Microsoft::WRL::FtmBase>::QueryInterface(
                                  v20,
                                  &GUID_00000000_0000_0000_c000_000000000046,
                                  a3);
          CoTaskMemFree(pv);
          GlobalUnlock(hBitmap);
        }
        else
        {
          LastError = GetLastError();
          ActivationFactory = LastError;
          if ( LastError > 0 )
            ActivationFactory = (unsigned __int16)LastError | 0x80070000;
          if ( ActivationFactory >= 0 )
            ActivationFactory = -2147467259;
        }
      }
      CLocalFileResMapGenerator::~CLocalFileResMapGenerator((CLocalFileResMapGenerator *)v22);
    }
    if ( v25[0] )
      CoTaskMemFree(v25[0]);
    if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v9);
    ReleaseStgMedium(&v24);
  }
  if ( v20 )
  {
    v20 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *> *>,Microsoft::WRL::FtmBase>::Release();
  }
LABEL_38:
  v17 = v21;
  if ( v21 )
  {
    v21 = 0;
    ((void (__fastcall *)(struct IDataObject *))v17->lpVtbl->Release)(v17);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180061e40  mov     [rsp-8+arg_0], rbx
0x180061e45  push    rbp
0x180061e46  push    rsi
0x180061e47  push    rdi
0x180061e48  push    r14
0x180061e4a  push    r15
0x180061e4c  lea     rbp, [rsp-1030h]
0x180061e54  mov     eax, 1130h
0x180061e59  call    _alloca_probe
0x180061e5e  sub     rsp, rax
0x180061e61  mov     rax, cs:__security_cookie
0x180061e68  xor     rax, rsp
0x180061e6b  mov     [rbp+1050h+var_30], rax
0x180061e72  mov     r14, r8
0x180061e75  mov     rcx, rdx
0x180061e78  xor     r15d, r15d
0x180061e7b  mov     [r8], r15
0x180061e7e  mov     [rsp+1150h+var_1110], r15
0x180061e83  mov     rax, [rdx]
0x180061e86  lea     r8, [rsp+1150h+var_1110]
0x180061e8b  lea     rdx, _GUID_0000010e_0000_0000_c000_000000000046
0x180061e92  mov     rax, [rax]
0x180061e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061e9a  mov     ebx, eax
0x180061e9c  test    eax, eax
0x180061e9e  js      loc_180062134
0x180061ea4  mov     [rsp+1150h+var_1118], r15
0x180061ea9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180061eb0  mov     ecx, 0C0h; unsigned __int64
0x180061eb5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180061eba  lea     esi, [r15+1]
0x180061ebe  test    rax, rax
0x180061ec1  jz      short loc_180061F0D
0x180061ec3  mov     rcx, rax
0x180061ec6  call    ??0?$HashMap@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@7895@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultHash@PEAUHSTRING__@@@1234@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::permission)
0x180061ecb  mov     rdi, rax
0x180061ece  test    rax, rax
0x180061ed1  jz      short loc_180061F10
0x180061ed3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180061eda  lea     ecx, [rsi+3]; unsigned __int64
0x180061edd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180061ee2  test    rax, rax
0x180061ee5  jz      short loc_180061F04
0x180061ee7  mov     [rax], esi
0x180061ee9  mov     [rdi+0B0h], rax
0x180061ef0  mov     [rdi+0B8h], sil
0x180061ef7  mov     [rsp+1150h+var_1118], rdi
0x180061efc  mov     edi, r15d
0x180061eff  mov     ebx, r15d
0x180061f02  jmp     short loc_180061F15
0x180061f04  mov     [rdi+0B0h], r15
0x180061f0b  jmp     short loc_180061F10
0x180061f0d  mov     rdi, r15
0x180061f10  mov     ebx, 8007000Eh
0x180061f15  test    rdi, rdi
0x180061f18  jz      short loc_180061F2A
0x180061f1a  mov     rax, [rdi]
0x180061f1d  mov     rcx, rdi
0x180061f20  mov     rax, [rax+10h]
0x180061f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f29  nop
0x180061f2a  test    ebx, ebx
0x180061f2c  js      loc_18006211F
0x180061f32  mov     [rsp+1150h+var_10E8.tymed], r15d
0x180061f37  xorps   xmm0, xmm0
0x180061f3a  movdqu  xmmword ptr [rsp+1150h+var_10E8.8], xmm0
0x180061f40  mov     [rsp+1150h+pv], r15
0x180061f45  mov     [rbp+1050h+var_10D0], r15
0x180061f49  or      rax, 0FFFFFFFFFFFFFFFFh
0x180061f4d  mov     [rbp+1050h+var_10C8], rax
0x180061f51  mov     [rbp+1050h+var_10C0], rax
0x180061f55  lea     rax, [rsp+1150h+var_10E8]
0x180061f5a  mov     [rsp+1150h+var_1130], rax; struct tagSTGMEDIUM *
0x180061f5f  lea     r9, [rbp+1050h+var_10D0]; unsigned __int16 **
0x180061f63  lea     r8, [rsp+1150h+pv]; void **
0x180061f68  movzx   edx, cs:word_1800AA626; unsigned __int16
0x180061f6f  mov     rcx, [rsp+1150h+var_1110]; struct IDataObject *
0x180061f74  call    ?s_ValidateCallerAndClipboardContent@CHtmlLocalFileResolver@@CAJPEAUIDataObject@@GPEAPEAXPEAPEAGPEAUtagSTGMEDIUM@@@Z; CHtmlLocalFileResolver::s_ValidateCallerAndClipboardContent(IDataObject *,ushort,void * *,ushort * *,tagSTGMEDIUM *)
0x180061f79  mov     ebx, eax
0x180061f7b  test    eax, eax
0x180061f7d  js      loc_1800620EA
0x180061f83  lea     rax, ??_7CLocalFileResMapGenerator@@6B@; const CLocalFileResMapGenerator::`vftable'
0x180061f8a  mov     [rsp+1150h+var_1108], rax
0x180061f8f  mov     rax, [rsp+1150h+pv]
0x180061f94  mov     rdi, r15
0x180061f97  mov     [rsp+1150h+pv], r15
0x180061f9c  mov     [rsp+1150h+var_1100], rax
0x180061fa1  mov     rcx, [rsp+1150h+var_1118]
0x180061fa6  mov     [rsp+1150h+var_10F8], rcx
0x180061fab  test    rcx, rcx
0x180061fae  jz      short loc_180061FBD
0x180061fb0  mov     rax, [rcx]
0x180061fb3  mov     rax, [rax+8]
0x180061fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061fbc  nop
0x180061fbd  mov     [rsp+1150h+var_10F0], r15
0x180061fc2  lea     r9, [rbp+1050h+string]; string
0x180061fc6  lea     r8, [rbp+1050h+hstringHeader]; hstringHeader
0x180061fca  mov     edx, 33h ; '3'; length
0x180061fcf  lea     rcx, ?RuntimeClass_Windows_Storage_Streams_RandomAccessStreamReference@@3QBGB; "Windows.Storage.Streams.RandomAccessStr"...
0x180061fd6  call    cs:__imp_WindowsCreateStringReference
0x180061fdc  test    eax, eax
0x180061fde  jns     short loc_180061FF3
0x180061fe0  xor     r9d, r9d; lpArguments
0x180061fe3  xor     r8d, r8d; nNumberOfArguments
0x180061fe6  mov     edx, esi; dwExceptionFlags
0x180061fe8  mov     ecx, 0C000000Dh; dwExceptionCode
0x180061fed  call    cs:__imp_RaiseException
0x180061ff3  mov     rbx, [rbp+1050h+string]
0x180061ff7  mov     rcx, [rsp+1150h+var_10F0]
0x180061ffc  test    rcx, rcx
0x180061fff  jz      short loc_180062013
0x180062001  mov     [rsp+1150h+var_10F0], r15
0x180062006  mov     rax, [rcx]
0x180062009  mov     rax, [rax+10h]
0x18006200d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062012  nop
0x180062013  lea     r8, [rsp+1150h+var_10F0]
0x180062018  lea     rdx, _GUID_857309dc_3fbf_4e7d_986f_ef3b1a07a964
0x18006201f  mov     rcx, rbx
0x180062022  call    cs:__imp_RoGetActivationFactory
0x180062028  mov     ebx, eax
0x18006202a  test    eax, eax
0x18006202c  js      loc_1800620DE
0x180062032  mov     rsi, qword ptr [rsp+1150h+var_10E8.8]
0x180062037  mov     rcx, rsi; hMem
0x18006203a  call    cs:__imp_GlobalLock
0x180062040  mov     rbx, rax
0x180062043  test    rax, rax
0x180062046  jnz     short loc_180062069
0x180062048  call    cs:__imp_GetLastError
0x18006204e  mov     ebx, eax
0x180062050  test    eax, eax
0x180062052  jle     short loc_18006205D
0x180062054  movzx   ebx, ax
0x180062057  or      ebx, 80070000h
0x18006205d  mov     eax, 80004005h
0x180062062  test    ebx, ebx
0x180062064  cmovns  ebx, eax
0x180062067  jmp     short loc_1800620DE
0x180062069  mov     rcx, qword ptr [rsp+1150h+var_10E8.8]; hMem
0x18006206e  call    cs:__imp_GlobalSize
0x180062074  mov     rdx, rax; unsigned __int64
0x180062077  mov     rcx, rbx; char *
0x18006207a  call    ?StringNzCbSize@@YA_KPEBD_K@Z; StringNzCbSize(char const *,unsigned __int64)
0x18006207f  lea     rcx, [rsp+1150h+var_1108]
0x180062084  mov     [rbp+1050h+var_1090], rcx
0x180062088  mov     [rbp+1050h+var_1088], r15b
0x18006208c  mov     ecx, 30h ; '0'
0x180062091  mov     [rbp+1050h+var_1086], cx
0x180062095  mov     [rsp+1150h+pv], r15
0x18006209a  lea     r9, [rsp+1150h+pv]; char **
0x18006209f  mov     r8, rax; unsigned __int64
0x1800620a2  mov     rdx, rbx; char *
0x1800620a5  lea     rcx, [rbp+1050h+var_1090]; this
0x1800620a9  call    ?ProcessHtml@CHtmlProcessor@@QEAAJPEBD_KPEAPEAD@Z; CHtmlProcessor::ProcessHtml(char const *,unsigned __int64,char * *)
0x1800620ae  mov     ebx, eax
0x1800620b0  test    eax, eax
0x1800620b2  js      short loc_1800620CA
0x1800620b4  mov     r8, r14
0x1800620b7  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800620be  mov     rcx, [rsp+1150h+var_1118]
0x1800620c3  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMap@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Collections@Foundation@Windows@@@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *> *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)
0x1800620c8  mov     ebx, eax
0x1800620ca  mov     rcx, [rsp+1150h+pv]; pv
0x1800620cf  call    cs:__imp_CoTaskMemFree
0x1800620d5  mov     rcx, rsi; hMem
0x1800620d8  call    cs:__imp_GlobalUnlock
0x1800620de  lea     rcx, [rsp+1150h+var_1108]; this
0x1800620e3  call    ??1CLocalFileResMapGenerator@@QEAA@XZ; CLocalFileResMapGenerator::~CLocalFileResMapGenerator(void)
0x1800620e8  jmp     short loc_1800620EF
0x1800620ea  mov     rdi, [rsp+1150h+pv]
0x1800620ef  mov     rcx, [rbp+1050h+var_10D0]; pv
0x1800620f3  test    rcx, rcx
0x1800620f6  jz      short loc_1800620FF
0x1800620f8  call    cs:__imp_CoTaskMemFree
0x1800620fe  nop
0x1800620ff  lea     rax, [rdi-1]
0x180062103  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180062107  ja      short loc_180062113
0x180062109  mov     rcx, rdi; hObject
0x18006210c  call    cs:__imp_CloseHandle
0x180062112  nop
0x180062113  lea     rcx, [rsp+1150h+var_10E8]; LPSTGMEDIUM
0x180062118  call    cs:__imp_ReleaseStgMedium
0x18006211e  nop
0x18006211f  mov     rcx, [rsp+1150h+var_1118]
0x180062124  test    rcx, rcx
0x180062127  jz      short loc_180062134
0x180062129  mov     [rsp+1150h+var_1118], r15
0x18006212e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMap@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Collections@Foundation@Windows@@@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *> *>,Microsoft::WRL::FtmBase>::Release(void)
0x180062133  nop
0x180062134  mov     rcx, [rsp+1150h+var_1110]
0x180062139  test    rcx, rcx
0x18006213c  jz      short loc_180062150
0x18006213e  mov     [rsp+1150h+var_1110], r15
0x180062143  mov     rax, [rcx]
0x180062146  mov     rax, [rax+10h]
0x18006214a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006214f  nop
0x180062150  mov     eax, ebx
0x180062152  mov     rcx, [rbp+1050h+var_30]
0x180062159  xor     rcx, rsp; StackCookie
0x18006215c  call    __security_check_cookie
0x180062161  mov     rbx, [rsp+1150h+arg_0]
0x180062169  add     rsp, 1130h
0x180062170  pop     r15
0x180062172  pop     r14
0x180062174  pop     rdi
0x180062175  pop     rsi
0x180062176  pop     rbp
0x180062177  retn
```
