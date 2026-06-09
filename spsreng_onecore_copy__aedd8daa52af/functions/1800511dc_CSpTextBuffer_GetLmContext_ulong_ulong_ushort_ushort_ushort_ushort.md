# CSpTextBuffer::GetLmContext(ulong,ulong,ushort * *,ushort * *,ushort * *,ushort * *)

- ea: `0x1800511dc`
- end: `0x180051604`
- name: `?GetLmContext@CSpTextBuffer@@QEAAJKKPEAPEAG000@Z`
- size: `1064`
- prototype: `__int64 __usercall@<rax>(CSpTextBuffer *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned __int16 **@<r9>, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x18009ac68`

## callees

- `0x18001474c`
- `0x1800511dc`
- `0x180052258`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005131d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005132c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800513db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800513ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005150c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051521`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800515d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800515e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005131d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005132c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800513db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800513ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005150c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051521`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800515d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800515e3`

## pseudocode

```c
__int64 __fastcall CSpTextBuffer::GetLmContext(
        CSpTextBuffer *this,
        unsigned int a2,
        int a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7)
{
  int v7; // r13d
  __int64 v8; // r12
  unsigned int v9; // r9d
  unsigned int v11; // r14d
  int v12; // edi
  unsigned int v13; // edx
  unsigned int v14; // ecx
  unsigned __int16 **v15; // r14
  const unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rax
  unsigned __int16 **v18; // rbx
  __int64 v19; // rcx
  int v20; // eax
  void *v21; // rcx
  unsigned __int16 *v22; // rax
  bool v23; // cc
  const unsigned __int16 *v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  void *v27; // rcx
  unsigned __int16 *v28; // rax
  __int64 v29; // rbx
  unsigned int v30; // edx
  unsigned __int16 **v31; // rdi
  const unsigned __int16 *v32; // rax
  unsigned __int16 *v33; // rax
  unsigned __int16 **v34; // r13
  __int64 v35; // rcx
  void *v36; // rcx
  unsigned __int16 *v37; // rax
  const unsigned __int16 *v38; // rax
  __int64 v39; // rcx
  int v40; // eax
  void *v41; // rcx
  unsigned __int16 *v42; // rax
  unsigned int v44; // [rsp+30h] [rbp-20h]
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  LPVOID v46[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v47; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v48; // [rsp+98h] [rbp+48h]
  unsigned __int16 **v49; // [rsp+A8h] [rbp+58h]

  v49 = a4;
  v48 = a2;
  v7 = *((_DWORD *)this + 4);
  v8 = *((_QWORD *)this + 1);
  v9 = a2;
  v44 = 0;
  v47 = 0;
  v11 = 0;
  pv = 0;
  v12 = v7;
  v46[0] = 0;
  if ( v7 <= 0 )
    goto LABEL_35;
  v13 = a3 + a2;
  do
  {
    if ( (*(_DWORD *)(v8 + 24LL * (unsigned int)v12 - 20) >> 5) + (*(_DWORD *)(v8 + 24LL * (unsigned int)v12 - 16) >> 2) <= v13 )
      break;
    --v12;
  }
  while ( v12 > 0 );
  if ( v12 >= v7 )
    goto LABEL_35;
  v14 = *(_DWORD *)(v8 + 24LL * v12 + 4);
  if ( v13 > v14 >> 5 || (v14 & 2) != 0 )
    goto LABEL_35;
  v15 = a7;
  if ( (v14 & 8) == 0 )
  {
    v16 = CSpTextBuffer::NormalizedWord(this, v12);
    v17 = CHeap::WcsDup((CHeap *)&g_heap, v16);
    v18 = a6;
    *a6 = v17;
    goto LABEL_20;
  }
  _mm_lfence();
  v19 = *(_QWORD *)(*((_QWORD *)this + 1) + 24LL * v12 + 16);
  v20 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *, LPVOID *))(*(_QWORD *)v19 + 40LL))(
          v19,
          &v47,
          &pv,
          v46);
  v18 = a6;
  v44 = v20;
  if ( v20 < 0 )
    goto LABEL_15;
  v21 = pv;
  if ( pv )
  {
    if ( !v47 )
      goto LABEL_16;
    v22 = CHeap::WcsDup((CHeap *)&g_heap, *(const unsigned __int16 **)pv);
    v23 = v47 <= 1;
    *v18 = v22;
    if ( !v23 )
      *v15 = CHeap::WcsDup((CHeap *)&g_heap, *((const unsigned __int16 **)pv + 1));
LABEL_15:
    v21 = pv;
LABEL_16:
    if ( v21 )
      CoTaskMemFree(v21);
  }
  if ( v46[0] )
    CoTaskMemFree(v46[0]);
LABEL_20:
  if ( !*v18 || *v15 || v12 + 1 >= v7 || (*(_BYTE *)(v8 + 24LL * v12 + 28) & 2) != 0 )
    goto LABEL_34;
  if ( (*(_BYTE *)(v8 + 24LL * v12 + 28) & 8) != 0 )
  {
    _mm_lfence();
    v25 = *(_QWORD *)(*((_QWORD *)this + 1) + 24LL * v12 + 40);
    v26 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *, LPVOID *))(*(_QWORD *)v25 + 40LL))(
            v25,
            &v47,
            &pv,
            v46);
    v27 = pv;
    v44 = v26;
    if ( v26 >= 0 )
    {
      if ( !pv )
      {
LABEL_32:
        if ( v46[0] )
          CoTaskMemFree(v46[0]);
        goto LABEL_34;
      }
      if ( v47 )
      {
        v28 = CHeap::WcsDup((CHeap *)&g_heap, *(const unsigned __int16 **)pv);
        v27 = pv;
        *v15 = v28;
      }
    }
    if ( v27 )
      CoTaskMemFree(v27);
    goto LABEL_32;
  }
  v24 = CSpTextBuffer::NormalizedWord(this, v12 + 1);
  *v15 = CHeap::WcsDup((CHeap *)&g_heap, v24);
LABEL_34:
  v11 = v44;
  v9 = v48;
LABEL_35:
  v29 = (unsigned int)(v12 - 1);
  if ( v12 != v7 )
    v29 = (unsigned int)v12;
  if ( (int)v29 >= 0 )
  {
    while ( *(_DWORD *)(v8 + 24 * v29 + 4) >> 5 >= v9 )
    {
      v29 = (unsigned int)(v29 - 1);
      if ( (int)v29 < 0 )
        return v11;
    }
    v30 = *(_DWORD *)(v8 + 24LL * (int)v29 + 4);
    if ( v9 >= (v30 >> 5) + (*(_DWORD *)(v8 + 24LL * (int)v29 + 8) >> 2) && (v30 & 2) == 0 )
    {
      v31 = a5;
      if ( (v30 & 8) == 0 )
      {
        v32 = CSpTextBuffer::NormalizedWord(this, v29);
        v33 = CHeap::WcsDup((CHeap *)&g_heap, v32);
        v34 = v49;
        *v49 = v33;
        goto LABEL_58;
      }
      _mm_lfence();
      v35 = *(_QWORD *)(*((_QWORD *)this + 1) + 24LL * (int)v29 + 16);
      v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *, LPVOID *))(*(_QWORD *)v35 + 40LL))(
              v35,
              &v47,
              &pv,
              v46);
      if ( (v11 & 0x80000000) != 0 )
      {
        v34 = v49;
      }
      else
      {
        v36 = pv;
        if ( !pv )
        {
          v34 = v49;
LABEL_56:
          if ( v46[0] )
            CoTaskMemFree(v46[0]);
LABEL_58:
          if ( !*v34 || *v31 || (int)v29 <= 0 || (*(_BYTE *)(v8 + 24LL * (int)v29 - 20) & 2) != 0 )
            return v11;
          if ( (*(_BYTE *)(v8 + 24LL * (int)v29 - 20) & 8) == 0 )
          {
            v38 = CSpTextBuffer::NormalizedWord(this, (int)v29 - 1);
            *v31 = CHeap::WcsDup((CHeap *)&g_heap, v38);
            return v11;
          }
          _mm_lfence();
          v39 = *(_QWORD *)(*((_QWORD *)this + 1) + 24LL * (int)v29 - 8);
          v40 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *, LPVOID *))(*(_QWORD *)v39 + 40LL))(
                  v39,
                  &v47,
                  &pv,
                  v46);
          v41 = pv;
          v11 = v40;
          if ( v40 >= 0 )
          {
            if ( !pv )
            {
LABEL_70:
              if ( v46[0] )
                CoTaskMemFree(v46[0]);
              return v11;
            }
            if ( v47 )
            {
              v42 = CHeap::WcsDup((CHeap *)&g_heap, *((const unsigned __int16 **)pv + v47 - 1));
              v41 = pv;
              *v31 = v42;
            }
          }
          if ( v41 )
            CoTaskMemFree(v41);
          goto LABEL_70;
        }
        if ( !v47 )
        {
          v34 = v49;
LABEL_53:
          if ( v36 )
            CoTaskMemFree(v36);
          goto LABEL_56;
        }
        v37 = CHeap::WcsDup((CHeap *)&g_heap, *((const unsigned __int16 **)pv + v47 - 1));
        v34 = v49;
        *v49 = v37;
        if ( v47 > 1 )
          *v31 = CHeap::WcsDup((CHeap *)&g_heap, *((const unsigned __int16 **)pv + v47 - 2));
      }
      v36 = pv;
      goto LABEL_53;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1800511dc  mov     [rsp-38h+arg_10], rbx
0x1800511e1  mov     [rsp-38h+arg_18], r9
0x1800511e6  mov     [rsp-38h+arg_8], edx
0x1800511ea  push    rbp
0x1800511eb  push    rsi
0x1800511ec  push    rdi
0x1800511ed  push    r12
0x1800511ef  push    r13
0x1800511f1  push    r14
0x1800511f3  push    r15
0x1800511f5  mov     rbp, rsp
0x1800511f8  sub     rsp, 50h
0x1800511fc  mov     r13d, [rcx+10h]
0x180051200  xor     ebx, ebx
0x180051202  mov     r12, [rcx+8]
0x180051206  mov     r9d, edx
0x180051209  mov     [rbp+var_20], ebx
0x18005120c  mov     r15, rcx
0x18005120f  mov     [rbp+arg_0], ebx
0x180051212  mov     r14d, ebx
0x180051215  mov     [rbp+pv], rbx
0x180051219  mov     edi, r13d
0x18005121c  mov     [rbp+var_10], rbx
0x180051220  test    r13d, r13d
0x180051223  jle     loc_1800513F8
0x180051229  add     edx, r8d
0x18005122c  mov     eax, edi
0x18005122e  lea     rax, [rax+rax*2]
0x180051232  mov     ecx, [r12+rax*8-10h]
0x180051237  mov     eax, [r12+rax*8-14h]
0x18005123c  shr     eax, 5
0x18005123f  shr     ecx, 2
0x180051242  add     ecx, eax
0x180051244  cmp     ecx, edx
0x180051246  jbe     short loc_18005124E
0x180051248  dec     edi
0x18005124a  test    edi, edi
0x18005124c  jg      short loc_18005122C
0x18005124e  cmp     edi, r13d
0x180051251  jge     loc_1800513F8
0x180051257  movsxd  rsi, edi
0x18005125a  lea     r8, [rsi+rsi*2]
0x18005125e  mov     ecx, [r12+r8*8+4]
0x180051263  mov     eax, ecx
0x180051265  shr     eax, 5
0x180051268  cmp     edx, eax
0x18005126a  ja      loc_1800513F8
0x180051270  test    cl, 2
0x180051273  jnz     loc_1800513F8
0x180051279  mov     r14, [rbp+arg_30]
0x18005127d  test    cl, 8
0x180051280  jnz     short loc_1800512A7
0x180051282  mov     edx, edi; int
0x180051284  mov     rcx, r15; this
0x180051287  call    ?NormalizedWord@CSpTextBuffer@@QEAAPEAGH@Z; CSpTextBuffer::NormalizedWord(int)
0x18005128c  mov     rdx, rax; unsigned __int16 *
0x18005128f  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180051296  call    ?WcsDup@CHeap@@QEAAPEAGPEBG@Z; CHeap::WcsDup(ushort const *)
0x18005129b  mov     rbx, [rbp+arg_28]
0x18005129f  mov     [rbx], rax
0x1800512a2  jmp     loc_180051332
0x1800512a7  lfence
0x1800512aa  mov     rax, [r15+8]
0x1800512ae  lea     r9, [rbp+var_10]
0x1800512b2  lea     rdx, [rbp+arg_0]
0x1800512b6  mov     rcx, [rax+r8*8+10h]
0x1800512bb  lea     r8, [rbp+pv]
0x1800512bf  mov     rax, [rcx]
0x1800512c2  mov     rax, [rax+28h]
0x1800512c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512cb  mov     rbx, [rbp+arg_28]
0x1800512cf  mov     [rbp+var_20], eax
0x1800512d2  test    eax, eax
0x1800512d4  js      short loc_180051314
0x1800512d6  mov     rcx, [rbp+pv]
0x1800512da  test    rcx, rcx
0x1800512dd  jz      short loc_180051323
0x1800512df  cmp     [rbp+arg_0], 0
0x1800512e3  jbe     short loc_180051318
0x1800512e5  mov     rdx, [rcx]; unsigned __int16 *
0x1800512e8  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800512ef  call    ?WcsDup@CHeap@@QEAAPEAGPEBG@Z; CHeap::WcsDup(ushort const *)
0x1800512f4  cmp     [rbp+arg_0], 1
0x1800512f8  mov     [rbx], rax
0x1800512fb  jbe     short loc_180051314
0x1800512fd  mov     rdx, [rbp+pv]
0x180051301  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180051308  mov     rdx, [rdx+8]; unsigned __int16 *
0x18005130c  call    ?WcsDup@CHeap@@QEAAPEAGPEBG@Z; CHeap::WcsDup(ushort const *)
0x180051311  mov     [r14], rax
0x180051314  mov     rcx, [rbp+pv]; pv
0x180051318  test    rcx, rcx
0x18005131b  jz      short loc_180051323
0x18005131d  call    cs:__imp_CoTaskMemFree
0x180051323  mov     rcx, [rbp+var_10]; pv
0x180051327  test    rcx, rcx
0x18005132a  jz      short loc_180051332
0x18005132c  call    cs:__imp_CoTaskMemFree
0x180051332  cmp     qword ptr [rbx], 0
0x180051336  jz      loc_1800513F0
0x18005133c  cmp     qword ptr [r14], 0
0x180051340  jnz     loc_1800513F0
0x180051346  lea     edx, [rdi+1]; int
0x180051349  cmp     edx, r13d
0x18005134c  jge     loc_1800513F0
0x180051352  lea     rcx, [rsi+rsi*2]
0x180051356  test    byte ptr [r12+rcx*8+1Ch], 2
0x18005135c  jnz     loc_1800513F0
0x180051362  test    byte ptr [r12+rcx*8+1Ch], 8
0x180051368  jnz     short loc_180051386
0x18005136a  mov     rcx, r15; this
0x18005136d  call    ?NormalizedWord@CSpTextBuffer@@QEAAPEAGH@Z; CSpTextBuffer::NormalizedWord(int)
0x180051372  mov     rdx, rax; unsigned __int16 *
0x180051375  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18005137c  call    ?WcsDup@CHeap@@QEAAPEAGPEBG@Z; CHeap::WcsDup(ushort const *)
0x180051381  mov     [r14], rax
0x180051384  jmp     short loc_1800513F0
0x180051386  lfence
0x180051389  mov     rax, [r15+8]
0x18005138d  lea     r9, [rbp+var_10]
0x180051391  lea     r8, [rbp+pv]
0x180051395  lea     rdx, [rbp+arg_0]
0x180051399  mov     rcx, [rax+rcx*8+28h]
0x18005139e  mov     rax, [rcx]
0x1800513a1  mov     rax, [rax+28h]
0x1800513a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800513aa  mov     rcx, [rbp+pv]
0x1800513ae  mov     [rbp+var_20], eax
0x1800513b1  test    eax, eax
0x1800513b3  js      short loc_1800513D6
0x1800513b5  test    rcx, rcx
0x1800513b8  jz      short loc_1800513E1
0x1800513ba  cmp     [rbp+arg_0], 0
0x1800513be  jbe     short loc_1800513D6
0x1800513c0  mov     rdx, [rcx]; unsigned __int16 *
0x1800513c3  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800513ca  call    ?WcsDup@CHeap@@QEAAPEAGPEBG@Z; CHeap::WcsDup(ushort const *)
0x1800513cf  mov     rcx, [rbp+pv]; pv
0x1800513d3  mov     [r14], rax
0x1800513d6  test    rcx, rcx
0x1800513d9  jz      short loc_1800513E1
0x1800513db  call    cs:__imp_CoTaskMemFree
0x1800513e1  mov     rcx, [rbp+var_10]; pv
0x1800513e5  test    rcx, rcx
0x1800513e8  jz      short loc_1800513F0
0x1800513ea  call    cs:__imp_CoTaskMemFree
0x1800513f0  mov     r14d, [rbp+var_20]
0x1800513f4  mov     r9d, [rbp+arg_8]
0x1800513f8  cmp     edi, r13d
0x1800513fb  lea     ebx, [rdi-1]
0x1800513fe  cmovnz  ebx, edi
0x180051401  test    ebx, ebx
0x180051403  js      loc_1800515E9
0x180051409  lea     rcx, [rbx+rbx*2]
0x18005140d  mov     eax, [r12+rcx*8+4]
0x180051412  shr     eax, 5
0x180051415  cmp     eax, r9d
0x180051418  jb      short loc_180051424
0x18005141a  sub     ebx, 1
0x18005141d  jns     short loc_180051409
0x18005141f  jmp     loc_1800515E9
0x180051424  movsxd  rsi, ebx
0x180051427  lea     r8, [rsi+rsi*2]
0x18005142b  mov     edx, [r12+r8*8+4]
0x180051430  mov     eax, edx
0x180051432  mov     ecx, [r12+r8*8+8]
0x180051437  shr     eax, 5
0x18005143a  shr     ecx, 2
0x18005143d  add     ecx, eax
0x18005143f  cmp     r9d, ecx
0x180051442  jb      loc_1800515E9
0x180051448  test    dl, 2
0x18005144b  jnz     loc_1800515E9
0x180051451  mov     rdi, [rbp+arg_20]
0x180051455  test    dl, 8
0x180051458  jnz     short loc_180051480
0x18005145a  mov     edx, ebx; int
0x18005145c  mov     rcx, r15; this
0x18005145f  call    ?NormalizedWord@CSpTextBuffer@@QEAAPEAGH@Z; CSpTextBuffer::NormalizedWord(int)
0x180051464  mov     rdx, rax; unsigned __int16 *
0x180051467  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18005146e  call    ?WcsDup@CHeap@@QEAAPEAGPEBG@Z; CHeap::WcsDup(ushort const *)
0x180051473  mov     r13, [rbp+arg_18]
0x180051477  mov     [r13+0], rax
0x18005147b  jmp     loc_180051527
0x180051480  lfence
0x180051483  mov     rax, [r15+8]
0x180051487  lea     r9, [rbp+var_10]
0x18005148b  lea     rdx, [rbp+arg_0]
0x18005148f  mov     rcx, [rax+r8*8+10h]
0x180051494  lea     r8, [rbp+pv]
0x180051498  mov     rax, [rcx]
0x18005149b  mov     rax, [rax+28h]
0x18005149f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800514a4  mov     r14d, eax
0x1800514a7  test    eax, eax
0x1800514a9  js      short loc_1800514FD
0x1800514ab  mov     rcx, [rbp+pv]; pv
0x1800514af  test    rcx, rcx
0x1800514b2  jz      short loc_180051514
0x1800514b4  mov     eax, [rbp+arg_0]
0x1800514b7  test    eax, eax
0x1800514b9  jz      short loc_180051503
0x1800514bb  dec     eax
0x1800514bd  mov     rdx, [rcx+rax*8]; unsigned __int16 *
0x1800514c1  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800514c8  call    ?WcsDup@CHeap@@QEAAPEAGPEBG@Z; CHeap::WcsDup(ushort const *)
0x1800514cd  mov     r13, [rbp+arg_18]
0x1800514d1  mov     [r13+0], rax
0x1800514d5  mov     eax, [rbp+arg_0]
0x1800514d8  cmp     eax, 1
0x1800514db  jbe     short loc_1800514F7
0x1800514dd  mov     rdx, [rbp+pv]
0x1800514e1  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800514e8  add     eax, 0FFFFFFFEh
0x1800514eb  mov     rdx, [rdx+rax*8]; unsigned __int16 *
0x1800514ef  call    ?WcsDup@CHeap@@QEAAPEAGPEBG@Z; CHeap::WcsDup(ushort const *)
0x1800514f4  mov     [rdi], rax
0x1800514f7  mov     rcx, [rbp+pv]
0x1800514fb  jmp     short loc_180051507
0x1800514fd  mov     r13, [rbp+arg_18]
0x180051501  jmp     short loc_1800514F7
0x180051503  mov     r13, [rbp+arg_18]
0x180051507  test    rcx, rcx
0x18005150a  jz      short loc_180051518
0x18005150c  call    cs:__imp_CoTaskMemFree
0x180051512  jmp     short loc_180051518
0x180051514  mov     r13, [rbp+arg_18]
0x180051518  mov     rcx, [rbp+var_10]; pv
0x18005151c  test    rcx, rcx
0x18005151f  jz      short loc_180051527
0x180051521  call    cs:__imp_CoTaskMemFree
0x180051527  cmp     qword ptr [r13+0], 0
0x18005152c  jz      loc_1800515E9
0x180051532  cmp     qword ptr [rdi], 0
0x180051536  jnz     loc_1800515E9
0x18005153c  test    ebx, ebx
0x18005153e  jle     loc_1800515E9
0x180051544  lea     rcx, [rsi+rsi*2]
0x180051548  test    byte ptr [r12+rcx*8-14h], 2
0x18005154e  jnz     loc_1800515E9
0x180051554  test    byte ptr [r12+rcx*8-14h], 8
0x18005155a  jnz     short loc_18005157B
0x18005155c  lea     edx, [rbx-1]; int
0x18005155f  mov     rcx, r15; this
0x180051562  call    ?NormalizedWord@CSpTextBuffer@@QEAAPEAGH@Z; CSpTextBuffer::NormalizedWord(int)
0x180051567  mov     rdx, rax; unsigned __int16 *
0x18005156a  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180051571  call    ?WcsDup@CHeap@@QEAAPEAGPEBG@Z; CHeap::WcsDup(ushort const *)
0x180051576  mov     [rdi], rax
0x180051579  jmp     short loc_1800515E9
0x18005157b  lfence
0x18005157e  mov     rax, [r15+8]
0x180051582  lea     r9, [rbp+var_10]
0x180051586  lea     r8, [rbp+pv]
0x18005158a  lea     rdx, [rbp+arg_0]
0x18005158e  mov     rcx, [rax+rcx*8-8]
0x180051593  mov     rax, [rcx]
0x180051596  mov     rax, [rax+28h]
0x18005159a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005159f  mov     rcx, [rbp+pv]
0x1800515a3  mov     r14d, eax
0x1800515a6  test    eax, eax
0x1800515a8  js      short loc_1800515CF
0x1800515aa  test    rcx, rcx
0x1800515ad  jz      short loc_1800515DA
0x1800515af  mov     eax, [rbp+arg_0]
0x1800515b2  test    eax, eax
0x1800515b4  jz      short loc_1800515CF
0x1800515b6  dec     eax
0x1800515b8  mov     rdx, [rcx+rax*8]; unsigned __int16 *
0x1800515bc  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800515c3  call    ?WcsDup@CHeap@@QEAAPEAGPEBG@Z; CHeap::WcsDup(ushort const *)
0x1800515c8  mov     rcx, [rbp+pv]; pv
0x1800515cc  mov     [rdi], rax
0x1800515cf  test    rcx, rcx
0x1800515d2  jz      short loc_1800515DA
0x1800515d4  call    cs:__imp_CoTaskMemFree
0x1800515da  mov     rcx, [rbp+var_10]; pv
0x1800515de  test    rcx, rcx
0x1800515e1  jz      short loc_1800515E9
0x1800515e3  call    cs:__imp_CoTaskMemFree
0x1800515e9  mov     rbx, [rsp+50h+arg_10]
0x1800515f1  mov     eax, r14d
0x1800515f4  add     rsp, 50h
0x1800515f8  pop     r15
0x1800515fa  pop     r14
0x1800515fc  pop     r13
0x1800515fe  pop     r12
0x180051600  pop     rdi
0x180051601  pop     rsi
0x180051602  pop     rbp
0x180051603  retn
```
