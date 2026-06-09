# CLTSLexicon::LTSGetLookupLexiconProns(ushort const *,ushort,LTS_OUTPUT *)

- ea: `0x1800cbc50`
- end: `0x1800cbd5b`
- name: `?LTSGetLookupLexiconProns@CLTSLexicon@@IEBAJPEBGGPEAULTS_OUTPUT@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(CLTSLexicon *__hidden this, const unsigned __int16 *, unsigned __int16, struct LTS_OUTPUT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800cc038`

## callees

- `0x180002470`
- `0x1800034d4`
- `0x1800141c0`
- `0x1800cab88`
- `0x1800cbc50`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cbd37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cbd37`

## pseudocode

```c
__int64 __fastcall CLTSLexicon::LTSGetLookupLexiconProns(
        CLTSLexicon *this,
        const unsigned __int16 *a2,
        unsigned __int16 a3,
        struct LTS_OUTPUT *a4)
{
  struct SPWORDPRONUNCIATIONLIST *v8; // rax
  struct SPWORDPRONUNCIATIONLIST *v9; // rbx
  int v10; // esi
  unsigned int v11; // edi
  unsigned int v12; // ebp
  SPWORDPRONUNCIATION *pFirstWordPronunciation; // r14
  __int64 v14; // r12

  if ( !*((_QWORD *)this + 15) )
  {
    v9 = 0;
LABEL_13:
    v10 = -2147200999;
    goto LABEL_14;
  }
  v8 = (struct SPWORDPRONUNCIATIONLIST *)CWinHeap::Alloc((CWinHeap *)&g_heap, 0x18u, 0);
  v9 = v8;
  if ( !v8 )
    goto LABEL_13;
  *(_OWORD *)&v8->ulSize = 0;
  v8->pFirstWordPronunciation = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, __int64, struct SPWORDPRONUNCIATIONLIST *))(**((_QWORD **)this + 15) + 24LL))(
          *((_QWORD *)this + 15),
          a2,
          a3,
          4096,
          v8);
  if ( v10 < 0 )
    goto LABEL_13;
  v11 = SpWordPronCountInList(v9);
  if ( !v11 )
  {
LABEL_10:
    if ( v11 )
      goto LABEL_14;
    goto LABEL_13;
  }
  if ( v11 > 0x10 )
    v11 = 16;
  v12 = 0;
  *(_DWORD *)a4 = v11;
  pFirstWordPronunciation = v9->pFirstWordPronunciation;
  while ( 1 )
  {
    v14 = 516LL * v12;
    v10 = StringCchCopyW((unsigned __int16 *)((char *)a4 + v14 + 8), 0x100u, pFirstWordPronunciation->szPronunciation);
    if ( v10 < 0 )
      break;
    ++v12;
    *(_DWORD *)((char *)a4 + v14 + 4) = 1065353216;
    pFirstWordPronunciation = pFirstWordPronunciation->pNextWordPronunciation;
    if ( v12 >= v11 )
      goto LABEL_10;
  }
LABEL_14:
  if ( v9 )
  {
    CoTaskMemFree(v9->pvBuffer);
    operator delete(v9, 0x18u);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800cbc50  push    rbx
0x1800cbc52  push    rbp
0x1800cbc53  push    rsi
0x1800cbc54  push    rdi
0x1800cbc55  push    r12
0x1800cbc57  push    r14
0x1800cbc59  push    r15
0x1800cbc5b  sub     rsp, 30h
0x1800cbc5f  cmp     qword ptr [rcx+78h], 0
0x1800cbc64  mov     r15, r9
0x1800cbc67  movzx   esi, r8w
0x1800cbc6b  mov     rbp, rdx
0x1800cbc6e  mov     rdi, rcx
0x1800cbc71  jz      loc_1800CBD27
0x1800cbc77  xor     r8d, r8d; bool
0x1800cbc7a  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800cbc81  lea     edx, [r8+18h]; unsigned __int64
0x1800cbc85  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800cbc8a  mov     rbx, rax
0x1800cbc8d  test    rax, rax
0x1800cbc90  jz      loc_1800CBD29
0x1800cbc96  xor     eax, eax
0x1800cbc98  mov     [rsp+68h+var_48], rbx
0x1800cbc9d  xorps   xmm0, xmm0
0x1800cbca0  mov     r9d, 1000h
0x1800cbca6  movups  xmmword ptr [rbx], xmm0
0x1800cbca9  mov     [rbx+10h], rax
0x1800cbcad  movzx   r8d, si
0x1800cbcb1  mov     rcx, [rdi+78h]
0x1800cbcb5  mov     rdx, [rcx]
0x1800cbcb8  mov     rax, [rdx+18h]
0x1800cbcbc  mov     rdx, rbp
0x1800cbcbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbcc4  mov     esi, eax
0x1800cbcc6  test    eax, eax
0x1800cbcc8  js      short loc_1800CBD29
0x1800cbcca  mov     rcx, rbx; struct SPWORDPRONUNCIATIONLIST *
0x1800cbccd  call    ?SpWordPronCountInList@@YAKPEAUSPWORDPRONUNCIATIONLIST@@@Z; SpWordPronCountInList(SPWORDPRONUNCIATIONLIST *)
0x1800cbcd2  mov     edi, eax
0x1800cbcd4  test    eax, eax
0x1800cbcd6  jz      short loc_1800CBD21
0x1800cbcd8  mov     eax, 10h
0x1800cbcdd  cmp     edi, eax
0x1800cbcdf  cmova   edi, eax
0x1800cbce2  xor     ebp, ebp
0x1800cbce4  mov     [r15], edi
0x1800cbce7  mov     r14, [rbx+10h]
0x1800cbceb  mov     eax, ebp
0x1800cbced  lea     rcx, [r15+8]
0x1800cbcf1  imul    r12, rax, 204h
0x1800cbcf8  lea     r8, [r14+14h]; unsigned __int16 *
0x1800cbcfc  mov     edx, 100h; unsigned __int64
0x1800cbd01  add     rcx, r12; unsigned __int16 *
0x1800cbd04  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800cbd09  mov     esi, eax
0x1800cbd0b  test    eax, eax
0x1800cbd0d  js      short loc_1800CBD2E
0x1800cbd0f  inc     ebp
0x1800cbd11  mov     dword ptr [r12+r15+4], 3F800000h
0x1800cbd1a  mov     r14, [r14]
0x1800cbd1d  cmp     ebp, edi
0x1800cbd1f  jb      short loc_1800CBCEB
0x1800cbd21  test    edi, edi
0x1800cbd23  jnz     short loc_1800CBD2E
0x1800cbd25  jmp     short loc_1800CBD29
0x1800cbd27  xor     ebx, ebx
0x1800cbd29  mov     esi, 80045019h
0x1800cbd2e  test    rbx, rbx
0x1800cbd31  jz      short loc_1800CBD4A
0x1800cbd33  mov     rcx, [rbx+8]; pv
0x1800cbd37  call    cs:__imp_CoTaskMemFree
0x1800cbd3d  mov     edx, 18h; unsigned __int64
0x1800cbd42  mov     rcx, rbx; void *
0x1800cbd45  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbd4a  mov     eax, esi
0x1800cbd4c  add     rsp, 30h
0x1800cbd50  pop     r15
0x1800cbd52  pop     r14
0x1800cbd54  pop     r12
0x1800cbd56  pop     rdi
0x1800cbd57  pop     rsi
0x1800cbd58  pop     rbp
0x1800cbd59  pop     rbx
0x1800cbd5a  retn
```
