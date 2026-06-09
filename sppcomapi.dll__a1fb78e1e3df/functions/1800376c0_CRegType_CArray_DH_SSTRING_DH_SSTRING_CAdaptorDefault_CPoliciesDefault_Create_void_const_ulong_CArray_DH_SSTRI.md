# CRegType<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>::Create(void const *,ulong,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,int *)

- ea: `0x1800376c0`
- end: `0x180037866`
- name: `?Create@?$CRegType@V?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@@@SAJPEBXKPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@PEAH@Z`
- size: `422`
- prototype: `__int64 __fastcall(char *Src, unsigned int, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180038090`
- `0x180039398`

## callees

- `0x1800031fc`
- `0x180003520`
- `0x1800036ec`
- `0x180004288`
- `0x180037118`
- `0x1800376c0`
- `0x180039cc0`
- `0x18003a180`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800377d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003780e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800377d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003780e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800377e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037822`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800377e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037822`

## pseudocode

```c
__int64 __fastcall CRegType<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>::Create(
        char *Src,
        unsigned int a2,
        __int64 a3,
        _DWORD *a4)
{
  char *v6; // rbx
  __int64 v7; // rcx
  int StringCch; // edi
  __int64 v9; // rdx
  char *v10; // r14
  int Internal; // eax
  int v12; // eax
  __int64 v13; // rbx
  HANDLE ProcessHeap; // rax
  void *v15; // rbx
  HANDLE v16; // rax
  int v18; // [rsp+20h] [rbp-20h] BYREF
  __int64 v19; // [rsp+28h] [rbp-18h] BYREF
  __int64 v20; // [rsp+30h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-8h]
  unsigned int v22; // [rsp+78h] [rbp+38h] BYREF

  v20 = 0;
  lpMem = 0;
  v6 = Src;
  v19 = 0;
  if ( a2 < 2
    || (a2 & 1) != 0
    || (v9 = a2 >> 1, v22 = v9, *(_WORD *)&Src[2 * (unsigned int)(v9 - 1)])
    || (unsigned int)v9 > 1 && *(_WORD *)&Src[2 * (unsigned int)(v9 - 2)] )
  {
LABEL_2:
    v7 = 2147942413LL;
    StringCch = -2147024883;
LABEL_19:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
  }
  else
  {
    v10 = &Src[2 * v9];
    while ( 1 )
    {
      StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Src, &v22);
      if ( StringCch < 0 )
      {
LABEL_18:
        v7 = (unsigned int)StringCch;
        goto LABEL_19;
      }
      if ( !v22 )
        break;
      v18 = 0;
      if ( v6
        && (Internal = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v6, &v18),
            StringCch = Internal,
            Internal < 0)
        || (Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v6),
            StringCch = Internal,
            Internal < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)StringCch);
      if ( StringCch < 0 )
        goto LABEL_18;
      v12 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(&v20, &v19);
      StringCch = v12;
      if ( v12 < 0 )
      {
        v7 = (unsigned int)v12;
        goto LABEL_19;
      }
      v6 += 2 * v22 + 2;
      if ( v6 > v10 )
        goto LABEL_2;
      Src = v6;
    }
    CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Swap(a3, &v20);
    *a4 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)StringCch);
  v13 = v19;
  if ( v19 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v13 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(&v20, 0);
  v15 = lpMem;
  if ( lpMem )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v15);
  }
  return (unsigned int)StringCch;
}

```

## disassembly

```asm
0x1800376c0  mov     [rsp-28h+arg_0], rbx
0x1800376c5  mov     [rsp-28h+arg_10], rdi
0x1800376ca  push    rbp
0x1800376cb  push    r12
0x1800376cd  push    r13
0x1800376cf  push    r14
0x1800376d1  push    r15
0x1800376d3  mov     rbp, rsp
0x1800376d6  sub     rsp, 40h
0x1800376da  xor     r13d, r13d
0x1800376dd  mov     r15, r9
0x1800376e0  mov     [rbp+var_10], r13
0x1800376e4  mov     r12, r8
0x1800376e7  mov     [rbp+lpMem], r13
0x1800376eb  mov     rbx, rcx
0x1800376ee  mov     [rbp+var_18], r13
0x1800376f2  cmp     edx, 2
0x1800376f5  jnb     short loc_180037703
0x1800376f7  mov     ecx, 8007000Dh
0x1800376fc  mov     edi, ecx
0x1800376fe  jmp     loc_1800377BD
0x180037703  test    dl, 1
0x180037706  jnz     short loc_1800376F7
0x180037708  shr     edx, 1
0x18003770a  mov     [rbp+arg_8], edx
0x18003770d  lea     eax, [rdx-1]
0x180037710  cmp     [rcx+rax*2], r13w
0x180037715  jnz     short loc_1800376F7
0x180037717  cmp     edx, 1
0x18003771a  jbe     short loc_180037726
0x18003771c  lea     eax, [rdx-2]
0x18003771f  cmp     [rcx+rax*2], r13w
0x180037724  jnz     short loc_1800376F7
0x180037726  lea     r14, [rcx+rdx*2]
0x18003772a  jmp     short loc_1800377A8
0x18003772c  cmp     [rbp+arg_8], r13d
0x180037730  jz      loc_180037852
0x180037736  mov     edx, r13d
0x180037739  mov     [rbp+var_20], edx
0x18003773c  test    rbx, rbx
0x18003773f  jz      short loc_180037756
0x180037741  lea     rdx, [rbp+var_20]
0x180037745  mov     rcx, rbx
0x180037748  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18003774d  mov     edi, eax
0x18003774f  test    eax, eax
0x180037751  js      short loc_180037768
0x180037753  mov     edx, [rbp+var_20]
0x180037756  lea     r8, [rbp+var_18]
0x18003775a  mov     rcx, rbx; Src
0x18003775d  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180037762  mov     edi, eax
0x180037764  test    eax, eax
0x180037766  jns     short loc_18003776F
0x180037768  mov     ecx, eax
0x18003776a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003776f  mov     ecx, edi
0x180037771  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180037776  test    edi, edi
0x180037778  js      short loc_1800377BB
0x18003777a  lea     rdx, [rbp+var_18]
0x18003777e  lea     rcx, [rbp+var_10]
0x180037782  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x180037787  mov     edi, eax
0x180037789  test    eax, eax
0x18003778b  js      loc_18003784B
0x180037791  mov     eax, [rbp+arg_8]
0x180037794  lea     rbx, [rbx+rax*2]
0x180037798  add     rbx, 2
0x18003779c  cmp     rbx, r14
0x18003779f  ja      loc_1800376F7
0x1800377a5  mov     rcx, rbx
0x1800377a8  lea     rdx, [rbp+arg_8]
0x1800377ac  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x1800377b1  mov     edi, eax
0x1800377b3  test    eax, eax
0x1800377b5  jns     loc_18003772C
0x1800377bb  mov     ecx, edi
0x1800377bd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800377c2  mov     ecx, edi
0x1800377c4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800377c9  mov     rbx, [rbp+var_18]
0x1800377cd  test    rbx, rbx
0x1800377d0  jz      short loc_1800377FA
0x1800377d2  call    cs:__imp_GetProcessHeap
0x1800377d9  nop     dword ptr [rax+rax+00h]
0x1800377de  lea     r8, [rbx-4]; lpMem
0x1800377e2  xor     edx, edx; dwFlags
0x1800377e4  mov     rcx, rax; hHeap
0x1800377e7  call    cs:__imp_HeapFree
0x1800377ee  nop     dword ptr [rax+rax+00h]
0x1800377f3  xor     ecx, ecx
0x1800377f5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800377fa  xor     edx, edx
0x1800377fc  lea     rcx, [rbp+var_10]
0x180037800  call    ?SetSize@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180037805  mov     rbx, [rbp+lpMem]
0x180037809  test    rbx, rbx
0x18003780c  jz      short loc_18003782E
0x18003780e  call    cs:__imp_GetProcessHeap
0x180037815  nop     dword ptr [rax+rax+00h]
0x18003781a  mov     r8, rbx; lpMem
0x18003781d  xor     edx, edx; dwFlags
0x18003781f  mov     rcx, rax; hHeap
0x180037822  call    cs:__imp_HeapFree
0x180037829  nop     dword ptr [rax+rax+00h]
0x18003782e  lea     r11, [rsp+40h+var_s0]
0x180037833  mov     eax, edi
0x180037835  mov     rbx, [r11+30h]
0x180037839  mov     rdi, [r11+40h]
0x18003783d  mov     rsp, r11
0x180037840  pop     r15
0x180037842  pop     r14
0x180037844  pop     r13
0x180037846  pop     r12
0x180037848  pop     rbp
0x180037849  retn
0x18003784b  mov     ecx, eax
0x18003784d  jmp     loc_1800377BD
0x180037852  lea     rdx, [rbp+var_10]
0x180037856  mov     rcx, r12
0x180037859  call    ?Swap@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAXPEAV1@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Swap(CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *)
0x18003785e  mov     [r15], r13d
0x180037861  jmp     loc_1800377C2
```
