# CCoreQueue::Enqueue(CCoreExecReq *,void * *)

- ea: `0x1800422a0`
- end: `0x1800427fb`
- name: `?Enqueue@CCoreQueue@@UEAAJPEAVCCoreExecReq@@PEAPEAX@Z`
- size: `1371`
- prototype: `__int64 __fastcall(CCoreQueue *__hidden this, struct CCoreExecReq *, void **)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800421ac`
- `0x180051770`
- `0x180051b10`
- `0x180068388`

## callees

- `0x18000b104`
- `0x18000b140`
- `0x18000b46c`
- `0x1800422a0`
- `0x180052250`
- `0x180061cf0`
- `0x18006379c`
- `0x180063ac0`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800424b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800424b4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180042387`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180042387`
- `wbemcomn!?Enter@CCritSec@@QEAAXXZ` at `0x180042307`
- `wbemcomn!?Enter@CCritSec@@QEAAXXZ` at `0x180042307`
- `wbemcomn!?Leave@CCritSec@@QEAAXXZ` at `0x180042390`
- `wbemcomn!?Leave@CCritSec@@QEAAXXZ` at `0x180042441`
- `wbemcomn!?Leave@CCritSec@@QEAAXXZ` at `0x18004265d`
- `wbemcomn!?Leave@CCritSec@@QEAAXXZ` at `0x180042715`
- `wbemcomn!?Leave@CCritSec@@QEAAXXZ` at `0x1800427bf`
- `wbemcomn!?Leave@CCritSec@@QEAAXXZ` at `0x180042390`
- `wbemcomn!?Leave@CCritSec@@QEAAXXZ` at `0x180042441`
- `wbemcomn!?Leave@CCritSec@@QEAAXXZ` at `0x18004265d`
- `wbemcomn!?Leave@CCritSec@@QEAAXXZ` at `0x180042715`
- `wbemcomn!?Leave@CCritSec@@QEAAXXZ` at `0x1800427bf`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180042321`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180042321`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180042335`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180042335`
- `wbemcomn!GetMemLogObject` at `0x1800424cf`
- `wbemcomn!GetMemLogObject` at `0x1800424e5`
- `wbemcomn!GetMemLogObject` at `0x1800425ae`
- `wbemcomn!GetMemLogObject` at `0x180042600`
- `wbemcomn!GetMemLogObject` at `0x180042668`
- `wbemcomn!GetMemLogObject` at `0x1800426ba`
- `wbemcomn!GetMemLogObject` at `0x180042764`
- `wbemcomn!GetMemLogObject` at `0x1800424cf`
- `wbemcomn!GetMemLogObject` at `0x1800424e5`
- `wbemcomn!GetMemLogObject` at `0x1800425ae`
- `wbemcomn!GetMemLogObject` at `0x180042600`
- `wbemcomn!GetMemLogObject` at `0x180042668`
- `wbemcomn!GetMemLogObject` at `0x1800426ba`
- `wbemcomn!GetMemLogObject` at `0x180042764`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800424da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800424f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800425bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004260e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042676`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800426c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042772`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800424da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800424f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800425bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004260e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042676`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800426c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042772`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCoreQueue::Enqueue(CCoreQueue *this, struct CCoreExecReq *a2, void **a3)
{
  unsigned int i; // edi
  _QWORD *v7; // rax
  __int64 v8; // rbx
  __int64 result; // rax
  int IsDependentRequest; // eax
  _DWORD *v11; // rdx
  BOOL v12; // ecx
  int v13; // ebx
  int v14; // edi
  HANDLE EventW; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  __int64 v22; // r8
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  CMemoryLog *v25; // rax

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids, a2);
  }
  try
  {
    if ( *((_DWORD *)this + 14) )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217357);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids, 2147749939LL);
      }
      result = 2147749939LL;
    }
    else if ( *((_BYTE *)a2 + 28) )
    {
      if ( a3 )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        *a3 = EventW;
        if ( !EventW )
        {
          v19 = GetMemLogObject();
          CMemoryLog::Write(v19, -2147217402);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              35,
              WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids,
              2147749894LL);
          }
          return 2147749894LL;
        }
        *((_QWORD *)a2 + 1) = EventW;
      }
      CCritSec::Enter((CCoreQueue *)((char *)this + 16));
      for ( i = 0; (signed int)i < CFlexArray::Size((CCoreQueue *)((char *)this + 64)); ++i )
      {
        v7 = (_QWORD *)CFlexArray::operator[]((char *)this + 64, i);
        v8 = *v7;
        if ( *(_DWORD *)(*v7 + 16LL)
          && (*(unsigned int (__fastcall **)(CCoreQueue *, _QWORD, struct CCoreExecReq *))(*(_QWORD *)this + 48LL))(
               this,
               *v7,
               a2) )
        {
          *(_QWORD *)(v8 + 8) = a2;
          *(_DWORD *)(v8 + 16) = 0;
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids);
          }
          SetEvent(*(HANDLE *)(v8 + 32));
          CCritSec::Leave((CCoreQueue *)((char *)this + 16));
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids, 0);
          }
          return 0;
        }
      }
      IsDependentRequest = CCoreQueue::IsDependentRequest(this, a2);
      v11 = (_DWORD *)((char *)a2 + 64);
      v12 = IsDependentRequest || *v11;
      if ( *((_DWORD *)this + 44) < *((_DWORD *)this + 49) )
      {
        if ( !v12 )
        {
          (*(void (__fastcall **)(CCoreQueue *, struct CCoreExecReq *))(*(_QWORD *)this + 152LL))(this, a2);
          LOBYTE(v22) = 1;
          if ( !(*(unsigned int (__fastcall **)(CCoreQueue *, struct CCoreExecReq *, __int64))(*(_QWORD *)this + 56LL))(
                  this,
                  a2,
                  v22)
            || (unsigned int)CCoreQueue::CreateNewThread(this, 0) )
          {
LABEL_25:
            v13 = CCoreQueue::PlaceRequestInQueue(this, a2);
            v14 = *((_DWORD *)this + 44);
            CCritSec::Leave((CCoreQueue *)((char *)this + 16));
            if ( v13 < 0 )
            {
              v16 = GetMemLogObject();
              CMemoryLog::Write(v16, v13);
            }
            else
            {
              CCoreQueue::SitOutPenalty(this, v14);
            }
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                40,
                WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids,
                (unsigned int)v13);
            }
            return (unsigned int)v13;
          }
          v23 = GetMemLogObject();
          CMemoryLog::Write(v23, -2147217402);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              39,
              WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids,
              2147749894LL);
          }
LABEL_42:
          CCritSec::Leave((CCoreQueue *)((char *)this + 16));
          return 2147749894LL;
        }
LABEL_22:
        if ( !*v11 )
          *((_DWORD *)a2 + 6) = -1610612735;
        if ( (unsigned int)CCoreQueue::CreateNewThread(this, 1) )
          goto LABEL_25;
        v21 = GetMemLogObject();
        CMemoryLog::Write(v21, -2147217402);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids,
            2147749894LL);
        }
        goto LABEL_42;
      }
      if ( v12 )
        goto LABEL_22;
      CCritSec::Leave((CCoreQueue *)((char *)this + 16));
      v20 = GetMemLogObject();
      CMemoryLog::Write(v20, -2147217407);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids, 2147749889LL);
      }
      result = 2147749889LL;
    }
    else
    {
      v18 = GetMemLogObject();
      CMemoryLog::Write(v18, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids, 2147749894LL);
      }
      result = 2147749894LL;
    }
  }
  catch ( CX_MemoryException )
  {
    _InterlockedIncrement(&ExceptionCounter::s_Count);
    v24 = GetMemLogObject();
    CMemoryLog::Write(v24, -1);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids);
    }
    v25 = GetMemLogObject();
    CMemoryLog::Write(v25, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800422a0  push    rbx
0x1800422a2  push    rsi
0x1800422a3  push    rdi
0x1800422a4  push    r12
0x1800422a6  push    r13
0x1800422a8  push    r14
0x1800422aa  push    r15
0x1800422ac  sub     rsp, 40h
0x1800422b0  mov     rbx, r8
0x1800422b3  mov     r15, rdx
0x1800422b6  mov     rsi, rcx
0x1800422b9  lea     r13, WPP_GLOBAL_Control
0x1800422c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800422c7  cmp     rcx, r13
0x1800422ca  jz      short loc_1800422D6
0x1800422cc  test    byte ptr [rcx+1Ch], 1
0x1800422d0  jnz     loc_18004250F
0x1800422d6  lea     r14, [rsi+10h]
0x1800422da  mov     [rsp+78h+var_48], r14
0x1800422df  xor     r12d, r12d
0x1800422e2  mov     [rsp+78h+var_50], r12d
0x1800422e7  cmp     [rsi+38h], r12d
0x1800422eb  jnz     loc_1800424E5
0x1800422f1  cmp     [r15+1Ch], r12b
0x1800422f5  jz      loc_1800425AE
0x1800422fb  test    rbx, rbx
0x1800422fe  jnz     loc_1800424AA
0x180042304  mov     rcx, r14
0x180042307  call    cs:__imp_?Enter@CCritSec@@QEAAXXZ; CCritSec::Enter(void)
0x18004230d  mov     [rsp+78h+var_50], 1
0x180042315  mov     edi, r12d
0x180042318  mov     [rsp+78h+var_58], r12d
0x18004231d  lea     rcx, [rsi+40h]
0x180042321  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180042327  cmp     edi, eax
0x180042329  jge     loc_1800423C3
0x18004232f  mov     edx, edi
0x180042331  lea     rcx, [rsi+40h]
0x180042335  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x18004233b  mov     rbx, [rax]
0x18004233e  cmp     dword ptr [rbx+10h], 0
0x180042342  jnz     short loc_18004234C
0x180042344  inc     edi
0x180042346  mov     [rsp+78h+var_58], edi
0x18004234a  jmp     short loc_18004231D
0x18004234c  mov     rax, [rsi]
0x18004234f  mov     r8, r15
0x180042352  mov     rdx, rbx
0x180042355  mov     rcx, rsi
0x180042358  mov     rax, [rax+30h]
0x18004235c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042361  test    eax, eax
0x180042363  jz      short loc_180042344
0x180042365  mov     [rbx+8], r15
0x180042369  mov     [rbx+10h], r12d
0x18004236d  mov     rcx, cs:WPP_GLOBAL_Control
0x180042374  cmp     rcx, r13
0x180042377  jz      short loc_180042383
0x180042379  test    byte ptr [rcx+1Ch], 1
0x18004237d  jnz     loc_180042536
0x180042383  mov     rcx, [rbx+20h]; hEvent
0x180042387  call    cs:__imp_SetEvent
0x18004238d  mov     rcx, r14
0x180042390  call    cs:__imp_?Leave@CCritSec@@QEAAXXZ; CCritSec::Leave(void)
0x180042396  mov     [rsp+78h+var_50], r12d
0x18004239b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800423a2  cmp     rcx, r13
0x1800423a5  jz      short loc_1800423B1
0x1800423a7  test    byte ptr [rcx+1Ch], 1
0x1800423ab  jnz     loc_180042483
0x1800423b1  xor     eax, eax
0x1800423b3  add     rsp, 40h
0x1800423b7  pop     r15
0x1800423b9  pop     r14
0x1800423bb  pop     r13
0x1800423bd  pop     r12
0x1800423bf  pop     rdi
0x1800423c0  pop     rsi
0x1800423c1  pop     rbx
0x1800423c2  retn
0x1800423c3  mov     rdx, r15; struct CCoreExecReq *
0x1800423c6  mov     rcx, rsi; this
0x1800423c9  call    ?IsDependentRequest@CCoreQueue@@MEAAHPEAVCCoreExecReq@@@Z; CCoreQueue::IsDependentRequest(CCoreExecReq *)
0x1800423ce  lea     rdx, [r15+40h]
0x1800423d2  test    eax, eax
0x1800423d4  jnz     loc_180042477
0x1800423da  cmp     [rdx], eax
0x1800423dc  ja      loc_180042477
0x1800423e2  mov     ecx, r12d
0x1800423e5  mov     ebx, 1
0x1800423ea  mov     eax, [rsi+0C4h]
0x1800423f0  cmp     [rsi+0B0h], eax
0x1800423f6  jge     loc_180042652
0x1800423fc  test    ecx, ecx
0x1800423fe  jz      loc_180042720
0x180042404  cmp     dword ptr [rdx], 0
0x180042407  jnz     short loc_180042411
0x180042409  mov     dword ptr [r15+18h], 0A0000001h
0x180042411  test    ecx, ecx
0x180042413  jz      loc_180042735
0x180042419  mov     edx, ebx; int
0x18004241b  mov     rcx, rsi; this
0x18004241e  call    ?CreateNewThread@CCoreQueue@@MEAAHH@Z; CCoreQueue::CreateNewThread(int)
0x180042423  test    eax, eax
0x180042425  jz      loc_1800426BA
0x18004242b  mov     rdx, r15; struct CCoreExecReq *
0x18004242e  mov     rcx, rsi; this
0x180042431  call    ?PlaceRequestInQueue@CCoreQueue@@AEAAJPEAVCCoreExecReq@@@Z; CCoreQueue::PlaceRequestInQueue(CCoreExecReq *)
0x180042436  mov     ebx, eax
0x180042438  mov     edi, [rsi+0B0h]
0x18004243e  mov     rcx, r14
0x180042441  call    cs:__imp_?Leave@CCritSec@@QEAAXXZ; CCritSec::Leave(void)
0x180042447  mov     [rsp+78h+var_50], r12d
0x18004244c  test    ebx, ebx
0x18004244e  js      short loc_1800424CF
0x180042450  mov     edx, edi; int
0x180042452  mov     rcx, rsi; this
0x180042455  call    ?SitOutPenalty@CCoreQueue@@MEAAXJ@Z; CCoreQueue::SitOutPenalty(long)
0x18004245a  mov     rcx, cs:WPP_GLOBAL_Control
0x180042461  cmp     rcx, r13
0x180042464  jz      short loc_180042470
0x180042466  test    byte ptr [rcx+1Ch], 1
0x18004246a  jnz     loc_1800427CA
0x180042470  mov     eax, ebx
0x180042472  jmp     loc_1800423B3
0x180042477  mov     ebx, 1
0x18004247c  mov     ecx, ebx
0x18004247e  jmp     loc_1800423EA
0x180042483  cmp     byte ptr [rcx+19h], 2
0x180042487  jb      loc_1800423B1
0x18004248d  mov     edx, 24h ; '$'
0x180042492  xor     r9d, r9d
0x180042495  lea     r8, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids
0x18004249c  mov     rcx, [rcx+10h]
0x1800424a0  call    WPP_SF_d
0x1800424a5  jmp     loc_1800423B1
0x1800424aa  xor     r9d, r9d; lpName
0x1800424ad  xor     r8d, r8d; bInitialState
0x1800424b0  xor     edx, edx; bManualReset
0x1800424b2  xor     ecx, ecx; lpEventAttributes
0x1800424b4  call    cs:__imp_CreateEventW
0x1800424ba  mov     [rbx], rax
0x1800424bd  test    rax, rax
0x1800424c0  jz      loc_180042600
0x1800424c6  mov     [r15+8], rax
0x1800424ca  jmp     loc_180042304
0x1800424cf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800424d5  mov     edx, ebx
0x1800424d7  mov     rcx, rax
0x1800424da  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800424e0  jmp     loc_18004245A
0x1800424e5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800424eb  mov     edx, 80041033h
0x1800424f0  mov     rcx, rax
0x1800424f3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800424f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180042500  cmp     rcx, r13
0x180042503  jnz     short loc_18004257E
0x180042505  mov     eax, 80041033h
0x18004250a  jmp     loc_1800423B3
0x18004250f  cmp     byte ptr [rcx+19h], 5
0x180042513  jb      loc_1800422D6
0x180042519  mov     edx, 20h ; ' '
0x18004251e  mov     r9, r15
0x180042521  lea     r8, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids
0x180042528  mov     rcx, [rcx+10h]
0x18004252c  call    WPP_SF_q
0x180042531  jmp     loc_1800422D6
0x180042536  cmp     byte ptr [rcx+19h], 5
0x18004253a  jb      loc_180042383
0x180042540  mov     edx, 14h
0x180042545  lea     r8, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids
0x18004254c  mov     rcx, [rcx+10h]
0x180042550  call    WPP_SF_
0x180042555  jmp     loc_180042383
0x18004255a  test    ebx, ebx
0x18004255c  jnz     loc_180042712
0x180042562  mov     eax, 80041006h
0x180042567  jmp     loc_1800423B3
0x18004256c  test    ebx, ebx
0x18004256e  jnz     loc_1800427BC
0x180042574  mov     eax, 80041006h
0x180042579  jmp     loc_1800423B3
0x18004257e  test    byte ptr [rcx+1Ch], 1
0x180042582  jz      short loc_180042505
0x180042584  cmp     byte ptr [rcx+19h], 2
0x180042588  jb      loc_180042505
0x18004258e  mov     edx, 21h ; '!'
0x180042593  mov     r9d, 80041033h
0x180042599  lea     r8, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids
0x1800425a0  mov     rcx, [rcx+10h]
0x1800425a4  call    WPP_SF_d
0x1800425a9  jmp     loc_180042505
0x1800425ae  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800425b4  mov     edx, 80041006h
0x1800425b9  mov     rcx, rax
0x1800425bc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800425c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800425c9  cmp     rcx, r13
0x1800425cc  jz      short loc_1800425F6
0x1800425ce  test    byte ptr [rcx+1Ch], 1
0x1800425d2  jz      short loc_1800425F6
0x1800425d4  cmp     byte ptr [rcx+19h], 2
0x1800425d8  jb      short loc_1800425F6
0x1800425da  mov     edx, 22h ; '"'
0x1800425df  mov     r9d, 80041006h
0x1800425e5  lea     r8, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids
0x1800425ec  mov     rcx, [rcx+10h]
0x1800425f0  call    WPP_SF_d
0x1800425f5  nop
0x1800425f6  mov     eax, 80041006h
0x1800425fb  jmp     loc_1800423B3
0x180042600  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042606  mov     edx, 80041006h
0x18004260b  mov     rcx, rax
0x18004260e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042614  mov     rcx, cs:WPP_GLOBAL_Control
0x18004261b  cmp     rcx, r13
0x18004261e  jz      short loc_180042648
0x180042620  test    byte ptr [rcx+1Ch], 1
0x180042624  jz      short loc_180042648
0x180042626  cmp     byte ptr [rcx+19h], 2
0x18004262a  jb      short loc_180042648
0x18004262c  mov     edx, 23h ; '#'
0x180042631  mov     r9d, 80041006h
0x180042637  lea     r8, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids
0x18004263e  mov     rcx, [rcx+10h]
0x180042642  call    WPP_SF_d
0x180042647  nop
0x180042648  mov     eax, 80041006h
0x18004264d  jmp     loc_1800423B3
0x180042652  test    ecx, ecx
0x180042654  jnz     loc_180042404
0x18004265a  mov     rcx, r14
0x18004265d  call    cs:__imp_?Leave@CCritSec@@QEAAXXZ; CCritSec::Leave(void)
0x180042663  mov     [rsp+78h+var_50], r12d
0x180042668  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004266e  mov     edx, 80041001h
0x180042673  mov     rcx, rax
0x180042676  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004267c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042683  cmp     rcx, r13
0x180042686  jz      short loc_1800426B0
0x180042688  test    byte ptr [rcx+1Ch], 1
0x18004268c  jz      short loc_1800426B0
0x18004268e  cmp     byte ptr [rcx+19h], 2
0x180042692  jb      short loc_1800426B0
0x180042694  mov     edx, 25h ; '%'
0x180042699  mov     r9d, 80041001h
0x18004269f  lea     r8, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids
0x1800426a6  mov     rcx, [rcx+10h]
0x1800426aa  call    WPP_SF_d
0x1800426af  nop
0x1800426b0  mov     eax, 80041001h
0x1800426b5  jmp     loc_1800423B3
0x1800426ba  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800426c0  mov     edx, 80041006h
0x1800426c5  mov     rcx, rax
0x1800426c8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800426ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800426d5  cmp     rcx, r13
0x1800426d8  jz      loc_18004255A
0x1800426de  test    byte ptr [rcx+1Ch], 1
0x1800426e2  jz      loc_18004255A
0x1800426e8  cmp     byte ptr [rcx+19h], 2
0x1800426ec  jb      loc_18004255A
0x1800426f2  mov     edx, 26h ; '&'
0x1800426f7  mov     r9d, 80041006h
0x1800426fd  lea     r8, WPP_28e29f57241430ec241c0d1bcbeea381_Traceguids
0x180042704  mov     rcx, [rcx+10h]
0x180042708  call    WPP_SF_d
0x18004270d  jmp     loc_18004255A
0x180042712  mov     rcx, r14
0x180042715  call    cs:__imp_?Leave@CCritSec@@QEAAXXZ; CCritSec::Leave(void)
0x18004271b  jmp     loc_180042562
0x180042720  mov     rax, [rsi]
0x180042723  mov     rdx, r15
0x180042726  mov     rcx, rsi
0x180042729  mov     rax, [rax+98h]
0x180042730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042735  mov     rax, [rsi]
0x180042738  mov     r8b, 1
0x18004273b  mov     rdx, r15
0x18004273e  mov     rcx, rsi
0x180042741  mov     rax, [rax+38h]
0x180042745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004274a  test    eax, eax
0x18004274c  jz      loc_18004242B
0x180042752  xor     edx, edx; int
0x180042754  mov     rcx, rsi; this
0x180042757  call    ?CreateNewThread@CCoreQueue@@MEAAHH@Z; CCoreQueue::CreateNewThread(int)
0x18004275c  test    eax, eax
0x18004275e  jnz     loc_18004242B
0x180042764  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004276a  mov     edx, 80041006h
0x18004276f  mov     rcx, rax
0x180042772  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042778  mov     rcx, cs:WPP_GLOBAL_Control
0x18004277f  cmp     rcx, r13
0x180042782  jz      loc_18004256C
  ... truncated ...
```
