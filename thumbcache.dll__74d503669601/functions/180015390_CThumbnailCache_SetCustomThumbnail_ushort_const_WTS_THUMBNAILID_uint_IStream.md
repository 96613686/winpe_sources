# CThumbnailCache::SetCustomThumbnail(ushort const *,WTS_THUMBNAILID,uint,IStream *)

- ea: `0x180015390`
- end: `0x1800156ba`
- name: `?SetCustomThumbnail@CThumbnailCache@@UEAAJPEBGUWTS_THUMBNAILID@@IPEAUIStream@@@Z`
- size: `810`
- prototype: `__int64 __fastcall(CThumbnailCache *this, const unsigned __int16 *, struct WTS_THUMBNAILID *, unsigned int, struct IStream *pstmFrom)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x18000c6f4`
- `0x180012e60`
- `0x1800130d0`
- `0x18001455c`
- `0x180014888`
- `0x180015390`
- `0x1800156c0`
- `0x180015798`
- `0x18002f6c0`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180015420`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180015420`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001543d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001543d`

## string_xrefs

- `0x18001555b`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x18001559c`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x18001560f`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x180015640`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x1800156a1`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CThumbnailCache::SetCustomThumbnail(
        CThumbnailCache *this,
        const unsigned __int16 *a2,
        struct WTS_THUMBNAILID *a3,
        unsigned int a4,
        struct IStream *pstmFrom)
{
  int MemStreamCopyOfStream; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  int v11; // eax
  const struct tagSIZE *v12; // r9
  int v13; // eax
  unsigned int NextThumbSizeFromPixelSize; // eax
  struct IBitmapResult *v15; // r10
  int v16; // eax
  __int64 v17; // rcx
  struct IStream *v18; // rcx
  struct IStream *v20; // rcx
  __int64 v21; // rcx
  struct IStream *v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  struct IStream *v25; // rcx
  __int64 v26; // rdx
  int v27; // [rsp+20h] [rbp-B1h]
  int *v28; // [rsp+20h] [rbp-B1h]
  int v29; // [rsp+20h] [rbp-B1h]
  int v30; // [rsp+20h] [rbp-B1h]
  int v31; // [rsp+50h] [rbp-81h] BYREF
  struct IStream *v32; // [rsp+58h] [rbp-79h] BYREF
  struct _GUID v33; // [rsp+60h] [rbp-71h] BYREF
  __int64 v34; // [rsp+70h] [rbp-61h]
  __int64 v35; // [rsp+78h] [rbp-59h] BYREF
  int v36; // [rsp+80h] [rbp-51h]
  int v37; // [rsp+84h] [rbp-4Dh]
  _WORD v38[40]; // [rsp+90h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  v32 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  MemStreamCopyOfStream = MakeMemStreamCopyOfStream(pstmFrom, &v32);
  v9 = MemStreamCopyOfStream;
  if ( MemStreamCopyOfStream < 0 )
  {
    v26 = 5226;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
      (const char *)(unsigned int)MemStreamCopyOfStream,
      v27);
    goto LABEL_22;
  }
  MemStreamCopyOfStream = CThumbnailCache::_Initialize(
                            (CThumbnailCache *)((char *)this - 8),
                            a4 == 0 ? (enum WTS_FLAGS)0x20000000 : WTS_NONE,
                            a4);
  v9 = MemStreamCopyOfStream;
  if ( MemStreamCopyOfStream < 0 )
  {
    v26 = 5229;
    goto LABEL_30;
  }
  _o__ui64tow_s(*(_QWORD *)a3->rgbKey, v38, 33);
  v36 = *((_DWORD *)this + 190) & 1;
  *(_QWORD *)v33.Data4 = 0;
  v35 = 0;
  CoTaskMemFree(0);
  v37 = 0;
  v34 = 0;
  v11 = CThumbnailMoniker::Initialize((__int64)v33.Data4, *(_QWORD *)a3->rgbKey, v38, v10, 2, 19);
  v9 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1475,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
      (const char *)(unsigned int)v11,
      (int)v28);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v35);
    v20 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return v9;
  }
  if ( a4 )
  {
    *(_QWORD *)&v33.Data1 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    v13 = Windows::Internal::Thumbnails::CreateBitmapResult(v32, 0, 0, v12, v28, &v33);
    v9 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x147E,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
        (const char *)(unsigned int)v13,
        v29);
      v21 = *(_QWORD *)&v33.Data1;
      if ( *(_QWORD *)&v33.Data1 )
      {
        *(_QWORD *)&v33.Data1 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v35);
      v22 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
    else
    {
      v31 = 0;
      NextThumbSizeFromPixelSize = CThumbnailCache::_GetNextThumbSizeFromPixelSize((__int64)this - 8, a4);
      v16 = CThumbnailCache::_RecordExtractionTransactionToCache(
              (__int64)this - 8,
              0,
              (struct CThumbnailMoniker *)v33.Data4,
              0,
              NextThumbSizeFromPixelSize,
              v15,
              0,
              0,
              &v31);
      v9 = v16;
      if ( v16 >= 0 )
      {
        v17 = *(_QWORD *)&v33.Data1;
        if ( *(_QWORD *)&v33.Data1 )
        {
          *(_QWORD *)&v33.Data1 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
        goto LABEL_9;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1481,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
        (const char *)(unsigned int)v16,
        v30);
      v24 = *(_QWORD *)&v33.Data1;
      if ( *(_QWORD *)&v33.Data1 )
      {
        *(_QWORD *)&v33.Data1 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v35);
      v25 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v25 + 16LL))(v25);
      }
    }
    return v9;
  }
  v23 = CThumbnailCache::_AddCustomThumbnailStreamToCache(
          (CThumbnailCache *)((char *)this - 8),
          (const struct CThumbnailMoniker *)v33.Data4,
          v32);
  v9 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1479,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
      (const char *)(unsigned int)v23,
      (int)v28);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v35);
LABEL_22:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    return v9;
  }
LABEL_9:
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v35);
  v18 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x180015390  push    rbp
0x180015392  push    rbx
0x180015393  push    rsi
0x180015394  push    rdi
0x180015395  push    r12
0x180015397  push    r14
0x180015399  push    r15
0x18001539b  lea     rbp, [rsp-1Fh]
0x1800153a0  sub     rsp, 0F0h
0x1800153a7  mov     rax, cs:__security_cookie
0x1800153ae  xor     rax, rsp
0x1800153b1  mov     [rbp+4Fh+var_40], rax
0x1800153b5  mov     edi, r9d
0x1800153b8  mov     r15, r8
0x1800153bb  mov     r14, rcx
0x1800153be  mov     rbx, [rbp+4Fh+pstmFrom]
0x1800153c2  xor     r12d, r12d
0x1800153c5  mov     [rbp+4Fh+var_C8], r12
0x1800153c9  lea     rcx, [rbp+4Fh+var_C8]
0x1800153cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800153d2  lea     rdx, [rbp+4Fh+var_C8]; struct IStream **
0x1800153d6  mov     rcx, rbx; pstmFrom
0x1800153d9  call    ?MakeMemStreamCopyOfStream@@YAJPEAUIStream@@PEAPEAU1@@Z; MakeMemStreamCopyOfStream(IStream *,IStream * *)
0x1800153de  mov     ebx, eax
0x1800153e0  test    eax, eax
0x1800153e2  js      loc_180015695
0x1800153e8  lea     rsi, [r14-8]
0x1800153ec  mov     eax, edi
0x1800153ee  neg     eax
0x1800153f0  sbb     edx, edx
0x1800153f2  not     edx
0x1800153f4  and     edx, 20000000h; enum WTS_FLAGS
0x1800153fa  mov     r8d, edi; int
0x1800153fd  mov     rcx, rsi; this
0x180015400  call    ?_Initialize@CThumbnailCache@@AEAAJW4WTS_FLAGS@@H@Z; CThumbnailCache::_Initialize(WTS_FLAGS,int)
0x180015405  mov     ebx, eax
0x180015407  test    eax, eax
0x180015409  js      loc_18001569C
0x18001540f  lea     r9d, [r12+10h]
0x180015414  lea     r8d, [r12+21h]
0x180015419  lea     rdx, [rbp+4Fh+var_90]
0x18001541d  mov     rcx, [r15]
0x180015420  call    cs:__imp__o__ui64tow_s
0x180015426  mov     eax, [r14+2F8h]
0x18001542d  and     eax, 1
0x180015430  mov     [rbp+4Fh+var_A0], eax
0x180015433  mov     qword ptr [rbp+4Fh+var_C0.Data4], r12
0x180015437  mov     [rbp+4Fh+var_A8], r12
0x18001543b  xor     ecx, ecx; pv
0x18001543d  call    cs:__imp_CoTaskMemFree
0x180015443  mov     [rbp+4Fh+var_9C], r12d
0x180015447  mov     [rbp+4Fh+var_B0], r12
0x18001544b  mov     dword ptr [rsp+120h+var_F8], 13h
0x180015453  mov     dword ptr [rsp+120h+var_100], 2; int
0x18001545b  lea     r8, [rbp+4Fh+var_90]
0x18001545f  mov     rdx, [r15]
0x180015462  lea     rcx, [rbp+4Fh+var_C0.Data4]
0x180015466  call    ?Initialize@CThumbnailMoniker@@QEAAJ_KPEBGHW4TRIBIT@@K@Z; CThumbnailMoniker::Initialize(unsigned __int64,ushort const *,int,TRIBIT,ulong)
0x18001546b  mov     ebx, eax
0x18001546d  test    eax, eax
0x18001546f  js      loc_180015554
0x180015475  test    edi, edi
0x180015477  jz      loc_1800155EE
0x18001547d  mov     qword ptr [rbp+4Fh+var_C0.Data1], r12
0x180015481  lea     rcx, [rbp+4Fh+var_C0]
0x180015485  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001548a  lea     rax, [rbp+4Fh+var_C0]
0x18001548e  mov     [rsp+120h+var_F8], rax; struct _GUID *
0x180015493  xor     r8d, r8d; unsigned __int16 *
0x180015496  xor     edx, edx; struct IStream *
0x180015498  mov     rcx, [rbp+4Fh+var_C8]; this
0x18001549c  call    ?CreateBitmapResult@Thumbnails@Internal@Windows@@YAJPEAUIStream@@PEBGPEBUtagSIZE@@PEBHAEBU_GUID@@PEAPEAX@Z; Windows::Internal::Thumbnails::CreateBitmapResult(IStream *,ushort const *,tagSIZE const *,int const *,_GUID const &,void * *)
0x1800154a1  mov     ebx, eax
0x1800154a3  test    eax, eax
0x1800154a5  js      loc_180015595
0x1800154ab  mov     [rsp+120h+var_D0], r12d
0x1800154b0  mov     r10, qword ptr [rbp+4Fh+var_C0.Data1]
0x1800154b4  mov     edx, edi
0x1800154b6  mov     rcx, rsi
0x1800154b9  call    ?_GetNextThumbSizeFromPixelSize@CThumbnailCache@@AEAA?AW4THUMBSIZE@@I@Z; CThumbnailCache::_GetNextThumbSizeFromPixelSize(uint)
0x1800154be  lea     rcx, [rsp+120h+var_D0]
0x1800154c3  mov     [rsp+120h+var_E0], rcx
0x1800154c8  mov     [rsp+120h+var_E8], r12d
0x1800154cd  mov     [rsp+120h+var_F0], r12d
0x1800154d2  mov     [rsp+120h+var_F8], r10
0x1800154d7  mov     dword ptr [rsp+120h+var_100], eax; int
0x1800154db  xor     r9d, r9d
0x1800154de  lea     r8, [rbp+4Fh+var_C0.Data4]
0x1800154e2  xor     edx, edx
0x1800154e4  mov     rcx, rsi
0x1800154e7  call    ?_RecordExtractionTransactionToCache@CThumbnailCache@@AEAAJPEAUIShellItem@@AEAVCThumbnailMoniker@@JW4THUMBSIZE@@PEAUIBitmapResult@@W4WTS_ALPHATYPE@@HPEAH@Z; CThumbnailCache::_RecordExtractionTransactionToCache(IShellItem *,CThumbnailMoniker &,long,THUMBSIZE,IBitmapResult *,WTS_ALPHATYPE,int,int *)
0x1800154ec  mov     ebx, eax
0x1800154ee  test    eax, eax
0x1800154f0  js      loc_180015639
0x1800154f6  mov     rcx, qword ptr [rbp+4Fh+var_C0.Data1]
0x1800154fa  test    rcx, rcx
0x1800154fd  jz      short loc_180015510
0x1800154ff  mov     qword ptr [rbp+4Fh+var_C0.Data1], r12
0x180015503  mov     rax, [rcx]
0x180015506  mov     rax, [rax+10h]
0x18001550a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001550f  nop
0x180015510  lea     rcx, [rbp+4Fh+var_A8]
0x180015514  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180015519  nop
0x18001551a  mov     rcx, [rbp+4Fh+var_C8]
0x18001551e  test    rcx, rcx
0x180015521  jz      short loc_180015534
0x180015523  mov     [rbp+4Fh+var_C8], r12
0x180015527  mov     rax, [rcx]
0x18001552a  mov     rax, [rax+10h]
0x18001552e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015533  nop
0x180015534  xor     eax, eax
0x180015536  mov     rcx, [rbp+4Fh+var_40]
0x18001553a  xor     rcx, rsp; StackCookie
0x18001553d  call    __security_check_cookie
0x180015542  add     rsp, 0F0h
0x180015549  pop     r15
0x18001554b  pop     r14
0x18001554d  pop     r12
0x18001554f  pop     rdi
0x180015550  pop     rsi
0x180015551  pop     rbx
0x180015552  pop     rbp
0x180015553  retn
0x180015554  mov     rcx, [rbp+57h]; this
0x180015558  mov     r9d, ebx; char *
0x18001555b  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180015562  mov     edx, 1475h; void *
0x180015567  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001556c  nop
0x18001556d  lea     rcx, [rbp+4Fh+var_A8]
0x180015571  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180015576  nop
0x180015577  mov     rcx, [rbp+4Fh+var_C8]
0x18001557b  test    rcx, rcx
0x18001557e  jz      short loc_180015591
0x180015580  mov     [rbp+4Fh+var_C8], r12
0x180015584  mov     rax, [rcx]
0x180015587  mov     rax, [rax+10h]
0x18001558b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015590  nop
0x180015591  mov     eax, ebx
0x180015593  jmp     short loc_180015536
0x180015595  mov     rcx, [rbp+57h]; this
0x180015599  mov     r9d, ebx; char *
0x18001559c  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x1800155a3  mov     edx, 147Eh; void *
0x1800155a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800155ad  nop
0x1800155ae  mov     rcx, qword ptr [rbp+4Fh+var_C0.Data1]
0x1800155b2  test    rcx, rcx
0x1800155b5  jz      short loc_1800155C8
0x1800155b7  mov     qword ptr [rbp+4Fh+var_C0.Data1], r12
0x1800155bb  mov     rax, [rcx]
0x1800155be  mov     rax, [rax+10h]
0x1800155c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155c7  nop
0x1800155c8  lea     rcx, [rbp+4Fh+var_A8]
0x1800155cc  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800155d1  nop
0x1800155d2  mov     rcx, [rbp+4Fh+var_C8]
0x1800155d6  test    rcx, rcx
0x1800155d9  jz      short loc_1800155EC
0x1800155db  mov     [rbp+4Fh+var_C8], r12
0x1800155df  mov     rax, [rcx]
0x1800155e2  mov     rax, [rax+10h]
0x1800155e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155eb  nop
0x1800155ec  jmp     short loc_180015591
0x1800155ee  mov     r8, [rbp+4Fh+var_C8]; struct IStream *
0x1800155f2  lea     rdx, [rbp+4Fh+var_C0.Data4]; struct CThumbnailMoniker *
0x1800155f6  mov     rcx, rsi; this
0x1800155f9  call    ?_AddCustomThumbnailStreamToCache@CThumbnailCache@@AEAAJAEBVCThumbnailMoniker@@PEAUIStream@@@Z; CThumbnailCache::_AddCustomThumbnailStreamToCache(CThumbnailMoniker const &,IStream *)
0x1800155fe  mov     ebx, eax
0x180015600  test    eax, eax
0x180015602  jns     loc_180015510
0x180015608  mov     rcx, [rbp+57h]; this
0x18001560c  mov     r9d, eax; char *
0x18001560f  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180015616  mov     edx, 1479h; void *
0x18001561b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015620  nop
0x180015621  lea     rcx, [rbp+4Fh+var_A8]
0x180015625  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001562a  nop
0x18001562b  lea     rcx, [rbp+4Fh+var_C8]
0x18001562f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015634  jmp     loc_180015591
0x180015639  mov     rcx, [rbp+57h]; this
0x18001563d  mov     r9d, ebx; char *
0x180015640  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180015647  mov     edx, 1481h; void *
0x18001564c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015651  nop
0x180015652  mov     rcx, qword ptr [rbp+4Fh+var_C0.Data1]
0x180015656  test    rcx, rcx
0x180015659  jz      short loc_18001566C
0x18001565b  mov     qword ptr [rbp+4Fh+var_C0.Data1], r12
0x18001565f  mov     rax, [rcx]
0x180015662  mov     rax, [rax+10h]
0x180015666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001566b  nop
0x18001566c  lea     rcx, [rbp+4Fh+var_A8]
0x180015670  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180015675  nop
0x180015676  mov     rcx, [rbp+4Fh+var_C8]
0x18001567a  test    rcx, rcx
0x18001567d  jz      short loc_180015690
0x18001567f  mov     [rbp+4Fh+var_C8], r12
0x180015683  mov     rax, [rcx]
0x180015686  mov     rax, [rax+10h]
0x18001568a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001568f  nop
0x180015690  jmp     loc_180015591
0x180015695  mov     edx, 146Ah
0x18001569a  jmp     short loc_1800156A1
0x18001569c  mov     edx, 146Dh; void *
0x1800156a1  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x1800156a8  mov     r9d, eax; char *
0x1800156ab  mov     rcx, [rbp+57h]; this
0x1800156af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800156b4  jmp     loc_18001562B
```
