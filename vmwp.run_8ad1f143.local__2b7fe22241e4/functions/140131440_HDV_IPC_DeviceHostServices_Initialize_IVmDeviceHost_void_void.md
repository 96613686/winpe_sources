# HDV::IPC::DeviceHostServices::Initialize(IVmDeviceHost *,void *,void * *)

- ea: `0x140131440`
- end: `0x14013183e`
- name: `?Initialize@DeviceHostServices@IPC@HDV@@UEAAXPEAUIVmDeviceHost@@PEAXPEAPEAX@Z`
- size: `1022`
- prototype: `void(HDV::IPC::DeviceHostServices *__hidden this, struct IVmDeviceHost *, void *, void **)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140021d20`
- `0x14004cb30`
- `0x14005ade4`
- `0x14005ae6c`
- `0x14005b648`
- `0x14006af58`
- `0x14006fee8`
- `0x1400828fc`
- `0x140084204`
- `0x140131440`
- `0x140131930`
- `0x140132960`
- `0x140132d0c`
- `0x14013361c`
- `0x14025f0b0`
- `0x140297164`
- `0x140297e78`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140131824`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140131831`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140131824`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140131831`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140131774`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140131774`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14013179f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14013179f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14013154b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14013154b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1401314f8`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1401314f8`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14013156f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14013156f`

## string_xrefs

- `0x14013148c`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x1401314b3`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140131527`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140131596`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x1401317b3`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall HDV::IPC::DeviceHostServices::Initialize(
        HDV::IPC::DeviceHostServices *this,
        struct IVmDeviceHost *a2,
        void *a3,
        void **a4)
{
  int v7; // ecx
  unsigned int v8; // r14d
  const char *v9; // r9
  char *v10; // r10
  LPVOID v11; // rbx
  const char *v12; // r9
  const void *v13; // rsi
  __int64 v14; // rcx
  __m128i v15; // xmm0
  size_t v16; // rax
  _DWORD *v17; // rsi
  __m128i v18; // xmm6
  __int64 v19; // rcx
  unsigned __int64 v20; // xmm6_8
  unsigned __int64 v21; // rax
  struct HDV::IPC::CallControlBlock *v22; // r14
  struct HDV::IPC::CallControlBlock *i; // rsi
  void *v24; // rbx
  HDV::IPC::Details::CallImpl *v25; // rax
  HDV::IPC::Details::CallImpl *v26; // rbx
  Vml::VmSharableObject *v27; // rcx
  HDV::IPC::Details::CallImpl **v28; // rdx
  void *v29; // rbx
  HANDLE CurrentProcess; // rax
  const char *v31; // r9
  __int64 v32; // rbx
  int dwMaximumSizeLow; // [rsp+20h] [rbp-60h]
  __m128i v34; // [rsp+40h] [rbp-40h] BYREF
  LPHANDLE lpTargetHandle; // [rsp+50h] [rbp-30h]
  _QWORD v36[2]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  lpTargetHandle = a4;
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      (const char *)0x80070057LL,
      dwMaximumSizeLow);
  if ( *((_QWORD *)this + 14) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      (const char *)0x8007139FLL,
      dwMaximumSizeLow);
  v7 = *((_DWORD *)this + 4) << 7;
  if ( !is_mul_ok(0x80u, *((_DWORD *)this + 4)) )
    msl::utilities::SafeIntErrorPolicy_SafeIntException::SafeIntOnOverflow();
  v8 = v7 + 64;
  CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, v7 + 64, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset((char *)this + 24);
  v10 = (char *)*((_QWORD *)this + 3);
  if ( (unsigned __int64)(v10 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      v9);
  v11 = MapViewOfFile(v10, 6u, 0, 0, 0);
  v13 = (const void *)*((_QWORD *)this + 5);
  if ( v13 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v36);
    UnmapViewOfFile(v13);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v36);
  }
  *((_QWORD *)this + 5) = v11;
  if ( !v11 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE6,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      v12);
  gsl::details::extent_type<-1>::extent_type<-1>(&v34, v8);
  v34.m128i_i64[1] = (__int64)v11;
  if ( v34.m128i_i64[0] == -1 )
    goto LABEL_35;
  v15 = v34;
  *((__m128i *)this + 3) = v34;
  v34 = v15;
  v16 = gsl::span<unsigned char,-1>::size_bytes(&v34);
  memset_0((void *)_mm_srli_si128(v15, 8).m128i_i64[0], 0, v16);
  v17 = (_DWORD *)*((_QWORD *)this + 7);
  v34.m128i_i64[0] = *((_QWORD *)this + 6);
  v34.m128i_i64[1] = (__int64)v17;
  if ( (unsigned __int64)gsl::span<unsigned char,-1>::size_bytes(&v34) < 0xC )
  {
LABEL_35:
    _o_terminate(v14);
    __debugbreak();
    JUMPOUT(0x14013183ELL);
  }
  gsl::span<unsigned char,-1>::size_bytes(&v34);
  *v17 = 4096;
  v17[1] = *((_DWORD *)this + 4);
  v17[2] = 64;
  v18 = *(__m128i *)gsl::span<unsigned char,-1>::subspan((char *)this + 48, v36);
  v34 = v18;
  if ( (gsl::span<unsigned char,-1>::size_bytes(&v34) & 0x7F) != 0
    || (v34 = v18,
        v20 = _mm_srli_si128(v18, 8).m128i_u64[0],
        v21 = gsl::span<unsigned char,-1>::size_bytes(&v34),
        gsl::details::extent_type<-1>::extent_type<-1>(&v34, v21 >> 7),
        v34.m128i_i64[1] = v20,
        v34.m128i_i64[0] == -1)
    || !v20 && v34.m128i_i64[0] )
  {
    _o_terminate(v19);
    __debugbreak();
    goto LABEL_35;
  }
  *((__m128i *)this + 4) = v34;
  v22 = (struct HDV::IPC::CallControlBlock *)*((_QWORD *)this + 9);
  for ( i = (struct HDV::IPC::CallControlBlock *)((char *)v22 + 128 * *((_QWORD *)this + 8));
        v22 != i;
        v22 = (struct HDV::IPC::CallControlBlock *)((char *)v22 + 128) )
  {
    v36[0] = 0;
    v24 = operator new(0xA0u);
    v34.m128i_i64[0] = (__int64)v24;
    memset_0(v24, 0, 0xA0u);
    v25 = HDV::IPC::Details::CallImpl::CallImpl((HDV::IPC::Details::CallImpl *)v24, v22, a3);
    v26 = v25;
    if ( v25 )
      v27 = (HDV::IPC::Details::CallImpl *)((char *)v25 + *(int *)(*((_QWORD *)v25 + 1) + 4LL) + 8);
    else
      v27 = 0;
    Vml::VmSharableObject::IncrementUserCount(v27);
    v36[0] = v26;
    v28 = (HDV::IPC::Details::CallImpl **)*((_QWORD *)this + 12);
    if ( v28 == *((HDV::IPC::Details::CallImpl ***)this + 13) )
    {
      std::vector<wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy>>(
        (char *)this + 88,
        v28,
        v36);
    }
    else
    {
      v36[0] = 0;
      *v28 = v26;
      *((_QWORD *)this + 12) += 8LL;
    }
    wil::com_ptr_t<HDV::IPC::DeviceHostServices,wil::err_exception_policy>::~com_ptr_t<HDV::IPC::DeviceHostServices,wil::err_exception_policy>(v36);
  }
  v29 = (void *)*((_QWORD *)this + 3);
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, v29, a3, lpTargetHandle, 6u, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      v31);
  v32 = *((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct IVmDeviceHost *))(*(_QWORD *)a2 + 8LL))(a2);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
}

```

## disassembly

```asm
0x140131440  mov     [rsp-38h+arg_8], rbx
0x140131445  push    rbp
0x140131446  push    rsi
0x140131447  push    rdi
0x140131448  push    r12
0x14013144a  push    r13
0x14013144c  push    r14
0x14013144e  push    r15
0x140131450  mov     rbp, rsp
0x140131453  sub     rsp, 80h
0x14013145a  movaps  [rsp+80h+var_10], xmm6
0x14013145f  mov     rax, cs:__security_cookie
0x140131466  xor     rax, rsp
0x140131469  mov     [rbp+var_18], rax
0x14013146d  mov     [rbp+lpTargetHandle], r9
0x140131471  mov     r13, r8
0x140131474  mov     r12, rdx
0x140131477  mov     rdi, rcx
0x14013147a  mov     rcx, [rbp+38h]; this
0x14013147e  xor     r15d, r15d
0x140131481  test    r8, r8
0x140131484  jnz     short loc_14013149E
0x140131486  mov     r9d, 80070057h; char *
0x14013148c  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x140131493  mov     edx, 0D6h; void *
0x140131498  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14013149e  cmp     [rdi+70h], r15
0x1401314a2  setnz   al
0x1401314a5  mov     rcx, [rbp+38h]; this
0x1401314a9  test    al, al
0x1401314ab  jz      short loc_1401314C5
0x1401314ad  mov     r9d, 8007139Fh; char *
0x1401314b3  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x1401314ba  mov     edx, 0D7h; void *
0x1401314bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401314c5  mov     ecx, [rdi+10h]
0x1401314c8  shl     rcx, 7
0x1401314cc  mov     rax, rcx
0x1401314cf  shr     rax, 20h
0x1401314d3  test    eax, eax
0x1401314d5  jz      short loc_1401314DD
0x1401314d7  call    ?SafeIntOnOverflow@SafeIntErrorPolicy_SafeIntException@utilities@msl@@SAXXZ; msl::utilities::SafeIntErrorPolicy_SafeIntException::SafeIntOnOverflow(void)
0x1401314dd  lea     r14d, [rcx+40h]
0x1401314e1  mov     [rsp+80h+lpName], r15; lpName
0x1401314e6  mov     [rsp+80h+dwMaximumSizeLow], r14d; dwMaximumSizeLow
0x1401314eb  xor     r9d, r9d; dwMaximumSizeHigh
0x1401314ee  xor     edx, edx; lpFileMappingAttributes
0x1401314f0  lea     r8d, [r9+4]; flProtect
0x1401314f4  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1401314f8  call    cs:__imp_CreateFileMappingW
0x1401314ff  nop     dword ptr [rax+rax+00h]
0x140131504  mov     rdx, rax
0x140131507  lea     rcx, [rdi+18h]
0x14013150b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140131510  mov     r10, [rdi+18h]
0x140131514  lea     rax, [r10-1]
0x140131518  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14013151c  setnbe  al
0x14013151f  mov     rcx, [rbp+38h]; this
0x140131523  test    al, al
0x140131525  jz      short loc_140131539
0x140131527  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x14013152e  mov     edx, 0E3h; void *
0x140131533  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140131539  mov     qword ptr [rsp+80h+dwMaximumSizeLow], r15; dwNumberOfBytesToMap
0x14013153e  xor     r9d, r9d; dwFileOffsetLow
0x140131541  xor     r8d, r8d; dwFileOffsetHigh
0x140131544  lea     edx, [r9+6]; dwDesiredAccess
0x140131548  mov     rcx, r10; hFileMappingObject
0x14013154b  call    cs:__imp_MapViewOfFile
0x140131552  nop     dword ptr [rax+rax+00h]
0x140131557  mov     rbx, rax
0x14013155a  mov     rsi, [rdi+28h]
0x14013155e  test    rsi, rsi
0x140131561  jz      short loc_140131584
0x140131563  lea     rcx, [rbp+var_28]; this
0x140131567  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14013156c  mov     rcx, rsi; lpBaseAddress
0x14013156f  call    cs:__imp_UnmapViewOfFile
0x140131576  nop     dword ptr [rax+rax+00h]
0x14013157b  lea     rcx, [rbp+var_28]; this
0x14013157f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140131584  mov     [rdi+28h], rbx
0x140131588  test    rbx, rbx
0x14013158b  setz    al
0x14013158e  mov     rcx, [rbp+38h]; this
0x140131592  test    al, al
0x140131594  jz      short loc_1401315A8
0x140131596  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x14013159d  mov     edx, 0E6h; void *
0x1401315a2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401315a8  mov     edx, r14d
0x1401315ab  lea     rcx, [rbp+var_40]
0x1401315af  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x1401315b4  mov     qword ptr [rbp+var_40+8], rbx
0x1401315b8  mov     rax, qword ptr [rbp+var_40]
0x1401315bc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401315c0  jz      loc_140131831
0x1401315c6  test    rbx, rbx
0x1401315c9  jnz     short loc_1401315D4
0x1401315cb  test    rax, rax
0x1401315ce  jnz     loc_140131831
0x1401315d4  lea     rbx, [rdi+30h]
0x1401315d8  movups  xmm0, [rbp+var_40]
0x1401315dc  movdqu  xmmword ptr [rbx], xmm0
0x1401315e0  movups  xmm6, xmm0
0x1401315e3  movaps  [rbp+var_40], xmm0
0x1401315e7  lea     rcx, [rbp+var_40]
0x1401315eb  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x1401315f0  mov     r8, rax; Size
0x1401315f3  xor     edx, edx; Val
0x1401315f5  psrldq  xmm6, 8
0x1401315fa  movq    rcx, xmm6; void *
0x1401315ff  call    memset_0
0x140131604  mov     rax, [rbx]
0x140131607  mov     rsi, [rbx+8]
0x14013160b  mov     qword ptr [rbp+var_40], rax
0x14013160f  mov     qword ptr [rbp+var_40+8], rsi
0x140131613  lea     rcx, [rbp+var_40]
0x140131617  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14013161c  cmp     rax, 0Ch
0x140131620  jb      loc_140131831
0x140131626  lea     rcx, [rbp+var_40]
0x14013162a  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14013162f  mov     dword ptr [rsi], 1000h
0x140131635  mov     eax, [rdi+10h]
0x140131638  mov     [rsi+4], eax
0x14013163b  mov     r8d, 40h ; '@'
0x140131641  mov     [rsi+8], r8d
0x140131645  lea     rdx, [rbp+var_28]
0x140131649  mov     rcx, rbx
0x14013164c  call    ?subspan@?$span@E$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<uchar,-1>::subspan(unsigned __int64,unsigned __int64)
0x140131651  movups  xmm6, xmmword ptr [rax]
0x140131654  movaps  [rbp+var_40], xmm6
0x140131658  lea     rcx, [rbp+var_40]
0x14013165c  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140131661  test    al, 7Fh
0x140131663  jnz     loc_140131824
0x140131669  movdqa  [rbp+var_40], xmm6
0x14013166e  psrldq  xmm6, 8
0x140131673  movq    rbx, xmm6
0x140131678  lea     rcx, [rbp+var_40]
0x14013167c  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140131681  shr     rax, 7
0x140131685  mov     rdx, rax
0x140131688  lea     rcx, [rbp+var_40]
0x14013168c  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x140131691  mov     qword ptr [rbp+var_40+8], rbx
0x140131695  mov     rax, qword ptr [rbp+var_40]
0x140131699  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14013169d  jz      loc_140131824
0x1401316a3  test    rbx, rbx
0x1401316a6  jnz     short loc_1401316B1
0x1401316a8  test    rax, rax
0x1401316ab  jnz     loc_140131824
0x1401316b1  movups  xmm0, [rbp+var_40]
0x1401316b5  movdqu  xmmword ptr [rdi+40h], xmm0
0x1401316ba  mov     r14, [rdi+48h]
0x1401316be  mov     rsi, [rdi+40h]
0x1401316c2  shl     rsi, 7
0x1401316c6  add     rsi, r14
0x1401316c9  cmp     r14, rsi
0x1401316cc  jz      loc_140131770
0x1401316d2  mov     [rbp+var_28], 0
0x1401316da  mov     ecx, 0A0h; Size
0x1401316df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401316e4  mov     rbx, rax
0x1401316e7  mov     qword ptr [rbp+var_40], rax
0x1401316eb  xor     edx, edx; Val
0x1401316ed  mov     r8d, 0A0h; Size
0x1401316f3  mov     rcx, rax; void *
0x1401316f6  call    memset_0
0x1401316fb  mov     r8, r13; void *
0x1401316fe  mov     rdx, r14; struct HDV::IPC::CallControlBlock *
0x140131701  mov     rcx, rbx; this
0x140131704  call    ??0CallImpl@Details@IPC@HDV@@QEAA@PEAUCallControlBlock@23@PEAX@Z; HDV::IPC::Details::CallImpl::CallImpl(HDV::IPC::CallControlBlock *,void *)
0x140131709  mov     rbx, rax
0x14013170c  test    rax, rax
0x14013170f  jnz     short loc_140131715
0x140131711  xor     ecx, ecx
0x140131713  jmp     short loc_140131724
0x140131715  mov     rax, [rax+8]
0x140131719  movsxd  rcx, dword ptr [rax+4]
0x14013171d  add     rcx, 8
0x140131721  add     rcx, rbx; this
0x140131724  call    ?IncrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::IncrementUserCount(void)
0x140131729  mov     [rbp+var_28], rbx
0x14013172d  mov     rdx, [rdi+60h]
0x140131731  cmp     rdx, [rdi+68h]
0x140131735  jz      short loc_140131749
0x140131737  mov     [rbp+var_28], 0
0x14013173f  mov     [rdx], rbx
0x140131742  add     qword ptr [rdi+60h], 8
0x140131747  jmp     short loc_140131757
0x140131749  lea     r8, [rbp+var_28]
0x14013174d  lea     rcx, [rdi+58h]
0x140131751  call    ??$_Emplace_reallocate@V?$com_ptr_t@VCallImpl@Details@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@VCallImpl@Details@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCallImpl@Details@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@VCallImpl@Details@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy>>(wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy> * const,wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy> &&)
0x140131756  nop
0x140131757  lea     rcx, [rbp+var_28]
0x14013175b  call    ??1?$com_ptr_t@VDeviceHostServices@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<HDV::IPC::DeviceHostServices,wil::err_exception_policy>::~com_ptr_t<HDV::IPC::DeviceHostServices,wil::err_exception_policy>(void)
0x140131760  sub     r14, 0FFFFFFFFFFFFFF80h
0x140131764  cmp     r14, rsi
0x140131767  jnz     loc_1401316D2
0x14013176d  xor     r15d, r15d
0x140131770  mov     rbx, [rdi+18h]
0x140131774  call    cs:__imp_GetCurrentProcess
0x14013177b  nop     dword ptr [rax+rax+00h]
0x140131780  mov     [rsp+80h+dwOptions], r15d; dwOptions
0x140131785  mov     dword ptr [rsp+80h+lpName], r15d; bInheritHandle
0x14013178a  mov     [rsp+80h+dwMaximumSizeLow], 6; dwDesiredAccess
0x140131792  mov     r9, [rbp+lpTargetHandle]; lpTargetHandle
0x140131796  mov     r8, r13; hTargetProcessHandle
0x140131799  mov     rdx, rbx; hSourceHandle
0x14013179c  mov     rcx, rax; hSourceProcessHandle
0x14013179f  call    cs:__imp_DuplicateHandle
0x1401317a6  nop     dword ptr [rax+rax+00h]
0x1401317ab  mov     rcx, [rbp+38h]; this
0x1401317af  test    eax, eax
0x1401317b1  jnz     short loc_1401317C5
0x1401317b3  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x1401317ba  mov     edx, 102h; void *
0x1401317bf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401317c5  mov     rbx, [rdi+70h]
0x1401317c9  mov     [rdi+70h], r12
0x1401317cd  test    r12, r12
0x1401317d0  jz      short loc_1401317E2
0x1401317d2  mov     rax, [r12]
0x1401317d6  mov     rcx, r12
0x1401317d9  mov     rax, [rax+8]
0x1401317dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401317e2  test    rbx, rbx
0x1401317e5  jz      short loc_1401317F7
0x1401317e7  mov     rax, [rbx]
0x1401317ea  mov     rcx, rbx
0x1401317ed  mov     rax, [rax+10h]
0x1401317f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401317f6  nop
0x1401317f7  mov     rcx, [rbp+var_18]
0x1401317fb  xor     rcx, rsp; StackCookie
0x1401317fe  call    __security_check_cookie
0x140131803  mov     rbx, [rsp+80h+arg_8]
0x14013180b  movaps  xmm6, [rsp+80h+var_10]
0x140131810  add     rsp, 80h
0x140131817  pop     r15
0x140131819  pop     r14
0x14013181b  pop     r13
0x14013181d  pop     r12
0x14013181f  pop     rdi
0x140131820  pop     rsi
0x140131821  pop     rbp
0x140131822  retn
0x140131824  call    cs:__imp__o_terminate
0x14013182b  nop     dword ptr [rax+rax+00h]
0x140131830  int     3; Trap to Debugger
0x140131831  call    cs:__imp__o_terminate
0x140131838  nop     dword ptr [rax+rax+00h]
0x14013183d  int     3; Trap to Debugger
```
