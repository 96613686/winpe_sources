# CBinDescriptorTable::DeleteID(unsigned __int64)

- ea: `0x180011aa0`
- end: `0x180011b82`
- name: `?DeleteID@CBinDescriptorTable@@QEAA_K_K@Z`
- size: `226`
- prototype: `unsigned __int64 __fastcall(CBinDescriptorTable *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180011868`

## callees

- `0x18000f73c`
- `0x18000fb08`
- `0x180011aa0`
- `0x180012408`
- `0x180013480`
- `0x180013738`
- `0x180017ab4`
- `0x180017b7c`

## pseudocode

```c
__int64 __fastcall CBinDescriptorTable::DeleteID(CBinDescriptorTable *this, unsigned __int64 a2)
{
  int v4; // edi
  __int64 v5; // r14
  CSpinLockFileMappingArray *v6; // rcx
  unsigned __int64 v7; // r8
  __int64 *v8; // rax
  __int64 v9; // rax
  unsigned __int64 v11; // [rsp+60h] [rbp+18h] BYREF

  v4 = 0;
  v5 = 0;
  v6 = (CSpinLockFileMappingArray *)*((_QWORD *)this + 48);
  if ( v6 )
  {
    CSpinLockFileMappingArray::AcquireWriteAccess(v6, a2, 0);
    AcquireReadAccess((volatile int *)(*(_QWORD *)(**((_QWORD **)this + 48) + 8LL) + 20LL));
  }
  if ( (unsigned int)CBin::EnumReset(this, 8 * a2) )
  {
    v11 = 0;
    v8 = (__int64 *)CBin::EnumView(this, &v11, v7);
    if ( v8 )
    {
      if ( v11 >= 8 )
      {
        v5 = *v8;
        *v8 = 0;
        v4 = 1;
      }
    }
  }
  CBin::EnumFinish(this);
  v9 = *((_QWORD *)this + 48);
  if ( v9 )
  {
    ReleaseAccess((volatile int *)(*(_QWORD *)(*(_QWORD *)v9 + 8LL) + 20LL));
    CSpinLockFileMappingArray::ReleaseAccess(*((CSpinLockFileMappingArray **)this + 48), a2);
  }
  return v5 & -(__int64)(v4 != 0);
}

```

## disassembly

```asm
0x180011aa0  mov     [rsp+arg_18], rbx
0x180011aa5  mov     [rsp+arg_8], rdx
0x180011aaa  mov     [rsp+arg_0], rcx
0x180011aaf  push    rsi
0x180011ab0  push    rdi
0x180011ab1  push    r14
0x180011ab3  sub     rsp, 30h
0x180011ab7  mov     rsi, rdx
0x180011aba  mov     rbx, rcx
0x180011abd  xor     edi, edi
0x180011abf  xor     r14d, r14d
0x180011ac2  mov     rcx, [rcx+180h]; this
0x180011ac9  test    rcx, rcx
0x180011acc  jz      short loc_180011AEE
0x180011ace  xor     r8d, r8d; unsigned int *
0x180011ad1  call    ?AcquireWriteAccess@CSpinLockFileMappingArray@@QEAAX_KPEAI@Z; CSpinLockFileMappingArray::AcquireWriteAccess(unsigned __int64,uint *)
0x180011ad6  mov     rax, [rbx+180h]
0x180011add  mov     rcx, [rax]
0x180011ae0  mov     rcx, [rcx+8]
0x180011ae4  add     rcx, 14h; volatile int *
0x180011ae8  call    ?AcquireReadAccess@@YAXPECJ@Z; AcquireReadAccess(long volatile *)
0x180011aed  nop
0x180011aee  lea     rdx, ds:0[rsi*8]; unsigned __int64
0x180011af6  mov     rcx, rbx; this
0x180011af9  call    ?EnumReset@CBin@@QEAAH_K@Z; CBin::EnumReset(unsigned __int64)
0x180011afe  test    eax, eax
0x180011b00  jz      short loc_180011B38
0x180011b02  mov     [rsp+48h+arg_10], 0
0x180011b0b  lea     rdx, [rsp+48h+arg_10]; unsigned __int64 *
0x180011b10  mov     rcx, rbx; this
0x180011b13  call    ?EnumView@CBin@@QEAAPEAXAEA_K_K@Z; CBin::EnumView(unsigned __int64 &,unsigned __int64)
0x180011b18  test    rax, rax
0x180011b1b  jz      short loc_180011B38
0x180011b1d  cmp     [rsp+48h+arg_10], 8
0x180011b23  jb      short loc_180011B38
0x180011b25  mov     r14, [rax]
0x180011b28  mov     qword ptr [rax], 0
0x180011b2f  mov     edi, 1
0x180011b34  mov     [rsp+48h+var_28], edi
0x180011b38  mov     rcx, rbx; this
0x180011b3b  call    ?EnumFinish@CBin@@QEAAHXZ; CBin::EnumFinish(void)
0x180011b40  mov     rax, [rbx+180h]
0x180011b47  test    rax, rax
0x180011b4a  jz      short loc_180011B6B
0x180011b4c  mov     rax, [rax]
0x180011b4f  mov     rcx, [rax+8]
0x180011b53  add     rcx, 14h; volatile int *
0x180011b57  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x180011b5c  mov     rdx, rsi; unsigned __int64
0x180011b5f  mov     rcx, [rbx+180h]; this
0x180011b66  call    ?ReleaseAccess@CSpinLockFileMappingArray@@QEAAX_K@Z; CSpinLockFileMappingArray::ReleaseAccess(unsigned __int64)
0x180011b6b  neg     edi
0x180011b6d  sbb     rax, rax
0x180011b70  and     rax, r14
0x180011b73  mov     rbx, [rsp+48h+arg_18]
0x180011b78  add     rsp, 30h
0x180011b7c  pop     r14
0x180011b7e  pop     rdi
0x180011b7f  pop     rsi
0x180011b80  retn
0x180028879  push    rbx
0x18002887b  push    rbp
0x18002887c  sub     rsp, 28h
0x180028880  mov     rbp, rdx
0x180028883  mov     rbx, [rbp+50h]
0x180028887  mov     rcx, rbx; this
0x18002888a  call    ?EnumFinish@CBin@@QEAAHXZ; CBin::EnumFinish(void)
0x18002888f  cmp     qword ptr [rbx+180h], 0
0x180028897  jz      short loc_1800288C1
0x180028899  mov     rax, [rbx+180h]
0x1800288a0  mov     rdx, [rax]
0x1800288a3  mov     rcx, [rdx+8]
0x1800288a7  add     rcx, 14h; volatile int *
0x1800288ab  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x1800288b0  mov     rdx, [rbp+58h]; unsigned __int64
0x1800288b4  mov     rcx, [rbx+180h]; this
0x1800288bb  call    ?ReleaseAccess@CSpinLockFileMappingArray@@QEAAX_K@Z; CSpinLockFileMappingArray::ReleaseAccess(unsigned __int64)
0x1800288c0  nop
0x1800288c1  add     rsp, 28h
0x1800288c5  pop     rbp
0x1800288c6  pop     rbx
0x1800288c7  retn
```
