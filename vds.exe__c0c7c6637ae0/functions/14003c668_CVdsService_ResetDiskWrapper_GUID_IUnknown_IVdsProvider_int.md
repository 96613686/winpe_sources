# CVdsService::ResetDiskWrapper(_GUID &,IUnknown *,IVdsProvider *,int)

- ea: `0x14003c668`
- end: `0x14003c92f`
- name: `?ResetDiskWrapper@CVdsService@@SAJAEAU_GUID@@PEAUIUnknown@@PEAUIVdsProvider@@H@Z`
- size: `711`
- prototype: `static int(struct _GUID *, struct IUnknown *, struct IVdsProvider *, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x140013f50`
- `0x140017250`
- `0x140026c0c`

## callees

- `0x140008410`
- `0x140009610`
- `0x14000d6e0`
- `0x140012c48`
- `0x140035cfc`
- `0x140038858`
- `0x14003c668`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003c6f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003c900`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003c6f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003c900`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003c6c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003c6c2`
- `vdsutil!VdsTraceEx` at `0x14003c6e2`
- `vdsutil!VdsTraceEx` at `0x14003c7ac`
- `vdsutil!VdsTraceEx` at `0x14003c8c6`
- `vdsutil!VdsTraceEx` at `0x14003c6e2`
- `vdsutil!VdsTraceEx` at `0x14003c7ac`
- `vdsutil!VdsTraceEx` at `0x14003c8c6`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003c7ff`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003c7ff`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003c818`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003c818`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003c845`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003c845`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003c8a5`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003c8a5`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003c69d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003c69d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003c917`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003c917`

## string_xrefs

- `0x14003c689`: `CVdsService::ResetDiskWrapper()`
- `0x14003c6d6`: `CVdsService::ResetDiskWrapper: 0: %lX.`
- `0x14003c736`: `CVdsService::ResetDiskWrapper: 1: %lX.`
- `0x14003c79d`: `CVdsService::ResetDiskWrapper: 2: %lX.`
- `0x14003c78e`: `CVdsService::ResetDiskWrapper: 3: %lX.`
- `0x14003c7be`: `CVdsService::ResetDiskWrapper: 4: %lX.`
- `0x14003c7e8`: `CVdsService::ResetDiskWrapper: 5: %lX.`
- `0x14003c8b0`: `CVdsService::ResetDiskWrapper: 6: %lX.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CVdsService::ResetDiskWrapper(
        struct _GUID *a1,
        struct IUnknown *a2,
        struct IVdsProvider *a3,
        int a4)
{
  unsigned int v8; // edi
  int v9; // eax
  int v10; // ebx
  int v11; // eax
  const char *v12; // r8
  int Disk; // eax
  CVdsService *EntryPointer; // rdi
  CVdsDiskLun *WrapperInMap; // r14
  enum _VDS_OBJECT_TYPE v16; // r8d
  struct IUnknown *v18; // [rsp+30h] [rbp-39h] BYREF
  __int64 v19; // [rsp+38h] [rbp-31h] BYREF
  __int128 Buf1; // [rsp+40h] [rbp-29h] BYREF
  struct _GUID Buf2; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v22[16]; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v23[80]; // [rsp+70h] [rbp+7h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v22, 0x5Eu, "CVdsService::ResetDiskWrapper()");
  v19 = 0;
  v18 = 0;
  Buf1 = 0;
  EnterCriticalSection(&g_GlobalCriticalSection);
  if ( !a2 )
  {
    v8 = -2147212216;
    VdsTraceEx(94, 0, "CVdsService::ResetDiskWrapper: 0: %lX.", -2147212216);
    LeaveCriticalSection(&g_GlobalCriticalSection);
    goto LABEL_27;
  }
  ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
  if ( !a3 )
  {
    Buf2 = *a1;
    Disk = CVdsService::GetDisk(&Buf2, &v18);
    v10 = Disk;
    if ( Disk < 0 )
    {
      VdsTraceEx(94, 0, "CVdsService::ResetDiskWrapper: 5: %lX.", (unsigned int)Disk);
      goto LABEL_24;
    }
    goto LABEL_17;
  }
  v9 = ((__int64 (__fastcall *)(struct IVdsProvider *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
         a3,
         &IID_IVdsProviderPrivate,
         &v19);
  v10 = v9;
  if ( v9 >= 0 )
  {
    Buf2 = *a1;
    v11 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, __int64, struct IUnknown **))(*(_QWORD *)v19 + 24LL))(
            v19,
            &Buf2,
            13,
            &v18);
    v10 = v11;
    if ( v11 < 0 )
    {
      if ( v11 == -2147212283 )
      {
        if ( a4 )
        {
          v10 = 1;
          goto LABEL_24;
        }
      }
      else if ( v11 != -2147212277 )
      {
        VdsTraceEx(94, 0, "CVdsService::ResetDiskWrapper: 3: %lX.", (unsigned int)v11);
        goto LABEL_24;
      }
      VdsTraceEx(94, 1, "CVdsService::ResetDiskWrapper: 2: %lX.", v11);
      goto LABEL_24;
    }
    if ( !v18 )
    {
      v12 = "CVdsService::ResetDiskWrapper: 4: %lX.";
LABEL_23:
      v10 = -2147212216;
      VdsTraceEx(94, 0, v12, 2147755080LL);
      goto LABEL_24;
    }
LABEL_17:
    for ( Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstServiceInstances, &Buf2);
          ;
          CRtlListIter::Next((CRtlListIter *)&Buf1) )
    {
      Buf2 = *(struct _GUID *)CRtlList::End(CVdsService::m_lstServiceInstances, v23);
      if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
        break;
      EntryPointer = (CVdsService *)CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
      WrapperInMap = (CVdsDiskLun *)CVdsService::FindWrapperInMap(EntryPointer, a2);
      if ( WrapperInMap )
      {
        ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->AddRef)(v18);
        CVdsDiskLun::SetObjectAndService(WrapperInMap, v18, 0, EntryPointer);
        CVdsService::RemoveObjectFromMap(EntryPointer, a2, v16);
        if ( !(unsigned int)CVdsService::AddObjectToMap(
                              (struct _RTL_CRITICAL_SECTION *)EntryPointer,
                              v18,
                              (struct IUnknown *)WrapperInMap) )
        {
          v12 = "CVdsService::ResetDiskWrapper: 6: %lX.";
          goto LABEL_23;
        }
      }
    }
    goto LABEL_24;
  }
  VdsTraceEx(94, 0, "CVdsService::ResetDiskWrapper: 1: %lX.", (unsigned int)v9);
LABEL_24:
  if ( v18 )
  {
    ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->Release)(v18);
    v18 = 0;
  }
  ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->Release)(a2);
  LeaveCriticalSection(&g_GlobalCriticalSection);
  v8 = v10;
LABEL_27:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v22);
  return v8;
}

```

## disassembly

```asm
0x14003c668  push    rbp
0x14003c66a  push    rbx
0x14003c66b  push    rsi
0x14003c66c  push    rdi
0x14003c66d  push    r12
0x14003c66f  push    r14
0x14003c671  lea     rbp, [rsp-2Fh]
0x14003c676  sub     rsp, 98h
0x14003c67d  mov     r14d, r9d
0x14003c680  mov     rbx, r8
0x14003c683  mov     rsi, rdx
0x14003c686  mov     rdi, rcx
0x14003c689  lea     r8, aCvdsserviceRes_5; "CVdsService::ResetDiskWrapper()"
0x14003c690  mov     r12d, 5Eh ; '^'
0x14003c696  mov     edx, r12d
0x14003c699  lea     rcx, [rbp+57h+var_60]
0x14003c69d  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003c6a3  nop
0x14003c6a4  mov     [rbp+57h+var_88], 0
0x14003c6ac  mov     [rbp+57h+var_90], 0
0x14003c6b4  xorps   xmm0, xmm0
0x14003c6b7  movups  [rbp+57h+Buf1], xmm0
0x14003c6bb  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003c6c2  call    cs:__imp_EnterCriticalSection
0x14003c6c8  nop
0x14003c6c9  test    rsi, rsi
0x14003c6cc  jnz     short loc_14003C6FC
0x14003c6ce  mov     edi, 80042448h
0x14003c6d3  mov     r9d, edi
0x14003c6d6  lea     r8, aCvdsserviceRes_1; "CVdsService::ResetDiskWrapper: 0: %lX."
0x14003c6dd  xor     edx, edx
0x14003c6df  mov     ecx, r12d
0x14003c6e2  call    cs:__imp_VdsTraceEx
0x14003c6e8  nop
0x14003c6e9  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003c6f0  call    cs:__imp_LeaveCriticalSection
0x14003c6f6  nop
0x14003c6f7  jmp     loc_14003C909
0x14003c6fc  mov     rax, [rsi]
0x14003c6ff  mov     rcx, rsi
0x14003c702  mov     rax, [rax+8]
0x14003c706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c70b  test    rbx, rbx
0x14003c70e  jz      loc_14003C7CA
0x14003c714  mov     rax, [rbx]
0x14003c717  lea     r8, [rbp+57h+var_88]
0x14003c71b  lea     rdx, IID_IVdsProviderPrivate
0x14003c722  mov     rcx, rbx
0x14003c725  mov     rax, [rax]
0x14003c728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c72d  mov     ebx, eax
0x14003c72f  test    eax, eax
0x14003c731  jns     short loc_14003C742
0x14003c733  mov     r9d, eax
0x14003c736  lea     r8, aCvdsserviceRes; "CVdsService::ResetDiskWrapper: 1: %lX."
0x14003c73d  jmp     loc_14003C8C1
0x14003c742  mov     rcx, [rbp+57h+var_88]
0x14003c746  movups  xmm0, xmmword ptr [rdi]
0x14003c749  movdqu  [rbp+57h+Buf2], xmm0
0x14003c74e  mov     rax, [rcx]
0x14003c751  lea     r9, [rbp+57h+var_90]
0x14003c755  mov     r8d, 0Dh
0x14003c75b  lea     rdx, [rbp+57h+Buf2]
0x14003c75f  mov     rax, [rax+18h]
0x14003c763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c768  mov     ebx, eax
0x14003c76a  test    eax, eax
0x14003c76c  jns     short loc_14003C7B7
0x14003c76e  cmp     eax, 80042405h
0x14003c773  jnz     short loc_14003C784
0x14003c775  test    r14d, r14d
0x14003c778  jz      short loc_14003C79A
0x14003c77a  mov     ebx, 1
0x14003c77f  jmp     loc_14003C8CC
0x14003c784  cmp     eax, 8004240Bh
0x14003c789  jz      short loc_14003C79A
0x14003c78b  mov     r9d, eax
0x14003c78e  lea     r8, aCvdsserviceRes_3; "CVdsService::ResetDiskWrapper: 3: %lX."
0x14003c795  jmp     loc_14003C8C1
0x14003c79a  mov     r9d, eax
0x14003c79d  lea     r8, aCvdsserviceRes_7; "CVdsService::ResetDiskWrapper: 2: %lX."
0x14003c7a4  mov     edx, 1
0x14003c7a9  mov     ecx, r12d
0x14003c7ac  call    cs:__imp_VdsTraceEx
0x14003c7b2  jmp     loc_14003C8CC
0x14003c7b7  cmp     [rbp+57h+var_90], 0
0x14003c7bc  jnz     short loc_14003C7F4
0x14003c7be  lea     r8, aCvdsserviceRes_4; "CVdsService::ResetDiskWrapper: 4: %lX."
0x14003c7c5  jmp     loc_14003C8B7
0x14003c7ca  movups  xmm0, xmmword ptr [rdi]
0x14003c7cd  movdqu  [rbp+57h+Buf2], xmm0
0x14003c7d2  lea     rdx, [rbp+57h+var_90]; struct IUnknown **
0x14003c7d6  lea     rcx, [rbp+57h+Buf2]; struct _GUID
0x14003c7da  call    ?GetDisk@CVdsService@@SAJU_GUID@@PEAPEAUIUnknown@@@Z; CVdsService::GetDisk(_GUID,IUnknown * *)
0x14003c7df  mov     ebx, eax
0x14003c7e1  test    eax, eax
0x14003c7e3  jns     short loc_14003C7F4
0x14003c7e5  mov     r9d, eax
0x14003c7e8  lea     r8, aCvdsserviceRes_0; "CVdsService::ResetDiskWrapper: 5: %lX."
0x14003c7ef  jmp     loc_14003C8C1
0x14003c7f4  lea     rdx, [rbp+57h+Buf2]
0x14003c7f8  lea     rcx, ?m_lstServiceInstances@CVdsService@@0VCRtlList@@A; CRtlList CVdsService::m_lstServiceInstances
0x14003c7ff  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14003c805  movups  xmm0, xmmword ptr [rax]
0x14003c808  movdqu  [rbp+57h+Buf1], xmm0
0x14003c80d  lea     rdx, [rbp+57h+var_50]
0x14003c811  lea     rcx, ?m_lstServiceInstances@CVdsService@@0VCRtlList@@A; CRtlList CVdsService::m_lstServiceInstances
0x14003c818  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14003c81e  movups  xmm0, xmmword ptr [rax]
0x14003c821  movdqu  [rbp+57h+Buf2], xmm0
0x14003c826  mov     r8d, 10h; Size
0x14003c82c  lea     rdx, [rbp+57h+Buf2]; Buf2
0x14003c830  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14003c834  call    memcmp_0
0x14003c839  test    eax, eax
0x14003c83b  jz      loc_14003C8CC
0x14003c841  lea     rcx, [rbp+57h+Buf1]
0x14003c845  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14003c84b  mov     rdi, rax
0x14003c84e  mov     rdx, rsi; struct IUnknown *
0x14003c851  mov     rcx, rax; this
0x14003c854  call    ?FindWrapperInMap@CVdsService@@QEAAPEAUIUnknown@@PEAU2@@Z; CVdsService::FindWrapperInMap(IUnknown *)
0x14003c859  mov     r14, rax
0x14003c85c  test    rax, rax
0x14003c85f  jz      short loc_14003C8A1
0x14003c861  mov     rcx, [rbp+57h+var_90]
0x14003c865  mov     rax, [rcx]
0x14003c868  mov     rax, [rax+8]
0x14003c86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c871  mov     r9, rdi; struct CVdsService *
0x14003c874  xor     r8d, r8d; struct IUnknown *
0x14003c877  mov     rdx, [rbp+57h+var_90]; struct IUnknown *
0x14003c87b  mov     rcx, r14; this
0x14003c87e  call    ?SetObjectAndService@CVdsDiskLun@@QEAAJPEAUIUnknown@@0PEAVCVdsService@@@Z; CVdsDiskLun::SetObjectAndService(IUnknown *,IUnknown *,CVdsService *)
0x14003c883  mov     rdx, rsi; struct IUnknown *
0x14003c886  mov     rcx, rdi; this
0x14003c889  call    ?RemoveObjectFromMap@CVdsService@@QEAAXPEAUIUnknown@@W4_VDS_OBJECT_TYPE@@@Z; CVdsService::RemoveObjectFromMap(IUnknown *,_VDS_OBJECT_TYPE)
0x14003c88e  mov     r8, r14; struct IUnknown *
0x14003c891  mov     rdx, [rbp+57h+var_90]; struct IUnknown *
0x14003c895  mov     rcx, rdi; this
0x14003c898  call    ?AddObjectToMap@CVdsService@@QEAAHPEAUIUnknown@@0@Z; CVdsService::AddObjectToMap(IUnknown *,IUnknown *)
0x14003c89d  test    eax, eax
0x14003c89f  jz      short loc_14003C8B0
0x14003c8a1  lea     rcx, [rbp+57h+Buf1]
0x14003c8a5  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14003c8ab  jmp     loc_14003C80D
0x14003c8b0  lea     r8, aCvdsserviceRes_2; "CVdsService::ResetDiskWrapper: 6: %lX."
0x14003c8b7  mov     edi, 80042448h
0x14003c8bc  mov     r9d, edi
0x14003c8bf  mov     ebx, edi
0x14003c8c1  xor     edx, edx
0x14003c8c3  mov     ecx, r12d
0x14003c8c6  call    cs:__imp_VdsTraceEx
0x14003c8cc  mov     rcx, [rbp+57h+var_90]
0x14003c8d0  test    rcx, rcx
0x14003c8d3  jz      short loc_14003C8E9
0x14003c8d5  mov     rax, [rcx]
0x14003c8d8  mov     rax, [rax+10h]
0x14003c8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c8e1  mov     [rbp+57h+var_90], 0
0x14003c8e9  mov     rax, [rsi]
0x14003c8ec  mov     rcx, rsi
0x14003c8ef  mov     rax, [rax+10h]
0x14003c8f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c8f8  nop
0x14003c8f9  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003c900  call    cs:__imp_LeaveCriticalSection
0x14003c906  nop
0x14003c907  mov     edi, ebx
0x14003c909  lea     rcx, [rbp+57h+var_88]
0x14003c90d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003c912  nop
0x14003c913  lea     rcx, [rbp+57h+var_60]
0x14003c917  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003c91d  mov     eax, edi
0x14003c91f  add     rsp, 98h
0x14003c926  pop     r14
0x14003c928  pop     r12
0x14003c92a  pop     rdi
0x14003c92b  pop     rsi
0x14003c92c  pop     rbx
0x14003c92d  pop     rbp
0x14003c92e  retn
```
