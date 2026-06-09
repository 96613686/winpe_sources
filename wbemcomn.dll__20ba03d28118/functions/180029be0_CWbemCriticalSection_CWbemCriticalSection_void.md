# CWbemCriticalSection::CWbemCriticalSection(void)

- ea: `0x180029be0`
- end: `0x180029c7f`
- name: `??0CWbemCriticalSection@@QEAA@XZ`
- size: `159`
- prototype: `CWbemCriticalSection *__fastcall(CWbemCriticalSection *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180014120`
- `0x180029be0`
- `0x18002ca74`
- `0x18002ee7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029c09`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029c09`

## pseudocode

```c
CWbemCriticalSection *__fastcall CWbemCriticalSection::CWbemCriticalSection(CWbemCriticalSection *this)
{
  HANDLE EventW; // rax
  char pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  *(_DWORD *)this = -1;
  *(_QWORD *)((char *)this + 4) = 0;
  *((_QWORD *)this + 2) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 2) = EventW;
  if ( !EventW )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_b7677a1132d13023803cac494ba58666_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180029be0  push    rbx
0x180029be2  sub     rsp, 20h
0x180029be6  mov     rbx, rcx
0x180029be9  mov     dword ptr [rcx], 0FFFFFFFFh
0x180029bef  mov     qword ptr [rcx+4], 0
0x180029bf7  xor     r9d, r9d; lpName
0x180029bfa  mov     qword ptr [rcx+10h], 0
0x180029c02  xor     r8d, r8d; bInitialState
0x180029c05  xor     ecx, ecx; lpEventAttributes
0x180029c07  xor     edx, edx; bManualReset
0x180029c09  call    cs:__imp_CreateEventW
0x180029c0f  mov     [rbx+10h], rax
0x180029c13  test    rax, rax
0x180029c16  jz      short loc_180029C21
0x180029c18  mov     rax, rbx
0x180029c1b  add     rsp, 20h
0x180029c1f  pop     rbx
0x180029c20  retn
0x180029c21  mov     edx, 0FFFFFFFEh; int
0x180029c26  lea     rcx, qword_18006A9C0; this
0x180029c2d  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180029c32  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c39  lea     rax, WPP_GLOBAL_Control
0x180029c40  cmp     rcx, rax
0x180029c43  jz      short loc_180029C6D
0x180029c45  test    byte ptr [rcx+1Ch], 1
0x180029c49  jz      short loc_180029C6D
0x180029c4b  cmp     byte ptr [rcx+19h], 2
0x180029c4f  jb      short loc_180029C6D
0x180029c51  mov     rcx, [rcx+10h]
0x180029c55  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180029c5c  mov     edx, 0Bh
0x180029c61  lea     r8, WPP_b7677a1132d13023803cac494ba58666_Traceguids
0x180029c68  call    WPP_SF_s
0x180029c6d  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180029c74  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180029c79  call    _CxxThrowException_0
```
