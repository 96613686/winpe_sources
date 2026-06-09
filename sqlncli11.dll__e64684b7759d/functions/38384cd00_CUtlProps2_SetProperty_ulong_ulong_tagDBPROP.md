# CUtlProps2::SetProperty(ulong,ulong,tagDBPROP *)

- ea: `0x38384cd00`
- end: `0x38384ce13`
- name: `?SetProperty@CUtlProps2@@AEAAJKKPEAUtagDBPROP@@@Z`
- size: `275`
- prototype: `int(CUtlProps2 *__hidden this, unsigned int, unsigned int, struct tagDBPROP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x38384cb20`

## callees

- `0x38384cd00`
- `0x38391afe0`
- `0x383a99124`
- `0x383a991c8`
- `0x383a99644`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x3838878b9`
- `OLEAUT32!__imp_VariantClear` at `0x3838878e2`
- `OLEAUT32!__imp_VariantClear` at `0x3838878b9`
- `OLEAUT32!__imp_VariantClear` at `0x3838878e2`
- `OLEAUT32!__imp_VariantCopy` at `0x3838878cc`
- `OLEAUT32!__imp_VariantCopy` at `0x3838f4bb3`
- `OLEAUT32!__imp_VariantCopy` at `0x3838878cc`
- `OLEAUT32!__imp_VariantCopy` at `0x3838f4bb3`

## pseudocode

```c
__int64 __fastcall CUtlProps2::SetProperty(CUtlProps2 *this, unsigned int a2, unsigned int a3, struct tagDBPROP *a4)
{
  __int64 v4; // r11
  __int64 v7; // r10
  __int64 v8; // r9
  unsigned int v9; // edx
  __int64 v11; // r15
  unsigned int v12; // ebx
  _DWORD **v13; // rcx
  __int64 v14; // rdi
  HRESULT v15; // eax
  int v16; // ebx
  __int64 v18; // rax
  __int64 dwPropertyID; // r8
  unsigned int v20; // edx
  HRESULT v21; // eax
  int v22; // r11d
  CColumnIds *v23; // rcx
  int v24; // eax
  CColumnIds *v25; // rcx
  _QWORD *v26; // rax
  CColumnIds *v27; // rcx
  VARIANTARG pvargSrc; // [rsp+30h] [rbp-48h] BYREF
  int v29; // [rsp+88h] [rbp+10h] BYREF

  v4 = *((_QWORD *)this + 6);
  v7 = 32LL * a2;
  v8 = 3LL * a2;
  v9 = *(_DWORD *)(v4 + 24LL * a2);
  v11 = *(_QWORD *)(v7 + *((_QWORD *)this + 4) + 16) + 16LL * a3;
  v12 = 0;
  if ( v9 )
  {
    v13 = *(_DWORD ***)(v4 + 8 * v8 + 8);
    do
    {
      if ( **v13 == a4->dwPropertyID )
        break;
      ++v12;
      ++v13;
    }
    while ( v12 < v9 );
  }
  if ( v12 >= v9 )
  {
    v16 = -2147467259;
    a4->dwStatus = 1;
    return (unsigned int)v16;
  }
  v14 = *(_QWORD *)(v4 + 8 * v8 + 16) + 56LL * v12;
  if ( !a4->vValue.vt )
  {
    v18 = *(_QWORD *)this;
    dwPropertyID = a4->dwPropertyID;
    pvargSrc.vt = 0;
    (*(void (__fastcall **)(CUtlProps2 *, _QWORD, __int64, int *, VARIANTARG *))(v18 + 96))(
      this,
      a2,
      dwPropertyID,
      &v29,
      &pvargSrc);
    if ( v29
      || !(*(unsigned int (__fastcall **)(CUtlProps2 *, _QWORD, _QWORD, VARIANTARG *))(*(_QWORD *)this + 56LL))(
            this,
            a2,
            v12,
            &pvargSrc) )
    {
      if ( (*(_DWORD *)(v11 + 12) & 0x100) != 0 )
      {
        v23 = *(CColumnIds **)(v14 + 24);
        if ( v23 )
          CColumnIds::`scalar deleting destructor'(v23, v20);
        *(_QWORD *)(v14 + 24) = 0;
      }
      VariantClear((VARIANTARG *)(v14 + 32));
      *(_DWORD *)(v14 + 4) &= ~1u;
      v21 = VariantCopy((VARIANTARG *)(v14 + 32), &pvargSrc);
      *(_DWORD *)v14 = v29;
      v16 = v21;
      VariantClear(&pvargSrc);
      v22 = 0;
      if ( v16 < 0 )
        v22 = 7;
      *(_DWORD *)(v14 + 12) = v22;
      goto LABEL_13;
    }
LABEL_23:
    a4->dwStatus = 8;
    return (unsigned int)-2147467259;
  }
  if ( !a4->dwOptions
    && (*(unsigned int (__fastcall **)(CUtlProps2 *, _QWORD, _QWORD, VARIANT *))(*(_QWORD *)this + 56LL))(
         this,
         a2,
         v12,
         &a4->vValue) )
  {
    goto LABEL_23;
  }
  if ( (*(_DWORD *)(v11 + 12) & 0x100) == 0 )
  {
    *(_DWORD *)v14 = a4->dwOptions;
    v15 = (*(__int64 (__fastcall **)(CUtlProps2 *, _QWORD, _QWORD, __int64, VARIANT *))(*(_QWORD *)this + 72LL))(
            this,
            a2,
            v12,
            v14 + 32,
            &a4->vValue);
LABEL_11:
    v16 = v15;
    if ( v15 >= 0 )
    {
LABEL_12:
      *(_DWORD *)(v14 + 4) |= 1u;
      *(_DWORD *)(v14 + 12) = 0;
      goto LABEL_13;
    }
    *(_DWORD *)(v14 + 12) = 7;
    goto LABEL_13;
  }
  if ( a4 == (struct tagDBPROP *)-16LL )
    v24 = 1;
  else
    v24 = CompareDBIDs(&a4->colid, &DB_NULLID);
  if ( !v24 )
  {
    v25 = *(CColumnIds **)(v14 + 24);
    if ( v25 )
      CColumnIds::`scalar deleting destructor'(v25, v9);
    *(_QWORD *)(v14 + 24) = 0;
    *(_DWORD *)v14 = a4->dwOptions;
    v15 = VariantCopy((VARIANTARG *)(v14 + 32), &a4->vValue);
    goto LABEL_11;
  }
  if ( !*(_QWORD *)(v14 + 24) )
  {
    v26 = (_QWORD *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 24);
    v26[2] = 0;
    *v26 = 0;
    v26[1] = 0;
    *(_QWORD *)(v14 + 24) = v26;
  }
  v27 = *(CColumnIds **)(v14 + 24);
  *(_DWORD *)(v14 + 12) = 7;
  if ( v27 )
  {
    v16 = CColumnIds::AddColumnId(v27, a4);
    if ( v16 < 0 )
      return (unsigned int)v16;
    goto LABEL_12;
  }
  if ( (bidGblFlags & 2) != 0 )
    v16 = bidTraceHR(off_383B43500[0], 2613257, 2147942414LL);
  else
    v16 = -2147024882;
LABEL_13:
  if ( v16 >= 0 )
    a4->dwStatus = 0;
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x38384cd00  mov     [rsp+arg_0], rbx
0x38384cd05  mov     [rsp+arg_10], rbp
0x38384cd0a  mov     [rsp+arg_18], rsi
0x38384cd0f  push    rdi
0x38384cd10  push    r12
0x38384cd12  push    r13
0x38384cd14  push    r14
0x38384cd16  push    r15
0x38384cd18  sub     rsp, 50h
0x38384cd1c  mov     r11, [rcx+30h]
0x38384cd20  mov     rax, [rcx+20h]
0x38384cd24  mov     r12d, edx
0x38384cd27  mov     r10d, edx
0x38384cd2a  xor     r13d, r13d
0x38384cd2d  mov     rsi, r9
0x38384cd30  shl     r10, 5
0x38384cd34  lea     r9, [r12+r12*2]
0x38384cd38  mov     r15d, r8d
0x38384cd3b  mov     edx, [r11+r9*8]
0x38384cd3f  shl     r15, 4
0x38384cd43  mov     r14, rcx
0x38384cd46  add     r15, [r10+rax+10h]
0x38384cd4b  mov     ebx, r13d
0x38384cd4e  test    edx, edx
0x38384cd50  jz      short loc_38384CD6C
0x38384cd52  mov     r8d, [rsi]
0x38384cd55  mov     rcx, [r11+r9*8+8]
0x38384cd5a  mov     rax, [rcx]
0x38384cd5d  cmp     [rax], r8d
0x38384cd60  jz      short loc_38384CD6C
0x38384cd62  inc     ebx
0x38384cd64  add     rcx, 8
0x38384cd68  cmp     ebx, edx
0x38384cd6a  jb      short loc_38384CD5A
0x38384cd6c  cmp     ebx, edx
0x38384cd6e  jnb     loc_3838F4B20
0x38384cd74  mov     edi, ebx
0x38384cd76  lea     rbp, [rsi+30h]
0x38384cd7a  imul    rdi, 38h ; '8'
0x38384cd7e  add     rdi, [r11+r9*8+10h]
0x38384cd83  cmp     [rbp+0], r13w
0x38384cd88  jz      loc_383887872
0x38384cd8e  cmp     [rsi+4], r13d
0x38384cd92  jnz     short loc_38384CDAE
0x38384cd94  mov     rax, [r14]
0x38384cd97  mov     r9, rbp
0x38384cd9a  mov     r8d, ebx
0x38384cd9d  mov     edx, r12d
0x38384cda0  mov     rcx, r14
0x38384cda3  call    qword ptr [rax+38h]
0x38384cda6  test    eax, eax
0x38384cda8  jnz     loc_3838F4B4D
0x38384cdae  test    dword ptr [r15+0Ch], 100h
0x38384cdb6  jnz     loc_3838F4B75
0x38384cdbc  mov     eax, [rsi+4]
0x38384cdbf  lea     r9, [rdi+20h]
0x38384cdc3  mov     r8d, ebx
0x38384cdc6  mov     [rdi], eax
0x38384cdc8  mov     rax, [r14]
0x38384cdcb  mov     edx, r12d
0x38384cdce  mov     rcx, r14
0x38384cdd1  mov     [rsp+78h+var_58], rbp
0x38384cdd6  call    qword ptr [rax+48h]
0x38384cdd9  mov     ebx, eax
0x38384cddb  test    eax, eax
0x38384cddd  js      loc_3838F4C3E
0x38384cde3  or      dword ptr [rdi+4], 1
0x38384cde7  mov     [rdi+0Ch], r13d
0x38384cdeb  test    ebx, ebx
0x38384cded  js      short loc_38384CDF3
0x38384cdef  mov     [rsi+8], r13d
0x38384cdf3  lea     r11, [rsp+78h+var_28]
0x38384cdf8  mov     eax, ebx
0x38384cdfa  mov     rbx, [r11+30h]
0x38384cdfe  mov     rbp, [r11+40h]
0x38384ce02  mov     rsi, [r11+48h]
0x38384ce06  mov     rsp, r11
0x38384ce09  pop     r15
0x38384ce0b  pop     r14
0x38384ce0d  pop     r13
0x38384ce0f  pop     r12
0x38384ce11  pop     rdi
0x38384ce12  retn
0x383887872  mov     rax, [r14]
0x383887875  mov     r8d, [rsi]
0x383887878  lea     rcx, [rsp+78h+pvargSrc]
0x38388787d  mov     [rsp+78h+var_58], rcx
0x383887882  lea     r9, [rsp+78h+arg_8]
0x38388788a  mov     edx, r12d
0x38388788d  mov     rcx, r14
0x383887890  mov     word ptr [rsp+78h+pvargSrc], r13w
0x383887896  call    qword ptr [rax+60h]
0x383887899  cmp     [rsp+78h+arg_8], r13d
0x3838878a1  jz      loc_3838F4B31
0x3838878a7  test    dword ptr [r15+0Ch], 100h
0x3838878af  jnz     loc_3838F4B5E
0x3838878b5  lea     rcx, [rdi+20h]; pvarg
0x3838878b9  call    cs:__imp_VariantClear
0x3838878bf  and     dword ptr [rdi+4], 0FFFFFFFEh
0x3838878c3  lea     rdx, [rsp+78h+pvargSrc]; pvargSrc
0x3838878c8  lea     rcx, [rdi+20h]; pvargDest
0x3838878cc  call    cs:__imp_VariantCopy
0x3838878d2  mov     ecx, [rsp+78h+arg_8]
0x3838878d9  mov     [rdi], ecx
0x3838878db  lea     rcx, [rsp+78h+pvargSrc]; pvarg
0x3838878e0  mov     ebx, eax
0x3838878e2  call    cs:__imp_VariantClear
0x3838878e8  mov     r11d, r13d
0x3838878eb  mov     eax, 7
0x3838878f0  test    ebx, ebx
0x3838878f2  cmovs   r11d, eax
0x3838878f6  mov     [rdi+0Ch], r11d
0x3838878fa  jmp     loc_38384CDEB
0x3838f4b20  mov     ebx, 80004005h
0x3838f4b25  mov     dword ptr [rsi+8], 1
0x3838f4b2c  jmp     loc_38384CDF3
0x3838f4b31  mov     rax, [r14]
0x3838f4b34  lea     r9, [rsp+78h+pvargSrc]
0x3838f4b39  mov     r8d, ebx
0x3838f4b3c  mov     edx, r12d
0x3838f4b3f  mov     rcx, r14
0x3838f4b42  call    qword ptr [rax+38h]
0x3838f4b45  test    eax, eax
0x3838f4b47  jz      loc_3838878A7
0x3838f4b4d  mov     dword ptr [rsi+8], 8
0x3838f4b54  mov     ebx, 80004005h
0x3838f4b59  jmp     loc_38384CDF3
0x3838f4b5e  mov     rcx, [rdi+18h]; this
0x3838f4b62  test    rcx, rcx
0x3838f4b65  jz      short loc_3838F4B6C
0x3838f4b67  call    ??_GCColumnIds@@QEAAPEAXI@Z; CColumnIds::`scalar deleting destructor'(uint)
0x3838f4b6c  mov     [rdi+18h], r13
0x3838f4b70  jmp     loc_3838878B5
0x3838f4b75  lea     rcx, [rsi+10h]; struct tagDBID *
0x3838f4b79  test    rcx, rcx
0x3838f4b7c  jz      short loc_3838F4B8C
0x3838f4b7e  lea     rdx, DB_NULLID; struct tagDBID *
0x3838f4b85  call    ?CompareDBIDs@@YAJPEBUtagDBID@@0@Z; CompareDBIDs(tagDBID const *,tagDBID const *)
0x3838f4b8a  jmp     short loc_3838F4B91
0x3838f4b8c  mov     eax, 1
0x3838f4b91  test    eax, eax
0x3838f4b93  jnz     short loc_3838F4BBE
0x3838f4b95  mov     rcx, [rdi+18h]; this
0x3838f4b99  test    rcx, rcx
0x3838f4b9c  jz      short loc_3838F4BA3
0x3838f4b9e  call    ??_GCColumnIds@@QEAAPEAXI@Z; CColumnIds::`scalar deleting destructor'(uint)
0x3838f4ba3  mov     [rdi+18h], r13
0x3838f4ba7  mov     eax, [rsi+4]
0x3838f4baa  lea     rcx, [rdi+20h]; pvargDest
0x3838f4bae  mov     rdx, rbp; pvargSrc
0x3838f4bb1  mov     [rdi], eax
0x3838f4bb3  call    cs:__imp_VariantCopy
0x3838f4bb9  jmp     loc_38384CDD9
0x3838f4bbe  cmp     [rdi+18h], r13
0x3838f4bc2  jnz     short loc_3838F4BE5
0x3838f4bc4  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3838f4bcb  mov     edx, 18h
0x3838f4bd0  mov     rax, [rcx]
0x3838f4bd3  call    qword ptr [rax+58h]
0x3838f4bd6  mov     [rax+10h], r13
0x3838f4bda  mov     [rax], r13
0x3838f4bdd  mov     [rax+8], r13
0x3838f4be1  mov     [rdi+18h], rax
0x3838f4be5  mov     rcx, [rdi+18h]; this
0x3838f4be9  mov     eax, 7
0x3838f4bee  mov     [rdi+0Ch], eax
0x3838f4bf1  test    rcx, rcx
0x3838f4bf4  jz      short loc_3838F4C0D
0x3838f4bf6  mov     rdx, rsi; struct tagDBPROP *
0x3838f4bf9  call    ?AddColumnId@CColumnIds@@QEAAJPEAUtagDBPROP@@@Z; CColumnIds::AddColumnId(tagDBPROP *)
0x3838f4bfe  mov     ebx, eax
0x3838f4c00  test    eax, eax
0x3838f4c02  jns     loc_38384CDE3
0x3838f4c08  jmp     loc_38384CDF3
0x3838f4c0d  test    byte ptr cs:_bidGblFlags, 2
0x3838f4c14  jz      short loc_3838F4C34
0x3838f4c16  mov     rcx, cs:off_383B43500; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838f4c1d  mov     edx, 27E009h
0x3838f4c22  mov     r8d, 8007000Eh
0x3838f4c28  call    _bidTraceHR
0x3838f4c2d  mov     ebx, eax
0x3838f4c2f  jmp     loc_38384CDEB
0x3838f4c34  mov     ebx, 8007000Eh
0x3838f4c39  jmp     loc_38384CDEB
0x3838f4c3e  mov     eax, 7
0x3838f4c43  mov     [rdi+0Ch], eax
0x3838f4c46  jmp     loc_38384CDEB
```
