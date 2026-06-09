# DBManager::SelectTableSortIndex(US_TABLEID,ulong,US_SORTSPEC *,_USRestriction const *,_USRestriction * *,ulong *,ulong *,unsigned __int64 *)

- ea: `0x1800429b0`
- end: `0x180042ec5`
- name: `?SelectTableSortIndex@DBManager@@IEAAJW4US_TABLEID@@KPEAUUS_SORTSPEC@@PEBU_USRestriction@@PEAPEAU4@PEAK4PEA_K@Z`
- size: `1301`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task`

## callers

- `0x180042580`

## callees

- `0x180004464`
- `0x1800068f0`
- `0x18001abf4`
- `0x1800429b0`
- `0x180042ed0`
- `0x180043680`
- `0x18004446c`
- `0x18004dcc0`
- `0x18006f180`
- `0x180078a40`
- `0x18007f00c`
- `0x180097324`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042e9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042e9e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042bcf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042bcf`

## string_xrefs

- `0x180042a0d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180042a28`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180042be3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180042c0c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180042d05`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180042d8a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180042de8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180042e3c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180042e88`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBManager::SelectTableSortIndex(
        DBManager *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        struct _USRestriction *a5,
        unsigned int **a6,
        struct _USRestriction *a7,
        int *a8,
        _QWORD *a9)
{
  __int64 v9; // r14
  unsigned int v11; // r12d
  __int64 v12; // rcx
  struct _USRestriction *v13; // rbx
  unsigned int v14; // r15d
  int *v15; // rdi
  __int64 v16; // rsi
  struct _USRestriction *v17; // r15
  __int64 v18; // rdx
  __int64 v19; // r8
  int v20; // eax
  int BestMatchSortIndex; // r14d
  unsigned __int64 v22; // r14
  int v24; // edx
  __int64 v25; // rcx
  _BYTE *v26; // r8
  unsigned int **v27; // rbx
  unsigned int *v28; // rax
  unsigned int *v29; // rdi
  int v30; // esi
  int PropertyRestrictions; // eax
  __int64 v32; // r9
  __int64 v33; // rdx
  __int64 v34; // rcx
  _DWORD *v35; // r9
  unsigned int v36; // eax
  __int64 v37; // rcx
  _DWORD *v38; // r8
  int v39; // eax
  __int64 v40; // r9
  __int64 v41; // r9
  int v42; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int64 v43; // [rsp+68h] [rbp-41h] BYREF
  _QWORD v44[2]; // [rsp+70h] [rbp-39h] BYREF
  void *Block; // [rsp+80h] [rbp-29h] BYREF
  _BYTE *v46; // [rsp+88h] [rbp-21h]
  _QWORD v47[9]; // [rsp+98h] [rbp-11h] BYREF
  int v49; // [rsp+F8h] [rbp+4Fh] BYREF

  v9 = (int)a2;
  v11 = a3;
  utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
    &Block,
    a2,
    a3);
  v13 = a7;
  v14 = 0;
  v49 = 0;
  v42 = 0;
  v43 = 0;
  v44[0] = 4;
  v44[1] = 0;
  if ( !a7 )
    Log_AssertionEvent(
      v12,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      1793);
  v15 = a8;
  if ( !a8 )
    Log_AssertionEvent(
      v12,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      1794);
  *(_DWORD *)v13 = 0;
  v16 = 12 * v9;
  *v15 = 0;
  if ( (*((_DWORD *)&g_rgTableInfo + 24 * v9 + 11) & 0x40000) != 0 )
  {
    while ( v14 < v11 )
    {
      if ( (GetPropSchemaFlags((unsigned int)v9, *(unsigned int *)(a4 + 8LL * v14)) & 0x10000000) != 0 )
      {
        Log_UnistoreHREvent_0(
          2147746004LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          1799);
        if ( Block != (void *)-1LL )
        {
          v46 = Block;
          operator delete(Block);
        }
        return 2147746004LL;
      }
      ++v14;
    }
  }
  v17 = a5;
  LODWORD(a7) = DBManager::ProcessRestrictionSortSpec(
                  (_DWORD)a1,
                  (_DWORD)a5,
                  (unsigned int)&Block,
                  (unsigned int)v44,
                  (__int64)&v49,
                  (__int64)&v42);
  if ( (int)a7 < 0 )
  {
    utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Block);
    return (unsigned int)a7;
  }
  v20 = v44[0];
  if ( (*((_DWORD *)&g_rgTableInfo + 2 * v16 + 11) & 0x40000) != 0 )
  {
    if ( LODWORD(v44[0]) == 4 )
    {
      if ( !v49 )
        goto LABEL_8;
    }
    else if ( (GetPropSchemaFlags((unsigned int)v9, HIDWORD(v44[0])) & 0x10000000) != 0 )
    {
      Log_UnistoreHREvent_0(
        2147746004LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        1730);
      goto LABEL_51;
    }
    utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
      v47,
      v18,
      v19);
    PropertyRestrictions = GetPropertyRestrictions(v17, v47);
    if ( PropertyRestrictions >= 0 )
    {
      v35 = Block;
      v36 = 0;
      while ( 2 )
      {
        LODWORD(a7) = v36;
        if ( v36 >= (unsigned __int64)((__int64)(v47[1] - v47[0]) >> 3) )
        {
          utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(v47);
          v20 = v44[0];
          goto LABEL_8;
        }
        v37 = 0;
        v38 = (_DWORD *)(v47[0] + 8LL * v36);
        while ( (unsigned int)v37 < (unsigned __int64)((v46 - (_BYTE *)v35) >> 3) )
        {
          if ( *v38 == v35[2 * v37] )
            goto LABEL_48;
          v37 = (unsigned int)(v37 + 1);
        }
        if ( (GetPropSchemaFlags((unsigned int)v9, (unsigned int)*v38) & 0x10000000) == 0 )
        {
          v35 = Block;
LABEL_48:
          v36 = (_DWORD)a7 + 1;
          continue;
        }
        break;
      }
      v32 = 1752;
      v33 = 0;
      v34 = 2147746004LL;
    }
    else
    {
      v32 = 1735;
      v33 = 1;
      v34 = (unsigned int)PropertyRestrictions;
    }
    Log_UnistoreHREvent_0(
      v34,
      v33,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v32);
    utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(v47);
LABEL_51:
    utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Block);
    return 2147746004LL;
  }
LABEL_8:
  BestMatchSortIndex = DBManager::GetBestMatchSortIndex(
                         (unsigned int)&v42,
                         v9,
                         v11,
                         a4,
                         (__int64)&Block,
                         v20,
                         (__int64)v13,
                         (__int64)v15,
                         (__int64)&v42,
                         (__int64)&v49,
                         (__int64)&v43);
  if ( BestMatchSortIndex < 0 )
  {
    utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Block);
    return (unsigned int)BestMatchSortIndex;
  }
  v22 = v43;
  if ( v17 && !v43 )
  {
    if ( Block != (void *)-1LL )
    {
      v46 = Block;
      operator delete(Block);
    }
    return 2147500037LL;
  }
  if ( v42 )
  {
    v22 = v43 + 1;
    *v15 |= 8u;
  }
  v24 = v49;
  v25 = 68LL * *(unsigned int *)v13;
  v43 = v22;
  if ( ((&g_rgTableInfo)[v16 + 2][v25 + 2] & 0x8000u) != 0 )
  {
    v39 = *v15;
    if ( (*v15 & 2) != 0 )
    {
      v40 = 1838;
    }
    else if ( (v39 & 8) != 0 )
    {
      v40 = 1839;
    }
    else if ( v49 )
    {
      v40 = 1842;
    }
    else
    {
      if ( LODWORD(v44[0]) <= 4 )
      {
        *v15 = v39 | 0x10;
        goto LABEL_17;
      }
      v40 = 1847;
    }
    Log_UnistoreHREvent_0(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v40);
    utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Block);
    return 2147942487LL;
  }
LABEL_17:
  v26 = Block;
  v27 = a6;
  *a9 = ((v46 - (_BYTE *)Block) >> 3) - v22;
  if ( v24 )
  {
    if ( !v27 )
    {
      Log_UnistoreHREvent_0(
        2147500037LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        1860);
      utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Block);
      return 2147500037LL;
    }
    v28 = (unsigned int *)LocalAlloc(0x40u, 24 * (v22 + 1));
    v29 = v28;
    if ( !v28 )
    {
      Log_UnistoreHREvent_0(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        1863);
      utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Block);
      return 2147942414LL;
    }
    a7 = (struct _USRestriction *)v28;
    if ( v22 > 1 )
    {
      *v28 = 0;
      v30 = ULongLongToULong(v22, v28 + 2);
      if ( v30 < 0 )
      {
        v41 = 1870;
        goto LABEL_68;
      }
      *((_QWORD *)v29 + 2) = v29 + 6;
      a7 = (struct _USRestriction *)(v29 + 6);
    }
    v30 = DBManager::CreatePartialRestriction(a1, v17, &v43, &a7);
    if ( v30 >= 0 )
    {
      v26 = Block;
      *v27 = v29;
      goto LABEL_18;
    }
    v41 = 1876;
LABEL_68:
    Log_UnistoreHREvent_0(
      (unsigned int)v30,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v41);
    LocalFree(v29);
    utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Block);
    return (unsigned int)v30;
  }
LABEL_18:
  if ( v26 != (_BYTE *)-1LL )
  {
    v46 = v26;
    operator delete(v26);
  }
  return 0;
}

```

## disassembly

```asm
0x1800429b0  mov     [rsp-8+arg_10], rbx
0x1800429b5  mov     [rsp-8+arg_0], rcx
0x1800429ba  push    rbp
0x1800429bb  push    rsi
0x1800429bc  push    rdi
0x1800429bd  push    r12
0x1800429bf  push    r13
0x1800429c1  push    r14
0x1800429c3  push    r15
0x1800429c5  lea     rbp, [rsp-7]
0x1800429ca  sub     rsp, 0B0h
0x1800429d1  lea     rcx, [rbp+37h+Block]
0x1800429d5  movsxd  r14, edx
0x1800429d8  mov     r13, r9
0x1800429db  mov     r12d, r8d
0x1800429de  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x1800429e3  mov     rbx, [rbp+37h+arg_30]
0x1800429e7  xor     r15d, r15d
0x1800429ea  mov     [rbp+37h+arg_8], r15d
0x1800429ee  mov     [rbp+37h+var_80], r15d
0x1800429f2  mov     [rbp+37h+var_78], r15
0x1800429f6  mov     [rbp+37h+var_70], 4
0x1800429fe  mov     [rbp+37h+var_68], r15
0x180042a02  test    rbx, rbx
0x180042a05  jnz     short loc_180042A19
0x180042a07  mov     r8d, 701h
0x180042a0d  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042a14  call    Log_AssertionEvent
0x180042a19  mov     rdi, [rbp+37h+arg_38]
0x180042a1d  test    rdi, rdi
0x180042a20  jnz     short loc_180042A34
0x180042a22  mov     r8d, 702h
0x180042a28  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042a2f  call    Log_AssertionEvent
0x180042a34  lea     rsi, [r14+r14*2]
0x180042a38  mov     [rbx], r15d
0x180042a3b  shl     rsi, 5
0x180042a3f  lea     rax, ?g_rgTableInfo@@3QBUUSTableInfo@@B; USTableInfo const near * const g_rgTableInfo
0x180042a46  mov     [rdi], r15d
0x180042a49  test    dword ptr [rsi+rax+2Ch], 40000h
0x180042a51  jnz     loc_180042C7B
0x180042a57  mov     r15, [rbp+37h+arg_20]
0x180042a5b  lea     rax, [rbp+37h+var_80]
0x180042a5f  mov     rcx, [rbp+37h+arg_0]
0x180042a63  lea     r9, [rbp+37h+var_70]
0x180042a67  mov     [rsp+0E0h+var_B8], rax
0x180042a6c  lea     r8, [rbp+37h+Block]
0x180042a70  lea     rax, [rbp+37h+arg_8]
0x180042a74  mov     rdx, r15
0x180042a77  mov     [rsp+0E0h+var_C0], rax
0x180042a7c  call    ?ProcessRestrictionSortSpec@DBManager@@IEAAJPEBU_USRestriction@@PEAV?$vector@UUS_SORTSPEC@@V?$allocator@UUS_SORTSPEC@@@utl@@@utl@@PEAU_USPropertyRestriction@@PEAH3@Z; DBManager::ProcessRestrictionSortSpec(_USRestriction const *,utl::vector<US_SORTSPEC,utl::allocator<US_SORTSPEC>> *,_USPropertyRestriction *,int *,int *)
0x180042a81  mov     dword ptr [rbp+37h+arg_30], eax
0x180042a84  test    eax, eax
0x180042a86  js      loc_180042CA3
0x180042a8c  lea     rax, ?g_rgTableInfo@@3QBUUSTableInfo@@B; USTableInfo const near * const g_rgTableInfo
0x180042a93  test    dword ptr [rsi+rax+2Ch], 40000h
0x180042a9b  mov     eax, dword ptr [rbp+37h+var_70]
0x180042a9e  jnz     loc_180042CB4
0x180042aa4  lea     rcx, [rbp+37h+var_78]
0x180042aa8  mov     r9, r13
0x180042aab  mov     [rsp+0E0h+var_90], rcx
0x180042ab0  mov     r8d, r12d
0x180042ab3  lea     rcx, [rbp+37h+arg_8]
0x180042ab7  mov     edx, r14d
0x180042aba  mov     [rsp+0E0h+var_98], rcx
0x180042abf  lea     rcx, [rbp+37h+var_80]
0x180042ac3  mov     [rsp+0E0h+var_A0], rcx
0x180042ac8  mov     [rsp+0E0h+var_A8], rdi
0x180042acd  mov     [rsp+0E0h+var_B0], rbx
0x180042ad2  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180042ad6  lea     rax, [rbp+37h+Block]
0x180042ada  mov     [rsp+0E0h+var_C0], rax
0x180042adf  call    ?GetBestMatchSortIndex@DBManager@@IEAAJW4US_TABLEID@@KPEAUUS_SORTSPEC@@PEAV?$vector@UUS_SORTSPEC@@V?$allocator@UUS_SORTSPEC@@@utl@@@utl@@W4__MIDL___MIDL_itf_unistore_0000_0000_0002@@PEAK4PEAH5PEA_K@Z; DBManager::GetBestMatchSortIndex(US_TABLEID,ulong,US_SORTSPEC *,utl::vector<US_SORTSPEC,utl::allocator<US_SORTSPEC>> *,__MIDL___MIDL_itf_unistore_0000_0000_0002,ulong *,ulong *,int *,int *,unsigned __int64 *)
0x180042ae4  mov     r14d, eax
0x180042ae7  test    eax, eax
0x180042ae9  js      loc_180042DC3
0x180042aef  mov     r14, [rbp+37h+var_78]
0x180042af3  test    r15, r15
0x180042af6  jz      short loc_180042B1E
0x180042af8  test    r14, r14
0x180042afb  jnz     short loc_180042B1E
0x180042afd  mov     rcx, [rbp+37h+Block]; Block
0x180042b01  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180042b05  jz      short loc_180042B17
0x180042b07  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180042b0e  mov     [rbp+37h+var_58], rcx
0x180042b12  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180042b17  mov     eax, 80004005h
0x180042b1c  jmp     short loc_180042B8F
0x180042b1e  cmp     [rbp+37h+var_80], 0
0x180042b22  jnz     loc_180042BAA
0x180042b28  mov     eax, [rbx]
0x180042b2a  mov     edx, [rbp+37h+arg_8]
0x180042b2d  imul    rcx, rax, 88h
0x180042b34  lea     rax, ?g_rgTableInfo@@3QBUUSTableInfo@@B; USTableInfo const near * const g_rgTableInfo
0x180042b3b  mov     [rbp+37h+var_78], r14
0x180042b3f  mov     rax, [rsi+rax+20h]
0x180042b44  cmp     word ptr [rax+rcx+4], 0
0x180042b4a  jl      loc_180042DD4
0x180042b50  mov     rcx, [rbp+37h+var_58]
0x180042b54  mov     r8, [rbp+37h+Block]
0x180042b58  mov     rax, [rbp+37h+arg_40]
0x180042b5f  sub     rcx, r8
0x180042b62  mov     rbx, [rbp+37h+arg_28]
0x180042b66  sar     rcx, 3
0x180042b6a  sub     rcx, r14
0x180042b6d  mov     [rax], rcx
0x180042b70  test    edx, edx
0x180042b72  jnz     short loc_180042BB5
0x180042b74  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180042b78  jz      short loc_180042B8D
0x180042b7a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180042b81  mov     [rbp+37h+var_58], r8
0x180042b85  mov     rcx, r8; Block
0x180042b88  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180042b8d  xor     eax, eax
0x180042b8f  mov     rbx, [rsp+0E0h+arg_10]
0x180042b97  add     rsp, 0B0h
0x180042b9e  pop     r15
0x180042ba0  pop     r14
0x180042ba2  pop     r13
0x180042ba4  pop     r12
0x180042ba6  pop     rdi
0x180042ba7  pop     rsi
0x180042ba8  pop     rbp
0x180042ba9  retn
0x180042baa  inc     r14
0x180042bad  or      dword ptr [rdi], 8
0x180042bb0  jmp     loc_180042B28
0x180042bb5  test    rbx, rbx
0x180042bb8  jz      loc_180042E36
0x180042bbe  lea     rdx, [r14+1]
0x180042bc2  mov     ecx, 40h ; '@'; uFlags
0x180042bc7  lea     rdx, [rdx+rdx*2]
0x180042bcb  shl     rdx, 3; uBytes
0x180042bcf  call    cs:__imp_LocalAlloc
0x180042bd5  mov     rdi, rax
0x180042bd8  test    rax, rax
0x180042bdb  jnz     short loc_180042C43
0x180042bdd  mov     r9d, 747h
0x180042be3  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042bea  xor     edx, edx
0x180042bec  mov     ecx, 8007000Eh
0x180042bf1  call    Log_UnistoreHREvent_0
0x180042bf6  lea     rcx, [rbp+37h+Block]
0x180042bfa  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x180042bff  mov     eax, 8007000Eh
0x180042c04  jmp     short loc_180042B8F
0x180042c06  mov     r9d, 707h
0x180042c0c  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042c13  xor     edx, edx
0x180042c15  mov     ecx, 800400D4h
0x180042c1a  call    Log_UnistoreHREvent_0
0x180042c1f  mov     rcx, [rbp+37h+Block]; Block
0x180042c23  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180042c27  jz      short loc_180042C39
0x180042c29  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180042c30  mov     [rbp+37h+var_58], rcx
0x180042c34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180042c39  mov     eax, 800400D4h
0x180042c3e  jmp     loc_180042B8F
0x180042c43  mov     [rbp+37h+arg_30], rdi
0x180042c47  cmp     r14, 1
0x180042c4b  ja      loc_180042E62
0x180042c51  mov     rcx, [rbp+37h+arg_0]; this
0x180042c55  lea     r9, [rbp+37h+arg_30]; struct _USRestriction **
0x180042c59  lea     r8, [rbp+37h+var_78]; unsigned __int64 *
0x180042c5d  mov     rdx, r15; struct _USRestriction *
0x180042c60  call    ?CreatePartialRestriction@DBManager@@IEAAJPEBU_USRestriction@@PEA_KPEAPEAU2@@Z; DBManager::CreatePartialRestriction(_USRestriction const *,unsigned __int64 *,_USRestriction * *)
0x180042c65  mov     esi, eax
0x180042c67  test    eax, eax
0x180042c69  js      loc_180042E82
0x180042c6f  mov     r8, [rbp+37h+Block]
0x180042c73  mov     [rbx], rdi
0x180042c76  jmp     loc_180042B74
0x180042c7b  cmp     r15d, r12d
0x180042c7e  jnb     loc_180042A57
0x180042c84  mov     edx, r15d
0x180042c87  mov     ecx, r14d
0x180042c8a  mov     edx, [r13+rdx*8+0]
0x180042c8f  call    ?GetPropSchemaFlags@@YAKW4US_TABLEID@@K@Z; GetPropSchemaFlags(US_TABLEID,ulong)
0x180042c94  bt      eax, 1Ch
0x180042c98  jb      loc_180042C06
0x180042c9e  inc     r15d
0x180042ca1  jmp     short loc_180042C7B
0x180042ca3  lea     rcx, [rbp+37h+Block]
0x180042ca7  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x180042cac  mov     eax, dword ptr [rbp+37h+arg_30]
0x180042caf  jmp     loc_180042B8F
0x180042cb4  cmp     eax, 4
0x180042cb7  jnz     short loc_180042CEE
0x180042cb9  cmp     [rbp+37h+arg_8], 0
0x180042cbd  jz      loc_180042AA4
0x180042cc3  lea     rcx, [rbp+37h+var_48]
0x180042cc7  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x180042ccc  lea     rdx, [rbp+37h+var_48]
0x180042cd0  mov     rcx, r15
0x180042cd3  call    ?GetPropertyRestrictions@@YAJPEBU_USRestriction@@PEAV?$vector@UUS_SORTSPEC@@V?$allocator@UUS_SORTSPEC@@@utl@@@utl@@@Z; GetPropertyRestrictions(_USRestriction const *,utl::vector<US_SORTSPEC,utl::allocator<US_SORTSPEC>> *)
0x180042cd8  test    eax, eax
0x180042cda  jns     short loc_180042D1D
0x180042cdc  mov     r9d, 6C7h
0x180042ce2  mov     edx, 1
0x180042ce7  mov     ecx, eax
0x180042ce9  jmp     loc_180042D8A
0x180042cee  mov     edx, dword ptr [rbp+37h+var_70+4]
0x180042cf1  mov     ecx, r14d
0x180042cf4  call    ?GetPropSchemaFlags@@YAKW4US_TABLEID@@K@Z; GetPropSchemaFlags(US_TABLEID,ulong)
0x180042cf9  bt      eax, 1Ch
0x180042cfd  jnb     short loc_180042CC3
0x180042cff  mov     r9d, 6C2h
0x180042d05  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042d0c  xor     edx, edx
0x180042d0e  mov     ecx, 800400D4h
0x180042d13  call    Log_UnistoreHREvent_0
0x180042d18  jmp     loc_180042D9F
0x180042d1d  mov     r9, [rbp+37h+Block]
0x180042d21  xor     eax, eax
0x180042d23  mov     r8, [rbp+37h+var_48]
0x180042d27  mov     edx, eax
0x180042d29  mov     dword ptr [rbp+37h+arg_30], eax
0x180042d2c  mov     rax, [rbp+37h+var_40]
0x180042d30  sub     rax, r8
0x180042d33  sar     rax, 3
0x180042d37  cmp     rdx, rax
0x180042d3a  jnb     short loc_180042DB2
0x180042d3c  xor     ecx, ecx
0x180042d3e  lea     r8, [r8+rdx*8]
0x180042d42  mov     rax, [rbp+37h+var_58]
0x180042d46  sub     rax, r9
0x180042d49  mov     edx, ecx
0x180042d4b  sar     rax, 3
0x180042d4f  cmp     rdx, rax
0x180042d52  jnb     short loc_180042D61
0x180042d54  mov     eax, [r9+rcx*8]
0x180042d58  cmp     [r8], eax
0x180042d5b  jz      short loc_180042D76
0x180042d5d  inc     ecx
0x180042d5f  jmp     short loc_180042D42
0x180042d61  mov     edx, [r8]
0x180042d64  mov     ecx, r14d
0x180042d67  call    ?GetPropSchemaFlags@@YAKW4US_TABLEID@@K@Z; GetPropSchemaFlags(US_TABLEID,ulong)
0x180042d6c  bt      eax, 1Ch
0x180042d70  jb      short loc_180042D7D
0x180042d72  mov     r9, [rbp+37h+Block]
0x180042d76  mov     eax, dword ptr [rbp+37h+arg_30]
0x180042d79  inc     eax
0x180042d7b  jmp     short loc_180042D23
0x180042d7d  mov     r9d, 6D8h
0x180042d83  xor     edx, edx
0x180042d85  mov     ecx, 800400D4h
0x180042d8a  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042d91  call    Log_UnistoreHREvent_0
0x180042d96  lea     rcx, [rbp+37h+var_48]
0x180042d9a  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x180042d9f  lea     rcx, [rbp+37h+Block]
0x180042da3  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x180042da8  mov     eax, 800400D4h
0x180042dad  jmp     loc_180042B8F
0x180042db2  lea     rcx, [rbp+37h+var_48]
0x180042db6  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x180042dbb  mov     eax, dword ptr [rbp+37h+var_70]
0x180042dbe  jmp     loc_180042AA4
0x180042dc3  lea     rcx, [rbp+37h+Block]
0x180042dc7  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x180042dcc  mov     eax, r14d
0x180042dcf  jmp     loc_180042B8F
0x180042dd4  mov     eax, [rdi]
0x180042dd6  test    al, 2
0x180042dd8  jz      short loc_180042E0E
0x180042dda  mov     r9d, 72Eh
0x180042de0  jmp     short loc_180042DE8
0x180042de2  mov     r9d, 737h
0x180042de8  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042def  xor     edx, edx
0x180042df1  mov     ecx, 80070057h
0x180042df6  call    Log_UnistoreHREvent_0
0x180042dfb  lea     rcx, [rbp+37h+Block]
0x180042dff  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x180042e04  mov     eax, 80070057h
0x180042e09  jmp     loc_180042B8F
0x180042e0e  test    al, 8
0x180042e10  jz      short loc_180042E1A
0x180042e12  mov     r9d, 72Fh
0x180042e18  jmp     short loc_180042DE8
0x180042e1a  test    edx, edx
0x180042e1c  jnz     short loc_180042E2E
0x180042e1e  cmp     dword ptr [rbp+37h+var_70], 4
0x180042e22  ja      short loc_180042DE2
0x180042e24  or      eax, 10h
0x180042e27  mov     [rdi], eax
0x180042e29  jmp     loc_180042B50
0x180042e2e  mov     r9d, 732h
0x180042e34  jmp     short loc_180042DE8
0x180042e36  mov     r9d, 744h
0x180042e3c  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042e43  xor     edx, edx
0x180042e45  mov     ecx, 80004005h
0x180042e4a  call    Log_UnistoreHREvent_0
0x180042e4f  lea     rcx, [rbp+37h+Block]
0x180042e53  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
  ... truncated ...
```
