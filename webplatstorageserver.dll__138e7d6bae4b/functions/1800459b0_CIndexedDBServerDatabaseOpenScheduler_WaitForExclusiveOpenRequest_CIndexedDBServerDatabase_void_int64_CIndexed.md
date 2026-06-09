# CIndexedDBServerDatabaseOpenScheduler::WaitForExclusiveOpenRequest(CIndexedDBServerDatabase *,void *,__int64,CIndexedDBServerOpenRequestQueueEntry * *)

- ea: `0x1800459b0`
- end: `0x180045c26`
- name: `?WaitForExclusiveOpenRequest@CIndexedDBServerDatabaseOpenScheduler@@QEAAJPEAVCIndexedDBServerDatabase@@PEAX_JPEAPEAVCIndexedDBServerOpenRequestQueueEntry@@@Z`
- size: `630`
- prototype: `int(CIndexedDBServerDatabaseOpenScheduler *__hidden this, struct CIndexedDBServerDatabase *, void *, __int64, struct CIndexedDBServerOpenRequestQueueEntry **)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800457c0`

## callees

- `0x18002c9b0`
- `0x18002e340`
- `0x18002eb80`
- `0x18004552c`
- `0x1800456b8`
- `0x1800459b0`
- `0x180045c2c`
- `0x18004604c`
- `0x1800472d0`
- `0x1800473c0`
- `0x1800814bc`
- `0x1800b28a0`
- `0x1800b28e8`
- `0x1800b37e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045a11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045a6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045a11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045a6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045a98`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045a98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045ad2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045b38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045ad2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b70`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CIndexedDBServerDatabaseOpenScheduler::WaitForExclusiveOpenRequest(
        struct _RTL_CRITICAL_SECTION **this,
        struct ICallerIdentity **a2,
        void *a3,
        __int64 a4,
        struct CIndexedDBServerOpenRequestQueueEntry **a5)
{
  struct CIndexedDBServerOpenRequestQueueEntry **v7; // rbx
  CIndexedDBServerOpenRequestQueueEntry *v8; // rsi
  char v9; // r14
  signed int v10; // edi
  struct _RTL_CRITICAL_SECTION *v11; // rbp
  int v12; // r12d
  CIndexedDBServerOpenRequestQueueEntry *v13; // rax
  int v14; // r14d
  HANDLE EventW; // rax
  struct _RTL_CRITICAL_SECTION *v16; // r13
  signed int LastError; // eax
  struct _RTL_CRITICAL_SECTION *v19; // [rsp+20h] [rbp-68h] BYREF
  int v20; // [rsp+28h] [rbp-60h]
  char *v21; // [rsp+30h] [rbp-58h]
  int v22; // [rsp+38h] [rbp-50h]
  char *v23; // [rsp+40h] [rbp-48h]
  int v24; // [rsp+48h] [rbp-40h]

  v7 = a5;
  *a5 = 0;
  v8 = 0;
  v9 = 1;
  v19 = 0;
  v10 = -2147024891;
  v11 = (struct _RTL_CRITICAL_SECTION *)(this + 9);
  v21 = (char *)(this + 9);
  v12 = 0;
  v22 = 0;
  if ( this != (struct _RTL_CRITICAL_SECTION **)-72LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(this + 9));
    v12 = 1;
    v22 = 1;
  }
  if ( *((_BYTE *)this + 112)
    && (v13 = (CIndexedDBServerOpenRequestQueueEntry *)operator new(0x70u),
        v8 = CIndexedDBServerOpenRequestQueueEntry::CIndexedDBServerOpenRequestQueueEntry(v13),
        v10 = v8 == 0 ? 0x8007000E : 0,
        v8) )
  {
    v23 = (char *)v8 + 16;
    v14 = 0;
    v24 = 0;
    if ( v8 != (CIndexedDBServerOpenRequestQueueEntry *)-16LL )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 16));
      v14 = 1;
      v24 = 1;
    }
    CRpcObject::Init(v8, a2[1]);
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)v8 + 13) = EventW;
    if ( EventW )
    {
      v10 = 0;
      *((_QWORD *)v8 + 11) = a2;
      CIndexedDBServerDatabase::IncrementInUseCount((CIndexedDBServerDatabase *)a2);
      *((_QWORD *)v8 + 12) = a4;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 < 0 )
        CIndexedDBServerOpenRequestQueueEntry::Close(v8);
    }
    if ( v14 && v8 != (CIndexedDBServerOpenRequestQueueEntry *)-16LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 16));
    if ( v10 < 0 )
    {
      v9 = 1;
      v16 = v19;
    }
    else
    {
      v9 = CThreadSafeLinkedList<CIndexedDBServerObjectStore,CDoubleLink<CIndexedDBServerObjectStore,&public: static int CIndexedDBServerObjectStore::CIndexedDBServerObjectStore_GetCLink_lnkOffset(void)>>::IsEmpty(this)
         ^ 1;
      CLock::Lock((CLock *)(this + 3));
      _InterlockedIncrement((volatile signed __int32 *)v8 + 16);
      *((_QWORD *)v8 + 9) = this;
      *((_QWORD *)v8 + 10) = this[1];
      this[1] = (struct _RTL_CRITICAL_SECTION *)((char *)v8 + 72);
      **((_QWORD **)v8 + 10) = (char *)v8 + 72;
      CLock::Unlock((CLock *)(this + 3));
      v16 = this[15];
    }
    v7 = a5;
  }
  else
  {
    v16 = v19;
  }
  if ( v12 && v11 )
    LeaveCriticalSection(v11);
  if ( v10 >= 0 )
  {
    if ( v9 && (v10 = CIndexedDBServerOpenRequestQueueEntry::BlockAndWaitForSignal(v8, a3, v16), v10 < 0) )
    {
      v19 = v11;
      v20 = 0;
      AutoCritSec::Lock((AutoCritSec *)&v19);
      CThreadSafeLinkedList<CIndexedDBServerOpenRequestQueueEntry,CDoubleLink<CIndexedDBServerOpenRequestQueueEntry,&public: static int CIndexedDBServerOpenRequestQueueEntry::CIndexedDBServerOpenRequestQueueEntry_GetCLink_lnkOffset(void)>>::RemoveFromList(
        this,
        v8);
      CIndexedDBServerOpenRequestQueueEntry::Close(v8);
      if ( v20 )
        AutoCritSec::Unlock((AutoCritSec *)&v19);
    }
    else
    {
      *v7 = v8;
      _InterlockedIncrement((volatile signed __int32 *)v8 + 16);
    }
  }
  if ( v8 )
    CIndexedDBServerFactoryWithSecurityContext::Release(v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800459b0  mov     rax, rsp
0x1800459b3  mov     [rax+10h], rbx
0x1800459b7  mov     [rax+20h], r9
0x1800459bb  mov     [rax+18h], r8
0x1800459bf  push    rbp
0x1800459c0  push    rsi
0x1800459c1  push    rdi
0x1800459c2  push    r12
0x1800459c4  push    r13
0x1800459c6  push    r14
0x1800459c8  push    r15
0x1800459ca  sub     rsp, 50h
0x1800459ce  mov     r13, rdx
0x1800459d1  mov     r15, rcx
0x1800459d4  mov     rbx, [rsp+88h+arg_20]
0x1800459dc  mov     qword ptr [rbx], 0
0x1800459e3  xor     esi, esi
0x1800459e5  mov     r14b, 1
0x1800459e8  mov     [rsp+88h+arg_0], r14b
0x1800459f0  mov     [rsp+88h+var_68], rsi
0x1800459f5  mov     edi, 80070005h
0x1800459fa  lea     rbp, [rcx+48h]
0x1800459fe  mov     [rax-58h], rbp
0x180045a02  xor     r12d, r12d
0x180045a05  mov     [rax-50h], r12d
0x180045a09  test    rbp, rbp
0x180045a0c  jz      short loc_180045A20
0x180045a0e  mov     rcx, rbp; lpCriticalSection
0x180045a11  call    cs:__imp_EnterCriticalSection
0x180045a17  lea     r12d, [rsi+1]
0x180045a1b  mov     [rsp+88h+var_50], r12d
0x180045a20  cmp     byte ptr [r15+70h], 0
0x180045a25  jz      loc_180045B69
0x180045a2b  mov     ecx, 70h ; 'p'; Size
0x180045a30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045a35  mov     rcx, rax; this
0x180045a38  call    ??0CIndexedDBServerOpenRequestQueueEntry@@AEAA@XZ; CIndexedDBServerOpenRequestQueueEntry::CIndexedDBServerOpenRequestQueueEntry(void)
0x180045a3d  mov     rsi, rax
0x180045a40  neg     rax
0x180045a43  sbb     edi, edi
0x180045a45  not     edi
0x180045a47  and     edi, 8007000Eh
0x180045a4d  test    rsi, rsi
0x180045a50  jz      loc_180045B69
0x180045a56  lea     rbx, [rsi+10h]
0x180045a5a  mov     [rsp+88h+var_48], rbx
0x180045a5f  xor     r14d, r14d
0x180045a62  mov     [rsp+88h+var_40], r14d
0x180045a67  test    rbx, rbx
0x180045a6a  jz      short loc_180045A80
0x180045a6c  mov     rcx, rbx; lpCriticalSection
0x180045a6f  call    cs:__imp_EnterCriticalSection
0x180045a75  mov     r14d, 1
0x180045a7b  mov     [rsp+88h+var_40], r14d
0x180045a80  mov     rdx, [r13+8]; struct ICallerIdentity *
0x180045a84  mov     rcx, rsi; this
0x180045a87  call    ?Init@CRpcObject@@QEAAXPEAUICallerIdentity@@@Z; CRpcObject::Init(ICallerIdentity *)
0x180045a8c  xor     r9d, r9d; lpName
0x180045a8f  xor     r8d, r8d; bInitialState
0x180045a92  lea     edx, [r9+1]; bManualReset
0x180045a96  xor     ecx, ecx; lpEventAttributes
0x180045a98  call    cs:__imp_CreateEventW
0x180045a9e  mov     [rsi+68h], rax
0x180045aa2  test    rax, rax
0x180045aa5  jz      loc_180045B70
0x180045aab  xor     edi, edi
0x180045aad  mov     [rsi+58h], r13
0x180045ab1  mov     rcx, r13; this
0x180045ab4  call    ?IncrementInUseCount@CIndexedDBServerDatabase@@QEAAKXZ; CIndexedDBServerDatabase::IncrementInUseCount(void)
0x180045ab9  mov     rax, [rsp+88h+arg_18]
0x180045ac1  mov     [rsi+60h], rax
0x180045ac5  test    r14d, r14d
0x180045ac8  jz      short loc_180045AD8
0x180045aca  test    rbx, rbx
0x180045acd  jz      short loc_180045AD8
0x180045acf  mov     rcx, rbx; lpCriticalSection
0x180045ad2  call    cs:__imp_LeaveCriticalSection
0x180045ad8  test    edi, edi
0x180045ada  js      loc_180045BDD
0x180045ae0  mov     rcx, r15
0x180045ae3  call    ?IsEmpty@?$CThreadSafeLinkedList@VCIndexedDBServerObjectStore@@V?$CDoubleLink@VCIndexedDBServerObjectStore@@$1?CIndexedDBServerObjectStore_GetCLink_lnkOffset@1@SAHXZ@@@@QEAA_NXZ; CThreadSafeLinkedList<CIndexedDBServerObjectStore,CDoubleLink<CIndexedDBServerObjectStore,&CIndexedDBServerObjectStore::CIndexedDBServerObjectStore_GetCLink_lnkOffset(void)>>::IsEmpty(void)
0x180045ae8  mov     r14b, al
0x180045aeb  xor     r14b, 1
0x180045aef  lea     rcx, [r15+18h]; this
0x180045af3  call    ?Lock@CLock@@QEAAHXZ; CLock::Lock(void)
0x180045af8  lock inc dword ptr [rsi+40h]
0x180045afc  lea     r8, [rsi+48h]
0x180045b00  mov     [r8], r15
0x180045b03  mov     rdx, [r15+8]
0x180045b07  mov     [r8+8], rdx
0x180045b0b  mov     [r15+8], r8
0x180045b0f  mov     rax, [r8+8]
0x180045b13  mov     [rax], r8
0x180045b16  lea     rcx, [r15+18h]; this
0x180045b1a  call    ?Unlock@CLock@@QEAAHXZ; CLock::Unlock(void)
0x180045b1f  mov     r13, [r15+78h]
0x180045b23  mov     rbx, [rsp+88h+arg_20]
0x180045b2b  test    r12d, r12d
0x180045b2e  jz      short loc_180045B3E
0x180045b30  test    rbp, rbp
0x180045b33  jz      short loc_180045B3E
0x180045b35  mov     rcx, rbp; lpCriticalSection
0x180045b38  call    cs:__imp_LeaveCriticalSection
0x180045b3e  test    edi, edi
0x180045b40  jns     loc_180045BEF
0x180045b46  test    rsi, rsi
0x180045b49  jnz     loc_180045C19
0x180045b4f  mov     eax, edi
0x180045b51  mov     rbx, [rsp+88h+arg_8]
0x180045b59  add     rsp, 50h
0x180045b5d  pop     r15
0x180045b5f  pop     r14
0x180045b61  pop     r13
0x180045b63  pop     r12
0x180045b65  pop     rdi
0x180045b66  pop     rsi
0x180045b67  pop     rbp
0x180045b68  retn
0x180045b69  mov     r13, [rsp+88h+var_68]
0x180045b6e  jmp     short loc_180045B2B
0x180045b70  call    cs:__imp_GetLastError
0x180045b76  mov     edi, eax
0x180045b78  test    eax, eax
0x180045b7a  jg      short loc_180045BD2
0x180045b7c  test    edi, edi
0x180045b7e  jns     loc_180045AC5
0x180045b84  mov     rcx, rsi; this
0x180045b87  call    ?Close@CIndexedDBServerOpenRequestQueueEntry@@QEAAXXZ; CIndexedDBServerOpenRequestQueueEntry::Close(void)
0x180045b8c  jmp     loc_180045AC5
0x180045b91  mov     [rsp+88h+var_68], rbp
0x180045b96  mov     [rsp+88h+var_60], 0
0x180045b9e  lea     rcx, [rsp+88h+var_68]; this
0x180045ba3  call    ?Lock@AutoCritSec@@QEAAXXZ; AutoCritSec::Lock(void)
0x180045ba8  mov     rdx, rsi
0x180045bab  mov     rcx, r15
0x180045bae  call    ?RemoveFromList@?$CThreadSafeLinkedList@VCIndexedDBServerOpenRequestQueueEntry@@V?$CDoubleLink@VCIndexedDBServerOpenRequestQueueEntry@@$1?CIndexedDBServerOpenRequestQueueEntry_GetCLink_lnkOffset@1@SAHXZ@@@@QEAAXPEAVCIndexedDBServerOpenRequestQueueEntry@@@Z; CThreadSafeLinkedList<CIndexedDBServerOpenRequestQueueEntry,CDoubleLink<CIndexedDBServerOpenRequestQueueEntry,&CIndexedDBServerOpenRequestQueueEntry::CIndexedDBServerOpenRequestQueueEntry_GetCLink_lnkOffset(void)>>::RemoveFromList(CIndexedDBServerOpenRequestQueueEntry *)
0x180045bb3  mov     rcx, rsi; this
0x180045bb6  call    ?Close@CIndexedDBServerOpenRequestQueueEntry@@QEAAXXZ; CIndexedDBServerOpenRequestQueueEntry::Close(void)
0x180045bbb  nop
0x180045bbc  cmp     [rsp+88h+var_60], 0
0x180045bc1  jz      short loc_180045B46
0x180045bc3  lea     rcx, [rsp+88h+var_68]; this
0x180045bc8  call    ?Unlock@AutoCritSec@@QEAAXXZ; AutoCritSec::Unlock(void)
0x180045bcd  jmp     loc_180045B46
0x180045bd2  movzx   edi, ax
0x180045bd5  or      edi, 80070000h
0x180045bdb  jmp     short loc_180045B7C
0x180045bdd  mov     r14b, [rsp+88h+arg_0]
0x180045be5  mov     r13, [rsp+88h+var_68]
0x180045bea  jmp     loc_180045B23
0x180045bef  test    r14b, r14b
0x180045bf2  jz      short loc_180045C0D
0x180045bf4  mov     r8, r13; void *
0x180045bf7  mov     rdx, [rsp+88h+arg_10]; void *
0x180045bff  mov     rcx, rsi; this
0x180045c02  call    ?BlockAndWaitForSignal@CIndexedDBServerOpenRequestQueueEntry@@QEAAJPEAX0@Z; CIndexedDBServerOpenRequestQueueEntry::BlockAndWaitForSignal(void *,void *)
0x180045c07  mov     edi, eax
0x180045c09  test    eax, eax
0x180045c0b  js      short loc_180045B91
0x180045c0d  mov     [rbx], rsi
0x180045c10  lock inc dword ptr [rsi+40h]
0x180045c14  jmp     loc_180045B46
0x180045c19  mov     rcx, rsi; this
0x180045c1c  call    ?Release@CIndexedDBServerFactoryWithSecurityContext@@QEAAKXZ; CIndexedDBServerFactoryWithSecurityContext::Release(void)
0x180045c21  jmp     loc_180045B4F
```
