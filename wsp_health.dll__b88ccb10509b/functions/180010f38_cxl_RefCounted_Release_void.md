# cxl::RefCounted::Release(void)

- ea: `0x180010f38`
- end: `0x180010fca`
- name: `?Release@RefCounted@cxl@@QEBAXXZ`
- size: `146`
- prototype: `void __fastcall(cxl::RefCounted *__hidden this)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180017d08`
- `0x180019fcc`
- `0x180019ff0`
- `0x18001a5b0`
- `0x18001a6c0`

## callees

- `0x180002eb0`
- `0x18000c858`
- `0x18000cdc4`
- `0x180010f38`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010f98`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010f98`

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
0x180010f38  mov     [rsp+arg_8], rbx
0x180010f3d  push    rdi
0x180010f3e  sub     rsp, 30h
0x180010f42  mov     rbx, rcx
0x180010f45  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010f49  lock xadd [rcx+8], rax
0x180010f4f  cmp     rax, 1
0x180010f53  jnz     short loc_180010FBF
0x180010f55  nop
0x180010f56  mov     rdx, [rcx+10h]
0x180010f5a  test    rdx, rdx
0x180010f5d  jz      short loc_180010FAB
0x180010f5f  lea     rcx, [rsp+38h+var_18]
0x180010f64  call    ??0?$AcquireExclusive@VCriticalSection@cxl@@@cxl@@QEAA@AEAVCriticalSection@1@@Z; cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(cxl::CriticalSection &)
0x180010f69  mov     rax, [rbx+10h]
0x180010f6d  mov     qword ptr [rax+38h], 0
0x180010f75  mov     rdi, [rbx+10h]
0x180010f79  xor     eax, eax
0x180010f7b  cmp     [rdi+40h], eax
0x180010f7e  cmovnz  rdi, rax
0x180010f82  mov     [rbx+10h], rax
0x180010f86  lea     rcx, [rsp+38h+var_18]
0x180010f8b  call    ??1?$AcquireExclusive@$$CBVCriticalSection@cxl@@@cxl@@QEAA@XZ; cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(void)
0x180010f90  test    rdi, rdi
0x180010f93  jz      short loc_180010FAB
0x180010f95  mov     rcx, rdi; lpCriticalSection
0x180010f98  call    cs:__imp_DeleteCriticalSection
0x180010f9e  mov     edx, 48h ; 'H'
0x180010fa3  mov     rcx, rdi; Block
0x180010fa6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010fab  mov     rax, [rbx]
0x180010fae  mov     edx, 1
0x180010fb3  mov     rcx, rbx
0x180010fb6  mov     rax, [rax+8]
0x180010fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fbf  mov     rbx, [rsp+38h+arg_8]
0x180010fc4  add     rsp, 30h
0x180010fc8  pop     rdi
0x180010fc9  retn
```
