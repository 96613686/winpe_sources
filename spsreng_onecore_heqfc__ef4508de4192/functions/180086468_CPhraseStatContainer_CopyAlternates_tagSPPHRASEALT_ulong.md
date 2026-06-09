# CPhraseStatContainer::CopyAlternates(tagSPPHRASEALT *,ulong)

- ea: `0x180086468`
- end: `0x180086571`
- name: `?CopyAlternates@CPhraseStatContainer@@QEAAXPEAUtagSPPHRASEALT@@K@Z`
- size: `265`
- prototype: `void __fastcall(CPhraseStatContainer *__hidden this, struct tagSPPHRASEALT *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006c3a8`

## callees

- `0x18000614c`
- `0x180086468`
- `0x180086740`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086549`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086549`

## pseudocode

```c
void __fastcall CPhraseStatContainer::CopyAlternates(
        CPhraseStatContainer *this,
        struct tagSPPHRASEALT *a2,
        unsigned int a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rdi
  _QWORD *v9; // rbp
  struct tagSPPHRASEALT *v10; // rsi
  LPVOID pv; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 )
  {
    if ( !*((_BYTE *)this + 92) )
      CPhraseStatContainer::SortEntry(this);
    v6 = *(_QWORD **)this;
    v7 = 0;
    if ( v6 )
    {
      do
      {
        if ( (unsigned int)v7 >= a3 )
          break;
        v8 = v6[2];
        v9 = (_QWORD *)*v6;
        if ( v8 )
        {
          pv = 0;
          v10 = &a2[v7];
          if ( !v10 )
            return;
          *(_OWORD *)&v10->pPhrase = 0;
          *(_OWORD *)&v10->cElementsInAlternate = 0;
          *(_QWORD *)&v10->cbAltExtra = 0;
          v10->pPhrase = *(ISpPhraseBuilder **)v8;
          TraceTag((struct CDebugTag *)&g_tagSimulation, L"(%s %f)\n", *(_QWORD *)(v8 + 40), *(float *)(v8 + 48));
          ((void (__fastcall *)(ISpPhraseBuilder *, LPVOID *))v10->pPhrase->lpVtbl->GetPhrase)(v10->pPhrase, &pv);
          if ( pv )
          {
            *((_DWORD *)pv + 22) = *(_DWORD *)(v8 + 48);
            ((void (__fastcall *)(ISpPhraseBuilder *, LPVOID))v10->pPhrase->lpVtbl->InitFromPhrase)(v10->pPhrase, pv);
            CoTaskMemFree(pv);
          }
          *(_QWORD *)v8 = 0;
          v7 = (unsigned int)(v7 + 1);
        }
        v6 = v9;
      }
      while ( v9 );
    }
  }
}

```

## disassembly

```asm
0x180086468  test    rdx, rdx
0x18008646b  jz      locret_180086570
0x180086471  push    rbx
0x180086472  push    rbp
0x180086473  push    rsi
0x180086474  push    rdi
0x180086475  push    r14
0x180086477  push    r15
0x180086479  sub     rsp, 28h
0x18008647d  cmp     byte ptr [rcx+5Ch], 0
0x180086481  mov     r15d, r8d
0x180086484  mov     r14, rdx
0x180086487  mov     rbx, rcx
0x18008648a  jnz     short loc_180086491
0x18008648c  call    ?SortEntry@CPhraseStatContainer@@AEAAXXZ; CPhraseStatContainer::SortEntry(void)
0x180086491  mov     rax, [rbx]
0x180086494  xor     ebx, ebx
0x180086496  test    rax, rax
0x180086499  jz      loc_180086564
0x18008649f  cmp     ebx, r15d
0x1800864a2  jnb     loc_180086564
0x1800864a8  mov     rdi, [rax+10h]
0x1800864ac  mov     rbp, [rax]
0x1800864af  test    rdi, rdi
0x1800864b2  jz      loc_180086558
0x1800864b8  lea     rcx, [rbx+rbx*4]
0x1800864bc  mov     [rsp+58h+pv], 0
0x1800864c5  lea     rsi, [r14+rcx*8]
0x1800864c9  test    rsi, rsi
0x1800864cc  jz      loc_180086564
0x1800864d2  xorps   xmm0, xmm0
0x1800864d5  lea     rdx, aSF; "(%s %f)\n"
0x1800864dc  movups  xmmword ptr [rsi], xmm0
0x1800864df  xor     eax, eax
0x1800864e1  lea     rcx, ?g_tagSimulation@@3VCDebugTag@@A; struct CDebugTag *
0x1800864e8  movups  xmmword ptr [rsi+10h], xmm0
0x1800864ec  mov     [rsi+20h], rax
0x1800864f0  mov     rax, [rdi]
0x1800864f3  mov     [rsi], rax
0x1800864f6  movss   xmm3, dword ptr [rdi+30h]
0x1800864fb  mov     r8, [rdi+28h]
0x1800864ff  cvtps2pd xmm3, xmm3
0x180086502  movq    r9, xmm3
0x180086507  call    ?TraceTag@@YAXPEAVCDebugTag@@PEBGZZ; TraceTag(CDebugTag *,ushort const *,...)
0x18008650c  mov     rcx, [rsi]
0x18008650f  lea     rdx, [rsp+58h+pv]
0x180086514  mov     rax, [rcx]
0x180086517  mov     rax, [rax+18h]
0x18008651b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086520  mov     rcx, [rsp+58h+pv]
0x180086525  test    rcx, rcx
0x180086528  jz      short loc_18008654F
0x18008652a  mov     eax, [rdi+30h]
0x18008652d  mov     [rcx+58h], eax
0x180086530  mov     rcx, [rsi]
0x180086533  mov     rdx, [rsp+58h+pv]
0x180086538  mov     rax, [rcx]
0x18008653b  mov     rax, [rax+38h]
0x18008653f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086544  mov     rcx, [rsp+58h+pv]; pv
0x180086549  call    cs:__imp_CoTaskMemFree
0x18008654f  mov     qword ptr [rdi], 0
0x180086556  inc     ebx
0x180086558  mov     rax, rbp
0x18008655b  test    rbp, rbp
0x18008655e  jnz     loc_18008649F
0x180086564  add     rsp, 28h
0x180086568  pop     r15
0x18008656a  pop     r14
0x18008656c  pop     rdi
0x18008656d  pop     rsi
0x18008656e  pop     rbp
0x18008656f  pop     rbx
0x180086570  retn
```
