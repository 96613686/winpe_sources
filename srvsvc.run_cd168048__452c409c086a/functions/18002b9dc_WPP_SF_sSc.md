# WPP_SF_sSc

- ea: `0x18002b9dc`
- end: `0x18002ba71`
- name: `WPP_SF_sSc`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003f60`

## callees

- `0x18002b9dc`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18002ba66`
- `ntdll!EtwTraceMessage` at `0x18002ba66`

## string_xrefs

- `0x18002ba48`: `I_NetrShareAdd`

## pseudocode

```c
__int64 __fastcall WPP_SF_sSc(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v5; // rax

  if ( a5 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)(a5 + 2 * v5) );
  }
  return EtwTraceMessage(a1, 43, WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids);
}

```

## disassembly

```asm
0x18002b9dc  sub     rsp, 68h
0x18002b9e0  mov     rdx, [rsp+68h+arg_20]
0x18002b9e8  xor     r10d, r10d
0x18002b9eb  test    rdx, rdx
0x18002b9ee  jz      short loc_18002BA08
0x18002b9f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b9f4  inc     rax
0x18002b9f7  cmp     [rdx+rax*2], r10w
0x18002b9fc  jnz     short loc_18002B9F4
0x18002b9fe  lea     rax, ds:2[rax*2]
0x18002ba06  jmp     short loc_18002BA0D
0x18002ba08  mov     eax, 0Ah
0x18002ba0d  mov     [rsp+68h+var_18], r10
0x18002ba12  lea     r8, aNull_0; "NULL"
0x18002ba19  mov     [rsp+68h+var_20], 1
0x18002ba22  test    rdx, rdx
0x18002ba25  mov     r9d, 12h
0x18002ba2b  cmovz   rdx, r8
0x18002ba2f  lea     r8, [rsp+68h+arg_28]
0x18002ba37  mov     [rsp+68h+var_28], r8
0x18002ba3c  lea     r8, WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids
0x18002ba43  mov     [rsp+68h+var_30], rax
0x18002ba48  lea     rax, aINetrshareadd; "I_NetrShareAdd"
0x18002ba4f  mov     [rsp+68h+var_38], rdx
0x18002ba54  lea     edx, [r9+19h]
0x18002ba58  mov     [rsp+68h+var_40], 0Fh
0x18002ba61  mov     [rsp+68h+var_48], rax
0x18002ba66  call    cs:__imp_EtwTraceMessage
0x18002ba6c  add     rsp, 68h
0x18002ba70  retn
```
