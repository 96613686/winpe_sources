# CWcnMessageSinkManager::~CWcnMessageSinkManager(void)

- ea: `0x18003b174`
- end: `0x18003b1e5`
- name: `??1CWcnMessageSinkManager@@QEAA@XZ`
- size: `113`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002e04`
- `0x180057323`

## callees

- `0x18003b174`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003b1ba`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003b1cb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003b1d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003b1ba`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003b1cb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003b1d4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b185`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b185`

## pseudocode

```c
void __fastcall CWcnMessageSinkManager::~CWcnMessageSinkManager(struct _RTL_CRITICAL_SECTION *this)
{
  _QWORD *SpinCount; // rdi
  _QWORD *v3; // rdx
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx

  DeleteCriticalSection(this + 2);
  SpinCount = (_QWORD *)this[1].SpinCount;
  if ( SpinCount )
  {
    v3 = *(_QWORD **)*SpinCount;
    *(_QWORD *)*SpinCount = *SpinCount;
    *(_QWORD *)(*SpinCount + 8LL) = *SpinCount;
    v4 = (_QWORD *)*SpinCount;
    SpinCount[1] = 0;
    if ( v3 != v4 )
    {
      do
      {
        v5 = (_QWORD *)*v3;
        operator delete(v3);
        v4 = (_QWORD *)*SpinCount;
        v3 = v5;
      }
      while ( v5 != (_QWORD *)*SpinCount );
    }
    operator delete(v4);
    operator delete(SpinCount);
  }
}

```

## disassembly

```asm
0x18003b174  mov     [rsp+arg_0], rbx
0x18003b179  push    rdi
0x18003b17a  sub     rsp, 20h
0x18003b17e  mov     rbx, rcx
0x18003b181  add     rcx, 50h ; 'P'; lpCriticalSection
0x18003b185  call    cs:__imp_DeleteCriticalSection
0x18003b18b  mov     rdi, [rbx+48h]
0x18003b18f  test    rdi, rdi
0x18003b192  jz      short loc_18003B1DA
0x18003b194  mov     rax, [rdi]
0x18003b197  mov     rdx, [rax]
0x18003b19a  mov     [rax], rax
0x18003b19d  mov     rax, [rdi]
0x18003b1a0  mov     [rax+8], rax
0x18003b1a4  mov     rcx, [rdi]
0x18003b1a7  mov     qword ptr [rdi+8], 0
0x18003b1af  cmp     rdx, rcx
0x18003b1b2  jz      short loc_18003B1CB
0x18003b1b4  mov     rbx, [rdx]
0x18003b1b7  mov     rcx, rdx
0x18003b1ba  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003b1c0  mov     rcx, [rdi]
0x18003b1c3  mov     rdx, rbx
0x18003b1c6  cmp     rbx, rcx
0x18003b1c9  jnz     short loc_18003B1B4
0x18003b1cb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003b1d1  mov     rcx, rdi
0x18003b1d4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003b1da  mov     rbx, [rsp+28h+arg_0]
0x18003b1df  add     rsp, 20h
0x18003b1e3  pop     rdi
0x18003b1e4  retn
```
