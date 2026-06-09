# CVdsDiskLun::CreatePartition(unsigned __int64,unsigned __int64,_CREATE_PARTITION_PARAMETERS *,IVdsAsync * *)

- ea: `0x14001d530`
- end: `0x14001d776`
- name: `?CreatePartition@CVdsDiskLun@@UEAAJ_K0PEAU_CREATE_PARTITION_PARAMETERS@@PEAPEAUIVdsAsync@@@Z`
- size: `582`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this, unsigned __int64, unsigned __int64, struct _CREATE_PARTITION_PARAMETERS *, struct IVdsAsync **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400025b0`
- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x14000f98c`
- `0x140010b04`
- `0x140012c48`
- `0x14001d530`
- `0x140031c50`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d5ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d63a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d6ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d70d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d73e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d5ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d63a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d6ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d70d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d73e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001d5ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001d5ac`
- `vdsutil!VdsTraceEx` at `0x14001d5d1`
- `vdsutil!VdsTraceEx` at `0x14001d696`
- `vdsutil!VdsTraceEx` at `0x14001d6f5`
- `vdsutil!VdsTraceEx` at `0x14001d5d1`
- `vdsutil!VdsTraceEx` at `0x14001d696`
- `vdsutil!VdsTraceEx` at `0x14001d6f5`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001d55e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001d55e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001d75f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001d75f`

## string_xrefs

- `0x14001d54e`: `CVdsDiskLun::CreatePartition()`
- `0x14001d5c5`: `CVdsDiskLun::CreatePartition, 1, hr=%lX`
- `0x14001d68a`: `CVdsDiskLun::CreatePartition, 2, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CVdsDiskLun::CreatePartition(
        CVdsDiskLun *this,
        __int64 a2,
        __int64 a3,
        struct _CREATE_PARTITION_PARAMETERS *a4,
        struct IVdsAsync **a5)
{
  struct IVdsAsync **v9; // r14
  signed int v10; // ebx
  int v11; // eax
  void *Instance; // rax
  struct CVdsAsyncObject *v13; // rbx
  int v14; // eax
  signed int v15; // esi
  int v16; // eax
  signed int v17; // edi
  struct IVdsAsync *v19; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+38h] [rbp-28h] BYREF
  int v21; // [rsp+40h] [rbp-20h]
  _BYTE v22[24]; // [rsp+48h] [rbp-18h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v22, 0x5Eu, "CVdsDiskLun::CreatePartition()");
  v19 = 0;
  v9 = a5;
  *a5 = 0;
  v20 = 0;
  v21 = 0;
  v10 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v20);
  if ( v10 >= 0 )
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    v11 = CVdsDiskLun::ValidateDiskInterfaces((CVdsDiskLun *)((char *)this - 32));
    v10 = v11;
    if ( v11 >= 0 )
    {
      a5 = 0;
      Instance = VdsCreateInstance(VDS_OT_ASYNC);
      ATL::CComPtrBase<CVdsEnumObject>::Attach((__int64 *)&a5, (__int64)Instance);
      v13 = (struct CVdsAsyncObject *)a5;
      if ( a5 )
      {
        *((_DWORD *)a5 + 22) = 10;
        v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, struct _CREATE_PARTITION_PARAMETERS *, struct IVdsAsync **))(**((_QWORD **)this + 26) + 40LL))(
                *((_QWORD *)this + 26),
                a2,
                a3,
                a4,
                &v19);
        v15 = v14;
        if ( v14 >= 0 )
        {
          v16 = ConnectAsyncWrapper(v13, v19, *((struct CVdsService **)this + 23));
          v17 = v16;
          if ( v16 >= 0 )
          {
            a5 = 0;
            *v9 = (struct IVdsAsync *)v13;
            ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&a5);
            LeaveCriticalSection(&g_GlobalCriticalSection);
            CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v20);
            v10 = 0;
          }
          else
          {
            VdsTraceEx(94, 0, "VDS(%X): unexpected failure connecting async wrapper: %X", 33882114, v16);
            ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&a5);
            LeaveCriticalSection(&g_GlobalCriticalSection);
            CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v20);
            v10 = v17;
          }
        }
        else
        {
          VdsTraceEx(94, 0, "CVdsDiskLun::CreatePartition, 2, hr=%lX", v14);
          ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&a5);
          LeaveCriticalSection(&g_GlobalCriticalSection);
          CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v20);
          v10 = v15;
        }
      }
      else
      {
        ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&a5);
        LeaveCriticalSection(&g_GlobalCriticalSection);
        CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v20);
        v10 = -2147024882;
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::CreatePartition, 1, hr=%lX", v11);
      if ( v10 == -2147212283 )
        v10 = -2147212277;
      LeaveCriticalSection(&g_GlobalCriticalSection);
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v20);
    }
  }
  else
  {
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v20);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v22);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14001d530  push    rbp
0x14001d532  push    rbx
0x14001d533  push    rsi
0x14001d534  push    rdi
0x14001d535  push    r12
0x14001d537  push    r14
0x14001d539  push    r15
0x14001d53b  mov     rbp, rsp
0x14001d53e  sub     rsp, 60h
0x14001d542  mov     rsi, r9
0x14001d545  mov     r15, r8
0x14001d548  mov     r12, rdx
0x14001d54b  mov     rdi, rcx
0x14001d54e  lea     r8, aCvdsdisklunCre_0; "CVdsDiskLun::CreatePartition()"
0x14001d555  mov     edx, 5Eh ; '^'
0x14001d55a  lea     rcx, [rbp+var_18]
0x14001d55e  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001d564  nop
0x14001d565  mov     [rbp+var_30], 0
0x14001d56d  mov     r14, [rbp+arg_20]
0x14001d571  mov     qword ptr [r14], 0
0x14001d578  mov     [rbp+var_28], 0
0x14001d580  mov     [rbp+var_20], 0
0x14001d587  lea     rcx, [rbp+var_28]; this
0x14001d58b  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x14001d590  mov     ebx, eax
0x14001d592  test    eax, eax
0x14001d594  jns     short loc_14001D5A5
0x14001d596  lea     rcx, [rbp+var_28]; this
0x14001d59a  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14001d59f  nop
0x14001d5a0  jmp     loc_14001D751
0x14001d5a5  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001d5ac  call    cs:__imp_EnterCriticalSection
0x14001d5b2  nop
0x14001d5b3  lea     rcx, [rdi-20h]; this
0x14001d5b7  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x14001d5bc  mov     ebx, eax
0x14001d5be  test    eax, eax
0x14001d5c0  jns     short loc_14001D602
0x14001d5c2  mov     r9d, eax
0x14001d5c5  lea     r8, aCvdsdisklunCre_3; "CVdsDiskLun::CreatePartition, 1, hr=%lX"
0x14001d5cc  xor     edx, edx
0x14001d5ce  lea     ecx, [rdx+5Eh]
0x14001d5d1  call    cs:__imp_VdsTraceEx
0x14001d5d7  mov     eax, 8004240Bh
0x14001d5dc  cmp     ebx, 80042405h
0x14001d5e2  cmovz   ebx, eax
0x14001d5e5  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001d5ec  call    cs:__imp_LeaveCriticalSection
0x14001d5f2  nop
0x14001d5f3  lea     rcx, [rbp+var_28]; this
0x14001d5f7  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14001d5fc  nop
0x14001d5fd  jmp     loc_14001D751
0x14001d602  mov     [rbp+arg_20], 0
0x14001d60a  mov     ecx, 64h ; 'd'; enum _VDS_OBJECT_TYPE
0x14001d60f  call    ?VdsCreateInstance@@YAPEAXW4_VDS_OBJECT_TYPE@@@Z; VdsCreateInstance(_VDS_OBJECT_TYPE)
0x14001d614  mov     rdx, rax
0x14001d617  lea     rcx, [rbp+arg_20]
0x14001d61b  call    ?Attach@?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAAXPEAVCVdsEnumObject@@@Z; ATL::CComPtrBase<CVdsEnumObject>::Attach(CVdsEnumObject *)
0x14001d620  mov     rbx, [rbp+arg_20]
0x14001d624  test    rbx, rbx
0x14001d627  jnz     short loc_14001D655
0x14001d629  lea     rcx, [rbp+arg_20]
0x14001d62d  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001d632  nop
0x14001d633  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001d63a  call    cs:__imp_LeaveCriticalSection
0x14001d640  nop
0x14001d641  lea     rcx, [rbp+var_28]; this
0x14001d645  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14001d64a  nop
0x14001d64b  mov     ebx, 8007000Eh
0x14001d650  jmp     loc_14001D751
0x14001d655  mov     dword ptr [rbx+58h], 0Ah
0x14001d65c  mov     rcx, [rdi+0D0h]
0x14001d663  mov     rax, [rcx]
0x14001d666  lea     rdx, [rbp+var_30]
0x14001d66a  mov     [rsp+60h+var_40], rdx
0x14001d66f  mov     r9, rsi
0x14001d672  mov     r8, r15
0x14001d675  mov     rdx, r12
0x14001d678  mov     rax, [rax+28h]
0x14001d67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d681  mov     esi, eax
0x14001d683  test    eax, eax
0x14001d685  jns     short loc_14001D6C6
0x14001d687  mov     r9d, eax
0x14001d68a  lea     r8, aCvdsdisklunCre; "CVdsDiskLun::CreatePartition, 2, hr=%lX"
0x14001d691  xor     edx, edx
0x14001d693  lea     ecx, [rdx+5Eh]
0x14001d696  call    cs:__imp_VdsTraceEx
0x14001d69c  nop
0x14001d69d  lea     rcx, [rbp+arg_20]
0x14001d6a1  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001d6a6  nop
0x14001d6a7  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001d6ae  call    cs:__imp_LeaveCriticalSection
0x14001d6b4  nop
0x14001d6b5  lea     rcx, [rbp+var_28]; this
0x14001d6b9  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14001d6be  nop
0x14001d6bf  mov     ebx, esi
0x14001d6c1  jmp     loc_14001D751
0x14001d6c6  mov     r8, [rdi+0B8h]; struct CVdsService *
0x14001d6cd  mov     rdx, [rbp+var_30]; struct IVdsAsync *
0x14001d6d1  mov     rcx, rbx; struct CVdsAsyncObject *
0x14001d6d4  call    ?ConnectAsyncWrapper@@YAJPEAVCVdsAsyncObject@@PEAUIVdsAsync@@PEAVCVdsService@@@Z; ConnectAsyncWrapper(CVdsAsyncObject *,IVdsAsync *,CVdsService *)
0x14001d6d9  mov     edi, eax
0x14001d6db  test    eax, eax
0x14001d6dd  jns     short loc_14001D722
0x14001d6df  mov     dword ptr [rsp+60h+var_40], eax
0x14001d6e3  mov     r9d, 2050002h
0x14001d6e9  lea     r8, aVdsXUnexpected; "VDS(%X): unexpected failure connecting "...
0x14001d6f0  xor     edx, edx
0x14001d6f2  lea     ecx, [rdx+5Eh]
0x14001d6f5  call    cs:__imp_VdsTraceEx
0x14001d6fb  nop
0x14001d6fc  lea     rcx, [rbp+arg_20]
0x14001d700  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001d705  nop
0x14001d706  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001d70d  call    cs:__imp_LeaveCriticalSection
0x14001d713  nop
0x14001d714  lea     rcx, [rbp+var_28]; this
0x14001d718  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14001d71d  nop
0x14001d71e  mov     ebx, edi
0x14001d720  jmp     short loc_14001D751
0x14001d722  mov     [rbp+arg_20], 0
0x14001d72a  mov     [r14], rbx
0x14001d72d  lea     rcx, [rbp+arg_20]
0x14001d731  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14001d736  nop
0x14001d737  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001d73e  call    cs:__imp_LeaveCriticalSection
0x14001d744  nop
0x14001d745  lea     rcx, [rbp+var_28]; this
0x14001d749  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14001d74e  nop
0x14001d74f  xor     ebx, ebx
0x14001d751  lea     rcx, [rbp+var_30]
0x14001d755  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001d75a  nop
0x14001d75b  lea     rcx, [rbp+var_18]
0x14001d75f  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001d765  mov     eax, ebx
0x14001d767  add     rsp, 60h
0x14001d76b  pop     r15
0x14001d76d  pop     r14
0x14001d76f  pop     r12
0x14001d771  pop     rdi
0x14001d772  pop     rsi
0x14001d773  pop     rbx
0x14001d774  pop     rbp
0x14001d775  retn
```
