# CVdsService::GetObjectW(_GUID,_VDS_OBJECT_TYPE,IUnknown * *)

- ea: `0x14000e920`
- end: `0x14000eb14`
- name: `?GetObjectW@CVdsService@@UEAAJU_GUID@@W4_VDS_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z`
- size: `500`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, struct _GUID *__struct_ptr, enum _VDS_OBJECT_TYPE, struct IUnknown **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x140001980`
- `0x140003710`
- `0x140004360`
- `0x14000d6e0`
- `0x14000dd3c`
- `0x14000e920`
- `0x14001fcf0`
- `0x14002918c`
- `0x14003972c`
- `0x140056010`

## import_xrefs

- `vdsutil!VdsTraceEx` at `0x14000ea4c`
- `vdsutil!VdsTraceEx` at `0x14000ea6d`
- `vdsutil!VdsTraceEx` at `0x14000ead6`
- `vdsutil!VdsTraceEx` at `0x14000ea4c`
- `vdsutil!VdsTraceEx` at `0x14000ea6d`
- `vdsutil!VdsTraceEx` at `0x14000ead6`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000e954`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000e954`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000eaff`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000eaff`

## string_xrefs

- `0x14000e944`: `CVdsService::GetObject()`
- `0x14000ea3d`: `CVdsService::GetObject, 1, hr=%lX`
- `0x14000ea63`: `CVdsService::GetObject, 2, hr=%lX`
- `0x14000eaca`: `CVdsService::GetObject, 3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::GetObjectW(
        struct _RTL_CRITICAL_SECTION *this,
        struct _GUID *a2,
        unsigned __int32 a3,
        struct IUnknown **a4)
{
  signed int v8; // ebx
  int Disk; // eax
  int ObjectFromProviders; // eax
  struct IUnknown *Wrapper; // rbx
  struct IUnknown *v12; // rcx
  __int64 v14; // [rsp+20h] [rbp-38h] BYREF
  int v15; // [rsp+28h] [rbp-30h]
  struct _GUID v16; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v17[24]; // [rsp+40h] [rbp-18h] BYREF
  struct IUnknown *v18; // [rsp+90h] [rbp+38h] BYREF

  v18 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v17, 0x5Eu, "CVdsService::GetObject()");
  *a4 = 0;
  v8 = (*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *))&this->DebugInfo->EntryCount)(this);
  if ( v8 < 0 )
    goto LABEL_24;
  v14 = 0;
  v15 = 0;
  v8 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v14);
  if ( v8 < 0 )
  {
LABEL_3:
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v14);
    goto LABEL_24;
  }
  switch ( a3 )
  {
    case 0xDu:
      v16 = *a2;
      Disk = CVdsService::GetDisk(&v16, &v18);
      break;
    case 0x5Au:
      v16 = *a2;
      Disk = CVdsService::GetHbaPort(&v16, &v18);
      break;
    case 0x5Bu:
      v16 = *a2;
      Disk = CVdsService::GetInitiatorAdapter(&v16, &v18);
      break;
    case 0x5Cu:
      v16 = *a2;
      Disk = CVdsService::GetInitiatorPortal(&v16, &v18);
      break;
    default:
      goto LABEL_13;
  }
  v8 = Disk;
  if ( Disk < 0 )
  {
LABEL_13:
    v16 = *a2;
    ObjectFromProviders = CVdsService::GetObjectFromProviders(&v16, a3, &v18);
    v8 = ObjectFromProviders;
    if ( ObjectFromProviders < 0 )
    {
      VdsTraceEx(94, 1, "CVdsService::GetObject, 1, hr=%lX", ObjectFromProviders);
      goto LABEL_3;
    }
  }
  if ( v18 )
  {
    Wrapper = CVdsService::FindOrCreateWrapper(this, v18, (enum _VDS_OBJECT_TYPE)a3, 0);
    v12 = v18;
    if ( v18 )
    {
      ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->Release)(v18);
      v12 = 0;
      v18 = 0;
    }
    if ( Wrapper )
    {
      *a4 = Wrapper;
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v14);
      v8 = 0;
    }
    else
    {
      if ( v12 )
      {
        ((void (__fastcall *)(struct IUnknown *))v12->lpVtbl->Release)(v12);
        v18 = 0;
      }
      VdsTraceEx(94, 0, "CVdsService::GetObject, 3");
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v14);
      v8 = -2147024882;
    }
  }
  else
  {
    VdsTraceEx(94, 0, "CVdsService::GetObject, 2, hr=%lX", v8);
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v14);
    v8 = -2147212283;
  }
LABEL_24:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000e920  push    rbp
0x14000e922  push    rbx
0x14000e923  push    rsi
0x14000e924  push    rdi
0x14000e925  push    r14
0x14000e927  push    r15
0x14000e929  mov     rbp, rsp
0x14000e92c  sub     rsp, 58h
0x14000e930  mov     r14, r9
0x14000e933  mov     esi, r8d
0x14000e936  mov     rdi, rdx
0x14000e939  mov     r15, rcx
0x14000e93c  mov     [rbp+arg_0], 0
0x14000e944  lea     r8, aCvdsserviceGet_41; "CVdsService::GetObject()"
0x14000e94b  mov     edx, 5Eh ; '^'
0x14000e950  lea     rcx, [rbp+var_18]
0x14000e954  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000e95a  nop
0x14000e95b  mov     qword ptr [r14], 0
0x14000e962  mov     rax, [r15]
0x14000e965  mov     rcx, r15
0x14000e968  mov     rax, [rax+20h]
0x14000e96c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e971  mov     ebx, eax
0x14000e973  test    eax, eax
0x14000e975  js      loc_14000EAFB
0x14000e97b  mov     [rbp+var_38], 0
0x14000e983  mov     [rbp+var_30], 0
0x14000e98a  lea     rcx, [rbp+var_38]; this
0x14000e98e  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x14000e993  mov     ebx, eax
0x14000e995  test    eax, eax
0x14000e997  jns     short loc_14000E9A7
0x14000e999  lea     rcx, [rbp+var_38]; this
0x14000e99d  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14000e9a2  jmp     loc_14000EAFB
0x14000e9a7  mov     ecx, esi
0x14000e9a9  sub     ecx, 0Dh
0x14000e9ac  jz      short loc_14000EA02
0x14000e9ae  sub     ecx, 4Dh ; 'M'
0x14000e9b1  jz      short loc_14000E9EB
0x14000e9b3  sub     ecx, 1
0x14000e9b6  jz      short loc_14000E9D4
0x14000e9b8  cmp     ecx, 1
0x14000e9bb  jnz     short loc_14000EA1D
0x14000e9bd  movups  xmm0, xmmword ptr [rdi]
0x14000e9c0  movdqu  xmmword ptr [rbp+var_28.Data1], xmm0
0x14000e9c5  lea     rdx, [rbp+arg_0]; struct IUnknown **
0x14000e9c9  lea     rcx, [rbp+var_28]; struct _GUID
0x14000e9cd  call    ?GetInitiatorPortal@CVdsService@@SAJU_GUID@@PEAPEAUIUnknown@@@Z; CVdsService::GetInitiatorPortal(_GUID,IUnknown * *)
0x14000e9d2  jmp     short loc_14000EA17
0x14000e9d4  movups  xmm0, xmmword ptr [rdi]
0x14000e9d7  movdqu  xmmword ptr [rbp+var_28.Data1], xmm0
0x14000e9dc  lea     rdx, [rbp+arg_0]; struct IUnknown **
0x14000e9e0  lea     rcx, [rbp+var_28]; struct _GUID
0x14000e9e4  call    ?GetInitiatorAdapter@CVdsService@@SAJU_GUID@@PEAPEAUIUnknown@@@Z; CVdsService::GetInitiatorAdapter(_GUID,IUnknown * *)
0x14000e9e9  jmp     short loc_14000EA17
0x14000e9eb  movups  xmm0, xmmword ptr [rdi]
0x14000e9ee  movdqu  xmmword ptr [rbp+var_28.Data1], xmm0
0x14000e9f3  lea     rdx, [rbp+arg_0]; struct IUnknown **
0x14000e9f7  lea     rcx, [rbp+var_28]; struct _GUID
0x14000e9fb  call    ?GetHbaPort@CVdsService@@SAJU_GUID@@PEAPEAUIUnknown@@@Z; CVdsService::GetHbaPort(_GUID,IUnknown * *)
0x14000ea00  jmp     short loc_14000EA17
0x14000ea02  movups  xmm0, xmmword ptr [rdi]
0x14000ea05  movdqu  xmmword ptr [rbp+var_28.Data1], xmm0
0x14000ea0a  lea     rdx, [rbp+arg_0]; struct IUnknown **
0x14000ea0e  lea     rcx, [rbp+var_28]; struct _GUID
0x14000ea12  call    ?GetDisk@CVdsService@@SAJU_GUID@@PEAPEAUIUnknown@@@Z; CVdsService::GetDisk(_GUID,IUnknown * *)
0x14000ea17  mov     ebx, eax
0x14000ea19  test    eax, eax
0x14000ea1b  jns     short loc_14000EA57
0x14000ea1d  movups  xmm0, xmmword ptr [rdi]
0x14000ea20  movdqu  xmmword ptr [rbp+var_28.Data1], xmm0
0x14000ea25  lea     r8, [rbp+arg_0]; struct IUnknown **
0x14000ea29  mov     edx, esi; enum _VDS_OBJECT_TYPE
0x14000ea2b  lea     rcx, [rbp+var_28]; struct _GUID
0x14000ea2f  call    ?GetObjectFromProviders@CVdsService@@SAJU_GUID@@W4_VDS_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z; CVdsService::GetObjectFromProviders(_GUID,_VDS_OBJECT_TYPE,IUnknown * *)
0x14000ea34  mov     ebx, eax
0x14000ea36  test    eax, eax
0x14000ea38  jns     short loc_14000EA57
0x14000ea3a  mov     r9d, eax
0x14000ea3d  lea     r8, aCvdsserviceGet_81; "CVdsService::GetObject, 1, hr=%lX"
0x14000ea44  mov     edx, 1
0x14000ea49  lea     ecx, [rdx+5Dh]
0x14000ea4c  call    cs:__imp_VdsTraceEx
0x14000ea52  jmp     loc_14000E999
0x14000ea57  mov     rdx, [rbp+arg_0]; struct IUnknown *
0x14000ea5b  test    rdx, rdx
0x14000ea5e  jnz     short loc_14000EA84
0x14000ea60  mov     r9d, ebx
0x14000ea63  lea     r8, aCvdsserviceGet_20; "CVdsService::GetObject, 2, hr=%lX"
0x14000ea6a  lea     ecx, [rdx+5Eh]
0x14000ea6d  call    cs:__imp_VdsTraceEx
0x14000ea73  nop
0x14000ea74  lea     rcx, [rbp+var_38]; this
0x14000ea78  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14000ea7d  mov     ebx, 80042405h
0x14000ea82  jmp     short loc_14000EAFB
0x14000ea84  xor     r9d, r9d; unsigned int **
0x14000ea87  mov     r8d, esi; enum _VDS_OBJECT_TYPE
0x14000ea8a  mov     rcx, r15; this
0x14000ea8d  call    ?FindOrCreateWrapper@CVdsService@@QEAAPEAUIUnknown@@PEAU2@W4_VDS_OBJECT_TYPE@@PEAPEAK@Z; CVdsService::FindOrCreateWrapper(IUnknown *,_VDS_OBJECT_TYPE,ulong * *)
0x14000ea92  mov     rbx, rax
0x14000ea95  mov     rcx, [rbp+arg_0]
0x14000ea99  test    rcx, rcx
0x14000ea9c  jz      short loc_14000EAB0
0x14000ea9e  mov     rdx, [rcx]
0x14000eaa1  mov     rax, [rdx+10h]
0x14000eaa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eaaa  xor     ecx, ecx
0x14000eaac  mov     [rbp+arg_0], rcx
0x14000eab0  test    rbx, rbx
0x14000eab3  jnz     short loc_14000EAED
0x14000eab5  test    rcx, rcx
0x14000eab8  jz      short loc_14000EACA
0x14000eaba  mov     rax, [rcx]
0x14000eabd  mov     rax, [rax+10h]
0x14000eac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eac6  mov     [rbp+arg_0], rbx
0x14000eaca  lea     r8, aCvdsserviceGet_45; "CVdsService::GetObject, 3"
0x14000ead1  xor     edx, edx
0x14000ead3  lea     ecx, [rdx+5Eh]
0x14000ead6  call    cs:__imp_VdsTraceEx
0x14000eadc  nop
0x14000eadd  lea     rcx, [rbp+var_38]; this
0x14000eae1  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14000eae6  mov     ebx, 8007000Eh
0x14000eaeb  jmp     short loc_14000EAFB
0x14000eaed  mov     [r14], rbx
0x14000eaf0  lea     rcx, [rbp+var_38]; this
0x14000eaf4  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14000eaf9  xor     ebx, ebx
0x14000eafb  lea     rcx, [rbp+var_18]
0x14000eaff  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000eb05  mov     eax, ebx
0x14000eb07  add     rsp, 58h
0x14000eb0b  pop     r15
0x14000eb0d  pop     r14
0x14000eb0f  pop     rdi
0x14000eb10  pop     rsi
0x14000eb11  pop     rbx
0x14000eb12  pop     rbp
0x14000eb13  retn
```
