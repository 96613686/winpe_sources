# CCryptoHelperT<CEmptyType>::GetSmartCardReaderStates(unsigned __int64,_tag_TOKEN_SCARD_READERSTATE * *,ulong *)

- ea: `0x180038090`
- end: `0x1800383df`
- name: `?GetSmartCardReaderStates@?$CCryptoHelperT@VCEmptyType@@@@SAJ_KPEAPEAU_tag_TOKEN_SCARD_READERSTATE@@PEAK@Z`
- size: `847`
- prototype: `__int64 __fastcall(SCARDCONTEXT hContext)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180037c68`

## callees

- `0x180003520`
- `0x180004288`
- `0x180036ec4`
- `0x180036ed8`
- `0x1800376c0`
- `0x180038090`
- `0x180039cc0`
- `0x18003c52a`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038147`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003819a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800382c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038377`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800383ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038147`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003819a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800382c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038377`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800383ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800382d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003838b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800383bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800382d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003838b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800383bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003815b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800381ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003815b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800381ae`
- `WinSCard!SCardGetStatusChangeW` at `0x18003823e`
- `WinSCard!SCardGetStatusChangeW` at `0x18003823e`
- `WinSCard!SCardFreeMemory` at `0x180038352`
- `WinSCard!SCardFreeMemory` at `0x180038352`
- `WinSCard!SCardListReadersW` at `0x1800380e3`
- `WinSCard!SCardListReadersW` at `0x1800380e3`

## pseudocode

```c
__int64 __fastcall CCryptoHelperT<CEmptyType>::GetSmartCardReaderStates(SCARDCONTEXT hContext, _QWORD *a2, _DWORD *a3)
{
  signed int v3; // r12d
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v5; // rbx
  SCARDCONTEXT v6; // r13
  LONG v7; // eax
  unsigned int v8; // esi
  __int64 v9; // rcx
  __int64 v10; // r15
  unsigned __int64 v11; // rsi
  SIZE_T v12; // rbx
  HANDLE ProcessHeap; // rax
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v14; // rax
  __int64 v15; // rdi
  bool v16; // cf
  SIZE_T v17; // rdi
  HANDLE v18; // rax
  _QWORD *v19; // rax
  char *v20; // r14
  _tag_TOKEN_SCARD_READERSTATE *v21; // r12
  __int64 v22; // rdi
  _QWORD *v23; // rdi
  unsigned int i; // edx
  const WCHAR *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // r13
  __int64 v28; // rcx
  __int128 v29; // xmm1
  __int128 v30; // xmm2
  __int128 v31; // xmm3
  char *v32; // rdx
  __int64 v33; // rax
  void *v34; // rdi
  HANDLE v35; // rax
  HANDLE v36; // rax
  void *v37; // rbx
  HANDLE v38; // rax
  WCHAR mszReaders[4]; // [rsp+28h] [rbp-30h] BYREF
  char *v41; // [rsp+30h] [rbp-28h] BYREF
  DWORD cReaders[2]; // [rsp+38h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-18h]
  DWORD pcchReaders; // [rsp+B8h] [rbp+60h] BYREF

  v3 = 0;
  pcchReaders = -1;
  *(_QWORD *)cReaders = 0;
  lpMem = 0;
  v41 = 0;
  v5 = 0;
  *(_QWORD *)mszReaders = 0;
  v6 = hContext;
  v7 = SCardListReadersW(hContext, 0, mszReaders, &pcchReaders);
  v8 = v7;
  if ( v7 == -2146435026 )
  {
    *a3 = 0;
    v8 = 0;
    goto LABEL_34;
  }
  if ( v7 < 0
    || (v7 = CRegType<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>::Create(*(void **)mszReaders),
        v8 = v7,
        v7 < 0) )
  {
    v9 = (unsigned int)v7;
LABEL_33:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
    goto LABEL_34;
  }
  v10 = cReaders[1];
  v11 = cReaders[1];
  v12 = (unsigned __int64)cReaders[1] << 6;
  if ( !is_mul_ok(cReaders[1], 0x40u) )
    v12 = -1;
  ProcessHeap = GetProcessHeap();
  v14 = (struct $B80B7D01E79FADDB4AAC58DE22BC823F *)HeapAlloc(ProcessHeap, 0, v12);
  v5 = v14;
  if ( !v14 )
    goto LABEL_32;
  memset_0(v14, 0, (unsigned __int64)(unsigned int)v10 << 6);
  v15 = 72 * v11;
  if ( !is_mul_ok(v11, 0x48u) )
    v15 = -1;
  v16 = __CFADD__(v15, 8);
  v17 = v15 + 8;
  if ( v16 )
    v17 = -1;
  v18 = GetProcessHeap();
  v19 = HeapAlloc(v18, 0, v17);
  if ( v19 )
  {
    *v19 = v10;
    v20 = (char *)(v19 + 1);
    v21 = (_tag_TOKEN_SCARD_READERSTATE *)(v19 + 1);
    v22 = (unsigned int)v10;
    if ( (_DWORD)v10 )
    {
      do
      {
        _tag_TOKEN_SCARD_READERSTATE::_tag_TOKEN_SCARD_READERSTATE(v21);
        v21 = (_tag_TOKEN_SCARD_READERSTATE *)((char *)v21 + 72);
        --v22;
      }
      while ( v22 );
    }
    v3 = 0;
  }
  else
  {
    v20 = 0;
  }
  v41 = v20;
  if ( !v20 )
  {
LABEL_32:
    v9 = 2147942414LL;
    v8 = -2147024882;
    goto LABEL_33;
  }
  memset_0(v20, 0, 72 * v10);
  v23 = lpMem;
  for ( i = 0; i < (unsigned int)v10; *(DWORD *)((char *)&v5->dwCurrentState + v26) = 0 )
  {
    v25 = (const WCHAR *)v23[i];
    v26 = i++;
    v26 <<= 6;
    *(LPCWSTR *)((char *)&v5->szReader + v26) = v25;
  }
  v8 = SCardGetStatusChangeW(v6, 0, v5, v10);
  if ( v8 )
  {
    if ( (int)v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v9 = v8;
    goto LABEL_33;
  }
  v8 = 0;
  if ( (_DWORD)v10 )
  {
    v27 = 0;
    do
    {
      v28 = 9 * v27;
      v29 = *(_OWORD *)&v5[v27].dwCurrentState;
      v30 = *(_OWORD *)&v5[v27].rgbAtr[4];
      v31 = *(_OWORD *)&v5[v27].rgbAtr[20];
      *(_OWORD *)&v20[8 * v28] = *(_OWORD *)&v5[v27].szReader;
      *(_OWORD *)&v20[8 * v28 + 16] = v29;
      *(_OWORD *)&v20[8 * v28 + 32] = v30;
      *(_OWORD *)&v20[8 * v28 + 48] = v31;
      v32 = (char *)v23[v3];
      v23[v3] = 0;
      v33 = *(_QWORD *)&v20[72 * v27 + 64];
      v41 = v32;
      if ( v33 )
      {
        v34 = (void *)(v33 - 4);
        v35 = GetProcessHeap();
        HeapFree(v35, 0, v34);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v23 = lpMem;
        v32 = v41;
        v28 = 9 * v27;
      }
      ++v3;
      *(_QWORD *)&v20[8 * v28 + 64] = v32;
      ++v27;
    }
    while ( v3 < (unsigned int)v10 );
    v6 = hContext;
  }
  v41 = 0;
  *a3 = v10;
  *a2 = v20;
LABEL_34:
  if ( *(_QWORD *)mszReaders )
  {
    SCardFreeMemory(v6, *(LPCVOID *)mszReaders);
    *(_QWORD *)mszReaders = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  SP<_tag_TOKEN_SCARD_READERSTATE,SP_CPP_ARRAY<_tag_TOKEN_SCARD_READERSTATE>>::~SP<_tag_TOKEN_SCARD_READERSTATE,SP_CPP_ARRAY<_tag_TOKEN_SCARD_READERSTATE>>(&v41);
  if ( v5 )
  {
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v5);
  }
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(cReaders, 0);
  v37 = lpMem;
  if ( lpMem )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v37);
  }
  return v8;
}

```

## disassembly

```asm
0x180038090  mov     [rsp-40h+arg_10], r8
0x180038095  mov     [rsp-40h+arg_8], rdx
0x18003809a  mov     [rsp-40h+arg_0], rcx
0x18003809f  push    rbp
0x1800380a0  push    rbx
0x1800380a1  push    rsi
0x1800380a2  push    rdi
0x1800380a3  push    r12
0x1800380a5  push    r13
0x1800380a7  push    r14
0x1800380a9  push    r15
0x1800380ab  mov     rbp, rsp
0x1800380ae  sub     rsp, 58h
0x1800380b2  xor     r12d, r12d
0x1800380b5  mov     [rbp+pcchReaders], 0FFFFFFFFh
0x1800380bc  mov     rdi, r8
0x1800380bf  mov     qword ptr [rbp+cReaders], r12
0x1800380c3  lea     r8, [rbp+mszReaders]; mszReaders
0x1800380c7  mov     [rbp+lpMem], r12
0x1800380cb  lea     r9, [rbp+pcchReaders]; pcchReaders
0x1800380cf  mov     [rbp+var_38], r12d
0x1800380d3  xor     edx, edx; mszGroups
0x1800380d5  mov     [rbp+var_28], r12
0x1800380d9  mov     ebx, r12d
0x1800380dc  mov     qword ptr [rbp+mszReaders], r12
0x1800380e0  mov     r13, rcx
0x1800380e3  call    cs:__imp_SCardListReadersW
0x1800380ea  nop     dword ptr [rax+rax+00h]
0x1800380ef  mov     esi, eax
0x1800380f1  cmp     eax, 8010002Eh
0x1800380f6  jnz     short loc_180038103
0x1800380f8  mov     [rdi], r12d
0x1800380fb  mov     esi, r12d
0x1800380fe  jmp     loc_180038346
0x180038103  test    eax, eax
0x180038105  jns     short loc_18003810E
0x180038107  mov     ecx, eax
0x180038109  jmp     loc_180038341
0x18003810e  mov     edx, [rbp+pcchReaders]
0x180038111  lea     r9, [rbp+var_38]
0x180038115  mov     rcx, qword ptr [rbp+mszReaders]; Src
0x180038119  lea     r8, [rbp+cReaders]
0x18003811d  add     edx, edx
0x18003811f  call    ?Create@?$CRegType@V?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@@@SAJPEBXKPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@PEAH@Z; CRegType<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>::Create(void const *,ulong,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,int *)
0x180038124  mov     esi, eax
0x180038126  test    eax, eax
0x180038128  js      short loc_180038107
0x18003812a  mov     r15d, [rbp+cReaders+4]
0x18003812e  mov     eax, 40h ; '@'
0x180038133  mul     r15
0x180038136  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18003813d  mov     esi, r15d
0x180038140  mov     rbx, rax
0x180038143  cmovb   rbx, r14
0x180038147  call    cs:__imp_GetProcessHeap
0x18003814e  nop     dword ptr [rax+rax+00h]
0x180038153  mov     r8, rbx; dwBytes
0x180038156  xor     edx, edx; dwFlags
0x180038158  mov     rcx, rax; hHeap
0x18003815b  call    cs:__imp_HeapAlloc
0x180038162  nop     dword ptr [rax+rax+00h]
0x180038167  mov     rbx, rax
0x18003816a  test    rax, rax
0x18003816d  jz      loc_18003833A
0x180038173  mov     r8d, r15d
0x180038176  xor     edx, edx; Val
0x180038178  shl     r8, 6; Size
0x18003817c  mov     rcx, rax; void *
0x18003817f  call    memset_0
0x180038184  lea     eax, [r14+49h]
0x180038188  mul     rsi
0x18003818b  mov     rdi, rax
0x18003818e  cmovb   rdi, r14
0x180038192  add     rdi, 8
0x180038196  cmovb   rdi, r14
0x18003819a  call    cs:__imp_GetProcessHeap
0x1800381a1  nop     dword ptr [rax+rax+00h]
0x1800381a6  mov     r8, rdi; dwBytes
0x1800381a9  xor     edx, edx; dwFlags
0x1800381ab  mov     rcx, rax; hHeap
0x1800381ae  call    cs:__imp_HeapAlloc
0x1800381b5  nop     dword ptr [rax+rax+00h]
0x1800381ba  test    rax, rax
0x1800381bd  jz      short loc_1800381E8
0x1800381bf  mov     [rax], r15
0x1800381c2  lea     r14, [rax+8]
0x1800381c6  mov     r12, r14
0x1800381c9  mov     edi, r15d
0x1800381cc  test    r15d, r15d
0x1800381cf  jz      short loc_1800381E3
0x1800381d1  mov     rcx, r12; this
0x1800381d4  call    ??0_tag_TOKEN_SCARD_READERSTATE@@QEAA@XZ; _tag_TOKEN_SCARD_READERSTATE::_tag_TOKEN_SCARD_READERSTATE(void)
0x1800381d9  add     r12, 48h ; 'H'
0x1800381dd  sub     rdi, 1
0x1800381e1  jnz     short loc_1800381D1
0x1800381e3  xor     r12d, r12d
0x1800381e6  jmp     short loc_1800381EB
0x1800381e8  mov     r14, r12
0x1800381eb  mov     [rbp+var_28], r14
0x1800381ef  test    r14, r14
0x1800381f2  jz      loc_18003833A
0x1800381f8  lea     r8, [r15+r15*8]
0x1800381fc  xor     edx, edx; Val
0x1800381fe  shl     r8, 3; Size
0x180038202  mov     rcx, r14; void *
0x180038205  call    memset_0
0x18003820a  mov     rdi, [rbp+lpMem]
0x18003820e  mov     edx, r12d
0x180038211  test    r15d, r15d
0x180038214  jz      short loc_180038233
0x180038216  movsxd  rax, edx
0x180038219  mov     rcx, [rdi+rax*8]
0x18003821d  mov     eax, edx
0x18003821f  inc     edx
0x180038221  shl     rax, 6
0x180038225  mov     [rax+rbx], rcx
0x180038229  mov     [rax+rbx+10h], r12d
0x18003822e  cmp     edx, r15d
0x180038231  jb      short loc_180038216
0x180038233  mov     r9d, r15d; cReaders
0x180038236  mov     r8, rbx; rgReaderStates
0x180038239  xor     edx, edx; dwTimeout
0x18003823b  mov     rcx, r13; hContext
0x18003823e  call    cs:__imp_SCardGetStatusChangeW
0x180038245  nop     dword ptr [rax+rax+00h]
0x18003824a  mov     esi, eax
0x18003824c  test    eax, eax
0x18003824e  jnz     loc_180038329
0x180038254  mov     esi, r12d
0x180038257  test    r15d, r15d
0x18003825a  jz      loc_180038312
0x180038260  xor     r13d, r13d
0x180038263  mov     rax, r13
0x180038266  lea     rcx, ds:0[r13*8]
0x18003826e  shl     rax, 6
0x180038272  add     rcx, r13
0x180038275  movups  xmm0, xmmword ptr [rax+rbx]
0x180038279  movups  xmm1, xmmword ptr [rax+rbx+10h]
0x18003827e  movups  xmm2, xmmword ptr [rax+rbx+20h]
0x180038283  movups  xmm3, xmmword ptr [rax+rbx+30h]
0x180038288  movsxd  rax, r12d
0x18003828b  movups  xmmword ptr [r14+rcx*8], xmm0
0x180038290  movups  xmmword ptr [r14+rcx*8+10h], xmm1
0x180038296  movups  xmmword ptr [r14+rcx*8+20h], xmm2
0x18003829c  movups  xmmword ptr [r14+rcx*8+30h], xmm3
0x1800382a2  mov     rdx, [rdi+rax*8]
0x1800382a6  mov     qword ptr [rdi+rax*8], 0
0x1800382ae  mov     rax, [r14+rcx*8+40h]
0x1800382b3  mov     [rbp+var_28], rdx
0x1800382b7  test    rax, rax
0x1800382ba  jz      short loc_1800382FA
0x1800382bc  lea     rdi, [rax-4]
0x1800382c0  call    cs:__imp_GetProcessHeap
0x1800382c7  nop     dword ptr [rax+rax+00h]
0x1800382cc  mov     r8, rdi; lpMem
0x1800382cf  xor     edx, edx; dwFlags
0x1800382d1  mov     rcx, rax; hHeap
0x1800382d4  call    cs:__imp_HeapFree
0x1800382db  nop     dword ptr [rax+rax+00h]
0x1800382e0  xor     ecx, ecx
0x1800382e2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800382e7  mov     rdi, [rbp+lpMem]
0x1800382eb  lea     rcx, ds:0[r13*8]
0x1800382f3  mov     rdx, [rbp+var_28]
0x1800382f7  add     rcx, r13
0x1800382fa  inc     r12d
0x1800382fd  mov     [r14+rcx*8+40h], rdx
0x180038302  inc     r13
0x180038305  cmp     r12d, r15d
0x180038308  jb      loc_180038263
0x18003830e  mov     r13, [rbp+arg_0]
0x180038312  mov     rax, [rbp+arg_10]
0x180038316  xor     r12d, r12d
0x180038319  mov     [rbp+var_28], r12
0x18003831d  mov     [rax], r15d
0x180038320  mov     rax, [rbp+arg_8]
0x180038324  mov     [rax], r14
0x180038327  jmp     short loc_180038346
0x180038329  test    esi, esi
0x18003832b  jle     short loc_180038336
0x18003832d  movzx   esi, si
0x180038330  or      esi, 80070000h
0x180038336  mov     ecx, esi
0x180038338  jmp     short loc_180038341
0x18003833a  mov     ecx, 8007000Eh
0x18003833f  mov     esi, ecx
0x180038341  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180038346  mov     rdx, qword ptr [rbp+mszReaders]; pvMem
0x18003834a  test    rdx, rdx
0x18003834d  jz      short loc_180038362
0x18003834f  mov     rcx, r13; hContext
0x180038352  call    cs:__imp_SCardFreeMemory
0x180038359  nop     dword ptr [rax+rax+00h]
0x18003835e  mov     qword ptr [rbp+mszReaders], r12
0x180038362  mov     ecx, esi
0x180038364  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180038369  lea     rcx, [rbp+var_28]
0x18003836d  call    ??1?$SP@U_tag_TOKEN_SCARD_READERSTATE@@V?$SP_CPP_ARRAY@U_tag_TOKEN_SCARD_READERSTATE@@@@@@QEAA@XZ; SP<_tag_TOKEN_SCARD_READERSTATE,SP_CPP_ARRAY<_tag_TOKEN_SCARD_READERSTATE>>::~SP<_tag_TOKEN_SCARD_READERSTATE,SP_CPP_ARRAY<_tag_TOKEN_SCARD_READERSTATE>>(void)
0x180038372  test    rbx, rbx
0x180038375  jz      short loc_180038397
0x180038377  call    cs:__imp_GetProcessHeap
0x18003837e  nop     dword ptr [rax+rax+00h]
0x180038383  mov     r8, rbx; lpMem
0x180038386  xor     edx, edx; dwFlags
0x180038388  mov     rcx, rax; hHeap
0x18003838b  call    cs:__imp_HeapFree
0x180038392  nop     dword ptr [rax+rax+00h]
0x180038397  xor     edx, edx
0x180038399  lea     rcx, [rbp+cReaders]
0x18003839d  call    ?SetSize@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x1800383a2  mov     rbx, [rbp+lpMem]
0x1800383a6  test    rbx, rbx
0x1800383a9  jz      short loc_1800383CB
0x1800383ab  call    cs:__imp_GetProcessHeap
0x1800383b2  nop     dword ptr [rax+rax+00h]
0x1800383b7  mov     r8, rbx; lpMem
0x1800383ba  xor     edx, edx; dwFlags
0x1800383bc  mov     rcx, rax; hHeap
0x1800383bf  call    cs:__imp_HeapFree
0x1800383c6  nop     dword ptr [rax+rax+00h]
0x1800383cb  mov     eax, esi
0x1800383cd  add     rsp, 58h
0x1800383d1  pop     r15
0x1800383d3  pop     r14
0x1800383d5  pop     r13
0x1800383d7  pop     r12
0x1800383d9  pop     rdi
0x1800383da  pop     rsi
0x1800383db  pop     rbx
0x1800383dc  pop     rbp
0x1800383dd  retn
```
