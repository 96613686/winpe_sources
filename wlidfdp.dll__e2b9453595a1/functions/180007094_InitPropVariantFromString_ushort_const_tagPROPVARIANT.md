# InitPropVariantFromString(ushort const *,tagPROPVARIANT *)

- ea: `0x180007094`
- end: `0x18000710c`
- name: `?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `120`
- prototype: `__int64 __fastcall(const unsigned __int16 *Source, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005d3c`

## callees

- `0x180007094`
- `0x180009b1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800070c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800070c9`

## pseudocode

```c
__int64 __fastcall InitPropVariantFromString(const unsigned __int16 *Source, struct tagPROPVARIANT *a2)
{
  unsigned int v2; // ebx
  __int64 v5; // rax
  __int64 v6; // rbp
  void *v7; // rax

  v2 = 0;
  if ( !Source )
  {
    v2 = -2147024809;
LABEL_8:
    *(_OWORD *)&a2->vt = 0;
    a2->bstrblobVal.pData = 0;
    return v2;
  }
  v5 = -1;
  do
    ++v5;
  while ( Source[v5] );
  v6 = 2 * v5 + 2;
  v7 = CoTaskMemAlloc(v6);
  a2->hVal.QuadPart = (LONGLONG)v7;
  if ( !v7 )
  {
    v2 = -2147024882;
    goto LABEL_8;
  }
  memcpy_s(v7, v6, Source, v6);
  a2->vt = 31;
  return v2;
}

```

## disassembly

```asm
0x180007094  push    rbx
0x180007096  push    rbp
0x180007097  push    rsi
0x180007098  push    rdi
0x180007099  sub     rsp, 28h
0x18000709d  xor     ebx, ebx
0x18000709f  mov     rdi, rdx
0x1800070a2  mov     rsi, rcx
0x1800070a5  test    rcx, rcx
0x1800070a8  jnz     short loc_1800070B1
0x1800070aa  mov     ebx, 80070057h
0x1800070af  jmp     short loc_1800070F5
0x1800070b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800070b5  inc     rax
0x1800070b8  cmp     [rcx+rax*2], bx
0x1800070bc  jnz     short loc_1800070B5
0x1800070be  lea     rbp, ds:2[rax*2]
0x1800070c6  mov     rcx, rbp; cb
0x1800070c9  call    cs:__imp_CoTaskMemAlloc
0x1800070cf  mov     [rdi+8], rax
0x1800070d3  test    rax, rax
0x1800070d6  jz      short loc_1800070F0
0x1800070d8  mov     r9, rbp; SourceSize
0x1800070db  mov     r8, rsi; Source
0x1800070de  mov     rdx, rbp; DestinationSize
0x1800070e1  mov     rcx, rax; Destination
0x1800070e4  call    memcpy_s
0x1800070e9  mov     word ptr [rdi], 1Fh
0x1800070ee  jmp     short loc_180007101
0x1800070f0  mov     ebx, 8007000Eh
0x1800070f5  xorps   xmm0, xmm0
0x1800070f8  xor     eax, eax
0x1800070fa  movups  xmmword ptr [rdi], xmm0
0x1800070fd  mov     [rdi+10h], rax
0x180007101  mov     eax, ebx
0x180007103  add     rsp, 28h
0x180007107  pop     rdi
0x180007108  pop     rsi
0x180007109  pop     rbp
0x18000710a  pop     rbx
0x18000710b  retn
```
