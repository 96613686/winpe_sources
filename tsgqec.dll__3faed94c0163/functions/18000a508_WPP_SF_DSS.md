# WPP_SF_DSS

- ea: `0x18000a508`
- end: `0x18000a5d7`
- name: `WPP_SF_DSS`
- size: `207`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, __int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007180`
- `0x180009bc0`
- `0x180009d6c`
- `0x18000a090`
- `0x18000a250`

## callees

- `0x18000a508`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000a5c1`
- `ADVAPI32!TraceMessage` at `0x18000a5c1`

## pseudocode

```c
ULONG __fastcall WPP_SF_DSS(
        TRACEHANDLE LoggerHandle,
        USHORT a2,
        const GUID *a3,
        int a4,
        const wchar_t *a5,
        const wchar_t *a6)
{
  const wchar_t *v6; // r10
  __int64 v7; // r9
  __int64 v9; // r11
  __int64 v10; // rax
  __int64 v11; // rcx
  const wchar_t *v12; // rax
  bool v13; // zf
  int v15; // [rsp+88h] [rbp+20h] BYREF

  v15 = a4;
  v6 = a6;
  v7 = -1;
  v9 = 10;
  if ( a6 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a6[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v12 = a5;
  if ( !a6 )
    v6 = L"NULL";
  v13 = a5 == 0;
  if ( a5 )
  {
    do
      ++v7;
    while ( a5[v7] );
    v9 = 2 * v7 + 2;
    v13 = a5 == 0;
  }
  if ( v13 )
    v12 = L"NULL";
  return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, &v15, 4, v12, v9, v6, v11, 0);
}

```

## disassembly

```asm
0x18000a508  mov     [rsp+arg_0], rbx
0x18000a50d  mov     [rsp+arg_8], rsi
0x18000a512  mov     [rsp+arg_18], r9d
0x18000a517  push    rdi
0x18000a518  sub     rsp, 60h
0x18000a51c  mov     r10, [rsp+68h+arg_28]
0x18000a524  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000a528  xor     edi, edi
0x18000a52a  mov     rbx, rcx
0x18000a52d  mov     r11d, 0Ah
0x18000a533  test    r10, r10
0x18000a536  jz      short loc_18000A54F
0x18000a538  mov     rax, r9
0x18000a53b  inc     rax
0x18000a53e  cmp     [r10+rax*2], di
0x18000a543  jnz     short loc_18000A53B
0x18000a545  lea     rcx, ds:2[rax*2]
0x18000a54d  jmp     short loc_18000A552
0x18000a54f  mov     rcx, r11
0x18000a552  mov     rax, [rsp+68h+arg_20]
0x18000a55a  lea     rsi, aNull_0; "NULL"
0x18000a561  test    r10, r10
0x18000a564  cmovz   r10, rsi
0x18000a568  test    rax, rax
0x18000a56b  jz      short loc_18000A582
0x18000a56d  inc     r9
0x18000a570  cmp     [rax+r9*2], di
0x18000a575  jnz     short loc_18000A56D
0x18000a577  lea     r11, ds:2[r9*2]
0x18000a57f  test    rax, rax
0x18000a582  mov     [rsp+68h+var_18], rdi
0x18000a587  cmovz   rax, rsi
0x18000a58b  mov     [rsp+68h+var_20], rcx
0x18000a590  mov     rcx, rbx; LoggerHandle
0x18000a593  mov     [rsp+68h+var_28], r10
0x18000a598  mov     [rsp+68h+var_30], r11
0x18000a59d  mov     [rsp+68h+var_38], rax
0x18000a5a2  lea     rax, [rsp+68h+arg_18]
0x18000a5aa  movzx   r9d, dx; MessageNumber
0x18000a5ae  mov     edx, 2Bh ; '+'; MessageFlags
0x18000a5b3  mov     [rsp+68h+var_40], 4
0x18000a5bc  mov     [rsp+68h+var_48], rax
0x18000a5c1  call    cs:__imp_TraceMessage
0x18000a5c7  mov     rbx, [rsp+68h+arg_0]
0x18000a5cc  mov     rsi, [rsp+68h+arg_8]
0x18000a5d1  add     rsp, 60h
0x18000a5d5  pop     rdi
0x18000a5d6  retn
```
