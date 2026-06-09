# CFsrmFileStream::CommitChanges(unsigned __int64 *,__int64 *)

- ea: `0x18005b2a8`
- end: `0x18005ba4f`
- name: `?CommitChanges@CFsrmFileStream@@QEAA_NPEA_KPEA_J@Z`
- size: `1959`
- prototype: `bool __fastcall(CFsrmFileStream *__hidden this, unsigned __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18008e6ac`

## callees

- `0x180001350`
- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000ac38`
- `0x18000ee10`
- `0x18005a1c0`
- `0x18005af68`
- `0x18005b128`
- `0x18005b2a8`
- `0x18005d014`
- `0x18006febc`
- `0x1800700b8`
- `0x180072a80`
- `0x180073a80`
- `0x180073f54`
- `0x18007c348`
- `0x18007de74`
- `0x18007dfb8`
- `0x18007e234`
- `0x18007e410`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18005b4ce`
- `KERNEL32!CreateFileW` at `0x18005b4ce`
- `KERNEL32!CloseHandle` at `0x18005b74b`
- `KERNEL32!CloseHandle` at `0x18005b814`
- `KERNEL32!CloseHandle` at `0x18005b74b`
- `KERNEL32!CloseHandle` at `0x18005b814`
- `KERNEL32!GetLastError` at `0x18005b6dc`
- `KERNEL32!GetLastError` at `0x18005b6dc`
- `KERNEL32!GetFileTime` at `0x18005b512`
- `KERNEL32!GetFileTime` at `0x18005b512`

## string_xrefs

- `0x18005b2f9`: `base\fs\fsrm\service\stream\streamlib.cpp`
- `0x18005b43b`: `Failed to update basic info for file '%s', error 0x%x.`
- `0x18005b307`: `CFsrmFileStream::CommitChanges`
- `0x18005b792`: `Failed to update basic info for temp file before deleting it, error 0x%x.`
- `0x18005b935`: `File '%s' changed since we opened it for write`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
char __fastcall CFsrmFileStream::CommitChanges(CFsrmFileStream *this, unsigned __int64 *a2, __int64 *a3)
{
  CFsrmFileStream *v4; // rdi
  enum _FILE_INFORMATION_CLASS v5; // edx
  unsigned int v6; // r9d
  unsigned __int64 *v7; // rcx
  int v9; // ecx
  _QWORD *v10; // rax
  DWORD v11; // edx
  const unsigned __int16 *v12; // rsi
  const WCHAR *v13; // rcx
  HANDLE FileW; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  const unsigned __int16 *v17; // r8
  const unsigned __int16 *NextName; // rdx
  bool v19; // r8
  _WORD *v20; // rcx
  signed int LastError; // eax
  __int64 v22; // r12
  int v23; // eax
  int LastFailureAsHRESULT; // eax
  char v25; // al
  __int64 v26; // rax
  void *v27; // rax
  const unsigned __int16 *v28; // rdx
  bool v29; // r8
  char v30; // al
  int v31; // eax
  char v32; // al
  int Hr; // eax
  char v34; // al
  int v35; // eax
  char v36; // al
  bool v37; // r8
  unsigned int *dwCreationDisposition; // [rsp+20h] [rbp-488h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-488h]
  char v40; // [rsp+40h] [rbp-468h]
  void **v42; // [rsp+50h] [rbp-458h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-450h]
  const unsigned __int16 *v44; // [rsp+60h] [rbp-448h]
  HANDLE *v45; // [rsp+68h] [rbp-440h]
  HANDLE hFile; // [rsp+70h] [rbp-438h]
  int v47; // [rsp+78h] [rbp-430h]
  struct _FILETIME LastWriteTime; // [rsp+80h] [rbp-428h] BYREF
  unsigned __int64 *v49; // [rsp+88h] [rbp-420h]
  _QWORD *v50; // [rsp+90h] [rbp-418h]
  __int64 *v51; // [rsp+98h] [rbp-410h]
  unsigned __int64 v52; // [rsp+A0h] [rbp-408h] BYREF
  _QWORD *v53; // [rsp+A8h] [rbp-400h]
  int v54; // [rsp+B0h] [rbp-3F8h] BYREF
  int v55; // [rsp+B4h] [rbp-3F4h] BYREF
  const unsigned __int16 *v56; // [rsp+C0h] [rbp-3E8h]
  _com_error *v57; // [rsp+C8h] [rbp-3E0h] BYREF
  const exception *v58; // [rsp+D0h] [rbp-3D8h] BYREF
  _com_error *v59; // [rsp+D8h] [rbp-3D0h] BYREF
  const exception *v60; // [rsp+E0h] [rbp-3C8h] BYREF
  _QWORD v61[3]; // [rsp+F8h] [rbp-3B0h] BYREF
  int v62; // [rsp+110h] [rbp-398h]
  int v63; // [rsp+114h] [rbp-394h]
  int v64; // [rsp+118h] [rbp-390h]
  _DWORD v65[28]; // [rsp+120h] [rbp-388h] BYREF
  void **v66; // [rsp+190h] [rbp-318h] BYREF
  int v67; // [rsp+198h] [rbp-310h]
  unsigned int v68; // [rsp+1BCh] [rbp-2ECh]
  _BYTE v69[16]; // [rsp+240h] [rbp-268h] BYREF
  __int64 v70; // [rsp+250h] [rbp-258h]
  void *Block; // [rsp+258h] [rbp-250h]
  _BYTE v72[528]; // [rsp+260h] [rbp-248h] BYREF

  v4 = this;
  v49 = a2;
  v51 = a3;
  v53 = v61;
  v61[0] = L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp";
  v61[1] = L"CFsrmFileStream::CommitChanges";
  v61[2] = L"STREAMLC";
  v62 = 455;
  v63 = 17;
  v64 = 255;
  v65[24] = 0x1000000;
  memset_0(v65, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v66, (const struct CSrmDebugInfo *)v61, 0);
  if ( a3 )
    *a3 = 0;
  v7 = v49;
  if ( v49 )
    *v49 = 0;
  if ( *(_DWORD *)v4 == 2 )
  {
    v52 = 0;
    v40 = *((_BYTE *)v4 + 92) & 1;
    if ( v7 )
      SrmQueryInformationByHandle(*((HANDLE *)v4 + 30), v5, &v52, v6, dwCreationDisposition);
    v45 = (HANDLE *)((char *)v4 + 240);
    v9 = SrmSetBasicInfoByHandle(
           *((HANDLE *)v4 + 30),
           *(struct _FILETIME *)((char *)v4 + 272),
           *(struct _FILETIME *)((char *)v4 + 280),
           *(struct _FILETIME *)((char *)v4 + 288),
           *((_DWORD *)v4 + 23));
    v67 = v9;
    if ( v9 < 0 )
    {
      v10 = (_QWORD *)((char *)v4 + 48);
      if ( *((_QWORD *)v4 + 9) >= 8u )
        v10 = (_QWORD *)*v10;
      CSrmFunctionTracer::Trace(
        (CSrmFunctionTracer *)&v66,
        0x3Cu,
        0x1E8u,
        L"Failed to update basic info for file '%s', error 0x%x.",
        v10,
        v9);
    }
    hFile = (HANDLE)*((_QWORD *)v4 + 30);
    hObject = (HANDLE)-1LL;
    v42 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
    v11 = 1114240;
    v47 = 1114240;
    if ( v40 )
      v11 = 1114496;
    v47 = v11;
    v12 = (const unsigned __int16 *)((char *)v4 + 8);
    if ( *((_QWORD *)v4 + 4) < 8u )
      v13 = (const WCHAR *)((char *)v4 + 8);
    else
      v13 = *(const WCHAR **)v12;
    FileW = CreateFileW(v13, v11, 0, 0, 3u, 0x2000000u, 0);
    hObject = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( LastError != 2 && LastError != 3 && LastError != 32 )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v67 = LastError;
        Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v66);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v66, Hr);
        v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v66);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v66, 0x214u, v34, 0);
      }
      v67 = -2147200134;
      v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v66);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v66, v35);
      v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v66);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v66, 0x210u, v36, 0);
    }
    LastWriteTime = 0;
    if ( !GetFileTime(FileW, 0, 0, &LastWriteTime) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v16, v15);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v66, LastFailureAsHRESULT);
      v25 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v66);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v66, 0x21Au, v25, 0);
    }
    v44 = (const unsigned __int16 *)((char *)v4 + 8);
    v50 = (_QWORD *)((char *)v4 + 32);
    v67 = 0;
    if ( LastWriteTime.dwLowDateTime != *((_DWORD *)v4 + 72) || LastWriteTime.dwHighDateTime != *((_DWORD *)v4 + 73) )
    {
      if ( *((_QWORD *)v4 + 4) >= 8u )
        v12 = *(const unsigned __int16 **)v12;
      CSrmFunctionTracer::Trace(
        (CSrmFunctionTracer *)&v66,
        0x8Cu,
        0x21Fu,
        L"File '%s' changed since we opened it for write",
        v12);
      v67 = -2147200134;
      v31 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v66);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v66, v31);
      v32 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v66);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v66, 0x220u, v32, 0);
    }
    v53 = (_QWORD *)((char *)v4 + 8);
    v17 = (const unsigned __int16 *)((char *)v4 + 8);
    if ( *((_QWORD *)v4 + 4) >= 8u )
      v17 = *(const unsigned __int16 **)v17;
    CSrmTempFileName::CSrmTempFileName((CSrmTempFileName *)v69, v15, v17, L"~$fsrmb", L"$");
    v56 = 0;
    while ( 1 )
    {
      NextName = CSrmTempFileName::GetNextName((CSrmTempFileName *)v69);
      v56 = NextName;
      if ( !NextName )
      {
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v66, -2147200132);
        v30 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v66);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v66, 0x22Cu, v30, 0);
      }
      v67 = 0;
      try
      {
        SrmRenameFileByHandle(hObject, NextName, v19);
      }
      catch ( long v54 )
      {
        CSrmFunctionTracer::HandleHresultException(
          (CSrmFunctionTracer *)&v66,
          v54,
          L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
          L"STREAMLC",
          L"CFsrmFileStream::CommitChanges",
          0x232u,
          v68);
        v4 = this;
        v12 = v44;
      }
      catch ( _com_error *v57 )
      {
        CSrmFunctionTracer::HandleComException(
          (CSrmFunctionTracer *)&v66,
          v57,
          L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
          L"STREAMLC",
          L"CFsrmFileStream::CommitChanges",
          0x232u,
          v68);
      }
      catch ( std::bad_alloc )
      {
        CSrmFunctionTracer::HandleStdBadAllocException(
          (CSrmFunctionTracer *)&v66,
          L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
          L"STREAMLC",
          L"CFsrmFileStream::CommitChanges",
          0x232u,
          v68);
        v4 = this;
        v12 = v44;
      }
      catch ( const exception *v58 )
      {
        CSrmFunctionTracer::HandleStdGenericException(
          (CSrmFunctionTracer *)&v66,
          v58,
          L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
          L"STREAMLC",
          L"CFsrmFileStream::CommitChanges",
          0x232u,
          v68);
      }
      if ( v67 >= 0 )
        break;
      if ( (v67 != -2147024816) == v67 && v67 != -2147024713 )
        CSrmFunctionTracer::ReThrow((CSrmFunctionTracer *)&v66);
      v67 = 0;
    }
    try
    {
      if ( *v50 >= 8u )
        v12 = *(const unsigned __int16 **)v12;
      SrmRenameFileByHandle(*v45, v12, v37);
    }
    catch ( long v55 )
    {
      CSrmFunctionTracer::HandleHresultException(
        (CSrmFunctionTracer *)&v66,
        v55,
        L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
        L"STREAMLC",
        L"CFsrmFileStream::CommitChanges",
        0x24Au,
        v68);
      v4 = this;
    }
    catch ( _com_error *v59 )
    {
      CSrmFunctionTracer::HandleComException(
        (CSrmFunctionTracer *)&v66,
        v59,
        L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
        L"STREAMLC",
        L"CFsrmFileStream::CommitChanges",
        0x24Au,
        v68);
    }
    catch ( std::bad_alloc )
    {
      CSrmFunctionTracer::HandleStdBadAllocException(
        (CSrmFunctionTracer *)&v66,
        L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
        L"STREAMLC",
        L"CFsrmFileStream::CommitChanges",
        0x24Au,
        v68);
      v4 = this;
    }
    catch ( const exception *v60 )
    {
      CSrmFunctionTracer::HandleStdGenericException(
        (CSrmFunctionTracer *)&v66,
        v60,
        L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
        L"STREAMLC",
        L"CFsrmFileStream::CommitChanges",
        0x24Au,
        v68);
    }
    if ( v67 < 0 )
    {
      v26 = std::wstring::c_str(v53);
      v27 = (void *)CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::operator void *(
                      &v42,
                      v26);
      SrmRenameFileByHandle(v27, v28, v29);
      CSrmFunctionTracer::ReThrow((CSrmFunctionTracer *)&v66);
    }
    if ( *((_QWORD *)v4 + 9) < 8u )
      v20 = (_WORD *)((char *)v4 + 48);
    else
      v20 = (_WORD *)*((_QWORD *)v4 + 6);
    *((_QWORD *)v4 + 8) = 0;
    *v20 = 0;
    hFile = hObject;
    if ( Block )
    {
      operator delete(Block);
      Block = 0;
    }
    v70 = 260;
    memset_0(v72, 0, 0x208u);
    v22 = 0;
    if ( *v45 != hFile )
    {
      if ( v51 )
        v22 = SrmWriteCloseUsnRecord(*v45);
      if ( *v45 != (HANDLE)-1LL )
        CloseHandle(*v45);
      *v45 = (HANDLE)-1LL;
      CFsrmDuplicatedAutoHandle::CloseTargetHandle((CFsrmFileStream *)((char *)v4 + 248));
    }
    if ( v40 )
    {
      v23 = SrmSetBasicInfoByHandle(hFile, 0, 0, 0, 0x80u);
      if ( v23 < 0 )
      {
        dwCreationDispositiona[0] = v23;
        CSrmFunctionTracer::Trace(
          (CSrmFunctionTracer *)&v66,
          0x3Cu,
          0x27Cu,
          L"Failed to update basic info for temp file before deleting it, error 0x%x.",
          *(_QWORD *)dwCreationDispositiona);
      }
    }
    SrmDeleteFileByHandle(hFile);
    CFsrmFileStream::Close(v4);
    if ( v67 < 0 )
      CSrmFunctionTracer::ReThrow((CSrmFunctionTracer *)&v66);
    if ( v51 )
      *v51 = v22;
    if ( v49 )
      *v49 = v52;
    v42 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    v42 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
    hObject = (HANDLE)-1LL;
    v66 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v66);
    return 1;
  }
  else
  {
    v66 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v66);
    return 0;
  }
}

```

## disassembly

```asm
0x18005b2a8  mov     r11, rsp
0x18005b2ab  mov     [r11+20h], rbx
0x18005b2af  push    rsi
0x18005b2b0  push    rdi
0x18005b2b1  push    r12
0x18005b2b3  push    r14
0x18005b2b5  push    r15
0x18005b2b7  sub     rsp, 480h
0x18005b2be  mov     rax, cs:__security_cookie
0x18005b2c5  xor     rax, rsp
0x18005b2c8  mov     [rsp+4A8h+var_38], rax
0x18005b2d0  mov     rsi, r8
0x18005b2d3  mov     rdi, rcx
0x18005b2d6  mov     [rsp+4A8h+var_460], rcx
0x18005b2db  mov     [rsp+4A8h+var_420], rdx
0x18005b2e3  mov     [rsp+4A8h+var_410], r8
0x18005b2eb  lea     rax, [r11-3B0h]
0x18005b2f2  mov     [r11-400h], rax
0x18005b2f9  lea     rax, aBaseFsFsrmServ_12; "base\\fs\\fsrm\\service\\stream\\stream"...
0x18005b300  mov     [r11-3B0h], rax
0x18005b307  lea     rax, aCfsrmfilestrea_9; "CFsrmFileStream::CommitChanges"
0x18005b30e  mov     [r11-3A8h], rax
0x18005b315  lea     rax, aStreamlc; "STREAMLC"
0x18005b31c  mov     [r11-3A0h], rax
0x18005b323  mov     [rsp+4A8h+var_398], 1C7h
0x18005b32e  mov     [rsp+4A8h+var_394], 11h
0x18005b339  mov     [rsp+4A8h+var_390], 0FFh
0x18005b344  xor     ebx, ebx
0x18005b346  mov     [rsp+4A8h+var_328], 1000000h
0x18005b351  xor     edx, edx; Val
0x18005b353  lea     r8d, [rbx+60h]; Size
0x18005b357  lea     rcx, [r11-388h]; void *
0x18005b35e  call    memset_0
0x18005b363  nop
0x18005b364  xor     r8d, r8d
0x18005b367  lea     rdx, [rsp+4A8h+var_3B0]
0x18005b36f  lea     rcx, [rsp+4A8h+var_318]
0x18005b377  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18005b37c  nop
0x18005b37d  test    rsi, rsi
0x18005b380  jz      short loc_18005B385
0x18005b382  mov     [rsi], rbx
0x18005b385  mov     rcx, [rsp+4A8h+var_420]
0x18005b38d  test    rcx, rcx
0x18005b390  jz      short loc_18005B395
0x18005b392  mov     [rcx], rbx
0x18005b395  cmp     dword ptr [rdi], 2
0x18005b398  jz      short loc_18005B3BD
0x18005b39a  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005b3a1  mov     [rsp+4A8h+var_318], rax
0x18005b3a9  lea     rcx, [rsp+4A8h+var_318]; this
0x18005b3b1  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18005b3b6  xor     al, al
0x18005b3b8  jmp     loc_18005B84F
0x18005b3bd  mov     [rsp+4A8h+var_408], rbx
0x18005b3c5  mov     al, [rdi+5Ch]
0x18005b3c8  and     al, 1
0x18005b3ca  mov     [rsp+4A8h+var_468], al
0x18005b3ce  test    rcx, rcx
0x18005b3d1  jz      short loc_18005B3E7
0x18005b3d3  lea     r8, [rsp+4A8h+var_408]; void *
0x18005b3db  mov     rcx, [rdi+0F0h]; FileHandle
0x18005b3e2  call    ?SrmQueryInformationByHandle@@YAXPEAXW4_FILE_INFORMATION_CLASS@@0KPEAK@Z; SrmQueryInformationByHandle(void *,_FILE_INFORMATION_CLASS,void *,ulong,ulong *)
0x18005b3e7  lea     rsi, [rdi+0F0h]
0x18005b3ee  mov     [rsp+4A8h+var_440], rsi
0x18005b3f3  mov     eax, [rdi+5Ch]
0x18005b3f6  mov     [rsp+4A8h+dwCreationDisposition], eax; unsigned int
0x18005b3fa  mov     r9, [rdi+120h]; struct _FILETIME
0x18005b401  mov     r8, [rdi+118h]; struct _FILETIME
0x18005b408  mov     rdx, [rdi+110h]; struct _FILETIME
0x18005b40f  mov     rcx, [rsi]; hFile
0x18005b412  call    ?SrmSetBasicInfoByHandle@@YAJPEAXU_FILETIME@@11K@Z; SrmSetBasicInfoByHandle(void *,_FILETIME,_FILETIME,_FILETIME,ulong)
0x18005b417  mov     ecx, eax
0x18005b419  mov     [rsp+4A8h+var_310], eax
0x18005b420  test    eax, eax
0x18005b422  jns     short loc_18005B45A
0x18005b424  lea     rax, [rdi+30h]
0x18005b428  cmp     qword ptr [rax+18h], 8
0x18005b42d  jb      short loc_18005B432
0x18005b42f  mov     rax, [rax]
0x18005b432  mov     [rsp+4A8h+dwFlagsAndAttributes], ecx
0x18005b436  mov     qword ptr [rsp+4A8h+dwCreationDisposition], rax
0x18005b43b  lea     r9, aFailedToUpdate_0; "Failed to update basic info for file '%"...
0x18005b442  mov     edx, 3Ch ; '<'; unsigned int
0x18005b447  mov     r8d, 1E8h; unsigned int
0x18005b44d  lea     rcx, [rsp+4A8h+var_318]; this
0x18005b455  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18005b45a  mov     rax, [rsi]
0x18005b45d  mov     [rsp+4A8h+hFile], rax
0x18005b462  lea     r15, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18005b469  mov     [rsp+4A8h+var_458], r15
0x18005b46e  mov     [rsp+4A8h+hObject], 0FFFFFFFFFFFFFFFFh
0x18005b477  lea     r14, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18005b47e  mov     [rsp+4A8h+var_458], r14
0x18005b483  mov     edx, 110080h
0x18005b488  mov     [rsp+4A8h+var_430], edx
0x18005b48c  mov     eax, 110180h
0x18005b491  cmp     [rsp+4A8h+var_468], bl
0x18005b495  cmovnz  edx, eax; dwDesiredAccess
0x18005b498  mov     [rsp+4A8h+var_430], edx
0x18005b49c  lea     rsi, [rdi+8]
0x18005b4a0  lea     r12, [rsi+18h]
0x18005b4a4  cmp     qword ptr [r12], 8
0x18005b4a9  jb      short loc_18005B4B0
0x18005b4ab  mov     rcx, [rsi]
0x18005b4ae  jmp     short loc_18005B4B3
0x18005b4b0  mov     rcx, rsi; lpFileName
0x18005b4b3  mov     [rsp+4A8h+hTemplateFile], rbx; hTemplateFile
0x18005b4b8  mov     [rsp+4A8h+dwFlagsAndAttributes], 2000000h; unsigned __int16 *
0x18005b4c0  mov     [rsp+4A8h+dwCreationDisposition], 3; dwCreationDisposition
0x18005b4c8  xor     r9d, r9d; lpSecurityAttributes
0x18005b4cb  xor     r8d, r8d; dwShareMode
0x18005b4ce  call    cs:__imp_CreateFileW
0x18005b4d4  mov     rcx, rax; hFile
0x18005b4d7  mov     [rsp+4A8h+hObject], 0FFFFFFFFFFFFFFFFh
0x18005b4e0  mov     [rsp+4A8h+hObject], rax
0x18005b4e5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005b4e9  jz      loc_18005B6DC
0x18005b4ef  mov     qword ptr [rsp+4A8h+LastWriteTime.dwLowDateTime], rbx
0x18005b4f7  mov     eax, [rsp+4A8h+var_310]
0x18005b4fe  mov     [rsp+4A8h+var_310], eax
0x18005b505  lea     r9, [rsp+4A8h+LastWriteTime]; lpLastWriteTime
0x18005b50d  xor     r8d, r8d; lpLastAccessTime
0x18005b510  xor     edx, edx; lpCreationTime
0x18005b512  call    cs:__imp_GetFileTime
0x18005b518  test    eax, eax
0x18005b51a  jz      loc_18005B877
0x18005b520  mov     [rsp+4A8h+var_448], rsi
0x18005b525  mov     [rsp+4A8h+var_418], r12
0x18005b52d  mov     [rsp+4A8h+var_310], ebx
0x18005b534  mov     eax, [rdi+120h]
0x18005b53a  cmp     [rsp+4A8h+LastWriteTime.dwLowDateTime], eax
0x18005b541  jnz     loc_18005B926
0x18005b547  mov     eax, [rdi+124h]
0x18005b54d  cmp     [rsp+4A8h+LastWriteTime.dwHighDateTime], eax
0x18005b554  jnz     loc_18005B926
0x18005b55a  mov     [rsp+4A8h+var_400], rsi
0x18005b562  lea     r8, [rdi+8]
0x18005b566  cmp     qword ptr [r8+18h], 8
0x18005b56b  jb      short loc_18005B570
0x18005b56d  mov     r8, [r8]; unsigned __int16 *
0x18005b570  lea     rax, asc_1800EACE8; "$"
0x18005b577  mov     qword ptr [rsp+4A8h+dwCreationDisposition], rax; unsigned __int16 *
0x18005b57c  lea     r9, aFsrmb; "~$fsrmb"
0x18005b583  lea     rcx, [rsp+4A8h+var_268]; this
0x18005b58b  call    ??0CSrmTempFileName@@QEAA@IPEBG000@Z; CSrmTempFileName::CSrmTempFileName(uint,ushort const *,ushort const *,ushort const *,ushort const *)
0x18005b590  nop
0x18005b591  mov     [rsp+4A8h+var_3E8], rbx
0x18005b599  lea     rcx, [rsp+4A8h+var_268]; this
0x18005b5a1  call    ?GetNextName@CSrmTempFileName@@QEAAPEBGXZ; CSrmTempFileName::GetNextName(void)
0x18005b5a6  mov     rdx, rax; unsigned __int16 *
0x18005b5a9  mov     [rsp+4A8h+var_3E8], rax
0x18005b5b1  mov     eax, [rsp+4A8h+var_310]
0x18005b5b8  mov     [rsp+4A8h+var_310], eax
0x18005b5bf  test    rdx, rdx
0x18005b5c2  jz      loc_18005B8EE
0x18005b5c8  mov     [rsp+4A8h+var_310], ebx
0x18005b5cf  mov     rcx, [rsp+4A8h+hObject]; hFile
0x18005b5d4  call    ?SrmRenameFileByHandle@@YAXPEAXPEBG_N@Z; SrmRenameFileByHandle(void *,ushort const *,bool)
0x18005b5d9  nop
0x18005b5da  jmp     short loc_18005B5F6
0x18005b5dc  mov     rdi, [rsp+4A8h+var_460]
0x18005b5e1  mov     rsi, [rsp+4A8h+var_448]
0x18005b5e6  lea     r14, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18005b5ed  lea     r15, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18005b5f4  xor     ebx, ebx
0x18005b5f6  mov     ecx, [rsp+4A8h+var_310]
0x18005b5fd  test    ecx, ecx
0x18005b5ff  js      loc_18005B6B5
0x18005b605  mov     rax, [rsp+4A8h+var_418]
0x18005b60d  cmp     qword ptr [rax], 8
0x18005b611  jb      short loc_18005B616
0x18005b613  mov     rsi, [rsi]
0x18005b616  mov     rdx, rsi; unsigned __int16 *
0x18005b619  mov     rcx, [rsp+4A8h+var_440]
0x18005b61e  mov     rcx, [rcx]; hFile
0x18005b621  call    ?SrmRenameFileByHandle@@YAXPEAXPEBG_N@Z; SrmRenameFileByHandle(void *,ushort const *,bool)
0x18005b626  nop
0x18005b627  jmp     short loc_18005B642
0x18005b629  jmp     short loc_18005B5DC
0x18005b62b  jmp     short loc_18005B5DC
0x18005b62d  mov     rdi, [rsp+4A8h+var_460]
0x18005b632  lea     r14, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18005b639  lea     r15, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18005b640  xor     ebx, ebx
0x18005b642  cmp     [rsp+4A8h+var_310], ebx
0x18005b649  jl      loc_18005B8B2
0x18005b64f  jmp     short loc_18005B655
0x18005b651  jmp     short loc_18005B62D
0x18005b653  jmp     short loc_18005B62D
0x18005b655  cmp     qword ptr [rdi+48h], 8
0x18005b65a  jb      short loc_18005B662
0x18005b65c  mov     rcx, [rdi+30h]
0x18005b660  jmp     short loc_18005B666
0x18005b662  lea     rcx, [rdi+30h]
0x18005b666  mov     [rdi+40h], rbx
0x18005b66a  mov     [rcx], bx
0x18005b66d  mov     rax, [rsp+4A8h+hObject]
0x18005b672  mov     [rsp+4A8h+hFile], rax
0x18005b677  mov     rcx, [rsp+4A8h+Block]; Block
0x18005b67f  test    rcx, rcx
0x18005b682  jz      short loc_18005B691
0x18005b684  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005b689  mov     [rsp+4A8h+Block], rbx
0x18005b691  mov     [rsp+4A8h+var_258], 104h
0x18005b69d  xor     edx, edx; Val
0x18005b69f  mov     r8d, 208h; Size
0x18005b6a5  lea     rcx, [rsp+4A8h+var_248]; void *
0x18005b6ad  call    memset_0
0x18005b6b2  nop
0x18005b6b3  jmp     short loc_18005B719
0x18005b6b5  mov     eax, ebx
0x18005b6b7  cmp     ecx, 80070050h
0x18005b6bd  setnz   al
0x18005b6c0  cmp     eax, ecx
0x18005b6c2  jnz     short loc_18005B6D0
0x18005b6c4  cmp     ecx, 800700B7h
0x18005b6ca  jnz     loc_18005B8E1
0x18005b6d0  mov     [rsp+4A8h+var_310], ebx
0x18005b6d7  jmp     loc_18005B599
0x18005b6dc  call    cs:__imp_GetLastError
0x18005b6e2  mov     ecx, eax
0x18005b6e4  sub     ecx, 2
0x18005b6e7  jz      loc_18005B9F4
0x18005b6ed  sub     ecx, 1
0x18005b6f0  jz      loc_18005B9F4
0x18005b6f6  cmp     ecx, 1Dh
0x18005b6f9  jz      loc_18005B9F4
0x18005b6ff  jmp     loc_18005B9A0
0x18005b704  mov     rdi, [rsp+4A8h+var_460]
0x18005b709  lea     r14, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18005b710  lea     r15, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18005b717  xor     ebx, ebx
0x18005b719  mov     r12, rbx
0x18005b71c  mov     rax, [rsp+4A8h+var_440]
0x18005b721  mov     rcx, [rax]; hFile
0x18005b724  cmp     rcx, [rsp+4A8h+hFile]
0x18005b729  jz      short loc_18005B769
0x18005b72b  cmp     [rsp+4A8h+var_410], rbx
0x18005b733  jz      short loc_18005B73D
0x18005b735  call    ?SrmWriteCloseUsnRecord@@YA_JPEAX@Z; SrmWriteCloseUsnRecord(void *)
0x18005b73a  mov     r12, rax
0x18005b73d  mov     rax, [rsp+4A8h+var_440]
0x18005b742  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x18005b746  jz      short loc_18005B751
0x18005b748  mov     rcx, [rax]; hObject
0x18005b74b  call    cs:__imp_CloseHandle
0x18005b751  mov     rax, [rsp+4A8h+var_440]
0x18005b756  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x18005b75d  lea     rcx, [rdi+0F8h]; this
0x18005b764  call    ?CloseTargetHandle@CFsrmDuplicatedAutoHandle@@QEAAXXZ; CFsrmDuplicatedAutoHandle::CloseTargetHandle(void)
0x18005b769  cmp     [rsp+4A8h+var_468], bl
0x18005b76d  jz      short loc_18005B7B1
0x18005b76f  mov     [rsp+4A8h+dwCreationDisposition], 80h; unsigned int
0x18005b777  mov     r9, rbx; struct _FILETIME
0x18005b77a  mov     r8, rbx; struct _FILETIME
0x18005b77d  mov     rdx, rbx; struct _FILETIME
0x18005b780  mov     rcx, [rsp+4A8h+hFile]; hFile
0x18005b785  call    ?SrmSetBasicInfoByHandle@@YAJPEAXU_FILETIME@@11K@Z; SrmSetBasicInfoByHandle(void *,_FILETIME,_FILETIME,_FILETIME,ulong)
0x18005b78a  test    eax, eax
0x18005b78c  jns     short loc_18005B7B1
0x18005b78e  mov     [rsp+4A8h+dwCreationDisposition], eax
0x18005b792  lea     r9, aFailedToUpdate; "Failed to update basic info for temp fi"...
0x18005b799  mov     edx, 3Ch ; '<'; unsigned int
0x18005b79e  mov     r8d, 27Ch; unsigned int
0x18005b7a4  lea     rcx, [rsp+4A8h+var_318]; this
0x18005b7ac  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18005b7b1  mov     rcx, [rsp+4A8h+hFile]; hFile
0x18005b7b6  call    ?SrmDeleteFileByHandle@@YAXPEAX_N@Z; SrmDeleteFileByHandle(void *,bool)
0x18005b7bb  mov     rcx, rdi; this
0x18005b7be  call    ?Close@CFsrmFileStream@@QEAAXXZ; CFsrmFileStream::Close(void)
0x18005b7c3  cmp     [rsp+4A8h+var_310], ebx
0x18005b7ca  jl      loc_18005BA41
0x18005b7d0  jmp     short loc_18005B7DC
0x18005b7d2  jmp     loc_18005B704
0x18005b7d7  jmp     loc_18005B704
0x18005b7dc  mov     rsi, [rsp+4A8h+var_410]
0x18005b7e4  test    rsi, rsi
0x18005b7e7  jz      short loc_18005B7EC
0x18005b7e9  mov     [rsi], r12
0x18005b7ec  mov     rcx, [rsp+4A8h+var_420]
0x18005b7f4  test    rcx, rcx
0x18005b7f7  jz      short loc_18005B804
0x18005b7f9  mov     rax, [rsp+4A8h+var_408]
0x18005b801  mov     [rcx], rax
0x18005b804  mov     [rsp+4A8h+var_458], r14
0x18005b809  mov     rcx, [rsp+4A8h+hObject]; hObject
0x18005b80e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005b812  jz      short loc_18005B81A
0x18005b814  call    cs:__imp_CloseHandle
0x18005b81a  mov     [rsp+4A8h+hObject], 0FFFFFFFFFFFFFFFFh
0x18005b823  mov     [rsp+4A8h+var_458], r15
0x18005b828  mov     [rsp+4A8h+hObject], 0FFFFFFFFFFFFFFFFh
0x18005b831  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005b838  mov     [rsp+4A8h+var_318], rax
0x18005b840  lea     rcx, [rsp+4A8h+var_318]; this
0x18005b848  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18005b84d  mov     al, 1
0x18005b84f  mov     rcx, [rsp+4A8h+var_38]
0x18005b857  xor     rcx, rsp; StackCookie
  ... truncated ...
```
