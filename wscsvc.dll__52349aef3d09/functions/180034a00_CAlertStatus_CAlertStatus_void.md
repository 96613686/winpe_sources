# CAlertStatus::~CAlertStatus(void)

- ea: `0x180034a00`
- end: `0x180034a7c`
- name: `??1CAlertStatus@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001cb1c`

## callees

- `0x180020198`
- `0x1800221e8`
- `0x180029e74`
- `0x180034a00`
- `0x180034a84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034a13`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034a13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034a45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034a45`

## pseudocode

```c
void __fastcall CAlertStatus::~CAlertStatus(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rcx
  HANDLE *Next; // rbx
  HANDLE v4; // rcx
  __int64 HeadPosition; // [rsp+30h] [rbp+8h] BYREF

  if ( LODWORD(this[1].DebugInfo) )
    DeleteCriticalSection(this);
  LockSemaphore = this[1].LockSemaphore;
  if ( LockSemaphore )
  {
    HeadPosition = CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::GetHeadPosition(LockSemaphore);
    while ( HeadPosition )
    {
      Next = (HANDLE *)CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::GetNext(
                         this[1].LockSemaphore,
                         &HeadPosition);
      CloseHandle(*Next);
      operator delete(Next);
    }
    v4 = this[1].LockSemaphore;
    if ( v4 )
      CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::`scalar deleting destructor'(v4);
    this[1].LockSemaphore = 0;
  }
}

```

## disassembly

```asm
0x180034a00  mov     [rsp+arg_8], rbx
0x180034a05  push    rdi
0x180034a06  sub     rsp, 20h
0x180034a0a  cmp     dword ptr [rcx+28h], 0
0x180034a0e  mov     rdi, rcx
0x180034a11  jz      short loc_180034A19
0x180034a13  call    cs:__imp_DeleteCriticalSection
0x180034a19  mov     rcx, [rdi+40h]
0x180034a1d  test    rcx, rcx
0x180034a20  jz      short loc_180034A71
0x180034a22  call    ?GetHeadPosition@?$CList@PEAUSTATUSCHANGENOTIFICATION@@PEAU1@@@QEBAPEAU_CListElement@@XZ; CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::GetHeadPosition(void)
0x180034a27  mov     [rsp+28h+arg_0], rax
0x180034a2c  test    rax, rax
0x180034a2f  jz      short loc_180034A5B
0x180034a31  mov     rcx, [rdi+40h]
0x180034a35  lea     rdx, [rsp+28h+arg_0]
0x180034a3a  call    ?GetNext@?$CList@PEAUSTATUSCHANGENOTIFICATION@@PEAU1@@@QEAAPEAUSTATUSCHANGENOTIFICATION@@AEAPEAU_CListElement@@@Z; CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::GetNext(_CListElement * &)
0x180034a3f  mov     rbx, rax
0x180034a42  mov     rcx, [rax]; hObject
0x180034a45  call    cs:__imp_CloseHandle
0x180034a4b  mov     rcx, rbx; Block
0x180034a4e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034a53  cmp     [rsp+28h+arg_0], 0
0x180034a59  jnz     short loc_180034A31
0x180034a5b  mov     rcx, [rdi+40h]; Block
0x180034a5f  test    rcx, rcx
0x180034a62  jz      short loc_180034A69
0x180034a64  call    ??_G?$CList@PEAUSTATUSCHANGENOTIFICATION@@PEAU1@@@QEAAPEAXI@Z; CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::`scalar deleting destructor'(uint)
0x180034a69  mov     qword ptr [rdi+40h], 0
0x180034a71  mov     rbx, [rsp+28h+arg_8]
0x180034a76  add     rsp, 20h
0x180034a7a  pop     rdi
0x180034a7b  retn
```
