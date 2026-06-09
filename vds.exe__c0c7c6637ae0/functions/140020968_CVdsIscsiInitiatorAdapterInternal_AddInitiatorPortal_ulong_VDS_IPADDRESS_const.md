# CVdsIscsiInitiatorAdapterInternal::AddInitiatorPortal(ulong,_VDS_IPADDRESS const *)

- ea: `0x140020968`
- end: `0x140020ae4`
- name: `?AddInitiatorPortal@CVdsIscsiInitiatorAdapterInternal@@QEAAJKPEBU_VDS_IPADDRESS@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(CVdsIscsiInitiatorAdapterInternal *__hidden this, unsigned int, const struct _VDS_IPADDRESS *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000ae70`

## callees

- `0x14000f98c`
- `0x140012c48`
- `0x140020968`
- `0x140020aec`
- `0x14003fd3c`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140020a9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140020a9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140020a79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140020a79`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1400209c4`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1400209c4`
- `vdsutil!VdsTraceEx` at `0x140020a6a`
- `vdsutil!VdsTraceEx` at `0x140020a6a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400209b9`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400209b9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140020aa8`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140020aa8`
- `vdsutil!?InsertTailPointer@CRtlList@@QEAAHPEAX@Z` at `0x140020a88`
- `vdsutil!?InsertTailPointer@CRtlList@@QEAAHPEAX@Z` at `0x140020a88`
- `vdsutil!VdsTraceW` at `0x1400209f7`
- `vdsutil!VdsTraceW` at `0x1400209f7`

## string_xrefs

- `0x1400209ee`: `CVdsIscsiInitiatorAdapterInternal::AddInitiatorPortal: CVdsIscsiInitiatorPortalInternal CreateInstance: Out of memory.`

## pseudocode

```c
__int64 __fastcall CVdsIscsiInitiatorAdapterInternal::AddInitiatorPortal(
        CVdsIscsiInitiatorAdapterInternal *this,
        unsigned int a2,
        const struct _VDS_IPADDRESS *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // edi
  CVdsIscsiInitiatorPortalInternal *v8; // rbx
  int v9; // eax
  int v10; // eax
  void *v12; // [rsp+30h] [rbp-40h] BYREF
  CVdsIscsiInitiatorPortalInternal *v13; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v14[16]; // [rsp+40h] [rbp-30h] BYREF
  GUID pguid; // [rsp+50h] [rbp-20h] BYREF

  pguid = 0;
  v13 = 0;
  v12 = 0;
  CVdsCallTracer::CVdsCallTracer(
    (CVdsCallTracer *)v14,
    0x5Eu,
    "CVdsIscsiInitiatorAdapterInternal::AddInitiatorPortal()");
  v6 = CoCreateGuid(&pguid);
  v7 = v6;
  if ( v6 >= 0 )
  {
    ATL::CComObject<CVdsIscsiInitiatorPortalInternal>::CreateInstance(&v13);
    v8 = v13;
    if ( v13 )
    {
      (*(void (__fastcall **)(CVdsIscsiInitiatorPortalInternal *))(*(_QWORD *)v13 + 8LL))(v13);
      v9 = CVdsIscsiInitiatorPortalInternal::Initialize(v8, &pguid, this, a2, a3);
      v7 = v9;
      if ( v9 >= 0 )
      {
        v10 = (**(__int64 (__fastcall ***)(CVdsIscsiInitiatorPortalInternal *, GUID *, void **))v8)(
                v8,
                &IID_IUnknown,
                &v12);
        v7 = v10;
        if ( v10 >= 0 )
        {
          EnterCriticalSection(&g_GlobalCriticalSection);
          CRtlList::InsertTailPointer((CVdsIscsiInitiatorAdapterInternal *)((char *)this + 88), v12);
          v12 = 0;
          LeaveCriticalSection(&g_GlobalCriticalSection);
        }
        else
        {
          VdsTraceEx(94, 0, "CVdsIscsiInitiatorAdapterInternal::AddInitiatorPortal, 3, hr=%lX", (unsigned int)v10);
        }
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsIscsiInitiatorAdapterInternal::AddInitiatorPortal, 2, hr=%lX", (unsigned int)v9);
      }
    }
    else
    {
      VdsTraceW(
        0,
        L"CVdsIscsiInitiatorAdapterInternal::AddInitiatorPortal: CVdsIscsiInitiatorPortalInternal CreateInstance: Out of memory.");
      v7 = -2147024882;
    }
  }
  else
  {
    VdsTraceEx(94, 0, "CVdsIscsiInitiatorAdapterInternal::AddInitiatorPortal, 1, hr=%lX", (unsigned int)v6);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v12);
  ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v13);
  return v7;
}

```

## disassembly

```asm
0x140020968  mov     [rsp-28h+arg_18], rbx
0x14002096d  push    rbp
0x14002096e  push    rsi
0x14002096f  push    rdi
0x140020970  push    r14
0x140020972  push    r15
0x140020974  mov     rbp, rsp
0x140020977  sub     rsp, 70h
0x14002097b  mov     rax, cs:__security_cookie
0x140020982  xor     rax, rsp
0x140020985  mov     [rbp+var_8], rax
0x140020989  mov     r15, r8
0x14002098c  mov     r14d, edx
0x14002098f  mov     rsi, rcx
0x140020992  xorps   xmm0, xmm0
0x140020995  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x140020999  mov     [rbp+var_38], 0
0x1400209a1  mov     [rbp+var_40], 0
0x1400209a9  lea     r8, aCvdsiscsiiniti_128; "CVdsIscsiInitiatorAdapterInternal::AddI"...
0x1400209b0  mov     edx, 5Eh ; '^'
0x1400209b5  lea     rcx, [rbp+var_30]
0x1400209b9  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400209bf  nop
0x1400209c0  lea     rcx, [rbp+pguid]; pguid
0x1400209c4  call    cs:__imp_CoCreateGuid
0x1400209ca  mov     edi, eax
0x1400209cc  test    eax, eax
0x1400209ce  jns     short loc_1400209DC
0x1400209d0  lea     r8, aCvdsiscsiiniti_119; "CVdsIscsiInitiatorAdapterInternal::AddI"...
0x1400209d7  jmp     loc_140020A62
0x1400209dc  lea     rcx, [rbp+var_38]
0x1400209e0  call    ?CreateInstance@?$CComObject@VCVdsIscsiInitiatorPortalInternal@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CVdsIscsiInitiatorPortalInternal>::CreateInstance(ATL::CComObject<CVdsIscsiInitiatorPortalInternal> * *)
0x1400209e5  mov     rbx, [rbp+var_38]
0x1400209e9  test    rbx, rbx
0x1400209ec  jnz     short loc_140020A07
0x1400209ee  lea     rdx, aCvdsiscsiiniti_113; "CVdsIscsiInitiatorAdapterInternal::AddI"...
0x1400209f5  xor     ecx, ecx
0x1400209f7  call    cs:__imp_VdsTraceW
0x1400209fd  mov     edi, 8007000Eh
0x140020a02  jmp     loc_140020AA4
0x140020a07  mov     rax, [rbx]
0x140020a0a  mov     rcx, rbx
0x140020a0d  mov     rax, [rax+8]
0x140020a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020a16  mov     [rsp+70h+var_50], r15; struct _VDS_IPADDRESS *
0x140020a1b  mov     r9d, r14d; unsigned int
0x140020a1e  mov     r8, rsi; struct CVdsIscsiInitiatorAdapterInternal *
0x140020a21  lea     rdx, [rbp+pguid]; struct _GUID *
0x140020a25  mov     rcx, rbx; this
0x140020a28  call    ?Initialize@CVdsIscsiInitiatorPortalInternal@@QEAAJPEBU_GUID@@PEAVCVdsIscsiInitiatorAdapterInternal@@KPEBU_VDS_IPADDRESS@@@Z; CVdsIscsiInitiatorPortalInternal::Initialize(_GUID const *,CVdsIscsiInitiatorAdapterInternal *,ulong,_VDS_IPADDRESS const *)
0x140020a2d  mov     edi, eax
0x140020a2f  test    eax, eax
0x140020a31  jns     short loc_140020A3C
0x140020a33  lea     r8, aCvdsiscsiiniti_124; "CVdsIscsiInitiatorAdapterInternal::AddI"...
0x140020a3a  jmp     short loc_140020A62
0x140020a3c  mov     rax, [rbx]
0x140020a3f  lea     r8, [rbp+var_40]
0x140020a43  lea     rdx, IID_IUnknown
0x140020a4a  mov     rcx, rbx
0x140020a4d  mov     rax, [rax]
0x140020a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020a55  mov     edi, eax
0x140020a57  test    eax, eax
0x140020a59  jns     short loc_140020A72
0x140020a5b  lea     r8, aCvdsiscsiiniti_89; "CVdsIscsiInitiatorAdapterInternal::AddI"...
0x140020a62  mov     r9d, eax
0x140020a65  xor     edx, edx
0x140020a67  lea     ecx, [rdx+5Eh]
0x140020a6a  call    cs:__imp_VdsTraceEx
0x140020a70  jmp     short loc_140020AA4
0x140020a72  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140020a79  call    cs:__imp_EnterCriticalSection
0x140020a7f  nop
0x140020a80  lea     rcx, [rsi+58h]
0x140020a84  mov     rdx, [rbp+var_40]
0x140020a88  call    cs:__imp_?InsertTailPointer@CRtlList@@QEAAHPEAX@Z; CRtlList::InsertTailPointer(void *)
0x140020a8e  mov     [rbp+var_40], 0
0x140020a96  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140020a9d  call    cs:__imp_LeaveCriticalSection
0x140020aa3  nop
0x140020aa4  lea     rcx, [rbp+var_30]
0x140020aa8  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140020aae  nop
0x140020aaf  lea     rcx, [rbp+var_40]
0x140020ab3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140020ab8  nop
0x140020ab9  lea     rcx, [rbp+var_38]
0x140020abd  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140020ac2  mov     eax, edi
0x140020ac4  mov     rcx, [rbp+var_8]
0x140020ac8  xor     rcx, rsp; StackCookie
0x140020acb  call    __security_check_cookie
0x140020ad0  mov     rbx, [rsp+70h+arg_18]
0x140020ad8  add     rsp, 70h
0x140020adc  pop     r15
0x140020ade  pop     r14
0x140020ae0  pop     rdi
0x140020ae1  pop     rsi
0x140020ae2  pop     rbp
0x140020ae3  retn
```
