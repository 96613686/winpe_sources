# WPP_SF_DSd

- ea: `0x18000a7b8`
- end: `0x18000a84f`
- name: `WPP_SF_DSd`
- size: `151`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007180`
- `0x180007430`
- `0x180007820`
- `0x180008bc0`
- `0x1800095c8`

## callees

- `0x18000a7b8`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000a844`
- `ADVAPI32!TraceMessage` at `0x18000a844`

## pseudocode

```c
ULONG WPP_SF_DSd(TRACEHANDLE a1, USHORT a2, __int64 a3, int a4, const wchar_t *a5, ...)
{
  const wchar_t *v5; // r8
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
    v7 = 2 * v6 + 2;
  }
  else
  {
    v7 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  return TraceMessage(a1, 0x2Bu, &WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids, a2, &v9, 4, v5, v7, va, 4, 0);
}

```

## disassembly

```asm
0x18000a7b8  mov     [rsp+arg_18], r9d
0x18000a7bd  sub     rsp, 68h
0x18000a7c1  mov     r8, [rsp+68h+arg_20]
0x18000a7c9  xor     r10d, r10d
0x18000a7cc  test    r8, r8
0x18000a7cf  jz      short loc_18000A7E9
0x18000a7d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a7d5  inc     rax
0x18000a7d8  cmp     [r8+rax*2], r10w
0x18000a7dd  jnz     short loc_18000A7D5
0x18000a7df  lea     rax, ds:2[rax*2]
0x18000a7e7  jmp     short loc_18000A7EE
0x18000a7e9  mov     eax, 0Ah
0x18000a7ee  mov     [rsp+68h+var_18], r10
0x18000a7f3  lea     r9, aNull_0; "NULL"
0x18000a7fa  mov     r10d, 4
0x18000a800  test    r8, r8
0x18000a803  mov     [rsp+68h+var_20], r10
0x18000a808  cmovz   r8, r9
0x18000a80c  lea     r9, [rsp+68h+arg_28]
0x18000a814  mov     [rsp+68h+var_28], r9
0x18000a819  mov     [rsp+68h+var_30], rax
0x18000a81e  lea     rax, [rsp+68h+arg_18]
0x18000a826  mov     [rsp+68h+var_38], r8
0x18000a82b  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids; MessageGuid
0x18000a832  movzx   r9d, dx; MessageNumber
0x18000a836  lea     edx, [r10+27h]; MessageFlags
0x18000a83a  mov     [rsp+68h+var_40], r10
0x18000a83f  mov     [rsp+68h+var_48], rax
0x18000a844  call    cs:__imp_TraceMessage
0x18000a84a  add     rsp, 68h
0x18000a84e  retn
```
