# WPP_SF_SSD

- ea: `0x18000ace0`
- end: `0x18000ad9b`
- name: `WPP_SF_SSD`
- size: `187`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180007b28`
- `0x180008b4c`
- `0x1800095c0`
- `0x18000bac8`
- `0x18000c240`
- `0x18000c5c8`
- `0x18000daac`
- `0x18000ebc0`

## callees

- `0x18000ace0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ad85`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ad85`

## pseudocode

```c
ULONG WPP_SF_SSD(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4, const wchar_t *a5, ...)
{
  const wchar_t *v5; // r11
  __int64 v6; // r10
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  bool v10; // zf
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
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
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v7, v5, v9, va, 4, 0);
}

```

## disassembly

```asm
0x18000ace0  mov     [rsp+arg_0], rbx
0x18000ace5  mov     [rsp+arg_8], rsi
0x18000acea  push    rdi
0x18000aceb  sub     rsp, 60h
0x18000acef  mov     r11, [rsp+68h+arg_20]
0x18000acf7  or      r10, 0FFFFFFFFFFFFFFFFh
0x18000acfb  xor     edi, edi
0x18000acfd  mov     ebx, 0Ah
0x18000ad02  test    r11, r11
0x18000ad05  jz      short loc_18000AD1E
0x18000ad07  mov     rax, r10
0x18000ad0a  inc     rax
0x18000ad0d  cmp     [r11+rax*2], di
0x18000ad12  jnz     short loc_18000AD0A
0x18000ad14  lea     rax, ds:2[rax*2]
0x18000ad1c  jmp     short loc_18000AD21
0x18000ad1e  mov     rax, rbx
0x18000ad21  test    r11, r11
0x18000ad24  lea     rsi, aNull_0; "NULL"
0x18000ad2b  cmovz   r11, rsi
0x18000ad2f  test    r9, r9
0x18000ad32  jz      short loc_18000AD49
0x18000ad34  inc     r10
0x18000ad37  cmp     [r9+r10*2], di
0x18000ad3c  jnz     short loc_18000AD34
0x18000ad3e  lea     rbx, ds:2[r10*2]
0x18000ad46  test    r9, r9
0x18000ad49  mov     [rsp+68h+var_18], rdi
0x18000ad4e  lea     r10, [rsp+68h+arg_28]
0x18000ad56  mov     [rsp+68h+var_20], 4
0x18000ad5f  cmovz   r9, rsi
0x18000ad63  mov     [rsp+68h+var_28], r10
0x18000ad68  mov     [rsp+68h+var_30], rax
0x18000ad6d  mov     [rsp+68h+var_38], r11
0x18000ad72  mov     [rsp+68h+var_40], rbx
0x18000ad77  mov     [rsp+68h+var_48], r9
0x18000ad7c  movzx   r9d, dx; MessageNumber
0x18000ad80  mov     edx, 2Bh ; '+'; MessageFlags
0x18000ad85  call    cs:__imp_TraceMessage
0x18000ad8b  mov     rbx, [rsp+68h+arg_0]
0x18000ad90  mov     rsi, [rsp+68h+arg_8]
0x18000ad95  add     rsp, 60h
0x18000ad99  pop     rdi
0x18000ad9a  retn
```
