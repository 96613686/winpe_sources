# KsppGetAssociatedECDHKey

- ea: `0x1800183ec`
- end: `0x18001876e`
- name: `KsppGetAssociatedECDHKey`
- size: `898`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180021220`

## callees

- `0x180009e76`
- `0x18000a3c8`
- `0x18000a408`
- `0x18000a848`
- `0x18000aa4c`
- `0x18000aee4`
- `0x18000b114`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180017f6c`
- `0x1800183ec`
- `0x1800199b0`
- `0x18002ec0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001851e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001851e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001852c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001852c`

## pseudocode

```c
__int64 __fastcall KsppGetAssociatedECDHKey(const WCHAR *lpValueName, void *a2, unsigned int a3, unsigned int *a4)
{
  HKEY v7; // rsi
  __int64 v8; // r9
  unsigned int ECDHKey; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r15
  const wchar_t *v14; // r14
  unsigned int v15; // edx
  __int64 v16; // rcx
  int v17; // eax
  HKEY v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  unsigned int v22; // edi
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF
  void *v25; // [rsp+78h] [rbp+48h]
  size_t pcchLength; // [rsp+88h] [rbp+58h] BYREF

  v25 = a2;
  hKey = 0;
  pcchLength = 0;
  v7 = 0;
  if ( !a4 )
  {
    WppTraceIndent((__int64)lpValueName, 2u);
    v8 = 2148073511LL;
    ECDHKey = -2146893785;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 146;
LABEL_6:
      WPP_SF_d(v10[2], v11, &WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids, v8);
      return ECDHKey;
    }
    return ECDHKey;
  }
  v12 = *((_QWORD *)lpValueName + 150);
  v13 = *((_QWORD *)lpValueName + 136);
  if ( v12 && !(unsigned int)KsppIsECDHContainer(lpValueName, v12, 0) )
  {
    CspFreeH(*((_QWORD *)lpValueName + 150));
    *((_QWORD *)lpValueName + 150) = 0;
  }
  v14 = (const wchar_t *)*((_QWORD *)lpValueName + 150);
  if ( !v14 )
  {
    if ( !(unsigned int)RegGetECDSAAssociation(v13, lpValueName, &hKey) )
    {
      v14 = (const wchar_t *)hKey;
      if ( (unsigned int)KsppIsECDHContainer(lpValueName, hKey, 0) )
      {
        *((_QWORD *)lpValueName + 150) = v14;
        goto LABEL_31;
      }
      v15 = *(_DWORD *)(v13 + 560);
      v16 = *(_QWORD *)(v13 + 552);
      hKey = 0;
      v17 = I_RegOpenCardKey(v16, v15, &hKey, 0x20006u);
      v18 = hKey;
      if ( !v17 )
        RegDeleteValueW(hKey, lpValueName);
      if ( v18 )
        RegCloseKey(v18);
      CspFreeH(v14);
      hKey = 0;
    }
    ECDHKey = KsppFindECDHKey(lpValueName, &hKey);
    if ( ECDHKey )
    {
      WppTraceIndent(v19, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          147,
          (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
          (_DWORD)WPP_pszIndent,
          ECDHKey);
      }
      v7 = hKey;
      goto LABEL_49;
    }
    v7 = hKey;
    ECDHKey = RegAddECDSAAssociation(v13, lpValueName, (const wchar_t *)hKey);
    if ( ECDHKey )
    {
      WppTraceIndent(v20, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          148,
          (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
          (_DWORD)WPP_pszIndent,
          ECDHKey);
      }
      goto LABEL_49;
    }
    *((_QWORD *)lpValueName + 150) = v7;
    v14 = (const wchar_t *)v7;
    v7 = 0;
  }
LABEL_31:
  ECDHKey = StringCchLengthW(v14, 0x28u, &pcchLength);
  if ( (ECDHKey & 0x80000000) != 0 )
  {
    WppTraceIndent(v21, 2u);
    ECDHKey = HR_Remap(ECDHKey);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        149,
        (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
        (_DWORD)WPP_pszIndent,
        ECDHKey);
    }
    return ECDHKey;
  }
  v22 = 2 * pcchLength + 2;
  if ( !a3 )
  {
    *a4 = v22;
    return ECDHKey;
  }
  if ( v25 )
  {
    if ( a3 < v22 )
    {
      WppTraceIndent(v21, 2u);
      ECDHKey = -2146893784;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 151;
        v8 = 2148073512LL;
        goto LABEL_6;
      }
      return ECDHKey;
    }
    memcpy_0(v25, v14, v22);
    *a4 = v22;
LABEL_49:
    if ( v7 )
      CspFreeH(v7);
    return ECDHKey;
  }
  WppTraceIndent(v21, 2u);
  v8 = 2148073511LL;
  ECDHKey = -2146893785;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 150;
    goto LABEL_6;
  }
  return ECDHKey;
}

```

## disassembly

```asm
0x1800183ec  mov     [rsp-38h+arg_10], rbx
0x1800183f1  mov     [rsp-38h+arg_8], rdx
0x1800183f6  push    rbp
0x1800183f7  push    rsi
0x1800183f8  push    rdi
0x1800183f9  push    r12
0x1800183fb  push    r13
0x1800183fd  push    r14
0x1800183ff  push    r15
0x180018401  mov     rbp, rsp
0x180018404  sub     rsp, 30h
0x180018408  xor     ebx, ebx
0x18001840a  mov     r12, r9
0x18001840d  mov     [rbp+hKey], rbx
0x180018411  mov     r13d, r8d
0x180018414  mov     [rbp+pcchLength], rbx
0x180018418  mov     rdi, rcx
0x18001841b  mov     esi, ebx
0x18001841d  test    r9, r9
0x180018420  jnz     short loc_180018478
0x180018422  lea     edx, [rbx+2]
0x180018425  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001842a  mov     r9d, 80090027h
0x180018430  mov     ebx, r9d
0x180018433  mov     rcx, cs:WPP_GLOBAL_Control
0x18001843a  lea     rax, WPP_GLOBAL_Control
0x180018441  cmp     rcx, rax
0x180018444  jz      loc_180018754
0x18001844a  test    byte ptr [rcx+1Ch], 1
0x18001844e  jz      loc_180018754
0x180018454  cmp     byte ptr [rcx+19h], 2
0x180018458  jb      loc_180018754
0x18001845e  mov     edx, 92h
0x180018463  mov     rcx, [rcx+10h]
0x180018467  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x18001846e  call    WPP_SF_d
0x180018473  jmp     loc_180018754
0x180018478  mov     rdx, [rcx+4B0h]
0x18001847f  mov     r15, [rcx+440h]
0x180018486  test    rdx, rdx
0x180018489  jz      short loc_1800184AA
0x18001848b  xor     r8d, r8d
0x18001848e  call    KsppIsECDHContainer
0x180018493  test    eax, eax
0x180018495  jnz     short loc_1800184AA
0x180018497  mov     rcx, [rdi+4B0h]
0x18001849e  call    CspFreeH
0x1800184a3  mov     [rdi+4B0h], rbx
0x1800184aa  mov     r14, [rdi+4B0h]
0x1800184b1  test    r14, r14
0x1800184b4  jnz     loc_180018620
0x1800184ba  lea     r8, [rbp+hKey]
0x1800184be  mov     rdx, rdi
0x1800184c1  mov     rcx, r15
0x1800184c4  call    RegGetECDSAAssociation
0x1800184c9  test    eax, eax
0x1800184cb  jnz     short loc_18001853E
0x1800184cd  mov     r14, [rbp+hKey]
0x1800184d1  xor     r8d, r8d
0x1800184d4  mov     rdx, r14
0x1800184d7  mov     rcx, rdi
0x1800184da  call    KsppIsECDHContainer
0x1800184df  test    eax, eax
0x1800184e1  jz      short loc_1800184EF
0x1800184e3  mov     [rdi+4B0h], r14
0x1800184ea  jmp     loc_180018620
0x1800184ef  mov     edx, [r15+230h]
0x1800184f6  lea     r8, [rbp+hKey]
0x1800184fa  mov     rcx, [r15+228h]
0x180018501  mov     r9d, 20006h
0x180018507  mov     [rbp+hKey], rbx
0x18001850b  call    I_RegOpenCardKey
0x180018510  mov     rbx, [rbp+hKey]
0x180018514  test    eax, eax
0x180018516  jnz     short loc_180018524
0x180018518  mov     rdx, rdi; lpValueName
0x18001851b  mov     rcx, rbx; hKey
0x18001851e  call    cs:__imp_RegDeleteValueW
0x180018524  test    rbx, rbx
0x180018527  jz      short loc_180018532
0x180018529  mov     rcx, rbx; hKey
0x18001852c  call    cs:__imp_RegCloseKey
0x180018532  mov     rcx, r14
0x180018535  call    CspFreeH
0x18001853a  mov     [rbp+hKey], rsi
0x18001853e  lea     rdx, [rbp+hKey]
0x180018542  mov     rcx, rdi
0x180018545  call    KsppFindECDHKey
0x18001854a  mov     ebx, eax
0x18001854c  test    eax, eax
0x18001854e  jz      short loc_1800185A2
0x180018550  mov     edx, 2
0x180018555  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001855a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018561  lea     rax, WPP_GLOBAL_Control
0x180018568  cmp     rcx, rax
0x18001856b  jz      short loc_180018599
0x18001856d  test    byte ptr [rcx+1Ch], 1
0x180018571  jz      short loc_180018599
0x180018573  cmp     byte ptr [rcx+19h], 2
0x180018577  jb      short loc_180018599
0x180018579  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180018580  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x180018587  mov     rcx, [rcx+10h]
0x18001858b  mov     edx, 93h
0x180018590  mov     [rsp+30h+var_10], ebx
0x180018594  call    WPP_SF_sd
0x180018599  mov     rsi, [rbp+hKey]
0x18001859d  jmp     loc_180018747
0x1800185a2  mov     rsi, [rbp+hKey]
0x1800185a6  mov     rdx, rdi
0x1800185a9  mov     r8, rsi
0x1800185ac  mov     rcx, r15
0x1800185af  call    RegAddECDSAAssociation
0x1800185b4  mov     ebx, eax
0x1800185b6  test    eax, eax
0x1800185b8  jz      short loc_180018614
0x1800185ba  mov     edx, 2
0x1800185bf  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800185c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185cb  lea     rax, WPP_GLOBAL_Control
0x1800185d2  cmp     rcx, rax
0x1800185d5  jz      loc_180018747
0x1800185db  test    byte ptr [rcx+1Ch], 1
0x1800185df  jz      loc_180018747
0x1800185e5  cmp     byte ptr [rcx+19h], 2
0x1800185e9  jb      loc_180018747
0x1800185ef  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800185f6  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x1800185fd  mov     rcx, [rcx+10h]
0x180018601  mov     edx, 94h
0x180018606  mov     [rsp+30h+var_10], ebx
0x18001860a  call    WPP_SF_sd
0x18001860f  jmp     loc_180018747
0x180018614  mov     [rdi+4B0h], rsi
0x18001861b  mov     r14, rsi
0x18001861e  xor     esi, esi
0x180018620  lea     r8, [rbp+pcchLength]; pcchLength
0x180018624  mov     edx, 28h ; '('; cchMax
0x180018629  mov     rcx, r14; psz
0x18001862c  call    StringCchLengthW
0x180018631  mov     ebx, eax
0x180018633  test    eax, eax
0x180018635  jns     short loc_18001869A
0x180018637  mov     edx, 2
0x18001863c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180018641  mov     ecx, ebx
0x180018643  call    HR_Remap
0x180018648  mov     ebx, eax
0x18001864a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018651  lea     rax, WPP_GLOBAL_Control
0x180018658  cmp     rcx, rax
0x18001865b  jz      loc_180018754
0x180018661  test    byte ptr [rcx+1Ch], 1
0x180018665  jz      loc_180018754
0x18001866b  cmp     byte ptr [rcx+19h], 2
0x18001866f  jb      loc_180018754
0x180018675  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001867c  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x180018683  mov     rcx, [rcx+10h]
0x180018687  mov     edx, 95h
0x18001868c  mov     [rsp+30h+var_10], ebx
0x180018690  call    WPP_SF_sd
0x180018695  jmp     loc_180018754
0x18001869a  mov     eax, dword ptr [rbp+pcchLength]
0x18001869d  lea     edi, ds:2[rax*2]
0x1800186a4  test    r13d, r13d
0x1800186a7  jnz     short loc_1800186B2
0x1800186a9  mov     [r12], edi
0x1800186ad  jmp     loc_180018754
0x1800186b2  mov     rax, [rbp+arg_8]
0x1800186b6  test    rax, rax
0x1800186b9  jnz     short loc_1800186F5
0x1800186bb  lea     edx, [rax+2]
0x1800186be  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800186c3  mov     r9d, 80090027h
0x1800186c9  mov     ebx, r9d
0x1800186cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186d3  lea     rax, WPP_GLOBAL_Control
0x1800186da  cmp     rcx, rax
0x1800186dd  jz      short loc_180018754
0x1800186df  test    byte ptr [rcx+1Ch], 1
0x1800186e3  jz      short loc_180018754
0x1800186e5  cmp     byte ptr [rcx+19h], 2
0x1800186e9  jb      short loc_180018754
0x1800186eb  mov     edx, 96h
0x1800186f0  jmp     loc_180018463
0x1800186f5  cmp     r13d, edi
0x1800186f8  jnb     short loc_180018735
0x1800186fa  mov     edx, 2
0x1800186ff  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180018704  mov     ebx, 80090028h
0x180018709  mov     rcx, cs:WPP_GLOBAL_Control
0x180018710  lea     rax, WPP_GLOBAL_Control
0x180018717  cmp     rcx, rax
0x18001871a  jz      short loc_180018754
0x18001871c  test    byte ptr [rcx+1Ch], 1
0x180018720  jz      short loc_180018754
0x180018722  cmp     byte ptr [rcx+19h], 2
0x180018726  jb      short loc_180018754
0x180018728  mov     edx, 97h
0x18001872d  mov     r9d, ebx
0x180018730  jmp     loc_180018463
0x180018735  mov     r8d, edi; Size
0x180018738  mov     rdx, r14; Src
0x18001873b  mov     rcx, rax; void *
0x18001873e  call    memcpy_0
0x180018743  mov     [r12], edi
0x180018747  test    rsi, rsi
0x18001874a  jz      short loc_180018754
0x18001874c  mov     rcx, rsi
0x18001874f  call    CspFreeH
0x180018754  mov     eax, ebx
0x180018756  mov     rbx, [rsp+30h+arg_10]
0x18001875e  add     rsp, 30h
0x180018762  pop     r15
0x180018764  pop     r14
0x180018766  pop     r13
0x180018768  pop     r12
0x18001876a  pop     rdi
0x18001876b  pop     rsi
0x18001876c  pop     rbp
0x18001876d  retn
```
