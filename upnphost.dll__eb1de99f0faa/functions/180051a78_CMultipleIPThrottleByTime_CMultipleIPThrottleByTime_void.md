# CMultipleIPThrottleByTime::~CMultipleIPThrottleByTime(void)

- ea: `0x180051a78`
- end: `0x180051aeb`
- name: `??1CMultipleIPThrottleByTime@@QEAA@XZ`
- size: `115`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180050cc0`

## callees

- `0x180050f0c`
- `0x180051a78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051aac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051ac2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051ad1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051aac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051ac2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051ad1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051ae4`

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
0x180051a78  push    rbx
0x180051a7a  push    rbp
0x180051a7b  push    rsi
0x180051a7c  push    rdi
0x180051a7d  push    r14
0x180051a7f  sub     rsp, 20h
0x180051a83  xor     ebp, ebp
0x180051a85  mov     rbx, rcx
0x180051a88  cmp     [rcx+30h], ebp
0x180051a8b  jbe     short loc_180051AB9
0x180051a8d  mov     rax, [rbx+48h]
0x180051a91  mov     rcx, [rax+rbp*8]; this
0x180051a95  test    rcx, rcx
0x180051a98  jz      short loc_180051A9F
0x180051a9a  call    ??_GCSingleThrottleByTime@@QEAAPEAXI@Z; CSingleThrottleByTime::`scalar deleting destructor'(uint)
0x180051a9f  mov     rax, [rbx+40h]
0x180051aa3  mov     rcx, [rax+rbp*8]; Block
0x180051aa7  test    rcx, rcx
0x180051aaa  jz      short loc_180051AB2
0x180051aac  call    cs:__imp_free
0x180051ab2  inc     ebp
0x180051ab4  cmp     ebp, [rbx+30h]
0x180051ab7  jb      short loc_180051A8D
0x180051ab9  mov     rcx, [rbx+40h]; Block
0x180051abd  test    rcx, rcx
0x180051ac0  jz      short loc_180051AC8
0x180051ac2  call    cs:__imp_free
0x180051ac8  mov     rcx, [rbx+48h]; Block
0x180051acc  test    rcx, rcx
0x180051acf  jz      short loc_180051AD7
0x180051ad1  call    cs:__imp_free
0x180051ad7  mov     rcx, rbx
0x180051ada  add     rsp, 20h
0x180051ade  pop     r14
0x180051ae0  pop     rdi
0x180051ae1  pop     rsi
0x180051ae2  pop     rbp
0x180051ae3  pop     rbx
0x180051ae4  jmp     cs:__imp_DeleteCriticalSection
```
