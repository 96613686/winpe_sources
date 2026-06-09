# CExecQueue::CThreadRecord::CThreadRecord(CExecQueue *)

- ea: `0x180016760`
- end: `0x180016804`
- name: `??0CThreadRecord@CExecQueue@@QEAA@PEAV1@@Z`
- size: `164`
- prototype: `__int64 __fastcall(CExecQueue::CThreadRecord *__hidden this, struct CExecQueue *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800161f0`

## callees

- `0x180014120`
- `0x180016760`
- `0x18002ca74`
- `0x18002ee7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001678e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001678e`

## pseudocode

```c
CExecQueue::CThreadRecord *__fastcall CExecQueue::CThreadRecord::CThreadRecord(
        CExecQueue::CThreadRecord *this,
        struct CExecQueue *a2)
{
  HANDLE EventW; // rax
  char pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = a2;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 4) = EventW;
  if ( !EventW )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_8b428a072f23334ffa8fa793348b70d5_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180016760  push    rbx
0x180016762  sub     rsp, 20h
0x180016766  mov     [rcx], rdx
0x180016769  mov     rbx, rcx
0x18001676c  mov     qword ptr [rcx+8], 0
0x180016774  xor     edx, edx; bManualReset
0x180016776  mov     qword ptr [rcx+10h], 0
0x18001677e  xor     r9d, r9d; lpName
0x180016781  mov     qword ptr [rcx+18h], 0
0x180016789  xor     r8d, r8d; bInitialState
0x18001678c  xor     ecx, ecx; lpEventAttributes
0x18001678e  call    cs:__imp_CreateEventW
0x180016794  mov     [rbx+20h], rax
0x180016798  test    rax, rax
0x18001679b  jz      short loc_1800167A6
0x18001679d  mov     rax, rbx
0x1800167a0  add     rsp, 20h
0x1800167a4  pop     rbx
0x1800167a5  retn
0x1800167a6  mov     edx, 0FFFFFFFEh; int
0x1800167ab  lea     rcx, unk_18006A9C0; this
0x1800167b2  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800167b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167be  lea     rax, WPP_GLOBAL_Control
0x1800167c5  cmp     rcx, rax
0x1800167c8  jz      short loc_1800167F2
0x1800167ca  test    byte ptr [rcx+1Ch], 1
0x1800167ce  jz      short loc_1800167F2
0x1800167d0  cmp     byte ptr [rcx+19h], 2
0x1800167d4  jb      short loc_1800167F2
0x1800167d6  mov     rcx, [rcx+10h]
0x1800167da  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800167e1  mov     edx, 0Bh
0x1800167e6  lea     r8, WPP_8b428a072f23334ffa8fa793348b70d5_Traceguids
0x1800167ed  call    WPP_SF_s
0x1800167f2  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800167f9  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800167fe  call    _CxxThrowException_0
```
