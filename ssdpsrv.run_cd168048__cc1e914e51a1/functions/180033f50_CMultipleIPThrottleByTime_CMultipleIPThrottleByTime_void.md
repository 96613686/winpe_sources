# CMultipleIPThrottleByTime::~CMultipleIPThrottleByTime(void)

- ea: `0x180033f50`
- end: `0x180033fda`
- name: `??1CMultipleIPThrottleByTime@@QEAA@XZ`
- size: `138`
- prototype: `void __fastcall(CMultipleIPThrottleByTime *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180032914`

## callees

- `0x180032b9c`
- `0x180033f50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033f84`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033fa0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033fb5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033f84`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033fa0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033fb5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033fce`

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
0x180033f50  push    rbx
0x180033f52  push    rbp
0x180033f53  push    rsi
0x180033f54  push    rdi
0x180033f55  push    r14
0x180033f57  sub     rsp, 20h
0x180033f5b  xor     ebp, ebp
0x180033f5d  mov     rbx, rcx
0x180033f60  cmp     [rcx+30h], ebp
0x180033f63  jbe     short loc_180033F97
0x180033f65  mov     rax, [rbx+48h]
0x180033f69  mov     rcx, [rax+rbp*8]; this
0x180033f6d  test    rcx, rcx
0x180033f70  jz      short loc_180033F77
0x180033f72  call    ??_GCSingleThrottleByTime@@QEAAPEAXI@Z; CSingleThrottleByTime::`scalar deleting destructor'(uint)
0x180033f77  mov     rax, [rbx+40h]
0x180033f7b  mov     rcx, [rax+rbp*8]; Block
0x180033f7f  test    rcx, rcx
0x180033f82  jz      short loc_180033F90
0x180033f84  call    cs:__imp_free
0x180033f8b  nop     dword ptr [rax+rax+00h]
0x180033f90  inc     ebp
0x180033f92  cmp     ebp, [rbx+30h]
0x180033f95  jb      short loc_180033F65
0x180033f97  mov     rcx, [rbx+40h]; Block
0x180033f9b  test    rcx, rcx
0x180033f9e  jz      short loc_180033FAC
0x180033fa0  call    cs:__imp_free
0x180033fa7  nop     dword ptr [rax+rax+00h]
0x180033fac  mov     rcx, [rbx+48h]; Block
0x180033fb0  test    rcx, rcx
0x180033fb3  jz      short loc_180033FC1
0x180033fb5  call    cs:__imp_free
0x180033fbc  nop     dword ptr [rax+rax+00h]
0x180033fc1  mov     rcx, rbx
0x180033fc4  add     rsp, 20h
0x180033fc8  pop     r14
0x180033fca  pop     rdi
0x180033fcb  pop     rsi
0x180033fcc  pop     rbp
0x180033fcd  pop     rbx
0x180033fce  jmp     cs:__imp_DeleteCriticalSection
```
