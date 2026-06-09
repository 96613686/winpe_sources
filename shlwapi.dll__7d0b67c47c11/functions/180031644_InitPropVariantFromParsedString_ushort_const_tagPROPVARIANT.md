# _InitPropVariantFromParsedString(ushort const *,tagPROPVARIANT *)

- ea: `0x180031644`
- end: `0x180031895`
- name: `?_InitPropVariantFromParsedString@@YAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `593`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800340e8`

## callees

- `0x180003400`
- `0x18000a47c`
- `0x18000fec0`
- `0x180012550`
- `0x18002d034`
- `0x180031644`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x1800317b2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x1800317b2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800316f3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180031790`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800316f3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180031790`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180031690`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800317bb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180031690`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800317bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003183a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003184b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003183a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003184b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031863`

## pseudocode

```c
__int64 __fastcall _InitPropVariantFromParsedString(const unsigned __int16 *a1, struct tagPROPVARIANT *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r9
  int v6; // eax
  int v7; // ebx
  int v8; // edi
  unsigned __int16 *v9; // r8
  PWSTR v10; // rax
  int v11; // ecx
  BYTE *v12; // r12
  void *v13; // rcx
  unsigned int v14; // r9d
  int v15; // eax
  unsigned __int16 *v16; // rsi
  unsigned int v17; // edi
  PWSTR v18; // r15
  __int64 v19; // rdx
  __int64 v20; // r9
  unsigned __int64 v21; // rsi
  unsigned __int64 i; // rdi
  unsigned int pszStart; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  void *v26; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v27[264]; // [rsp+50h] [rbp-B0h] BYREF

  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  if ( (unsigned int)lstrlenW(a1) < 0x104 )
  {
    v6 = StringCchCopyW(v27, 0x104u, a1);
  }
  else
  {
    v5 = -1;
    do
      ++v5;
    while ( a1[v5] );
    v6 = _AllocStringWorker<CTCoAllocPolicy>(v4, 260, a1);
  }
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = 0;
    v9 = v27;
    while ( v9 )
    {
      v10 = StrChrW(v9, 0x3Bu);
      v11 = v8 + 1;
      if ( !v10 )
        v11 = v8;
      v9 = v10 + 1;
      v8 = v11;
      if ( !v10 )
        v9 = 0;
    }
    pszStart = v8 + 1;
    if ( v8 != -1 )
    {
      v26 = 0;
      v12 = 0;
      v25 = 0;
      v7 = ULongLongMult((unsigned int)(v8 + 1), 8u, &v25);
      if ( v7 >= 0 )
      {
        v15 = CTCoAllocPolicy::Alloc(v13, 1u, v25, &v26);
        v14 = v8 + 1;
        v7 = v15;
        v12 = (BYTE *)v26;
      }
      if ( v7 >= 0 )
      {
        v16 = v27;
        v17 = 0;
        while ( v16 )
        {
          if ( v17 >= v14 )
            goto LABEL_28;
          v18 = StrChrW(v16, 0x3Bu);
          if ( v18 )
            *v18++ = 0;
          StrTrimW(v16, L" ");
          if ( lstrlenW(v16) <= 0 )
            goto LABEL_27;
          v20 = -1;
          do
            ++v20;
          while ( v16[v20] );
          v7 = _AllocStringWorker<CTCoAllocPolicy>(&v12[8 * v17], v19, v16);
          if ( v7 < 0 )
          {
LABEL_27:
            v14 = pszStart;
            v16 = v18;
            if ( v7 < 0 )
            {
LABEL_28:
              if ( v7 < 0 )
                goto LABEL_31;
              break;
            }
          }
          else
          {
            v14 = pszStart;
            ++v17;
            v16 = v18;
          }
        }
        if ( v17 )
        {
          a2->vt = 4127;
          a2->lVal = v17;
          a2->bstrblobVal.pData = v12;
          return (unsigned int)v7;
        }
LABEL_31:
        v21 = v17;
        for ( i = 0; i < v21; ++i )
          CoTaskMemFree(*(LPVOID *)&v12[8 * i]);
        CoTaskMemFree(v12);
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180031644  mov     [rsp-8+arg_10], rbx
0x180031649  push    rbp
0x18003164a  push    rsi
0x18003164b  push    rdi
0x18003164c  push    r12
0x18003164e  push    r13
0x180031650  push    r14
0x180031652  push    r15
0x180031654  lea     rbp, [rsp-170h]
0x18003165c  sub     rsp, 270h
0x180031663  mov     rax, cs:__security_cookie
0x18003166a  xor     rax, rsp
0x18003166d  mov     [rbp+1A0h+var_40], rax
0x180031674  xorps   xmm0, xmm0
0x180031677  lea     r14, [rsp+2A0h+var_250]
0x18003167c  xor     eax, eax
0x18003167e  mov     [rsp+2A0h+pszStart], r14
0x180031683  movups  xmmword ptr [rdx], xmm0
0x180031686  mov     [rdx+10h], rax
0x18003168a  mov     r13, rdx
0x18003168d  mov     rbx, rcx
0x180031690  call    cs:__imp_lstrlenW
0x180031696  mov     edx, 104h; unsigned __int64
0x18003169b  xor     r15d, r15d
0x18003169e  cmp     eax, edx
0x1800316a0  jb      short loc_1800316C9
0x1800316a2  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800316a6  inc     r9
0x1800316a9  cmp     [rbx+r9*2], r15w
0x1800316ae  jnz     short loc_1800316A6
0x1800316b0  lea     rax, [rsp+2A0h+pszStart]
0x1800316b5  mov     r8, rbx
0x1800316b8  mov     [rsp+2A0h+var_278], rax
0x1800316bd  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800316c2  mov     r14, [rsp+2A0h+pszStart]
0x1800316c7  jmp     short loc_1800316D6
0x1800316c9  mov     r8, rbx; unsigned __int16 *
0x1800316cc  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x1800316d1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800316d6  mov     ebx, eax
0x1800316d8  test    eax, eax
0x1800316da  js      loc_180031851
0x1800316e0  mov     edi, r15d
0x1800316e3  mov     r8, r14
0x1800316e6  test    r14, r14
0x1800316e9  jz      short loc_180031711
0x1800316eb  mov     edx, 3Bh ; ';'; wMatch
0x1800316f0  mov     rcx, r8; pszStart
0x1800316f3  call    cs:__imp_StrChrW
0x1800316f9  test    rax, rax
0x1800316fc  lea     ecx, [rdi+1]
0x1800316ff  cmovz   ecx, edi
0x180031702  lea     r8, [rax+2]
0x180031706  mov     edi, ecx
0x180031708  cmovz   r8, rax
0x18003170c  test    r8, r8
0x18003170f  jnz     short loc_1800316EB
0x180031711  lea     r9d, [rdi+1]
0x180031715  mov     dword ptr [rsp+2A0h+pszStart], r9d
0x18003171a  test    r9d, r9d
0x18003171d  jz      loc_180031851
0x180031723  mov     ecx, r9d; unsigned __int64
0x180031726  lea     r8, [rsp+2A0h+var_268]; unsigned __int64 *
0x18003172b  mov     edx, 8; unsigned __int64
0x180031730  mov     [rsp+2A0h+var_260], r15
0x180031735  mov     r12, r15
0x180031738  mov     [rsp+2A0h+var_268], r15
0x18003173d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180031742  mov     ebx, eax
0x180031744  test    eax, eax
0x180031746  js      short loc_180031768
0x180031748  mov     r8, [rsp+2A0h+var_268]; unsigned __int64
0x18003174d  lea     r9, [rsp+2A0h+var_260]; void **
0x180031752  mov     edx, 1; unsigned int
0x180031757  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003175c  mov     r9d, dword ptr [rsp+2A0h+pszStart]
0x180031761  mov     ebx, eax
0x180031763  mov     r12, [rsp+2A0h+var_260]
0x180031768  test    ebx, ebx
0x18003176a  js      loc_180031851
0x180031770  mov     rsi, r14
0x180031773  mov     edi, r15d
0x180031776  test    rsi, rsi
0x180031779  jz      loc_180031817
0x18003177f  cmp     edi, r9d
0x180031782  jnb     loc_180031813
0x180031788  mov     edx, 3Bh ; ';'; wMatch
0x18003178d  mov     rcx, rsi; pszStart
0x180031790  call    cs:__imp_StrChrW
0x180031796  mov     r15, rax
0x180031799  xor     eax, eax
0x18003179b  test    r15, r15
0x18003179e  jz      short loc_1800317A8
0x1800317a0  mov     [r15], ax
0x1800317a4  add     r15, 2
0x1800317a8  lea     rdx, pszTrimChars; " "
0x1800317af  mov     rcx, rsi; psz
0x1800317b2  call    cs:__imp_StrTrimW
0x1800317b8  mov     rcx, rsi; lpString
0x1800317bb  call    cs:__imp_lstrlenW
0x1800317c1  xor     ecx, ecx
0x1800317c3  test    eax, eax
0x1800317c5  jle     short loc_180031800
0x1800317c7  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800317cb  inc     r9
0x1800317ce  cmp     [rsi+r9*2], cx
0x1800317d3  jnz     short loc_1800317CB
0x1800317d5  mov     eax, edi
0x1800317d7  mov     r8, rsi
0x1800317da  lea     rcx, [r12+rax*8]
0x1800317de  mov     [rsp+2A0h+var_278], rcx
0x1800317e3  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800317e8  mov     ebx, eax
0x1800317ea  test    eax, eax
0x1800317ec  js      short loc_180031800
0x1800317ee  mov     r9d, dword ptr [rsp+2A0h+pszStart]
0x1800317f3  inc     edi
0x1800317f5  mov     rsi, r15
0x1800317f8  xor     r15d, r15d
0x1800317fb  jmp     loc_180031776
0x180031800  mov     r9d, dword ptr [rsp+2A0h+pszStart]
0x180031805  mov     rsi, r15
0x180031808  xor     r15d, r15d
0x18003180b  test    ebx, ebx
0x18003180d  jns     loc_180031776
0x180031813  test    ebx, ebx
0x180031815  js      short loc_18003182C
0x180031817  test    edi, edi
0x180031819  jz      short loc_18003182C
0x18003181b  mov     word ptr [r13+0], 101Fh
0x180031822  mov     [r13+8], edi
0x180031826  mov     [r13+10h], r12
0x18003182a  jmp     short loc_180031851
0x18003182c  mov     esi, edi
0x18003182e  mov     rdi, r15
0x180031831  test    rsi, rsi
0x180031834  jz      short loc_180031848
0x180031836  mov     rcx, [r12+rdi*8]; pv
0x18003183a  call    cs:__imp_CoTaskMemFree
0x180031840  inc     rdi
0x180031843  cmp     rdi, rsi
0x180031846  jb      short loc_180031836
0x180031848  mov     rcx, r12; pv
0x18003184b  call    cs:__imp_CoTaskMemFree
0x180031851  test    r14, r14
0x180031854  jz      short loc_180031869
0x180031856  lea     rax, [rsp+2A0h+var_250]
0x18003185b  cmp     r14, rax
0x18003185e  jz      short loc_180031869
0x180031860  mov     rcx, r14; pv
0x180031863  call    cs:__imp_CoTaskMemFree
0x180031869  mov     eax, ebx
0x18003186b  mov     rcx, [rbp+1A0h+var_40]
0x180031872  xor     rcx, rsp; StackCookie
0x180031875  call    __security_check_cookie
0x18003187a  mov     rbx, [rsp+2A0h+arg_10]
0x180031882  add     rsp, 270h
0x180031889  pop     r15
0x18003188b  pop     r14
0x18003188d  pop     r13
0x18003188f  pop     r12
0x180031891  pop     rdi
0x180031892  pop     rsi
0x180031893  pop     rbp
0x180031894  retn
```
