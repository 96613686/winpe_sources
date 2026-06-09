# CVdsPack::MigrateDisks(_GUID *,long,_GUID,int,int,long *,int *)

- ea: `0x140017250`
- end: `0x140017ca1`
- name: `?MigrateDisks@CVdsPack@@UEAAJPEAU_GUID@@JU2@HHPEAJPEAH@Z`
- size: `2641`
- prototype: `__int64 __usercall@<rax>(CVdsPack *__hidden this@<rcx>, struct _GUID *@<rdx>, int@<r8d>, struct _GUID *__struct_ptr@<r9>, int, int, int *, int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x14000f930`
- `0x14000f9b0`
- `0x140012c48`
- `0x140013298`
- `0x140017250`
- `0x14002e123`
- `0x14003a9fc`
- `0x14003aabc`
- `0x14003c084`
- `0x14003c668`
- `0x1400405a0`
- `0x140040808`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140017425`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140017425`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140017aaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140017c4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140017aaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140017c4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017501`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017530`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017b76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017b93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017bb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017c08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017501`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017530`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017b76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017b93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017bb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017c08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001744c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001744c`
- `vdsutil!CoFreeStringArray` at `0x140017b70`
- `vdsutil!CoFreeStringArray` at `0x140017b70`
- `vdsutil!VdsHeapAlloc` at `0x140017516`
- `vdsutil!VdsHeapAlloc` at `0x14001753f`
- `vdsutil!VdsHeapAlloc` at `0x140017516`
- `vdsutil!VdsHeapAlloc` at `0x14001753f`
- `vdsutil!VdsHeapFree` at `0x140017b85`
- `vdsutil!VdsHeapFree` at `0x140017ba1`
- `vdsutil!VdsHeapFree` at `0x140017bc6`
- `vdsutil!VdsHeapFree` at `0x140017c17`
- `vdsutil!VdsHeapFree` at `0x140017b85`
- `vdsutil!VdsHeapFree` at `0x140017ba1`
- `vdsutil!VdsHeapFree` at `0x140017bc6`
- `vdsutil!VdsHeapFree` at `0x140017c17`
- `vdsutil!VdsTraceEx` at `0x14001738d`
- `vdsutil!VdsTraceEx` at `0x140017404`
- `vdsutil!VdsTraceEx` at `0x14001743e`
- `vdsutil!VdsTraceEx` at `0x1400175b7`
- `vdsutil!VdsTraceEx` at `0x140017650`
- `vdsutil!VdsTraceEx` at `0x140017730`
- `vdsutil!VdsTraceEx` at `0x140017769`
- `vdsutil!VdsTraceEx` at `0x140017799`
- `vdsutil!VdsTraceEx` at `0x14001789a`
- `vdsutil!VdsTraceEx` at `0x140017969`
- `vdsutil!VdsTraceEx` at `0x1400179f4`
- `vdsutil!VdsTraceEx` at `0x140017a82`
- `vdsutil!VdsTraceEx` at `0x140017b05`
- `vdsutil!VdsTraceEx` at `0x140017b35`
- `vdsutil!VdsTraceEx` at `0x140017b50`
- `vdsutil!VdsTraceEx` at `0x14001738d`
- `vdsutil!VdsTraceEx` at `0x140017404`
- `vdsutil!VdsTraceEx` at `0x14001743e`
- `vdsutil!VdsTraceEx` at `0x1400175b7`
- `vdsutil!VdsTraceEx` at `0x140017650`
- `vdsutil!VdsTraceEx` at `0x140017730`
- `vdsutil!VdsTraceEx` at `0x140017769`
- `vdsutil!VdsTraceEx` at `0x140017799`
- `vdsutil!VdsTraceEx` at `0x14001789a`
- `vdsutil!VdsTraceEx` at `0x140017969`
- `vdsutil!VdsTraceEx` at `0x1400179f4`
- `vdsutil!VdsTraceEx` at `0x140017a82`
- `vdsutil!VdsTraceEx` at `0x140017b05`
- `vdsutil!VdsTraceEx` at `0x140017b35`
- `vdsutil!VdsTraceEx` at `0x140017b50`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140017308`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140017308`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140017c5a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140017c5a`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CVdsPack::MigrateDisks(
        CVdsPack *this,
        struct _GUID *a2,
        int a3,
        struct _GUID *a4,
        int a5,
        int a6,
        int *a7,
        int *a8)
{
  CVdsPack *v9; // rsi
  CVdsPack *v11; // rdi
  struct _VDSSVC_MP_NODE *v12; // r13
  CVdsPack *v13; // rcx
  int *v14; // rdi
  int TargetInfo; // eax
  signed int v16; // ebx
  const char *v17; // r8
  int v18; // eax
  DWORD v19; // eax
  int v20; // r14d
  HANDLE ProcessHeap; // rax
  __int64 v22; // rax
  HANDLE v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdi
  int v26; // eax
  int v27; // r14d
  __int64 v28; // r8
  __int64 v29; // r13
  int v30; // eax
  int v31; // eax
  int i; // ecx
  int v33; // ebx
  int j; // edx
  unsigned __int16 *v35; // rax
  __int64 v36; // r10
  int v37; // r8d
  int v38; // r9d
  int v39; // eax
  int v40; // eax
  int k; // ecx
  int v42; // r9d
  signed int v43; // eax
  struct CVdsService *v44; // rcx
  int v45; // eax
  int v46; // r14d
  int v47; // edi
  int v48; // eax
  int v49; // r9d
  int m; // edi
  int v51; // eax
  struct IVdsPack *v52; // r12
  int v53; // eax
  struct CVdsService *v54; // rcx
  struct _VDSSVC_MP_NODE *v55; // r14
  int v56; // eax
  HANDLE v57; // rax
  struct _VDSSVC_MP_NODE *v58; // rdi
  HANDLE v59; // rax
  struct _VDSSVC_MP_NODE *v60; // rdi
  HANDLE v61; // rax
  __int64 n; // rdi
  struct IUnknown **v63; // r15
  struct IUnknown *v64; // rcx
  HANDLE v65; // rax
  char v67; // [rsp+40h] [rbp-C0h]
  struct IVdsPack *v68; // [rsp+48h] [rbp-B8h] BYREF
  struct _VDSSVC_MP_NODE *v69; // [rsp+50h] [rbp-B0h]
  int v70; // [rsp+58h] [rbp-A8h] BYREF
  struct IVdsMigrateDisks *v71[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID id; // [rsp+70h] [rbp-90h] BYREF
  int v73; // [rsp+80h] [rbp-80h] BYREF
  __int64 v74; // [rsp+88h] [rbp-78h] BYREF
  __int64 v75; // [rsp+90h] [rbp-70h] BYREF
  struct IVdsMigrateDisks *v76; // [rsp+98h] [rbp-68h] BYREF
  __int64 v77; // [rsp+A0h] [rbp-60h]
  struct IUnknown **v78; // [rsp+A8h] [rbp-58h] BYREF
  struct _VDSSVC_MP_NODE *v79; // [rsp+B0h] [rbp-50h]
  int *v80; // [rsp+B8h] [rbp-48h]
  struct _VDSSVC_MP_NODE *v81; // [rsp+C0h] [rbp-40h] BYREF
  struct _VDSSVC_MP_NODE *v82; // [rsp+C8h] [rbp-38h] BYREF
  struct IVdsProvider *v83; // [rsp+D0h] [rbp-30h] BYREF
  CVdsPack *v84; // [rsp+D8h] [rbp-28h]
  _BYTE v85[16]; // [rsp+E0h] [rbp-20h] BYREF
  _VDS_PROVIDER_PROP v86; // [rsp+F0h] [rbp-10h] BYREF
  struct _VDS_PROVIDER_PROP v87; // [rsp+130h] [rbp+30h] BYREF

  v9 = (CVdsPack *)a3;
  v11 = this;
  v84 = this;
  v80 = a8;
  v68 = 0;
  v70 = 0;
  v73 = 0;
  v74 = 0;
  v77 = 0;
  v67 = 0;
  v12 = 0;
  v79 = 0;
  v81 = 0;
  v69 = 0;
  v82 = 0;
  v78 = 0;
  v83 = 0;
  memset_0(&v87, 0, sizeof(v87));
  memset_0(&v86, 0, sizeof(v86));
  v71[0] = 0;
  v76 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v85, 0x5Eu, "CVdsPack::MigrateDisks()");
  memset_0(&v87, 0, sizeof(v87));
  memset_0(&v86, 0, sizeof(v86));
  *a8 = 0;
  if ( (int)v9 > 0 )
  {
    v13 = v9;
    v14 = a7;
    while ( v13 )
    {
      *v14++ = -2147467259;
      v13 = (CVdsPack *)((char *)v13 - 1);
    }
    v11 = v84;
  }
  id = *a4;
  TargetInfo = CVdsPack::MigrateGetTargetInfo(v13, &id, &v68, &v83, &v87, &v76);
  v16 = TargetInfo;
  if ( TargetInfo < 0 )
  {
    v17 = "CVdsPack::MigrateDisks, 1, %lX";
LABEL_8:
    VdsTraceEx(94, 0, v17, (unsigned int)TargetInfo);
    goto LABEL_110;
  }
  TargetInfo = CVdsPack::MigrateGetSourceInfo(v11, &v86, v71, (unsigned int)v9, a2, &v78);
  v16 = TargetInfo;
  if ( TargetInfo < 0 )
  {
    v17 = "CVdsPack::MigrateDisks, 2, %lX";
    goto LABEL_8;
  }
  if ( (v86.ulFlags & 1) == 0 )
  {
    id = *a2;
    v18 = MigrateSaveMountPoints(*((struct CVdsService **)v11 + 10), *((struct IVdsPack **)v11 + 11), &id, &v81);
    v16 = v18;
    if ( v18 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 3, hr=%lX", v18);
      v12 = v81;
      goto LABEL_110;
    }
    v12 = v81;
    v79 = v81;
  }
  v19 = WaitForSingleObject(g_hExclusiveOperationSem, 0xFFFFFFFF);
  if ( v19 )
  {
    VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 4, error=%ld", v19);
    v16 = -2147467259;
    goto LABEL_110;
  }
  g_dwThreadIdExclusiveLock = GetCurrentThreadId();
  v67 = 1;
  id = v87.id;
  TargetInfo = (*(__int64 (__fastcall **)(struct IVdsMigrateDisks *, struct _GUID *))(*(_QWORD *)v71[0] + 24LL))(
                 v71[0],
                 &id);
  v16 = TargetInfo;
  if ( TargetInfo < 0 )
  {
    v17 = "CVdsPack::MigrateDisks, 5, %lX";
    goto LABEL_8;
  }
  if ( TargetInfo )
  {
    id = v86.id;
    TargetInfo = (*(__int64 (__fastcall **)(struct IVdsMigrateDisks *, struct _GUID *))(*(_QWORD *)v76 + 32LL))(
                   v76,
                   &id);
    v16 = TargetInfo;
    if ( TargetInfo < 0 )
    {
      v17 = "CVdsPack::MigrateDisks, 6, %lX";
      goto LABEL_8;
    }
    if ( TargetInfo )
    {
      v16 = -2147212288;
      VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 7, %lX", 2147755008LL);
      goto LABEL_110;
    }
    v20 = 0;
  }
  else
  {
    v20 = 1;
  }
  if ( a6 == 1 )
  {
    v75 = 0;
    ProcessHeap = GetProcessHeap();
    v22 = VdsHeapAlloc(ProcessHeap, 8, 4LL * (_QWORD)v9);
    CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=(&v75, v22);
    v23 = GetProcessHeap();
    v24 = VdsHeapAlloc(v23, 8, 8LL * (_QWORD)v9);
    v77 = v24;
    v25 = v75;
    if ( v75 && v24 )
    {
      id = v87.id;
      v26 = (*(__int64 (__fastcall **)(struct IVdsMigrateDisks *, struct _GUID *, struct _GUID *, _QWORD, __int64 *, int *, int *))(*(_QWORD *)v71[0] + 40LL))(
              v71[0],
              &id,
              a2,
              (unsigned int)v9,
              &v74,
              a7,
              &v70);
      v16 = v26;
      if ( v26 >= 0 )
      {
        v27 = 0;
        v28 = 0;
        if ( (int)v9 > 0 )
        {
          v29 = v77;
          do
          {
            if ( a7[v28] >= 0 )
              *(_QWORD *)(v29 + 8LL * v27++) = *(_QWORD *)(v74 + 8 * v28);
            v28 = (unsigned int)(v28 + 1);
          }
          while ( (int)v28 < (int)v9 );
          v12 = v79;
          if ( v27 > 0 )
          {
            id = v86.id;
            v30 = (*(__int64 (__fastcall **)(struct IVdsMigrateDisks *, struct _GUID *, __int64, _QWORD, __int64, int *))(*(_QWORD *)v76 + 48LL))(
                    v76,
                    &id,
                    v77,
                    (unsigned int)v27,
                    v25,
                    &v73);
            v16 = v30;
            if ( v30 >= 0 )
            {
              for ( i = 0; i < v27; ++i )
              {
                v33 = *(_DWORD *)(v25 + 4LL * i);
                if ( v33 )
                {
                  for ( j = 0; j < (int)v9; ++j )
                  {
                    v35 = *(unsigned __int16 **)(v74 + 8LL * j);
                    if ( v35 )
                    {
                      v36 = *(_QWORD *)(v77 + 8LL * i) - (_QWORD)v35;
                      do
                      {
                        v37 = *(unsigned __int16 *)((char *)v35 + v36);
                        v38 = *v35 - v37;
                        if ( v38 )
                          break;
                        ++v35;
                      }
                      while ( v37 );
                      if ( !v38 )
                      {
                        a7[j] = v33;
                        break;
                      }
                    }
                  }
                }
              }
              v16 = 0;
              if ( v70 || v73 )
                *v80 = 1;
              v39 = (*(__int64 (__fastcall **)(struct IVdsMigrateDisks *, struct _GUID *, _QWORD, _QWORD))(*(_QWORD *)v71[0] + 72LL))(
                      v71[0],
                      a2,
                      (unsigned int)v9,
                      0);
              if ( v39 < 0 )
                VdsTraceEx(94, 1, "CVdsPack::MigrateDisks, 11.1, %lX, Finish Export failed will ignore", v39);
              v40 = (*(__int64 (__fastcall **)(struct IVdsMigrateDisks *, __int64, struct _GUID *, _QWORD, _DWORD))(*(_QWORD *)v76 + 80LL))(
                      v76,
                      v74,
                      a2,
                      (unsigned int)v9,
                      0);
              if ( v40 < 0 )
                VdsTraceEx(94, 1, "CVdsPack::MigrateDisks, 11.2, %lX, Finish Import failed will ignore", v40);
              for ( k = 0; k < (int)v9; ++k )
              {
                v42 = a7[k];
                if ( v42 )
                {
                  v16 = 1;
                  VdsTraceEx(
                    94,
                    1,
                    "CVdsPack::MigrateDisks, 11.3, %lX, Result vector error found in element %i",
                    v42,
                    k);
                  break;
                }
              }
              CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(&v75);
              v12 = v79;
              goto LABEL_110;
            }
            VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 10, %lX", v30);
            v31 = (*(__int64 (__fastcall **)(struct IVdsMigrateDisks *, struct _GUID *, _QWORD, _QWORD))(*(_QWORD *)v71[0] + 72LL))(
                    v71[0],
                    a2,
                    (unsigned int)v9,
                    0);
            if ( v31 < 0 )
              VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 11, %lX", (unsigned int)v31);
          }
        }
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 9, %lX", (unsigned int)v26);
      }
    }
    else
    {
      v16 = -2147024882;
      VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 8, %lX", 2147942414LL);
    }
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(&v75);
LABEL_110:
    v52 = v68;
LABEL_111:
    v55 = v69;
    goto LABEL_112;
  }
  id = v87.id;
  TargetInfo = (*(__int64 (__fastcall **)(struct IVdsMigrateDisks *, struct _GUID *, struct _GUID *, _QWORD, __int64 *, int *, int *))(*(_QWORD *)v71[0] + 40LL))(
                 v71[0],
                 &id,
                 a2,
                 (unsigned int)v9,
                 &v74,
                 a7,
                 &v70);
  v16 = TargetInfo;
  if ( TargetInfo < 0 )
  {
    v17 = "CVdsPack::MigrateDisks, 12, %lX";
    goto LABEL_8;
  }
  if ( TargetInfo && !a5 )
  {
LABEL_71:
    v16 = -2147467259;
    goto LABEL_110;
  }
  if ( v70 == 1 )
    *v80 = 1;
  id = v86.id;
  TargetInfo = (*(__int64 (__fastcall **)(struct IVdsMigrateDisks *, struct _GUID *, __int64, _QWORD, int *, int *))(*(_QWORD *)v76 + 48LL))(
                 v76,
                 &id,
                 v74,
                 (unsigned int)v9,
                 a7,
                 &v73);
  v16 = TargetInfo;
  if ( TargetInfo < 0 )
  {
    v17 = "CVdsPack::MigrateDisks, 13, %lX";
    goto LABEL_8;
  }
  if ( TargetInfo && !a5 )
  {
    VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 14, %lX", TargetInfo);
    (*(void (__fastcall **)(struct IVdsMigrateDisks *, struct _GUID *, _QWORD, _QWORD))(*(_QWORD *)v71[0] + 72LL))(
      v71[0],
      a2,
      (unsigned int)v9,
      0);
    goto LABEL_71;
  }
  if ( v73 == 1 )
    *v80 = 1;
  if ( v20 )
  {
    id = v87.id;
    v43 = (*(__int64 (__fastcall **)(struct IVdsMigrateDisks *, struct _GUID *, struct _GUID *, _QWORD, int *))(*(_QWORD *)v71[0] + 56LL))(
            v71[0],
            &id,
            a2,
            (unsigned int)v9,
            a7);
  }
  else
  {
    id = v86.id;
    v43 = (*(__int64 (__fastcall **)(struct IVdsMigrateDisks *, struct _GUID *, __int64, struct _GUID *, _DWORD, int *, int *))(*(_QWORD *)v76 + 64LL))(
            v76,
            &id,
            v74,
            a2,
            (_DWORD)v9,
            a7,
            &v70);
  }
  v16 = v43;
  if ( (v86.ulFlags & 1) == 0 )
  {
    v45 = MigrateAssignClearMountPoints(v44, v12, 1u);
    v12 = 0;
    if ( v45 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 15, %lX", v45);
      VdsLogError(0xC2000016, 0, 0, v16, 0x207000Au, 0);
    }
  }
  v46 = (*(__int64 (__fastcall **)(struct IVdsMigrateDisks *, struct _GUID *, _QWORD, bool))(*(_QWORD *)v71[0] + 72LL))(
          v71[0],
          a2,
          (unsigned int)v9,
          v16 >= 0);
  v47 = (*(__int64 (__fastcall **)(struct IVdsMigrateDisks *, __int64, struct _GUID *, _QWORD, bool))(*(_QWORD *)v76 + 80LL))(
          v76,
          v74,
          a2,
          (unsigned int)v9,
          v16 >= 0);
  v48 = CVdsService::RemoveObsoleteDevNodes();
  if ( v48 < 0 )
    VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 16, hr=%lX", v48);
  if ( v16 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 17, %lX", (unsigned int)v16);
    goto LABEL_110;
  }
  if ( v46 < 0 || v47 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 18, %lX, %lX", v46, v47);
    v16 = -2147212257;
    goto LABEL_110;
  }
  v49 = v70;
  if ( v70 == 1 )
    *v80 = 1;
  for ( m = 0; m < (int)v9; ++m )
  {
    v51 = CVdsService::ResetDiskWrapper(&a2[m], v78[m], v83, v49);
    v16 = v51;
    if ( v51 < 0 )
    {
      if ( v51 != -2147212283 && v51 != -2147212277 )
      {
        VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 19, %lX", v51);
        v16 = -2147211946;
        goto LABEL_110;
      }
      v16 = 0;
    }
    v49 = v70;
  }
  _InterlockedExchange((volatile __int32 *)&g_dwThreadIdExclusiveLock, 0);
  ReleaseSemaphore(g_hExclusiveOperationSem, 1, 0);
  v67 = 0;
  v52 = v68;
  if ( !v68 || (v86.ulFlags & 1) != 0 )
    goto LABEL_111;
  id = *a2;
  v53 = MigrateSaveMountPoints(*((struct CVdsService **)v84 + 10), v68, &id, &v82);
  v16 = v53;
  if ( v53 >= 0 )
  {
    v56 = MigrateAssignClearMountPoints(v54, v82, 0);
    v16 = v56;
    v55 = 0;
    if ( v56 < 0 )
      VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 21, hr=%lX", v56);
  }
  else
  {
    VdsTraceEx(94, 0, "CVdsPack::MigrateDisks, 20, hr=%lX", v53);
    v55 = v82;
  }
LABEL_112:
  if ( v74 )
    CoFreeStringArray(v74, (unsigned int)v9);
  v57 = GetProcessHeap();
  VdsHeapFree(v57, 0, v77);
  if ( v55 )
  {
    do
    {
      v58 = *(struct _VDSSVC_MP_NODE **)v55;
      v59 = GetProcessHeap();
      VdsHeapFree(v59, 0, v55);
      v55 = v58;
    }
    while ( v58 );
  }
  if ( v12 )
  {
    do
    {
      v60 = *(struct _VDSSVC_MP_NODE **)v12;
      v61 = GetProcessHeap();
      VdsHeapFree(v61, 0, v12);
      v12 = v60;
    }
    while ( v60 );
  }
  if ( v78 )
  {
    for ( n = 0; (int)n < (int)v9; n = (unsigned int)(n + 1) )
    {
      v63 = v78;
      v64 = v78[n];
      if ( v64 )
      {
        ((void (__fastcall *)(struct IUnknown *))v64->lpVtbl->Release)(v64);
        v63[n] = 0;
      }
    }
    v65 = GetProcessHeap();
    VdsHeapFree(v65, 0, v78);
  }
  if ( v52 )
    ((void (__fastcall *)(struct IVdsPack *))v52->lpVtbl->Release)(v52);
  if ( v67 )
  {
    _InterlockedExchange((volatile __int32 *)&g_dwThreadIdExclusiveLock, 0);
    ReleaseSemaphore(g_hExclusiveOperationSem, 1, 0);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v85);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v76);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v71);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v83);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140017250  push    rbp
0x140017252  push    rbx
0x140017253  push    rsi
0x140017254  push    rdi
0x140017255  push    r12
0x140017257  push    r13
0x140017259  push    r14
0x14001725b  push    r15
0x14001725d  lea     rbp, [rsp-88h]
0x140017265  sub     rsp, 188h
0x14001726c  mov     rax, cs:__security_cookie
0x140017273  xor     rax, rsp
0x140017276  mov     [rbp+0C0h+var_50], rax
0x14001727a  mov     rbx, r9
0x14001727d  movsxd  rsi, r8d
0x140017280  mov     r15, rdx
0x140017283  mov     rdi, rcx
0x140017286  mov     [rbp+0C0h+var_E8], rcx
0x14001728a  mov     r12, [rbp+0C0h+arg_30]
0x140017291  mov     r14, [rbp+0C0h+arg_38]
0x140017298  mov     [rbp+0C0h+var_108], r14
0x14001729c  xor     ecx, ecx
0x14001729e  mov     [rsp+1C0h+var_178], rcx
0x1400172a3  mov     [rsp+1C0h+var_168], ecx
0x1400172a7  mov     [rbp+0C0h+var_140], ecx
0x1400172aa  mov     [rbp+0C0h+var_138], rcx
0x1400172ae  mov     [rbp+0C0h+var_120], rcx
0x1400172b2  mov     [rsp+1C0h+var_180], cl
0x1400172b6  mov     r13d, ecx
0x1400172b9  mov     [rbp+0C0h+var_110], rcx
0x1400172bd  mov     [rbp+0C0h+var_100], rcx
0x1400172c1  mov     [rsp+1C0h+var_170], rcx
0x1400172c6  mov     [rbp+0C0h+var_F8], rcx
0x1400172ca  mov     [rbp+0C0h+var_118], rcx
0x1400172ce  mov     [rbp+0C0h+var_F0], rcx
0x1400172d2  xor     edx, edx; Val
0x1400172d4  lea     r8d, [rcx+40h]; Size
0x1400172d8  lea     rcx, [rbp+0C0h+var_90]; void *
0x1400172dc  call    memset_0
0x1400172e1  xor     edx, edx; Val
0x1400172e3  lea     r8d, [r13+40h]; Size
0x1400172e7  lea     rcx, [rbp+0C0h+var_D0]; void *
0x1400172eb  call    memset_0
0x1400172f0  mov     [rsp+1C0h+var_160], r13
0x1400172f5  mov     [rbp+0C0h+var_128], r13
0x1400172f9  lea     r8, aCvdspackMigrat_22; "CVdsPack::MigrateDisks()"
0x140017300  lea     edx, [r13+5Eh]
0x140017304  lea     rcx, [rbp+0C0h+var_E0]
0x140017308  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001730e  nop
0x14001730f  xor     edx, edx; Val
0x140017311  lea     r8d, [r13+40h]; Size
0x140017315  lea     rcx, [rbp+0C0h+var_90]; void *
0x140017319  call    memset_0
0x14001731e  xor     edx, edx; Val
0x140017320  lea     r8d, [r13+40h]; Size
0x140017324  lea     rcx, [rbp+0C0h+var_D0]; void *
0x140017328  call    memset_0
0x14001732d  mov     [r14], r13d
0x140017330  mov     r14, 0FFFFFFFF80004005h
0x140017337  test    esi, esi
0x140017339  jle     short loc_14001734A
0x14001733b  mov     rcx, rsi; this
0x14001733e  mov     rdi, r12
0x140017341  mov     rax, r14
0x140017344  rep stosd
0x140017346  mov     rdi, [rbp+0C0h+var_E8]
0x14001734a  movups  xmm0, xmmword ptr [rbx]
0x14001734d  movdqu  xmmword ptr [rsp+1C0h+var_150.Data1], xmm0
0x140017353  lea     rax, [rbp+0C0h+var_128]
0x140017357  mov     [rsp+1C0h+var_198], rax; struct IVdsMigrateDisks **
0x14001735c  lea     rax, [rbp+0C0h+var_90]
0x140017360  mov     [rsp+1C0h+var_1A0], rax; struct _VDS_PROVIDER_PROP *
0x140017365  lea     r9, [rbp+0C0h+var_F0]; struct IVdsProvider **
0x140017369  lea     r8, [rsp+1C0h+var_178]; struct IVdsPack **
0x14001736e  lea     rdx, [rsp+1C0h+var_150]; struct _GUID *
0x140017373  call    ?MigrateGetTargetInfo@CVdsPack@@QEAAJU_GUID@@PEAPEAUIVdsPack@@PEAPEAUIVdsProvider@@PEAU_VDS_PROVIDER_PROP@@PEAPEAUIVdsMigrateDisks@@@Z; CVdsPack::MigrateGetTargetInfo(_GUID,IVdsPack * *,IVdsProvider * *,_VDS_PROVIDER_PROP *,IVdsMigrateDisks * *)
0x140017378  mov     ebx, eax
0x14001737a  test    eax, eax
0x14001737c  jns     short loc_140017398
0x14001737e  lea     r8, aCvdspackMigrat_17; "CVdsPack::MigrateDisks, 1, %lX"
0x140017385  mov     r9d, eax
0x140017388  xor     edx, edx
0x14001738a  lea     ecx, [rdx+5Eh]
0x14001738d  call    cs:__imp_VdsTraceEx
0x140017393  jmp     loc_140017B5B
0x140017398  lea     rax, [rbp+0C0h+var_118]
0x14001739c  mov     [rsp+1C0h+var_198], rax; struct IUnknown ***
0x1400173a1  mov     [rsp+1C0h+var_1A0], r15; struct _GUID *
0x1400173a6  mov     r9d, esi; unsigned int
0x1400173a9  lea     r8, [rsp+1C0h+var_160]; struct IVdsMigrateDisks **
0x1400173ae  lea     rdx, [rbp+0C0h+var_D0]; struct _VDS_PROVIDER_PROP *
0x1400173b2  mov     rcx, rdi; this
0x1400173b5  call    ?MigrateGetSourceInfo@CVdsPack@@QEAAJPEAU_VDS_PROVIDER_PROP@@PEAPEAUIVdsMigrateDisks@@KPEAU_GUID@@PEAPEAPEAUIUnknown@@@Z; CVdsPack::MigrateGetSourceInfo(_VDS_PROVIDER_PROP *,IVdsMigrateDisks * *,ulong,_GUID *,IUnknown * * *)
0x1400173ba  mov     ebx, eax
0x1400173bc  test    eax, eax
0x1400173be  jns     short loc_1400173C9
0x1400173c0  lea     r8, aCvdspackMigrat_7; "CVdsPack::MigrateDisks, 2, %lX"
0x1400173c7  jmp     short loc_140017385
0x1400173c9  test    byte ptr [rbp+0C0h+var_D0.ulFlags], 1
0x1400173cd  jnz     short loc_14001741B
0x1400173cf  movups  xmm0, xmmword ptr [r15]
0x1400173d3  movdqu  xmmword ptr [rsp+1C0h+var_150.Data1], xmm0
0x1400173d9  lea     r9, [rbp+0C0h+var_100]; struct _VDSSVC_MP_NODE **
0x1400173dd  lea     r8, [rsp+1C0h+var_150]; struct _GUID
0x1400173e2  mov     rdx, [rdi+58h]; struct IVdsPack *
0x1400173e6  mov     rcx, [rdi+50h]; struct CVdsService *
0x1400173ea  call    ?MigrateSaveMountPoints@@YAJPEAVCVdsService@@PEAUIVdsPack@@U_GUID@@PEAPEAU_VDSSVC_MP_NODE@@@Z; MigrateSaveMountPoints(CVdsService *,IVdsPack *,_GUID,_VDSSVC_MP_NODE * *)
0x1400173ef  mov     ebx, eax
0x1400173f1  test    eax, eax
0x1400173f3  jns     short loc_140017413
0x1400173f5  mov     r9d, eax
0x1400173f8  lea     r8, aCvdspackMigrat_15; "CVdsPack::MigrateDisks, 3, hr=%lX"
0x1400173ff  xor     edx, edx
0x140017401  lea     ecx, [rdx+5Eh]
0x140017404  call    cs:__imp_VdsTraceEx
0x14001740a  mov     r13, [rbp+0C0h+var_100]
0x14001740e  jmp     loc_140017B5B
0x140017413  mov     r13, [rbp+0C0h+var_100]
0x140017417  mov     [rbp+0C0h+var_110], r13
0x14001741b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001741e  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hHandle
0x140017425  call    cs:__imp_WaitForSingleObject
0x14001742b  test    eax, eax
0x14001742d  jz      short loc_14001744C
0x14001742f  mov     r9d, eax
0x140017432  lea     r8, aCvdspackMigrat_3; "CVdsPack::MigrateDisks, 4, error=%ld"
0x140017439  xor     edx, edx
0x14001743b  lea     ecx, [rdx+5Eh]
0x14001743e  call    cs:__imp_VdsTraceEx
0x140017444  mov     ebx, r14d
0x140017447  jmp     loc_140017B5B
0x14001744c  call    cs:__imp_GetCurrentThreadId
0x140017452  mov     cs:?g_dwThreadIdExclusiveLock@@3KC, eax; ulong volatile g_dwThreadIdExclusiveLock
0x140017458  mov     edi, 1
0x14001745d  mov     [rsp+1C0h+var_180], dil
0x140017462  mov     rcx, [rsp+1C0h+var_160]
0x140017467  movaps  xmm0, xmmword ptr [rbp+0C0h+var_90.id.Data1]
0x14001746b  movdqu  xmmword ptr [rsp+1C0h+var_150.Data1], xmm0
0x140017471  mov     rax, [rcx]
0x140017474  lea     rdx, [rsp+1C0h+var_150]
0x140017479  mov     rax, [rax+18h]
0x14001747d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017482  mov     ebx, eax
0x140017484  test    eax, eax
0x140017486  jns     short loc_140017494
0x140017488  lea     r8, aCvdspackMigrat_13; "CVdsPack::MigrateDisks, 5, %lX"
0x14001748f  jmp     loc_140017385
0x140017494  jnz     short loc_14001749B
0x140017496  mov     r14d, edi
0x140017499  jmp     short loc_1400174E5
0x14001749b  mov     rcx, [rbp+0C0h+var_128]
0x14001749f  movaps  xmm0, xmmword ptr [rbp+0C0h+var_D0.id.Data1]
0x1400174a3  movdqu  xmmword ptr [rsp+1C0h+var_150.Data1], xmm0
0x1400174a9  mov     rax, [rcx]
0x1400174ac  lea     rdx, [rsp+1C0h+var_150]
0x1400174b1  mov     rax, [rax+20h]
0x1400174b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400174ba  mov     ebx, eax
0x1400174bc  test    eax, eax
0x1400174be  jns     short loc_1400174CC
0x1400174c0  lea     r8, aCvdspackMigrat_20; "CVdsPack::MigrateDisks, 6, %lX"
0x1400174c7  jmp     loc_140017385
0x1400174cc  jz      short loc_1400174E2
0x1400174ce  mov     ebx, 80042400h
0x1400174d3  mov     r9d, ebx
0x1400174d6  lea     r8, aCvdspackMigrat_23; "CVdsPack::MigrateDisks, 7, %lX"
0x1400174dd  jmp     loc_140017388
0x1400174e2  xor     r14d, r14d
0x1400174e5  cmp     [rbp+0C0h+arg_28], edi
0x1400174eb  jnz     loc_1400177C6
0x1400174f1  mov     [rbp+0C0h+var_130], 0
0x1400174f9  lea     rdi, ds:0[rsi*4]
0x140017501  call    cs:__imp_GetProcessHeap
0x140017507  mov     rcx, rax
0x14001750a  mov     r8, rdi
0x14001750d  mov     r14d, 8
0x140017513  mov     edx, r14d
0x140017516  call    cs:__imp_VdsHeapAlloc
0x14001751c  mov     rdx, rax
0x14001751f  lea     rcx, [rbp+0C0h+var_130]
0x140017523  call    ??4?$CVdsHeapPtr@U_MOUNTMGR_MOUNT_POINT@@@@QEAAPEAU_MOUNTMGR_MOUNT_POINT@@PEAU1@@Z; CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=(_MOUNTMGR_MOUNT_POINT *)
0x140017528  lea     rdi, ds:0[rsi*8]
0x140017530  call    cs:__imp_GetProcessHeap
0x140017536  mov     rcx, rax
0x140017539  mov     r8, rdi
0x14001753c  mov     edx, r14d
0x14001753f  call    cs:__imp_VdsHeapAlloc
0x140017545  mov     [rbp+0C0h+var_120], rax
0x140017549  mov     rdi, [rbp+0C0h+var_130]
0x14001754d  test    rdi, rdi
0x140017550  jz      loc_1400177B2
0x140017556  test    rax, rax
0x140017559  jz      loc_1400177B2
0x14001755f  mov     r10, [rsp+1C0h+var_160]
0x140017564  movaps  xmm0, xmmword ptr [rbp+0C0h+var_90.id.Data1]
0x140017568  movdqu  xmmword ptr [rsp+1C0h+var_150.Data1], xmm0
0x14001756e  mov     rcx, [r10]
0x140017571  mov     rax, [rcx+28h]
0x140017575  lea     rcx, [rsp+1C0h+var_168]
0x14001757a  mov     [rsp+1C0h+var_190], rcx
0x14001757f  mov     [rsp+1C0h+var_198], r12
0x140017584  lea     rcx, [rbp+0C0h+var_138]
0x140017588  mov     [rsp+1C0h+var_1A0], rcx
0x14001758d  mov     r9d, esi
0x140017590  mov     r8, r15
0x140017593  lea     rdx, [rsp+1C0h+var_150]
0x140017598  mov     rcx, r10
0x14001759b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400175a0  mov     ebx, eax
0x1400175a2  test    eax, eax
0x1400175a4  jns     short loc_1400175CC
0x1400175a6  mov     r9d, eax
0x1400175a9  lea     r8, aCvdspackMigrat_39; "CVdsPack::MigrateDisks, 9, %lX"
0x1400175b0  mov     ecx, 5Eh ; '^'
0x1400175b5  xor     edx, edx
0x1400175b7  call    cs:__imp_VdsTraceEx
0x1400175bd  nop
0x1400175be  lea     rcx, [rbp+0C0h+var_130]
0x1400175c2  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x1400175c7  jmp     loc_140017B5B
0x1400175cc  xor     r14d, r14d
0x1400175cf  xor     r8d, r8d
0x1400175d2  test    esi, esi
0x1400175d4  jle     short loc_1400175BE
0x1400175d6  mov     r13, [rbp+0C0h+var_120]
0x1400175da  cmp     dword ptr [r12+r8*4], 0
0x1400175df  jl      short loc_1400175F4
0x1400175e1  movsxd  rdx, r14d
0x1400175e4  mov     rax, [rbp+0C0h+var_138]
0x1400175e8  mov     rcx, [rax+r8*8]
0x1400175ec  mov     [r13+rdx*8+0], rcx
0x1400175f1  inc     r14d
0x1400175f4  inc     r8d
0x1400175f7  cmp     r8d, esi
0x1400175fa  jl      short loc_1400175DA
0x1400175fc  test    r14d, r14d
0x1400175ff  mov     r13, [rbp+0C0h+var_110]
0x140017603  jle     short loc_1400175BE
0x140017605  mov     rcx, [rbp+0C0h+var_128]
0x140017609  movaps  xmm0, xmmword ptr [rbp+0C0h+var_D0.id.Data1]
0x14001760d  movdqu  xmmword ptr [rsp+1C0h+var_150.Data1], xmm0
0x140017613  mov     rax, [rcx]
0x140017616  lea     rdx, [rbp+0C0h+var_140]
0x14001761a  mov     [rsp+1C0h+var_198], rdx
0x14001761f  mov     [rsp+1C0h+var_1A0], rdi
0x140017624  mov     r9d, r14d
0x140017627  mov     r8, [rbp+0C0h+var_120]
0x14001762b  lea     rdx, [rsp+1C0h+var_150]
0x140017630  mov     rax, [rax+30h]
0x140017634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017639  mov     ebx, eax
0x14001763b  test    eax, eax
0x14001763d  jns     short loc_140017689
0x14001763f  mov     r9d, eax
0x140017642  lea     r8, aCvdspackMigrat_21; "CVdsPack::MigrateDisks, 10, %lX"
0x140017649  xor     edx, edx
0x14001764b  lea     edi, [rdx+5Eh]
0x14001764e  mov     ecx, edi
0x140017650  call    cs:__imp_VdsTraceEx
0x140017656  mov     rcx, [rsp+1C0h+var_160]
0x14001765b  mov     rax, [rcx]
0x14001765e  xor     r9d, r9d
0x140017661  mov     r8d, esi
0x140017664  mov     rdx, r15
0x140017667  mov     rax, [rax+48h]
0x14001766b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017670  test    eax, eax
0x140017672  jns     loc_1400175BE
0x140017678  mov     r9d, eax
0x14001767b  lea     r8, aCvdspackMigrat_14; "CVdsPack::MigrateDisks, 11, %lX"
0x140017682  mov     ecx, edi
0x140017684  jmp     loc_1400175B5
0x140017689  xor     ecx, ecx
0x14001768b  movsxd  r13, ecx
0x14001768e  mov     ebx, [rdi+r13*4]
0x140017692  test    ebx, ebx
0x140017694  jz      short loc_1400176DB
0x140017696  xor     edx, edx
0x140017698  cmp     edx, esi
0x14001769a  jge     short loc_1400176DB
0x14001769c  movsxd  r11, edx
0x14001769f  mov     rax, [rbp+0C0h+var_138]
0x1400176a3  mov     rax, [rax+r11*8]
0x1400176a7  test    rax, rax
0x1400176aa  jz      short loc_1400176D3
0x1400176ac  mov     r8, [rbp+0C0h+var_120]
0x1400176b0  mov     r10, [r8+r13*8]
0x1400176b4  sub     r10, rax
0x1400176b7  movzx   r9d, word ptr [rax]
0x1400176bb  movzx   r8d, word ptr [rax+r10]
0x1400176c0  sub     r9d, r8d
0x1400176c3  jnz     short loc_1400176CE
0x1400176c5  add     rax, 2
0x1400176c9  test    r8d, r8d
0x1400176cc  jnz     short loc_1400176B7
0x1400176ce  test    r9d, r9d
0x1400176d1  jz      short loc_1400176D7
0x1400176d3  inc     edx
0x1400176d5  jmp     short loc_140017698
  ... truncated ...
```
