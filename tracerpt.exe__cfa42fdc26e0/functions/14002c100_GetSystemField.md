# GetSystemField

- ea: `0x14002c100`
- end: `0x14002c446`
- name: `GetSystemField`
- size: `838`
- prototype: `__int64 __fastcall(__int64, __int64, struct _RPT_TRAN *, struct _UNICODE_STRING *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14002a1e0`
- `0x14002a42c`

## callees

- `0x140016808`
- `0x1400291bc`
- `0x14002bf58`
- `0x14002c100`

## string_xrefs

- `0x14002c16c`: `sys:Task`

## pseudocode

```c
__int64 __fastcall GetSystemField(__int64 a1, __int64 a2, struct _RPT_TRAN *a3, struct _UNICODE_STRING *a4, __int64 a5)
{
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 RptTransaction; // rax
  struct _RPT_TRAN *v12; // rcx
  double v13; // xmm0_8
  __int64 v14; // rax
  struct _RPT_TRAN *v15; // rcx
  __int64 result; // rax
  __int128 v17; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING v18; // [rsp+30h] [rbp-10h] BYREF

  v17 = 0;
  v18 = *a4;
  if ( EqualString(&v18, L"sys:Opcode", 0) )
  {
    *(_DWORD *)a5 = 262148;
    *(_QWORD *)(a5 + 8) = a2 + 61;
    *(_DWORD *)(a5 + 16) = 1;
    goto LABEL_42;
  }
  v18 = *a4;
  if ( EqualString(&v18, L"sys:Task", 0) )
  {
    *(_DWORD *)a5 = 393222;
    *(_QWORD *)(a5 + 8) = a2 + 62;
    *(_DWORD *)(a5 + 16) = 2;
    goto LABEL_42;
  }
  v18 = *a4;
  if ( !EqualString(&v18, L"sys:ProviderName", 0) )
  {
    v18 = *a4;
    if ( EqualString(&v18, L"sys:TID", 0) )
    {
      v10 = a2 + 24;
LABEL_11:
      *(_QWORD *)(a5 + 8) = v10;
      goto LABEL_41;
    }
    v18 = *a4;
    if ( EqualString(&v18, L"sys:PID", 0) )
    {
      v10 = a2 + 28;
      goto LABEL_11;
    }
    v18 = *a4;
    if ( EqualString(&v18, L"sys:ActivityId", 0) )
    {
      *(_DWORD *)a5 = 917519;
      *(_QWORD *)(a5 + 8) = a2 + 80;
      *(_DWORD *)(a5 + 16) = 16;
      goto LABEL_42;
    }
    v18 = *a4;
    if ( EqualString(&v18, L"sys:Timestamp", 0) )
    {
      *(_DWORD *)a5 = 655370;
      *(_QWORD *)(a5 + 8) = a2 + 32;
      *(_DWORD *)(a5 + 16) = 8;
      goto LABEL_42;
    }
    v18 = *a4;
    if ( EqualString(&v18, L"sys:KCPU", 0) )
    {
      v10 = a2 + 72;
      goto LABEL_11;
    }
    v18 = *a4;
    if ( EqualString(&v18, L"sys:UCPU", 0) )
    {
      v10 = a2 + 76;
      goto LABEL_11;
    }
    v18 = *a4;
    if ( EqualString(&v18, L"sys:CPUPercent", 0) )
    {
      if ( a3 )
      {
        v12 = a3;
      }
      else
      {
        RptTransaction = GetRptTransaction(a1, a2);
        if ( !RptTransaction )
        {
LABEL_28:
          v13 = *(double *)&v17;
          goto LABEL_38;
        }
        v12 = (struct _RPT_TRAN *)RptTransaction;
      }
      CalculateTrans(v12, (struct _SYSTEM_TRANS *)&v17);
      goto LABEL_28;
    }
    v18 = *a4;
    if ( !EqualString(&v18, L"sys:ResponseTime", 0) )
    {
      v18 = *a4;
      if ( !EqualString(&v18, L"sys:RequestRate", 0) )
      {
        v18 = *a4;
        if ( !EqualString(&v18, L"sys:AggregateCount", 0) )
          goto LABEL_42;
        *(_DWORD *)(a5 + 8) = 0;
        *(_BYTE *)(a5 + 25) = 1;
LABEL_41:
        *(_DWORD *)a5 = 524296;
        *(_DWORD *)(a5 + 16) = 4;
        goto LABEL_42;
      }
      v13 = 1.0 / ((double)(SystemTimeAsFileTime.dwLowDateTime - CurrentSystem.dwLowDateTime) / 10000000.0);
LABEL_38:
      *(double *)(a5 + 8) = v13;
      *(_DWORD *)a5 = 786444;
      *(_DWORD *)(a5 + 16) = 8;
      *(_BYTE *)(a5 + 25) = 1;
      goto LABEL_42;
    }
    if ( a3 )
    {
      v15 = a3;
    }
    else
    {
      v14 = GetRptTransaction(a1, a2);
      if ( !v14 )
      {
LABEL_35:
        v13 = *((double *)&v17 + 1);
        goto LABEL_38;
      }
      v15 = (struct _RPT_TRAN *)v14;
    }
    CalculateTrans(v15, (struct _SYSTEM_TRANS *)&v17);
    goto LABEL_35;
  }
  *(_DWORD *)a5 = 65537;
  *(_QWORD *)(a5 + 8) = *(_QWORD *)(a1 + 32);
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(*(_QWORD *)(a1 + 32) + 2 * v9) );
  *(_DWORD *)(a5 + 16) = 2 * v9 + 2;
LABEL_42:
  result = *(unsigned __int16 *)(a2 + 20);
  *(_DWORD *)(a5 + 28) = result;
  return result;
}

```

## disassembly

```asm
0x14002c100  push    rbp
0x14002c102  push    rbx
0x14002c103  push    rsi
0x14002c104  push    rdi
0x14002c105  push    r12
0x14002c107  push    r14
0x14002c109  push    r15
0x14002c10b  mov     rbp, rsp
0x14002c10e  sub     rsp, 40h
0x14002c112  xorps   xmm0, xmm0
0x14002c115  mov     r14, r8
0x14002c118  mov     rdi, rdx
0x14002c11b  mov     r15, rcx
0x14002c11e  movups  [rbp+var_20], xmm0
0x14002c122  xor     r8d, r8d; unsigned __int8
0x14002c125  lea     rdx, aSysOpcode; "sys:Opcode"
0x14002c12c  movups  xmm0, xmmword ptr [r9]
0x14002c130  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14002c134  mov     rsi, r9
0x14002c137  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14002c13c  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14002c141  mov     rbx, [rbp+arg_20]
0x14002c145  xor     r12d, r12d
0x14002c148  test    al, al
0x14002c14a  jz      short loc_14002C166
0x14002c14c  lea     rax, [rdi+3Dh]
0x14002c150  mov     dword ptr [rbx], 40004h
0x14002c156  mov     [rbx+8], rax
0x14002c15a  mov     dword ptr [rbx+10h], 1
0x14002c161  jmp     loc_14002C430
0x14002c166  movups  xmm0, xmmword ptr [rsi]
0x14002c169  xor     r8d, r8d; unsigned __int8
0x14002c16c  lea     rdx, aSysTask; "sys:Task"
0x14002c173  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14002c177  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14002c17c  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14002c181  test    al, al
0x14002c183  jz      short loc_14002C19F
0x14002c185  lea     rax, [rdi+3Eh]
0x14002c189  mov     dword ptr [rbx], 60006h
0x14002c18f  mov     [rbx+8], rax
0x14002c193  mov     dword ptr [rbx+10h], 2
0x14002c19a  jmp     loc_14002C430
0x14002c19f  movups  xmm0, xmmword ptr [rsi]
0x14002c1a2  xor     r8d, r8d; unsigned __int8
0x14002c1a5  lea     rdx, aSysProvidernam; "sys:ProviderName"
0x14002c1ac  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14002c1b0  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14002c1b5  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14002c1ba  test    al, al
0x14002c1bc  jz      short loc_14002C1ED
0x14002c1be  mov     dword ptr [rbx], 10001h
0x14002c1c4  mov     rax, [r15+20h]
0x14002c1c8  mov     [rbx+8], rax
0x14002c1cc  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002c1d0  mov     rcx, [r15+20h]
0x14002c1d4  inc     rax
0x14002c1d7  cmp     [rcx+rax*2], r12w
0x14002c1dc  jnz     short loc_14002C1D4
0x14002c1de  lea     eax, ds:2[rax*2]
0x14002c1e5  mov     [rbx+10h], eax
0x14002c1e8  jmp     loc_14002C430
0x14002c1ed  movups  xmm0, xmmword ptr [rsi]
0x14002c1f0  xor     r8d, r8d; unsigned __int8
0x14002c1f3  lea     rdx, aSysTid; "sys:TID"
0x14002c1fa  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14002c1fe  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14002c203  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14002c208  test    al, al
0x14002c20a  jz      short loc_14002C219
0x14002c20c  lea     rax, [rdi+18h]
0x14002c210  mov     [rbx+8], rax
0x14002c214  jmp     loc_14002C423
0x14002c219  movups  xmm0, xmmword ptr [rsi]
0x14002c21c  xor     r8d, r8d; unsigned __int8
0x14002c21f  lea     rdx, aSysPid; "sys:PID"
0x14002c226  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14002c22a  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14002c22f  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14002c234  test    al, al
0x14002c236  jz      short loc_14002C23E
0x14002c238  lea     rax, [rdi+1Ch]
0x14002c23c  jmp     short loc_14002C210
0x14002c23e  movups  xmm0, xmmword ptr [rsi]
0x14002c241  xor     r8d, r8d; unsigned __int8
0x14002c244  lea     rdx, aSysActivityid; "sys:ActivityId"
0x14002c24b  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14002c24f  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14002c254  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14002c259  test    al, al
0x14002c25b  jz      short loc_14002C277
0x14002c25d  lea     rax, [rdi+50h]
0x14002c261  mov     dword ptr [rbx], 0E000Fh
0x14002c267  mov     [rbx+8], rax
0x14002c26b  mov     dword ptr [rbx+10h], 10h
0x14002c272  jmp     loc_14002C430
0x14002c277  movups  xmm0, xmmword ptr [rsi]
0x14002c27a  xor     r8d, r8d; unsigned __int8
0x14002c27d  lea     rdx, aSysTimestamp; "sys:Timestamp"
0x14002c284  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14002c288  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14002c28d  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14002c292  test    al, al
0x14002c294  jz      short loc_14002C2B0
0x14002c296  lea     rax, [rdi+20h]
0x14002c29a  mov     dword ptr [rbx], 0A000Ah
0x14002c2a0  mov     [rbx+8], rax
0x14002c2a4  mov     dword ptr [rbx+10h], 8
0x14002c2ab  jmp     loc_14002C430
0x14002c2b0  movups  xmm0, xmmword ptr [rsi]
0x14002c2b3  xor     r8d, r8d; unsigned __int8
0x14002c2b6  lea     rdx, aSysKcpu; "sys:KCPU"
0x14002c2bd  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14002c2c1  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14002c2c6  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14002c2cb  test    al, al
0x14002c2cd  jz      short loc_14002C2D8
0x14002c2cf  lea     rax, [rdi+48h]
0x14002c2d3  jmp     loc_14002C210
0x14002c2d8  movups  xmm0, xmmword ptr [rsi]
0x14002c2db  xor     r8d, r8d; unsigned __int8
0x14002c2de  lea     rdx, aSysUcpu; "sys:UCPU"
0x14002c2e5  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14002c2e9  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14002c2ee  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14002c2f3  test    al, al
0x14002c2f5  jz      short loc_14002C300
0x14002c2f7  lea     rax, [rdi+4Ch]
0x14002c2fb  jmp     loc_14002C210
0x14002c300  movups  xmm0, xmmword ptr [rsi]
0x14002c303  xor     r8d, r8d; unsigned __int8
0x14002c306  lea     rdx, aSysCpupercent; "sys:CPUPercent"
0x14002c30d  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14002c311  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14002c316  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14002c31b  test    al, al
0x14002c31d  jz      short loc_14002C34F
0x14002c31f  test    r14, r14
0x14002c322  jnz     short loc_14002C339
0x14002c324  mov     rdx, rdi
0x14002c327  mov     rcx, r15
0x14002c32a  call    GetRptTransaction
0x14002c32f  test    rax, rax
0x14002c332  jz      short loc_14002C345
0x14002c334  mov     rcx, rax
0x14002c337  jmp     short loc_14002C33C
0x14002c339  mov     rcx, r14; struct _RPT_TRAN *
0x14002c33c  lea     rdx, [rbp+var_20]; struct _SYSTEM_TRANS *
0x14002c340  call    ?CalculateTrans@@YAXPEAU_RPT_TRAN@@PEAU_SYSTEM_TRANS@@@Z; CalculateTrans(_RPT_TRAN *,_SYSTEM_TRANS *)
0x14002c345  movsd   xmm0, qword ptr [rbp+var_20]
0x14002c34a  jmp     loc_14002C3E4
0x14002c34f  movups  xmm0, xmmword ptr [rsi]
0x14002c352  xor     r8d, r8d; unsigned __int8
0x14002c355  lea     rdx, aSysResponsetim; "sys:ResponseTime"
0x14002c35c  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14002c360  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14002c365  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14002c36a  test    al, al
0x14002c36c  jz      short loc_14002C39B
0x14002c36e  test    r14, r14
0x14002c371  jnz     short loc_14002C388
0x14002c373  mov     rdx, rdi
0x14002c376  mov     rcx, r15
0x14002c379  call    GetRptTransaction
0x14002c37e  test    rax, rax
0x14002c381  jz      short loc_14002C394
0x14002c383  mov     rcx, rax
0x14002c386  jmp     short loc_14002C38B
0x14002c388  mov     rcx, r14; struct _RPT_TRAN *
0x14002c38b  lea     rdx, [rbp+var_20]; struct _SYSTEM_TRANS *
0x14002c38f  call    ?CalculateTrans@@YAXPEAU_RPT_TRAN@@PEAU_SYSTEM_TRANS@@@Z; CalculateTrans(_RPT_TRAN *,_SYSTEM_TRANS *)
0x14002c394  movsd   xmm0, qword ptr [rbp+var_20+8]
0x14002c399  jmp     short loc_14002C3E4
0x14002c39b  movups  xmm0, xmmword ptr [rsi]
0x14002c39e  xor     r8d, r8d; unsigned __int8
0x14002c3a1  lea     rdx, aSysRequestrate; "sys:RequestRate"
0x14002c3a8  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14002c3ac  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14002c3b1  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14002c3b6  test    al, al
0x14002c3b8  jz      short loc_14002C3FC
0x14002c3ba  mov     rax, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x14002c3c1  xorps   xmm1, xmm1
0x14002c3c4  sub     rax, qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime; _SYSTEM_RECORD CurrentSystem ...
0x14002c3cb  movsd   xmm0, cs:__real@3ff0000000000000
0x14002c3d3  cvtsi2sd xmm1, rax
0x14002c3d8  divsd   xmm1, cs:__real@416312d000000000
0x14002c3e0  divsd   xmm0, xmm1
0x14002c3e4  movsd   qword ptr [rbx+8], xmm0
0x14002c3e9  mov     dword ptr [rbx], 0C000Ch
0x14002c3ef  mov     dword ptr [rbx+10h], 8
0x14002c3f6  mov     byte ptr [rbx+19h], 1
0x14002c3fa  jmp     short loc_14002C430
0x14002c3fc  movups  xmm0, xmmword ptr [rsi]
0x14002c3ff  xor     r8d, r8d; unsigned __int8
0x14002c402  lea     rdx, aSysAggregateco; "sys:AggregateCount"
0x14002c409  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14002c40d  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14002c412  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14002c417  test    al, al
0x14002c419  jz      short loc_14002C430
0x14002c41b  mov     [rbx+8], r12d
0x14002c41f  mov     byte ptr [rbx+19h], 1
0x14002c423  mov     dword ptr [rbx], 80008h
0x14002c429  mov     dword ptr [rbx+10h], 4
0x14002c430  movzx   eax, word ptr [rdi+14h]
0x14002c434  mov     [rbx+1Ch], eax
0x14002c437  add     rsp, 40h
0x14002c43b  pop     r15
0x14002c43d  pop     r14
0x14002c43f  pop     r12
0x14002c441  pop     rdi
0x14002c442  pop     rsi
0x14002c443  pop     rbx
0x14002c444  pop     rbp
0x14002c445  retn
```
