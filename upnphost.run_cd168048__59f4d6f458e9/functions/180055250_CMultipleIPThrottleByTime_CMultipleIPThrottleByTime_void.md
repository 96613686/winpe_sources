# CMultipleIPThrottleByTime::~CMultipleIPThrottleByTime(void)

- ea: `0x180055250`
- end: `0x1800552da`
- name: `??1CMultipleIPThrottleByTime@@QEAA@XZ`
- size: `138`
- prototype: `void __fastcall(CMultipleIPThrottleByTime *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800543bc`

## callees

- `0x18005463c`
- `0x180055250`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180055284`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800552a0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800552b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180055284`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800552a0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800552b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800552ce`

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
0x180055250  push    rbx
0x180055252  push    rbp
0x180055253  push    rsi
0x180055254  push    rdi
0x180055255  push    r14
0x180055257  sub     rsp, 20h
0x18005525b  xor     ebp, ebp
0x18005525d  mov     rbx, rcx
0x180055260  cmp     [rcx+30h], ebp
0x180055263  jbe     short loc_180055297
0x180055265  mov     rax, [rbx+48h]
0x180055269  mov     rcx, [rax+rbp*8]; this
0x18005526d  test    rcx, rcx
0x180055270  jz      short loc_180055277
0x180055272  call    ??_GCSingleThrottleByTime@@QEAAPEAXI@Z; CSingleThrottleByTime::`scalar deleting destructor'(uint)
0x180055277  mov     rax, [rbx+40h]
0x18005527b  mov     rcx, [rax+rbp*8]; Block
0x18005527f  test    rcx, rcx
0x180055282  jz      short loc_180055290
0x180055284  call    cs:__imp_free
0x18005528b  nop     dword ptr [rax+rax+00h]
0x180055290  inc     ebp
0x180055292  cmp     ebp, [rbx+30h]
0x180055295  jb      short loc_180055265
0x180055297  mov     rcx, [rbx+40h]; Block
0x18005529b  test    rcx, rcx
0x18005529e  jz      short loc_1800552AC
0x1800552a0  call    cs:__imp_free
0x1800552a7  nop     dword ptr [rax+rax+00h]
0x1800552ac  mov     rcx, [rbx+48h]; Block
0x1800552b0  test    rcx, rcx
0x1800552b3  jz      short loc_1800552C1
0x1800552b5  call    cs:__imp_free
0x1800552bc  nop     dword ptr [rax+rax+00h]
0x1800552c1  mov     rcx, rbx
0x1800552c4  add     rsp, 20h
0x1800552c8  pop     r14
0x1800552ca  pop     rdi
0x1800552cb  pop     rsi
0x1800552cc  pop     rbp
0x1800552cd  pop     rbx
0x1800552ce  jmp     cs:__imp_DeleteCriticalSection
```
