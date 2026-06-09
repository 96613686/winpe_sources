# CLatticeWrapper::AssignHomophoneGroups(void)

- ea: `0x180076738`
- end: `0x180076a8e`
- name: `?AssignHomophoneGroups@CLatticeWrapper@@IEAAJXZ`
- size: `854`
- prototype: `__int64 __fastcall(CLatticeWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180077cf4`

## callees

- `0x180002470`
- `0x1800034d4`
- `0x1800035b0`
- `0x180006684`
- `0x1800765d0`
- `0x180076738`
- `0x180083578`
- `0x180084764`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076936`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076a3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076936`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076a3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLatticeWrapper::AssignHomophoneGroups(CLatticeWrapper *this)
{
  unsigned int v2; // eax
  __int64 v3; // rbx
  __int64 v4; // rax
  unsigned __int64 v5; // kr00_8
  bool v6; // cf
  SIZE_T v7; // rax
  _QWORD *v8; // rax
  void (__fastcall ***v9)(_QWORD, __int64); // rdi
  int Text; // ebx
  __int64 *v11; // r14
  unsigned int v12; // r12d
  __int64 i; // rsi
  unsigned int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // ebx
  void *v18; // rcx
  unsigned __int16 *v19; // rax
  int v20; // edx
  int v21; // r8d
  _DWORD *v22; // rcx
  __int64 v23; // rsi
  int v24; // r15d
  unsigned int j; // r8d
  unsigned __int16 *v26; // rax
  __int64 v27; // r10
  int v28; // ecx
  int v29; // edx
  __int64 v30; // rcx
  __int16 v31; // ax
  __int64 k; // rdx
  __int64 v33; // r10
  unsigned __int16 *v34; // r8
  __int64 v35; // r11
  int v36; // eax
  int v37; // ecx
  __int16 v38; // dx
  LPVOID v40; // [rsp+80h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+50h] BYREF
  _QWORD *v42; // [rsp+90h] [rbp+58h] BYREF

  v40 = 0;
  v2 = *((_DWORD *)this + 240);
  if ( !v2 )
  {
    Text = 0;
    v9 = 0;
    v11 = (__int64 *)((char *)this + 944);
LABEL_14:
    v12 = 0;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v14 = *((_DWORD *)this + 240);
      if ( (unsigned int)i >= v14 )
        break;
      v15 = *(_QWORD *)(*v11 + 8 * i);
      *(_DWORD *)(v15 + 2312) &= 0x80000000;
      **(_WORD **)(v15 + 2304) = 0;
      v16 = *v11;
      if ( *(_DWORD *)(*(_QWORD *)(*v11 + 8 * i) + 816LL) )
      {
        v17 = 0;
        do
        {
          CQuickStringW<384>::Append(
            *(_QWORD *)(v16 + 8 * i) + 2296LL,
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 8 * i) + 16LL) + 104LL) + 56LL * v17++ + 40));
          v16 = *v11;
        }
        while ( v17 < *(_DWORD *)(*(_QWORD *)(*v11 + 8 * i) + 816LL) );
      }
      pv = 0;
      ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(
        &v42,
        *(_QWORD *)(*(_QWORD *)(v16 + 8 * i) + 24LL));
      Text = GetText(&v42, 1, &pv);
      if ( Text < 0 )
        goto LABEL_51;
      v18 = pv;
      v19 = (unsigned __int16 *)pv;
      do
      {
        v20 = *(unsigned __int16 *)((char *)v19 + (_BYTE *)v40 - (_BYTE *)pv);
        v21 = *v19 - v20;
        if ( v21 )
          break;
        ++v19;
      }
      while ( v20 );
      if ( !v21 )
      {
        v22 = &v9[100 * v12];
        v22[4] &= 0x80000000;
        **((_WORD **)v22 + 1) = 0;
        Text = CQuickStringW<384>::Append(v22, *(_QWORD *)(*(_QWORD *)(*v11 + 8 * i) + 2304LL));
        if ( Text < 0 )
          goto LABEL_51;
        ++v12;
        v18 = pv;
      }
      CoTaskMemFree(v18);
    }
    if ( v14 )
    {
      v23 = 0;
      v24 = 1;
      do
      {
        for ( j = 0; j < v12; ++j )
        {
          v26 = (unsigned __int16 *)v9[100 * j + 1];
          v27 = *(_QWORD *)(*(_QWORD *)(*v11 + 8 * v23) + 2304LL) - (_QWORD)v26;
          do
          {
            v28 = *(unsigned __int16 *)((char *)v26 + v27);
            v29 = *v26 - v28;
            if ( v29 )
              break;
            ++v26;
          }
          while ( v28 );
          if ( !v29 )
          {
            v30 = *(_QWORD *)(*(_QWORD *)(*v11 + 8 * v23) + 16LL);
            v31 = 0;
LABEL_46:
            *(_WORD *)(v30 + 6) = v31;
            goto LABEL_49;
          }
        }
        if ( j == v12 )
        {
          for ( k = 0; (unsigned int)k < (unsigned int)v23; k = (unsigned int)(k + 1) )
          {
            v33 = *v11;
            v34 = *(unsigned __int16 **)(*(_QWORD *)(*v11 + 8 * v23) + 2304LL);
            v35 = *(_QWORD *)(*(_QWORD *)(*v11 + 8 * k) + 2304LL) - (_QWORD)v34;
            do
            {
              v36 = *(unsigned __int16 *)((char *)v34 + v35);
              v37 = *v34 - v36;
              if ( v37 )
                break;
              ++v34;
            }
            while ( v36 );
            if ( !v37 )
            {
              v30 = *(_QWORD *)(*(_QWORD *)(v33 + 8 * v23) + 16LL);
              v31 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v33 + 8 * k) + 16LL) + 6LL);
              goto LABEL_46;
            }
          }
          if ( (_DWORD)k == (_DWORD)v23 )
          {
            v38 = v24++;
            *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*v11 + 8 * v23) + 16LL) + 6LL) = v38;
          }
        }
LABEL_49:
        Text = CPhrase::UpdatePhraseBuilder(*(CPhrase **)(*v11 + 8 * v23));
        if ( Text < 0 )
          break;
        v23 = (unsigned int)(v23 + 1);
      }
      while ( (unsigned int)v23 < *((_DWORD *)this + 240) );
    }
    goto LABEL_51;
  }
  v3 = v2;
  pv = (LPVOID)*((unsigned int *)this + 240);
  v5 = v2;
  v4 = 800LL * v2;
  if ( !is_mul_ok(v5, 0x320u) )
    v4 = -1;
  v6 = __CFADD__(v4, 8);
  v7 = v4 + 8;
  if ( v6 )
    v7 = -1;
  v8 = CWinHeap::Alloc(&g_heap, v7, 0);
  v42 = v8;
  if ( v8 )
  {
    *v8 = v3;
    v9 = (void (__fastcall ***)(_QWORD, __int64))(v8 + 1);
    `eh vector constructor iterator'(
      v8 + 1,
      0x320u,
      (unsigned int)v3,
      CQuickStringW<384>::CQuickStringW<384>,
      CQuickStringW<64>::~CQuickStringW<64>);
  }
  else
  {
    v9 = 0;
  }
  if ( !v9 )
  {
    Text = -2147024809;
    goto LABEL_51;
  }
  v11 = (__int64 *)((char *)this + 944);
  ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(
    &pv,
    *(_QWORD *)(**((_QWORD **)this + 118) + 24LL));
  Text = GetText(&pv, 1, &v40);
  if ( Text >= 0 )
    goto LABEL_14;
LABEL_51:
  if ( v40 )
  {
    CoTaskMemFree(v40);
    v40 = 0;
  }
  if ( v9 )
  {
    if ( *(v9 - 1) )
      (**v9)(v9, 3);
    else
      operator delete(v9 - 1, 8u);
  }
  return (unsigned int)Text;
}

```

## disassembly

```asm
0x180076738  push    rbp
0x18007673a  push    rbx
0x18007673b  push    rsi
0x18007673c  push    rdi
0x18007673d  push    r12
0x18007673f  push    r13
0x180076741  push    r14
0x180076743  push    r15
0x180076745  mov     rbp, rsp
0x180076748  sub     rsp, 38h
0x18007674c  mov     r13, rcx
0x18007674f  mov     [rbp+arg_0], 0
0x180076757  mov     eax, [rcx+3C0h]
0x18007675d  test    eax, eax
0x18007675f  jz      loc_180076815
0x180076765  mov     ebx, eax
0x180076767  mov     [rbp+pv], rax
0x18007676b  mov     esi, 320h
0x180076770  mov     eax, esi
0x180076772  mul     rbx
0x180076775  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18007677c  cmovb   rax, rcx
0x180076780  add     rax, 8
0x180076784  cmovb   rax, rcx
0x180076788  xor     r8d, r8d; bool
0x18007678b  mov     rdx, rax; unsigned __int64
0x18007678e  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180076795  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x18007679a  mov     [rbp+arg_10], rax
0x18007679e  test    rax, rax
0x1800767a1  jz      short loc_1800767CC
0x1800767a3  mov     [rax], rbx
0x1800767a6  lea     rdi, [rax+8]
0x1800767aa  lea     rax, ??1?$CQuickStringW@$0EA@@@UEAA@XZ; CQuickStringW<64>::~CQuickStringW<64>(void)
0x1800767b1  mov     [rsp+38h+var_18], rax; void (*)(void *)
0x1800767b6  lea     r9, ??0?$CQuickStringW@$0BIA@@@QEAA@XZ; void (*)(void *)
0x1800767bd  mov     r8d, ebx; unsigned __int64
0x1800767c0  mov     edx, esi; unsigned __int64
0x1800767c2  mov     rcx, rdi; void *
0x1800767c5  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800767ca  jmp     short loc_1800767CE
0x1800767cc  xor     edi, edi
0x1800767ce  test    rdi, rdi
0x1800767d1  jnz     short loc_1800767DD
0x1800767d3  mov     ebx, 80070057h
0x1800767d8  jmp     loc_180076A36
0x1800767dd  lea     r14, [r13+3B0h]
0x1800767e4  mov     rax, [r14]
0x1800767e7  mov     rdx, [rax]
0x1800767ea  mov     rdx, [rdx+18h]
0x1800767ee  lea     rcx, [rbp+pv]
0x1800767f2  call    ??0?$CComPtrBase@UIMSASRLocaleHandler@@@ATL@@IEAA@PEAUIMSASRLocaleHandler@@@Z; ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(IMSASRLocaleHandler *)
0x1800767f7  lea     r8, [rbp+arg_0]
0x1800767fb  mov     edx, 1
0x180076800  lea     rcx, [rbp+pv]
0x180076804  call    ?GetText@@YAJV?$CComPtr@UISpPhraseBuilder@@@ATL@@HPEAPEAG@Z; GetText(ATL::CComPtr<ISpPhraseBuilder>,int,ushort * *)
0x180076809  mov     ebx, eax
0x18007680b  test    eax, eax
0x18007680d  js      loc_180076A36
0x180076813  jmp     short loc_180076820
0x180076815  xor     ebx, ebx
0x180076817  xor     edi, edi
0x180076819  lea     r14, [rcx+3B0h]
0x180076820  xor     r12d, r12d
0x180076823  xor     esi, esi
0x180076825  mov     eax, [r13+3C0h]
0x18007682c  cmp     esi, eax
0x18007682e  jnb     loc_180076943
0x180076834  mov     rax, [r14]
0x180076837  mov     rcx, [rax+rsi*8]
0x18007683b  and     dword ptr [rcx+908h], 80000000h
0x180076845  mov     rcx, [rcx+900h]
0x18007684c  xor     eax, eax
0x18007684e  mov     [rcx], ax
0x180076851  mov     rdx, [r14]
0x180076854  mov     rax, [rdx+rsi*8]
0x180076858  cmp     dword ptr [rax+330h], 0
0x18007685f  jbe     short loc_180076897
0x180076861  xor     ebx, ebx
0x180076863  mov     rcx, [rdx+rsi*8]
0x180076867  mov     rdx, [rcx+10h]
0x18007686b  mov     eax, ebx
0x18007686d  imul    r8, rax, 38h ; '8'
0x180076871  mov     rdx, [rdx+68h]
0x180076875  add     rcx, 8F8h
0x18007687c  mov     rdx, [rdx+r8+28h]
0x180076881  call    ?Append@?$CQuickStringW@$0BIA@@@QEAAJQEBG@Z; CQuickStringW<384>::Append(ushort const * const)
0x180076886  inc     ebx
0x180076888  mov     rdx, [r14]
0x18007688b  mov     rax, [rdx+rsi*8]
0x18007688f  cmp     ebx, [rax+330h]
0x180076895  jb      short loc_180076863
0x180076897  mov     [rbp+pv], 0
0x18007689f  mov     rdx, [rdx+rsi*8]
0x1800768a3  mov     rdx, [rdx+18h]
0x1800768a7  lea     rcx, [rbp+arg_10]
0x1800768ab  call    ??0?$CComPtrBase@UIMSASRLocaleHandler@@@ATL@@IEAA@PEAUIMSASRLocaleHandler@@@Z; ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(IMSASRLocaleHandler *)
0x1800768b0  lea     r8, [rbp+pv]
0x1800768b4  mov     edx, 1
0x1800768b9  lea     rcx, [rbp+arg_10]
0x1800768bd  call    ?GetText@@YAJV?$CComPtr@UISpPhraseBuilder@@@ATL@@HPEAPEAG@Z; GetText(ATL::CComPtr<ISpPhraseBuilder>,int,ushort * *)
0x1800768c2  mov     ebx, eax
0x1800768c4  test    eax, eax
0x1800768c6  js      loc_180076A36
0x1800768cc  mov     rcx, [rbp+pv]
0x1800768d0  mov     rax, rcx
0x1800768d3  mov     r9, [rbp+arg_0]
0x1800768d7  sub     r9, rcx
0x1800768da  movzx   r8d, word ptr [rax]
0x1800768de  movzx   edx, word ptr [rax+r9]
0x1800768e3  sub     r8d, edx
0x1800768e6  jnz     short loc_1800768F0
0x1800768e8  add     rax, 2
0x1800768ec  test    edx, edx
0x1800768ee  jnz     short loc_1800768DA
0x1800768f0  test    r8d, r8d
0x1800768f3  jnz     short loc_180076936
0x1800768f5  mov     eax, r12d
0x1800768f8  imul    rcx, rax, 320h
0x1800768ff  add     rcx, rdi
0x180076902  and     dword ptr [rcx+10h], 80000000h
0x180076909  mov     rdx, [rcx+8]
0x18007690d  xor     eax, eax
0x18007690f  mov     [rdx], ax
0x180076912  mov     rax, [r14]
0x180076915  mov     rdx, [rax+rsi*8]
0x180076919  mov     rdx, [rdx+900h]
0x180076920  call    ?Append@?$CQuickStringW@$0BIA@@@QEAAJQEBG@Z; CQuickStringW<384>::Append(ushort const * const)
0x180076925  mov     ebx, eax
0x180076927  test    eax, eax
0x180076929  js      loc_180076A36
0x18007692f  inc     r12d
0x180076932  mov     rcx, [rbp+pv]; pv
0x180076936  call    cs:__imp_CoTaskMemFree
0x18007693c  inc     esi
0x18007693e  jmp     loc_180076825
0x180076943  test    eax, eax
0x180076945  jz      loc_180076A36
0x18007694b  xor     esi, esi
0x18007694d  lea     r15d, [rsi+1]
0x180076951  xor     r8d, r8d
0x180076954  cmp     r8d, r12d
0x180076957  jnb     short loc_1800769A2
0x180076959  mov     r11, [r14]
0x18007695c  mov     rdx, [r11+rsi*8]
0x180076960  mov     eax, r8d
0x180076963  imul    rcx, rax, 320h
0x18007696a  mov     rax, [rcx+rdi+8]
0x18007696f  mov     r10, [rdx+900h]
0x180076976  sub     r10, rax
0x180076979  movzx   edx, word ptr [rax]
0x18007697c  movzx   ecx, word ptr [rax+r10]
0x180076981  sub     edx, ecx
0x180076983  jnz     short loc_18007698D
0x180076985  add     rax, 2
0x180076989  test    ecx, ecx
0x18007698b  jnz     short loc_180076979
0x18007698d  test    edx, edx
0x18007698f  jz      short loc_180076996
0x180076991  inc     r8d
0x180076994  jmp     short loc_180076954
0x180076996  mov     rax, [r11+rsi*8]
0x18007699a  mov     rcx, [rax+10h]
0x18007699e  xor     eax, eax
0x1800769a0  jmp     short loc_1800769F7
0x1800769a2  jnz     short loc_180076A15
0x1800769a4  xor     edx, edx
0x1800769a6  cmp     edx, esi
0x1800769a8  jnb     short loc_1800769FD
0x1800769aa  mov     r10, [r14]
0x1800769ad  mov     rcx, [r10+rdx*8]
0x1800769b1  mov     rax, [r10+rsi*8]
0x1800769b5  mov     r8, [rax+900h]
0x1800769bc  mov     r11, [rcx+900h]
0x1800769c3  sub     r11, r8
0x1800769c6  movzx   ecx, word ptr [r8]
0x1800769ca  movzx   eax, word ptr [r8+r11]
0x1800769cf  sub     ecx, eax
0x1800769d1  jnz     short loc_1800769DB
0x1800769d3  add     r8, 2
0x1800769d7  test    eax, eax
0x1800769d9  jnz     short loc_1800769C6
0x1800769db  test    ecx, ecx
0x1800769dd  jz      short loc_1800769E3
0x1800769df  inc     edx
0x1800769e1  jmp     short loc_1800769A6
0x1800769e3  mov     rax, [r10+rdx*8]
0x1800769e7  mov     rdx, [rax+10h]
0x1800769eb  mov     rax, [r10+rsi*8]
0x1800769ef  mov     rcx, [rax+10h]
0x1800769f3  movzx   eax, word ptr [rdx+6]
0x1800769f7  mov     [rcx+6], ax
0x1800769fb  jmp     short loc_180076A15
0x1800769fd  jnz     short loc_180076A15
0x1800769ff  movzx   edx, r15w
0x180076a03  inc     r15d
0x180076a06  mov     rax, [r14]
0x180076a09  mov     rcx, [rax+rsi*8]
0x180076a0d  mov     rax, [rcx+10h]
0x180076a11  mov     [rax+6], dx
0x180076a15  mov     rcx, [r14]
0x180076a18  mov     rcx, [rcx+rsi*8]; this
0x180076a1c  call    ?UpdatePhraseBuilder@CPhrase@@QEAAJXZ; CPhrase::UpdatePhraseBuilder(void)
0x180076a21  mov     ebx, eax
0x180076a23  test    eax, eax
0x180076a25  js      short loc_180076A36
0x180076a27  inc     esi
0x180076a29  cmp     esi, [r13+3C0h]
0x180076a30  jb      loc_180076951
0x180076a36  mov     rcx, [rbp+arg_0]; pv
0x180076a3a  test    rcx, rcx
0x180076a3d  jz      short loc_180076A4D
0x180076a3f  call    cs:__imp_CoTaskMemFree
0x180076a45  mov     [rbp+arg_0], 0
0x180076a4d  test    rdi, rdi
0x180076a50  jz      short loc_180076A7B
0x180076a52  lea     rcx, [rdi-8]; void *
0x180076a56  cmp     qword ptr [rcx], 0
0x180076a5a  jz      short loc_180076A71
0x180076a5c  mov     rax, [rdi]
0x180076a5f  mov     edx, 3
0x180076a64  mov     rcx, rdi
0x180076a67  mov     rax, [rax]
0x180076a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076a6f  jmp     short loc_180076A7B
0x180076a71  mov     edx, 8; unsigned __int64
0x180076a76  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180076a7b  mov     eax, ebx
0x180076a7d  add     rsp, 38h
0x180076a81  pop     r15
0x180076a83  pop     r14
0x180076a85  pop     r13
0x180076a87  pop     r12
0x180076a89  pop     rdi
0x180076a8a  pop     rsi
0x180076a8b  pop     rbx
0x180076a8c  pop     rbp
0x180076a8d  retn
```
