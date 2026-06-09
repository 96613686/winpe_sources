# CFsrmFileStream::OpenStreamForWrite(bool,bool)

- ea: `0x18005ea5c`
- end: `0x18005ee68`
- name: `?OpenStreamForWrite@CFsrmFileStream@@AEAAX_N0@Z`
- size: `1036`
- prototype: `void __fastcall(CFsrmFileStream *__hidden this, bool, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18005e24c`

## callees

- `0x180001350`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000ee10`
- `0x18003ed58`
- `0x18005e040`
- `0x18005ea5c`
- `0x18006febc`
- `0x1800700b8`
- `0x180072a80`
- `0x180073a80`
- `0x180073f54`
- `0x18007cdec`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18005ebfe`
- `KERNEL32!CreateFileW` at `0x18005ebfe`
- `KERNEL32!CloseHandle` at `0x18005ec47`
- `KERNEL32!CloseHandle` at `0x18005ec47`
- `KERNEL32!GetLastError` at `0x18005ed7b`
- `KERNEL32!GetLastError` at `0x18005ee1d`
- `KERNEL32!GetLastError` at `0x18005ed7b`
- `KERNEL32!GetLastError` at `0x18005ee1d`
- `KERNEL32!DeleteFileW` at `0x18005ee13`
- `KERNEL32!DeleteFileW` at `0x18005ee13`

## string_xrefs

- `0x18005ee3b`: `Cannot delete temp copy '%s', error %ld`
- `0x18005ea9b`: `base\fs\fsrm\service\stream\streamlib.cpp`
- `0x18005ed97`: `Error while opening file '%s': %d`
- `0x18005eaa9`: `CFsrmFileStream::OpenStreamForWrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CFsrmFileStream::OpenStreamForWrite(CFsrmFileStream *this)
{
  const WCHAR **v2; // rdi
  const WCHAR *v3; // rcx
  unsigned int v4; // r15d
  unsigned __int16 *v5; // rcx
  const WCHAR *v6; // rcx
  HANDLE FileW; // r14
  void *v8; // rcx
  char Hr; // al
  DWORD LastError; // eax
  int v11; // eax
  char v12; // al
  const WCHAR *v13; // rax
  __int64 v14; // rax
  int v15; // edx
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-200h]
  unsigned int v17; // [rsp+40h] [rbp-1E8h] BYREF
  void **v18; // [rsp+48h] [rbp-1E0h]
  __int64 v19; // [rsp+50h] [rbp-1D8h]
  struct _FILETIME v20; // [rsp+58h] [rbp-1D0h] BYREF
  struct _FILETIME v21; // [rsp+60h] [rbp-1C8h] BYREF
  struct _FILETIME v22; // [rsp+68h] [rbp-1C0h] BYREF
  int v23; // [rsp+70h] [rbp-1B8h] BYREF
  _com_error *v24; // [rsp+78h] [rbp-1B0h] BYREF
  const exception *v25; // [rsp+80h] [rbp-1A8h] BYREF
  _QWORD v26[3]; // [rsp+88h] [rbp-1A0h] BYREF
  int v27; // [rsp+A0h] [rbp-188h]
  int v28; // [rsp+A4h] [rbp-184h]
  int v29; // [rsp+A8h] [rbp-180h]
  _DWORD v30[26]; // [rsp+B0h] [rbp-178h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+118h] [rbp-110h] BYREF
  __int64 v32; // [rsp+128h] [rbp-100h]
  unsigned __int64 v33; // [rsp+130h] [rbp-F8h]
  void **v34; // [rsp+140h] [rbp-E8h] BYREF
  int v35; // [rsp+148h] [rbp-E0h]
  unsigned int v36; // [rsp+16Ch] [rbp-BCh]

  v26[0] = L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp";
  v26[1] = L"CFsrmFileStream::OpenStreamForWrite";
  v26[2] = L"STREAMLC";
  v27 = 284;
  v28 = 17;
  v29 = 255;
  v30[24] = 0x1000000;
  memset_0(v30, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v34, (const struct CSrmDebugInfo *)v26, 0);
  v21 = 0;
  v22 = 0;
  v20 = 0;
  v17 = 0;
  v2 = (const WCHAR **)((char *)this + 8);
  if ( *((_QWORD *)this + 4) < 8u )
    v3 = (const WCHAR *)((char *)this + 8);
  else
    v3 = *v2;
  SrmGetBasicInfoByName(v3, &v21, &v22, &v20, &v17);
  v4 = v17;
  if ( (v17 & 1) != 0 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v34, -2147018887);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v34);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v34, 0x128u, Hr, 0);
  }
  v35 = 0;
  v33 = 7;
  v32 = 0;
  LOWORD(lpFileName[0]) = 0;
  if ( *((_QWORD *)this + 4) < 8u )
    v5 = (unsigned __int16 *)((char *)this + 8);
  else
    v5 = (unsigned __int16 *)*v2;
  CFsrmFileStream::MakeTempCopy(v5);
  try
  {
    v6 = (const WCHAR *)lpFileName;
    if ( v33 >= 8 )
      v6 = lpFileName[0];
    FileW = CreateFileW(v6, 0xC0010000, 1u, 0, 3u, 0x42000000u, 0);
    v18 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
    v19 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      *((_DWORD *)this + 22) = LastError;
      if ( *((_QWORD *)this + 4) >= 8u )
        v2 = (const WCHAR **)*v2;
      LODWORD(dwFlagsAndAttributes) = LastError;
      CSrmFunctionTracer::Trace(
        (CSrmFunctionTracer *)&v34,
        0x8Cu,
        0x155u,
        L"Error while opening file '%s': %d",
        v2,
        dwFlagsAndAttributes);
      v35 = -2147200189;
      v11 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v34);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v34, v11);
      v12 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v34);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v34, 0x156u, v12, 0);
    }
    v19 = -1;
    v8 = (void *)*((_QWORD *)this + 30);
    if ( v8 != (void *)-1LL )
      CloseHandle(v8);
    *((_QWORD *)this + 30) = -1;
    *((_QWORD *)this + 30) = FileW;
    std::wstring::swap((char *)this + 48, lpFileName);
    *((struct _FILETIME *)this + 34) = v21;
    *((struct _FILETIME *)this + 35) = v22;
    *((struct _FILETIME *)this + 36) = v20;
    *((_DWORD *)this + 23) = v4;
    v18 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
    v19 = -1;
  }
  catch ( long v23 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v34,
      v23,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmFileStream::OpenStreamForWrite",
      0x163u,
      v36);
  }
  catch ( _com_error *v24 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v34,
      v24,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmFileStream::OpenStreamForWrite",
      0x163u,
      v36);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v34,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmFileStream::OpenStreamForWrite",
      0x163u,
      v36);
  }
  catch ( const exception *v25 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v34,
      v25,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmFileStream::OpenStreamForWrite",
      0x163u,
      v36);
  }
  if ( v35 < 0 )
  {
    v13 = (const WCHAR *)std::wstring::c_str(lpFileName);
    if ( !DeleteFileW(v13) )
    {
      GetLastError();
      v14 = std::wstring::c_str(lpFileName);
      LODWORD(dwFlagsAndAttributes) = v15;
      CSrmFunctionTracer::Trace(
        (CSrmFunctionTracer *)&v34,
        0x3Cu,
        0x16Fu,
        L"Cannot delete temp copy '%s', error %ld",
        v14,
        dwFlagsAndAttributes);
    }
    CSrmFunctionTracer::ReThrow((CSrmFunctionTracer *)&v34);
  }
  if ( v33 >= 8 )
    operator delete((void *)lpFileName[0]);
  v33 = 7;
  v32 = 0;
  LOWORD(lpFileName[0]) = 0;
  v34 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v34);
}

```

## disassembly

```asm
0x18005ea5c  mov     r11, rsp
0x18005ea5f  mov     [r11+18h], rbx
0x18005ea63  mov     [r11+20h], rsi
0x18005ea67  push    rdi
0x18005ea68  push    r12
0x18005ea6a  push    r13
0x18005ea6c  push    r14
0x18005ea6e  push    r15
0x18005ea70  sub     rsp, 200h
0x18005ea77  mov     rax, cs:__security_cookie
0x18005ea7e  xor     rax, rsp
0x18005ea81  mov     [rsp+228h+var_38], rax
0x18005ea89  mov     r14b, dl
0x18005ea8c  mov     rsi, rcx
0x18005ea8f  lea     rax, [r11-1A0h]
0x18005ea96  mov     qword ptr [rsp+228h+var_1D0.dwLowDateTime], rax
0x18005ea9b  lea     rax, aBaseFsFsrmServ_12; "base\\fs\\fsrm\\service\\stream\\stream"...
0x18005eaa2  mov     [r11-1A0h], rax
0x18005eaa9  lea     rax, aCfsrmfilestrea_5; "CFsrmFileStream::OpenStreamForWrite"
0x18005eab0  mov     [r11-198h], rax
0x18005eab7  lea     rax, aStreamlc; "STREAMLC"
0x18005eabe  mov     [r11-190h], rax
0x18005eac5  mov     [rsp+228h+var_188], 11Ch
0x18005ead0  mov     [rsp+228h+var_184], 11h
0x18005eadb  mov     [rsp+228h+var_180], 0FFh
0x18005eae6  xor     ebx, ebx
0x18005eae8  mov     [rsp+228h+var_118], 1000000h
0x18005eaf3  xor     edx, edx; Val
0x18005eaf5  lea     r8d, [rbx+60h]; Size
0x18005eaf9  lea     rcx, [r11-178h]; void *
0x18005eb00  call    memset_0
0x18005eb05  nop
0x18005eb06  xor     r8d, r8d
0x18005eb09  lea     rdx, [rsp+228h+var_1A0]
0x18005eb11  lea     rcx, [rsp+228h+var_E8]
0x18005eb19  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18005eb1e  nop
0x18005eb1f  mov     qword ptr [rsp+228h+var_1C8.dwLowDateTime], rbx
0x18005eb24  mov     qword ptr [rsp+228h+var_1C0.dwLowDateTime], rbx
0x18005eb29  mov     qword ptr [rsp+228h+var_1D0.dwLowDateTime], rbx
0x18005eb2e  mov     [rsp+228h+var_1E8], ebx
0x18005eb32  lea     rdi, [rsi+8]
0x18005eb36  cmp     qword ptr [rdi+18h], 8
0x18005eb3b  jb      short loc_18005EB42
0x18005eb3d  mov     rcx, [rdi]
0x18005eb40  jmp     short loc_18005EB45
0x18005eb42  mov     rcx, rdi; lpFileName
0x18005eb45  lea     rax, [rsp+228h+var_1E8]
0x18005eb4a  mov     qword ptr [rsp+228h+dwCreationDisposition], rax; unsigned int *
0x18005eb4f  lea     r9, [rsp+228h+var_1D0]; struct _FILETIME *
0x18005eb54  lea     r8, [rsp+228h+var_1C0]; struct _FILETIME *
0x18005eb59  lea     rdx, [rsp+228h+var_1C8]; struct _FILETIME *
0x18005eb5e  call    ?SrmGetBasicInfoByName@@YAXPEBGPEAU_FILETIME@@11PEAK@Z; SrmGetBasicInfoByName(ushort const *,_FILETIME *,_FILETIME *,_FILETIME *,ulong *)
0x18005eb63  mov     eax, [rsp+228h+var_E0]
0x18005eb6a  mov     [rsp+228h+var_E0], eax
0x18005eb71  mov     r15d, [rsp+228h+var_1E8]
0x18005eb76  test    r15b, 1
0x18005eb7a  jnz     loc_18005ED43
0x18005eb80  mov     [rsp+228h+var_E0], ebx
0x18005eb87  mov     [rsp+228h+var_F8], 7
0x18005eb93  mov     [rsp+228h+var_100], rbx
0x18005eb9b  mov     word ptr [rsp+228h+lpFileName], bx
0x18005eba3  cmp     qword ptr [rdi+18h], 8
0x18005eba8  jb      short loc_18005EBAF
0x18005ebaa  mov     rcx, [rdi]
0x18005ebad  jmp     short loc_18005EBB2
0x18005ebaf  mov     rcx, rdi; unsigned __int16 *
0x18005ebb2  lea     r8, [rsp+228h+lpFileName]
0x18005ebba  mov     dl, r14b
0x18005ebbd  call    ?MakeTempCopy@CFsrmFileStream@@CAXPEBG_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CFsrmFileStream::MakeTempCopy(ushort const *,bool,std::wstring &)
0x18005ebc2  nop
0x18005ebc3  lea     rcx, [rsp+228h+lpFileName]
0x18005ebcb  cmp     [rsp+228h+var_F8], 8
0x18005ebd4  cmovnb  rcx, [rsp+228h+lpFileName]; lpFileName
0x18005ebdd  mov     [rsp+228h+hTemplateFile], rbx; hTemplateFile
0x18005ebe2  mov     dword ptr [rsp+228h+dwFlagsAndAttributes], 42000000h; dwFlagsAndAttributes
0x18005ebea  mov     [rsp+228h+dwCreationDisposition], 3; dwCreationDisposition
0x18005ebf2  xor     r9d, r9d; lpSecurityAttributes
0x18005ebf5  mov     edx, 0C0010000h; dwDesiredAccess
0x18005ebfa  lea     r8d, [r9+1]; dwShareMode
0x18005ebfe  call    cs:__imp_CreateFileW
0x18005ec04  mov     r14, rax
0x18005ec07  lea     r13, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18005ec0e  mov     [rsp+228h+var_1E0], r13
0x18005ec13  or      r12, 0FFFFFFFFFFFFFFFFh
0x18005ec17  mov     [rsp+228h+var_1D8], r12
0x18005ec1c  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18005ec23  mov     [rsp+228h+var_1E0], rax
0x18005ec28  mov     [rsp+228h+var_1D8], r14
0x18005ec2d  cmp     r14, r12
0x18005ec30  jz      loc_18005ED7B
0x18005ec36  mov     [rsp+228h+var_1D8], r12
0x18005ec3b  mov     rcx, [rsi+0F0h]; hObject
0x18005ec42  cmp     rcx, r12
0x18005ec45  jz      short loc_18005EC4D
0x18005ec47  call    cs:__imp_CloseHandle
0x18005ec4d  mov     [rsi+0F0h], r12
0x18005ec54  mov     [rsi+0F0h], r14
0x18005ec5b  lea     rcx, [rsi+30h]
0x18005ec5f  lea     rdx, [rsp+228h+lpFileName]
0x18005ec67  call    ?swap@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXAEAV12@@Z; std::wstring::swap(std::wstring &)
0x18005ec6c  mov     rdx, qword ptr [rsp+228h+var_1C8.dwLowDateTime]
0x18005ec71  mov     [rsi+110h], rdx
0x18005ec78  mov     rax, qword ptr [rsp+228h+var_1C0.dwLowDateTime]
0x18005ec7d  mov     [rsi+118h], rax
0x18005ec84  mov     rax, qword ptr [rsp+228h+var_1D0.dwLowDateTime]
0x18005ec89  mov     [rsi+120h], rax
0x18005ec90  mov     [rsi+5Ch], r15d
0x18005ec94  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18005ec9b  mov     [rsp+228h+var_1E0], rax
0x18005eca0  mov     [rsp+228h+var_1D8], r12
0x18005eca5  mov     [rsp+228h+var_1E0], r13
0x18005ecaa  mov     [rsp+228h+var_1D8], r12
0x18005ecaf  jmp     short loc_18005ECB3
0x18005ecb1  xor     ebx, ebx
0x18005ecb3  cmp     [rsp+228h+var_E0], ebx
0x18005ecba  jl      loc_18005EE03
0x18005ecc0  jmp     short loc_18005ECC6
0x18005ecc2  jmp     short loc_18005ECB1
0x18005ecc4  jmp     short loc_18005ECB1
0x18005ecc6  cmp     [rsp+228h+var_F8], 8
0x18005eccf  jb      short loc_18005ECDE
0x18005ecd1  mov     rcx, [rsp+228h+lpFileName]; Block
0x18005ecd9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005ecde  mov     [rsp+228h+var_F8], 7
0x18005ecea  mov     [rsp+228h+var_100], rbx
0x18005ecf2  mov     word ptr [rsp+228h+lpFileName], bx
0x18005ecfa  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005ed01  mov     [rsp+228h+var_E8], rax
0x18005ed09  lea     rcx, [rsp+228h+var_E8]; this
0x18005ed11  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18005ed16  mov     rcx, [rsp+228h+var_38]
0x18005ed1e  xor     rcx, rsp; StackCookie
0x18005ed21  call    __security_check_cookie
0x18005ed26  lea     r11, [rsp+228h+var_28]
0x18005ed2e  mov     rbx, [r11+40h]
0x18005ed32  mov     rsi, [r11+48h]
0x18005ed36  mov     rsp, r11
0x18005ed39  pop     r15
0x18005ed3b  pop     r14
0x18005ed3d  pop     r13
0x18005ed3f  pop     r12
0x18005ed41  pop     rdi
0x18005ed42  retn
0x18005ed43  mov     edx, 80071779h; int
0x18005ed48  lea     rcx, [rsp+228h+var_E8]; this
0x18005ed50  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005ed55  lea     rcx, [rsp+228h+var_E8]; this
0x18005ed5d  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005ed62  mov     r8d, eax; char
0x18005ed65  xor     r9d, r9d; unsigned __int16 *
0x18005ed68  mov     edx, 128h; unsigned int
0x18005ed6d  lea     rcx, [rsp+228h+var_E8]; this
0x18005ed75  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005ed7b  call    cs:__imp_GetLastError
0x18005ed81  mov     [rsi+58h], eax
0x18005ed84  cmp     qword ptr [rdi+18h], 8
0x18005ed89  jb      short loc_18005ED8E
0x18005ed8b  mov     rdi, [rdi]
0x18005ed8e  mov     dword ptr [rsp+228h+dwFlagsAndAttributes], eax
0x18005ed92  mov     qword ptr [rsp+228h+dwCreationDisposition], rdi
0x18005ed97  lea     r9, aErrorWhileOpen; "Error while opening file '%s': %d"
0x18005ed9e  mov     edx, 8Ch; unsigned int
0x18005eda3  mov     r8d, 155h; unsigned int
0x18005eda9  lea     rcx, [rsp+228h+var_E8]; this
0x18005edb1  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18005edb6  mov     [rsp+228h+var_E0], 80045343h
0x18005edc1  lea     rcx, [rsp+228h+var_E8]; this
0x18005edc9  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005edce  mov     edx, eax; int
0x18005edd0  lea     rcx, [rsp+228h+var_E8]; this
0x18005edd8  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005eddd  lea     rcx, [rsp+228h+var_E8]; this
0x18005ede5  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005edea  mov     r8d, eax; char
0x18005eded  xor     r9d, r9d; unsigned __int16 *
0x18005edf0  mov     edx, 156h; unsigned int
0x18005edf5  lea     rcx, [rsp+228h+var_E8]; this
0x18005edfd  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005ee03  lea     rcx, [rsp+228h+lpFileName]
0x18005ee0b  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18005ee10  mov     rcx, rax; lpFileName
0x18005ee13  call    cs:__imp_DeleteFileW
0x18005ee19  test    eax, eax
0x18005ee1b  jnz     short loc_18005EE5A
0x18005ee1d  call    cs:__imp_GetLastError
0x18005ee23  mov     edx, eax
0x18005ee25  lea     rcx, [rsp+228h+lpFileName]
0x18005ee2d  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18005ee32  mov     dword ptr [rsp+228h+dwFlagsAndAttributes], edx
0x18005ee36  mov     qword ptr [rsp+228h+dwCreationDisposition], rax
0x18005ee3b  lea     r9, aCannotDeleteTe; "Cannot delete temp copy '%s', error %ld"
0x18005ee42  mov     edx, 3Ch ; '<'; unsigned int
0x18005ee47  mov     r8d, 16Fh; unsigned int
0x18005ee4d  lea     rcx, [rsp+228h+var_E8]; this
0x18005ee55  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18005ee5a  lea     rcx, [rsp+228h+var_E8]; this
0x18005ee62  call    ?ReThrow@CSrmFunctionTracer@@QEAAXXZ; CSrmFunctionTracer::ReThrow(void)
```
