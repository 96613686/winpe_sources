# CVdsVolume::QueryReparsePoints(VDS_REPARSE_POINT_PROP * *,long *)

- ea: `0x140023620`
- end: `0x140023c54`
- name: `?QueryReparsePoints@CVdsVolume@@UEAAJPEAPEAUVDS_REPARSE_POINT_PROP@@PEAJ@Z`
- size: `1588`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this, struct VDS_REPARSE_POINT_PROP **, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140006a80`
- `0x140006e60`
- `0x140023620`
- `0x14002dbd8`
- `0x14002e123`
- `0x14003cd8c`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1400239af`
- `msvcrt!_wcsicmp` at `0x1400239af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002372f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400239d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002372f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400239d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x140023b34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x140023b34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400237ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140023808`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140023af6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140023b7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140023bce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140023bf3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400237ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140023808`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140023af6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140023b7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140023bce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140023bf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023a87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140023953`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140023ba1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140023953`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140023ba1`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14002383a`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14002383a`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14002388d`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14002388d`
- `vdsutil!OpenDevice` at `0x140023910`
- `vdsutil!OpenDevice` at `0x140023910`
- `vdsutil!GetDeviceName` at `0x140023934`
- `vdsutil!GetDeviceName` at `0x140023934`
- `vdsutil!CoFreeStringArray` at `0x140023b78`
- `vdsutil!CoFreeStringArray` at `0x140023b78`
- `vdsutil!VdsHeapAlloc` at `0x140023819`
- `vdsutil!VdsHeapAlloc` at `0x140023819`
- `vdsutil!VdsHeapFree` at `0x1400237fa`
- `vdsutil!VdsHeapFree` at `0x140023b04`
- `vdsutil!VdsHeapFree` at `0x140023b8c`
- `vdsutil!VdsHeapFree` at `0x140023bdc`
- `vdsutil!VdsHeapFree` at `0x140023c01`
- `vdsutil!VdsHeapFree` at `0x1400237fa`
- `vdsutil!VdsHeapFree` at `0x140023b04`
- `vdsutil!VdsHeapFree` at `0x140023b8c`
- `vdsutil!VdsHeapFree` at `0x140023bdc`
- `vdsutil!VdsHeapFree` at `0x140023c01`
- `vdsutil!VdsTraceEx` at `0x140023707`
- `vdsutil!VdsTraceEx` at `0x14002374e`
- `vdsutil!VdsTraceEx` at `0x140023862`
- `vdsutil!VdsTraceEx` at `0x140023a53`
- `vdsutil!VdsTraceEx` at `0x140023a76`
- `vdsutil!VdsTraceEx` at `0x140023abd`
- `vdsutil!VdsTraceEx` at `0x140023ae0`
- `vdsutil!VdsTraceEx` at `0x140023707`
- `vdsutil!VdsTraceEx` at `0x14002374e`
- `vdsutil!VdsTraceEx` at `0x140023862`
- `vdsutil!VdsTraceEx` at `0x140023a53`
- `vdsutil!VdsTraceEx` at `0x140023a76`
- `vdsutil!VdsTraceEx` at `0x140023abd`
- `vdsutil!VdsTraceEx` at `0x140023ae0`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002368e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002368e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400236c4`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140023c22`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400236c4`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140023c22`

## string_xrefs

- `0x140023856`: `CVdsVolume::QueryReparsePoints, 7, error=%ld`
- `0x140023a5e`: `CVdsVolume::QueryReparsePoints, 10, error=%ld`
- `0x140023a67`: `CVdsVolume::QueryReparsePoints, 9, error=%ld`
- `0x140023a92`: `CVdsVolume::QueryReparsePoints, 8, error=%ld`
- `0x14002367b`: `CVdsVolume::QueryReparsePoints()`
- `0x1400236fb`: `CVdsVolume::QueryReparsePoints, 1, hr=%lX`
- `0x140023742`: `CVdsVolume::QueryReparsePoints, 3`
- `0x140023ad4`: `CVdsVolume::QueryReparsePoints, 4`
- `0x140023ab1`: `CVdsVolume::QueryReparsePoints, 5`
- `0x140023aa3`: `CVdsVolume::QueryReparsePoints, 6`
- `0x140023a47`: `CVdsVolume::QueryReparsePoints, 11, hr=%lX`
- `0x140023a3b`: `CVdsVolume::QueryReparsePoints, 12, hr=%lX`
- `0x140023b47`: `CVdsVolume::QueryReparsePoints, 13`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsVolume::QueryReparsePoints(CVdsVolume *this, struct VDS_REPARSE_POINT_PROP **a2, int *a3)
{
  struct VDS_REPARSE_POINT_PROP **v4; // r12
  signed int v6; // ebx
  struct VDS_REPARSE_POINT_PROP *v8; // r14
  WCHAR *v9; // r13
  int v10; // eax
  __int64 v11; // rsi
  int v12; // r15d
  int v13; // eax
  __int64 v14; // r12
  __int64 v15; // rcx
  __int64 v16; // rax
  _WORD *v17; // rdi
  __int64 v18; // rcx
  unsigned __int64 v19; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v21; // rax
  WCHAR *v22; // rax
  DWORD LastError; // eax
  __int64 v24; // rdx
  __int64 v25; // rax
  unsigned __int64 v26; // rcx
  __int64 v27; // rdx
  int v28; // ebx
  int VolumeId; // eax
  __int64 v30; // rax
  __int64 v31; // rcx
  unsigned __int16 *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r10
  HANDLE v35; // rax
  HANDLE v36; // rax
  int i; // r15d
  LPWSTR pwszPath; // rbx
  HANDLE v39; // rax
  HANDLE v40; // rax
  int v41; // [rsp+20h] [rbp-E0h] BYREF
  struct VDS_REPARSE_POINT_PROP **v42; // [rsp+28h] [rbp-D8h]
  _QWORD *v43; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  int v45; // [rsp+40h] [rbp-C0h]
  int *v46; // [rsp+48h] [rbp-B8h]
  __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  int v48; // [rsp+58h] [rbp-A8h]
  _BYTE v49[16]; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID v50; // [rsp+70h] [rbp-90h] BYREF
  WCHAR szVolumeName[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v52[280]; // [rsp+290h] [rbp+190h] BYREF

  v46 = a3;
  v4 = a2;
  v42 = a2;
  v41 = 0;
  v43 = 0;
  hObject = 0;
  v50 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v49, 0x5Eu, "CVdsVolume::QueryReparsePoints()");
  *a3 = 0;
  *v4 = 0;
  v47 = 0;
  v48 = 0;
  v6 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v47);
  if ( v6 >= 0 )
  {
    v8 = 0;
    v9 = 0;
    v10 = (*(__int64 (__fastcall **)(CVdsVolume *, _QWORD **, int *))(*(_QWORD *)this + 48LL))(this, &v43, &v41);
    LODWORD(v11) = v10;
    if ( v10 >= 0 )
    {
      if ( v41 )
      {
        v8 = (struct VDS_REPARSE_POINT_PROP *)CoTaskMemAlloc(24LL * v41);
        if ( v8 )
        {
          v12 = 0;
          memset_0(v8, 0, 24LL * v41);
          v13 = 0;
          v45 = 0;
          while ( v13 < v41 )
          {
            v14 = v13;
            v15 = v43[v13];
            v16 = -1;
            do
              ++v16;
            while ( *(_WORD *)(v15 + 2 * v16) );
            if ( v16 != 3 )
            {
              v17 = (_WORD *)(v15 + 2 * (v16 - 1));
              *v17 = 0;
              do
                --v17;
              while ( *v17 != 92 );
              *v17 = 0;
              v18 = v43[v14];
              if ( !v18 )
              {
                LODWORD(v11) = -2147418113;
                VdsTraceEx(94, 0, "CVdsVolume::QueryReparsePoints, 4");
LABEL_61:
                v4 = v42;
                goto LABEL_68;
              }
              v19 = -1;
              do
                ++v19;
              while ( *(_WORD *)(v18 + 2 * v19) );
              if ( !v19 )
              {
                LODWORD(v11) = -2147418113;
                VdsTraceEx(94, 0, "CVdsVolume::QueryReparsePoints, 5");
LABEL_59:
                v4 = v42;
                goto LABEL_68;
              }
              while ( 1 )
              {
                ProcessHeap = GetProcessHeap();
                VdsHeapFree(ProcessHeap, 0, v9);
                v19 += 128LL;
                v11 = 2 * v19;
                v21 = GetProcessHeap();
                v22 = (WCHAR *)VdsHeapAlloc(v21, 8, 2 * v19);
                v9 = v22;
                if ( !v22 )
                {
                  LODWORD(v11) = -2147024882;
                  VdsTraceEx(94, 0, "CVdsVolume::QueryReparsePoints, 6");
                  goto LABEL_59;
                }
                if ( GetVolumePathNameW((LPCWSTR)v43[v14], v22, v19) )
                  break;
                LastError = GetLastError();
                LODWORD(v11) = LastError;
                if ( LastError != 206 )
                {
                  VdsTraceEx(94, 0, "CVdsVolume::QueryReparsePoints, 7, error=%ld", LastError);
                  goto LABEL_24;
                }
              }
              if ( !GetVolumeNameForVolumeMountPointW(v9, szVolumeName, 0x104u) )
              {
                v11 = GetLastError();
                VdsTraceEx(94, 0, "CVdsVolume::QueryReparsePoints, 8, error=%ld", v11);
LABEL_24:
                if ( (int)v11 > 0 )
                  LODWORD(v11) = (unsigned __int16)v11 | 0x80070000;
                goto LABEL_61;
              }
              v25 = -1;
              do
                ++v25;
              while ( szVolumeName[v25] );
              v26 = 2 * v25 - 2;
              if ( v26 >= 0x208 )
                _report_rangecheckfailure(v26, v24, 0);
              *(WCHAR *)((char *)szVolumeName + v26) = 0;
              *v17 = 92;
              v27 = -1;
              do
                ++v27;
              while ( v9[v27] );
              StringCchCopyNW(v9, v19, (const unsigned __int16 *)(v43[v14] + 2 * (v27 - 1)), v19);
              v28 = 0;
              *(WCHAR *)((char *)v9 + v11 - 2) = 0;
              LODWORD(v11) = OpenDevice(szVolumeName, 0, &hObject);
              if ( (_DWORD)v11 )
              {
                VdsTraceEx(94, 0, "CVdsVolume::QueryReparsePoints, 9, error=%ld", (unsigned int)v11);
                goto LABEL_24;
              }
              LODWORD(v11) = GetDeviceName(hObject, 0, 274, v52);
              if ( (_DWORD)v11 )
              {
                VdsTraceEx(94, 0, "CVdsVolume::QueryReparsePoints, 10, error=%ld", (unsigned int)v11);
                goto LABEL_24;
              }
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(hObject);
                hObject = (HANDLE)-1LL;
              }
              VolumeId = CVdsService::GetVolumeId(v52, &v50, 0);
              LODWORD(v11) = VolumeId;
              if ( VolumeId < 0 )
              {
                VdsTraceEx(94, 0, "CVdsVolume::QueryReparsePoints, 11, hr=%lX", (unsigned int)VolumeId);
                goto LABEL_61;
              }
              if ( v12 <= 0 )
              {
LABEL_43:
                v31 = -1;
                do
                  ++v31;
                while ( v9[v31] );
                v32 = (unsigned __int16 *)CoTaskMemAlloc(2 * v31 + 2);
                v8[v28].pwszPath = v32;
                if ( !v32 )
                {
                  LODWORD(v11) = -2147024882;
                  VdsTraceEx(94, 0, "CVdsVolume::QueryReparsePoints, 12, hr=%lX", 2147942414LL);
                  goto LABEL_61;
                }
                v33 = -1;
                do
                  ++v33;
                while ( v9[v33] );
                StringCchCopyW(v32, v33 + 1, v9);
                *(struct _GUID *)((char *)&v8->SourceVolumeId + 8 * v34) = v50;
                ++v12;
              }
              else
              {
                while ( 1 )
                {
                  v30 = *(_QWORD *)&v8[v28].SourceVolumeId.Data1 - *(_QWORD *)&v50.Data1;
                  if ( !v30 )
                    v30 = *(_QWORD *)v8[v28].SourceVolumeId.Data4 - *(_QWORD *)v50.Data4;
                  if ( !v30 && !_wcsicmp(v8[v28].pwszPath, v9) )
                    break;
                  if ( ++v28 >= v12 )
                    goto LABEL_43;
                }
              }
            }
            v13 = ++v45;
          }
          if ( v12 )
          {
            if ( v12 < v41 )
            {
              v8 = (struct VDS_REPARSE_POINT_PROP *)CoTaskMemRealloc(v8, 24LL * v12);
              if ( !v8 )
              {
                LODWORD(v11) = -2147024882;
                VdsTraceEx(94, 0, "CVdsVolume::QueryReparsePoints, 13");
                goto LABEL_61;
              }
            }
            *v46 = v12;
            v4 = v42;
            *v42 = v8;
          }
          else
          {
            LODWORD(v11) = 1;
            v35 = GetProcessHeap();
            VdsHeapFree(v35, 0, v8);
            v8 = 0;
            *v46 = 0;
            v4 = v42;
            *v42 = 0;
          }
        }
        else
        {
          LODWORD(v11) = -2147024882;
          VdsTraceEx(94, 0, "CVdsVolume::QueryReparsePoints, 3");
        }
      }
      else
      {
        LODWORD(v11) = 1;
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsVolume::QueryReparsePoints, 1, hr=%lX", v10);
    }
LABEL_68:
    if ( v43 && *v43 && v41 )
      CoFreeStringArray();
    v36 = GetProcessHeap();
    VdsHeapFree(v36, 0, v9);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
    if ( (int)v11 < 0 )
    {
      if ( v8 )
      {
        for ( i = 0; i < v41; ++i )
        {
          pwszPath = v8[i].pwszPath;
          v39 = GetProcessHeap();
          VdsHeapFree(v39, 0, pwszPath);
          v8[i].pwszPath = 0;
        }
      }
      v40 = GetProcessHeap();
      VdsHeapFree(v40, 0, v8);
      *v46 = 0;
      *v4 = 0;
    }
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v47);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v49);
    return (unsigned int)v11;
  }
  else
  {
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v47);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v49);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x140023620  mov     [rsp-8+arg_18], rbx
0x140023625  push    rbp
0x140023626  push    rsi
0x140023627  push    rdi
0x140023628  push    r12
0x14002362a  push    r13
0x14002362c  push    r14
0x14002362e  push    r15
0x140023630  lea     rbp, [rsp-3D0h]
0x140023638  sub     rsp, 4D0h
0x14002363f  mov     rax, cs:__security_cookie
0x140023646  xor     rax, rsp
0x140023649  mov     [rbp+400h+var_40], rax
0x140023650  mov     rbx, r8
0x140023653  mov     [rsp+500h+var_4B8], rbx
0x140023658  mov     r12, rdx
0x14002365b  mov     [rsp+500h+var_4D8], rdx
0x140023660  mov     rdi, rcx
0x140023663  xor     esi, esi
0x140023665  mov     [rsp+500h+var_4E0], esi
0x140023669  mov     [rsp+500h+var_4D0], rsi
0x14002366e  mov     [rsp+500h+hObject], rsi
0x140023673  xorps   xmm0, xmm0
0x140023676  movups  xmmword ptr [rsp+500h+var_490.Data1], xmm0
0x14002367b  lea     r8, aCvdsvolumeQuer_42; "CVdsVolume::QueryReparsePoints()"
0x140023682  lea     r15d, [rsi+5Eh]
0x140023686  mov     edx, r15d
0x140023689  lea     rcx, [rsp+500h+var_4A0]
0x14002368e  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140023694  nop
0x140023695  mov     [rbx], esi
0x140023697  mov     [r12], rsi
0x14002369b  mov     [rsp+500h+var_4B0], rsi
0x1400236a0  mov     [rsp+500h+var_4A8], esi
0x1400236a4  lea     rcx, [rsp+500h+var_4B0]; this
0x1400236a9  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x1400236ae  mov     ebx, eax
0x1400236b0  test    eax, eax
0x1400236b2  jns     short loc_1400236D1
0x1400236b4  lea     rcx, [rsp+500h+var_4B0]; this
0x1400236b9  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400236be  nop
0x1400236bf  lea     rcx, [rsp+500h+var_4A0]
0x1400236c4  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400236ca  mov     eax, ebx
0x1400236cc  jmp     loc_140023C2A
0x1400236d1  xor     ebx, ebx
0x1400236d3  mov     r14d, ebx
0x1400236d6  mov     r13d, ebx
0x1400236d9  mov     rax, [rdi]
0x1400236dc  lea     r8, [rsp+500h+var_4E0]
0x1400236e1  lea     rdx, [rsp+500h+var_4D0]
0x1400236e6  mov     rcx, rdi
0x1400236e9  mov     rax, [rax+30h]
0x1400236ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400236f2  mov     esi, eax
0x1400236f4  test    eax, eax
0x1400236f6  jns     short loc_140023712
0x1400236f8  mov     r9d, eax
0x1400236fb  lea     r8, aCvdsvolumeQuer_15; "CVdsVolume::QueryReparsePoints, 1, hr=%"...
0x140023702  xor     edx, edx
0x140023704  mov     ecx, r15d
0x140023707  call    cs:__imp_VdsTraceEx
0x14002370d  jmp     loc_140023B61
0x140023712  cmp     [rsp+500h+var_4E0], ebx
0x140023716  jnz     short loc_140023722
0x140023718  mov     esi, 1
0x14002371d  jmp     loc_140023B61
0x140023722  movsxd  rax, [rsp+500h+var_4E0]
0x140023727  lea     rcx, [rax+rax*2]
0x14002372b  shl     rcx, 3; cb
0x14002372f  call    cs:__imp_CoTaskMemAlloc
0x140023735  mov     r14, rax
0x140023738  test    rax, rax
0x14002373b  jnz     short loc_140023759
0x14002373d  mov     esi, 8007000Eh
0x140023742  lea     r8, aCvdsvolumeQuer_1; "CVdsVolume::QueryReparsePoints, 3"
0x140023749  xor     edx, edx
0x14002374b  mov     ecx, r15d
0x14002374e  call    cs:__imp_VdsTraceEx
0x140023754  jmp     loc_140023B61
0x140023759  mov     r15d, ebx
0x14002375c  movsxd  rax, [rsp+500h+var_4E0]
0x140023761  lea     r8, [rax+rax*2]
0x140023765  shl     r8, 3; Size
0x140023769  xor     edx, edx; Val
0x14002376b  mov     rcx, r14; void *
0x14002376e  call    memset_0
0x140023773  mov     eax, ebx
0x140023775  mov     [rsp+500h+var_4C0], ebx
0x140023779  mov     edx, 5Ch ; '\'
0x14002377e  cmp     eax, [rsp+500h+var_4E0]
0x140023782  jge     loc_140023AED
0x140023788  movsxd  r12, eax
0x14002378b  mov     rax, [rsp+500h+var_4D0]
0x140023790  mov     rcx, [rax+r12*8]
0x140023794  or      rax, 0FFFFFFFFFFFFFFFFh
0x140023798  inc     rax
0x14002379b  cmp     [rcx+rax*2], bx
0x14002379f  jnz     short loc_140023798
0x1400237a1  cmp     rax, 3
0x1400237a5  jz      loc_140023A20
0x1400237ab  lea     rdi, [rax-1]
0x1400237af  lea     rdi, [rcx+rdi*2]
0x1400237b3  mov     [rdi], bx
0x1400237b6  lea     rdi, [rdi-2]
0x1400237ba  cmp     [rdi], dx
0x1400237bd  jnz     short loc_1400237B6
0x1400237bf  mov     [rdi], bx
0x1400237c2  mov     rax, [rsp+500h+var_4D0]
0x1400237c7  mov     rcx, [rax+r12*8]
0x1400237cb  test    rcx, rcx
0x1400237ce  jz      loc_140023ACF
0x1400237d4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400237d8  xor     eax, eax
0x1400237da  inc     rbx
0x1400237dd  cmp     [rcx+rbx*2], ax
0x1400237e1  jnz     short loc_1400237DA
0x1400237e3  test    rbx, rbx
0x1400237e6  jz      loc_140023AAC
0x1400237ec  call    cs:__imp_GetProcessHeap
0x1400237f2  mov     rcx, rax
0x1400237f5  mov     r8, r13
0x1400237f8  xor     edx, edx
0x1400237fa  call    cs:__imp_VdsHeapFree
0x140023800  sub     rbx, 0FFFFFFFFFFFFFF80h
0x140023804  lea     rsi, [rbx+rbx]
0x140023808  call    cs:__imp_GetProcessHeap
0x14002380e  mov     rcx, rax
0x140023811  mov     r8, rsi
0x140023814  mov     edx, 8
0x140023819  call    cs:__imp_VdsHeapAlloc
0x14002381f  mov     r13, rax
0x140023822  test    rax, rax
0x140023825  jz      loc_140023A9E
0x14002382b  mov     r8d, ebx; cchBufferLength
0x14002382e  mov     rdx, rax; lpszVolumePathName
0x140023831  mov     rcx, [rsp+500h+var_4D0]
0x140023836  mov     rcx, [rcx+r12*8]; lpszFileName
0x14002383a  call    cs:__imp_GetVolumePathNameW
0x140023840  test    eax, eax
0x140023842  jnz     short loc_140023880
0x140023844  call    cs:__imp_GetLastError
0x14002384a  mov     esi, eax
0x14002384c  cmp     eax, 0CEh
0x140023851  jz      short loc_1400237EC
0x140023853  mov     r9d, eax
0x140023856  lea     r8, aCvdsvolumeQuer_33; "CVdsVolume::QueryReparsePoints, 7, erro"...
0x14002385d  xor     edx, edx
0x14002385f  lea     ecx, [rdx+5Eh]
0x140023862  call    cs:__imp_VdsTraceEx
0x140023868  xor     ebx, ebx
0x14002386a  test    esi, esi
0x14002386c  jle     loc_140023AE6
0x140023872  movzx   esi, si
0x140023875  or      esi, 80070000h
0x14002387b  jmp     loc_140023AE6
0x140023880  mov     r8d, 104h; cchBufferLength
0x140023886  lea     rdx, [rbp+400h+szVolumeName]; lpszVolumeName
0x14002388a  mov     rcx, r13; lpszVolumeMountPoint
0x14002388d  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x140023893  xor     r8d, r8d
0x140023896  test    eax, eax
0x140023898  jz      loc_140023A87
0x14002389e  lea     rcx, [rbp+400h+szVolumeName]
0x1400238a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400238a6  inc     rax
0x1400238a9  cmp     [rcx+rax*2], r8w
0x1400238ae  jnz     short loc_1400238A6
0x1400238b0  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x1400238b8  cmp     rcx, 208h
0x1400238bf  jnb     loc_140023A81
0x1400238c5  mov     [rbp+rcx+400h+szVolumeName], r8w
0x1400238cb  mov     word ptr [rdi], 5Ch ; '\'
0x1400238d0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400238d4  inc     rdx
0x1400238d7  cmp     [r13+rdx*2+0], r8w
0x1400238dd  jnz     short loc_1400238D4
0x1400238df  mov     rax, [rsp+500h+var_4D0]
0x1400238e4  mov     rcx, [rax+r12*8]
0x1400238e8  dec     rdx
0x1400238eb  lea     r8, [rcx+rdx*2]; unsigned __int16 *
0x1400238ef  mov     r9, rbx; unsigned __int64
0x1400238f2  mov     rdx, rbx; unsigned __int64
0x1400238f5  mov     rcx, r13; unsigned __int16 *
0x1400238f8  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1400238fd  xor     ebx, ebx
0x1400238ff  mov     [rsi+r13-2], bx
0x140023905  lea     r8, [rsp+500h+hObject]
0x14002390a  xor     edx, edx
0x14002390c  lea     rcx, [rbp+400h+szVolumeName]
0x140023910  call    cs:__imp_OpenDevice
0x140023916  mov     esi, eax
0x140023918  test    eax, eax
0x14002391a  jnz     loc_140023A67
0x140023920  lea     r9, [rbp+400h+var_270]
0x140023927  xor     edx, edx
0x140023929  mov     r8d, 112h
0x14002392f  mov     rcx, [rsp+500h+hObject]
0x140023934  call    cs:__imp_GetDeviceName
0x14002393a  mov     esi, eax
0x14002393c  test    eax, eax
0x14002393e  jnz     loc_140023A5E
0x140023944  mov     rcx, [rsp+500h+hObject]; hObject
0x140023949  lea     rax, [rcx-1]
0x14002394d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140023951  ja      short loc_140023962
0x140023953  call    cs:__imp_CloseHandle
0x140023959  mov     [rsp+500h+hObject], 0FFFFFFFFFFFFFFFFh
0x140023962  xor     r8d, r8d; int *
0x140023965  lea     rdx, [rsp+500h+var_490]; struct _GUID *
0x14002396a  lea     rcx, [rbp+400h+var_270]; unsigned __int16 *
0x140023971  call    ?GetVolumeId@CVdsService@@SAJPEAGPEAU_GUID@@PEAH@Z; CVdsService::GetVolumeId(ushort *,_GUID *,int *)
0x140023976  mov     esi, eax
0x140023978  test    eax, eax
0x14002397a  js      loc_140023A44
0x140023980  xor     edi, edi
0x140023982  test    r15d, r15d
0x140023985  jle     short loc_1400239C0
0x140023987  mov     eax, ebx
0x140023989  lea     rcx, [rax+rax*2]
0x14002398d  mov     rax, [r14+rcx*8]
0x140023991  sub     rax, qword ptr [rsp+500h+var_490.Data1]
0x140023996  jnz     short loc_1400239A2
0x140023998  mov     rax, [r14+rcx*8+8]
0x14002399d  sub     rax, qword ptr [rsp+500h+var_490.Data4]
0x1400239a2  test    rax, rax
0x1400239a5  jnz     short loc_1400239B9
0x1400239a7  mov     rdx, r13; String2
0x1400239aa  mov     rcx, [r14+rcx*8+10h]; String1
0x1400239af  call    cs:__imp__wcsicmp
0x1400239b5  test    eax, eax
0x1400239b7  jz      short loc_140023A2F
0x1400239b9  inc     ebx
0x1400239bb  cmp     ebx, r15d
0x1400239be  jl      short loc_140023987
0x1400239c0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400239c4  inc     rcx
0x1400239c7  cmp     [r13+rcx*2+0], di
0x1400239cd  jnz     short loc_1400239C4
0x1400239cf  lea     rcx, ds:2[rcx*2]; cb
0x1400239d7  call    cs:__imp_CoTaskMemAlloc
0x1400239dd  movsxd  rcx, ebx
0x1400239e0  lea     r10, [rcx+rcx*2]
0x1400239e4  mov     [r14+r10*8+10h], rax
0x1400239e9  xor     ebx, ebx
0x1400239eb  test    rax, rax
0x1400239ee  jz      short loc_140023A33
0x1400239f0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400239f4  inc     rdx
0x1400239f7  cmp     [r13+rdx*2+0], bx
0x1400239fd  jnz     short loc_1400239F4
0x1400239ff  inc     rdx; unsigned __int64
0x140023a02  mov     r8, r13; unsigned __int16 *
0x140023a05  mov     rcx, rax; unsigned __int16 *
0x140023a08  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140023a0d  movups  xmm0, xmmword ptr [rsp+500h+var_490.Data1]
0x140023a12  movdqu  xmmword ptr [r14+r10*8], xmm0
0x140023a18  inc     r15d
0x140023a1b  mov     edx, 5Ch ; '\'
0x140023a20  mov     eax, [rsp+500h+var_4C0]
0x140023a24  inc     eax
0x140023a26  mov     [rsp+500h+var_4C0], eax
0x140023a2a  jmp     loc_14002377E
0x140023a2f  xor     ebx, ebx
0x140023a31  jmp     short loc_140023A1B
0x140023a33  mov     esi, 8007000Eh
0x140023a38  mov     r9d, esi
0x140023a3b  lea     r8, aCvdsvolumeQuer_29; "CVdsVolume::QueryReparsePoints, 12, hr="...
0x140023a42  jmp     short loc_140023A4E
0x140023a44  mov     r9d, eax
0x140023a47  lea     r8, aCvdsvolumeQuer_9; "CVdsVolume::QueryReparsePoints, 11, hr="...
0x140023a4e  xor     edx, edx
0x140023a50  lea     ecx, [rdx+5Eh]
0x140023a53  call    cs:__imp_VdsTraceEx
0x140023a59  jmp     loc_140023AE6
0x140023a5e  lea     r8, aCvdsvolumeQuer_16; "CVdsVolume::QueryReparsePoints, 10, err"...
0x140023a65  jmp     short loc_140023A6E
0x140023a67  lea     r8, aCvdsvolumeQuer; "CVdsVolume::QueryReparsePoints, 9, erro"...
0x140023a6e  mov     r9d, esi
0x140023a71  xor     edx, edx
0x140023a73  lea     ecx, [rdx+5Eh]
0x140023a76  call    cs:__imp_VdsTraceEx
0x140023a7c  jmp     loc_14002386A
0x140023a81  call    __report_rangecheckfailure
0x140023a87  call    cs:__imp_GetLastError
0x140023a8d  mov     esi, eax
0x140023a8f  mov     r9d, eax
0x140023a92  lea     r8, aCvdsvolumeQuer_30; "CVdsVolume::QueryReparsePoints, 8, erro"...
0x140023a99  jmp     loc_14002385D
0x140023a9e  mov     esi, 8007000Eh
0x140023aa3  lea     r8, aCvdsvolumeQuer_14; "CVdsVolume::QueryReparsePoints, 6"
0x140023aaa  jmp     short loc_140023AB8
0x140023aac  mov     esi, 8000FFFFh
0x140023ab1  lea     r8, aCvdsvolumeQuer_41; "CVdsVolume::QueryReparsePoints, 5"
0x140023ab8  xor     edx, edx
0x140023aba  lea     ecx, [rdx+5Eh]
0x140023abd  call    cs:__imp_VdsTraceEx
0x140023ac3  mov     r12, [rsp+500h+var_4D8]
0x140023ac8  xor     ebx, ebx
  ... truncated ...
```
