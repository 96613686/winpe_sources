# CEventLog::~CEventLog(void)

- ea: `0x180022d40`
- end: `0x180022d99`
- name: `??1CEventLog@@QEAA@XZ`
- size: `89`
- prototype: `void __fastcall(CEventLog *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000ab30`
- `0x180022d40`
- `0x180022da0`
- `0x180022e10`
- `0x180032ac8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022d7d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022d7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CEventLog::~CEventLog(CEventLog *this)
{
  CFlexArray *v2; // rdi

  v2 = (CFlexArray *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    CPointerArray<CEventLogRecord,CUniqueManager<CEventLogRecord>,CFlexArray>::~CPointerArray<CEventLogRecord,CUniqueManager<CEventLogRecord>,CFlexArray>(v2);
    CMUILocale::_Free(v2);
  }
  CEventLog::Close(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  WString::DeleteString(this, *(unsigned __int16 **)this);
}

```

## disassembly

```asm
0x180022d40  mov     [rsp+arg_10], rbx
0x180022d45  mov     [rsp+arg_0], rcx
0x180022d4a  push    rdi
0x180022d4b  sub     rsp, 20h
0x180022d4f  mov     rbx, rcx
0x180022d52  mov     rdi, [rcx+28h]
0x180022d56  mov     [rsp+28h+arg_8], rdi
0x180022d5b  test    rdi, rdi
0x180022d5e  jz      short loc_180022D70
0x180022d60  mov     rcx, rdi; this
0x180022d63  call    ??1?$CPointerArray@VCEventLogRecord@@V?$CUniqueManager@VCEventLogRecord@@@@VCFlexArray@@@@QEAA@XZ; CPointerArray<CEventLogRecord,CUniqueManager<CEventLogRecord>,CFlexArray>::~CPointerArray<CEventLogRecord,CUniqueManager<CEventLogRecord>,CFlexArray>(void)
0x180022d68  mov     rcx, rdi; void *
0x180022d6b  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180022d70  mov     rcx, rbx; this
0x180022d73  call    ?Close@CEventLog@@QEAAHXZ; CEventLog::Close(void)
0x180022d78  nop
0x180022d79  lea     rcx, [rbx+30h]; lpCriticalSection
0x180022d7d  call    cs:__imp_DeleteCriticalSection
0x180022d83  nop
0x180022d84  mov     rdx, [rbx]; unsigned __int16 *
0x180022d87  mov     rcx, rbx; this
0x180022d8a  mov     rbx, [rsp+28h+arg_10]
0x180022d8f  add     rsp, 20h
0x180022d93  pop     rdi
0x180022d94  jmp     ?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
```
