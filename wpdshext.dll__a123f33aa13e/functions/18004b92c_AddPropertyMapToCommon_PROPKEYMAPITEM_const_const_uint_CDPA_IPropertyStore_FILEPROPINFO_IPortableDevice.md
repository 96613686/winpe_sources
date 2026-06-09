# _AddPropertyMapToCommon(PROPKEYMAPITEM const * const,uint,CDPA<IPropertyStore> *,FILEPROPINFO *,IPortableDevice *)

- ea: `0x18004b92c`
- end: `0x18004be5a`
- name: `?_AddPropertyMapToCommon@@YAJQEBUPROPKEYMAPITEM@@IPEAV?$CDPA@UIPropertyStore@@@@PEAUFILEPROPINFO@@PEAUIPortableDevice@@@Z`
- size: `1326`
- prototype: `__int64 __fastcall(int, int, int, int, struct IPortableDevice *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800303e4`

## callees

- `0x18000d540`
- `0x18000d610`
- `0x18000e760`
- `0x18001d6b0`
- `0x18002ff5c`
- `0x180035960`
- `0x180049684`
- `0x180049a1c`
- `0x18004b92c`
- `0x18005ce34`
- `0x18006d9ec`
- `0x18006dc78`
- `0x180078010`

## import_xrefs

- `SHLWAPI!StrCmpW` at `0x18004baef`
- `SHLWAPI!StrCmpW` at `0x18004baef`
- `ole32!PropVariantCopy` at `0x18004bb33`
- `ole32!PropVariantCopy` at `0x18004bb78`
- `ole32!PropVariantCopy` at `0x18004bb33`
- `ole32!PropVariantCopy` at `0x18004bb78`
- `ole32!PropVariantClear` at `0x18004bb0c`
- `ole32!PropVariantClear` at `0x18004bb56`
- `ole32!PropVariantClear` at `0x18004bbd3`
- `ole32!PropVariantClear` at `0x18004bbf6`
- `ole32!PropVariantClear` at `0x18004bc0a`
- `ole32!PropVariantClear` at `0x18004bc14`
- `ole32!PropVariantClear` at `0x18004bdef`
- `ole32!PropVariantClear` at `0x18004bb0c`
- `ole32!PropVariantClear` at `0x18004bb56`
- `ole32!PropVariantClear` at `0x18004bbd3`
- `ole32!PropVariantClear` at `0x18004bbf6`
- `ole32!PropVariantClear` at `0x18004bc0a`
- `ole32!PropVariantClear` at `0x18004bc14`
- `ole32!PropVariantClear` at `0x18004bdef`

## pseudocode

```c
__int64 __fastcall _AddPropertyMapToCommon(
        __int64 a1,
        unsigned int a2,
        int **a3,
        __int64 a4,
        struct IPortableDevice *a5)
{
  unsigned int v5; // r15d
  int *v7; // rbx
  unsigned int v8; // eax
  HRESULT v9; // esi
  char *v10; // rax
  PROPVARIANT *v11; // r14
  PROPKEYINFO *v12; // rdi
  char *v13; // r12
  int **v14; // r15
  __int64 v15; // r12
  __int64 v16; // rcx
  __int64 i; // rdx
  int *v18; // rcx
  int v19; // eax
  __int64 Ptr; // rax
  int v21; // eax
  const struct std::nothrow_t *v22; // rdx
  VARTYPE vt; // cx
  int j; // r15d
  int v25; // eax
  __int64 v26; // rax
  unsigned int v27; // edx
  int v28; // eax
  PROPVARIANT *v29; // r15
  __int64 v30; // rdx
  PROPVARIANT *v31; // rcx
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  BOOL v34; // r15d
  __int64 v35; // r15
  __int64 v36; // rax
  int v38; // [rsp+20h] [rbp-40h] BYREF
  int v39; // [rsp+24h] [rbp-3Ch]
  BOOL v40; // [rsp+28h] [rbp-38h]
  unsigned int v41; // [rsp+2Ch] [rbp-34h]
  int *v42; // [rsp+30h] [rbp-30h] BYREF
  __int64 v43; // [rsp+38h] [rbp-28h]
  PROPVARIANT psz2; // [rsp+40h] [rbp-20h] BYREF

  v5 = 0;
  v7 = 0;
  v40 = 0;
  v42 = 0;
  v8 = a2;
  v38 = 0;
  v9 = 0;
  memset(&psz2, 0, sizeof(psz2));
  while ( 2 )
  {
    v41 = v5;
    if ( v5 < v8 )
    {
      v10 = (char *)operator new(0x50u, (const struct std::nothrow_t *)&WPP_GLOBAL_Control);
      v43 = (__int64)v10;
      v11 = (PROPVARIANT *)v10;
      if ( v10 )
      {
        v12 = (PROPKEYINFO *)v10;
        *(PROPERTYKEY *)v10 = WPD_PROPERTY_NULL;
        *((_QWORD *)v10 + 6) = 0;
        *((_QWORD *)v10 + 7) = 0;
        *((_QWORD *)v10 + 8) = 0;
        *((_DWORD *)v10 + 18) = 0;
        *(_OWORD *)(v10 + 24) = 0;
        *((_QWORD *)v10 + 5) = 0;
        v13 = (char *)v5;
        v14 = a3;
        v43 = (__int64)v13;
        v15 = 32LL * (_QWORD)v13;
        if ( !*(_DWORD *)(v15 + a1 + 20) )
          goto LABEL_10;
        if ( *a3 )
          v16 = (unsigned int)**a3;
        else
          v16 = 0;
        v42 = (int *)IsolationAwareDPA_Create(v16);
        v7 = v42;
        if ( v42 )
        {
          v9 = 0;
          v11[2].hVal.HighPart = 1;
LABEL_10:
          for ( i = 0; ; i = (unsigned int)(v39 + 1) )
          {
            v18 = *v14;
            v39 = i;
            if ( v18 )
              v19 = *v18;
            else
              v19 = 0;
            if ( (int)i >= v19 )
              goto LABEL_47;
            Ptr = IsolationAwareDPA_GetPtr(v18, (int)i);
            if ( !Ptr )
            {
              v9 = -2147467259;
              goto LABEL_75;
            }
            v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)Ptr + 40LL))(
                    Ptr,
                    *(_QWORD *)(v15 + a1),
                    &psz2);
            v22 = 0;
            v9 = v21;
            if ( v21 < 0 )
              break;
            vt = psz2.vt;
            if ( psz2.vt == 10 || !psz2.vt )
              break;
            if ( *(_DWORD *)(v15 + a1 + 20) )
            {
              if ( psz2.vt == 31 )
              {
                if ( *psz2.bstrVal )
                {
                  for ( j = 0; ; ++j )
                  {
                    v25 = v7 ? *v7 : 0;
                    if ( j >= v25 )
                      break;
                    v26 = IsolationAwareDPA_GetPtr(v7, j);
                    if ( !v26 || *(_WORD *)v26 != psz2.vt )
                    {
                      v9 = -2147467259;
                      goto LABEL_76;
                    }
                    v28 = StrCmpW(*(PCWSTR *)(v26 + 8), psz2.bstrVal);
                    v22 = 0;
                    if ( !v28 )
                    {
                      v11[2].hVal.HighPart = 0;
                      goto LABEL_32;
                    }
                    vt = psz2.vt;
                  }
                }
                else
                {
LABEL_32:
                  PropVariantClear(&psz2);
                  vt = psz2.vt;
                }
              }
              if ( vt )
              {
                v29 = (PROPVARIANT *)operator new(0x18u, v22);
                v9 = PropVariantCopy(v29, &psz2);
                if ( v9 < 0 )
                {
                  v32 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v33 = 53;
                    goto LABEL_62;
                  }
                  goto LABEL_75;
                }
                if ( (unsigned int)IsolationAwareDPA_InsertPtr(v7, v30, v29) == -1 )
                {
                  PropVariantClear(v29);
                  operator delete(v29, 0x18u);
                }
              }
            }
            else
            {
              v31 = v11 + 1;
              if ( v11[1].vt )
              {
                v9 = PropVariantCompare(v31, &psz2, &v38, 1u);
                if ( v9 < 0 )
                {
                  v32 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v33 = 55;
                    goto LABEL_62;
                  }
                  goto LABEL_75;
                }
                if ( v38 )
                {
                  v11[2].hVal.HighPart = 1;
                  PropVariantClear(&psz2);
                  goto LABEL_47;
                }
              }
              else
              {
                v9 = PropVariantCopy(v31, &psz2);
                if ( v9 < 0 )
                {
                  v32 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v33 = 54;
                    goto LABEL_62;
                  }
                  goto LABEL_75;
                }
              }
            }
            PropVariantClear(&psz2);
            v14 = a3;
          }
          v11[2].hVal.HighPart = 1;
          PropVariantClear(&psz2);
          PropVariantClear(v11 + 1);
          CDPA<tagPROPVARIANT>::DestroyCallback(&v42);
          v7 = v42;
LABEL_47:
          if ( *(_DWORD *)(v15 + a1 + 20) )
          {
            PropVariantConcat(&v42, v11 + 1);
            CDPA<tagPROPVARIANT>::DestroyCallback(&v42);
            v7 = v42;
          }
          if ( *(_DWORD *)(v15 + a1 + 16) == 1 )
          {
            v9 = IsPropertySupportedByDevice(a5, *(const struct _tagpropertykey **)(v15 + a1));
            v34 = v9 == 0;
            v40 = v34;
          }
          else
          {
            v34 = v40;
          }
          if ( !v11[1].vt && (*(_DWORD *)(v15 + a1 + 16) != 1 || !v34) )
          {
            PROPKEYINFO::`scalar deleting destructor'((PROPKEYINFO *)v11, i);
LABEL_58:
            v8 = a2;
            v5 = v41 + 1;
            continue;
          }
          v35 = v43;
          v36 = *(_QWORD *)(32 * v43 + a1);
          *(_OWORD *)&v11->vt = *(_OWORD *)v36;
          *((_DWORD *)&v11->decVal + 4) = *(_DWORD *)(v36 + 16);
          *(_DWORD *)&v11[3].vt = *(_DWORD *)(32 * v35 + a1 + 12);
          *((_DWORD *)&v11[2].decVal + 5) = *(_DWORD *)(32 * v35 + a1 + 8);
          v35 *= 32;
          *(_QWORD *)&v11[2].vt = *(_QWORD *)(v35 + a1 + 24);
          v11[2].lVal = *(_DWORD *)(v35 + a1 + 20);
          if ( (unsigned int)IsolationAwareDPA_InsertPtr(*(_QWORD *)(a4 + 616), i, v11) != -1 )
          {
            v9 = 0;
            goto LABEL_58;
          }
          v9 = -2147024882;
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v33 = 56;
            goto LABEL_62;
          }
          goto LABEL_75;
        }
        v9 = -2147024882;
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v33 = 52;
LABEL_62:
          WPP_SF_d(v32[2], v33, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)v9);
        }
      }
      else
      {
        v12 = 0;
        v9 = -2147024882;
      }
LABEL_75:
      PropVariantClear(&psz2);
      CDPA<tagPROPVARIANT>::DestroyCallback(&v42);
      if ( v12 )
LABEL_76:
        PROPKEYINFO::`scalar deleting destructor'(v12, v27);
    }
    break;
  }
  if ( v9 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004b92c  mov     rax, rsp
0x18004b92f  mov     [rax+8], rbx
0x18004b933  mov     [rax+20h], r9
0x18004b937  mov     [rax+18h], r8
0x18004b93b  mov     [rax+10h], edx
0x18004b93e  push    rbp
0x18004b93f  push    rsi
0x18004b940  push    rdi
0x18004b941  push    r12
0x18004b943  push    r13
0x18004b945  push    r14
0x18004b947  push    r15
0x18004b949  mov     rbp, rsp
0x18004b94c  sub     rsp, 60h
0x18004b950  xor     r15d, r15d
0x18004b953  mov     r13, rcx
0x18004b956  mov     ebx, r15d
0x18004b959  mov     [rbp+var_38], r15d
0x18004b95d  xor     ecx, ecx
0x18004b95f  mov     [rbp+var_30], rbx
0x18004b963  xorps   xmm0, xmm0
0x18004b966  mov     [rbp+var_10], rcx
0x18004b96a  mov     eax, edx
0x18004b96c  mov     [rbp+var_40], r15d
0x18004b970  mov     esi, r15d
0x18004b973  movups  xmmword ptr [rbp+psz2], xmm0
0x18004b977  mov     [rbp+var_34], r15d
0x18004b97b  lea     rdx, WPP_GLOBAL_Control; struct std::nothrow_t *
0x18004b982  cmp     r15d, eax
0x18004b985  jnb     loc_18004BE12
0x18004b98b  mov     ecx, 50h ; 'P'; unsigned __int64
0x18004b990  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004b995  xor     r8d, r8d
0x18004b998  mov     [rbp+var_28], rax
0x18004b99c  mov     r14, rax
0x18004b99f  test    rax, rax
0x18004b9a2  jz      loc_18004BDE3
0x18004b9a8  movups  xmm0, xmmword ptr cs:WPD_PROPERTY_NULL.fmtid.Data1
0x18004b9af  mov     rdi, r14
0x18004b9b2  movups  xmmword ptr [rax], xmm0
0x18004b9b5  mov     eax, cs:WPD_PROPERTY_NULL.pid
0x18004b9bb  mov     [r14+10h], eax
0x18004b9bf  xorps   xmm0, xmm0
0x18004b9c2  xor     eax, eax
0x18004b9c4  mov     [r14+30h], r8
0x18004b9c8  mov     [r14+38h], r8
0x18004b9cc  mov     [r14+40h], r8
0x18004b9d0  mov     [r14+48h], r8d
0x18004b9d4  movups  xmmword ptr [r14+18h], xmm0
0x18004b9d9  mov     [r14+28h], rax
0x18004b9dd  test    r14, r14
0x18004b9e0  jz      loc_18004BDE6
0x18004b9e6  mov     r12d, r15d
0x18004b9e9  mov     r15, [rbp+arg_10]
0x18004b9ed  mov     [rbp+var_28], r12
0x18004b9f1  shl     r12, 5
0x18004b9f5  cmp     [r12+r13+14h], r8d
0x18004b9fa  jz      short loc_18004BA2E
0x18004b9fc  mov     rax, [r15]
0x18004b9ff  test    rax, rax
0x18004ba02  jz      short loc_18004BA08
0x18004ba04  mov     ecx, [rax]
0x18004ba06  jmp     short loc_18004BA0B
0x18004ba08  mov     ecx, r8d
0x18004ba0b  call    IsolationAwareDPA_Create
0x18004ba10  xor     r8d, r8d
0x18004ba13  mov     [rbp+var_30], rax
0x18004ba17  mov     rbx, rax
0x18004ba1a  test    rax, rax
0x18004ba1d  jz      loc_18004BD27
0x18004ba23  mov     esi, r8d
0x18004ba26  mov     dword ptr [r14+3Ch], 1
0x18004ba2e  mov     edx, r8d
0x18004ba31  mov     rcx, [r15]
0x18004ba34  mov     [rbp+var_3C], edx
0x18004ba37  test    rcx, rcx
0x18004ba3a  jz      short loc_18004BA40
0x18004ba3c  mov     eax, [rcx]
0x18004ba3e  jmp     short loc_18004BA43
0x18004ba40  mov     eax, r8d
0x18004ba43  cmp     edx, eax
0x18004ba45  jge     loc_18004BC2A
0x18004ba4b  movsxd  rdx, edx
0x18004ba4e  call    IsolationAwareDPA_GetPtr
0x18004ba53  mov     r9, rax
0x18004ba56  test    rax, rax
0x18004ba59  jz      loc_18004BDB4
0x18004ba5f  mov     rcx, [rax]
0x18004ba62  lea     r8, [rbp+psz2]
0x18004ba66  mov     rdx, [r12+r13]
0x18004ba6a  mov     rax, [rcx+28h]
0x18004ba6e  mov     rcx, r9
0x18004ba71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba76  xor     edx, edx
0x18004ba78  mov     esi, eax
0x18004ba7a  test    eax, eax
0x18004ba7c  js      loc_18004BBFE
0x18004ba82  movzx   ecx, word ptr [rbp+psz2]
0x18004ba86  cmp     cx, 0Ah
0x18004ba8a  jz      loc_18004BBFE
0x18004ba90  test    cx, cx
0x18004ba93  jz      loc_18004BBFE
0x18004ba99  cmp     [r12+r13+14h], edx
0x18004ba9e  jz      loc_18004BB6B
0x18004baa4  cmp     cx, 1Fh
0x18004baa8  jnz     short loc_18004BB16
0x18004baaa  mov     rax, [rbp+psz2+8]
0x18004baae  cmp     [rax], dx
0x18004bab1  jz      short loc_18004BB08
0x18004bab3  mov     r15d, edx
0x18004bab6  test    rbx, rbx
0x18004bab9  jz      short loc_18004BABF
0x18004babb  mov     eax, [rbx]
0x18004babd  jmp     short loc_18004BAC1
0x18004babf  mov     eax, edx
0x18004bac1  cmp     r15d, eax
0x18004bac4  jge     short loc_18004BB16
0x18004bac6  movsxd  rdx, r15d
0x18004bac9  mov     rcx, rbx
0x18004bacc  call    IsolationAwareDPA_GetPtr
0x18004bad1  test    rax, rax
0x18004bad4  jz      loc_18004BD6A
0x18004bada  movzx   ecx, word ptr [rbp+psz2]
0x18004bade  cmp     [rax], cx
0x18004bae1  jnz     loc_18004BD6A
0x18004bae7  mov     rdx, [rbp+psz2+8]; psz2
0x18004baeb  mov     rcx, [rax+8]; psz1
0x18004baef  call    cs:__imp_StrCmpW
0x18004baf5  xor     edx, edx
0x18004baf7  test    eax, eax
0x18004baf9  jz      short loc_18004BB04
0x18004bafb  movzx   ecx, word ptr [rbp+psz2]
0x18004baff  inc     r15d
0x18004bb02  jmp     short loc_18004BAB6
0x18004bb04  mov     [r14+3Ch], edx
0x18004bb08  lea     rcx, [rbp+psz2]; pvar
0x18004bb0c  call    cs:__imp_PropVariantClear
0x18004bb12  movzx   ecx, word ptr [rbp+psz2]
0x18004bb16  test    cx, cx
0x18004bb19  jz      loc_18004BBCF
0x18004bb1f  mov     ecx, 18h; unsigned __int64
0x18004bb24  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004bb29  lea     rdx, [rbp+psz2]; pvarSrc
0x18004bb2d  mov     rcx, rax; pvarDest
0x18004bb30  mov     r15, rax
0x18004bb33  call    cs:__imp_PropVariantCopy
0x18004bb39  mov     esi, eax
0x18004bb3b  test    eax, eax
0x18004bb3d  js      loc_18004BD74
0x18004bb43  mov     r8, r15
0x18004bb46  mov     rcx, rbx
0x18004bb49  call    IsolationAwareDPA_InsertPtr
0x18004bb4e  cmp     eax, 0FFFFFFFFh
0x18004bb51  jnz     short loc_18004BBCF
0x18004bb53  mov     rcx, r15; pvar
0x18004bb56  call    cs:__imp_PropVariantClear
0x18004bb5c  mov     edx, 18h; unsigned __int64
0x18004bb61  mov     rcx, r15; void *
0x18004bb64  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004bb69  jmp     short loc_18004BBCF
0x18004bb6b  lea     rcx, [r14+18h]; struct tagPROPVARIANT *
0x18004bb6f  cmp     [rcx], dx
0x18004bb72  lea     rdx, [rbp+psz2]; struct tagPROPVARIANT *
0x18004bb76  jnz     short loc_18004BBAF
0x18004bb78  call    cs:__imp_PropVariantCopy
0x18004bb7e  mov     esi, eax
0x18004bb80  test    eax, eax
0x18004bb82  jns     short loc_18004BBCF
0x18004bb84  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb8b  lea     rax, WPP_GLOBAL_Control
0x18004bb92  cmp     rcx, rax
0x18004bb95  jz      loc_18004BDEB
0x18004bb9b  test    byte ptr [rcx+1Ch], 2
0x18004bb9f  jz      loc_18004BDEB
0x18004bba5  mov     edx, 36h ; '6'
0x18004bbaa  jmp     loc_18004BD52
0x18004bbaf  mov     r9d, 1; unsigned int
0x18004bbb5  lea     r8, [rbp+var_40]; int *
0x18004bbb9  call    ?PropVariantCompare@@YAJAEBUtagPROPVARIANT@@0PEAHK@Z; PropVariantCompare(tagPROPVARIANT const &,tagPROPVARIANT const &,int *,ulong)
0x18004bbbe  mov     esi, eax
0x18004bbc0  xor     eax, eax
0x18004bbc2  test    esi, esi
0x18004bbc4  js      loc_18004BD94
0x18004bbca  cmp     [rbp+var_40], eax
0x18004bbcd  jnz     short loc_18004BBEA
0x18004bbcf  lea     rcx, [rbp+psz2]; pvar
0x18004bbd3  call    cs:__imp_PropVariantClear
0x18004bbd9  mov     edx, [rbp+var_3C]
0x18004bbdc  mov     r15, [rbp+arg_10]
0x18004bbe0  inc     edx
0x18004bbe2  xor     r8d, r8d
0x18004bbe5  jmp     loc_18004BA31
0x18004bbea  lea     rcx, [rbp+psz2]; pvar
0x18004bbee  mov     dword ptr [r14+3Ch], 1
0x18004bbf6  call    cs:__imp_PropVariantClear
0x18004bbfc  jmp     short loc_18004BC27
0x18004bbfe  lea     rcx, [rbp+psz2]; pvar
0x18004bc02  mov     dword ptr [r14+3Ch], 1
0x18004bc0a  call    cs:__imp_PropVariantClear
0x18004bc10  lea     rcx, [r14+18h]; pvar
0x18004bc14  call    cs:__imp_PropVariantClear
0x18004bc1a  lea     rcx, [rbp+var_30]
0x18004bc1e  call    ?DestroyCallback@?$CDPA@UtagPROPVARIANT@@@@QEAAXP6AHPEAUtagPROPVARIANT@@PEAX@Z1@Z; CDPA<tagPROPVARIANT>::DestroyCallback(int (*)(tagPROPVARIANT *,void *),void *)
0x18004bc23  mov     rbx, [rbp+var_30]
0x18004bc27  xor     r8d, r8d
0x18004bc2a  cmp     [r12+r13+14h], r8d
0x18004bc2f  jz      short loc_18004BC4E
0x18004bc31  lea     rdx, [r14+18h]
0x18004bc35  lea     rcx, [rbp+var_30]
0x18004bc39  call    ?PropVariantConcat@@YAJPEAV?$CDPA@UtagPROPVARIANT@@@@PEAUtagPROPVARIANT@@@Z; PropVariantConcat(CDPA<tagPROPVARIANT> *,tagPROPVARIANT *)
0x18004bc3e  lea     rcx, [rbp+var_30]
0x18004bc42  call    ?DestroyCallback@?$CDPA@UtagPROPVARIANT@@@@QEAAXP6AHPEAUtagPROPVARIANT@@PEAX@Z1@Z; CDPA<tagPROPVARIANT>::DestroyCallback(int (*)(tagPROPVARIANT *,void *),void *)
0x18004bc47  mov     rbx, [rbp+var_30]
0x18004bc4b  xor     r8d, r8d
0x18004bc4e  mov     eax, 1
0x18004bc53  cmp     [r12+r13+10h], eax
0x18004bc58  jnz     short loc_18004BC7F
0x18004bc5a  mov     rdx, [r12+r13]; struct _tagpropertykey *
0x18004bc5e  mov     r15d, r8d
0x18004bc61  mov     rcx, [rbp+arg_20]; struct IPortableDevice *
0x18004bc65  call    ?IsPropertySupportedByDevice@@YAJPEAUIPortableDevice@@AEBU_tagpropertykey@@@Z; IsPropertySupportedByDevice(IPortableDevice *,_tagpropertykey const &)
0x18004bc6a  xor     r8d, r8d
0x18004bc6d  mov     esi, eax
0x18004bc6f  test    eax, eax
0x18004bc71  lea     eax, [r8+1]
0x18004bc75  cmovz   r15d, eax
0x18004bc79  mov     [rbp+var_38], r15d
0x18004bc7d  jmp     short loc_18004BC83
0x18004bc7f  mov     r15d, [rbp+var_38]
0x18004bc83  cmp     [r14+18h], r8w
0x18004bc88  jnz     short loc_18004BCA0
0x18004bc8a  cmp     [r12+r13+10h], eax
0x18004bc8f  jnz     short loc_18004BC96
0x18004bc91  test    r15d, r15d
0x18004bc94  jnz     short loc_18004BCA0
0x18004bc96  mov     rcx, r14; this
0x18004bc99  call    ??_GPROPKEYINFO@@QEAAPEAXI@Z; PROPKEYINFO::`scalar deleting destructor'(uint)
0x18004bc9e  jmp     short loc_18004BD18
0x18004bca0  mov     r15, [rbp+var_28]
0x18004bca4  mov     r8, r14
0x18004bca7  mov     rax, r15
0x18004bcaa  shl     rax, 5
0x18004bcae  mov     rax, [rax+r13]
0x18004bcb2  movups  xmm0, xmmword ptr [rax]
0x18004bcb5  movups  xmmword ptr [r14], xmm0
0x18004bcb9  mov     eax, [rax+10h]
0x18004bcbc  mov     [r14+10h], eax
0x18004bcc0  mov     rax, r15
0x18004bcc3  shl     rax, 5
0x18004bcc7  mov     eax, [rax+r13+0Ch]
0x18004bccc  mov     [r14+48h], eax
0x18004bcd0  mov     rax, r15
0x18004bcd3  shl     rax, 5
0x18004bcd7  mov     eax, [rax+r13+8]
0x18004bcdc  mov     [r14+44h], eax
0x18004bce0  mov     rax, r15
0x18004bce3  shl     rax, 5
0x18004bce7  shl     r15, 5
0x18004bceb  mov     rax, [rax+r13+18h]
0x18004bcf0  mov     [r14+30h], rax
0x18004bcf4  mov     eax, [r15+r13+14h]
0x18004bcf9  mov     [r14+38h], eax
0x18004bcfd  mov     rax, [rbp+arg_18]
0x18004bd01  mov     rcx, [rax+268h]
0x18004bd08  call    IsolationAwareDPA_InsertPtr
0x18004bd0d  cmp     eax, 0FFFFFFFFh
0x18004bd10  jz      loc_18004BDBB
0x18004bd16  xor     esi, esi
0x18004bd18  mov     r15d, [rbp+var_34]
0x18004bd1c  mov     eax, [rbp+arg_8]
0x18004bd1f  inc     r15d
0x18004bd22  jmp     loc_18004B977
0x18004bd27  mov     esi, 8007000Eh
0x18004bd2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bd33  lea     rax, WPP_GLOBAL_Control
0x18004bd3a  cmp     rcx, rax
0x18004bd3d  jz      loc_18004BDEB
0x18004bd43  test    byte ptr [rcx+1Ch], 2
0x18004bd47  jz      loc_18004BDEB
0x18004bd4d  mov     edx, 34h ; '4'
0x18004bd52  mov     rcx, [rcx+10h]
0x18004bd56  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x18004bd5d  mov     r9d, esi
0x18004bd60  call    WPP_SF_d
0x18004bd65  jmp     loc_18004BDEB
0x18004bd6a  mov     esi, 80004005h
0x18004bd6f  jmp     loc_18004BE03
0x18004bd74  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bd7b  lea     rax, WPP_GLOBAL_Control
0x18004bd82  cmp     rcx, rax
0x18004bd85  jz      short loc_18004BDEB
0x18004bd87  test    byte ptr [rcx+1Ch], 2
0x18004bd8b  jz      short loc_18004BDEB
0x18004bd8d  mov     edx, 35h ; '5'
0x18004bd92  jmp     short loc_18004BD52
0x18004bd94  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bd9b  lea     rax, WPP_GLOBAL_Control
0x18004bda2  cmp     rcx, rax
0x18004bda5  jz      short loc_18004BDEB
0x18004bda7  test    byte ptr [rcx+1Ch], 2
  ... truncated ...
```
