# CVdsRawDiskLun::Clean(int,int,int,IVdsAsync * *)

- ea: `0x1400132f0`
- end: `0x140013503`
- name: `?Clean@CVdsRawDiskLun@@UEAAJHHHPEAPEAUIVdsAsync@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(CVdsRawDiskLun *this, __int64, __int64, int, struct IVdsAsync **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000f98c`
- `0x140011a60`
- `0x140012c70`
- `0x140013298`
- `0x1400132f0`
- `0x14001350c`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400134e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400134e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140013324`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140013324`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400133bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400133bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001344a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001344a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140013431`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140013431`
- `vdsutil!VdsHeapAlloc` at `0x1400133ce`
- `vdsutil!VdsHeapAlloc` at `0x1400133ce`
- `vdsutil!VdsTraceEx` at `0x140013461`
- `vdsutil!VdsTraceEx` at `0x140013461`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140013316`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140013316`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400134ee`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400134ee`
- `vdsutil!VdsTraceW` at `0x140013384`
- `vdsutil!VdsTraceW` at `0x1400133e5`
- `vdsutil!VdsTraceW` at `0x140013384`
- `vdsutil!VdsTraceW` at `0x1400133e5`

## string_xrefs

- `0x140013455`: `CRawDiskLun::Clean: CreateThread failed: %X`

## pseudocode

```c
__int64 __fastcall CVdsRawDiskLun::Clean(CVdsRawDiskLun *this, __int64 a2, __int64 a3, int a4, struct IVdsAsync **a5)
{
  char *v7; // r14
  signed int LastError; // ebx
  struct IVdsAsync **v9; // rdi
  struct IVdsAsync *v10; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rsi
  HANDLE Thread; // rax
  void *v16; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v17[32]; // [rsp+38h] [rbp-20h] BYREF
  struct IVdsAsync *v18; // [rsp+90h] [rbp+38h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v17, 0x5Eu, "CVdsRawDiskLun::Clean()");
  EnterCriticalSection(&g_GlobalCriticalSection);
  v7 = (char *)this - 32;
  if ( *((_DWORD *)this + 76) == 1 )
  {
    LastError = -2147212277;
    goto LABEL_15;
  }
  if ( *((_DWORD *)this + 77) == 1 )
  {
    LastError = -2147212205;
    goto LABEL_15;
  }
  v9 = a5;
  *a5 = 0;
  v18 = 0;
  ATL::CComObject<CVdsServiceAsyncObject>::CreateInstance(&v18);
  v10 = v18;
  if ( !v18 )
  {
    VdsTraceW(0, L"CVdsRawDiskLun::Clean(), 1");
LABEL_7:
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v18);
    LastError = -2147024882;
    goto LABEL_15;
  }
  ((void (__fastcall *)(struct IVdsAsync *))v18->lpVtbl->AddRef)(v18);
  LODWORD(v10[10].lpVtbl) = 11;
  v16 = 0;
  ProcessHeap = GetProcessHeap();
  v12 = (_QWORD *)VdsHeapAlloc(ProcessHeap, 8, 24);
  v13 = v12;
  if ( !v12 )
  {
    VdsTraceW(0, L"CVdsRawDiskLun::Clean(), 2");
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v16);
    goto LABEL_7;
  }
  *v12 = v7;
  v12[1] = v10;
  ((void (__fastcall *)(struct IVdsAsync *))v10->lpVtbl->AddRef)(v10);
  *((_DWORD *)v13 + 4) = a4;
  Thread = CreateThread(0, 0, CVdsRawDiskLun::CleanDiskThreadEntry, v13, 0, 0);
  CVdsHandleImpl<0>::operator=(&v16, Thread);
  if ( v16 )
  {
    v18 = 0;
    *v9 = v10;
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v16);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v18);
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    VdsTraceEx(94, 0, "CRawDiskLun::Clean: CreateThread failed: %X", LastError);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[1] + 16LL))(v13[1]);
    VdsLogError(0xC2000001, 0, 0, LastError, 0x20D000Au, 0);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v16);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v18);
  }
LABEL_15:
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400132f0  push    rbp
0x1400132f2  push    rbx
0x1400132f3  push    rsi
0x1400132f4  push    rdi
0x1400132f5  push    r14
0x1400132f7  push    r15
0x1400132f9  mov     rbp, rsp
0x1400132fc  sub     rsp, 58h
0x140013300  mov     r15d, r9d
0x140013303  mov     rbx, rcx
0x140013306  lea     r8, aCvdsrawdisklun_15; "CVdsRawDiskLun::Clean()"
0x14001330d  mov     edx, 5Eh ; '^'
0x140013312  lea     rcx, [rbp+var_20]
0x140013316  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001331c  nop
0x14001331d  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140013324  call    cs:__imp_EnterCriticalSection
0x14001332a  nop
0x14001332b  lea     r14, [rbx-20h]
0x14001332f  cmp     dword ptr [r14+150h], 1
0x140013337  jnz     short loc_140013343
0x140013339  mov     ebx, 8004240Bh
0x14001333e  jmp     loc_1400134DC
0x140013343  cmp     dword ptr [rbx+134h], 1
0x14001334a  jnz     short loc_140013356
0x14001334c  mov     ebx, 80042453h
0x140013351  jmp     loc_1400134DC
0x140013356  mov     rdi, [rbp+arg_20]
0x14001335a  mov     qword ptr [rdi], 0
0x140013361  mov     [rbp+arg_0], 0
0x140013369  lea     rcx, [rbp+arg_0]
0x14001336d  call    ?CreateInstance@?$CComObject@VCVdsServiceAsyncObject@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CVdsServiceAsyncObject>::CreateInstance(ATL::CComObject<CVdsServiceAsyncObject> * *)
0x140013372  mov     rbx, [rbp+arg_0]
0x140013376  test    rbx, rbx
0x140013379  jnz     short loc_14001339E
0x14001337b  lea     rdx, aCvdsrawdisklun_17; "CVdsRawDiskLun::Clean(), 1"
0x140013382  xor     ecx, ecx
0x140013384  call    cs:__imp_VdsTraceW
0x14001338a  nop
0x14001338b  lea     rcx, [rbp+arg_0]
0x14001338f  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140013394  mov     ebx, 8007000Eh
0x140013399  jmp     loc_1400134DC
0x14001339e  mov     rax, [rbx]
0x1400133a1  mov     rcx, rbx
0x1400133a4  mov     rax, [rax+8]
0x1400133a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400133ad  mov     dword ptr [rbx+50h], 0Bh
0x1400133b4  mov     [rbp+var_28], 0
0x1400133bc  call    cs:__imp_GetProcessHeap
0x1400133c2  mov     rcx, rax
0x1400133c5  mov     edx, 8
0x1400133ca  lea     r8d, [rdx+10h]
0x1400133ce  call    cs:__imp_VdsHeapAlloc
0x1400133d4  mov     rsi, rax
0x1400133d7  test    rax, rax
0x1400133da  jnz     short loc_1400133F8
0x1400133dc  lea     rdx, aCvdsrawdisklun_88; "CVdsRawDiskLun::Clean(), 2"
0x1400133e3  xor     ecx, ecx
0x1400133e5  call    cs:__imp_VdsTraceW
0x1400133eb  nop
0x1400133ec  lea     rcx, [rbp+var_28]
0x1400133f0  call    ??1?$CVdsHandleImpl@$0A@@@QEAA@XZ; CVdsHandleImpl<0>::~CVdsHandleImpl<0>(void)
0x1400133f5  nop
0x1400133f6  jmp     short loc_14001338B
0x1400133f8  mov     [rax], r14
0x1400133fb  mov     [rax+8], rbx
0x1400133ff  mov     rax, [rbx]
0x140013402  mov     rcx, rbx
0x140013405  mov     rax, [rax+8]
0x140013409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001340e  mov     [rsi+10h], r15d
0x140013412  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x14001341b  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x140013423  mov     r9, rsi; lpParameter
0x140013426  lea     r8, ?CleanDiskThreadEntry@CVdsRawDiskLun@@SAKPEAX@Z; lpStartAddress
0x14001342d  xor     edx, edx; dwStackSize
0x14001342f  xor     ecx, ecx; lpThreadAttributes
0x140013431  call    cs:__imp_CreateThread
0x140013437  mov     rdx, rax
0x14001343a  lea     rcx, [rbp+var_28]
0x14001343e  call    ??4?$CVdsHandleImpl@$0A@@@QEAAPEAXPEAX@Z; CVdsHandleImpl<0>::operator=(void *)
0x140013443  cmp     [rbp+var_28], 0
0x140013448  jnz     short loc_1400134BC
0x14001344a  call    cs:__imp_GetLastError
0x140013450  mov     ebx, eax
0x140013452  mov     r9d, eax
0x140013455  lea     r8, aCrawdisklunCle_4; "CRawDiskLun::Clean: CreateThread failed"...
0x14001345c  xor     edx, edx
0x14001345e  lea     ecx, [rdx+5Eh]
0x140013461  call    cs:__imp_VdsTraceEx
0x140013467  mov     rcx, [rsi+8]
0x14001346b  mov     rax, [rcx]
0x14001346e  mov     rax, [rax+10h]
0x140013472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013477  mov     [rsp+58h+lpThreadId], 0; unsigned __int16 *
0x140013480  mov     [rsp+58h+dwCreationFlags], 20D000Ah; unsigned int
0x140013488  mov     r9d, ebx; unsigned int
0x14001348b  xor     r8d, r8d; void *
0x14001348e  xor     edx, edx; unsigned int
0x140013490  mov     ecx, 0C2000001h; unsigned int
0x140013495  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14001349a  test    ebx, ebx
0x14001349c  jle     short loc_1400134A7
0x14001349e  movzx   ebx, bx
0x1400134a1  or      ebx, 80070000h
0x1400134a7  lea     rcx, [rbp+var_28]
0x1400134ab  call    ??1?$CVdsHandleImpl@$0A@@@QEAA@XZ; CVdsHandleImpl<0>::~CVdsHandleImpl<0>(void)
0x1400134b0  nop
0x1400134b1  lea     rcx, [rbp+arg_0]
0x1400134b5  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x1400134ba  jmp     short loc_1400134DC
0x1400134bc  mov     [rbp+arg_0], 0
0x1400134c4  mov     [rdi], rbx
0x1400134c7  lea     rcx, [rbp+var_28]
0x1400134cb  call    ??1?$CVdsHandleImpl@$0A@@@QEAA@XZ; CVdsHandleImpl<0>::~CVdsHandleImpl<0>(void)
0x1400134d0  nop
0x1400134d1  lea     rcx, [rbp+arg_0]
0x1400134d5  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x1400134da  xor     ebx, ebx
0x1400134dc  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400134e3  call    cs:__imp_LeaveCriticalSection
0x1400134e9  nop
0x1400134ea  lea     rcx, [rbp+var_20]
0x1400134ee  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400134f4  mov     eax, ebx
0x1400134f6  add     rsp, 58h
0x1400134fa  pop     r15
0x1400134fc  pop     r14
0x1400134fe  pop     rdi
0x1400134ff  pop     rsi
0x140013500  pop     rbx
0x140013501  pop     rbp
0x140013502  retn
```
