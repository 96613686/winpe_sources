# CDlpManager::SerializeSynchronous(void)

- ea: `0x1800720c4`
- end: `0x1800731ad`
- name: `?SerializeSynchronous@CDlpManager@@AEAAJXZ`
- size: `4329`
- prototype: `__int64 __fastcall(CDlpManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800706a0`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180028640`
- `0x1800475b0`
- `0x180061d1c`
- `0x180070950`
- `0x1800720c4`
- `0x180074ed4`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007229b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072803`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072836`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007229b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072803`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072836`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800722aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072812`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072844`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800722aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072812`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072844`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072114`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072333`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800724be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072692`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072aab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072d4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072114`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072333`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800724be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072692`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072aab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072d4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007235a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007267a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072857`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072872`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007288f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800728ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800728c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072a94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072d26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072ebd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007235a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007267a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072857`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072872`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007288f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800728ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800728c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072a94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072d26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072ebd`
- `UNATTEND!UnattendCtxCleanup` at `0x180072216`
- `UNATTEND!UnattendCtxCleanup` at `0x180072216`
- `UNATTEND!UnattendCtxDeserializeString` at `0x18007227c`
- `UNATTEND!UnattendCtxDeserializeString` at `0x18007227c`

## string_xrefs

- `0x180072459`: `WorkingPath`
- `0x1800723ea`: `TaskCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CDlpManager::SerializeSynchronous(CDlpManager *this)
{
  char *v2; // r12
  char *v3; // r15
  _QWORD *v4; // r13
  unsigned __int16 *v5; // rbx
  __int64 v6; // r14
  int XmlFilePaths; // edi
  unsigned __int16 *v8; // rbx
  int v9; // ecx
  int v10; // eax
  int v11; // eax
  HANDLE ProcessHeap; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // edi
  unsigned int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  int v21; // r14d
  unsigned int v22; // r14d
  __int64 v23; // rax
  __int64 v24; // rcx
  int v25; // eax
  HANDLE v26; // rax
  void *v27; // rbx
  HANDLE v28; // rax
  int v30; // ebx
  unsigned int v31; // r14d
  int v32; // ebx
  unsigned int v33; // r15d
  int v34; // r14d
  __int64 v35; // rbx
  int v36; // ebx
  __int64 (__fastcall ***v37)(_QWORD, __int64); // rcx
  unsigned __int16 **v38; // r8
  int v39; // eax
  __int64 v40; // rax
  __int64 v41; // rcx
  int v42; // eax
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+28h] [rbp-D8h]
  int v47; // [rsp+28h] [rbp-D8h]
  int v48; // [rsp+28h] [rbp-D8h]
  int v49; // [rsp+40h] [rbp-C0h]
  int v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v52; // [rsp+68h] [rbp-98h] BYREF
  __int64 v53; // [rsp+70h] [rbp-90h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-88h]
  void **v55; // [rsp+80h] [rbp-80h]
  char *v56; // [rsp+88h] [rbp-78h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  void **v58; // [rsp+98h] [rbp-68h]
  char *v59; // [rsp+A0h] [rbp-60h]
  __int64 v60; // [rsp+A8h] [rbp-58h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B0h] [rbp-50h]
  void **v62; // [rsp+B8h] [rbp-48h]
  char *v63; // [rsp+C0h] [rbp-40h]
  __int64 v64; // [rsp+C8h] [rbp-38h]
  __int64 v65; // [rsp+D0h] [rbp-30h]
  int v66; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v67; // [rsp+150h] [rbp+50h] BYREF
  _QWORD *v68; // [rsp+158h] [rbp+58h] BYREF
  __int64 v69; // [rsp+160h] [rbp+60h] BYREF
  __int64 v70; // [rsp+168h] [rbp+68h] BYREF

  v65 = 0;
  v63 = (char *)this + 304;
  v62 = &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable';
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 312);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  v64 = 1;
  v60 = 0;
  v58 = &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable';
  v59 = (char *)this + 360;
  v57 = 0;
  v55 = &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable';
  v56 = (char *)this + 416;
  v50 = 0;
  v2 = (char *)this + 472;
  v49 = 0;
  v3 = (char *)this + 192;
  v53 = 0;
  v4 = 0;
  lpMem = 0;
  v5 = 0;
  v67 = 0;
  v51 = 0;
  v69 = 0;
  v68 = 0;
  v70 = 0;
  v6 = *((_QWORD *)this + 83);
  if ( v6 && (*((_BYTE *)this + 856) & 2) == 0 )
  {
    v8 = 0;
    v52 = 0;
    XmlFilePaths = UnattendCtxCleanup(v6 + 136);
    if ( (int)(XmlFilePaths + 0x80000000) < 0 || XmlFilePaths == -2147024809 )
    {
      *(_QWORD *)(v6 + 136) = 0;
      v10 = STRAPI_Format(&v52, &qword_18009B400, L"WINDLP", L"WINDLP");
      XmlFilePaths = v10;
      if ( v10 < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
        v8 = v52;
        goto LABEL_13;
      }
      v8 = v52;
      v11 = UnattendCtxDeserializeString(v6 + 136, v52);
      XmlFilePaths = v11;
      if ( v11 >= 0 )
      {
LABEL_13:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)XmlFilePaths);
        if ( v8 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v8 - 2);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
          {
LABEL_22:
            v5 = v67;
            goto LABEL_69;
          }
          v13 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v14 = 0;
          if ( !v13 )
          {
LABEL_21:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
            goto LABEL_22;
          }
          v46 = XmlFilePaths;
          v43 = 2584;
LABEL_19:
          v15 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v13,
                  4u,
                  (__int64)L"%s(%d): Result = 0x%X",
                  L"CDlpManager::SerializeSynchronous",
                  v43,
                  v46,
                  &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable');
          v14 = (unsigned int)v15;
          if ( v15 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
          goto LABEL_21;
        }
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
        v66 = 1;
        v16 = *((_DWORD *)this + 32);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( v66 )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
          v66 = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 83)
                                                                                               + 8LL)
                                                                                   + 24LL))(
                         *((_QWORD *)this + 83) + 8LL,
                         L"State",
                         v16);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_22;
          v13 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v14 = 0;
          if ( !v13 )
            goto LABEL_21;
          v46 = XmlFilePaths;
          v43 = 2593;
          goto LABEL_19;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 83)
                                                                                               + 8LL)
                                                                                   + 24LL))(
                         *((_QWORD *)this + 83) + 8LL,
                         L"TaskCount",
                         *((unsigned int *)this + 133));
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_22;
          v13 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v14 = 0;
          if ( !v13 )
            goto LABEL_21;
          v46 = XmlFilePaths;
          v43 = 2596;
          goto LABEL_19;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 83)
                                                                                               + 8LL)
                                                                                   + 40LL))(
                         *((_QWORD *)this + 83) + 8LL,
                         L"WorkingPath",
                         *((_QWORD *)this + 15));
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_22;
          v13 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v14 = 0;
          if ( !v13 )
            goto LABEL_21;
          v46 = XmlFilePaths;
          v43 = 2599;
          goto LABEL_19;
        }
        EnterCriticalSection((LPCRITICAL_SECTION)this + 12);
        v50 = 1;
        v17 = *((_DWORD *)this + 137);
        XmlFilePaths = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 83)
                                                                                               + 8LL)
                                                                                   + 24LL))(
                         *((_QWORD *)this + 83) + 8LL,
                         L"StringCount",
                         v17);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
          {
LABEL_44:
            v5 = v67;
LABEL_68:
            v3 = (char *)this + 192;
            goto LABEL_69;
          }
          v18 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v19 = 0;
          if ( !v18 )
          {
LABEL_43:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v19);
            goto LABEL_44;
          }
          v47 = XmlFilePaths;
          v44 = 2606;
LABEL_41:
          v20 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v18,
                  4u,
                  (__int64)L"%s(%d): Result = 0x%X",
                  L"CDlpManager::SerializeSynchronous",
                  v44,
                  v47,
                  &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable');
          v19 = (unsigned int)v20;
          if ( v20 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v20);
          goto LABEL_43;
        }
        if ( *((_DWORD *)this + 141) != v17 )
        {
          XmlFilePaths = -2147418113;
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_44;
          v18 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v19 = 0;
          if ( !v18 )
            goto LABEL_43;
          v47 = -2147418113;
          v44 = 2608;
          goto LABEL_41;
        }
        v21 = 0;
        if ( v17 )
        {
          while ( 1 )
          {
            if ( v68 )
            {
              (*(void (__fastcall **)(_QWORD *))(*v68 + 16LL))(v68);
              v68 = 0;
            }
            XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD **))(**((_QWORD **)this + 83)
                                                                                         + 24LL))(
                             *((_QWORD *)this + 83),
                             L"StringProperty",
                             &v68);
            if ( XmlFilePaths < 0 )
              break;
            XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD))(v68[1] + 40LL))(
                             v68 + 1,
                             L"Name",
                             *(_QWORD *)(*((_QWORD *)this + 69) + 8LL * v21));
            if ( XmlFilePaths < 0 )
            {
              if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
                goto LABEL_66;
              v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
              v24 = 0;
              if ( v23 )
              {
                v48 = XmlFilePaths;
                v45 = 2613;
                goto LABEL_63;
              }
              goto LABEL_65;
            }
            XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD))(v68[1] + 40LL))(
                             v68 + 1,
                             L"Value",
                             *(_QWORD *)(*((_QWORD *)this + 71) + 8LL * v21));
            if ( XmlFilePaths < 0 )
            {
              if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
                goto LABEL_66;
              v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
              v24 = 0;
              if ( v23 )
              {
                v48 = XmlFilePaths;
                v45 = 2614;
                goto LABEL_63;
              }
              goto LABEL_65;
            }
            if ( ++v21 >= v17 )
              goto LABEL_56;
          }
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_66;
          v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v24 = 0;
          if ( v23 )
          {
            v48 = XmlFilePaths;
            v45 = 2612;
            goto LABEL_63;
          }
          goto LABEL_65;
        }
LABEL_56:
        LeaveCriticalSection((LPCRITICAL_SECTION)this + 12);
        v50 = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
        LODWORD(v60) = 1;
        v22 = *((_DWORD *)this + 145);
        XmlFilePaths = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 83)
                                                                                               + 8LL)
                                                                                   + 24LL))(
                         *((_QWORD *)this + 83) + 8LL,
                         L"DwordCount",
                         v22);
        if ( XmlFilePaths >= 0 )
        {
          if ( *((_DWORD *)this + 149) != v22 )
          {
            XmlFilePaths = -2147418113;
            if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
              goto LABEL_66;
            v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
            v24 = 0;
            if ( !v23 )
              goto LABEL_65;
            v48 = -2147418113;
            v45 = 2626;
            goto LABEL_63;
          }
          v30 = 0;
          if ( v22 )
          {
            while ( 1 )
            {
              if ( v68 )
              {
                (*(void (__fastcall **)(_QWORD *))(*v68 + 16LL))(v68);
                v68 = 0;
              }
              XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD **))(**((_QWORD **)this + 83)
                                                                                           + 24LL))(
                               *((_QWORD *)this + 83),
                               L"DwordProperty",
                               &v68);
              if ( XmlFilePaths < 0 )
                break;
              XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD))(v68[1] + 40LL))(
                               v68 + 1,
                               L"Name",
                               *(_QWORD *)(*((_QWORD *)this + 73) + 8LL * v30));
              if ( XmlFilePaths < 0 )
              {
                if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
                  goto LABEL_66;
                v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
                v24 = 0;
                if ( v23 )
                {
                  v48 = XmlFilePaths;
                  v45 = 2631;
                  goto LABEL_63;
                }
                goto LABEL_65;
              }
              XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD))(v68[1] + 24LL))(
                               v68 + 1,
                               L"Value",
                               *(unsigned int *)(*((_QWORD *)this + 75) + 4LL * v30));
              if ( XmlFilePaths < 0 )
              {
                if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
                  goto LABEL_66;
                v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
                v24 = 0;
                if ( v23 )
                {
                  v48 = XmlFilePaths;
                  v45 = 2632;
                  goto LABEL_63;
                }
                goto LABEL_65;
              }
              if ( ++v30 >= v22 )
                goto LABEL_109;
            }
            if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
              goto LABEL_66;
            v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
            v24 = 0;
            if ( v23 )
            {
              v48 = XmlFilePaths;
              v45 = 2630;
              goto LABEL_63;
            }
            goto LABEL_65;
          }
LABEL_109:
          if ( (_DWORD)v60 )
          {
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
            LODWORD(v60) = 0;
          }
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
          LODWORD(v57) = 1;
          v31 = *((_DWORD *)this + 153);
          XmlFilePaths = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 83)
                                                                                                 + 8LL)
                                                                                     + 24LL))(
                           *((_QWORD *)this + 83) + 8LL,
                           L"QuadwordCount",
                           v31);
          if ( XmlFilePaths < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
              goto LABEL_66;
            v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
            v24 = 0;
            if ( !v23 )
              goto LABEL_65;
            v48 = XmlFilePaths;
            v45 = 2642;
            goto LABEL_63;
          }
          if ( *((_DWORD *)this + 157) != v31 )
          {
            XmlFilePaths = -2147418113;
            if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
              goto LABEL_66;
            v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
            v24 = 0;
            if ( !v23 )
              goto LABEL_65;
            v48 = -2147418113;
            v45 = 2644;
            goto LABEL_63;
          }
          v32 = 0;
          if ( v31 )
          {
            while ( 1 )
            {
              if ( v68 )
              {
                (*(void (__fastcall **)(_QWORD *))(*v68 + 16LL))(v68);
                v68 = 0;
              }
              XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD **))(**((_QWORD **)this + 83)
                                                                                           + 24LL))(
                               *((_QWORD *)this + 83),
                               L"QuadwordProperty",
                               &v68);
              if ( XmlFilePaths < 0 )
                break;
              XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD))(v68[1] + 40LL))(
                               v68 + 1,
                               L"Name",
                               *(_QWORD *)(*((_QWORD *)this + 77) + 8LL * v32));
              if ( XmlFilePaths < 0 )
              {
                if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
                  goto LABEL_66;
                v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
                v24 = 0;
                if ( v23 )
                {
                  v48 = XmlFilePaths;
                  v45 = 2649;
                  goto LABEL_63;
                }
                goto LABEL_65;
              }
              XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD))(v68[1] + 32LL))(
                               v68 + 1,
                               L"Value",
                               *(_QWORD *)(*((_QWORD *)this + 79) + 8LL * v32));
              if ( XmlFilePaths < 0 )
              {
                if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
                  goto LABEL_66;
                v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
                v24 = 0;
                if ( v23 )
                {
                  v48 = XmlFilePaths;
                  v45 = 2650;
                  goto LABEL_63;
                }
                goto LABEL_65;
              }
              if ( ++v32 >= v31 )
                goto LABEL_135;
            }
            if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
              goto LABEL_66;
            v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
            v24 = 0;
            if ( v23 )
            {
              v48 = XmlFilePaths;
              v45 = 2648;
              goto LABEL_63;
            }
            goto LABEL_65;
          }
LABEL_135:
          if ( (_DWORD)v57 )
          {
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
            LODWORD(v57) = 0;
          }
          if ( (*((_BYTE *)this + 856) & 4) == 0 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
            v49 = 1;
            v33 = *((_DWORD *)this + 133);
            v34 = 0;
            if ( v33 )
            {
              while ( 1 )
              {
                v35 = *(_QWORD *)(*((_QWORD *)this + 67) + 8LL * v34);
                if ( v70 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
                v70 = v35 ? v35 : 0LL;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
                XmlFilePaths = CArray<DP_COM<IUnknown>,DP_COM<IUnknown>,CAdaptorDefault,CPoliciesDefault>::Append(
                                 (__int64)&v53,
                                 &v70);
                if ( XmlFilePaths < 0 )
                  break;
                if ( ++v34 >= v33 )
                {
                  v4 = lpMem;
                  goto LABEL_156;
                }
              }
              if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
                goto LABEL_66;
              v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
              v24 = 0;
              if ( !v23 )
                goto LABEL_65;
              v48 = XmlFilePaths;
              v45 = 2666;
              goto LABEL_63;
            }
LABEL_156:
            LeaveCriticalSection((LPCRITICAL_SECTION)this + 5);
            v49 = 0;
            v36 = 0;
            if ( v33 )
            {
              while ( 1 )
              {
                if ( v69 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
                  v69 = 0;
                }
                XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 *))(**((_QWORD **)this + 83)
                                                                                             + 24LL))(
                                 *((_QWORD *)this + 83),
                                 L"TASK",
                                 &v69);
                if ( XmlFilePaths < 0 )
                  break;
                v37 = (__int64 (__fastcall ***)(_QWORD, __int64))(v4[v36] + 8LL);
                XmlFilePaths = (**v37)(v37, v69);
                if ( XmlFilePaths < 0 )
                {
                  if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
                    goto LABEL_66;
                  v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
                  v24 = 0;
                  if ( v23 )
                  {
                    v48 = XmlFilePaths;
                    v45 = 2677;
                    goto LABEL_63;
                  }
                  goto LABEL_65;
                }
                if ( ++v36 >= v33 )
                  goto LABEL_162;
              }
              if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
                goto LABEL_66;
              v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
              v24 = 0;
              if ( v23 )
              {
                v48 = XmlFilePaths;
                v45 = 2676;
                goto LABEL_63;
              }
              goto LABEL_65;
            }
LABEL_162:
            CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(&v53, 0);
          }
          XmlFilePaths = CDlpStateXml::Serialize(*((CDlpStateXml **)this + 83));
          if ( XmlFilePaths < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
              goto LABEL_66;
            v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
            v24 = 0;
            if ( !v23 )
              goto LABEL_65;
            v48 = XmlFilePaths;
            v45 = 2684;
            goto LABEL_63;
          }
          if ( !*((_DWORD *)this + 215) )
          {
            XmlFilePaths = CDlpStateXml::GetXmlFilePaths(*((CDlpStateXml **)this + 83), &v67, v38);
            if ( XmlFilePaths >= 0 )
            {
              v39 = (*(__int64 (__fastcall **)(CDlpManager *, __int64 *))(*(_QWORD *)this + 152LL))(this, &v51);
              v5 = v67;
              if ( v39 >= 0 )
              {
                XmlFilePaths = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v51 + 40LL))(
                                 v51,
                                 v67);
                if ( XmlFilePaths == -2147467263 )
                {
                  XmlFilePaths = 1;
                }
                else if ( XmlFilePaths < 0 )
                {
                  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
                  {
                    v40 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
                    v41 = 0;
                    if ( v40 )
                    {
                      v42 = CDlpLogT<CEmptyType>::DlpLogFormat(
                              v40,
                              4u,
                              (__int64)L"%s(%d): Result = 0x%X",
                              L"CDlpManager::SerializeSynchronous",
                              2694,
                              XmlFilePaths,
                              &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable');
                      v41 = (unsigned int)v42;
                      if ( v42 < 0 )
                        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v42);
                    }
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v41);
                  }
                  goto LABEL_67;
                }
              }
              *((_DWORD *)this + 215) = 1;
LABEL_67:
              v2 = (char *)this + 472;
              goto LABEL_68;
            }
            if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            {
              v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
              v24 = 0;
              if ( v23 )
              {
                v48 = XmlFilePaths;
                v45 = 2691;
LABEL_63:
                v25 = CDlpLogT<CEmptyType>::DlpLogFormat(
                        v23,
                        4u,
                        (__int64)L"%s(%d): Result = 0x%X",
                        L"CDlpManager::SerializeSynchronous",
                        v45,
                        v48,
                        &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable');
                v24 = (unsigned int)v25;
                if ( v25 < 0 )
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v25);
              }
LABEL_65:
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v24);
            }
          }
        }
        else if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        {
          v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v24 = 0;
          if ( v23 )
          {
            v48 = XmlFilePaths;
            v45 = 2624;
            goto LABEL_63;
          }
          goto LABEL_65;
        }
LABEL_66:
        v5 = v67;
        goto LABEL_67;
      }
      v9 = v11;
    }
    else
    {
      v9 = XmlFilePaths;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
    goto LABEL_13;
  }
  XmlFilePaths = 0;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
LABEL_69:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)XmlFilePaths);
  if ( v70 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
  if ( v68 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v68 + 16LL))(v68);
    v68 = 0;
  }
  if ( v69 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    v69 = 0;
  }
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  if ( v5 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v5 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(&v53, 0);
  v27 = lpMem;
  if ( lpMem )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v27);
  }
  if ( v49 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  if ( v50 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
  if ( (_DWORD)v57 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v56 + 8));
    LODWORD(v57) = 0;
  }
  if ( (_DWORD)v60 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v59 + 8));
    LODWORD(v60) = 0;
  }
  if ( (_DWORD)v64 )
  {
    LeaveCriticalSection(lpCriticalSection);
    LODWORD(v64) = 0;
  }
  return (unsigned int)XmlFilePaths;
}

```

## disassembly

```asm
0x1800720c4  push    rbp
0x1800720c6  push    rbx
0x1800720c7  push    rsi
0x1800720c8  push    rdi
0x1800720c9  push    r12
0x1800720cb  push    r13
0x1800720cd  push    r14
0x1800720cf  push    r15
0x1800720d1  lea     rbp, [rsp-8]
0x1800720d6  sub     rsp, 108h
0x1800720dd  mov     rsi, rcx
0x1800720e0  xor     edi, edi
0x1800720e2  mov     [rbp+40h+var_70], rdi
0x1800720e6  xorps   xmm0, xmm0
0x1800720e9  xor     eax, eax
0x1800720eb  movups  [rbp+40h+var_88], xmm0
0x1800720ef  mov     [rbp+40h+var_78], rax
0x1800720f3  lea     rax, [rcx+130h]
0x1800720fa  mov     qword ptr [rbp+40h+var_88+8], rax
0x1800720fe  lea     rcx, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x180072105  mov     qword ptr [rbp+40h+var_88], rcx
0x180072109  add     rax, 8
0x18007210d  mov     [rbp+40h+lpCriticalSection], rax
0x180072111  mov     rcx, rax; lpCriticalSection
0x180072114  call    cs:__imp_EnterCriticalSection
0x18007211a  mov     dword ptr [rbp+40h+var_78], 1
0x180072121  xorps   xmm0, xmm0
0x180072124  xor     eax, eax
0x180072126  movups  [rbp+40h+var_A8], xmm0
0x18007212a  mov     [rbp+40h+var_98], rax
0x18007212e  lea     rcx, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x180072135  mov     qword ptr [rbp+40h+var_A8], rcx
0x180072139  lea     rax, [rsi+168h]
0x180072140  mov     qword ptr [rbp+40h+var_A8+8], rax
0x180072144  xor     eax, eax
0x180072146  movups  [rbp+40h+var_C0], xmm0
0x18007214a  mov     [rbp+40h+var_B0], rax
0x18007214e  mov     qword ptr [rbp+40h+var_C0], rcx
0x180072152  lea     rax, [rsi+1A0h]
0x180072159  mov     qword ptr [rbp+40h+var_C0+8], rax
0x18007215d  xor     eax, eax
0x18007215f  movups  [rsp+140h+var_F8], xmm0
0x180072164  mov     [rsp+140h+var_E8], rax
0x180072169  mov     qword ptr [rsp+140h+var_F8], rcx
0x18007216e  lea     r12, [rsi+1D8h]
0x180072175  mov     qword ptr [rsp+140h+var_F8+8], r12
0x18007217a  movups  [rsp+140h+var_110], xmm0
0x18007217f  mov     [rsp+140h+var_100], rax
0x180072184  mov     qword ptr [rsp+140h+var_110], rcx
0x180072189  lea     r15, [rsi+0C0h]
0x180072190  mov     qword ptr [rsp+140h+var_110+8], r15
0x180072195  mov     [rsp+140h+var_D0], rdi
0x18007219a  mov     r13d, edi
0x18007219d  mov     [rsp+140h+lpMem], rdi
0x1800721a2  mov     ebx, edi
0x1800721a4  mov     [rbp+40h+arg_0], rbx
0x1800721a8  mov     [rsp+140h+var_E0], rdi
0x1800721ad  mov     [rbp+40h+arg_10], rdi
0x1800721b1  mov     [rbp+40h+arg_8], rdi
0x1800721b5  mov     [rbp+40h+arg_18], rdi
0x1800721b9  mov     r14, [rsi+298h]
0x1800721c0  test    r14, r14
0x1800721c3  jnz     short loc_1800721FE
0x1800721c5  xor     edi, edi
0x1800721c7  mov     rax, [rsi+50h]
0x1800721cb  lea     rcx, [rsi+50h]
0x1800721cf  mov     rax, [rax+10h]
0x1800721d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800721d8  test    rax, rax
0x1800721db  jz      loc_180072784
0x1800721e1  mov     rax, [rsi+50h]
0x1800721e5  lea     rcx, [rsi+50h]
0x1800721e9  mov     rax, [rax+10h]
0x1800721ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800721f2  xor     ecx, ecx
0x1800721f4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800721f9  jmp     loc_180072784
0x1800721fe  test    byte ptr [rsi+358h], 2
0x180072205  jnz     short loc_1800721C5
0x180072207  mov     rbx, rdi
0x18007220a  mov     [rsp+140h+var_D8], rbx
0x18007220f  lea     rcx, [r14+88h]
0x180072216  call    cs:__imp_UnattendCtxCleanup
0x18007221c  mov     edi, eax
0x18007221e  mov     ecx, 80000000h
0x180072223  add     eax, ecx
0x180072225  test    ecx, eax
0x180072227  jnz     short loc_180072235
0x180072229  cmp     edi, 80070057h
0x18007222f  jz      short loc_180072235
0x180072231  mov     ecx, edi
0x180072233  jmp     short loc_18007228A
0x180072235  xor     eax, eax
0x180072237  mov     [r14+88h], rax
0x18007223e  lea     r8, aWindlp; "WINDLP"
0x180072245  mov     r9, r8
0x180072248  lea     rdx, qword_18009B400; unsigned __int16 *
0x18007224f  lea     rcx, [rsp+140h+var_D8]; unsigned __int16 **
0x180072254  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x180072259  mov     edi, eax
0x18007225b  test    eax, eax
0x18007225d  jns     short loc_18007226D
0x18007225f  mov     ecx, eax
0x180072261  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180072266  mov     rbx, [rsp+140h+var_D8]
0x18007226b  jmp     short loc_18007228F
0x18007226d  mov     rbx, [rsp+140h+var_D8]
0x180072272  mov     rdx, rbx
0x180072275  lea     rcx, [r14+88h]
0x18007227c  call    cs:__imp_UnattendCtxDeserializeString
0x180072282  mov     edi, eax
0x180072284  test    eax, eax
0x180072286  jns     short loc_18007228F
0x180072288  mov     ecx, eax
0x18007228a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18007228f  mov     ecx, edi
0x180072291  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180072296  test    rbx, rbx
0x180072299  jz      short loc_1800722B7
0x18007229b  call    cs:__imp_GetProcessHeap
0x1800722a1  mov     rcx, rax; hHeap
0x1800722a4  lea     r8, [rbx-4]; lpMem
0x1800722a8  xor     edx, edx; dwFlags
0x1800722aa  call    cs:__imp_HeapFree
0x1800722b0  xor     ecx, ecx
0x1800722b2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800722b7  test    edi, edi
0x1800722b9  jns     short loc_180072329
0x1800722bb  mov     rax, [rsi+50h]
0x1800722bf  lea     rcx, [rsi+50h]
0x1800722c3  mov     rax, [rax+10h]
0x1800722c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800722cc  test    rax, rax
0x1800722cf  jz      short loc_180072320
0x1800722d1  mov     rax, [rsi+50h]
0x1800722d5  lea     rcx, [rsi+50h]
0x1800722d9  mov     rax, [rax+10h]
0x1800722dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800722e2  xor     ecx, ecx
0x1800722e4  test    rax, rax
0x1800722e7  jz      short loc_18007231B
0x1800722e9  mov     [rsp+140h+var_118], edi
0x1800722ed  mov     [rsp+140h+var_120], 0A18h
0x1800722f5  lea     r9, aCdlpmanagerSer; "CDlpManager::SerializeSynchronous"
0x1800722fc  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180072303  mov     edx, 4
0x180072308  mov     rcx, rax
0x18007230b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180072310  test    eax, eax
0x180072312  mov     ecx, eax
0x180072314  jns     short loc_18007231B
0x180072316  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18007231b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180072320  mov     rbx, [rbp+40h+arg_0]
0x180072324  jmp     loc_180072784
0x180072329  lea     rbx, [rsi+90h]
0x180072330  mov     rcx, rbx; lpCriticalSection
0x180072333  call    cs:__imp_EnterCriticalSection
0x180072339  mov     r14d, 1
0x18007233f  mov     [rbp+40h+var_58], r14d
0x180072343  mov     edi, [rsi+80h]
0x180072349  xor     ecx, ecx
0x18007234b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180072350  mov     eax, [rbp+40h+var_58]
0x180072353  test    eax, eax
0x180072355  jz      short loc_180072367
0x180072357  mov     rcx, rbx; lpCriticalSection
0x18007235a  call    cs:__imp_LeaveCriticalSection
0x180072360  mov     [rbp+40h+var_58], 0
0x180072367  mov     rcx, [rsi+298h]
0x18007236e  add     rcx, 8
0x180072372  mov     rax, [rcx]
0x180072375  mov     r8d, edi
0x180072378  lea     rdx, aState; "State"
0x18007237f  mov     rax, [rax+18h]
0x180072383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072388  mov     edi, eax
0x18007238a  test    eax, eax
0x18007238c  jns     short loc_1800723D5
0x18007238e  mov     rdx, [rsi+50h]
0x180072392  lea     rcx, [rsi+50h]
0x180072396  mov     rax, [rdx+10h]
0x18007239a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007239f  test    rax, rax
0x1800723a2  jz      loc_180072320
0x1800723a8  mov     rax, [rsi+50h]
0x1800723ac  lea     rcx, [rsi+50h]
0x1800723b0  mov     rax, [rax+10h]
0x1800723b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800723b9  xor     ecx, ecx
0x1800723bb  test    rax, rax
0x1800723be  jz      loc_18007231B
0x1800723c4  mov     [rsp+140h+var_118], edi
0x1800723c8  mov     [rsp+140h+var_120], 0A21h
0x1800723d0  jmp     loc_1800722F5
0x1800723d5  mov     rcx, [rsi+298h]
0x1800723dc  add     rcx, 8
0x1800723e0  mov     rax, [rcx]
0x1800723e3  mov     r8d, [rsi+214h]
0x1800723ea  lea     rdx, aTaskcount; "TaskCount"
0x1800723f1  mov     rax, [rax+18h]
0x1800723f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800723fa  mov     edi, eax
0x1800723fc  test    eax, eax
0x1800723fe  jns     short loc_180072447
0x180072400  mov     rax, [rsi+50h]
0x180072404  lea     rcx, [rsi+50h]
0x180072408  mov     rax, [rax+10h]
0x18007240c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072411  test    rax, rax
0x180072414  jz      loc_180072320
0x18007241a  mov     rax, [rsi+50h]
0x18007241e  lea     rcx, [rsi+50h]
0x180072422  mov     rax, [rax+10h]
0x180072426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007242b  xor     ecx, ecx
0x18007242d  test    rax, rax
0x180072430  jz      loc_18007231B
0x180072436  mov     [rsp+140h+var_118], edi
0x18007243a  mov     [rsp+140h+var_120], 0A24h
0x180072442  jmp     loc_1800722F5
0x180072447  mov     rcx, [rsi+298h]
0x18007244e  add     rcx, 8
0x180072452  mov     rax, [rcx]
0x180072455  mov     r8, [rsi+78h]
0x180072459  lea     rdx, aWorkingpath; "WorkingPath"
0x180072460  mov     rax, [rax+28h]
0x180072464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072469  mov     edi, eax
0x18007246b  test    eax, eax
0x18007246d  jns     short loc_1800724B6
0x18007246f  mov     rax, [rsi+50h]
0x180072473  lea     rcx, [rsi+50h]
0x180072477  mov     rax, [rax+10h]
0x18007247b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072480  test    rax, rax
0x180072483  jz      loc_180072320
0x180072489  mov     rax, [rsi+50h]
0x18007248d  lea     rcx, [rsi+50h]
0x180072491  mov     rax, [rax+10h]
0x180072495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007249a  xor     ecx, ecx
0x18007249c  test    rax, rax
0x18007249f  jz      loc_18007231B
0x1800724a5  mov     [rsp+140h+var_118], edi
0x1800724a9  mov     [rsp+140h+var_120], 0A27h
0x1800724b1  jmp     loc_1800722F5
0x1800724b6  lea     r15, [r12+8]
0x1800724bb  mov     rcx, r15; lpCriticalSection
0x1800724be  call    cs:__imp_EnterCriticalSection
0x1800724c4  mov     dword ptr [rsp+140h+var_E8], r14d
0x1800724c9  mov     ebx, [rsi+224h]
0x1800724cf  mov     rcx, [rsi+298h]
0x1800724d6  add     rcx, 8
0x1800724da  mov     rax, [rcx]
0x1800724dd  mov     r8d, ebx
0x1800724e0  lea     rdx, aStringcount; "StringCount"
0x1800724e7  mov     rax, [rax+18h]
0x1800724eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800724f0  mov     edi, eax
0x1800724f2  test    eax, eax
0x1800724f4  jns     short loc_180072564
0x1800724f6  mov     rax, [rsi+50h]
0x1800724fa  lea     rcx, [rsi+50h]
0x1800724fe  mov     rax, [rax+10h]
0x180072502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072507  test    rax, rax
0x18007250a  jz      short loc_18007255B
0x18007250c  mov     rax, [rsi+50h]
0x180072510  lea     rcx, [rsi+50h]
0x180072514  mov     rax, [rax+10h]
0x180072518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007251d  xor     ecx, ecx
0x18007251f  test    rax, rax
0x180072522  jz      short loc_180072556
0x180072524  mov     [rsp+140h+var_118], edi
0x180072528  mov     [rsp+140h+var_120], 0A2Eh
0x180072530  lea     r9, aCdlpmanagerSer; "CDlpManager::SerializeSynchronous"
0x180072537  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18007253e  mov     edx, 4
0x180072543  mov     rcx, rax
0x180072546  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18007254b  test    eax, eax
0x18007254d  mov     ecx, eax
0x18007254f  jns     short loc_180072556
0x180072551  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180072556  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007255b  mov     rbx, [rbp+40h+arg_0]
0x18007255f  jmp     loc_18007277F
0x180072564  cmp     [rsi+234h], ebx
0x18007256a  jz      short loc_1800725AF
0x18007256c  mov     ebx, 8000FFFFh
0x180072571  mov     edi, ebx
0x180072573  mov     rax, [rsi+50h]
0x180072577  lea     rcx, [rsi+50h]
0x18007257b  mov     rax, [rax+10h]
0x18007257f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072584  test    rax, rax
0x180072587  jz      short loc_18007255B
0x180072589  mov     rax, [rsi+50h]
  ... truncated ...
```
