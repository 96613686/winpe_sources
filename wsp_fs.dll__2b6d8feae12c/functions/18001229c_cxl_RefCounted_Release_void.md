# cxl::RefCounted::Release(void)

- ea: `0x18001229c`
- end: `0x18001232e`
- name: `?Release@RefCounted@cxl@@QEBAXXZ`
- size: `146`
- prototype: `void __fastcall(cxl::RefCounted *__hidden this)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001adf0`
- `0x18001d0ac`
- `0x18001d0d0`
- `0x18001d690`
- `0x18001d7a0`

## callees

- `0x180002e84`
- `0x18000d100`
- `0x18000d5b0`
- `0x18001229c`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800122fc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800122fc`

## pseudocode

```c
void __fastcall cxl::RefCounted::Release(cxl::RefCounted *this)
{
  __int64 v2; // rdi
  _BYTE v3[24]; // [rsp+20h] [rbp-18h] BYREF

  if ( _InterlockedExchangeAdd64((volatile signed __int64 *)this + 1, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
  {
    if ( *((_QWORD *)this + 2) )
    {
      cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(v3);
      *(_QWORD *)(*((_QWORD *)this + 2) + 56LL) = 0;
      v2 = *((_QWORD *)this + 2);
      if ( *(_DWORD *)(v2 + 64) )
        v2 = 0;
      *((_QWORD *)this + 2) = 0;
      cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(v3);
      if ( v2 )
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)v2);
        operator delete((void *)v2);
      }
    }
    (*(void (__fastcall **)(cxl::RefCounted *, __int64))(*(_QWORD *)this + 8LL))(this, 1);
  }
}

```

## disassembly

```asm
0x18001229c  mov     [rsp+arg_8], rbx
0x1800122a1  push    rdi
0x1800122a2  sub     rsp, 30h
0x1800122a6  mov     rbx, rcx
0x1800122a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800122ad  lock xadd [rcx+8], rax
0x1800122b3  cmp     rax, 1
0x1800122b7  jnz     short loc_180012323
0x1800122b9  nop
0x1800122ba  mov     rdx, [rcx+10h]
0x1800122be  test    rdx, rdx
0x1800122c1  jz      short loc_18001230F
0x1800122c3  lea     rcx, [rsp+38h+var_18]
0x1800122c8  call    ??0?$AcquireExclusive@VCriticalSection@cxl@@@cxl@@QEAA@AEAVCriticalSection@1@@Z; cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(cxl::CriticalSection &)
0x1800122cd  mov     rax, [rbx+10h]
0x1800122d1  mov     qword ptr [rax+38h], 0
0x1800122d9  mov     rdi, [rbx+10h]
0x1800122dd  xor     eax, eax
0x1800122df  cmp     [rdi+40h], eax
0x1800122e2  cmovnz  rdi, rax
0x1800122e6  mov     [rbx+10h], rax
0x1800122ea  lea     rcx, [rsp+38h+var_18]
0x1800122ef  call    ??1?$AcquireExclusive@$$CBVCriticalSection@cxl@@@cxl@@QEAA@XZ; cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(void)
0x1800122f4  test    rdi, rdi
0x1800122f7  jz      short loc_18001230F
0x1800122f9  mov     rcx, rdi; lpCriticalSection
0x1800122fc  call    cs:__imp_DeleteCriticalSection
0x180012302  mov     edx, 48h ; 'H'
0x180012307  mov     rcx, rdi; Block
0x18001230a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001230f  mov     rax, [rbx]
0x180012312  mov     edx, 1
0x180012317  mov     rcx, rbx
0x18001231a  mov     rax, [rax+8]
0x18001231e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012323  mov     rbx, [rsp+38h+arg_8]
0x180012328  add     rsp, 30h
0x18001232c  pop     rdi
0x18001232d  retn
```
