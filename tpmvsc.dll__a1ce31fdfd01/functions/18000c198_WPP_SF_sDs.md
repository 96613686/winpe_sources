# WPP_SF_sDs

- ea: `0x18000c198`
- end: `0x18000c242`
- name: `WPP_SF_sDs`
- size: `170`
- prototype: ``
- caller_count: `171`
- callee_count: `1`
- tags: ``

## callers

- `0x180006038`
- `0x180006a54`
- `0x180006c74`
- `0x180006dc0`
- `0x180007064`
- `0x180007170`
- `0x1800073cc`
- `0x180007628`
- `0x180007a78`
- `0x180007bcc`
- `0x1800081c0`
- `0x180008324`
- `0x1800085b8`
- `0x180008d28`
- `0x180009154`
- `0x1800093c8`
- `0x180009834`
- `0x180009d24`
- `0x180009ea4`
- `0x18000a1b8`
- `0x18000a46c`
- `0x18000a81c`
- `0x18000acb4`
- `0x18000b85c`
- `0x18000c404`
- `0x18000f53c`
- `0x18000f6a0`
- `0x18001001c`
- `0x180010298`
- `0x1800105b4`
- `0x180010b0c`
- `0x180010cdc`
- `0x180010e90`
- `0x1800110c0`
- `0x18001130c`
- `0x1800116a0`
- `0x18001195c`
- `0x180011c40`
- `0x180012074`
- `0x1800121dc`
- `0x180012990`
- `0x180012e58`
- `0x180013434`
- `0x1800135d4`
- `0x180013814`
- `0x180013cc4`
- `0x180014130`
- `0x1800143b4`
- `0x180014524`
- `0x1800146b8`

## callees

- `0x18000c198`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000c231`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000c231`

## pseudocode

```c
ULONG __fastcall WPP_SF_sDs(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4, char a5, const char *a6)
{
  const char *v6; // r11
  __int64 v7; // r10
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  bool v11; // zf

  v6 = a6;
  v7 = -1;
  v8 = 5;
  if ( a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a6[v9] );
    v10 = v9 + 1;
  }
  else
  {
    v10 = 5;
  }
  if ( !a6 )
    v6 = "NULL";
  v11 = a4 == 0;
  if ( a4 )
  {
    do
      ++v7;
    while ( a4[v7] );
    v8 = v7 + 1;
    v11 = a4 == 0;
  }
  if ( v11 )
    a4 = "NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v8, &a5, 4, v6, v10, 0);
}

```

## disassembly

```asm
0x18000c198  mov     [rsp+arg_0], rbx
0x18000c19d  push    rsi
0x18000c19e  sub     rsp, 60h
0x18000c1a2  mov     r11, [rsp+68h+arg_28]
0x18000c1aa  or      r10, 0FFFFFFFFFFFFFFFFh
0x18000c1ae  mov     ebx, 5
0x18000c1b3  test    r11, r11
0x18000c1b6  jz      short loc_18000C1CA
0x18000c1b8  mov     rax, r10
0x18000c1bb  inc     rax
0x18000c1be  cmp     byte ptr [r11+rax], 0
0x18000c1c3  jnz     short loc_18000C1BB
0x18000c1c5  inc     rax
0x18000c1c8  jmp     short loc_18000C1CD
0x18000c1ca  mov     rax, rbx
0x18000c1cd  test    r11, r11
0x18000c1d0  lea     rsi, aNull; "NULL"
0x18000c1d7  cmovz   r11, rsi
0x18000c1db  test    r9, r9
0x18000c1de  jz      short loc_18000C1F1
0x18000c1e0  inc     r10
0x18000c1e3  cmp     byte ptr [r9+r10], 0
0x18000c1e8  jnz     short loc_18000C1E0
0x18000c1ea  lea     rbx, [r10+1]
0x18000c1ee  test    r9, r9
0x18000c1f1  mov     [rsp+68h+var_18], 0
0x18000c1fa  cmovz   r9, rsi
0x18000c1fe  mov     [rsp+68h+var_20], rax
0x18000c203  lea     rax, [rsp+68h+arg_20]
0x18000c20b  mov     [rsp+68h+var_28], r11
0x18000c210  mov     [rsp+68h+var_30], 4
0x18000c219  mov     [rsp+68h+var_38], rax
0x18000c21e  mov     [rsp+68h+var_40], rbx
0x18000c223  mov     [rsp+68h+var_48], r9
0x18000c228  movzx   r9d, dx; MessageNumber
0x18000c22c  mov     edx, 2Bh ; '+'; MessageFlags
0x18000c231  call    cs:__imp_TraceMessage
0x18000c237  mov     rbx, [rsp+68h+arg_0]
0x18000c23c  add     rsp, 60h
0x18000c240  pop     rsi
0x18000c241  retn
```
