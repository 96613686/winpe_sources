# _log_special_common

- ea: `0x100423378`
- end: `0x10042340e`
- name: `_log_special_common`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100423350`

## callees

- `0x100423174`
- `0x100423378`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__m128 __fastcall log_special_common(double a1, double a2, int a3, int a4, __int64 a5)
{
  int v6; // r8d
  int v7; // r9d
  int v9; // [rsp+20h] [rbp-48h]
  int v10; // [rsp+28h] [rbp-40h]
  __int64 v11; // [rsp+30h] [rbp-38h]

  v6 = a3 - 1;
  if ( !v6 )
  {
    v7 = 2;
    v11 = *(_QWORD *)&a1;
    v10 = 34;
    v9 = 4;
    goto LABEL_5;
  }
  if ( v6 == 1 )
  {
    v7 = 1;
    v11 = *(_QWORD *)&a1;
    v10 = 33;
    v9 = 8;
LABEL_5:
    handle_error(a5, a4, LODWORD(a2), v7, v9, v10, v11, 0, 1);
  }
  return *(__m128 *)&a2;
}

```

## disassembly

```asm
0x100423378  mov     rax, rsp
0x10042337b  sub     rsp, 68h
0x10042337f  movaps  xmmword ptr [rax-18h], xmm6
0x100423383  movaps  xmm6, xmm1
0x100423386  mov     edx, r9d
0x100423389  movaps  xmm3, xmm0
0x10042338c  sub     r8d, 1
0x100423390  jz      short loc_1004233BC
0x100423392  cmp     r8d, 1
0x100423396  jnz     short loc_100423401
0x100423398  mov     [rax-28h], r8d
0x10042339c  xorps   xmm2, xmm2
0x10042339f  movsd   qword ptr [rax-30h], xmm2
0x1004233a4  mov     r9d, r8d
0x1004233a7  movsd   qword ptr [rax-38h], xmm0
0x1004233ac  mov     dword ptr [rax-40h], 21h ; '!'
0x1004233b3  mov     dword ptr [rax-48h], 8
0x1004233ba  jmp     short loc_1004233E9
0x1004233bc  mov     [rsp+68h+var_28], 1
0x1004233c4  xorps   xmm0, xmm0
0x1004233c7  movsd   [rsp+68h+var_30], xmm0
0x1004233cd  mov     r9d, 2
0x1004233d3  movsd   [rsp+68h+var_38], xmm3
0x1004233d9  mov     [rsp+68h+var_40], 22h ; '"'
0x1004233e1  mov     [rsp+68h+var_48], 4
0x1004233e9  mov     rcx, [rsp+68h+arg_20]
0x1004233f1  movsd   [rsp+68h+arg_8], xmm6
0x1004233f7  mov     r8, [rsp+68h+arg_8]
0x1004233fc  call    _handle_error
0x100423401  movaps  xmm0, xmm6
0x100423404  movaps  xmm6, [rsp+68h+var_18]
0x100423409  add     rsp, 68h
0x10042340d  retn
```
