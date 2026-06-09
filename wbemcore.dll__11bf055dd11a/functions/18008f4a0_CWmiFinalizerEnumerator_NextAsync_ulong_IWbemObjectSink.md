# CWmiFinalizerEnumerator::NextAsync(ulong,IWbemObjectSink *)

- ea: `0x18008f4a0`
- end: `0x18008f81c`
- name: `?NextAsync@CWmiFinalizerEnumerator@@UEAAJKPEAUIWbemObjectSink@@@Z`
- size: `892`
- prototype: `__int64 __fastcall(CWmiFinalizerEnumerator *__hidden this, unsigned int, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007fb0`
- `0x180009b90`
- `0x18000b140`
- `0x18000b46c`
- `0x18005e5e8`
- `0x18008f2c8`
- `0x18008f4a0`
- `0x180090014`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008f5f7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008f5f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f651`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f651`
- `wbemcomn!?AccessCheck@CIdentitySecurity@@QEAAHXZ` at `0x18008f4f5`
- `wbemcomn!?AccessCheck@CIdentitySecurity@@QEAAHXZ` at `0x18008f4f5`
- `wbemcomn!GetMemLogObject` at `0x18008f4ff`
- `wbemcomn!GetMemLogObject` at `0x18008f552`
- `wbemcomn!GetMemLogObject` at `0x18008f599`
- `wbemcomn!GetMemLogObject` at `0x18008f605`
- `wbemcomn!GetMemLogObject` at `0x18008f661`
- `wbemcomn!GetMemLogObject` at `0x18008f6b2`
- `wbemcomn!GetMemLogObject` at `0x18008f71a`
- `wbemcomn!GetMemLogObject` at `0x18008f7c4`
- `wbemcomn!GetMemLogObject` at `0x18008f4ff`
- `wbemcomn!GetMemLogObject` at `0x18008f552`
- `wbemcomn!GetMemLogObject` at `0x18008f599`
- `wbemcomn!GetMemLogObject` at `0x18008f605`
- `wbemcomn!GetMemLogObject` at `0x18008f661`
- `wbemcomn!GetMemLogObject` at `0x18008f6b2`
- `wbemcomn!GetMemLogObject` at `0x18008f71a`
- `wbemcomn!GetMemLogObject` at `0x18008f7c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f50f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f560`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f5a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f613`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f66f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f6c0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f725`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f7cf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f50f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f560`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f5a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f613`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f66f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f6c0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f725`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f7cf`

## pseudocode

```c
int __fastcall CWmiFinalizerEnumerator::NextAsync(CWmiFinalizerEnumerator *this, int a2, struct IWbemObjectSink *a3)
{
  CMemoryLog *MemLogObject; // rax
  int v7; // ebx
  CClientCnt *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  CMemoryLog *v12; // rax
  CClientCnt *v13; // rcx
  __int64 v14; // rdx
  CMemoryLog *v15; // rax
  HANDLE EventW; // rax
  CMemoryLog *v17; // rax
  CMemoryLog *v18; // rax
  CWmiFinalizer *v19; // rcx
  CMemoryLog *v20; // rax
  int v21; // edi
  CMemoryLog *v22; // rax
  CClientCnt *v23; // rcx
  __int64 v24; // rdx
  struct IWbemObjectSink *v25; // rdx
  CWmiFinalizer *v26; // rcx
  CMemoryLog *v27; // rax

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids);
  }
  if ( !CIdentitySecurity::AccessCheck((CWmiFinalizerEnumerator *)((char *)this + 112)) )
  {
    MemLogObject = GetMemLogObject();
    v7 = -2147217405;
    CMemoryLog::Write(MemLogObject, -2147217405);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v7;
    }
    v9 = 227;
    v10 = 2147749891LL;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids, v10);
    return v7;
  }
  if ( !*((_QWORD *)this + 5) )
  {
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, -2147217407);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return -2147217407;
    }
    v14 = 228;
LABEL_42:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids, 2147749889LL);
    return -2147217407;
  }
  if ( !a3 )
  {
    v15 = GetMemLogObject();
    v7 = -2147217400;
    CMemoryLog::Write(v15, -2147217400);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v7;
    }
    v9 = 229;
    v10 = 2147749896LL;
    goto LABEL_10;
  }
  if ( !a2 )
    return 1;
  if ( !*((_QWORD *)this + 4) )
  {
    EventW = CreateEventW(0, 0, 1, 0);
    if ( !EventW )
    {
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, -2147217407);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return -2147217407;
      }
      v14 = 230;
      goto LABEL_42;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 4, (signed __int64)EventW, 0) )
      CloseHandle(EventW);
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 5) + 40LL) )
  {
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, -2147217407);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return -2147217407;
    }
    v14 = 231;
    goto LABEL_42;
  }
  CCoreQueue::QueueWaitForSingleObject(*((void **)this + 4), 0xFFFFFFFF);
  v19 = (CWmiFinalizer *)*((_QWORD *)this + 5);
  if ( *((_DWORD *)v19 + 10) )
  {
    CWmiFinalizerEnumerator::SetCompletionSignalEvent(this);
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, -2147217407);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return -2147217407;
    }
    v14 = 232;
    goto LABEL_42;
  }
  if ( *((_DWORD *)this + 55) )
  {
    v21 = CWmiFinalizer::SetSinkToIdentity(v19, a3);
    if ( v21 >= 0 )
    {
      CWmiFinalizer::DoSetStatus(
        *((CWmiFinalizer **)this + 5),
        a3,
        0,
        *(_DWORD *)(*((_QWORD *)this + 5) + 504LL),
        0,
        0,
        0);
      CWmiFinalizerEnumerator::SetCompletionSignalEvent(this);
      return 1;
    }
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, v21);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v21;
    }
    v24 = 233;
    goto LABEL_50;
  }
  *((_QWORD *)this + 7) = a3;
  ((void (__fastcall *)(struct IWbemObjectSink *))a3->lpVtbl->AddRef)(a3);
  v25 = (struct IWbemObjectSink *)*((_QWORD *)this + 7);
  v26 = (CWmiFinalizer *)*((_QWORD *)this + 5);
  *((_DWORD *)this + 6) = a2;
  v21 = CWmiFinalizer::SetSinkToIdentity(v26, v25);
  if ( v21 < 0 )
  {
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, v21);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v21;
    }
    v24 = 234;
LABEL_50:
    WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids, (unsigned int)v21);
    return v21;
  }
  return CWmiFinalizer::NextAsync(*((CWmiFinalizer **)this + 5), this);
}

```

## disassembly

```asm
0x18008f4a0  push    rbx
0x18008f4a2  push    rbp
0x18008f4a3  push    rsi
0x18008f4a4  push    rdi
0x18008f4a5  push    r12
0x18008f4a7  push    r15
0x18008f4a9  sub     rsp, 48h
0x18008f4ad  mov     rsi, r8
0x18008f4b0  mov     edi, edx
0x18008f4b2  mov     rbx, rcx
0x18008f4b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f4bc  lea     r12, WPP_GLOBAL_Control
0x18008f4c3  lea     r15, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids
0x18008f4ca  mov     ebp, 1
0x18008f4cf  cmp     rcx, r12
0x18008f4d2  jz      short loc_18008F4F1
0x18008f4d4  test    [rcx+1Ch], bpl
0x18008f4d8  jz      short loc_18008F4F1
0x18008f4da  cmp     byte ptr [rcx+19h], 5
0x18008f4de  jb      short loc_18008F4F1
0x18008f4e0  mov     rcx, [rcx+10h]
0x18008f4e4  mov     edx, 0E2h
0x18008f4e9  mov     r8, r15
0x18008f4ec  call    WPP_SF_
0x18008f4f1  lea     rcx, [rbx+70h]
0x18008f4f5  call    cs:__imp_?AccessCheck@CIdentitySecurity@@QEAAHXZ; CIdentitySecurity::AccessCheck(void)
0x18008f4fb  test    eax, eax
0x18008f4fd  jnz     short loc_18008F54B
0x18008f4ff  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008f505  mov     ebx, 80041003h
0x18008f50a  mov     rcx, rax
0x18008f50d  mov     edx, ebx
0x18008f50f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008f515  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f51c  cmp     rcx, r12
0x18008f51f  jz      short loc_18008F544
0x18008f521  test    [rcx+1Ch], bpl
0x18008f525  jz      short loc_18008F544
0x18008f527  cmp     byte ptr [rcx+19h], 2
0x18008f52b  jb      short loc_18008F544
0x18008f52d  mov     edx, 0E3h
0x18008f532  mov     r9d, 80041003h
0x18008f538  mov     rcx, [rcx+10h]
0x18008f53c  mov     r8, r15
0x18008f53f  call    WPP_SF_d
0x18008f544  mov     eax, ebx
0x18008f546  jmp     loc_18008F80F
0x18008f54b  cmp     qword ptr [rbx+28h], 0
0x18008f550  jnz     short loc_18008F594
0x18008f552  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008f558  mov     rcx, rax
0x18008f55b  mov     edx, 80041001h
0x18008f560  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008f566  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f56d  cmp     rcx, r12
0x18008f570  jz      loc_18008F6F5
0x18008f576  test    [rcx+1Ch], bpl
0x18008f57a  jz      loc_18008F6F5
0x18008f580  cmp     byte ptr [rcx+19h], 2
0x18008f584  jb      loc_18008F6F5
0x18008f58a  mov     edx, 0E4h
0x18008f58f  jmp     loc_18008F6E3
0x18008f594  test    rsi, rsi
0x18008f597  jnz     short loc_18008F5DB
0x18008f599  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008f59f  mov     ebx, 80041008h
0x18008f5a4  mov     rcx, rax
0x18008f5a7  mov     edx, ebx
0x18008f5a9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008f5af  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f5b6  cmp     rcx, r12
0x18008f5b9  jz      short loc_18008F544
0x18008f5bb  test    [rcx+1Ch], bpl
0x18008f5bf  jz      short loc_18008F544
0x18008f5c1  cmp     byte ptr [rcx+19h], 2
0x18008f5c5  jb      loc_18008F544
0x18008f5cb  mov     edx, 0E5h
0x18008f5d0  mov     r9d, 80041008h
0x18008f5d6  jmp     loc_18008F538
0x18008f5db  test    edi, edi
0x18008f5dd  jnz     short loc_18008F5E6
0x18008f5df  mov     eax, ebp
0x18008f5e1  jmp     loc_18008F80F
0x18008f5e6  cmp     qword ptr [rbx+20h], 0
0x18008f5eb  jnz     short loc_18008F657
0x18008f5ed  xor     r9d, r9d; lpName
0x18008f5f0  mov     r8d, ebp; bInitialState
0x18008f5f3  xor     edx, edx; bManualReset
0x18008f5f5  xor     ecx, ecx; lpEventAttributes
0x18008f5f7  call    cs:__imp_CreateEventW
0x18008f5fd  mov     rcx, rax; hObject
0x18008f600  test    rax, rax
0x18008f603  jnz     short loc_18008F647
0x18008f605  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008f60b  mov     rcx, rax
0x18008f60e  mov     edx, 80041001h
0x18008f613  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008f619  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f620  cmp     rcx, r12
0x18008f623  jz      loc_18008F6F5
0x18008f629  test    [rcx+1Ch], bpl
0x18008f62d  jz      loc_18008F6F5
0x18008f633  cmp     byte ptr [rcx+19h], 2
0x18008f637  jb      loc_18008F6F5
0x18008f63d  mov     edx, 0E6h
0x18008f642  jmp     loc_18008F6E3
0x18008f647  xor     eax, eax
0x18008f649  lock cmpxchg [rbx+20h], rcx
0x18008f64f  jz      short loc_18008F657
0x18008f651  call    cs:__imp_CloseHandle
0x18008f657  mov     rax, [rbx+28h]
0x18008f65b  cmp     dword ptr [rax+28h], 0
0x18008f65f  jz      short loc_18008F694
0x18008f661  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008f667  mov     rcx, rax
0x18008f66a  mov     edx, 80041001h
0x18008f66f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008f675  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f67c  cmp     rcx, r12
0x18008f67f  jz      short loc_18008F6F5
0x18008f681  test    [rcx+1Ch], bpl
0x18008f685  jz      short loc_18008F6F5
0x18008f687  cmp     byte ptr [rcx+19h], 2
0x18008f68b  jb      short loc_18008F6F5
0x18008f68d  mov     edx, 0E7h
0x18008f692  jmp     short loc_18008F6E3
0x18008f694  mov     rcx, [rbx+20h]; void *
0x18008f698  or      edx, 0FFFFFFFFh; unsigned int
0x18008f69b  call    ?QueueWaitForSingleObject@CCoreQueue@@SAKPEAXK@Z; CCoreQueue::QueueWaitForSingleObject(void *,ulong)
0x18008f6a0  mov     rcx, [rbx+28h]; this
0x18008f6a4  cmp     dword ptr [rcx+28h], 0
0x18008f6a8  jz      short loc_18008F6FF
0x18008f6aa  mov     rcx, rbx; this
0x18008f6ad  call    ?SetCompletionSignalEvent@CWmiFinalizerEnumerator@@QEAAJXZ; CWmiFinalizerEnumerator::SetCompletionSignalEvent(void)
0x18008f6b2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008f6b8  mov     rcx, rax
0x18008f6bb  mov     edx, 80041001h
0x18008f6c0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008f6c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f6cd  cmp     rcx, r12
0x18008f6d0  jz      short loc_18008F6F5
0x18008f6d2  test    [rcx+1Ch], bpl
0x18008f6d6  jz      short loc_18008F6F5
0x18008f6d8  cmp     byte ptr [rcx+19h], 2
0x18008f6dc  jb      short loc_18008F6F5
0x18008f6de  mov     edx, 0E8h
0x18008f6e3  mov     rcx, [rcx+10h]
0x18008f6e7  mov     r9d, 80041001h
0x18008f6ed  mov     r8, r15
0x18008f6f0  call    WPP_SF_d
0x18008f6f5  mov     eax, 80041001h
0x18008f6fa  jmp     loc_18008F80F
0x18008f6ff  cmp     dword ptr [rbx+0DCh], 0
0x18008f706  jz      loc_18008F79B
0x18008f70c  mov     rdx, rsi; struct IWbemObjectSink *
0x18008f70f  call    ?SetSinkToIdentity@CWmiFinalizer@@QEAAJPEAUIWbemObjectSink@@@Z; CWmiFinalizer::SetSinkToIdentity(IWbemObjectSink *)
0x18008f714  mov     edi, eax
0x18008f716  test    eax, eax
0x18008f718  jns     short loc_18008F75E
0x18008f71a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008f720  mov     rcx, rax
0x18008f723  mov     edx, edi
0x18008f725  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008f72b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f732  cmp     rcx, r12
0x18008f735  jz      short loc_18008F757
0x18008f737  test    [rcx+1Ch], bpl
0x18008f73b  jz      short loc_18008F757
0x18008f73d  cmp     byte ptr [rcx+19h], 2
0x18008f741  jb      short loc_18008F757
0x18008f743  mov     edx, 0E9h
0x18008f748  mov     rcx, [rcx+10h]
0x18008f74c  mov     r9d, edi
0x18008f74f  mov     r8, r15
0x18008f752  call    WPP_SF_d
0x18008f757  mov     eax, edi
0x18008f759  jmp     loc_18008F80F
0x18008f75e  mov     rcx, [rbx+28h]; this
0x18008f762  xor     r8d, r8d; int
0x18008f765  mov     [rsp+78h+var_48], 0; int
0x18008f76d  mov     rdx, rsi; struct IWbemObjectSink *
0x18008f770  mov     [rsp+78h+var_50], 0; struct IWbemClassObject *
0x18008f779  mov     [rsp+78h+var_58], 0; unsigned __int16 *
0x18008f782  mov     r9d, [rcx+1F8h]; int
0x18008f789  call    ?DoSetStatus@CWmiFinalizer@@QEAAJPEAUIWbemObjectSink@@JJPEAGPEAUIWbemClassObject@@H@Z; CWmiFinalizer::DoSetStatus(IWbemObjectSink *,long,long,ushort *,IWbemClassObject *,int)
0x18008f78e  mov     rcx, rbx; this
0x18008f791  call    ?SetCompletionSignalEvent@CWmiFinalizerEnumerator@@QEAAJXZ; CWmiFinalizerEnumerator::SetCompletionSignalEvent(void)
0x18008f796  jmp     loc_18008F5DF
0x18008f79b  mov     [rbx+38h], rsi
0x18008f79f  mov     rcx, rsi
0x18008f7a2  mov     rax, [rsi]
0x18008f7a5  mov     rax, [rax+8]
0x18008f7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f7ae  mov     rdx, [rbx+38h]; struct IWbemObjectSink *
0x18008f7b2  mov     rcx, [rbx+28h]; this
0x18008f7b6  mov     [rbx+18h], edi
0x18008f7b9  call    ?SetSinkToIdentity@CWmiFinalizer@@QEAAJPEAUIWbemObjectSink@@@Z; CWmiFinalizer::SetSinkToIdentity(IWbemObjectSink *)
0x18008f7be  mov     edi, eax
0x18008f7c0  test    eax, eax
0x18008f7c2  jns     short loc_18008F803
0x18008f7c4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008f7ca  mov     rcx, rax
0x18008f7cd  mov     edx, edi
0x18008f7cf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008f7d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f7dc  cmp     rcx, r12
0x18008f7df  jz      loc_18008F757
0x18008f7e5  test    [rcx+1Ch], bpl
0x18008f7e9  jz      loc_18008F757
0x18008f7ef  cmp     byte ptr [rcx+19h], 2
0x18008f7f3  jb      loc_18008F757
0x18008f7f9  mov     edx, 0EAh
0x18008f7fe  jmp     loc_18008F748
0x18008f803  mov     rcx, [rbx+28h]; this
0x18008f807  mov     rdx, rbx; struct CWmiFinalizerEnumerator *
0x18008f80a  call    ?NextAsync@CWmiFinalizer@@QEAAJPEAVCWmiFinalizerEnumerator@@@Z; CWmiFinalizer::NextAsync(CWmiFinalizerEnumerator *)
0x18008f80f  add     rsp, 48h
0x18008f813  pop     r15
0x18008f815  pop     r12
0x18008f817  pop     rdi
0x18008f818  pop     rsi
0x18008f819  pop     rbp
0x18008f81a  pop     rbx
0x18008f81b  retn
```
