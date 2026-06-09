# CHttp2::QueueReceiveProcessing(void)

- ea: `0x1800663cc`
- end: `0x18006644c`
- name: `?QueueReceiveProcessing@CHttp2@@AEAAXXZ`
- size: `128`
- prototype: `void __fastcall(CHttp2 *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002f864`

## callees

- `0x18002eaf4`
- `0x1800663cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800663ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800663ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006642f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006642f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180066417`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180066417`

## pseudocode

```c
void __fastcall CHttp2::QueueReceiveProcessing(CHttp2 *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  int v2; // esi

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v2 = 0;
  if ( this != (CHttp2 *)-8LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    v2 = 1;
  }
  if ( (int)CHttp2::IsAborted(this) >= 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)this);
    SubmitThreadpoolWork(*(PTP_WORK *)(*((_QWORD *)this + 30) + 8LL));
  }
  if ( v1 )
  {
    if ( v2 )
      LeaveCriticalSection(v1);
  }
}

```

## disassembly

```asm
0x1800663cc  mov     [rsp+arg_8], rbx
0x1800663d1  mov     [rsp+arg_10], rsi
0x1800663d6  push    rdi
0x1800663d7  sub     rsp, 20h
0x1800663db  lea     rbx, [rcx+8]
0x1800663df  xor     esi, esi
0x1800663e1  mov     rdi, rcx
0x1800663e4  test    rbx, rbx
0x1800663e7  jz      short loc_1800663FD
0x1800663e9  mov     rcx, rbx; lpCriticalSection
0x1800663ec  call    cs:__imp_EnterCriticalSection
0x1800663f3  nop     dword ptr [rax+rax+00h]
0x1800663f8  mov     esi, 1
0x1800663fd  mov     rcx, rdi; this
0x180066400  call    ?IsAborted@CHttp2@@AEAAJXZ; CHttp2::IsAborted(void)
0x180066405  test    eax, eax
0x180066407  js      short loc_180066423
0x180066409  lock inc dword ptr [rdi]
0x18006640c  mov     rcx, [rdi+0F0h]
0x180066413  mov     rcx, [rcx+8]; pwk
0x180066417  call    cs:__imp_SubmitThreadpoolWork
0x18006641e  nop     dword ptr [rax+rax+00h]
0x180066423  test    rbx, rbx
0x180066426  jz      short loc_18006643B
0x180066428  test    esi, esi
0x18006642a  jz      short loc_18006643B
0x18006642c  mov     rcx, rbx; lpCriticalSection
0x18006642f  call    cs:__imp_LeaveCriticalSection
0x180066436  nop     dword ptr [rax+rax+00h]
0x18006643b  mov     rbx, [rsp+28h+arg_8]
0x180066440  mov     rsi, [rsp+28h+arg_10]
0x180066445  add     rsp, 20h
0x180066449  pop     rdi
0x18006644a  retn
```
