# CVdsIscsiTarget::Delete(IVdsAsync * *)

- ea: `0x14001e840`
- end: `0x14001ea72`
- name: `?Delete@CVdsIscsiTarget@@UEAAJPEAPEAUIVdsAsync@@@Z`
- size: `562`
- prototype: `__int64 __fastcall(CVdsIscsiTarget *__hidden this, struct IVdsAsync **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400025b0`
- `0x14000f98c`
- `0x140010b04`
- `0x140012c48`
- `0x14001e840`
- `0x140031c50`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001e91e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001e935`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001e91e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001e935`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001e8c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001e8c9`
- `vdsutil!VdsTraceEx` at `0x14001e901`
- `vdsutil!VdsTraceEx` at `0x14001e9b9`
- `vdsutil!VdsTraceEx` at `0x14001ea03`
- `vdsutil!VdsTraceEx` at `0x14001e901`
- `vdsutil!VdsTraceEx` at `0x14001e9b9`
- `vdsutil!VdsTraceEx` at `0x14001ea03`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001e893`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001e893`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001e978`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001e9ce`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001ea18`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001ea3a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001e978`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001e9ce`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001ea18`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001ea3a`

## string_xrefs

- `0x14001e885`: `CVdsIscsiTarget::Delete()`
- `0x14001e8c2`: `RemoveIScsiStaticTargetW`
- `0x14001e8f5`: `CVdsIscsiTarget::Delete, 1, error=%lX`
- `0x14001e9ad`: `CVdsIscsiTarget::Delete, 2, error=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CVdsIscsiTarget::Delete(CVdsIscsiTarget *this, struct IVdsAsync **a2)
{
  FARPROC ProcAddress; // rbx
  int v5; // eax
  void *Instance; // rax
  struct CVdsAsyncObject *v7; // rdi
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // eax
  struct CVdsAsyncObject *v12; // [rsp+30h] [rbp-50h] BYREF
  struct IVdsAsync *v13; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v14[16]; // [rsp+40h] [rbp-40h] BYREF
  __int128 v15; // [rsp+50h] [rbp-30h] BYREF
  LPVOID pv[2]; // [rsp+60h] [rbp-20h]
  __int64 v17; // [rsp+70h] [rbp-10h]

  v13 = 0;
  v15 = 0;
  *(_OWORD *)pv = 0;
  v17 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v14, 0x5Eu, "CVdsIscsiTarget::Delete()");
  *a2 = 0;
  v15 = 0;
  *(_OWORD *)pv = 0;
  v17 = 0;
  if ( CVdsService::m_hIscsidscModule )
  {
    ProcAddress = GetProcAddress(CVdsService::m_hIscsidscModule, "RemoveIScsiStaticTargetW");
    if ( ProcAddress )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 10) + 24LL))(
             *((_QWORD *)this + 10),
             &v15);
      if ( v5 >= 0 )
      {
        ((void (__fastcall *)(LPVOID))ProcAddress)(pv[0]);
        if ( pv[0] )
        {
          CoTaskMemFree(pv[0]);
          pv[0] = 0;
        }
        if ( pv[1] )
        {
          CoTaskMemFree(pv[1]);
          pv[1] = 0;
        }
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsIscsiTarget::Delete, 1, error=%lX", v5);
      }
    }
  }
  v12 = 0;
  Instance = VdsCreateInstance(VDS_OT_ASYNC);
  ATL::CComPtrBase<CVdsEnumObject>::Attach((__int64 *)&v12, (__int64)Instance);
  v7 = v12;
  if ( v12 )
  {
    *((_DWORD *)v12 + 22) = 64;
    v9 = (*(__int64 (__fastcall **)(_QWORD, struct IVdsAsync **))(**((_QWORD **)this + 10) + 64LL))(
           *((_QWORD *)this + 10),
           &v13);
    v8 = v9;
    if ( v9 >= 0 )
    {
      v10 = ConnectAsyncWrapper(v7, v13, *((struct CVdsService **)this + 9));
      v8 = v10;
      if ( v10 >= 0 )
      {
        v12 = 0;
        *a2 = (struct IVdsAsync *)v7;
        ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v12);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
        v8 = 0;
      }
      else
      {
        VdsTraceEx(94, 0, "VDS(%X): unexpected failure connecting async wrapper: %X", 34865156, v10);
        ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v12);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsIscsiTarget::Delete, 2, error=%lX", v9);
      ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v12);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
    }
  }
  else
  {
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v12);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
    v8 = -2147024882;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
  return v8;
}

```

## disassembly

```asm
0x14001e840  mov     [rsp-18h+arg_10], rbx
0x14001e845  mov     [rsp-18h+arg_18], rsi
0x14001e84a  push    rbp
0x14001e84b  push    rdi
0x14001e84c  push    r14
0x14001e84e  mov     rbp, rsp
0x14001e851  sub     rsp, 80h
0x14001e858  mov     rax, cs:__security_cookie
0x14001e85f  xor     rax, rsp
0x14001e862  mov     [rbp+var_8], rax
0x14001e866  mov     r14, rdx
0x14001e869  mov     rsi, rcx
0x14001e86c  mov     [rbp+var_48], 0
0x14001e874  xorps   xmm0, xmm0
0x14001e877  xor     eax, eax
0x14001e879  movups  [rbp+var_30], xmm0
0x14001e87d  movups  xmmword ptr [rbp+pv], xmm0
0x14001e881  mov     [rbp+var_10], rax
0x14001e885  lea     r8, aCvdsiscsitarge_14; "CVdsIscsiTarget::Delete()"
0x14001e88c  lea     edx, [rax+5Eh]
0x14001e88f  lea     rcx, [rbp+var_40]
0x14001e893  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001e899  nop
0x14001e89a  mov     qword ptr [r14], 0
0x14001e8a1  xorps   xmm0, xmm0
0x14001e8a4  xor     eax, eax
0x14001e8a6  movups  [rbp+var_30], xmm0
0x14001e8aa  movups  xmmword ptr [rbp+pv], xmm0
0x14001e8ae  mov     [rbp+var_10], rax
0x14001e8b2  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x14001e8b9  test    rcx, rcx
0x14001e8bc  jz      loc_14001E943
0x14001e8c2  lea     rdx, aRemoveiscsista; "RemoveIScsiStaticTargetW"
0x14001e8c9  call    cs:__imp_GetProcAddress
0x14001e8cf  mov     rbx, rax
0x14001e8d2  test    rax, rax
0x14001e8d5  jz      short loc_14001E943
0x14001e8d7  mov     r8, [rsi+50h]
0x14001e8db  mov     rcx, [r8]
0x14001e8de  mov     rax, [rcx+18h]
0x14001e8e2  lea     rdx, [rbp+var_30]
0x14001e8e6  mov     rcx, r8
0x14001e8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e8ee  test    eax, eax
0x14001e8f0  jns     short loc_14001E909
0x14001e8f2  mov     r9d, eax
0x14001e8f5  lea     r8, aCvdsiscsitarge_17; "CVdsIscsiTarget::Delete, 1, error=%lX"
0x14001e8fc  xor     edx, edx
0x14001e8fe  lea     ecx, [rdx+5Eh]
0x14001e901  call    cs:__imp_VdsTraceEx
0x14001e907  jmp     short loc_14001E943
0x14001e909  mov     rcx, [rbp+pv]
0x14001e90d  mov     rax, rbx
0x14001e910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e915  mov     rcx, [rbp+pv]; pv
0x14001e919  test    rcx, rcx
0x14001e91c  jz      short loc_14001E92C
0x14001e91e  call    cs:__imp_CoTaskMemFree
0x14001e924  mov     [rbp+pv], 0
0x14001e92c  mov     rcx, [rbp+pv+8]; pv
0x14001e930  test    rcx, rcx
0x14001e933  jz      short loc_14001E943
0x14001e935  call    cs:__imp_CoTaskMemFree
0x14001e93b  mov     [rbp+pv+8], 0
0x14001e943  mov     [rbp+var_50], 0
0x14001e94b  mov     ecx, 64h ; 'd'; enum _VDS_OBJECT_TYPE
0x14001e950  call    ?VdsCreateInstance@@YAPEAXW4_VDS_OBJECT_TYPE@@@Z; VdsCreateInstance(_VDS_OBJECT_TYPE)
0x14001e955  mov     rdx, rax
0x14001e958  lea     rcx, [rbp+var_50]
0x14001e95c  call    ?Attach@?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAAXPEAVCVdsEnumObject@@@Z; ATL::CComPtrBase<CVdsEnumObject>::Attach(CVdsEnumObject *)
0x14001e961  mov     rdi, [rbp+var_50]
0x14001e965  test    rdi, rdi
0x14001e968  jnz     short loc_14001E989
0x14001e96a  lea     rcx, [rbp+var_50]
0x14001e96e  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001e973  nop
0x14001e974  lea     rcx, [rbp+var_40]
0x14001e978  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001e97e  nop
0x14001e97f  mov     ebx, 8007000Eh
0x14001e984  jmp     loc_14001EA43
0x14001e989  mov     dword ptr [rdi+58h], 40h ; '@'
0x14001e990  mov     rcx, [rsi+50h]
0x14001e994  mov     rax, [rcx]
0x14001e997  lea     rdx, [rbp+var_48]
0x14001e99b  mov     rax, [rax+40h]
0x14001e99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e9a4  mov     ebx, eax
0x14001e9a6  test    eax, eax
0x14001e9a8  jns     short loc_14001E9D7
0x14001e9aa  mov     r9d, eax
0x14001e9ad  lea     r8, aCvdsiscsitarge_20; "CVdsIscsiTarget::Delete, 2, error=%lX"
0x14001e9b4  xor     edx, edx
0x14001e9b6  lea     ecx, [rdx+5Eh]
0x14001e9b9  call    cs:__imp_VdsTraceEx
0x14001e9bf  nop
0x14001e9c0  lea     rcx, [rbp+var_50]
0x14001e9c4  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001e9c9  nop
0x14001e9ca  lea     rcx, [rbp+var_40]
0x14001e9ce  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001e9d4  nop
0x14001e9d5  jmp     short loc_14001EA43
0x14001e9d7  mov     r8, [rsi+48h]; struct CVdsService *
0x14001e9db  mov     rdx, [rbp+var_48]; struct IVdsAsync *
0x14001e9df  mov     rcx, rdi; struct CVdsAsyncObject *
0x14001e9e2  call    ?ConnectAsyncWrapper@@YAJPEAVCVdsAsyncObject@@PEAUIVdsAsync@@PEAVCVdsService@@@Z; ConnectAsyncWrapper(CVdsAsyncObject *,IVdsAsync *,CVdsService *)
0x14001e9e7  mov     ebx, eax
0x14001e9e9  test    eax, eax
0x14001e9eb  jns     short loc_14001EA21
0x14001e9ed  mov     [rsp+80h+var_60], eax
0x14001e9f1  mov     r9d, 2140004h
0x14001e9f7  lea     r8, aVdsXUnexpected; "VDS(%X): unexpected failure connecting "...
0x14001e9fe  xor     edx, edx
0x14001ea00  lea     ecx, [rdx+5Eh]
0x14001ea03  call    cs:__imp_VdsTraceEx
0x14001ea09  nop
0x14001ea0a  lea     rcx, [rbp+var_50]
0x14001ea0e  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001ea13  nop
0x14001ea14  lea     rcx, [rbp+var_40]
0x14001ea18  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001ea1e  nop
0x14001ea1f  jmp     short loc_14001EA43
0x14001ea21  mov     [rbp+var_50], 0
0x14001ea29  mov     [r14], rdi
0x14001ea2c  lea     rcx, [rbp+var_50]
0x14001ea30  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001ea35  nop
0x14001ea36  lea     rcx, [rbp+var_40]
0x14001ea3a  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001ea40  nop
0x14001ea41  xor     ebx, ebx
0x14001ea43  lea     rcx, [rbp+var_48]
0x14001ea47  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001ea4c  mov     eax, ebx
0x14001ea4e  mov     rcx, [rbp+var_8]
0x14001ea52  xor     rcx, rsp; StackCookie
0x14001ea55  call    __security_check_cookie
0x14001ea5a  lea     r11, [rsp+80h+var_s0]
0x14001ea62  mov     rbx, [r11+30h]
0x14001ea66  mov     rsi, [r11+38h]
0x14001ea6a  mov     rsp, r11
0x14001ea6d  pop     r14
0x14001ea6f  pop     rdi
0x14001ea70  pop     rbp
0x14001ea71  retn
```
