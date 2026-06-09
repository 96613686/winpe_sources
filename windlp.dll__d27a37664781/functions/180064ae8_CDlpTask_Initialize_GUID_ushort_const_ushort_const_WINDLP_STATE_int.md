# CDlpTask::Initialize(_GUID,ushort const *,ushort const *,WINDLP_STATE,int)

- ea: `0x180064ae8`
- end: `0x180065f5e`
- name: `?Initialize@CDlpTask@@QEAAJU_GUID@@PEBG1W4WINDLP_STATE@@H@Z`
- size: `5238`
- prototype: `int __high(struct _GUID, const unsigned __int16 *, const unsigned __int16 *, enum WINDLP_STATE, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18004e1c0`
- `0x180051b90`

## callees

- `0x180002898`
- `0x18000aba4`
- `0x18000ea20`
- `0x180012f5c`
- `0x18001cdb0`
- `0x18001ce28`
- `0x18001fd60`
- `0x18002aee4`
- `0x18006309c`
- `0x180064ae8`
- `0x180075124`
- `0x18007ec76`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180065c8a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180065d86`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180065c8a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180065d86`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180065061`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180065197`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180065061`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180065197`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18006510f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18006510f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800659b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800659fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065edc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065f06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800659b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800659fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065edc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065f06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800659c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065a09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065eea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065f14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800659c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065a09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065eea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065f14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064ce7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065b08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065cb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065dad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064ce7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065b08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065cb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065dad`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064c00`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064cb9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064d72`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065a27`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065add`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065b95`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064c00`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064cb9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064d72`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065a27`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065add`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065b95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064b42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800658bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800658d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064b42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800658bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800658d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064b67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065901`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065927`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064b67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065901`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065927`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064c15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064cce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064d87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065a3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065af2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065baa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065d9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064c15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064cce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064d87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065a3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065af2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065baa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065d9b`

## string_xrefs

- `0x180065e9b`: `CDlpTask::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDlpTask::Initialize(__int64 a1, __int128 *a2, void *a3, WCHAR *a4, unsigned int a5, int a6)
{
  int *v10; // r13
  int v11; // edi
  signed int v12; // edi
  __int64 v13; // rax
  __int64 v14; // rcx
  HANDLE EventW; // rbx
  void *v16; // rcx
  signed int v17; // eax
  HANDLE v18; // rbx
  void *v19; // rcx
  signed int LastError; // eax
  HANDLE v21; // rbx
  void *v22; // rcx
  signed int v23; // eax
  __int64 v24; // rcx
  int StringCch; // eax
  DWORD FileAttributesW; // ebx
  int v27; // ebx
  signed int v28; // eax
  DWORD v29; // ebx
  int v30; // ebx
  int Internal; // eax
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rdi
  __int64 v36; // rbx
  HANDLE ProcessHeap; // rax
  DWORD *v38; // r12
  DWORD *v39; // rdi
  __int64 v40; // rbx
  HANDLE v41; // rax
  HANDLE v42; // rbx
  void *v43; // rcx
  signed int v44; // eax
  HANDLE v45; // rbx
  void *v46; // rcx
  signed int v47; // eax
  HANDLE v48; // rbx
  void *v49; // rcx
  signed int v50; // eax
  HANDLE Thread; // rbx
  void *v52; // rcx
  signed int v53; // eax
  HANDLE v54; // rbx
  void *v55; // rcx
  signed int v56; // eax
  int v57; // eax
  int v58; // eax
  void *v59; // rbx
  HANDLE v60; // rax
  void *v61; // rbx
  HANDLE v62; // rax
  __int64 dwCreationFlags; // [rsp+20h] [rbp-E0h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-D8h]
  int v66; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v67[2]; // [rsp+38h] [rbp-C8h]
  __int64 v68; // [rsp+40h] [rbp-C0h]
  __int64 v69; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR FilePart; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v71; // [rsp+60h] [rbp-A0h] BYREF
  int v72; // [rsp+70h] [rbp-90h]
  int v73; // [rsp+90h] [rbp-70h]
  WCHAR Buffer[1040]; // [rsp+A0h] [rbp-60h] BYREF

  v69 = 0;
  v68 = 0;
  *(_QWORD *)v67 = 0;
  FilePart = 0;
  v10 = (int *)(a1 + 296);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 312));
  v72 = 1;
  v11 = *v10;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 4));
  v72 = 0;
  if ( v11 != -21037378 )
  {
    v12 = -2147023649;
    if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
      goto LABEL_236;
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
    v14 = 0;
    if ( !v13 )
      goto LABEL_235;
    LODWORD(lpThreadId) = -2147023649;
    LODWORD(dwCreationFlags) = 723;
    goto LABEL_233;
  }
  *(_DWORD *)(a1 + 1432) = 30000;
  *(_DWORD *)(a1 + 1436) = 1000;
  *(_DWORD *)(a1 + 1440) = 1000;
  EventW = CreateEventW(0, 1, 0, 0);
  v16 = *(void **)(a1 + 232);
  if ( v16 )
    CloseHandle(v16);
  if ( EventW )
  {
    *(_QWORD *)(a1 + 232) = EventW;
    v18 = CreateEventW(0, 0, 0, 0);
    v19 = *(void **)(a1 + 240);
    if ( v19 )
      CloseHandle(v19);
    if ( !v18 )
    {
      *(_QWORD *)(a1 + 240) = 0;
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v12 = -2147467259;
      }
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( v12 >= 0 || !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 739;
      goto LABEL_233;
    }
    *(_QWORD *)(a1 + 240) = v18;
    v21 = CreateEventW(0, 0, 0, 0);
    v22 = *(void **)(a1 + 248);
    if ( v22 )
      CloseHandle(v22);
    if ( !v21 )
    {
      *(_QWORD *)(a1 + 248) = 0;
      v23 = GetLastError();
      v12 = v23;
      if ( v23 )
      {
        if ( v23 > 0 )
          v12 = (unsigned __int16)v23 | 0x80070000;
      }
      else
      {
        v12 = -2147467259;
      }
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( v12 >= 0 || !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 742;
      goto LABEL_233;
    }
    *(_QWORD *)(a1 + 248) = v21;
    if ( memcmp_0(&WINDLP_TRANSPORT_NONE, a2, 0x10u) )
    {
      v24 = *(_QWORD *)(a1 + 1304);
      v71 = *a2;
      v12 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *))(*(_QWORD *)v24 + 80LL))(v24, &v71, &v69);
      if ( v12 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
          goto LABEL_236;
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
        v14 = 0;
        if ( !v13 )
          goto LABEL_235;
        LODWORD(lpThreadId) = v12;
        LODWORD(dwCreationFlags) = 749;
        goto LABEL_233;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 56LL))(v69, a1 + 1488);
      if ( v12 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
          goto LABEL_236;
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
        v14 = 0;
        if ( !v13 )
          goto LABEL_235;
        LODWORD(lpThreadId) = v12;
        LODWORD(dwCreationFlags) = 753;
        goto LABEL_233;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 64LL))(v69, a1 + 1428);
      if ( v12 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
          goto LABEL_236;
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
        v14 = 0;
        if ( !v13 )
          goto LABEL_235;
        LODWORD(lpThreadId) = v12;
        LODWORD(dwCreationFlags) = 757;
        goto LABEL_233;
      }
    }
    if ( a3 )
    {
      v66 = 0;
      StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a3, &v66);
      v12 = StringCch;
      if ( StringCch < 0
        || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(a3),
            v12 = StringCch,
            StringCch < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
      if ( v12 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
          goto LABEL_236;
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
        v14 = 0;
        if ( !v13 )
          goto LABEL_235;
        LODWORD(lpThreadId) = v12;
        LODWORD(dwCreationFlags) = 765;
        goto LABEL_233;
      }
    }
    if ( a4 )
    {
      if ( a6 )
      {
        FileAttributesW = GetFileAttributesW(a4);
        if ( FileAttributesW == -1 )
          v27 = 0;
        else
          v27 = (FileAttributesW >> 4) & 1;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( !v27 )
        {
          v12 = -2147024893;
          if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
            goto LABEL_236;
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
          v14 = 0;
          if ( !v13 )
            goto LABEL_235;
          LODWORD(lpThreadId) = -2147024893;
          LODWORD(dwCreationFlags) = 775;
          goto LABEL_233;
        }
        FilePart = 0;
        memset_0(Buffer, 0, sizeof(Buffer));
        if ( !GetFullPathNameW(a4, 0x410u, Buffer, &FilePart) )
        {
          v28 = GetLastError();
          v12 = v28;
          if ( v28 )
          {
            if ( v28 > 0 )
              v12 = (unsigned __int16)v28 | 0x80070000;
          }
          else
          {
            v12 = -2147467259;
          }
          if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
            goto LABEL_236;
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
          v14 = 0;
          if ( v12 >= 0 || !v13 )
            goto LABEL_235;
          LODWORD(lpThreadId) = v12;
          LODWORD(dwCreationFlags) = 781;
          goto LABEL_233;
        }
        v29 = GetFileAttributesW(Buffer);
        if ( v29 == -1 )
          v30 = 0;
        else
          v30 = (v29 >> 4) & 1;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( !v30 )
        {
          v12 = -2147024893;
          if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
            goto LABEL_236;
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
          v14 = 0;
          if ( !v13 )
            goto LABEL_235;
          LODWORD(lpThreadId) = -2147024893;
          LODWORD(dwCreationFlags) = 786;
          goto LABEL_233;
        }
        v66 = 0;
        Internal = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Buffer, &v66);
        v12 = Internal;
        if ( Internal < 0
          || (Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Buffer),
              v12 = Internal,
              Internal < 0) )
        {
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
        if ( v12 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
            goto LABEL_236;
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
          v14 = 0;
          if ( !v13 )
            goto LABEL_235;
          LODWORD(lpThreadId) = v12;
          LODWORD(dwCreationFlags) = 791;
          goto LABEL_233;
        }
      }
      else
      {
        v66 = 0;
        v32 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a4, &v66);
        v12 = v32;
        if ( v32 < 0
          || (v32 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(a4),
              v12 = v32,
              v32 < 0) )
        {
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v32);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
        if ( v12 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
            goto LABEL_236;
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
          v14 = 0;
          if ( !v13 )
            goto LABEL_235;
          LODWORD(lpThreadId) = v12;
          LODWORD(dwCreationFlags) = 798;
          goto LABEL_233;
        }
      }
    }
    v33 = *(_QWORD *)(a1 + 1304);
    if ( v33 )
    {
      v12 = 0;
      *(_QWORD *)(a1 + 96) = v33;
    }
    else
    {
      v12 = -2147024809;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 804;
      goto LABEL_233;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 432));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 808;
      goto LABEL_233;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 488));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 809;
      goto LABEL_233;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 544));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 810;
      goto LABEL_233;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 600));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 811;
      goto LABEL_233;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 656));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 812;
      goto LABEL_233;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 712));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 813;
      goto LABEL_233;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 768));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 814;
      goto LABEL_233;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 824));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 815;
      goto LABEL_233;
    }
    v12 = CDword::Init((CDword *)(a1 + 872), 0xFFFFFFFF);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 816;
      goto LABEL_233;
    }
    v12 = CDword::Init((CDword *)(a1 + 1240), 0xFFFFFFFF);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 817;
      goto LABEL_233;
    }
    v12 = CProgressData::Init((CProgressData *)(a1 + 936));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 818;
      goto LABEL_233;
    }
    v12 = CProgressData::Init((CProgressData *)(a1 + 1096));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 819;
      goto LABEL_233;
    }
    v34 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 1048));
    v12 = v34;
    if ( v34 >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1048));
      v73 = 1;
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1048));
      v72 = 1;
      CArray<DP_CPP<CProgressData>,DP_CPP<CProgressData>,CAdaptorDefault,CPoliciesDefault>::SetSize(a1 + 1024, 0);
      *(_DWORD *)(a1 + 1016) = 0;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( v72 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1048));
        v72 = 0;
      }
      *(_DWORD *)(a1 + 1020) = 30;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( v73 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1048));
        v73 = 0;
      }
      v12 = 0;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v34);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 820;
      goto LABEL_233;
    }
    if ( v68 )
    {
      v35 = v68;
      v68 = 0;
      v36 = *(_QWORD *)(a1 + 224);
      if ( v36 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v36 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      *(_QWORD *)(a1 + 224) = v35;
    }
    v38 = *(DWORD **)v67;
    if ( *(_QWORD *)v67 )
    {
      v39 = *(DWORD **)v67;
      v38 = 0;
      *(_QWORD *)v67 = 0;
      v40 = *(_QWORD *)(a1 + 216);
      if ( v40 )
      {
        v41 = GetProcessHeap();
        HeapFree(v41, 0, (LPVOID)(v40 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      *(_QWORD *)(a1 + 216) = v39;
    }
    v42 = CreateEventW(0, 0, 0, 0);
    v43 = *(void **)(a1 + 256);
    if ( v43 )
      CloseHandle(v43);
    if ( v42 )
    {
      *(_QWORD *)(a1 + 256) = v42;
      v45 = CreateEventW(0, 0, 0, 0);
      v46 = *(void **)(a1 + 264);
      if ( v46 )
        CloseHandle(v46);
      if ( v45 )
      {
        *(_QWORD *)(a1 + 264) = v45;
        v48 = CreateEventW(0, 1, 0, 0);
        v49 = *(void **)(a1 + 272);
        if ( v49 )
          CloseHandle(v49);
        if ( v48 )
        {
          *(_QWORD *)(a1 + 272) = v48;
          *(_QWORD *)(a1 + 1328) = a1;
          *(_QWORD *)(a1 + 1352) = a1 + 392;
          *(_QWORD *)(a1 + 1360) = a1 + 536;
          *(_QWORD *)(a1 + 1336) = *(_QWORD *)(a1 + 256);
          *(_QWORD *)(a1 + 1344) = v48;
          Thread = CreateThread(0, 0, CDlpTask::TaskOperationThreadProc, (LPVOID)(a1 + 1328), (DWORD)v38, v38);
          v52 = *(void **)(a1 + 280);
          if ( v52 )
            CloseHandle(v52);
          if ( Thread )
          {
            *(_QWORD *)(a1 + 280) = Thread;
            *(_QWORD *)(a1 + 1368) = a1;
            *(_QWORD *)(a1 + 1392) = a1 + 408;
            *(_QWORD *)(a1 + 1400) = a1 + 592;
            *(_QWORD *)(a1 + 1376) = *(_QWORD *)(a1 + 264);
            *(_QWORD *)(a1 + 1384) = *(_QWORD *)(a1 + 272);
            v54 = CreateThread(0, 0, CDlpTask::TaskOperationThreadProc, (LPVOID)(a1 + 1368), (DWORD)v38, v38);
            v55 = *(void **)(a1 + 288);
            if ( v55 )
              CloseHandle(v55);
            if ( v54 )
            {
              *(_QWORD *)(a1 + 288) = v54;
              v57 = CDlpState::Set(v10, a5, 0);
              v12 = v57;
              if ( v57 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v57);
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
              if ( v12 >= 0 || !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
                goto LABEL_236;
              v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
              v14 = (unsigned int)v38;
              if ( !v13 )
                goto LABEL_235;
              LODWORD(lpThreadId) = v12;
              LODWORD(dwCreationFlags) = 876;
            }
            else
            {
              *(_QWORD *)(a1 + 288) = v38;
              v56 = GetLastError();
              v12 = v56;
              if ( v56 )
              {
                if ( v56 > 0 )
                  v12 = (unsigned __int16)v56 | 0x80070000;
              }
              else
              {
                v12 = -2147467259;
              }
              if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
                goto LABEL_236;
              v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
              v14 = (unsigned int)v38;
              if ( v12 >= 0 || !v13 )
                goto LABEL_235;
              LODWORD(lpThreadId) = v12;
              LODWORD(dwCreationFlags) = 872;
            }
          }
          else
          {
            *(_QWORD *)(a1 + 280) = v38;
            v53 = GetLastError();
            v12 = v53;
            if ( v53 )
            {
              if ( v53 > 0 )
                v12 = (unsigned __int16)v53 | 0x80070000;
            }
            else
            {
              v12 = -2147467259;
            }
            if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
              goto LABEL_236;
            v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
            v14 = (unsigned int)v38;
            if ( v12 >= 0 || !v13 )
              goto LABEL_235;
            LODWORD(lpThreadId) = v12;
            LODWORD(dwCreationFlags) = 858;
          }
        }
        else
        {
          *(_QWORD *)(a1 + 272) = v38;
          v50 = GetLastError();
          v12 = v50;
          if ( v50 )
          {
            if ( v50 > 0 )
              v12 = (unsigned __int16)v50 | 0x80070000;
          }
          else
          {
            v12 = -2147467259;
          }
          if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
            goto LABEL_236;
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
          v14 = (unsigned int)v38;
          if ( v12 >= 0 || !v13 )
            goto LABEL_235;
          LODWORD(lpThreadId) = v12;
          LODWORD(dwCreationFlags) = 842;
        }
      }
      else
      {
        *(_QWORD *)(a1 + 264) = v38;
        v47 = GetLastError();
        v12 = v47;
        if ( v47 )
        {
          if ( v47 > 0 )
            v12 = (unsigned __int16)v47 | 0x80070000;
        }
        else
        {
          v12 = -2147467259;
        }
        if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
          goto LABEL_236;
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
        v14 = (unsigned int)v38;
        if ( v12 >= 0 || !v13 )
          goto LABEL_235;
        LODWORD(lpThreadId) = v12;
        LODWORD(dwCreationFlags) = 839;
      }
    }
    else
    {
      *(_QWORD *)(a1 + 256) = v38;
      v44 = GetLastError();
      v12 = v44;
      if ( v44 )
      {
        if ( v44 > 0 )
          v12 = (unsigned __int16)v44 | 0x80070000;
      }
      else
      {
        v12 = -2147467259;
      }
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_236;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = (unsigned int)v38;
      if ( v12 >= 0 || !v13 )
        goto LABEL_235;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 836;
    }
LABEL_233:
    v58 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v13,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpTask::Initialize",
            dwCreationFlags,
            lpThreadId);
    v14 = (unsigned int)v58;
    if ( v58 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v58);
    goto LABEL_235;
  }
  *(_QWORD *)(a1 + 232) = 0;
  v17 = GetLastError();
  v12 = v17;
  if ( v17 )
  {
    if ( v17 > 0 )
      v12 = (unsigned __int16)v17 | 0x80070000;
  }
  else
  {
    v12 = -2147467259;
  }
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
  {
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
    v14 = 0;
    if ( v12 < 0 && v13 )
    {
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 736;
      goto LABEL_233;
    }
LABEL_235:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
  }
LABEL_236:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
  if ( *(_QWORD *)v67 )
  {
    v59 = (void *)(*(_QWORD *)v67 - 4LL);
    v60 = GetProcessHeap();
    HeapFree(v60, 0, v59);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v68 )
  {
    v61 = (void *)(v68 - 4);
    v62 = GetProcessHeap();
    HeapFree(v62, 0, v61);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v69 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180064ae8  push    rbp
0x180064aea  push    rbx
0x180064aeb  push    rsi
0x180064aec  push    rdi
0x180064aed  push    r12
0x180064aef  push    r13
0x180064af1  push    r14
0x180064af3  push    r15
0x180064af5  lea     rbp, [rsp-7D8h]
0x180064afd  sub     rsp, 8D8h
0x180064b04  mov     rax, cs:__security_cookie
0x180064b0b  xor     rax, rsp
0x180064b0e  mov     [rbp+810h+var_50], rax
0x180064b15  mov     r14, r9
0x180064b18  mov     r15, r8
0x180064b1b  mov     r12, rdx
0x180064b1e  mov     rsi, rcx
0x180064b21  xor     eax, eax
0x180064b23  mov     [rsp+910h+var_8C8], rax
0x180064b28  mov     [rsp+910h+var_8D0], rax
0x180064b2d  mov     qword ptr [rsp+910h+var_8D8], rax
0x180064b32  mov     [rsp+910h+FilePart], rax
0x180064b37  lea     r13, [rcx+128h]
0x180064b3e  lea     rcx, [r13+10h]; lpCriticalSection
0x180064b42  call    cs:__imp_EnterCriticalSection
0x180064b48  mov     [rsp+910h+var_8A0], 1
0x180064b50  mov     edi, [r13+0]
0x180064b54  xor     ecx, ecx
0x180064b56  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180064b5b  mov     eax, [rsp+910h+var_8A0]
0x180064b5f  test    eax, eax
0x180064b61  jz      short loc_180064B75
0x180064b63  lea     rcx, [r13+10h]; lpCriticalSection
0x180064b67  call    cs:__imp_LeaveCriticalSection
0x180064b6d  mov     [rsp+910h+var_8A0], 0
0x180064b75  cmp     edi, 0FEBEFEBEh
0x180064b7b  jz      short loc_180064BD9
0x180064b7d  mov     edi, 800704DFh
0x180064b82  mov     rax, [rsi+0B0h]
0x180064b89  lea     rcx, [rsi+0B0h]
0x180064b90  mov     rax, [rax+10h]
0x180064b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b99  xor     r12d, r12d
0x180064b9c  test    rax, rax
0x180064b9f  jz      loc_180065EC6
0x180064ba5  mov     rax, [rsi+0B0h]
0x180064bac  lea     rcx, [rsi+0B0h]
0x180064bb3  mov     rax, [rax+10h]
0x180064bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064bbc  mov     ecx, r12d
0x180064bbf  test    rax, rax
0x180064bc2  jz      loc_180065EC1
0x180064bc8  mov     dword ptr [rsp+910h+lpThreadId], edi
0x180064bcc  mov     dword ptr [rsp+910h+dwCreationFlags], 2D3h
0x180064bd4  jmp     loc_180065E9B
0x180064bd9  mov     dword ptr [rsi+598h], 7530h
0x180064be3  mov     eax, 3E8h
0x180064be8  mov     [rsi+59Ch], eax
0x180064bee  mov     [rsi+5A0h], eax
0x180064bf4  xor     r9d, r9d; lpName
0x180064bf7  xor     r8d, r8d; bInitialState
0x180064bfa  lea     edx, [r9+1]; bManualReset
0x180064bfe  xor     ecx, ecx; lpEventAttributes
0x180064c00  call    cs:__imp_CreateEventW
0x180064c06  mov     rbx, rax
0x180064c09  mov     rcx, [rsi+0E8h]; hObject
0x180064c10  test    rcx, rcx
0x180064c13  jz      short loc_180064C1B
0x180064c15  call    cs:__imp_CloseHandle
0x180064c1b  test    rbx, rbx
0x180064c1e  jnz     loc_180064CA8
0x180064c24  xor     r12d, r12d
0x180064c27  mov     [rsi+0E8h], r12
0x180064c2e  call    cs:__imp_GetLastError
0x180064c34  mov     edi, eax
0x180064c36  test    eax, eax
0x180064c38  jnz     short loc_180064C41
0x180064c3a  mov     edi, 80004005h
0x180064c3f  jmp     short loc_180064C4C
0x180064c41  jle     short loc_180064C4C
0x180064c43  movzx   edi, ax
0x180064c46  or      edi, 80070000h
0x180064c4c  mov     rax, [rsi+0B0h]
0x180064c53  lea     rcx, [rsi+0B0h]
0x180064c5a  mov     rax, [rax+10h]
0x180064c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064c63  test    rax, rax
0x180064c66  jz      loc_180065EC6
0x180064c6c  mov     rax, [rsi+0B0h]
0x180064c73  lea     rcx, [rsi+0B0h]
0x180064c7a  mov     rax, [rax+10h]
0x180064c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064c83  mov     ecx, r12d
0x180064c86  test    edi, edi
0x180064c88  jns     loc_180065EC1
0x180064c8e  test    rax, rax
0x180064c91  jz      loc_180065EC1
0x180064c97  mov     dword ptr [rsp+910h+lpThreadId], edi
0x180064c9b  mov     dword ptr [rsp+910h+dwCreationFlags], 2E0h
0x180064ca3  jmp     loc_180065E9B
0x180064ca8  mov     [rsi+0E8h], rbx
0x180064caf  xor     r9d, r9d; lpName
0x180064cb2  xor     r8d, r8d; bInitialState
0x180064cb5  xor     edx, edx; bManualReset
0x180064cb7  xor     ecx, ecx; lpEventAttributes
0x180064cb9  call    cs:__imp_CreateEventW
0x180064cbf  mov     rbx, rax
0x180064cc2  mov     rcx, [rsi+0F0h]; hObject
0x180064cc9  test    rcx, rcx
0x180064ccc  jz      short loc_180064CD4
0x180064cce  call    cs:__imp_CloseHandle
0x180064cd4  test    rbx, rbx
0x180064cd7  jnz     loc_180064D61
0x180064cdd  xor     r12d, r12d
0x180064ce0  mov     [rsi+0F0h], r12
0x180064ce7  call    cs:__imp_GetLastError
0x180064ced  mov     edi, eax
0x180064cef  test    eax, eax
0x180064cf1  jnz     short loc_180064CFA
0x180064cf3  mov     edi, 80004005h
0x180064cf8  jmp     short loc_180064D05
0x180064cfa  jle     short loc_180064D05
0x180064cfc  movzx   edi, ax
0x180064cff  or      edi, 80070000h
0x180064d05  mov     rax, [rsi+0B0h]
0x180064d0c  lea     rcx, [rsi+0B0h]
0x180064d13  mov     rax, [rax+10h]
0x180064d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d1c  test    rax, rax
0x180064d1f  jz      loc_180065EC6
0x180064d25  mov     rax, [rsi+0B0h]
0x180064d2c  lea     rcx, [rsi+0B0h]
0x180064d33  mov     rax, [rax+10h]
0x180064d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d3c  mov     ecx, r12d
0x180064d3f  test    edi, edi
0x180064d41  jns     loc_180065EC1
0x180064d47  test    rax, rax
0x180064d4a  jz      loc_180065EC1
0x180064d50  mov     dword ptr [rsp+910h+lpThreadId], edi
0x180064d54  mov     dword ptr [rsp+910h+dwCreationFlags], 2E3h
0x180064d5c  jmp     loc_180065E9B
0x180064d61  mov     [rsi+0F0h], rbx
0x180064d68  xor     r9d, r9d; lpName
0x180064d6b  xor     r8d, r8d; bInitialState
0x180064d6e  xor     edx, edx; bManualReset
0x180064d70  xor     ecx, ecx; lpEventAttributes
0x180064d72  call    cs:__imp_CreateEventW
0x180064d78  mov     rbx, rax
0x180064d7b  mov     rcx, [rsi+0F8h]; hObject
0x180064d82  test    rcx, rcx
0x180064d85  jz      short loc_180064D8D
0x180064d87  call    cs:__imp_CloseHandle
0x180064d8d  test    rbx, rbx
0x180064d90  jnz     loc_180064E1A
0x180064d96  xor     r12d, r12d
0x180064d99  mov     [rsi+0F8h], r12
0x180064da0  call    cs:__imp_GetLastError
0x180064da6  mov     edi, eax
0x180064da8  test    eax, eax
0x180064daa  jnz     short loc_180064DB3
0x180064dac  mov     edi, 80004005h
0x180064db1  jmp     short loc_180064DBE
0x180064db3  jle     short loc_180064DBE
0x180064db5  movzx   edi, ax
0x180064db8  or      edi, 80070000h
0x180064dbe  mov     rax, [rsi+0B0h]
0x180064dc5  lea     rcx, [rsi+0B0h]
0x180064dcc  mov     rax, [rax+10h]
0x180064dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064dd5  test    rax, rax
0x180064dd8  jz      loc_180065EC6
0x180064dde  mov     rax, [rsi+0B0h]
0x180064de5  lea     rcx, [rsi+0B0h]
0x180064dec  mov     rax, [rax+10h]
0x180064df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064df5  mov     ecx, r12d
0x180064df8  test    edi, edi
0x180064dfa  jns     loc_180065EC1
0x180064e00  test    rax, rax
0x180064e03  jz      loc_180065EC1
0x180064e09  mov     dword ptr [rsp+910h+lpThreadId], edi
0x180064e0d  mov     dword ptr [rsp+910h+dwCreationFlags], 2E6h
0x180064e15  jmp     loc_180065E9B
0x180064e1a  mov     [rsi+0F8h], rbx
0x180064e21  mov     r8d, 10h; Size
0x180064e27  mov     rdx, r12; Buf2
0x180064e2a  lea     rcx, WINDLP_TRANSPORT_NONE; Buf1
0x180064e31  call    memcmp_0
0x180064e36  test    eax, eax
0x180064e38  jz      loc_180064FA7
0x180064e3e  mov     rcx, [rsi+518h]
0x180064e45  movaps  xmm0, xmmword ptr [r12]
0x180064e4a  movdqa  [rsp+910h+var_8B0], xmm0
0x180064e50  mov     rax, [rcx]
0x180064e53  lea     r8, [rsp+910h+var_8C8]
0x180064e58  lea     rdx, [rsp+910h+var_8B0]
0x180064e5d  mov     rax, [rax+50h]
0x180064e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064e66  mov     edi, eax
0x180064e68  xor     r12d, r12d
0x180064e6b  test    eax, eax
0x180064e6d  jns     short loc_180064EC3
0x180064e6f  mov     rdx, [rsi+0B0h]
0x180064e76  lea     rcx, [rsi+0B0h]
0x180064e7d  mov     rax, [rdx+10h]
0x180064e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064e86  test    rax, rax
0x180064e89  jz      loc_180065EC6
0x180064e8f  mov     rax, [rsi+0B0h]
0x180064e96  lea     rcx, [rsi+0B0h]
0x180064e9d  mov     rax, [rax+10h]
0x180064ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ea6  mov     ecx, r12d
0x180064ea9  test    rax, rax
0x180064eac  jz      loc_180065EC1
0x180064eb2  mov     dword ptr [rsp+910h+lpThreadId], edi
0x180064eb6  mov     dword ptr [rsp+910h+dwCreationFlags], 2EDh
0x180064ebe  jmp     loc_180065E9B
0x180064ec3  mov     rcx, [rsp+910h+var_8C8]
0x180064ec8  mov     rax, [rcx]
0x180064ecb  lea     rdx, [rsi+5D0h]
0x180064ed2  mov     rax, [rax+38h]
0x180064ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064edb  mov     edi, eax
0x180064edd  test    eax, eax
0x180064edf  jns     short loc_180064F35
0x180064ee1  mov     rax, [rsi+0B0h]
0x180064ee8  lea     rcx, [rsi+0B0h]
0x180064eef  mov     rax, [rax+10h]
0x180064ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ef8  test    rax, rax
0x180064efb  jz      loc_180065EC6
0x180064f01  mov     rax, [rsi+0B0h]
0x180064f08  lea     rcx, [rsi+0B0h]
0x180064f0f  mov     rax, [rax+10h]
0x180064f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f18  mov     ecx, r12d
0x180064f1b  test    rax, rax
0x180064f1e  jz      loc_180065EC1
0x180064f24  mov     dword ptr [rsp+910h+lpThreadId], edi
0x180064f28  mov     dword ptr [rsp+910h+dwCreationFlags], 2F1h
0x180064f30  jmp     loc_180065E9B
0x180064f35  mov     rcx, [rsp+910h+var_8C8]
0x180064f3a  mov     rax, [rcx]
0x180064f3d  lea     rdx, [rsi+594h]
0x180064f44  mov     rax, [rax+40h]
0x180064f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f4d  mov     edi, eax
0x180064f4f  test    eax, eax
0x180064f51  jns     short loc_180064FAA
0x180064f53  mov     rax, [rsi+0B0h]
0x180064f5a  lea     rcx, [rsi+0B0h]
0x180064f61  mov     rax, [rax+10h]
0x180064f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f6a  test    rax, rax
0x180064f6d  jz      loc_180065EC6
0x180064f73  mov     rax, [rsi+0B0h]
0x180064f7a  lea     rcx, [rsi+0B0h]
0x180064f81  mov     rax, [rax+10h]
0x180064f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f8a  mov     ecx, r12d
0x180064f8d  test    rax, rax
0x180064f90  jz      loc_180065EC1
0x180064f96  mov     dword ptr [rsp+910h+lpThreadId], edi
0x180064f9a  mov     dword ptr [rsp+910h+dwCreationFlags], 2F5h
0x180064fa2  jmp     loc_180065E9B
0x180064fa7  xor     r12d, r12d
0x180064faa  test    r15, r15
0x180064fad  jz      loc_180065048
0x180064fb3  mov     [rsp+910h+var_8E0], r12d
0x180064fb8  lea     rdx, [rsp+910h+var_8E0]
0x180064fbd  mov     rcx, r15
0x180064fc0  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180064fc5  mov     edi, eax
0x180064fc7  test    eax, eax
0x180064fc9  js      short loc_180064FE2
0x180064fcb  lea     r8, [rsp+910h+var_8D0]
0x180064fd0  mov     edx, [rsp+910h+var_8E0]
0x180064fd4  mov     rcx, r15; Src
0x180064fd7  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180064fdc  mov     edi, eax
0x180064fde  test    eax, eax
0x180064fe0  jns     short loc_180064FE9
0x180064fe2  mov     ecx, eax
0x180064fe4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180064fe9  mov     ecx, edi
0x180064feb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180064ff0  test    edi, edi
0x180064ff2  jns     short loc_180065048
0x180064ff4  mov     rax, [rsi+0B0h]
0x180064ffb  lea     rcx, [rsi+0B0h]
0x180065002  mov     rax, [rax+10h]
0x180065006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006500b  test    rax, rax
0x18006500e  jz      loc_180065EC6
0x180065014  mov     rax, [rsi+0B0h]
0x18006501b  lea     rcx, [rsi+0B0h]
0x180065022  mov     rax, [rax+10h]
0x180065026  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
