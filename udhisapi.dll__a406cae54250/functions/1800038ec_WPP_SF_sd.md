# WPP_SF_sd

- ea: `0x1800038ec`
- end: `0x180003958`
- name: `WPP_SF_sd`
- size: `108`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const char *)`
- caller_count: `41`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002af0`
- `0x180002dec`
- `0x180002f08`
- `0x180003aa0`
- `0x180003dac`
- `0x18000449c`
- `0x180004c94`
- `0x18000512c`
- `0x180005580`
- `0x180005674`
- `0x180005b68`
- `0x180005e60`
- `0x1800063e0`
- `0x180006764`
- `0x180006868`
- `0x180006f64`
- `0x180007310`
- `0x180007734`
- `0x180007938`
- `0x180007d5c`
- `0x1800080bc`
- `0x1800083f0`
- `0x180008800`
- `0x180008a4c`
- `0x180008e38`
- `0x180009070`
- `0x180009200`
- `0x180009420`
- `0x18000979c`
- `0x180009908`
- `0x180009a74`
- `0x180009d2c`
- `0x18000a070`
- `0x18000a250`
- `0x18000a4a4`
- `0x18000a9b8`
- `0x18000abb0`
- `0x18000ad54`
- `0x18000afb4`
- `0x18000b158`
- `0x18000b608`

## callees

- `0x1800038ec`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000394d`
- `ntdll!EtwTraceMessage` at `0x18000394d`

## pseudocode

```c
__int64 __fastcall WPP_SF_sd(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4)
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
  return EtwTraceMessage(a1, 43, a3, a2, a4);
}

```

## disassembly

```asm
0x1800038ec  sub     rsp, 58h
0x1800038f0  test    r9, r9
0x1800038f3  jz      short loc_180003908
0x1800038f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800038f9  inc     rax
0x1800038fc  cmp     byte ptr [r9+rax], 0
0x180003901  jnz     short loc_1800038F9
0x180003903  inc     rax
0x180003906  jmp     short loc_18000390D
0x180003908  mov     eax, 5
0x18000390d  mov     [rsp+58h+var_18], 0
0x180003916  lea     r10, aNull_0; "NULL"
0x18000391d  test    r9, r9
0x180003920  mov     [rsp+58h+var_20], 4
0x180003929  cmovz   r9, r10
0x18000392d  lea     r10, [rsp+58h+arg_20]
0x180003935  mov     [rsp+58h+var_28], r10
0x18000393a  mov     [rsp+58h+var_30], rax
0x18000393f  mov     [rsp+58h+var_38], r9
0x180003944  movzx   r9d, dx
0x180003948  mov     edx, 2Bh ; '+'
0x18000394d  call    cs:__imp_EtwTraceMessage
0x180003953  add     rsp, 58h
0x180003957  retn
```
