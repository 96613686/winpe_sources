# CVdsSubSystem::CreateLun2(_VDS_LUN_TYPE,unsigned __int64,_GUID *,long,ushort *,_VDS_HINTS2 *,IVdsAsync * *)

- ea: `0x14001ea80`
- end: `0x14001ec63`
- name: `?CreateLun2@CVdsSubSystem@@UEAAJW4_VDS_LUN_TYPE@@_KPEAU_GUID@@JPEAGPEAU_VDS_HINTS2@@PEAPEAUIVdsAsync@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(CVdsSubSystem *__hidden this, enum _VDS_LUN_TYPE, unsigned __int64, struct _GUID *, int, unsigned __int16 *, struct _VDS_HINTS2 *, struct IVdsAsync **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400025b0`
- `0x14000f98c`
- `0x140010b04`
- `0x140012c48`
- `0x14001ea80`
- `0x140031c50`
- `0x140056010`

## import_xrefs

- `vdsutil!VdsTraceEx` at `0x14001ead2`
- `vdsutil!VdsTraceEx` at `0x14001eaf5`
- `vdsutil!VdsTraceEx` at `0x14001ebae`
- `vdsutil!VdsTraceEx` at `0x14001ec15`
- `vdsutil!VdsTraceEx` at `0x14001ead2`
- `vdsutil!VdsTraceEx` at `0x14001eaf5`
- `vdsutil!VdsTraceEx` at `0x14001ebae`
- `vdsutil!VdsTraceEx` at `0x14001ec15`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001eaba`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001eaba`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001eb42`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001ebc6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001ec2d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001ec55`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001eb42`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001ebc6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001ec2d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001ec55`

## string_xrefs

- `0x14001eaa8`: `CVdsSubSystem::CreateLun2()`
- `0x14001eac6`: `CVdsSubSystem::CreateLun2, NULL pDriveIdArray`
- `0x14001eae9`: `CVdsSubSystem::CreateLun2, 1, hr=%lX`
- `0x14001eba2`: `CVdsSubSystem::CreateLun2, 1, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CVdsSubSystem::CreateLun2(
        CVdsSubSystem *this,
        unsigned int a2,
        __int64 a3,
        struct _GUID *a4,
        int a5,
        unsigned __int16 *a6,
        struct _VDS_HINTS2 *a7,
        struct IVdsAsync **a8)
{
  int v12; // ebx
  struct IVdsAsync **v13; // r14
  void *Instance; // rax
  struct CVdsAsyncObject *v15; // rdi
  int v16; // eax
  int v18; // eax
  _BYTE v19[24]; // [rsp+50h] [rbp-18h] BYREF
  struct IVdsAsync *v20; // [rsp+B0h] [rbp+48h] BYREF

  v20 = 0;
  v12 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v19, 0x5Eu, "CVdsSubSystem::CreateLun2()");
  if ( !a4 )
    VdsTraceEx(94, 0, "CVdsSubSystem::CreateLun2, NULL pDriveIdArray");
  if ( !*((_QWORD *)this + 19) )
  {
    v12 = -2147418113;
    VdsTraceEx(94, 0, "CVdsSubSystem::CreateLun2, 1, hr=%lX", -2147418113);
  }
  v13 = a8;
  *a8 = 0;
  a8 = 0;
  Instance = VdsCreateInstance(VDS_OT_ASYNC);
  ATL::CComPtrBase<CVdsEnumObject>::Attach((__int64 *)&a8, (__int64)Instance);
  v15 = (struct CVdsAsyncObject *)a8;
  if ( !a8 )
  {
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&a8);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v19);
    v12 = -2147024882;
    goto LABEL_11;
  }
  *((_DWORD *)a8 + 22) = 50;
  if ( v12 < 0 )
  {
LABEL_10:
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&a8);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v19);
    goto LABEL_11;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, struct _GUID *, int, unsigned __int16 *, struct _VDS_HINTS2 *, struct IVdsAsync **))(**((_QWORD **)this + 19) + 40LL))(
          *((_QWORD *)this + 19),
          a2,
          a3,
          a4,
          a5,
          a6,
          a7,
          &v20);
  v12 = v16;
  if ( v16 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsSubSystem::CreateLun2, 1, hr=%lX", v16);
    goto LABEL_10;
  }
  v18 = ConnectAsyncWrapper(v15, v20, *((struct CVdsService **)this + 14));
  v12 = v18;
  if ( v18 >= 0 )
  {
    a8 = 0;
    *v13 = (struct IVdsAsync *)v15;
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&a8);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v19);
    v12 = 0;
  }
  else
  {
    VdsTraceEx(94, 0, "VDS(%X): unexpected failure connecting async wrapper: %X", 34144260, v18);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&a8);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v19);
  }
LABEL_11:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14001ea80  push    rbp
0x14001ea82  push    rbx
0x14001ea83  push    rsi
0x14001ea84  push    rdi
0x14001ea85  push    r12
0x14001ea87  push    r13
0x14001ea89  push    r14
0x14001ea8b  push    r15
0x14001ea8d  mov     rbp, rsp
0x14001ea90  sub     rsp, 68h
0x14001ea94  mov     r15, r9
0x14001ea97  mov     r12, r8
0x14001ea9a  mov     r13d, edx
0x14001ea9d  mov     rsi, rcx
0x14001eaa0  xor     edi, edi
0x14001eaa2  mov     [rbp+arg_0], rdi
0x14001eaa6  mov     ebx, edi
0x14001eaa8  lea     r8, aCvdssubsystemC_5; "CVdsSubSystem::CreateLun2()"
0x14001eaaf  lea     r14d, [rdi+5Eh]
0x14001eab3  mov     edx, r14d
0x14001eab6  lea     rcx, [rbp+var_18]
0x14001eaba  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001eac0  nop
0x14001eac1  test    r15, r15
0x14001eac4  jnz     short loc_14001EAD8
0x14001eac6  lea     r8, aCvdssubsystemC_0; "CVdsSubSystem::CreateLun2, NULL pDriveI"...
0x14001eacd  xor     edx, edx
0x14001eacf  mov     ecx, r14d
0x14001ead2  call    cs:__imp_VdsTraceEx
0x14001ead8  cmp     [rsi+98h], rdi
0x14001eadf  jnz     short loc_14001EAFB
0x14001eae1  mov     ebx, 8000FFFFh
0x14001eae6  mov     r9d, ebx
0x14001eae9  lea     r8, aCvdssubsystemC_6; "CVdsSubSystem::CreateLun2, 1, hr=%lX"
0x14001eaf0  xor     edx, edx
0x14001eaf2  mov     ecx, r14d
0x14001eaf5  call    cs:__imp_VdsTraceEx
0x14001eafb  mov     r14, [rbp+arg_38]
0x14001eb02  mov     [r14], rdi
0x14001eb05  mov     [rbp+arg_38], rdi
0x14001eb0c  mov     ecx, 64h ; 'd'; enum _VDS_OBJECT_TYPE
0x14001eb11  call    ?VdsCreateInstance@@YAPEAXW4_VDS_OBJECT_TYPE@@@Z; VdsCreateInstance(_VDS_OBJECT_TYPE)
0x14001eb16  mov     rdx, rax
0x14001eb19  lea     rcx, [rbp+arg_38]
0x14001eb20  call    ?Attach@?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAAXPEAVCVdsEnumObject@@@Z; ATL::CComPtrBase<CVdsEnumObject>::Attach(CVdsEnumObject *)
0x14001eb25  mov     rdi, [rbp+arg_38]
0x14001eb2c  test    rdi, rdi
0x14001eb2f  jnz     short loc_14001EB50
0x14001eb31  lea     rcx, [rbp+arg_38]
0x14001eb38  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001eb3d  nop
0x14001eb3e  lea     rcx, [rbp+var_18]
0x14001eb42  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001eb48  nop
0x14001eb49  mov     ebx, 8007000Eh
0x14001eb4e  jmp     short loc_14001EBCD
0x14001eb50  mov     dword ptr [rdi+58h], 32h ; '2'
0x14001eb57  test    ebx, ebx
0x14001eb59  js      short loc_14001EBB5
0x14001eb5b  mov     rcx, [rsi+98h]
0x14001eb62  mov     rax, [rcx]
0x14001eb65  lea     rdx, [rbp+arg_0]
0x14001eb69  mov     [rsp+68h+var_30], rdx
0x14001eb6e  mov     rdx, [rbp+arg_30]
0x14001eb72  mov     [rsp+68h+var_38], rdx
0x14001eb77  mov     rdx, [rbp+arg_28]
0x14001eb7b  mov     [rsp+68h+var_40], rdx
0x14001eb80  mov     edx, [rbp+arg_20]
0x14001eb83  mov     [rsp+68h+var_48], edx
0x14001eb87  mov     r9, r15
0x14001eb8a  mov     r8, r12
0x14001eb8d  mov     edx, r13d
0x14001eb90  mov     rax, [rax+28h]
0x14001eb94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001eb99  mov     ebx, eax
0x14001eb9b  test    eax, eax
0x14001eb9d  jns     short loc_14001EBE9
0x14001eb9f  mov     r9d, eax
0x14001eba2  lea     r8, aCvdssubsystemC_6; "CVdsSubSystem::CreateLun2, 1, hr=%lX"
0x14001eba9  xor     edx, edx
0x14001ebab  lea     ecx, [rdx+5Eh]
0x14001ebae  call    cs:__imp_VdsTraceEx
0x14001ebb4  nop
0x14001ebb5  lea     rcx, [rbp+arg_38]
0x14001ebbc  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001ebc1  nop
0x14001ebc2  lea     rcx, [rbp+var_18]
0x14001ebc6  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001ebcc  nop
0x14001ebcd  lea     rcx, [rbp+arg_0]
0x14001ebd1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001ebd6  mov     eax, ebx
0x14001ebd8  add     rsp, 68h
0x14001ebdc  pop     r15
0x14001ebde  pop     r14
0x14001ebe0  pop     r13
0x14001ebe2  pop     r12
0x14001ebe4  pop     rdi
0x14001ebe5  pop     rsi
0x14001ebe6  pop     rbx
0x14001ebe7  pop     rbp
0x14001ebe8  retn
0x14001ebe9  mov     r8, [rsi+70h]; struct CVdsService *
0x14001ebed  mov     rdx, [rbp+arg_0]; struct IVdsAsync *
0x14001ebf1  mov     rcx, rdi; struct CVdsAsyncObject *
0x14001ebf4  call    ?ConnectAsyncWrapper@@YAJPEAVCVdsAsyncObject@@PEAUIVdsAsync@@PEAVCVdsService@@@Z; ConnectAsyncWrapper(CVdsAsyncObject *,IVdsAsync *,CVdsService *)
0x14001ebf9  mov     ebx, eax
0x14001ebfb  test    eax, eax
0x14001ebfd  jns     short loc_14001EC36
0x14001ebff  mov     [rsp+68h+var_48], eax
0x14001ec03  mov     r9d, 2090004h
0x14001ec09  lea     r8, aVdsXUnexpected; "VDS(%X): unexpected failure connecting "...
0x14001ec10  xor     edx, edx
0x14001ec12  lea     ecx, [rdx+5Eh]
0x14001ec15  call    cs:__imp_VdsTraceEx
0x14001ec1b  nop
0x14001ec1c  lea     rcx, [rbp+arg_38]
0x14001ec23  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001ec28  nop
0x14001ec29  lea     rcx, [rbp+var_18]
0x14001ec2d  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001ec33  nop
0x14001ec34  jmp     short loc_14001EBCD
0x14001ec36  mov     [rbp+arg_38], 0
0x14001ec41  mov     [r14], rdi
0x14001ec44  lea     rcx, [rbp+arg_38]
0x14001ec4b  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001ec50  nop
0x14001ec51  lea     rcx, [rbp+var_18]
0x14001ec55  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001ec5b  nop
0x14001ec5c  xor     ebx, ebx
0x14001ec5e  jmp     loc_14001EBCD
```
