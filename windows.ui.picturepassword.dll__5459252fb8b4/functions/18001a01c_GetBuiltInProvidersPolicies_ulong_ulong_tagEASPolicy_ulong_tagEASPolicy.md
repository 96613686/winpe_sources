# _GetBuiltInProvidersPolicies(ulong,ulong,_tagEASPolicy *,ulong *,_tagEASPolicy * *)

- ea: `0x18001a01c`
- end: `0x18001a14d`
- name: `?_GetBuiltInProvidersPolicies@@YAJKKPEAU_tagEASPolicy@@PEAKPEAPEAU1@@Z`
- size: `305`
- prototype: `__int64 __fastcall(__int64, unsigned int, struct _tagEASPolicy *, unsigned int *, struct _tagEASPolicy **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019e3c`

## callees

- `0x18001a01c`
- `0x18001a154`
- `0x18001a22c`
- `0x18001a7d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a059`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a059`

## string_xrefs

- `0x18001a08c`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x18001a10a`: `_myVariantCopy`

## pseudocode

```c
__int64 __fastcall _GetBuiltInProvidersPolicies(
        __int64 a1,
        unsigned int a2,
        struct _tagEASPolicy *a3,
        unsigned int *a4,
        struct _tagEASPolicy **a5)
{
  unsigned int v5; // esi
  struct _tagEASPolicy *v9; // rdi
  unsigned int v10; // ebx
  unsigned int v11; // ebp
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // r8d
  __int64 v15; // rax

  v5 = 0;
  *a4 = 0;
  *a5 = 0;
  if ( !a2 )
    goto LABEL_16;
  v9 = (struct _tagEASPolicy *)LocalAlloc(0x40u, 32LL * a2);
  if ( !v9 )
  {
    v10 = -1073741801;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221225495LL,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      31,
      L"LocalAlloc",
      &pszPassword);
    goto LABEL_17;
  }
  v11 = 0;
  while ( 2 )
  {
    if ( v11 >= a2 )
    {
      *a4 = v5;
      v5 = 0;
      *a5 = v9;
LABEL_16:
      v9 = 0;
      v10 = 0;
      goto LABEL_17;
    }
    v12 = 0;
    v13 = 32LL * v11;
    while ( 1 )
    {
      if ( (unsigned int)v12 >= 5 )
        goto LABEL_13;
      v14 = *(_DWORD *)((char *)a3 + v13);
      if ( v14 == *((_DWORD *)&g_dwPasswordProvPolicies + v12) )
        break;
      v12 = (unsigned int)(v12 + 1);
    }
    v15 = 32LL * v5;
    *(_DWORD *)((char *)v9 + v15) = v14;
    v10 = _myVariantCopy(
            (struct tagPROPVARIANT *)((char *)v9 + v15 + 8),
            (struct tagPROPVARIANT *)((char *)a3 + v13 + 8));
    if ( !v10 )
    {
      ++v5;
LABEL_13:
      ++v11;
      continue;
    }
    break;
  }
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    v10,
    L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
    71,
    L"_myVariantCopy",
    &pszPassword);
LABEL_17:
  _FreePolicies(v5, v9);
  return v10;
}

```

## disassembly

```asm
0x18001a01c  push    rbx
0x18001a01e  push    rbp
0x18001a01f  push    rsi
0x18001a020  push    rdi
0x18001a021  push    r12
0x18001a023  push    r13
0x18001a025  push    r14
0x18001a027  push    r15
0x18001a029  sub     rsp, 48h
0x18001a02d  mov     r12, [rsp+88h+arg_20]
0x18001a035  xor     esi, esi
0x18001a037  mov     r14d, edx
0x18001a03a  mov     r15, r9
0x18001a03d  mov     [r9], esi
0x18001a040  mov     r13, r8
0x18001a043  mov     [r12], rsi
0x18001a047  test    edx, edx
0x18001a049  jz      loc_18001A12C
0x18001a04f  mov     edx, r14d
0x18001a052  lea     ecx, [rsi+40h]; uFlags
0x18001a055  shl     rdx, 5; uBytes
0x18001a059  call    cs:__imp_LocalAlloc
0x18001a05f  mov     rdi, rax
0x18001a062  test    rax, rax
0x18001a065  jnz     short loc_18001A0AC
0x18001a067  lea     rax, pszPassword
0x18001a06e  mov     ebx, 0C0000017h
0x18001a073  mov     [rsp+88h+var_58], rax
0x18001a078  lea     rax, aLocalalloc; "LocalAlloc"
0x18001a07f  mov     [rsp+88h+var_60], rax
0x18001a084  mov     [rsp+88h+var_68], 1Fh
0x18001a08c  lea     r9, aOnecoreDsSecur_1; "onecore\\ds\\security\\eas\\policyengin"...
0x18001a093  mov     r8d, ebx
0x18001a096  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18001a09d  mov     ecx, 1; unsigned int
0x18001a0a2  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18001a0a7  jmp     loc_18001A130
0x18001a0ac  xor     ebp, ebp
0x18001a0ae  cmp     ebp, r14d
0x18001a0b1  jnb     short loc_18001A123
0x18001a0b3  xor     ecx, ecx
0x18001a0b5  mov     edx, ebp
0x18001a0b7  shl     rdx, 5
0x18001a0bb  cmp     ecx, 5
0x18001a0be  jnb     short loc_18001A0FA
0x18001a0c0  mov     r8d, [rdx+r13]
0x18001a0c4  lea     r9, ?g_dwPasswordProvPolicies@@3PAKA; ulong near * g_dwPasswordProvPolicies
0x18001a0cb  cmp     r8d, [r9+rcx*4]
0x18001a0cf  jz      short loc_18001A0D5
0x18001a0d1  inc     ecx
0x18001a0d3  jmp     short loc_18001A0BB
0x18001a0d5  add     rdx, 8
0x18001a0d9  mov     eax, esi
0x18001a0db  shl     rax, 5
0x18001a0df  lea     rcx, [rdi+8]
0x18001a0e3  add     rdx, r13; struct tagPROPVARIANT *
0x18001a0e6  add     rcx, rax; struct tagPROPVARIANT *
0x18001a0e9  mov     [rax+rdi], r8d
0x18001a0ed  call    ?_myVariantCopy@@YAJPEAUtagPROPVARIANT@@0@Z; _myVariantCopy(tagPROPVARIANT *,tagPROPVARIANT *)
0x18001a0f2  mov     ebx, eax
0x18001a0f4  test    eax, eax
0x18001a0f6  jnz     short loc_18001A0FE
0x18001a0f8  inc     esi
0x18001a0fa  inc     ebp
0x18001a0fc  jmp     short loc_18001A0AE
0x18001a0fe  lea     rax, pszPassword
0x18001a105  mov     [rsp+88h+var_58], rax
0x18001a10a  lea     rax, aMyvariantcopy; "_myVariantCopy"
0x18001a111  mov     [rsp+88h+var_60], rax
0x18001a116  mov     [rsp+88h+var_68], 47h ; 'G'
0x18001a11e  jmp     loc_18001A08C
0x18001a123  mov     [r15], esi
0x18001a126  xor     esi, esi
0x18001a128  mov     [r12], rdi
0x18001a12c  xor     edi, edi
0x18001a12e  xor     ebx, ebx
0x18001a130  mov     rdx, rdi; struct _tagEASPolicy *
0x18001a133  mov     ecx, esi; unsigned int
0x18001a135  call    ?_FreePolicies@@YAXKPEAU_tagEASPolicy@@@Z; _FreePolicies(ulong,_tagEASPolicy *)
0x18001a13a  mov     eax, ebx
0x18001a13c  add     rsp, 48h
0x18001a140  pop     r15
0x18001a142  pop     r14
0x18001a144  pop     r13
0x18001a146  pop     r12
0x18001a148  pop     rdi
0x18001a149  pop     rsi
0x18001a14a  pop     rbp
0x18001a14b  pop     rbx
0x18001a14c  retn
```
