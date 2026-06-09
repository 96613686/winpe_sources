# cxl::RefCounted::Release(void)

- ea: `0x180012730`
- end: `0x1800127c9`
- name: `?Release@RefCounted@cxl@@QEBAXXZ`
- size: `153`
- prototype: `void __fastcall(cxl::RefCounted *__hidden this)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001b85c`
- `0x18001dbfc`
- `0x18001dc20`
- `0x18001e230`
- `0x18001e340`

## callees

- `0x180002ee4`
- `0x18000d460`
- `0x18000d92c`
- `0x180012730`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012790`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012790`

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
0x180012730  mov     [rsp+arg_8], rbx
0x180012735  push    rdi
0x180012736  sub     rsp, 30h
0x18001273a  mov     rbx, rcx
0x18001273d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012741  lock xadd [rcx+8], rax
0x180012747  cmp     rax, 1
0x18001274b  jnz     short loc_1800127BD
0x18001274d  nop
0x18001274e  mov     rdx, [rcx+10h]
0x180012752  test    rdx, rdx
0x180012755  jz      short loc_1800127A9
0x180012757  lea     rcx, [rsp+38h+var_18]
0x18001275c  call    ??0?$AcquireExclusive@VCriticalSection@cxl@@@cxl@@QEAA@AEAVCriticalSection@1@@Z; cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(cxl::CriticalSection &)
0x180012761  mov     rax, [rbx+10h]
0x180012765  mov     qword ptr [rax+38h], 0
0x18001276d  mov     rdi, [rbx+10h]
0x180012771  xor     eax, eax
0x180012773  cmp     [rdi+40h], eax
0x180012776  cmovnz  rdi, rax
0x18001277a  mov     [rbx+10h], rax
0x18001277e  lea     rcx, [rsp+38h+var_18]
0x180012783  call    ??1?$AcquireExclusive@$$CBVCriticalSection@cxl@@@cxl@@QEAA@XZ; cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(void)
0x180012788  test    rdi, rdi
0x18001278b  jz      short loc_1800127A9
0x18001278d  mov     rcx, rdi; lpCriticalSection
0x180012790  call    cs:__imp_DeleteCriticalSection
0x180012797  nop     dword ptr [rax+rax+00h]
0x18001279c  mov     edx, 48h ; 'H'
0x1800127a1  mov     rcx, rdi; Block
0x1800127a4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800127a9  mov     rax, [rbx]
0x1800127ac  mov     edx, 1
0x1800127b1  mov     rcx, rbx
0x1800127b4  mov     rax, [rax+8]
0x1800127b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127bd  mov     rbx, [rsp+38h+arg_8]
0x1800127c2  add     rsp, 30h
0x1800127c6  pop     rdi
0x1800127c7  retn
```
