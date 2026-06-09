# HDV::IPC::DeviceHostServices::Initialize(IVmDeviceHost *,void *,void * *)

- ea: `0x140084f20`
- end: `0x14008531e`
- name: `?Initialize@DeviceHostServices@IPC@HDV@@UEAAXPEAUIVmDeviceHost@@PEAXPEAPEAX@Z`
- size: `1022`
- prototype: `void(HDV::IPC::DeviceHostServices *__hidden this, struct IVmDeviceHost *, void *, void **)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140022290`
- `0x14004bab0`
- `0x140078628`
- `0x14007a6cc`
- `0x140083990`
- `0x1400840cc`
- `0x140084154`
- `0x140084f20`
- `0x140085410`
- `0x140085634`
- `0x14009394c`
- `0x14011ea40`
- `0x14011edec`
- `0x14011f6fc`
- `0x140184350`
- `0x14029fca4`
- `0x1402a09b8`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140085304`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140085311`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140085304`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140085311`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140085254`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140085254`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14008527f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14008527f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140084fd8`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140084fd8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14008502b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14008502b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14008504f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14008504f`

## string_xrefs

- `0x140084f6c`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140084f93`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140085007`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140085076`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140085293`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`

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
    JUMPOUT(0x14008531ELL);
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
0x140084f20  mov     [rsp-38h+arg_8], rbx
0x140084f25  push    rbp
0x140084f26  push    rsi
0x140084f27  push    rdi
0x140084f28  push    r12
0x140084f2a  push    r13
0x140084f2c  push    r14
0x140084f2e  push    r15
0x140084f30  mov     rbp, rsp
0x140084f33  sub     rsp, 80h
0x140084f3a  movaps  [rsp+80h+var_10], xmm6
0x140084f3f  mov     rax, cs:__security_cookie
0x140084f46  xor     rax, rsp
0x140084f49  mov     [rbp+var_18], rax
0x140084f4d  mov     [rbp+lpTargetHandle], r9
0x140084f51  mov     r13, r8
0x140084f54  mov     r12, rdx
0x140084f57  mov     rdi, rcx
0x140084f5a  mov     rcx, [rbp+38h]; this
0x140084f5e  xor     r15d, r15d
0x140084f61  test    r8, r8
0x140084f64  jnz     short loc_140084F7E
0x140084f66  mov     r9d, 80070057h; char *
0x140084f6c  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x140084f73  mov     edx, 0D6h; void *
0x140084f78  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140084f7e  cmp     [rdi+70h], r15
0x140084f82  setnz   al
0x140084f85  mov     rcx, [rbp+38h]; this
0x140084f89  test    al, al
0x140084f8b  jz      short loc_140084FA5
0x140084f8d  mov     r9d, 8007139Fh; char *
0x140084f93  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x140084f9a  mov     edx, 0D7h; void *
0x140084f9f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140084fa5  mov     ecx, [rdi+10h]
0x140084fa8  shl     rcx, 7
0x140084fac  mov     rax, rcx
0x140084faf  shr     rax, 20h
0x140084fb3  test    eax, eax
0x140084fb5  jz      short loc_140084FBD
0x140084fb7  call    ?SafeIntOnOverflow@SafeIntErrorPolicy_SafeIntException@utilities@msl@@SAXXZ; msl::utilities::SafeIntErrorPolicy_SafeIntException::SafeIntOnOverflow(void)
0x140084fbd  lea     r14d, [rcx+40h]
0x140084fc1  mov     [rsp+80h+lpName], r15; lpName
0x140084fc6  mov     [rsp+80h+dwMaximumSizeLow], r14d; dwMaximumSizeLow
0x140084fcb  xor     r9d, r9d; dwMaximumSizeHigh
0x140084fce  xor     edx, edx; lpFileMappingAttributes
0x140084fd0  lea     r8d, [r9+4]; flProtect
0x140084fd4  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x140084fd8  call    cs:__imp_CreateFileMappingW
0x140084fdf  nop     dword ptr [rax+rax+00h]
0x140084fe4  mov     rdx, rax
0x140084fe7  lea     rcx, [rdi+18h]
0x140084feb  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140084ff0  mov     r10, [rdi+18h]
0x140084ff4  lea     rax, [r10-1]
0x140084ff8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140084ffc  setnbe  al
0x140084fff  mov     rcx, [rbp+38h]; this
0x140085003  test    al, al
0x140085005  jz      short loc_140085019
0x140085007  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x14008500e  mov     edx, 0E3h; void *
0x140085013  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140085019  mov     qword ptr [rsp+80h+dwMaximumSizeLow], r15; dwNumberOfBytesToMap
0x14008501e  xor     r9d, r9d; dwFileOffsetLow
0x140085021  xor     r8d, r8d; dwFileOffsetHigh
0x140085024  lea     edx, [r9+6]; dwDesiredAccess
0x140085028  mov     rcx, r10; hFileMappingObject
0x14008502b  call    cs:__imp_MapViewOfFile
0x140085032  nop     dword ptr [rax+rax+00h]
0x140085037  mov     rbx, rax
0x14008503a  mov     rsi, [rdi+28h]
0x14008503e  test    rsi, rsi
0x140085041  jz      short loc_140085064
0x140085043  lea     rcx, [rbp+var_28]; this
0x140085047  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14008504c  mov     rcx, rsi; lpBaseAddress
0x14008504f  call    cs:__imp_UnmapViewOfFile
0x140085056  nop     dword ptr [rax+rax+00h]
0x14008505b  lea     rcx, [rbp+var_28]; this
0x14008505f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140085064  mov     [rdi+28h], rbx
0x140085068  test    rbx, rbx
0x14008506b  setz    al
0x14008506e  mov     rcx, [rbp+38h]; this
0x140085072  test    al, al
0x140085074  jz      short loc_140085088
0x140085076  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x14008507d  mov     edx, 0E6h; void *
0x140085082  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140085088  mov     edx, r14d
0x14008508b  lea     rcx, [rbp+var_40]
0x14008508f  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x140085094  mov     qword ptr [rbp+var_40+8], rbx
0x140085098  mov     rax, qword ptr [rbp+var_40]
0x14008509c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400850a0  jz      loc_140085311
0x1400850a6  test    rbx, rbx
0x1400850a9  jnz     short loc_1400850B4
0x1400850ab  test    rax, rax
0x1400850ae  jnz     loc_140085311
0x1400850b4  lea     rbx, [rdi+30h]
0x1400850b8  movups  xmm0, [rbp+var_40]
0x1400850bc  movdqu  xmmword ptr [rbx], xmm0
0x1400850c0  movups  xmm6, xmm0
0x1400850c3  movaps  [rbp+var_40], xmm0
0x1400850c7  lea     rcx, [rbp+var_40]
0x1400850cb  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x1400850d0  mov     r8, rax; Size
0x1400850d3  xor     edx, edx; Val
0x1400850d5  psrldq  xmm6, 8
0x1400850da  movq    rcx, xmm6; void *
0x1400850df  call    memset_0
0x1400850e4  mov     rax, [rbx]
0x1400850e7  mov     rsi, [rbx+8]
0x1400850eb  mov     qword ptr [rbp+var_40], rax
0x1400850ef  mov     qword ptr [rbp+var_40+8], rsi
0x1400850f3  lea     rcx, [rbp+var_40]
0x1400850f7  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x1400850fc  cmp     rax, 0Ch
0x140085100  jb      loc_140085311
0x140085106  lea     rcx, [rbp+var_40]
0x14008510a  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14008510f  mov     dword ptr [rsi], 1000h
0x140085115  mov     eax, [rdi+10h]
0x140085118  mov     [rsi+4], eax
0x14008511b  mov     r8d, 40h ; '@'
0x140085121  mov     [rsi+8], r8d
0x140085125  lea     rdx, [rbp+var_28]
0x140085129  mov     rcx, rbx
0x14008512c  call    ?subspan@?$span@E$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<uchar,-1>::subspan(unsigned __int64,unsigned __int64)
0x140085131  movups  xmm6, xmmword ptr [rax]
0x140085134  movaps  [rbp+var_40], xmm6
0x140085138  lea     rcx, [rbp+var_40]
0x14008513c  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140085141  test    al, 7Fh
0x140085143  jnz     loc_140085304
0x140085149  movdqa  [rbp+var_40], xmm6
0x14008514e  psrldq  xmm6, 8
0x140085153  movq    rbx, xmm6
0x140085158  lea     rcx, [rbp+var_40]
0x14008515c  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140085161  shr     rax, 7
0x140085165  mov     rdx, rax
0x140085168  lea     rcx, [rbp+var_40]
0x14008516c  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x140085171  mov     qword ptr [rbp+var_40+8], rbx
0x140085175  mov     rax, qword ptr [rbp+var_40]
0x140085179  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14008517d  jz      loc_140085304
0x140085183  test    rbx, rbx
0x140085186  jnz     short loc_140085191
0x140085188  test    rax, rax
0x14008518b  jnz     loc_140085304
0x140085191  movups  xmm0, [rbp+var_40]
0x140085195  movdqu  xmmword ptr [rdi+40h], xmm0
0x14008519a  mov     r14, [rdi+48h]
0x14008519e  mov     rsi, [rdi+40h]
0x1400851a2  shl     rsi, 7
0x1400851a6  add     rsi, r14
0x1400851a9  cmp     r14, rsi
0x1400851ac  jz      loc_140085250
0x1400851b2  mov     [rbp+var_28], 0
0x1400851ba  mov     ecx, 0A0h; Size
0x1400851bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400851c4  mov     rbx, rax
0x1400851c7  mov     qword ptr [rbp+var_40], rax
0x1400851cb  xor     edx, edx; Val
0x1400851cd  mov     r8d, 0A0h; Size
0x1400851d3  mov     rcx, rax; void *
0x1400851d6  call    memset_0
0x1400851db  mov     r8, r13; void *
0x1400851de  mov     rdx, r14; struct HDV::IPC::CallControlBlock *
0x1400851e1  mov     rcx, rbx; this
0x1400851e4  call    ??0CallImpl@Details@IPC@HDV@@QEAA@PEAUCallControlBlock@23@PEAX@Z; HDV::IPC::Details::CallImpl::CallImpl(HDV::IPC::CallControlBlock *,void *)
0x1400851e9  mov     rbx, rax
0x1400851ec  test    rax, rax
0x1400851ef  jnz     short loc_1400851F5
0x1400851f1  xor     ecx, ecx
0x1400851f3  jmp     short loc_140085204
0x1400851f5  mov     rax, [rax+8]
0x1400851f9  movsxd  rcx, dword ptr [rax+4]
0x1400851fd  add     rcx, 8
0x140085201  add     rcx, rbx; this
0x140085204  call    ?IncrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::IncrementUserCount(void)
0x140085209  mov     [rbp+var_28], rbx
0x14008520d  mov     rdx, [rdi+60h]
0x140085211  cmp     rdx, [rdi+68h]
0x140085215  jz      short loc_140085229
0x140085217  mov     [rbp+var_28], 0
0x14008521f  mov     [rdx], rbx
0x140085222  add     qword ptr [rdi+60h], 8
0x140085227  jmp     short loc_140085237
0x140085229  lea     r8, [rbp+var_28]
0x14008522d  lea     rcx, [rdi+58h]
0x140085231  call    ??$_Emplace_reallocate@V?$com_ptr_t@VCallImpl@Details@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@VCallImpl@Details@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCallImpl@Details@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@VCallImpl@Details@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy>>(wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy> * const,wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy> &&)
0x140085236  nop
0x140085237  lea     rcx, [rbp+var_28]
0x14008523b  call    ??1?$com_ptr_t@VDeviceHostServices@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<HDV::IPC::DeviceHostServices,wil::err_exception_policy>::~com_ptr_t<HDV::IPC::DeviceHostServices,wil::err_exception_policy>(void)
0x140085240  sub     r14, 0FFFFFFFFFFFFFF80h
0x140085244  cmp     r14, rsi
0x140085247  jnz     loc_1400851B2
0x14008524d  xor     r15d, r15d
0x140085250  mov     rbx, [rdi+18h]
0x140085254  call    cs:__imp_GetCurrentProcess
0x14008525b  nop     dword ptr [rax+rax+00h]
0x140085260  mov     [rsp+80h+dwOptions], r15d; dwOptions
0x140085265  mov     dword ptr [rsp+80h+lpName], r15d; bInheritHandle
0x14008526a  mov     [rsp+80h+dwMaximumSizeLow], 6; dwDesiredAccess
0x140085272  mov     r9, [rbp+lpTargetHandle]; lpTargetHandle
0x140085276  mov     r8, r13; hTargetProcessHandle
0x140085279  mov     rdx, rbx; hSourceHandle
0x14008527c  mov     rcx, rax; hSourceProcessHandle
0x14008527f  call    cs:__imp_DuplicateHandle
0x140085286  nop     dword ptr [rax+rax+00h]
0x14008528b  mov     rcx, [rbp+38h]; this
0x14008528f  test    eax, eax
0x140085291  jnz     short loc_1400852A5
0x140085293  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x14008529a  mov     edx, 102h; void *
0x14008529f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400852a5  mov     rbx, [rdi+70h]
0x1400852a9  mov     [rdi+70h], r12
0x1400852ad  test    r12, r12
0x1400852b0  jz      short loc_1400852C2
0x1400852b2  mov     rax, [r12]
0x1400852b6  mov     rcx, r12
0x1400852b9  mov     rax, [rax+8]
0x1400852bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400852c2  test    rbx, rbx
0x1400852c5  jz      short loc_1400852D7
0x1400852c7  mov     rax, [rbx]
0x1400852ca  mov     rcx, rbx
0x1400852cd  mov     rax, [rax+10h]
0x1400852d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400852d6  nop
0x1400852d7  mov     rcx, [rbp+var_18]
0x1400852db  xor     rcx, rsp; StackCookie
0x1400852de  call    __security_check_cookie
0x1400852e3  mov     rbx, [rsp+80h+arg_8]
0x1400852eb  movaps  xmm6, [rsp+80h+var_10]
0x1400852f0  add     rsp, 80h
0x1400852f7  pop     r15
0x1400852f9  pop     r14
0x1400852fb  pop     r13
0x1400852fd  pop     r12
0x1400852ff  pop     rdi
0x140085300  pop     rsi
0x140085301  pop     rbp
0x140085302  retn
0x140085304  call    cs:__imp__o_terminate
0x14008530b  nop     dword ptr [rax+rax+00h]
0x140085310  int     3; Trap to Debugger
0x140085311  call    cs:__imp__o_terminate
0x140085318  nop     dword ptr [rax+rax+00h]
0x14008531d  int     3; Trap to Debugger
```
