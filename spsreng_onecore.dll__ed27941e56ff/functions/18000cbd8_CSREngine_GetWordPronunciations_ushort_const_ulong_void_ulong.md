# CSREngine::GetWordPronunciations(ushort const *,ulong,void * *,ulong *)

- ea: `0x18000cbd8`
- end: `0x18000d22e`
- name: `?GetWordPronunciations@CSREngine@@QEAAJPEBGKPEAPEAXPEAK@Z`
- size: `1622`
- prototype: `__int64 __fastcall(CSREngine *this, const unsigned __int16 *, __int16, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000ed20`

## callees

- `0x180002470`
- `0x180002db8`
- `0x180002e00`
- `0x1800034b0`
- `0x180004312`
- `0x180006b20`
- `0x18000cbd8`
- `0x1800137e0`
- `0x1800c77ac`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cd4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cd4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d0d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d0d0`

## pseudocode

```c
__int64 __fastcall CSREngine::GetWordPronunciations(
        CSREngine *this,
        const unsigned __int16 *a2,
        __int16 a3,
        void **a4,
        unsigned int *a5)
{
  __int64 v7; // rcx
  int v9; // ebx
  unsigned int v10; // ebx
  char v11; // r14
  int v12; // r15d
  int v13; // eax
  __int64 *v14; // rdi
  char *v15; // r14
  _QWORD *v16; // rdi
  unsigned int v17; // esi
  unsigned int k; // r14d
  const unsigned __int16 *v19; // rdx
  const unsigned __int16 *v20; // r8
  __int64 v21; // rdx
  BOOL v22; // r15d
  unsigned __int64 v23; // rax
  unsigned int i; // r14d
  void *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  SIZE_T v28; // r13
  __int64 *v29; // r12
  unsigned int v30; // r14d
  CSREngine *v31; // r15
  _WORD *v32; // r13
  __int64 v33; // r11
  __int64 v34; // r10
  unsigned int j; // edx
  unsigned __int16 *v36; // rcx
  int v37; // eax
  int v38; // r8d
  unsigned int v39; // r12d
  __int64 *v40; // rdx
  __int64 *v41; // r15
  __int64 *v42; // r13
  void *v43; // rcx
  _WORD *v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rdx
  struct ISpPhoneConverter *v49; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v50; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+50h] [rbp-B0h]
  __int128 v52; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v53; // [rsp+68h] [rbp-98h]
  BOOL v54; // [rsp+70h] [rbp-90h]
  __int64 v55; // [rsp+78h] [rbp-88h] BYREF
  CSREngine *v56; // [rsp+80h] [rbp-80h]
  __int64 v57; // [rsp+88h] [rbp-78h] BYREF
  unsigned int *v58; // [rsp+90h] [rbp-70h]
  void **v59; // [rsp+98h] [rbp-68h]
  void **v60; // [rsp+A0h] [rbp-60h] BYREF
  __int16 *v61; // [rsp+A8h] [rbp-58h]
  unsigned int v62; // [rsp+B0h] [rbp-50h]
  __int16 v63; // [rsp+B8h] [rbp-48h] BYREF
  void **v64; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int16 *v65; // [rsp+3C8h] [rbp+2C8h]
  unsigned int v66; // [rsp+3D0h] [rbp+2D0h]
  __int16 v67; // [rsp+3D8h] [rbp+2D8h] BYREF

  v59 = a4;
  v56 = this;
  v58 = a5;
  v7 = *((_QWORD *)this + 17);
  if ( !v7 )
    return 2147500037LL;
  v57 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, const unsigned __int16 *, _QWORD, int, __int64 *))(**(_QWORD **)(v7 + 456) + 40LL))(
         *(_QWORD *)(v7 + 456),
         a2,
         a2,
         0,
         1,
         &v57);
  if ( v9 >= 0 )
  {
    v52 = 0;
    v53 = 0;
    v10 = a3 & 1;
    v11 = 0;
    v12 = 1;
    while ( 1 )
    {
      if ( v10 )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int128 *, int))(**(_QWORD **)(*((_QWORD *)this + 17)
                                                                                                + 456LL)
                                                                                  + 64LL))(
                *(_QWORD *)(*((_QWORD *)this + 17) + 456LL),
                v57,
                v10,
                &v52,
                1);
        if ( v13 >= 0 && v13 != 1 )
        {
          v14 = v53;
          if ( v53 )
          {
            if ( *((_WORD *)v53 + 10) )
              break;
          }
        }
      }
      switch ( v12 )
      {
        case 1:
          v10 = a3 & 2;
          break;
        case 2:
          v10 = a3 & 0x1000;
          break;
        case 3:
          v10 = a3 & 0x4000;
          break;
        case 4:
          v10 = a3 & 0x2000;
          break;
        default:
          v11 = 1;
          break;
      }
      ++v12;
      if ( v11 )
      {
        v15 = 0;
        v16 = 0;
        v17 = 0;
        v9 = -2147467259;
        goto LABEL_21;
      }
    }
    v66 = 0x80000000;
    v65 = &v67;
    v67 = 0;
    v64 = &CQuickStringW<384>::`vftable';
    v62 = 0x80000000;
    v61 = &v63;
    v63 = 0;
    v60 = &CQuickStringW<384>::`vftable';
    v50 = 0;
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)(*((_QWORD *)this + 17) + 456LL) + 112LL))(
           *(_QWORD *)(*((_QWORD *)this + 17) + 456LL),
           4096,
           &v50);
    if ( v9 < 0 )
      goto LABEL_40;
    v49 = 0;
    v9 = SpCreatePhoneConverter(*((_WORD *)v14 + 6), v19, v20, &v49);
    if ( v9 < 0
      || (v55 = 0,
          v9 = ((__int64 (__fastcall *)(struct ISpPhoneConverter *, GUID *, __int64 *))v49->lpVtbl->QueryInterface)(
                 v49,
                 &IID_ISpPhoneticAlphabetSelection,
                 &v55),
          v9 < 0)
      || (v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v55 + 32LL))(v55, *((unsigned int *)this + 231)),
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55),
          v9 < 0) )
    {
LABEL_39:
      ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v49, v21);
LABEL_40:
      ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v50, v19);
      CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v60);
      CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v64);
      CWordPronunciationList::~CWordPronunciationList((CWordPronunciationList *)&v52);
      return (unsigned int)v9;
    }
    v22 = v53 != 0;
    v54 = v22;
    v17 = 0;
    do
    {
      ++v17;
      v14 = (__int64 *)*v14;
    }
    while ( v14 );
    v23 = 8LL * v17;
    if ( !is_mul_ok(v17, 8u) )
      v23 = -1;
    v16 = CWinHeap::Alloc((CWinHeap *)&g_heap, v23, 0);
    if ( !v16 )
    {
      v9 = -2147024882;
      goto LABEL_39;
    }
    for ( i = 0; i < v17; ++i )
    {
      v25 = CWinHeap::Alloc((CWinHeap *)&g_heap, 0x1802u, 0);
      v16[i] = v25;
      if ( !v25 )
        goto LABEL_45;
    }
    v28 = 24;
    v51 = 24;
    v29 = v53;
    v30 = 0;
    if ( v22 )
    {
      while ( v29 && v9 >= 0 && v30 < v17 )
      {
        v31 = v56;
        v32 = (_WORD *)v29 + 10;
        v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int16 *))(**(_QWORD **)(*((_QWORD *)v56 + 17) + 456LL)
                                                                           + 160LL))(
               *(_QWORD *)(*((_QWORD *)v56 + 17) + 456LL),
               *((unsigned int *)v29 + 2),
               (__int64)v29 + 20,
               v65);
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(_QWORD, __int16 *, __int16 *))(**(_QWORD **)(*((_QWORD *)v31 + 17) + 456LL)
                                                                       + 152LL))(
                 *(_QWORD *)(*((_QWORD *)v31 + 17) + 456LL),
                 v65,
                 v61);
          if ( v9 >= 0 )
          {
            v9 = ((__int64 (__fastcall *)(struct ISpPhoneConverter *, __int16 *, _QWORD))v49->lpVtbl->IdToPhone)(
                   v49,
                   v61,
                   v16[v30]);
            if ( v9 >= 0 )
            {
              v33 = v16[v30];
              v34 = -1;
              do
                ++v34;
              while ( *(_WORD *)(v33 + 2 * v34) );
              for ( j = 0; j < v30; ++j )
              {
                v36 = (unsigned __int16 *)v16[v30];
                do
                {
                  v37 = *(unsigned __int16 *)((char *)v36 + v16[j] - v33);
                  v38 = *v36 - v37;
                  if ( v38 )
                    break;
                  ++v36;
                }
                while ( v37 );
                if ( !v38 )
                  goto LABEL_64;
              }
              if ( *v32 )
              {
                v28 = ((2 * v34 + 9) & 0xFFFFFFFFFFFFFFF8uLL) + v51 + 20;
                v51 = v28;
                goto LABEL_66;
              }
LABEL_64:
              *v32 = 0;
            }
          }
        }
        v28 = v51;
LABEL_66:
        v29 = (__int64 *)*v29;
        ++v30;
      }
    }
    v15 = (char *)CoTaskMemAlloc(v28);
    v39 = 0;
    if ( v15 )
    {
      *(_DWORD *)v15 = v28 - 4;
      *((_QWORD *)v15 + 1) = v15;
      *((_QWORD *)v15 + 2) = 24;
      v40 = (__int64 *)(v15 + 24);
      v41 = v53;
      v42 = 0;
      if ( v54 )
      {
        while ( 1 )
        {
          if ( !v41 )
            goto LABEL_83;
          if ( v9 < 0 )
            goto LABEL_85;
          if ( v39 >= v17 )
            goto LABEL_84;
          if ( *((_WORD *)v41 + 10) )
            break;
          if ( !*v41 && v42 )
          {
            v47 = 0;
LABEL_81:
            *v42 = v47;
          }
          v41 = (__int64 *)*v41;
          ++v39;
        }
        v42 = v40;
        *((_DWORD *)v40 + 2) = *((_DWORD *)v41 + 2);
        *((_WORD *)v40 + 6) = *((_WORD *)v41 + 6);
        *((_WORD *)v41 + 7) = 1;
        *((_WORD *)v40 + 7) = 1;
        *((_DWORD *)v40 + 4) = *((_DWORD *)v41 + 4);
        v43 = (char *)v40 + 20;
        v56 = (CSREngine *)((char *)v40 + 20);
        v44 = (_WORD *)v16[v39];
        v45 = -1;
        do
          ++v45;
        while ( v44[v45] );
        memcpy_0(v43, v44, 2 * v45 + 2);
        v46 = -1;
        do
          ++v46;
        while ( *(_WORD *)(v16[v39] + 2 * v46) );
        v40 = (__int64 *)((char *)v56 + ((2 * v46 + 9) & 0xFFFFFFFFFFFFFFF8uLL));
        v47 = ((char *)v40 - v15) & -(__int64)(*v41 != 0);
        goto LABEL_81;
      }
LABEL_83:
      if ( v9 >= 0 )
      {
LABEL_84:
        *v58 = v51;
        *v59 = v15;
      }
LABEL_85:
      ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v49, v40);
      ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v50, v48);
      CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v60);
      CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v64);
LABEL_21:
      CWordPronunciationList::~CWordPronunciationList((CWordPronunciationList *)&v52);
      if ( v9 < 0 && v15 )
        CoTaskMemFree(v15);
      if ( !v16 )
        return (unsigned int)v9;
    }
    else
    {
LABEL_45:
      v9 = -2147024882;
      ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v49, v26);
      ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v50, v27);
      CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v60);
      CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v64);
      CWordPronunciationList::~CWordPronunciationList((CWordPronunciationList *)&v52);
    }
    for ( k = 0; k < v17; ++k )
      operator delete((void *)v16[k]);
    operator delete(v16);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000cbd8  push    rbp
0x18000cbda  push    rbx
0x18000cbdb  push    rsi
0x18000cbdc  push    rdi
0x18000cbdd  push    r12
0x18000cbdf  push    r13
0x18000cbe1  push    r14
0x18000cbe3  push    r15
0x18000cbe5  lea     rbp, [rsp-5F8h]
0x18000cbed  sub     rsp, 6F8h
0x18000cbf4  mov     rax, cs:__security_cookie
0x18000cbfb  xor     rax, rsp
0x18000cbfe  mov     [rbp+630h+var_50], rax
0x18000cc05  mov     [rbp+630h+var_698], r9
0x18000cc09  mov     esi, r8d
0x18000cc0c  mov     r13, rcx
0x18000cc0f  mov     [rbp+630h+var_6B0], rcx
0x18000cc13  mov     rax, [rbp+630h+arg_20]
0x18000cc1a  mov     [rbp+630h+var_6A0], rax
0x18000cc1e  mov     rcx, [rcx+88h]
0x18000cc25  xor     r12d, r12d
0x18000cc28  test    rcx, rcx
0x18000cc2b  jnz     short loc_18000CC37
0x18000cc2d  mov     eax, 80004005h
0x18000cc32  jmp     loc_18000CD80
0x18000cc37  mov     [rbp+630h+var_6A8], r12
0x18000cc3b  mov     rcx, [rcx+1C8h]
0x18000cc42  mov     rax, [rcx]
0x18000cc45  lea     r8, [rbp+630h+var_6A8]
0x18000cc49  mov     [rsp+730h+var_708], r8
0x18000cc4e  mov     edi, 1
0x18000cc53  mov     [rsp+730h+var_710], edi
0x18000cc57  xor     r9d, r9d
0x18000cc5a  mov     r8, rdx
0x18000cc5d  mov     rax, [rax+28h]
0x18000cc61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc66  mov     ebx, eax
0x18000cc68  test    eax, eax
0x18000cc6a  js      loc_18000CD7E
0x18000cc70  xorps   xmm0, xmm0
0x18000cc73  xor     eax, eax
0x18000cc75  movups  [rsp+730h+var_6D8], xmm0
0x18000cc7a  mov     [rsp+730h+var_6C8], rax
0x18000cc7f  mov     ebx, esi
0x18000cc81  and     ebx, edi
0x18000cc83  mov     r14b, r12b
0x18000cc86  mov     r15d, edi
0x18000cc89  test    ebx, ebx
0x18000cc8b  jz      short loc_18000CCDE
0x18000cc8d  mov     rax, [r13+88h]
0x18000cc94  mov     rcx, [rax+1C8h]
0x18000cc9b  mov     rax, [rcx]
0x18000cc9e  mov     [rsp+730h+var_710], edi
0x18000cca2  lea     r9, [rsp+730h+var_6D8]
0x18000cca7  mov     r8d, ebx
0x18000ccaa  mov     rdx, [rbp+630h+var_6A8]
0x18000ccae  mov     rax, [rax+40h]
0x18000ccb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccb7  mov     edx, 80000000h
0x18000ccbc  test    edx, eax
0x18000ccbe  jnz     short loc_18000CCDE
0x18000ccc0  cmp     eax, edi
0x18000ccc2  jz      short loc_18000CCDE
0x18000ccc4  mov     rdi, [rsp+730h+var_6C8]
0x18000ccc9  test    rdi, rdi
0x18000cccc  jz      short loc_18000CCD9
0x18000ccce  cmp     [rdi+14h], r12w
0x18000ccd3  jnz     loc_18000CDA3
0x18000ccd9  mov     edi, 1
0x18000ccde  mov     eax, r15d
0x18000cce1  sub     eax, 1
0x18000cce4  jz      short loc_18000CD18
0x18000cce6  sub     eax, 1
0x18000cce9  jz      short loc_18000CD0E
0x18000cceb  sub     eax, 1
0x18000ccee  jz      short loc_18000CD04
0x18000ccf0  cmp     eax, 1
0x18000ccf3  jz      short loc_18000CCFA
0x18000ccf5  mov     r14b, dil
0x18000ccf8  jmp     short loc_18000CD1D
0x18000ccfa  mov     ebx, esi
0x18000ccfc  and     ebx, 2000h
0x18000cd02  jmp     short loc_18000CD1D
0x18000cd04  mov     ebx, esi
0x18000cd06  and     ebx, 4000h
0x18000cd0c  jmp     short loc_18000CD1D
0x18000cd0e  mov     ebx, esi
0x18000cd10  and     ebx, 1000h
0x18000cd16  jmp     short loc_18000CD1D
0x18000cd18  mov     ebx, esi
0x18000cd1a  and     ebx, 2
0x18000cd1d  add     r15d, edi
0x18000cd20  test    r14b, r14b
0x18000cd23  jz      loc_18000CC89
0x18000cd29  mov     r14, r12
0x18000cd2c  mov     rdi, r12
0x18000cd2f  mov     esi, r12d
0x18000cd32  mov     ebx, 80004005h
0x18000cd37  lea     rcx, [rsp+730h+var_6D8]; this
0x18000cd3c  call    ??1CWordPronunciationList@@QEAA@XZ; CWordPronunciationList::~CWordPronunciationList(void)
0x18000cd41  test    ebx, ebx
0x18000cd43  jns     short loc_18000CD53
0x18000cd45  test    r14, r14
0x18000cd48  jz      short loc_18000CD53
0x18000cd4a  mov     rcx, r14; pv
0x18000cd4d  call    cs:__imp_CoTaskMemFree
0x18000cd53  test    rdi, rdi
0x18000cd56  jz      short loc_18000CD7E
0x18000cd58  mov     r15, rdi
0x18000cd5b  mov     r14d, r12d
0x18000cd5e  test    esi, esi
0x18000cd60  jz      short loc_18000CD76
0x18000cd62  mov     ecx, r14d
0x18000cd65  mov     rcx, [r15+rcx*8]; void *
0x18000cd69  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cd6e  inc     r14d
0x18000cd71  cmp     r14d, esi
0x18000cd74  jb      short loc_18000CD62
0x18000cd76  mov     rcx, rdi; void *
0x18000cd79  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cd7e  mov     eax, ebx
0x18000cd80  mov     rcx, [rbp+630h+var_50]
0x18000cd87  xor     rcx, rsp; StackCookie
0x18000cd8a  call    __security_check_cookie
0x18000cd8f  add     rsp, 6F8h
0x18000cd96  pop     r15
0x18000cd98  pop     r14
0x18000cd9a  pop     r13
0x18000cd9c  pop     r12
0x18000cd9e  pop     rdi
0x18000cd9f  pop     rsi
0x18000cda0  pop     rbx
0x18000cda1  pop     rbp
0x18000cda2  retn
0x18000cda3  mov     [rbp+630h+var_360], edx
0x18000cda9  lea     rax, [rbp+630h+var_358]
0x18000cdb0  mov     [rbp+630h+var_368], rax
0x18000cdb7  mov     [rbp+630h+var_358], r12w
0x18000cdbf  lea     rcx, ??_7?$CQuickStringW@$0BIA@@@6B@; const CQuickStringW<384>::`vftable'
0x18000cdc6  mov     [rbp+630h+var_370], rcx
0x18000cdcd  mov     [rbp+630h+var_680], edx
0x18000cdd0  lea     rax, [rbp+630h+var_678]
0x18000cdd4  mov     [rbp+630h+var_688], rax
0x18000cdd8  mov     [rbp+630h+var_678], r12w
0x18000cddd  mov     [rbp+630h+var_690], rcx
0x18000cde1  mov     [rsp+730h+var_6E8], r12
0x18000cde6  mov     rax, [r13+88h]
0x18000cded  mov     rcx, [rax+1C8h]
0x18000cdf4  mov     rax, [rcx]
0x18000cdf7  lea     r8, [rsp+730h+var_6E8]
0x18000cdfc  mov     edx, 1000h
0x18000ce01  mov     rax, [rax+70h]
0x18000ce05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce0a  mov     ebx, eax
0x18000ce0c  test    eax, eax
0x18000ce0e  js      loc_18000CEDF
0x18000ce14  mov     [rsp+730h+var_6F0], r12
0x18000ce19  lea     r9, [rsp+730h+var_6F0]; struct ISpPhoneConverter **
0x18000ce1e  movzx   ecx, word ptr [rdi+0Ch]; unsigned __int16
0x18000ce22  call    ?SpCreatePhoneConverter@@YAJGPEBG0PEAPEAUISpPhoneConverter@@@Z; SpCreatePhoneConverter(ushort,ushort const *,ushort const *,ISpPhoneConverter * *)
0x18000ce27  mov     ebx, eax
0x18000ce29  test    eax, eax
0x18000ce2b  js      loc_18000CED4
0x18000ce31  mov     [rsp+730h+var_6B8], r12
0x18000ce36  mov     rcx, [rsp+730h+var_6F0]
0x18000ce3b  mov     rax, [rcx]
0x18000ce3e  lea     r8, [rsp+730h+var_6B8]
0x18000ce43  lea     rdx, IID_ISpPhoneticAlphabetSelection
0x18000ce4a  mov     rax, [rax]
0x18000ce4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce52  mov     ebx, eax
0x18000ce54  test    eax, eax
0x18000ce56  js      short loc_18000CED4
0x18000ce58  mov     rcx, [rsp+730h+var_6B8]
0x18000ce5d  mov     rax, [rcx]
0x18000ce60  mov     edx, [r13+39Ch]
0x18000ce67  mov     rax, [rax+20h]
0x18000ce6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce70  mov     ebx, eax
0x18000ce72  mov     rcx, [rsp+730h+var_6B8]
0x18000ce77  mov     rax, [rcx]
0x18000ce7a  mov     rax, [rax+10h]
0x18000ce7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce83  test    ebx, ebx
0x18000ce85  js      short loc_18000CED4
0x18000ce87  mov     r15d, r12d
0x18000ce8a  cmp     [rsp+730h+var_6C8], r12
0x18000ce8f  setnz   r15b
0x18000ce93  mov     [rsp+730h+var_6C0], r15d
0x18000ce98  mov     esi, r12d
0x18000ce9b  inc     esi
0x18000ce9d  mov     rdi, [rdi]
0x18000cea0  test    rdi, rdi
0x18000cea3  jnz     short loc_18000CE9B
0x18000cea5  mov     ecx, esi
0x18000cea7  lea     eax, [rdi+8]
0x18000ceaa  mul     rcx
0x18000cead  lea     rcx, [rdi-1]
0x18000ceb1  cmovb   rax, rcx
0x18000ceb5  xor     r8d, r8d; bool
0x18000ceb8  mov     rdx, rax; unsigned __int64
0x18000cebb  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18000cec2  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x18000cec7  mov     rdi, rax
0x18000ceca  test    rax, rax
0x18000cecd  jnz     short loc_18000CF10
0x18000cecf  mov     ebx, 8007000Eh
0x18000ced4  lea     rcx, [rsp+730h+var_6F0]
0x18000ced9  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x18000cede  nop
0x18000cedf  lea     rcx, [rsp+730h+var_6E8]
0x18000cee4  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x18000cee9  nop
0x18000ceea  lea     rcx, [rbp+630h+var_690]; this
0x18000ceee  call    ??1CQuickStringTBase@@MEAA@XZ; CQuickStringTBase::~CQuickStringTBase(void)
0x18000cef3  nop
0x18000cef4  lea     rcx, [rbp+630h+var_370]; this
0x18000cefb  call    ??1CQuickStringTBase@@MEAA@XZ; CQuickStringTBase::~CQuickStringTBase(void)
0x18000cf00  nop
0x18000cf01  lea     rcx, [rsp+730h+var_6D8]; this
0x18000cf06  call    ??1CWordPronunciationList@@QEAA@XZ; CWordPronunciationList::~CWordPronunciationList(void)
0x18000cf0b  jmp     loc_18000CD7E
0x18000cf10  mov     r14d, r12d
0x18000cf13  cmp     r14d, esi
0x18000cf16  jnb     short loc_18000CF7E
0x18000cf18  xor     r8d, r8d; bool
0x18000cf1b  mov     edx, 1802h; unsigned __int64
0x18000cf20  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18000cf27  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x18000cf2c  mov     ecx, r14d
0x18000cf2f  mov     [rdi+rcx*8], rax
0x18000cf33  test    rax, rax
0x18000cf36  jz      short loc_18000CF3D
0x18000cf38  inc     r14d
0x18000cf3b  jmp     short loc_18000CF13
0x18000cf3d  mov     ebx, 8007000Eh
0x18000cf42  lea     rcx, [rsp+730h+var_6F0]
0x18000cf47  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x18000cf4c  nop
0x18000cf4d  lea     rcx, [rsp+730h+var_6E8]
0x18000cf52  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x18000cf57  nop
0x18000cf58  lea     rcx, [rbp+630h+var_690]; this
0x18000cf5c  call    ??1CQuickStringTBase@@MEAA@XZ; CQuickStringTBase::~CQuickStringTBase(void)
0x18000cf61  nop
0x18000cf62  lea     rcx, [rbp+630h+var_370]; this
0x18000cf69  call    ??1CQuickStringTBase@@MEAA@XZ; CQuickStringTBase::~CQuickStringTBase(void)
0x18000cf6e  nop
0x18000cf6f  lea     rcx, [rsp+730h+var_6D8]; this
0x18000cf74  call    ??1CWordPronunciationList@@QEAA@XZ; CWordPronunciationList::~CWordPronunciationList(void)
0x18000cf79  jmp     loc_18000CD58
0x18000cf7e  mov     r13d, 18h
0x18000cf84  mov     [rsp+730h+var_6E0], r13
0x18000cf89  mov     r12, [rsp+730h+var_6C8]
0x18000cf8e  xor     eax, eax
0x18000cf90  mov     r14d, eax
0x18000cf93  test    r15d, r15d
0x18000cf96  jz      loc_18000D0CD
0x18000cf9c  test    r12, r12
0x18000cf9f  jz      loc_18000D0CD
0x18000cfa5  test    ebx, ebx
0x18000cfa7  js      loc_18000D0CD
0x18000cfad  cmp     r14d, esi
0x18000cfb0  jnb     loc_18000D0CD
0x18000cfb6  mov     r15, [rbp+630h+var_6B0]
0x18000cfba  mov     rax, [r15+88h]
0x18000cfc1  mov     rcx, [rax+1C8h]
0x18000cfc8  lea     r13, [r12+14h]
0x18000cfcd  mov     rax, [rcx]
0x18000cfd0  mov     r9, [rbp+630h+var_368]
0x18000cfd7  mov     r8, r13
0x18000cfda  mov     edx, [r12+8]
0x18000cfdf  mov     rax, [rax+0A0h]
0x18000cfe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfeb  mov     ebx, eax
0x18000cfed  test    eax, eax
0x18000cfef  js      loc_18000D0BC
0x18000cff5  mov     rax, [r15+88h]
0x18000cffc  mov     rcx, [rax+1C8h]
0x18000d003  mov     rax, [rcx]
0x18000d006  mov     r8, [rbp+630h+var_688]
0x18000d00a  mov     rdx, [rbp+630h+var_368]
0x18000d011  mov     rax, [rax+98h]
0x18000d018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d01d  mov     ebx, eax
0x18000d01f  test    eax, eax
0x18000d021  js      loc_18000D0BC
0x18000d027  mov     rcx, [rsp+730h+var_6F0]
0x18000d02c  mov     r15d, r14d
0x18000d02f  mov     rax, [rcx]
0x18000d032  mov     r8, [rdi+r15*8]
0x18000d036  mov     rdx, [rbp+630h+var_688]
0x18000d03a  mov     rax, [rax+30h]
0x18000d03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d043  mov     ebx, eax
0x18000d045  xor     eax, eax
0x18000d047  test    ebx, ebx
0x18000d049  js      short loc_18000D0BC
0x18000d04b  mov     r11, [rdi+r15*8]
0x18000d04f  or      r10, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
