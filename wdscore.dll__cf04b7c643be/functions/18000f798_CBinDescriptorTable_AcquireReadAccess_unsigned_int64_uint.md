# CBinDescriptorTable::AcquireReadAccess(unsigned __int64,uint *)

- ea: `0x18000f798`
- end: `0x18000f827`
- name: `?AcquireReadAccess@CBinDescriptorTable@@QEAA_K_KPEAI@Z`
- size: `143`
- prototype: `unsigned __int64(CBinDescriptorTable *__hidden this, unsigned __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180017888`

## callees

- `0x18000f73c`
- `0x18000f798`
- `0x18000f830`
- `0x180014dfc`
- `0x180017ab4`
- `0x180017b7c`

## pseudocode

```c
unsigned __int64 __fastcall CBinDescriptorTable::AcquireReadAccess(
        CBinDescriptorTable *this,
        unsigned __int64 a2,
        unsigned int *a3)
{
  CSpinLockFileMappingArray *v5; // rcx
  unsigned __int64 PageFromID; // rax
  __int64 v7; // rcx
  unsigned __int64 v8; // rdi

  v5 = (CSpinLockFileMappingArray *)*((_QWORD *)this + 48);
  if ( v5 )
  {
    CSpinLockFileMappingArray::AcquireReadAccess(v5, a2, a3);
    AcquireReadAccess((volatile int *)(*(_QWORD *)(**((_QWORD **)this + 48) + 8LL) + 20LL));
  }
  PageFromID = CBinDescriptorTable::GetPageFromID(this, a2);
  v7 = *((_QWORD *)this + 48);
  v8 = PageFromID;
  if ( v7 )
  {
    ReleaseAccess((volatile int *)(*(_QWORD *)(*(_QWORD *)v7 + 8LL) + 20LL));
    if ( !v8 )
      CSpinLockFileMappingArray::ReleaseAccess(*((CSpinLockFileMappingArray **)this + 48), a2);
  }
  return v8;
}

```

## disassembly

```asm
0x18000f798  mov     [rsp+arg_0], rbx
0x18000f79d  mov     [rsp+arg_8], rsi
0x18000f7a2  push    rdi
0x18000f7a3  sub     rsp, 20h
0x18000f7a7  mov     rbx, rcx
0x18000f7aa  mov     rsi, rdx
0x18000f7ad  mov     rcx, [rcx+180h]; this
0x18000f7b4  test    rcx, rcx
0x18000f7b7  jz      short loc_18000F7D5
0x18000f7b9  call    ?AcquireReadAccess@CSpinLockFileMappingArray@@QEAAX_KPEAI@Z; CSpinLockFileMappingArray::AcquireReadAccess(unsigned __int64,uint *)
0x18000f7be  mov     rax, [rbx+180h]
0x18000f7c5  mov     r8, [rax]
0x18000f7c8  mov     rcx, [r8+8]
0x18000f7cc  add     rcx, 14h; volatile int *
0x18000f7d0  call    ?AcquireReadAccess@@YAXPECJ@Z; AcquireReadAccess(long volatile *)
0x18000f7d5  mov     rdx, rsi; unsigned __int64
0x18000f7d8  mov     rcx, rbx; this
0x18000f7db  call    ?GetPageFromID@CBinDescriptorTable@@IEAA_K_K@Z; CBinDescriptorTable::GetPageFromID(unsigned __int64)
0x18000f7e0  mov     rcx, [rbx+180h]
0x18000f7e7  mov     rdi, rax
0x18000f7ea  test    rcx, rcx
0x18000f7ed  jz      short loc_18000F813
0x18000f7ef  mov     rcx, [rcx]
0x18000f7f2  mov     rcx, [rcx+8]
0x18000f7f6  add     rcx, 14h; volatile int *
0x18000f7fa  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x18000f7ff  test    rdi, rdi
0x18000f802  jnz     short loc_18000F813
0x18000f804  mov     rcx, [rbx+180h]; this
0x18000f80b  mov     rdx, rsi; unsigned __int64
0x18000f80e  call    ?ReleaseAccess@CSpinLockFileMappingArray@@QEAAX_K@Z; CSpinLockFileMappingArray::ReleaseAccess(unsigned __int64)
0x18000f813  mov     rbx, [rsp+28h+arg_0]
0x18000f818  mov     rax, rdi
0x18000f81b  mov     rsi, [rsp+28h+arg_8]
0x18000f820  add     rsp, 20h
0x18000f824  pop     rdi
0x18000f825  retn
```
