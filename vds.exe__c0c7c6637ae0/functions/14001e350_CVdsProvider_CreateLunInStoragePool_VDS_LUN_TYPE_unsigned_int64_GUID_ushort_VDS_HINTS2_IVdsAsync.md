# CVdsProvider::CreateLunInStoragePool(_VDS_LUN_TYPE,unsigned __int64,_GUID,ushort *,_VDS_HINTS2 *,IVdsAsync * *)

- ea: `0x14001e350`
- end: `0x14001e567`
- name: `?CreateLunInStoragePool@CVdsProvider@@UEAAJW4_VDS_LUN_TYPE@@_KU_GUID@@PEAGPEAU_VDS_HINTS2@@PEAPEAUIVdsAsync@@@Z`
- size: `535`
- prototype: `int(CVdsProvider *__hidden this, enum _VDS_LUN_TYPE, unsigned __int64, struct _GUID *__struct_ptr, unsigned __int16 *, struct _VDS_HINTS2 *, struct IVdsAsync **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400025b0`
- `0x14000f98c`
- `0x140010b04`
- `0x140012c48`
- `0x14001e350`
- `0x140031c50`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `vdsutil!VdsTraceEx` at `0x14001e3ae`
- `vdsutil!VdsTraceEx` at `0x14001e407`
- `vdsutil!VdsTraceEx` at `0x14001e4d2`
- `vdsutil!VdsTraceEx` at `0x14001e51f`
- `vdsutil!VdsTraceEx` at `0x14001e3ae`
- `vdsutil!VdsTraceEx` at `0x14001e407`
- `vdsutil!VdsTraceEx` at `0x14001e4d2`
- `vdsutil!VdsTraceEx` at `0x14001e51f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001e38a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001e38a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001e3b9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001e464`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001e4e7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001e534`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001e559`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001e3b9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001e464`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001e4e7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001e534`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001e559`

## string_xrefs

- `0x14001e3fc`: `CVdsProvider::CreateLunInStoragePool, 2, NULL StoragePoolId`
- `0x14001e378`: `CVdsProvider::CreateLunInStoragePool()`
- `0x14001e3a0`: `CVdsProvider::CreateLunInStoragePool, 1, hr=%lX`
- `0x14001e416`: `CVdsProvider::CreateLunInStoragePool, 3, hr=%lX`
- `0x14001e4c6`: `CVdsProvider::CreateLunInStoragePool, 4, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CVdsProvider::CreateLunInStoragePool(
        CVdsProvider *this,
        unsigned int a2,
        __int64 a3,
        struct _GUID *a4,
        unsigned __int16 *a5,
        struct _VDS_HINTS2 *a6,
        struct IVdsAsync **a7)
{
  unsigned int v11; // ebx
  int v13; // edi
  struct IVdsAsync **v14; // rsi
  void *Instance; // rax
  struct CVdsAsyncObject *v16; // rdi
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  struct IVdsAsync *v20; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v21[24]; // [rsp+48h] [rbp-30h] BYREF
  __int128 v22; // [rsp+60h] [rbp-18h] BYREF
  struct CVdsAsyncObject *v23; // [rsp+C0h] [rbp+48h] BYREF

  v20 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v21, 0x5Eu, "CVdsProvider::CreateLunInStoragePool()");
  if ( !*((_QWORD *)this + 17) )
  {
    v11 = -2147418113;
    VdsTraceEx(94, 0, "CVdsProvider::CreateLunInStoragePool, 1, hr=%lX", 2147549183LL);
LABEL_3:
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v21);
    goto LABEL_4;
  }
  v13 = 0;
  v11 = -2147024809;
  if ( !memcmp_0(&GUID_NULL, a4, 0x10u) )
  {
    v13 = -2147024809;
    VdsTraceEx(94, 0, "CVdsProvider::CreateLunInStoragePool, 2, NULL StoragePoolId");
  }
  v14 = a7;
  if ( !a7 )
  {
    VdsTraceEx(94, 0, "CVdsProvider::CreateLunInStoragePool, 3, hr=%lX", 2147942487LL);
    goto LABEL_3;
  }
  v11 = v13;
  if ( v13 < 0 )
    goto LABEL_3;
  *a7 = 0;
  v23 = 0;
  Instance = VdsCreateInstance(VDS_OT_ASYNC);
  ATL::CComPtrBase<CVdsEnumObject>::Attach((__int64 *)&v23, (__int64)Instance);
  v16 = v23;
  if ( v23 )
  {
    *((_DWORD *)v23 + 22) = 50;
    v17 = *((_QWORD *)this + 17);
    v22 = (__int128)*a4;
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int128 *, unsigned __int16 *, struct _VDS_HINTS2 *, struct IVdsAsync **))(*(_QWORD *)v17 + 32LL))(
            v17,
            a2,
            a3,
            &v22,
            a5,
            a6,
            &v20);
    v11 = v18;
    if ( v18 >= 0 )
    {
      v19 = ConnectAsyncWrapper(v16, v20, *((struct CVdsService **)this + 9));
      v11 = v19;
      if ( v19 >= 0 )
      {
        v23 = 0;
        *v14 = (struct IVdsAsync *)v16;
        ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v23);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v21);
        v11 = 0;
      }
      else
      {
        VdsTraceEx(94, 0, "VDS(%X): unexpected failure connecting async wrapper: %X", 34078725, v19);
        ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v23);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v21);
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsProvider::CreateLunInStoragePool, 4, hr=%lX", v18);
      ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v23);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v21);
    }
  }
  else
  {
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v23);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v21);
    v11 = -2147024882;
  }
LABEL_4:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
  return v11;
}

```

## disassembly

```asm
0x14001e350  push    rbp
0x14001e352  push    rbx
0x14001e353  push    rsi
0x14001e354  push    rdi
0x14001e355  push    r12
0x14001e357  push    r13
0x14001e359  push    r14
0x14001e35b  push    r15
0x14001e35d  mov     rbp, rsp
0x14001e360  sub     rsp, 78h
0x14001e364  mov     r15, r9
0x14001e367  mov     r12, r8
0x14001e36a  mov     r13d, edx
0x14001e36d  mov     r14, rcx
0x14001e370  mov     [rbp+var_38], 0
0x14001e378  lea     r8, aCvdsproviderCr_2; "CVdsProvider::CreateLunInStoragePool()"
0x14001e37f  mov     esi, 5Eh ; '^'
0x14001e384  mov     edx, esi
0x14001e386  lea     rcx, [rbp+var_30]
0x14001e38a  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001e390  nop
0x14001e391  cmp     qword ptr [r14+88h], 0
0x14001e399  jnz     short loc_14001E3DC
0x14001e39b  mov     ebx, 8000FFFFh
0x14001e3a0  lea     r8, aCvdsproviderCr_6; "CVdsProvider::CreateLunInStoragePool, 1"...
0x14001e3a7  mov     ecx, esi
0x14001e3a9  xor     edx, edx
0x14001e3ab  mov     r9d, ebx
0x14001e3ae  call    cs:__imp_VdsTraceEx
0x14001e3b4  nop
0x14001e3b5  lea     rcx, [rbp+var_30]
0x14001e3b9  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001e3bf  nop
0x14001e3c0  lea     rcx, [rbp+var_38]
0x14001e3c4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001e3c9  mov     eax, ebx
0x14001e3cb  add     rsp, 78h
0x14001e3cf  pop     r15
0x14001e3d1  pop     r14
0x14001e3d3  pop     r13
0x14001e3d5  pop     r12
0x14001e3d7  pop     rdi
0x14001e3d8  pop     rsi
0x14001e3d9  pop     rbx
0x14001e3da  pop     rbp
0x14001e3db  retn
0x14001e3dc  xor     edi, edi
0x14001e3de  lea     r8d, [rdi+10h]; Size
0x14001e3e2  mov     rdx, r15; Buf2
0x14001e3e5  lea     rcx, GUID_NULL; Buf1
0x14001e3ec  call    memcmp_0
0x14001e3f1  mov     ebx, 80070057h
0x14001e3f6  test    eax, eax
0x14001e3f8  jnz     short loc_14001E40D
0x14001e3fa  mov     edi, ebx
0x14001e3fc  lea     r8, aCvdsproviderCr_4; "CVdsProvider::CreateLunInStoragePool, 2"...
0x14001e403  xor     edx, edx
0x14001e405  mov     ecx, esi
0x14001e407  call    cs:__imp_VdsTraceEx
0x14001e40d  mov     rsi, [rbp+arg_30]
0x14001e411  test    rsi, rsi
0x14001e414  jnz     short loc_14001E422
0x14001e416  lea     r8, aCvdsproviderCr_0; "CVdsProvider::CreateLunInStoragePool, 3"...
0x14001e41d  lea     ecx, [rsi+5Eh]
0x14001e420  jmp     short loc_14001E3A9
0x14001e422  mov     ebx, edi
0x14001e424  test    edi, edi
0x14001e426  js      short loc_14001E3B5
0x14001e428  mov     qword ptr [rsi], 0
0x14001e42f  mov     [rbp+arg_0], 0
0x14001e437  mov     ecx, 64h ; 'd'; enum _VDS_OBJECT_TYPE
0x14001e43c  call    ?VdsCreateInstance@@YAPEAXW4_VDS_OBJECT_TYPE@@@Z; VdsCreateInstance(_VDS_OBJECT_TYPE)
0x14001e441  mov     rdx, rax
0x14001e444  lea     rcx, [rbp+arg_0]
0x14001e448  call    ?Attach@?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAAXPEAVCVdsEnumObject@@@Z; ATL::CComPtrBase<CVdsEnumObject>::Attach(CVdsEnumObject *)
0x14001e44d  mov     rdi, [rbp+arg_0]
0x14001e451  test    rdi, rdi
0x14001e454  jnz     short loc_14001E475
0x14001e456  lea     rcx, [rbp+arg_0]
0x14001e45a  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001e45f  nop
0x14001e460  lea     rcx, [rbp+var_30]
0x14001e464  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001e46a  nop
0x14001e46b  mov     ebx, 8007000Eh
0x14001e470  jmp     loc_14001E3C0
0x14001e475  mov     dword ptr [rdi+58h], 32h ; '2'
0x14001e47c  mov     rcx, [r14+88h]
0x14001e483  movups  xmm0, xmmword ptr [r15]
0x14001e487  movdqu  [rbp+var_18], xmm0
0x14001e48c  mov     rax, [rcx]
0x14001e48f  lea     rdx, [rbp+var_38]
0x14001e493  mov     [rsp+78h+var_48], rdx
0x14001e498  mov     rdx, [rbp+arg_28]
0x14001e49c  mov     [rsp+78h+var_50], rdx
0x14001e4a1  mov     rdx, [rbp+arg_20]
0x14001e4a5  mov     [rsp+78h+var_58], rdx
0x14001e4aa  lea     r9, [rbp+var_18]
0x14001e4ae  mov     r8, r12
0x14001e4b1  mov     edx, r13d
0x14001e4b4  mov     rax, [rax+20h]
0x14001e4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e4bd  mov     ebx, eax
0x14001e4bf  test    eax, eax
0x14001e4c1  jns     short loc_14001E4F3
0x14001e4c3  mov     r9d, eax
0x14001e4c6  lea     r8, aCvdsproviderCr_3; "CVdsProvider::CreateLunInStoragePool, 4"...
0x14001e4cd  xor     edx, edx
0x14001e4cf  lea     ecx, [rdx+5Eh]
0x14001e4d2  call    cs:__imp_VdsTraceEx
0x14001e4d8  nop
0x14001e4d9  lea     rcx, [rbp+arg_0]
0x14001e4dd  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001e4e2  nop
0x14001e4e3  lea     rcx, [rbp+var_30]
0x14001e4e7  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001e4ed  nop
0x14001e4ee  jmp     loc_14001E3C0
0x14001e4f3  mov     r8, [r14+48h]; struct CVdsService *
0x14001e4f7  mov     rdx, [rbp+var_38]; struct IVdsAsync *
0x14001e4fb  mov     rcx, rdi; struct CVdsAsyncObject *
0x14001e4fe  call    ?ConnectAsyncWrapper@@YAJPEAVCVdsAsyncObject@@PEAUIVdsAsync@@PEAVCVdsService@@@Z; ConnectAsyncWrapper(CVdsAsyncObject *,IVdsAsync *,CVdsService *)
0x14001e503  mov     ebx, eax
0x14001e505  test    eax, eax
0x14001e507  jns     short loc_14001E540
0x14001e509  mov     dword ptr [rsp+78h+var_58], eax
0x14001e50d  mov     r9d, 2080005h
0x14001e513  lea     r8, aVdsXUnexpected; "VDS(%X): unexpected failure connecting "...
0x14001e51a  xor     edx, edx
0x14001e51c  lea     ecx, [rdx+5Eh]
0x14001e51f  call    cs:__imp_VdsTraceEx
0x14001e525  nop
0x14001e526  lea     rcx, [rbp+arg_0]
0x14001e52a  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001e52f  nop
0x14001e530  lea     rcx, [rbp+var_30]
0x14001e534  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001e53a  nop
0x14001e53b  jmp     loc_14001E3C0
0x14001e540  mov     [rbp+arg_0], 0
0x14001e548  mov     [rsi], rdi
0x14001e54b  lea     rcx, [rbp+arg_0]
0x14001e54f  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001e554  nop
0x14001e555  lea     rcx, [rbp+var_30]
0x14001e559  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001e55f  nop
0x14001e560  xor     ebx, ebx
0x14001e562  jmp     loc_14001E3C0
```
