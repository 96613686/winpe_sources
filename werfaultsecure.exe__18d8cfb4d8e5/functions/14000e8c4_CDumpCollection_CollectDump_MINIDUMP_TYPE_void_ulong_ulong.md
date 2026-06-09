# CDumpCollection::CollectDump(_MINIDUMP_TYPE,void *,ulong,ulong)

- ea: `0x14000e8c4`
- end: `0x14000f32d`
- name: `?CollectDump@CDumpCollection@@QEAAJW4_MINIDUMP_TYPE@@PEAXKK@Z`
- size: `2665`
- prototype: `__int64 __fastcall(CDumpCollection *this, enum _MINIDUMP_TYPE, void *, int, char)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140006184`

## callees

- `0x14000113c`
- `0x140001d40`
- `0x1400023d0`
- `0x1400023f4`
- `0x140002fcc`
- `0x1400073fc`
- `0x140007c34`
- `0x140007cd4`
- `0x140008620`
- `0x14000cc0c`
- `0x14000e598`
- `0x14000e8c4`
- `0x14000f6dc`
- `0x14000fb3c`
- `0x140010e14`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000ec5a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f151`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f2dd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000ec5a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f151`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f2dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x14000ec71`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x14000ec71`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14000edfa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14000ef8a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14000edfa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14000ef8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000ed40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000ed50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000ed40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000ed50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000edd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000edee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000ef7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000edd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000edee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000ef7f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14000ea01`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14000ea01`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x14000eddf`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x14000eddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ea0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ea62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ec7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ed84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ea0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ea62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ec7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ed84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f16f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f302`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f16f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f302`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14000ed7a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14000ed7a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14000f160`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14000f160`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x14000ea58`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x14000ea58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000e90e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000f0ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000e90e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000f0ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000edc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000f135`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000f2ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000edc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000f135`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000f2ec`
- `dbghelp!MiniDumpWriteDump` at `0x14000ee3e`
- `dbghelp!MiniDumpWriteDump` at `0x14000ee3e`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14000eb06`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14000eb06`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDumpCollection::CollectDump(
        CDumpCollection *this,
        enum _MINIDUMP_TYPE a2,
        void *a3,
        int a4,
        char a5)
{
  char v9; // si
  DWORD v10; // ebx
  __int64 v11; // rax
  unsigned int v12; // edi
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  int v16; // r12d
  HANDLE v17; // rax
  signed int LastError; // eax
  signed int v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  int v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  HMODULE v25; // rcx
  signed int v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  int v30; // eax
  HANDLE *v31; // rsi
  HANDLE CurrentProcess; // rbx
  void *v33; // rdi
  HANDLE v34; // rax
  signed int v35; // eax
  MINIDUMP_TYPE v36; // r13d
  HANDLE CurrentThread; // rax
  int ThreadPriority; // ebx
  HANDLE v39; // rax
  HANDLE *v40; // r8
  BOOL v41; // esi
  int FinalPathByHandle; // eax
  int v43; // r8d
  int v44; // r9d
  _QWORD *v45; // rcx
  HANDLE v46; // rax
  __int64 v47; // rbx
  HANDLE v48; // rcx
  HMODULE v49; // rcx
  char v51; // [rsp+50h] [rbp-B0h]
  unsigned __int32 v52; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v53; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE hLibModule; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hProcess; // [rsp+68h] [rbp-98h] BYREF
  __int128 v56; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hFile; // [rsp+80h] [rbp-80h]
  _QWORD v58[2]; // [rsp+88h] [rbp-78h] BYREF
  _MINIDUMP_EXCEPTION_INFORMATION ExceptionParam; // [rsp+98h] [rbp-68h] BYREF
  CDumpCollection *v60; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE *v61; // [rsp+B0h] [rbp-50h]
  void *v62; // [rsp+B8h] [rbp-48h]
  _WORD *v63; // [rsp+C0h] [rbp-40h]
  _WORD v64[8]; // [rsp+C8h] [rbp-38h] BYREF
  void *v65; // [rsp+D8h] [rbp-28h] BYREF
  int *v66; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v67; // [rsp+E8h] [rbp-18h] BYREF
  CDumpCollection *v68; // [rsp+F8h] [rbp-8h]
  char v69; // [rsp+100h] [rbp+0h]
  _MINIDUMP_CALLBACK_INFORMATION CallbackParam; // [rsp+108h] [rbp+8h] BYREF
  HANDLE hObject[2]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v72; // [rsp+130h] [rbp+30h]
  __int128 v73; // [rsp+140h] [rbp+40h]
  __int128 v74; // [rsp+150h] [rbp+50h]
  __int128 v75; // [rsp+160h] [rbp+60h]
  _DWORD v76[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v77; // [rsp+178h] [rbp+78h]
  __int64 v78; // [rsp+180h] [rbp+80h]
  int v79; // [rsp+188h] [rbp+88h]
  _BYTE v80[128]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE Source2[48]; // [rsp+210h] [rbp+110h] BYREF
  int v82; // [rsp+240h] [rbp+140h]
  _OWORD v83[2]; // [rsp+6E0h] [rbp+5E0h] BYREF
  __int128 v84; // [rsp+700h] [rbp+600h]
  __int128 v85; // [rsp+710h] [rbp+610h]
  __int128 v86; // [rsp+720h] [rbp+620h]
  unsigned int v87; // [rsp+7B0h] [rbp+6B0h]

  hFile = a3;
  hProcess = 0;
  v68 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  v9 = 1;
  v51 = 1;
  v69 = 1;
  if ( *((_QWORD *)this + 136) != -1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *((_QWORD *)this + 136) = a3;
  ExceptionParam = 0;
  memset_0(v76, 0, 0x98u);
  v67 = 0;
  v10 = *((_DWORD *)this + 279);
  hLibModule = 0;
  memset_0(hObject, 0, 0x50u);
  v62 = v64;
  v63 = v64;
  v64[0] = 0;
  if ( v10 )
  {
    v12 = -2147467259;
  }
  else
  {
    CDumpCollection::_SnapAllThreads(this);
    v11 = *((_QWORD *)this + 301);
    if ( *((_QWORD *)this + 300) == v11 || (v10 = *(_DWORD *)(v11 - 4)) == 0 )
    {
      v12 = -2147467259;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_10;
      v14 = 43;
      v15 = 2147500037LL;
LABEL_9:
      WPP_SF_d(v13[2], v14, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v15);
LABEL_10:
      v16 = 2;
      goto LABEL_114;
    }
    v12 = 0;
  }
  v17 = OpenThread(0x48u, 0, v10);
  if ( !v17 )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_10;
    v14 = 44;
    v15 = v12;
    goto LABEL_9;
  }
  *((_DWORD *)this + 304) = 1048607;
  if ( GetThreadContext(v17, (LPCONTEXT)((char *)this + 1168)) )
  {
    v16 = -1;
    v76[0] = a4;
    v76[1] = 1;
    v77 = 0;
    v78 = *((_QWORD *)this + 177);
    memset_0(Source2, 0, 0x4D0u);
    v82 = 1048607;
    if ( RtlCompareMemory((char *)this + 1168, Source2, 0x4D0u) == 1232 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
      goto LABEL_113;
    }
    v79 = 0;
    memset_0(v80, 0, 0x78u);
    *(_QWORD *)&v67 = v76;
    *((_QWORD *)&v67 + 1) = (char *)this + 1168;
    ExceptionParam.ThreadId = v10;
    ExceptionParam.ExceptionPointers = (PEXCEPTION_POINTERS)&v67;
    ExceptionParam.ClientPointers = 0;
    v60 = this;
    v61 = 0;
    v56 = 0;
    CallbackParam.CallbackRoutine = (MINIDUMP_CALLBACK_ROUTINE)CDumpCollection::StaticMinidumpCallback;
    CallbackParam.CallbackParam = &v60;
    v87 = a5 & 1;
    if ( v87 )
    {
      v22 = CDumpCollection::_InitializeDumpEncryptor(this);
      v12 = v22;
      if ( v22 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_37;
        v24 = 47;
LABEL_36:
        WPP_SF_d(v23[2], v24, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, (unsigned int)v22);
LABEL_37:
        v16 = 4;
        goto LABEL_113;
      }
      if ( !*((_QWORD *)this + 141) )
      {
        v12 = -2147024769;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
        goto LABEL_37;
      }
      if ( !*((_QWORD *)this + 140) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v25 = hLibModule;
      hLibModule = 0;
      if ( v25 )
        FreeLibrary(v25);
      if ( !GetModuleHandleExW(4u, *((LPCWSTR *)this + 140), &hLibModule) )
      {
        v26 = GetLastError();
        v12 = v26;
        if ( v26 > 0 )
          v12 = (unsigned __int16)v26 | 0x80070000;
        if ( (v12 & 0x80000000) == 0 )
          v12 = -2147467259;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_113;
        v28 = 49;
        v29 = v12;
        goto LABEL_54;
      }
      v30 = MmsCreate(hObject);
      v12 = v30;
      if ( v30 < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_113;
        v28 = 50;
        goto LABEL_59;
      }
      v61 = hObject;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
    }
    v31 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&hProcess);
    CurrentProcess = GetCurrentProcess();
    v33 = (void *)*((_QWORD *)this + 137);
    v34 = GetCurrentProcess();
    if ( !DuplicateHandle(v34, v33, CurrentProcess, v31, 0, 0, 2u) )
    {
      v35 = GetLastError();
      v12 = v35;
      if ( v35 > 0 )
        v12 = (unsigned __int16)v35 | 0x80070000;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_26;
      v21 = 52;
      goto LABEL_25;
    }
    v36 = a2 | 0x820000;
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    v51 = 0;
    v69 = 0;
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    if ( ThreadPriority != 0x7FFFFFFF )
    {
      v39 = GetCurrentThread();
      SetThreadPriority(v39, -1);
    }
    v40 = hObject;
    if ( !v87 )
      v40 = (HANDLE *)*((_QWORD *)this + 136);
    v41 = MiniDumpWriteDump(hProcess, *((_DWORD *)this + 278), v40, v36, &ExceptionParam, 0, &CallbackParam);
    if ( v41 )
      v12 = 0;
    else
      v12 = GetLastError();
    FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(hFile);
    if ( FinalPathByHandle < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids,
        (unsigned int)FinalPathByHandle);
    }
    if ( (unsigned int)dword_14001A000 > 5
      && (qword_14001A010 & 0x400000000000LL) != 0
      && (qword_14001A018 & 0x400000000000LL) == qword_14001A018 )
    {
      v65 = v62;
      v52 = v36;
      v66 = &dword_140014A6C;
      v58[0] = L"DumpCollection";
      v53 = v12;
      *(_QWORD *)&v56 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        qword_14001A018,
        (unsigned int)&dword_14001620C,
        v43,
        v44,
        (__int64)&v56,
        (__int64)&v53,
        (__int64)v58,
        (__int64)&v66,
        (__int64)&v52,
        (__int64)&v65);
    }
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v12, v36);
      v45 = WPP_GLOBAL_Control;
    }
    if ( ThreadPriority != 0x7FFFFFFF )
    {
      v46 = GetCurrentThread();
      SetThreadPriority(v46, ThreadPriority);
      v45 = WPP_GLOBAL_Control;
    }
    if ( !v41 && v45 != &WPP_GLOBAL_Control && (*((_BYTE *)v45 + 28) & 1) != 0 )
      WPP_SF_d(v45[2], 55, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v12);
    if ( v87 && *((_QWORD *)this + 141) )
    {
      v58[0] = off_1400131D0;
      v58[1] = hFile;
      v47 = v73;
      v56 = (unsigned __int64)v73;
      v30 = (*((__int64 (__fastcall **)(HANDLE *, _QWORD, _QWORD, _QWORD))hObject[0] + 5))(hObject, 0, 0, 0);
      v12 = v30;
      if ( v30 < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_113;
        v28 = 58;
LABEL_59:
        v29 = (unsigned int)v30;
LABEL_54:
        WPP_SF_d(v27[2], v28, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v29);
        goto LABEL_113;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids,
          DWORD1(v56),
          v47);
      if ( !v61 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v22 = (*((__int64 (__fastcall **)(HANDLE *, _QWORD *, __int64))this + 141))(hObject, v58, v47);
      v12 = v22;
      if ( v22 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_37;
        v24 = 60;
        goto LABEL_36;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)this);
    v51 = 1;
    if ( v41 )
    {
      v12 = 0;
      v16 = 0;
    }
    goto LABEL_113;
  }
  v19 = GetLastError();
  v12 = v19;
  if ( v19 > 0 )
    v12 = (unsigned __int16)v19 | 0x80070000;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_26;
  v21 = 45;
LABEL_25:
  WPP_SF_d(v20[2], v21, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v12);
LABEL_26:
  v16 = 2;
LABEL_113:
  v9 = v51;
LABEL_114:
  *((_QWORD *)this + 136) = -1;
  v48 = hProcess;
  hProcess = 0;
  if ( (unsigned __int64)v48 + 1 > 1 )
    CloseHandle(v48);
  if ( v9 )
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
  v49 = hLibModule;
  hLibModule = 0;
  if ( v49 )
    FreeLibrary(v49);
  if ( *((_QWORD *)&v74 + 1) )
    UnmapViewOfFile(*((LPCVOID *)&v74 + 1));
  if ( hObject[1] )
    CloseHandle(hObject[1]);
  memset_0(v83, 0, 0x50u);
  *(_OWORD *)hObject = v83[0];
  v72 = v83[1];
  v73 = v84;
  v74 = v85;
  v75 = v86;
  if ( v12 )
  {
    if ( (unsigned int)dword_14001A000 > 5
      && (qword_14001A010 & 0x400000000000LL) != 0
      && (qword_14001A018 & 0x400000000000LL) == qword_14001A018 )
    {
      v53 = v16;
      v52 = v12;
      *(_QWORD *)&v56 = 0x1000000;
      *(_QWORD *)&v86 = &v53;
      *((_QWORD *)&v86 + 1) = 4;
      *(_QWORD *)&v85 = &v52;
      *((_QWORD *)&v85 + 1) = 4;
      *(_QWORD *)&v84 = &v56;
      *((_QWORD *)&v84 + 1) = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_14001A000, word_1400161BA, 0, 0, 5, v83);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v12, v16);
  }
  if ( v62 != v64 )
    operator delete(v62, (const struct std::nothrow_t *)&std::nothrow);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( (unsigned __int64)hProcess + 1 > 1 )
    CloseHandle(hProcess);
  return v12;
}

```

## disassembly

```asm
0x14000e8c4  push    rbp
0x14000e8c6  push    rbx
0x14000e8c7  push    rsi
0x14000e8c8  push    rdi
0x14000e8c9  push    r12
0x14000e8cb  push    r13
0x14000e8cd  push    r14
0x14000e8cf  push    r15
0x14000e8d1  lea     rbp, [rsp-648h]
0x14000e8d9  sub     rsp, 748h
0x14000e8e0  mov     rax, cs:__security_cookie
0x14000e8e7  xor     rax, rsp
0x14000e8ea  mov     [rbp+680h+var_50], rax
0x14000e8f1  mov     r14d, r9d
0x14000e8f4  mov     rbx, r8
0x14000e8f7  mov     [rbp+680h+hFile], rbx
0x14000e8fb  mov     r13d, edx
0x14000e8fe  mov     r15, rcx
0x14000e901  mov     [rsp+780h+hProcess], 0
0x14000e90a  mov     [rbp+680h+var_688], rcx
0x14000e90e  call    cs:__imp_EnterCriticalSection
0x14000e914  mov     sil, 1
0x14000e917  mov     [rsp+780h+var_730], sil
0x14000e91c  mov     [rbp+680h+var_680], sil
0x14000e920  cmp     qword ptr [r15+440h], 0FFFFFFFFFFFFFFFFh
0x14000e928  jz      short loc_14000E92F
0x14000e92a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14000e92f  mov     [r15+440h], rbx
0x14000e936  xorps   xmm0, xmm0
0x14000e939  movups  xmmword ptr [rbp+680h+ExceptionParam.ThreadId], xmm0
0x14000e93d  xor     edx, edx; Val
0x14000e93f  mov     r8d, 98h; Size
0x14000e945  lea     rcx, [rbp+680h+var_610]; void *
0x14000e949  call    memset_0
0x14000e94e  xorps   xmm0, xmm0
0x14000e951  movups  [rbp+680h+var_698], xmm0
0x14000e955  mov     ebx, [r15+45Ch]
0x14000e95c  mov     [rsp+780h+hLibModule], 0
0x14000e965  xor     edx, edx; Val
0x14000e967  lea     r8d, [rdx+50h]; Size
0x14000e96b  lea     rcx, [rbp+680h+hObject]; void *
0x14000e96f  call    memset_0
0x14000e974  lea     rax, [rbp+680h+var_6B8]
0x14000e978  mov     [rbp+680h+var_6C8], rax
0x14000e97c  lea     rax, [rbp+680h+var_6B8]
0x14000e980  mov     [rbp+680h+var_6C0], rax
0x14000e984  xor     eax, eax
0x14000e986  mov     [rbp+680h+var_6B8], ax
0x14000e98a  mov     r12d, 80004005h
0x14000e990  test    ebx, ebx
0x14000e992  jnz     short loc_14000E9F6
0x14000e994  mov     rcx, r15; this
0x14000e997  call    ?_SnapAllThreads@CDumpCollection@@AEAAJXZ; CDumpCollection::_SnapAllThreads(void)
0x14000e99c  mov     rax, [r15+968h]
0x14000e9a3  cmp     [r15+960h], rax
0x14000e9aa  jz      short loc_14000E9B3
0x14000e9ac  mov     ebx, [rax-4]
0x14000e9af  test    ebx, ebx
0x14000e9b1  jnz     short loc_14000E9F2
0x14000e9b3  mov     edi, r12d
0x14000e9b6  lea     r14, WPP_GLOBAL_Control
0x14000e9bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e9c4  cmp     rcx, r14
0x14000e9c7  jz      short loc_14000E9E7
0x14000e9c9  test    byte ptr [rcx+1Ch], 1
0x14000e9cd  jz      short loc_14000E9E7
0x14000e9cf  mov     edx, 2Bh ; '+'
0x14000e9d4  mov     r9d, r12d
0x14000e9d7  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000e9de  mov     rcx, [rcx+10h]
0x14000e9e2  call    WPP_SF_d
0x14000e9e7  mov     r12d, 2
0x14000e9ed  jmp     loc_14000F104
0x14000e9f2  xor     edi, edi
0x14000e9f4  jmp     short loc_14000E9F9
0x14000e9f6  mov     edi, r12d
0x14000e9f9  mov     r8d, ebx; dwThreadId
0x14000e9fc  xor     edx, edx; bInheritHandle
0x14000e9fe  lea     ecx, [rdx+48h]; dwDesiredAccess
0x14000ea01  call    cs:__imp_OpenThread
0x14000ea07  test    rax, rax
0x14000ea0a  jnz     short loc_14000EA44
0x14000ea0c  call    cs:__imp_GetLastError
0x14000ea12  mov     edi, eax
0x14000ea14  test    eax, eax
0x14000ea16  jle     short loc_14000EA21
0x14000ea18  movzx   edi, ax
0x14000ea1b  or      edi, 80070000h
0x14000ea21  lea     r14, WPP_GLOBAL_Control
0x14000ea28  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea2f  cmp     rcx, r14
0x14000ea32  jz      short loc_14000E9E7
0x14000ea34  test    byte ptr [rcx+1Ch], 1
0x14000ea38  jz      short loc_14000E9E7
0x14000ea3a  mov     edx, 2Ch ; ','
0x14000ea3f  mov     r9d, edi
0x14000ea42  jmp     short loc_14000E9D7
0x14000ea44  lea     rsi, [r15+490h]
0x14000ea4b  mov     dword ptr [rsi+30h], 10001Fh
0x14000ea52  mov     rdx, rsi; lpContext
0x14000ea55  mov     rcx, rax; hThread
0x14000ea58  call    cs:__imp_GetThreadContext
0x14000ea5e  test    eax, eax
0x14000ea60  jnz     short loc_14000EAB3
0x14000ea62  call    cs:__imp_GetLastError
0x14000ea68  mov     edi, eax
0x14000ea6a  test    eax, eax
0x14000ea6c  jle     short loc_14000EA77
0x14000ea6e  movzx   edi, ax
0x14000ea71  or      edi, 80070000h
0x14000ea77  lea     r14, WPP_GLOBAL_Control
0x14000ea7e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea85  cmp     rcx, r14
0x14000ea88  jz      short loc_14000EAA8
0x14000ea8a  test    byte ptr [rcx+1Ch], 1
0x14000ea8e  jz      short loc_14000EAA8
0x14000ea90  mov     edx, 2Dh ; '-'
0x14000ea95  mov     r9d, edi
0x14000ea98  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000ea9f  mov     rcx, [rcx+10h]
0x14000eaa3  call    WPP_SF_d
0x14000eaa8  mov     r12d, 2
0x14000eaae  jmp     loc_14000F0FF
0x14000eab3  or      r12d, 0FFFFFFFFh
0x14000eab7  mov     [rbp+680h+var_610], r14d
0x14000eabb  mov     [rbp+680h+var_60C], 1
0x14000eac2  mov     [rbp+680h+var_608], 0
0x14000eaca  mov     rax, [r15+588h]
0x14000ead1  mov     [rbp+680h+var_600], rax
0x14000ead8  mov     r14d, 4D0h
0x14000eade  mov     r8d, r14d; Size
0x14000eae1  xor     edx, edx; Val
0x14000eae3  lea     rcx, [rbp+680h+Source2]; void *
0x14000eaea  call    memset_0
0x14000eaef  mov     [rbp+680h+var_540], 10001Fh
0x14000eaf9  mov     r8d, r14d; Length
0x14000eafc  lea     rdx, [rbp+680h+Source2]; Source2
0x14000eb03  mov     rcx, rsi; Source1
0x14000eb06  call    cs:__imp_RtlCompareMemory
0x14000eb0c  cmp     rax, r14
0x14000eb0f  jnz     short loc_14000EB51
0x14000eb11  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14000eb16  lea     r14, WPP_GLOBAL_Control
0x14000eb1d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eb24  cmp     rcx, r14
0x14000eb27  jz      loc_14000F0FF
0x14000eb2d  test    byte ptr [rcx+1Ch], 1
0x14000eb31  jz      loc_14000F0FF
0x14000eb37  lea     edx, [r12+2Fh]
0x14000eb3c  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000eb43  mov     rcx, [rcx+10h]
0x14000eb47  call    WPP_SF_
0x14000eb4c  jmp     loc_14000F0FF
0x14000eb51  mov     [rbp+680h+var_5F8], 0
0x14000eb5b  xor     edx, edx; Val
0x14000eb5d  lea     r8d, [rdx+78h]; Size
0x14000eb61  lea     rcx, [rbp+680h+var_5F0]; void *
0x14000eb68  call    memset_0
0x14000eb6d  lea     rax, [rbp+680h+var_610]
0x14000eb71  mov     qword ptr [rbp+680h+var_698], rax
0x14000eb75  mov     qword ptr [rbp+680h+var_698+8], rsi
0x14000eb79  mov     [rbp+680h+ExceptionParam.ThreadId], ebx
0x14000eb7c  lea     rax, [rbp+680h+var_698]
0x14000eb80  mov     [rbp+680h+ExceptionParam.ExceptionPointers], rax
0x14000eb84  xor     esi, esi
0x14000eb86  mov     [rbp+680h+ExceptionParam.ClientPointers], esi
0x14000eb89  xorps   xmm0, xmm0
0x14000eb8c  movups  [rsp+780h+var_710], xmm0
0x14000eb91  mov     [rbp+680h+var_6D8], r15
0x14000eb95  mov     [rbp+680h+var_6D0], rsi
0x14000eb99  movups  [rsp+780h+var_710], xmm0
0x14000eb9e  lea     rax, ?StaticMinidumpCallback@CDumpCollection@@CAHPEAXQEAU_MINIDUMP_CALLBACK_INPUT@@PEAU_MINIDUMP_CALLBACK_OUTPUT@@@Z; CDumpCollection::StaticMinidumpCallback(void *,_MINIDUMP_CALLBACK_INPUT * const,_MINIDUMP_CALLBACK_OUTPUT *)
0x14000eba5  mov     [rbp+680h+CallbackParam.CallbackRoutine], rax
0x14000eba9  lea     rax, [rbp+680h+var_6D8]
0x14000ebad  mov     [rbp+680h+CallbackParam.CallbackParam], rax
0x14000ebb1  lea     r14, WPP_GLOBAL_Control
0x14000ebb8  and     [rbp+680h+arg_20], 1
0x14000ebbf  jz      loc_14000ED33
0x14000ebc5  mov     rcx, r15; this
0x14000ebc8  call    ?_InitializeDumpEncryptor@CDumpCollection@@AEAAJXZ; CDumpCollection::_InitializeDumpEncryptor(void)
0x14000ebcd  mov     edi, eax
0x14000ebcf  test    eax, eax
0x14000ebd1  jns     short loc_14000EC06
0x14000ebd3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ebda  cmp     rcx, r14
0x14000ebdd  jz      short loc_14000EBFB
0x14000ebdf  test    byte ptr [rcx+1Ch], 1
0x14000ebe3  jz      short loc_14000EBFB
0x14000ebe5  lea     edx, [rsi+2Fh]
0x14000ebe8  mov     r9d, eax
0x14000ebeb  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000ebf2  mov     rcx, [rcx+10h]
0x14000ebf6  call    WPP_SF_d
0x14000ebfb  mov     r12d, 4
0x14000ec01  jmp     loc_14000F0FF
0x14000ec06  cmp     [r15+468h], rsi
0x14000ec0d  jnz     short loc_14000EC3D
0x14000ec0f  mov     edi, 8007007Fh
0x14000ec14  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec1b  cmp     rcx, r14
0x14000ec1e  jz      short loc_14000EBFB
0x14000ec20  test    byte ptr [rcx+1Ch], 1
0x14000ec24  jz      short loc_14000EBFB
0x14000ec26  mov     edx, 30h ; '0'
0x14000ec2b  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000ec32  mov     rcx, [rcx+10h]
0x14000ec36  call    WPP_SF_
0x14000ec3b  jmp     short loc_14000EBFB
0x14000ec3d  cmp     [r15+460h], rsi
0x14000ec44  jnz     short loc_14000EC4B
0x14000ec46  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14000ec4b  mov     rcx, [rsp+780h+hLibModule]; hLibModule
0x14000ec50  mov     [rsp+780h+hLibModule], rsi
0x14000ec55  test    rcx, rcx
0x14000ec58  jz      short loc_14000EC60
0x14000ec5a  call    cs:__imp_FreeLibrary
0x14000ec60  lea     r8, [rsp+780h+hLibModule]; phModule
0x14000ec65  mov     rdx, [r15+460h]; lpModuleName
0x14000ec6c  mov     ecx, 4; dwFlags
0x14000ec71  call    cs:__imp_GetModuleHandleExW
0x14000ec77  test    eax, eax
0x14000ec79  jnz     short loc_14000ECD1
0x14000ec7b  call    cs:__imp_GetLastError
0x14000ec81  mov     edi, eax
0x14000ec83  test    eax, eax
0x14000ec85  jle     short loc_14000EC90
0x14000ec87  movzx   edi, ax
0x14000ec8a  or      edi, 80070000h
0x14000ec90  test    edi, edi
0x14000ec92  mov     eax, 80004005h
0x14000ec97  cmovns  edi, eax
0x14000ec9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eca1  cmp     rcx, r14
0x14000eca4  jz      loc_14000F0FF
0x14000ecaa  test    byte ptr [rcx+1Ch], 1
0x14000ecae  jz      loc_14000F0FF
0x14000ecb4  mov     edx, 31h ; '1'
0x14000ecb9  mov     r9d, edi
0x14000ecbc  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000ecc3  mov     rcx, [rcx+10h]
0x14000ecc7  call    WPP_SF_d
0x14000eccc  jmp     loc_14000F0FF
0x14000ecd1  lea     rcx, [rbp+680h+hObject]
0x14000ecd5  call    MmsCreate
0x14000ecda  mov     edi, eax
0x14000ecdc  test    eax, eax
0x14000ecde  jns     short loc_14000ED04
0x14000ece0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ece7  cmp     rcx, r14
0x14000ecea  jz      loc_14000F0FF
0x14000ecf0  test    byte ptr [rcx+1Ch], 1
0x14000ecf4  jz      loc_14000F0FF
0x14000ecfa  mov     edx, 32h ; '2'
0x14000ecff  mov     r9d, eax
0x14000ed02  jmp     short loc_14000ECBC
0x14000ed04  lea     rax, [rbp+680h+hObject]
0x14000ed08  mov     [rbp+680h+var_6D0], rax
0x14000ed0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed13  cmp     rcx, r14
0x14000ed16  jz      short loc_14000ED33
0x14000ed18  test    byte ptr [rcx+1Ch], 8
0x14000ed1c  jz      short loc_14000ED33
0x14000ed1e  mov     edx, 33h ; '3'
0x14000ed23  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000ed2a  mov     rcx, [rcx+10h]
0x14000ed2e  call    WPP_SF_
0x14000ed33  lea     rcx, [rsp+780h+hProcess]
0x14000ed38  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x14000ed3d  mov     rsi, rax
0x14000ed40  call    cs:__imp_GetCurrentProcess
0x14000ed46  mov     rbx, rax
0x14000ed49  mov     rdi, [r15+448h]
0x14000ed50  call    cs:__imp_GetCurrentProcess
0x14000ed56  mov     [rsp+780h+dwOptions], 2; dwOptions
0x14000ed5e  mov     [rsp+780h+bInheritHandle], 0; bInheritHandle
0x14000ed66  mov     [rsp+780h+dwDesiredAccess], 0; dwDesiredAccess
0x14000ed6e  mov     r9, rsi; lpTargetHandle
0x14000ed71  mov     r8, rbx; hTargetProcessHandle
0x14000ed74  mov     rdx, rdi; hSourceHandle
0x14000ed77  mov     rcx, rax; hSourceProcessHandle
0x14000ed7a  call    cs:__imp_DuplicateHandle
0x14000ed80  test    eax, eax
0x14000ed82  jnz     short loc_14000EDBD
0x14000ed84  call    cs:__imp_GetLastError
0x14000ed8a  mov     edi, eax
0x14000ed8c  test    eax, eax
0x14000ed8e  jle     short loc_14000ED99
0x14000ed90  movzx   edi, ax
0x14000ed93  or      edi, 80070000h
0x14000ed99  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eda0  cmp     rcx, r14
0x14000eda3  jz      loc_14000EAA8
0x14000eda9  test    byte ptr [rcx+1Ch], 1
0x14000edad  jz      loc_14000EAA8
0x14000edb3  mov     edx, 34h ; '4'
0x14000edb8  jmp     loc_14000EA95
0x14000edbd  or      r13d, 820000h
0x14000edc4  mov     rcx, r15; lpCriticalSection
0x14000edc7  call    cs:__imp_LeaveCriticalSection
0x14000edcd  xor     al, al
  ... truncated ...
```
