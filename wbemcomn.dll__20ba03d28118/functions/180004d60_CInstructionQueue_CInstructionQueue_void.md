# CInstructionQueue::CInstructionQueue(void)

- ea: `0x180004d60`
- end: `0x180004e03`
- name: `??0CInstructionQueue@@QEAA@XZ`
- size: `163`
- prototype: `CInstructionQueue *__fastcall(CInstructionQueue *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004e10`

## callees

- `0x180004d60`
- `0x180005690`
- `0x180014120`
- `0x18002ca74`
- `0x18002ee7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004d8f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004d8f`

## pseudocode

```c
CInstructionQueue *__fastcall CInstructionQueue::CInstructionQueue(CInstructionQueue *this)
{
  HANDLE EventW; // rax
  char pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  *(_QWORD *)this = 0;
  CCritSec::CCritSec((CInstructionQueue *)((char *)this + 8));
  *((_DWORD *)this + 14) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 6) = EventW;
  if ( !EventW )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_80c4de501dd43dae8cc7ac2b25a53ef7_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180004d60  mov     [rsp+arg_0], rcx
0x180004d65  push    rbx
0x180004d66  sub     rsp, 20h
0x180004d6a  mov     rbx, rcx
0x180004d6d  mov     qword ptr [rcx], 0
0x180004d74  add     rcx, 8; this
0x180004d78  call    ??0CCritSec@@QEAA@XZ; CCritSec::CCritSec(void)
0x180004d7d  nop
0x180004d7e  mov     dword ptr [rbx+38h], 0
0x180004d85  xor     r9d, r9d; lpName
0x180004d88  xor     r8d, r8d; bInitialState
0x180004d8b  xor     edx, edx; bManualReset
0x180004d8d  xor     ecx, ecx; lpEventAttributes
0x180004d8f  call    cs:__imp_CreateEventW
0x180004d95  mov     [rbx+30h], rax
0x180004d99  test    rax, rax
0x180004d9c  jnz     short loc_180004DFA
0x180004d9e  lea     edx, [rax-2]; int
0x180004da1  lea     rcx, qword_18006A9C0; this
0x180004da8  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180004dad  lea     rax, WPP_GLOBAL_Control
0x180004db4  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dbb  cmp     rcx, rax
0x180004dbe  jz      short loc_180004DE8
0x180004dc0  test    byte ptr [rcx+1Ch], 1
0x180004dc4  jz      short loc_180004DE8
0x180004dc6  cmp     byte ptr [rcx+19h], 2
0x180004dca  jb      short loc_180004DE8
0x180004dcc  mov     edx, 0Ah
0x180004dd1  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180004dd8  lea     r8, WPP_80c4de501dd43dae8cc7ac2b25a53ef7_Traceguids
0x180004ddf  mov     rcx, [rcx+10h]
0x180004de3  call    WPP_SF_s
0x180004de8  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180004def  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180004df4  call    _CxxThrowException_0
0x180004dfa  mov     rax, rbx
0x180004dfd  add     rsp, 20h
0x180004e01  pop     rbx
0x180004e02  retn
```
