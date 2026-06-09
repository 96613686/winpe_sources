# CVdsVolume::DeleteAccessPath(ushort *,int)

- ea: `0x14001f450`
- end: `0x14001f955`
- name: `?DeleteAccessPath@CVdsVolume@@UEAAJPEAGH@Z`
- size: `1285`
- prototype: `int(CVdsVolume *__hidden this, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140006e60`
- `0x140009990`
- `0x14000d0f0`
- `0x14000e270`
- `0x14001f450`
- `0x1400428a0`
- `0x140044170`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14001f565`
- `msvcrt!_wcsicmp` at `0x14001f766`
- `msvcrt!_wcsicmp` at `0x14001f565`
- `msvcrt!_wcsicmp` at `0x14001f766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001f582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001f5af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001f582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001f5af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f851`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f8a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f851`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f8a5`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x14001f6d4`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x14001f6d4`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x14001f895`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x14001f895`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x14001f847`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x14001f847`
- `vdsutil!OpenDevice` at `0x14001f6f8`
- `vdsutil!OpenDevice` at `0x14001f6f8`
- `vdsutil!GetDeviceName` at `0x14001f746`
- `vdsutil!GetDeviceName` at `0x14001f746`
- `vdsutil!IsDriveLetter` at `0x14001f622`
- `vdsutil!IsDriveLetter` at `0x14001f671`
- `vdsutil!IsDriveLetter` at `0x14001f7a3`
- `vdsutil!IsDriveLetter` at `0x14001f8b7`
- `vdsutil!IsDriveLetter` at `0x14001f622`
- `vdsutil!IsDriveLetter` at `0x14001f671`
- `vdsutil!IsDriveLetter` at `0x14001f7a3`
- `vdsutil!IsDriveLetter` at `0x14001f8b7`
- `vdsutil!LockVolume` at `0x14001f7fa`
- `vdsutil!LockVolume` at `0x14001f7fa`
- `vdsutil!DeleteNetworkShare` at `0x14001f8c4`
- `vdsutil!DeleteNetworkShare` at `0x14001f8c4`
- `vdsutil!VdsTraceEx` at `0x14001f4f3`
- `vdsutil!VdsTraceEx` at `0x14001f600`
- `vdsutil!VdsTraceEx` at `0x14001f63e`
- `vdsutil!VdsTraceEx` at `0x14001f687`
- `vdsutil!VdsTraceEx` at `0x14001f713`
- `vdsutil!VdsTraceEx` at `0x14001f7dd`
- `vdsutil!VdsTraceEx` at `0x14001f816`
- `vdsutil!VdsTraceEx` at `0x14001f868`
- `vdsutil!VdsTraceEx` at `0x14001f8da`
- `vdsutil!VdsTraceEx` at `0x14001f4f3`
- `vdsutil!VdsTraceEx` at `0x14001f600`
- `vdsutil!VdsTraceEx` at `0x14001f63e`
- `vdsutil!VdsTraceEx` at `0x14001f687`
- `vdsutil!VdsTraceEx` at `0x14001f713`
- `vdsutil!VdsTraceEx` at `0x14001f7dd`
- `vdsutil!VdsTraceEx` at `0x14001f816`
- `vdsutil!VdsTraceEx` at `0x14001f868`
- `vdsutil!VdsTraceEx` at `0x14001f8da`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001f4a9`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001f4a9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001f923`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001f923`

## string_xrefs

- `0x14001f8ab`: `CVdsVolume::DeleteAccessPath, 13, error=%ld`
- `0x14001f704`: `CVdsVolume::DeleteAccessPath, 6, error=%ld`
- `0x14001f857`: `CVdsVolume::DeleteAccessPath, 11, error=%ld`
- `0x14001f752`: `CVdsVolume::DeleteAccessPath, 7, error=%ld`
- `0x14001f496`: `CVdsVolume::DeleteAccessPath()`
- `0x14001f4e4`: `CVdsVolume::DeleteAccessPath, .5, hr=%lX`
- `0x14001f512`: `CVdsVolume::DeleteAccessPath, 0, hr=%lX`
- `0x14001f53a`: `CVdsVolume::DeleteAccessPath, 1, hr=%lX`
- `0x14001f5f4`: `CVdsVolume::DeleteAccessPath, 2, hr=%lX`
- `0x14001f632`: `CVdsVolume::DeleteAccessPath, 3`
- `0x14001f67b`: `CVdsVolume::DeleteAccessPath, 4`
- `0x14001f6e4`: `CVdsVolume::DeleteAccessPath, 5`
- `0x14001f770`: `CVdsVolume::DeleteAccessPath, 8`
- `0x14001f7d1`: `CVdsVolume::DeleteAccessPath, 9, hr=%lX`
- `0x14001f807`: `CVdsVolume::DeleteAccessPath, 10, error=%ld`
- `0x14001f8ce`: `CVdsVolume::DeleteAccessPath, 15`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVdsVolume::DeleteAccessPath(CVdsVolume *this, unsigned __int16 *a2, int a3)
{
  int DeviceName; // ebx
  CVdsVolume *v7; // r12
  int v8; // eax
  CVdsVolume *v9; // rcx
  const char *v10; // r8
  int v11; // r14d
  int v12; // ebx
  const wchar_t **v13; // rcx
  int v14; // eax
  int v15; // esi
  DWORD DosDeviceW; // eax
  void **v17; // rcx
  unsigned int v18; // edx
  int v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  DWORD LastError; // eax
  const char *v23; // r8
  BOOL v24; // eax
  wchar_t *v26; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v27; // [rsp+28h] [rbp-D8h] BYREF
  void *v28; // [rsp+30h] [rbp-D0h] BYREF
  int v29; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  int v32; // [rsp+50h] [rbp-B0h]
  _BYTE v33[16]; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v34[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v35; // [rsp+88h] [rbp-78h]
  wchar_t *String1; // [rsp+98h] [rbp-68h]
  unsigned __int16 v37[14]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR TargetPath[266]; // [rsp+BCh] [rbp-44h] BYREF
  wchar_t String2[280]; // [rsp+2D0h] [rbp+1D0h] BYREF

  pv = 0;
  v29 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v33, 0x5Eu, "CVdsVolume::DeleteAccessPath()");
  v31 = 0;
  v32 = 0;
  DeviceName = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v31);
  if ( DeviceName >= 0 )
  {
    v7 = (CVdsVolume *)((char *)this - 24);
    v8 = CVdsVolume::ValidateCall((CVdsVolume *)((char *)this - 24), 0xAu);
    DeviceName = v8;
    if ( v8 < 0 )
    {
      v10 = "CVdsVolume::DeleteAccessPath, .5, hr=%lX";
LABEL_4:
      VdsTraceEx(94, 0, v10, (unsigned int)v8);
      goto LABEL_60;
    }
    if ( CVdsVolume::IsVolumeGuidPathname(v9, a2) )
    {
      DeviceName = -2147210995;
      VdsTraceEx(94, 0, "CVdsVolume::DeleteAccessPath, 0, hr=%lX", 2147756301LL);
      goto LABEL_60;
    }
    v8 = (*(__int64 (__fastcall **)(CVdsVolume *, LPVOID *, int *))(*(_QWORD *)this + 48LL))(this, &pv, &v29);
    DeviceName = v8;
    if ( v8 < 0 )
    {
      v10 = "CVdsVolume::DeleteAccessPath, 1, hr=%lX";
      goto LABEL_4;
    }
    v11 = 0;
    v12 = 0;
    v13 = (const wchar_t **)pv;
    if ( v29 > 0 )
    {
      do
      {
        if ( !_wcsicmp(v13[v12], a2) )
          v11 = 1;
        v13 = (const wchar_t **)pv;
        if ( *((_QWORD *)pv + v12) )
        {
          CoTaskMemFree(*((LPVOID *)pv + v12));
          *((_QWORD *)pv + v12) = 0;
          v13 = (const wchar_t **)pv;
        }
        ++v12;
      }
      while ( v12 < v29 );
      v7 = (CVdsVolume *)((char *)this - 24);
    }
    if ( v13 )
    {
      CoTaskMemFree(v13);
      pv = 0;
    }
    memset(v34, 0, sizeof(v34));
    v35 = 0;
    String1 = 0;
    v26 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(**((_QWORD **)this + 13) + 24LL))(*((_QWORD *)this + 13), v34);
    DeviceName = v14;
    if ( v14 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsVolume::DeleteAccessPath, 2, hr=%lX", v14);
LABEL_20:
      CVdsCoTaskPtr<unsigned short>::~CVdsCoTaskPtr<unsigned short>((void **)&v26);
      goto LABEL_60;
    }
    v26 = String1;
    if ( (unsigned int)IsDriveLetter(a2) && (BYTE8(v35) & 0x82) != 0 )
    {
      VdsTraceEx(94, 0, "CVdsVolume::DeleteAccessPath, 3");
      CVdsCoTaskPtr<unsigned short>::~CVdsCoTaskPtr<unsigned short>((void **)&v26);
      DeviceName = -2147210994;
      goto LABEL_60;
    }
    v15 = 0;
    if ( !v11 )
    {
      v27 = -1;
      if ( !(unsigned int)IsDriveLetter(a2) )
      {
        VdsTraceEx(94, 0, "CVdsVolume::DeleteAccessPath, 4");
LABEL_27:
        CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>((void **)&v27);
        CVdsCoTaskPtr<unsigned short>::~CVdsCoTaskPtr<unsigned short>((void **)&v26);
        DeviceName = -2147212266;
        goto LABEL_60;
      }
      StringCchCopyW(v37, 0x112u, L"\\\\?\\GLOBALROOT");
      a2[2] = 0;
      DosDeviceW = QueryDosDeviceW(a2, TargetPath, 0x104u);
      a2[2] = 92;
      if ( !DosDeviceW )
      {
        VdsTraceEx(94, 0, "CVdsVolume::DeleteAccessPath, 5");
        goto LABEL_27;
      }
      DeviceName = OpenDevice(v37, 0, &v27);
      if ( DeviceName )
      {
        VdsTraceEx(94, 0, "CVdsVolume::DeleteAccessPath, 6, error=%ld", (unsigned int)DeviceName);
LABEL_32:
        if ( DeviceName > 0 )
          DeviceName = (unsigned __int16)DeviceName | 0x80070000;
        v17 = (void **)&v27;
        goto LABEL_35;
      }
      DeviceName = GetDeviceName(v27, 0, 274, String2);
      if ( DeviceName )
      {
        VdsTraceEx(94, 0, "CVdsVolume::DeleteAccessPath, 7, error=%ld", (unsigned int)DeviceName);
        goto LABEL_32;
      }
      if ( _wcsicmp(String1, String2) )
      {
        VdsTraceEx(94, 0, "CVdsVolume::DeleteAccessPath, 8");
        goto LABEL_27;
      }
      v15 = 1;
      CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>((void **)&v27);
    }
    v28 = (void *)-1LL;
    if ( (unsigned int)IsDriveLetter(a2) )
    {
      v19 = CVdsVolume::OpenHandle(v7, v18, &v28, 0);
      DeviceName = v19;
      if ( v19 >= 0 )
      {
        LOBYTE(v20) = 1;
        v21 = LockVolume(v28, v20);
        if ( v21 )
        {
          VdsTraceEx(94, 1, "CVdsVolume::DeleteAccessPath, 10, error=%ld", v21);
          if ( !a3 )
          {
            CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&v28);
            CVdsCoTaskPtr<unsigned short>::~CVdsCoTaskPtr<unsigned short>((void **)&v26);
            DeviceName = -2147212269;
            goto LABEL_60;
          }
        }
      }
      else if ( v19 != -2147212270 )
      {
        VdsTraceEx(94, 0, "CVdsVolume::DeleteAccessPath, 9, hr=%lX", v19);
        if ( !a3 )
        {
LABEL_45:
          v17 = &v28;
LABEL_35:
          CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(v17);
          goto LABEL_20;
        }
      }
    }
    if ( v15 )
    {
      a2[2] = 0;
      v24 = DefineDosDeviceW(3u, a2, TargetPath);
      a2[2] = 92;
      if ( !v24 )
      {
        LastError = GetLastError();
        v23 = "CVdsVolume::DeleteAccessPath, 13, error=%ld";
LABEL_52:
        DeviceName = LastError;
        VdsTraceEx(94, 0, v23, LastError, v26);
        if ( DeviceName > 0 )
          DeviceName = (unsigned __int16)DeviceName | 0x80070000;
        goto LABEL_45;
      }
    }
    else if ( !DeleteVolumeMountPointW(a2) )
    {
      LastError = GetLastError();
      v23 = "CVdsVolume::DeleteAccessPath, 11, error=%ld";
      goto LABEL_52;
    }
    if ( !(unsigned int)IsDriveLetter(a2) || (unsigned int)DeleteNetworkShare(a2) )
    {
      CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&v28);
      CVdsCoTaskPtr<unsigned short>::~CVdsCoTaskPtr<unsigned short>((void **)&v26);
      DeviceName = 0;
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsVolume::DeleteAccessPath, 15");
      CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&v28);
      CVdsCoTaskPtr<unsigned short>::~CVdsCoTaskPtr<unsigned short>((void **)&v26);
      DeviceName = 1;
    }
  }
LABEL_60:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v33);
  return (unsigned int)DeviceName;
}

```

## disassembly

```asm
0x14001f450  mov     [rsp-8+arg_10], rbx
0x14001f455  push    rbp
0x14001f456  push    rsi
0x14001f457  push    rdi
0x14001f458  push    r12
0x14001f45a  push    r13
0x14001f45c  push    r14
0x14001f45e  push    r15
0x14001f460  lea     rbp, [rsp-410h]
0x14001f468  sub     rsp, 510h
0x14001f46f  mov     rax, cs:__security_cookie
0x14001f476  xor     rax, rsp
0x14001f479  mov     [rbp+440h+var_40], rax
0x14001f480  mov     r13d, r8d
0x14001f483  mov     rdi, rdx
0x14001f486  mov     rsi, rcx
0x14001f489  xor     r15d, r15d
0x14001f48c  mov     [rsp+540h+pv], r15
0x14001f491  mov     [rsp+540h+var_508], r15d
0x14001f496  lea     r8, aCvdsvolumeDele_15; "CVdsVolume::DeleteAccessPath()"
0x14001f49d  lea     r14d, [r15+5Eh]
0x14001f4a1  mov     edx, r14d
0x14001f4a4  lea     rcx, [rsp+540h+var_4E8]
0x14001f4a9  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001f4af  nop
0x14001f4b0  mov     [rsp+540h+var_4F8], r15
0x14001f4b5  mov     [rsp+540h+var_4F0], r15d
0x14001f4ba  lea     rcx, [rsp+540h+var_4F8]; this
0x14001f4bf  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x14001f4c4  mov     ebx, eax
0x14001f4c6  test    eax, eax
0x14001f4c8  js      loc_14001F913
0x14001f4ce  lea     r12, [rsi-18h]
0x14001f4d2  lea     edx, [r15+0Ah]; unsigned int
0x14001f4d6  mov     rcx, r12; this
0x14001f4d9  call    ?ValidateCall@CVdsVolume@@AEAAJK@Z; CVdsVolume::ValidateCall(ulong)
0x14001f4de  mov     ebx, eax
0x14001f4e0  test    eax, eax
0x14001f4e2  jns     short loc_14001F4FE
0x14001f4e4  lea     r8, aCvdsvolumeDele_18; "CVdsVolume::DeleteAccessPath, .5, hr=%l"...
0x14001f4eb  mov     r9d, eax
0x14001f4ee  xor     edx, edx
0x14001f4f0  mov     ecx, r14d
0x14001f4f3  call    cs:__imp_VdsTraceEx
0x14001f4f9  jmp     loc_14001F913
0x14001f4fe  mov     rdx, rdi; unsigned __int16 *
0x14001f501  call    ?IsVolumeGuidPathname@CVdsVolume@@AEAAEPEAG@Z; CVdsVolume::IsVolumeGuidPathname(ushort *)
0x14001f506  test    al, al
0x14001f508  jz      short loc_14001F51B
0x14001f50a  mov     ebx, 8004290Dh
0x14001f50f  mov     r9d, ebx
0x14001f512  lea     r8, aCvdsvolumeDele_3; "CVdsVolume::DeleteAccessPath, 0, hr=%lX"
0x14001f519  jmp     short loc_14001F4EE
0x14001f51b  mov     rax, [rsi]
0x14001f51e  lea     r8, [rsp+540h+var_508]
0x14001f523  lea     rdx, [rsp+540h+pv]
0x14001f528  mov     rcx, rsi
0x14001f52b  mov     rax, [rax+30h]
0x14001f52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f534  mov     ebx, eax
0x14001f536  test    eax, eax
0x14001f538  jns     short loc_14001F543
0x14001f53a  lea     r8, aCvdsvolumeDele_2; "CVdsVolume::DeleteAccessPath, 1, hr=%lX"
0x14001f541  jmp     short loc_14001F4EB
0x14001f543  mov     r14d, r15d
0x14001f546  mov     ebx, r15d
0x14001f549  mov     rcx, [rsp+540h+pv]
0x14001f54e  cmp     [rsp+540h+var_508], r15d
0x14001f553  jle     short loc_14001F5AA
0x14001f555  mov     r12d, 1
0x14001f55b  movsxd  r15, ebx
0x14001f55e  mov     rdx, rdi; String2
0x14001f561  mov     rcx, [rcx+r15*8]; String1
0x14001f565  call    cs:__imp__wcsicmp
0x14001f56b  test    eax, eax
0x14001f56d  cmovz   r14d, r12d
0x14001f571  mov     rcx, [rsp+540h+pv]
0x14001f576  mov     rax, [rcx+r15*8]
0x14001f57a  test    rax, rax
0x14001f57d  jz      short loc_14001F59A
0x14001f57f  mov     rcx, rax; pv
0x14001f582  call    cs:__imp_CoTaskMemFree
0x14001f588  mov     rax, [rsp+540h+pv]
0x14001f58d  mov     qword ptr [rax+r15*8], 0
0x14001f595  mov     rcx, [rsp+540h+pv]; pv
0x14001f59a  add     ebx, r12d
0x14001f59d  cmp     ebx, [rsp+540h+var_508]
0x14001f5a1  jl      short loc_14001F55B
0x14001f5a3  lea     r12, [rsi-18h]
0x14001f5a7  xor     r15d, r15d
0x14001f5aa  test    rcx, rcx
0x14001f5ad  jz      short loc_14001F5BA
0x14001f5af  call    cs:__imp_CoTaskMemFree
0x14001f5b5  mov     [rsp+540h+pv], r15
0x14001f5ba  xorps   xmm0, xmm0
0x14001f5bd  xor     eax, eax
0x14001f5bf  movups  [rsp+540h+var_4D8], xmm0
0x14001f5c4  movups  [rsp+540h+var_4C8], xmm0
0x14001f5c9  movups  [rbp+440h+var_4B8], xmm0
0x14001f5cd  mov     [rbp+440h+String1], rax
0x14001f5d1  mov     [rsp+540h+var_520], r15
0x14001f5d6  mov     rcx, [rsi+68h]
0x14001f5da  mov     rax, [rcx]
0x14001f5dd  lea     rdx, [rsp+540h+var_4D8]
0x14001f5e2  mov     rax, [rax+18h]
0x14001f5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f5eb  mov     ebx, eax
0x14001f5ed  test    eax, eax
0x14001f5ef  jns     short loc_14001F616
0x14001f5f1  mov     r9d, eax
0x14001f5f4  lea     r8, aCvdsvolumeDele_21; "CVdsVolume::DeleteAccessPath, 2, hr=%lX"
0x14001f5fb  xor     edx, edx
0x14001f5fd  lea     ecx, [rdx+5Eh]
0x14001f600  call    cs:__imp_VdsTraceEx
0x14001f606  nop
0x14001f607  lea     rcx, [rsp+540h+var_520]
0x14001f60c  call    ??1?$CVdsCoTaskPtr@G@@QEAA@XZ; CVdsCoTaskPtr<ushort>::~CVdsCoTaskPtr<ushort>(void)
0x14001f611  jmp     loc_14001F913
0x14001f616  mov     rax, [rbp+440h+String1]
0x14001f61a  mov     [rsp+540h+var_520], rax
0x14001f61f  mov     rcx, rdi
0x14001f622  call    cs:__imp_IsDriveLetter
0x14001f628  test    eax, eax
0x14001f62a  jz      short loc_14001F659
0x14001f62c  test    byte ptr [rbp+440h+var_4B8+8], 82h
0x14001f630  jz      short loc_14001F659
0x14001f632  lea     r8, aCvdsvolumeDele_1; "CVdsVolume::DeleteAccessPath, 3"
0x14001f639  xor     edx, edx
0x14001f63b  lea     ecx, [rdx+5Eh]
0x14001f63e  call    cs:__imp_VdsTraceEx
0x14001f644  nop
0x14001f645  lea     rcx, [rsp+540h+var_520]
0x14001f64a  call    ??1?$CVdsCoTaskPtr@G@@QEAA@XZ; CVdsCoTaskPtr<ushort>::~CVdsCoTaskPtr<ushort>(void)
0x14001f64f  mov     ebx, 8004290Eh
0x14001f654  jmp     loc_14001F913
0x14001f659  mov     esi, r15d
0x14001f65c  test    r14d, r14d
0x14001f65f  jnz     loc_14001F791
0x14001f665  mov     [rsp+540h+var_518], 0FFFFFFFFFFFFFFFFh
0x14001f66e  mov     rcx, rdi
0x14001f671  call    cs:__imp_IsDriveLetter
0x14001f677  test    eax, eax
0x14001f679  jnz     short loc_14001F6AD
0x14001f67b  lea     r8, aCvdsvolumeDele_4; "CVdsVolume::DeleteAccessPath, 4"
0x14001f682  xor     edx, edx
0x14001f684  lea     ecx, [rdx+5Eh]
0x14001f687  call    cs:__imp_VdsTraceEx
0x14001f68d  nop
0x14001f68e  lea     rcx, [rsp+540h+var_518]
0x14001f693  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x14001f698  nop
0x14001f699  lea     rcx, [rsp+540h+var_520]
0x14001f69e  call    ??1?$CVdsCoTaskPtr@G@@QEAA@XZ; CVdsCoTaskPtr<ushort>::~CVdsCoTaskPtr<ushort>(void)
0x14001f6a3  mov     ebx, 80042416h
0x14001f6a8  jmp     loc_14001F913
0x14001f6ad  lea     r8, aGlobalroot; "\\\\?\\GLOBALROOT"
0x14001f6b4  mov     esi, 112h
0x14001f6b9  mov     edx, esi; unsigned __int64
0x14001f6bb  lea     rcx, [rbp+440h+var_4A0]; unsigned __int16 *
0x14001f6bf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001f6c4  mov     [rdi+4], r15w
0x14001f6c9  lea     r8d, [rsi-0Eh]; ucchMax
0x14001f6cd  lea     rdx, [rbp+440h+TargetPath]; lpTargetPath
0x14001f6d1  mov     rcx, rdi; lpDeviceName
0x14001f6d4  call    cs:__imp_QueryDosDeviceW
0x14001f6da  mov     word ptr [rdi+4], 5Ch ; '\'
0x14001f6e0  test    eax, eax
0x14001f6e2  jnz     short loc_14001F6ED
0x14001f6e4  lea     r8, aCvdsvolumeDele_13; "CVdsVolume::DeleteAccessPath, 5"
0x14001f6eb  jmp     short loc_14001F682
0x14001f6ed  lea     r8, [rsp+540h+var_518]
0x14001f6f2  xor     edx, edx
0x14001f6f4  lea     rcx, [rbp+440h+var_4A0]
0x14001f6f8  call    cs:__imp_OpenDevice
0x14001f6fe  mov     ebx, eax
0x14001f700  test    eax, eax
0x14001f702  jz      short loc_14001F735
0x14001f704  lea     r8, aCvdsvolumeDele_16; "CVdsVolume::DeleteAccessPath, 6, error="...
0x14001f70b  mov     r9d, ebx
0x14001f70e  xor     edx, edx
0x14001f710  lea     ecx, [rdx+5Eh]
0x14001f713  call    cs:__imp_VdsTraceEx
0x14001f719  test    ebx, ebx
0x14001f71b  jle     short loc_14001F726
0x14001f71d  movzx   ebx, bx
0x14001f720  or      ebx, 80070000h
0x14001f726  lea     rcx, [rsp+540h+var_518]
0x14001f72b  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x14001f730  jmp     loc_14001F607
0x14001f735  lea     r9, [rbp+440h+String2]
0x14001f73c  mov     r8d, esi
0x14001f73f  xor     edx, edx
0x14001f741  mov     rcx, [rsp+540h+var_518]
0x14001f746  call    cs:__imp_GetDeviceName
0x14001f74c  mov     ebx, eax
0x14001f74e  test    eax, eax
0x14001f750  jz      short loc_14001F75B
0x14001f752  lea     r8, aCvdsvolumeDele_7; "CVdsVolume::DeleteAccessPath, 7, error="...
0x14001f759  jmp     short loc_14001F70B
0x14001f75b  lea     rdx, [rbp+440h+String2]; String2
0x14001f762  mov     rcx, [rbp+440h+String1]; String1
0x14001f766  call    cs:__imp__wcsicmp
0x14001f76c  test    eax, eax
0x14001f76e  jz      short loc_14001F77C
0x14001f770  lea     r8, aCvdsvolumeDele_11; "CVdsVolume::DeleteAccessPath, 8"
0x14001f777  jmp     loc_14001F682
0x14001f77c  mov     r14d, 1
0x14001f782  mov     esi, r14d
0x14001f785  lea     rcx, [rsp+540h+var_518]
0x14001f78a  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x14001f78f  jmp     short loc_14001F797
0x14001f791  mov     r14d, 1
0x14001f797  mov     [rsp+540h+var_510], 0FFFFFFFFFFFFFFFFh
0x14001f7a0  mov     rcx, rdi
0x14001f7a3  call    cs:__imp_IsDriveLetter
0x14001f7a9  test    eax, eax
0x14001f7ab  jz      loc_14001F840
0x14001f7b1  xor     r9d, r9d; struct _VDS_VOLUME_PROP *
0x14001f7b4  lea     r8, [rsp+540h+var_510]; void **
0x14001f7b9  mov     rcx, r12; this
0x14001f7bc  call    ?OpenHandle@CVdsVolume@@QEAAJKPEAPEAXPEAU_VDS_VOLUME_PROP@@@Z; CVdsVolume::OpenHandle(ulong,void * *,_VDS_VOLUME_PROP *)
0x14001f7c1  mov     ebx, eax
0x14001f7c3  test    eax, eax
0x14001f7c5  jns     short loc_14001F7F2
0x14001f7c7  cmp     eax, 80042412h
0x14001f7cc  jz      short loc_14001F840
0x14001f7ce  mov     r9d, eax
0x14001f7d1  lea     r8, aCvdsvolumeDele_9; "CVdsVolume::DeleteAccessPath, 9, hr=%lX"
0x14001f7d8  xor     edx, edx
0x14001f7da  lea     ecx, [rdx+5Eh]
0x14001f7dd  call    cs:__imp_VdsTraceEx
0x14001f7e3  test    r13d, r13d
0x14001f7e6  jnz     short loc_14001F840
0x14001f7e8  lea     rcx, [rsp+540h+var_510]
0x14001f7ed  jmp     loc_14001F72B
0x14001f7f2  mov     dl, r14b
0x14001f7f5  mov     rcx, [rsp+540h+var_510]
0x14001f7fa  call    cs:__imp_LockVolume
0x14001f800  test    eax, eax
0x14001f802  jz      short loc_14001F840
0x14001f804  mov     r9d, eax
0x14001f807  lea     r8, aCvdsvolumeDele_22; "CVdsVolume::DeleteAccessPath, 10, error"...
0x14001f80e  mov     edx, r14d
0x14001f811  mov     ecx, 5Eh ; '^'
0x14001f816  call    cs:__imp_VdsTraceEx
0x14001f81c  test    r13d, r13d
0x14001f81f  jnz     short loc_14001F840
0x14001f821  lea     rcx, [rsp+540h+var_510]
0x14001f826  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x14001f82b  nop
0x14001f82c  lea     rcx, [rsp+540h+var_520]
0x14001f831  call    ??1?$CVdsCoTaskPtr@G@@QEAA@XZ; CVdsCoTaskPtr<ushort>::~CVdsCoTaskPtr<ushort>(void)
0x14001f836  mov     ebx, 80042413h
0x14001f83b  jmp     loc_14001F913
0x14001f840  test    esi, esi
0x14001f842  jnz     short loc_14001F884
0x14001f844  mov     rcx, rdi; lpszVolumeMountPoint
0x14001f847  call    cs:__imp_DeleteVolumeMountPointW
0x14001f84d  test    eax, eax
0x14001f84f  jnz     short loc_14001F8B4
0x14001f851  call    cs:__imp_GetLastError
0x14001f857  lea     r8, aCvdsvolumeDele_10; "CVdsVolume::DeleteAccessPath, 11, error"...
0x14001f85e  mov     r9d, eax
0x14001f861  mov     ebx, eax
0x14001f863  xor     edx, edx
0x14001f865  lea     ecx, [rdx+5Eh]
0x14001f868  call    cs:__imp_VdsTraceEx
0x14001f86e  test    ebx, ebx
0x14001f870  jle     loc_14001F7E8
0x14001f876  movzx   ebx, bx
0x14001f879  or      ebx, 80070000h
0x14001f87f  jmp     loc_14001F7E8
0x14001f884  mov     [rdi+4], r15w
0x14001f889  lea     r8, [rbp+440h+TargetPath]; lpTargetPath
0x14001f88d  mov     rdx, rdi; lpDeviceName
0x14001f890  mov     ecx, 3; dwFlags
0x14001f895  call    cs:__imp_DefineDosDeviceW
0x14001f89b  mov     word ptr [rdi+4], 5Ch ; '\'
0x14001f8a1  test    eax, eax
0x14001f8a3  jnz     short loc_14001F8B4
0x14001f8a5  call    cs:__imp_GetLastError
0x14001f8ab  lea     r8, aCvdsvolumeDele_24; "CVdsVolume::DeleteAccessPath, 13, error"...
0x14001f8b2  jmp     short loc_14001F85E
0x14001f8b4  mov     rcx, rdi
0x14001f8b7  call    cs:__imp_IsDriveLetter
0x14001f8bd  test    eax, eax
0x14001f8bf  jz      short loc_14001F8FB
0x14001f8c1  mov     rcx, rdi
0x14001f8c4  call    cs:__imp_DeleteNetworkShare
0x14001f8ca  test    eax, eax
0x14001f8cc  jnz     short loc_14001F8FB
0x14001f8ce  lea     r8, aCvdsvolumeDele_19; "CVdsVolume::DeleteAccessPath, 15"
0x14001f8d5  xor     edx, edx
0x14001f8d7  lea     ecx, [rax+5Eh]
0x14001f8da  call    cs:__imp_VdsTraceEx
0x14001f8e0  nop
0x14001f8e1  lea     rcx, [rsp+540h+var_510]
0x14001f8e6  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x14001f8eb  nop
0x14001f8ec  lea     rcx, [rsp+540h+var_520]
  ... truncated ...
```
