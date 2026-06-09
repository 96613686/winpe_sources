# CGlobalThumbsDBStore::SetThumbnail(IShellItem2 *,uint,IBitmapResult *)

- ea: `0x1800443fc`
- end: `0x1800446ee`
- name: `?SetThumbnail@CGlobalThumbsDBStore@@QEAAJPEAUIShellItem2@@IPEAUIBitmapResult@@@Z`
- size: `754`
- prototype: `__int64 __fastcall(CGlobalThumbsDBStore *__hidden this, struct IShellItem2 *, unsigned int, struct IBitmapResult *)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800446f4`

## callees

- `0x18000e280`
- `0x18000e4b0`
- `0x18001f98c`
- `0x180024cbc`
- `0x18002b024`
- `0x18002b11c`
- `0x18002da64`
- `0x18002dc80`
- `0x180035830`
- `0x1800364ac`
- `0x1800443d0`
- `0x1800443fc`
- `0x1800447a0`
- `0x180044a74`
- `0x180044c24`
- `0x180049010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18004460e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18004460e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044675`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044675`

## string_xrefs

- `0x18004445b`: `WriteThumbsDB`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CGlobalThumbsDBStore::SetThumbnail(
        CGlobalThumbsDBStore *this,
        struct IShellItem2 *a2,
        __int64 a3,
        struct IBitmapResult *a4)
{
  unsigned int v5; // r15d
  int v8; // r14d
  int Storage; // ebx
  __int64 ContentTypeFromStreamType; // rax
  CGlobalThumbsDBStore *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned __int16 *v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  IStream *pstm; // [rsp+50h] [rbp-B0h] BYREF
  IUnknown *v18; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v19; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD pv[4]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v21; // [rsp+78h] [rbp-88h]
  _BYTE v22[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v23; // [rsp+90h] [rbp-70h]
  _QWORD v24[42]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v25[2]; // [rsp+220h] [rbp+120h] BYREF

  v5 = a3;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(this, Thumbnails_WriteThumbsDB_Start, a3, 1, v25);
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v24,
    "WriteThumbsDB");
  v24[0] = &ThumbnailCacheTelemetry::WriteThumbsDB::`vftable';
  ThumbnailCacheTelemetry::WriteThumbsDB::StartActivity((ThumbnailCacheTelemetry::WriteThumbsDB *)v24);
  _InterlockedAdd((volatile signed __int32 *)this + 10, 1u);
  v8 = CGlobalThumbsDBStore::_CanWrite(this, a2);
  v18 = 0;
  Storage = CGlobalThumbsDBStore::_GetStorage((__int64)this, a2, 1u, v8, &v18);
  if ( Storage >= 0 )
  {
    v15 = 0;
    Storage = CGlobalThumbsDBStore::_GetStreamName(a2, v5, &v15);
    if ( Storage >= 0 )
    {
      if ( v8 )
      {
        pstm = 0;
        Storage = ((__int64 (__fastcall *)(IUnknown *, unsigned __int16 *, __int64, _QWORD, _DWORD, IStream **))v18->lpVtbl[1].QueryInterface)(
                    v18,
                    v15,
                    4198418,
                    0,
                    0,
                    &pstm);
        if ( Storage >= 0 )
        {
          v16 = 0;
          ContentTypeFromStreamType = GetContentTypeFromStreamType(1);
          Storage = (*(__int64 (__fastcall **)(struct IBitmapResult *, __int64, GUID *, __int64 *))(*(_QWORD *)a4 + 56LL))(
                      a4,
                      ContentTypeFromStreamType,
                      &GUID_0000000c_0000_0000_c000_000000000046,
                      &v16);
          if ( Storage >= 0 )
          {
            memset_0(v22, 0, 0x50u);
            Storage = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v16 + 96LL))(v16, v22, 1);
            if ( Storage >= 0 )
            {
              v19 = 0;
              Storage = CGlobalThumbsDBStore::_GetFileHash(v11, a2, &v19);
              if ( Storage >= 0 )
              {
                pv[0] = 24;
                pv[1] = 3;
                pv[2] = v23;
                pv[3] = 0;
                v21 = v19;
                Storage = IStream_Write(pstm, pv, 0x18u);
                if ( Storage >= 0 )
                {
                  v25[0] = 0;
                  v19 = 0;
                  Storage = (*(__int64 (__fastcall **)(__int64, IStream *, __int64, _QWORD *, unsigned __int64 *))(*(_QWORD *)v16 + 56LL))(
                              v16,
                              pstm,
                              v23,
                              v25,
                              &v19);
                }
              }
            }
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pstm);
      }
      else
      {
        ((void (__fastcall *)(IUnknown *, unsigned __int16 *))v18->lpVtbl[4].QueryInterface)(v18, v15);
      }
      CoTaskMemFree(v15);
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 10);
  if ( Storage == -2147287038 || Storage == -2147175932 )
    v12 = 0;
  else
    v12 = (unsigned int)Storage;
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v24, v12);
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(v13, Thumbnails_WriteThumbsDB_Stop, (unsigned int)Storage);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  ThumbnailCacheTelemetry::WriteThumbsDB::~WriteThumbsDB((ThumbnailCacheTelemetry::WriteThumbsDB *)v24);
  return (unsigned int)Storage;
}

```

## disassembly

```asm
0x1800443fc  push    rbp
0x1800443fe  push    rbx
0x1800443ff  push    rsi
0x180044400  push    rdi
0x180044401  push    r12
0x180044403  push    r14
0x180044405  push    r15
0x180044407  lea     rbp, [rsp-140h]
0x18004440f  sub     rsp, 240h
0x180044416  mov     rax, cs:__security_cookie
0x18004441d  xor     rax, rsp
0x180044420  mov     [rbp+170h+var_40], rax
0x180044427  mov     r12, r9
0x18004442a  mov     r15d, r8d
0x18004442d  mov     rsi, rdx
0x180044430  mov     rdi, rcx
0x180044433  mov     ebx, 1
0x180044438  test    cs:Microsoft_Windows_Shell_CoreEnableBits, bl
0x18004443e  jz      short loc_18004445B
0x180044440  lea     rax, [rbp+170h+var_50]
0x180044447  mov     [rsp+270h+var_250], rax
0x18004444c  mov     r9d, ebx
0x18004444f  lea     rdx, Thumbnails_WriteThumbsDB_Start
0x180044456  call    McGenEventWrite_EventWriteTransfer
0x18004445b  lea     rdx, aWritethumbsdb; "WriteThumbsDB"
0x180044462  lea     rcx, [rbp+170h+var_1A0]
0x180044466  call    ??0?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004446b  lea     rcx, ??_7WriteThumbsDB@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::WriteThumbsDB::`vftable'
0x180044472  mov     [rbp+170h+var_1A0], rcx
0x180044476  lea     rcx, [rbp+170h+var_1A0]; this
0x18004447a  call    ?StartActivity@WriteThumbsDB@ThumbnailCacheTelemetry@@QEAAXXZ; ThumbnailCacheTelemetry::WriteThumbsDB::StartActivity(void)
0x18004447f  nop
0x180044480  lock add [rdi+28h], ebx
0x180044484  mov     rdx, rsi; struct IShellItem2 *
0x180044487  mov     rcx, rdi; this
0x18004448a  call    ?_CanWrite@CGlobalThumbsDBStore@@AEAAHPEAUIShellItem2@@@Z; CGlobalThumbsDBStore::_CanWrite(IShellItem2 *)
0x18004448f  mov     r14d, eax
0x180044492  mov     [rsp+270h+var_218], 0
0x18004449b  lea     rax, [rsp+270h+var_218]
0x1800444a0  mov     [rsp+270h+var_250], rax
0x1800444a5  mov     r9d, r14d
0x1800444a8  mov     r8d, ebx
0x1800444ab  mov     rdx, rsi
0x1800444ae  mov     rcx, rdi
0x1800444b1  call    ?_GetStorage@CGlobalThumbsDBStore@@AEAAJPEAUIShellItem2@@W4STORAGEMODE@1@HPEAPEAUIStorage@@@Z; CGlobalThumbsDBStore::_GetStorage(IShellItem2 *,CGlobalThumbsDBStore::STORAGEMODE,int,IStorage * *)
0x1800444b6  mov     ebx, eax
0x1800444b8  test    eax, eax
0x1800444ba  js      loc_18004467B
0x1800444c0  mov     [rsp+270h+var_230], 0
0x1800444c9  lea     r8, [rsp+270h+var_230]; unsigned __int16 **
0x1800444ce  mov     edx, r15d; unsigned int
0x1800444d1  mov     rcx, rsi; struct IShellItem2 *
0x1800444d4  call    ?_GetStreamName@CGlobalThumbsDBStore@@CAJPEAUIShellItem2@@IPEAPEAG@Z; CGlobalThumbsDBStore::_GetStreamName(IShellItem2 *,uint,ushort * *)
0x1800444d9  mov     ebx, eax
0x1800444db  test    eax, eax
0x1800444dd  js      loc_18004467B
0x1800444e3  test    r14d, r14d
0x1800444e6  jnz     short loc_180044503
0x1800444e8  mov     rcx, [rsp+270h+var_218]
0x1800444ed  mov     rax, [rcx]
0x1800444f0  mov     rdx, [rsp+270h+var_230]
0x1800444f5  mov     rax, [rax+60h]
0x1800444f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444fe  jmp     loc_180044670
0x180044503  mov     [rsp+270h+pstm], 0
0x18004450c  mov     rcx, [rsp+270h+var_218]
0x180044511  mov     rax, [rcx]
0x180044514  lea     rdx, [rsp+270h+pstm]
0x180044519  mov     [rsp+270h+var_248], rdx
0x18004451e  mov     dword ptr [rsp+270h+var_250], 0
0x180044526  xor     r9d, r9d
0x180044529  mov     r8d, 401012h
0x18004452f  mov     rdx, [rsp+270h+var_230]
0x180044534  mov     rax, [rax+18h]
0x180044538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004453d  mov     ebx, eax
0x18004453f  test    eax, eax
0x180044541  js      loc_180044666
0x180044547  mov     [rsp+270h+var_228], 0
0x180044550  mov     ecx, 1
0x180044555  call    ?GetContentTypeFromStreamType@@YAPEBGW4WTS_STREAMTYPE@@@Z; GetContentTypeFromStreamType(WTS_STREAMTYPE)
0x18004455a  mov     rdx, [r12]
0x18004455e  mov     r10, [rdx+38h]
0x180044562  lea     r9, [rsp+270h+var_228]
0x180044567  lea     r8, _GUID_0000000c_0000_0000_c000_000000000046
0x18004456e  mov     rdx, rax
0x180044571  mov     rcx, r12
0x180044574  mov     rax, r10
0x180044577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004457c  mov     ebx, eax
0x18004457e  test    eax, eax
0x180044580  js      loc_18004465B
0x180044586  xor     edx, edx; Val
0x180044588  lea     r8d, [rdx+50h]; Size
0x18004458c  lea     rcx, [rbp+170h+var_1F0]; void *
0x180044590  call    memset_0
0x180044595  mov     rcx, [rsp+270h+var_228]
0x18004459a  mov     rax, [rcx]
0x18004459d  mov     r8d, 1
0x1800445a3  lea     rdx, [rbp+170h+var_1F0]
0x1800445a7  mov     rax, [rax+60h]
0x1800445ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445b0  mov     ebx, eax
0x1800445b2  test    eax, eax
0x1800445b4  js      loc_18004465B
0x1800445ba  mov     [rsp+270h+var_210], 0
0x1800445c3  lea     r8, [rsp+270h+var_210]; unsigned __int64 *
0x1800445c8  mov     rdx, rsi; struct IShellItem2 *
0x1800445cb  call    ?_GetFileHash@CGlobalThumbsDBStore@@AEAAJPEAUIShellItem2@@PEA_K@Z; CGlobalThumbsDBStore::_GetFileHash(IShellItem2 *,unsigned __int64 *)
0x1800445d0  mov     ebx, eax
0x1800445d2  test    eax, eax
0x1800445d4  js      loc_18004465B
0x1800445da  mov     r8d, 18h; cb
0x1800445e0  mov     [rsp+270h+pv], r8d
0x1800445e5  mov     [rsp+270h+var_204], 3
0x1800445ed  mov     eax, dword ptr [rbp+170h+var_1E0]
0x1800445f0  mov     [rsp+270h+var_200], eax
0x1800445f4  xor     eax, eax
0x1800445f6  mov     [rsp+270h+var_1FC], eax
0x1800445fa  mov     rax, [rsp+270h+var_210]
0x1800445ff  mov     [rsp+270h+var_1F8], rax
0x180044604  lea     rdx, [rsp+270h+pv]; pv
0x180044609  mov     rcx, [rsp+270h+pstm]; pstm
0x18004460e  call    cs:__imp_IStream_Write
0x180044614  mov     ebx, eax
0x180044616  test    eax, eax
0x180044618  js      short loc_18004465B
0x18004461a  mov     [rbp+170h+var_50], 0
0x180044625  mov     [rsp+270h+var_210], 0
0x18004462e  mov     rcx, [rsp+270h+var_228]
0x180044633  mov     rax, [rcx]
0x180044636  lea     rdx, [rsp+270h+var_210]
0x18004463b  mov     [rsp+270h+var_250], rdx
0x180044640  lea     r9, [rbp+170h+var_50]
0x180044647  mov     r8, [rbp+170h+var_1E0]
0x18004464b  mov     rdx, [rsp+270h+pstm]
0x180044650  mov     rax, [rax+38h]
0x180044654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044659  mov     ebx, eax
0x18004465b  lea     rcx, [rsp+270h+var_228]
0x180044660  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180044665  nop
0x180044666  lea     rcx, [rsp+270h+pstm]
0x18004466b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180044670  mov     rcx, [rsp+270h+var_230]; pv
0x180044675  call    cs:__imp_CoTaskMemFree
0x18004467b  lock dec dword ptr [rdi+28h]
0x18004467f  cmp     ebx, 80030002h
0x180044685  jz      short loc_180044693
0x180044687  cmp     ebx, 8004B204h
0x18004468d  jz      short loc_180044693
0x18004468f  mov     edx, ebx
0x180044691  jmp     short loc_180044695
0x180044693  xor     edx, edx
0x180044695  lea     rcx, [rbp+170h+var_1A0]
0x180044699  call    ?Stop@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004469e  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1800446a5  jz      short loc_1800446B7
0x1800446a7  mov     r8d, ebx
0x1800446aa  lea     rdx, Thumbnails_WriteThumbsDB_Stop
0x1800446b1  call    McTemplateU0q_EventWriteTransfer
0x1800446b6  nop
0x1800446b7  lea     rcx, [rsp+270h+var_218]
0x1800446bc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800446c1  nop
0x1800446c2  lea     rcx, [rbp+170h+var_1A0]; this
0x1800446c6  call    ??1WriteThumbsDB@ThumbnailCacheTelemetry@@QEAA@XZ; ThumbnailCacheTelemetry::WriteThumbsDB::~WriteThumbsDB(void)
0x1800446cb  mov     eax, ebx
0x1800446cd  mov     rcx, [rbp+170h+var_40]
0x1800446d4  xor     rcx, rsp; StackCookie
0x1800446d7  call    __security_check_cookie
0x1800446dc  add     rsp, 240h
0x1800446e3  pop     r15
0x1800446e5  pop     r14
0x1800446e7  pop     r12
0x1800446e9  pop     rdi
0x1800446ea  pop     rsi
0x1800446eb  pop     rbx
0x1800446ec  pop     rbp
0x1800446ed  retn
```
