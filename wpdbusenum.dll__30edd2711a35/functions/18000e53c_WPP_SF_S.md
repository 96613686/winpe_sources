# WPP_SF_S

- ea: `0x18000e53c`
- end: `0x18000e596`
- name: `WPP_SF_S`
- size: `90`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const char *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800018c0`
- `0x1800022c0`
- `0x180002b00`
- `0x180003cd0`
- `0x180003ed0`
- `0x180004620`
- `0x1800060b0`
- `0x180008128`
- `0x18000e260`
- `0x18000e5d0`

## callees

- `0x18000e53c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000e58b`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000e58b`

## pseudocode

```c
ULONG __fastcall WPP_SF_S(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&a4[2 * v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, 0);
}

```

## disassembly

```asm
0x18000e53c  sub     rsp, 48h
0x18000e540  xor     r11d, r11d
0x18000e543  test    r9, r9
0x18000e546  jz      short loc_18000E560
0x18000e548  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e54c  inc     rax
0x18000e54f  cmp     [r9+rax*2], r11w
0x18000e554  jnz     short loc_18000E54C
0x18000e556  lea     rax, ds:2[rax*2]
0x18000e55e  jmp     short loc_18000E565
0x18000e560  mov     eax, 0Ah
0x18000e565  test    r9, r9
0x18000e568  mov     [rsp+48h+var_18], r11
0x18000e56d  lea     r10, aNull_0; "NULL"
0x18000e574  mov     [rsp+48h+var_20], rax
0x18000e579  cmovz   r9, r10
0x18000e57d  mov     [rsp+48h+var_28], r9
0x18000e582  movzx   r9d, dx; MessageNumber
0x18000e586  mov     edx, 2Bh ; '+'; MessageFlags
0x18000e58b  call    cs:__imp_TraceMessage
0x18000e591  add     rsp, 48h
0x18000e595  retn
```
