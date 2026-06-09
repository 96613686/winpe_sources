# CVdsDiskLun::SetSANMode(int)

- ea: `0x140027e20`
- end: `0x1400280be`
- name: `?SetSANMode@CVdsDiskLun@@UEAAJH@Z`
- size: `670`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x140012c48`
- `0x140027e20`
- `0x14002e123`
- `0x14003ca88`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140028079`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140028079`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140027ebe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140027ebe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027fea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028001`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028018`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002802f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028046`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027fea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028001`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028018`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002802f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028046`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140028063`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140028063`
- `vdsutil!OpenDevice` at `0x140027f47`
- `vdsutil!OpenDevice` at `0x140027f47`
- `vdsutil!VdsTraceEx` at `0x140027ee6`
- `vdsutil!VdsTraceEx` at `0x140027f2e`
- `vdsutil!VdsTraceEx` at `0x140027fcd`
- `vdsutil!VdsTraceEx` at `0x140027ee6`
- `vdsutil!VdsTraceEx` at `0x140027f2e`
- `vdsutil!VdsTraceEx` at `0x140027fcd`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140027e5d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140027e5d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002809a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002809a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVdsDiskLun::SetSANMode(CVdsDiskLun *this, int a2)
{
  int v4; // ebx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  const char *v8; // r8
  int v9; // eax
  __int64 v10; // rax
  __int64 (*v11)(void); // rax
  HANDLE hObject; // [rsp+20h] [rbp-99h] BYREF
  __int64 *v14; // [rsp+28h] [rbp-91h] BYREF
  __int64 v15; // [rsp+30h] [rbp-89h] BYREF
  int v16; // [rsp+38h] [rbp-81h]
  _BYTE v17[16]; // [rsp+40h] [rbp-79h] BYREF
  struct _GUID v18; // [rsp+50h] [rbp-69h] BYREF
  LPVOID v19; // [rsp+A8h] [rbp-11h]
  LPVOID pv; // [rsp+B0h] [rbp-9h]
  LPVOID v21; // [rsp+B8h] [rbp-1h]
  LPVOID v22; // [rsp+C0h] [rbp+7h]
  LPVOID v23; // [rsp+C8h] [rbp+Fh]

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v17, 0x5Eu, "CVdsDiskLun::SetSANMode()");
  hObject = 0;
  v14 = 0;
  memset_0(&v18, 0, 0x80u);
  v15 = 0;
  v16 = 0;
  v4 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v15);
  if ( v4 < 0 )
  {
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v15);
    goto LABEL_33;
  }
  EnterCriticalSection(&g_GlobalCriticalSection);
  v5 = CVdsDiskLun::ValidateDiskInterfaces((CVdsDiskLun *)((char *)this - 8));
  v4 = v5;
  if ( v5 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsDiskLun::SetSANMode, 1, hr=%lX", v5);
    if ( v4 == -2147212283 )
      v4 = -2147212277;
    goto LABEL_30;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 27) + 24LL))(
         *((_QWORD *)this + 27),
         &v18);
  v4 = v6;
  if ( v6 >= 0 )
  {
    v7 = OpenDevice(v23, 3221225472LL, &hObject);
    v4 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      hObject = 0;
      v8 = "CVdsDiskLun::SetSANMode, 3, hr=%lX";
    }
    else
    {
      v9 = (**((__int64 (__fastcall ***)(char *, GUID *, __int64 **))this - 1))(
             (char *)this - 8,
             &IID_IVdsDiskOnline,
             &v14);
      v4 = v9;
      if ( v9 < 0 )
      {
        VdsTraceEx(94, 0, "CVdsDiskLun::SetSANMode, 4, hr=%lX", (unsigned int)v9);
LABEL_20:
        CVdsService::SendDiskNotification(0xAu, &v18);
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v21 )
        {
          CoTaskMemFree(v21);
          v21 = 0;
        }
        if ( v23 )
        {
          CoTaskMemFree(v23);
          v23 = 0;
        }
        if ( v19 )
        {
          CoTaskMemFree(v19);
          v19 = 0;
        }
        if ( v22 )
        {
          CoTaskMemFree(v22);
          v22 = 0;
        }
        goto LABEL_30;
      }
      v10 = *v14;
      if ( a2 )
        v11 = *(__int64 (**)(void))(v10 + 24);
      else
        v11 = *(__int64 (**)(void))(v10 + 32);
      v4 = v11();
      if ( v4 >= 0 )
        goto LABEL_20;
      v8 = "CVdsDiskLun::SetSANMode, 5, hr=%lX";
    }
    VdsTraceEx(94, 0, v8, (unsigned int)v4, hObject);
    goto LABEL_20;
  }
  VdsTraceEx(94, 0, "CVdsDiskLun::SetSANMode, 2, hr=%lX", v6);
LABEL_30:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v15);
LABEL_33:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140027e20  push    rbp
0x140027e22  push    rbx
0x140027e23  push    rsi
0x140027e24  push    rdi
0x140027e25  push    r12
0x140027e27  push    r14
0x140027e29  lea     rbp, [rsp-2Fh]
0x140027e2e  sub     rsp, 0E8h
0x140027e35  mov     rax, cs:__security_cookie
0x140027e3c  xor     rax, rsp
0x140027e3f  mov     [rbp+57h+var_38], rax
0x140027e43  mov     r14d, edx
0x140027e46  mov     rsi, rcx
0x140027e49  lea     r8, aCvdsdisklunSet_7; "CVdsDiskLun::SetSANMode()"
0x140027e50  mov     r12d, 5Eh ; '^'
0x140027e56  mov     edx, r12d
0x140027e59  lea     rcx, [rbp+57h+var_D0]
0x140027e5d  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140027e63  nop
0x140027e64  mov     [rsp+110h+hObject], 0
0x140027e6d  mov     [rsp+110h+var_E8], 0
0x140027e76  xor     edx, edx; Val
0x140027e78  lea     r8d, [r12+22h]; Size
0x140027e7d  lea     rcx, [rbp+57h+var_C0]; void *
0x140027e81  call    memset_0
0x140027e86  mov     [rsp+110h+var_E0], 0
0x140027e8f  mov     [rsp+110h+var_D8], 0
0x140027e97  lea     rcx, [rsp+110h+var_E0]; this
0x140027e9c  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140027ea1  mov     ebx, eax
0x140027ea3  test    eax, eax
0x140027ea5  jns     short loc_140027EB7
0x140027ea7  lea     rcx, [rsp+110h+var_E0]; this
0x140027eac  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140027eb1  nop
0x140027eb2  jmp     loc_14002808B
0x140027eb7  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140027ebe  call    cs:__imp_EnterCriticalSection
0x140027ec4  nop
0x140027ec5  lea     rdi, [rsi-8]
0x140027ec9  mov     rcx, rdi; this
0x140027ecc  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x140027ed1  mov     ebx, eax
0x140027ed3  test    eax, eax
0x140027ed5  jns     short loc_140027F02
0x140027ed7  mov     r9d, eax
0x140027eda  lea     r8, aCvdsdisklunSet_15; "CVdsDiskLun::SetSANMode, 1, hr=%lX"
0x140027ee1  xor     edx, edx
0x140027ee3  mov     ecx, r12d
0x140027ee6  call    cs:__imp_VdsTraceEx
0x140027eec  cmp     ebx, 80042405h
0x140027ef2  jnz     loc_140028054
0x140027ef8  mov     ebx, 8004240Bh
0x140027efd  jmp     loc_140028054
0x140027f02  mov     rcx, [rsi+0D8h]
0x140027f09  mov     rax, [rcx]
0x140027f0c  lea     rdx, [rbp+57h+var_C0]
0x140027f10  mov     rax, [rax+18h]
0x140027f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027f19  mov     ebx, eax
0x140027f1b  test    eax, eax
0x140027f1d  jns     short loc_140027F39
0x140027f1f  mov     r9d, eax
0x140027f22  lea     r8, aCvdsdisklunSet_40; "CVdsDiskLun::SetSANMode, 2, hr=%lX"
0x140027f29  xor     edx, edx
0x140027f2b  mov     ecx, r12d
0x140027f2e  call    cs:__imp_VdsTraceEx
0x140027f34  jmp     loc_140028054
0x140027f39  lea     r8, [rsp+110h+hObject]
0x140027f3e  mov     edx, 0C0000000h
0x140027f43  mov     rcx, [rbp+57h+var_48]
0x140027f47  call    cs:__imp_OpenDevice
0x140027f4d  mov     ebx, eax
0x140027f4f  test    eax, eax
0x140027f51  jz      short loc_140027F70
0x140027f53  jle     short loc_140027F5E
0x140027f55  movzx   ebx, ax
0x140027f58  or      ebx, 80070000h
0x140027f5e  mov     [rsp+110h+hObject], 0
0x140027f67  lea     r8, aCvdsdisklunSet_0; "CVdsDiskLun::SetSANMode, 3, hr=%lX"
0x140027f6e  jmp     short loc_140027FC5
0x140027f70  mov     rax, [rdi]
0x140027f73  lea     r8, [rsp+110h+var_E8]
0x140027f78  lea     rdx, IID_IVdsDiskOnline
0x140027f7f  mov     rcx, rdi
0x140027f82  mov     rax, [rax]
0x140027f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027f8a  mov     ebx, eax
0x140027f8c  test    eax, eax
0x140027f8e  jns     short loc_140027F9C
0x140027f90  mov     r9d, eax
0x140027f93  lea     r8, aCvdsdisklunSet_36; "CVdsDiskLun::SetSANMode, 4, hr=%lX"
0x140027f9a  jmp     short loc_140027FC8
0x140027f9c  mov     rcx, [rsp+110h+var_E8]
0x140027fa1  mov     rax, [rcx]
0x140027fa4  test    r14d, r14d
0x140027fa7  jz      short loc_140027FAF
0x140027fa9  mov     rax, [rax+18h]
0x140027fad  jmp     short loc_140027FB3
0x140027faf  mov     rax, [rax+20h]
0x140027fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027fb8  mov     ebx, eax
0x140027fba  test    eax, eax
0x140027fbc  jns     short loc_140027FD3
0x140027fbe  lea     r8, aCvdsdisklunSet_5; "CVdsDiskLun::SetSANMode, 5, hr=%lX"
0x140027fc5  mov     r9d, ebx
0x140027fc8  xor     edx, edx
0x140027fca  mov     ecx, r12d
0x140027fcd  call    cs:__imp_VdsTraceEx
0x140027fd3  lea     rdx, [rbp+57h+var_C0]; struct _GUID *
0x140027fd7  mov     ecx, 0Ah; unsigned int
0x140027fdc  call    ?SendDiskNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendDiskNotification(ulong,_GUID &)
0x140027fe1  mov     rcx, [rbp+57h+pv]; pv
0x140027fe5  test    rcx, rcx
0x140027fe8  jz      short loc_140027FF8
0x140027fea  call    cs:__imp_CoTaskMemFree
0x140027ff0  mov     [rbp+57h+pv], 0
0x140027ff8  mov     rcx, [rbp+57h+var_58]; pv
0x140027ffc  test    rcx, rcx
0x140027fff  jz      short loc_14002800F
0x140028001  call    cs:__imp_CoTaskMemFree
0x140028007  mov     [rbp+57h+var_58], 0
0x14002800f  mov     rcx, [rbp+57h+var_48]; pv
0x140028013  test    rcx, rcx
0x140028016  jz      short loc_140028026
0x140028018  call    cs:__imp_CoTaskMemFree
0x14002801e  mov     [rbp+57h+var_48], 0
0x140028026  mov     rcx, [rbp+57h+var_68]; pv
0x14002802a  test    rcx, rcx
0x14002802d  jz      short loc_14002803D
0x14002802f  call    cs:__imp_CoTaskMemFree
0x140028035  mov     [rbp+57h+var_68], 0
0x14002803d  mov     rcx, [rbp+57h+var_50]; pv
0x140028041  test    rcx, rcx
0x140028044  jz      short loc_140028054
0x140028046  call    cs:__imp_CoTaskMemFree
0x14002804c  mov     [rbp+57h+var_50], 0
0x140028054  mov     rcx, [rsp+110h+hObject]; hObject
0x140028059  lea     rax, [rcx-1]
0x14002805d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140028061  ja      short loc_140028072
0x140028063  call    cs:__imp_CloseHandle
0x140028069  mov     [rsp+110h+hObject], 0FFFFFFFFFFFFFFFFh
0x140028072  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140028079  call    cs:__imp_LeaveCriticalSection
0x14002807f  nop
0x140028080  lea     rcx, [rsp+110h+var_E0]; this
0x140028085  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14002808a  nop
0x14002808b  lea     rcx, [rsp+110h+var_E8]
0x140028090  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140028095  nop
0x140028096  lea     rcx, [rbp+57h+var_D0]
0x14002809a  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400280a0  mov     eax, ebx
0x1400280a2  mov     rcx, [rbp+57h+var_38]
0x1400280a6  xor     rcx, rsp; StackCookie
0x1400280a9  call    __security_check_cookie
0x1400280ae  add     rsp, 0E8h
0x1400280b5  pop     r14
0x1400280b7  pop     r12
0x1400280b9  pop     rdi
0x1400280ba  pop     rsi
0x1400280bb  pop     rbx
0x1400280bc  pop     rbp
0x1400280bd  retn
```
