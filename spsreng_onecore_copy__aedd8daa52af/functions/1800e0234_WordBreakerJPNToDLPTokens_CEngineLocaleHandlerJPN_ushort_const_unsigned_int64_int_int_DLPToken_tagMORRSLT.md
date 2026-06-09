# WordBreakerJPNToDLPTokens(CEngineLocaleHandlerJPN *,ushort const *,unsigned __int64,int *,int *,DLPToken * *,tagMORRSLT * *)

- ea: `0x1800e0234`
- end: `0x1800e045a`
- name: `?WordBreakerJPNToDLPTokens@@YAJPEAVCEngineLocaleHandlerJPN@@PEBG_KPEAH3PEAPEAVDLPToken@@PEAPEAUtagMORRSLT@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(struct CEngineLocaleHandlerJPN *, const unsigned __int16 *, unsigned __int64, int *, int *, struct DLPToken **, struct tagMORRSLT **)`
- caller_count: `2`
- callee_count: `21`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800dff68`
- `0x1800e0460`

## callees

- `0x180002470`
- `0x1800035b0`
- `0x1800dbfb4`
- `0x1800ddd08`
- `0x1800dde30`
- `0x1800de1b0`
- `0x1800de5a0`
- `0x1800de6f0`
- `0x1800de870`
- `0x1800de9f0`
- `0x1800deba0`
- `0x1800ded40`
- `0x1800deef0`
- `0x1800df090`
- `0x1800df430`
- `0x1800df730`
- `0x1800df780`
- `0x1800dfad0`
- `0x1800e0234`
- `0x1800e0658`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e03d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e03d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WordBreakerJPNToDLPTokens(
        struct CEngineLocaleHandlerJPN *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        int *a4,
        int *a5,
        struct DLPToken **a6,
        struct tagMORRSLT **a7)
{
  unsigned int v8; // edi
  int ReverseConverter; // ebx
  void *v13; // rdx
  unsigned __int64 v14; // rsi
  unsigned __int64 v15; // rax
  bool v16; // cf
  unsigned __int64 v17; // rax
  char *v18; // rax
  DLPToken *v19; // rdi
  int v20; // edi
  int v21; // eax
  int v22; // edi
  int v23; // [rsp+40h] [rbp-38h] BYREF
  int v24; // [rsp+44h] [rbp-34h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-30h] BYREF
  DLPToken *v26; // [rsp+50h] [rbp-28h] BYREF
  struct CReverseConverter *v27[4]; // [rsp+58h] [rbp-20h] BYREF
  int v28; // [rsp+C0h] [rbp+48h] BYREF

  v8 = a3;
  if ( (int)a3 != a3 )
    return 2147942414LL;
  v27[0] = 0;
  pv = 0;
  v26 = 0;
  v23 = 0;
  v24 = 0;
  v28 = 0;
  ReverseConverter = CEngineLocaleHandlerJPN::GetReverseConverter(a1, v27);
  if ( ReverseConverter < 0 )
  {
    v13 = pv;
    goto LABEL_26;
  }
  ReverseConverter = (*(__int64 (__fastcall **)(struct CReverseConverter *, const unsigned __int16 *, _QWORD, LPVOID *))(*(_QWORD *)v27[0] + 40LL))(
                       v27[0],
                       a2,
                       v8,
                       &pv);
  v13 = pv;
  if ( ReverseConverter || !pv )
  {
    ReverseConverter = -2147467259;
    goto LABEL_26;
  }
  v28 = *((_DWORD *)pv + 16);
  v14 = v28;
  v27[0] = (struct CReverseConverter *)v28;
  v15 = v28 * (unsigned __int64)(unsigned int)(ReverseConverter + 48);
  if ( !is_mul_ok(v28, (unsigned int)(ReverseConverter + 48)) )
    v15 = -1;
  v16 = __CFADD__(v15, 8);
  v17 = v15 + 8;
  if ( v16 )
    v17 = -1;
  v18 = (char *)CWinHeap::Alloc((CWinHeap *)&g_heap, v17, 0);
  v27[1] = (struct CReverseConverter *)v18;
  if ( v18 )
  {
    *(_QWORD *)v18 = v14;
    v19 = (DLPToken *)(v18 + 8);
    `eh vector constructor iterator'(
      v18 + 8,
      (unsigned int)(ReverseConverter + 48),
      v14,
      (void (*)(void *))DLPToken::DLPToken,
      CSPHash<unsigned long,unsigned long>::DestroyKey);
  }
  else
  {
    v19 = 0;
  }
  v26 = v19;
  v13 = pv;
  if ( !v19 )
  {
    ReverseConverter = -2147024882;
LABEL_26:
    if ( v13 )
    {
      CoTaskMemFree(v13);
      v13 = 0;
      pv = 0;
    }
    if ( v26 )
    {
      v22 = 0;
      if ( v28 > 0 )
      {
        do
          DLPToken::clean((DLPToken *)((char *)v26 + 48 * v22++));
        while ( v22 < v28 );
        v13 = pv;
      }
      if ( v26 )
      {
        DLPToken::`vector deleting destructor'(v26, (unsigned int)v13);
        v13 = pv;
      }
      v26 = 0;
    }
    goto LABEL_35;
  }
  if ( v23 < *((_DWORD *)pv + 16) )
  {
    while ( ReverseConverter >= 0 )
    {
      v20 = 0;
      while ( 1 )
      {
        v21 = ((__int64 (__fastcall *)(struct CEngineLocaleHandlerJPN *, void *, int *, DLPToken **, int *, int *))(&IMEPatchTbl)[v20])(
                a1,
                v13,
                &v23,
                &v26,
                &v24,
                &v28);
        ReverseConverter = v21;
        if ( v21 < 1 )
          break;
        if ( !(&IMEPatchTbl)[++v20] )
          break;
        v13 = pv;
      }
      v13 = pv;
      if ( v23 >= *((_DWORD *)pv + 16) )
      {
        if ( v21 < 0 )
          goto LABEL_26;
        goto LABEL_35;
      }
    }
    goto LABEL_26;
  }
LABEL_35:
  *a4 = v28;
  *a5 = v24;
  *a6 = v26;
  *a7 = (struct tagMORRSLT *)v13;
  return (unsigned int)ReverseConverter;
}

```

## disassembly

```asm
0x1800e0234  push    rbp
0x1800e0236  push    rbx
0x1800e0237  push    rsi
0x1800e0238  push    rdi
0x1800e0239  push    r14
0x1800e023b  push    r15
0x1800e023d  mov     rbp, rsp
0x1800e0240  sub     rsp, 78h
0x1800e0244  mov     r15, r9
0x1800e0247  mov     rdi, r8
0x1800e024a  mov     rsi, rdx
0x1800e024d  mov     r14, rcx
0x1800e0250  movsxd  rax, r8d
0x1800e0253  cmp     rax, r8
0x1800e0256  jz      short loc_1800E0262
0x1800e0258  mov     eax, 8007000Eh
0x1800e025d  jmp     loc_1800E044D
0x1800e0262  mov     [rbp+var_20], 0
0x1800e026a  mov     [rbp+pv], 0
0x1800e0272  mov     [rbp+var_28], 0
0x1800e027a  mov     [rbp+var_38], 0
0x1800e0281  mov     [rbp+var_34], 0
0x1800e0288  mov     [rbp+arg_10], 0
0x1800e028f  lea     rdx, [rbp+var_20]; struct CReverseConverter **
0x1800e0293  call    ?GetReverseConverter@CEngineLocaleHandlerJPN@@QEAAJPEAPEAVCReverseConverter@@@Z; CEngineLocaleHandlerJPN::GetReverseConverter(CReverseConverter * *)
0x1800e0298  mov     ebx, eax
0x1800e029a  test    eax, eax
0x1800e029c  js      loc_1800E03CB
0x1800e02a2  mov     rcx, [rbp+var_20]
0x1800e02a6  mov     rax, [rcx]
0x1800e02a9  lea     r9, [rbp+pv]
0x1800e02ad  mov     r8d, edi
0x1800e02b0  mov     rdx, rsi
0x1800e02b3  mov     rax, [rax+28h]
0x1800e02b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e02bc  mov     ebx, eax
0x1800e02be  mov     rdx, [rbp+pv]
0x1800e02c2  test    eax, eax
0x1800e02c4  jnz     loc_1800E03C4
0x1800e02ca  test    rdx, rdx
0x1800e02cd  jz      loc_1800E03C4
0x1800e02d3  movsxd  rax, dword ptr [rdx+40h]
0x1800e02d7  mov     [rbp+arg_10], eax
0x1800e02da  mov     rsi, rax
0x1800e02dd  mov     [rbp+var_20], rax
0x1800e02e1  lea     eax, [rbx+30h]
0x1800e02e4  mul     rsi
0x1800e02e7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800e02ee  cmovb   rax, rcx
0x1800e02f2  add     rax, 8
0x1800e02f6  cmovb   rax, rcx
0x1800e02fa  xor     r8d, r8d; bool
0x1800e02fd  mov     rdx, rax; unsigned __int64
0x1800e0300  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800e0307  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800e030c  mov     [rbp+var_18], rax
0x1800e0310  test    rax, rax
0x1800e0313  jz      short loc_1800E033F
0x1800e0315  mov     [rax], rsi
0x1800e0318  lea     rdi, [rax+8]
0x1800e031c  lea     rax, ?DestroyKey@?$CSPHash@KK@@MEBAXK@Z; CSPHash<ulong,ulong>::DestroyKey(ulong)
0x1800e0323  mov     [rsp+78h+var_58], rax; void (*)(void *)
0x1800e0328  lea     r9, ??0DLPToken@@QEAA@XZ; void (*)(void *)
0x1800e032f  mov     r8, rsi; unsigned __int64
0x1800e0332  lea     edx, [rbx+30h]; unsigned __int64
0x1800e0335  mov     rcx, rdi; void *
0x1800e0338  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800e033d  jmp     short loc_1800E0341
0x1800e033f  xor     edi, edi
0x1800e0341  mov     [rbp+var_28], rdi
0x1800e0345  mov     rdx, [rbp+pv]; struct tagMORRSLT *
0x1800e0349  test    rdi, rdi
0x1800e034c  jz      short loc_1800E03BD
0x1800e034e  mov     eax, [rdx+40h]
0x1800e0351  cmp     [rbp+var_38], eax
0x1800e0354  jge     loc_1800E042A
0x1800e035a  lea     rsi, ?IMEPatchTbl@@3PAP6AJPEAVCEngineLocaleHandlerJPN@@PEAUtagMORRSLT@@PEAHPEAPEAVDLPToken@@22@ZA; long (*near * IMEPatchTbl)(CEngineLocaleHandlerJPN *,tagMORRSLT *,int *,DLPToken * *,int *,int *)
0x1800e0361  test    ebx, ebx
0x1800e0363  js      short loc_1800E03CF
0x1800e0365  xor     edi, edi
0x1800e0367  movsxd  rax, edi
0x1800e036a  lea     rcx, [rbp+arg_10]
0x1800e036e  mov     [rsp+78h+var_50], rcx; int *
0x1800e0373  lea     rcx, [rbp+var_34]
0x1800e0377  mov     [rsp+78h+var_58], rcx; int *
0x1800e037c  lea     r9, [rbp+var_28]; struct DLPToken **
0x1800e0380  lea     r8, [rbp+var_38]; int *
0x1800e0384  mov     rcx, r14; struct CEngineLocaleHandlerJPN *
0x1800e0387  mov     rax, ds:(?IMEPatchTbl@@3PAP6AJPEAVCEngineLocaleHandlerJPN@@PEAUtagMORRSLT@@PEAHPEAPEAVDLPToken@@22@ZA - 180108510h)[rsi+rax*8]; long (*near * IMEPatchTbl)(CEngineLocaleHandlerJPN *,tagMORRSLT *,int *,DLPToken * *,int *,int *)
0x1800e038b  call    _guard_dispatch_icall$thunk$10345483385596137414; IMEPatchArabicNum(CEngineLocaleHandlerJPN *,tagMORRSLT *,int *,DLPToken * *,int *,int *)
0x1800e0390  mov     ebx, eax
0x1800e0392  mov     ecx, eax
0x1800e0394  cmp     eax, 1
0x1800e0397  jl      short loc_1800E03AB
0x1800e0399  inc     edi
0x1800e039b  movsxd  rax, edi
0x1800e039e  cmp     qword ptr [rsi+rax*8], 0
0x1800e03a3  jz      short loc_1800E03AB
0x1800e03a5  mov     rdx, [rbp+pv]
0x1800e03a9  jmp     short loc_1800E0367
0x1800e03ab  mov     rdx, [rbp+pv]
0x1800e03af  mov     eax, [rdx+40h]
0x1800e03b2  cmp     [rbp+var_38], eax
0x1800e03b5  jl      short loc_1800E0361
0x1800e03b7  test    ecx, ecx
0x1800e03b9  js      short loc_1800E03CF
0x1800e03bb  jmp     short loc_1800E042A
0x1800e03bd  mov     ebx, 8007000Eh
0x1800e03c2  jmp     short loc_1800E03CF
0x1800e03c4  mov     ebx, 80004005h
0x1800e03c9  jmp     short loc_1800E03CF
0x1800e03cb  mov     rdx, [rbp+pv]
0x1800e03cf  test    rdx, rdx
0x1800e03d2  jz      short loc_1800E03E3
0x1800e03d4  mov     rcx, rdx; pv
0x1800e03d7  call    cs:__imp_CoTaskMemFree
0x1800e03dd  xor     edx, edx
0x1800e03df  mov     [rbp+pv], rdx
0x1800e03e3  cmp     [rbp+var_28], 0
0x1800e03e8  jz      short loc_1800E042A
0x1800e03ea  xor     edi, edi
0x1800e03ec  cmp     [rbp+arg_10], edi
0x1800e03ef  jle     short loc_1800E0410
0x1800e03f1  movsxd  rax, edi
0x1800e03f4  lea     rcx, [rax+rax*2]
0x1800e03f8  shl     rcx, 4
0x1800e03fc  add     rcx, [rbp+var_28]; this
0x1800e0400  call    ?clean@DLPToken@@QEAAXXZ; DLPToken::clean(void)
0x1800e0405  inc     edi
0x1800e0407  cmp     edi, [rbp+arg_10]
0x1800e040a  jl      short loc_1800E03F1
0x1800e040c  mov     rdx, [rbp+pv]; unsigned int
0x1800e0410  mov     rcx, [rbp+var_28]; this
0x1800e0414  test    rcx, rcx
0x1800e0417  jz      short loc_1800E0422
0x1800e0419  call    ??_EDLPToken@@QEAAPEAXI@Z; DLPToken::`vector deleting destructor'(uint)
0x1800e041e  mov     rdx, [rbp+pv]
0x1800e0422  mov     [rbp+var_28], 0
0x1800e042a  mov     eax, [rbp+arg_10]
0x1800e042d  mov     [r15], eax
0x1800e0430  mov     rcx, [rbp+arg_20]
0x1800e0434  mov     eax, [rbp+var_34]
0x1800e0437  mov     [rcx], eax
0x1800e0439  mov     rcx, [rbp+arg_28]
0x1800e043d  mov     rax, [rbp+var_28]
0x1800e0441  mov     [rcx], rax
0x1800e0444  mov     rax, [rbp+arg_30]
0x1800e0448  mov     [rax], rdx
0x1800e044b  mov     eax, ebx
0x1800e044d  add     rsp, 78h
0x1800e0451  pop     r15
0x1800e0453  pop     r14
0x1800e0455  pop     rdi
0x1800e0456  pop     rsi
0x1800e0457  pop     rbx
0x1800e0458  pop     rbp
0x1800e0459  retn
```
