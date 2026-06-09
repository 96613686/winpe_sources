# UL_APP_POOL::QueryAndLockHandle(void * *)

- ea: `0x180012050`
- end: `0x18001209d`
- name: `?QueryAndLockHandle@UL_APP_POOL@@QEAAPEAXPEAPEAX@Z`
- size: `77`
- prototype: `void *__fastcall(UL_APP_POOL *__hidden this, void **)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180001060`
- `0x18000eef0`
- `0x180011f70`
- `0x1800129e0`
- `0x180014b3c`
- `0x180014bfc`
- `0x180014d64`
- `0x180014e9c`
- `0x180014f7c`
- `0x18001520c`
- `0x180015334`
- `0x180015460`
- `0x180015510`
- `0x180015590`
- `0x180015820`
- `0x1800158e0`
- `0x1800159b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180012084`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180012084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012069`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012069`

## pseudocode

```c
void *__fastcall UL_APP_POOL::QueryAndLockHandle(UL_APP_POOL *this, RTL_SRWLOCK **a2)
{
  _QWORD *v2; // rbx
  RTL_SRWLOCK *v5; // rcx

  v2 = (_QWORD *)*((_QWORD *)this + 1);
  v5 = (RTL_SRWLOCK *)(*v2 + v2[1] * ((unsigned __int64)GetCurrentThreadId() % v2[2]));
  *a2 = v5;
  AcquireSRWLockShared(v5);
  return *(void **)this;
}

```

## disassembly

```asm
0x180012050  mov     [rsp+arg_0], rbx
0x180012055  mov     [rsp+arg_8], rsi
0x18001205a  push    rdi
0x18001205b  sub     rsp, 20h
0x18001205f  mov     rbx, [rcx+8]
0x180012063  mov     rdi, rdx
0x180012066  mov     rsi, rcx
0x180012069  call    cs:__imp_GetCurrentThreadId
0x18001206f  mov     eax, eax
0x180012071  xor     edx, edx
0x180012073  div     qword ptr [rbx+10h]
0x180012077  mov     ecx, edx
0x180012079  imul    rcx, [rbx+8]
0x18001207e  add     rcx, [rbx]; SRWLock
0x180012081  mov     [rdi], rcx
0x180012084  call    cs:__imp_AcquireSRWLockShared
0x18001208a  mov     rax, [rsi]
0x18001208d  mov     rsi, [rsp+28h+arg_8]
0x180012092  mov     rbx, [rsp+28h+arg_0]
0x180012097  add     rsp, 20h
0x18001209b  pop     rdi
0x18001209c  retn
```
