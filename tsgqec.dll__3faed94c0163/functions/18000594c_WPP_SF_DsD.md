# WPP_SF_DsD

- ea: `0x18000594c`
- end: `0x1800059d8`
- name: `WPP_SF_DsD`
- size: `140`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180007180`
- `0x180007430`
- `0x180007820`
- `0x180008990`
- `0x180008ea0`
- `0x180009170`
- `0x180009380`
- `0x180009960`
- `0x180009bc0`
- `0x18000a090`
- `0x18000a250`
- `0x18000aafc`

## callees

- `0x18000594c`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x1800059cd`
- `ADVAPI32!TraceMessage` at `0x1800059cd`

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
0x18000594c  mov     [rsp+arg_18], r9d
0x180005951  sub     rsp, 68h
0x180005955  mov     r9, [rsp+68h+arg_20]
0x18000595d  test    r9, r9
0x180005960  jz      short loc_180005975
0x180005962  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005966  inc     rax
0x180005969  cmp     byte ptr [r9+rax], 0
0x18000596e  jnz     short loc_180005966
0x180005970  inc     rax
0x180005973  jmp     short loc_18000597A
0x180005975  mov     eax, 5
0x18000597a  mov     [rsp+68h+var_18], 0
0x180005983  lea     r10, aNull; "NULL"
0x18000598a  mov     r11d, 4
0x180005990  test    r9, r9
0x180005993  mov     [rsp+68h+var_20], r11
0x180005998  cmovz   r9, r10
0x18000599c  lea     r10, [rsp+68h+arg_28]
0x1800059a4  mov     [rsp+68h+var_28], r10
0x1800059a9  mov     [rsp+68h+var_30], rax
0x1800059ae  lea     rax, [rsp+68h+arg_18]
0x1800059b6  mov     [rsp+68h+var_38], r9
0x1800059bb  movzx   r9d, dx; MessageNumber
0x1800059bf  lea     edx, [r11+27h]; MessageFlags
0x1800059c3  mov     [rsp+68h+var_40], r11
0x1800059c8  mov     [rsp+68h+var_48], rax
0x1800059cd  call    cs:__imp_TraceMessage
0x1800059d3  add     rsp, 68h
0x1800059d7  retn
```
