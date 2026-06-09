# CTDCArr::EOLN(void)

- ea: `0x18000baa0`
- end: `0x18000bd85`
- name: `?EOLN@CTDCArr@@UEAAJXZ`
- size: `741`
- prototype: `__int64 __fastcall(CTDCArr *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800011b8`
- `0x18000baa0`
- `0x18000bd8c`
- `0x18000c864`
- `0x18000c914`
- `0x18000ca08`
- `0x18000caac`
- `0x18000cf50`
- `0x18000d2b0`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000bc61`
- `OLEAUT32!__imp_VariantClear` at `0x18000bc61`
- `OLEAUT32!__imp_VariantCopy` at `0x18000bc54`
- `OLEAUT32!__imp_VariantCopy` at `0x18000bc54`

## pseudocode

```c
__int64 __fastcall CTDCArr::EOLN(CTDCArr *this)
{
  HRESULT inserted; // ebx
  __int64 **v2; // rsi
  __int64 v4; // rbp
  __int64 **v5; // r14
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // ebp
  __int64 v12; // r14
  struct CTDCColInfo *v13; // r9
  bool v14; // zf
  int v16; // edx
  struct CTDCFilterNode *v17; // r8
  int v18; // edx
  int v19; // ebp
  int v20; // r14d
  int v21; // ebx
  int v22; // eax
  int v23; // ecx
  __int64 v24; // rcx
  unsigned int v26; // [rsp+20h] [rbp-68h]
  VARIANTARG pvargSrc; // [rsp+30h] [rbp-58h] BYREF

  inserted = 0;
  v2 = (__int64 **)((char *)this - 8);
  if ( *((_BYTE *)this + 85) )
  {
    *((_BYTE *)this + 85) = 0;
    return (unsigned int)inserted;
  }
  if ( *((_DWORD *)this + 22) )
    goto LABEL_16;
  if ( !*((_BYTE *)this + 84) )
  {
    v4 = *((int *)v2 + 28);
    v5 = v2 + 16;
    inserted = TSTDArray<TSTDArray<CTDCCell> *>::InsertElems(v2 + 16, 0, 1);
    if ( inserted < 0 )
      return (unsigned int)inserted;
    v6 = operator new(0x18u);
    v7 = v6;
    if ( v6 )
    {
      *v6 = 0;
      v6[1] = 0;
      v6[2] = 0;
    }
    else
    {
      v7 = 0;
    }
    **v5 = (__int64)v7;
    v8 = **v5;
    if ( !v8 )
      return (unsigned int)-2147024882;
    inserted = TSTDArray<CTDCCell>::InsertElems(v8, 0, v4);
    if ( inserted < 0 )
      return (unsigned int)inserted;
    ++*((_DWORD *)this + 22);
    CTDCArr::RenumberColumnHeadings((CTDCArr *)v2);
  }
  ++*((_DWORD *)this + 24);
  ++*((_DWORD *)this + 25);
  CTDCArr::ParseColumnHeadings((CTDCArr *)v2);
  *((_DWORD *)this + 7) = 2;
  inserted = TSTDArray<TSTDArray<CTDCCell> *>::InsertElems((char *)this + 144, 0, 1);
  if ( inserted >= 0 )
  {
    **((_QWORD **)this + 18) = **((_QWORD **)this + 15);
    v9 = *((_QWORD *)this + 1);
    if ( !v9 || (inserted = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 136LL))(v9), inserted >= 0) )
    {
LABEL_16:
      v10 = *((_DWORD *)this + 22);
      if ( v10 > 0 )
      {
        v11 = *((_DWORD *)this + 23);
        if ( v11 < *((_DWORD *)this + 26) )
        {
          while ( 1 )
          {
            v12 = **(_QWORD **)(*((_QWORD *)this + 15) + 8LL * *((int *)this + 22)) + 24LL * v11;
            *(_WORD *)(v12 - 24) = 8;
            *(_QWORD *)(v12 - 16) = 0;
            v13 = (struct CTDCColInfo *)(*((_QWORD *)this + 21) - 8LL + 8LL * v11);
            if ( *(_WORD *)v13 != 8 )
            {
              v26 = *((_DWORD *)this + 9);
              memset(&pvargSrc, 0, sizeof(pvargSrc));
              if ( CTDCArr::VariantFromBSTR((CTDCArr *)(3LL * v11), &pvargSrc, 0, v13, v26) >= 0 )
              {
                inserted = VariantCopy((VARIANTARG *)(v12 - 24), &pvargSrc);
                VariantClear(&pvargSrc);
                if ( inserted < 0 )
                  return (unsigned int)inserted;
              }
            }
            if ( ++v11 >= *((_DWORD *)this + 26) )
            {
              v10 = *((_DWORD *)this + 22);
              break;
            }
          }
        }
        ++*((_DWORD *)this + 24);
      }
      *((_DWORD *)v2 + 25) = 1;
      v14 = *((_BYTE *)this + 40) == 0;
      *((_DWORD *)this + 22) = v10 + 1;
      if ( v14 )
      {
        v16 = *((_DWORD *)v2 + 26);
        if ( v16 <= 0 )
          return (unsigned int)inserted;
        v17 = (struct CTDCFilterNode *)*((_QWORD *)this + 8);
        if ( v17 )
        {
          if ( !CTDCArr::EvalDataRow((CTDCArr *)v2, v16, v17) )
            return (unsigned int)inserted;
        }
        v18 = *((_DWORD *)this + 25);
        v19 = v18 + 1;
        if ( *((_QWORD *)this + 6) )
        {
          if ( v18 )
          {
            if ( (int)CTDCArr::InsertionSortHelper((CTDCArr *)v2, v18) < 0 )
            {
              v19 = 1;
              v20 = *((_DWORD *)this + 25) + 1;
              if ( v20 > 1 )
              {
                do
                {
                  v21 = (v20 + v19) / 2;
                  v22 = CTDCArr::InsertionSortHelper((CTDCArr *)v2, v21);
                  v23 = v21;
                  if ( v22 > 0 )
                    v23 = v20;
                  v20 = v23;
                  if ( v22 > 0 )
                    v19 = v21 + 1;
                }
                while ( v19 < v23 );
              }
            }
          }
        }
        inserted = TSTDArray<TSTDArray<CTDCCell> *>::InsertElems((char *)this + 144, v19, 1);
        if ( inserted < 0 )
          return (unsigned int)inserted;
        *(_QWORD *)(*((_QWORD *)this + 18) + 8LL * v19) = *(_QWORD *)(*((_QWORD *)this + 15) + 8LL * *((int *)this + 24));
        ++*((_DWORD *)this + 25);
        v24 = *((_QWORD *)this + 1);
        if ( !v24 )
          return (unsigned int)inserted;
        return (unsigned int)(*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v24 + 88LL))(
                               v24,
                               (unsigned int)v19,
                               1);
      }
      else
      {
        return ((unsigned int (__fastcall *)(__int64 **))(*v2)[22])(v2);
      }
    }
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18000baa0  push    rbx
0x18000baa2  push    rbp
0x18000baa3  push    rsi
0x18000baa4  push    rdi
0x18000baa5  push    r12
0x18000baa7  push    r13
0x18000baa9  push    r14
0x18000baab  sub     rsp, 50h
0x18000baaf  xor     ebx, ebx
0x18000bab1  lea     rsi, [rcx-8]
0x18000bab5  mov     rdi, rcx
0x18000bab8  cmp     [rsi+5Dh], bl
0x18000babb  jz      short loc_18000BAC5
0x18000babd  mov     [rcx+55h], bl
0x18000bac0  jmp     loc_18000BD74
0x18000bac5  mov     r12d, 1
0x18000bacb  cmp     [rcx+58h], ebx
0x18000bace  jnz     loc_18000BBCB
0x18000bad4  cmp     [rcx+54h], bl
0x18000bad7  jnz     loc_18000BB67
0x18000badd  movsxd  rbp, dword ptr [rsi+70h]
0x18000bae1  lea     r14, [rsi+80h]
0x18000bae8  mov     rcx, r14
0x18000baeb  mov     r8d, r12d
0x18000baee  xor     edx, edx
0x18000baf0  call    ?InsertElems@?$TSTDArray@PEAV?$TSTDArray@VCTDCCell@@@@@@QEAAJ_K0@Z; TSTDArray<TSTDArray<CTDCCell> *>::InsertElems(unsigned __int64,unsigned __int64)
0x18000baf5  mov     ebx, eax
0x18000baf7  test    eax, eax
0x18000baf9  js      loc_18000BD74
0x18000baff  lea     ecx, [r12+17h]; Size
0x18000bb04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bb09  mov     rcx, rax
0x18000bb0c  test    rax, rax
0x18000bb0f  jz      short loc_18000BB2A
0x18000bb11  mov     qword ptr [rax], 0
0x18000bb18  mov     qword ptr [rax+8], 0
0x18000bb20  mov     qword ptr [rax+10h], 0
0x18000bb28  jmp     short loc_18000BB2C
0x18000bb2a  xor     ecx, ecx
0x18000bb2c  mov     rax, [r14]
0x18000bb2f  mov     [rax], rcx
0x18000bb32  mov     rax, [r14]
0x18000bb35  mov     rcx, [rax]
0x18000bb38  test    rcx, rcx
0x18000bb3b  jnz     short loc_18000BB47
0x18000bb3d  mov     ebx, 8007000Eh
0x18000bb42  jmp     loc_18000BD74
0x18000bb47  mov     r8, rbp
0x18000bb4a  xor     edx, edx
0x18000bb4c  call    ?InsertElems@?$TSTDArray@VCTDCCell@@@@QEAAJ_K0@Z; TSTDArray<CTDCCell>::InsertElems(unsigned __int64,unsigned __int64)
0x18000bb51  mov     ebx, eax
0x18000bb53  test    eax, eax
0x18000bb55  js      loc_18000BD74
0x18000bb5b  add     [rdi+58h], r12d
0x18000bb5f  mov     rcx, rsi; this
0x18000bb62  call    ?RenumberColumnHeadings@CTDCArr@@AEAAXXZ; CTDCArr::RenumberColumnHeadings(void)
0x18000bb67  add     [rdi+60h], r12d
0x18000bb6b  mov     rcx, rsi; this
0x18000bb6e  add     [rdi+64h], r12d
0x18000bb72  call    ?ParseColumnHeadings@CTDCArr@@AEAAJXZ; CTDCArr::ParseColumnHeadings(void)
0x18000bb77  lea     r14, [rdi+90h]
0x18000bb7e  mov     dword ptr [rdi+1Ch], 2
0x18000bb85  mov     rcx, r14
0x18000bb88  mov     r8, r12
0x18000bb8b  xor     edx, edx
0x18000bb8d  call    ?InsertElems@?$TSTDArray@PEAV?$TSTDArray@VCTDCCell@@@@@@QEAAJ_K0@Z; TSTDArray<TSTDArray<CTDCCell> *>::InsertElems(unsigned __int64,unsigned __int64)
0x18000bb92  mov     ebx, eax
0x18000bb94  test    eax, eax
0x18000bb96  js      loc_18000BD74
0x18000bb9c  mov     rcx, [rdi+78h]
0x18000bba0  mov     rdx, [r14]
0x18000bba3  mov     rcx, [rcx]
0x18000bba6  mov     [rdx], rcx
0x18000bba9  mov     rcx, [rdi+8]
0x18000bbad  test    rcx, rcx
0x18000bbb0  jz      short loc_18000BBCB
0x18000bbb2  mov     rax, [rcx]
0x18000bbb5  mov     rax, [rax+88h]
0x18000bbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbc1  mov     ebx, eax
0x18000bbc3  test    eax, eax
0x18000bbc5  js      loc_18000BD74
0x18000bbcb  mov     eax, [rdi+58h]
0x18000bbce  test    eax, eax
0x18000bbd0  jle     loc_18000BC82
0x18000bbd6  mov     ebp, [rdi+5Ch]
0x18000bbd9  cmp     ebp, [rdi+68h]
0x18000bbdc  jge     loc_18000BC7E
0x18000bbe2  mov     r13d, 8
0x18000bbe8  movsxd  rcx, dword ptr [rdi+58h]
0x18000bbec  mov     rax, [rdi+78h]
0x18000bbf0  movsxd  rdx, ebp
0x18000bbf3  mov     rax, [rax+rcx*8]
0x18000bbf7  lea     rcx, [rdx+rdx*2]; this
0x18000bbfb  mov     rax, [rax]
0x18000bbfe  lea     r14, [rax+rcx*8]
0x18000bc02  mov     [r14-18h], r13w
0x18000bc07  mov     qword ptr [r14-10h], 0
0x18000bc0f  mov     r9, [rdi+0A8h]
0x18000bc16  add     r9, 0FFFFFFFFFFFFFFF8h
0x18000bc1a  lea     r9, [r9+rdx*8]; struct CTDCColInfo *
0x18000bc1e  cmp     [r9], r13w
0x18000bc22  jz      short loc_18000BC6F
0x18000bc24  xor     eax, eax
0x18000bc26  lea     rdx, [rsp+88h+pvargSrc]; struct tagVARIANT *
0x18000bc2b  mov     qword ptr [rsp+88h+pvargSrc+10h], rax
0x18000bc30  xorps   xmm0, xmm0
0x18000bc33  mov     eax, [rdi+24h]
0x18000bc36  xor     r8d, r8d; unsigned __int16 *
0x18000bc39  mov     [rsp+88h+var_68], eax; unsigned int
0x18000bc3d  movups  xmmword ptr [rsp+88h+pvargSrc], xmm0
0x18000bc42  call    ?VariantFromBSTR@CTDCArr@@AEAAJPEAUtagVARIANT@@PEAGPEAVCTDCColInfo@@K@Z; CTDCArr::VariantFromBSTR(tagVARIANT *,ushort *,CTDCColInfo *,ulong)
0x18000bc47  test    eax, eax
0x18000bc49  js      short loc_18000BC6F
0x18000bc4b  lea     rdx, [rsp+88h+pvargSrc]; pvargSrc
0x18000bc50  lea     rcx, [r14-18h]; pvargDest
0x18000bc54  call    cs:__imp_VariantCopy
0x18000bc5a  lea     rcx, [rsp+88h+pvargSrc]; pvarg
0x18000bc5f  mov     ebx, eax
0x18000bc61  call    cs:__imp_VariantClear
0x18000bc67  test    ebx, ebx
0x18000bc69  js      loc_18000BD74
0x18000bc6f  add     ebp, r12d
0x18000bc72  cmp     ebp, [rdi+68h]
0x18000bc75  jl      loc_18000BBE8
0x18000bc7b  mov     eax, [rdi+58h]
0x18000bc7e  add     [rdi+60h], r12d
0x18000bc82  inc     eax
0x18000bc84  mov     [rsi+64h], r12d
0x18000bc88  cmp     byte ptr [rdi+28h], 0
0x18000bc8c  mov     [rdi+58h], eax
0x18000bc8f  jz      short loc_18000BCA8
0x18000bc91  mov     rax, [rsi]
0x18000bc94  mov     rcx, rsi
0x18000bc97  mov     rax, [rax+0B0h]
0x18000bc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bca3  jmp     loc_18000BD72
0x18000bca8  mov     edx, [rsi+68h]; int
0x18000bcab  test    edx, edx
0x18000bcad  jle     loc_18000BD74
0x18000bcb3  mov     r8, [rdi+40h]; struct CTDCFilterNode *
0x18000bcb7  test    r8, r8
0x18000bcba  jz      short loc_18000BCCC
0x18000bcbc  mov     rcx, rsi; this
0x18000bcbf  call    ?EvalDataRow@CTDCArr@@AEAAEJPEAVCTDCFilterNode@@@Z; CTDCArr::EvalDataRow(long,CTDCFilterNode *)
0x18000bcc4  test    al, al
0x18000bcc6  jz      loc_18000BD74
0x18000bccc  cmp     qword ptr [rdi+30h], 0
0x18000bcd1  mov     edx, [rdi+64h]; int
0x18000bcd4  lea     ebp, [rdx+1]
0x18000bcd7  jz      short loc_18000BD23
0x18000bcd9  test    edx, edx
0x18000bcdb  jz      short loc_18000BD23
0x18000bcdd  mov     rcx, rsi; this
0x18000bce0  call    ?InsertionSortHelper@CTDCArr@@AEAAHH@Z; CTDCArr::InsertionSortHelper(int)
0x18000bce5  test    eax, eax
0x18000bce7  jns     short loc_18000BD23
0x18000bce9  mov     r14d, [rdi+64h]
0x18000bced  mov     ebp, r12d
0x18000bcf0  add     r14d, r12d
0x18000bcf3  cmp     r14d, r12d
0x18000bcf6  jle     short loc_18000BD23
0x18000bcf8  lea     eax, [r14+rbp]
0x18000bcfc  mov     rcx, rsi; this
0x18000bcff  cdq
0x18000bd00  sub     eax, edx
0x18000bd02  sar     eax, 1
0x18000bd04  mov     edx, eax; int
0x18000bd06  mov     ebx, eax
0x18000bd08  call    ?InsertionSortHelper@CTDCArr@@AEAAHH@Z; CTDCArr::InsertionSortHelper(int)
0x18000bd0d  test    eax, eax
0x18000bd0f  mov     ecx, ebx
0x18000bd11  cmovg   ecx, r14d
0x18000bd15  mov     r14d, ecx
0x18000bd18  lea     ecx, [rbx+1]
0x18000bd1b  cmovg   ebp, ecx
0x18000bd1e  cmp     ebp, r14d
0x18000bd21  jl      short loc_18000BCF8
0x18000bd23  movsxd  rsi, ebp
0x18000bd26  lea     r14, [rdi+90h]
0x18000bd2d  mov     rdx, rsi
0x18000bd30  mov     rcx, r14
0x18000bd33  mov     r8, r12
0x18000bd36  call    ?InsertElems@?$TSTDArray@PEAV?$TSTDArray@VCTDCCell@@@@@@QEAAJ_K0@Z; TSTDArray<TSTDArray<CTDCCell> *>::InsertElems(unsigned __int64,unsigned __int64)
0x18000bd3b  mov     ebx, eax
0x18000bd3d  test    eax, eax
0x18000bd3f  js      short loc_18000BD74
0x18000bd41  mov     rax, [rdi+78h]
0x18000bd45  mov     rcx, [r14]
0x18000bd48  movsxd  r9, dword ptr [rdi+60h]
0x18000bd4c  mov     rax, [rax+r9*8]
0x18000bd50  mov     [rcx+rsi*8], rax
0x18000bd54  add     [rdi+64h], r12d
0x18000bd58  mov     rcx, [rdi+8]
0x18000bd5c  test    rcx, rcx
0x18000bd5f  jz      short loc_18000BD74
0x18000bd61  mov     rax, [rcx]
0x18000bd64  mov     r8d, r12d
0x18000bd67  mov     edx, ebp
0x18000bd69  mov     rax, [rax+58h]
0x18000bd6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd72  mov     ebx, eax
0x18000bd74  mov     eax, ebx
0x18000bd76  add     rsp, 50h
0x18000bd7a  pop     r14
0x18000bd7c  pop     r13
0x18000bd7e  pop     r12
0x18000bd80  pop     rdi
0x18000bd81  pop     rsi
0x18000bd82  pop     rbp
0x18000bd83  pop     rbx
0x18000bd84  retn
```
