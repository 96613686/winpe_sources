# CSrmFunctionTracer::SetError(HINSTANCE__ *,ulong,CSrmDebugInfo)

- ea: `0x180073080`
- end: `0x180073707`
- name: `?SetError@CSrmFunctionTracer@@QEAAXPEAUHINSTANCE__@@KUCSrmDebugInfo@@@Z`
- size: `1671`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x180072ed8`

## callees

- `0x180006a1c`
- `0x18006fe68`
- `0x18006febc`
- `0x18007006c`
- `0x1800700b8`
- `0x18007120c`
- `0x180073080`
- `0x180073d04`
- `0x180074048`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180073447`
- `ole32!CoTaskMemFree` at `0x180073447`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800733c4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800733c4`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180073331`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180073331`
- `KERNEL32!GetLastError` at `0x1800734aa`
- `KERNEL32!GetLastError` at `0x1800734aa`
- `KERNEL32!LocalFree` at `0x1800732d9`
- `KERNEL32!LocalFree` at `0x180073416`
- `KERNEL32!LocalFree` at `0x180073437`
- `KERNEL32!LocalFree` at `0x1800732d9`
- `KERNEL32!LocalFree` at `0x180073416`
- `KERNEL32!LocalFree` at `0x180073437`
- `KERNEL32!FormatMessageW` at `0x180073314`
- `KERNEL32!FormatMessageW` at `0x180073314`

## string_xrefs

- `0x1800735bc`: `spCreateErrorInfo::SetDescription failed, %#x`
- `0x180073557`: `CreateErrorInfo failed, %#x`
- `0x180073686`: `ICreateErrorInfo->QI(IErrorInfo) failed, %#x`
- `0x180073621`: `spCreateErrorInfo::SetSource failed, %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=17 #try_helpers=1
void __fastcall CSrmFunctionTracer::SetError(CSrmFunctionTracerBase *a1, const void *a2, __int64 a3, __int64 a4)
{
  int v7; // edx
  unsigned __int16 i; // di
  LPVOID v9; // r9
  unsigned __int16 j; // cx
  DWORD LastError; // ebx
  __int64 v12; // rax
  unsigned int Hr; // ebx
  __int64 v14; // rax
  unsigned int v15; // ebx
  __int64 v16; // rax
  unsigned int v17; // ebx
  __int64 v18; // rax
  unsigned int v19; // ebx
  __int64 v20; // rax
  unsigned int v21; // ebx
  __int64 v22; // rax
  LPWSTR lpBuffer; // [rsp+20h] [rbp-2F8h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-2F8h]
  LPWSTR lpBufferb; // [rsp+20h] [rbp-2F8h]
  LPWSTR lpBufferc; // [rsp+20h] [rbp-2F8h]
  LPWSTR lpBufferd; // [rsp+20h] [rbp-2F8h]
  LPWSTR lpBuffere; // [rsp+20h] [rbp-2F8h]
  HLOCAL hMem; // [rsp+50h] [rbp-2C8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-2C0h] BYREF
  IErrorInfo *perrinfo; // [rsp+60h] [rbp-2B8h] BYREF
  ICreateErrorInfo *pperrinfo[2]; // [rsp+68h] [rbp-2B0h] BYREF
  _QWORD *v33; // [rsp+78h] [rbp-2A0h]
  _QWORD v34[3]; // [rsp+88h] [rbp-290h] BYREF
  int v35; // [rsp+A0h] [rbp-278h]
  int v36; // [rsp+A4h] [rbp-274h]
  int v37; // [rsp+A8h] [rbp-270h]
  _QWORD v38[12]; // [rsp+B0h] [rbp-268h]
  __int16 v39; // [rsp+110h] [rbp-208h]
  char v40; // [rsp+112h] [rbp-206h]
  char v41; // [rsp+113h] [rbp-205h]
  _QWORD v42[3]; // [rsp+128h] [rbp-1F0h] BYREF
  int v43; // [rsp+140h] [rbp-1D8h]
  int v44; // [rsp+144h] [rbp-1D4h]
  int v45; // [rsp+148h] [rbp-1D0h]
  _DWORD v46[28]; // [rsp+150h] [rbp-1C8h] BYREF
  void **v47; // [rsp+1C0h] [rbp-158h] BYREF
  HRESULT ErrorInfo; // [rsp+1C8h] [rbp-150h]
  va_list Arguments[12]; // [rsp+270h] [rbp-A8h] BYREF

  pperrinfo[1] = (ICreateErrorInfo *)a4;
  perrinfo = (IErrorInfo *)v42;
  v42[0] = L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp";
  v42[1] = L"CSrmFunctionTracer::SetError";
  v42[2] = L"TRCTRCC";
  v43 = 2578;
  v44 = 17;
  v45 = 255;
  v46[24] = 0x1000000;
  memset_0(v46, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v47, (const struct CSrmDebugInfo *)v42, 0);
  memset_0(Arguments, 0, sizeof(Arguments));
  v7 = *(unsigned __int16 *)(a4 + 136);
  if ( (unsigned int)(v7 + 1) < 0xC )
  {
    for ( i = 0; i < (unsigned __int16)v7; ++i )
      Arguments[i] = *(va_list *)(a4 + 8LL * i + 40);
    pv = 0;
    CSrmFunctionTracerBase::GetCurrentContexts(a1, (struct CSrmAutoPWSZ *)&pv);
    v9 = pv;
    perrinfo = (IErrorInfo *)v34;
    v34[0] = L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp";
    v34[1] = L"CSrmFunctionTracer::SetError";
    v34[2] = L"TRCTRCC";
    v35 = 2598;
    v36 = 17;
    v37 = 255;
    v39 = 0;
    v40 = 0;
    v41 = 1;
    for ( j = 0; j < 0xCu; ++j )
      v38[j] = 0;
    CSrmFunctionTracer::Trace(&v47, v34, L"Current context: %s", v9);
    Arguments[i] = (va_list)pv;
    hMem = 0;
    if ( !FormatMessageW(0x2900u, a2, 0x8004203E, 0x400u, (LPWSTR)&hMem, 1u, Arguments) )
    {
      LastError = GetLastError();
      perrinfo = (IErrorInfo *)v34;
      v12 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v34,
              (__int64)L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
              (__int64)L"TRCTRCC",
              (__int64)L"CSrmFunctionTracer::SetError",
              2615,
              17);
      LODWORD(lpBuffer) = LastError;
      CSrmFunctionTracer::Throw(&v47, v12, 2147767062LL, L"Error on FormatMessage0x%08lx", lpBuffer);
    }
    pperrinfo[0] = 0;
    perrinfo = 0;
    ErrorInfo = CreateErrorInfo(pperrinfo);
    if ( ErrorInfo < 0 )
    {
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v47);
      v33 = v34;
      v14 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v34,
              (__int64)L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
              (__int64)L"TRCTRCC",
              (__int64)L"CSrmFunctionTracer::SetError",
              2625,
              17);
      LODWORD(lpBuffera) = Hr;
      CSrmFunctionTracer::Throw(&v47, v14, Hr, L"CreateErrorInfo failed, %#x", lpBuffera);
    }
    ErrorInfo = ((__int64 (__fastcall *)(ICreateErrorInfo *, HLOCAL))pperrinfo[0]->lpVtbl->SetDescription)(
                  pperrinfo[0],
                  hMem);
    if ( ErrorInfo < 0 )
    {
      v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v47);
      v33 = v34;
      v16 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v34,
              (__int64)L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
              (__int64)L"TRCTRCC",
              (__int64)L"CSrmFunctionTracer::SetError",
              2630,
              17);
      LODWORD(lpBufferb) = v15;
      CSrmFunctionTracer::Throw(&v47, v16, v15, L"spCreateErrorInfo::SetDescription failed, %#x", lpBufferb);
    }
    ErrorInfo = ((__int64 (__fastcall *)(ICreateErrorInfo *, const WCHAR *))pperrinfo[0]->lpVtbl->SetSource)(
                  pperrinfo[0],
                  L"SRMSVC");
    if ( ErrorInfo < 0 )
    {
      v17 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v47);
      v33 = v34;
      v18 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v34,
              (__int64)L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
              (__int64)L"TRCTRCC",
              (__int64)L"CSrmFunctionTracer::SetError",
              2635,
              17);
      LODWORD(lpBufferc) = v17;
      CSrmFunctionTracer::Throw(&v47, v18, v17, L"spCreateErrorInfo::SetSource failed, %#x", lpBufferc);
    }
    ErrorInfo = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo[0]->lpVtbl->QueryInterface)(
                  pperrinfo[0],
                  &IID_IErrorInfo,
                  &perrinfo);
    if ( ErrorInfo < 0 )
    {
      v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v47);
      v33 = v34;
      v20 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v34,
              (__int64)L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
              (__int64)L"TRCTRCC",
              (__int64)L"CSrmFunctionTracer::SetError",
              2640,
              17);
      LODWORD(lpBufferd) = v19;
      CSrmFunctionTracer::Throw(&v47, v20, v19, L"ICreateErrorInfo->QI(IErrorInfo) failed, %#x", lpBufferd);
    }
    ErrorInfo = SetErrorInfo(0, perrinfo);
    if ( ErrorInfo < 0 )
    {
      v21 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v47);
      v33 = v34;
      v22 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v34,
              (__int64)L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
              (__int64)L"TRCTRCC",
              (__int64)L"CSrmFunctionTracer::SetError",
              2645,
              17);
      LODWORD(lpBuffere) = v21;
      CSrmFunctionTracer::Throw(&v47, v22, v21, L"SetErrorInfo failed, %#x", lpBuffere);
    }
    if ( perrinfo )
      ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
    if ( pperrinfo[0] )
      ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo[0]->lpVtbl->Release)(pperrinfo[0]);
    if ( hMem )
      LocalFree(hMem);
    hMem = 0;
    CoTaskMemFree(pv);
    pv = 0;
    v47 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v47);
    CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)a4);
  }
  else
  {
    v47 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v47);
    CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)a4);
  }
}

```

## disassembly

```asm
0x180073080  mov     r11, rsp
0x180073083  push    rbx
0x180073084  push    rsi
0x180073085  push    rdi
0x180073086  push    r12
0x180073088  push    r13
0x18007308a  push    r14
0x18007308c  push    r15
0x18007308e  sub     rsp, 2E0h
0x180073095  mov     rax, cs:__security_cookie
0x18007309c  xor     rax, rsp
0x18007309f  mov     [rsp+318h+var_48], rax
0x1800730a7  mov     rbx, r9
0x1800730aa  mov     r14, rdx
0x1800730ad  mov     rsi, rcx
0x1800730b0  mov     [rsp+318h+var_2A8], rbx
0x1800730b5  lea     rax, [r11-1F0h]
0x1800730bc  mov     [rsp+318h+perrinfo], rax
0x1800730c1  lea     r13, aBaseFsFsrmUtil_9; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x1800730c8  mov     [r11-1F0h], r13
0x1800730cf  lea     rax, aCsrmfunctiontr_1; "CSrmFunctionTracer::SetError"
0x1800730d6  mov     [r11-1E8h], rax
0x1800730dd  lea     rax, aTrctrcc; "TRCTRCC"
0x1800730e4  mov     [r11-1E0h], rax
0x1800730eb  mov     [rsp+318h+var_1D8], 0A12h
0x1800730f6  mov     [rsp+318h+var_1D4], 11h
0x180073101  mov     [rsp+318h+var_1D0], 0FFh
0x18007310c  xor     r15d, r15d
0x18007310f  mov     [rsp+318h+var_168], 1000000h
0x18007311a  lea     edi, [r15+60h]
0x18007311e  lea     r12d, [r15+1]
0x180073122  mov     r8d, edi; Size
0x180073125  xor     edx, edx; Val
0x180073127  lea     rcx, [r11-1C8h]; void *
0x18007312e  call    memset_0
0x180073133  nop
0x180073134  xor     r8d, r8d
0x180073137  lea     rdx, [rsp+318h+var_1F0]
0x18007313f  lea     rcx, [rsp+318h+var_158]
0x180073147  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007314c  nop
0x18007314d  mov     r8d, edi; Size
0x180073150  xor     edx, edx; Val
0x180073152  lea     rcx, [rsp+318h+var_A8]; void *
0x18007315a  call    memset_0
0x18007315f  movzx   edx, word ptr [rbx+88h]
0x180073166  lea     eax, [r12+rdx]
0x18007316a  cmp     eax, 0Ch
0x18007316d  jb      short loc_180073199
0x18007316f  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180073176  mov     [rsp+318h+var_158], rax
0x18007317e  lea     rcx, [rsp+318h+var_158]; this
0x180073186  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007318b  nop
0x18007318c  mov     rcx, rbx; this
0x18007318f  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180073194  jmp     loc_180073483
0x180073199  mov     [rsp+318h+var_2D8], r15w
0x18007319f  mov     edi, r15d
0x1800731a2  mov     [rsp+318h+var_2D8], r15w
0x1800731a8  cmp     di, dx
0x1800731ab  jnb     short loc_1800731C8
0x1800731ad  movzx   ecx, di
0x1800731b0  mov     rax, [rbx+rcx*8+28h]
0x1800731b5  mov     [rsp+rcx*8+318h+var_A8], rax
0x1800731bd  add     di, r12w
0x1800731c1  mov     [rsp+318h+var_2D8], di
0x1800731c6  jmp     short loc_1800731A8
0x1800731c8  mov     [rsp+318h+pv], r15
0x1800731cd  lea     rdx, [rsp+318h+pv]; struct CSrmAutoPWSZ *
0x1800731d2  mov     rcx, rsi; this
0x1800731d5  call    ?GetCurrentContexts@CSrmFunctionTracerBase@@QEAAXAEAVCSrmAutoPWSZ@@@Z; CSrmFunctionTracerBase::GetCurrentContexts(CSrmAutoPWSZ &)
0x1800731da  mov     r9, [rsp+318h+pv]
0x1800731df  lea     rdx, [rsp+318h+var_290]
0x1800731e7  mov     [rsp+318h+perrinfo], rdx
0x1800731ec  mov     [rsp+318h+var_290], r13
0x1800731f4  lea     rsi, aCsrmfunctiontr_1; "CSrmFunctionTracer::SetError"
0x1800731fb  mov     [rsp+318h+var_288], rsi
0x180073203  lea     rax, aTrctrcc; "TRCTRCC"
0x18007320a  mov     [rsp+318h+var_280], rax
0x180073212  mov     [rsp+318h+var_278], 0A26h
0x18007321d  mov     [rsp+318h+var_274], 11h
0x180073228  mov     [rsp+318h+var_270], 0FFh
0x180073233  mov     [rsp+318h+var_208], r15w
0x18007323c  mov     [rsp+318h+var_206], r15b
0x180073244  mov     [rsp+318h+var_205], r12b
0x18007324c  mov     ecx, r15d
0x18007324f  mov     r8d, 0Ch
0x180073255  mov     [rsp+318h+var_2D4], cx
0x18007325a  cmp     cx, r8w
0x18007325e  jnb     short loc_180073271
0x180073260  movzx   eax, cx
0x180073263  mov     [rsp+rax*8+318h+var_268], r15
0x18007326b  add     cx, r12w
0x18007326f  jmp     short loc_180073255
0x180073271  lea     r8, aCurrentContext_0; "Current context: %s"
0x180073278  lea     rcx, [rsp+318h+var_158]
0x180073280  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180073285  movzx   ecx, di
0x180073288  mov     rax, [rsp+318h+pv]
0x18007328d  mov     [rsp+rcx*8+318h+var_A8], rax
0x180073295  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x18007329c  mov     [rsp+318h+var_2D0], rax
0x1800732a1  mov     [rsp+318h+hMem], r15
0x1800732a6  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAE@@6B@; const CSrmAutoLocalPtr_Storage<uchar *>::`vftable'
0x1800732ad  mov     [rsp+318h+var_2D0], rax
0x1800732b2  lea     rdi, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x1800732b9  mov     [rsp+318h+var_2D0], rdi
0x1800732be  mov     [rsp+318h+hMem], r15
0x1800732c3  lea     rax, ??_7?$CSrmAutoLocalPtr@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@6B@; const CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable'
0x1800732ca  mov     [rsp+318h+var_2D0], rax
0x1800732cf  mov     rcx, [rsp+318h+hMem]; hMem
0x1800732d4  test    rcx, rcx
0x1800732d7  jz      short loc_1800732DF
0x1800732d9  call    cs:__imp_LocalFree
0x1800732df  mov     [rsp+318h+hMem], r15
0x1800732e4  lea     rax, [rsp+318h+var_A8]
0x1800732ec  mov     [rsp+318h+Arguments], rax; Arguments
0x1800732f1  mov     [rsp+318h+nSize], r12d; nSize
0x1800732f6  lea     rax, [rsp+318h+hMem]
0x1800732fb  mov     [rsp+318h+lpBuffer], rax; lpBuffer
0x180073300  mov     r9d, 400h; dwLanguageId
0x180073306  mov     r8d, 8004203Eh; dwMessageId
0x18007330c  mov     rdx, r14; lpSource
0x18007330f  mov     ecx, 2900h; dwFlags
0x180073314  call    cs:__imp_FormatMessageW
0x18007331a  test    eax, eax
0x18007331c  jz      loc_1800734AA
0x180073322  mov     [rsp+318h+pperrinfo], r15
0x180073327  mov     [rsp+318h+perrinfo], r15
0x18007332c  lea     rcx, [rsp+318h+pperrinfo]; pperrinfo
0x180073331  call    cs:__imp_CreateErrorInfo
0x180073337  mov     [rsp+318h+var_150], eax
0x18007333e  test    eax, eax
0x180073340  js      loc_18007350C
0x180073346  mov     rcx, [rsp+318h+pperrinfo]
0x18007334b  mov     rax, [rcx]
0x18007334e  mov     rdx, [rsp+318h+hMem]
0x180073353  mov     rax, [rax+28h]
0x180073357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007335c  mov     [rsp+318h+var_150], eax
0x180073363  test    eax, eax
0x180073365  js      loc_180073571
0x18007336b  mov     rcx, [rsp+318h+pperrinfo]
0x180073370  mov     rax, [rcx]
0x180073373  lea     rdx, SourceName; "SRMSVC"
0x18007337a  mov     rax, [rax+20h]
0x18007337e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073383  mov     [rsp+318h+var_150], eax
0x18007338a  test    eax, eax
0x18007338c  js      loc_1800735D6
0x180073392  mov     rcx, [rsp+318h+pperrinfo]
0x180073397  mov     rax, [rcx]
0x18007339a  lea     r8, [rsp+318h+perrinfo]
0x18007339f  lea     rdx, IID_IErrorInfo
0x1800733a6  mov     rax, [rax]
0x1800733a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800733ae  mov     [rsp+318h+var_150], eax
0x1800733b5  test    eax, eax
0x1800733b7  js      loc_18007363B
0x1800733bd  mov     rdx, [rsp+318h+perrinfo]; perrinfo
0x1800733c2  xor     ecx, ecx; dwReserved
0x1800733c4  call    cs:__imp_SetErrorInfo
0x1800733ca  mov     [rsp+318h+var_150], eax
0x1800733d1  test    eax, eax
0x1800733d3  js      loc_1800736A0
0x1800733d9  mov     rcx, [rsp+318h+perrinfo]
0x1800733de  test    rcx, rcx
0x1800733e1  jz      short loc_1800733F0
0x1800733e3  mov     rax, [rcx]
0x1800733e6  mov     rax, [rax+10h]
0x1800733ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800733ef  nop
0x1800733f0  mov     rcx, [rsp+318h+pperrinfo]
0x1800733f5  test    rcx, rcx
0x1800733f8  jz      short loc_180073407
0x1800733fa  mov     rax, [rcx]
0x1800733fd  mov     rax, [rax+10h]
0x180073401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073406  nop
0x180073407  mov     [rsp+318h+var_2D0], rdi
0x18007340c  mov     rcx, [rsp+318h+hMem]; hMem
0x180073411  test    rcx, rcx
0x180073414  jz      short loc_18007341C
0x180073416  call    cs:__imp_LocalFree
0x18007341c  mov     [rsp+318h+hMem], r15
0x180073421  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x180073428  mov     [rsp+318h+var_2D0], rax
0x18007342d  mov     rcx, [rsp+318h+hMem]; hMem
0x180073432  test    rcx, rcx
0x180073435  jz      short loc_18007343D
0x180073437  call    cs:__imp_LocalFree
0x18007343d  mov     [rsp+318h+hMem], r15
0x180073442  mov     rcx, [rsp+318h+pv]; pv
0x180073447  call    cs:__imp_CoTaskMemFree
0x18007344d  mov     [rsp+318h+pv], r15
0x180073452  mov     [rsp+318h+pv], r15
0x180073457  jmp     short loc_18007345E
0x180073459  mov     rbx, [rsp+318h+var_2A8]
0x18007345e  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180073465  mov     [rsp+318h+var_158], rax
0x18007346d  lea     rcx, [rsp+318h+var_158]; this
0x180073475  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007347a  nop
0x18007347b  mov     rcx, rbx; this
0x18007347e  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180073483  mov     rcx, [rsp+318h+var_48]
0x18007348b  xor     rcx, rsp; StackCookie
0x18007348e  call    __security_check_cookie
0x180073493  add     rsp, 2E0h
0x18007349a  pop     r15
0x18007349c  pop     r14
0x18007349e  pop     r13
0x1800734a0  pop     r12
0x1800734a2  pop     rdi
0x1800734a3  pop     rsi
0x1800734a4  pop     rbx
0x1800734a5  retn
0x1800734a6  jmp     short loc_180073459
0x1800734a8  jmp     short loc_180073459
0x1800734aa  call    cs:__imp_GetLastError
0x1800734b0  mov     ebx, eax
0x1800734b2  lea     rax, [rsp+318h+var_290]
0x1800734ba  mov     [rsp+318h+perrinfo], rax
0x1800734bf  mov     [rsp+318h+nSize], 11h
0x1800734c7  mov     dword ptr [rsp+318h+lpBuffer], 0A37h
0x1800734cf  mov     r9, rsi
0x1800734d2  lea     r8, aTrctrcc; "TRCTRCC"
0x1800734d9  mov     rdx, r13
0x1800734dc  lea     rcx, [rsp+318h+var_290]
0x1800734e4  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800734e9  nop
0x1800734ea  mov     dword ptr [rsp+318h+lpBuffer], ebx
0x1800734ee  lea     r9, aErrorOnFormatm; "Error on FormatMessage0x%08lx"
0x1800734f5  mov     r8d, 80045316h
0x1800734fb  mov     rdx, rax
0x1800734fe  lea     rcx, [rsp+318h+var_158]
0x180073506  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18007350c  lea     rcx, [rsp+318h+var_158]; this
0x180073514  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180073519  mov     ebx, eax
0x18007351b  lea     rax, [rsp+318h+var_290]
0x180073523  mov     [rsp+318h+var_2A0], rax
0x180073528  mov     [rsp+318h+nSize], 11h
0x180073530  mov     dword ptr [rsp+318h+lpBuffer], 0A41h
0x180073538  mov     r9, rsi
0x18007353b  lea     r8, aTrctrcc; "TRCTRCC"
0x180073542  mov     rdx, r13
0x180073545  lea     rcx, [rsp+318h+var_290]
0x18007354d  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180073552  nop
0x180073553  mov     dword ptr [rsp+318h+lpBuffer], ebx
0x180073557  lea     r9, aCreateerrorinf; "CreateErrorInfo failed, %#x"
0x18007355e  mov     r8d, ebx
0x180073561  mov     rdx, rax
0x180073564  lea     rcx, [rsp+318h+var_158]
0x18007356c  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x180073571  lea     rcx, [rsp+318h+var_158]; this
0x180073579  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007357e  mov     ebx, eax
0x180073580  lea     rax, [rsp+318h+var_290]
0x180073588  mov     [rsp+318h+var_2A0], rax
0x18007358d  mov     [rsp+318h+nSize], 11h
0x180073595  mov     dword ptr [rsp+318h+lpBuffer], 0A46h
0x18007359d  mov     r9, rsi
0x1800735a0  lea     r8, aTrctrcc; "TRCTRCC"
0x1800735a7  mov     rdx, r13
0x1800735aa  lea     rcx, [rsp+318h+var_290]
0x1800735b2  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800735b7  nop
0x1800735b8  mov     dword ptr [rsp+318h+lpBuffer], ebx
0x1800735bc  lea     r9, aSpcreateerrori_0; "spCreateErrorInfo::SetDescription faile"...
0x1800735c3  mov     r8d, ebx
0x1800735c6  mov     rdx, rax
0x1800735c9  lea     rcx, [rsp+318h+var_158]
0x1800735d1  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x1800735d6  lea     rcx, [rsp+318h+var_158]; this
0x1800735de  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800735e3  mov     ebx, eax
0x1800735e5  lea     rax, [rsp+318h+var_290]
0x1800735ed  mov     [rsp+318h+var_2A0], rax
0x1800735f2  mov     [rsp+318h+nSize], 11h
0x1800735fa  mov     dword ptr [rsp+318h+lpBuffer], 0A4Bh
0x180073602  mov     r9, rsi
0x180073605  lea     r8, aTrctrcc; "TRCTRCC"
0x18007360c  mov     rdx, r13
0x18007360f  lea     rcx, [rsp+318h+var_290]
0x180073617  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007361c  nop
0x18007361d  mov     dword ptr [rsp+318h+lpBuffer], ebx
0x180073621  lea     r9, aSpcreateerrori; "spCreateErrorInfo::SetSource failed, %#"...
0x180073628  mov     r8d, ebx
0x18007362b  mov     rdx, rax
0x18007362e  lea     rcx, [rsp+318h+var_158]
0x180073636  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18007363b  lea     rcx, [rsp+318h+var_158]; this
0x180073643  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180073648  mov     ebx, eax
0x18007364a  lea     rax, [rsp+318h+var_290]
0x180073652  mov     [rsp+318h+var_2A0], rax
  ... truncated ...
```
