# CHaltable::CHaltable(void)

- ea: `0x180004ef0`
- end: `0x180004f9f`
- name: `??0CHaltable@@QEAA@XZ`
- size: `175`
- prototype: `CHaltable *__fastcall(CHaltable *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004e10`

## callees

- `0x180004ef0`
- `0x180005690`
- `0x180014120`
- `0x18002ca74`
- `0x18002ee7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004f2b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004f2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CHaltable *__fastcall CHaltable::CHaltable(CHaltable *this)
{
  HANDLE EventW; // rax
  char pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  *(_QWORD *)this = &CHaltable::`vftable';
  CCritSec::CCritSec((CHaltable *)((char *)this + 8));
  *((_DWORD *)this + 14) = 0;
  *((_DWORD *)this + 15) = 1;
  EventW = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)this + 6) = EventW;
  if ( !EventW )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_b7677a1132d13023803cac494ba58666_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180004ef0  mov     [rsp+arg_0], rcx
0x180004ef5  push    rbx
0x180004ef6  sub     rsp, 20h
0x180004efa  mov     rbx, rcx
0x180004efd  lea     rax, ??_7CHaltable@@6B@; const CHaltable::`vftable'
0x180004f04  mov     [rcx], rax
0x180004f07  add     rcx, 8; this
0x180004f0b  call    ??0CCritSec@@QEAA@XZ; CCritSec::CCritSec(void)
0x180004f10  nop
0x180004f11  mov     dword ptr [rbx+38h], 0
0x180004f18  mov     dword ptr [rbx+3Ch], 1
0x180004f1f  xor     r9d, r9d; lpName
0x180004f22  lea     edx, [r9+1]; bManualReset
0x180004f26  xor     ecx, ecx; lpEventAttributes
0x180004f28  mov     r8d, edx; bInitialState
0x180004f2b  call    cs:__imp_CreateEventW
0x180004f31  mov     [rbx+30h], rax
0x180004f35  test    rax, rax
0x180004f38  jnz     short loc_180004F96
0x180004f3a  lea     edx, [rax-2]; int
0x180004f3d  lea     rcx, unk_18006A9C0; this
0x180004f44  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180004f49  lea     rax, WPP_GLOBAL_Control
0x180004f50  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f57  cmp     rcx, rax
0x180004f5a  jz      short loc_180004F84
0x180004f5c  test    byte ptr [rcx+1Ch], 1
0x180004f60  jz      short loc_180004F84
0x180004f62  cmp     byte ptr [rcx+19h], 2
0x180004f66  jb      short loc_180004F84
0x180004f68  mov     edx, 0Ah
0x180004f6d  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180004f74  lea     r8, WPP_b7677a1132d13023803cac494ba58666_Traceguids
0x180004f7b  mov     rcx, [rcx+10h]
0x180004f7f  call    WPP_SF_s
0x180004f84  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180004f8b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180004f90  call    _CxxThrowException_0
0x180004f96  mov     rax, rbx
0x180004f99  add     rsp, 20h
0x180004f9d  pop     rbx
0x180004f9e  retn
```
