# CAdsCacheStream::SaveCacheStreamToDisk(bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void const *,ulong,__int64 *)

- ea: `0x18008ae3c`
- end: `0x18008b5cb`
- name: `?SaveCacheStreamToDisk@CAdsCacheStream@@SAX_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBXKPEA_J@Z`
- size: `1935`
- prototype: `void __fastcall(char, const WCHAR *, const void *, DWORD, _QWORD *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180047c30`

## callees

- `0x180001350`
- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x180010b24`
- `0x18001af28`
- `0x18003ecc4`
- `0x18006febc`
- `0x1800700b8`
- `0x180070648`
- `0x180072a80`
- `0x180073a80`
- `0x180073f54`
- `0x18007cc3c`
- `0x18007e234`
- `0x18007e410`
- `0x18008ae3c`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18008b263`
- `KERNEL32!WriteFile` at `0x18008b263`
- `KERNEL32!CreateFileW` at `0x18008b07b`
- `KERNEL32!CreateFileW` at `0x18008b205`
- `KERNEL32!CreateFileW` at `0x18008b07b`
- `KERNEL32!CreateFileW` at `0x18008b205`
- `KERNEL32!CloseHandle` at `0x18008b157`
- `KERNEL32!CloseHandle` at `0x18008b216`
- `KERNEL32!CloseHandle` at `0x18008b2fa`
- `KERNEL32!CloseHandle` at `0x18008b3b7`
- `KERNEL32!CloseHandle` at `0x18008b157`
- `KERNEL32!CloseHandle` at `0x18008b216`
- `KERNEL32!CloseHandle` at `0x18008b2fa`
- `KERNEL32!CloseHandle` at `0x18008b3b7`
- `KERNEL32!Sleep` at `0x18008b2c6`
- `KERNEL32!Sleep` at `0x18008b2c6`
- `KERNEL32!GetLastError` at `0x18008b293`
- `KERNEL32!GetLastError` at `0x18008b293`
- `KERNEL32!ReOpenFile` at `0x18008b111`
- `KERNEL32!ReOpenFile` at `0x18008b111`

## string_xrefs

- `0x18008ae9e`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x18008aeac`: `CAdsCacheStream::SaveCacheStreamToDisk`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CAdsCacheStream::SaveCacheStreamToDisk(char a1, const WCHAR *a2, const void *a3, DWORD a4, _QWORD *a5)
{
  __int64 v6; // rax
  void *v7; // rax
  LPCWSTR *v8; // rax
  const WCHAR *v9; // rcx
  __int64 v10; // rdx
  HANDLE FileW; // r12
  unsigned int v12; // r13d
  __int64 v13; // rdx
  __int64 v14; // rcx
  HANDLE v15; // r12
  unsigned int v16; // r13d
  int v17; // eax
  LPCWSTR v18; // r13
  const WCHAR *v19; // rcx
  HANDLE v20; // r12
  void *v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // rcx
  _QWORD *v24; // r13
  signed int LastError; // eax
  int v26; // r12d
  int v27; // eax
  int LastFailureAsHRESULT; // eax
  char Hr; // al
  int v30; // eax
  char v31; // al
  int v32; // eax
  char v33; // al
  int v34; // eax
  char v35; // al
  int v36; // eax
  char v37; // al
  int v38; // eax
  char v39; // al
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-288h]
  char v41; // [rsp+40h] [rbp-268h]
  unsigned int v43; // [rsp+44h] [rbp-264h] BYREF
  void **v44; // [rsp+48h] [rbp-260h]
  __int64 v45; // [rsp+50h] [rbp-258h]
  void **v46; // [rsp+58h] [rbp-250h]
  HANDLE hFile; // [rsp+60h] [rbp-248h]
  LPCWSTR *v48; // [rsp+68h] [rbp-240h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-238h] BYREF
  void **v50; // [rsp+78h] [rbp-230h]
  __int64 v51; // [rsp+80h] [rbp-228h]
  DWORD NumberOfBytesWritten; // [rsp+88h] [rbp-220h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+8Ch] [rbp-21Ch]
  struct _FILETIME v54; // [rsp+90h] [rbp-218h] BYREF
  struct _FILETIME v55; // [rsp+98h] [rbp-210h] BYREF
  struct _FILETIME v56; // [rsp+A0h] [rbp-208h] BYREF
  int v57; // [rsp+A8h] [rbp-200h]
  int v58; // [rsp+ACh] [rbp-1FCh] BYREF
  LPCWSTR v59; // [rsp+B0h] [rbp-1F8h]
  LPCVOID lpBuffer; // [rsp+B8h] [rbp-1F0h]
  _QWORD *v61; // [rsp+C0h] [rbp-1E8h]
  _com_error *v62; // [rsp+C8h] [rbp-1E0h] BYREF
  const exception *v63; // [rsp+D0h] [rbp-1D8h] BYREF
  _QWORD v64[3]; // [rsp+D8h] [rbp-1D0h] BYREF
  int v65; // [rsp+F0h] [rbp-1B8h]
  int v66; // [rsp+F4h] [rbp-1B4h]
  int v67; // [rsp+F8h] [rbp-1B0h]
  _DWORD v68[26]; // [rsp+100h] [rbp-1A8h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+168h] [rbp-140h] BYREF
  __int64 v70; // [rsp+178h] [rbp-130h]
  unsigned __int64 v71; // [rsp+180h] [rbp-128h]
  void **v72; // [rsp+190h] [rbp-118h] BYREF
  unsigned int v73; // [rsp+198h] [rbp-110h]
  unsigned int v74; // [rsp+1BCh] [rbp-ECh]
  void *Block[3]; // [rsp+240h] [rbp-68h] BYREF
  unsigned __int64 v76; // [rsp+258h] [rbp-50h]

  nNumberOfBytesToWrite = a4;
  lpBuffer = a3;
  v59 = a2;
  v61 = a5;
  hObject = v64;
  v64[0] = L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp";
  v64[1] = L"CAdsCacheStream::SaveCacheStreamToDisk";
  v64[2] = L"SRMADSCC";
  v65 = 682;
  v66 = 17;
  v67 = 255;
  v68[24] = 0x1000000;
  memset_0(v68, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v72, (const struct CSrmDebugInfo *)v64, 0);
  if ( a5 )
    *a5 = 0;
  v71 = 7;
  v70 = 0;
  LOWORD(lpFileName[0]) = 0;
  hFile = (HANDLE)-1LL;
  v46 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v45 = -1;
  v44 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v56 = 0;
  v55 = 0;
  v54 = 0;
  v43 = 0;
  v6 = std::wstring::rfind(a2, 58);
  v7 = (void *)std::wstring::substr(a2, Block, 0, v6);
  std::wstring::assign(lpFileName, v7);
  if ( v76 >= 8 )
    operator delete(Block[0]);
  v76 = 7;
  Block[2] = 0;
  LOWORD(Block[0]) = 0;
  v8 = lpFileName;
  if ( v71 >= 8 )
    v8 = (LPCWSTR *)lpFileName[0];
  v48 = v8;
  hObject = (HANDLE)1509;
  CSrmFunctionTracerBase::AddContext(&v72, 1, &hObject, &v48);
  v9 = (const WCHAR *)lpFileName;
  if ( v71 >= 8 )
    v9 = lpFileName[0];
  FileW = CreateFileW(v9, 0x100180u, 7u, 0, 3u, 0x2000000u, 0);
  hObject = FileW;
  hFile = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v73, v10);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v72, LastFailureAsHRESULT);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v72);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v72, 0x2D1u, Hr, 0);
  }
  v41 = 0;
  LODWORD(v48) = 0;
  v73 = 0;
  SrmGetBasicInfoByHandle(FileW, &v56, &v55, &v54, &v43);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v12 = v43;
    if ( (v43 & 1) != 0 && a1 )
    {
      v15 = ReOpenFile(FileW, 0x100101u, 5u, 0x2000000u);
      v50 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
      v51 = (__int64)v15;
      if ( v15 == (HANDLE)-1LL )
      {
        v32 = GetLastFailureAsHRESULT(v14, v13);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v72, v32);
        v33 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v72);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v72, 0x2DEu, v33, 0);
      }
      v73 = 0;
      CloseHandle(hObject);
      v51 = -1;
      hFile = v15;
      v16 = v12 & 0xFFFFFFFE;
      if ( !v16 )
        v16 = 128;
      v17 = SrmSetBasicInfoByHandle(v15, 0, 0, 0, v16);
      v73 = v17;
      if ( v17 < 0 )
      {
        v30 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v72);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v72, v30);
        v31 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v72);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v72, 0x2E9u, v31, 0);
      }
      v73 = v17;
      v41 = 1;
      v50 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
      v51 = -1;
    }
    v18 = v59;
    while ( 1 )
    {
      v19 = *((_QWORD *)v18 + 3) < 8u ? v18 : *(const WCHAR **)v18;
      v20 = CreateFileW(v19, 0x100106u, 4u, 0, 2u, 0x2000000u, 0);
      v21 = v20;
      v45 = (__int64)v20;
      if ( v20 != (HANDLE)-1LL )
        break;
      LastError = GetLastError();
      if ( LastError != 32 )
      {
        if ( LastError > 0 )
LABEL_45:
          LastError = (unsigned __int16)LastError | 0x80070000;
        v73 = LastError;
        v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v72);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v72, v36);
        v37 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v72);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v72, 0x30Eu, v37, 0);
      }
      LODWORD(v48) = (_DWORD)v48 + 1;
      v57 = (int)v48;
      if ( (unsigned int)v48 >= 5 )
        goto LABEL_45;
      Sleep(0xFAu);
    }
    NumberOfBytesWritten = 0;
    if ( !WriteFile(v20, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
    {
      v34 = GetLastFailureAsHRESULT(v23, v22);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v72, v34);
      v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v72);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v72, 0x332u, v35, 0);
    }
    v73 = 0;
    v24 = v61;
    if ( v61 )
      *v24 = SrmWriteCloseUsnRecord(v20);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v58) )
    {
      CSrmFunctionTracer::HandleHresultException(
        (CSrmFunctionTracer *)&v72,
        v58,
        L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
        L"SRMADSCC",
        L"CAdsCacheStream::SaveCacheStreamToDisk",
        0x33Bu,
        v74);
      v21 = (void *)v45;
      __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_18008B2D1);
      goto LABEL_29;
    }
    if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', &v62) )
      CSrmFunctionTracer::HandleComException(
        (CSrmFunctionTracer *)&v72,
        v62,
        L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
        L"SRMADSCC",
        L"CAdsCacheStream::SaveCacheStreamToDisk",
        0x33Bu,
        v74);
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      CSrmFunctionTracer::HandleStdBadAllocException(
        (CSrmFunctionTracer *)&v72,
        L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
        L"SRMADSCC",
        L"CAdsCacheStream::SaveCacheStreamToDisk",
        0x33Bu,
        v74);
      v21 = (void *)v45;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18008B35B);
      goto LABEL_29;
    }
    if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', &v63) )
      CSrmFunctionTracer::HandleStdGenericException(
        (CSrmFunctionTracer *)&v72,
        v63,
        L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
        L"SRMADSCC",
        L"CAdsCacheStream::SaveCacheStreamToDisk",
        0x33Bu,
        v74);
  }
LABEL_29:
  v26 = v73;
  if ( v21 != (void *)-1LL )
    CloseHandle(v21);
  v45 = -1;
  v27 = SrmSetBasicInfoByHandle(hFile, v56, v55, v54, v41 != 0 ? v43 : 0);
  v73 = v27;
  if ( v27 < 0 )
  {
    if ( v41 )
      CSrmFunctionTracer::ReThrow((CSrmFunctionTracer *)&v72);
    dwCreationDisposition[0] = v27;
    CSrmFunctionTracer::Trace(
      (CSrmFunctionTracer *)&v72,
      0x3Cu,
      0x355u,
      L"Failed to restore file times, error 0x%08lX",
      *(_QWORD *)dwCreationDisposition);
  }
  v73 = v26;
  if ( v26 < 0 )
  {
    v38 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v72);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v72, v38);
    v39 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v72);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v72, 0x358u, v39, 0);
  }
  v73 = v26;
  v44 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
  v45 = -1;
  v46 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  if ( hFile != (HANDLE)-1LL )
    CloseHandle(hFile);
  v46 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
  hFile = (HANDLE)-1LL;
  if ( v71 >= 8 )
    operator delete((void *)lpFileName[0]);
  v71 = 7;
  v70 = 0;
  LOWORD(lpFileName[0]) = 0;
  v72 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v72);
}

```

## disassembly

```asm
0x18008ae3c  mov     r11, rsp
0x18008ae3f  push    rbx
0x18008ae40  push    rsi
0x18008ae41  push    rdi
0x18008ae42  push    r12
0x18008ae44  push    r13
0x18008ae46  push    r14
0x18008ae48  push    r15
0x18008ae4a  sub     rsp, 270h
0x18008ae51  mov     rax, cs:__security_cookie
0x18008ae58  xor     rax, rsp
0x18008ae5b  mov     [rsp+2A8h+var_40], rax
0x18008ae63  mov     [rsp+2A8h+nNumberOfBytesToWrite], r9d
0x18008ae6b  mov     [rsp+2A8h+lpBuffer], r8
0x18008ae73  mov     r12, rdx
0x18008ae76  mov     [rsp+2A8h+var_1F8], rdx
0x18008ae7e  mov     [rsp+2A8h+var_267], cl
0x18008ae82  mov     rdi, [rsp+2A8h+arg_20]
0x18008ae8a  mov     [rsp+2A8h+var_1E8], rdi
0x18008ae92  lea     rax, [r11-1D0h]
0x18008ae99  mov     [rsp+2A8h+hObject], rax
0x18008ae9e  lea     rax, aBaseFsFsrmUtil; "base\\fs\\fsrm\\utilities\\property\\sr"...
0x18008aea5  mov     [r11-1D0h], rax
0x18008aeac  lea     rax, aCadscachestrea_9; "CAdsCacheStream::SaveCacheStreamToDisk"
0x18008aeb3  mov     [r11-1C8h], rax
0x18008aeba  lea     rax, aSrmadscc; "SRMADSCC"
0x18008aec1  mov     [r11-1C0h], rax
0x18008aec8  mov     [rsp+2A8h+var_1B8], 2AAh
0x18008aed3  mov     [rsp+2A8h+var_1B4], 11h
0x18008aede  mov     [rsp+2A8h+var_1B0], 0FFh
0x18008aee9  xor     ebx, ebx
0x18008aeeb  mov     [rsp+2A8h+var_148], 1000000h
0x18008aef6  xor     edx, edx; Val
0x18008aef8  lea     r8d, [rbx+60h]; Size
0x18008aefc  lea     rcx, [r11-1A8h]; void *
0x18008af03  call    memset_0
0x18008af08  nop
0x18008af09  xor     r8d, r8d
0x18008af0c  lea     rdx, [rsp+2A8h+var_1D0]
0x18008af14  lea     rcx, [rsp+2A8h+var_118]
0x18008af1c  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18008af21  nop
0x18008af22  test    rdi, rdi
0x18008af25  jz      short loc_18008AF2A
0x18008af27  mov     [rdi], rbx
0x18008af2a  mov     [rsp+2A8h+var_128], 7
0x18008af36  mov     [rsp+2A8h+var_130], rbx
0x18008af3e  mov     word ptr [rsp+2A8h+lpFileName], bx
0x18008af46  lea     r14, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18008af4d  mov     [rsp+2A8h+var_250], r14
0x18008af52  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008af56  mov     [rsp+2A8h+hFile], rdi
0x18008af5b  lea     r15, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18008af62  mov     [rsp+2A8h+var_250], r15
0x18008af67  mov     [rsp+2A8h+var_260], r14
0x18008af6c  mov     rsi, rdi
0x18008af6f  mov     [rsp+2A8h+var_258], rdi
0x18008af74  mov     [rsp+2A8h+var_260], r15
0x18008af79  mov     qword ptr [rsp+2A8h+var_208.dwLowDateTime], rbx
0x18008af81  mov     qword ptr [rsp+2A8h+var_210.dwLowDateTime], rbx
0x18008af89  mov     qword ptr [rsp+2A8h+var_218.dwLowDateTime], rbx
0x18008af91  mov     [rsp+2A8h+var_264], ebx
0x18008af95  lea     edx, [rdi+3Bh]
0x18008af98  mov     rcx, r12
0x18008af9b  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x18008afa0  mov     r9, rax
0x18008afa3  xor     r8d, r8d
0x18008afa6  lea     rdx, [rsp+2A8h+Block]
0x18008afae  mov     rcx, r12
0x18008afb1  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18008afb6  nop
0x18008afb7  mov     rdx, rax; Src
0x18008afba  lea     rcx, [rsp+2A8h+lpFileName]; void *
0x18008afc2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x18008afc7  nop
0x18008afc8  cmp     [rsp+2A8h+var_50], 8
0x18008afd1  jb      short loc_18008AFE0
0x18008afd3  mov     rcx, [rsp+2A8h+Block]; Block
0x18008afdb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008afe0  mov     [rsp+2A8h+var_50], 7
0x18008afec  mov     [rsp+2A8h+var_58], rbx
0x18008aff4  mov     word ptr [rsp+2A8h+Block], bx
0x18008affc  lea     rax, [rsp+2A8h+lpFileName]
0x18008b004  cmp     [rsp+2A8h+var_128], 8
0x18008b00d  cmovnb  rax, [rsp+2A8h+lpFileName]
0x18008b016  mov     [rsp+2A8h+var_240], rax
0x18008b01b  mov     [rsp+2A8h+hObject], 5E5h
0x18008b024  lea     r9, [rsp+2A8h+var_240]
0x18008b029  lea     r8, [rsp+2A8h+hObject]
0x18008b02e  mov     edx, 1
0x18008b033  lea     rcx, [rsp+2A8h+var_118]
0x18008b03b  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x18008b040  lea     rcx, [rsp+2A8h+lpFileName]
0x18008b048  cmp     [rsp+2A8h+var_128], 8
0x18008b051  cmovnb  rcx, [rsp+2A8h+lpFileName]; lpFileName
0x18008b05a  mov     [rsp+2A8h+hTemplateFile], rbx; hTemplateFile
0x18008b05f  mov     [rsp+2A8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18008b067  mov     [rsp+2A8h+dwCreationDisposition], 3; dwCreationDisposition
0x18008b06f  xor     r9d, r9d; lpSecurityAttributes
0x18008b072  mov     edx, 100180h; dwDesiredAccess
0x18008b077  lea     r8d, [r9+7]; dwShareMode
0x18008b07b  call    cs:__imp_CreateFileW
0x18008b081  mov     r12, rax
0x18008b084  mov     [rsp+2A8h+hObject], rax
0x18008b089  mov     [rsp+2A8h+hFile], rdi
0x18008b08e  mov     [rsp+2A8h+hFile], rax
0x18008b093  mov     ecx, [rsp+2A8h+var_110]
0x18008b09a  mov     [rsp+2A8h+var_110], ecx
0x18008b0a1  cmp     rax, rdi
0x18008b0a4  jz      loc_18008B43F
0x18008b0aa  mov     [rsp+2A8h+var_268], bl
0x18008b0ae  mov     dword ptr [rsp+2A8h+var_240], ebx
0x18008b0b2  mov     [rsp+2A8h+var_110], ebx
0x18008b0b9  lea     rax, [rsp+2A8h+var_264]
0x18008b0be  mov     qword ptr [rsp+2A8h+dwCreationDisposition], rax; unsigned int *
0x18008b0c3  lea     r9, [rsp+2A8h+var_218]; struct _FILETIME *
0x18008b0cb  lea     r8, [rsp+2A8h+var_210]; struct _FILETIME *
0x18008b0d3  lea     rdx, [rsp+2A8h+var_208]; struct _FILETIME *
0x18008b0db  mov     rcx, r12; hFile
0x18008b0de  call    ?SrmGetBasicInfoByHandle@@YAXPEAXPEAU_FILETIME@@11PEAK@Z; SrmGetBasicInfoByHandle(void *,_FILETIME *,_FILETIME *,_FILETIME *,ulong *)
0x18008b0e3  nop
0x18008b0e4  mov     r13d, [rsp+2A8h+var_264]
0x18008b0e9  test    r13b, 1
0x18008b0ed  jz      loc_18008B1CC
0x18008b0f3  cmp     [rsp+2A8h+var_267], bl
0x18008b0f7  jz      loc_18008B1CC
0x18008b0fd  mov     edx, 100101h; dwDesiredAccess
0x18008b102  mov     r9d, 2000000h; dwFlagsAndAttributes
0x18008b108  mov     r8d, 5; dwShareMode
0x18008b10e  mov     rcx, r12; hOriginalFile
0x18008b111  call    cs:__imp_ReOpenFile
0x18008b117  mov     r12, rax
0x18008b11a  mov     [rsp+2A8h+var_230], r14
0x18008b11f  mov     [rsp+2A8h+var_228], rdi
0x18008b127  mov     [rsp+2A8h+var_230], r15
0x18008b12c  mov     [rsp+2A8h+var_228], rax
0x18008b134  mov     eax, [rsp+2A8h+var_110]
0x18008b13b  mov     [rsp+2A8h+var_110], eax
0x18008b142  cmp     r12, rdi
0x18008b145  jz      loc_18008B4BB
0x18008b14b  mov     [rsp+2A8h+var_110], ebx
0x18008b152  mov     rcx, [rsp+2A8h+hObject]; hObject
0x18008b157  call    cs:__imp_CloseHandle
0x18008b15d  mov     [rsp+2A8h+hFile], rdi
0x18008b162  mov     [rsp+2A8h+var_228], rdi
0x18008b16a  mov     [rsp+2A8h+hFile], rdi
0x18008b16f  mov     [rsp+2A8h+hFile], r12
0x18008b174  and     r13d, 0FFFFFFFEh
0x18008b178  mov     eax, 80h
0x18008b17d  cmovz   r13d, eax
0x18008b181  mov     [rsp+2A8h+dwCreationDisposition], r13d; unsigned int
0x18008b186  mov     r9, rbx; struct _FILETIME
0x18008b189  mov     r8, rbx; struct _FILETIME
0x18008b18c  mov     rdx, rbx; struct _FILETIME
0x18008b18f  mov     rcx, r12; hFile
0x18008b192  call    ?SrmSetBasicInfoByHandle@@YAJPEAXU_FILETIME@@11K@Z; SrmSetBasicInfoByHandle(void *,_FILETIME,_FILETIME,_FILETIME,ulong)
0x18008b197  mov     [rsp+2A8h+var_110], eax
0x18008b19e  test    eax, eax
0x18008b1a0  js      loc_18008B47A
0x18008b1a6  mov     [rsp+2A8h+var_110], eax
0x18008b1ad  mov     [rsp+2A8h+var_268], 1
0x18008b1b2  mov     [rsp+2A8h+var_230], r15
0x18008b1b7  mov     [rsp+2A8h+var_228], rdi
0x18008b1bf  mov     [rsp+2A8h+var_230], r14
0x18008b1c4  mov     [rsp+2A8h+var_228], rdi
0x18008b1cc  mov     r13, [rsp+2A8h+var_1F8]
0x18008b1d4  cmp     qword ptr [r13+18h], 8
0x18008b1d9  jb      short loc_18008B1E1
0x18008b1db  mov     rcx, [r13+0]
0x18008b1df  jmp     short loc_18008B1E4
0x18008b1e1  mov     rcx, r13; lpFileName
0x18008b1e4  mov     [rsp+2A8h+hTemplateFile], rbx; hTemplateFile
0x18008b1e9  mov     [rsp+2A8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18008b1f1  mov     [rsp+2A8h+dwCreationDisposition], 2; dwCreationDisposition
0x18008b1f9  xor     r9d, r9d; lpSecurityAttributes
0x18008b1fc  mov     edx, 100106h; dwDesiredAccess
0x18008b201  lea     r8d, [r9+4]; dwShareMode
0x18008b205  call    cs:__imp_CreateFileW
0x18008b20b  mov     r12, rax
0x18008b20e  cmp     rsi, rdi
0x18008b211  jz      short loc_18008B21C
0x18008b213  mov     rcx, rsi; hObject
0x18008b216  call    cs:__imp_CloseHandle
0x18008b21c  mov     [rsp+2A8h+var_258], rdi
0x18008b221  mov     rsi, r12
0x18008b224  mov     [rsp+2A8h+var_258], r12
0x18008b229  cmp     r12, rdi
0x18008b22c  jz      short loc_18008B293
0x18008b22e  mov     [rsp+2A8h+NumberOfBytesWritten], ebx
0x18008b235  mov     eax, [rsp+2A8h+var_110]
0x18008b23c  mov     [rsp+2A8h+var_110], eax
0x18008b243  mov     qword ptr [rsp+2A8h+dwCreationDisposition], rbx; lpOverlapped
0x18008b248  lea     r9, [rsp+2A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008b250  mov     r8d, [rsp+2A8h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18008b258  mov     rdx, [rsp+2A8h+lpBuffer]; lpBuffer
0x18008b260  mov     rcx, r12; hFile
0x18008b263  call    cs:__imp_WriteFile
0x18008b269  test    eax, eax
0x18008b26b  jz      loc_18008B4F5
0x18008b271  mov     [rsp+2A8h+var_110], ebx
0x18008b278  mov     r13, [rsp+2A8h+var_1E8]
0x18008b280  test    r13, r13
0x18008b283  jz      short loc_18008B291
0x18008b285  mov     rcx, r12; hFile
0x18008b288  call    ?SrmWriteCloseUsnRecord@@YA_JPEAX@Z; SrmWriteCloseUsnRecord(void *)
0x18008b28d  mov     [r13+0], rax
0x18008b291  jmp     short loc_18008B2EA
0x18008b293  call    cs:__imp_GetLastError
0x18008b299  cmp     eax, 20h ; ' '
0x18008b29c  jnz     loc_18008B52E
0x18008b2a2  mov     r12d, dword ptr [rsp+2A8h+var_240]
0x18008b2a7  inc     r12d
0x18008b2aa  mov     dword ptr [rsp+2A8h+var_240], r12d
0x18008b2af  mov     [rsp+2A8h+var_200], r12d
0x18008b2b7  cmp     r12d, 5
0x18008b2bb  jnb     loc_18008B532
0x18008b2c1  mov     ecx, 0FAh; dwMilliseconds
0x18008b2c6  call    cs:__imp_Sleep
0x18008b2cc  jmp     loc_18008B1D4
0x18008b2d1  xor     ebx, ebx
0x18008b2d3  mov     rsi, [rsp+2A8h+var_258]
0x18008b2d8  lea     r15, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18008b2df  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008b2e3  lea     r14, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18008b2ea  mov     r12d, [rsp+2A8h+var_110]
0x18008b2f2  cmp     rsi, rdi
0x18008b2f5  jz      short loc_18008B300
0x18008b2f7  mov     rcx, rsi; hObject
0x18008b2fa  call    cs:__imp_CloseHandle
0x18008b300  mov     [rsp+2A8h+var_258], rdi
0x18008b305  mov     al, [rsp+2A8h+var_268]
0x18008b309  neg     al
0x18008b30b  sbb     ecx, ecx
0x18008b30d  and     ecx, [rsp+2A8h+var_264]
0x18008b311  mov     [rsp+2A8h+dwCreationDisposition], ecx; unsigned int
0x18008b315  mov     r9, qword ptr [rsp+2A8h+var_218.dwLowDateTime]; struct _FILETIME
0x18008b31d  mov     r8, qword ptr [rsp+2A8h+var_210.dwLowDateTime]; struct _FILETIME
0x18008b325  mov     rdx, qword ptr [rsp+2A8h+var_208.dwLowDateTime]; struct _FILETIME
0x18008b32d  mov     rcx, [rsp+2A8h+hFile]; hFile
0x18008b332  call    ?SrmSetBasicInfoByHandle@@YAJPEAXU_FILETIME@@11K@Z; SrmSetBasicInfoByHandle(void *,_FILETIME,_FILETIME,_FILETIME,ulong)
0x18008b337  mov     [rsp+2A8h+var_110], eax
0x18008b33e  test    eax, eax
0x18008b340  jns     short loc_18008B37B
0x18008b342  lea     rcx, [rsp+2A8h+var_118]; this
0x18008b34a  cmp     [rsp+2A8h+var_268], bl
0x18008b34e  jnz     loc_18008B583
0x18008b354  jmp     short loc_18008B360
0x18008b356  jmp     loc_18008B2D1
0x18008b35b  jmp     loc_18008B2D1
0x18008b360  mov     [rsp+2A8h+dwCreationDisposition], eax
0x18008b364  lea     r9, aFailedToRestor; "Failed to restore file times, error 0x%"...
0x18008b36b  mov     edx, 3Ch ; '<'; unsigned int
0x18008b370  mov     r8d, 355h; unsigned int
0x18008b376  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18008b37b  mov     [rsp+2A8h+var_110], r12d
0x18008b383  test    r12d, r12d
0x18008b386  js      loc_18008B589
0x18008b38c  mov     [rsp+2A8h+var_110], r12d
0x18008b394  mov     [rsp+2A8h+var_260], r15
0x18008b399  mov     [rsp+2A8h+var_258], rdi
0x18008b39e  mov     [rsp+2A8h+var_260], r14
0x18008b3a3  mov     [rsp+2A8h+var_258], rdi
0x18008b3a8  mov     [rsp+2A8h+var_250], r15
0x18008b3ad  mov     rcx, [rsp+2A8h+hFile]; hObject
0x18008b3b2  cmp     rcx, rdi
0x18008b3b5  jz      short loc_18008B3BD
0x18008b3b7  call    cs:__imp_CloseHandle
0x18008b3bd  mov     [rsp+2A8h+hFile], rdi
0x18008b3c2  mov     [rsp+2A8h+var_250], r14
0x18008b3c7  mov     [rsp+2A8h+hFile], rdi
0x18008b3cc  cmp     [rsp+2A8h+var_128], 8
0x18008b3d5  jb      short loc_18008B3E4
0x18008b3d7  mov     rcx, [rsp+2A8h+lpFileName]; Block
0x18008b3df  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008b3e4  mov     [rsp+2A8h+var_128], 7
0x18008b3f0  mov     [rsp+2A8h+var_130], rbx
0x18008b3f8  mov     word ptr [rsp+2A8h+lpFileName], bx
0x18008b400  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18008b407  mov     [rsp+2A8h+var_118], rax
0x18008b40f  lea     rcx, [rsp+2A8h+var_118]; this
0x18008b417  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18008b41c  mov     rcx, [rsp+2A8h+var_40]
0x18008b424  xor     rcx, rsp; StackCookie
0x18008b427  call    __security_check_cookie
0x18008b42c  add     rsp, 270h
0x18008b433  pop     r15
0x18008b435  pop     r14
0x18008b437  pop     r13
0x18008b439  pop     r12
0x18008b43b  pop     rdi
0x18008b43c  pop     rsi
0x18008b43d  pop     rbx
0x18008b43e  retn
0x18008b43f  call    GetLastFailureAsHRESULT
0x18008b444  nop
0x18008b445  mov     edx, eax; int
0x18008b447  lea     rcx, [rsp+2A8h+var_118]; this
0x18008b44f  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18008b454  lea     rcx, [rsp+2A8h+var_118]; this
0x18008b45c  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
  ... truncated ...
```
