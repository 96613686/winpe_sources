# CWcnEventSink::~CWcnEventSink(void)

- ea: `0x18003be88`
- end: `0x18003bf35`
- name: `??1CWcnEventSink@@QEAA@XZ`
- size: `173`
- prototype: `void __fastcall(CWcnEventSink *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18003a0c8`
- `0x180058d0e`

## callees

- `0x18003be88`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003bebf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003bef9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003bf0a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003bf13`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003bebf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003bef9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003bf0a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003bf13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003be9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003be9c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003bf2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bf1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bf1c`

## pseudocode

```c
void __fastcall CWcnEventSink::~CWcnEventSink(CWcnEventSink *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  _QWORD **v3; // rax
  _QWORD **v4; // r14
  _QWORD *i; // rbx
  void *v6; // rcx
  _QWORD *v7; // rdi
  _QWORD *v8; // rdx
  _QWORD *v9; // rcx
  _QWORD *v10; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v3 = (_QWORD **)*((_QWORD *)this + 10);
  if ( v3 )
  {
    v4 = (_QWORD **)*v3;
    for ( i = (_QWORD *)**v3; i != v4; i = (_QWORD *)*i )
    {
      v6 = (void *)i[2];
      if ( v6 )
        operator delete(v6);
    }
    v7 = (_QWORD *)*((_QWORD *)this + 10);
    if ( v7 )
    {
      v8 = *(_QWORD **)*v7;
      *(_QWORD *)*v7 = *v7;
      *(_QWORD *)(*v7 + 8LL) = *v7;
      v9 = (_QWORD *)*v7;
      v7[1] = 0;
      if ( v8 != v9 )
      {
        do
        {
          v10 = (_QWORD *)*v8;
          operator delete(v8);
          v9 = (_QWORD *)*v7;
          v8 = v10;
        }
        while ( v10 != (_QWORD *)*v7 );
      }
      operator delete(v9);
      operator delete(v7);
    }
  }
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
}

```

## disassembly

```asm
0x18003be88  push    rbx
0x18003be8a  push    rsi
0x18003be8b  push    rdi
0x18003be8c  push    r14
0x18003be8e  sub     rsp, 28h
0x18003be92  lea     rsi, [rcx+18h]
0x18003be96  mov     rdi, rcx
0x18003be99  mov     rcx, rsi; lpCriticalSection
0x18003be9c  call    cs:__imp_EnterCriticalSection
0x18003bea2  mov     rax, [rdi+50h]
0x18003bea6  test    rax, rax
0x18003bea9  jz      short loc_18003BF19
0x18003beab  mov     r14, [rax]
0x18003beae  mov     rbx, [r14]
0x18003beb1  cmp     rbx, r14
0x18003beb4  jz      short loc_18003BECA
0x18003beb6  mov     rcx, [rbx+10h]
0x18003beba  test    rcx, rcx
0x18003bebd  jz      short loc_18003BEC5
0x18003bebf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003bec5  mov     rbx, [rbx]
0x18003bec8  jmp     short loc_18003BEB1
0x18003beca  mov     rdi, [rdi+50h]
0x18003bece  test    rdi, rdi
0x18003bed1  jz      short loc_18003BF19
0x18003bed3  mov     rax, [rdi]
0x18003bed6  mov     rdx, [rax]
0x18003bed9  mov     [rax], rax
0x18003bedc  mov     rax, [rdi]
0x18003bedf  mov     [rax+8], rax
0x18003bee3  mov     rcx, [rdi]
0x18003bee6  mov     qword ptr [rdi+8], 0
0x18003beee  cmp     rdx, rcx
0x18003bef1  jz      short loc_18003BF0A
0x18003bef3  mov     rbx, [rdx]
0x18003bef6  mov     rcx, rdx
0x18003bef9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003beff  mov     rcx, [rdi]
0x18003bf02  mov     rdx, rbx
0x18003bf05  cmp     rbx, rcx
0x18003bf08  jnz     short loc_18003BEF3
0x18003bf0a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003bf10  mov     rcx, rdi
0x18003bf13  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003bf19  mov     rcx, rsi; lpCriticalSection
0x18003bf1c  call    cs:__imp_LeaveCriticalSection
0x18003bf22  mov     rcx, rsi
0x18003bf25  add     rsp, 28h
0x18003bf29  pop     r14
0x18003bf2b  pop     rdi
0x18003bf2c  pop     rsi
0x18003bf2d  pop     rbx
0x18003bf2e  jmp     cs:__imp_DeleteCriticalSection
```
