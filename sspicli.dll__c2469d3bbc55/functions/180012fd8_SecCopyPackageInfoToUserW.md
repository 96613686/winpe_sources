# SecCopyPackageInfoToUserW

- ea: `0x180012fd8`
- end: `0x18001309a`
- name: `SecCopyPackageInfoToUserW`
- size: `194`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800049c0`
- `0x180009c40`
- `0x1800197b0`
- `0x180019de0`

## callees

- `0x180012fd8`
- `0x180022047`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013006`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013006`

## pseudocode

```c
__int64 __fastcall SecCopyPackageInfoToUserW(__int64 a1, _QWORD *a2)
{
  _WORD *v4; // rax
  _WORD *v5; // rsi
  char *v6; // rbx
  unsigned __int64 v7; // rcx
  char *v8; // rbx
  __int64 result; // rax

  if ( !a1 )
    return 2148074245LL;
  v4 = LocalAlloc(0x40u, *(unsigned __int16 *)(a1 + 112) + 36LL + *(unsigned __int16 *)(a1 + 96));
  v5 = v4;
  if ( v4 )
  {
    v6 = (char *)(v4 + 16);
    *(_DWORD *)v4 = *(_DWORD *)(a1 + 80);
    v4[2] = *(_WORD *)(a1 + 84);
    v4[3] = *(_WORD *)(a1 + 86);
    *((_DWORD *)v4 + 2) = *(_DWORD *)(a1 + 92);
    *((_QWORD *)v4 + 2) = v4 + 16;
    memcpy_0(v4 + 16, *(const void **)(a1 + 104), *(unsigned __int16 *)(a1 + 96));
    v7 = (unsigned __int64)*(unsigned __int16 *)(a1 + 96) >> 1;
    *(_WORD *)&v6[2 * v7] = 0;
    v8 = &v6[2 * v7 + 2];
    *((_QWORD *)v5 + 3) = v8;
    memcpy_0(v8, *(const void **)(a1 + 120), *(unsigned __int16 *)(a1 + 112));
    result = 0;
    *(_WORD *)&v8[2 * ((unsigned __int64)*(unsigned __int16 *)(a1 + 112) >> 1)] = 0;
  }
  else
  {
    result = 2148074240LL;
  }
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x180012fd8  push    rbx
0x180012fda  push    rsi
0x180012fdb  push    rdi
0x180012fdc  push    r14
0x180012fde  sub     rsp, 28h
0x180012fe2  mov     r14, rdx
0x180012fe5  mov     rdi, rcx
0x180012fe8  test    rcx, rcx
0x180012feb  jz      loc_18001308B
0x180012ff1  movzx   r8d, word ptr [rcx+70h]
0x180012ff6  movzx   edx, word ptr [rcx+60h]
0x180012ffa  add     r8, 24h ; '$'
0x180012ffe  add     rdx, r8; uBytes
0x180013001  mov     ecx, 40h ; '@'; uFlags
0x180013006  call    cs:__imp_LocalAlloc
0x18001300c  mov     rsi, rax
0x18001300f  test    rax, rax
0x180013012  jz      short loc_180013081
0x180013014  mov     ecx, [rdi+50h]
0x180013017  lea     rbx, [rax+20h]
0x18001301b  mov     [rax], ecx
0x18001301d  movzx   ecx, word ptr [rdi+54h]
0x180013021  mov     [rax+4], cx
0x180013025  movzx   ecx, word ptr [rdi+56h]
0x180013029  mov     [rax+6], cx
0x18001302d  mov     ecx, [rdi+5Ch]
0x180013030  mov     [rax+8], ecx
0x180013033  mov     rcx, rbx; void *
0x180013036  mov     [rax+10h], rbx
0x18001303a  movzx   r8d, word ptr [rdi+60h]; Size
0x18001303f  mov     rdx, [rdi+68h]; Src
0x180013043  call    memcpy_0
0x180013048  movzx   ecx, word ptr [rdi+60h]
0x18001304c  xor     eax, eax
0x18001304e  shr     rcx, 1
0x180013051  mov     [rbx+rcx*2], ax
0x180013055  lea     rbx, [rbx+rcx*2]
0x180013059  add     rbx, 2
0x18001305d  mov     [rsi+18h], rbx
0x180013061  mov     rcx, rbx; void *
0x180013064  movzx   r8d, word ptr [rdi+70h]; Size
0x180013069  mov     rdx, [rdi+78h]; Src
0x18001306d  call    memcpy_0
0x180013072  movzx   ecx, word ptr [rdi+70h]
0x180013076  shr     rcx, 1
0x180013079  xor     eax, eax
0x18001307b  mov     [rbx+rcx*2], ax
0x18001307f  jmp     short loc_180013086
0x180013081  mov     eax, 80090300h
0x180013086  mov     [r14], rsi
0x180013089  jmp     short loc_180013090
0x18001308b  mov     eax, 80090305h
0x180013090  add     rsp, 28h
0x180013094  pop     r14
0x180013096  pop     rdi
0x180013097  pop     rsi
0x180013098  pop     rbx
0x180013099  retn
```
