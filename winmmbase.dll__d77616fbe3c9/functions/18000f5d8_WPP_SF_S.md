# WPP_SF_S

- ea: `0x18000f5d8`
- end: `0x18000f632`
- name: `WPP_SF_S`
- size: `90`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800011e4`
- `0x180001660`
- `0x180002558`
- `0x180002718`
- `0x1800027d8`
- `0x180002eb0`
- `0x180003460`

## callees

- `0x18000f5d8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000f627`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000f627`

## pseudocode

```c
ULONG __fastcall WPP_SF_S(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  __int64 v5; // rax

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
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, 0);
}

```

## disassembly

```asm
0x18000f5d8  sub     rsp, 48h
0x18000f5dc  xor     r11d, r11d
0x18000f5df  test    r9, r9
0x18000f5e2  jz      short loc_18000F5FC
0x18000f5e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f5e8  inc     rax
0x18000f5eb  cmp     [r9+rax*2], r11w
0x18000f5f0  jnz     short loc_18000F5E8
0x18000f5f2  lea     rax, ds:2[rax*2]
0x18000f5fa  jmp     short loc_18000F601
0x18000f5fc  mov     eax, 0Ah
0x18000f601  test    r9, r9
0x18000f604  mov     [rsp+48h+var_18], r11
0x18000f609  lea     r10, aNull_1; "NULL"
0x18000f610  mov     [rsp+48h+var_20], rax
0x18000f615  cmovz   r9, r10
0x18000f619  mov     [rsp+48h+var_28], r9
0x18000f61e  movzx   r9d, dx; MessageNumber
0x18000f622  mov     edx, 2Bh ; '+'; MessageFlags
0x18000f627  call    cs:__imp_TraceMessage
0x18000f62d  add     rsp, 48h
0x18000f631  retn
```
