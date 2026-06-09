# CFileDescriptorEntry::_Initialize(IVssWMFiledesc *,CPathCache *,uchar *)

- ea: `0x180024640`
- end: `0x180024b83`
- name: `?_Initialize@CFileDescriptorEntry@@QEAAJPEAVIVssWMFiledesc@@PEAVCPathCache@@PEAE@Z`
- size: `1347`
- prototype: `__int64 __fastcall(CFileDescriptorEntry *__hidden this, struct IVssWMFiledesc *, struct CPathCache *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180023874`

## callees

- `0x180008c74`
- `0x18000c894`
- `0x18000cbc0`
- `0x18000e104`
- `0x180020710`
- `0x180020908`
- `0x180020968`
- `0x18002345c`
- `0x180024640`
- `0x1800268b4`
- `0x1800269ac`
- `0x180027eac`
- `0x18002d0b4`
- `0x18002ecd0`
- `0x180034de0`
- `0x180034f54`
- `0x18003532c`
- `0x180035b00`
- `0x180037010`

## import_xrefs

- `msvcrt!isalpha` at `0x180024847`
- `msvcrt!isalpha` at `0x180024847`
- `OLEAUT32!__imp_SysFreeString` at `0x180024b4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180024b57`
- `OLEAUT32!__imp_SysFreeString` at `0x180024b4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180024b57`

## string_xrefs

- `0x1800246a4`: `CFileDescriptorEntry::_Initialize`

## pseudocode

```c
__int64 __fastcall CFileDescriptorEntry::_Initialize(
        CFileDescriptorEntry *this,
        struct IVssWMFiledesc *a2,
        struct CPathCache *a3,
        unsigned __int8 *a4)
{
  __int16 v8; // ax
  struct CPathCacheNode *v9; // rdi
  const unsigned __int16 **v10; // rsi
  __int16 v11; // ax
  __int16 v12; // ax
  LPCWSTR v13; // rbx
  int IsCsvFile; // eax
  int v15; // ecx
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // rdx
  bool v19; // sf
  unsigned int v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // r8
  _BYTE v24[8]; // [rsp+30h] [rbp-69h] BYREF
  int v25; // [rsp+38h] [rbp-61h] BYREF
  __int16 v26; // [rsp+3Ch] [rbp-5Dh]
  __int16 v27; // [rsp+3Eh] [rbp-5Bh]
  LPCWSTR lpFileName[2]; // [rsp+70h] [rbp-29h] BYREF
  int v29; // [rsp+80h] [rbp-19h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-11h] BYREF
  BSTR v31; // [rsp+90h] [rbp-9h] BYREF
  struct CPathCacheNode *v32; // [rsp+98h] [rbp-1h] BYREF
  const unsigned __int16 **v33; // [rsp+A0h] [rbp+7h] BYREF
  LPCWSTR lpSrc; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v35; // [rsp+B0h] [rbp+17h]
  unsigned __int8 v36; // [rsp+108h] [rbp+6Fh] BYREF
  struct CPathCache *v37; // [rsp+110h] [rbp+77h]

  v37 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v25, "CFileDescriptorEntry::_Initialize", 913, 1);
  lpSrc = &FileName;
  v8 = 924;
  v31 = 0;
  v9 = 0;
  bstrString = 0;
  v10 = 0;
  v35 = 0;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v24[0] = 0;
  if ( !a2 || (v26 = 924, v8 = 925, !a4) )
  {
    v25 = -2147024809;
    goto LABEL_6;
  }
  v26 = 925;
  v25 = 0;
  *a4 = 0;
  v25 = (*(__int64 (__fastcall **)(struct IVssWMFiledesc *, int *))(*(_QWORD *)a2 + 56LL))(a2, &v29);
  v8 = 934;
  if ( v25 < 0 )
    goto LABEL_6;
  v26 = 934;
  if ( (v29 & 0xF00) == 0 )
  {
    v11 = 937;
LABEL_60:
    v25 = 1;
    goto LABEL_61;
  }
  v25 = (*(__int64 (__fastcall **)(struct IVssWMFiledesc *, BSTR *))(*(_QWORD *)a2 + 24LL))(a2, &v31);
  v8 = 940;
  if ( v25 < 0 )
  {
LABEL_6:
    v27 = v8;
    goto LABEL_62;
  }
  v26 = 940;
  if ( !ATL::CComBSTR::Length((ATL::CComBSTR *)&v31) )
  {
    v11 = 1032;
    goto LABEL_60;
  }
  lpFileName[0] = &FileName;
  lpFileName[1] = 0;
  v36 = 0;
  v25 = CBsString::Set((CBsString *)&lpSrc, v31);
  v12 = 945;
  if ( v25 < 0 )
    goto LABEL_14;
  v13 = lpSrc;
  v26 = 945;
  v25 = CBsString::ExpandEnvironmentStringsW((CBsString *)lpFileName, lpSrc);
  if ( v25 >= 0 )
  {
    IsCsvFile = SxIsCsvFile(lpFileName[0], &v36);
    v25 = IsCsvFile;
    if ( IsCsvFile >= 0 )
    {
      if ( v36 )
        *a4 = 1;
      goto LABEL_22;
    }
    *a4 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids,
        lpFileName[0],
        IsCsvFile);
  }
  v25 = 0;
LABEL_22:
  if ( (_DWORD)v35 == 2 && isalpha(*v13) && v13[1] == 58 )
  {
    v25 = CBsString::Append((CBsString *)&lpSrc, L"\\");
    v12 = 984;
    if ( v25 < 0 )
      goto LABEL_14;
    v13 = lpSrc;
    v26 = 984;
  }
  v25 = CPathCacheNode::CreateInstance(&v32);
  if ( v25 < 0 )
  {
    v27 = 986;
    CBsString::_Release((CBsString *)lpFileName);
    v9 = v32;
    goto LABEL_62;
  }
  v9 = v32;
  v26 = 986;
  v25 = CBsString::Set((struct CPathCacheNode *)((char *)v32 + 8), v13);
  v12 = 987;
  if ( v25 < 0 )
    goto LABEL_14;
  v26 = 987;
  v15 = CSxRefMap<CPathCache,CPathCacheNode>::Find(a3, v9, &v33);
  v25 = v15;
  if ( v15 < 0 )
  {
    v27 = 988;
    CBsString::_Release((CBsString *)lpFileName);
    v10 = v33;
    goto LABEL_62;
  }
  v10 = v33;
  v26 = 988;
  if ( !v15 )
  {
    v25 = CBsString::Set((CFileDescriptorEntry *)((char *)this + 40), v33[3]);
    v12 = 1018;
    if ( v25 < 0 )
      goto LABEL_14;
    v26 = 1018;
    v25 = CBsString::Set((CFileDescriptorEntry *)((char *)this + 8), v10[5]);
    v19 = v25 < 0;
    v12 = 1019;
    goto LABEL_49;
  }
  if ( !(unsigned int)SxIsPathUNC(v13) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids, v13);
    v25 = -2130706163;
    v12 = 999;
    goto LABEL_14;
  }
  v16 = SxCrackPath(v13, (CFileDescriptorEntry *)((char *)this + 40), (CFileDescriptorEntry *)((char *)this + 8));
  if ( v16 == -2147024894 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids, v13);
    v25 = -2130706162;
    v12 = 1008;
    goto LABEL_14;
  }
  v25 = v16;
  v19 = v16 < 0;
  v12 = 1011;
  if ( v19 )
    goto LABEL_14;
  v17 = (const unsigned __int16 *)*((_QWORD *)this + 5);
  v26 = 1011;
  v25 = CBsString::Set((struct CPathCacheNode *)((char *)v9 + 24), v17);
  v12 = 1012;
  if ( v25 < 0
    || (v18 = (const unsigned __int16 *)*((_QWORD *)this + 1),
        v26 = 1012,
        v25 = CBsString::Set((struct CPathCacheNode *)((char *)v9 + 40), v18),
        v12 = 1013,
        v25 < 0) )
  {
LABEL_14:
    v27 = v12;
    CBsString::_Release((CBsString *)lpFileName);
    goto LABEL_62;
  }
  v26 = 1013;
  v25 = CSxRefMap<CWriterEntryMap,CWriterEntry>::Insert(v37, v9);
  v19 = v25 < 0;
  v12 = 1014;
LABEL_49:
  if ( v19 )
    goto LABEL_14;
  v26 = v12;
  CBsString::_Release((CBsString *)lpFileName);
  v25 = (*(__int64 (__fastcall **)(struct IVssWMFiledesc *, BSTR *))(*(_QWORD *)a2 + 32LL))(a2, &bstrString);
  v8 = 1035;
  if ( v25 < 0 )
    goto LABEL_6;
  v26 = 1035;
  if ( !ATL::CComBSTR::Length((ATL::CComBSTR *)&bstrString) )
    goto LABEL_54;
  v25 = CBsString::Set((CFileDescriptorEntry *)((char *)this + 24), bstrString);
  v8 = 1038;
  if ( v25 < 0 )
    goto LABEL_6;
  v26 = 1038;
LABEL_54:
  v25 = (*(__int64 (__fastcall **)(struct IVssWMFiledesc *, _BYTE *))(*(_QWORD *)a2 + 40LL))(a2, v24);
  if ( v25 < 0 )
  {
    v8 = 1041;
    goto LABEL_6;
  }
  *((_BYTE *)this + 56) = v24[0];
  v11 = 1044;
  v25 = 0;
LABEL_61:
  v26 = v11;
LABEL_62:
  v20 = v25;
  if ( v10 )
    CFileDescriptorEntry::Release((CFileDescriptorEntry *)v10);
  if ( v9 )
    CFileDescriptorEntry::Release(v9);
  CBsString::_Release((CBsString *)&lpSrc);
  SysFreeString(bstrString);
  SysFreeString(v31);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v25, v21, v22);
  return v20;
}

```

## disassembly

```asm
0x180024640  mov     [rsp-8+arg_0], rbx
0x180024645  mov     [rsp-8+arg_10], r8
0x18002464a  push    rbp
0x18002464b  push    rsi
0x18002464c  push    rdi
0x18002464d  push    r12
0x18002464f  push    r13
0x180024651  push    r14
0x180024653  push    r15
0x180024655  lea     rbp, [rsp-27h]
0x18002465a  sub     rsp, 0C0h
0x180024661  mov     r15, r9
0x180024664  mov     r13, r8
0x180024667  mov     r12, rdx
0x18002466a  mov     r14, rcx
0x18002466d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024674  lea     rax, WPP_GLOBAL_Control
0x18002467b  cmp     rcx, rax
0x18002467e  jz      short loc_18002469E
0x180024680  test    dword ptr [rcx+1Ch], 20000000h
0x180024687  jz      short loc_18002469E
0x180024689  mov     rcx, [rcx+10h]
0x18002468d  lea     r8, WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids
0x180024694  mov     edx, 15h
0x180024699  call    WPP_SF_
0x18002469e  mov     r9d, 1; unsigned __int16
0x1800246a4  lea     rdx, aCfiledescripto; "CFileDescriptorEntry::_Initialize"
0x1800246ab  mov     r8d, 391h; unsigned __int16
0x1800246b1  lea     rcx, [rbp+57h+var_B8]; this
0x1800246b5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800246ba  xor     ebx, ebx
0x1800246bc  lea     rax, FileName
0x1800246c3  mov     [rbp+57h+lpSrc], rax
0x1800246c7  mov     eax, 39Ch
0x1800246cc  mov     [rbp+57h+var_60], rbx
0x1800246d0  mov     edi, ebx
0x1800246d2  mov     [rbp+57h+bstrString], rbx
0x1800246d6  mov     esi, ebx
0x1800246d8  mov     [rbp+57h+var_40], rbx
0x1800246dc  mov     [rbp+57h+var_70], ebx
0x1800246df  mov     [rbp+57h+var_58], rbx
0x1800246e3  mov     [rbp+57h+var_50], rbx
0x1800246e7  mov     [rbp+57h+var_C0], bl
0x1800246ea  test    r12, r12
0x1800246ed  jnz     short loc_1800246FF
0x1800246ef  mov     [rbp+57h+var_B8], 80070057h
0x1800246f6  mov     [rbp+57h+var_B2], ax
0x1800246fa  jmp     loc_180024B23
0x1800246ff  mov     [rbp+57h+var_B4], ax
0x180024703  mov     eax, 39Dh
0x180024708  test    r15, r15
0x18002470b  jz      short loc_1800246EF
0x18002470d  mov     [rbp+57h+var_B4], ax
0x180024711  lea     rdx, [rbp+57h+var_70]
0x180024715  mov     [rbp+57h+var_B8], ebx
0x180024718  mov     rcx, r12
0x18002471b  mov     [r15], bl
0x18002471e  mov     rax, [r12]
0x180024722  mov     rax, [rax+38h]
0x180024726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002472b  mov     [rbp+57h+var_B8], eax
0x18002472e  test    eax, eax
0x180024730  mov     eax, 3A6h
0x180024735  js      short loc_1800246F6
0x180024737  test    [rbp+57h+var_70], 0F00h
0x18002473e  mov     [rbp+57h+var_B4], ax
0x180024742  jnz     short loc_18002474E
0x180024744  mov     eax, 3A9h
0x180024749  jmp     loc_180024B18
0x18002474e  mov     rax, [r12]
0x180024752  lea     rdx, [rbp+57h+var_60]
0x180024756  mov     rcx, r12
0x180024759  mov     rax, [rax+18h]
0x18002475d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024762  mov     [rbp+57h+var_B8], eax
0x180024765  test    eax, eax
0x180024767  mov     eax, 3ACh
0x18002476c  js      short loc_1800246F6
0x18002476e  lea     rcx, [rbp+57h+var_60]; this
0x180024772  mov     [rbp+57h+var_B4], ax
0x180024776  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x18002477b  test    eax, eax
0x18002477d  jz      loc_180024B13
0x180024783  mov     rdx, [rbp+57h+var_60]; unsigned __int16 *
0x180024787  lea     rax, FileName
0x18002478e  lea     rcx, [rbp+57h+lpSrc]; this
0x180024792  mov     [rbp+57h+lpFileName], rax
0x180024796  mov     [rbp+57h+var_78], rbx
0x18002479a  mov     [rbp+57h+arg_8], bl
0x18002479d  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800247a2  mov     [rbp+57h+var_B8], eax
0x1800247a5  lea     rcx, [rbp+57h+lpFileName]; this
0x1800247a9  test    eax, eax
0x1800247ab  mov     eax, 3B1h
0x1800247b0  jns     short loc_1800247C0
0x1800247b2  mov     [rbp+57h+var_B2], ax
0x1800247b6  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800247bb  jmp     loc_180024B23
0x1800247c0  mov     rbx, [rbp+57h+lpSrc]
0x1800247c4  mov     rdx, rbx; lpSrc
0x1800247c7  mov     [rbp+57h+var_B4], ax
0x1800247cb  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x1800247d0  mov     [rbp+57h+var_B8], eax
0x1800247d3  test    eax, eax
0x1800247d5  js      loc_18002487D
0x1800247db  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800247df  lea     rdx, [rbp+57h+arg_8]; unsigned __int8 *
0x1800247e3  call    ?SxIsCsvFile@@YAJPEBGPEAE@Z; SxIsCsvFile(ushort const *,uchar *)
0x1800247e8  mov     [rbp+57h+var_B8], eax
0x1800247eb  test    eax, eax
0x1800247ed  jns     short loc_18002482D
0x1800247ef  mov     [r15], sil
0x1800247f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247f9  lea     r15, WPP_GLOBAL_Control
0x180024800  cmp     rcx, r15
0x180024803  jz      short loc_180024884
0x180024805  test    dword ptr [rcx+1Ch], 4000000h
0x18002480c  jz      short loc_180024884
0x18002480e  mov     r9, [rbp+57h+lpFileName]
0x180024812  lea     r8, WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids
0x180024819  mov     rcx, [rcx+10h]
0x18002481d  mov     edx, 16h
0x180024822  mov     [rsp+0F0h+var_D0], eax
0x180024826  call    WPP_SF_Sd
0x18002482b  jmp     short loc_180024884
0x18002482d  cmp     [rbp+57h+arg_8], sil
0x180024831  jz      short loc_180024837
0x180024833  mov     byte ptr [r15], 1
0x180024837  lea     r15, WPP_GLOBAL_Control
0x18002483e  cmp     dword ptr [rbp+57h+var_40], 2
0x180024842  jnz     short loc_180024891
0x180024844  movzx   ecx, word ptr [rbx]; C
0x180024847  call    cs:__imp_isalpha
0x18002484d  test    eax, eax
0x18002484f  jz      short loc_180024891
0x180024851  cmp     word ptr [rbx+2], 3Ah ; ':'
0x180024856  jnz     short loc_180024891
0x180024858  lea     rdx, asc_18003A0A0; "\\"
0x18002485f  lea     rcx, [rbp+57h+lpSrc]; this
0x180024863  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180024868  mov     [rbp+57h+var_B8], eax
0x18002486b  test    eax, eax
0x18002486d  mov     eax, 3D8h
0x180024872  jns     short loc_180024889
0x180024874  lea     rcx, [rbp+57h+lpFileName]
0x180024878  jmp     loc_1800247B2
0x18002487d  lea     r15, WPP_GLOBAL_Control
0x180024884  mov     [rbp+57h+var_B8], esi
0x180024887  jmp     short loc_18002483E
0x180024889  mov     rbx, [rbp+57h+lpSrc]
0x18002488d  mov     [rbp+57h+var_B4], ax
0x180024891  lea     rcx, [rbp+57h+var_58]; struct CPathCacheNode **
0x180024895  call    ?CreateInstance@CPathCacheNode@@SAJPEAPEAV1@@Z; CPathCacheNode::CreateInstance(CPathCacheNode * *)
0x18002489a  mov     [rbp+57h+var_B8], eax
0x18002489d  test    eax, eax
0x18002489f  mov     eax, 3DAh
0x1800248a4  jns     short loc_1800248BC
0x1800248a6  lea     rcx, [rbp+57h+lpFileName]; this
0x1800248aa  mov     [rbp+57h+var_B2], ax
0x1800248ae  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800248b3  mov     rdi, [rbp+57h+var_58]
0x1800248b7  jmp     loc_180024B23
0x1800248bc  mov     rdi, [rbp+57h+var_58]
0x1800248c0  mov     rdx, rbx; unsigned __int16 *
0x1800248c3  mov     [rbp+57h+var_B4], ax
0x1800248c7  lea     rcx, [rdi+8]; this
0x1800248cb  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800248d0  mov     [rbp+57h+var_B8], eax
0x1800248d3  test    eax, eax
0x1800248d5  mov     eax, 3DBh
0x1800248da  js      short loc_180024874
0x1800248dc  lea     r8, [rbp+57h+var_50]
0x1800248e0  mov     [rbp+57h+var_B4], ax
0x1800248e4  mov     rdx, rdi
0x1800248e7  mov     rcx, r13
0x1800248ea  call    ?Find@?$CSxRefMap@VCPathCache@@VCPathCacheNode@@@@QEAAJPEAVCPathCacheNode@@PEAPEAV2@@Z; CSxRefMap<CPathCache,CPathCacheNode>::Find(CPathCacheNode *,CPathCacheNode * *)
0x1800248ef  mov     ecx, eax
0x1800248f1  mov     [rbp+57h+var_B8], eax
0x1800248f4  test    eax, eax
0x1800248f6  mov     eax, 3DCh
0x1800248fb  jns     short loc_180024913
0x1800248fd  lea     rcx, [rbp+57h+lpFileName]; this
0x180024901  mov     [rbp+57h+var_B2], ax
0x180024905  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18002490a  mov     rsi, [rbp+57h+var_50]
0x18002490e  jmp     loc_180024B23
0x180024913  mov     rsi, [rbp+57h+var_50]
0x180024917  mov     [rbp+57h+var_B4], ax
0x18002491b  test    ecx, ecx
0x18002491d  jz      loc_180024AC1
0x180024923  mov     rcx, rbx; unsigned __int16 *
0x180024926  call    ?SxIsPathUNC@@YAJPEBG@Z; SxIsPathUNC(ushort const *)
0x18002492b  test    eax, eax
0x18002492d  jnz     short loc_18002496B
0x18002492f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024936  cmp     rcx, r15
0x180024939  jz      short loc_18002495A
0x18002493b  test    dword ptr [rcx+1Ch], 2000000h
0x180024942  jz      short loc_18002495A
0x180024944  mov     rcx, [rcx+10h]
0x180024948  lea     edx, [rax+17h]
0x18002494b  mov     r9, rbx
0x18002494e  lea     r8, WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids
0x180024955  call    WPP_SF_S
0x18002495a  mov     [rbp+57h+var_B8], 8100010Dh
0x180024961  mov     eax, 3E7h
0x180024966  jmp     loc_180024874
0x18002496b  lea     r8, [r14+8]; struct CBsString *
0x18002496f  mov     rcx, rbx; lpSrc
0x180024972  lea     rdx, [r14+28h]; this
0x180024976  call    ?SxCrackPath@@YAJPEBGPEAVCBsString@@1@Z; SxCrackPath(ushort const *,CBsString *,CBsString *)
0x18002497b  cmp     eax, 80070002h
0x180024980  jnz     short loc_1800249C7
0x180024982  mov     rcx, cs:WPP_GLOBAL_Control
0x180024989  lea     rax, WPP_GLOBAL_Control
0x180024990  cmp     rcx, rax
0x180024993  jz      short loc_1800249B6
0x180024995  test    dword ptr [rcx+1Ch], 2000000h
0x18002499c  jz      short loc_1800249B6
0x18002499e  mov     rcx, [rcx+10h]
0x1800249a2  lea     r8, WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids
0x1800249a9  mov     edx, 18h
0x1800249ae  mov     r9, rbx
0x1800249b1  call    WPP_SF_S
0x1800249b6  mov     [rbp+57h+var_B8], 8100010Eh
0x1800249bd  mov     eax, 3F0h
0x1800249c2  jmp     loc_180024874
0x1800249c7  mov     [rbp+57h+var_B8], eax
0x1800249ca  test    eax, eax
0x1800249cc  mov     eax, 3F3h
0x1800249d1  js      loc_180024874
0x1800249d7  mov     rdx, [r14+28h]; unsigned __int16 *
0x1800249db  lea     rcx, [rdi+18h]; this
0x1800249df  mov     [rbp+57h+var_B4], ax
0x1800249e3  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800249e8  mov     [rbp+57h+var_B8], eax
0x1800249eb  test    eax, eax
0x1800249ed  mov     eax, 3F4h
0x1800249f2  js      loc_180024874
0x1800249f8  mov     rdx, [r14+8]; unsigned __int16 *
0x1800249fc  lea     rcx, [rdi+28h]; this
0x180024a00  mov     [rbp+57h+var_B4], ax
0x180024a04  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180024a09  mov     [rbp+57h+var_B8], eax
0x180024a0c  test    eax, eax
0x180024a0e  mov     eax, 3F5h
0x180024a13  js      loc_180024874
0x180024a19  mov     rcx, [rbp+57h+arg_10]
0x180024a1d  mov     rdx, rdi
0x180024a20  mov     [rbp+57h+var_B4], ax
0x180024a24  call    ?Insert@?$CSxRefMap@VCWriterEntryMap@@VCWriterEntry@@@@QEAAJPEAVCWriterEntry@@PEAPEAV2@@Z; CSxRefMap<CWriterEntryMap,CWriterEntry>::Insert(CWriterEntry *,CWriterEntry * *)
0x180024a29  mov     [rbp+57h+var_B8], eax
0x180024a2c  test    eax, eax
0x180024a2e  mov     eax, 3F6h
0x180024a33  js      loc_180024874
0x180024a39  lea     rcx, [rbp+57h+lpFileName]; this
0x180024a3d  mov     [rbp+57h+var_B4], ax
0x180024a41  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180024a46  mov     rax, [r12]
0x180024a4a  lea     rdx, [rbp+57h+bstrString]
0x180024a4e  mov     rcx, r12
0x180024a51  mov     rax, [rax+20h]
0x180024a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a5a  mov     [rbp+57h+var_B8], eax
0x180024a5d  test    eax, eax
0x180024a5f  mov     eax, 40Bh
0x180024a64  js      loc_1800246F6
0x180024a6a  lea     rcx, [rbp+57h+bstrString]; this
0x180024a6e  mov     [rbp+57h+var_B4], ax
0x180024a72  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x180024a77  test    eax, eax
0x180024a79  jz      short loc_180024A9C
0x180024a7b  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x180024a7f  lea     rcx, [r14+18h]; this
0x180024a83  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180024a88  mov     [rbp+57h+var_B8], eax
0x180024a8b  test    eax, eax
0x180024a8d  mov     eax, 40Eh
0x180024a92  js      loc_1800246F6
0x180024a98  mov     [rbp+57h+var_B4], ax
0x180024a9c  mov     rax, [r12]
0x180024aa0  lea     rdx, [rbp+57h+var_C0]
0x180024aa4  mov     rcx, r12
0x180024aa7  mov     rax, [rax+28h]
0x180024aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ab0  mov     [rbp+57h+var_B8], eax
0x180024ab3  test    eax, eax
0x180024ab5  jns     short loc_180024AFE
0x180024ab7  mov     eax, 411h
0x180024abc  jmp     loc_1800246F6
0x180024ac1  mov     rdx, [rsi+18h]; unsigned __int16 *
0x180024ac5  lea     rcx, [r14+28h]; this
0x180024ac9  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180024ace  mov     [rbp+57h+var_B8], eax
0x180024ad1  test    eax, eax
0x180024ad3  mov     eax, 3FAh
0x180024ad8  js      loc_180024874
0x180024ade  mov     [rbp+57h+var_B4], ax
0x180024ae2  lea     rcx, [r14+8]; this
0x180024ae6  mov     rdx, [rsi+28h]; unsigned __int16 *
  ... truncated ...
```
