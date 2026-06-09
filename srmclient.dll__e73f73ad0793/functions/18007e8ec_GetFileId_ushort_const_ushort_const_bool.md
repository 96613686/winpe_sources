# GetFileId(ushort const *,ushort const *,bool)

- ea: `0x18007e8ec`
- end: `0x18007ecc0`
- name: `?GetFileId@@YA?AT_ULARGE_INTEGER@@PEBG0_N@Z`
- size: `980`
- prototype: `union _ULARGE_INTEGER(const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task`

## callers

- `0x1800a42d0`

## callees

- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000ad14`
- `0x18000af40`
- `0x180017fd8`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073f54`
- `0x18007e8ec`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007eb21`
- `ole32!CoTaskMemFree` at `0x18007ebb1`
- `ole32!CoTaskMemFree` at `0x18007eb21`
- `ole32!CoTaskMemFree` at `0x18007ebb1`
- `KERNEL32!CreateFileW` at `0x18007eaab`
- `KERNEL32!CreateFileW` at `0x18007eaab`
- `KERNEL32!CloseHandle` at `0x18007ebd5`
- `KERNEL32!CloseHandle` at `0x18007ebd5`
- `KERNEL32!GetLastError` at `0x18007eac7`
- `KERNEL32!GetLastError` at `0x18007eac7`
- `KERNEL32!GetFileInformationByHandle` at `0x18007eb88`
- `KERNEL32!GetFileInformationByHandle` at `0x18007eb88`

## string_xrefs

- `0x18007eb02`: `%s cannot be accessed <%#x>; returning fileId<%I64u>.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
union _ULARGE_INTEGER __fastcall GetFileId(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // esi
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rsi
  HANDLE FileW; // rsi
  signed int LastError; // eax
  signed int v14; // ecx
  __int64 v16; // rdx
  __int64 v17; // rcx
  int LastFailureAsHRESULT; // eax
  char v19; // al
  int Hr; // eax
  char v21; // al
  int v22; // eax
  char v23; // al
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  void **v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  _QWORD *v28; // [rsp+58h] [rbp-A8h]
  _QWORD v29[3]; // [rsp+60h] [rbp-A0h] BYREF
  int v30; // [rsp+78h] [rbp-88h]
  int v31; // [rsp+7Ch] [rbp-84h]
  int v32; // [rsp+80h] [rbp-80h]
  _BYTE v33[96]; // [rsp+88h] [rbp-78h] BYREF
  int v34; // [rsp+E8h] [rbp-18h]
  void **v35; // [rsp+F0h] [rbp-10h] BYREF
  signed int v36; // [rsp+F8h] [rbp-8h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+1A0h] [rbp+A0h] BYREF

  v28 = v29;
  v29[0] = L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp";
  v29[1] = L"GetFileId";
  v29[2] = L"SRMVOLMC";
  v30 = 1245;
  v31 = 17;
  v32 = 255;
  v34 = 0x1000000;
  memset_0(v33, 0, sizeof(v33));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v35, (const struct CSrmDebugInfo *)v29, 0);
  v27 = -1;
  v26 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v4 = 0;
  lpFileName = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( a1 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a1[v5] );
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v7 = v6 + v5;
    CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&lpFileName, (unsigned int)(v6 + v5));
    v4 = (unsigned __int16 *)lpFileName;
    v8 = StringCchPrintfW((unsigned __int16 *)lpFileName, (unsigned int)(v7 + 1), L"%s%s", a1, a2);
    v36 = v8;
    if ( v8 < 0 )
    {
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v35);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v35, Hr);
      v21 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v35);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v35, 0x4EEu, v21, 0);
    }
    v36 = v8;
    a2 = v4;
    v9 = (unsigned int)(v7 - 1);
    if ( v4[v9] == 92 )
      v4[v9] = 0;
  }
  else
  {
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    v11 = (unsigned int)(v10 - 1);
    if ( a2[v11] == 92 )
    {
      CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&lpFileName, (unsigned int)v10);
      CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&lpFileName, a2);
      v4 = (unsigned __int16 *)lpFileName;
      lpFileName[v11] = 0;
      a2 = v4;
    }
  }
  FileW = CreateFileW(a2, 0, 7u, 0, 3u, 0x2000000u, 0);
  v27 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    v36 = v14;
    if ( ((v14 + 2147024894) & 0xFFFFFFFC) == 0 && v14 != -2147024892 )
    {
      LODWORD(dwFlagsAndAttributes) = v14;
      CSrmFunctionTracer::Trace(
        (CSrmFunctionTracer *)&v35,
        0x3Cu,
        0x51Du,
        L"%s cannot be accessed <%#x>; returning fileId<%I64u>.",
        a2,
        dwFlagsAndAttributes,
        0);
      CoTaskMemFree(v4);
      lpFileName = 0;
      v26 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
      v27 = -1;
      v35 = &CSrmFunctionTracer::`vftable';
      CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v35);
      return 0;
    }
    v36 = v14;
    if ( v14 < 0 )
    {
      v22 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v35);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v35, v22);
      v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v35);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v35, 0x521u, v23, 0);
    }
    v36 = v14;
  }
  else
  {
    v14 = v36;
  }
  v36 = v14;
  if ( !GetFileInformationByHandle(FileW, &FileInformation) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v17, v16);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v35, LastFailureAsHRESULT);
    v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v35);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v35, 0x524u, v19, 0);
  }
  v36 = 0;
  v28 = (_QWORD *)__PAIR64__(FileInformation.nFileIndexHigh, FileInformation.nFileIndexLow);
  CoTaskMemFree(v4);
  lpFileName = 0;
  v26 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  v26 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
  v27 = -1;
  v35 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v35);
  return (union _ULARGE_INTEGER)v28;
}

```

## disassembly

```asm
0x18007e8ec  mov     [rsp-8+arg_10], rbx
0x18007e8f1  push    rbp
0x18007e8f2  push    rsi
0x18007e8f3  push    rdi
0x18007e8f4  push    r12
0x18007e8f6  push    r13
0x18007e8f8  push    r14
0x18007e8fa  push    r15
0x18007e8fc  lea     rbp, [rsp-0E0h]
0x18007e904  sub     rsp, 1E0h
0x18007e90b  mov     rax, cs:__security_cookie
0x18007e912  xor     rax, rsp
0x18007e915  mov     [rbp+110h+var_38], rax
0x18007e91c  mov     rdi, rdx
0x18007e91f  mov     r14, rcx
0x18007e922  lea     rax, [rsp+210h+var_1B0]
0x18007e927  mov     [rsp+210h+var_1B8], rax
0x18007e92c  lea     rax, aBaseFsFsrmUtil_2; "base\\fs\\fsrm\\utilities\\volume\\srmv"...
0x18007e933  mov     [rsp+210h+var_1B0], rax
0x18007e938  lea     rax, aGetfileid; "GetFileId"
0x18007e93f  mov     [rsp+210h+var_1A8], rax
0x18007e944  lea     rax, aSrmvolmc; "SRMVOLMC"
0x18007e94b  mov     [rsp+210h+var_1A0], rax
0x18007e950  mov     [rsp+210h+var_198], 4DDh
0x18007e958  mov     [rsp+210h+var_194], 11h
0x18007e960  mov     [rbp+110h+var_190], 0FFh
0x18007e967  xor     r15d, r15d
0x18007e96a  mov     [rbp+110h+var_128], 1000000h
0x18007e971  xor     edx, edx; Val
0x18007e973  lea     r8d, [r15+60h]; Size
0x18007e977  lea     rcx, [rbp+110h+var_188]; void *
0x18007e97b  call    memset_0
0x18007e980  nop
0x18007e981  xor     r8d, r8d
0x18007e984  lea     rdx, [rsp+210h+var_1B0]
0x18007e989  lea     rcx, [rbp+110h+var_120]
0x18007e98d  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007e992  nop
0x18007e993  lea     r13, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18007e99a  mov     [rsp+210h+var_1C8], r13
0x18007e99f  or      r12, 0FFFFFFFFFFFFFFFFh
0x18007e9a3  mov     [rsp+210h+var_1C0], r12
0x18007e9a8  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18007e9af  mov     [rsp+210h+var_1C8], rax
0x18007e9b4  mov     ebx, r15d
0x18007e9b7  mov     [rsp+210h+lpFileName], rbx
0x18007e9bc  xorps   xmm0, xmm0
0x18007e9bf  xor     eax, eax
0x18007e9c1  movups  xmmword ptr [rbp+110h+FileInformation.dwFileAttributes], xmm0
0x18007e9c8  movups  xmmword ptr [rbp+110h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18007e9cf  movups  xmmword ptr [rbp+110h+FileInformation.nFileSizeHigh], xmm0
0x18007e9d6  mov     [rbp+110h+FileInformation.nFileIndexLow], eax
0x18007e9dc  test    r14, r14
0x18007e9df  jz      short loc_18007EA4B
0x18007e9e1  mov     rax, r12
0x18007e9e4  inc     rax
0x18007e9e7  cmp     [r14+rax*2], r15w
0x18007e9ec  jnz     short loc_18007E9E4
0x18007e9ee  mov     rcx, r12
0x18007e9f1  inc     rcx
0x18007e9f4  cmp     [rdi+rcx*2], r15w
0x18007e9f9  jnz     short loc_18007E9F1
0x18007e9fb  lea     esi, [rcx+rax]
0x18007e9fe  mov     edx, esi; unsigned __int64
0x18007ea00  lea     rcx, [rsp+210h+lpFileName]; this
0x18007ea05  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18007ea0a  lea     edx, [rsi+1]; unsigned __int64
0x18007ea0d  mov     qword ptr [rsp+210h+dwCreationDisposition], rdi
0x18007ea12  mov     r9, r14
0x18007ea15  lea     r8, aSS_0; "%s%s"
0x18007ea1c  mov     rbx, [rsp+210h+lpFileName]
0x18007ea21  mov     rcx, rbx; unsigned __int16 *
0x18007ea24  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007ea29  mov     [rbp+110h+var_118], eax
0x18007ea2c  test    eax, eax
0x18007ea2e  js      loc_18007EC5C
0x18007ea34  mov     [rbp+110h+var_118], eax
0x18007ea37  mov     rdi, rbx
0x18007ea3a  lea     eax, [rsi-1]
0x18007ea3d  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x18007ea42  jnz     short loc_18007EA8A
0x18007ea44  mov     [rbx+rax*2], r15w
0x18007ea49  jmp     short loc_18007EA8A
0x18007ea4b  mov     rcx, r12
0x18007ea4e  inc     rcx
0x18007ea51  cmp     [rdi+rcx*2], r15w
0x18007ea56  jnz     short loc_18007EA4E
0x18007ea58  lea     eax, [rcx-1]
0x18007ea5b  mov     esi, eax
0x18007ea5d  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x18007ea62  jnz     short loc_18007EA8A
0x18007ea64  mov     edx, ecx; unsigned __int64
0x18007ea66  lea     rcx, [rsp+210h+lpFileName]; this
0x18007ea6b  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18007ea70  mov     rdx, rdi; unsigned __int16 *
0x18007ea73  lea     rcx, [rsp+210h+lpFileName]; this
0x18007ea78  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18007ea7d  mov     rbx, [rsp+210h+lpFileName]
0x18007ea82  mov     [rbx+rsi*2], r15w
0x18007ea87  mov     rdi, rbx
0x18007ea8a  mov     [rsp+210h+hTemplateFile], r15; hTemplateFile
0x18007ea8f  mov     dword ptr [rsp+210h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18007ea97  mov     [rsp+210h+dwCreationDisposition], 3; dwCreationDisposition
0x18007ea9f  xor     r9d, r9d; lpSecurityAttributes
0x18007eaa2  xor     edx, edx; dwDesiredAccess
0x18007eaa4  lea     r8d, [r9+7]; dwShareMode
0x18007eaa8  mov     rcx, rdi; lpFileName
0x18007eaab  call    cs:__imp_CreateFileW
0x18007eab1  mov     rsi, rax
0x18007eab4  mov     [rsp+210h+var_1C0], r12
0x18007eab9  mov     [rsp+210h+var_1C0], rax
0x18007eabe  cmp     rax, r12
0x18007eac1  jnz     loc_18007EB78
0x18007eac7  call    cs:__imp_GetLastError
0x18007eacd  mov     ecx, eax
0x18007eacf  test    eax, eax
0x18007ead1  jle     short loc_18007EADC
0x18007ead3  movzx   ecx, ax
0x18007ead6  or      ecx, 80070000h
0x18007eadc  mov     [rbp+110h+var_118], ecx
0x18007eadf  lea     eax, [rcx+7FF8FFFEh]
0x18007eae5  test    eax, 0FFFFFFFCh
0x18007eaea  jnz     short loc_18007EB68
0x18007eaec  cmp     ecx, 80070004h
0x18007eaf2  jz      short loc_18007EB68
0x18007eaf4  mov     [rsp+210h+hTemplateFile], r15
0x18007eaf9  mov     dword ptr [rsp+210h+dwFlagsAndAttributes], ecx
0x18007eafd  mov     qword ptr [rsp+210h+dwCreationDisposition], rdi
0x18007eb02  lea     r9, aSCannotBeAcces; "%s cannot be accessed <%#x>; returning "...
0x18007eb09  mov     edx, 3Ch ; '<'; unsigned int
0x18007eb0e  mov     r8d, 51Dh; unsigned int
0x18007eb14  lea     rcx, [rbp+110h+var_120]; this
0x18007eb18  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18007eb1d  nop
0x18007eb1e  mov     rcx, rbx; pv
0x18007eb21  call    cs:__imp_CoTaskMemFree
0x18007eb27  mov     [rsp+210h+lpFileName], r15
0x18007eb2c  mov     [rsp+210h+lpFileName], r15
0x18007eb31  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18007eb38  mov     [rsp+210h+var_1C8], rax
0x18007eb3d  mov     [rsp+210h+var_1C0], r12
0x18007eb42  mov     [rsp+210h+var_1C8], r13
0x18007eb47  mov     [rsp+210h+var_1C0], r12
0x18007eb4c  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007eb53  mov     [rbp+110h+var_120], rax
0x18007eb57  lea     rcx, [rbp+110h+var_120]; this
0x18007eb5b  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007eb60  mov     rax, r15
0x18007eb63  jmp     loc_18007EC03
0x18007eb68  mov     [rbp+110h+var_118], ecx
0x18007eb6b  test    ecx, ecx
0x18007eb6d  js      loc_18007EC8E
0x18007eb73  mov     [rbp+110h+var_118], ecx
0x18007eb76  jmp     short loc_18007EB7B
0x18007eb78  mov     ecx, [rbp+110h+var_118]
0x18007eb7b  mov     [rbp+110h+var_118], ecx
0x18007eb7e  lea     rdx, [rbp+110h+FileInformation]; lpFileInformation
0x18007eb85  mov     rcx, rsi; hFile
0x18007eb88  call    cs:__imp_GetFileInformationByHandle
0x18007eb8e  test    eax, eax
0x18007eb90  jz      loc_18007EC2D
0x18007eb96  mov     [rbp+110h+var_118], r15d
0x18007eb9a  mov     eax, [rbp+110h+FileInformation.nFileIndexHigh]
0x18007eba0  mov     dword ptr [rsp+210h+var_1B8+4], eax
0x18007eba4  mov     eax, [rbp+110h+FileInformation.nFileIndexLow]
0x18007ebaa  mov     dword ptr [rsp+210h+var_1B8], eax
0x18007ebae  mov     rcx, rbx; pv
0x18007ebb1  call    cs:__imp_CoTaskMemFree
0x18007ebb7  mov     [rsp+210h+lpFileName], r15
0x18007ebbc  mov     [rsp+210h+lpFileName], r15
0x18007ebc1  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18007ebc8  mov     [rsp+210h+var_1C8], rax
0x18007ebcd  cmp     rsi, r12
0x18007ebd0  jz      short loc_18007EBDB
0x18007ebd2  mov     rcx, rsi; hObject
0x18007ebd5  call    cs:__imp_CloseHandle
0x18007ebdb  mov     [rsp+210h+var_1C0], r12
0x18007ebe0  mov     [rsp+210h+var_1C8], r13
0x18007ebe5  mov     [rsp+210h+var_1C0], r12
0x18007ebea  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007ebf1  mov     [rbp+110h+var_120], rax
0x18007ebf5  lea     rcx, [rbp+110h+var_120]; this
0x18007ebf9  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007ebfe  mov     rax, [rsp+210h+var_1B8]
0x18007ec03  mov     rcx, [rbp+110h+var_38]
0x18007ec0a  xor     rcx, rsp; StackCookie
0x18007ec0d  call    __security_check_cookie
0x18007ec12  mov     rbx, [rsp+210h+arg_10]
0x18007ec1a  add     rsp, 1E0h
0x18007ec21  pop     r15
0x18007ec23  pop     r14
0x18007ec25  pop     r13
0x18007ec27  pop     r12
0x18007ec29  pop     rdi
0x18007ec2a  pop     rsi
0x18007ec2b  pop     rbp
0x18007ec2c  retn
0x18007ec2d  call    GetLastFailureAsHRESULT
0x18007ec32  nop
0x18007ec33  mov     edx, eax; int
0x18007ec35  lea     rcx, [rbp+110h+var_120]; this
0x18007ec39  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18007ec3e  lea     rcx, [rbp+110h+var_120]; this
0x18007ec42  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007ec47  mov     r8d, eax; char
0x18007ec4a  xor     r9d, r9d; unsigned __int16 *
0x18007ec4d  mov     edx, 524h; unsigned int
0x18007ec52  lea     rcx, [rbp+110h+var_120]; this
0x18007ec56  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18007ec5c  lea     rcx, [rbp+110h+var_120]; this
0x18007ec60  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007ec65  mov     edx, eax; int
0x18007ec67  lea     rcx, [rbp+110h+var_120]; this
0x18007ec6b  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18007ec70  lea     rcx, [rbp+110h+var_120]; this
0x18007ec74  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007ec79  mov     r8d, eax; char
0x18007ec7c  xor     r9d, r9d; unsigned __int16 *
0x18007ec7f  mov     edx, 4EEh; unsigned int
0x18007ec84  lea     rcx, [rbp+110h+var_120]; this
0x18007ec88  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18007ec8e  lea     rcx, [rbp+110h+var_120]; this
0x18007ec92  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007ec97  mov     edx, eax; int
0x18007ec99  lea     rcx, [rbp+110h+var_120]; this
0x18007ec9d  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18007eca2  lea     rcx, [rbp+110h+var_120]; this
0x18007eca6  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007ecab  mov     r8d, eax; char
0x18007ecae  xor     r9d, r9d; unsigned __int16 *
0x18007ecb1  mov     edx, 521h; unsigned int
0x18007ecb6  lea     rcx, [rbp+110h+var_120]; this
0x18007ecba  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
