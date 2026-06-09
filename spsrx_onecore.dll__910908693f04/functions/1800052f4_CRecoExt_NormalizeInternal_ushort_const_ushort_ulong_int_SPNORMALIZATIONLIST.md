# CRecoExt::NormalizeInternal(ushort const *,ushort,ulong,int,SPNORMALIZATIONLIST *)

- ea: `0x1800052f4`
- end: `0x180005618`
- name: `?NormalizeInternal@CRecoExt@@AEAAJPEBGGKHPEAUSPNORMALIZATIONLIST@@@Z`
- size: `804`
- prototype: `int(CRecoExt *__hidden this, const unsigned __int16 *, unsigned __int16, unsigned int, int, struct SPNORMALIZATIONLIST *)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800052a0`
- `0x1800052d0`

## callees

- `0x180001c50`
- `0x1800031c8`
- `0x180003774`
- `0x180004ee0`
- `0x1800052f4`
- `0x180010010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180005365`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180005365`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800053e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800053e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000551b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000551b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000539b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800055f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000539b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800055f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecoExt::NormalizeInternal(
        CRecoExt *this,
        const unsigned __int16 *a2,
        __int16 a3,
        int a4,
        int a5,
        struct SPNORMALIZATIONLIST *a6)
{
  unsigned int v10; // r14d
  int TextNormMultiResult; // ebx
  unsigned __int64 v12; // rbx
  int v13; // esi
  void *v14; // r13
  SIZE_T v16; // r8
  __int64 v17; // rsi
  _QWORD *v18; // rax
  __int64 v19; // rcx
  int v20; // r12d
  struct ITextNormMultiResult *v21; // rdi
  struct SPNORMALIZATIONLIST *v22; // rsi
  int v23; // eax
  int v24; // ecx
  __int64 v25; // rdx
  int i; // r8d
  __int64 v27; // rax
  WCHAR **v28; // rax
  WCHAR **v29; // r14
  WCHAR *v30; // rdi
  WCHAR *v31; // rdx
  __int64 v32; // r8
  unsigned int v33; // edx
  WCHAR **ppszzNormalizedList; // r8
  __int64 v35; // rax
  unsigned __int64 v36; // rcx
  __int64 v37; // rax
  char *v38; // rcx
  unsigned int v39; // [rsp+30h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-20h] BYREF
  struct ITextNormMultiResult *v41[3]; // [rsp+40h] [rbp-18h] BYREF
  void *v42; // [rsp+A8h] [rbp+50h] BYREF

  pv = 0;
  v39 = 0;
  v41[0] = 0;
  v42 = 0;
  if ( !a2 )
    goto LABEL_11;
  if ( !*a2 )
    goto LABEL_11;
  if ( !a6 )
    goto LABEL_11;
  v10 = a4 + 1;
  if ( a4 + 1 <= 1 )
    goto LABEL_11;
  TextNormMultiResult = -2147467259;
  if ( !*((_QWORD *)this + 15) )
  {
LABEL_12:
    v14 = v42;
    goto LABEL_13;
  }
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  v13 = 0;
  if ( !v12 )
  {
LABEL_11:
    TextNormMultiResult = -2147024809;
    goto LABEL_12;
  }
  while ( (unsigned int)_o_iswspace(a2[v13]) )
  {
    if ( (unsigned int)++v13 >= v12 )
      goto LABEL_11;
  }
  v16 = 2 * v12 + 22;
  v17 = (unsigned int)(2 * v12 + 22);
  if ( v17 != v16 )
  {
    TextNormMultiResult = -2147024882;
    v14 = 0;
    goto LABEL_13;
  }
  if ( !g_heap )
  {
    v42 = 0;
    goto LABEL_51;
  }
  v18 = HeapAlloc(g_heap, 0, v16);
  v42 = v18;
  if ( !v18 )
  {
LABEL_51:
    TextNormMultiResult = -2147024882;
    goto LABEL_12;
  }
  *v18 = 48;
  *((_WORD *)v18 + 4) = a3;
  *((_DWORD *)v18 + 3) = a5;
  memcpy_0(v18 + 2, a2, 2 * v12 + 2);
  v19 = *((_QWORD *)this + 15);
  v14 = v42;
  TextNormMultiResult = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, LPVOID *, unsigned int *))(*(_QWORD *)v19 + 32LL))(
                          v19,
                          v42,
                          (unsigned int)v17,
                          &pv,
                          &v39);
  v20 = 0;
  if ( TextNormMultiResult >= 0 )
  {
    TextNormMultiResult = CreateTextNormMultiResult(v41);
    if ( TextNormMultiResult >= 0 )
    {
      v21 = v41[0];
      TextNormMultiResult = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *, LPVOID, _QWORD))(*(_QWORD *)v41[0] + 112LL))(
                              v41[0],
                              pv,
                              v39);
      if ( TextNormMultiResult >= 0 )
      {
        LODWORD(v42) = 0;
        v22 = a6;
        v23 = (*(__int64 (__fastcall **)(struct ITextNormMultiResult *, _QWORD, WCHAR ***, void **))(*(_QWORD *)v21 + 48LL))(
                v21,
                v10,
                &a6->ppszzNormalizedList,
                &v42);
        TextNormMultiResult = v23;
        if ( v23 >= 0 )
        {
          v24 = (int)v42;
          if ( (_DWORD)v42 == v10 )
          {
            v24 = a4;
            LODWORD(v42) = a4;
            TextNormMultiResult = 282751;
          }
          v25 = 8LL * v24;
          if ( v24 > 0 )
          {
            for ( i = 0; i < v24; ++i )
            {
              v27 = -1;
              do
                ++v27;
              while ( v22->ppszzNormalizedList[i][v27] );
              v25 += 2 * v27 + 4;
            }
          }
          v28 = (WCHAR **)CoTaskMemAlloc(v25 + 2);
          v29 = v28;
          if ( v28 )
          {
            v30 = (WCHAR *)&v28[(int)v42];
            if ( (int)v42 > 0 )
            {
              do
              {
                v29[v20] = v30;
                v31 = v22->ppszzNormalizedList[v20];
                v32 = -1;
                do
                  ++v32;
                while ( v31[v32] );
                memcpy_0(v30, v31, 2 * v32 + 2);
                v33 = 0;
                ppszzNormalizedList = v22->ppszzNormalizedList;
                v35 = -1;
                do
                  ++v35;
                while ( ppszzNormalizedList[v20][v35] );
                if ( v35 )
                {
                  do
                  {
                    if ( v30[v33] == 32 )
                      v30[v33] = 0;
                    ++v33;
                    ppszzNormalizedList = v22->ppszzNormalizedList;
                    v36 = -1;
                    do
                      ++v36;
                    while ( ppszzNormalizedList[v20][v36] );
                  }
                  while ( v33 < v36 );
                }
                v37 = -1;
                do
                  ++v37;
                while ( ppszzNormalizedList[v20][v37] );
                v38 = (char *)&v30[v37];
                *((_WORD *)v38 + 1) = 0;
                v30 = (WCHAR *)(v38 + 4);
                ++v20;
              }
              while ( v20 < (int)v42 );
            }
            CoTaskMemFree(v22->ppszzNormalizedList);
            v22->ppszzNormalizedList = v29;
            v22->ulSize = (unsigned int)v42;
          }
          else
          {
            TextNormMultiResult = -2147024882;
          }
        }
        else if ( v23 == -2147217404 )
        {
          TextNormMultiResult = -2147467259;
        }
      }
    }
  }
LABEL_13:
  CWinHeap::Free((CWinHeap *)&g_heap, v14);
  if ( pv )
    CoTaskMemFree(pv);
  ATL::CComPtrBase<ISpPhraseBuilder>::~CComPtrBase<ISpPhraseBuilder>(v41);
  return (unsigned int)TextNormMultiResult;
}

```

## disassembly

```asm
0x1800052f4  push    rbp
0x1800052f6  push    rbx
0x1800052f7  push    rsi
0x1800052f8  push    rdi
0x1800052f9  push    r12
0x1800052fb  push    r13
0x1800052fd  push    r14
0x1800052ff  push    r15
0x180005301  mov     rbp, rsp
0x180005304  sub     rsp, 58h
0x180005308  mov     r15d, r9d
0x18000530b  movzx   r12d, r8w
0x18000530f  mov     rdi, rdx
0x180005312  mov     r13, rcx
0x180005315  xor     edx, edx
0x180005317  mov     [rbp+pv], rdx
0x18000531b  mov     [rbp+var_28], edx
0x18000531e  mov     [rbp+var_18], rdx
0x180005322  mov     [rbp+arg_8], rdx
0x180005326  test    rdi, rdi
0x180005329  jz      short loc_18000537A
0x18000532b  cmp     [rdi], dx
0x18000532e  jz      short loc_18000537A
0x180005330  cmp     [rbp+arg_28], rdx
0x180005334  jz      short loc_18000537A
0x180005336  lea     r14d, [r9+1]
0x18000533a  cmp     r14d, 1
0x18000533e  jle     short loc_18000537A
0x180005340  mov     ebx, 80004005h
0x180005345  cmp     [rcx+78h], rdx
0x180005349  jz      short loc_18000537F
0x18000534b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000534f  inc     rbx
0x180005352  cmp     [rdi+rbx*2], dx
0x180005356  jnz     short loc_18000534F
0x180005358  mov     esi, edx
0x18000535a  test    rbx, rbx
0x18000535d  jz      short loc_18000537A
0x18000535f  mov     ecx, esi
0x180005361  movzx   ecx, word ptr [rdi+rcx*2]
0x180005365  call    cs:__imp__o_iswspace
0x18000536b  xor     edx, edx; dwFlags
0x18000536d  test    eax, eax
0x18000536f  jz      short loc_1800053BE
0x180005371  inc     esi
0x180005373  mov     eax, esi
0x180005375  cmp     rax, rbx
0x180005378  jb      short loc_18000535F
0x18000537a  mov     ebx, 80070057h
0x18000537f  mov     r13, [rbp+arg_8]
0x180005383  mov     rdx, r13; void *
0x180005386  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18000538d  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180005392  mov     rcx, [rbp+pv]; pv
0x180005396  test    rcx, rcx
0x180005399  jz      short loc_1800053A2
0x18000539b  call    cs:__imp_CoTaskMemFree
0x1800053a1  nop
0x1800053a2  lea     rcx, [rbp+var_18]
0x1800053a6  call    ??1?$CComPtrBase@UISpPhraseBuilder@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpPhraseBuilder>::~CComPtrBase<ISpPhraseBuilder>(void)
0x1800053ab  mov     eax, ebx
0x1800053ad  add     rsp, 58h
0x1800053b1  pop     r15
0x1800053b3  pop     r14
0x1800053b5  pop     r13
0x1800053b7  pop     r12
0x1800053b9  pop     rdi
0x1800053ba  pop     rsi
0x1800053bb  pop     rbx
0x1800053bc  pop     rbp
0x1800053bd  retn
0x1800053be  lea     r8, ds:16h[rbx*2]; dwBytes
0x1800053c6  mov     esi, r8d
0x1800053c9  cmp     rsi, r8
0x1800053cc  jz      short loc_1800053D8
0x1800053ce  mov     ebx, 8007000Eh
0x1800053d3  mov     r13, rdx
0x1800053d6  jmp     short loc_180005383
0x1800053d8  mov     rcx, cs:?g_heap@@3VCHeap@@A; hHeap
0x1800053df  test    rcx, rcx
0x1800053e2  jz      loc_180005609
0x1800053e8  call    cs:__imp_HeapAlloc
0x1800053ee  mov     rcx, rax
0x1800053f1  mov     [rbp+arg_8], rax
0x1800053f5  test    rax, rax
0x1800053f8  jz      loc_18000560D
0x1800053fe  mov     qword ptr [rax], 30h ; '0'
0x180005405  mov     [rax+8], r12w
0x18000540a  mov     eax, [rbp+arg_20]
0x18000540d  mov     [rcx+0Ch], eax
0x180005410  lea     r8, ds:2[rbx*2]; Size
0x180005418  add     rcx, 10h; void *
0x18000541c  mov     rdx, rdi; Src
0x18000541f  call    memcpy_0
0x180005424  mov     rcx, [r13+78h]
0x180005428  mov     rax, [rcx]
0x18000542b  lea     rdx, [rbp+var_28]
0x18000542f  mov     [rsp+58h+var_38], rdx
0x180005434  lea     r9, [rbp+pv]
0x180005438  mov     r8d, esi
0x18000543b  mov     r13, [rbp+arg_8]
0x18000543f  mov     rdx, r13
0x180005442  mov     rax, [rax+20h]
0x180005446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000544b  mov     ebx, eax
0x18000544d  xor     r12d, r12d
0x180005450  test    eax, eax
0x180005452  js      loc_180005383
0x180005458  lea     rcx, [rbp+var_18]; struct ITextNormMultiResult **
0x18000545c  call    ?CreateTextNormMultiResult@@YAJPEAPEAUITextNormMultiResult@@@Z; CreateTextNormMultiResult(ITextNormMultiResult * *)
0x180005461  mov     ebx, eax
0x180005463  test    eax, eax
0x180005465  js      loc_180005383
0x18000546b  mov     rdi, [rbp+var_18]
0x18000546f  mov     rax, [rdi]
0x180005472  mov     r8d, [rbp+var_28]
0x180005476  mov     rdx, [rbp+pv]
0x18000547a  mov     rcx, rdi
0x18000547d  mov     rax, [rax+70h]
0x180005481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005486  mov     ebx, eax
0x180005488  test    eax, eax
0x18000548a  js      loc_180005383
0x180005490  mov     dword ptr [rbp+arg_8], r12d
0x180005494  mov     rsi, [rbp+arg_28]
0x180005498  mov     rax, [rdi]
0x18000549b  lea     r9, [rbp+arg_8]
0x18000549f  lea     r8, [rsi+8]
0x1800054a3  mov     edx, r14d
0x1800054a6  mov     rcx, rdi
0x1800054a9  mov     rax, [rax+30h]
0x1800054ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054b2  mov     ebx, eax
0x1800054b4  test    eax, eax
0x1800054b6  jns     short loc_1800054CD
0x1800054b8  cmp     eax, 80041004h
0x1800054bd  jnz     loc_180005383
0x1800054c3  mov     ebx, 80004005h
0x1800054c8  jmp     loc_180005383
0x1800054cd  mov     ecx, dword ptr [rbp+arg_8]
0x1800054d0  cmp     ecx, r14d
0x1800054d3  jnz     short loc_1800054E0
0x1800054d5  mov     ecx, r15d
0x1800054d8  mov     dword ptr [rbp+arg_8], ecx
0x1800054db  mov     ebx, 4507Fh
0x1800054e0  movsxd  rdx, ecx
0x1800054e3  shl     rdx, 3
0x1800054e7  test    ecx, ecx
0x1800054e9  jle     short loc_180005517
0x1800054eb  mov     r8d, r12d
0x1800054ee  mov     r10, [rsi+8]
0x1800054f2  movsxd  rax, r8d
0x1800054f5  mov     r9, [r10+rax*8]
0x1800054f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800054fd  inc     rax
0x180005500  cmp     [r9+rax*2], r12w
0x180005505  jnz     short loc_1800054FD
0x180005507  lea     rdx, [rdx+rax*2]
0x18000550b  add     rdx, 4
0x18000550f  inc     r8d
0x180005512  cmp     r8d, ecx
0x180005515  jl      short loc_1800054F2
0x180005517  lea     rcx, [rdx+2]; cb
0x18000551b  call    cs:__imp_CoTaskMemAlloc
0x180005521  mov     r14, rax
0x180005524  xor     r9d, r9d
0x180005527  test    rax, rax
0x18000552a  jnz     short loc_180005536
0x18000552c  mov     ebx, 8007000Eh
0x180005531  jmp     loc_180005383
0x180005536  movsxd  rcx, dword ptr [rbp+arg_8]
0x18000553a  lea     rdi, [rax+rcx*8]
0x18000553e  test    ecx, ecx
0x180005540  jle     loc_1800055F1
0x180005546  or      r10, 0FFFFFFFFFFFFFFFFh
0x18000554a  movsxd  r15, r12d
0x18000554d  mov     [r14+r15*8], rdi
0x180005551  mov     rax, [rsi+8]
0x180005555  mov     rdx, [rax+r15*8]; Src
0x180005559  mov     r8, r10
0x18000555c  inc     r8
0x18000555f  cmp     [rdx+r8*2], r9w
0x180005564  jnz     short loc_18000555C
0x180005566  lea     r8, ds:2[r8*2]; Size
0x18000556e  mov     rcx, rdi; void *
0x180005571  call    memcpy_0
0x180005576  xor     r9d, r9d
0x180005579  mov     edx, r9d
0x18000557c  mov     r8, [rsi+8]
0x180005580  mov     rcx, [r8+r15*8]
0x180005584  or      r10, 0FFFFFFFFFFFFFFFFh
0x180005588  mov     rax, r10
0x18000558b  inc     rax
0x18000558e  cmp     [rcx+rax*2], r9w
0x180005593  jnz     short loc_18000558B
0x180005595  test    rax, rax
0x180005598  jz      short loc_1800055C6
0x18000559a  mov     ecx, edx
0x18000559c  cmp     word ptr [rdi+rcx*2], 20h ; ' '
0x1800055a1  jnz     short loc_1800055A8
0x1800055a3  mov     [rdi+rcx*2], r9w
0x1800055a8  inc     edx
0x1800055aa  mov     r8, [rsi+8]
0x1800055ae  mov     rax, [r8+r15*8]
0x1800055b2  mov     rcx, r10
0x1800055b5  inc     rcx
0x1800055b8  cmp     [rax+rcx*2], r9w
0x1800055bd  jnz     short loc_1800055B5
0x1800055bf  mov     eax, edx
0x1800055c1  cmp     rax, rcx
0x1800055c4  jb      short loc_18000559A
0x1800055c6  mov     rcx, [r8+r15*8]
0x1800055ca  mov     rax, r10
0x1800055cd  inc     rax
0x1800055d0  cmp     [rcx+rax*2], r9w
0x1800055d5  jnz     short loc_1800055CD
0x1800055d7  lea     rcx, [rdi+rax*2]
0x1800055db  mov     [rcx+2], r9w
0x1800055e0  lea     rdi, [rcx+4]
0x1800055e4  inc     r12d
0x1800055e7  cmp     r12d, dword ptr [rbp+arg_8]
0x1800055eb  jl      loc_18000554A
0x1800055f1  mov     rcx, [rsi+8]; pv
0x1800055f5  call    cs:__imp_CoTaskMemFree
0x1800055fb  mov     [rsi+8], r14
0x1800055ff  mov     eax, dword ptr [rbp+arg_8]
0x180005602  mov     [rsi], eax
0x180005604  jmp     loc_180005383
0x180005609  mov     [rbp+arg_8], rdx
0x18000560d  mov     ebx, 8007000Eh
0x180005612  jmp     loc_18000537F
```
