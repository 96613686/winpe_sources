# MakeAlternatePhraseTemplate(tagSPPHRASEALTREQUEST *,SPPHRASE * *)

- ea: `0x180083684`
- end: `0x180083831`
- name: `?MakeAlternatePhraseTemplate@@YAJPEAUtagSPPHRASEALTREQUEST@@PEAPEAUSPPHRASE@@@Z`
- size: `429`
- prototype: `__int64 __fastcall(struct tagSPPHRASEALTREQUEST *, struct SPPHRASE **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009cd0`

## callees

- `0x180083684`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083817`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083817`

## pseudocode

```c
__int64 __fastcall MakeAlternatePhraseTemplate(struct tagSPPHRASEALTREQUEST *a1, LPVOID *a2)
{
  int v4; // r15d
  _DWORD *v5; // r11
  __int64 ulStartElement; // r14
  ULONG v7; // ebx
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // rdx
  __int64 v10; // r10
  unsigned __int64 v11; // r9
  unsigned int v12; // r12d
  unsigned int v13; // edi
  unsigned __int64 v14; // rsi
  unsigned int v15; // ecx
  _DWORD *v16; // rdx
  unsigned int v17; // r14d
  int v18; // r9d
  int v19; // r11d
  int v20; // ebp
  __int64 v21; // rax
  unsigned int v22; // r9d
  __int64 v23; // rdx
  __int64 v24; // rcx
  unsigned int v25; // eax
  LPVOID pv; // [rsp+70h] [rbp+8h] BYREF

  pv = 0;
  v4 = ((__int64 (__fastcall *)(ISpPhrase *, LPVOID *))a1->pPhrase->lpVtbl->GetPhrase)(a1->pPhrase, &pv);
  if ( v4 < 0 )
  {
    CoTaskMemFree(pv);
  }
  else
  {
    v5 = pv;
    ulStartElement = a1->ulStartElement;
    v7 = a1->cElements - 1;
    v8 = *((_QWORD *)pv + 15);
    v9 = v8;
    v10 = *((_QWORD *)pv + 13);
    v11 = v8;
    v12 = *((_DWORD *)pv + 16);
    v13 = ulStartElement + v7;
    v14 = v8 + 24LL * *((unsigned int *)pv + 28);
    if ( v8 < v14 )
    {
      do
      {
        v15 = *(_DWORD *)(v11 + 16);
        if ( v13 < v15 || (unsigned int)ulStartElement > *(_DWORD *)(v11 + 20) + v15 - 1 )
        {
          if ( v9 != v11 )
          {
            *(_OWORD *)v9 = *(_OWORD *)v11;
            *(_QWORD *)(v9 + 16) = *(_QWORD *)(v11 + 16);
          }
          v9 += 24LL;
        }
        v11 += 24LL;
      }
      while ( v11 < v14 );
      v5 = pv;
    }
    v5[28] = -1431655765 * ((__int64)(v9 - v8) >> 3);
    if ( v7 )
    {
      v16 = (_DWORD *)(v10 + 56 * ulStartElement);
      v17 = ulStartElement + 1;
      if ( v17 <= v13 )
      {
        v18 = v16[1];
        v19 = v16[3];
        v20 = v16[5];
        do
        {
          v21 = v17++;
          v18 += *(_DWORD *)(56 * v21 + v10 + 4);
          v16[1] = v18;
          v19 += *(_DWORD *)(56 * v21 + v10 + 12);
          v16[3] = v19;
          v20 += *(_DWORD *)(56 * v21 + v10 + 20);
          v16[5] = v20;
        }
        while ( v17 <= v13 );
      }
      v22 = v13 + 1;
      while ( v22 < v12 )
      {
        v23 = 56LL * v22;
        v24 = 56LL * (v22 - v7);
        ++v22;
        *(_OWORD *)(v24 + v10) = *(_OWORD *)(v23 + v10);
        *(_OWORD *)(v24 + v10 + 16) = *(_OWORD *)(v23 + v10 + 16);
        *(_OWORD *)(v24 + v10 + 32) = *(_OWORD *)(v23 + v10 + 32);
        *(_QWORD *)(v24 + v10 + 48) = *(_QWORD *)(v23 + v10 + 48);
      }
      *((_DWORD *)pv + 16) -= v7;
      while ( v8 < v14 )
      {
        v25 = *(_DWORD *)(v8 + 16);
        if ( v25 > v13 )
          *(_DWORD *)(v8 + 16) = v25 - v7;
        v8 += 24LL;
      }
    }
    *a2 = pv;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180083684  push    rbx
0x180083686  push    rbp
0x180083687  push    rsi
0x180083688  push    rdi
0x180083689  push    r12
0x18008368b  push    r13
0x18008368d  push    r14
0x18008368f  push    r15
0x180083691  sub     rsp, 28h
0x180083695  mov     rbx, rcx
0x180083698  mov     [rsp+68h+pv], 0
0x1800836a1  mov     rcx, [rcx+20h]
0x1800836a5  mov     r13, rdx
0x1800836a8  lea     rdx, [rsp+68h+pv]
0x1800836ad  mov     rax, [rcx]
0x1800836b0  mov     rax, [rax+18h]
0x1800836b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800836b9  mov     r15d, eax
0x1800836bc  test    eax, eax
0x1800836be  js      loc_180083812
0x1800836c4  mov     r11, [rsp+68h+pv]
0x1800836c9  mov     r14d, [rbx]
0x1800836cc  mov     ebx, [rbx+4]
0x1800836cf  dec     ebx
0x1800836d1  mov     r8, [r11+78h]
0x1800836d5  mov     eax, [r11+70h]
0x1800836d9  mov     rdx, r8
0x1800836dc  mov     r10, [r11+68h]
0x1800836e0  mov     r9, r8
0x1800836e3  mov     r12d, [r11+40h]
0x1800836e7  lea     edi, [r14+rbx]
0x1800836eb  lea     rcx, [rax+rax*2]
0x1800836ef  lea     rsi, [r8+rcx*8]
0x1800836f3  cmp     r8, rsi
0x1800836f6  jnb     short loc_180083734
0x1800836f8  mov     ecx, [r9+10h]
0x1800836fc  cmp     edi, ecx
0x1800836fe  jb      short loc_18008370B
0x180083700  dec     ecx
0x180083702  add     ecx, [r9+14h]
0x180083706  cmp     r14d, ecx
0x180083709  jbe     short loc_180083726
0x18008370b  cmp     rdx, r9
0x18008370e  jz      short loc_180083722
0x180083710  movups  xmm0, xmmword ptr [r9]
0x180083714  movups  xmmword ptr [rdx], xmm0
0x180083717  movsd   xmm1, qword ptr [r9+10h]
0x18008371d  movsd   qword ptr [rdx+10h], xmm1
0x180083722  add     rdx, 18h
0x180083726  add     r9, 18h
0x18008372a  cmp     r9, rsi
0x18008372d  jb      short loc_1800836F8
0x18008372f  mov     r11, [rsp+68h+pv]
0x180083734  sub     rdx, r8
0x180083737  mov     rax, 0AAAAAAAAAAAAAAABh
0x180083741  sar     rdx, 3
0x180083745  imul    rdx, rax
0x180083749  mov     [r11+70h], edx
0x18008374d  test    ebx, ebx
0x18008374f  jz      loc_180083807
0x180083755  imul    rdx, r14, 38h ; '8'
0x180083759  add     rdx, r10
0x18008375c  inc     r14d
0x18008375f  cmp     r14d, edi
0x180083762  ja      short loc_180083798
0x180083764  mov     r9d, [rdx+4]
0x180083768  mov     r11d, [rdx+0Ch]
0x18008376c  mov     ebp, [rdx+14h]
0x18008376f  mov     eax, r14d
0x180083772  inc     r14d
0x180083775  imul    rcx, rax, 38h ; '8'
0x180083779  add     r9d, [rcx+r10+4]
0x18008377e  mov     [rdx+4], r9d
0x180083782  add     r11d, [rcx+r10+0Ch]
0x180083787  mov     [rdx+0Ch], r11d
0x18008378b  add     ebp, [rcx+r10+14h]
0x180083790  mov     [rdx+14h], ebp
0x180083793  cmp     r14d, edi
0x180083796  jbe     short loc_18008376F
0x180083798  lea     r9d, [rdi+1]
0x18008379c  jmp     short loc_1800837E1
0x18008379e  mov     eax, r9d
0x1800837a1  imul    rdx, rax, 38h ; '8'
0x1800837a5  mov     eax, r9d
0x1800837a8  sub     eax, ebx
0x1800837aa  imul    rcx, rax, 38h ; '8'
0x1800837ae  movups  xmm0, xmmword ptr [rdx+r10]
0x1800837b3  inc     r9d
0x1800837b6  movups  xmmword ptr [rcx+r10], xmm0
0x1800837bb  movups  xmm1, xmmword ptr [rdx+r10+10h]
0x1800837c1  movups  xmmword ptr [rcx+r10+10h], xmm1
0x1800837c7  movups  xmm0, xmmword ptr [rdx+r10+20h]
0x1800837cd  movups  xmmword ptr [rcx+r10+20h], xmm0
0x1800837d3  movsd   xmm1, qword ptr [rdx+r10+30h]
0x1800837da  movsd   qword ptr [rcx+r10+30h], xmm1
0x1800837e1  cmp     r9d, r12d
0x1800837e4  jb      short loc_18008379E
0x1800837e6  mov     rax, [rsp+68h+pv]
0x1800837eb  sub     [rax+40h], ebx
0x1800837ee  jmp     short loc_180083802
0x1800837f0  mov     eax, [r8+10h]
0x1800837f4  cmp     eax, edi
0x1800837f6  jbe     short loc_1800837FE
0x1800837f8  sub     eax, ebx
0x1800837fa  mov     [r8+10h], eax
0x1800837fe  add     r8, 18h
0x180083802  cmp     r8, rsi
0x180083805  jb      short loc_1800837F0
0x180083807  mov     rax, [rsp+68h+pv]
0x18008380c  mov     [r13+0], rax
0x180083810  jmp     short loc_18008381D
0x180083812  mov     rcx, [rsp+68h+pv]; pv
0x180083817  call    cs:__imp_CoTaskMemFree
0x18008381d  mov     eax, r15d
0x180083820  add     rsp, 28h
0x180083824  pop     r15
0x180083826  pop     r14
0x180083828  pop     r13
0x18008382a  pop     r12
0x18008382c  pop     rdi
0x18008382d  pop     rsi
0x18008382e  pop     rbp
0x18008382f  pop     rbx
0x180083830  retn
```
