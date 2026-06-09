# PHN_DICT::SAPIIdToSRId_BSTR(ushort * const,ushort * *)

- ea: `0x1800ae4bc`
- end: `0x1800ae7b5`
- name: `?SAPIIdToSRId_BSTR@PHN_DICT@@QEBAJQEAGPEAPEAG@Z`
- size: `761`
- prototype: `int(PHN_DICT *__hidden this, unsigned __int16 *const, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800c8350`

## callees

- `0x180002470`
- `0x180002e00`
- `0x1800041d0`
- `0x1800060c0`
- `0x1800ae260`
- `0x1800ae4bc`
- `0x1800ba6b4`
- `0x180102010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800ae6eb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800ae70d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800ae72a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800ae6eb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800ae70d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800ae72a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800ae4e1`
- `OLEAUT32!__imp_SysStringLen` at `0x1800ae4e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae777`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae777`

## pseudocode

```c
__int64 __fastcall PHN_DICT::SAPIIdToSRId_BSTR(PHN_DICT *this, unsigned __int16 *const a2, unsigned __int16 **a3)
{
  UINT v5; // eax
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rbx
  struct ITextNormMultiResult *v9; // r12
  SIZE_T v10; // rax
  OLECHAR *v11; // r14
  unsigned __int16 *v12; // rdi
  int InputTape; // ebx
  __int64 v14; // rax
  PHN_DICT *v15; // rcx
  wchar_t *v16; // rax
  unsigned __int64 v17; // rdx
  UINT v18; // esi
  wchar_t *v19; // r15
  char v20; // r9
  unsigned __int64 v21; // rcx
  wchar_t *v22; // r8
  SIZE_T v23; // rax
  UINT v24; // edi
  __int64 v25; // rax
  __int64 v26; // rax
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rax
  struct ITextNormMultiResult *v29; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v30; // [rsp+38h] [rbp-18h]
  struct InputTape *v31; // [rsp+40h] [rbp-10h] BYREF
  wchar_t *Buffer; // [rsp+A8h] [rbp+58h] BYREF

  v5 = SysStringLen(a2);
  v6 = 0;
  v7 = v5;
  if ( !v5 )
    return 2147942487LL;
  v29 = 0;
  Buffer = 0;
  v9 = 0;
  v10 = 2 * (v5 + 4LL * v5 + 1);
  v11 = 0;
  if ( !is_mul_ok(v7 + 4 * v7 + 1, 2u) )
    v10 = -1;
  v30 = (unsigned __int16 *)CWinHeap::Alloc(&g_heap, v10, 0);
  v12 = v30;
  v31 = 0;
  if ( v30 )
  {
    if ( v7 )
    {
      do
      {
        StringCchPrintfW(v12, 6u, L"%04x ", a2[v6]);
        v14 = -1;
        do
          ++v14;
        while ( v12[v14] );
        ++v6;
        v12 += v14;
      }
      while ( v6 < v7 );
    }
    v12 = v30;
    InputTape = ITransducer::GetInputTape(*((_QWORD *)this + 21), (__int64)v30, 0, &v31, 0);
    if ( InputTape < 0 )
    {
LABEL_42:
      if ( v31 )
        (**(void (__fastcall ***)(struct InputTape *, __int64))v31)(v31, 1);
      if ( v9 )
        (*(void (__fastcall **)(struct ITextNormMultiResult *))(*(_QWORD *)v9 + 16LL))(v9);
      goto LABEL_46;
    }
    InputTape = PHN_DICT::ReceiveString(v15, v31, *((struct ITransducer **)this + 21), &v29);
    if ( InputTape < 0 )
    {
      v28 = SysAllocStringLen(&word_18010FB50, 0);
      v9 = v29;
      *a3 = v28;
      goto LABEL_42;
    }
    v9 = v29;
    InputTape = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *, wchar_t **))(*(_QWORD *)v29 + 24LL))(
                  v29,
                  &Buffer);
    if ( InputTape < 0 )
      goto LABEL_42;
    v16 = Buffer;
    v17 = -1;
    do
      ++v17;
    while ( Buffer[v17] );
    if ( !v17 )
    {
      InputTape = -2147196928;
      *a3 = SysAllocStringLen(&word_18010FB50, 0);
      goto LABEL_42;
    }
    v18 = 1;
    v19 = Buffer;
    v20 = 0;
    v21 = 0;
    while ( 1 )
    {
      v22 = &v16[v21++];
      if ( *v22 != 32 )
        break;
      if ( v21 >= v17 )
      {
LABEL_21:
        v23 = 2LL * (v18 + 1);
        if ( !is_mul_ok(v18 + 1, 2u) )
          v23 = -1;
        v11 = (OLECHAR *)CWinHeap::Alloc(&g_heap, v23, 0);
        if ( !v11 )
          goto LABEL_24;
        v24 = 0;
        if ( v18 )
        {
          do
          {
            v25 = -1;
            do
              ++v25;
            while ( v19[v25] );
            if ( v25 )
              swscanf_s(v19, L"%d", &v11[v24]);
            v26 = -1;
            do
              ++v26;
            while ( v19[v26] );
            ++v24;
            v19 += v26 + 1;
          }
          while ( v24 < v18 );
          v9 = v29;
        }
        v11[v18] = 0;
        v27 = SysAllocStringLen(v11, v18);
        v12 = v30;
        *a3 = v27;
        if ( !v27 )
LABEL_24:
          InputTape = -2147024882;
        goto LABEL_42;
      }
      if ( v22[1] == 32 || !v20 )
      {
LABEL_20:
        if ( v21 >= v17 )
          goto LABEL_21;
      }
      else
      {
        *v22 = 0;
        ++v18;
        v16 = Buffer;
      }
    }
    v20 = 1;
    goto LABEL_20;
  }
  InputTape = -2147024882;
LABEL_46:
  if ( Buffer )
  {
    CoTaskMemFree(Buffer);
    Buffer = 0;
  }
  if ( v12 )
    operator delete(v12);
  if ( v11 )
    operator delete(v11);
  return (unsigned int)InputTape;
}

```

## disassembly

```asm
0x1800ae4bc  mov     [rsp-38h+arg_0], rbx
0x1800ae4c1  mov     [rsp-38h+arg_10], r8
0x1800ae4c6  push    rbp
0x1800ae4c7  push    rsi
0x1800ae4c8  push    rdi
0x1800ae4c9  push    r12
0x1800ae4cb  push    r13
0x1800ae4cd  push    r14
0x1800ae4cf  push    r15
0x1800ae4d1  mov     rbp, rsp
0x1800ae4d4  sub     rsp, 50h
0x1800ae4d8  mov     r13, rcx
0x1800ae4db  mov     r15, rdx
0x1800ae4de  mov     rcx, rdx; pbstr
0x1800ae4e1  call    cs:__imp_SysStringLen
0x1800ae4e7  xor     esi, esi
0x1800ae4e9  mov     ebx, eax
0x1800ae4eb  test    eax, eax
0x1800ae4ed  jnz     short loc_1800AE4F9
0x1800ae4ef  mov     eax, 80070057h
0x1800ae4f4  jmp     loc_1800AE79D
0x1800ae4f9  lea     rcx, ds:1[rbx*4]
0x1800ae501  mov     [rbp+var_20], rsi
0x1800ae505  add     rcx, rbx
0x1800ae508  mov     [rbp+Buffer], rsi
0x1800ae50c  mov     eax, 2
0x1800ae511  mov     r12, rsi
0x1800ae514  mul     rcx
0x1800ae517  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ae51e  mov     r14, rsi
0x1800ae521  cmovb   rax, rcx
0x1800ae525  xor     r8d, r8d; bool
0x1800ae528  mov     rdx, rax; unsigned __int64
0x1800ae52b  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800ae532  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800ae537  mov     [rbp+var_18], rax
0x1800ae53b  mov     rdi, rax
0x1800ae53e  mov     [rbp+var_10], rsi
0x1800ae542  test    rax, rax
0x1800ae545  jnz     short loc_1800AE554
0x1800ae547  mov     ebx, 8007000Eh
0x1800ae54c  xor     r13d, r13d
0x1800ae54f  jmp     loc_1800AE76E
0x1800ae554  test    rbx, rbx
0x1800ae557  jz      short loc_1800AE58D
0x1800ae559  movzx   r9d, word ptr [r15+rsi*2]
0x1800ae55e  lea     r8, a04x; "%04x "
0x1800ae565  mov     edx, 6; unsigned __int64
0x1800ae56a  mov     rcx, rdi; unsigned __int16 *
0x1800ae56d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ae572  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ae576  xor     ecx, ecx
0x1800ae578  inc     rax
0x1800ae57b  cmp     [rdi+rax*2], cx
0x1800ae57f  jnz     short loc_1800AE578
0x1800ae581  inc     rsi
0x1800ae584  lea     rdi, [rdi+rax*2]
0x1800ae588  cmp     rsi, rbx
0x1800ae58b  jb      short loc_1800AE559
0x1800ae58d  mov     rdi, [rbp+var_18]
0x1800ae591  lea     r9, [rbp+var_10]
0x1800ae595  mov     rcx, [r13+0A8h]
0x1800ae59c  xor     esi, esi
0x1800ae59e  mov     rdx, rdi
0x1800ae5a1  mov     [rsp+50h+var_30], rsi
0x1800ae5a6  xor     r8d, r8d
0x1800ae5a9  call    ?GetInputTape@ITransducer@@QEBAJPEBGW4INPUT_TYPE@InputTape@@PEAPEAV3@PEAUIAttributeLexicon@@W4TN_BOUNDARY@@@Z; ITransducer::GetInputTape(ushort const *,InputTape::INPUT_TYPE,InputTape * *,IAttributeLexicon *,TN_BOUNDARY)
0x1800ae5ae  mov     ebx, eax
0x1800ae5b0  test    eax, eax
0x1800ae5b2  js      loc_1800AE73D
0x1800ae5b8  mov     r8, [r13+0A8h]; struct ITransducer *
0x1800ae5bf  lea     r9, [rbp+var_20]; struct ITextNormMultiResult **
0x1800ae5c3  mov     rdx, [rbp+var_10]; struct InputTape *
0x1800ae5c7  call    ?ReceiveString@PHN_DICT@@IEBAJPEBVInputTape@@PEAVITransducer@@PEAPEAUITextNormMultiResult@@@Z; PHN_DICT::ReceiveString(InputTape const *,ITransducer *,ITextNormMultiResult * *)
0x1800ae5cc  xor     r13d, r13d
0x1800ae5cf  mov     ebx, eax
0x1800ae5d1  test    eax, eax
0x1800ae5d3  js      loc_1800AE721
0x1800ae5d9  mov     r12, [rbp+var_20]
0x1800ae5dd  lea     rdx, [rbp+Buffer]
0x1800ae5e1  mov     rcx, r12
0x1800ae5e4  mov     rax, [r12]
0x1800ae5e8  mov     rax, [rax+18h]
0x1800ae5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae5f1  mov     ebx, eax
0x1800ae5f3  test    eax, eax
0x1800ae5f5  js      loc_1800AE740
0x1800ae5fb  mov     rax, [rbp+Buffer]
0x1800ae5ff  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800ae603  mov     rdx, r10
0x1800ae606  inc     rdx; ui
0x1800ae609  cmp     [rax+rdx*2], r13w
0x1800ae60e  jnz     short loc_1800AE606
0x1800ae610  test    rdx, rdx
0x1800ae613  jz      loc_1800AE706
0x1800ae619  mov     esi, 1
0x1800ae61e  mov     r15, rax
0x1800ae621  mov     r9b, r13b
0x1800ae624  mov     rcx, r13
0x1800ae627  lea     r8, [rax+rcx*2]
0x1800ae62b  inc     rcx
0x1800ae62e  cmp     word ptr [r8], 20h ; ' '
0x1800ae633  jz      short loc_1800AE670
0x1800ae635  mov     r9b, 1
0x1800ae638  cmp     rcx, rdx
0x1800ae63b  jb      short loc_1800AE627
0x1800ae63d  lea     edx, [rsi+1]
0x1800ae640  mov     eax, 2
0x1800ae645  mul     rdx
0x1800ae648  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800ae64f  cmovb   rax, r10
0x1800ae653  xor     r8d, r8d; bool
0x1800ae656  mov     rdx, rax; unsigned __int64
0x1800ae659  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800ae65e  mov     r14, rax
0x1800ae661  test    rax, rax
0x1800ae664  jnz     short loc_1800AE68E
0x1800ae666  mov     ebx, 8007000Eh
0x1800ae66b  jmp     loc_1800AE740
0x1800ae670  cmp     rcx, rdx
0x1800ae673  jnb     short loc_1800AE63D
0x1800ae675  cmp     word ptr [r8+2], 20h ; ' '
0x1800ae67b  jz      short loc_1800AE638
0x1800ae67d  test    r9b, r9b
0x1800ae680  jz      short loc_1800AE638
0x1800ae682  mov     [r8], r13w
0x1800ae686  inc     esi
0x1800ae688  mov     rax, [rbp+Buffer]
0x1800ae68c  jmp     short loc_1800AE627
0x1800ae68e  mov     edi, r13d
0x1800ae691  test    esi, esi
0x1800ae693  jz      short loc_1800AE6DF
0x1800ae695  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800ae699  mov     rax, r12
0x1800ae69c  inc     rax
0x1800ae69f  cmp     [r15+rax*2], r13w
0x1800ae6a4  jnz     short loc_1800AE69C
0x1800ae6a6  test    rax, rax
0x1800ae6a9  jz      short loc_1800AE6C0
0x1800ae6ab  mov     eax, edi
0x1800ae6ad  lea     rdx, aD; "%d"
0x1800ae6b4  mov     rcx, r15; Buffer
0x1800ae6b7  lea     r8, [r14+rax*2]
0x1800ae6bb  call    swscanf_s
0x1800ae6c0  mov     rax, r12
0x1800ae6c3  inc     rax
0x1800ae6c6  cmp     [r15+rax*2], r13w
0x1800ae6cb  jnz     short loc_1800AE6C3
0x1800ae6cd  lea     r15, [r15+rax*2]
0x1800ae6d1  inc     edi
0x1800ae6d3  add     r15, 2
0x1800ae6d7  cmp     edi, esi
0x1800ae6d9  jb      short loc_1800AE699
0x1800ae6db  mov     r12, [rbp+var_20]
0x1800ae6df  mov     ecx, esi
0x1800ae6e1  mov     edx, esi; ui
0x1800ae6e3  mov     [r14+rcx*2], r13w
0x1800ae6e8  mov     rcx, r14; strIn
0x1800ae6eb  call    cs:__imp_SysAllocStringLen
0x1800ae6f1  mov     rcx, [rbp+arg_10]
0x1800ae6f5  mov     rdi, [rbp+var_18]
0x1800ae6f9  mov     [rcx], rax
0x1800ae6fc  test    rax, rax
0x1800ae6ff  jnz     short loc_1800AE740
0x1800ae701  jmp     loc_1800AE666
0x1800ae706  lea     rcx, word_18010FB50; strIn
0x1800ae70d  call    cs:__imp_SysAllocStringLen
0x1800ae713  mov     rcx, [rbp+arg_10]
0x1800ae717  mov     ebx, 80046000h
0x1800ae71c  mov     [rcx], rax
0x1800ae71f  jmp     short loc_1800AE740
0x1800ae721  xor     edx, edx; ui
0x1800ae723  lea     rcx, word_18010FB50; strIn
0x1800ae72a  call    cs:__imp_SysAllocStringLen
0x1800ae730  mov     rcx, [rbp+arg_10]
0x1800ae734  mov     r12, [rbp+var_20]
0x1800ae738  mov     [rcx], rax
0x1800ae73b  jmp     short loc_1800AE740
0x1800ae73d  xor     r13d, r13d
0x1800ae740  mov     rcx, [rbp+var_10]
0x1800ae744  test    rcx, rcx
0x1800ae747  jz      short loc_1800AE759
0x1800ae749  mov     rax, [rcx]
0x1800ae74c  mov     edx, 1
0x1800ae751  mov     rax, [rax]
0x1800ae754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae759  test    r12, r12
0x1800ae75c  jz      short loc_1800AE76E
0x1800ae75e  mov     rax, [r12]
0x1800ae762  mov     rcx, r12
0x1800ae765  mov     rax, [rax+10h]
0x1800ae769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae76e  mov     rcx, [rbp+Buffer]; pv
0x1800ae772  test    rcx, rcx
0x1800ae775  jz      short loc_1800AE781
0x1800ae777  call    cs:__imp_CoTaskMemFree
0x1800ae77d  mov     [rbp+Buffer], r13
0x1800ae781  test    rdi, rdi
0x1800ae784  jz      short loc_1800AE78E
0x1800ae786  mov     rcx, rdi; void *
0x1800ae789  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ae78e  test    r14, r14
0x1800ae791  jz      short loc_1800AE79B
0x1800ae793  mov     rcx, r14; void *
0x1800ae796  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ae79b  mov     eax, ebx
0x1800ae79d  mov     rbx, [rsp+50h+arg_0]
0x1800ae7a5  add     rsp, 50h
0x1800ae7a9  pop     r15
0x1800ae7ab  pop     r14
0x1800ae7ad  pop     r13
0x1800ae7af  pop     r12
0x1800ae7b1  pop     rdi
0x1800ae7b2  pop     rsi
0x1800ae7b3  pop     rbp
0x1800ae7b4  retn
```
