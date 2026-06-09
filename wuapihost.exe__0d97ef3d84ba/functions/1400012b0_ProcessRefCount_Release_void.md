# ProcessRefCount::Release(void)

- ea: `0x1400012b0`
- end: `0x140001324`
- name: `?Release@ProcessRefCount@@UEAAKXZ`
- size: `116`
- prototype: `unsigned int __fastcall(ProcessRefCount *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400012b0`
- `0x140001500`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1400012f8`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1400012f8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400012f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400012f2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140001309`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140001309`

## pseudocode

```c
__int64 __fastcall ProcessRefCount::Release(ProcessRefCount *this)
{
  unsigned __int32 v1; // ebx
  struct _TP_TIMER *v2; // rax
  void *v3; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 )
  {
    v2 = (struct _TP_TIMER *)*((_QWORD *)this + 3);
    if ( v2 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v2, &pftDueTime, 0, 0);
      CoFreeUnusedLibraries();
    }
    else
    {
      v3 = (void *)*((_QWORD *)this + 2);
      if ( v3 )
        SetEvent(v3);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1400012b0  push    rbx
0x1400012b2  sub     rsp, 30h
0x1400012b6  mov     rax, cs:__security_cookie
0x1400012bd  xor     rax, rsp
0x1400012c0  mov     [rsp+38h+var_10], rax
0x1400012c5  or      ebx, 0FFFFFFFFh
0x1400012c8  lock xadd [rcx+8], ebx
0x1400012cd  sub     ebx, 1
0x1400012d0  jnz     short loc_14000130F
0x1400012d2  mov     rax, [rcx+18h]
0x1400012d6  test    rax, rax
0x1400012d9  jz      short loc_140001300
0x1400012db  xor     r9d, r9d; msWindowLength
0x1400012de  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1400012e7  xor     r8d, r8d; msPeriod
0x1400012ea  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1400012ef  mov     rcx, rax; pti
0x1400012f2  call    cs:__imp_SetThreadpoolTimer
0x1400012f8  call    cs:__imp_CoFreeUnusedLibraries
0x1400012fe  jmp     short loc_14000130F
0x140001300  mov     rcx, [rcx+10h]; hEvent
0x140001304  test    rcx, rcx
0x140001307  jz      short loc_14000130F
0x140001309  call    cs:__imp_SetEvent
0x14000130f  mov     eax, ebx
0x140001311  mov     rcx, [rsp+38h+var_10]
0x140001316  xor     rcx, rsp; StackCookie
0x140001319  call    __security_check_cookie
0x14000131e  add     rsp, 30h
0x140001322  pop     rbx
0x140001323  retn
```
