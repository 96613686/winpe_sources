# CThumbnailCacheInternal::SetCustomThumbnail(HSTRING__ *,unsigned __int64,Windows::Storage::Streams::IRandomAccessStream *)

- ea: `0x18003e890`
- end: `0x18003eac2`
- name: `?SetCustomThumbnail@CThumbnailCacheInternal@@UEAAJPEAUHSTRING__@@_KPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `562`
- prototype: `__int64 __fastcall(CThumbnailCacheInternal *__hidden this, HSTRING string, unsigned __int64, struct Windows::Storage::Streams::IRandomAccessStream *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x18000e280`
- `0x18000e4b0`
- `0x18001a0e8`
- `0x18002a508`
- `0x18002db60`
- `0x18002e2d4`
- `0x180035830`
- `0x18003d1b4`
- `0x18003e890`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ea58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ea6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ea58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ea6d`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x18003e99d`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x18003e99d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e9f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e9f9`

## string_xrefs

- `0x18003e8db`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18003e965`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18003e9b3`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18003ea38`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CThumbnailCacheInternal::SetCustomThumbnail(
        CThumbnailCacheInternal *this,
        HSTRING string,
        unsigned __int64 a3,
        struct Windows::Storage::Streams::IRandomAccessStream *a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  bool v10; // r9
  const struct _GUID *v11; // rdx
  int CustomThumbnailCache; // eax
  int StreamOverRandomAccessStream; // eax
  void *v14; // rsi
  __int64 (__fastcall *v15)(void *, PCWSTR, _QWORD *, _QWORD); // rdi
  int v16; // ebx
  PCWSTR StringRawBuffer; // rax
  int v18; // eax
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  PSRWLOCK SRWLock[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v24[2]; // [rsp+50h] [rbp-B0h] BYREF
  void *v25; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v26[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  if ( IsCallerAllowed((bool)this) )
  {
    if ( !a3 )
    {
      v8 = -2147024809;
      v9 = 872;
      goto LABEL_3;
    }
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v26,
      "SetCustomThumbnail");
    v26[0] = &ThumbnailCacheTelemetry::SetCustomThumbnail::`vftable';
    ThumbnailCacheTelemetry::SetCustomThumbnail::StartActivity(
      (ThumbnailCacheTelemetry::SetCustomThumbnail *)v26,
      v10,
      a3);
    v25 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    CustomThumbnailCache = CThumbnailCacheInternal::GetCustomThumbnailCache(this, v11, &v25);
    v8 = CustomThumbnailCache;
    if ( CustomThumbnailCache >= 0 )
    {
      *(_QWORD *)v24 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
      StreamOverRandomAccessStream = CreateStreamOverRandomAccessStream(
                                       a4,
                                       &GUID_0000000c_0000_0000_c000_000000000046,
                                       v24);
      v8 = StreamOverRandomAccessStream;
      if ( StreamOverRandomAccessStream >= 0 )
      {
        Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, (char *)this + 64);
        v14 = v25;
        v15 = *(__int64 (__fastcall **)(void *, PCWSTR, _QWORD *, _QWORD))(*(_QWORD *)v25 + 120LL);
        v16 = v24[0];
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v23[0] = a3;
        v23[1] = 0;
        v21 = v16;
        v18 = v15(v14, StringRawBuffer, v23, 0);
        v8 = v18;
        if ( v18 >= 0 )
        {
          if ( SRWLock[0] )
            ReleaseSRWLockExclusive(SRWLock[0]);
          wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v26, 0);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
          v8 = 0;
          goto LABEL_17;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x376,
          (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
          (const char *)(unsigned int)v18,
          v21);
        if ( SRWLock[0] )
          ReleaseSRWLockExclusive(SRWLock[0]);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x371,
          (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
          (const char *)(unsigned int)StreamOverRandomAccessStream,
          v20);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36C,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
        (const char *)(unsigned int)CustomThumbnailCache,
        v20);
    }
LABEL_17:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    ThumbnailCacheTelemetry::SetCustomThumbnail::~SetCustomThumbnail((ThumbnailCacheTelemetry::SetCustomThumbnail *)v26);
    return v8;
  }
  v8 = -2147024891;
  v9 = 871;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
    (const char *)v8,
    v20);
  return v8;
}

```

## disassembly

```asm
0x18003e890  push    rbp
0x18003e892  push    rbx
0x18003e893  push    rsi
0x18003e894  push    rdi
0x18003e895  push    r14
0x18003e897  push    r15
0x18003e899  lea     rbp, [rsp-0C8h]
0x18003e8a1  sub     rsp, 1C8h
0x18003e8a8  mov     rax, cs:__security_cookie
0x18003e8af  xor     rax, rsp
0x18003e8b2  mov     [rbp+0F0h+var_40], rax
0x18003e8b9  mov     rdi, r9
0x18003e8bc  mov     r14, r8
0x18003e8bf  mov     r15, rdx
0x18003e8c2  mov     rsi, rcx
0x18003e8c5  call    ?IsCallerAllowed@@YA_N_N@Z; IsCallerAllowed(bool)
0x18003e8ca  mov     r9b, al
0x18003e8cd  test    al, al
0x18003e8cf  jnz     short loc_18003E8F6
0x18003e8d1  mov     ebx, 80070005h
0x18003e8d6  mov     edx, 367h; void *
0x18003e8db  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003e8e2  mov     r9d, ebx; char *
0x18003e8e5  mov     rcx, [rbp+0F8h]; this
0x18003e8ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e8f1  jmp     loc_18003EAA1
0x18003e8f6  test    r14, r14
0x18003e8f9  jnz     short loc_18003E907
0x18003e8fb  mov     ebx, 80070057h
0x18003e900  mov     edx, 368h
0x18003e905  jmp     short loc_18003E8DB
0x18003e907  lea     rdx, aSetcustomthumb; "SetCustomThumbnail"
0x18003e90e  lea     rcx, [rsp+1F0h+var_190]
0x18003e913  call    ??0?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003e918  lea     rcx, ??_7SetCustomThumbnail@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::SetCustomThumbnail::`vftable'
0x18003e91f  mov     [rsp+1F0h+var_190], rcx
0x18003e924  mov     r8, r14; unsigned __int64
0x18003e927  mov     dl, r9b; bool
0x18003e92a  lea     rcx, [rsp+1F0h+var_190]; this
0x18003e92f  call    ?StartActivity@SetCustomThumbnail@ThumbnailCacheTelemetry@@QEAAX_N_K@Z; ThumbnailCacheTelemetry::SetCustomThumbnail::StartActivity(bool,unsigned __int64)
0x18003e934  nop
0x18003e935  mov     [rsp+1F0h+var_198], 0
0x18003e93e  lea     rcx, [rsp+1F0h+var_198]
0x18003e943  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e948  lea     r8, [rsp+1F0h+var_198]; void **
0x18003e94d  mov     rcx, rsi; this
0x18003e950  call    ?GetCustomThumbnailCache@CThumbnailCacheInternal@@AEAAJAEBU_GUID@@PEAPEAX@Z; CThumbnailCacheInternal::GetCustomThumbnailCache(_GUID const &,void * *)
0x18003e955  mov     ebx, eax
0x18003e957  test    eax, eax
0x18003e959  jns     short loc_18003E97B
0x18003e95b  mov     rcx, [rbp+0F8h]; this
0x18003e962  mov     r9d, eax; char *
0x18003e965  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003e96c  mov     edx, 36Ch; void *
0x18003e971  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e976  jmp     loc_18003EA8C
0x18003e97b  mov     qword ptr [rsp+1F0h+var_1A0], 0
0x18003e984  lea     rcx, [rsp+1F0h+var_1A0]
0x18003e989  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e98e  lea     r8, [rsp+1F0h+var_1A0]
0x18003e993  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18003e99a  mov     rcx, rdi
0x18003e99d  call    cs:__imp_CreateStreamOverRandomAccessStream
0x18003e9a3  mov     ebx, eax
0x18003e9a5  test    eax, eax
0x18003e9a7  jns     short loc_18003E9D4
0x18003e9a9  mov     rcx, [rbp+0F8h]; this
0x18003e9b0  mov     r9d, eax; char *
0x18003e9b3  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003e9ba  mov     edx, 371h; void *
0x18003e9bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e9c4  nop
0x18003e9c5  lea     rcx, [rsp+1F0h+var_1A0]
0x18003e9ca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e9cf  jmp     loc_18003EA8C
0x18003e9d4  lea     rdx, [rsi+40h]
0x18003e9d8  lea     rcx, [rsp+1F0h+SRWLock]
0x18003e9dd  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18003e9e2  nop
0x18003e9e3  mov     rsi, [rsp+1F0h+var_198]
0x18003e9e8  mov     rax, [rsi]
0x18003e9eb  mov     rdi, [rax+78h]
0x18003e9ef  mov     rbx, qword ptr [rsp+1F0h+var_1A0]
0x18003e9f4  xor     edx, edx; length
0x18003e9f6  mov     rcx, r15; string
0x18003e9f9  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e9ff  mov     [rsp+1F0h+var_1B0], r14
0x18003ea04  mov     [rsp+1F0h+var_1A8], 0
0x18003ea0d  mov     qword ptr [rsp+1F0h+var_1D0], rbx; int
0x18003ea12  xor     r9d, r9d
0x18003ea15  lea     r8, [rsp+1F0h+var_1B0]
0x18003ea1a  mov     rdx, rax
0x18003ea1d  mov     rcx, rsi
0x18003ea20  mov     rax, rdi
0x18003ea23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea28  mov     ebx, eax
0x18003ea2a  test    eax, eax
0x18003ea2c  jns     short loc_18003EA63
0x18003ea2e  mov     rcx, [rbp+0F8h]; this
0x18003ea35  mov     r9d, eax; char *
0x18003ea38  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003ea3f  mov     edx, 376h; void *
0x18003ea44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ea49  nop
0x18003ea4a  mov     rcx, [rsp+1F0h+SRWLock]; SRWLock
0x18003ea4f  test    rcx, rcx
0x18003ea52  jz      loc_18003E9C5
0x18003ea58  call    cs:__imp_ReleaseSRWLockExclusive
0x18003ea5e  jmp     loc_18003E9C5
0x18003ea63  mov     rcx, [rsp+1F0h+SRWLock]; SRWLock
0x18003ea68  test    rcx, rcx
0x18003ea6b  jz      short loc_18003EA73
0x18003ea6d  call    cs:__imp_ReleaseSRWLockExclusive
0x18003ea73  xor     edx, edx
0x18003ea75  lea     rcx, [rsp+1F0h+var_190]
0x18003ea7a  call    ?Stop@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003ea7f  nop
0x18003ea80  lea     rcx, [rsp+1F0h+var_1A0]
0x18003ea85  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ea8a  xor     ebx, ebx
0x18003ea8c  lea     rcx, [rsp+1F0h+var_198]
0x18003ea91  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ea96  nop
0x18003ea97  lea     rcx, [rsp+1F0h+var_190]; this
0x18003ea9c  call    ??1SetCustomThumbnail@ThumbnailCacheTelemetry@@QEAA@XZ; ThumbnailCacheTelemetry::SetCustomThumbnail::~SetCustomThumbnail(void)
0x18003eaa1  mov     eax, ebx
0x18003eaa3  mov     rcx, [rbp+0F0h+var_40]
0x18003eaaa  xor     rcx, rsp; StackCookie
0x18003eaad  call    __security_check_cookie
0x18003eab2  add     rsp, 1C8h
0x18003eab9  pop     r15
0x18003eabb  pop     r14
0x18003eabd  pop     rdi
0x18003eabe  pop     rsi
0x18003eabf  pop     rbx
0x18003eac0  pop     rbp
0x18003eac1  retn
```
