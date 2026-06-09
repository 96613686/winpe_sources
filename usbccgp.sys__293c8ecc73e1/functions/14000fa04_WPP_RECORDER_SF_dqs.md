# WPP_RECORDER_SF_dqs

- ea: `0x14000fa04`
- end: `0x14000fb60`
- name: `WPP_RECORDER_SF_dqs`
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

- `0x14000fa04`
- `0x140014d50`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000fb48`
- `WppRecorder!WppAutoLogTrace` at `0x14000fb48`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_dqs(
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
      4,
      &a7,
      8,
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
0x14000fa04  push    rbx
0x14000fa06  push    rbp
0x14000fa07  push    rsi
0x14000fa08  push    rdi
0x14000fa09  push    r14
0x14000fa0b  sub     rsp, 60h
0x14000fa0f  mov     rdx, cs:WPP_GLOBAL_Control
0x14000fa16  lea     r8, aNull; "NULL"
0x14000fa1d  mov     rbx, [rsp+88h+arg_38]
0x14000fa25  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000fa29  movzx   ebp, r9w
0x14000fa2d  mov     r14, rcx
0x14000fa30  mov     eax, [rdx+2Ch]
0x14000fa33  lea     esi, [rdi+6]
0x14000fa36  test    al, 1
0x14000fa38  jz      loc_14000FAD8
0x14000fa3e  cmp     byte ptr [rdx+29h], 2
0x14000fa42  jb      loc_14000FAD8
0x14000fa48  test    rbx, rbx
0x14000fa4b  jz      short loc_14000FA5F
0x14000fa4d  mov     rax, rdi
0x14000fa50  inc     rax
0x14000fa53  cmp     byte ptr [rbx+rax], 0
0x14000fa57  jnz     short loc_14000FA50
0x14000fa59  lea     rdx, [rax+1]
0x14000fa5d  jmp     short loc_14000FA62
0x14000fa5f  mov     rdx, rsi
0x14000fa62  mov     rax, cs:pfnWppTraceMessage
0x14000fa69  test    rbx, rbx
0x14000fa6c  mov     [rsp+88h+var_38], 0
0x14000fa75  mov     rcx, rbx
0x14000fa78  cmovz   rcx, r8
0x14000fa7c  mov     [rsp+88h+var_40], rdx
0x14000fa81  mov     [rsp+88h+var_48], rcx
0x14000fa86  lea     r8, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14000fa8d  mov     [rsp+88h+var_50], 8
0x14000fa96  lea     rcx, [rsp+88h+arg_30]
0x14000fa9e  mov     [rsp+88h+var_58], rcx
0x14000faa3  mov     r9d, ebp
0x14000faa6  lea     rcx, [rsp+88h+arg_28]
0x14000faae  mov     [rsp+88h+var_60], 4
0x14000fab7  mov     [rsp+88h+var_68], rcx
0x14000fabc  mov     edx, 2Bh ; '+'
0x14000fac1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fac8  mov     rcx, [rcx+18h]
0x14000facc  call    _guard_dispatch_icall
0x14000fad1  lea     r8, aNull; "NULL"
0x14000fad8  test    rbx, rbx
0x14000fadb  jz      short loc_14000FAED
0x14000fadd  inc     rdi
0x14000fae0  cmp     byte ptr [rbx+rdi], 0
0x14000fae4  jnz     short loc_14000FADD
0x14000fae6  lea     rsi, [rdi+1]
0x14000faea  test    rbx, rbx
0x14000faed  mov     [rsp+88h+var_30], 0
0x14000faf6  lea     rax, [rsp+88h+arg_30]
0x14000fafe  mov     [rsp+88h+var_38], rsi
0x14000fb03  lea     r9, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14000fb0a  cmovz   rbx, r8
0x14000fb0e  mov     edx, 2
0x14000fb13  mov     [rsp+88h+var_40], rbx
0x14000fb18  mov     rcx, r14
0x14000fb1b  mov     [rsp+88h+var_48], 8
0x14000fb24  mov     [rsp+88h+var_50], rax
0x14000fb29  lea     rax, [rsp+88h+arg_28]
0x14000fb31  mov     [rsp+88h+var_58], 4
0x14000fb3a  lea     r8d, [rdx-1]
0x14000fb3e  mov     [rsp+88h+var_60], rax
0x14000fb43  mov     word ptr [rsp+88h+var_68], bp
0x14000fb48  call    cs:__imp_WppAutoLogTrace
0x14000fb4f  nop     dword ptr [rax+rax+00h]
0x14000fb54  add     rsp, 60h
0x14000fb58  pop     r14
0x14000fb5a  pop     rdi
0x14000fb5b  pop     rsi
0x14000fb5c  pop     rbp
0x14000fb5d  pop     rbx
0x14000fb5e  retn
```
