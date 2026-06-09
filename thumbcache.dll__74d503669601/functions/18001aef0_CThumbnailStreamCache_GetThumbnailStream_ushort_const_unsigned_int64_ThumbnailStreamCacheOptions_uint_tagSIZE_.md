# CThumbnailStreamCache::GetThumbnailStream(ushort const *,unsigned __int64,ThumbnailStreamCacheOptions,uint,tagSIZE *,IStream * *)

- ea: `0x18001aef0`
- end: `0x18001b194`
- name: `?GetThumbnailStream@CThumbnailStreamCache@@UEAAJPEBG_KW4ThumbnailStreamCacheOptions@@IPEAUtagSIZE@@PEAPEAUIStream@@@Z`
- size: `676`
- prototype: `__int64 __fastcall(CThumbnailStreamCache *this, const unsigned __int16 *, __int64, unsigned int, signed int, struct tagSIZE *, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x18000c67c`
- `0x18001aef0`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001af80`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b107`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001af80`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b107`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x18001b182`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x18001b182`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001af99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001af99`

## string_xrefs

- `0x18001b056`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18001b0cd`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18001b115`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18001b14e`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CThumbnailStreamCache::GetThumbnailStream(
        CThumbnailStreamCache *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        struct tagSIZE *a6,
        struct IStream **a7)
{
  __m128 v10; // xmm6
  __int64 *v11; // r14
  __int64 v12; // r13
  unsigned __int64 v13; // rdx
  HRESULT v14; // eax
  int v15; // ecx
  int v16; // eax
  __int64 v17; // rdi
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v22; // rcx
  int v23; // [rsp+28h] [rbp-71h]
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-51h] BYREF
  HSTRING string; // [rsp+60h] [rbp-39h] BYREF
  __int64 v26; // [rsp+68h] [rbp-31h] BYREF
  __int64 v27; // [rsp+70h] [rbp-29h] BYREF
  __int64 v28; // [rsp+78h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+47h]

  *a6 = 0;
  *a7 = 0;
  v10 = 0;
  v26 = 0;
  v11 = (__int64 *)*((_QWORD *)this + 6);
  v12 = *v11;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  string = 0;
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  if ( v13 > 0xFFFFFFFF || (int)v13 + 1 < (unsigned int)v13 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v14 = WindowsCreateStringReference(a2, v13, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    RaiseException(v14, 1u, 0, 0);
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C5,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)a2,
      v23);
LABEL_21:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    goto LABEL_22;
  }
  v10.m128_f32[0] = (float)(int)a5;
  v23 = _mm_unpacklo_ps(v10, v10).m128_u32[0];
  a2 = (const unsigned __int16 *)(*(unsigned int (__fastcall **)(__int64 *, HSTRING, __int64, _QWORD))(v12 + 48))(
                                   v11,
                                   string,
                                   a3,
                                   a4);
  if ( (unsigned __int8)ShouldSuppressWilErrorTelemetry(a2) )
  {
    if ( v15 < 0 )
    {
LABEL_22:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      return (unsigned int)a2;
    }
  }
  else if ( (int)a2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B9,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)a2,
      v23);
    goto LABEL_22;
  }
  v28 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 56LL))(v26, &v28);
  LODWORD(a2) = v16;
  if ( v16 >= 0 )
  {
    a6->cx = (int)*(float *)&v28;
    a6->cy = (int)*((float *)&v28 + 1);
    v27 = 0;
    v17 = v26;
    a2 = *(const unsigned __int16 **)(*(_QWORD *)v26 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    v18 = ((__int64 (__fastcall *)(__int64, __int64 *))a2)(v17, &v27);
    LODWORD(a2) = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C1,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
        (const char *)(unsigned int)v18,
        v23);
      v19 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      v20 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      return (unsigned int)a2;
    }
    if ( !v27 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
      LODWORD(a2) = 0;
      goto LABEL_22;
    }
    LODWORD(a2) = CreateStreamOverRandomAccessStream(v27, &GUID_0000000c_0000_0000_c000_000000000046, a7);
    if ( (int)a2 >= 0 )
      goto LABEL_21;
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4BC,
    (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
    (const char *)(unsigned int)v16,
    v23);
  v22 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x18001aef0  mov     rax, rsp
0x18001aef3  push    rbp
0x18001aef4  push    rbx
0x18001aef5  push    rsi
0x18001aef6  push    rdi
0x18001aef7  push    r12
0x18001aef9  push    r13
0x18001aefb  push    r14
0x18001aefd  push    r15
0x18001aeff  lea     rbp, [rax-47h]
0x18001af03  sub     rsp, 98h
0x18001af0a  movaps  xmmword ptr [rax-58h], xmm6
0x18001af0e  mov     rax, cs:__security_cookie
0x18001af15  xor     rax, rsp
0x18001af18  mov     qword ptr [rbp+3Fh+var_58], rax
0x18001af1c  mov     r12d, r9d
0x18001af1f  mov     r15, r8
0x18001af22  mov     rbx, rdx
0x18001af25  mov     rdi, [rbp+3Fh+arg_28]
0x18001af29  mov     rsi, [rbp+3Fh+arg_30]
0x18001af2d  xor     edx, edx
0x18001af2f  mov     [rdi], rdx
0x18001af32  mov     [rsi], rdx
0x18001af35  mov     eax, [rbp+3Fh+arg_20]
0x18001af38  xorps   xmm6, xmm6
0x18001af3b  cvtsi2ss xmm6, rax
0x18001af40  mov     [rbp+3Fh+var_70], rdx
0x18001af44  mov     r14, [rcx+30h]
0x18001af48  mov     r13, [r14]
0x18001af4b  lea     rcx, [rbp+3Fh+var_70]
0x18001af4f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001af54  xor     eax, eax
0x18001af56  mov     [rbp+3Fh+string], rax
0x18001af5a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001af5e  inc     rdx; length
0x18001af61  cmp     [rbx+rdx*2], ax
0x18001af65  jnz     short loc_18001AF5E
0x18001af67  mov     eax, 0FFFFFFFFh
0x18001af6c  cmp     rdx, rax
0x18001af6f  jbe     short loc_18001AF87
0x18001af71  xor     r9d, r9d; lpArguments
0x18001af74  xor     r8d, r8d; nNumberOfArguments
0x18001af77  lea     edx, [r9+1]; dwExceptionFlags
0x18001af7b  mov     ecx, 80070216h; dwExceptionCode
0x18001af80  call    cs:__imp_RaiseException
0x18001af86  int     3; Trap to Debugger
0x18001af87  lea     eax, [rdx+1]
0x18001af8a  cmp     eax, edx
0x18001af8c  jb      short loc_18001AF71
0x18001af8e  lea     r9, [rbp+3Fh+string]; string
0x18001af92  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x18001af96  mov     rcx, rbx; sourceString
0x18001af99  call    cs:__imp_WindowsCreateStringReference
0x18001af9f  test    eax, eax
0x18001afa1  js      loc_18001B0FB
0x18001afa7  lea     rax, [rbp+3Fh+var_70]
0x18001afab  mov     qword ptr [rsp+0D0h+var_B0+8], rax
0x18001afb0  unpcklps xmm6, xmm6
0x18001afb3  movsd   qword ptr [rsp+0D0h+var_B0], xmm6; int
0x18001afb9  mov     r9d, r12d
0x18001afbc  mov     r8, r15
0x18001afbf  mov     rdx, [rbp+3Fh+string]
0x18001afc3  mov     rcx, r14
0x18001afc6  mov     rax, [r13+30h]
0x18001afca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afcf  mov     ebx, eax
0x18001afd1  mov     ecx, eax
0x18001afd3  call    ShouldSuppressWilErrorTelemetry
0x18001afd8  xor     r14d, r14d
0x18001afdb  test    al, al
0x18001afdd  jz      loc_18001B13F
0x18001afe3  test    ecx, ecx
0x18001afe5  js      loc_18001B131
0x18001afeb  xor     eax, eax
0x18001afed  mov     [rbp+3Fh+var_60], rax
0x18001aff1  mov     rcx, [rbp+3Fh+var_70]
0x18001aff5  mov     rax, [rcx]
0x18001aff8  lea     rdx, [rbp+3Fh+var_60]
0x18001affc  mov     rax, [rax+38h]
0x18001b000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b005  mov     ebx, eax
0x18001b007  test    eax, eax
0x18001b009  js      loc_18001B0C6
0x18001b00f  cvttss2si eax, dword ptr [rbp+3Fh+var_60]
0x18001b014  mov     [rdi], eax
0x18001b016  cvttss2si eax, dword ptr [rbp+3Fh+var_60+4]
0x18001b01b  mov     [rdi+4], eax
0x18001b01e  mov     [rbp+3Fh+var_68], r14
0x18001b022  mov     rdi, [rbp+3Fh+var_70]
0x18001b026  mov     rax, [rdi]
0x18001b029  mov     rbx, [rax+30h]
0x18001b02d  lea     rcx, [rbp+3Fh+var_68]
0x18001b031  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b036  lea     rdx, [rbp+3Fh+var_68]
0x18001b03a  mov     rcx, rdi
0x18001b03d  mov     rax, rbx
0x18001b040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b045  mov     ebx, eax
0x18001b047  test    eax, eax
0x18001b049  jns     loc_18001B161
0x18001b04f  mov     rcx, [rbp+47h]; this
0x18001b053  mov     r9d, eax; char *
0x18001b056  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001b05d  mov     edx, 4C1h; void *
0x18001b062  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b067  nop
0x18001b068  mov     rcx, [rbp+3Fh+var_68]
0x18001b06c  test    rcx, rcx
0x18001b06f  jz      short loc_18001B082
0x18001b071  mov     [rbp+3Fh+var_68], r14
0x18001b075  mov     rax, [rcx]
0x18001b078  mov     rax, [rax+10h]
0x18001b07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b081  nop
0x18001b082  mov     rcx, [rbp+3Fh+var_70]
0x18001b086  test    rcx, rcx
0x18001b089  jz      short loc_18001B09C
0x18001b08b  mov     [rbp+3Fh+var_70], r14
0x18001b08f  mov     rax, [rcx]
0x18001b092  mov     rax, [rax+10h]
0x18001b096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b09b  nop
0x18001b09c  mov     eax, ebx
0x18001b09e  mov     rcx, qword ptr [rbp+3Fh+var_58]
0x18001b0a2  xor     rcx, rsp; StackCookie
0x18001b0a5  call    __security_check_cookie
0x18001b0aa  movaps  xmm6, [rsp+0D0h+var_58+8]
0x18001b0b2  add     rsp, 98h
0x18001b0b9  pop     r15
0x18001b0bb  pop     r14
0x18001b0bd  pop     r13
0x18001b0bf  pop     r12
0x18001b0c1  pop     rdi
0x18001b0c2  pop     rsi
0x18001b0c3  pop     rbx
0x18001b0c4  pop     rbp
0x18001b0c5  retn
0x18001b0c6  mov     rcx, [rbp+47h]; this
0x18001b0ca  mov     r9d, ebx; char *
0x18001b0cd  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001b0d4  mov     edx, 4BCh; void *
0x18001b0d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b0de  nop
0x18001b0df  mov     rcx, [rbp+3Fh+var_70]
0x18001b0e3  test    rcx, rcx
0x18001b0e6  jz      short loc_18001B0F9
0x18001b0e8  mov     [rbp+3Fh+var_70], r14
0x18001b0ec  mov     rax, [rcx]
0x18001b0ef  mov     rax, [rax+10h]
0x18001b0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0f8  nop
0x18001b0f9  jmp     short loc_18001B09C
0x18001b0fb  xor     r9d, r9d; lpArguments
0x18001b0fe  xor     r8d, r8d; nNumberOfArguments
0x18001b101  lea     edx, [r9+1]; dwExceptionFlags
0x18001b105  mov     ecx, eax; dwExceptionCode
0x18001b107  call    cs:__imp_RaiseException
0x18001b10d  nop
0x18001b10e  mov     rcx, [rbp+47h]; this
0x18001b112  mov     r9d, ebx; char *
0x18001b115  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001b11c  mov     edx, 4C5h; void *
0x18001b121  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b126  nop
0x18001b127  lea     rcx, [rbp+3Fh+var_68]
0x18001b12b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b130  nop
0x18001b131  lea     rcx, [rbp+3Fh+var_70]
0x18001b135  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b13a  jmp     loc_18001B09C
0x18001b13f  test    ebx, ebx
0x18001b141  jns     loc_18001AFEB
0x18001b147  mov     rcx, [rbp+47h]; this
0x18001b14b  mov     r9d, ebx; char *
0x18001b14e  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001b155  mov     edx, 4B9h; void *
0x18001b15a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b15f  jmp     short loc_18001B131
0x18001b161  mov     rcx, [rbp+3Fh+var_68]
0x18001b165  test    rcx, rcx
0x18001b168  jnz     short loc_18001B178
0x18001b16a  lea     rcx, [rbp+3Fh+var_68]
0x18001b16e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b173  mov     ebx, r14d
0x18001b176  jmp     short loc_18001B131
0x18001b178  mov     r8, rsi
0x18001b17b  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18001b182  call    cs:__imp_CreateStreamOverRandomAccessStream
0x18001b188  mov     ebx, eax
0x18001b18a  test    eax, eax
0x18001b18c  jns     short loc_18001B127
0x18001b18e  jmp     loc_18001B10E
```
