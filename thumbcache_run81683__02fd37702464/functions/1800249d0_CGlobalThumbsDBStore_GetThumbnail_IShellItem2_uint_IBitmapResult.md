# CGlobalThumbsDBStore::GetThumbnail(IShellItem2 *,uint,IBitmapResult * *)

- ea: `0x1800249d0`
- end: `0x180024cb4`
- name: `?GetThumbnail@CGlobalThumbsDBStore@@QEAAJPEAUIShellItem2@@IPEAPEAUIBitmapResult@@@Z`
- size: `740`
- prototype: `int(CGlobalThumbsDBStore *__hidden this, struct IShellItem2 *, unsigned int, struct IBitmapResult **)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024618`

## callees

- `0x18000e280`
- `0x18000e4b0`
- `0x18000ed30`
- `0x18000ed88`
- `0x18000edf0`
- `0x18000f234`
- `0x1800156c0`
- `0x180015798`
- `0x18001f98c`
- `0x1800249d0`
- `0x180024cbc`
- `0x180024f64`
- `0x18002b024`
- `0x18002b11c`
- `0x18002da64`
- `0x18002dc80`
- `0x180035830`
- `0x180044c24`
- `0x180044f84`
- `0x180049010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180024b3e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180024b3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024bfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024bfa`

## string_xrefs

- `0x180024a33`: `ReadThumbsDB`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CGlobalThumbsDBStore::GetThumbnail(
        CGlobalThumbsDBStore *this,
        struct IShellItem2 *a2,
        __int64 a3,
        const struct _GUID *a4)
{
  unsigned int v5; // r14d
  int Storage; // ebx
  __int64 v9; // rcx
  __int64 v10; // r8
  CGlobalThumbsDBStore *v11; // rcx
  struct IStream *ContentTypeFromStreamType; // rax
  const struct tagSIZE *v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int *v18; // [rsp+20h] [rbp-E0h]
  void **v19; // [rsp+30h] [rbp-D0h]
  IStream *pstm; // [rsp+40h] [rbp-C0h] BYREF
  IUnknown *v21; // [rsp+48h] [rbp-B8h] BYREF
  __int128 pv; // [rsp+50h] [rbp-B0h] BYREF
  struct IStream *v23; // [rsp+60h] [rbp-A0h]
  void **v24; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v25[272]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v26[8]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v27[48]; // [rsp+190h] [rbp+90h] BYREF
  struct IStream *v28[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 *v29[2]; // [rsp+1D0h] [rbp+D0h] BYREF

  v5 = a3;
  *(_QWORD *)&a4->Data1 = 0;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(this, Thumbnails_ReadThumbsDB_Start, a3, 1, v29);
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v24,
    "ReadThumbsDB");
  v24 = &ThumbnailCacheTelemetry::ReadThumbsDB::`vftable';
  ThumbnailCacheTelemetry::ReadThumbsDB::StartActivity((ThumbnailCacheTelemetry::ReadThumbsDB *)&v24);
  v21 = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 10);
  Storage = CGlobalThumbsDBStore::_GetStorage((__int64)this, a2, 0, 0, &v21);
  if ( Storage >= 0 )
  {
    v29[0] = 0;
    Storage = CGlobalThumbsDBStore::_GetStreamName(a2, v5, v29);
    if ( Storage >= 0 )
    {
      pstm = 0;
      LODWORD(v18) = 0;
      Storage = ((__int64 (__fastcall *)(IUnknown *, unsigned __int16 *, _QWORD, __int64))v21->lpVtbl[1].AddRef)(
                  v21,
                  v29[0],
                  0,
                  4194320);
      if ( Storage >= 0 )
      {
        if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(v9, Thumbnails_LoadFromThumbsDB_Start, v10, 1, v28);
        pv = 0;
        v23 = 0;
        Storage = IStream_Read(pstm, &pv, 0x18u);
        if ( Storage >= 0 )
        {
          v28[0] = 0;
          Storage = CGlobalThumbsDBStore::_GetFileHash(v11, a2, (unsigned __int64 *)v28);
          if ( Storage >= 0 )
          {
            if ( DWORD1(pv) == 3 && v23 == v28[0] )
            {
              v28[0] = 0;
              Storage = MakeMemStreamCopyOfStream(pstm, v28);
              if ( Storage >= 0 )
              {
                ContentTypeFromStreamType = (struct IStream *)GetContentTypeFromStreamType(1);
                Storage = Windows::Internal::Thumbnails::CreateBitmapResult(
                            v28[0],
                            ContentTypeFromStreamType,
                            0,
                            v13,
                            v18,
                            a4,
                            v19);
              }
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v28);
            }
            else
            {
              Storage = -2147287038;
            }
          }
        }
        if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
          McTemplateU0q_EventWriteTransfer(v11, Thumbnails_LoadFromThumbsDB_Stop, (unsigned int)Storage);
      }
      CoTaskMemFree(v29[0]);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pstm);
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 10);
  if ( Storage == -2147287038 || Storage == -2147175932 )
    v14 = 0;
  else
    v14 = (unsigned int)Storage;
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v24, v14);
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McTemplateU0dq_EventWriteTransfer(v16, v15, (unsigned int)Storage, v5);
  if ( v21 )
    ((void (__fastcall *)(IUnknown *))v21->lpVtbl->Release)(v21);
  v24 = &ThumbnailCacheTelemetry::ReadThumbsDB::`vftable';
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v24);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v27);
  wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v26);
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v25);
  return (unsigned int)Storage;
}

```

## disassembly

```asm
0x1800249d0  push    rbp
0x1800249d2  push    rbx
0x1800249d3  push    rsi
0x1800249d4  push    rdi
0x1800249d5  push    r14
0x1800249d7  push    r15
0x1800249d9  lea     rbp, [rsp-0F8h]
0x1800249e1  sub     rsp, 1F8h
0x1800249e8  mov     rax, cs:__security_cookie
0x1800249ef  xor     rax, rsp
0x1800249f2  mov     [rbp+120h+var_40], rax
0x1800249f9  mov     r15, r9
0x1800249fc  mov     r14d, r8d
0x1800249ff  mov     rsi, rdx
0x180024a02  mov     rdi, rcx
0x180024a05  mov     qword ptr [r9], 0
0x180024a0c  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180024a13  jz      short loc_180024A33
0x180024a15  lea     rax, [rbp+120h+var_50]
0x180024a1c  mov     [rsp+220h+var_200], rax
0x180024a21  mov     r9d, 1
0x180024a27  lea     rdx, Thumbnails_ReadThumbsDB_Start
0x180024a2e  call    McGenEventWrite_EventWriteTransfer
0x180024a33  lea     rdx, aReadthumbsdb; "ReadThumbsDB"
0x180024a3a  lea     rcx, [rsp+220h+var_1B0]
0x180024a3f  call    ??0?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180024a44  lea     rax, ??_7ReadThumbsDB@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::ReadThumbsDB::`vftable'
0x180024a4b  mov     [rsp+220h+var_1B0], rax
0x180024a50  lea     rcx, [rsp+220h+var_1B0]; this
0x180024a55  call    ?StartActivity@ReadThumbsDB@ThumbnailCacheTelemetry@@QEAAXXZ; ThumbnailCacheTelemetry::ReadThumbsDB::StartActivity(void)
0x180024a5a  nop
0x180024a5b  mov     [rsp+220h+var_1D8], 0
0x180024a64  lock inc dword ptr [rdi+28h]
0x180024a68  lea     rax, [rsp+220h+var_1D8]
0x180024a6d  mov     [rsp+220h+var_200], rax
0x180024a72  xor     r9d, r9d
0x180024a75  xor     r8d, r8d
0x180024a78  mov     rdx, rsi
0x180024a7b  mov     rcx, rdi
0x180024a7e  call    ?_GetStorage@CGlobalThumbsDBStore@@AEAAJPEAUIShellItem2@@W4STORAGEMODE@1@HPEAPEAUIStorage@@@Z; CGlobalThumbsDBStore::_GetStorage(IShellItem2 *,CGlobalThumbsDBStore::STORAGEMODE,int,IStorage * *)
0x180024a83  mov     ebx, eax
0x180024a85  test    eax, eax
0x180024a87  js      loc_180024C0B
0x180024a8d  mov     [rbp+120h+var_50], 0
0x180024a98  lea     r8, [rbp+120h+var_50]; unsigned __int16 **
0x180024a9f  mov     edx, r14d; unsigned int
0x180024aa2  mov     rcx, rsi; struct IShellItem2 *
0x180024aa5  call    ?_GetStreamName@CGlobalThumbsDBStore@@CAJPEAUIShellItem2@@IPEAPEAG@Z; CGlobalThumbsDBStore::_GetStreamName(IShellItem2 *,uint,ushort * *)
0x180024aaa  mov     ebx, eax
0x180024aac  test    eax, eax
0x180024aae  js      loc_180024C0B
0x180024ab4  mov     [rsp+220h+pstm], 0
0x180024abd  mov     rcx, [rsp+220h+var_1D8]
0x180024ac2  mov     rax, [rcx]
0x180024ac5  lea     rdx, [rsp+220h+pstm]
0x180024aca  mov     [rsp+220h+var_1F8], rdx
0x180024acf  mov     dword ptr [rsp+220h+var_200], 0
0x180024ad7  mov     r9d, 400010h
0x180024add  xor     r8d, r8d
0x180024ae0  mov     rdx, [rbp+120h+var_50]
0x180024ae7  mov     rax, [rax+20h]
0x180024aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024af0  mov     ebx, eax
0x180024af2  test    eax, eax
0x180024af4  js      loc_180024BF3
0x180024afa  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180024b01  jz      short loc_180024B21
0x180024b03  lea     rax, [rbp+120h+var_60]
0x180024b0a  mov     [rsp+220h+var_200], rax; int *
0x180024b0f  mov     r9d, 1
0x180024b15  lea     rdx, Thumbnails_LoadFromThumbsDB_Start
0x180024b1c  call    McGenEventWrite_EventWriteTransfer
0x180024b21  xorps   xmm0, xmm0
0x180024b24  xor     eax, eax
0x180024b26  movups  [rsp+220h+pv], xmm0
0x180024b2b  mov     [rsp+220h+var_1C0], rax
0x180024b30  lea     r8d, [rax+18h]; cb
0x180024b34  lea     rdx, [rsp+220h+pv]; pv
0x180024b39  mov     rcx, [rsp+220h+pstm]; pstm
0x180024b3e  call    cs:__imp_IStream_Read
0x180024b44  mov     ebx, eax
0x180024b46  test    eax, eax
0x180024b48  js      loc_180024BDB
0x180024b4e  mov     [rbp+120h+var_60], 0
0x180024b59  lea     r8, [rbp+120h+var_60]; unsigned __int64 *
0x180024b60  mov     rdx, rsi; struct IShellItem2 *
0x180024b63  call    ?_GetFileHash@CGlobalThumbsDBStore@@AEAAJPEAUIShellItem2@@PEA_K@Z; CGlobalThumbsDBStore::_GetFileHash(IShellItem2 *,unsigned __int64 *)
0x180024b68  mov     ebx, eax
0x180024b6a  test    eax, eax
0x180024b6c  js      short loc_180024BDB
0x180024b6e  cmp     dword ptr [rsp+220h+pv+4], 3
0x180024b73  jnz     short loc_180024BD6
0x180024b75  mov     rax, [rbp+120h+var_60]
0x180024b7c  cmp     [rsp+220h+var_1C0], rax
0x180024b81  jnz     short loc_180024BD6
0x180024b83  mov     [rbp+120h+var_60], 0
0x180024b8e  lea     rdx, [rbp+120h+var_60]; struct IStream **
0x180024b95  mov     rcx, [rsp+220h+pstm]; pstmFrom
0x180024b9a  call    ?MakeMemStreamCopyOfStream@@YAJPEAUIStream@@PEAPEAU1@@Z; MakeMemStreamCopyOfStream(IStream *,IStream * *)
0x180024b9f  mov     ebx, eax
0x180024ba1  test    eax, eax
0x180024ba3  js      short loc_180024BC8
0x180024ba5  mov     ecx, 1
0x180024baa  call    ?GetContentTypeFromStreamType@@YAPEBGW4WTS_STREAMTYPE@@@Z; GetContentTypeFromStreamType(WTS_STREAMTYPE)
0x180024baf  mov     [rsp+220h+var_1F8], r15; struct _GUID *
0x180024bb4  xor     r8d, r8d; unsigned __int16 *
0x180024bb7  mov     rdx, rax; struct IStream *
0x180024bba  mov     rcx, [rbp+120h+var_60]; this
0x180024bc1  call    ?CreateBitmapResult@Thumbnails@Internal@Windows@@YAJPEAUIStream@@PEBGPEBUtagSIZE@@PEBHAEBU_GUID@@PEAPEAX@Z; Windows::Internal::Thumbnails::CreateBitmapResult(IStream *,ushort const *,tagSIZE const *,int const *,_GUID const &,void * *)
0x180024bc6  mov     ebx, eax
0x180024bc8  lea     rcx, [rbp+120h+var_60]
0x180024bcf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180024bd4  jmp     short loc_180024BDB
0x180024bd6  mov     ebx, 80030002h
0x180024bdb  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180024be2  jz      short loc_180024BF3
0x180024be4  mov     r8d, ebx
0x180024be7  lea     rdx, Thumbnails_LoadFromThumbsDB_Stop
0x180024bee  call    McTemplateU0q_EventWriteTransfer
0x180024bf3  mov     rcx, [rbp+120h+var_50]; pv
0x180024bfa  call    cs:__imp_CoTaskMemFree
0x180024c00  nop
0x180024c01  lea     rcx, [rsp+220h+pstm]
0x180024c06  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180024c0b  lock dec dword ptr [rdi+28h]
0x180024c0f  cmp     ebx, 80030002h
0x180024c15  jz      short loc_180024C23
0x180024c17  cmp     ebx, 8004B204h
0x180024c1d  jz      short loc_180024C23
0x180024c1f  mov     edx, ebx
0x180024c21  jmp     short loc_180024C25
0x180024c23  xor     edx, edx
0x180024c25  lea     rcx, [rsp+220h+var_1B0]
0x180024c2a  call    ?Stop@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180024c2f  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180024c36  jz      short loc_180024C44
0x180024c38  mov     r9d, r14d
0x180024c3b  mov     r8d, ebx
0x180024c3e  call    McTemplateU0dq_EventWriteTransfer
0x180024c43  nop
0x180024c44  mov     rcx, [rsp+220h+var_1D8]
0x180024c49  test    rcx, rcx
0x180024c4c  jz      short loc_180024C5B
0x180024c4e  mov     rax, [rcx]
0x180024c51  mov     rax, [rax+10h]
0x180024c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c5a  nop
0x180024c5b  lea     rax, ??_7ReadThumbsDB@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::ReadThumbsDB::`vftable'
0x180024c62  mov     [rsp+220h+var_1B0], rax
0x180024c67  lea     rcx, [rsp+220h+var_1B0]
0x180024c6c  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180024c71  lea     rcx, [rbp+120h+var_90]; this
0x180024c78  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180024c7d  lea     rcx, [rbp+120h+var_98]
0x180024c84  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180024c89  lea     rcx, [rsp+220h+var_1A8]
0x180024c8e  call    ??1?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180024c93  mov     eax, ebx
0x180024c95  mov     rcx, [rbp+120h+var_40]
0x180024c9c  xor     rcx, rsp; StackCookie
0x180024c9f  call    __security_check_cookie
0x180024ca4  add     rsp, 1F8h
0x180024cab  pop     r15
0x180024cad  pop     r14
0x180024caf  pop     rdi
0x180024cb0  pop     rsi
0x180024cb1  pop     rbx
0x180024cb2  pop     rbp
0x180024cb3  retn
```
