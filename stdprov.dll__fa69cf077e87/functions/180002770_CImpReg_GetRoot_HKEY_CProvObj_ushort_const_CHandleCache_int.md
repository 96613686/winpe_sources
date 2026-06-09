# CImpReg::GetRoot(HKEY__ * *,CProvObj &,ushort const *,CHandleCache *,int &)

- ea: `0x180002770`
- end: `0x180002e09`
- name: `?GetRoot@CImpReg@@QEAAHPEAPEAUHKEY__@@AEAVCProvObj@@PEBGPEAVCHandleCache@@AEAH@Z`
- size: `1689`
- prototype: `LSTATUS __fastcall(CImpReg *this, HKEY *, struct CProvObj *, const unsigned __int16 *, struct CHandleCache *, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001640`
- `0x1800121e0`

## callees

- `0x180001010`
- `0x180001310`
- `0x180002770`
- `0x180002e10`
- `0x180002f30`
- `0x180002fa0`
- `0x180006524`
- `0x1800087f0`
- `0x180008830`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002874`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800028cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002a3d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002a65`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002b4c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002874`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800028cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002a3d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002a65`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002b4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002bc0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002bc0`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180002d99`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180002d99`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x180002c03`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x180002c03`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800027b0`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800027da`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800027fe`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180002aa2`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180002ac4`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180002b9e`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180002bdd`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180002c1f`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800027b0`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800027da`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800027fe`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180002aa2`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180002ac4`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180002b9e`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180002bdd`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180002c1f`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x1800029eb`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x1800029eb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002976`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800029d5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002b6d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002c4d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002976`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800029d5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002b6d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002c4d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800028eb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002952`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800029b2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002b11`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800028eb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002952`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800029b2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002b11`

## pseudocode

```c
LSTATUS __fastcall CImpReg::GetRoot(
        CImpReg *this,
        HKEY *a2,
        struct CProvObj *a3,
        const unsigned __int16 *a4,
        struct CHandleCache *a5,
        int *a6)
{
  CFlexArray *v7; // r14
  void *v8; // rax
  const WCHAR *v9; // r12
  struct CHandleCache *v10; // r13
  CFlexArray *v11; // rbx
  _QWORD *v12; // rax
  const WCHAR *v13; // rdi
  void *v14; // rax
  const WCHAR *v15; // r13
  LSTATUS result; // eax
  int i; // r14d
  HKEY v18; // rdi
  int *v19; // rax
  CEntry *v20; // r14
  __int64 v21; // rax
  int v22; // r13d
  unsigned __int16 *v23; // rax
  char *v24; // rcx
  unsigned __int16 *v25; // r15
  __int64 v26; // rcx
  int v27; // r13d
  unsigned __int16 *v28; // rax
  int v29; // r15d
  int v30; // r12d
  int j; // edi
  void *v32; // rax
  const unsigned __int16 *v33; // rdi
  __int64 v34; // rax
  int v35; // r12d
  WCHAR *v36; // rax
  int v37; // eax
  int *v38; // r14
  int v39; // esi
  int v40; // edi
  void *v41; // rax
  HKEY v42; // rcx
  int k; // edi
  void (__fastcall ***v44)(void *, __int64); // rax
  int v45; // edx
  void *v46; // rax
  HKEY v47; // rcx
  LSTATUS v48; // ebx
  int v49; // [rsp+30h] [rbp-50h]
  LPCWSTR lpMachineName; // [rsp+38h] [rbp-48h] BYREF
  __int16 v51; // [rsp+40h] [rbp-40h] BYREF
  int v52; // [rsp+44h] [rbp-3Ch]
  PCNZWCH v53; // [rsp+48h] [rbp-38h]
  _WORD v54[2]; // [rsp+50h] [rbp-30h] BYREF
  int v55; // [rsp+54h] [rbp-2Ch]
  unsigned __int16 *v56; // [rsp+58h] [rbp-28h]
  _WORD v57[2]; // [rsp+60h] [rbp-20h] BYREF
  int v58; // [rsp+64h] [rbp-1Ch]
  __int16 *v59; // [rsp+68h] [rbp-18h] BYREF
  __int16 v60; // [rsp+70h] [rbp-10h] BYREF
  int v61; // [rsp+74h] [rbp-Ch]
  int v64; // [rsp+D0h] [rbp+50h]

  *a2 = 0;
  *a6 = 0;
  v7 = (struct CProvObj *)((char *)a3 + 8);
  if ( *((int *)a3 + 2) <= 0 )
    return 255;
  v8 = CFlexArray::GetAt((struct CProvObj *)((char *)a3 + 8), 0);
  if ( !v8 )
    return 255;
  v9 = (const WCHAR *)*((_QWORD *)v8 + 4);
  if ( !v9 || !a4 )
    return 255;
  v10 = a5;
  v11 = (struct CHandleCache *)((char *)a5 + 8);
  if ( *((int *)a5 + 2) <= 0 )
  {
LABEL_14:
    for ( i = 0; ; ++i )
    {
      if ( i >= 7 )
        return 255;
      if ( CompareStringW(0x7Fu, 1u, v9, -1, (PCNZWCH)*(&Bases + 2 * i), -1) == 2 )
        break;
    }
    v18 = (HKEY)*(&Bases + 2 * i + 1);
    a6 = (int *)v18;
    if ( (((unsigned __int64)v18 + 0x7FFFFFFF) & 0xFFFFFFFFFFFFFFFDuLL) == 0 )
    {
      result = AutoProfile::LoadProfile((CImpReg *)((char *)this + 176), (HKEY *)&a6);
      if ( result < 0 )
        return result;
      v18 = (HKEY)a6;
    }
    if ( !v18 )
      return 255;
    if ( CompareStringW(0x7Fu, 1u, a4, -1, L"LOCAL", -1) != 2 )
    {
      *((_DWORD *)v10 + 24) = 1;
      v51 = 0;
      lpMachineName = (LPCWSTR)&v51;
      v52 = 0;
      v60 = 0;
      v59 = &v60;
      v61 = 0;
      TString::assign((TString *)&v59, a4);
      TString::operator=(&lpMachineName, &v59);
      TString::Empty((TString *)&v59);
      v48 = RegConnectRegistryW(lpMachineName, v18, a2);
      TString::Empty((TString *)&lpMachineName);
      if ( !v48 )
      {
        v48 = CHandleCache::lAddToList(v10, a4, 0);
        if ( !v48 )
          v48 = CHandleCache::lAddToList(v10, v9, *a2);
      }
      TString::Empty((TString *)&lpMachineName);
      return v48;
    }
    *((_DWORD *)v10 + 24) = 0;
    v19 = (int *)CWin32DefaultArena::WbemMemAlloc(0x20u);
    a6 = v19;
    if ( v19 )
      v20 = CEntry::CEntry((CEntry *)v19);
    else
      v20 = 0;
    if ( v20 )
    {
      *((_QWORD *)v20 + 3) = 0;
      v57[0] = 0;
      v56 = v57;
      v58 = 0;
      v21 = -1;
      do
        ++v21;
      while ( a4[v21] );
      v22 = v21 + 1;
      v23 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((int)v21 + 1, 2u));
      if ( v23 )
      {
        v56 = v23;
        v58 = v22;
        StringCchCopyW(v23, v22, a4);
      }
      *((_DWORD *)v20 + 5) = 0;
      v24 = (char *)*((_QWORD *)v20 + 1);
      if ( v24 != (char *)v20 + 16 )
        CWin32DefaultArena::WbemMemFree(v24);
      *((_QWORD *)v20 + 1) = (char *)v20 + 16;
      v25 = v56;
      if ( v56 )
      {
        v26 = -1;
        do
          ++v26;
        while ( v56[v26] );
        v27 = v26 + 1;
        v28 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((int)v26 + 1, 2u));
        if ( v28 )
        {
          *((_QWORD *)v20 + 1) = v28;
          *((_DWORD *)v20 + 5) = v27;
          StringCchCopyW(v28, v27, v25);
        }
      }
      v58 = 0;
      if ( v56 != v57 )
        CWin32DefaultArena::WbemMemFree(v56);
      v56 = v57;
      if ( !CFlexArray::InsertAt(v11, *(_DWORD *)v11, v20) )
      {
        result = CHandleCache::lAddToList(a5, v9, 0);
LABEL_38:
        *a2 = v18;
        return result;
      }
      (**(void (__fastcall ***)(CEntry *, __int64))v20)(v20, 1);
    }
    result = -2147217402;
    goto LABEL_38;
  }
  v12 = CFlexArray::GetAt((struct CHandleCache *)((char *)a5 + 8), 0);
  v13 = v12 ? (const WCHAR *)v12[1] : 0LL;
  if ( *(int *)v11 > 1 && (v14 = CFlexArray::GetAt(v11, 1)) != 0 )
    v15 = (const WCHAR *)*((_QWORD *)v14 + 1);
  else
    v15 = 0;
  if ( !v13 || !v15 )
    return 255;
  if ( CompareStringW(0x7Fu, 1u, v13, -1, a4, -1) != 2 || CompareStringW(0x7Fu, 1u, v15, -1, v9, -1) != 2 )
  {
    v10 = a5;
    CImpReg::Free(this, 0, a5);
    goto LABEL_14;
  }
  v29 = 1;
  v30 = 2;
  for ( j = 0; ; ++j )
  {
    v64 = j;
    v49 = v30;
    if ( v30 >= *(_DWORD *)v11 || v29 >= *(_DWORD *)v7 )
      break;
    lpMachineName = (LPCWSTR)CFlexArray::GetAt(v11, v30);
    if ( v29 < *(_DWORD *)v7 && v29 >= 0 && (v32 = CFlexArray::GetAt(v7, v29)) != 0 )
    {
      v33 = (const unsigned __int16 *)*((_QWORD *)v32 + 4);
      v54[0] = 0;
      v53 = v54;
      v55 = 0;
      if ( v33 )
      {
        v34 = -1;
        do
          ++v34;
        while ( v33[v34] );
        v35 = v34 + 1;
        v36 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((int)v34 + 1, 2u));
        if ( v36 )
        {
          v53 = v36;
          v55 = v35;
          StringCchCopyW(v36, v35, v33);
        }
        v30 = v49;
      }
      j = v64;
    }
    else
    {
      v54[0] = 0;
      v53 = v54;
      v55 = 0;
    }
    v37 = CompareStringW(0x7Fu, 1u, *((PCNZWCH *)lpMachineName + 1), -1, v53, -1);
    v55 = 0;
    if ( v37 != 2 )
    {
      if ( v53 != v54 )
        CWin32DefaultArena::WbemMemFree((void *)v53);
      v53 = v54;
      break;
    }
    if ( v53 != v54 )
      CWin32DefaultArena::WbemMemFree((void *)v53);
    v53 = v54;
    ++v30;
    ++v29;
  }
  v38 = a6;
  *a6 = j;
  v39 = j + 2;
  v40 = *(_DWORD *)v11 - 1;
  if ( v40 >= v39 )
  {
    do
    {
      if ( v40 < *(_DWORD *)v11 )
      {
        v41 = CFlexArray::GetAt(v11, v40);
        if ( v41 )
        {
          v42 = (HKEY)*((_QWORD *)v41 + 3);
          if ( v42 )
          {
            if ( !*((_QWORD *)this + 16) || *((_DWORD *)a5 + 24) )
              RegCloseKey(v42);
            else
              (*((void (**)(void))this + 18))();
          }
        }
      }
      --v40;
    }
    while ( v40 >= v39 );
    v38 = a6;
  }
  for ( k = *(_DWORD *)v11 - 1; k >= v39; --k )
  {
    v44 = (void (__fastcall ***)(void *, __int64))CFlexArray::GetAt(v11, k);
    if ( v44 )
      (**v44)(v44, 1);
    CFlexArray::RemoveAt(v11, k);
  }
  v45 = *v38 + 1;
  if ( v45 < *(_DWORD *)v11 && (v46 = CFlexArray::GetAt(v11, v45)) != 0 )
    v47 = (HKEY)*((_QWORD *)v46 + 3);
  else
    v47 = 0;
  *a2 = v47;
  return 0;
}

```

## disassembly

```asm
0x180002770  mov     [rsp-38h+arg_18], rbx
0x180002775  mov     [rsp-38h+phkResult], rdx
0x18000277a  mov     [rsp-38h+arg_0], rcx
0x18000277f  push    rbp
0x180002780  push    rsi
0x180002781  push    rdi
0x180002782  push    r12
0x180002784  push    r13
0x180002786  push    r14
0x180002788  push    r15
0x18000278a  mov     rbp, rsp
0x18000278d  sub     rsp, 80h
0x180002794  mov     r15, r9
0x180002797  xor     esi, esi
0x180002799  mov     [rdx], rsi
0x18000279c  mov     rax, [rbp+arg_28]
0x1800027a0  mov     [rax], esi
0x1800027a2  lea     r14, [r8+8]
0x1800027a6  cmp     [r14], esi
0x1800027a9  jle     short loc_18000281A
0x1800027ab  xor     edx, edx
0x1800027ad  mov     rcx, r14
0x1800027b0  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800027b6  test    rax, rax
0x1800027b9  jz      short loc_18000281A
0x1800027bb  mov     r12, [rax+20h]
0x1800027bf  test    r12, r12
0x1800027c2  jz      short loc_18000281A
0x1800027c4  test    r15, r15
0x1800027c7  jz      short loc_18000281A
0x1800027c9  mov     r13, [rbp+arg_20]
0x1800027cd  lea     rbx, [r13+8]
0x1800027d1  cmp     [rbx], esi
0x1800027d3  jle     short loc_18000283A
0x1800027d5  xor     edx, edx
0x1800027d7  mov     rcx, rbx
0x1800027da  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800027e0  test    rax, rax
0x1800027e3  jz      loc_180002CB9
0x1800027e9  mov     rdi, [rax+8]
0x1800027ed  cmp     dword ptr [rbx], 1
0x1800027f0  jle     loc_180002CC1
0x1800027f6  mov     edx, 1
0x1800027fb  mov     rcx, rbx
0x1800027fe  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180002804  test    rax, rax
0x180002807  jz      loc_180002CC1
0x18000280d  mov     r13, [rax+8]
0x180002811  test    rdi, rdi
0x180002814  jnz     loc_180002A14
0x18000281a  mov     eax, 0FFh
0x18000281f  mov     rbx, [rsp+80h+arg_18]
0x180002827  add     rsp, 80h
0x18000282e  pop     r15
0x180002830  pop     r14
0x180002832  pop     r13
0x180002834  pop     r12
0x180002836  pop     rdi
0x180002837  pop     rsi
0x180002838  pop     rbp
0x180002839  retn
0x18000283a  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180002841  xor     r14d, r14d
0x180002844  lea     rax, ?Bases@@3PAUBaseTypes@@A; BaseTypes near * Bases
0x18000284b  cmp     r14d, 7
0x18000284f  jge     short loc_18000281A
0x180002851  movsxd  rdi, r14d
0x180002854  add     rdi, rdi
0x180002857  mov     [rsp+80h+cchCount2], esi; cchCount2
0x18000285b  mov     rax, [rax+rdi*8]
0x18000285f  mov     [rsp+80h+lpString2], rax; lpString2
0x180002864  mov     r9d, esi; cchCount1
0x180002867  mov     r8, r12; lpString1
0x18000286a  mov     edx, 1; dwCmpFlags
0x18000286f  mov     ecx, 7Fh; Locale
0x180002874  call    cs:__imp_CompareStringW
0x18000287a  cmp     eax, 2
0x18000287d  lea     rax, ?Bases@@3PAUBaseTypes@@A; BaseTypes near * Bases
0x180002884  jnz     loc_180002C40
0x18000288a  mov     rdi, [rax+rdi*8+8]
0x18000288f  mov     [rbp+arg_28], rdi
0x180002893  lea     rax, [rdi+7FFFFFFFh]
0x18000289a  test    rax, 0FFFFFFFFFFFFFFFDh
0x1800028a0  jz      loc_180002D1A
0x1800028a6  test    rdi, rdi
0x1800028a9  jz      loc_18000281A
0x1800028af  mov     [rsp+80h+cchCount2], esi; cchCount2
0x1800028b3  lea     rax, String2; "LOCAL"
0x1800028ba  mov     [rsp+80h+lpString2], rax; lpString2
0x1800028bf  mov     r9d, esi; cchCount1
0x1800028c2  mov     r8, r15; lpString1
0x1800028c5  mov     edx, 1; dwCmpFlags
0x1800028ca  mov     ecx, 7Fh; Locale
0x1800028cf  call    cs:__imp_CompareStringW
0x1800028d5  cmp     eax, 2
0x1800028d8  jnz     loc_180002D3F
0x1800028de  mov     dword ptr [r13+60h], 0
0x1800028e6  mov     ecx, 20h ; ' '
0x1800028eb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800028f1  mov     [rbp+arg_28], rax
0x1800028f5  test    rax, rax
0x1800028f8  jz      loc_180002DE2
0x1800028fe  mov     rcx, rax; this
0x180002901  call    ??0CEntry@@QEAA@XZ; CEntry::CEntry(void)
0x180002906  mov     r14, rax
0x180002909  xor     ecx, ecx
0x18000290b  test    r14, r14
0x18000290e  jz      loc_180002DFF
0x180002914  mov     [r14+18h], rcx
0x180002918  mov     [rbp+var_20], cx
0x18000291c  lea     rax, [rbp+var_20]
0x180002920  mov     [rbp+var_28], rax
0x180002924  mov     [rbp+var_1C], ecx
0x180002927  mov     rax, rsi
0x18000292a  nop     word ptr [rax+rax+00h]
0x180002930  lea     rax, [rax+1]
0x180002934  cmp     word ptr [r15+rax*2], 0
0x18000293a  jnz     short loc_180002930
0x18000293c  lea     r13d, [rax+1]
0x180002940  movsxd  rcx, r13d
0x180002943  mov     eax, 2
0x180002948  mul     rcx
0x18000294b  cmovb   rax, rsi
0x18000294f  mov     rcx, rax
0x180002952  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180002958  test    rax, rax
0x18000295b  jnz     loc_180002C83
0x180002961  mov     dword ptr [r14+14h], 0
0x180002969  lea     r15, [r14+10h]
0x18000296d  mov     rcx, [r14+8]
0x180002971  cmp     rcx, r15
0x180002974  jz      short loc_18000297C
0x180002976  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000297c  mov     [r14+8], r15
0x180002980  mov     r15, [rbp+var_28]
0x180002984  test    r15, r15
0x180002987  jz      short loc_1800029C1
0x180002989  mov     rcx, rsi
0x18000298c  nop     dword ptr [rax+00h]
0x180002990  lea     rcx, [rcx+1]
0x180002994  cmp     word ptr [r15+rcx*2], 0
0x18000299a  jnz     short loc_180002990
0x18000299c  lea     r13d, [rcx+1]
0x1800029a0  movsxd  rcx, r13d
0x1800029a3  mov     eax, 2
0x1800029a8  mul     rcx
0x1800029ab  cmovb   rax, rsi
0x1800029af  mov     rcx, rax
0x1800029b2  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800029b8  test    rax, rax
0x1800029bb  jnz     loc_180002C9E
0x1800029c1  mov     [rbp+var_1C], 0
0x1800029c8  lea     rax, [rbp+var_20]
0x1800029cc  mov     rcx, [rbp+var_28]
0x1800029d0  cmp     rcx, rax
0x1800029d3  jz      short loc_1800029DB
0x1800029d5  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800029db  lea     rax, [rbp+var_20]
0x1800029df  mov     [rbp+var_28], rax
0x1800029e3  mov     r8, r14
0x1800029e6  mov     edx, [rbx]
0x1800029e8  mov     rcx, rbx
0x1800029eb  call    cs:__imp_?InsertAt@CFlexArray@@QEAAHHPEAX@Z; CFlexArray::InsertAt(int,void *)
0x1800029f1  test    eax, eax
0x1800029f3  jnz     loc_180002DEC
0x1800029f9  xor     r8d, r8d; void *
0x1800029fc  mov     rdx, r12; unsigned __int16 *
0x1800029ff  mov     rcx, [rbp+arg_20]; this
0x180002a03  call    ?lAddToList@CHandleCache@@QEAAJPEBGPEAX@Z; CHandleCache::lAddToList(ushort const *,void *)
0x180002a08  mov     rsi, [rbp+phkResult]
0x180002a0c  mov     [rsi], rdi
0x180002a0f  jmp     loc_18000281F
0x180002a14  test    r13, r13
0x180002a17  jz      loc_18000281A
0x180002a1d  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180002a24  mov     [rsp+80h+cchCount2], esi; cchCount2
0x180002a28  mov     [rsp+80h+lpString2], r15; lpString2
0x180002a2d  mov     r9d, esi; cchCount1
0x180002a30  mov     r8, rdi; lpString1
0x180002a33  mov     edx, 1; dwCmpFlags
0x180002a38  mov     ecx, 7Fh; Locale
0x180002a3d  call    cs:__imp_CompareStringW
0x180002a43  cmp     eax, 2
0x180002a46  jnz     loc_180002D03
0x180002a4c  mov     [rsp+80h+cchCount2], esi; cchCount2
0x180002a50  mov     [rsp+80h+lpString2], r12; lpString2
0x180002a55  mov     r9d, esi; cchCount1
0x180002a58  mov     r8, r13; lpString1
0x180002a5b  mov     edx, 1; dwCmpFlags
0x180002a60  mov     ecx, 7Fh; Locale
0x180002a65  call    cs:__imp_CompareStringW
0x180002a6b  cmp     eax, 2
0x180002a6e  jnz     loc_180002D03
0x180002a74  mov     r15d, 1
0x180002a7a  mov     r12d, eax
0x180002a7d  xor     r13d, r13d
0x180002a80  mov     edi, r13d
0x180002a83  mov     [rbp+arg_10], edi
0x180002a86  mov     [rbp+var_50], r12d
0x180002a8a  cmp     r12d, [rbx]
0x180002a8d  jge     loc_180002B7B
0x180002a93  cmp     r15d, [r14]
0x180002a96  jge     loc_180002B7B
0x180002a9c  mov     edx, r12d
0x180002a9f  mov     rcx, rbx
0x180002aa2  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180002aa8  mov     [rbp+lpMachineName], rax
0x180002aac  cmp     r15d, [r14]
0x180002aaf  jge     loc_180002CC9
0x180002ab5  test    r15d, r15d
0x180002ab8  js      loc_180002CC9
0x180002abe  mov     edx, r15d
0x180002ac1  mov     rcx, r14
0x180002ac4  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180002aca  test    rax, rax
0x180002acd  jz      loc_180002CC9
0x180002ad3  mov     rdi, [rax+20h]
0x180002ad7  mov     [rbp+var_30], r13w
0x180002adc  lea     rax, [rbp+var_30]
0x180002ae0  mov     [rbp+var_38], rax
0x180002ae4  mov     [rbp+var_2C], r13d
0x180002ae8  test    rdi, rdi
0x180002aeb  jz      short loc_180002B27
0x180002aed  mov     rax, rsi
0x180002af0  lea     rax, [rax+1]
0x180002af4  cmp     word ptr [rdi+rax*2], 0
0x180002af9  jnz     short loc_180002AF0
0x180002afb  lea     r12d, [rax+1]
0x180002aff  movsxd  r13, r12d
0x180002b02  mov     eax, 2
0x180002b07  mul     r13
0x180002b0a  cmovb   rax, rsi
0x180002b0e  mov     rcx, rax
0x180002b11  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180002b17  test    rax, rax
0x180002b1a  jnz     loc_180002C68
0x180002b20  xor     r13d, r13d
0x180002b23  mov     r12d, [rbp+var_50]
0x180002b27  mov     edi, [rbp+arg_10]
0x180002b2a  mov     rax, [rbp+var_38]
0x180002b2e  mov     [rsp+80h+cchCount2], esi; cchCount2
0x180002b32  mov     [rsp+80h+lpString2], rax; lpString2
0x180002b37  mov     r9d, esi; cchCount1
0x180002b3a  mov     r8, [rbp+lpMachineName]
0x180002b3e  mov     r8, [r8+8]; lpString1
0x180002b42  mov     edx, 1; dwCmpFlags
0x180002b47  mov     ecx, 7Fh; Locale
0x180002b4c  call    cs:__imp_CompareStringW
0x180002b52  nop
0x180002b53  mov     [rbp+var_2C], r13d
0x180002b57  mov     rcx, [rbp+var_38]
0x180002b5b  cmp     eax, 2
0x180002b5e  lea     rax, [rbp+var_30]
0x180002b62  jz      loc_180002C48
0x180002b68  cmp     rcx, rax
0x180002b6b  jz      short loc_180002B73
0x180002b6d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180002b73  lea     rax, [rbp+var_30]
0x180002b77  mov     [rbp+var_38], rax
0x180002b7b  mov     r14, [rbp+arg_28]
0x180002b7f  mov     [r14], edi
0x180002b82  lea     esi, [rdi+2]
0x180002b85  mov     edi, [rbx]
0x180002b87  dec     edi
0x180002b89  cmp     edi, esi
0x180002b8b  jl      short loc_180002BD0
0x180002b8d  mov     r15, [rbp+arg_20]
0x180002b91  mov     r14, [rbp+arg_0]
0x180002b95  cmp     edi, [rbx]
0x180002b97  jge     short loc_180002BC6
0x180002b99  mov     edx, edi
0x180002b9b  mov     rcx, rbx
0x180002b9e  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180002ba4  test    rax, rax
0x180002ba7  jz      short loc_180002BC6
0x180002ba9  mov     rcx, [rax+18h]; hKey
0x180002bad  test    rcx, rcx
0x180002bb0  jz      short loc_180002BC6
0x180002bb2  cmp     qword ptr [r14+80h], 0
0x180002bba  jnz     loc_180002CDF
0x180002bc0  call    cs:__imp_RegCloseKey
0x180002bc6  dec     edi
0x180002bc8  cmp     edi, esi
0x180002bca  jge     short loc_180002B95
0x180002bcc  mov     r14, [rbp+arg_28]
0x180002bd0  mov     edi, [rbx]
0x180002bd2  dec     edi
0x180002bd4  cmp     edi, esi
0x180002bd6  jl      short loc_180002C0F
0x180002bd8  mov     edx, edi
0x180002bda  mov     rcx, rbx
0x180002bdd  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180002be3  mov     r8, rax
0x180002be6  test    rax, rax
0x180002be9  jz      short loc_180002BFE
0x180002beb  mov     rcx, [rax]
0x180002bee  mov     rax, [rcx]
0x180002bf1  mov     edx, 1
0x180002bf6  mov     rcx, r8
0x180002bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
