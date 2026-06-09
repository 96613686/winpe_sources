# CSpinLockFileMappingArray::AcquireWriteAccess(unsigned __int64,uint *)

- ea: `0x18000fb08`
- end: `0x18000fbd3`
- name: `?AcquireWriteAccess@CSpinLockFileMappingArray@@QEAAX_KPEAI@Z`
- size: `203`
- prototype: `void __fastcall(CSpinLockFileMappingArray *__hidden this, unsigned __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fa70`
- `0x180011aa0`

## callees

- `0x18000fb08`
- `0x18000fbdc`
- `0x18002a010`

## pseudocode

```c
void __fastcall CSpinLockFileMappingArray::AcquireWriteAccess(
        CSpinLockFileMappingArray *this,
        __int64 a2,
        unsigned int *a3)
{
  __int64 v5; // r14
  __int64 v6; // rcx
  volatile int *v7; // rax
  volatile int *v8; // rbx
  int v9; // ebp
  int v10; // [rsp+50h] [rbp+8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF

  v10 = 0;
  v5 = 8 * a2;
  while ( 1 )
  {
    do
    {
      v6 = *(_QWORD *)this;
      v11 = 0;
      v7 = (volatile int *)(*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v6 + 16LL))(
                             v6,
                             v5,
                             8,
                             &v11);
      v8 = v7;
    }
    while ( !v7 );
    v9 = AcquireWriteAccessIfSomebodyDoesNotWaitOnSecondSpinlock(
           v7,
           (volatile int *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 8LL),
           &v10);
    if ( v9 )
    {
      ++*((_DWORD *)v8 + 1);
      if ( a3 )
        *a3 = *((_DWORD *)v8 + 1);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)this + 24LL))(*(_QWORD *)this, v11);
    if ( v9 )
      break;
    (*(void (__fastcall **)(struct IKernel32Interface *, __int64))(*(_QWORD *)g_Kernel32 + 496LL))(g_Kernel32, 1);
  }
}

```

## disassembly

```asm
0x18000fb08  mov     [rsp+arg_10], rbx
0x18000fb0d  mov     [rsp+arg_18], rbp
0x18000fb12  push    rsi
0x18000fb13  push    rdi
0x18000fb14  push    r14
0x18000fb16  sub     rsp, 30h
0x18000fb1a  mov     rdi, r8
0x18000fb1d  mov     [rsp+48h+arg_0], 0
0x18000fb25  mov     rsi, rcx
0x18000fb28  lea     r14, ds:0[rdx*8]
0x18000fb30  mov     rcx, [rsi]
0x18000fb33  lea     r9, [rsp+48h+arg_8]
0x18000fb38  mov     [rsp+48h+arg_8], 0
0x18000fb41  mov     r8d, 8
0x18000fb47  mov     rdx, r14
0x18000fb4a  mov     rax, [rcx]
0x18000fb4d  mov     rax, [rax+10h]
0x18000fb51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb56  mov     rbx, rax
0x18000fb59  test    rax, rax
0x18000fb5c  jz      short loc_18000FB30
0x18000fb5e  mov     rcx, [rsi]
0x18000fb61  lea     r8, [rsp+48h+arg_0]; int *
0x18000fb66  mov     rdx, [rcx+8]
0x18000fb6a  mov     rcx, rax; volatile int *
0x18000fb6d  add     rdx, 8; volatile int *
0x18000fb71  call    ?AcquireWriteAccessIfSomebodyDoesNotWaitOnSecondSpinlock@@YAHPECJ0AEAJ@Z; AcquireWriteAccessIfSomebodyDoesNotWaitOnSecondSpinlock(long volatile *,long volatile *,long &)
0x18000fb76  mov     ebp, eax
0x18000fb78  test    eax, eax
0x18000fb7a  jz      short loc_18000FB89
0x18000fb7c  inc     dword ptr [rbx+4]
0x18000fb7f  mov     ecx, [rbx+4]
0x18000fb82  test    rdi, rdi
0x18000fb85  jz      short loc_18000FB89
0x18000fb87  mov     [rdi], ecx
0x18000fb89  mov     rcx, [rsi]
0x18000fb8c  mov     rdx, [rcx]
0x18000fb8f  mov     rax, [rdx+18h]
0x18000fb93  mov     rdx, [rsp+48h+arg_8]
0x18000fb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb9d  test    ebp, ebp
0x18000fb9f  jnz     short loc_18000FBBF
0x18000fba1  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000fba8  lea     edx, [rbp+1]
0x18000fbab  mov     rax, [rcx]
0x18000fbae  mov     rax, [rax+1F0h]
0x18000fbb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbba  jmp     loc_18000FB30
0x18000fbbf  mov     rbx, [rsp+48h+arg_10]
0x18000fbc4  mov     rbp, [rsp+48h+arg_18]
0x18000fbc9  add     rsp, 30h
0x18000fbcd  pop     r14
0x18000fbcf  pop     rdi
0x18000fbd0  pop     rsi
0x18000fbd1  retn
```
