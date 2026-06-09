# WPP_SF_SS

- ea: `0x18000ac34`
- end: `0x18000acd9`
- name: `WPP_SF_SS`
- size: `165`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007b28`
- `0x180008b4c`
- `0x18000a168`
- `0x18000ee04`

## callees

- `0x18000ac34`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000acc3`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000acc3`

## pseudocode

```c
ULONG __fastcall WPP_SF_SS(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4, const wchar_t *a5)
{
  const wchar_t *v5; // r11
  __int64 v6; // r10
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  bool v10; // zf

  v5 = a5;
  v6 = -1;
  v7 = 10;
  if ( a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a5[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v7 = 2 * v6 + 2;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = L"NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v7, v5, v9, 0);
}

```

## disassembly

```asm
0x18000ac34  mov     [rsp+arg_0], rbx
0x18000ac39  mov     [rsp+arg_8], rsi
0x18000ac3e  push    rdi
0x18000ac3f  sub     rsp, 50h
0x18000ac43  mov     r11, [rsp+58h+arg_20]
0x18000ac4b  or      r10, 0FFFFFFFFFFFFFFFFh
0x18000ac4f  xor     edi, edi
0x18000ac51  mov     ebx, 0Ah
0x18000ac56  test    r11, r11
0x18000ac59  jz      short loc_18000AC72
0x18000ac5b  mov     rax, r10
0x18000ac5e  inc     rax
0x18000ac61  cmp     [r11+rax*2], di
0x18000ac66  jnz     short loc_18000AC5E
0x18000ac68  lea     rax, ds:2[rax*2]
0x18000ac70  jmp     short loc_18000AC75
0x18000ac72  mov     rax, rbx
0x18000ac75  test    r11, r11
0x18000ac78  lea     rsi, aNull_0; "NULL"
0x18000ac7f  cmovz   r11, rsi
0x18000ac83  test    r9, r9
0x18000ac86  jz      short loc_18000AC9D
0x18000ac88  inc     r10
0x18000ac8b  cmp     [r9+r10*2], di
0x18000ac90  jnz     short loc_18000AC88
0x18000ac92  lea     rbx, ds:2[r10*2]
0x18000ac9a  test    r9, r9
0x18000ac9d  mov     [rsp+58h+var_18], rdi
0x18000aca2  cmovz   r9, rsi
0x18000aca6  mov     [rsp+58h+var_20], rax
0x18000acab  mov     [rsp+58h+var_28], r11
0x18000acb0  mov     [rsp+58h+var_30], rbx
0x18000acb5  mov     [rsp+58h+var_38], r9
0x18000acba  movzx   r9d, dx; MessageNumber
0x18000acbe  mov     edx, 2Bh ; '+'; MessageFlags
0x18000acc3  call    cs:__imp_TraceMessage
0x18000acc9  mov     rbx, [rsp+58h+arg_0]
0x18000acce  mov     rsi, [rsp+58h+arg_8]
0x18000acd3  add     rsp, 50h
0x18000acd7  pop     rdi
0x18000acd8  retn
```
