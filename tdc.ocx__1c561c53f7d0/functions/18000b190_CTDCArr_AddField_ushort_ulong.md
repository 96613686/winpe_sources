# CTDCArr::AddField(ushort *,ulong)

- ea: `0x18000b190`
- end: `0x18000b34f`
- name: `?AddField@CTDCArr@@UEAAJPEAGK@Z`
- size: `447`
- prototype: `int(CTDCArr *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800011b8`
- `0x18000b190`
- `0x18000c864`
- `0x18000c914`
- `0x18000d2b0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000b2c5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000b2c5`
- `OLEAUT32!__imp_VariantClear` at `0x18000b29f`
- `OLEAUT32!__imp_VariantClear` at `0x18000b334`
- `OLEAUT32!__imp_VariantClear` at `0x18000b29f`
- `OLEAUT32!__imp_VariantClear` at `0x18000b334`
- `OLEAUT32!__imp_VariantCopy` at `0x18000b327`
- `OLEAUT32!__imp_VariantCopy` at `0x18000b327`

## pseudocode

```c
__int64 __fastcall CTDCArr::AddField(CTDCArr *this, unsigned __int16 *a2, UINT a3)
{
  HRESULT inserted; // edi
  _QWORD *v7; // rsi
  _QWORD *v8; // rax
  bool v9; // zf
  int *v10; // rsi
  _DWORD *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r14
  CTDCArr *v14; // rcx
  unsigned __int16 *v15; // r8
  BSTR v16; // rax
  struct CTDCColInfo *v17; // r9
  unsigned int v19; // [rsp+20h] [rbp-68h]
  VARIANTARG pvargSrc; // [rsp+30h] [rbp-58h] BYREF

  inserted = 0;
  if ( *((_BYTE *)this + 85) )
    return (unsigned int)inserted;
  if ( *((_DWORD *)this + 22) > *((_DWORD *)this + 24) && *((_DWORD *)this + 23) == 1 )
  {
    v7 = (_QWORD *)((char *)this + 120);
    inserted = TSTDArray<TSTDArray<CTDCCell> *>::InsertElems((char *)this + 120, *((int *)this + 22), 1);
    if ( inserted < 0 )
      return (unsigned int)inserted;
    v8 = operator new(0x18u);
    if ( !v8 )
      return (unsigned int)-2147024882;
    *v8 = 0;
    v8[1] = 0;
    v8[2] = 0;
    *(_QWORD *)(*v7 + 8LL * *((int *)this + 22)) = v8;
    v9 = *((_DWORD *)this + 22) == 0;
    if ( *((int *)this + 22) <= 0 )
      goto LABEL_9;
    inserted = TSTDArray<CTDCCell>::InsertElems(*(_QWORD *)(*v7 + 8LL * *((int *)this + 22)), 0, *((int *)this + 26));
    if ( inserted < 0 )
      return (unsigned int)inserted;
  }
  v9 = *((_DWORD *)this + 22) == 0;
LABEL_9:
  v10 = (int *)((char *)this + 92);
  if ( !v9 )
  {
    v11 = (_DWORD *)((char *)this + 104);
    goto LABEL_14;
  }
  inserted = TSTDArray<CTDCCell>::InsertElems(**((_QWORD **)this + 15), *v10 - 1, 1);
  if ( inserted >= 0 )
  {
    v11 = (_DWORD *)((char *)this + 104);
    ++*((_DWORD *)this + 26);
LABEL_14:
    v12 = *v10;
    if ( (int)v12 > *v11 )
    {
LABEL_23:
      ++*v10;
      return (unsigned int)inserted;
    }
    v13 = **(_QWORD **)(*((_QWORD *)this + 15) + 8LL * *((int *)this + 22)) + 24 * v12;
    VariantClear((VARIANTARG *)(v13 - 24));
    *(_WORD *)(v13 - 24) = 8;
    if ( !a3 )
    {
      *(_QWORD *)(v13 - 16) = 0;
      v15 = 0;
LABEL_18:
      if ( *((int *)this + 22) > 0 )
      {
        v17 = (struct CTDCColInfo *)(*((_QWORD *)this + 21) - 8LL + 8LL * *v10);
        if ( *(_WORD *)v17 != 8 )
        {
          v19 = *((_DWORD *)this + 9);
          memset(&pvargSrc, 0, sizeof(pvargSrc));
          if ( CTDCArr::VariantFromBSTR(v14, &pvargSrc, v15, v17, v19) < 0 )
          {
            inserted = 0;
          }
          else
          {
            inserted = VariantCopy((VARIANTARG *)(v13 - 24), &pvargSrc);
            VariantClear(&pvargSrc);
          }
        }
      }
      goto LABEL_23;
    }
    v16 = SysAllocStringLen(a2, a3);
    *(_QWORD *)(v13 - 16) = v16;
    v15 = v16;
    if ( v16 )
      goto LABEL_18;
    return (unsigned int)-2147024882;
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18000b190  push    rbx
0x18000b192  push    rbp
0x18000b193  push    rsi
0x18000b194  push    rdi
0x18000b195  push    r14
0x18000b197  push    r15
0x18000b199  sub     rsp, 58h
0x18000b19d  xor     edi, edi
0x18000b19f  mov     ebp, r8d
0x18000b1a2  mov     r15, rdx
0x18000b1a5  mov     rbx, rcx
0x18000b1a8  cmp     [rcx+55h], dil
0x18000b1ac  jnz     loc_18000B340
0x18000b1b2  movsxd  rax, dword ptr [rcx+58h]
0x18000b1b6  cmp     eax, [rcx+60h]
0x18000b1b9  jle     short loc_18000B235
0x18000b1bb  cmp     dword ptr [rcx+5Ch], 1
0x18000b1bf  jnz     short loc_18000B235
0x18000b1c1  lea     rsi, [rcx+78h]
0x18000b1c5  mov     rdx, rax
0x18000b1c8  mov     rcx, rsi
0x18000b1cb  lea     r8d, [rdi+1]
0x18000b1cf  call    ?InsertElems@?$TSTDArray@PEAV?$TSTDArray@VCTDCCell@@@@@@QEAAJ_K0@Z; TSTDArray<TSTDArray<CTDCCell> *>::InsertElems(unsigned __int64,unsigned __int64)
0x18000b1d4  mov     edi, eax
0x18000b1d6  test    eax, eax
0x18000b1d8  js      loc_18000B340
0x18000b1de  mov     ecx, 18h; Size
0x18000b1e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b1e8  test    rax, rax
0x18000b1eb  jz      short loc_18000B26A
0x18000b1ed  mov     qword ptr [rax], 0
0x18000b1f4  mov     qword ptr [rax+8], 0
0x18000b1fc  mov     qword ptr [rax+10h], 0
0x18000b204  movsxd  rdx, dword ptr [rbx+58h]
0x18000b208  mov     rcx, [rsi]
0x18000b20b  mov     [rcx+rdx*8], rax
0x18000b20f  cmp     dword ptr [rbx+58h], 0
0x18000b213  jle     short loc_18000B239
0x18000b215  movsxd  rax, dword ptr [rbx+58h]
0x18000b219  xor     edx, edx
0x18000b21b  mov     rcx, [rsi]
0x18000b21e  movsxd  r8, dword ptr [rbx+68h]
0x18000b222  mov     rcx, [rcx+rax*8]
0x18000b226  call    ?InsertElems@?$TSTDArray@VCTDCCell@@@@QEAAJ_K0@Z; TSTDArray<CTDCCell>::InsertElems(unsigned __int64,unsigned __int64)
0x18000b22b  mov     edi, eax
0x18000b22d  test    eax, eax
0x18000b22f  js      loc_18000B340
0x18000b235  cmp     dword ptr [rbx+58h], 0
0x18000b239  lea     rsi, [rbx+5Ch]
0x18000b23d  jnz     short loc_18000B274
0x18000b23f  mov     rcx, [rbx+78h]
0x18000b243  mov     r8d, 1
0x18000b249  mov     eax, [rsi]
0x18000b24b  dec     eax
0x18000b24d  movsxd  rdx, eax
0x18000b250  mov     rcx, [rcx]
0x18000b253  call    ?InsertElems@?$TSTDArray@VCTDCCell@@@@QEAAJ_K0@Z; TSTDArray<CTDCCell>::InsertElems(unsigned __int64,unsigned __int64)
0x18000b258  mov     edi, eax
0x18000b25a  test    eax, eax
0x18000b25c  js      loc_18000B340
0x18000b262  lea     rax, [rbx+68h]
0x18000b266  inc     dword ptr [rax]
0x18000b268  jmp     short loc_18000B278
0x18000b26a  mov     edi, 8007000Eh
0x18000b26f  jmp     loc_18000B340
0x18000b274  lea     rax, [rbx+68h]
0x18000b278  movsxd  r8, dword ptr [rsi]
0x18000b27b  cmp     r8d, [rax]
0x18000b27e  jg      loc_18000B33E
0x18000b284  movsxd  rcx, dword ptr [rbx+58h]
0x18000b288  mov     rax, [rbx+78h]
0x18000b28c  mov     rdx, [rax+rcx*8]
0x18000b290  lea     rcx, [r8+r8*2]
0x18000b294  mov     rax, [rdx]
0x18000b297  lea     r14, [rax+rcx*8]
0x18000b29b  lea     rcx, [r14-18h]; pvarg
0x18000b29f  call    cs:__imp_VariantClear
0x18000b2a5  mov     edx, 8
0x18000b2aa  mov     [r14-18h], dx
0x18000b2af  test    ebp, ebp
0x18000b2b1  jnz     short loc_18000B2C0
0x18000b2b3  mov     qword ptr [r14-10h], 0
0x18000b2bb  xor     r8d, r8d
0x18000b2be  jmp     short loc_18000B2DC
0x18000b2c0  mov     edx, ebp; ui
0x18000b2c2  mov     rcx, r15; strIn
0x18000b2c5  call    cs:__imp_SysAllocStringLen
0x18000b2cb  mov     [r14-10h], rax
0x18000b2cf  mov     r8, rax; unsigned __int16 *
0x18000b2d2  test    rax, rax
0x18000b2d5  jz      short loc_18000B26A
0x18000b2d7  mov     edx, 8
0x18000b2dc  cmp     dword ptr [rbx+58h], 0
0x18000b2e0  jle     short loc_18000B33E
0x18000b2e2  mov     rax, [rbx+0A8h]
0x18000b2e9  movsxd  r9, dword ptr [rsi]
0x18000b2ec  sub     rax, 8
0x18000b2f0  lea     r9, [rax+r9*8]; struct CTDCColInfo *
0x18000b2f4  cmp     [r9], dx
0x18000b2f8  jz      short loc_18000B33E
0x18000b2fa  xor     eax, eax
0x18000b2fc  lea     rdx, [rsp+88h+pvargSrc]; struct tagVARIANT *
0x18000b301  mov     qword ptr [rsp+88h+pvargSrc+10h], rax
0x18000b306  xorps   xmm0, xmm0
0x18000b309  mov     eax, [rbx+24h]
0x18000b30c  mov     [rsp+88h+var_68], eax; unsigned int
0x18000b310  movups  xmmword ptr [rsp+88h+pvargSrc], xmm0
0x18000b315  call    ?VariantFromBSTR@CTDCArr@@AEAAJPEAUtagVARIANT@@PEAGPEAVCTDCColInfo@@K@Z; CTDCArr::VariantFromBSTR(tagVARIANT *,ushort *,CTDCColInfo *,ulong)
0x18000b31a  test    eax, eax
0x18000b31c  js      short loc_18000B33C
0x18000b31e  lea     rdx, [rsp+88h+pvargSrc]; pvargSrc
0x18000b323  lea     rcx, [r14-18h]; pvargDest
0x18000b327  call    cs:__imp_VariantCopy
0x18000b32d  lea     rcx, [rsp+88h+pvargSrc]; pvarg
0x18000b332  mov     edi, eax
0x18000b334  call    cs:__imp_VariantClear
0x18000b33a  jmp     short loc_18000B33E
0x18000b33c  xor     edi, edi
0x18000b33e  inc     dword ptr [rsi]
0x18000b340  mov     eax, edi
0x18000b342  add     rsp, 58h
0x18000b346  pop     r15
0x18000b348  pop     r14
0x18000b34a  pop     rdi
0x18000b34b  pop     rsi
0x18000b34c  pop     rbp
0x18000b34d  pop     rbx
0x18000b34e  retn
```
