# WdcTraceControl::CallbackEvent(_EVENT_RECORD *)

- ea: `0x18000a4d0`
- end: `0x18000afeb`
- name: `?CallbackEvent@WdcTraceControl@@CAXPEAU_EVENT_RECORD@@@Z`
- size: `2843`
- prototype: `void __fastcall(struct _EVENT_RECORD *)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, service_task`

## callees

- `0x1800056ec`
- `0x180005964`
- `0x180005ff0`
- `0x1800065f0`
- `0x1800081e0`
- `0x1800085f0`
- `0x180008ab0`
- `0x180008b10`
- `0x18000a4d0`
- `0x18000b854`
- `0x18000e400`
- `0x1800102d0`
- `0x1800137d0`
- `0x1800138e0`
- `0x1800158c0`
- `0x1800168b0`
- `0x180017460`
- `0x1800193a0`
- `0x18001efac`
- `0x18003a920`
- `0x18003a988`
- `0x18003b0ac`
- `0x180086010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18000ae98`
- `KERNEL32!GetCurrentProcessId` at `0x18000ae98`
- `KERNEL32!LeaveCriticalSection` at `0x18000a7f3`
- `KERNEL32!LeaveCriticalSection` at `0x18000ac79`
- `KERNEL32!LeaveCriticalSection` at `0x18000adab`
- `KERNEL32!LeaveCriticalSection` at `0x18000a7f3`
- `KERNEL32!LeaveCriticalSection` at `0x18000ac79`
- `KERNEL32!LeaveCriticalSection` at `0x18000adab`
- `KERNEL32!EnterCriticalSection` at `0x18000a5c6`
- `KERNEL32!EnterCriticalSection` at `0x18000a9f1`
- `KERNEL32!EnterCriticalSection` at `0x18000acfa`
- `KERNEL32!EnterCriticalSection` at `0x18000a5c6`
- `KERNEL32!EnterCriticalSection` at `0x18000a9f1`
- `KERNEL32!EnterCriticalSection` at `0x18000acfa`
- `KERNEL32!TlsGetValue` at `0x18000a507`
- `KERNEL32!TlsGetValue` at `0x18000a507`

## string_xrefs

- `0x18000a7dc`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x18000ad94`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x18000af0a`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x18000af50`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x18000ac9e`: `WdcDiskMonitor::EventFileCreate`
- `0x18000afcf`: `WdcDiskMonitor::CreateEntry`
- `0x18000adc2`: `WdcServiceMonitor::EventThreadPool`
- `0x18000af6d`: `WdcThreadStat::CheckIn`
- `0x18000af22`: `WdcThreadStat::CheckOut`

## pseudocode

```c
void __fastcall WdcTraceControl::CallbackEvent(struct _EVENT_RECORD *a1)
{
  WdcDiskMonitor **Value; // rax
  WdcDiskMonitor **v3; // rbx
  __int64 v4; // rcx
  WdcDiskMonitor *v5; // rbp
  _QWORD *UserData; // r8
  __int64 v7; // r14
  __int64 v8; // r15
  int v9; // r12d
  ULONG v10; // r9d
  unsigned int v11; // r10d
  ULONG v12; // r13d
  __int64 v13; // rdi
  __int64 v14; // r8
  __int64 *v15; // rcx
  __int64 *j; // rdi
  __int64 *v17; // rax
  __int64 v18; // r13
  __int64 v19; // r14
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // eax
  __int64 **v27; // rdx
  __int64 *v28; // rax
  int v29; // esi
  WdcDiskMonitor *v30; // r8
  unsigned int v31; // ebx
  const char *v32; // rdx
  __int16 v33; // cx
  unsigned __int64 v34; // r15
  __int64 v35; // rax
  bool v36; // zf
  unsigned __int16 *v37; // rax
  int v38; // ecx
  unsigned __int16 v39; // ax
  unsigned int v40; // r13d
  unsigned int v41; // ebp
  int v42; // edi
  char *v43; // r14
  char *k; // rdi
  char *v45; // rax
  void **v46; // rcx
  char *v47; // rax
  int v48; // eax
  int v49; // eax
  int v50; // esi
  WdcDiskMonitor *v51; // rcx
  char *v52; // rax
  __int64 v53; // rcx
  char *v54; // rax
  _QWORD *v55; // rdi
  __int64 v56; // rcx
  _QWORD *v57; // rax
  _DWORD *v58; // rax
  __int64 v59; // r15
  ULONG KernelTime; // eax
  unsigned __int64 ThreadId; // rsi
  unsigned int v62; // eax
  int v63; // ebp
  char *v64; // rdx
  char *i; // rax
  char *v66; // rcx
  char **v67; // r8
  char *v68; // rcx
  __int64 *v69; // rax
  _QWORD *v70; // r10
  __int64 v71; // rcx
  __int64 v72; // r14
  int v73; // eax
  char *v74; // rax
  __int64 v75; // [rsp+20h] [rbp-58h]
  unsigned __int16 *v76; // [rsp+30h] [rbp-48h]
  ULONG v77; // [rsp+88h] [rbp+10h]
  int v78; // [rsp+88h] [rbp+10h]
  ULONG UserTime; // [rsp+88h] [rbp+10h]
  unsigned int v80; // [rsp+90h] [rbp+18h]
  WdcDiskMonitor *v81; // [rsp+90h] [rbp+18h]
  ULONG v82; // [rsp+90h] [rbp+18h]
  _DWORD *v83; // [rsp+98h] [rbp+20h]
  unsigned int v84; // [rsp+98h] [rbp+20h]

  if ( dword_1800B5A9C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800B5A9C);
    if ( dword_1800B5A9C == -1 )
    {
      dword_1800B5AA0 = GetCurrentProcessId();
      Init_thread_footer(&dword_1800B5A9C);
    }
  }
  Value = (WdcDiskMonitor **)TlsGetValue(g_tls);
  v3 = Value;
  if ( !*((_DWORD *)Value + 14) )
    return;
  v4 = *(_QWORD *)&a1->EventHeader.ProviderId.Data1 - *(_QWORD *)&ThreadPoolGuid.Data1;
  if ( !v4 )
    v4 = *(_QWORD *)a1->EventHeader.ProviderId.Data4 - *(_QWORD *)ThreadPoolGuid.Data4;
  if ( !v4 )
  {
    v5 = Value[20];
    UserData = a1->UserData;
    if ( a1->EventHeader.EventDescriptor.Opcode == 34 )
    {
      if ( (a1->EventHeader.Flags & 0x40) != 0 )
      {
        v18 = UserData[1];
        v19 = UserData[4];
      }
      else
      {
        LODWORD(v18) = *((_DWORD *)UserData + 1);
        v19 = *((unsigned int *)UserData + 4);
      }
      if ( v19 )
      {
        v59 = *((_QWORD *)v5 + 1168);
        UserTime = a1->EventHeader.UserTime;
        KernelTime = a1->EventHeader.KernelTime;
        ThreadId = a1->EventHeader.ThreadId;
        v82 = KernelTime;
        v62 = *((_DWORD *)v5 + 2355);
        v63 = 0;
        v84 = v62;
        if ( *(_DWORD *)(v59 + 48) )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v59 + 8));
          v63 = 1;
        }
        v64 = (char *)(v59
                     + 16LL
                     * (((69069 * (_DWORD)ThreadId + 1) & 0xFFFF0000
                       | ((unsigned int)(1103515245 * ThreadId + 12345) >> 16))
                      % 0x1F7)
                     + 104);
        for ( i = *(char **)v64; i != v64; i = *(char **)i )
        {
          v66 = *(char **)i;
          if ( *((_QWORD *)i + 6) == ThreadId )
          {
            if ( *((char **)v66 + 1) == i )
            {
              v67 = (char **)*((_QWORD *)i + 1);
              if ( *v67 == i )
              {
                *v67 = v66;
                *((_QWORD *)v66 + 1) = v67;
                v68 = *(char **)v64;
                if ( *(char **)(*(_QWORD *)v64 + 8LL) == v64 )
                {
                  *(_QWORD *)i = v68;
                  *((_QWORD *)i + 1) = v64;
                  *((_QWORD *)v68 + 1) = i;
                  *(_QWORD *)v64 = i;
                  goto LABEL_126;
                }
              }
            }
LABEL_59:
            __fastfail(3u);
          }
        }
        v74 = (char *)WdcAlloc(0x70u, v64, (int)UserData);
        if ( v74 )
        {
          *((_QWORD *)v74 + 7) = 112;
          *(_OWORD *)(v74 + 66) = 0;
          *((_QWORD *)v74 + 10) = 0;
          *((_DWORD *)v74 + 25) = 0;
          *((_QWORD *)v74 + 1) = v74;
          *(_QWORD *)v74 = v74;
          *((_QWORD *)v74 + 3) = v74 + 16;
          *((_QWORD *)v74 + 2) = v74 + 16;
          *((_QWORD *)v74 + 5) = v74 + 32;
          *((_QWORD *)v74 + 4) = v74 + 32;
          *((_WORD *)v74 + 32) = 1;
          *((_QWORD *)v74 + 13) = v84 * (unsigned __int64)(v82 + UserTime);
          *((_QWORD *)v74 + 6) = ThreadId;
          *((_DWORD *)v74 + 22) = ThreadId;
          *((_DWORD *)v74 + 23) = v19;
          *((_DWORD *)v74 + 24) = v18;
          v69 = (__int64 *)(v59 + 16LL * (unsigned int)WdcHashKey(ThreadId) + 104);
          v71 = *v69;
          if ( *(__int64 **)(*v69 + 8) != v69 )
            goto LABEL_59;
          *v70 = v71;
          v70[1] = v69;
          *(_QWORD *)(v71 + 8) = v70;
          *v69 = (__int64)v70;
LABEL_126:
          v29 = 0;
        }
        else
        {
          v29 = -2147024882;
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
            "WdcThreadStat::CheckIn",
            0,
            L"FAILURE: 0x%08x",
            -2147024882);
        }
        if ( *(_DWORD *)(v59 + 48) && v63 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v59 + 8));
        if ( v29 < 0 )
          goto LABEL_131;
      }
    }
    else if ( a1->EventHeader.EventDescriptor.Opcode == 35 )
    {
      if ( (a1->EventHeader.Flags & 0x40) != 0 )
        v7 = *UserData;
      else
        LODWORD(v7) = *(_DWORD *)UserData;
      v8 = *((_QWORD *)v5 + 1168);
      v9 = 0;
      v10 = a1->EventHeader.KernelTime;
      v11 = *((_DWORD *)v5 + 2355);
      v12 = a1->EventHeader.UserTime;
      v13 = a1->EventHeader.ThreadId;
      v77 = v10;
      v80 = v11;
      if ( *(_DWORD *)(v8 + 48) )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
        v10 = v77;
        v9 = 1;
        v11 = v80;
      }
      v14 = v13;
      v15 = (__int64 *)(v8
                      + 16LL
                      * (((69069 * (_DWORD)v13 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v13 + 12345) >> 16))
                       % 0x1F7)
                      + 104);
      for ( j = (__int64 *)*v15; ; j = (__int64 *)*j )
      {
        if ( j == v15 )
        {
          v29 = 0;
          goto LABEL_46;
        }
        v17 = (__int64 *)*j;
        if ( j[6] == v14 )
          break;
      }
      if ( (__int64 *)v17[1] != j )
        goto LABEL_59;
      v27 = (__int64 **)j[1];
      if ( *v27 != j )
        goto LABEL_59;
      *v27 = v17;
      v17[1] = (__int64)v27;
      v28 = (__int64 *)*v15;
      if ( *(__int64 **)(*v15 + 8) != v15 )
        goto LABEL_59;
      *j = (__int64)v28;
      v29 = 0;
      j[1] = (__int64)v15;
      v28[1] = (__int64)j;
      *v15 = (__int64)j;
      if ( (_DWORD)v7 == *((_DWORD *)j + 24) )
      {
        v72 = 0;
        if ( (__int64)(v11 * (unsigned __int64)(v10 + v12) - j[13]) >= 0 )
          v72 = v11 * (unsigned __int64)(v10 + v12) - j[13];
        v73 = WdcServiceMonitor::ChargeService(v5, *((_DWORD *)j + 23), v72);
        v29 = v73;
        if ( v73 < 0
          || (j[13] += v72,
              *((_DWORD *)j + 17) |= 0x10000000u,
              v73 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v8 + 16LL))(
                      v8,
                      j,
                      *((unsigned int *)j + 14)),
              v29 = v73,
              v73 < 0) )
        {
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
            "WdcThreadStat::CheckOut",
            0,
            L"FAILURE: 0x%08x",
            v73);
        }
      }
LABEL_46:
      if ( *(_DWORD *)(v8 + 48) )
      {
        if ( v9 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
      }
      if ( v29 < 0 )
      {
LABEL_131:
        LODWORD(v75) = v29;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
          "WdcServiceMonitor::EventThreadPool",
          0,
          L"FAILURE: 0x%08x",
          v75);
        LODWORD(v75) = v29;
        goto LABEL_58;
      }
    }
    return;
  }
  v20 = *(_QWORD *)&a1->EventHeader.ProviderId.Data1 - *(_QWORD *)&FileProvGuid.Data1;
  if ( !v20 )
    v20 = *(_QWORD *)a1->EventHeader.ProviderId.Data4 - *(_QWORD *)FileProvGuid.Data4;
  if ( v20 )
  {
    v21 = *(_QWORD *)&a1->EventHeader.ProviderId.Data1 - FileIoGuid;
    if ( !v21 )
      v21 = *(_QWORD *)a1->EventHeader.ProviderId.Data4 + 0x1C9BFB07FFFF0B7CLL;
    if ( v21 )
    {
      v22 = *(_QWORD *)&a1->EventHeader.ProviderId.Data1 - *(_QWORD *)&DiskProvGuid.Data1;
      if ( !v22 )
        v22 = *(_QWORD *)a1->EventHeader.ProviderId.Data4 - *(_QWORD *)DiskProvGuid.Data4;
      if ( v22 )
      {
        v23 = *(_QWORD *)&a1->EventHeader.ProviderId.Data1 - *(_QWORD *)&WdcRundownProvGuid.Data1;
        if ( !v23 )
          v23 = *(_QWORD *)a1->EventHeader.ProviderId.Data4 - *(_QWORD *)WdcRundownProvGuid.Data4;
        if ( v23 || a1->EventHeader.ProcessId != dword_1800B5AA0 )
        {
          v24 = *(_QWORD *)&a1->EventHeader.ProviderId.Data1 - *(_QWORD *)&PsProvGuid.Data1;
          if ( !v24 )
            v24 = *(_QWORD *)a1->EventHeader.ProviderId.Data4 - *(_QWORD *)PsProvGuid.Data4;
          if ( v24 )
          {
            v25 = *(_QWORD *)&a1->EventHeader.ProviderId.Data1 - *(_QWORD *)&NetProvGuid.Data1;
            if ( !v25 )
              v25 = *(_QWORD *)a1->EventHeader.ProviderId.Data4 - *(_QWORD *)NetProvGuid.Data4;
            if ( v25 )
              return;
            v26 = WdcNetworkMonitor::EventNetIO(v3[24], a1);
            if ( v26 >= 0 )
            {
              v26 = WdcProcessNetworkMonitor::EventNetIO(v3[25], a1);
              if ( v26 >= 0 )
                return;
            }
          }
          else
          {
            v26 = WdcServiceMonitor::EventThread(v3[20], a1);
            if ( v26 >= 0 )
              return;
          }
        }
        else
        {
          v26 = WdcServiceMonitor::EventRundown(v3[20], a1);
          if ( v26 >= 0 )
          {
            v26 = WdcDiskMonitor::EventRundown(v3[16], a1);
            if ( v26 >= 0 )
            {
              v26 = WdcProcessDiskMonitor::EventRundown(v3[17], a1);
              if ( v26 >= 0 )
              {
                v26 = WdcNetworkMonitor::EventRundown(v3[24], a1);
                if ( v26 >= 0 )
                {
                  v26 = WdcProcessNetworkMonitor::EventRundown(v3[25], a1);
                  if ( v26 >= 0 )
                    return;
                }
              }
            }
          }
        }
      }
      else
      {
        v26 = WdcDiskMonitor::EventDisk(v3[16], a1);
        if ( v26 >= 0 )
        {
          v26 = WdcProcessDiskMonitor::EventDisk(v3[17], a1);
          if ( v26 >= 0 )
            return;
        }
      }
      goto LABEL_57;
    }
    if ( a1->EventHeader.EventDescriptor.Opcode != 36 )
      return;
    v30 = v3[16];
    v31 = 0;
    v32 = (const char *)a1->UserData;
    v81 = v30;
    v78 = 0;
    v33 = a1->EventHeader.Flags & 0x40;
    if ( v33 )
      v34 = *(_QWORD *)v32;
    else
      v34 = *(unsigned int *)v32;
    v35 = 8;
    if ( !v33 )
      v35 = 4;
    v36 = &v32[v35] == 0;
    v37 = (unsigned __int16 *)&v32[v35];
    v76 = v37;
    if ( v36 )
    {
      v40 = 0;
    }
    else
    {
      v32 = (const char *)v37;
      v38 = 0;
      v39 = *v37;
      if ( v39 )
      {
        do
        {
          v32 += 2;
          v38 = v39 + 37 * v38;
          v39 = *(_WORD *)v32;
        }
        while ( *(_WORD *)v32 );
      }
      v40 = 314159269 * v38 % 0x3B9ACA07u;
    }
    if ( !v34 )
    {
      v50 = 0;
      v58 = (_DWORD *)((char *)v30 + 48);
LABEL_108:
      if ( v78 && *v58 )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v30 + 8));
      if ( v50 >= 0 )
        return;
      LODWORD(v75) = v50;
LABEL_58:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\control.cpp",
        "WdcTraceControl::CallbackEvent",
        0,
        L"FAILURE: 0x%08x",
        v75);
      return;
    }
    v41 = ((unsigned int)(1103515245 * HIDWORD(v34) + 12345) >> 16) | (69069 * HIDWORD(v34) + 1) & 0xFFFF0000;
    v42 = ((unsigned int)(1103515245 * v34 + 12345) >> 16) | (69069 * v34 + 1) & 0xFFFF0000;
    LODWORD(v32) = (2185907809u * (unsigned __int64)(v42 + v41)) >> 32;
    v83 = (_DWORD *)((char *)v30 + 48);
    if ( *((_DWORD *)v30 + 12) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v30 + 8));
      v30 = v81;
      v78 = 1;
    }
    v43 = (char *)v30 + 16 * (int)(v41 + v42 - 503 * ((v42 + v41) / 0x1F7)) + 104;
    for ( k = *(char **)v43; ; k = *(char **)k )
    {
      if ( k == v43 )
        goto LABEL_98;
      v45 = *(char **)k;
      if ( *((_QWORD *)k + 6) == v34 )
        break;
    }
    if ( *((char **)v45 + 1) != k )
      goto LABEL_59;
    v46 = (void **)*((_QWORD *)k + 1);
    if ( *v46 != k )
      goto LABEL_59;
    *v46 = v45;
    *((_QWORD *)v45 + 1) = v46;
    v47 = *(char **)v43;
    if ( *(char **)(*(_QWORD *)v43 + 8LL) != v43 )
      goto LABEL_59;
    *(_QWORD *)k = v47;
    *((_QWORD *)k + 1) = v43;
    *((_QWORD *)v47 + 1) = k;
    *(_QWORD *)v43 = k;
    v48 = *((_DWORD *)k + 130);
    if ( v48 )
    {
      if ( v40 == v48 )
      {
        v50 = 0;
LABEL_107:
        v58 = v83;
        goto LABEL_108;
      }
      v49 = WdcDiskMonitor::DeleteFileObject(v30, v34);
      v50 = v49;
      if ( v49 < 0 )
      {
LABEL_113:
        LODWORD(v75) = v49;
LABEL_114:
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\disk.cpp",
          "WdcDiskMonitor::EventFileCreate",
          0,
          L"FAILURE: 0x%08x",
          v75);
        goto LABEL_115;
      }
LABEL_98:
      v52 = (char *)WdcAlloc(0x210u, v32, (int)v30);
      k = v52;
      if ( !v52 )
      {
        v50 = -2147024882;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\disk.cpp",
          "WdcDiskMonitor::CreateEntry",
          0,
          L"FAILURE: 0x%08x",
          -2147024882);
        LODWORD(v75) = -2147024882;
        goto LABEL_114;
      }
      memset_0(v52, 0, 0x210u);
      *((_DWORD *)k + 14) = 528;
      *((_QWORD *)k + 1) = k;
      *(_QWORD *)k = k;
      *((_QWORD *)k + 3) = k + 16;
      *((_QWORD *)k + 2) = k + 16;
      *((_QWORD *)k + 5) = k + 32;
      *((_QWORD *)k + 4) = k + 32;
      *((_QWORD *)k + 10) = k + 88;
      *((_DWORD *)k + 22) = 0x10000000;
      *((_DWORD *)k + 16) = 524289;
      *((_DWORD *)k + 17) = 536870913;
      *((_DWORD *)k + 26) = 553648128;
      *((_DWORD *)k + 30) = 0x10000000;
      *((_DWORD *)k + 34) = 0x20000000;
      *((_DWORD *)k + 38) = 0x20000000;
      *((_DWORD *)k + 42) = 587202560;
      *((_DWORD *)k + 46) = 0x20000000;
      *((_DWORD *)k + 50) = 0x20000000;
      do
      {
        v53 = v31++;
        *(_DWORD *)(16 * v53 + *((_QWORD *)k + 10)) |= 3u;
      }
      while ( v31 < *((unsigned __int16 *)k + 33) );
      *((_QWORD *)k + 6) = v34;
      v54 = *(char **)v43;
      if ( *(char **)(*(_QWORD *)v43 + 8LL) != v43 )
        goto LABEL_59;
      *(_QWORD *)k = v54;
      *((_QWORD *)k + 1) = v43;
      *((_QWORD *)v54 + 1) = k;
      *(_QWORD *)v43 = k;
    }
    else if ( (*((_DWORD *)k + 17) & 0x10000000) != 0 && a1->EventHeader.EventDescriptor.Opcode == 36 )
    {
      v49 = WdcDiskMonitor::DeleteFileObject(v30, v34);
      v50 = v49;
      if ( v49 >= 0 )
      {
        v50 = 0;
LABEL_115:
        v30 = v81;
        goto LABEL_107;
      }
      goto LABEL_113;
    }
    *((_DWORD *)k + 130) = v40;
    v49 = WdcDiskMonitor::SetFileName(v81, (struct _WDC_FILE_INFO *)k, v76);
    v50 = v49;
    if ( v49 >= 0 )
    {
      *((_DWORD *)k + 30) |= 1u;
      v55 = k + 16;
      if ( (_QWORD *)*v55 != v55 )
        goto LABEL_115;
      v30 = v81;
      v56 = *((_QWORD *)v81 + 11);
      v57 = (_QWORD *)((char *)v81 + 88);
      if ( *(WdcDiskMonitor **)(v56 + 8) != (WdcDiskMonitor *)((char *)v81 + 88) )
        goto LABEL_59;
      *v55 = v56;
      v55[1] = v57;
      *(_QWORD *)(v56 + 8) = v55;
      *v57 = v55;
      goto LABEL_107;
    }
    goto LABEL_113;
  }
  v51 = v3[16];
  if ( a1->EventHeader.EventDescriptor.Id == 10 )
  {
    v26 = WdcDiskMonitor::EventFileCreate(v51, a1);
  }
  else
  {
    if ( a1->EventHeader.EventDescriptor.Id != 11 )
      return;
    v26 = WdcDiskMonitor::EventFileDelete(v51, a1);
  }
  if ( v26 < 0 )
  {
LABEL_57:
    LODWORD(v75) = v26;
    goto LABEL_58;
  }
}

```

## disassembly

```asm
0x18000a4d0  push    rbx
0x18000a4d2  push    rsi
0x18000a4d3  sub     rsp, 68h
0x18000a4d7  mov     edx, cs:_tls_index
0x18000a4dd  mov     rsi, rcx
0x18000a4e0  mov     rax, gs:58h
0x18000a4e9  mov     ecx, 4
0x18000a4ee  mov     rax, [rax+rdx*8]
0x18000a4f2  mov     eax, [rcx+rax]
0x18000a4f5  cmp     cs:dword_1800B5A9C, eax
0x18000a4fb  jg      loc_18000AE7F
0x18000a501  mov     ecx, cs:?g_tls@@3KA; dwTlsIndex
0x18000a507  call    cs:__imp_TlsGetValue
0x18000a50d  mov     rbx, rax
0x18000a510  mov     ecx, [rax+38h]
0x18000a513  test    ecx, ecx
0x18000a515  jz      loc_18000A67D
0x18000a51b  mov     rcx, [rsi+18h]
0x18000a51f  sub     rcx, qword ptr cs:ThreadPoolGuid.Data1
0x18000a526  jnz     short loc_18000A533
0x18000a528  mov     rcx, [rsi+20h]
0x18000a52c  sub     rcx, qword ptr cs:ThreadPoolGuid.Data4
0x18000a533  mov     [rsp+78h+arg_0], rbp
0x18000a53b  mov     [rsp+78h+var_18], rdi
0x18000a540  mov     [rsp+78h+var_20], r12
0x18000a545  mov     [rsp+78h+var_28], r13
0x18000a54a  mov     [rsp+78h+var_30], r14
0x18000a54f  mov     [rsp+78h+var_38], r15
0x18000a554  test    rcx, rcx
0x18000a557  jnz     loc_18000A684
0x18000a55d  movzx   ecx, byte ptr [rsi+2Dh]
0x18000a561  mov     rbp, [rax+0A0h]
0x18000a568  mov     edx, ecx
0x18000a56a  mov     r8, [rsi+60h]
0x18000a56e  sub     edx, 22h ; '"'
0x18000a571  jz      loc_18000A641
0x18000a577  xor     ebx, ebx
0x18000a579  cmp     edx, 1
0x18000a57c  jnz     loc_18000A77D
0x18000a582  test    byte ptr [rsi+4], 40h
0x18000a586  jz      loc_18000AB1F
0x18000a58c  mov     r14, [r8]
0x18000a58f  mov     r15, [rbp+2480h]
0x18000a596  mov     r12d, ebx
0x18000a599  mov     r9d, [rsi+38h]
0x18000a59d  mov     r10d, [rbp+24CCh]
0x18000a5a4  mov     r13d, [rsi+3Ch]
0x18000a5a8  cmp     dword ptr [r15+30h], 0
0x18000a5ad  mov     edi, [rsi+8]
0x18000a5b0  mov     [rsp+78h+arg_8], r9d
0x18000a5b8  mov     dword ptr [rsp+78h+arg_10], r10d
0x18000a5c0  jz      short loc_18000A5E2
0x18000a5c2  lea     rcx, [r15+8]; lpCriticalSection
0x18000a5c6  call    cs:__imp_EnterCriticalSection
0x18000a5cc  mov     r9d, [rsp+78h+arg_8]
0x18000a5d4  mov     r12d, 1
0x18000a5da  mov     r10d, dword ptr [rsp+78h+arg_10]
0x18000a5e2  imul    ecx, edi, 41C64E6Dh
0x18000a5e8  mov     r8, rdi
0x18000a5eb  imul    eax, edi, 10DCDh
0x18000a5f1  add     ecx, 3039h
0x18000a5f7  shr     ecx, 10h
0x18000a5fa  inc     eax
0x18000a5fc  and     eax, 0FFFF0000h
0x18000a601  or      ecx, eax
0x18000a603  mov     eax, 824A4E61h
0x18000a608  mul     ecx
0x18000a60a  shr     edx, 8
0x18000a60d  imul    eax, edx, 1F7h
0x18000a613  sub     ecx, eax
0x18000a615  movsxd  rcx, ecx
0x18000a618  shl     rcx, 4
0x18000a61c  add     rcx, 68h ; 'h'
0x18000a620  add     rcx, r15
0x18000a623  mov     rdi, [rcx]
0x18000a626  cmp     rdi, rcx
0x18000a629  jz      loc_18000AF33
0x18000a62f  mov     rax, [rdi]
0x18000a632  cmp     [rdi+30h], r8
0x18000a636  jz      loc_18000A797
0x18000a63c  mov     rdi, rax
0x18000a63f  jmp     short loc_18000A626
0x18000a641  test    byte ptr [rsi+4], 40h
0x18000a645  jz      loc_18000AAC4
0x18000a64b  mov     r13, [r8+8]
0x18000a64f  mov     r14, [r8+20h]
0x18000a653  test    r14, r14
0x18000a656  jnz     loc_18000ACBB
0x18000a65c  mov     r14, [rsp+78h+var_30]
0x18000a661  mov     r13, [rsp+78h+var_28]
0x18000a666  mov     r12, [rsp+78h+var_20]
0x18000a66b  mov     rdi, [rsp+78h+var_18]
0x18000a670  mov     rbp, [rsp+78h+arg_0]
0x18000a678  mov     r15, [rsp+78h+var_38]
0x18000a67d  add     rsp, 68h
0x18000a681  pop     rsi
0x18000a682  pop     rbx
0x18000a683  retn
0x18000a684  mov     rax, [rsi+18h]
0x18000a688  sub     rax, qword ptr cs:FileProvGuid.Data1
0x18000a68f  jnz     short loc_18000A69C
0x18000a691  mov     rax, [rsi+20h]
0x18000a695  sub     rax, qword ptr cs:FileProvGuid.Data4
0x18000a69c  test    rax, rax
0x18000a69f  jz      loc_18000AAD1
0x18000a6a5  mov     rax, [rsi+18h]
0x18000a6a9  sub     rax, cs:FileIoGuid
0x18000a6b0  jnz     short loc_18000A6BD
0x18000a6b2  mov     rax, [rsi+20h]
0x18000a6b6  sub     rax, cs:qword_18008D6B8
0x18000a6bd  test    rax, rax
0x18000a6c0  jz      loc_18000A8D1
0x18000a6c6  mov     rax, [rsi+18h]
0x18000a6ca  sub     rax, qword ptr cs:DiskProvGuid.Data1
0x18000a6d1  jnz     short loc_18000A6DE
0x18000a6d3  mov     rax, [rsi+20h]
0x18000a6d7  sub     rax, qword ptr cs:DiskProvGuid.Data4
0x18000a6de  test    rax, rax
0x18000a6e1  jz      loc_18000A8A5
0x18000a6e7  mov     rax, [rsi+18h]
0x18000a6eb  sub     rax, qword ptr cs:WdcRundownProvGuid.Data1
0x18000a6f2  jnz     short loc_18000A6FF
0x18000a6f4  mov     rax, [rsi+20h]
0x18000a6f8  sub     rax, qword ptr cs:WdcRundownProvGuid.Data4
0x18000a6ff  test    rax, rax
0x18000a702  jz      loc_18000A806
0x18000a708  mov     rax, [rsi+18h]
0x18000a70c  sub     rax, qword ptr cs:PsProvGuid.Data1
0x18000a713  jnz     short loc_18000A720
0x18000a715  mov     rax, [rsi+20h]
0x18000a719  sub     rax, qword ptr cs:PsProvGuid.Data4
0x18000a720  test    rax, rax
0x18000a723  jz      loc_18000AB03
0x18000a729  mov     rax, [rsi+18h]
0x18000a72d  sub     rax, qword ptr cs:NetProvGuid.Data1
0x18000a734  jnz     short loc_18000A741
0x18000a736  mov     rax, [rsi+20h]
0x18000a73a  sub     rax, qword ptr cs:NetProvGuid.Data4
0x18000a741  test    rax, rax
0x18000a744  jnz     loc_18000A65C
0x18000a74a  mov     rcx, [rbx+0C0h]; this
0x18000a751  mov     rdx, rsi; struct _EVENT_RECORD *
0x18000a754  call    ?EventNetIO@WdcNetworkMonitor@@QEAAJPEAU_EVENT_RECORD@@@Z; WdcNetworkMonitor::EventNetIO(_EVENT_RECORD *)
0x18000a759  test    eax, eax
0x18000a75b  js      loc_18000A878
0x18000a761  mov     rcx, [rbx+0C8h]; this
0x18000a768  mov     rdx, rsi; struct _EVENT_RECORD *
0x18000a76b  call    ?EventNetIO@WdcProcessNetworkMonitor@@QEAAJPEAU_EVENT_RECORD@@@Z; WdcProcessNetworkMonitor::EventNetIO(_EVENT_RECORD *)
0x18000a770  test    eax, eax
0x18000a772  jns     loc_18000A65C
0x18000a778  jmp     loc_18000A878
0x18000a77d  mov     r14, rbx
0x18000a780  sub     ecx, 22h ; '"'
0x18000a783  jz      loc_18000A65C
0x18000a789  cmp     ecx, 1
0x18000a78c  jnz     loc_18000A65C
0x18000a792  jmp     loc_18000A58F
0x18000a797  cmp     [rax+8], rdi
0x18000a79b  jnz     loc_18000A89E
0x18000a7a1  mov     rdx, [rdi+8]
0x18000a7a5  cmp     [rdx], rdi
0x18000a7a8  jnz     loc_18000A89E
0x18000a7ae  mov     [rdx], rax
0x18000a7b1  mov     [rax+8], rdx
0x18000a7b5  mov     rax, [rcx]
0x18000a7b8  cmp     [rax+8], rcx
0x18000a7bc  jnz     loc_18000A89E
0x18000a7c2  mov     [rdi], rax
0x18000a7c5  mov     esi, ebx
0x18000a7c7  mov     [rdi+8], rcx
0x18000a7cb  mov     [rax+8], rdi
0x18000a7cf  mov     [rcx], rdi
0x18000a7d2  cmp     r14d, [rdi+60h]
0x18000a7d6  jz      loc_18000AEB5
0x18000a7dc  lea     rdi, aBaseDiagnosisP_45; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x18000a7e3  cmp     dword ptr [r15+30h], 0
0x18000a7e8  jz      short loc_18000A7F9
0x18000a7ea  test    r12d, r12d
0x18000a7ed  jz      short loc_18000A7F9
0x18000a7ef  lea     rcx, [r15+8]; lpCriticalSection
0x18000a7f3  call    cs:__imp_LeaveCriticalSection
0x18000a7f9  test    esi, esi
0x18000a7fb  jns     loc_18000A65C
0x18000a801  jmp     loc_18000ADB9
0x18000a806  mov     eax, cs:dword_1800B5AA0
0x18000a80c  cmp     [rsi+0Ch], eax
0x18000a80f  jnz     loc_18000A708
0x18000a815  mov     rcx, [rbx+0A0h]; this
0x18000a81c  mov     rdx, rsi; struct _EVENT_RECORD *
0x18000a81f  call    ?EventRundown@WdcServiceMonitor@@QEAAJPEAU_EVENT_RECORD@@@Z; WdcServiceMonitor::EventRundown(_EVENT_RECORD *)
0x18000a824  test    eax, eax
0x18000a826  js      short loc_18000A878
0x18000a828  mov     rcx, [rbx+80h]; this
0x18000a82f  mov     rdx, rsi; struct _EVENT_RECORD *
0x18000a832  call    ?EventRundown@WdcDiskMonitor@@QEAAJPEAU_EVENT_RECORD@@@Z; WdcDiskMonitor::EventRundown(_EVENT_RECORD *)
0x18000a837  test    eax, eax
0x18000a839  js      short loc_18000A878
0x18000a83b  mov     rcx, [rbx+88h]; this
0x18000a842  mov     rdx, rsi; struct _EVENT_RECORD *
0x18000a845  call    ?EventRundown@WdcProcessDiskMonitor@@QEAAJPEAU_EVENT_RECORD@@@Z; WdcProcessDiskMonitor::EventRundown(_EVENT_RECORD *)
0x18000a84a  test    eax, eax
0x18000a84c  js      short loc_18000A878
0x18000a84e  mov     rcx, [rbx+0C0h]; this
0x18000a855  mov     rdx, rsi; struct _EVENT_RECORD *
0x18000a858  call    ?EventRundown@WdcNetworkMonitor@@QEAAJPEAU_EVENT_RECORD@@@Z; WdcNetworkMonitor::EventRundown(_EVENT_RECORD *)
0x18000a85d  test    eax, eax
0x18000a85f  js      short loc_18000A878
0x18000a861  mov     rcx, [rbx+0C8h]; this
0x18000a868  mov     rdx, rsi; struct _EVENT_RECORD *
0x18000a86b  call    ?EventRundown@WdcProcessNetworkMonitor@@QEAAJPEAU_EVENT_RECORD@@@Z; WdcProcessNetworkMonitor::EventRundown(_EVENT_RECORD *)
0x18000a870  test    eax, eax
0x18000a872  jns     loc_18000A65C
0x18000a878  mov     [rsp+78h+var_58], eax
0x18000a87c  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18000a883  xor     r8d, r8d; int
0x18000a886  lea     rdx, aWdctracecontro_12; "WdcTraceControl::CallbackEvent"
0x18000a88d  lea     rcx, aBaseDiagnosisP_37; "base\\diagnosis\\pdui\\perfmon\\mon\\co"...
0x18000a894  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18000a899  jmp     loc_18000A65C
0x18000a89e  mov     ecx, 3
0x18000a8a3  int     29h; Win8: RtlFailFast(ecx)
0x18000a8a5  mov     rcx, [rbx+80h]; this
0x18000a8ac  mov     rdx, rsi; struct _EVENT_RECORD *
0x18000a8af  call    ?EventDisk@WdcDiskMonitor@@QEAAJPEAU_EVENT_RECORD@@@Z; WdcDiskMonitor::EventDisk(_EVENT_RECORD *)
0x18000a8b4  test    eax, eax
0x18000a8b6  js      short loc_18000A878
0x18000a8b8  mov     rcx, [rbx+88h]; this
0x18000a8bf  mov     rdx, rsi; struct _EVENT_RECORD *
0x18000a8c2  call    ?EventDisk@WdcProcessDiskMonitor@@QEAAJPEAU_EVENT_RECORD@@@Z; WdcProcessDiskMonitor::EventDisk(_EVENT_RECORD *)
0x18000a8c7  test    eax, eax
0x18000a8c9  jns     loc_18000A65C
0x18000a8cf  jmp     short loc_18000A878
0x18000a8d1  cmp     byte ptr [rsi+2Dh], 24h ; '$'
0x18000a8d5  jnz     loc_18000A65C
0x18000a8db  mov     r8, [rbx+80h]
0x18000a8e2  xor     ebx, ebx
0x18000a8e4  movzx   ecx, word ptr [rsi+4]
0x18000a8e8  mov     rdx, [rsi+60h]
0x18000a8ec  mov     [rsp+78h+arg_10], r8
0x18000a8f4  mov     [rsp+78h+arg_8], ebx
0x18000a8fb  and     cx, 40h
0x18000a8ff  jz      loc_18000AABC
0x18000a905  mov     r15, [rdx]
0x18000a908  test    cx, cx
0x18000a90b  mov     eax, 8
0x18000a910  mov     r9d, 4
0x18000a916  cmovz   eax, r9d
0x18000a91a  add     rax, rdx
0x18000a91d  mov     [rsp+78h+var_48], rax
0x18000a922  jz      loc_18000AAB4
0x18000a928  mov     rdx, rax
0x18000a92b  mov     ecx, ebx
0x18000a92d  movzx   eax, word ptr [rax]
0x18000a930  test    ax, ax
0x18000a933  jz      short loc_18000A954
0x18000a935  nop     word ptr [rax+rax+00000000h]
0x18000a940  imul    ecx, 25h ; '%'
0x18000a943  lea     rdx, [rdx+2]
0x18000a947  movzx   eax, ax
0x18000a94a  add     ecx, eax
0x18000a94c  movzx   eax, word ptr [rdx]
0x18000a94f  test    ax, ax
0x18000a952  jnz     short loc_18000A940
0x18000a954  imul    r13d, ecx, 12B9B0A5h
0x18000a95b  mov     eax, 12E0BE63h
0x18000a960  mul     r13d
0x18000a963  mov     eax, r13d
0x18000a966  sub     eax, edx
0x18000a968  shr     eax, 1
0x18000a96a  add     eax, edx
0x18000a96c  shr     eax, 1Dh
0x18000a96f  imul    eax, 3B9ACA07h
0x18000a975  sub     r13d, eax
0x18000a978  test    r15, r15
0x18000a97b  jz      loc_18000AF8B
0x18000a981  imul    edi, r15d, 10DCDh
0x18000a988  mov     rax, r15
0x18000a98b  shr     rax, 20h
0x18000a98f  mov     r12d, 1
0x18000a995  imul    ebp, eax, 10DCDh
0x18000a99b  imul    eax, 41C64E6Dh
0x18000a9a1  inc     edi
0x18000a9a3  and     edi, 0FFFF0000h
0x18000a9a9  inc     ebp
0x18000a9ab  add     eax, 3039h
0x18000a9b0  and     ebp, 0FFFF0000h
0x18000a9b6  shr     eax, 10h
0x18000a9b9  or      ebp, eax
0x18000a9bb  imul    eax, r15d, 41C64E6Dh
0x18000a9c2  add     eax, 3039h
0x18000a9c7  shr     eax, 10h
0x18000a9ca  or      edi, eax
0x18000a9cc  mov     eax, 824A4E61h
0x18000a9d1  lea     ecx, [rdi+rbp]
0x18000a9d4  mul     ecx
0x18000a9d6  lea     rax, [r8+30h]
0x18000a9da  mov     r14d, edx
0x18000a9dd  mov     [rsp+78h+arg_18], rax
0x18000a9e5  shr     r14d, 8
0x18000a9e9  cmp     [rax], ebx
  ... truncated ...
```
