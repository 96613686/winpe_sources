# CDbOperationManager::CheckForFatalInstanceError(long)

- ea: `0x1800e8adc`
- end: `0x1800e8dc0`
- name: `?CheckForFatalInstanceError@CDbOperationManager@@AEAAXJ@Z`
- size: `740`
- prototype: `void __fastcall(CDbOperationManager *__hidden this, int)`
- caller_count: `8`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x1800d8710`
- `0x1800d8800`
- `0x1800d8940`
- `0x1800d8ac0`
- `0x1800e85f4`
- `0x1800e90e8`
- `0x1800eaad0`
- `0x1800ead0c`

## callees

- `0x18002dad0`
- `0x1800d8a68`
- `0x1800e7fe4`
- `0x1800e8120`
- `0x1800e82cc`
- `0x1800e8410`
- `0x1800e8adc`
- `0x1800ea298`
- `0x1800ea580`
- `0x1800ea9d4`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e8b28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e8b31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e8d91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e8b28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e8b31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e8d91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8b5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8b6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8c99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8ca7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8d9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8b5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8b6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8c99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8ca7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8d9c`
- `ESENT!JetStopServiceInstance` at `0x1800e8d4c`
- `ESENT!JetStopServiceInstance` at `0x1800e8d4c`

## pseudocode

```c
void __fastcall CDbOperationManager::CheckForFatalInstanceError(struct _RTL_CRITICAL_SECTION *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  __int64 **v5; // r10
  HANDLE OwningThread; // rax
  __int64 v7; // r10
  __int64 v8; // rcx
  HANDLE *p_OwningThread; // rsi
  __int64 v10; // r10
  __int64 v11; // r10
  __int64 v12; // rax
  __int64 v13; // rdx
  ULONG_PTR SpinCount; // rcx
  __int64 i; // rcx
  CDbTransactionContext *v16; // rdi
  JET_INSTANCE v17; // rcx
  JET_ERR v18; // eax
  _BYTE v19[16]; // [rsp+30h] [rbp-40h] BYREF
  __int64 DebugInfo; // [rsp+40h] [rbp-30h] BYREF
  __int128 v21; // [rsp+48h] [rbp-28h]
  _BYTE v22[16]; // [rsp+58h] [rbp-18h] BYREF
  int v23; // [rsp+68h] [rbp-8h]
  int v24; // [rsp+A0h] [rbp+30h] BYREF

  v24 = 0;
  if ( (unsigned int)CDbOperationManager::IsFatalJetError((CDbOperationManager *)this, a2, &v24) )
  {
    v4 = lpCriticalSection;
    DebugInfo = 176;
    v21 = 0;
    EnterCriticalSection(lpCriticalSection);
    EnterCriticalSection(this);
    if ( HIDWORD(this[1].DebugInfo) )
    {
LABEL_7:
      LeaveCriticalSection(this);
      if ( v4 )
        LeaveCriticalSection(v4);
      return;
    }
    if ( this[1].LockCount )
    {
      if ( v24 && !LODWORD(this[1].DebugInfo) )
      {
        LODWORD(this[1].DebugInfo) = 1;
        this[1].RecursionCount = a2;
      }
      goto LABEL_7;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
        this[1].SpinCount,
        a2);
    LODWORD(this[1].DebugInfo) = v24;
    this[1].LockCount = 1;
    this[1].RecursionCount = a2;
    v5 = *(__int64 ***)&this[4].LockCount;
    OwningThread = this[4].OwningThread;
    DebugInfo = (__int64)this[4].DebugInfo;
    *(_QWORD *)&v21 = v5;
    *((_QWORD *)&v21 + 1) = OwningThread;
    this[4].OwningThread = 0;
    *(_QWORD *)&this[4].LockCount = 0;
    if ( !v5 )
      goto LABEL_15;
    do
    {
      *v5 = &DebugInfo;
      v5 = (__int64 **)v5[2];
    }
    while ( v5 );
    v7 = v21;
    v8 = DebugInfo;
    if ( (_QWORD)v21 )
    {
      p_OwningThread = &this[1].OwningThread;
      ++LODWORD(this[1].OwningThread);
      v10 = v7 - v8;
      if ( v10 )
      {
        do
        {
          CDoublyLinkedList<CDbTransactionContext>::DListEntry::Remove(v10 + 152);
          *(_DWORD *)(v11 + 8) = 1;
          v12 = 0;
          v13 = *(_QWORD *)(DebugInfo + v11 + 16);
          if ( v13 )
            v12 = v13 - DebugInfo;
          v10 = v12;
        }
        while ( v12 );
      }
    }
    else
    {
LABEL_15:
      p_OwningThread = &this[1].OwningThread;
    }
    SpinCount = this[4].SpinCount;
    if ( SpinCount )
    {
      for ( i = SpinCount - (unsigned __int64)this[4].LockSemaphore;
            i;
            i = (*(_QWORD *)((char *)this[4].LockSemaphore + i + 16) - (unsigned __int64)this[4].LockSemaphore)
              & -(__int64)(*(_QWORD *)((char *)this[4].LockSemaphore + i + 16) != 0) )
      {
        ++*(_DWORD *)p_OwningThread;
        *(_DWORD *)(i + 8) = 1;
      }
    }
    LeaveCriticalSection(this);
    if ( v4 )
      LeaveCriticalSection(v4);
    if ( (_QWORD)v21 )
    {
      CDbOperationManager::CImpersonateEseDbUser::CImpersonateEseDbUser(
        (CDbOperationManager::CImpersonateEseDbUser *)v22,
        (struct CDbOperationManager *)this);
      if ( v23 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
          this[1].SpinCount,
          v23);
      CAcquireReleaseSemaphore::CAcquireReleaseSemaphore(
        (CAcquireReleaseSemaphore *)v19,
        *(void **)&lpCriticalSection[1].LockCount);
      do
      {
        v16 = (CDbTransactionContext *)CDoublyLinkedList<CDbTransactionContext>::PopFront(&DebugInfo);
        CDbTransactionContext::ReleaseAllResources(v16);
        if ( v16 )
          (*(void (__fastcall **)(CDbTransactionContext *, __int64))(*(_QWORD *)v16 + 64LL))(v16, 1);
      }
      while ( (_QWORD)v21 );
      v17 = (JET_INSTANCE)this[3].DebugInfo;
      if ( v17 != -1 )
      {
        v18 = JetStopServiceInstance(v17);
        if ( v18 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
            this[1].SpinCount,
            v18);
      }
      CAcquireReleaseSemaphore::~CAcquireReleaseSemaphore((CAcquireReleaseSemaphore *)v19);
      EnterCriticalSection(this);
      --*(_DWORD *)p_OwningThread;
      LeaveCriticalSection(this);
      CDbOperationManager::CImpersonateEseDbUser::~CImpersonateEseDbUser((CDbOperationManager::CImpersonateEseDbUser *)v22);
    }
  }
}

```

## disassembly

```asm
0x1800e8adc  mov     [rsp-18h+arg_0], rbx
0x1800e8ae1  mov     [rsp-18h+arg_8], rsi
0x1800e8ae6  push    rbp
0x1800e8ae7  push    rdi
0x1800e8ae8  push    r12
0x1800e8aea  mov     rbp, rsp
0x1800e8aed  sub     rsp, 70h
0x1800e8af1  lea     r8, [rbp+arg_10]; int *
0x1800e8af5  mov     [rbp+arg_10], 0
0x1800e8afc  mov     esi, edx
0x1800e8afe  mov     rbx, rcx
0x1800e8b01  call    ?IsFatalJetError@CDbOperationManager@@AEAAHJPEAH@Z; CDbOperationManager::IsFatalJetError(long,int *)
0x1800e8b06  test    eax, eax
0x1800e8b08  jz      loc_1800E8DAB
0x1800e8b0e  mov     rdi, cs:lpCriticalSection
0x1800e8b15  xorps   xmm0, xmm0
0x1800e8b18  mov     rcx, rdi; lpCriticalSection
0x1800e8b1b  mov     [rbp+var_30], 0B0h
0x1800e8b23  movdqu  [rbp+var_28], xmm0
0x1800e8b28  call    cs:__imp_EnterCriticalSection
0x1800e8b2e  mov     rcx, rbx; lpCriticalSection
0x1800e8b31  call    cs:__imp_EnterCriticalSection
0x1800e8b37  cmp     dword ptr [rbx+2Ch], 0
0x1800e8b3b  jnz     short loc_1800E8B59
0x1800e8b3d  cmp     dword ptr [rbx+30h], 0
0x1800e8b41  jz      short loc_1800E8B79
0x1800e8b43  cmp     [rbp+arg_10], 0
0x1800e8b47  jz      short loc_1800E8B59
0x1800e8b49  cmp     dword ptr [rbx+28h], 0
0x1800e8b4d  jnz     short loc_1800E8B59
0x1800e8b4f  mov     dword ptr [rbx+28h], 1
0x1800e8b56  mov     [rbx+34h], esi
0x1800e8b59  mov     rcx, rbx; lpCriticalSection
0x1800e8b5c  call    cs:__imp_LeaveCriticalSection
0x1800e8b62  test    rdi, rdi
0x1800e8b65  jz      loc_1800E8DAB
0x1800e8b6b  mov     rcx, rdi; lpCriticalSection
0x1800e8b6e  call    cs:__imp_LeaveCriticalSection
0x1800e8b74  jmp     loc_1800E8DAB
0x1800e8b79  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8b80  lea     r12, WPP_GLOBAL_Control
0x1800e8b87  cmp     rcx, r12
0x1800e8b8a  jz      short loc_1800E8BAF
0x1800e8b8c  test    byte ptr [rcx+1Ch], 4
0x1800e8b90  jz      short loc_1800E8BAF
0x1800e8b92  mov     r9, [rbx+48h]
0x1800e8b96  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e8b9d  mov     rcx, [rcx+10h]
0x1800e8ba1  mov     edx, 42h ; 'B'
0x1800e8ba6  mov     [rsp+70h+var_50], esi
0x1800e8baa  call    WPP_SF_Sd
0x1800e8baf  mov     eax, [rbp+arg_10]
0x1800e8bb2  mov     [rbx+28h], eax
0x1800e8bb5  mov     dword ptr [rbx+30h], 1
0x1800e8bbc  mov     [rbx+34h], esi
0x1800e8bbf  mov     r10, [rbx+0A8h]
0x1800e8bc6  mov     rax, [rbx+0B0h]
0x1800e8bcd  mov     rcx, [rbx+0A0h]
0x1800e8bd4  mov     [rbp+var_30], rcx
0x1800e8bd8  mov     qword ptr [rbp+var_28], r10
0x1800e8bdc  mov     qword ptr [rbp+var_28+8], rax
0x1800e8be0  mov     qword ptr [rbx+0B0h], 0
0x1800e8beb  mov     qword ptr [rbx+0A8h], 0
0x1800e8bf6  test    r10, r10
0x1800e8bf9  jz      short loc_1800E8C18
0x1800e8bfb  lea     rax, [rbp+var_30]
0x1800e8bff  mov     [r10], rax
0x1800e8c02  mov     r10, [r10+10h]
0x1800e8c06  test    r10, r10
0x1800e8c09  jnz     short loc_1800E8BFB
0x1800e8c0b  mov     r10, qword ptr [rbp+var_28]
0x1800e8c0f  mov     rcx, [rbp+var_30]
0x1800e8c13  test    r10, r10
0x1800e8c16  jnz     short loc_1800E8C1E
0x1800e8c18  lea     rsi, [rbx+38h]
0x1800e8c1c  jmp     short loc_1800E8C5B
0x1800e8c1e  lea     rsi, [rbx+38h]
0x1800e8c22  inc     dword ptr [rsi]
0x1800e8c24  sub     r10, rcx
0x1800e8c27  jz      short loc_1800E8C5B
0x1800e8c29  lea     rcx, [r10+98h]
0x1800e8c30  call    ?Remove@DListEntry@?$CDoublyLinkedList@VCDbTransactionContext@@@@QEAAXXZ; CDoublyLinkedList<CDbTransactionContext>::DListEntry::Remove(void)
0x1800e8c35  mov     dword ptr [r10+8], 1
0x1800e8c3d  xor     eax, eax
0x1800e8c3f  mov     rcx, [rbp+var_30]
0x1800e8c43  mov     rdx, [rcx+r10+10h]
0x1800e8c48  test    rdx, rdx
0x1800e8c4b  jz      short loc_1800E8C53
0x1800e8c4d  mov     rax, rdx
0x1800e8c50  sub     rax, rcx
0x1800e8c53  mov     r10, rax
0x1800e8c56  test    rax, rax
0x1800e8c59  jnz     short loc_1800E8C29
0x1800e8c5b  mov     rcx, [rbx+0C0h]
0x1800e8c62  test    rcx, rcx
0x1800e8c65  jz      short loc_1800E8C96
0x1800e8c67  sub     rcx, [rbx+0B8h]
0x1800e8c6e  jz      short loc_1800E8C96
0x1800e8c70  inc     dword ptr [rsi]
0x1800e8c72  mov     dword ptr [rcx+8], 1
0x1800e8c79  mov     rax, [rbx+0B8h]
0x1800e8c80  mov     rcx, [rax+rcx+10h]
0x1800e8c85  mov     rdx, rcx
0x1800e8c88  sub     rdx, rax
0x1800e8c8b  neg     rcx
0x1800e8c8e  sbb     rcx, rcx
0x1800e8c91  and     rcx, rdx
0x1800e8c94  jnz     short loc_1800E8C70
0x1800e8c96  mov     rcx, rbx; lpCriticalSection
0x1800e8c99  call    cs:__imp_LeaveCriticalSection
0x1800e8c9f  test    rdi, rdi
0x1800e8ca2  jz      short loc_1800E8CAD
0x1800e8ca4  mov     rcx, rdi; lpCriticalSection
0x1800e8ca7  call    cs:__imp_LeaveCriticalSection
0x1800e8cad  cmp     qword ptr [rbp+var_28], 0
0x1800e8cb2  jz      loc_1800E8DAB
0x1800e8cb8  mov     rdx, rbx; struct CDbOperationManager *
0x1800e8cbb  lea     rcx, [rbp+var_18]; this
0x1800e8cbf  call    ??0CImpersonateEseDbUser@CDbOperationManager@@QEAA@PEAV1@@Z; CDbOperationManager::CImpersonateEseDbUser::CImpersonateEseDbUser(CDbOperationManager *)
0x1800e8cc4  mov     eax, [rbp+var_8]
0x1800e8cc7  test    eax, eax
0x1800e8cc9  jns     short loc_1800E8CFA
0x1800e8ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8cd2  cmp     rcx, r12
0x1800e8cd5  jz      short loc_1800E8CFA
0x1800e8cd7  test    byte ptr [rcx+1Ch], 1
0x1800e8cdb  jz      short loc_1800E8CFA
0x1800e8cdd  mov     r9, [rbx+48h]
0x1800e8ce1  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e8ce8  mov     rcx, [rcx+10h]
0x1800e8cec  mov     edx, 43h ; 'C'
0x1800e8cf1  mov     [rsp+70h+var_50], eax
0x1800e8cf5  call    WPP_SF_Sd
0x1800e8cfa  mov     rdx, cs:lpCriticalSection
0x1800e8d01  lea     rcx, [rbp+var_40]; this
0x1800e8d05  mov     rdx, [rdx+30h]; void *
0x1800e8d09  call    ??0CAcquireReleaseSemaphore@@QEAA@PEAX@Z; CAcquireReleaseSemaphore::CAcquireReleaseSemaphore(void *)
0x1800e8d0e  lea     rcx, [rbp+var_30]
0x1800e8d12  call    ?PopFront@?$CDoublyLinkedList@VCDbTransactionContext@@@@QEAAPEAVCDbTransactionContext@@XZ; CDoublyLinkedList<CDbTransactionContext>::PopFront(void)
0x1800e8d17  mov     rcx, rax; this
0x1800e8d1a  mov     rdi, rax
0x1800e8d1d  call    ?ReleaseAllResources@CDbTransactionContext@@AEAAXXZ; CDbTransactionContext::ReleaseAllResources(void)
0x1800e8d22  test    rdi, rdi
0x1800e8d25  jz      short loc_1800E8D3B
0x1800e8d27  mov     rcx, [rdi]
0x1800e8d2a  mov     edx, 1
0x1800e8d2f  mov     rax, [rcx+40h]
0x1800e8d33  mov     rcx, rdi
0x1800e8d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8d3b  cmp     qword ptr [rbp+var_28], 0
0x1800e8d40  jnz     short loc_1800E8D0E
0x1800e8d42  mov     rcx, [rbx+78h]; instance
0x1800e8d46  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800e8d4a  jz      short loc_1800E8D85
0x1800e8d4c  call    cs:__imp_JetStopServiceInstance
0x1800e8d52  test    eax, eax
0x1800e8d54  jns     short loc_1800E8D85
0x1800e8d56  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8d5d  cmp     rcx, r12
0x1800e8d60  jz      short loc_1800E8D85
0x1800e8d62  test    byte ptr [rcx+1Ch], 1
0x1800e8d66  jz      short loc_1800E8D85
0x1800e8d68  mov     r9, [rbx+48h]
0x1800e8d6c  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e8d73  mov     rcx, [rcx+10h]
0x1800e8d77  mov     edx, 44h ; 'D'
0x1800e8d7c  mov     [rsp+70h+var_50], eax
0x1800e8d80  call    WPP_SF_Sd
0x1800e8d85  lea     rcx, [rbp+var_40]; this
0x1800e8d89  call    ??1CAcquireReleaseSemaphore@@QEAA@XZ; CAcquireReleaseSemaphore::~CAcquireReleaseSemaphore(void)
0x1800e8d8e  mov     rcx, rbx; lpCriticalSection
0x1800e8d91  call    cs:__imp_EnterCriticalSection
0x1800e8d97  dec     dword ptr [rsi]
0x1800e8d99  mov     rcx, rbx; lpCriticalSection
0x1800e8d9c  call    cs:__imp_LeaveCriticalSection
0x1800e8da2  lea     rcx, [rbp+var_18]; this
0x1800e8da6  call    ??1CImpersonateEseDbUser@CDbOperationManager@@QEAA@XZ; CDbOperationManager::CImpersonateEseDbUser::~CImpersonateEseDbUser(void)
0x1800e8dab  lea     r11, [rsp+70h+var_s0]
0x1800e8db0  mov     rbx, [r11+20h]
0x1800e8db4  mov     rsi, [r11+28h]
0x1800e8db8  mov     rsp, r11
0x1800e8dbb  pop     r12
0x1800e8dbd  pop     rdi
0x1800e8dbe  pop     rbp
0x1800e8dbf  retn
```
