# AttachAltExtraData(tagSPPHRASEALTREQUEST *,tagSPPHRASEALT *,ulong,int *,ulong,ulong,CStreamPair *)

- ea: `0x180082800`
- end: `0x1800828cc`
- name: `?AttachAltExtraData@@YAJPEAUtagSPPHRASEALTREQUEST@@PEAUtagSPPHRASEALT@@KPEAHKKPEAVCStreamPair@@@Z`
- size: `204`
- prototype: `int(struct tagSPPHRASEALTREQUEST *, struct tagSPPHRASEALT *, unsigned int, int *, unsigned int, unsigned int, struct CStreamPair *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009cd0`

## callees

- `0x180004312`
- `0x180082800`
- `0x180083838`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180082858`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180082858`

## pseudocode

```c
__int64 __fastcall AttachAltExtraData(
        struct tagSPPHRASEALTREQUEST *a1,
        struct tagSPPHRASEALT *a2,
        unsigned int a3,
        int *a4,
        unsigned int a5,
        unsigned int a6,
        struct CStreamPair *a7)
{
  unsigned int v11; // ebp
  unsigned int i; // edi
  void *v13; // rax
  _DWORD *pvAltExtra; // r9
  __int64 j; // rdx
  signed int v16; // ecx

  v11 = MarkWildCardsAndCancelRecos(a1, a4, a5, (unsigned __int64)a7);
  for ( i = 1; i < a3; ++i )
  {
    a2[i].cbAltExtra = 4 * a5;
    v13 = CoTaskMemAlloc(4 * a5);
    a2[i].pvAltExtra = v13;
    if ( !v13 )
      return (unsigned int)-2147024882;
    memcpy_0(v13, a4, a2[i].cbAltExtra);
    if ( a2[i].cElementsInParent != a2[i].cElementsInAlternate )
    {
      pvAltExtra = a2[i].pvAltExtra;
      for ( j = 0; (unsigned int)j < a5; j = (unsigned int)(j + 1) )
      {
        v16 = pvAltExtra[j];
        if ( v16 >= (signed int)(a1->cElements + a1->ulStartElement) )
          pvAltExtra[j] = a2[i].cElementsInAlternate + v16 - a2[i].cElementsInParent;
      }
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180082800  push    rbx
0x180082802  push    rbp
0x180082803  push    rsi
0x180082804  push    rdi
0x180082805  push    r12
0x180082807  push    r13
0x180082809  push    r14
0x18008280b  push    r15
0x18008280d  sub     rsp, 28h
0x180082811  mov     r14d, [rsp+68h+arg_20]
0x180082819  mov     r13, r9
0x18008281c  mov     r9, [rsp+68h+arg_30]; struct CStreamPair *
0x180082824  mov     rsi, rdx
0x180082827  mov     r12d, r8d
0x18008282a  mov     rdx, r13; int *
0x18008282d  mov     r8d, r14d; unsigned int
0x180082830  mov     r15, rcx
0x180082833  call    ?MarkWildCardsAndCancelRecos@@YAJPEAUtagSPPHRASEALTREQUEST@@PEAHKPEAVCStreamPair@@@Z; MarkWildCardsAndCancelRecos(tagSPPHRASEALTREQUEST *,int *,ulong,CStreamPair *)
0x180082838  mov     ebp, eax
0x18008283a  mov     edi, 1
0x18008283f  cmp     edi, r12d
0x180082842  jnb     short loc_1800828B9
0x180082844  lea     edx, ds:0[r14*4]
0x18008284c  mov     ecx, edi
0x18008284e  lea     rbx, [rcx+rcx*4]
0x180082852  mov     ecx, edx; cb
0x180082854  mov     [rsi+rbx*8+20h], edx
0x180082858  call    cs:__imp_CoTaskMemAlloc
0x18008285e  mov     [rsi+rbx*8+18h], rax
0x180082863  test    rax, rax
0x180082866  jz      short loc_1800828B4
0x180082868  mov     r8d, [rsi+rbx*8+20h]; Size
0x18008286d  mov     rdx, r13; Src
0x180082870  mov     rcx, rax; void *
0x180082873  call    memcpy_0
0x180082878  mov     eax, [rsi+rbx*8+10h]
0x18008287c  cmp     [rsi+rbx*8+0Ch], eax
0x180082880  jz      short loc_1800828B0
0x180082882  mov     r9, [rsi+rbx*8+18h]
0x180082887  xor     edx, edx
0x180082889  test    r14d, r14d
0x18008288c  jz      short loc_1800828B0
0x18008288e  mov     eax, [r15]
0x180082891  add     eax, [r15+4]
0x180082895  mov     ecx, [r9+rdx*4]
0x180082899  cmp     ecx, eax
0x18008289b  jl      short loc_1800828A9
0x18008289d  sub     ecx, [rsi+rbx*8+0Ch]
0x1800828a1  add     ecx, [rsi+rbx*8+10h]
0x1800828a5  mov     [r9+rdx*4], ecx
0x1800828a9  inc     edx
0x1800828ab  cmp     edx, r14d
0x1800828ae  jb      short loc_18008288E
0x1800828b0  inc     edi
0x1800828b2  jmp     short loc_18008283F
0x1800828b4  mov     ebp, 8007000Eh
0x1800828b9  mov     eax, ebp
0x1800828bb  add     rsp, 28h
0x1800828bf  pop     r15
0x1800828c1  pop     r14
0x1800828c3  pop     r13
0x1800828c5  pop     r12
0x1800828c7  pop     rdi
0x1800828c8  pop     rsi
0x1800828c9  pop     rbp
0x1800828ca  pop     rbx
0x1800828cb  retn
```
