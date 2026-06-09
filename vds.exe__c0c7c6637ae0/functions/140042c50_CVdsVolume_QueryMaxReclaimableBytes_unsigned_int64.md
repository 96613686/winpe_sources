# CVdsVolume::QueryMaxReclaimableBytes(unsigned __int64 *)

- ea: `0x140042c50`
- end: `0x140043135`
- name: `?QueryMaxReclaimableBytes@CVdsVolume@@UEAAJPEA_K@Z`
- size: `1253`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140009990`
- `0x140012c48`
- `0x140013298`
- `0x14002e123`
- `0x140040b54`
- `0x140042c50`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140042e39`
- `msvcrt!_wcsnicmp` at `0x140042e5d`
- `msvcrt!_wcsnicmp` at `0x140043029`
- `msvcrt!_wcsnicmp` at `0x140042e39`
- `msvcrt!_wcsnicmp` at `0x140042e5d`
- `msvcrt!_wcsnicmp` at `0x140043029`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140042ec9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140042ec9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140042e80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140042e80`
- `ntdll!NtQueryVolumeInformationFile` at `0x140042daf`
- `ntdll!NtQueryVolumeInformationFile` at `0x140042daf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140042ea4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140042ea4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400430dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400430dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140043069`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004308f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140043069`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004308f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140042e13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140042e70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400430ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140042e13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140042e70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400430ad`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140042f22`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140042f22`
- `vdsutil!GetFileSystemRecognitionName` at `0x140043041`
- `vdsutil!GetFileSystemRecognitionName` at `0x140043041`
- `vdsutil!VdsHeapFree` at `0x140043077`
- `vdsutil!VdsHeapFree` at `0x14004309d`
- `vdsutil!VdsHeapFree` at `0x140043077`
- `vdsutil!VdsHeapFree` at `0x14004309d`
- `vdsutil!VdsTraceEx` at `0x140042d8d`
- `vdsutil!VdsTraceEx` at `0x140042dca`
- `vdsutil!VdsTraceEx` at `0x140042e08`
- `vdsutil!VdsTraceEx` at `0x140042ebf`
- `vdsutil!VdsTraceEx` at `0x140042d8d`
- `vdsutil!VdsTraceEx` at `0x140042dca`
- `vdsutil!VdsTraceEx` at `0x140042e08`
- `vdsutil!VdsTraceEx` at `0x140042ebf`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140042cf5`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140042cf5`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140042d26`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400430f7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140042d26`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400430f7`
- `vdsutil!VdsTraceW` at `0x140043059`
- `vdsutil!VdsTraceW` at `0x140043059`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVdsVolume::QueryMaxReclaimableBytes(CVdsVolume *this, unsigned __int64 *a2)
{
  __int64 v4; // rdx
  signed int v5; // edi
  int v6; // eax
  CVdsVolume *v7; // rcx
  int v8; // eax
  NTSTATUS v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  HRESULT v12; // eax
  const char *v13; // r8
  int v14; // ebx
  __int64 v15; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v17; // rbx
  HANDLE v18; // rax
  ULONGLONG v19; // rax
  HANDLE FileHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+58h] [rbp-A8h]
  __int128 v27; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[16]; // [rsp+70h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-80h] BYREF
  struct _VDS_VOLUME_PROP v30; // [rsp+90h] [rbp-70h] BYREF
  __int128 v31; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE FsInformation[8]; // [rsp+E0h] [rbp-20h] BYREF
  int v33; // [rsp+E8h] [rbp-18h]
  wchar_t String1[42]; // [rsp+ECh] [rbp-14h] BYREF
  _BYTE v35[216]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v36; // [rsp+218h] [rbp+118h]

  ppv = 0;
  memset(&v30, 0, sizeof(v30));
  FileHandle = 0;
  v31 = 0;
  memset_0(v35, 0, 0x280u);
  v24 = 0;
  v22 = 0;
  memset_0(FsInformation, 0, 0x60u);
  IoStatusBlock = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v28, 0x5Eu, "CVdsVolume::QueryMaxReclaimableBytes()");
  v25 = 0;
  v26 = 0;
  v5 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v25);
  if ( v5 < 0 )
  {
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v25);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
    goto LABEL_56;
  }
  *a2 = 0;
  v6 = CVdsVolume::OpenHandle((CVdsVolume *)((char *)this - 16), v4, &FileHandle, &v30);
  v5 = v6;
  if ( v6 < 0 )
  {
    if ( v6 == -2147212270 )
      v5 = -2147211942;
    goto LABEL_53;
  }
  v8 = CVdsVolume::CheckFVEStatus(v7, v30.pwszName, 1);
  v5 = v8;
  if ( v8 == -2144272310 )
  {
    VdsTraceEx(
      94,
      1,
      "CVdsVolume::QueryMaxReclaimableBytes(), BITLOCKER NOT ON STACK (expected for CDROMS), hr=%lX",
      -2144272310);
  }
  else if ( v8 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::QueryMaxReclaimableBytes(), 1.5, hr=%lX", v8);
    goto LABEL_12;
  }
  v9 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, FsInformation, 0x60u, FileFsAttributeInformation);
  v10 = v9;
  if ( v9 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::QueryMaxReclaimableBytes(), 2, NtQueryVolumeInformationFile failed: %X", v9);
    VdsLogError(0xC2000001, 0, 0, v10, 0x20A001Au, 0);
    v5 = v10 | 0x10000000;
LABEL_12:
    CloseHandle(FileHandle);
    goto LABEL_53;
  }
  v11 = v33;
  if ( v33 == 8 )
  {
    if ( !_wcsnicmp(String1, L"NTFS", 4u) )
      goto LABEL_18;
    v11 = v33;
  }
  if ( v11 == 10 )
  {
    if ( !_wcsnicmp(String1, L"CSVFS", 5u) )
    {
LABEL_18:
      CloseHandle(FileHandle);
      EnterCriticalSection(&g_GlobalCriticalSection);
      v12 = CoCreateInstance(&CLSID_CDefragEngine, 0, 4u, &IID_IDefragEngine, &ppv);
      v5 = v12;
      if ( v12 >= 0 )
      {
        v14 = 0;
        while ( 1 )
        {
          v5 = (*(__int64 (__fastcall **)(LPVOID, LPWSTR, __int128 *))(*(_QWORD *)ppv + 72LL))(ppv, v30.pwszName, &v31);
          if ( v5 != 1 )
            break;
          v27 = v31;
          v12 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)ppv + 40LL))(ppv, &v27);
          v5 = v12;
          if ( v12 < 0 )
          {
            v13 = "CVdsVolume::QueryMaxReclaimableBytes(), 4 hr=%lX";
            goto LABEL_20;
          }
          Sleep(0x1F4u);
          if ( (unsigned int)++v14 >= 0xA )
          {
            v5 = -2147211887;
            goto LABEL_21;
          }
        }
        if ( v5 < 0 )
        {
          if ( v5 == -1996488683 )
            v5 = -2147211878;
          VdsTraceEx(94, 0, "CVdsVolume::QueryMaxReclaimableBytes(), 5 hr=%lX", (unsigned int)v5);
          goto LABEL_21;
        }
        v27 = v31;
        v12 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, int *))(*(_QWORD *)ppv + 160LL))(ppv, &v27, &v24);
        v5 = v12;
        if ( v12 >= 0 )
        {
          v5 = v24;
          if ( v24 < 0 )
          {
            if ( v24 == -1996488683 )
            {
              v5 = -2147211878;
            }
            else if ( v24 == -1996488698 )
            {
              v5 = -2147211879;
            }
            VdsTraceEx(94, 0, "CVdsVolume::QueryMaxReclaimableBytes(), 7 hr=%lX", (unsigned int)v5);
            goto LABEL_21;
          }
          v12 = (*(__int64 (__fastcall **)(LPVOID, LPWSTR, _BYTE *))(*(_QWORD *)ppv + 136LL))(ppv, v30.pwszName, v35);
          v5 = v12;
          if ( v12 >= 0 )
          {
            *a2 = v36;
            goto LABEL_21;
          }
          v13 = "CVdsVolume::QueryMaxReclaimableBytes(), 8 hr=%lX";
        }
        else
        {
          v13 = "CVdsVolume::QueryMaxReclaimableBytes(), 6 hr=%lX";
        }
      }
      else
      {
        v13 = "CVdsVolume::QueryMaxReclaimableBytes(), 3 hr=%lX";
      }
LABEL_20:
      VdsTraceEx(94, 0, v13, (unsigned int)v12);
LABEL_21:
      LeaveCriticalSection(&g_GlobalCriticalSection);
      goto LABEL_53;
    }
    v11 = v33;
  }
  if ( v11 != 6 || _wcsnicmp(String1, L"RAW", 3u) )
  {
    v5 = -2147212002;
    goto LABEL_53;
  }
  if ( (int)GetFileSystemRecognitionName(FileHandle, &v22) >= 0 )
  {
    VdsTraceW(
      0,
      L"CVdsVolume::QueryMaxReclaimableBytes(), 9: Unknown file system, do not support shrink. File system name=%s",
      v22);
    v5 = -2147210966;
    v15 = v22;
    ProcessHeap = GetProcessHeap();
    VdsHeapFree(ProcessHeap, 0, v15);
    v22 = 0;
    goto LABEL_12;
  }
  v5 = 0;
  v17 = v22;
  v18 = GetProcessHeap();
  VdsHeapFree(v18, 0, v17);
  v22 = 0;
  CloseHandle(FileHandle);
  if ( v30.ullSize > 0x100000 )
    v19 = v30.ullSize - 0x100000;
  else
    v19 = 0;
  *a2 = v19;
LABEL_53:
  if ( v30.pwszName )
  {
    CoTaskMemFree(v30.pwszName);
    v30.pwszName = 0;
  }
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v25);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
LABEL_56:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140042c50  mov     [rsp-8+arg_10], rbx
0x140042c55  mov     [rsp-8+arg_18], rsi
0x140042c5a  push    rbp
0x140042c5b  push    rdi
0x140042c5c  push    r12
0x140042c5e  push    r14
0x140042c60  push    r15
0x140042c62  lea     rbp, [rsp-2D0h]
0x140042c6a  sub     rsp, 3D0h
0x140042c71  mov     rax, cs:__security_cookie
0x140042c78  xor     rax, rsp
0x140042c7b  mov     [rbp+2F0h+var_28], rax
0x140042c82  mov     rsi, rdx
0x140042c85  mov     rbx, rcx
0x140042c88  xor     r14d, r14d
0x140042c8b  mov     [rsp+3F0h+ppv], r14
0x140042c90  mov     [rbp+2F0h+var_360.id.Data1], r14d
0x140042c94  xorps   xmm0, xmm0
0x140042c97  xor     eax, eax
0x140042c99  movups  xmmword ptr [rbp+2F0h+var_360.id.Data2], xmm0
0x140042c9d  movups  xmmword ptr [rbp+2F0h+var_360.status], xmm0
0x140042ca1  movups  xmmword ptr [rbp+2F0h+var_360.ullSize+4], xmm0
0x140042ca5  mov     dword ptr [rbp+2F0h+var_360.pwszName+4], eax
0x140042ca8  mov     [rsp+3F0h+FileHandle], r14
0x140042cad  movups  [rbp+2F0h+var_320], xmm0
0x140042cb1  xor     edx, edx; Val
0x140042cb3  mov     r8d, 280h; Size
0x140042cb9  lea     rcx, [rbp+2F0h+var_2B0]; void *
0x140042cbd  call    memset_0
0x140042cc2  mov     [rsp+3F0h+var_3A8], r14d
0x140042cc7  mov     [rsp+3F0h+var_3B8], r14
0x140042ccc  xor     edx, edx; Val
0x140042cce  lea     r8d, [r14+60h]; Size
0x140042cd2  lea     rcx, [rbp+2F0h+FsInformation]; void *
0x140042cd6  call    memset_0
0x140042cdb  xorps   xmm0, xmm0
0x140042cde  movups  xmmword ptr [rbp+2F0h+IoStatusBlock], xmm0
0x140042ce2  lea     r8, aCvdsvolumeQuer_18; "CVdsVolume::QueryMaxReclaimableBytes()"
0x140042ce9  lea     r12d, [r14+5Eh]
0x140042ced  mov     edx, r12d
0x140042cf0  lea     rcx, [rsp+3F0h+var_380]
0x140042cf5  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140042cfb  nop
0x140042cfc  mov     [rsp+3F0h+var_3A0], r14
0x140042d01  mov     [rsp+3F0h+var_398], r14d
0x140042d06  lea     rcx, [rsp+3F0h+var_3A0]; this
0x140042d0b  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140042d10  mov     edi, eax
0x140042d12  test    eax, eax
0x140042d14  jns     short loc_140042D32
0x140042d16  lea     rcx, [rsp+3F0h+var_3A0]; this
0x140042d1b  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140042d20  nop
0x140042d21  lea     rcx, [rsp+3F0h+var_380]
0x140042d26  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140042d2c  nop
0x140042d2d  jmp     loc_1400430FE
0x140042d32  mov     [rsi], r14
0x140042d35  lea     rcx, [rbx-10h]; this
0x140042d39  lea     r9, [rbp+2F0h+var_360]; struct _VDS_VOLUME_PROP *
0x140042d3d  lea     r8, [rsp+3F0h+FileHandle]; void **
0x140042d42  call    ?OpenHandle@CVdsVolume@@QEAAJKPEAPEAXPEAU_VDS_VOLUME_PROP@@@Z; CVdsVolume::OpenHandle(ulong,void * *,_VDS_VOLUME_PROP *)
0x140042d47  mov     edi, eax
0x140042d49  test    eax, eax
0x140042d4b  jns     short loc_140042D62
0x140042d4d  cmp     eax, 80042412h
0x140042d52  jnz     loc_1400430D4
0x140042d58  mov     edi, 8004255Ah
0x140042d5d  jmp     loc_1400430D4
0x140042d62  mov     r8d, 1; int
0x140042d68  mov     rdx, [rbp+2F0h+var_360.pwszName]; unsigned __int16 *
0x140042d6c  call    ?CheckFVEStatus@CVdsVolume@@AEAAJQEAGH@Z; CVdsVolume::CheckFVEStatus(ushort * const,int)
0x140042d71  mov     edi, eax
0x140042d73  mov     r9d, 8031004Ah
0x140042d79  cmp     eax, r9d
0x140042d7c  jnz     short loc_140042DF5
0x140042d7e  lea     r8, aCvdsvolumeQuer_37; "CVdsVolume::QueryMaxReclaimableBytes(),"...
0x140042d85  mov     edx, 1
0x140042d8a  mov     ecx, r12d
0x140042d8d  call    cs:__imp_VdsTraceEx
0x140042d93  mov     r15d, 5
0x140042d99  mov     [rsp+3F0h+FsInformationClass], r15d; FsInformationClass
0x140042d9e  lea     r9d, [r15+5Bh]; Length
0x140042da2  lea     r8, [rbp+2F0h+FsInformation]; FsInformation
0x140042da6  lea     rdx, [rbp+2F0h+IoStatusBlock]; IoStatusBlock
0x140042daa  mov     rcx, [rsp+3F0h+FileHandle]; FileHandle
0x140042daf  call    cs:__imp_NtQueryVolumeInformationFile
0x140042db5  mov     edi, eax
0x140042db7  test    eax, eax
0x140042db9  jz      short loc_140042E1E
0x140042dbb  mov     r9d, eax
0x140042dbe  lea     r8, aCvdsvolumeQuer_26; "CVdsVolume::QueryMaxReclaimableBytes(),"...
0x140042dc5  xor     edx, edx
0x140042dc7  mov     ecx, r12d
0x140042dca  call    cs:__imp_VdsTraceEx
0x140042dd0  mov     [rsp+3F0h+var_3C8], r14; unsigned __int16 *
0x140042dd5  mov     [rsp+3F0h+FsInformationClass], 20A001Ah; unsigned int
0x140042ddd  mov     r9d, edi; unsigned int
0x140042de0  xor     r8d, r8d; void *
0x140042de3  xor     edx, edx; unsigned int
0x140042de5  mov     ecx, 0C2000001h; unsigned int
0x140042dea  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140042def  bts     edi, 1Ch
0x140042df3  jmp     short loc_140042E0E
0x140042df5  test    eax, eax
0x140042df7  jns     short loc_140042D93
0x140042df9  mov     r9d, eax
0x140042dfc  lea     r8, aCvdsvolumeQuer_10; "CVdsVolume::QueryMaxReclaimableBytes(),"...
0x140042e03  xor     edx, edx
0x140042e05  mov     ecx, r12d
0x140042e08  call    cs:__imp_VdsTraceEx
0x140042e0e  mov     rcx, [rsp+3F0h+FileHandle]; hObject
0x140042e13  call    cs:__imp_CloseHandle
0x140042e19  jmp     loc_1400430D4
0x140042e1e  mov     ebx, 4
0x140042e23  mov     eax, [rbp+2F0h+var_308]
0x140042e26  cmp     eax, 8
0x140042e29  jnz     short loc_140042E46
0x140042e2b  mov     r8d, ebx; MaxCount
0x140042e2e  lea     rdx, aNtfs; "NTFS"
0x140042e35  lea     rcx, [rbp+2F0h+String1]; String1
0x140042e39  call    cs:__imp__wcsnicmp
0x140042e3f  test    eax, eax
0x140042e41  jz      short loc_140042E6B
0x140042e43  mov     eax, [rbp+2F0h+var_308]
0x140042e46  cmp     eax, 0Ah
0x140042e49  jnz     loc_140043011
0x140042e4f  mov     r8, r15; MaxCount
0x140042e52  lea     rdx, aCsvfs; "CSVFS"
0x140042e59  lea     rcx, [rbp+2F0h+String1]; String1
0x140042e5d  call    cs:__imp__wcsnicmp
0x140042e63  test    eax, eax
0x140042e65  jnz     loc_14004300E
0x140042e6b  mov     rcx, [rsp+3F0h+FileHandle]; hObject
0x140042e70  call    cs:__imp_CloseHandle
0x140042e76  lea     r15, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_GlobalCriticalSection
0x140042e7d  mov     rcx, r15; lpCriticalSection
0x140042e80  call    cs:__imp_EnterCriticalSection
0x140042e86  nop
0x140042e87  lea     rax, [rsp+3F0h+ppv]
0x140042e8c  mov     qword ptr [rsp+3F0h+FsInformationClass], rax; ppv
0x140042e91  lea     r9, IID_IDefragEngine; riid
0x140042e98  mov     r8d, ebx; dwClsContext
0x140042e9b  xor     edx, edx; pUnkOuter
0x140042e9d  lea     rcx, CLSID_CDefragEngine; rclsid
0x140042ea4  call    cs:__imp_CoCreateInstance
0x140042eaa  mov     edi, eax
0x140042eac  test    eax, eax
0x140042eae  jns     short loc_140042ED4
0x140042eb0  lea     r8, aCvdsvolumeQuer_27; "CVdsVolume::QueryMaxReclaimableBytes(),"...
0x140042eb7  mov     r9d, eax
0x140042eba  xor     edx, edx
0x140042ebc  mov     ecx, r12d
0x140042ebf  call    cs:__imp_VdsTraceEx
0x140042ec5  nop
0x140042ec6  mov     rcx, r15; lpCriticalSection
0x140042ec9  call    cs:__imp_LeaveCriticalSection
0x140042ecf  jmp     loc_1400430D4
0x140042ed4  mov     ebx, r14d
0x140042ed7  mov     rcx, [rsp+3F0h+ppv]
0x140042edc  mov     rax, [rcx]
0x140042edf  lea     r8, [rbp+2F0h+var_320]
0x140042ee3  mov     rdx, [rbp+2F0h+var_360.pwszName]
0x140042ee7  mov     rax, [rax+48h]
0x140042eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042ef0  mov     edi, eax
0x140042ef2  cmp     eax, 1
0x140042ef5  jnz     short loc_140042F42
0x140042ef7  mov     rcx, [rsp+3F0h+ppv]
0x140042efc  movaps  xmm0, [rbp+2F0h+var_320]
0x140042f00  movdqa  [rsp+3F0h+var_390], xmm0
0x140042f06  mov     rax, [rcx]
0x140042f09  lea     rdx, [rsp+3F0h+var_390]
0x140042f0e  mov     rax, [rax+28h]
0x140042f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042f17  mov     edi, eax
0x140042f19  test    eax, eax
0x140042f1b  js      short loc_140042F36
0x140042f1d  mov     ecx, 1F4h; dwMilliseconds
0x140042f22  call    cs:__imp_Sleep
0x140042f28  inc     ebx
0x140042f2a  cmp     ebx, 0Ah
0x140042f2d  jb      short loc_140042ED7
0x140042f2f  mov     edi, 80042591h
0x140042f34  jmp     short loc_140042EC6
0x140042f36  lea     r8, aCvdsvolumeQuer_21; "CVdsVolume::QueryMaxReclaimableBytes(),"...
0x140042f3d  jmp     loc_140042EB7
0x140042f42  test    edi, edi
0x140042f44  jns     short loc_140042F63
0x140042f46  mov     eax, 8004259Ah
0x140042f4b  cmp     edi, 89000015h
0x140042f51  cmovz   edi, eax
0x140042f54  mov     r9d, edi
0x140042f57  lea     r8, aCvdsvolumeQuer_4; "CVdsVolume::QueryMaxReclaimableBytes(),"...
0x140042f5e  jmp     loc_140042EBA
0x140042f63  mov     rcx, [rsp+3F0h+ppv]
0x140042f68  movaps  xmm0, [rbp+2F0h+var_320]
0x140042f6c  movdqa  [rsp+3F0h+var_390], xmm0
0x140042f72  mov     rax, [rcx]
0x140042f75  lea     r8, [rsp+3F0h+var_3A8]
0x140042f7a  lea     rdx, [rsp+3F0h+var_390]
0x140042f7f  mov     rax, [rax+0A0h]
0x140042f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042f8b  mov     edi, eax
0x140042f8d  test    eax, eax
0x140042f8f  jns     short loc_140042F9D
0x140042f91  lea     r8, aCvdsvolumeQuer_8; "CVdsVolume::QueryMaxReclaimableBytes(),"...
0x140042f98  jmp     loc_140042EB7
0x140042f9d  mov     edi, [rsp+3F0h+var_3A8]
0x140042fa1  test    edi, edi
0x140042fa3  jns     short loc_140042FD1
0x140042fa5  cmp     edi, 89000015h
0x140042fab  jnz     short loc_140042FB4
0x140042fad  mov     edi, 8004259Ah
0x140042fb2  jmp     short loc_140042FC2
0x140042fb4  mov     eax, 80042599h
0x140042fb9  cmp     edi, 89000006h
0x140042fbf  cmovz   edi, eax
0x140042fc2  mov     r9d, edi
0x140042fc5  lea     r8, aCvdsvolumeQuer_32; "CVdsVolume::QueryMaxReclaimableBytes(),"...
0x140042fcc  jmp     loc_140042EBA
0x140042fd1  mov     rcx, [rsp+3F0h+ppv]
0x140042fd6  mov     rax, [rcx]
0x140042fd9  lea     r8, [rbp+2F0h+var_2B0]
0x140042fdd  mov     rdx, [rbp+2F0h+var_360.pwszName]
0x140042fe1  mov     rax, [rax+88h]
0x140042fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042fed  mov     edi, eax
0x140042fef  test    eax, eax
0x140042ff1  jns     short loc_140042FFF
0x140042ff3  lea     r8, aCvdsvolumeQuer_3; "CVdsVolume::QueryMaxReclaimableBytes(),"...
0x140042ffa  jmp     loc_140042EB7
0x140042fff  mov     rax, [rbp+2F0h+var_1D8]
0x140043006  mov     [rsi], rax
0x140043009  jmp     loc_140042EC6
0x14004300e  mov     eax, [rbp+2F0h+var_308]
0x140043011  cmp     eax, 6
0x140043014  jnz     loc_1400430CF
0x14004301a  lea     r8d, [rax-3]; MaxCount
0x14004301e  lea     rdx, aRaw; "RAW"
0x140043025  lea     rcx, [rbp+2F0h+String1]; String1
0x140043029  call    cs:__imp__wcsnicmp
0x14004302f  test    eax, eax
0x140043031  jnz     loc_1400430CF
0x140043037  lea     rdx, [rsp+3F0h+var_3B8]
0x14004303c  mov     rcx, [rsp+3F0h+FileHandle]
0x140043041  call    cs:__imp_GetFileSystemRecognitionName
0x140043047  test    eax, eax
0x140043049  js      short loc_140043087
0x14004304b  mov     r8, [rsp+3F0h+var_3B8]
0x140043050  lea     rdx, aCvdsvolumeQuer_17; "CVdsVolume::QueryMaxReclaimableBytes(),"...
0x140043057  xor     ecx, ecx
0x140043059  call    cs:__imp_VdsTraceW
0x14004305f  mov     edi, 8004292Ah
0x140043064  mov     rbx, [rsp+3F0h+var_3B8]
0x140043069  call    cs:__imp_GetProcessHeap
0x14004306f  mov     r8, rbx
0x140043072  xor     edx, edx
0x140043074  mov     rcx, rax
0x140043077  call    cs:__imp_VdsHeapFree
0x14004307d  mov     [rsp+3F0h+var_3B8], r14
0x140043082  jmp     loc_140042E0E
0x140043087  mov     edi, r14d
0x14004308a  mov     rbx, [rsp+3F0h+var_3B8]
0x14004308f  call    cs:__imp_GetProcessHeap
0x140043095  mov     r8, rbx
0x140043098  xor     edx, edx
0x14004309a  mov     rcx, rax
0x14004309d  call    cs:__imp_VdsHeapFree
0x1400430a3  mov     [rsp+3F0h+var_3B8], r14
0x1400430a8  mov     rcx, [rsp+3F0h+FileHandle]; hObject
0x1400430ad  call    cs:__imp_CloseHandle
0x1400430b3  mov     rax, [rbp+2F0h+var_360.ullSize]
0x1400430b7  cmp     rax, 100000h
0x1400430bd  ja      short loc_1400430C4
0x1400430bf  mov     rax, r14
0x1400430c2  jmp     short loc_1400430CA
0x1400430c4  add     rax, 0FFFFFFFFFFF00000h
0x1400430ca  mov     [rsi], rax
0x1400430cd  jmp     short loc_1400430D4
0x1400430cf  mov     edi, 8004251Eh
0x1400430d4  mov     rcx, [rbp+2F0h+var_360.pwszName]; pv
0x1400430d8  test    rcx, rcx
0x1400430db  jz      short loc_1400430E7
0x1400430dd  call    cs:__imp_CoTaskMemFree
0x1400430e3  mov     [rbp+2F0h+var_360.pwszName], r14
0x1400430e7  lea     rcx, [rsp+3F0h+var_3A0]; this
0x1400430ec  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400430f1  nop
0x1400430f2  lea     rcx, [rsp+3F0h+var_380]
0x1400430f7  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400430fd  nop
0x1400430fe  lea     rcx, [rsp+3F0h+ppv]
0x140043103  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140043108  mov     eax, edi
0x14004310a  mov     rcx, [rbp+2F0h+var_28]
0x140043111  xor     rcx, rsp; StackCookie
0x140043114  call    __security_check_cookie
0x140043119  lea     r11, [rsp+3F0h+var_20]
0x140043121  mov     rbx, [r11+40h]
  ... truncated ...
```
