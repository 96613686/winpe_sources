# WPP_SF_DsD

- ea: `0x180014bb0`
- end: `0x180014c3c`
- name: `WPP_SF_DsD`
- size: `140`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x180012690`
- `0x180012a78`
- `0x180012c20`
- `0x180012e70`
- `0x180013020`
- `0x1800131b0`
- `0x180013290`
- `0x1800133f0`
- `0x180013600`
- `0x180013990`
- `0x180013c70`
- `0x180013d30`
- `0x180013e30`
- `0x180013fa0`
- `0x1800140f0`
- `0x180014230`
- `0x180014390`
- `0x1800144a4`
- `0x180014698`
- `0x180014898`
- `0x180014c74`

## callees

- `0x180014bb0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180014c31`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180014c31`

## pseudocode

```c
ULONG WPP_SF_DsD(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4, const char *a5, ...)
{
  const char *v5; // r9
  __int64 v6; // rax
  __int64 v7; // rax
  int v9; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v9 = a4;
  v5 = a5;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a5[v6] );
    v7 = v6 + 1;
  }
  else
  {
    v7 = 5;
  }
  if ( !a5 )
    v5 = "NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, &v9, 4, v5, v7, va, 4, 0);
}

```

## disassembly

```asm
0x180014bb0  mov     [rsp+arg_18], r9d
0x180014bb5  sub     rsp, 68h
0x180014bb9  mov     r9, [rsp+68h+arg_20]
0x180014bc1  test    r9, r9
0x180014bc4  jz      short loc_180014BD9
0x180014bc6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014bca  inc     rax
0x180014bcd  cmp     byte ptr [r9+rax], 0
0x180014bd2  jnz     short loc_180014BCA
0x180014bd4  inc     rax
0x180014bd7  jmp     short loc_180014BDE
0x180014bd9  mov     eax, 5
0x180014bde  mov     [rsp+68h+var_18], 0
0x180014be7  lea     r10, aNull; "NULL"
0x180014bee  mov     r11d, 4
0x180014bf4  test    r9, r9
0x180014bf7  mov     [rsp+68h+var_20], r11
0x180014bfc  cmovz   r9, r10
0x180014c00  lea     r10, [rsp+68h+arg_28]
0x180014c08  mov     [rsp+68h+var_28], r10
0x180014c0d  mov     [rsp+68h+var_30], rax
0x180014c12  lea     rax, [rsp+68h+arg_18]
0x180014c1a  mov     [rsp+68h+var_38], r9
0x180014c1f  movzx   r9d, dx; MessageNumber
0x180014c23  lea     edx, [r11+27h]; MessageFlags
0x180014c27  mov     [rsp+68h+var_40], r11
0x180014c2c  mov     [rsp+68h+var_48], rax
0x180014c31  call    cs:__imp_TraceMessage
0x180014c37  add     rsp, 68h
0x180014c3b  retn
```
