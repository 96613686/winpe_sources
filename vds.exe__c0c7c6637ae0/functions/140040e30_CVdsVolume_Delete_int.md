# CVdsVolume::Delete(int)

- ea: `0x140040e30`
- end: `0x14004117c`
- name: `?Delete@CVdsVolume@@UEAAJH@Z`
- size: `844`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, reparse_path, service_task`

## callees

- `0x140003710`
- `0x140004360`
- `0x140009990`
- `0x14000d0f0`
- `0x14000e270`
- `0x14000ed14`
- `0x14003bca8`
- `0x140040e30`
- `0x140044170`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400410ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400410ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400410d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400410d8`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x14004107d`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x14004107d`
- `vdsutil!LockDismountVolume` at `0x140040fe1`
- `vdsutil!LockDismountVolume` at `0x140040fe1`
- `vdsutil!CoFreeStringArray` at `0x140041112`
- `vdsutil!CoFreeStringArray` at `0x140041112`
- `vdsutil!GarbageCollectDriveLetters` at `0x1400410a6`
- `vdsutil!GarbageCollectDriveLetters` at `0x1400410a6`
- `vdsutil!VdsHeapFree` at `0x1400410fb`
- `vdsutil!VdsHeapFree` at `0x1400410fb`
- `vdsutil!VdsTraceEx` at `0x140040ec6`
- `vdsutil!VdsTraceEx` at `0x140040f03`
- `vdsutil!VdsTraceEx` at `0x140040f60`
- `vdsutil!VdsTraceEx` at `0x140040f93`
- `vdsutil!VdsTraceEx` at `0x140040fc2`
- `vdsutil!VdsTraceEx` at `0x140040ffb`
- `vdsutil!VdsTraceEx` at `0x140041045`
- `vdsutil!VdsTraceEx` at `0x140041093`
- `vdsutil!VdsTraceEx` at `0x140040ec6`
- `vdsutil!VdsTraceEx` at `0x140040f03`
- `vdsutil!VdsTraceEx` at `0x140040f60`
- `vdsutil!VdsTraceEx` at `0x140040f93`
- `vdsutil!VdsTraceEx` at `0x140040fc2`
- `vdsutil!VdsTraceEx` at `0x140040ffb`
- `vdsutil!VdsTraceEx` at `0x140041045`
- `vdsutil!VdsTraceEx` at `0x140041093`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140040e9d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140040e9d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140041139`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140041139`

## string_xrefs

- `0x140040e8b`: `CVdsVolume::Delete()`
- `0x140040eba`: `CVdsVolume::Delete, .5, hr=%lX`
- `0x140040ef6`: `CVdsVolume::Delete, 1`
- `0x140040f54`: `CVdsVolume::Delete, 2, hr=%lX`
- `0x140040f87`: `CVdsVolume::Delete, 3`
- `0x140040fb6`: `CVdsVolume::Delete, 4`
- `0x140040fef`: `CVdsVolume::Delete, 5`
- `0x140041039`: `CVdsVolume::Delete, 6, hr=%lX`
- `0x140041087`: `CVdsVolume::Delete, 7`
- `0x1400410e1`: `CVdsVolume::Delete, 9, hr=%ld`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CVdsVolume::Delete(CVdsVolume *this, unsigned int a2)
{
  int v4; // eax
  int v5; // ebx
  int v6; // r14d
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // r15d
  int v10; // eax
  int i; // edi
  const WCHAR *v12; // rcx
  unsigned __int64 v13; // rax
  void *FSPropertiesInMap; // rdi
  __int64 LastError; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v18; // [rsp+20h] [rbp-59h] BYREF
  __int64 v19; // [rsp+28h] [rbp-51h] BYREF
  int v20; // [rsp+30h] [rbp-49h]
  __int64 v21; // [rsp+38h] [rbp-41h] BYREF
  void *v22; // [rsp+40h] [rbp-39h] BYREF
  LPWSTR pwszName; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v24[16]; // [rsp+50h] [rbp-29h] BYREF
  struct _VDS_VOLUME_PROP v25; // [rsp+60h] [rbp-19h] BYREF

  memset(&v25, 0, sizeof(v25));
  pwszName = 0;
  v22 = (void *)-1LL;
  v21 = 0;
  v18 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v24, 0x5Eu, "CVdsVolume::Delete()");
  v4 = CVdsVolume::ValidateCall(this, 3u);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = 0;
    if ( (*(int (__fastcall **)(char *, __int64 *, unsigned int *))(*((_QWORD *)this + 3) + 48LL))(
           (char *)this + 24,
           &v21,
           &v18) < 0 )
    {
      VdsTraceEx(94, 1, "CVdsVolume::Delete, 1");
      v6 = 1;
    }
    v19 = 1;
    v20 = 0;
    v5 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v19);
    if ( v5 >= 0 )
    {
      v5 = CVdsVolume::OpenHandle(this, v7, &v22, &v25);
      if ( (int)(v5 + 0x80000000) < 0 || v5 == -2147212239 || a2 )
      {
        if ( v22 != (void *)-1LL )
        {
          pwszName = v25.pwszName;
          if ( v25.status == VDS_VS_NO_MEDIA )
          {
            VdsTraceEx(94, 0, "CVdsVolume::Delete, 3");
            CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v19);
            v5 = -2147211942;
            goto LABEL_41;
          }
          if ( (v25.ulFlags & 0x1000383) != 0 )
          {
            VdsTraceEx(94, 0, "CVdsVolume::Delete, 4");
            CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v19);
            v5 = -2147210993;
            goto LABEL_41;
          }
          LOBYTE(v8) = 1;
          if ( (unsigned int)LockDismountVolume(v22, a2, v8) && !a2 )
          {
            VdsTraceEx(94, 0, "CVdsVolume::Delete, 5");
            CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v19);
            v5 = -2147212269;
            goto LABEL_41;
          }
        }
        v9 = 0;
        v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 16) + 88LL))(*((_QWORD *)this + 16), 1);
        v5 = v10;
        if ( v10 >= 0 )
        {
          if ( !v6 )
          {
            for ( i = 0; i < (int)v18; ++i )
            {
              v12 = *(const WCHAR **)(v21 + 8LL * i);
              v13 = -1;
              do
                ++v13;
              while ( v12[v13] );
              if ( v13 > 3 && !DeleteVolumeMountPointW(v12) )
              {
                VdsTraceEx(94, 0, "CVdsVolume::Delete, 7");
                v9 = 1;
              }
            }
          }
          GarbageCollectDriveLetters();
          FSPropertiesInMap = CVdsService::FindFSPropertiesInMap(
                                *((CVdsService **)this + 15),
                                *((struct IUnknown **)this + 16));
          if ( FSPropertiesInMap )
          {
            if ( (unsigned int)CVdsService::RemoveFSPropertiesFromMap(
                                 *((CVdsService **)this + 15),
                                 *((struct IUnknown **)this + 16)) )
            {
              ProcessHeap = GetProcessHeap();
              VdsHeapFree(ProcessHeap, 0, FSPropertiesInMap);
            }
            else
            {
              LastError = GetLastError();
              VdsTraceEx(94, 0, "CVdsVolume::Delete, 9, hr=%ld", LastError);
            }
          }
        }
        else
        {
          VdsTraceEx(94, 0, "CVdsVolume::Delete, 6, hr=%lX", (unsigned int)v10);
        }
        if ( !v6 && v21 )
          CoFreeStringArray(v21, v18);
        if ( v5 >= 0 && (v6 || v9) )
          v5 = 279108;
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsVolume::Delete, 2, hr=%lX", v5);
      }
    }
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v19);
    goto LABEL_41;
  }
  VdsTraceEx(94, 0, "CVdsVolume::Delete, .5, hr=%lX", v4);
LABEL_41:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
  CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&v22);
  CVdsCoTaskPtr<unsigned short>::~CVdsCoTaskPtr<unsigned short>((void **)&pwszName);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140040e30  mov     [rsp-8+arg_10], rbx
0x140040e35  push    rbp
0x140040e36  push    rsi
0x140040e37  push    rdi
0x140040e38  push    r12
0x140040e3a  push    r13
0x140040e3c  push    r14
0x140040e3e  push    r15
0x140040e40  lea     rbp, [rsp-27h]
0x140040e45  sub     rsp, 0A0h
0x140040e4c  mov     rax, cs:__security_cookie
0x140040e53  xor     rax, rsp
0x140040e56  mov     [rbp+57h+var_38], rax
0x140040e5a  mov     edi, edx
0x140040e5c  mov     rsi, rcx
0x140040e5f  xorps   xmm0, xmm0
0x140040e62  xor     eax, eax
0x140040e64  movups  xmmword ptr [rbp+57h+var_70.id.Data1], xmm0
0x140040e68  movups  xmmword ptr [rbp+57h+var_70.type], xmm0
0x140040e6c  movups  xmmword ptr [rbp+57h+var_70.ullSize], xmm0
0x140040e70  mov     [rbp+57h+var_70.pwszName], rax
0x140040e74  xor     r12d, r12d
0x140040e77  mov     [rbp+57h+var_88], r12
0x140040e7b  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFFh
0x140040e83  mov     [rbp+57h+var_98], r12
0x140040e87  mov     [rbp+57h+var_B0], r12d
0x140040e8b  lea     r8, aCvdsvolumeDele_12; "CVdsVolume::Delete()"
0x140040e92  lea     r13d, [rax+5Eh]
0x140040e96  mov     edx, r13d
0x140040e99  lea     rcx, [rbp+57h+var_80]
0x140040e9d  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140040ea3  nop
0x140040ea4  lea     edx, [r12+3]; unsigned int
0x140040ea9  mov     rcx, rsi; this
0x140040eac  call    ?ValidateCall@CVdsVolume@@AEAAJK@Z; CVdsVolume::ValidateCall(ulong)
0x140040eb1  mov     ebx, eax
0x140040eb3  test    eax, eax
0x140040eb5  jns     short loc_140040ED1
0x140040eb7  mov     r9d, eax
0x140040eba  lea     r8, aCvdsvolumeDele_0; "CVdsVolume::Delete, .5, hr=%lX"
0x140040ec1  xor     edx, edx
0x140040ec3  mov     ecx, r13d
0x140040ec6  call    cs:__imp_VdsTraceEx
0x140040ecc  jmp     loc_140041135
0x140040ed1  mov     r14d, r12d
0x140040ed4  lea     rcx, [rsi+18h]
0x140040ed8  mov     rax, [rcx]
0x140040edb  lea     r8, [rbp+57h+var_B0]
0x140040edf  lea     rdx, [rbp+57h+var_98]
0x140040ee3  mov     rax, [rax+30h]
0x140040ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040eec  mov     r15d, 1
0x140040ef2  test    eax, eax
0x140040ef4  jns     short loc_140040F0C
0x140040ef6  lea     r8, aCvdsvolumeDele_23; "CVdsVolume::Delete, 1"
0x140040efd  mov     edx, r15d
0x140040f00  mov     ecx, r13d
0x140040f03  call    cs:__imp_VdsTraceEx
0x140040f09  mov     r14d, r15d
0x140040f0c  mov     [rbp+57h+var_A8], r15
0x140040f10  mov     [rbp+57h+var_A0], r12d
0x140040f14  lea     rcx, [rbp+57h+var_A8]; this
0x140040f18  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140040f1d  mov     ebx, eax
0x140040f1f  test    eax, eax
0x140040f21  js      loc_14004112B
0x140040f27  lea     r9, [rbp+57h+var_70]; struct _VDS_VOLUME_PROP *
0x140040f2b  lea     r8, [rbp+57h+var_90]; void **
0x140040f2f  mov     rcx, rsi; this
0x140040f32  call    ?OpenHandle@CVdsVolume@@QEAAJKPEAPEAXPEAU_VDS_VOLUME_PROP@@@Z; CVdsVolume::OpenHandle(ulong,void * *,_VDS_VOLUME_PROP *)
0x140040f37  mov     ebx, eax
0x140040f39  mov     eax, 80000000h
0x140040f3e  lea     ecx, [rbx+rax]
0x140040f41  test    eax, ecx
0x140040f43  jnz     short loc_140040F6B
0x140040f45  cmp     ebx, 80042431h
0x140040f4b  jz      short loc_140040F6B
0x140040f4d  test    edi, edi
0x140040f4f  jnz     short loc_140040F6B
0x140040f51  mov     r9d, ebx
0x140040f54  lea     r8, aCvdsvolumeDele_8; "CVdsVolume::Delete, 2, hr=%lX"
0x140040f5b  xor     edx, edx
0x140040f5d  mov     ecx, r13d
0x140040f60  call    cs:__imp_VdsTraceEx
0x140040f66  jmp     loc_14004112B
0x140040f6b  mov     rcx, [rbp+57h+var_90]
0x140040f6f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140040f73  jz      loc_140041015
0x140040f79  mov     rax, [rbp+57h+var_70.pwszName]
0x140040f7d  mov     [rbp+57h+var_88], rax
0x140040f81  cmp     [rbp+57h+var_70.status], 3
0x140040f85  jnz     short loc_140040FAD
0x140040f87  lea     r8, aCvdsvolumeDele_17; "CVdsVolume::Delete, 3"
0x140040f8e  xor     edx, edx
0x140040f90  mov     ecx, r13d
0x140040f93  call    cs:__imp_VdsTraceEx
0x140040f99  nop
0x140040f9a  lea     rcx, [rbp+57h+var_A8]; this
0x140040f9e  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140040fa3  mov     ebx, 8004255Ah
0x140040fa8  jmp     loc_140041135
0x140040fad  test    [rbp+57h+var_70.ulFlags], 1000383h
0x140040fb4  jz      short loc_140040FDC
0x140040fb6  lea     r8, aCvdsvolumeDele_5; "CVdsVolume::Delete, 4"
0x140040fbd  xor     edx, edx
0x140040fbf  mov     ecx, r13d
0x140040fc2  call    cs:__imp_VdsTraceEx
0x140040fc8  nop
0x140040fc9  lea     rcx, [rbp+57h+var_A8]; this
0x140040fcd  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140040fd2  mov     ebx, 8004290Fh
0x140040fd7  jmp     loc_140041135
0x140040fdc  mov     r8b, r15b
0x140040fdf  mov     edx, edi
0x140040fe1  call    cs:__imp_LockDismountVolume
0x140040fe7  test    eax, eax
0x140040fe9  jz      short loc_140041015
0x140040feb  test    edi, edi
0x140040fed  jnz     short loc_140041015
0x140040fef  lea     r8, aCvdsvolumeDele; "CVdsVolume::Delete, 5"
0x140040ff6  xor     edx, edx
0x140040ff8  mov     ecx, r13d
0x140040ffb  call    cs:__imp_VdsTraceEx
0x140041001  nop
0x140041002  lea     rcx, [rbp+57h+var_A8]; this
0x140041006  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14004100b  mov     ebx, 80042413h
0x140041010  jmp     loc_140041135
0x140041015  mov     r15d, r12d
0x140041018  mov     rcx, [rsi+80h]
0x14004101f  mov     rax, [rcx]
0x140041022  mov     edx, 1
0x140041027  mov     rax, [rax+58h]
0x14004102b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041030  mov     ebx, eax
0x140041032  test    eax, eax
0x140041034  jns     short loc_140041050
0x140041036  mov     r9d, eax
0x140041039  lea     r8, aCvdsvolumeDele_20; "CVdsVolume::Delete, 6, hr=%lX"
0x140041040  xor     edx, edx
0x140041042  mov     ecx, r13d
0x140041045  call    cs:__imp_VdsTraceEx
0x14004104b  jmp     loc_140041101
0x140041050  test    r14d, r14d
0x140041053  jnz     short loc_1400410A6
0x140041055  mov     edi, r12d
0x140041058  cmp     [rbp+57h+var_B0], r12d
0x14004105c  jle     short loc_1400410A6
0x14004105e  movsxd  rcx, edi
0x140041061  mov     rax, [rbp+57h+var_98]
0x140041065  mov     rcx, [rax+rcx*8]; lpszVolumeMountPoint
0x140041069  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004106d  inc     rax
0x140041070  cmp     [rcx+rax*2], r12w
0x140041075  jnz     short loc_14004106D
0x140041077  cmp     rax, 3
0x14004107b  jbe     short loc_14004109F
0x14004107d  call    cs:__imp_DeleteVolumeMountPointW
0x140041083  test    eax, eax
0x140041085  jnz     short loc_14004109F
0x140041087  lea     r8, aCvdsvolumeDele_14; "CVdsVolume::Delete, 7"
0x14004108e  xor     edx, edx
0x140041090  mov     ecx, r13d
0x140041093  call    cs:__imp_VdsTraceEx
0x140041099  mov     r15d, 1
0x14004109f  inc     edi
0x1400410a1  cmp     edi, [rbp+57h+var_B0]
0x1400410a4  jl      short loc_14004105E
0x1400410a6  call    cs:__imp_GarbageCollectDriveLetters
0x1400410ac  mov     rdx, [rsi+80h]; struct IUnknown *
0x1400410b3  mov     rcx, [rsi+78h]; this
0x1400410b7  call    ?FindFSPropertiesInMap@CVdsService@@QEAAPEAXPEAUIUnknown@@@Z; CVdsService::FindFSPropertiesInMap(IUnknown *)
0x1400410bc  mov     rdi, rax
0x1400410bf  test    rax, rax
0x1400410c2  jz      short loc_140041101
0x1400410c4  mov     rdx, [rsi+80h]; struct IUnknown *
0x1400410cb  mov     rcx, [rsi+78h]; this
0x1400410cf  call    ?RemoveFSPropertiesFromMap@CVdsService@@QEAAHPEAUIUnknown@@@Z; CVdsService::RemoveFSPropertiesFromMap(IUnknown *)
0x1400410d4  test    eax, eax
0x1400410d6  jnz     short loc_1400410ED
0x1400410d8  call    cs:__imp_GetLastError
0x1400410de  mov     r9d, eax
0x1400410e1  lea     r8, aCvdsvolumeDele_6; "CVdsVolume::Delete, 9, hr=%ld"
0x1400410e8  jmp     loc_140041040
0x1400410ed  call    cs:__imp_GetProcessHeap
0x1400410f3  mov     rcx, rax
0x1400410f6  mov     r8, rdi
0x1400410f9  xor     edx, edx
0x1400410fb  call    cs:__imp_VdsHeapFree
0x140041101  test    r14d, r14d
0x140041104  jnz     short loc_140041118
0x140041106  mov     rcx, [rbp+57h+var_98]
0x14004110a  test    rcx, rcx
0x14004110d  jz      short loc_140041118
0x14004110f  mov     edx, [rbp+57h+var_B0]
0x140041112  call    cs:__imp_CoFreeStringArray
0x140041118  test    ebx, ebx
0x14004111a  js      short loc_14004112B
0x14004111c  test    r14d, r14d
0x14004111f  jnz     short loc_140041126
0x140041121  test    r15d, r15d
0x140041124  jz      short loc_14004112B
0x140041126  mov     ebx, 44244h
0x14004112b  lea     rcx, [rbp+57h+var_A8]; this
0x14004112f  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140041134  nop
0x140041135  lea     rcx, [rbp+57h+var_80]
0x140041139  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14004113f  nop
0x140041140  lea     rcx, [rbp+57h+var_90]
0x140041144  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x140041149  nop
0x14004114a  lea     rcx, [rbp+57h+var_88]
0x14004114e  call    ??1?$CVdsCoTaskPtr@G@@QEAA@XZ; CVdsCoTaskPtr<ushort>::~CVdsCoTaskPtr<ushort>(void)
0x140041153  mov     eax, ebx
0x140041155  mov     rcx, [rbp+57h+var_38]
0x140041159  xor     rcx, rsp; StackCookie
0x14004115c  call    __security_check_cookie
0x140041161  mov     rbx, [rsp+0D0h+arg_10]
0x140041169  add     rsp, 0A0h
0x140041170  pop     r15
0x140041172  pop     r14
0x140041174  pop     r13
0x140041176  pop     r12
0x140041178  pop     rdi
0x140041179  pop     rsi
0x14004117a  pop     rbp
0x14004117b  retn
```
