# CVdsService::Refresh(void)

- ea: `0x14003b4b0`
- end: `0x14003b700`
- name: `?Refresh@CVdsService@@UEAAJXZ`
- size: `592`
- prototype: `__int64 __fastcall(CVdsService *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x14000d0f0`
- `0x140012c48`
- `0x140013298`
- `0x1400171e8`
- `0x14003b4b0`
- `0x14003c150`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003b6cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003b6cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003b527`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003b527`
- `vdsutil!OpenDevice` at `0x14003b57d`
- `vdsutil!OpenDevice` at `0x14003b57d`
- `vdsutil!VdsTraceEx` at `0x14003b644`
- `vdsutil!VdsTraceEx` at `0x14003b644`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003b5ba`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003b5ba`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003b5d8`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003b5d8`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003b60d`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003b60d`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003b6b9`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003b6b9`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003b4d4`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003b4d4`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003b6ec`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003b6ec`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003b589`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003b589`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003b54b`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003b54b`

## string_xrefs

- `0x14003b4c4`: `CVdsService::Refresh()`
- `0x14003b638`: `CVdsService::Refresh: failed to get the private interface from a software provider: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CVdsService::Refresh(CVdsService *this)
{
  int v2; // ebx
  BOOL v3; // edi
  __int64 v4; // rax
  wchar_t *v5; // rsi
  int v6; // ebx
  __int64 (__fastcall ***EntryPointer)(void *, GUID *, __int64 *); // rax
  int v8; // eax
  unsigned int v9; // ebx
  signed int v10; // eax
  __int64 v12; // [rsp+30h] [rbp-49h] BYREF
  __int64 v13; // [rsp+38h] [rbp-41h] BYREF
  int v14; // [rsp+40h] [rbp-39h]
  __int128 Buf1; // [rsp+48h] [rbp-31h] BYREF
  __int128 Buf2; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v17[16]; // [rsp+70h] [rbp-9h] BYREF
  _BYTE v18[16]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v19; // [rsp+90h] [rbp+17h] BYREF
  __int64 v20; // [rsp+98h] [rbp+1Fh]
  __int64 v21; // [rsp+E0h] [rbp+67h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v17, 0x5Eu, "CVdsService::Refresh()");
  v2 = (*(__int64 (__fastcall **)(CVdsService *))(*(_QWORD *)this + 32LL))(this);
  if ( v2 >= 0 )
  {
    v13 = 0;
    v14 = 0;
    v2 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v13);
    if ( v2 >= 0 )
    {
      EnterCriticalSection(&g_GlobalCriticalSection);
      v3 = CVdsService::AssignDisksToProviders(1) != 0;
      CRtlMap::Begin(CVdsService::m_mapUnallocatedDisks, &v19);
      while ( v19 && v20 )
      {
        v4 = *(_QWORD *)(v20 + 48);
        v21 = -1;
        v5 = *(wchar_t **)(v4 + 240);
        v6 = OpenDevice(v5, 0, &v21);
        CRtlMapIter::Next((CRtlMapIter *)&v19);
        if ( v6 == 2 )
          CVdsService::RemoveObsoleteObject(v5);
        CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>((void **)&v21);
      }
      Buf1 = 0;
      for ( Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstSoftwareProviders, &Buf2);
            ;
            CRtlListIter::Next((CRtlListIter *)&Buf1) )
      {
        Buf2 = *(_OWORD *)CRtlList::End(CVdsService::m_lstSoftwareProviders, v18);
        if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
          break;
        v12 = 0;
        EntryPointer = (__int64 (__fastcall ***)(void *, GUID *, __int64 *))CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
        v8 = (**EntryPointer)(EntryPointer, &IID_IVdsSwProviderPrivate, &v12);
        v9 = v8;
        if ( v8 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 56LL))(v12);
          if ( v10 < 0 )
          {
            VdsLogError(0xC2000009, 0, 0, v10, 0x2000021u, 0);
            v3 = 1;
          }
        }
        else
        {
          VdsTraceEx(
            94,
            0,
            "CVdsService::Refresh: failed to get the private interface from a software provider: %X",
            v8);
          VdsLogError(0xC2000009, 0, 0, v9, 0x2000020u, 0);
          v3 = 1;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
      }
      LeaveCriticalSection(&g_GlobalCriticalSection);
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v13);
      v2 = v3;
    }
    else
    {
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v13);
    }
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14003b4b0  push    rbp
0x14003b4b2  push    rbx
0x14003b4b3  push    rsi
0x14003b4b4  push    rdi
0x14003b4b5  lea     rbp, [rsp-3Fh]
0x14003b4ba  sub     rsp, 0B8h
0x14003b4c1  mov     rbx, rcx
0x14003b4c4  lea     r8, aCvdsserviceRef; "CVdsService::Refresh()"
0x14003b4cb  mov     edx, 5Eh ; '^'
0x14003b4d0  lea     rcx, [rbp+57h+var_60]
0x14003b4d4  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003b4da  nop
0x14003b4db  mov     rax, [rbx]
0x14003b4de  mov     rcx, rbx
0x14003b4e1  mov     rax, [rax+20h]
0x14003b4e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b4ea  mov     ebx, eax
0x14003b4ec  test    eax, eax
0x14003b4ee  js      loc_14003B6E8
0x14003b4f4  mov     [rbp+57h+var_98], 0
0x14003b4fc  mov     [rbp+57h+var_90], 0
0x14003b503  lea     rcx, [rbp+57h+var_98]; this
0x14003b507  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x14003b50c  mov     ebx, eax
0x14003b50e  test    eax, eax
0x14003b510  jns     short loc_14003B520
0x14003b512  lea     rcx, [rbp+57h+var_98]; this
0x14003b516  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14003b51b  jmp     loc_14003B6E8
0x14003b520  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b527  call    cs:__imp_EnterCriticalSection
0x14003b52d  nop
0x14003b52e  mov     ecx, 1; int
0x14003b533  call    ?AssignDisksToProviders@CVdsService@@CAKH@Z; CVdsService::AssignDisksToProviders(int)
0x14003b538  xor     edi, edi
0x14003b53a  test    eax, eax
0x14003b53c  setnz   dil
0x14003b540  lea     rdx, [rbp+57h+var_40]
0x14003b544  lea     rcx, ?m_mapUnallocatedDisks@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisks
0x14003b54b  call    cs:__imp_?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ; CRtlMap::Begin(void)
0x14003b551  cmp     [rbp+57h+var_40], 0
0x14003b556  jz      short loc_14003B5A8
0x14003b558  mov     rax, [rbp+57h+var_38]
0x14003b55c  test    rax, rax
0x14003b55f  jz      short loc_14003B5A8
0x14003b561  mov     rax, [rax+30h]
0x14003b565  mov     [rbp+57h+arg_0], 0FFFFFFFFFFFFFFFFh
0x14003b56d  mov     rsi, [rax+0F0h]
0x14003b574  lea     r8, [rbp+57h+arg_0]
0x14003b578  xor     edx, edx
0x14003b57a  mov     rcx, rsi
0x14003b57d  call    cs:__imp_OpenDevice
0x14003b583  mov     ebx, eax
0x14003b585  lea     rcx, [rbp+57h+var_40]
0x14003b589  call    cs:__imp_?Next@CRtlMapIter@@QEAAAEAV1@XZ; CRtlMapIter::Next(void)
0x14003b58f  cmp     ebx, 2
0x14003b592  jnz     short loc_14003B59D
0x14003b594  mov     rcx, rsi; String1
0x14003b597  call    ?RemoveObsoleteObject@CVdsService@@SAXPEAG@Z; CVdsService::RemoveObsoleteObject(ushort *)
0x14003b59c  nop
0x14003b59d  lea     rcx, [rbp+57h+arg_0]
0x14003b5a1  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x14003b5a6  jmp     short loc_14003B551
0x14003b5a8  xorps   xmm0, xmm0
0x14003b5ab  movups  [rbp+57h+Buf1], xmm0
0x14003b5af  lea     rdx, [rbp+57h+Buf2]
0x14003b5b3  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x14003b5ba  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14003b5c0  movups  xmm0, xmmword ptr [rax]
0x14003b5c3  movdqu  [rbp+57h+Buf1], xmm0
0x14003b5c8  mov     esi, 0C2000009h
0x14003b5cd  lea     rdx, [rbp+57h+var_50]
0x14003b5d1  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x14003b5d8  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14003b5de  movups  xmm0, xmmword ptr [rax]
0x14003b5e1  movdqu  [rbp+57h+Buf2], xmm0
0x14003b5e6  mov     r8d, 10h; Size
0x14003b5ec  lea     rdx, [rbp+57h+Buf2]; Buf2
0x14003b5f0  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14003b5f4  call    memcmp_0
0x14003b5f9  test    eax, eax
0x14003b5fb  jz      loc_14003B6C4
0x14003b601  mov     [rbp+57h+var_A0], 0
0x14003b609  lea     rcx, [rbp+57h+Buf1]
0x14003b60d  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14003b613  mov     r9, rax
0x14003b616  mov     rcx, [rax]
0x14003b619  mov     rax, [rcx]
0x14003b61c  lea     r8, [rbp+57h+var_A0]
0x14003b620  lea     rdx, IID_IVdsSwProviderPrivate
0x14003b627  mov     rcx, r9
0x14003b62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b62f  mov     ebx, eax
0x14003b631  test    eax, eax
0x14003b633  jns     short loc_14003B671
0x14003b635  mov     r9d, eax
0x14003b638  lea     r8, aCvdsserviceRef_0; "CVdsService::Refresh: failed to get the"...
0x14003b63f  xor     edx, edx
0x14003b641  lea     ecx, [rdx+5Eh]
0x14003b644  call    cs:__imp_VdsTraceEx
0x14003b64a  mov     [rsp+0D0h+var_A8], 0; unsigned __int16 *
0x14003b653  mov     [rsp+0D0h+var_B0], 2000020h; unsigned int
0x14003b65b  mov     r9d, ebx; unsigned int
0x14003b65e  xor     r8d, r8d; void *
0x14003b661  xor     edx, edx; unsigned int
0x14003b663  mov     ecx, esi; unsigned int
0x14003b665  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14003b66a  mov     edi, 1
0x14003b66f  jmp     short loc_14003B6AC
0x14003b671  mov     rcx, [rbp+57h+var_A0]
0x14003b675  mov     rax, [rcx]
0x14003b678  mov     rax, [rax+38h]
0x14003b67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b681  test    eax, eax
0x14003b683  jns     short loc_14003B6AC
0x14003b685  mov     [rsp+0D0h+var_A8], 0; unsigned __int16 *
0x14003b68e  mov     [rsp+0D0h+var_B0], 2000021h; unsigned int
0x14003b696  mov     r9d, eax; unsigned int
0x14003b699  xor     r8d, r8d; void *
0x14003b69c  xor     edx, edx; unsigned int
0x14003b69e  mov     ecx, esi; unsigned int
0x14003b6a0  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14003b6a5  mov     edi, 1
0x14003b6aa  jmp     short $+2
0x14003b6ac  lea     rcx, [rbp+57h+var_A0]
0x14003b6b0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003b6b5  lea     rcx, [rbp+57h+Buf1]
0x14003b6b9  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14003b6bf  jmp     loc_14003B5CD
0x14003b6c4  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b6cb  call    cs:__imp_LeaveCriticalSection
0x14003b6d1  nop
0x14003b6d2  lea     rcx, [rbp+57h+var_98]; this
0x14003b6d6  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14003b6db  test    edi, edi
0x14003b6dd  jz      short loc_14003B6E6
0x14003b6df  mov     ebx, 1
0x14003b6e4  jmp     short loc_14003B6E8
0x14003b6e6  xor     ebx, ebx
0x14003b6e8  lea     rcx, [rbp+57h+var_60]
0x14003b6ec  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003b6f2  mov     eax, ebx
0x14003b6f4  add     rsp, 0B8h
0x14003b6fb  pop     rdi
0x14003b6fc  pop     rsi
0x14003b6fd  pop     rbx
0x14003b6fe  pop     rbp
0x14003b6ff  retn
```
