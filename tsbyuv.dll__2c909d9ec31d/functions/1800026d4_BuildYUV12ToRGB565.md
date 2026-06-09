# BuildYUV12ToRGB565

- ea: `0x1800026d4`
- end: `0x180002765`
- name: `BuildYUV12ToRGB565`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002028`

## callees

- `0x1800026d4`
- `0x180002840`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800026f6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800026f6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002704`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002704`

## pseudocode

```c
_WORD *__fastcall BuildYUV12ToRGB565(__int64 a1)
{
  _WORD *result; // rax
  _WORD *v2; // rbx
  HGLOBAL v3; // rax
  _WORD *v4; // rax
  _WORD *v5; // rsi
  unsigned __int16 i; // di

  result = *(_WORD **)(a1 + 8);
  if ( !result )
  {
    v2 = 0;
    v3 = GlobalAlloc(0x40u, 0x10000u);
    if ( v3 )
    {
      v4 = GlobalLock(v3);
      v2 = v4;
      if ( v4 )
      {
        v5 = v4;
        for ( i = 0; i < 0x8000u; ++i )
          *v5++ = TosYUVToRGB565((i >> 7) & 0xF8, (i >> 2) & 0xF8, 8 * (i & 0x1Fu));
      }
    }
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x1800026d4  mov     [rsp+arg_0], rbx
0x1800026d9  mov     [rsp+arg_8], rsi
0x1800026de  push    rdi
0x1800026df  sub     rsp, 20h
0x1800026e3  mov     rax, [rcx+8]
0x1800026e7  test    rax, rax
0x1800026ea  jnz     short loc_180002755
0x1800026ec  mov     edx, 10000h; dwBytes
0x1800026f1  lea     ecx, [rax+40h]; uFlags
0x1800026f4  xor     ebx, ebx
0x1800026f6  call    cs:__imp_GlobalAlloc
0x1800026fc  test    rax, rax
0x1800026ff  jz      short loc_180002752
0x180002701  mov     rcx, rax; hMem
0x180002704  call    cs:__imp_GlobalLock
0x18000270a  mov     rbx, rax
0x18000270d  test    rax, rax
0x180002710  jz      short loc_180002752
0x180002712  mov     rsi, rax
0x180002715  xor     edi, edi
0x180002717  movzx   ecx, di
0x18000271a  mov     r8d, ecx
0x18000271d  mov     edx, ecx
0x18000271f  shr     edx, 2
0x180002722  and     r8d, 1Fh
0x180002726  shr     ecx, 7
0x180002729  and     edx, 0F8h
0x18000272f  shl     r8d, 3
0x180002733  and     ecx, 0F8h
0x180002739  call    TosYUVToRGB565
0x18000273e  mov     [rsi], ax
0x180002741  inc     di
0x180002744  mov     eax, 8000h
0x180002749  lea     rsi, [rsi+2]
0x18000274d  cmp     di, ax
0x180002750  jb      short loc_180002717
0x180002752  mov     rax, rbx
0x180002755  mov     rbx, [rsp+28h+arg_0]
0x18000275a  mov     rsi, [rsp+28h+arg_8]
0x18000275f  add     rsp, 20h
0x180002763  pop     rdi
0x180002764  retn
```
