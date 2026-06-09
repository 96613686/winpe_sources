# SqospFlushDeferredJobCompletions

- ea: `0x140002550`
- end: `0x1400025d2`
- name: `SqospFlushDeferredJobCompletions`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002300`

## callees

- `0x140002550`
- `0x1400025e0`
- `0x140003080`

## pseudocode

```c
__int64 __fastcall SqospFlushDeferredJobCompletions(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  _QWORD *v7; // rbx
  __int64 v8; // rbp
  _QWORD *v9; // rcx

  result = SqospFlushDeferredJobList(a1 + 272);
  v7 = (_QWORD *)result;
  if ( result )
  {
    do
    {
      v8 = (__int64)(v7 - 8);
      v7 = (_QWORD *)*v7;
      BalanceCompleteJob(v8, a3);
      v9 = *(_QWORD **)(a4 + 8);
      if ( *v9 != a4 )
        __fastfail(3u);
      *(_QWORD *)(v8 + 96) = a4;
      result = v8 + 96;
      *(_QWORD *)(v8 + 104) = v9;
      *v9 = v8 + 96;
      *(_QWORD *)(a4 + 8) = v8 + 96;
    }
    while ( v7 );
  }
  return result;
}

```

## disassembly

```asm
0x140002550  mov     [rsp+arg_8], rbx
0x140002555  mov     [rsp+arg_10], rsi
0x14000255a  push    rdi
0x14000255b  sub     rsp, 20h
0x14000255f  add     rcx, 110h
0x140002566  mov     rdi, r9
0x140002569  mov     rsi, r8
0x14000256c  call    SqospFlushDeferredJobList
0x140002571  mov     rbx, rax
0x140002574  test    rax, rax
0x140002577  jnz     short loc_1400025C4
0x140002579  mov     rbx, [rsp+28h+arg_8]
0x14000257e  mov     rsi, [rsp+28h+arg_10]
0x140002583  add     rsp, 20h
0x140002587  pop     rdi
0x140002588  retn
0x14000258a  lea     rbp, [rbx-40h]
0x14000258e  mov     rdx, rsi
0x140002591  mov     rbx, [rbx]
0x140002594  mov     rcx, rbp
0x140002597  call    BalanceCompleteJob
0x14000259c  mov     rcx, [rdi+8]
0x1400025a0  cmp     [rcx], rdi
0x1400025a3  jnz     short loc_1400025CB
0x1400025a5  mov     [rbp+60h], rdi
0x1400025a9  lea     rax, [rbp+60h]
0x1400025ad  mov     [rax+8], rcx
0x1400025b1  mov     [rcx], rax
0x1400025b4  mov     [rdi+8], rax
0x1400025b8  test    rbx, rbx
0x1400025bb  jnz     short loc_14000258A
0x1400025bd  mov     rbp, [rsp+28h+arg_0]
0x1400025c2  jmp     short loc_140002579
0x1400025c4  mov     [rsp+28h+arg_0], rbp
0x1400025c9  jmp     short loc_14000258A
0x1400025cb  mov     ecx, 3
0x1400025d0  int     29h; Win8: RtlFailFast(ecx)
```
