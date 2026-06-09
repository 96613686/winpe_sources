# CStorageThumbnailCache::SetThumbnail(HSTRING__ *,unsigned __int64,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStream *)

- ea: `0x18002ff10`
- end: `0x180030192`
- name: `?SetThumbnail@CStorageThumbnailCache@@UEAAJPEAUHSTRING__@@_KUSize@Foundation@Windows@@PEAUIRandomAccessStream@Streams@Storage@5@@Z`
- size: `642`
- prototype: `__int64 __fastcall(CStorageThumbnailCache *, __int64, unsigned __int64, RTL_SRWLOCK *, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x18000e280`
- `0x18000e4b0`
- `0x18001a000`
- `0x18001a0e8`
- `0x18002a508`
- `0x18002db60`
- `0x18002e2d4`
- `0x18002ff10`
- `0x180035830`
- `0x18003c080`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800300f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003010e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800300f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003010e`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x18002fff0`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x18002fff0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030098`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030098`

## string_xrefs

- `0x18002ff74`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x180030006`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18003004c`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x1800300d9`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CStorageThumbnailCache::SetThumbnail(
        RTL_SRWLOCK *a1,
        __int64 a2,
        unsigned __int64 a3,
        RTL_SRWLOCK *a4,
        __int64 a5)
{
  float v7; // xmm6_4
  float v8; // xmm7_4
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int StreamOverRandomAccessStream; // eax
  const struct _GUID *v12; // rdx
  int ThumbnailCache; // eax
  void *v14; // rsi
  __int64 (__fastcall *v15)(void *, PCWSTR, HSTRING **, _QWORD); // rdi
  int v16; // ebx
  PCWSTR StringRawBuffer; // rax
  int v18; // eax
  int v20; // [rsp+28h] [rbp-E0h]
  int v21; // [rsp+28h] [rbp-E0h]
  PSRWLOCK SRWLock[2]; // [rsp+38h] [rbp-D0h] BYREF
  HSTRING *p_string; // [rsp+48h] [rbp-C0h] BYREF
  void **v24; // [rsp+50h] [rbp-B8h]
  RTL_SRWLOCK *v25; // [rsp+58h] [rbp-B0h]
  HSTRING string; // [rsp+68h] [rbp-A0h] BYREF
  void *v27; // [rsp+70h] [rbp-98h] BYREF
  int v28[4]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v29[42]; // [rsp+88h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+240h] [rbp+138h]

  v7 = *(float *)&a4;
  SRWLock[0] = a4;
  string = (HSTRING)a2;
  v8 = *((float *)&a4 + 1);
  if ( a3 )
  {
    if ( !IsCallerAllowed((__int64)a1, a2) )
    {
      v9 = -2147024891;
      v10 = 1086;
      goto LABEL_3;
    }
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v29,
      "SetCustomThumbnail");
    v29[0] = &ThumbnailCacheTelemetry::SetCustomThumbnail::`vftable';
    ThumbnailCacheTelemetry::SetCustomThumbnail::StartActivity(
      (ThumbnailCacheTelemetry::SetCustomThumbnail *)v29,
      1,
      a3);
    *(_QWORD *)v28 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v28);
    StreamOverRandomAccessStream = CreateStreamOverRandomAccessStream(
                                     a5,
                                     &GUID_0000000c_0000_0000_c000_000000000046,
                                     v28);
    v9 = StreamOverRandomAccessStream;
    if ( StreamOverRandomAccessStream >= 0 )
    {
      v27 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
      ThumbnailCache = CStorageThumbnailCache::GetThumbnailCache(a1, v12, &v27);
      v9 = ThumbnailCache;
      if ( ThumbnailCache >= 0 )
      {
        Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, &a1[8]);
        v14 = v27;
        v15 = *(__int64 (__fastcall **)(void *, PCWSTR, HSTRING **, _QWORD))(*(_QWORD *)v27 + 120LL);
        v16 = v28[0];
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        p_string = (HSTRING *)a3;
        v24 = 0;
        v21 = v16;
        v18 = v15(v14, StringRawBuffer, &p_string, (unsigned int)(int)fmaxf(v7, v8));
        v9 = v18;
        if ( v18 >= 0 )
        {
          if ( SRWLock[0] )
            ReleaseSRWLockExclusive(SRWLock[0]);
          p_string = &string;
          v24 = &v27;
          v25 = a1;
          _lambda_639341b02e32c8ae0d65114f396fb9ff_::operator()((__int64)&p_string);
          wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v29, 0);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
          v9 = 0;
          goto LABEL_17;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x44F,
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
          (void *)0x44A,
          (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
          (const char *)(unsigned int)ThumbnailCache,
          v20);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x445,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
        (const char *)(unsigned int)StreamOverRandomAccessStream,
        v20);
    }
LABEL_17:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v28);
    ThumbnailCacheTelemetry::SetCustomThumbnail::~SetCustomThumbnail((ThumbnailCacheTelemetry::SetCustomThumbnail *)v29);
    return v9;
  }
  v9 = -2147024809;
  v10 = 1085;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
    (const char *)v9,
    v20);
  return v9;
}

```

## disassembly

```asm
0x18002ff10  mov     rax, rsp
0x18002ff13  push    rbp
0x18002ff14  push    rbx
0x18002ff15  push    rsi
0x18002ff16  push    rdi
0x18002ff17  push    r14
0x18002ff19  push    r15
0x18002ff1b  lea     rbp, [rax-138h]
0x18002ff22  sub     rsp, 208h
0x18002ff29  movaps  xmmword ptr [rax-48h], xmm6
0x18002ff2d  movaps  xmmword ptr [rax-58h], xmm7
0x18002ff31  mov     rax, cs:__security_cookie
0x18002ff38  xor     rax, rsp
0x18002ff3b  mov     [rbp+130h+var_60], rax
0x18002ff42  mov     r15, r8
0x18002ff45  mov     r14, rcx
0x18002ff48  movq    xmm6, r9
0x18002ff4d  movsd   [rsp+230h+SRWLock], xmm6
0x18002ff53  mov     [rsp+230h+string], rdx
0x18002ff58  movss   xmm7, dword ptr [rsp+230h+SRWLock+4]
0x18002ff5e  mov     rbx, [rbp+130h+arg_20]
0x18002ff65  test    r8, r8
0x18002ff68  jnz     short loc_18002FF8F
0x18002ff6a  mov     ebx, 80070057h
0x18002ff6f  mov     edx, 43Dh; void *
0x18002ff74  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18002ff7b  mov     r9d, ebx; char *
0x18002ff7e  mov     rcx, [rbp+138h]; this
0x18002ff85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ff8a  jmp     loc_180030163
0x18002ff8f  call    ?IsCallerAllowed@@YA_N_N@Z; IsCallerAllowed(bool)
0x18002ff94  test    al, al
0x18002ff96  jnz     short loc_18002FFA4
0x18002ff98  mov     ebx, 80070005h
0x18002ff9d  mov     edx, 43Eh
0x18002ffa2  jmp     short loc_18002FF74
0x18002ffa4  lea     rdx, aSetcustomthumb; "SetCustomThumbnail"
0x18002ffab  lea     rcx, [rbp+130h+var_1B0]
0x18002ffaf  call    ??0?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002ffb4  lea     rcx, ??_7SetCustomThumbnail@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::SetCustomThumbnail::`vftable'
0x18002ffbb  mov     [rbp+130h+var_1B0], rcx
0x18002ffbf  mov     r8, r15; unsigned __int64
0x18002ffc2  mov     dl, 1; bool
0x18002ffc4  lea     rcx, [rbp+130h+var_1B0]; this
0x18002ffc8  call    ?StartActivity@SetCustomThumbnail@ThumbnailCacheTelemetry@@QEAAX_N_K@Z; ThumbnailCacheTelemetry::SetCustomThumbnail::StartActivity(bool,unsigned __int64)
0x18002ffcd  nop
0x18002ffce  mov     qword ptr [rsp+230h+var_1C0], 0
0x18002ffd7  lea     rcx, [rsp+230h+var_1C0]
0x18002ffdc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ffe1  lea     r8, [rsp+230h+var_1C0]
0x18002ffe6  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18002ffed  mov     rcx, rbx
0x18002fff0  call    cs:__imp_CreateStreamOverRandomAccessStream
0x18002fff6  mov     ebx, eax
0x18002fff8  test    eax, eax
0x18002fffa  jns     short loc_18003001C
0x18002fffc  mov     rcx, [rbp+138h]; this
0x180030003  mov     r9d, eax; char *
0x180030006  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003000d  mov     edx, 445h; void *
0x180030012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030017  jmp     loc_18003014F
0x18003001c  mov     [rsp+230h+var_1C8], 0
0x180030025  lea     rcx, [rsp+230h+var_1C8]
0x18003002a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003002f  lea     r8, [rsp+230h+var_1C8]; void **
0x180030034  mov     rcx, r14; this
0x180030037  call    ?GetThumbnailCache@CStorageThumbnailCache@@AEAAJAEBU_GUID@@PEAPEAX@Z; CStorageThumbnailCache::GetThumbnailCache(_GUID const &,void * *)
0x18003003c  mov     ebx, eax
0x18003003e  test    eax, eax
0x180030040  jns     short loc_18003006D
0x180030042  mov     rcx, [rbp+138h]; this
0x180030049  mov     r9d, eax; char *
0x18003004c  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180030053  mov     edx, 44Ah; void *
0x180030058  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003005d  nop
0x18003005e  lea     rcx, [rsp+230h+var_1C8]
0x180030063  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030068  jmp     loc_18003014F
0x18003006d  maxss   xmm6, xmm7
0x180030071  lea     rdx, [r14+40h]
0x180030075  lea     rcx, [rsp+230h+SRWLock]
0x18003007a  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18003007f  nop
0x180030080  mov     rsi, [rsp+230h+var_1C8]
0x180030085  mov     rax, [rsi]
0x180030088  mov     rdi, [rax+78h]
0x18003008c  mov     rbx, qword ptr [rsp+230h+var_1C0]
0x180030091  xor     edx, edx; length
0x180030093  mov     rcx, [rsp+230h+string]; string
0x180030098  call    cs:__imp_WindowsGetStringRawBuffer
0x18003009e  mov     [rsp+230h+var_1F0], r15
0x1800300a3  mov     [rsp+230h+var_1E8], 0
0x1800300ac  cvttss2si r9, xmm6
0x1800300b1  mov     qword ptr [rsp+230h+var_210], rbx; int
0x1800300b6  lea     r8, [rsp+230h+var_1F0]
0x1800300bb  mov     rdx, rax
0x1800300be  mov     rcx, rsi
0x1800300c1  mov     rax, rdi
0x1800300c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300c9  mov     ebx, eax
0x1800300cb  test    eax, eax
0x1800300cd  jns     short loc_180030104
0x1800300cf  mov     rcx, [rbp+138h]; this
0x1800300d6  mov     r9d, eax; char *
0x1800300d9  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x1800300e0  mov     edx, 44Fh; void *
0x1800300e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800300ea  nop
0x1800300eb  mov     rcx, [rsp+230h+SRWLock]; SRWLock
0x1800300f0  test    rcx, rcx
0x1800300f3  jz      loc_18003005E
0x1800300f9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800300ff  jmp     loc_18003005E
0x180030104  mov     rcx, [rsp+230h+SRWLock]; SRWLock
0x180030109  test    rcx, rcx
0x18003010c  jz      short loc_180030114
0x18003010e  call    cs:__imp_ReleaseSRWLockExclusive
0x180030114  lea     rax, [rsp+230h+string]
0x180030119  mov     [rsp+230h+var_1F0], rax
0x18003011e  lea     rax, [rsp+230h+var_1C8]
0x180030123  mov     [rsp+230h+var_1E8], rax
0x180030128  mov     [rsp+230h+var_1E0], r14
0x18003012d  lea     rcx, [rsp+230h+var_1F0]
0x180030132  call    ??R_lambda_639341b02e32c8ae0d65114f396fb9ff_@@QEBA@XZ; _lambda_639341b02e32c8ae0d65114f396fb9ff_::operator()(void)
0x180030137  xor     edx, edx
0x180030139  lea     rcx, [rbp+130h+var_1B0]
0x18003013d  call    ?Stop@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180030142  nop
0x180030143  lea     rcx, [rsp+230h+var_1C8]
0x180030148  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003014d  xor     ebx, ebx
0x18003014f  lea     rcx, [rsp+230h+var_1C0]
0x180030154  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030159  nop
0x18003015a  lea     rcx, [rbp+130h+var_1B0]; this
0x18003015e  call    ??1SetCustomThumbnail@ThumbnailCacheTelemetry@@QEAA@XZ; ThumbnailCacheTelemetry::SetCustomThumbnail::~SetCustomThumbnail(void)
0x180030163  mov     eax, ebx
0x180030165  mov     rcx, [rbp+130h+var_60]
0x18003016c  xor     rcx, rsp; StackCookie
0x18003016f  call    __security_check_cookie
0x180030174  lea     r11, [rsp+230h+var_28]
0x18003017c  movaps  xmm6, xmmword ptr [r11-18h]
0x180030181  movaps  xmm7, xmmword ptr [r11-28h]
0x180030186  mov     rsp, r11
0x180030189  pop     r15
0x18003018b  pop     r14
0x18003018d  pop     rdi
0x18003018e  pop     rsi
0x18003018f  pop     rbx
0x180030190  pop     rbp
0x180030191  retn
```
