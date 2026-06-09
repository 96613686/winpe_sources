# WPP_SF_sD

- ea: `0x18000a38c`
- end: `0x18000a3ff`
- name: `WPP_SF_sD`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004000`
- `0x180009ee4`

## callees

- `0x18000a38c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000a3f4`
- `ntdll!EtwTraceMessage` at `0x18000a3f4`

## pseudocode

```c
__int64 __fastcall WPP_SF_sD(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4)
{
  __int64 v4; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
  }
  if ( !a4 )
    a4 = "NULL";
  return EtwTraceMessage(a1, 43, WPP_6bd4623f25de30d5bdcfadbe3b7ae59e_Traceguids, a2, a4);
}

```

## disassembly

```asm
0x18000a38c  sub     rsp, 58h
0x18000a390  test    r9, r9
0x18000a393  jz      short loc_18000A3A8
0x18000a395  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a399  inc     rax
0x18000a39c  cmp     byte ptr [r9+rax], 0
0x18000a3a1  jnz     short loc_18000A399
0x18000a3a3  inc     rax
0x18000a3a6  jmp     short loc_18000A3AD
0x18000a3a8  mov     eax, 5
0x18000a3ad  mov     [rsp+58h+var_18], 0
0x18000a3b6  lea     r8, aNull; "NULL"
0x18000a3bd  test    r9, r9
0x18000a3c0  mov     [rsp+58h+var_20], 4
0x18000a3c9  cmovz   r9, r8
0x18000a3cd  lea     r8, [rsp+58h+arg_20]
0x18000a3d5  mov     [rsp+58h+var_28], r8
0x18000a3da  lea     r8, WPP_6bd4623f25de30d5bdcfadbe3b7ae59e_Traceguids
0x18000a3e1  mov     [rsp+58h+var_30], rax
0x18000a3e6  mov     [rsp+58h+var_38], r9
0x18000a3eb  movzx   r9d, dx
0x18000a3ef  mov     edx, 2Bh ; '+'
0x18000a3f4  call    cs:__imp_EtwTraceMessage
0x18000a3fa  add     rsp, 58h
0x18000a3fe  retn
```
