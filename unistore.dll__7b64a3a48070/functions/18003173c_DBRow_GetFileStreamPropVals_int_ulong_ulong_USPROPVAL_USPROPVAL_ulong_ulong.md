# DBRow::GetFileStreamPropVals(int,ulong,ulong *,_USPROPVAL *,_USPROPVAL * *,ulong *,ulong *)

- ea: `0x18003173c`
- end: `0x180031d06`
- name: `?GetFileStreamPropVals@DBRow@@IEAAJHKPEAKPEAU_USPROPVAL@@PEAPEAU2@00@Z`
- size: `1482`
- prototype: `__int64 __fastcall(DBRow *__hidden this, int, unsigned int, unsigned int *, struct _USPROPVAL *, struct _USPROPVAL **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task`

## callers

- `0x18002ea70`

## callees

- `0x180004464`
- `0x1800068f0`
- `0x18001aadc`
- `0x18001abf4`
- `0x180028ef4`
- `0x18003173c`
- `0x180031d0c`
- `0x180031d70`
- `0x18006f180`
- `0x180078a40`
- `0x180079030`
- `0x1800c5092`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031bfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031bfd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800317fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800317fc`

## string_xrefs

- `0x18003179d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180031ab3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180031af9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180031bac`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180031be1`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBRow::GetFileStreamPropVals(
        DBRow *this,
        int a2,
        unsigned int a3,
        unsigned int *a4,
        struct _USPROPVAL *a5,
        struct _USPROPVAL **a6,
        unsigned int *a7,
        unsigned int *a8)
{
  DBRow *v8; // rbx
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  char *v15; // rdi
  __m128i si128; // xmm6
  unsigned int v17; // r13d
  char *v18; // r14
  unsigned int v19; // r12d
  _BYTE *v20; // rsi
  void *v21; // r15
  struct _USPROPVAL *v22; // rbx
  unsigned int v23; // r12d
  unsigned __int64 v24; // r14
  char *v25; // rdi
  char *v26; // rax
  __int16 v27; // cx
  __int64 i; // rdi
  int OneFileStreamPropValImpl; // eax
  __int64 v30; // rdx
  unsigned int v31; // ebx
  __int16 v32; // ax
  char *v33; // rbx
  char v34; // al
  char *v35; // rcx
  int v36; // eax
  unsigned __int64 v37; // rax
  char *v38; // r13
  __int64 v39; // r12
  __int64 v40; // rdx
  _QWORD *v41; // rbx
  __int64 v42; // r8
  char *v43; // r12
  __int64 v44; // rcx
  __int64 v45; // rdi
  char v46; // bl
  __int64 v47; // r9
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // r8
  HLOCAL *v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // r8
  HLOCAL v55; // rcx
  __int64 v56; // r9
  __int64 v57; // rdx
  HLOCAL *p_hMem; // rcx
  HLOCAL v59; // rax
  unsigned int v60; // edx
  __int64 v61; // xmm1_8
  __int64 v62; // rax
  HLOCAL hMem; // [rsp+38h] [rbp-91h] BYREF
  __int64 v64; // [rsp+40h] [rbp-89h]
  struct _USPROPVAL *v65; // [rsp+48h] [rbp-81h] BYREF
  void *v66; // [rsp+50h] [rbp-79h] BYREF
  char *v67; // [rsp+58h] [rbp-71h]
  char *v68; // [rsp+60h] [rbp-69h]
  char *v69; // [rsp+68h] [rbp-61h]
  void *Block; // [rsp+70h] [rbp-59h] BYREF
  char *v71; // [rsp+78h] [rbp-51h]
  char *v72; // [rsp+80h] [rbp-49h]
  __int128 v73; // [rsp+88h] [rbp-41h] BYREF
  __int64 v74; // [rsp+98h] [rbp-31h]
  __m128i v75; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v76; // [rsp+B0h] [rbp-19h]

  v8 = this;
  v9 = (*(__int64 (__fastcall **)(DBRow *))(*(_QWORD *)this + 32LL))(this);
  if ( v9 >= 0x36 || (v11 = 24LL * v9, (dword_18010A17C[v11] & 0x10000) != 0) )
    Log_AssertionEvent(
      v11 * 4,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      8235);
  utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
    &Block,
    v10,
    v12);
  utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
    &v66,
    v13,
    v14);
  v15 = v67;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v17 = 0;
  v18 = v71;
  v19 = 0;
  v20 = Block;
  v21 = v66;
  LODWORD(v64) = 0;
  LODWORD(v65) = 0;
  v69 = v67;
  while ( v19 < a3 )
  {
    v74 = 0;
    hMem = 0;
    v73 = 0;
    OneFileStreamPropValImpl = DBRow::GetOneFileStreamPropValImpl(
                                 v8,
                                 a4[v19],
                                 (struct _USPROPVAL *)((char *)a5 + 24 * v19),
                                 (struct _USPROPVAL *)&v73,
                                 (WCHAR *)&hMem);
    v31 = OneFileStreamPropValImpl;
    if ( (unsigned int)(OneFileStreamPropValImpl + 2147024894) <= 1 )
    {
      v32 = 256;
      WORD3(v73) = 256;
    }
    else
    {
      if ( OneFileStreamPropValImpl < 0 )
      {
        v56 = 8246;
        v57 = 1;
        goto LABEL_60;
      }
      v32 = WORD3(v73);
    }
    if ( a2 && (v32 & 0x100) != 0 )
    {
      v55 = hMem;
      goto LABEL_49;
    }
    if ( v18 == v72 )
    {
      v33 = (char *)((char *)&v73 - v20);
      v34 = utl::vector<_USPROPVAL,utl::allocator<_USPROPVAL>>::_Grow(&Block, v30, 0);
      v20 = Block;
      v18 = v71;
      if ( v34 )
      {
        v35 = (char *)&v73;
        if ( (unsigned __int64)v33 < v71 - (_BYTE *)Block )
          v35 = (char *)Block + (_QWORD)v33;
        v36 = 1;
        *(_OWORD *)v71 = *(_OWORD *)v35;
        *((_QWORD *)v18 + 2) = *((_QWORD *)v35 + 2);
        v18 += 24;
        v71 = v18;
      }
      else
      {
        v36 = 0;
      }
      if ( !v36 )
      {
        v56 = 8250;
        v57 = 0;
        v31 = -2147024882;
LABEL_60:
        Log_UnistoreHREvent_0(
          v31,
          v57,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          v56);
        if ( hMem )
          LocalFree(hMem);
LABEL_40:
        utl::vector<auto_local_ptr<unsigned char>,utl::allocator<auto_local_ptr<unsigned char>>>::_Uninit(
          &v66,
          v49,
          v50);
        if ( v20 != (_BYTE *)-1LL )
          operator delete(v20);
        return v31;
      }
    }
    else
    {
      v61 = v74;
      *(_OWORD *)v18 = v73;
      *((_QWORD *)v18 + 2) = v61;
      v18 += 24;
      v71 = v18;
    }
    if ( v15 == v68 )
    {
      v37 = 7 * ((unsigned __int64)((v68 - (_BYTE *)v21) >> 3) >> 2) + 8;
      if ( v37 > 0xFFFFFFFFFFFFFFFLL )
        v37 = 0xFFFFFFFFFFFFFFFLL;
      if ( (v68 - (_BYTE *)v21) >> 3 >= v37 )
      {
LABEL_38:
        v47 = 8251;
        v48 = 0;
        v31 = -2147024882;
        goto LABEL_44;
      }
      v38 = (char *)((char *)&hMem - (_BYTE *)v21);
      v39 = v37;
      v41 = operator new(8 * v37, (const struct std::nothrow_t *)&std::nothrow);
      v42 = 0;
      v75.m128i_i64[0] = (__int64)v41;
      if ( v41 )
      {
        v43 = (char *)&v41[v39];
        v75.m128i_i64[1] = (__int64)v41;
        *(_QWORD *)&v76 = v43;
        if ( v41 != (_QWORD *)-1LL )
        {
          v44 = 0;
          v45 = (v15 - (_BYTE *)v21) >> 3;
          while ( v44 != v45 )
          {
            v62 = *((_QWORD *)v21 + v44);
            *((_QWORD *)v21 + v44) = 0;
            v41[v44++] = v62;
          }
          v15 = (char *)&v41[v45];
          utl::vector<auto_local_ptr<unsigned char>,utl::allocator<auto_local_ptr<unsigned char>>>::_Uninit(
            &v66,
            v40,
            0);
          v21 = v41;
          v66 = v41;
          v46 = 1;
          v67 = v15;
          v68 = v43;
          v75 = si128;
          *(_QWORD *)&v76 = -1;
          goto LABEL_37;
        }
      }
      else
      {
        v75 = si128;
        *(_QWORD *)&v76 = -1;
      }
      v46 = 0;
LABEL_37:
      utl::vector<auto_local_ptr<unsigned char>,utl::allocator<auto_local_ptr<unsigned char>>>::_Uninit(&v75, v40, v42);
      if ( !v46 )
        goto LABEL_38;
      p_hMem = &hMem;
      if ( (unsigned __int64)v38 < v15 - (_BYTE *)v21 )
        p_hMem = (HLOCAL *)&v38[(_QWORD)v21];
      v59 = *p_hMem;
      v17 = v64;
      v19 = (unsigned int)v65;
      *p_hMem = 0;
      v55 = hMem;
      goto LABEL_68;
    }
    v59 = hMem;
    v55 = 0;
    hMem = 0;
LABEL_68:
    *(_QWORD *)v15 = v59;
    v60 = v17 + 24;
    v15 += 8;
    v67 = v15;
    v69 = v15;
    if ( v17 + 24 < v17 )
    {
      v47 = 8253;
LABEL_43:
      v48 = 1;
      v31 = -2147024362;
LABEL_44:
      Log_UnistoreHREvent_0(
        v31,
        v48,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        v47);
      v51 = &hMem;
LABEL_45:
      auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(v51);
      utl::vector<auto_local_ptr<unsigned char>,utl::allocator<auto_local_ptr<unsigned char>>>::_Uninit(&v66, v52, v53);
      utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Block);
      return v31;
    }
    v17 = v60 + ((DWORD2(v73) + 3) & 0xFFFFFFFC);
    LODWORD(v64) = v17;
    if ( v17 < v60 )
    {
      v47 = 8254;
      goto LABEL_43;
    }
LABEL_49:
    if ( v55 )
      LocalFree(v55);
    v8 = this;
    LODWORD(v65) = ++v19;
  }
  v65 = (struct _USPROPVAL *)LocalAlloc(0x40u, v17);
  v22 = v65;
  if ( !v65 )
  {
    v31 = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      8260);
    goto LABEL_40;
  }
  v23 = 0;
  v24 = 0xAAAAAAAAAAAAAAABuLL * ((v18 - v20) >> 3);
  if ( v24 )
  {
    v25 = (char *)v65 + 24 * v24;
    do
    {
      v26 = 0;
      v27 = *(_WORD *)&v20[24 * v23 + 6] & 0x100;
      if ( !v27 )
        v26 = v25;
      *(_OWORD *)((char *)v22 + 24 * v23) = *(_OWORD *)&v20[24 * v23];
      *((_QWORD *)v22 + 3 * v23 + 2) = v26;
      if ( !v27 )
      {
        memcpy_0(v25, *((const void **)v21 + v23), *(unsigned int *)&v20[24 * v23 + 8]);
        v25 += (*(unsigned int *)&v20[24 * v23 + 8] + 3LL) & 0xFFFFFFFFFFFFFFFCuLL;
      }
      ++v23;
    }
    while ( v23 < v24 );
    v15 = v69;
    v17 = v64;
  }
  if ( v24 > 0xFFFFFFFF )
  {
    *a8 = -1;
    v31 = -2147024362;
    Log_UnistoreHREvent_0(
      2147942934LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      8277);
    v51 = (HLOCAL *)&v65;
    goto LABEL_45;
  }
  *a8 = v24;
  *a7 = v17;
  *a6 = v22;
  if ( v21 != (void *)-1LL )
  {
    for ( i = (v15 - (_BYTE *)v21) >> 3;
          i;
          auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>((char *)v21 + 8 * i) )
    {
      --i;
    }
    operator delete(v21);
  }
  if ( v20 != (_BYTE *)-1LL )
    operator delete(v20);
  return 0;
}

```

## disassembly

```asm
0x18003173c  mov     rax, rsp
0x18003173f  mov     [rax+20h], r9
0x180031743  mov     [rax+18h], r8d
0x180031747  mov     [rax+10h], edx
0x18003174a  mov     [rax+8], rcx
0x18003174e  push    rbp
0x18003174f  push    rbx
0x180031750  push    rsi
0x180031751  push    rdi
0x180031752  push    r12
0x180031754  push    r13
0x180031756  push    r14
0x180031758  push    r15
0x18003175a  lea     rbp, [rax-47h]
0x18003175e  sub     rsp, 0C8h
0x180031765  movaps  xmmword ptr [rax-58h], xmm6
0x180031769  mov     rbx, rcx
0x18003176c  mov     rax, [rcx]
0x18003176f  mov     rax, [rax+20h]
0x180031773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031778  cmp     eax, 36h ; '6'
0x18003177b  jnb     short loc_180031797
0x18003177d  mov     eax, eax
0x18003177f  lea     rcx, [rax+rax*2]
0x180031783  shl     rcx, 5
0x180031787  lea     rax, dword_18010A17C
0x18003178e  test    dword ptr [rcx+rax], 10000h
0x180031795  jz      short loc_1800317A9
0x180031797  mov     r8d, 202Bh
0x18003179d  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800317a4  call    Log_AssertionEvent
0x1800317a9  lea     rcx, [rbp+3Fh+Block]
0x1800317ad  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x1800317b2  lea     rcx, [rbp+3Fh+var_B8]
0x1800317b6  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x1800317bb  mov     rdi, [rbp+3Fh+var_B0]
0x1800317bf  xor     r8d, r8d
0x1800317c2  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800317ca  mov     r13d, r8d
0x1800317cd  mov     r14, [rbp+3Fh+var_90]
0x1800317d1  mov     r12d, r8d
0x1800317d4  mov     rsi, [rbp+3Fh+Block]
0x1800317d8  mov     r15, [rbp+3Fh+var_B8]
0x1800317dc  mov     dword ptr [rsp+100h+var_C8], r8d
0x1800317e1  mov     dword ptr [rsp+100h+var_C0], r8d
0x1800317e6  mov     [rbp+3Fh+var_A0], rdi
0x1800317ea  cmp     r12d, [rbp+3Fh+arg_10]
0x1800317ee  jb      loc_1800318DF
0x1800317f4  mov     edx, r13d; uBytes
0x1800317f7  mov     ecx, 40h ; '@'; uFlags
0x1800317fc  call    cs:__imp_LocalAlloc
0x180031802  xor     r8d, r8d
0x180031805  mov     [rsp+100h+var_C0], rax
0x18003180a  mov     rbx, rax
0x18003180d  test    rax, rax
0x180031810  jz      loc_180031AAE
0x180031816  sub     r14, rsi
0x180031819  mov     rax, 0AAAAAAAAAAAAAAABh
0x180031823  sar     r14, 3
0x180031827  mov     r12d, r8d
0x18003182a  imul    r14, rax
0x18003182e  lea     rax, [r14+r14*2]
0x180031832  lea     rcx, [rbx+rax*8]
0x180031836  test    r14, r14
0x180031839  jz      short loc_1800318A3
0x18003183b  mov     rdi, rcx
0x18003183e  mov     edx, r12d
0x180031841  mov     ecx, 100h
0x180031846  mov     rax, r8
0x180031849  lea     r13, [rdx+rdx*2]
0x18003184d  and     cx, [rsi+r13*8+6]
0x180031853  movups  xmm0, xmmword ptr [rsi+r13*8]
0x180031858  cmovz   rax, rdi
0x18003185c  movups  xmmword ptr [rbx+r13*8], xmm0
0x180031861  mov     [rbx+r13*8+10h], rax
0x180031866  test    cx, cx
0x180031869  jnz     short loc_18003188F
0x18003186b  mov     r8d, [rsi+r13*8+8]; Size
0x180031870  mov     rcx, rdi; void *
0x180031873  mov     rdx, [r15+rdx*8]; Src
0x180031877  call    memcpy_0
0x18003187c  mov     eax, [rsi+r13*8+8]
0x180031881  add     rax, 3
0x180031885  and     rax, 0FFFFFFFFFFFFFFFCh
0x180031889  add     rdi, rax
0x18003188c  xor     r8d, r8d
0x18003188f  inc     r12d
0x180031892  mov     eax, r12d
0x180031895  cmp     rax, r14
0x180031898  jb      short loc_18003183E
0x18003189a  mov     rdi, [rbp+3Fh+var_A0]
0x18003189e  mov     r13d, dword ptr [rsp+100h+var_C8]
0x1800318a3  mov     rax, [rbp+3Fh+arg_38]
0x1800318aa  mov     ecx, 0FFFFFFFFh
0x1800318af  cmp     r14, rcx
0x1800318b2  ja      loc_180031BAA
0x1800318b8  mov     [rax], r14d
0x1800318bb  mov     rax, [rbp+3Fh+arg_30]
0x1800318bf  mov     [rax], r13d
0x1800318c2  mov     rax, [rbp+3Fh+arg_28]
0x1800318c6  mov     [rax], rbx
0x1800318c9  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800318cd  jz      loc_180031B8E
0x1800318d3  sub     rdi, r15
0x1800318d6  sar     rdi, 3
0x1800318da  jmp     loc_180031B7A
0x1800318df  mov     rcx, [rbp+3Fh+arg_20]
0x1800318e3  lea     r9, [rbp+3Fh+var_80]; struct _USPROPVAL *
0x1800318e7  xor     eax, eax
0x1800318e9  mov     edx, r12d
0x1800318ec  mov     [rbp+3Fh+var_70], rax
0x1800318f0  xorps   xmm0, xmm0
0x1800318f3  mov     [rsp+100h+hMem], r8
0x1800318f8  movups  [rbp+3Fh+var_80], xmm0
0x1800318fc  lea     rax, [rdx+rdx*2]
0x180031900  lea     r8, [rcx+rax*8]; struct _USPROPVAL *
0x180031904  mov     rcx, rbx; this
0x180031907  lea     rax, [rsp+100h+hMem]
0x18003190c  mov     [rsp+20h], rax; unsigned __int8 **
0x180031911  mov     rax, [rbp+3Fh+arg_18]
0x180031915  mov     edx, [rax+rdx*4]; unsigned int
0x180031918  call    ?GetOneFileStreamPropValImpl@DBRow@@IEAAJKAEBU_USPROPVAL@@PEAU2@PEAPEAE@Z; DBRow::GetOneFileStreamPropValImpl(ulong,_USPROPVAL const &,_USPROPVAL *,uchar * *)
0x18003191d  xor     r8d, r8d
0x180031920  mov     ebx, eax
0x180031922  lea     ecx, [rax+7FF8FFFEh]
0x180031928  cmp     ecx, 1
0x18003192b  jbe     loc_180031C9F
0x180031931  test    eax, eax
0x180031933  js      loc_180031C1D
0x180031939  movzx   eax, word ptr [rbp+3Fh+var_80+6]
0x18003193d  mov     ecx, 100h
0x180031942  cmp     [rbp+3Fh+arg_8], r8d
0x180031946  jnz     loc_180031B41
0x18003194c  cmp     r14, [rbp+3Fh+var_88]
0x180031950  jnz     loc_180031CAF
0x180031956  lea     rbx, [rbp+3Fh+var_80]
0x18003195a  lea     rcx, [rbp+3Fh+Block]
0x18003195e  sub     rbx, rsi
0x180031961  call    ?_Grow@?$vector@U_USPROPVAL@@V?$allocator@U_USPROPVAL@@@utl@@@utl@@AEAA_NXZ; utl::vector<_USPROPVAL,utl::allocator<_USPROPVAL>>::_Grow(void)
0x180031966  mov     rsi, [rbp+3Fh+Block]
0x18003196a  xor     r8d, r8d
0x18003196d  mov     r14, [rbp+3Fh+var_90]
0x180031971  test    al, al
0x180031973  jz      loc_180031CCF
0x180031979  mov     rax, r14
0x18003197c  lea     rcx, [rbp+3Fh+var_80]
0x180031980  sub     rax, rsi
0x180031983  cmp     rbx, rax
0x180031986  jnb     short loc_18003198C
0x180031988  lea     rcx, [rbx+rsi]
0x18003198c  movups  xmm0, xmmword ptr [rcx]
0x18003198f  mov     eax, 1
0x180031994  movups  xmmword ptr [r14], xmm0
0x180031998  movsd   xmm1, qword ptr [rcx+10h]
0x18003199d  movsd   qword ptr [r14+10h], xmm1
0x1800319a3  add     r14, 18h
0x1800319a7  mov     [rbp+3Fh+var_90], r14
0x1800319ab  test    eax, eax
0x1800319ad  jz      loc_180031BD4
0x1800319b3  mov     rax, [rbp+3Fh+var_A8]
0x1800319b7  cmp     rdi, rax
0x1800319ba  jnz     loc_180031CD7
0x1800319c0  mov     rcx, rax
0x1800319c3  mov     rdx, 0FFFFFFFFFFFFFFFh
0x1800319cd  sub     rcx, r15
0x1800319d0  sar     rcx, 3
0x1800319d4  mov     rax, rcx
0x1800319d7  shr     rax, 2
0x1800319db  imul    rax, 7
0x1800319df  add     rax, 8
0x1800319e3  cmp     rax, rdx
0x1800319e6  cmova   rax, rdx
0x1800319ea  cmp     rcx, rax
0x1800319ed  jnb     loc_180031A9F
0x1800319f3  lea     r13, [rsp+100h+hMem]
0x1800319f8  mov     rcx, 1FFFFFFFFFFFFFFFh
0x180031a02  sub     r13, r15
0x180031a05  lea     r12, ds:0[rax*8]
0x180031a0d  cmp     rax, rcx
0x180031a10  ja      loc_180031C2A
0x180031a16  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180031a1d  mov     rcx, r12; unsigned __int64
0x180031a20  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180031a25  mov     rbx, rax
0x180031a28  xor     r8d, r8d
0x180031a2b  mov     qword ptr [rbp+3Fh+var_68], rbx
0x180031a2f  test    rbx, rbx
0x180031a32  jz      loc_180031C08
0x180031a38  add     r12, rbx
0x180031a3b  mov     qword ptr [rbp+3Fh+var_68+8], rbx
0x180031a3f  mov     qword ptr [rbp+3Fh+var_58], r12
0x180031a43  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180031a47  jz      loc_180031C15
0x180031a4d  sub     rdi, r15
0x180031a50  mov     rcx, r8
0x180031a53  sar     rdi, 3
0x180031a57  cmp     rcx, rdi
0x180031a5a  jnz     loc_180031CE9
0x180031a60  lea     rcx, [rbp+3Fh+var_B8]
0x180031a64  lea     rdi, [rbx+rdi*8]
0x180031a68  call    ?_Uninit@?$vector@V?$auto_local_ptr@E@@V?$allocator@V?$auto_local_ptr@E@@@utl@@@utl@@AEAAXXZ; utl::vector<auto_local_ptr<uchar>,utl::allocator<auto_local_ptr<uchar>>>::_Uninit(void)
0x180031a6d  mov     r15, rbx
0x180031a70  mov     [rbp+3Fh+var_B8], rbx
0x180031a74  mov     bl, 1
0x180031a76  mov     [rbp+3Fh+var_B0], rdi
0x180031a7a  mov     [rbp+3Fh+var_A8], r12
0x180031a7e  movdqu  [rbp+3Fh+var_68], xmm6
0x180031a83  mov     qword ptr [rbp+3Fh+var_58], 0FFFFFFFFFFFFFFFFh
0x180031a8b  lea     rcx, [rbp+3Fh+var_68]
0x180031a8f  call    ?_Uninit@?$vector@V?$auto_local_ptr@E@@V?$allocator@V?$auto_local_ptr@E@@@utl@@@utl@@AEAAXXZ; utl::vector<auto_local_ptr<uchar>,utl::allocator<auto_local_ptr<uchar>>>::_Uninit(void)
0x180031a94  xor     r8d, r8d
0x180031a97  test    bl, bl
0x180031a99  jnz     loc_180031C32
0x180031a9f  mov     r9d, 203Bh
0x180031aa5  xor     edx, edx
0x180031aa7  mov     ebx, 8007000Eh
0x180031aac  jmp     short loc_180031AF9
0x180031aae  mov     ebx, 8007000Eh
0x180031ab3  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180031aba  mov     ecx, ebx
0x180031abc  mov     r9d, 2044h
0x180031ac2  xor     edx, edx
0x180031ac4  call    Log_UnistoreHREvent_0
0x180031ac9  lea     rcx, [rbp+3Fh+var_B8]
0x180031acd  call    ?_Uninit@?$vector@V?$auto_local_ptr@E@@V?$allocator@V?$auto_local_ptr@E@@@utl@@@utl@@AEAAXXZ; utl::vector<auto_local_ptr<uchar>,utl::allocator<auto_local_ptr<uchar>>>::_Uninit(void)
0x180031ad2  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180031ad6  jz      short loc_180031B23
0x180031ad8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180031adf  mov     rcx, rsi; Block
0x180031ae2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031ae7  jmp     short loc_180031B23
0x180031ae9  mov     r9d, 203Dh
0x180031aef  mov     edx, 1
0x180031af4  mov     ebx, 80070216h
0x180031af9  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180031b00  mov     ecx, ebx
0x180031b02  call    Log_UnistoreHREvent_0
0x180031b07  lea     rcx, [rsp+100h+hMem]
0x180031b0c  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x180031b11  lea     rcx, [rbp+3Fh+var_B8]
0x180031b15  call    ?_Uninit@?$vector@V?$auto_local_ptr@E@@V?$allocator@V?$auto_local_ptr@E@@@utl@@@utl@@AEAAXXZ; utl::vector<auto_local_ptr<uchar>,utl::allocator<auto_local_ptr<uchar>>>::_Uninit(void)
0x180031b1a  lea     rcx, [rbp+3Fh+Block]
0x180031b1e  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x180031b23  mov     eax, ebx
0x180031b25  movaps  xmm6, [rsp+100h+var_58+8]
0x180031b2d  add     rsp, 0C8h
0x180031b34  pop     r15
0x180031b36  pop     r14
0x180031b38  pop     r13
0x180031b3a  pop     r12
0x180031b3c  pop     rdi
0x180031b3d  pop     rsi
0x180031b3e  pop     rbx
0x180031b3f  pop     rbp
0x180031b40  retn
0x180031b41  test    cx, ax
0x180031b44  jz      loc_18003194C
0x180031b4a  mov     rcx, [rsp+100h+hMem]; hMem
0x180031b4f  test    rcx, rcx
0x180031b52  jz      short loc_180031B5D
0x180031b54  call    cs:__imp_LocalFree
0x180031b5a  xor     r8d, r8d
0x180031b5d  mov     rbx, [rbp+3Fh+arg_0]
0x180031b61  inc     r12d
0x180031b64  mov     dword ptr [rsp+100h+var_C0], r12d
0x180031b69  jmp     loc_1800317EA
0x180031b6e  dec     rdi
0x180031b71  lea     rcx, [r15+rdi*8]
0x180031b75  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x180031b7a  test    rdi, rdi
0x180031b7d  jnz     short loc_180031B6E
0x180031b7f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180031b86  mov     rcx, r15; Block
0x180031b89  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031b8e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180031b92  jz      short loc_180031BA3
0x180031b94  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180031b9b  mov     rcx, rsi; Block
0x180031b9e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031ba3  xor     eax, eax
0x180031ba5  jmp     loc_180031B25
0x180031baa  mov     [rax], ecx
0x180031bac  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180031bb3  mov     ebx, 80070216h
0x180031bb8  mov     r9d, 2055h
0x180031bbe  mov     ecx, ebx
0x180031bc0  mov     edx, 1
0x180031bc5  call    Log_UnistoreHREvent_0
0x180031bca  lea     rcx, [rsp+100h+var_C0]
0x180031bcf  jmp     loc_180031B0C
0x180031bd4  mov     r9d, 203Ah
0x180031bda  xor     edx, edx
0x180031bdc  mov     ebx, 8007000Eh
0x180031be1  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180031be8  mov     ecx, ebx
0x180031bea  call    Log_UnistoreHREvent_0
0x180031bef  mov     rcx, [rsp+100h+hMem]; hMem
0x180031bf4  test    rcx, rcx
0x180031bf7  jz      loc_180031AC9
0x180031bfd  call    cs:__imp_LocalFree
  ... truncated ...
```
