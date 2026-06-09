# cxl::RefCounted::Release(void)

- ea: `0x18001143c`
- end: `0x1800114d5`
- name: `?Release@RefCounted@cxl@@QEBAXXZ`
- size: `153`
- prototype: `void __fastcall(cxl::RefCounted *__hidden this)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180018690`
- `0x18001aa1c`
- `0x18001aa40`
- `0x18001b050`
- `0x18001b160`

## callees

- `0x180002f20`
- `0x18000cbfc`
- `0x18000d184`
- `0x18001143c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001149c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001149c`

## pseudocode

```c
void __fastcall cxl::RefCounted::Release(cxl::RefCounted *this)
{
  __int64 v2; // rdx
  __int64 v3; // rdi
  _BYTE v4[24]; // [rsp+20h] [rbp-18h] BYREF

  if ( _InterlockedExchangeAdd64((volatile signed __int64 *)this + 1, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
  {
    v2 = *((_QWORD *)this + 2);
    if ( v2 )
    {
      cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(v4, v2);
      *(_QWORD *)(*((_QWORD *)this + 2) + 56LL) = 0;
      v3 = *((_QWORD *)this + 2);
      if ( *(_DWORD *)(v3 + 64) )
        v3 = 0;
      *((_QWORD *)this + 2) = 0;
      cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(v4);
      if ( v3 )
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)v3);
        operator delete((void *)v3);
      }
    }
    (*(void (__fastcall **)(cxl::RefCounted *, __int64))(*(_QWORD *)this + 8LL))(this, 1);
  }
}

```

## disassembly

```asm
0x18001143c  mov     [rsp+arg_8], rbx
0x180011441  push    rdi
0x180011442  sub     rsp, 30h
0x180011446  mov     rbx, rcx
0x180011449  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001144d  lock xadd [rcx+8], rax
0x180011453  cmp     rax, 1
0x180011457  jnz     short loc_1800114C9
0x180011459  nop
0x18001145a  mov     rdx, [rcx+10h]
0x18001145e  test    rdx, rdx
0x180011461  jz      short loc_1800114B5
0x180011463  lea     rcx, [rsp+38h+var_18]
0x180011468  call    ??0?$AcquireExclusive@VCriticalSection@cxl@@@cxl@@QEAA@AEAVCriticalSection@1@@Z; cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(cxl::CriticalSection &)
0x18001146d  mov     rax, [rbx+10h]
0x180011471  mov     qword ptr [rax+38h], 0
0x180011479  mov     rdi, [rbx+10h]
0x18001147d  xor     eax, eax
0x18001147f  cmp     [rdi+40h], eax
0x180011482  cmovnz  rdi, rax
0x180011486  mov     [rbx+10h], rax
0x18001148a  lea     rcx, [rsp+38h+var_18]
0x18001148f  call    ??1?$AcquireExclusive@$$CBVCriticalSection@cxl@@@cxl@@QEAA@XZ; cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(void)
0x180011494  test    rdi, rdi
0x180011497  jz      short loc_1800114B5
0x180011499  mov     rcx, rdi; lpCriticalSection
0x18001149c  call    cs:__imp_DeleteCriticalSection
0x1800114a3  nop     dword ptr [rax+rax+00h]
0x1800114a8  mov     edx, 48h ; 'H'
0x1800114ad  mov     rcx, rdi; Block
0x1800114b0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800114b5  mov     rax, [rbx]
0x1800114b8  mov     edx, 1
0x1800114bd  mov     rcx, rbx
0x1800114c0  mov     rax, [rax+8]
0x1800114c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114c9  mov     rbx, [rsp+38h+arg_8]
0x1800114ce  add     rsp, 30h
0x1800114d2  pop     rdi
0x1800114d3  retn
```
