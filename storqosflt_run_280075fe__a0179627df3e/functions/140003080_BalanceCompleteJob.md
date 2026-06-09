# BalanceCompleteJob

- ea: `0x140003080`
- end: `0x140003142`
- name: `BalanceCompleteJob`
- size: `194`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400011c0`
- `0x140002550`
- `0x140006b04`

## callees

- `0x140003080`
- `0x140003150`
- `0x140005158`
- `0x140005540`

## pseudocode

```c
unsigned __int64 __fastcall BalanceCompleteJob(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rax
  __int64 v3; // r11
  __int64 v4; // rdi
  _QWORD *v5; // rbx
  unsigned __int64 result; // rax
  __int64 v7; // rdx
  _QWORD *v8; // rax
  _QWORD *v9; // r8
  __int64 v10; // rax

  v2 = *(_QWORD **)(a1 + 40);
  v3 = a2;
  v4 = *(_QWORD *)(a1 + 176);
  v5 = (_QWORD *)*v2;
  v2[24] = v4;
  if ( *(_BYTE *)(a1 + 131) )
  {
    BalanceDeIssueJob();
  }
  else if ( *(_BYTE *)(a1 + 130) )
  {
    v7 = *(_QWORD *)(a1 + 80);
    v8 = (_QWORD *)(a1 + 80);
    if ( *(_QWORD *)(v7 + 8) != a1 + 80 || (v9 = *(_QWORD **)(a1 + 88), (_QWORD *)*v9 != v8) )
      __fastfail(3u);
    *v9 = v7;
    *(_QWORD *)(v7 + 8) = v9;
    *v8 = 0;
    v10 = *(_QWORD *)(a1 + 152);
    *(_QWORD *)(a1 + 88) = 0;
    v5[119] -= v10;
  }
  if ( v5[117] < v5[124] )
    BalanceIssueBalancedJobs(v5, v3);
  result = v4 - v5[128];
  if ( result >= qword_14000D2C0 )
    return BalanceResetReservedIoCounts(v5, v4);
  return result;
}

```

## disassembly

```asm
0x140003080  mov     [rsp+arg_0], rbx
0x140003085  push    rdi
0x140003086  sub     rsp, 20h
0x14000308a  mov     rax, [rcx+28h]
0x14000308e  mov     r11, rdx
0x140003091  mov     rdi, [rcx+0B0h]
0x140003098  mov     rbx, [rax]
0x14000309b  mov     [rax+0C0h], rdi
0x1400030a2  cmp     byte ptr [rcx+83h], 0
0x1400030a9  jz      short loc_140003116
0x1400030ab  call    BalanceDeIssueJob
0x1400030b0  mov     rax, [rbx+3E0h]
0x1400030b7  cmp     [rbx+3A8h], rax
0x1400030be  jb      short loc_140003128
0x1400030c0  mov     rax, rdi
0x1400030c3  sub     rax, [rbx+400h]
0x1400030ca  cmp     rax, cs:qword_14000D2C0
0x1400030d1  jnb     short loc_140003135
0x1400030d3  mov     rbx, [rsp+28h+arg_0]
0x1400030d8  add     rsp, 20h
0x1400030dc  pop     rdi
0x1400030dd  retn
0x1400030df  mov     rdx, [rcx+50h]
0x1400030e3  lea     rax, [rcx+50h]
0x1400030e7  cmp     [rdx+8], rax
0x1400030eb  jnz     short loc_140003121
0x1400030ed  mov     r8, [rax+8]
0x1400030f1  cmp     [r8], rax
0x1400030f4  jnz     short loc_140003121
0x1400030f6  mov     [r8], rdx
0x1400030f9  mov     [rdx+8], r8
0x1400030fd  xor     edx, edx
0x1400030ff  mov     [rax], rdx
0x140003102  mov     rax, [rcx+98h]
0x140003109  mov     [rcx+58h], rdx
0x14000310d  sub     [rbx+3B8h], rax
0x140003114  jmp     short loc_1400030B0
0x140003116  cmp     byte ptr [rcx+82h], 0
0x14000311d  jz      short loc_1400030B0
0x14000311f  jmp     short loc_1400030DF
0x140003121  mov     ecx, 3
0x140003126  int     29h; Win8: RtlFailFast(ecx)
0x140003128  mov     rdx, r11
0x14000312b  mov     rcx, rbx
0x14000312e  call    BalanceIssueBalancedJobs
0x140003133  jmp     short loc_1400030C0
0x140003135  mov     rdx, rdi
0x140003138  mov     rcx, rbx
0x14000313b  call    BalanceResetReservedIoCounts
0x140003140  jmp     short loc_1400030D3
```
