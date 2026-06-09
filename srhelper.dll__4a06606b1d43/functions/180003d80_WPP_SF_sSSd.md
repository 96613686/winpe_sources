# WPP_SF_sSSd

- ea: `0x180003d80`
- end: `0x180003e56`
- name: `WPP_SF_sSSd`
- size: `214`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180002054`
- `0x1800022e4`

## callees

- `0x180003d80`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180003e4a`
- `ntdll!EtwTraceMessage` at `0x180003e4a`

## string_xrefs

- `0x180003e15`: `::MoveFileEx( strTempFileName, strFileName, MOVEFILE_REPLACE_EXISTING | MOVEFILE_WRITE_THROUGH )`

## pseudocode

```c
__int64 __fastcall WPP_SF_sSSd(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int64 v6; // rax
  __int64 v7; // rdx

  v6 = -1;
  if ( a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(a6 + 2 * v7) );
  }
  if ( a5 )
  {
    do
      ++v6;
    while ( *(_WORD *)(a5 + 2 * v6) );
  }
  return EtwTraceMessage(
           a1,
           43,
           WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids,
           13,
           "::MoveFileEx( strTempFileName, strFileName, MOVEFILE_REPLACE_EXISTING | MOVEFILE_WRITE_THROUGH )");
}

```

## disassembly

```asm
0x180003d80  push    rbx
0x180003d82  sub     rsp, 70h
0x180003d86  mov     r8, [rsp+78h+arg_28]
0x180003d8e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003d92  xor     ebx, ebx
0x180003d94  mov     r10, rcx
0x180003d97  mov     r9d, 0Ah
0x180003d9d  test    r8, r8
0x180003da0  jz      short loc_180003DB9
0x180003da2  mov     rdx, rax
0x180003da5  inc     rdx
0x180003da8  cmp     [r8+rdx*2], bx
0x180003dad  jnz     short loc_180003DA5
0x180003daf  lea     rdx, ds:2[rdx*2]
0x180003db7  jmp     short loc_180003DBC
0x180003db9  mov     rdx, r9
0x180003dbc  mov     rcx, [rsp+78h+arg_20]
0x180003dc4  lea     r11, aNull_0; "NULL"
0x180003dcb  test    r8, r8
0x180003dce  cmovz   r8, r11
0x180003dd2  test    rcx, rcx
0x180003dd5  jz      short loc_180003DEB
0x180003dd7  inc     rax
0x180003dda  cmp     [rcx+rax*2], bx
0x180003dde  jnz     short loc_180003DD7
0x180003de0  lea     r9, ds:2[rax*2]
0x180003de8  test    rcx, rcx
0x180003deb  mov     [rsp+78h+var_18], rbx
0x180003df0  lea     rax, [rsp+78h+arg_30]
0x180003df8  mov     [rsp+78h+var_20], 4
0x180003e01  cmovz   rcx, r11
0x180003e05  mov     [rsp+78h+var_28], rax
0x180003e0a  mov     r11d, 0Dh
0x180003e10  mov     [rsp+78h+var_30], rdx
0x180003e15  lea     rax, aMovefileexStrt; "::MoveFileEx( strTempFileName, strFileN"...
0x180003e1c  mov     [rsp+78h+var_38], r8
0x180003e21  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x180003e28  mov     [rsp+78h+var_40], r9
0x180003e2d  mov     r9d, r11d
0x180003e30  mov     [rsp+78h+var_48], rcx
0x180003e35  lea     edx, [r11+1Eh]
0x180003e39  mov     [rsp+78h+var_50], 61h ; 'a'
0x180003e42  mov     rcx, r10
0x180003e45  mov     [rsp+78h+var_58], rax
0x180003e4a  call    cs:__imp_EtwTraceMessage
0x180003e50  add     rsp, 70h
0x180003e54  pop     rbx
0x180003e55  retn
```
