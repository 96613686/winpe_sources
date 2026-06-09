# WPP_SF_SD

- ea: `0x18000abbc`
- end: `0x18000ac2c`
- name: `WPP_SF_SD`
- size: `112`
- prototype: ``
- caller_count: `27`
- callee_count: `1`
- tags: ``

## callers

- `0x180007b28`
- `0x1800085ac`
- `0x180008b4c`
- `0x1800095c0`
- `0x1800099b4`
- `0x18000a168`
- `0x18000b114`
- `0x18000b4b8`
- `0x18000bac8`
- `0x18000c240`
- `0x18000d070`
- `0x18000d43c`
- `0x18000daac`
- `0x18000ded4`
- `0x18000e140`
- `0x18000e40c`
- `0x18000e61c`
- `0x18000e8bc`
- `0x18000ebc0`
- `0x18000ee04`
- `0x18000f010`
- `0x18000f238`
- `0x18000f484`
- `0x18000f7c4`
- `0x180010a54`
- `0x180010dcc`
- `0x180010ff4`

## callees

- `0x18000abbc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ac21`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ac21`

## pseudocode

```c
ULONG WPP_SF_SD(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4, ...)
{
  __int64 v4; // rax
  __int64 v5; // rax
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, va, 4, 0);
}

```

## disassembly

```asm
0x18000abbc  sub     rsp, 58h
0x18000abc0  xor     r11d, r11d
0x18000abc3  test    r9, r9
0x18000abc6  jz      short loc_18000ABE0
0x18000abc8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000abcc  inc     rax
0x18000abcf  cmp     [r9+rax*2], r11w
0x18000abd4  jnz     short loc_18000ABCC
0x18000abd6  lea     rax, ds:2[rax*2]
0x18000abde  jmp     short loc_18000ABE5
0x18000abe0  mov     eax, 0Ah
0x18000abe5  mov     [rsp+58h+var_18], r11
0x18000abea  lea     r10, aNull_0; "NULL"
0x18000abf1  test    r9, r9
0x18000abf4  mov     [rsp+58h+var_20], 4
0x18000abfd  cmovz   r9, r10
0x18000ac01  lea     r10, [rsp+58h+arg_20]
0x18000ac09  mov     [rsp+58h+var_28], r10
0x18000ac0e  mov     [rsp+58h+var_30], rax
0x18000ac13  mov     [rsp+58h+var_38], r9
0x18000ac18  movzx   r9d, dx; MessageNumber
0x18000ac1c  mov     edx, 2Bh ; '+'; MessageFlags
0x18000ac21  call    cs:__imp_TraceMessage
0x18000ac27  add     rsp, 58h
0x18000ac2b  retn
```
