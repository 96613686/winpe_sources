# CMultipleIPThrottleByTime::~CMultipleIPThrottleByTime(void)

- ea: `0x1800316bc`
- end: `0x18003172f`
- name: `??1CMultipleIPThrottleByTime@@QEAA@XZ`
- size: `115`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180030590`

## callees

- `0x1800307dc`
- `0x1800316bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800316f0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031706`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031715`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800316f0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031706`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031715`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031728`

## pseudocode

```c
void __fastcall CMultipleIPThrottleByTime::~CMultipleIPThrottleByTime(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2)
{
  __int64 i; // rbp
  CSingleThrottleByTime *v4; // rcx
  void *v5; // rcx
  HANDLE LockSemaphore; // rcx
  void *SpinCount; // rcx

  for ( i = 0; (unsigned int)i < this[1].LockCount; i = (unsigned int)(i + 1) )
  {
    v4 = *(CSingleThrottleByTime **)(this[1].SpinCount + 8 * i);
    if ( v4 )
      CSingleThrottleByTime::`scalar deleting destructor'(v4, a2);
    v5 = (void *)*((_QWORD *)this[1].LockSemaphore + i);
    if ( v5 )
      free(v5);
  }
  LockSemaphore = this[1].LockSemaphore;
  if ( LockSemaphore )
    free(LockSemaphore);
  SpinCount = (void *)this[1].SpinCount;
  if ( SpinCount )
    free(SpinCount);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1800316bc  push    rbx
0x1800316be  push    rbp
0x1800316bf  push    rsi
0x1800316c0  push    rdi
0x1800316c1  push    r14
0x1800316c3  sub     rsp, 20h
0x1800316c7  xor     ebp, ebp
0x1800316c9  mov     rbx, rcx
0x1800316cc  cmp     [rcx+30h], ebp
0x1800316cf  jbe     short loc_1800316FD
0x1800316d1  mov     rax, [rbx+48h]
0x1800316d5  mov     rcx, [rax+rbp*8]; this
0x1800316d9  test    rcx, rcx
0x1800316dc  jz      short loc_1800316E3
0x1800316de  call    ??_GCSingleThrottleByTime@@QEAAPEAXI@Z; CSingleThrottleByTime::`scalar deleting destructor'(uint)
0x1800316e3  mov     rax, [rbx+40h]
0x1800316e7  mov     rcx, [rax+rbp*8]; Block
0x1800316eb  test    rcx, rcx
0x1800316ee  jz      short loc_1800316F6
0x1800316f0  call    cs:__imp_free
0x1800316f6  inc     ebp
0x1800316f8  cmp     ebp, [rbx+30h]
0x1800316fb  jb      short loc_1800316D1
0x1800316fd  mov     rcx, [rbx+40h]; Block
0x180031701  test    rcx, rcx
0x180031704  jz      short loc_18003170C
0x180031706  call    cs:__imp_free
0x18003170c  mov     rcx, [rbx+48h]; Block
0x180031710  test    rcx, rcx
0x180031713  jz      short loc_18003171B
0x180031715  call    cs:__imp_free
0x18003171b  mov     rcx, rbx
0x18003171e  add     rsp, 20h
0x180031722  pop     r14
0x180031724  pop     rdi
0x180031725  pop     rsi
0x180031726  pop     rbp
0x180031727  pop     rbx
0x180031728  jmp     cs:__imp_DeleteCriticalSection
```
