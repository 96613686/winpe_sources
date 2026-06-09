# _log_special_common

- ea: `0x100438b48`
- end: `0x100438bde`
- name: `_log_special_common`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100438b20`

## callees

- `0x100438940`
- `0x100438b48`

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
0x100438b48  mov     rax, rsp
0x100438b4b  sub     rsp, 68h
0x100438b4f  movaps  xmmword ptr [rax-18h], xmm6
0x100438b53  movaps  xmm6, xmm1
0x100438b56  mov     edx, r9d
0x100438b59  movaps  xmm3, xmm0
0x100438b5c  sub     r8d, 1
0x100438b60  jz      short loc_100438B8C
0x100438b62  cmp     r8d, 1
0x100438b66  jnz     short loc_100438BD1
0x100438b68  mov     [rax-28h], r8d
0x100438b6c  xorps   xmm2, xmm2
0x100438b6f  movsd   qword ptr [rax-30h], xmm2
0x100438b74  mov     r9d, r8d
0x100438b77  movsd   qword ptr [rax-38h], xmm0
0x100438b7c  mov     dword ptr [rax-40h], 21h ; '!'
0x100438b83  mov     dword ptr [rax-48h], 8
0x100438b8a  jmp     short loc_100438BB9
0x100438b8c  mov     [rsp+68h+var_28], 1
0x100438b94  xorps   xmm0, xmm0
0x100438b97  movsd   [rsp+68h+var_30], xmm0
0x100438b9d  mov     r9d, 2
0x100438ba3  movsd   [rsp+68h+var_38], xmm3
0x100438ba9  mov     [rsp+68h+var_40], 22h ; '"'
0x100438bb1  mov     [rsp+68h+var_48], 4
0x100438bb9  mov     rcx, [rsp+68h+arg_20]
0x100438bc1  movsd   [rsp+68h+arg_8], xmm6
0x100438bc7  mov     r8, [rsp+68h+arg_8]
0x100438bcc  call    _handle_error
0x100438bd1  movaps  xmm0, xmm6
0x100438bd4  movaps  xmm6, [rsp+68h+var_18]
0x100438bd9  add     rsp, 68h
0x100438bdd  retn
```
