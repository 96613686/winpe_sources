# WPP_SF_SSd

- ea: `0x18000712c`
- end: `0x1800071ec`
- name: `WPP_SF_SSd`
- size: `192`
- prototype: `ULONG(TRACEHANDLE, USHORT, __int64, const wchar_t *, const wchar_t *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002740`
- `0x18000648c`

## callees

- `0x18000712c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800071d4`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800071d4`

## pseudocode

```c
ULONG WPP_SF_SSd(TRACEHANDLE a1, USHORT a2, __int64 a3, const wchar_t *a4, const wchar_t *a5, ...)
{
  const wchar_t *v5; // r10
  __int64 v6; // rax
  __int64 v7; // r11
  __int64 v8; // r8
  __int64 v9; // r8
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
  return TraceMessage(a1, 0x2Bu, &WPP_0a153a6dcad731a9943f71b10be1e25e_Traceguids, a2, a4, v7, v5, v9, va, 4, 0);
}

```

## disassembly

```asm
0x18000712c  mov     [rsp+arg_0], rbx
0x180007131  push    rdi
0x180007132  sub     rsp, 60h
0x180007136  mov     r10, [rsp+68h+arg_20]
0x18000713e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007142  xor     ebx, ebx
0x180007144  mov     r11d, 0Ah
0x18000714a  test    r10, r10
0x18000714d  jz      short loc_180007166
0x18000714f  mov     r8, rax
0x180007152  inc     r8
0x180007155  cmp     [r10+r8*2], bx
0x18000715a  jnz     short loc_180007152
0x18000715c  lea     r8, ds:2[r8*2]
0x180007164  jmp     short loc_180007169
0x180007166  mov     r8, r11
0x180007169  test    r10, r10
0x18000716c  lea     rdi, aNull; "NULL"
0x180007173  cmovz   r10, rdi
0x180007177  test    r9, r9
0x18000717a  jz      short loc_180007191
0x18000717c  inc     rax
0x18000717f  cmp     [r9+rax*2], bx
0x180007184  jnz     short loc_18000717C
0x180007186  lea     r11, ds:2[rax*2]
0x18000718e  test    r9, r9
0x180007191  mov     [rsp+68h+var_18], rbx
0x180007196  lea     rax, [rsp+68h+arg_28]
0x18000719e  mov     [rsp+68h+var_20], 4
0x1800071a7  cmovz   r9, rdi
0x1800071ab  mov     [rsp+68h+var_28], rax
0x1800071b0  mov     [rsp+68h+var_30], r8
0x1800071b5  lea     r8, WPP_0a153a6dcad731a9943f71b10be1e25e_Traceguids; MessageGuid
0x1800071bc  mov     [rsp+68h+var_38], r10
0x1800071c1  mov     [rsp+68h+var_40], r11
0x1800071c6  mov     [rsp+68h+var_48], r9
0x1800071cb  movzx   r9d, dx; MessageNumber
0x1800071cf  mov     edx, 2Bh ; '+'; MessageFlags
0x1800071d4  call    cs:__imp_TraceMessage
0x1800071db  nop     dword ptr [rax+rax+00h]
0x1800071e0  mov     rbx, [rsp+68h+arg_0]
0x1800071e5  add     rsp, 60h
0x1800071e9  pop     rdi
0x1800071ea  retn
```
