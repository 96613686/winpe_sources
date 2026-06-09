# BuildYUV12ToRGB555

- ea: `0x18000263c`
- end: `0x1800026cd`
- name: `BuildYUV12ToRGB555`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002028`

## callees

- `0x18000263c`
- `0x18000276c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000265e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000265e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000266c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000266c`

## pseudocode

```c
_WORD *__fastcall BuildYUV12ToRGB555(__int64 a1)
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
          *v5++ = TosYUVToRGB555((i >> 7) & 0xF8, (i >> 2) & 0xF8, 8 * (i & 0x1Fu));
      }
    }
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x18000263c  mov     [rsp+arg_0], rbx
0x180002641  mov     [rsp+arg_8], rsi
0x180002646  push    rdi
0x180002647  sub     rsp, 20h
0x18000264b  mov     rax, [rcx+8]
0x18000264f  test    rax, rax
0x180002652  jnz     short loc_1800026BD
0x180002654  mov     edx, 10000h; dwBytes
0x180002659  lea     ecx, [rax+40h]; uFlags
0x18000265c  xor     ebx, ebx
0x18000265e  call    cs:__imp_GlobalAlloc
0x180002664  test    rax, rax
0x180002667  jz      short loc_1800026BA
0x180002669  mov     rcx, rax; hMem
0x18000266c  call    cs:__imp_GlobalLock
0x180002672  mov     rbx, rax
0x180002675  test    rax, rax
0x180002678  jz      short loc_1800026BA
0x18000267a  mov     rsi, rax
0x18000267d  xor     edi, edi
0x18000267f  movzx   ecx, di
0x180002682  mov     r8d, ecx
0x180002685  mov     edx, ecx
0x180002687  shr     edx, 2
0x18000268a  and     r8d, 1Fh
0x18000268e  shr     ecx, 7
0x180002691  and     edx, 0F8h
0x180002697  shl     r8d, 3
0x18000269b  and     ecx, 0F8h
0x1800026a1  call    TosYUVToRGB555
0x1800026a6  mov     [rsi], ax
0x1800026a9  inc     di
0x1800026ac  mov     eax, 8000h
0x1800026b1  lea     rsi, [rsi+2]
0x1800026b5  cmp     di, ax
0x1800026b8  jb      short loc_18000267F
0x1800026ba  mov     rax, rbx
0x1800026bd  mov     rbx, [rsp+28h+arg_0]
0x1800026c2  mov     rsi, [rsp+28h+arg_8]
0x1800026c7  add     rsp, 20h
0x1800026cb  pop     rdi
0x1800026cc  retn
```
