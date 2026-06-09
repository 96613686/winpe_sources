# PxeRequest::Release(void)

- ea: `0x180006368`
- end: `0x180006427`
- name: `?Release@PxeRequest@@QEAAKXZ`
- size: `191`
- prototype: `__int64 __fastcall(PxeRequest *this)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005aa4`
- `0x180007060`
- `0x1800076b0`

## callees

- `0x180006368`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800063ed`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800063ed`
- `KERNEL32!InterlockedPushEntrySList` at `0x180006405`
- `KERNEL32!InterlockedPushEntrySList` at `0x180006405`

## pseudocode

```c
__int64 __fastcall PxeRequest::Release(PxeRequest *this)
{
  unsigned __int32 v1; // ebx
  __int64 v2; // rdi

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 43);
  if ( v1 == 1 )
  {
    v2 = *((_QWORD *)this + 22);
    *(_OWORD *)((char *)this + 72) = 0;
    *((_QWORD *)this + 11) = 0;
    *((_DWORD *)this + 24) = 0;
    *(_OWORD *)((char *)this + 100) = 0;
    *(_QWORD *)((char *)this + 116) = 0;
    *(_QWORD *)((char *)this + 124) = 0;
    *(_OWORD *)this = 0;
    *((_OWORD *)this + 1) = 0;
    *((_OWORD *)this + 2) = 0;
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 17) = 0;
    *((_QWORD *)this + 20) = 0;
    *((_QWORD *)this + 8) = 0;
    *((_DWORD *)this + 14) = 0;
    *((_QWORD *)this + 18) = 0;
    *((_DWORD *)this + 42) = 0;
    *((_QWORD *)this + 19) = 0;
    if ( (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 16), 0) <= *(_DWORD *)(v2 + 36) )
    {
      InterlockedPushEntrySList((PSLIST_HEADER)v2, (PSLIST_ENTRY)this + 13);
      _InterlockedIncrement((volatile signed __int32 *)(v2 + 16));
    }
    else
    {
      operator delete(this);
    }
    _InterlockedDecrement((volatile signed __int32 *)(v2 + 32));
  }
  return v1;
}

```

## disassembly

```asm
0x180006368  mov     [rsp+arg_0], rbx
0x18000636d  push    rdi
0x18000636e  sub     rsp, 20h
0x180006372  or      ebx, 0FFFFFFFFh
0x180006375  lock xadd [rcx+0ACh], ebx
0x18000637d  dec     ebx
0x18000637f  cmp     ebx, 1
0x180006382  jnz     loc_180006419
0x180006388  mov     rdi, [rcx+0B0h]
0x18000638f  xor     eax, eax
0x180006391  xorps   xmm0, xmm0
0x180006394  movups  xmmword ptr [rcx+48h], xmm0
0x180006398  mov     [rcx+58h], rax
0x18000639c  mov     [rcx+60h], eax
0x18000639f  movups  xmmword ptr [rcx+64h], xmm0
0x1800063a3  mov     [rcx+74h], rax
0x1800063a7  mov     [rcx+7Ch], rax
0x1800063ab  movups  xmmword ptr [rcx], xmm0
0x1800063ae  movups  xmmword ptr [rcx+10h], xmm0
0x1800063b2  movups  xmmword ptr [rcx+20h], xmm0
0x1800063b6  mov     [rcx+30h], rax
0x1800063ba  mov     [rcx+88h], rax
0x1800063c1  mov     [rcx+0A0h], rax
0x1800063c8  mov     [rcx+40h], rax
0x1800063cc  mov     [rcx+38h], eax
0x1800063cf  mov     [rcx+90h], rax
0x1800063d6  mov     [rcx+0A8h], eax
0x1800063dc  mov     [rcx+98h], rax
0x1800063e3  lock xadd [rdi+10h], eax
0x1800063e8  cmp     eax, [rdi+24h]
0x1800063eb  jbe     short loc_1800063FB
0x1800063ed  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800063f4  nop     dword ptr [rax+rax+00h]
0x1800063f9  jmp     short loc_180006415
0x1800063fb  lea     rdx, [rcx+0D0h]; ListEntry
0x180006402  mov     rcx, rdi; ListHead
0x180006405  call    cs:__imp_InterlockedPushEntrySList
0x18000640c  nop     dword ptr [rax+rax+00h]
0x180006411  lock inc dword ptr [rdi+10h]
0x180006415  lock dec dword ptr [rdi+20h]
0x180006419  mov     eax, ebx
0x18000641b  mov     rbx, [rsp+28h+arg_0]
0x180006420  add     rsp, 20h
0x180006424  pop     rdi
0x180006425  retn
```
