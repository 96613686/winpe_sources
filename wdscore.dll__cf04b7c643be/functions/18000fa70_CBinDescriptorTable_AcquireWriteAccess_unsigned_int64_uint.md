# CBinDescriptorTable::AcquireWriteAccess(unsigned __int64,uint *)

- ea: `0x18000fa70`
- end: `0x18000faff`
- name: `?AcquireWriteAccess@CBinDescriptorTable@@QEAA_K_KPEAI@Z`
- size: `143`
- prototype: `unsigned __int64(CBinDescriptorTable *__hidden this, unsigned __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180017888`

## callees

- `0x18000f73c`
- `0x18000fa70`
- `0x18000fb08`
- `0x180014dfc`
- `0x180017ab4`
- `0x180017b7c`

## pseudocode

```c
unsigned __int64 __fastcall CBinDescriptorTable::AcquireWriteAccess(
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
    CSpinLockFileMappingArray::AcquireWriteAccess(v5, a2, a3);
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
0x18000fa70  mov     [rsp+arg_0], rbx
0x18000fa75  mov     [rsp+arg_8], rsi
0x18000fa7a  push    rdi
0x18000fa7b  sub     rsp, 20h
0x18000fa7f  mov     rbx, rcx
0x18000fa82  mov     rsi, rdx
0x18000fa85  mov     rcx, [rcx+180h]; this
0x18000fa8c  test    rcx, rcx
0x18000fa8f  jz      short loc_18000FAAD
0x18000fa91  call    ?AcquireWriteAccess@CSpinLockFileMappingArray@@QEAAX_KPEAI@Z; CSpinLockFileMappingArray::AcquireWriteAccess(unsigned __int64,uint *)
0x18000fa96  mov     rax, [rbx+180h]
0x18000fa9d  mov     r8, [rax]
0x18000faa0  mov     rcx, [r8+8]
0x18000faa4  add     rcx, 14h; volatile int *
0x18000faa8  call    ?AcquireReadAccess@@YAXPECJ@Z; AcquireReadAccess(long volatile *)
0x18000faad  mov     rdx, rsi; unsigned __int64
0x18000fab0  mov     rcx, rbx; this
0x18000fab3  call    ?GetPageFromID@CBinDescriptorTable@@IEAA_K_K@Z; CBinDescriptorTable::GetPageFromID(unsigned __int64)
0x18000fab8  mov     rcx, [rbx+180h]
0x18000fabf  mov     rdi, rax
0x18000fac2  test    rcx, rcx
0x18000fac5  jz      short loc_18000FAEB
0x18000fac7  mov     rcx, [rcx]
0x18000faca  mov     rcx, [rcx+8]
0x18000face  add     rcx, 14h; volatile int *
0x18000fad2  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x18000fad7  test    rdi, rdi
0x18000fada  jnz     short loc_18000FAEB
0x18000fadc  mov     rcx, [rbx+180h]; this
0x18000fae3  mov     rdx, rsi; unsigned __int64
0x18000fae6  call    ?ReleaseAccess@CSpinLockFileMappingArray@@QEAAX_K@Z; CSpinLockFileMappingArray::ReleaseAccess(unsigned __int64)
0x18000faeb  mov     rbx, [rsp+28h+arg_0]
0x18000faf0  mov     rax, rdi
0x18000faf3  mov     rsi, [rsp+28h+arg_8]
0x18000faf8  add     rsp, 20h
0x18000fafc  pop     rdi
0x18000fafd  retn
```
