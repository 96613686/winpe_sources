# WPP_SF_sq_SOCKADDR_

- ea: `0x140013d04`
- end: `0x140013db7`
- name: `WPP_SF_sq_SOCKADDR_`
- size: `179`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002920`
- `0x140002fb0`
- `0x140004df4`

## callees

- `0x140013d04`
- `0x140018590`

## pseudocode

```c
__int64 __fastcall WPP_SF_sq_SOCKADDR_(
        __int64 a1,
        unsigned __int16 a2,
        __int64 a3,
        const char *a4,
        char a5,
        __int64 a6)
{
  __int64 v6; // rax
  __int64 v7; // r10

  if ( a4 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a4[v6] );
    v7 = v6 + 1;
  }
  else
  {
    v7 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return pfnWppTraceMessage(
           a1,
           43,
           WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
           a2,
           a4,
           v7,
           &a5,
           8,
           a6 + 8,
           2,
           *(_QWORD *)a6,
           *(unsigned __int16 *)(a6 + 8),
           0);
}

```

## disassembly

```asm
0x140013d04  push    rbx
0x140013d06  sub     rsp, 70h
0x140013d0a  movzx   r11d, dx
0x140013d0e  mov     rbx, rcx
0x140013d11  test    r9, r9
0x140013d14  jz      short loc_140013D2A
0x140013d16  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013d1a  inc     rax
0x140013d1d  cmp     byte ptr [r9+rax], 0
0x140013d22  jnz     short loc_140013D1A
0x140013d24  lea     r10, [rax+1]
0x140013d28  jmp     short loc_140013D30
0x140013d2a  mov     r10d, 5
0x140013d30  mov     rdx, [rsp+78h+arg_28]
0x140013d38  lea     rax, aNull; "NULL"
0x140013d3f  mov     [rsp+78h+var_18], 0
0x140013d48  test    r9, r9
0x140013d4b  cmovz   r9, rax
0x140013d4f  mov     rax, cs:pfnWppTraceMessage
0x140013d56  lea     r8, [rdx+8]
0x140013d5a  movzx   ecx, word ptr [r8]
0x140013d5e  mov     [rsp+78h+var_20], rcx
0x140013d63  mov     rcx, [rdx]
0x140013d66  mov     edx, 2Bh ; '+'
0x140013d6b  mov     [rsp+78h+var_28], rcx
0x140013d70  lea     rcx, [rsp+78h+arg_20]
0x140013d78  mov     [rsp+78h+var_30], 2
0x140013d81  mov     [rsp+78h+var_38], r8
0x140013d86  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140013d8d  mov     [rsp+78h+var_40], 8
0x140013d96  mov     [rsp+78h+var_48], rcx
0x140013d9b  mov     rcx, rbx
0x140013d9e  mov     [rsp+78h+var_50], r10
0x140013da3  mov     [rsp+78h+var_58], r9
0x140013da8  mov     r9d, r11d
0x140013dab  call    _guard_dispatch_icall
0x140013db0  add     rsp, 70h
0x140013db4  pop     rbx
0x140013db5  retn
```
