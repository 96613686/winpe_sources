# CVdsDiskLun::Shrink(unsigned __int64,IVdsAsync * *)

- ea: `0x14001c250`
- end: `0x14001c70a`
- name: `?Shrink@CVdsDiskLun@@UEAAJ_KPEAPEAUIVdsAsync@@@Z`
- size: `1210`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this, unsigned __int64, struct IVdsAsync **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400025b0`
- `0x14000f98c`
- `0x140010b04`
- `0x140012c48`
- `0x14001c250`
- `0x14002e123`
- `0x140031c50`
- `0x140045758`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c60a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c61e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c644`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c66a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c67d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c690`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c60a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c61e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c644`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c66a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c67d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c690`
- `vdsutil!VdsTraceEx` at `0x14001c45e`
- `vdsutil!VdsTraceEx` at `0x14001c5fa`
- `vdsutil!VdsTraceEx` at `0x14001c45e`
- `vdsutil!VdsTraceEx` at `0x14001c5fa`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001c2d7`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001c2d7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001c312`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001c6c5`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001c312`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001c6c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CVdsDiskLun::Shrink(CVdsDiskLun *this, unsigned __int64 a2, struct IVdsAsync **a3)
{
  void *Instance; // rax
  struct CVdsAsyncObject *v7; // rsi
  unsigned int v8; // ebx
  const char *v9; // r8
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // r9
  const wchar_t *pwszDevicePath; // r9
  int EndOfLastVolume; // eax
  struct IVdsDisk *v16; // [rsp+20h] [rbp-E0h] BYREF
  struct CVdsAsyncObject *v17; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  struct IVdsAsync *v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[24]; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v23[12]; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int64 v24; // [rsp+70h] [rbp-90h]
  LPVOID pv; // [rsp+78h] [rbp-88h]
  LPVOID v26; // [rsp+80h] [rbp-80h]
  LPVOID v27; // [rsp+88h] [rbp-78h]
  int v28; // [rsp+98h] [rbp-68h]
  _VDS_DISK_PROP v29; // [rsp+B0h] [rbp-50h] BYREF

  v16 = 0;
  v22 = 0;
  memset_0(v23, 0, 0x44u);
  v29.id.Data1 = 0;
  memset_0(&v29.id.Data2, 0, 0x7Cu);
  v18 = 0;
  v19 = 0;
  v20 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v21, 0x5Eu, "CVdsDiskLun::Shrink()");
  v17 = 0;
  Instance = VdsCreateInstance(VDS_OT_ASYNC);
  ATL::CComPtrBase<CVdsEnumObject>::Attach((__int64 *)&v17, (__int64)Instance);
  v7 = v17;
  if ( !v17 )
  {
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v17);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v21);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
    v8 = -2147024882;
    goto LABEL_72;
  }
  *((_DWORD *)v17 + 22) = 55;
  if ( !a3 )
  {
    v8 = -2147024809;
    v9 = "CVdsDiskLun::Shrink, 0, hr=%lX";
LABEL_51:
    v12 = v8;
    goto LABEL_52;
  }
  *a3 = 0;
  v10 = *((_QWORD *)this + 24);
  if ( !v10 )
  {
    v8 = -2147212216;
    v9 = "CVdsDiskLun::Shrink, 1, hr=%lX";
    goto LABEL_51;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 24LL))(v10, &v22);
  v8 = v11;
  if ( v11 < 0 )
  {
    v9 = "CVdsDiskLun::Shrink, 2, hr=%lX";
LABEL_9:
    v12 = (unsigned int)v11;
LABEL_52:
    VdsTraceEx(94, 0, v9, v12, v16);
    goto LABEL_53;
  }
  if ( a2 >= v24 )
  {
    v8 = -2147211241;
    v9 = "CVdsDiskLun::Shrink, 3, hr=%lX";
    goto LABEL_51;
  }
  switch ( v28 )
  {
    case 2:
      v8 = -2147211236;
      v9 = "CVdsDiskLun::Shrink, 5, hr=%lX";
      goto LABEL_51;
    case 4:
      v8 = -2147211235;
      v9 = "CVdsDiskLun::Shrink, 4, hr=%lX";
      goto LABEL_51;
    case 5:
      v8 = -2147211234;
      v9 = "CVdsDiskLun::Shrink, 6, hr=%lX";
      goto LABEL_51;
  }
  v11 = (**((__int64 (__fastcall ***)(char *, GUID *, struct IVdsDisk **))this - 11))(
          (char *)this - 88,
          &IID_IVdsDisk,
          &v16);
  v8 = v11;
  if ( v11 == -2147467262 )
  {
    v8 = -2147210979;
    v9 = "CVdsDiskLun::Shrink, 7, hr=%lX";
    goto LABEL_51;
  }
  if ( v11 < 0 )
  {
    v9 = "CVdsDiskLun::Shrink, 8, hr=%lX";
    goto LABEL_9;
  }
  v11 = ((__int64 (__fastcall *)(struct IVdsDisk *, _VDS_DISK_PROP *))v16->lpVtbl->GetProperties)(v16, &v29);
  v8 = v11;
  if ( v11 < 0 )
  {
    v9 = "CVdsDiskLun::Shrink, 9, hr=%lX";
    goto LABEL_9;
  }
  pwszDevicePath = L"UNKNOWN";
  if ( v29.pwszDevicePath )
    pwszDevicePath = v29.pwszDevicePath;
  VdsTraceEx(94, 3, "CVdsDiskLun::Shrink, 10, name=%S", pwszDevicePath);
  if ( (v29.ulFlags & 0x40) != 0 )
  {
    v8 = -2147210978;
    v9 = "CVdsDiskLun::Shrink, 11, hr=%lX";
    goto LABEL_51;
  }
  if ( (v29.ulFlags & 0x2000) != 0 )
  {
    v8 = -2147210976;
    v9 = "CVdsDiskLun::Shrink, 12, hr=%lX";
    goto LABEL_51;
  }
  switch ( v29.status )
  {
    case VDS_DS_NOT_READY:
      v8 = -2147211238;
      v9 = "CVdsDiskLun::Shrink, 16, hr=%lX";
      goto LABEL_51;
    case VDS_DS_NO_MEDIA:
      v8 = -2147211237;
      v9 = "CVdsDiskLun::Shrink, 17, hr=%lX";
      goto LABEL_51;
    case VDS_DS_FAILED:
      v8 = -2147211239;
      v9 = "CVdsDiskLun::Shrink, 15, hr=%lX";
      goto LABEL_51;
    case VDS_DS_MISSING:
      v8 = -2147211240;
      v9 = "CVdsDiskLun::Shrink, 14, hr=%lX";
      goto LABEL_51;
  }
  EndOfLastVolume = CVdsDiskLun::FindEndOfLastVolume((CVdsDiskLun *)(unsigned int)(v29.status - 5), v16, &v29, &v18);
  v8 = EndOfLastVolume;
  if ( EndOfLastVolume < 0 )
  {
    v9 = "CVdsDiskLun::Shrink, 18, hr=%lX";
LABEL_33:
    v12 = (unsigned int)EndOfLastVolume;
    goto LABEL_52;
  }
  if ( v18 >= v24 - a2 )
  {
    v8 = -2147211242;
    v9 = "CVdsDiskLun::Shrink, 19, hr=%lX";
    goto LABEL_51;
  }
  if ( v29.PartitionStyle == VDS_PST_GPT && v24 - a2 - v18 < 0x10000 )
  {
    v8 = -2147210974;
    v9 = "CVdsDiskLun::Shrink, 20, hr=%lX";
    goto LABEL_51;
  }
  EndOfLastVolume = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, struct IVdsAsync **))(**((_QWORD **)this + 24)
                                                                                             + 64LL))(
                      *((_QWORD *)this + 24),
                      a2,
                      &v19);
  v8 = EndOfLastVolume;
  if ( EndOfLastVolume < 0 )
  {
    v9 = "CVdsDiskLun::Shrink, 21, hr=%lX";
    goto LABEL_33;
  }
  EndOfLastVolume = ConnectAsyncWrapper(v7, v19, *((struct CVdsService **)this + 16));
  v8 = EndOfLastVolume;
  if ( EndOfLastVolume < 0 )
  {
    v9 = "CVdsDiskLun::Shrink, 22, %lX";
    goto LABEL_33;
  }
  v17 = 0;
  *a3 = (struct IVdsAsync *)v7;
LABEL_53:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v26 )
  {
    CoTaskMemFree(v26);
    v26 = 0;
  }
  if ( v27 )
  {
    CoTaskMemFree(v27);
    v27 = 0;
  }
  if ( v29.pwszDiskAddress )
  {
    CoTaskMemFree(v29.pwszDiskAddress);
    v29.pwszDiskAddress = 0;
  }
  if ( v29.pwszName )
  {
    CoTaskMemFree(v29.pwszName);
    v29.pwszName = 0;
  }
  if ( v29.pwszFriendlyName )
  {
    CoTaskMemFree(v29.pwszFriendlyName);
    v29.pwszFriendlyName = 0;
  }
  if ( v29.pwszAdaptorName )
  {
    CoTaskMemFree(v29.pwszAdaptorName);
    v29.pwszAdaptorName = 0;
  }
  if ( v29.pwszDevicePath )
  {
    CoTaskMemFree(v29.pwszDevicePath);
    v29.pwszDevicePath = 0;
  }
  if ( v16 )
  {
    ((void (__fastcall *)(struct IVdsDisk *))v16->lpVtbl->Release)(v16);
    v16 = 0;
  }
  ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v17);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
LABEL_72:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
  return v8;
}

```

## disassembly

```asm
0x14001c250  mov     [rsp-8+arg_18], rbx
0x14001c255  push    rbp
0x14001c256  push    rsi
0x14001c257  push    rdi
0x14001c258  push    r12
0x14001c25a  push    r13
0x14001c25c  push    r14
0x14001c25e  push    r15
0x14001c260  lea     rbp, [rsp-40h]
0x14001c265  sub     rsp, 140h
0x14001c26c  mov     rax, cs:__security_cookie
0x14001c273  xor     rax, rsp
0x14001c276  mov     [rbp+70h+var_40], rax
0x14001c27a  mov     r14, r8
0x14001c27d  mov     r15, rdx
0x14001c280  mov     r13, rcx
0x14001c283  xor     r12d, r12d
0x14001c286  mov     [rsp+170h+var_150], r12
0x14001c28b  mov     [rsp+170h+var_110], r12d
0x14001c290  xor     edx, edx; Val
0x14001c292  lea     r8d, [r12+44h]; Size
0x14001c297  lea     rcx, [rsp+170h+var_10C]; void *
0x14001c29c  call    memset_0
0x14001c2a1  mov     [rbp+70h+var_C0.id.Data1], r12d
0x14001c2a5  xor     edx, edx; Val
0x14001c2a7  lea     r8d, [r12+7Ch]; Size
0x14001c2ac  lea     rcx, [rbp+70h+var_C0.id.Data2]; void *
0x14001c2b0  call    memset_0
0x14001c2b5  mov     [rsp+170h+var_140], r12
0x14001c2ba  mov     [rsp+170h+var_138], r12
0x14001c2bf  mov     [rsp+170h+var_130], r12
0x14001c2c4  lea     r8, aCvdsdisklunShr_11; "CVdsDiskLun::Shrink()"
0x14001c2cb  lea     edi, [r12+5Eh]
0x14001c2d0  mov     edx, edi
0x14001c2d2  lea     rcx, [rsp+170h+var_128]
0x14001c2d7  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001c2dd  nop
0x14001c2de  mov     [rsp+170h+var_148], r12
0x14001c2e3  lea     ecx, [rdi+6]; enum _VDS_OBJECT_TYPE
0x14001c2e6  call    ?VdsCreateInstance@@YAPEAXW4_VDS_OBJECT_TYPE@@@Z; VdsCreateInstance(_VDS_OBJECT_TYPE)
0x14001c2eb  mov     rdx, rax
0x14001c2ee  lea     rcx, [rsp+170h+var_148]
0x14001c2f3  call    ?Attach@?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAAXPEAVCVdsEnumObject@@@Z; ATL::CComPtrBase<CVdsEnumObject>::Attach(CVdsEnumObject *)
0x14001c2f8  mov     rsi, [rsp+170h+var_148]
0x14001c2fd  test    rsi, rsi
0x14001c300  jnz     short loc_14001C32E
0x14001c302  lea     rcx, [rsp+170h+var_148]
0x14001c307  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001c30c  nop
0x14001c30d  lea     rcx, [rsp+170h+var_128]
0x14001c312  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001c318  nop
0x14001c319  lea     rcx, [rsp+170h+var_130]
0x14001c31e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001c323  nop
0x14001c324  mov     ebx, 8007000Eh
0x14001c329  jmp     loc_14001C6D7
0x14001c32e  mov     dword ptr [rsi+58h], 37h ; '7'
0x14001c335  test    r14, r14
0x14001c338  jnz     short loc_14001C34D
0x14001c33a  mov     ebx, 80070057h
0x14001c33f  lea     r8, aCvdsdisklunShr_15; "CVdsDiskLun::Shrink, 0, hr=%lX"
0x14001c346  mov     ecx, edi
0x14001c348  jmp     loc_14001C5F5
0x14001c34d  mov     [r14], r12
0x14001c350  mov     rcx, [r13+0C0h]
0x14001c357  test    rcx, rcx
0x14001c35a  jnz     short loc_14001C36D
0x14001c35c  mov     ebx, 80042448h
0x14001c361  lea     r8, aCvdsdisklunShr_4; "CVdsDiskLun::Shrink, 1, hr=%lX"
0x14001c368  jmp     loc_14001C5F0
0x14001c36d  mov     rax, [rcx]
0x14001c370  lea     rdx, [rsp+170h+var_110]
0x14001c375  mov     rax, [rax+18h]
0x14001c379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c37e  mov     ebx, eax
0x14001c380  test    eax, eax
0x14001c382  jns     short loc_14001C398
0x14001c384  lea     r8, aCvdsdisklunShr_6; "CVdsDiskLun::Shrink, 2, hr=%lX"
0x14001c38b  mov     r9d, eax
0x14001c38e  mov     ecx, 5Eh ; '^'
0x14001c393  jmp     loc_14001C5F8
0x14001c398  cmp     r15, [rsp+170h+var_100]
0x14001c39d  jb      short loc_14001C3B0
0x14001c39f  mov     ebx, 80042817h
0x14001c3a4  lea     r8, aCvdsdisklunShr_10; "CVdsDiskLun::Shrink, 3, hr=%lX"
0x14001c3ab  jmp     loc_14001C5F0
0x14001c3b0  mov     edx, [rbp+70h+var_D8]
0x14001c3b3  sub     edx, 2
0x14001c3b6  jz      loc_14001C5E4
0x14001c3bc  sub     edx, 2
0x14001c3bf  jz      loc_14001C5D6
0x14001c3c5  cmp     edx, 1
0x14001c3c8  jz      loc_14001C5C8
0x14001c3ce  mov     rax, [r13-58h]
0x14001c3d2  lea     r8, [rsp+170h+var_150]
0x14001c3d7  lea     rdx, IID_IVdsDisk
0x14001c3de  lea     rcx, [r13-58h]
0x14001c3e2  mov     rax, [rax]
0x14001c3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c3ea  mov     ebx, eax
0x14001c3ec  cmp     eax, 80004002h
0x14001c3f1  jnz     short loc_14001C404
0x14001c3f3  mov     ebx, 8004291Dh
0x14001c3f8  lea     r8, aCvdsdisklunShr_7; "CVdsDiskLun::Shrink, 7, hr=%lX"
0x14001c3ff  jmp     loc_14001C5F0
0x14001c404  test    eax, eax
0x14001c406  jns     short loc_14001C414
0x14001c408  lea     r8, aCvdsdisklunShr_8; "CVdsDiskLun::Shrink, 8, hr=%lX"
0x14001c40f  jmp     loc_14001C38B
0x14001c414  mov     rcx, [rsp+170h+var_150]
0x14001c419  mov     rax, [rcx]
0x14001c41c  lea     rdx, [rbp+70h+var_C0]
0x14001c420  mov     rax, [rax+18h]
0x14001c424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c429  mov     ebx, eax
0x14001c42b  test    eax, eax
0x14001c42d  jns     short loc_14001C43B
0x14001c42f  lea     r8, aCvdsdisklunShr_2; "CVdsDiskLun::Shrink, 9, hr=%lX"
0x14001c436  jmp     loc_14001C38B
0x14001c43b  lea     r9, aUnknown_0; "UNKNOWN"
0x14001c442  mov     rax, [rbp+70h+var_C0.pwszDevicePath]
0x14001c446  test    rax, rax
0x14001c449  cmovnz  r9, rax
0x14001c44d  lea     r8, aCvdsdisklunShr_9; "CVdsDiskLun::Shrink, 10, name=%S"
0x14001c454  mov     edx, 3
0x14001c459  lea     edi, [rdx+5Bh]
0x14001c45c  mov     ecx, edi
0x14001c45e  call    cs:__imp_VdsTraceEx
0x14001c464  test    byte ptr [rbp+70h+var_C0.ulFlags], 40h
0x14001c468  jz      short loc_14001C47B
0x14001c46a  mov     ebx, 8004291Eh
0x14001c46f  lea     r8, aCvdsdisklunShr_21; "CVdsDiskLun::Shrink, 11, hr=%lX"
0x14001c476  jmp     loc_14001C346
0x14001c47b  test    [rbp+70h+var_C0.ulFlags], 2000h
0x14001c482  jz      short loc_14001C495
0x14001c484  mov     ebx, 80042920h
0x14001c489  lea     r8, aCvdsdisklunShr_20; "CVdsDiskLun::Shrink, 12, hr=%lX"
0x14001c490  jmp     loc_14001C346
0x14001c495  mov     ecx, [rbp+70h+var_C0.status]
0x14001c498  sub     ecx, 2
0x14001c49b  jz      loc_14001C5B7
0x14001c4a1  sub     ecx, 1
0x14001c4a4  jz      loc_14001C5A6
0x14001c4aa  sub     ecx, 2; this
0x14001c4ad  jz      loc_14001C595
0x14001c4b3  cmp     ecx, 1
0x14001c4b6  jz      loc_14001C584
0x14001c4bc  lea     r9, [rsp+170h+var_140]; unsigned __int64 *
0x14001c4c1  lea     r8, [rbp+70h+var_C0]; struct _VDS_DISK_PROP *
0x14001c4c5  mov     rdx, [rsp+170h+var_150]; struct IVdsDisk *
0x14001c4ca  call    ?FindEndOfLastVolume@CVdsDiskLun@@AEAAJPEAUIVdsDisk@@PEAU_VDS_DISK_PROP@@PEA_K@Z; CVdsDiskLun::FindEndOfLastVolume(IVdsDisk *,_VDS_DISK_PROP *,unsigned __int64 *)
0x14001c4cf  mov     ebx, eax
0x14001c4d1  test    eax, eax
0x14001c4d3  jns     short loc_14001C4E6
0x14001c4d5  lea     r8, aCvdsdisklunShr_19; "CVdsDiskLun::Shrink, 18, hr=%lX"
0x14001c4dc  mov     r9d, eax
0x14001c4df  mov     ecx, edi
0x14001c4e1  jmp     loc_14001C5F8
0x14001c4e6  mov     rax, [rsp+170h+var_100]
0x14001c4eb  sub     rax, r15
0x14001c4ee  cmp     [rsp+170h+var_140], rax
0x14001c4f3  jb      short loc_14001C506
0x14001c4f5  mov     ebx, 80042816h
0x14001c4fa  lea     r8, aCvdsdisklunShr_1; "CVdsDiskLun::Shrink, 19, hr=%lX"
0x14001c501  jmp     loc_14001C346
0x14001c506  cmp     [rbp+70h+var_C0.PartitionStyle], 2
0x14001c50a  jnz     short loc_14001C52A
0x14001c50c  sub     rax, [rsp+170h+var_140]
0x14001c511  cmp     rax, 10000h
0x14001c517  jnb     short loc_14001C52A
0x14001c519  mov     ebx, 80042922h
0x14001c51e  lea     r8, aCvdsdisklunShr; "CVdsDiskLun::Shrink, 20, hr=%lX"
0x14001c525  jmp     loc_14001C346
0x14001c52a  mov     rcx, [r13+0C0h]
0x14001c531  mov     rax, [rcx]
0x14001c534  lea     r8, [rsp+170h+var_138]
0x14001c539  mov     rdx, r15
0x14001c53c  mov     rax, [rax+40h]
0x14001c540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c545  mov     ebx, eax
0x14001c547  test    eax, eax
0x14001c549  jns     short loc_14001C554
0x14001c54b  lea     r8, aCvdsdisklunShr_16; "CVdsDiskLun::Shrink, 21, hr=%lX"
0x14001c552  jmp     short loc_14001C4DC
0x14001c554  mov     r8, [r13+80h]; struct CVdsService *
0x14001c55b  mov     rdx, [rsp+170h+var_138]; struct IVdsAsync *
0x14001c560  mov     rcx, rsi; struct CVdsAsyncObject *
0x14001c563  call    ?ConnectAsyncWrapper@@YAJPEAVCVdsAsyncObject@@PEAUIVdsAsync@@PEAVCVdsService@@@Z; ConnectAsyncWrapper(CVdsAsyncObject *,IVdsAsync *,CVdsService *)
0x14001c568  mov     ebx, eax
0x14001c56a  test    eax, eax
0x14001c56c  jns     short loc_14001C57A
0x14001c56e  lea     r8, aCvdsdisklunShr_12; "CVdsDiskLun::Shrink, 22, %lX"
0x14001c575  jmp     loc_14001C4DC
0x14001c57a  mov     [rsp+170h+var_148], r12
0x14001c57f  mov     [r14], rsi
0x14001c582  jmp     short loc_14001C600
0x14001c584  mov     ebx, 80042818h
0x14001c589  lea     r8, aCvdsdisklunShr_5; "CVdsDiskLun::Shrink, 14, hr=%lX"
0x14001c590  jmp     loc_14001C346
0x14001c595  mov     ebx, 80042819h
0x14001c59a  lea     r8, aCvdsdisklunShr_18; "CVdsDiskLun::Shrink, 15, hr=%lX"
0x14001c5a1  jmp     loc_14001C346
0x14001c5a6  mov     ebx, 8004281Bh
0x14001c5ab  lea     r8, aCvdsdisklunShr_0; "CVdsDiskLun::Shrink, 17, hr=%lX"
0x14001c5b2  jmp     loc_14001C346
0x14001c5b7  mov     ebx, 8004281Ah
0x14001c5bc  lea     r8, aCvdsdisklunShr_13; "CVdsDiskLun::Shrink, 16, hr=%lX"
0x14001c5c3  jmp     loc_14001C346
0x14001c5c8  mov     ebx, 8004281Eh
0x14001c5cd  lea     r8, aCvdsdisklunShr_17; "CVdsDiskLun::Shrink, 6, hr=%lX"
0x14001c5d4  jmp     short loc_14001C5F0
0x14001c5d6  mov     ebx, 8004281Dh
0x14001c5db  lea     r8, aCvdsdisklunShr_3; "CVdsDiskLun::Shrink, 4, hr=%lX"
0x14001c5e2  jmp     short loc_14001C5F0
0x14001c5e4  mov     ebx, 8004281Ch
0x14001c5e9  lea     r8, aCvdsdisklunShr_14; "CVdsDiskLun::Shrink, 5, hr=%lX"
0x14001c5f0  mov     ecx, 5Eh ; '^'
0x14001c5f5  mov     r9d, ebx
0x14001c5f8  xor     edx, edx
0x14001c5fa  call    cs:__imp_VdsTraceEx
0x14001c600  mov     rcx, [rsp+170h+pv]; pv
0x14001c605  test    rcx, rcx
0x14001c608  jz      short loc_14001C615
0x14001c60a  call    cs:__imp_CoTaskMemFree
0x14001c610  mov     [rsp+170h+pv], r12
0x14001c615  mov     rcx, [rbp+70h+var_F0]; pv
0x14001c619  test    rcx, rcx
0x14001c61c  jz      short loc_14001C628
0x14001c61e  call    cs:__imp_CoTaskMemFree
0x14001c624  mov     [rbp+70h+var_F0], r12
0x14001c628  mov     rcx, [rbp+70h+var_E8]; pv
0x14001c62c  test    rcx, rcx
0x14001c62f  jz      short loc_14001C63B
0x14001c631  call    cs:__imp_CoTaskMemFree
0x14001c637  mov     [rbp+70h+var_E8], r12
0x14001c63b  mov     rcx, [rbp+70h+var_C0.pwszDiskAddress]; pv
0x14001c63f  test    rcx, rcx
0x14001c642  jz      short loc_14001C64E
0x14001c644  call    cs:__imp_CoTaskMemFree
0x14001c64a  mov     [rbp+70h+var_C0.pwszDiskAddress], r12
0x14001c64e  mov     rcx, [rbp+70h+var_C0.pwszName]; pv
0x14001c652  test    rcx, rcx
0x14001c655  jz      short loc_14001C661
0x14001c657  call    cs:__imp_CoTaskMemFree
0x14001c65d  mov     [rbp+70h+var_C0.pwszName], r12
0x14001c661  mov     rcx, [rbp+70h+var_C0.pwszFriendlyName]; pv
0x14001c665  test    rcx, rcx
0x14001c668  jz      short loc_14001C674
0x14001c66a  call    cs:__imp_CoTaskMemFree
0x14001c670  mov     [rbp+70h+var_C0.pwszFriendlyName], r12
0x14001c674  mov     rcx, [rbp+70h+var_C0.pwszAdaptorName]; pv
0x14001c678  test    rcx, rcx
0x14001c67b  jz      short loc_14001C687
0x14001c67d  call    cs:__imp_CoTaskMemFree
0x14001c683  mov     [rbp+70h+var_C0.pwszAdaptorName], r12
0x14001c687  mov     rcx, [rbp+70h+var_C0.pwszDevicePath]; pv
0x14001c68b  test    rcx, rcx
0x14001c68e  jz      short loc_14001C69A
0x14001c690  call    cs:__imp_CoTaskMemFree
0x14001c696  mov     [rbp+70h+var_C0.pwszDevicePath], r12
0x14001c69a  mov     rcx, [rsp+170h+var_150]
0x14001c69f  test    rcx, rcx
0x14001c6a2  jz      short loc_14001C6B5
0x14001c6a4  mov     rax, [rcx]
0x14001c6a7  mov     rax, [rax+10h]
0x14001c6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c6b0  mov     [rsp+170h+var_150], r12
0x14001c6b5  lea     rcx, [rsp+170h+var_148]
0x14001c6ba  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001c6bf  nop
0x14001c6c0  lea     rcx, [rsp+170h+var_128]
0x14001c6c5  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001c6cb  nop
0x14001c6cc  lea     rcx, [rsp+170h+var_130]
0x14001c6d1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001c6d6  nop
0x14001c6d7  lea     rcx, [rsp+170h+var_138]
0x14001c6dc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001c6e1  mov     eax, ebx
0x14001c6e3  mov     rcx, [rbp+70h+var_40]
0x14001c6e7  xor     rcx, rsp; StackCookie
0x14001c6ea  call    __security_check_cookie
0x14001c6ef  mov     rbx, [rsp+170h+arg_18]
0x14001c6f7  add     rsp, 140h
0x14001c6fe  pop     r15
0x14001c700  pop     r14
0x14001c702  pop     r13
0x14001c704  pop     r12
0x14001c706  pop     rdi
0x14001c707  pop     rsi
0x14001c708  pop     rbp
0x14001c709  retn
```
