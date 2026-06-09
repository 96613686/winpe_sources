# WPP_RECORDER_SF_qds

- ea: `0x140013d4c`
- end: `0x140013ea8`
- name: `WPP_RECORDER_SF_qds`
- size: `348`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140006834`
- `0x140006af8`
- `0x1400090e0`
- `0x140028800`
- `0x140029b50`
- `0x14002a0b0`

## callees

- `0x140013d4c`
- `0x140014d50`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140013e90`
- `WppRecorder!WppAutoLogTrace` at `0x140013e90`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_qds(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        int a5,
        char a6,
        char a7,
        const char *a8)
{
  __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 v12; // rax
  __int64 v13; // rdx
  const char *v14; // rcx
  int v16; // [rsp+20h] [rbp-68h]

  v8 = (__int64)a8;
  v9 = -1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    if ( a8 )
    {
      v12 = -1;
      do
        ++v12;
      while ( a8[v12] );
      v13 = v12 + 1;
    }
    else
    {
      v13 = 5;
    }
    v14 = a8;
    if ( !a8 )
      v14 = "NULL";
    pfnWppTraceMessage(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids,
      a4,
      &a6,
      8,
      &a7,
      4,
      v14,
      v13,
      0);
  }
  if ( v8 )
  {
    do
      ++v9;
    while ( *(_BYTE *)(v8 + v9) );
  }
  LOWORD(v16) = a4;
  return WppAutoLogTrace(a1, 2, 1, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids, v16, &a6);
}

```

## disassembly

```asm
0x140013d4c  push    rbx
0x140013d4e  push    rbp
0x140013d4f  push    rsi
0x140013d50  push    rdi
0x140013d51  push    r14
0x140013d53  sub     rsp, 60h
0x140013d57  mov     rdx, cs:WPP_GLOBAL_Control
0x140013d5e  lea     r8, aNull; "NULL"
0x140013d65  mov     rbx, [rsp+88h+arg_38]
0x140013d6d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140013d71  movzx   ebp, r9w
0x140013d75  mov     r14, rcx
0x140013d78  mov     eax, [rdx+2Ch]
0x140013d7b  lea     esi, [rdi+6]
0x140013d7e  test    al, 1
0x140013d80  jz      loc_140013E20
0x140013d86  cmp     byte ptr [rdx+29h], 2
0x140013d8a  jb      loc_140013E20
0x140013d90  test    rbx, rbx
0x140013d93  jz      short loc_140013DA7
0x140013d95  mov     rax, rdi
0x140013d98  inc     rax
0x140013d9b  cmp     byte ptr [rbx+rax], 0
0x140013d9f  jnz     short loc_140013D98
0x140013da1  lea     rdx, [rax+1]
0x140013da5  jmp     short loc_140013DAA
0x140013da7  mov     rdx, rsi
0x140013daa  mov     rax, cs:pfnWppTraceMessage
0x140013db1  test    rbx, rbx
0x140013db4  mov     [rsp+88h+var_38], 0
0x140013dbd  mov     rcx, rbx
0x140013dc0  cmovz   rcx, r8
0x140013dc4  mov     [rsp+88h+var_40], rdx
0x140013dc9  mov     [rsp+88h+var_48], rcx
0x140013dce  lea     r8, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140013dd5  mov     [rsp+88h+var_50], 4
0x140013dde  lea     rcx, [rsp+88h+arg_30]
0x140013de6  mov     [rsp+88h+var_58], rcx
0x140013deb  mov     r9d, ebp
0x140013dee  lea     rcx, [rsp+88h+arg_28]
0x140013df6  mov     [rsp+88h+var_60], 8
0x140013dff  mov     [rsp+88h+var_68], rcx
0x140013e04  mov     edx, 2Bh ; '+'
0x140013e09  mov     rcx, cs:WPP_GLOBAL_Control
0x140013e10  mov     rcx, [rcx+18h]
0x140013e14  call    _guard_dispatch_icall
0x140013e19  lea     r8, aNull; "NULL"
0x140013e20  test    rbx, rbx
0x140013e23  jz      short loc_140013E35
0x140013e25  inc     rdi
0x140013e28  cmp     byte ptr [rbx+rdi], 0
0x140013e2c  jnz     short loc_140013E25
0x140013e2e  lea     rsi, [rdi+1]
0x140013e32  test    rbx, rbx
0x140013e35  mov     [rsp+88h+var_30], 0
0x140013e3e  lea     rax, [rsp+88h+arg_30]
0x140013e46  mov     [rsp+88h+var_38], rsi
0x140013e4b  lea     r9, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140013e52  cmovz   rbx, r8
0x140013e56  mov     edx, 2
0x140013e5b  mov     [rsp+88h+var_40], rbx
0x140013e60  mov     rcx, r14
0x140013e63  mov     [rsp+88h+var_48], 4
0x140013e6c  mov     [rsp+88h+var_50], rax
0x140013e71  lea     rax, [rsp+88h+arg_28]
0x140013e79  mov     [rsp+88h+var_58], 8
0x140013e82  lea     r8d, [rdx-1]
0x140013e86  mov     [rsp+88h+var_60], rax
0x140013e8b  mov     word ptr [rsp+88h+var_68], bp
0x140013e90  call    cs:__imp_WppAutoLogTrace
0x140013e97  nop     dword ptr [rax+rax+00h]
0x140013e9c  add     rsp, 60h
0x140013ea0  pop     r14
0x140013ea2  pop     rdi
0x140013ea3  pop     rsi
0x140013ea4  pop     rbp
0x140013ea5  pop     rbx
0x140013ea6  retn
```
