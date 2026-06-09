# CAdsCacheStream::LoadCacheStreamFromDisk(ulong,bool)

- ea: `0x18008a024`
- end: `0x18008a5f1`
- name: `?LoadCacheStreamFromDisk@CAdsCacheStream@@QEAA_NK_N@Z`
- size: `1485`
- prototype: `bool __fastcall(CAdsCacheStream *__hidden this, unsigned int, bool)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180046a80`
- `0x1800473c0`

## callees

- `0x180001350`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000ee10`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073d04`
- `0x180073f54`
- `0x18007c000`
- `0x18007c030`
- `0x180084bc4`
- `0x1800889d4`
- `0x18008a024`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18008a2da`
- `KERNEL32!ReadFile` at `0x18008a2da`
- `KERNEL32!CloseHandle` at `0x18008a198`
- `KERNEL32!CloseHandle` at `0x18008a307`
- `KERNEL32!CloseHandle` at `0x18008a198`
- `KERNEL32!CloseHandle` at `0x18008a307`
- `KERNEL32!Sleep` at `0x18008a1dd`
- `KERNEL32!Sleep` at `0x18008a1dd`
- `KERNEL32!GetLastError` at `0x18008a1b9`
- `KERNEL32!GetLastError` at `0x18008a426`
- `KERNEL32!GetLastError` at `0x18008a42e`
- `KERNEL32!GetLastError` at `0x18008a573`
- `KERNEL32!GetLastError` at `0x18008a57b`
- `KERNEL32!GetLastError` at `0x18008a1b9`
- `KERNEL32!GetLastError` at `0x18008a426`
- `KERNEL32!GetLastError` at `0x18008a42e`
- `KERNEL32!GetLastError` at `0x18008a573`
- `KERNEL32!GetLastError` at `0x18008a57b`
- `KERNEL32!GetFileSizeEx` at `0x18008a28b`
- `KERNEL32!GetFileSizeEx` at `0x18008a28b`

## string_xrefs

- `0x18008a1fb`: `Cache does not exist for file '%s'`
- `0x18008a065`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x18008a3b4`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x18008a46b`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x18008a4d8`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x18008a53d`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x18008a5b8`: `base\fs\fsrm\utilities\property\srmadscache.cpp`
- `0x18008a071`: `CAdsCacheStream::LoadCacheStreamFromDisk`
- `0x18008a3a6`: `CAdsCacheStream::LoadCacheStreamFromDisk`
- `0x18008a45d`: `CAdsCacheStream::LoadCacheStreamFromDisk`
- `0x18008a4ca`: `CAdsCacheStream::LoadCacheStreamFromDisk`
- `0x18008a52f`: `CAdsCacheStream::LoadCacheStreamFromDisk`
- `0x18008a5aa`: `CAdsCacheStream::LoadCacheStreamFromDisk`
- `0x18008a137`: `Loading property cache from file: %s`
- `0x18008a559`: `Cache file '%s' is too large: size = %i64d`
- `0x18008a5ce`: `L"ReadFile"`
- `0x18008a4ef`: `Cache file '%s' is empty`
- `0x18008a3cb`: `Cache file '%s' is invalid or corrupt`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall CAdsCacheStream::LoadCacheStreamFromDisk(DWORD **this, unsigned int a2, unsigned __int8 a3)
{
  int v3; // r15d
  union _LARGE_INTEGER v4; // r12
  int v6; // esi
  __int64 v7; // rdx
  void **v8; // rax
  void **v9; // rcx
  HANDLE FileWithAlternateAccess; // rdi
  signed int LastError; // eax
  void **v12; // rax
  union _LARGE_INTEGER v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rax
  int Hr; // eax
  char v18; // al
  DWORD v19; // edi
  signed int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rax
  DWORD v27; // edi
  signed int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rax
  struct _SECURITY_ATTRIBUTES *lpOverlapped; // [rsp+20h] [rbp-E0h]
  unsigned int v32; // [rsp+28h] [rbp-D8h]
  __int64 v33; // [rsp+28h] [rbp-D8h]
  __int64 v34; // [rsp+28h] [rbp-D8h]
  void *v35; // [rsp+38h] [rbp-C8h]
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v37; // [rsp+68h] [rbp-98h]
  union _LARGE_INTEGER FileSize; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v39[3]; // [rsp+78h] [rbp-88h] BYREF
  int v40; // [rsp+90h] [rbp-70h]
  int v41; // [rsp+94h] [rbp-6Ch]
  int v42; // [rsp+98h] [rbp-68h]
  _BYTE v43[96]; // [rsp+A0h] [rbp-60h] BYREF
  int v44; // [rsp+100h] [rbp+0h]
  void *Block[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v46; // [rsp+118h] [rbp+18h]
  unsigned __int64 v47; // [rsp+120h] [rbp+20h]
  void **v48; // [rsp+130h] [rbp+30h] BYREF
  signed int v49; // [rsp+138h] [rbp+38h]

  v3 = a3;
  v4.QuadPart = a2;
  v37 = v39;
  v39[0] = L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp";
  v39[1] = L"CAdsCacheStream::LoadCacheStreamFromDisk";
  v39[2] = L"SRMADSCC";
  v40 = 152;
  v41 = 17;
  v42 = 255;
  v44 = 0x1000000;
  memset_0(v43, 0, sizeof(v43));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v48, (const struct CSrmDebugInfo *)v39, 0);
  v47 = 7;
  v46 = 0;
  LOWORD(Block[0]) = 0;
  v6 = 0;
  LOBYTE(v7) = v3;
  CPropertyBagFieldsBase::BuildFullPath(*this, v7, L"FSRM{ef88c031-5950-4164-ab92-eec5f16005a5}", Block);
  SrmConvertToLongPath(Block);
  v8 = Block;
  if ( v47 >= 8 )
    v8 = (void **)Block[0];
  CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v48, 0x8Cu, 0xACu, L"Loading property cache from file: %s", v8);
  while ( 1 )
  {
    v9 = Block;
    if ( v47 >= 8 )
      v9 = (void **)Block[0];
    FileWithAlternateAccess = SrmCreateFileWithAlternateAccess(
                                (LPCWSTR)v9,
                                (v3 << 8) + 1048705,
                                0x100081u,
                                1u,
                                lpOverlapped,
                                v32,
                                0x2000000u,
                                v35,
                                v3,
                                0);
    if ( FileWithAlternateAccess != (HANDLE)-1LL )
      break;
    LastError = GetLastError();
    if ( LastError == 2 )
    {
      v12 = Block;
      if ( v47 >= 8 )
        v12 = (void **)Block[0];
      CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v48, 0x8Cu, 0xC8u, L"Cache does not exist for file '%s'", v12);
      if ( v47 >= 8 )
        operator delete(Block[0]);
      v47 = 7;
      v46 = 0;
      LOWORD(Block[0]) = 0;
      v48 = &CSrmFunctionTracer::`vftable';
      CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v48);
      return 0;
    }
    if ( LastError != 32 )
    {
      if ( LastError > 0 )
LABEL_26:
        LastError = (unsigned __int16)LastError | 0x80070000;
      v49 = LastError;
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v48);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v48, Hr);
      v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v48);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v48, 0xCFu, v18, 0);
    }
    if ( (unsigned int)++v6 >= 5 )
      goto LABEL_26;
    Sleep(0xFAu);
  }
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileWithAlternateAccess, &FileSize) )
  {
    v19 = GetLastError();
    v20 = GetLastError();
    v21 = v20;
    if ( v20 > 0 )
      v21 = (unsigned __int16)v20 | 0x80070000;
    v37 = v39;
    v22 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v39,
            (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
            (__int64)L"SRMADSCC",
            (__int64)L"CAdsCacheStream::LoadCacheStreamFromDisk",
            217,
            17);
    LODWORD(v33) = v19;
    CSrmFunctionTracer::Throw(&v48, v22, v21, L"Win32 call %s failed [GetLastError() = %u]", "L\"GetFileSizeEx\"", v33);
  }
  v14 = FileSize;
  if ( !FileSize.QuadPart )
  {
    v23 = std::wstring::c_str(Block);
    v37 = v39;
    v24 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v39,
            (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
            (__int64)L"SRMADSCC",
            (__int64)L"CAdsCacheStream::LoadCacheStreamFromDisk",
            222,
            17);
    CSrmFunctionTracer::Throw(&v48, v24, 2147767109LL, L"Cache file '%s' is empty", v23);
  }
  if ( FileSize.QuadPart > v4.QuadPart )
  {
    v25 = std::wstring::c_str(Block);
    v37 = v39;
    v26 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v39,
            (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
            (__int64)L"SRMADSCC",
            (__int64)L"CAdsCacheStream::LoadCacheStreamFromDisk",
            227,
            17);
    CSrmFunctionTracer::Throw(&v48, v26, 2147767109LL, L"Cache file '%s' is too large: size = %i64d", v25, v14.QuadPart);
  }
  CAdsCacheStream::Allocate((CAdsCacheStream *)this);
  NumberOfBytesRead = 0;
  if ( !ReadFile(FileWithAlternateAccess, this[6] + 1, *this[6], &NumberOfBytesRead, 0) )
  {
    v27 = GetLastError();
    v28 = GetLastError();
    v29 = v28;
    if ( v28 > 0 )
      v29 = (unsigned __int16)v28 | 0x80070000;
    v37 = v39;
    v30 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v39,
            (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
            (__int64)L"SRMADSCC",
            (__int64)L"CAdsCacheStream::LoadCacheStreamFromDisk",
            244,
            17);
    LODWORD(v34) = v27;
    CSrmFunctionTracer::Throw(&v48, v30, v29, L"Win32 call %s failed [GetLastError() = %u]", "L\"ReadFile\"", v34);
  }
  if ( NumberOfBytesRead != *this[6] )
  {
    v15 = std::wstring::c_str(Block);
    v37 = v39;
    v16 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v39,
            (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmadscache.cpp",
            (__int64)L"SRMADSCC",
            (__int64)L"CAdsCacheStream::LoadCacheStreamFromDisk",
            249,
            17);
    CSrmFunctionTracer::Throw(&v48, v16, 2147767109LL, L"Cache file '%s' is invalid or corrupt", v15);
  }
  CloseHandle(FileWithAlternateAccess);
  if ( v47 >= 8 )
    operator delete(Block[0]);
  v47 = 7;
  v46 = 0;
  LOWORD(Block[0]) = 0;
  v48 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v48);
  return 1;
}

```

## disassembly

```asm
0x18008a024  push    rbp
0x18008a026  push    rbx
0x18008a027  push    rsi
0x18008a028  push    rdi
0x18008a029  push    r12
0x18008a02b  push    r13
0x18008a02d  push    r14
0x18008a02f  push    r15
0x18008a031  lea     rbp, [rsp-0F8h]
0x18008a039  sub     rsp, 1F8h
0x18008a040  mov     rax, cs:__security_cookie
0x18008a047  xor     rax, rsp
0x18008a04a  mov     [rbp+130h+var_50], rax
0x18008a051  movzx   r15d, r8b
0x18008a055  mov     r12d, edx
0x18008a058  mov     r14, rcx
0x18008a05b  lea     rax, [rsp+230h+var_1B8]
0x18008a060  mov     [rsp+230h+var_1C8], rax
0x18008a065  lea     rax, aBaseFsFsrmUtil; "base\\fs\\fsrm\\utilities\\property\\sr"...
0x18008a06c  mov     [rsp+230h+var_1B8], rax
0x18008a071  lea     rax, aCadscachestrea_2; "CAdsCacheStream::LoadCacheStreamFromDis"...
0x18008a078  mov     [rbp+130h+var_1B0], rax
0x18008a07c  lea     rax, aSrmadscc; "SRMADSCC"
0x18008a083  mov     [rbp+130h+var_1A8], rax
0x18008a087  mov     [rbp+130h+var_1A0], 98h
0x18008a08e  mov     [rbp+130h+var_19C], 11h
0x18008a095  mov     [rbp+130h+var_198], 0FFh
0x18008a09c  mov     [rbp+130h+var_130], 1000000h
0x18008a0a3  xor     edx, edx; Val
0x18008a0a5  lea     r8d, [rdx+60h]; Size
0x18008a0a9  lea     rcx, [rbp+130h+var_190]; void *
0x18008a0ad  call    memset_0
0x18008a0b2  nop
0x18008a0b3  xor     r8d, r8d
0x18008a0b6  lea     rdx, [rsp+230h+var_1B8]
0x18008a0bb  lea     rcx, [rbp+130h+var_100]
0x18008a0bf  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18008a0c4  nop
0x18008a0c5  mov     [rbp+130h+var_110], 7
0x18008a0cd  mov     [rbp+130h+var_118], 0
0x18008a0d5  xor     eax, eax
0x18008a0d7  mov     word ptr [rbp+130h+Block], ax
0x18008a0db  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18008a0e2  mov     [rsp+230h+var_1E0], rax
0x18008a0e7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008a0eb  mov     [rsp+230h+var_1D8], rbx
0x18008a0f0  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18008a0f7  mov     [rsp+230h+var_1E0], rax
0x18008a0fc  xor     esi, esi
0x18008a0fe  mov     r13d, r15d
0x18008a101  shl     r13d, 8
0x18008a105  lea     r9, [rbp+130h+Block]
0x18008a109  lea     r8, aFsrmEf88c03159; "FSRM{ef88c031-5950-4164-ab92-eec5f16005"...
0x18008a110  mov     dl, r15b
0x18008a113  mov     rcx, [r14]
0x18008a116  call    ?BuildFullPath@CPropertyBagFieldsBase@@QEBAX_NPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CPropertyBagFieldsBase::BuildFullPath(bool,ushort const *,std::wstring &)
0x18008a11b  lea     rcx, [rbp+130h+Block]
0x18008a11f  call    ?SrmConvertToLongPath@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SrmConvertToLongPath(std::wstring &)
0x18008a124  lea     rax, [rbp+130h+Block]
0x18008a128  cmp     [rbp+130h+var_110], 8
0x18008a12d  cmovnb  rax, [rbp+130h+Block]
0x18008a132  mov     [rsp+230h+lpOverlapped], rax; struct _SECURITY_ATTRIBUTES *
0x18008a137  lea     r9, aLoadingPropert; "Loading property cache from file: %s"
0x18008a13e  mov     edx, 8Ch; unsigned int
0x18008a143  lea     r8d, [rdx+20h]; unsigned int
0x18008a147  lea     rcx, [rbp+130h+var_100]; this
0x18008a14b  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18008a150  lea     rcx, [rbp+130h+Block]
0x18008a154  cmp     [rbp+130h+var_110], 8
0x18008a159  cmovnb  rcx, [rbp+130h+Block]; lpFileName
0x18008a15e  mov     [rsp+230h+var_1E8], 0; unsigned int *
0x18008a167  mov     [rsp+230h+var_1F0], r15b; bool
0x18008a16c  mov     [rsp+230h+var_200], 2000000h; DWORD
0x18008a174  mov     r9d, 1; unsigned int
0x18008a17a  mov     r8d, 100081h; unsigned int
0x18008a180  lea     edx, [r13+100081h]; unsigned int
0x18008a187  call    ?SrmCreateFileWithAlternateAccess@@YAPEAXPEBGKKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX_NPEAK@Z; SrmCreateFileWithAlternateAccess(ushort const *,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,bool,ulong *)
0x18008a18c  mov     rdi, rax
0x18008a18f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18008a193  jz      short loc_18008A19E
0x18008a195  mov     rcx, rbx; hObject
0x18008a198  call    cs:__imp_CloseHandle
0x18008a19e  mov     [rsp+230h+var_1D8], 0FFFFFFFFFFFFFFFFh
0x18008a1a7  mov     rbx, rdi
0x18008a1aa  mov     [rsp+230h+var_1D8], rbx
0x18008a1af  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18008a1b3  jnz     loc_18008A27C
0x18008a1b9  call    cs:__imp_GetLastError
0x18008a1bf  cmp     eax, 2
0x18008a1c2  jz      short loc_18008A1E8
0x18008a1c4  cmp     eax, 20h ; ' '
0x18008a1c7  jnz     loc_18008A3E5
0x18008a1cd  inc     esi
0x18008a1cf  cmp     esi, 5
0x18008a1d2  jnb     loc_18008A3E9
0x18008a1d8  mov     ecx, 0FAh; dwMilliseconds
0x18008a1dd  call    cs:__imp_Sleep
0x18008a1e3  jmp     loc_18008A150
0x18008a1e8  lea     rax, [rbp+130h+Block]
0x18008a1ec  cmp     [rbp+130h+var_110], 8
0x18008a1f1  cmovnb  rax, [rbp+130h+Block]
0x18008a1f6  mov     [rsp+230h+lpOverlapped], rax
0x18008a1fb  lea     r9, aCacheDoesNotEx; "Cache does not exist for file '%s'"
0x18008a202  mov     edx, 8Ch; unsigned int
0x18008a207  lea     r8d, [rdx+3Ch]; unsigned int
0x18008a20b  lea     rcx, [rbp+130h+var_100]; this
0x18008a20f  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18008a214  nop
0x18008a215  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18008a21c  mov     [rsp+230h+var_1E0], rax
0x18008a221  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008a225  mov     [rsp+230h+var_1D8], rax
0x18008a22a  lea     rcx, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18008a231  mov     [rsp+230h+var_1E0], rcx
0x18008a236  mov     [rsp+230h+var_1D8], rax
0x18008a23b  cmp     [rbp+130h+var_110], 8
0x18008a240  jb      short loc_18008A24B
0x18008a242  mov     rcx, [rbp+130h+Block]; Block
0x18008a246  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008a24b  mov     [rbp+130h+var_110], 7
0x18008a253  mov     [rbp+130h+var_118], 0
0x18008a25b  xor     eax, eax
0x18008a25d  mov     word ptr [rbp+130h+Block], ax
0x18008a261  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18008a268  mov     [rbp+130h+var_100], rax
0x18008a26c  lea     rcx, [rbp+130h+var_100]; this
0x18008a270  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18008a275  xor     al, al
0x18008a277  jmp     loc_18008A35D
0x18008a27c  xor     esi, esi
0x18008a27e  mov     qword ptr [rsp+230h+FileSize], rsi
0x18008a283  lea     rdx, [rsp+230h+FileSize]; lpFileSize
0x18008a288  mov     rcx, rdi; hFile
0x18008a28b  call    cs:__imp_GetFileSizeEx
0x18008a291  test    eax, eax
0x18008a293  jz      loc_18008A426
0x18008a299  mov     rbx, qword ptr [rsp+230h+FileSize]
0x18008a29e  test    rbx, rbx
0x18008a2a1  jz      loc_18008A4A4
0x18008a2a7  cmp     rbx, r12
0x18008a2aa  jg      loc_18008A509
0x18008a2b0  mov     edx, ebx
0x18008a2b2  lea     r8, [rbp+130h+Block]
0x18008a2b6  mov     rcx, r14; this
0x18008a2b9  call    ?Allocate@CAdsCacheStream@@AEAAX_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CAdsCacheStream::Allocate(unsigned __int64,std::wstring const &)
0x18008a2be  mov     [rsp+230h+NumberOfBytesRead], esi
0x18008a2c2  mov     r8, [r14+30h]
0x18008a2c6  lea     rdx, [r8+4]; lpBuffer
0x18008a2ca  mov     [rsp+230h+lpOverlapped], rsi; lpOverlapped
0x18008a2cf  lea     r9, [rsp+230h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18008a2d4  mov     r8d, [r8]; nNumberOfBytesToRead
0x18008a2d7  mov     rcx, rdi; hFile
0x18008a2da  call    cs:__imp_ReadFile
0x18008a2e0  test    eax, eax
0x18008a2e2  jz      loc_18008A573
0x18008a2e8  mov     rax, [r14+30h]
0x18008a2ec  mov     ecx, [rax]
0x18008a2ee  cmp     [rsp+230h+NumberOfBytesRead], ecx
0x18008a2f2  jnz     loc_18008A380
0x18008a2f8  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18008a2ff  mov     [rsp+230h+var_1E0], rax
0x18008a304  mov     rcx, rdi; hObject
0x18008a307  call    cs:__imp_CloseHandle
0x18008a30d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008a311  mov     [rsp+230h+var_1D8], rax
0x18008a316  lea     rcx, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18008a31d  mov     [rsp+230h+var_1E0], rcx
0x18008a322  mov     [rsp+230h+var_1D8], rax
0x18008a327  cmp     [rbp+130h+var_110], 8
0x18008a32c  jb      short loc_18008A337
0x18008a32e  mov     rcx, [rbp+130h+Block]; Block
0x18008a332  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008a337  mov     [rbp+130h+var_110], 7
0x18008a33f  mov     [rbp+130h+var_118], rsi
0x18008a343  mov     word ptr [rbp+130h+Block], si
0x18008a347  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18008a34e  mov     [rbp+130h+var_100], rax
0x18008a352  lea     rcx, [rbp+130h+var_100]; this
0x18008a356  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18008a35b  mov     al, 1
0x18008a35d  mov     rcx, [rbp+130h+var_50]
0x18008a364  xor     rcx, rsp; StackCookie
0x18008a367  call    __security_check_cookie
0x18008a36c  add     rsp, 1F8h
0x18008a373  pop     r15
0x18008a375  pop     r14
0x18008a377  pop     r13
0x18008a379  pop     r12
0x18008a37b  pop     rdi
0x18008a37c  pop     rsi
0x18008a37d  pop     rbx
0x18008a37e  pop     rbp
0x18008a37f  retn
0x18008a380  lea     rcx, [rbp+130h+Block]
0x18008a384  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18008a389  mov     rbx, rax
0x18008a38c  lea     rax, [rsp+230h+var_1B8]
0x18008a391  mov     [rsp+230h+var_1C8], rax
0x18008a396  mov     dword ptr [rsp+230h+var_208], 11h
0x18008a39e  mov     dword ptr [rsp+230h+lpOverlapped], 0F9h
0x18008a3a6  lea     r9, aCadscachestrea_2; "CAdsCacheStream::LoadCacheStreamFromDis"...
0x18008a3ad  lea     r8, aSrmadscc; "SRMADSCC"
0x18008a3b4  lea     rdx, aBaseFsFsrmUtil; "base\\fs\\fsrm\\utilities\\property\\sr"...
0x18008a3bb  lea     rcx, [rsp+230h+var_1B8]
0x18008a3c0  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18008a3c5  nop
0x18008a3c6  mov     [rsp+230h+lpOverlapped], rbx
0x18008a3cb  lea     r9, aCacheFileSIsIn; "Cache file '%s' is invalid or corrupt"
0x18008a3d2  mov     r8d, 80045345h
0x18008a3d8  mov     rdx, rax
0x18008a3db  lea     rcx, [rbp+130h+var_100]
0x18008a3df  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18008a3e5  test    eax, eax
0x18008a3e7  jle     short loc_18008A3F1
0x18008a3e9  movzx   eax, ax
0x18008a3ec  or      eax, 80070000h
0x18008a3f1  mov     [rbp+130h+var_F8], eax
0x18008a3f4  lea     rcx, [rbp+130h+var_100]; this
0x18008a3f8  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18008a3fd  mov     edx, eax; int
0x18008a3ff  lea     rcx, [rbp+130h+var_100]; this
0x18008a403  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18008a408  lea     rcx, [rbp+130h+var_100]; this
0x18008a40c  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18008a411  mov     r8d, eax; char
0x18008a414  xor     r9d, r9d; unsigned __int16 *
0x18008a417  mov     edx, 0CFh; unsigned int
0x18008a41c  lea     rcx, [rbp+130h+var_100]; this
0x18008a420  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18008a426  call    cs:__imp_GetLastError
0x18008a42c  mov     edi, eax
0x18008a42e  call    cs:__imp_GetLastError
0x18008a434  mov     ebx, eax
0x18008a436  test    eax, eax
0x18008a438  jle     short loc_18008A443
0x18008a43a  movzx   ebx, ax
0x18008a43d  or      ebx, 80070000h
0x18008a443  lea     rax, [rsp+230h+var_1B8]
0x18008a448  mov     [rsp+230h+var_1C8], rax
0x18008a44d  mov     dword ptr [rsp+230h+var_208], 11h
0x18008a455  mov     dword ptr [rsp+230h+lpOverlapped], 0D9h
0x18008a45d  lea     r9, aCadscachestrea_2; "CAdsCacheStream::LoadCacheStreamFromDis"...
0x18008a464  lea     r8, aSrmadscc; "SRMADSCC"
0x18008a46b  lea     rdx, aBaseFsFsrmUtil; "base\\fs\\fsrm\\utilities\\property\\sr"...
0x18008a472  lea     rcx, [rsp+230h+var_1B8]
0x18008a477  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18008a47c  nop
0x18008a47d  mov     dword ptr [rsp+230h+var_208], edi
0x18008a481  lea     rcx, aLGetfilesizeex; "L\"GetFileSizeEx\""
0x18008a488  mov     [rsp+230h+lpOverlapped], rcx
0x18008a48d  lea     r9, aWin32CallSFail; "Win32 call %s failed [GetLastError() = "...
0x18008a494  mov     r8d, ebx
0x18008a497  mov     rdx, rax
0x18008a49a  lea     rcx, [rbp+130h+var_100]
0x18008a49e  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18008a4a4  lea     rcx, [rbp+130h+Block]
0x18008a4a8  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18008a4ad  mov     rbx, rax
0x18008a4b0  lea     rax, [rsp+230h+var_1B8]
0x18008a4b5  mov     [rsp+230h+var_1C8], rax
0x18008a4ba  mov     dword ptr [rsp+230h+var_208], 11h
0x18008a4c2  mov     dword ptr [rsp+230h+lpOverlapped], 0DEh
0x18008a4ca  lea     r9, aCadscachestrea_2; "CAdsCacheStream::LoadCacheStreamFromDis"...
0x18008a4d1  lea     r8, aSrmadscc; "SRMADSCC"
0x18008a4d8  lea     rdx, aBaseFsFsrmUtil; "base\\fs\\fsrm\\utilities\\property\\sr"...
0x18008a4df  lea     rcx, [rsp+230h+var_1B8]
0x18008a4e4  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18008a4e9  nop
0x18008a4ea  mov     [rsp+230h+lpOverlapped], rbx
0x18008a4ef  lea     r9, aCacheFileSIsEm; "Cache file '%s' is empty"
0x18008a4f6  mov     r8d, 80045345h
0x18008a4fc  mov     rdx, rax
0x18008a4ff  lea     rcx, [rbp+130h+var_100]
0x18008a503  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18008a509  lea     rcx, [rbp+130h+Block]
0x18008a50d  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18008a512  mov     rdi, rax
0x18008a515  lea     rax, [rsp+230h+var_1B8]
0x18008a51a  mov     [rsp+230h+var_1C8], rax
0x18008a51f  mov     dword ptr [rsp+230h+var_208], 11h
0x18008a527  mov     dword ptr [rsp+230h+lpOverlapped], 0E3h
0x18008a52f  lea     r9, aCadscachestrea_2; "CAdsCacheStream::LoadCacheStreamFromDis"...
0x18008a536  lea     r8, aSrmadscc; "SRMADSCC"
0x18008a53d  lea     rdx, aBaseFsFsrmUtil; "base\\fs\\fsrm\\utilities\\property\\sr"...
0x18008a544  lea     rcx, [rsp+230h+var_1B8]
0x18008a549  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18008a54e  nop
0x18008a54f  mov     [rsp+230h+var_208], rbx
0x18008a554  mov     [rsp+230h+lpOverlapped], rdi
0x18008a559  lea     r9, aCacheFileSIsTo; "Cache file '%s' is too large: size = %i"...
0x18008a560  mov     r8d, 80045345h
0x18008a566  mov     rdx, rax
0x18008a569  lea     rcx, [rbp+130h+var_100]
0x18008a56d  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18008a573  call    cs:__imp_GetLastError
0x18008a579  mov     edi, eax
0x18008a57b  call    cs:__imp_GetLastError
0x18008a581  mov     ebx, eax
0x18008a583  test    eax, eax
0x18008a585  jle     short loc_18008A590
  ... truncated ...
```
