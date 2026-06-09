# WPP_SF_sSSl

- ea: `0x180026cd8`
- end: `0x180026dae`
- name: `WPP_SF_sSSl`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x1800021a0`

## callees

- `0x180026cd8`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180026da2`
- `ntdll!EtwTraceMessage` at `0x180026da2`

## string_xrefs

- `0x180026d6d`: `UpdateStickyShare`

## pseudocode

```c
__int64 __fastcall WPP_SF_sSSl(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
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
  return EtwTraceMessage(a1, 43, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids);
}

```

## disassembly

```asm
0x180026cd8  push    rbx
0x180026cda  sub     rsp, 70h
0x180026cde  mov     r8, [rsp+78h+arg_28]
0x180026ce6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026cea  xor     ebx, ebx
0x180026cec  mov     r10, rcx
0x180026cef  mov     r9d, 0Ah
0x180026cf5  test    r8, r8
0x180026cf8  jz      short loc_180026D11
0x180026cfa  mov     rdx, rax
0x180026cfd  inc     rdx
0x180026d00  cmp     [r8+rdx*2], bx
0x180026d05  jnz     short loc_180026CFD
0x180026d07  lea     rdx, ds:2[rdx*2]
0x180026d0f  jmp     short loc_180026D14
0x180026d11  mov     rdx, r9
0x180026d14  mov     rcx, [rsp+78h+arg_20]
0x180026d1c  lea     r11, aNull_0; "NULL"
0x180026d23  test    r8, r8
0x180026d26  cmovz   r8, r11
0x180026d2a  test    rcx, rcx
0x180026d2d  jz      short loc_180026D43
0x180026d2f  inc     rax
0x180026d32  cmp     [rcx+rax*2], bx
0x180026d36  jnz     short loc_180026D2F
0x180026d38  lea     r9, ds:2[rax*2]
0x180026d40  test    rcx, rcx
0x180026d43  mov     [rsp+78h+var_18], rbx
0x180026d48  lea     rax, [rsp+78h+arg_30]
0x180026d50  mov     [rsp+78h+var_20], 4
0x180026d59  cmovz   rcx, r11
0x180026d5d  mov     [rsp+78h+var_28], rax
0x180026d62  mov     r11d, 5Dh ; ']'
0x180026d68  mov     [rsp+78h+var_30], rdx
0x180026d6d  lea     rax, aUpdatestickysh; "UpdateStickyShare"
0x180026d74  mov     [rsp+78h+var_38], r8
0x180026d79  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180026d80  mov     [rsp+78h+var_40], r9
0x180026d85  mov     r9d, r11d
0x180026d88  mov     [rsp+78h+var_48], rcx
0x180026d8d  lea     edx, [r11-32h]
0x180026d91  mov     [rsp+78h+var_50], 12h
0x180026d9a  mov     rcx, r10
0x180026d9d  mov     [rsp+78h+var_58], rax
0x180026da2  call    cs:__imp_EtwTraceMessage
0x180026da8  add     rsp, 70h
0x180026dac  pop     rbx
0x180026dad  retn
```
