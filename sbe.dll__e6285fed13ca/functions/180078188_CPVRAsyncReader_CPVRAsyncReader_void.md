# CPVRAsyncReader::~CPVRAsyncReader(void)

- ea: `0x180078188`
- end: `0x180078355`
- name: `??1CPVRAsyncReader@@QEAA@XZ`
- size: `461`
- prototype: `void __fastcall(CPVRAsyncReader *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1800785c8`

## callees

- `0x18000c1c4`
- `0x180016a74`
- `0x180067980`
- `0x18006874c`
- `0x180077ff4`
- `0x180078078`
- `0x180078188`
- `0x180078714`
- `0x180078754`
- `0x180079b34`
- `0x180079b7c`
- `0x18007b34c`
- `0x18007b448`
- `0x18007b5a0`
- `0x18007b670`
- `0x18007c130`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x1800782df`
- `KERNEL32!VirtualFree` at `0x1800782df`
- `KERNEL32!CloseHandle` at `0x1800782f2`
- `KERNEL32!CloseHandle` at `0x1800782f2`
- `KERNEL32!DeleteCriticalSection` at `0x180078315`
- `KERNEL32!DeleteCriticalSection` at `0x180078315`
- `KERNEL32!LeaveCriticalSection` at `0x180078224`
- `KERNEL32!LeaveCriticalSection` at `0x180078224`
- `KERNEL32!EnterCriticalSection` at `0x1800781ed`
- `KERNEL32!EnterCriticalSection` at `0x1800781ed`

## pseudocode

```c
void __fastcall CPVRAsyncReader::~CPVRAsyncReader(CPVRAsyncReader *this, unsigned int a2)
{
  PVR_READ_BUFFER *v3; // r14
  COutstandingOps *v4; // rcx
  struct CWait **v5; // rbx
  unsigned int v6; // edx
  CWait *v7; // r8
  _QWORD *v8; // rbx
  __int64 v9; // rcx
  _QWORD *v10; // r9
  __int64 v11; // r9
  int v12; // ebp
  struct PVR_READ_BUFFER *v13; // rax
  CPVRAsyncReader *v14; // rcx
  char *v15; // rsi
  CPVRAsyncReader *v16; // rcx
  struct PVR_READ_BUFFER *v17; // rax
  COutstandingOps *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx

  *(_QWORD *)this = &CPVRAsyncReader::`vftable';
  v3 = 0;
  v4 = (COutstandingOps *)*((_QWORD *)this + 360);
  if ( v4 )
    COutstandingOps::WaitAllCompleted(v4, a2);
  v5 = (struct CWait **)((char *)this + 24);
  while ( *v5 != (struct CWait *)v5 )
  {
    CWait::ListRemove(*v5);
    if ( v7 )
      CWait::`scalar deleting destructor'(v7, v6);
  }
  v8 = (_QWORD *)((char *)this + 2656);
  while ( (_QWORD *)*v8 != v8 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2672));
    v10 = (_QWORD *)*v8;
    if ( (_QWORD *)*v8 == v8 )
    {
      v12 = 25;
    }
    else
    {
      v3 = (PVR_READ_BUFFER *)*(v10 - 2);
      TGenericMap<PVR_READ_BUFFER *,unsigned __int64,0,50,151>::HashListsPop_(v9, v10 - 3);
      TStructPool<TGenericMap<PVR_READ_BUFFER *,unsigned __int64,0,50,151>::TABLE_ENTRY,50>::Recycle(
        (char *)this + 144,
        v11 - 24);
      v12 = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2672));
    if ( v12 )
      break;
    PVR_READ_BUFFER::AddRef(v3);
    PVR_READ_BUFFER::Release(v3);
  }
  v13 = CPVRAsyncReader::HeadPop_(v4, (struct _LIST_ENTRY *)((char *)this + 2888));
  if ( v13 )
  {
    do
    {
      v15 = (char *)this + 40;
      TStructPool<PVR_READ_BUFFER,50>::Recycle((char *)this + 40, v13);
      v13 = CPVRAsyncReader::HeadPop_(v16, (struct _LIST_ENTRY *)((char *)this + 2888));
    }
    while ( v13 );
  }
  else
  {
    v15 = (char *)this + 40;
  }
  while ( 1 )
  {
    v17 = CPVRAsyncReader::HeadPop_(v14, (struct _LIST_ENTRY *)((char *)this + 2904));
    if ( !v17 )
      break;
    TStructPool<PVR_READ_BUFFER,50>::Recycle(v15, v17);
  }
  v18 = (COutstandingOps *)*((_QWORD *)this + 360);
  if ( v18 )
  {
    COutstandingOps::Release(v18);
    *((_QWORD *)this + 360) = 0;
  }
  CAsyncIo::Release(*((CAsyncIo **)this + 348));
  CPVRIOCounters::Release(*((CPVRIOCounters **)this + 359));
  v19 = (void *)*((_QWORD *)this + 339);
  if ( v19 )
    VirtualFree(v19, 0, 0x8000u);
  v20 = (void *)*((_QWORD *)this + 356);
  if ( v20 != (void *)-1LL )
    CloseHandle(v20);
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 342) + 8LL))((char *)this + 2736);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 2808));
  *((_QWORD *)this + 342) = &CPVRWriteBufferStream::`vftable';
  CPVRWriteBufferStream::Uninitialize((CPVRAsyncReader *)((char *)this + 2736));
  *((_QWORD *)this + 17) = &CPVRReadCache<151>::`vftable';
  TGenericMap<PVR_READ_BUFFER *,unsigned __int64,0,50,151>::~TGenericMap<PVR_READ_BUFFER *,unsigned __int64,0,50,151>();
  TStructPool<PVR_READ_BUFFER,50>::~TStructPool<PVR_READ_BUFFER,50>(v15);
}

```

## disassembly

```asm
0x180078188  push    rbx
0x18007818a  push    rbp
0x18007818b  push    rsi
0x18007818c  push    rdi
0x18007818d  push    r14
0x18007818f  sub     rsp, 20h
0x180078193  lea     rax, ??_7CPVRAsyncReader@@6B@; const CPVRAsyncReader::`vftable'
0x18007819a  mov     rdi, rcx
0x18007819d  mov     [rcx], rax
0x1800781a0  xor     r14d, r14d
0x1800781a3  mov     rcx, [rcx+0B40h]; this
0x1800781aa  test    rcx, rcx
0x1800781ad  jz      short loc_1800781B4
0x1800781af  call    ?WaitAllCompleted@COutstandingOps@@QEAAKK@Z; COutstandingOps::WaitAllCompleted(ulong)
0x1800781b4  lea     rbx, [rdi+18h]
0x1800781b8  mov     r8, [rbx]
0x1800781bb  cmp     r8, rbx
0x1800781be  jz      short loc_1800781D7
0x1800781c0  mov     rcx, r8; struct CWait *
0x1800781c3  call    ?ListRemove@CWait@@SAXPEAV1@@Z; CWait::ListRemove(CWait *)
0x1800781c8  test    r8, r8
0x1800781cb  jz      short loc_1800781B8
0x1800781cd  mov     rcx, r8; this
0x1800781d0  call    ??_GCWait@@QEAAPEAXI@Z; CWait::`scalar deleting destructor'(uint)
0x1800781d5  jmp     short loc_1800781B8
0x1800781d7  lea     rbx, [rdi+0A60h]
0x1800781de  cmp     [rbx], rbx
0x1800781e1  jz      short loc_180078240
0x1800781e3  lea     rsi, [rdi+0A70h]
0x1800781ea  mov     rcx, rsi; lpCriticalSection
0x1800781ed  call    cs:__imp_EnterCriticalSection
0x1800781f3  mov     r9, [rbx]
0x1800781f6  cmp     r9, rbx
0x1800781f9  jz      short loc_18007821C
0x1800781fb  mov     r14, [r9-10h]
0x1800781ff  lea     rdx, [r9-18h]
0x180078203  call    ?HashListsPop_@?$TGenericMap@PEAUPVR_READ_BUFFER@@_K$0A@$0DC@$0JH@@@AEAAXPEAUTABLE_ENTRY@1@@Z; TGenericMap<PVR_READ_BUFFER *,unsigned __int64,0,50,151>::HashListsPop_(TGenericMap<PVR_READ_BUFFER *,unsigned __int64,0,50,151>::TABLE_ENTRY *)
0x180078208  lea     rcx, [rdi+90h]
0x18007820f  lea     rdx, [r9-18h]
0x180078213  call    ?Recycle@?$TStructPool@UTABLE_ENTRY@?$TGenericMap@PEAUPVR_READ_BUFFER@@_K$0A@$0DC@$0JH@@@$0DC@@@QEAAXPEAUTABLE_ENTRY@?$TGenericMap@PEAUPVR_READ_BUFFER@@_K$0A@$0DC@$0JH@@@@Z; TStructPool<TGenericMap<PVR_READ_BUFFER *,unsigned __int64,0,50,151>::TABLE_ENTRY,50>::Recycle(TGenericMap<PVR_READ_BUFFER *,unsigned __int64,0,50,151>::TABLE_ENTRY *)
0x180078218  xor     ebp, ebp
0x18007821a  jmp     short loc_180078221
0x18007821c  mov     ebp, 19h
0x180078221  mov     rcx, rsi; lpCriticalSection
0x180078224  call    cs:__imp_LeaveCriticalSection
0x18007822a  test    ebp, ebp
0x18007822c  jnz     short loc_180078240
0x18007822e  mov     rcx, r14; this
0x180078231  call    ?AddRef@PVR_READ_BUFFER@@QEAAJXZ; PVR_READ_BUFFER::AddRef(void)
0x180078236  mov     rcx, r14; this
0x180078239  call    ?Release@PVR_READ_BUFFER@@QEAAJXZ; PVR_READ_BUFFER::Release(void)
0x18007823e  jmp     short loc_1800781DE
0x180078240  lea     rbx, [rdi+0B48h]
0x180078247  mov     rdx, rbx; struct _LIST_ENTRY *
0x18007824a  call    ?HeadPop_@CPVRAsyncReader@@AEAAPEAUPVR_READ_BUFFER@@PEAU_LIST_ENTRY@@@Z; CPVRAsyncReader::HeadPop_(_LIST_ENTRY *)
0x18007824f  test    rax, rax
0x180078252  jz      short loc_180078272
0x180078254  lea     rsi, [rdi+28h]
0x180078258  mov     rdx, rax
0x18007825b  mov     rcx, rsi
0x18007825e  call    ?Recycle@?$TStructPool@UPVR_READ_BUFFER@@$0DC@@@QEAAXPEAUPVR_READ_BUFFER@@@Z; TStructPool<PVR_READ_BUFFER,50>::Recycle(PVR_READ_BUFFER *)
0x180078263  mov     rdx, rbx; struct _LIST_ENTRY *
0x180078266  call    ?HeadPop_@CPVRAsyncReader@@AEAAPEAUPVR_READ_BUFFER@@PEAU_LIST_ENTRY@@@Z; CPVRAsyncReader::HeadPop_(_LIST_ENTRY *)
0x18007826b  test    rax, rax
0x18007826e  jnz     short loc_180078254
0x180078270  jmp     short loc_180078276
0x180078272  lea     rsi, [rdi+28h]
0x180078276  lea     rbx, [rdi+0B58h]
0x18007827d  jmp     short loc_18007828A
0x18007827f  mov     rdx, rax
0x180078282  mov     rcx, rsi
0x180078285  call    ?Recycle@?$TStructPool@UPVR_READ_BUFFER@@$0DC@@@QEAAXPEAUPVR_READ_BUFFER@@@Z; TStructPool<PVR_READ_BUFFER,50>::Recycle(PVR_READ_BUFFER *)
0x18007828a  mov     rdx, rbx; struct _LIST_ENTRY *
0x18007828d  call    ?HeadPop_@CPVRAsyncReader@@AEAAPEAUPVR_READ_BUFFER@@PEAU_LIST_ENTRY@@@Z; CPVRAsyncReader::HeadPop_(_LIST_ENTRY *)
0x180078292  test    rax, rax
0x180078295  jnz     short loc_18007827F
0x180078297  mov     rcx, [rdi+0B40h]; this
0x18007829e  test    rcx, rcx
0x1800782a1  jz      short loc_1800782B3
0x1800782a3  call    ?Release@COutstandingOps@@QEAAJXZ; COutstandingOps::Release(void)
0x1800782a8  mov     qword ptr [rdi+0B40h], 0
0x1800782b3  mov     rcx, [rdi+0AE0h]; this
0x1800782ba  call    ?Release@CAsyncIo@@QEAAJXZ; CAsyncIo::Release(void)
0x1800782bf  mov     rcx, [rdi+0B38h]; this
0x1800782c6  call    ?Release@CPVRIOCounters@@QEAAJXZ; CPVRIOCounters::Release(void)
0x1800782cb  mov     rcx, [rdi+0A98h]; lpAddress
0x1800782d2  test    rcx, rcx
0x1800782d5  jz      short loc_1800782E5
0x1800782d7  xor     edx, edx; dwSize
0x1800782d9  mov     r8d, 8000h; dwFreeType
0x1800782df  call    cs:__imp_VirtualFree
0x1800782e5  mov     rcx, [rdi+0B20h]; hObject
0x1800782ec  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800782f0  jz      short loc_1800782F8
0x1800782f2  call    cs:__imp_CloseHandle
0x1800782f8  lea     rbx, [rdi+0AB0h]
0x1800782ff  mov     rax, [rbx]
0x180078302  mov     rcx, rbx
0x180078305  mov     rax, [rax+8]
0x180078309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007830e  lea     rcx, [rdi+0AF8h]; lpCriticalSection
0x180078315  call    cs:__imp_DeleteCriticalSection
0x18007831b  lea     rax, ??_7CPVRWriteBufferStream@@6B@; const CPVRWriteBufferStream::`vftable'
0x180078322  mov     rcx, rbx; this
0x180078325  mov     [rbx], rax
0x180078328  call    ?Uninitialize@CPVRWriteBufferStream@@UEAAXXZ; CPVRWriteBufferStream::Uninitialize(void)
0x18007832d  lea     rcx, [rdi+88h]
0x180078334  lea     rax, ??_7?$CPVRReadCache@$0JH@@@6B@; const CPVRReadCache<151>::`vftable'
0x18007833b  mov     [rcx], rax
0x18007833e  call    ??1?$TGenericMap@PEAUPVR_READ_BUFFER@@_K$0A@$0DC@$0JH@@@UEAA@XZ; TGenericMap<PVR_READ_BUFFER *,unsigned __int64,0,50,151>::~TGenericMap<PVR_READ_BUFFER *,unsigned __int64,0,50,151>(void)
0x180078343  mov     rcx, rsi
0x180078346  add     rsp, 20h
0x18007834a  pop     r14
0x18007834c  pop     rdi
0x18007834d  pop     rsi
0x18007834e  pop     rbp
0x18007834f  pop     rbx
0x180078350  jmp     ??1?$TStructPool@UPVR_READ_BUFFER@@$0DC@@@QEAA@XZ; TStructPool<PVR_READ_BUFFER,50>::~TStructPool<PVR_READ_BUFFER,50>(void)
```
