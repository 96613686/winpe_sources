# CVdsService::LoadSasPorts(void)

- ea: `0x14000a9c4`
- end: `0x14000ae68`
- name: `?LoadSasPorts@CVdsService@@CAJXZ`
- size: `1188`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x140009e70`

## callees

- `0x14000a9c4`
- `0x14000b99c`
- `0x14000f98c`
- `0x140012c48`
- `0x140015f54`
- `0x1400160f8`
- `0x140016150`
- `0x1400163a4`
- `0x14002e123`
- `0x140037044`
- `0x1400381a4`
- `0x14003e23c`
- `0x14005071c`
- `0x140050aac`
- `0x140050b3c`
- `0x140050e5c`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000adc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000adc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000ad9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000ad9e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14000ad58`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14000ad58`
- `vdsutil!VdsTrace` at `0x14000aa91`
- `vdsutil!VdsTrace` at `0x14000ab13`
- `vdsutil!VdsTrace` at `0x14000ab53`
- `vdsutil!VdsTrace` at `0x14000abe3`
- `vdsutil!VdsTrace` at `0x14000ac9e`
- `vdsutil!VdsTrace` at `0x14000aa91`
- `vdsutil!VdsTrace` at `0x14000ab13`
- `vdsutil!VdsTrace` at `0x14000ab53`
- `vdsutil!VdsTrace` at `0x14000abe3`
- `vdsutil!VdsTrace` at `0x14000ac9e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000a9fe`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000a9fe`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000ae40`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000ae40`
- `vdsutil!?InsertTailPointer@CRtlList@@QEAAHPEAX@Z` at `0x14000adb1`
- `vdsutil!?InsertTailPointer@CRtlList@@QEAAHPEAX@Z` at `0x14000adb1`

## string_xrefs

- `0x14000a9ee`: `CVdsService::LoadSasPorts()`
- `0x14000aa82`: `SmHbaAdapterEnum::MoveNext, 2, hr=%x`
- `0x14000ab09`: `SmHbaAdapterEnum::MoveNext, 3, Failed to IEnumWbemClassObject::Next: %x`
- `0x14000aad2`: `SmHbaAdapterEnum::MoveNext, 4, Expect to IEnumWbemClassObject::Next to return non-NULL IWbemClassObject: %x`
- `0x14000aaf3`: `SmHbaAdapterEnum::MoveNext, 5, hr: %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 CVdsService::LoadSasPorts(void)
{
  int v0; // ebx
  const char *v1; // rdx
  int v2; // eax
  int v3; // eax
  int UlongFromInstance; // eax
  unsigned int i; // edi
  unsigned int v6; // r8d
  const char *v7; // rdx
  int v8; // ebx
  int AdapterPortAttributes; // eax
  unsigned int v10; // eax
  int refreshed; // eax
  unsigned int v12; // r8d
  int v13; // eax
  CVdsHbaPortInternal *v14; // rbx
  unsigned int v16; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v17; // [rsp+34h] [rbp-CCh]
  struct IUnknown *v18; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  struct IWbemServices *v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  struct IUnknown *v22; // [rsp+58h] [rbp-A8h] BYREF
  void *v23; // [rsp+60h] [rbp-A0h] BYREF
  struct IWbemClassObject *v24; // [rsp+68h] [rbp-98h] BYREF
  CVdsHbaPortInternal *v25; // [rsp+70h] [rbp-90h] BYREF
  struct IUnknown *v26; // [rsp+78h] [rbp-88h] BYREF
  struct IWbemClassObject *v27; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v28[2]; // [rsp+88h] [rbp-78h] BYREF
  struct IWbemServices **v29; // [rsp+98h] [rbp-68h]
  struct IUnknown **v30; // [rsp+A0h] [rbp-60h]
  struct IUnknown **v31; // [rsp+A8h] [rbp-58h]
  struct IWbemClassObject **v32; // [rsp+B0h] [rbp-50h]
  _BYTE v33[24]; // [rsp+B8h] [rbp-48h] BYREF
  HBA_PortAttributes v34; // [rsp+D0h] [rbp-30h] BYREF
  GUID pguid; // [rsp+350h] [rbp+250h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v33, 0x5Eu, "CVdsService::LoadSasPorts()");
  v25 = (CVdsHbaPortInternal *)&v20;
  v20 = 0;
  v24 = (struct IWbemClassObject *)&v21;
  v21 = 0;
  v0 = SmHbaAdapterEnum::Initialize((SmHbaAdapterEnum *)&v20);
  if ( v0 < 0 )
    goto LABEL_53;
  while ( 1 )
  {
    v31 = &v26;
    v26 = 0;
    v32 = &v27;
    v27 = 0;
    v29 = (struct IWbemServices **)v28;
    v28[0] = 0;
    v28[1] = 0;
    v24 = 0;
    v19 = 0;
    if ( !v21 )
    {
      v1 = "SmHbaAdapterEnum::MoveNext, 2, hr=%x";
LABEL_4:
      v0 = -2147418113;
      VdsTrace(0, v1, 2147549183LL);
      goto LABEL_14;
    }
    v2 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, struct IWbemClassObject **, int *))(*(_QWORD *)v21 + 32LL))(
           v21,
           0xFFFFFFFFLL,
           1,
           &v24,
           &v19);
    if ( v2 )
    {
      if ( v2 == 1 )
      {
        v0 = 1;
        goto LABEL_14;
      }
LABEL_13:
      VdsTrace(1, "SmHbaAdapterEnum::MoveNext, 3, Failed to IEnumWbemClassObject::Next: %x", v2);
      v0 = -2147467259;
      goto LABEL_14;
    }
    if ( v19 != 1 )
      goto LABEL_13;
    if ( !v24 )
    {
      v1 = "SmHbaAdapterEnum::MoveNext, 4, Expect to IEnumWbemClassObject::Next to return non-NULL IWbemClassObject: %x";
      goto LABEL_4;
    }
    v3 = SmHbaAdapter::Initialize(&v26, v20, v24);
    v0 = v3;
    if ( v3 < 0 )
      VdsTrace(0, "SmHbaAdapterEnum::MoveNext, 5, hr: %x", (unsigned int)v3);
LABEL_14:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v24);
    if ( v0 < 0 )
      goto LABEL_52;
    if ( v0 == 1 )
      break;
    v17 = 0;
    if ( !v27 )
    {
      VdsTrace(0, "SmHbaAdapter::GetPortCount, 2, hr: %x", 2147549183LL);
      goto LABEL_50;
    }
    UlongFromInstance = GetUlongFromInstance(v27, L"NumberOfPorts");
    if ( UlongFromInstance < 0 )
    {
      VdsTrace(0, "SmHbaAdapter::GetPortCount, 3, hr: %x", (unsigned int)UlongFromInstance);
      goto LABEL_50;
    }
    for ( i = 0; i < v17; ++i )
    {
      pguid = 0;
      v25 = 0;
      v23 = 0;
      v34.NodeWWN.wwn[0] = 0;
      memset_0((char *)&v34.NodeWWN + 1, 0, 0x277u);
      v30 = &v18;
      v18 = 0;
      v16 = 0;
      v22 = 0;
      if ( !v27 )
      {
        v7 = "SmHbaAdapter::GetPort, 2, hr: %x";
LABEL_23:
        v8 = -2147418113;
        VdsTrace(0, v7, 2147549183LL);
        goto LABEL_40;
      }
      if ( !v26 )
      {
        v7 = "SmHbaAdapter::GetPort, 3, hr: %x";
        goto LABEL_23;
      }
      AdapterPortAttributes = SmHbaAdapter::SmGetAdapterPortAttributes(
                                (SmHbaAdapter *)&v26,
                                i,
                                v6,
                                &v16,
                                (struct IWbemClassObject **)&v22);
      v8 = AdapterPortAttributes;
      if ( AdapterPortAttributes < 0 )
      {
        VdsTrace(0, "SmHbaAdapter::GetPort, 4, hr: %x", (unsigned int)AdapterPortAttributes);
        goto LABEL_40;
      }
      v10 = v16;
      if ( v16 == 8 )
      {
        refreshed = SmHbaAdapter::SmRefreshInformation((SmHbaAdapter *)&v26);
        v8 = refreshed;
        if ( refreshed < 0 )
        {
          VdsTrace(0, "SmHbaAdapter::GetPort, 5, hr: %x", (unsigned int)refreshed);
          goto LABEL_40;
        }
        v13 = SmHbaAdapter::SmGetAdapterPortAttributes(
                (SmHbaAdapter *)&v26,
                i,
                v12,
                &v16,
                (struct IWbemClassObject **)&v22);
        v8 = v13;
        if ( v13 < 0 )
        {
          VdsTrace(0, "SmHbaAdapter::GetPort, 6, hr: %x", (unsigned int)v13);
          goto LABEL_40;
        }
        v10 = v16;
      }
      if ( !v10 )
      {
        if ( v22 )
        {
          v8 = 0;
          if ( v18 != v22 )
            ATL::AtlComPtrAssign(&v18, v22);
          goto LABEL_40;
        }
        v7 = "SmHbaAdapter::GetPort, 8, hr: %x";
        goto LABEL_23;
      }
      VdsTrace(
        0,
        "SmHbaAdapter::GetPort, 7, Failed to SmGetAdapterPortAttributes(%d,%d,...): HBA_STATUS(%d)",
        i,
        616,
        v10);
      v8 = -2147467259;
LABEL_40:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
      if ( v8 >= 0 )
      {
        v16 = 1;
        if ( (int)SmHbaAdapterPort::GetType((SmHbaAdapterPort *)&v18, &v16) >= 0
          && v16 - 30 <= 2
          && (int)SmHbaAdapterPort::GetSasAttributes((SmHbaAdapterPort *)&v18, &v34) >= 0 )
        {
          ATL::CComObject<CVdsHbaPortInternal>::CreateInstance((__int64 *)&v25);
          v14 = v25;
          if ( v25 )
          {
            (*(void (__fastcall **)(CVdsHbaPortInternal *))(*(_QWORD *)v25 + 8LL))(v25);
            if ( CoCreateGuid(&pguid) >= 0
              && (int)CVdsHbaPortInternal::Initialize(v14, &pguid, &v34) >= 0
              && (**(int (__fastcall ***)(CVdsHbaPortInternal *, GUID *, void **))v14)(v14, &IID_IUnknown, &v23) >= 0 )
            {
              EnterCriticalSection(&g_GlobalCriticalSection);
              CRtlList::InsertTailPointer((CRtlList *)CVdsService::m_lstHbaPorts, v23);
              v23 = 0;
              LeaveCriticalSection(&g_GlobalCriticalSection);
            }
          }
        }
      }
      SmHbaAdapterPort::~SmHbaAdapterPort((SmHbaAdapterPort *)&v18);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v23);
      ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v25);
    }
LABEL_50:
    SmHbaAdapter::~SmHbaAdapter((SmHbaAdapter *)&v26);
  }
  v0 = 0;
LABEL_52:
  SmHbaAdapter::~SmHbaAdapter((SmHbaAdapter *)&v26);
LABEL_53:
  v30 = (struct IUnknown **)&v21;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  v29 = &v20;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v33);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14000a9c4  push    rbp
0x14000a9c6  push    rbx
0x14000a9c7  push    rdi
0x14000a9c8  push    r12
0x14000a9ca  push    r14
0x14000a9cc  push    r15
0x14000a9ce  lea     rbp, [rsp-278h]
0x14000a9d6  sub     rsp, 378h
0x14000a9dd  mov     rax, cs:__security_cookie
0x14000a9e4  xor     rax, rsp
0x14000a9e7  mov     [rbp+2A0h+var_38], rax
0x14000a9ee  lea     r8, aCvdsserviceLoa_6; "CVdsService::LoadSasPorts()"
0x14000a9f5  mov     edx, 5Eh ; '^'
0x14000a9fa  lea     rcx, [rbp+2A0h+var_2E8]
0x14000a9fe  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000aa04  nop
0x14000aa05  lea     rax, [rsp+3A0h+var_358]
0x14000aa0a  mov     [rsp+3A0h+var_330], rax
0x14000aa0f  xor     r14d, r14d
0x14000aa12  mov     [rsp+3A0h+var_358], r14
0x14000aa17  lea     rax, [rsp+3A0h+var_350]
0x14000aa1c  mov     [rsp+3A0h+var_338], rax
0x14000aa21  mov     [rsp+3A0h+var_350], r14
0x14000aa26  lea     rcx, [rsp+3A0h+var_358]; this
0x14000aa2b  call    ?Initialize@SmHbaAdapterEnum@@QEAAJXZ; SmHbaAdapterEnum::Initialize(void)
0x14000aa30  mov     ebx, eax
0x14000aa32  test    eax, eax
0x14000aa34  js      loc_14000AE14
0x14000aa3a  mov     r15d, 8000FFFFh
0x14000aa40  lea     r12d, [r14+1]
0x14000aa44  lea     rax, [rsp+3A0h+var_328]
0x14000aa49  mov     [rbp+2A0h+var_2F8], rax
0x14000aa4d  mov     [rsp+3A0h+var_328], r14
0x14000aa52  lea     rax, [rbp+2A0h+var_320]
0x14000aa56  mov     [rbp+2A0h+var_2F0], rax
0x14000aa5a  mov     [rbp+2A0h+var_320], r14
0x14000aa5e  lea     rax, [rbp+2A0h+var_318]
0x14000aa62  mov     [rbp+2A0h+var_308], rax
0x14000aa66  mov     [rbp+2A0h+var_318], r14
0x14000aa6a  mov     [rbp+2A0h+var_310], r14
0x14000aa6e  mov     [rsp+3A0h+var_338], r14
0x14000aa73  mov     [rsp+3A0h+var_360], r14d
0x14000aa78  mov     rcx, [rsp+3A0h+var_350]
0x14000aa7d  test    rcx, rcx
0x14000aa80  jnz     short loc_14000AA9C
0x14000aa82  lea     rdx, aSmhbaadapteren_1; "SmHbaAdapterEnum::MoveNext, 2, hr=%x"
0x14000aa89  mov     r8d, r15d
0x14000aa8c  mov     ebx, r15d
0x14000aa8f  xor     ecx, ecx
0x14000aa91  call    cs:__imp_VdsTrace
0x14000aa97  jmp     loc_14000AB1E
0x14000aa9c  mov     rax, [rcx]
0x14000aa9f  lea     rdx, [rsp+3A0h+var_360]
0x14000aaa4  mov     [rsp+3A0h+var_380], rdx
0x14000aaa9  lea     r9, [rsp+3A0h+var_338]
0x14000aaae  mov     r8d, r12d
0x14000aab1  or      edx, 0FFFFFFFFh
0x14000aab4  mov     rax, [rax+20h]
0x14000aab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aabd  test    eax, eax
0x14000aabf  jnz     short loc_14000AAFC
0x14000aac1  cmp     [rsp+3A0h+var_360], r12d
0x14000aac6  jnz     short loc_14000AB06
0x14000aac8  mov     r8, [rsp+3A0h+var_338]; struct IWbemClassObject *
0x14000aacd  test    r8, r8
0x14000aad0  jnz     short loc_14000AADB
0x14000aad2  lea     rdx, aSmhbaadapteren_2; "SmHbaAdapterEnum::MoveNext, 4, Expect t"...
0x14000aad9  jmp     short loc_14000AA89
0x14000aadb  mov     rdx, [rsp+3A0h+var_358]; struct IWbemServices *
0x14000aae0  lea     rcx, [rsp+3A0h+var_328]; this
0x14000aae5  call    ?Initialize@SmHbaAdapter@@QEAAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; SmHbaAdapter::Initialize(IWbemServices *,IWbemClassObject *)
0x14000aaea  mov     ebx, eax
0x14000aaec  test    eax, eax
0x14000aaee  jns     short loc_14000AB1E
0x14000aaf0  mov     r8d, eax
0x14000aaf3  lea     rdx, aSmhbaadapteren; "SmHbaAdapterEnum::MoveNext, 5, hr: %x"
0x14000aafa  jmp     short loc_14000AA8F
0x14000aafc  cmp     eax, r12d
0x14000aaff  jnz     short loc_14000AB06
0x14000ab01  mov     ebx, r12d
0x14000ab04  jmp     short loc_14000AB1E
0x14000ab06  mov     r8d, eax
0x14000ab09  lea     rdx, aSmhbaadapteren_0; "SmHbaAdapterEnum::MoveNext, 3, Failed t"...
0x14000ab10  mov     ecx, r12d
0x14000ab13  call    cs:__imp_VdsTrace
0x14000ab19  mov     ebx, 80004005h
0x14000ab1e  lea     rcx, [rsp+3A0h+var_338]
0x14000ab23  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000ab28  test    ebx, ebx
0x14000ab2a  js      loc_14000AE09
0x14000ab30  cmp     ebx, r12d
0x14000ab33  jz      loc_14000AE06
0x14000ab39  mov     [rsp+3A0h+var_36C], r14d
0x14000ab3e  mov     rcx, [rbp+2A0h+var_320]; struct IWbemClassObject *
0x14000ab42  test    rcx, rcx
0x14000ab45  jnz     short loc_14000AB5E
0x14000ab47  mov     r8d, r15d
0x14000ab4a  lea     rdx, aSmhbaadapterGe_4; "SmHbaAdapter::GetPortCount, 2, hr: %x"
0x14000ab51  xor     ecx, ecx
0x14000ab53  call    cs:__imp_VdsTrace
0x14000ab59  jmp     loc_14000ADF7
0x14000ab5e  lea     r8, [rsp+3A0h+var_36C]
0x14000ab63  lea     rdx, aNumberofports; "NumberOfPorts"
0x14000ab6a  call    GetUlongFromInstance
0x14000ab6f  test    eax, eax
0x14000ab71  jns     short loc_14000AB7F
0x14000ab73  mov     r8d, eax
0x14000ab76  lea     rdx, aSmhbaadapterGe_0; "SmHbaAdapter::GetPortCount, 3, hr: %x"
0x14000ab7d  jmp     short loc_14000AB51
0x14000ab7f  mov     edi, r14d
0x14000ab82  cmp     [rsp+3A0h+var_36C], r14d
0x14000ab87  jbe     loc_14000ADF7
0x14000ab8d  xorps   xmm0, xmm0
0x14000ab90  movups  xmmword ptr [rbp+2A0h+pguid.Data1], xmm0
0x14000ab97  mov     [rsp+3A0h+var_330], r14
0x14000ab9c  mov     [rsp+3A0h+var_340], r14
0x14000aba1  mov     [rbp+2A0h+var_2D0.NodeWWN.wwn], r14b
0x14000aba5  xor     edx, edx; Val
0x14000aba7  mov     r8d, 277h; Size
0x14000abad  lea     rcx, [rbp+2A0h+var_2D0.NodeWWN.wwn+1]; void *
0x14000abb1  call    memset_0
0x14000abb6  lea     rax, [rsp+3A0h+var_368]
0x14000abbb  mov     [rbp+2A0h+var_300], rax
0x14000abbf  mov     [rsp+3A0h+var_368], r14
0x14000abc4  mov     [rsp+3A0h+var_370], r14d
0x14000abc9  mov     [rsp+3A0h+var_348], r14
0x14000abce  cmp     [rbp+2A0h+var_320], r14
0x14000abd2  jnz     short loc_14000ABEE
0x14000abd4  lea     rdx, aSmhbaadapterGe; "SmHbaAdapter::GetPort, 2, hr: %x"
0x14000abdb  mov     ebx, r15d
0x14000abde  mov     r8d, r15d
0x14000abe1  xor     ecx, ecx
0x14000abe3  call    cs:__imp_VdsTrace
0x14000abe9  jmp     loc_14000ACD6
0x14000abee  cmp     [rsp+3A0h+var_328], r14
0x14000abf3  jnz     short loc_14000ABFE
0x14000abf5  lea     rdx, aSmhbaadapterGe_6; "SmHbaAdapter::GetPort, 3, hr: %x"
0x14000abfc  jmp     short loc_14000ABDB
0x14000abfe  lea     rax, [rsp+3A0h+var_348]
0x14000ac03  mov     [rsp+3A0h+var_380], rax; struct IWbemClassObject **
0x14000ac08  lea     r9, [rsp+3A0h+var_370]; unsigned int *
0x14000ac0d  mov     edx, edi; unsigned int
0x14000ac0f  lea     rcx, [rsp+3A0h+var_328]; this
0x14000ac14  call    ?SmGetAdapterPortAttributes@SmHbaAdapter@@AEAAJKKPEAKPEAPEAUIWbemClassObject@@@Z; SmHbaAdapter::SmGetAdapterPortAttributes(ulong,ulong,ulong *,IWbemClassObject * *)
0x14000ac19  mov     ebx, eax
0x14000ac1b  test    eax, eax
0x14000ac1d  jns     short loc_14000AC2B
0x14000ac1f  mov     r8d, eax
0x14000ac22  lea     rdx, aSmhbaadapterGe_1; "SmHbaAdapter::GetPort, 4, hr: %x"
0x14000ac29  jmp     short loc_14000ABE1
0x14000ac2b  mov     eax, [rsp+3A0h+var_370]
0x14000ac2f  cmp     eax, 8
0x14000ac32  jnz     short loc_14000AC84
0x14000ac34  lea     rcx, [rsp+3A0h+var_328]; this
0x14000ac39  call    ?SmRefreshInformation@SmHbaAdapter@@AEAAJXZ; SmHbaAdapter::SmRefreshInformation(void)
0x14000ac3e  mov     ebx, eax
0x14000ac40  test    eax, eax
0x14000ac42  jns     short loc_14000AC50
0x14000ac44  mov     r8d, eax
0x14000ac47  lea     rdx, aSmhbaadapterGe_3; "SmHbaAdapter::GetPort, 5, hr: %x"
0x14000ac4e  jmp     short loc_14000ABE1
0x14000ac50  lea     rax, [rsp+3A0h+var_348]
0x14000ac55  mov     [rsp+3A0h+var_380], rax; struct IWbemClassObject **
0x14000ac5a  lea     r9, [rsp+3A0h+var_370]; unsigned int *
0x14000ac5f  mov     edx, edi; unsigned int
0x14000ac61  lea     rcx, [rsp+3A0h+var_328]; this
0x14000ac66  call    ?SmGetAdapterPortAttributes@SmHbaAdapter@@AEAAJKKPEAKPEAPEAUIWbemClassObject@@@Z; SmHbaAdapter::SmGetAdapterPortAttributes(ulong,ulong,ulong *,IWbemClassObject * *)
0x14000ac6b  mov     ebx, eax
0x14000ac6d  test    eax, eax
0x14000ac6f  jns     short loc_14000AC80
0x14000ac71  mov     r8d, eax
0x14000ac74  lea     rdx, aSmhbaadapterGe_2; "SmHbaAdapter::GetPort, 6, hr: %x"
0x14000ac7b  jmp     loc_14000ABE1
0x14000ac80  mov     eax, [rsp+3A0h+var_370]
0x14000ac84  test    eax, eax
0x14000ac86  jz      short loc_14000ACAB
0x14000ac88  mov     dword ptr [rsp+3A0h+var_380], eax
0x14000ac8c  mov     r9d, 268h
0x14000ac92  mov     r8d, edi
0x14000ac95  lea     rdx, aSmhbaadapterGe_7; "SmHbaAdapter::GetPort, 7, Failed to SmG"...
0x14000ac9c  xor     ecx, ecx
0x14000ac9e  call    cs:__imp_VdsTrace
0x14000aca4  mov     ebx, 80004005h
0x14000aca9  jmp     short loc_14000ACD6
0x14000acab  mov     rdx, [rsp+3A0h+var_348]; struct IUnknown *
0x14000acb0  test    rdx, rdx
0x14000acb3  jnz     short loc_14000ACC1
0x14000acb5  lea     rdx, aSmhbaadapterGe_5; "SmHbaAdapter::GetPort, 8, hr: %x"
0x14000acbc  jmp     loc_14000ABDB
0x14000acc1  mov     ebx, r14d
0x14000acc4  cmp     [rsp+3A0h+var_368], rdx
0x14000acc9  jz      short loc_14000ACD6
0x14000accb  lea     rcx, [rsp+3A0h+var_368]; struct IUnknown **
0x14000acd0  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x14000acd5  nop
0x14000acd6  lea     rcx, [rsp+3A0h+var_348]
0x14000acdb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000ace0  test    ebx, ebx
0x14000ace2  js      loc_14000ADCA
0x14000ace8  mov     [rsp+3A0h+var_370], r12d
0x14000aced  lea     rdx, [rsp+3A0h+var_370]; unsigned int *
0x14000acf2  lea     rcx, [rsp+3A0h+var_368]; this
0x14000acf7  call    ?GetType@SmHbaAdapterPort@@QEAAJPEAK@Z; SmHbaAdapterPort::GetType(ulong *)
0x14000acfc  test    eax, eax
0x14000acfe  js      loc_14000ADCA
0x14000ad04  mov     eax, [rsp+3A0h+var_370]
0x14000ad08  add     eax, 0FFFFFFE2h
0x14000ad0b  cmp     eax, 2
0x14000ad0e  ja      loc_14000ADCA
0x14000ad14  lea     rdx, [rbp+2A0h+var_2D0]; struct HBA_PortAttributes *
0x14000ad18  lea     rcx, [rsp+3A0h+var_368]; this
0x14000ad1d  call    ?GetSasAttributes@SmHbaAdapterPort@@QEAAJPEAUHBA_PortAttributes@@@Z; SmHbaAdapterPort::GetSasAttributes(HBA_PortAttributes *)
0x14000ad22  test    eax, eax
0x14000ad24  js      loc_14000ADCA
0x14000ad2a  lea     rcx, [rsp+3A0h+var_330]
0x14000ad2f  call    ?CreateInstance@?$CComObject@VCVdsHbaPortInternal@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CVdsHbaPortInternal>::CreateInstance(ATL::CComObject<CVdsHbaPortInternal> * *)
0x14000ad34  mov     rbx, [rsp+3A0h+var_330]
0x14000ad39  test    rbx, rbx
0x14000ad3c  jz      loc_14000ADCA
0x14000ad42  mov     rax, [rbx]
0x14000ad45  mov     rcx, rbx
0x14000ad48  mov     rax, [rax+8]
0x14000ad4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad51  lea     rcx, [rbp+2A0h+pguid]; pguid
0x14000ad58  call    cs:__imp_CoCreateGuid
0x14000ad5e  test    eax, eax
0x14000ad60  js      short loc_14000ADCA
0x14000ad62  lea     r8, [rbp+2A0h+var_2D0]; struct HBA_PortAttributes *
0x14000ad66  lea     rdx, [rbp+2A0h+pguid]; struct _GUID *
0x14000ad6d  mov     rcx, rbx; this
0x14000ad70  call    ?Initialize@CVdsHbaPortInternal@@QEAAJPEBU_GUID@@PEAUHBA_PortAttributes@@@Z; CVdsHbaPortInternal::Initialize(_GUID const *,HBA_PortAttributes *)
0x14000ad75  test    eax, eax
0x14000ad77  js      short loc_14000ADCA
0x14000ad79  mov     rax, [rbx]
0x14000ad7c  lea     r8, [rsp+3A0h+var_340]
0x14000ad81  lea     rdx, IID_IUnknown
0x14000ad88  mov     rcx, rbx
0x14000ad8b  mov     rax, [rax]
0x14000ad8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad93  test    eax, eax
0x14000ad95  js      short loc_14000ADCA
0x14000ad97  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000ad9e  call    cs:__imp_EnterCriticalSection
0x14000ada4  nop
0x14000ada5  mov     rdx, [rsp+3A0h+var_340]
0x14000adaa  lea     rcx, ?m_lstHbaPorts@CVdsService@@0VCRtlList@@A; CRtlList CVdsService::m_lstHbaPorts
0x14000adb1  call    cs:__imp_?InsertTailPointer@CRtlList@@QEAAHPEAX@Z; CRtlList::InsertTailPointer(void *)
0x14000adb7  mov     [rsp+3A0h+var_340], r14
0x14000adbc  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000adc3  call    cs:__imp_LeaveCriticalSection
0x14000adc9  nop
0x14000adca  lea     rcx, [rsp+3A0h+var_368]; this
0x14000adcf  call    ??1SmHbaAdapterPort@@QEAA@XZ; SmHbaAdapterPort::~SmHbaAdapterPort(void)
0x14000add4  nop
0x14000add5  lea     rcx, [rsp+3A0h+var_340]
0x14000adda  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000addf  nop
0x14000ade0  lea     rcx, [rsp+3A0h+var_330]
0x14000ade5  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14000adea  add     edi, r12d
0x14000aded  cmp     edi, [rsp+3A0h+var_36C]
0x14000adf1  jb      loc_14000AB8D
0x14000adf7  lea     rcx, [rsp+3A0h+var_328]; this
0x14000adfc  call    ??1SmHbaAdapter@@QEAA@XZ; SmHbaAdapter::~SmHbaAdapter(void)
0x14000ae01  jmp     loc_14000AA44
0x14000ae06  mov     ebx, r14d
0x14000ae09  lea     rcx, [rsp+3A0h+var_328]; this
0x14000ae0e  call    ??1SmHbaAdapter@@QEAA@XZ; SmHbaAdapter::~SmHbaAdapter(void)
0x14000ae13  nop
0x14000ae14  lea     rax, [rsp+3A0h+var_350]
0x14000ae19  mov     [rbp+2A0h+var_300], rax
0x14000ae1d  lea     rcx, [rsp+3A0h+var_350]
0x14000ae22  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000ae27  nop
0x14000ae28  lea     rax, [rsp+3A0h+var_358]
0x14000ae2d  mov     [rbp+2A0h+var_308], rax
0x14000ae31  lea     rcx, [rsp+3A0h+var_358]
0x14000ae36  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000ae3b  nop
0x14000ae3c  lea     rcx, [rbp+2A0h+var_2E8]
0x14000ae40  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000ae46  mov     eax, ebx
0x14000ae48  mov     rcx, [rbp+2A0h+var_38]
0x14000ae4f  xor     rcx, rsp; StackCookie
0x14000ae52  call    __security_check_cookie
0x14000ae57  add     rsp, 378h
0x14000ae5e  pop     r15
0x14000ae60  pop     r14
0x14000ae62  pop     r12
0x14000ae64  pop     rdi
0x14000ae65  pop     rbx
0x14000ae66  pop     rbp
0x14000ae67  retn
```
