# CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_dependentAssembly_assemblyIdentity(ushort,_SXS_NODE_INFO const *)

- ea: `0x180065700`
- end: `0x1800659e4`
- name: `?XMLParser_Element_doc_configuration_windows_assemblyBinding_dependentAssembly_assemblyIdentity@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `740`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x1800075c0`
- `0x180009f00`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x180022d40`
- `0x18002b580`
- `0x1800419e4`
- `0x180041f10`
- `0x1800515ec`
- `0x180052698`
- `0x180057858`
- `0x18005d2e4`
- `0x1800650e8`
- `0x180065700`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006577c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800657c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800657f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065822`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800658d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800658e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065968`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006598a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006577c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800657c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800657f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065822`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800658d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800658e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065968`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006598a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006589a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006589a`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_dependentAssembly_assemblyIdentity(
        CNodeFactory *this,
        unsigned __int16 a2,
        const struct _SXS_NODE_INFO *a3)
{
  unsigned int v3; // ebx
  const struct _ACTCTXCTB_PARSE_CONTEXT *v6; // rdx
  __int64 v7; // rcx
  char **v8; // rcx
  struct _ASSEMBLY_IDENTITY *v9; // rdi
  __int64 v10; // rcx
  _DWORD *v11; // rax
  const char *v12; // rcx
  _DWORD *v13; // rbx
  void *v14; // rcx
  unsigned int v15; // ebx
  const struct _UNICODE_STRING *v17; // [rsp+30h] [rbp-110h]
  const struct _UNICODE_STRING *v18; // [rsp+38h] [rbp-108h]
  const struct _UNICODE_STRING *v19; // [rsp+40h] [rbp-100h]
  const struct _UNICODE_STRING *v20; // [rsp+48h] [rbp-F8h]
  const struct _UNICODE_STRING *v21; // [rsp+50h] [rbp-F0h]
  const struct _UNICODE_STRING *v22; // [rsp+58h] [rbp-E8h]
  const struct _UNICODE_STRING *v23; // [rsp+60h] [rbp-E0h]
  const struct _UNICODE_STRING *v24; // [rsp+68h] [rbp-D8h]
  const struct _UNICODE_STRING *v25; // [rsp+70h] [rbp-D0h]
  const struct _UNICODE_STRING *v26; // [rsp+78h] [rbp-C8h]
  const struct _UNICODE_STRING *v27; // [rsp+80h] [rbp-C0h]
  const struct _UNICODE_STRING *v28; // [rsp+88h] [rbp-B8h]
  const struct _UNICODE_STRING *v29; // [rsp+90h] [rbp-B0h]
  const struct _UNICODE_STRING *v30; // [rsp+98h] [rbp-A8h]
  const struct _UNICODE_STRING *v31; // [rsp+A0h] [rbp-A0h]
  const struct _UNICODE_STRING *v32; // [rsp+A8h] [rbp-98h]
  const struct _UNICODE_STRING *v33; // [rsp+B0h] [rbp-90h]
  _DWORD *v34; // [rsp+C0h] [rbp-80h] BYREF
  char v35; // [rsp+C8h] [rbp-78h]
  struct _ASSEMBLY_IDENTITY *v36; // [rsp+D0h] [rbp-70h] BYREF
  char v37; // [rsp+D8h] [rbp-68h]
  __int64 v38; // [rsp+E0h] [rbp-60h] BYREF
  _BYTE v39[16]; // [rsp+E8h] [rbp-58h] BYREF
  int v40; // [rsp+F8h] [rbp-48h] BYREF
  int v41; // [rsp+100h] [rbp-40h] BYREF
  __int64 v42; // [rsp+108h] [rbp-38h]
  __int64 *v43; // [rsp+110h] [rbp-30h]
  __int64 v44; // [rsp+118h] [rbp-28h]
  int v45; // [rsp+120h] [rbp-20h]
  unsigned int *v46; // [rsp+128h] [rbp-18h]

  v3 = a2;
  v43 = &qword_180078FA8;
  v41 = 1;
  v46 = (unsigned int *)&v40;
  v40 = 0;
  v42 = 0;
  v44 = 544438355;
  v45 = 2953;
  CFrame::BaseEnter((CFrame *)&v41);
  v36 = 0;
  v34 = 0;
  v35 = 0;
  v38 = 0;
  SetLastError(0);
  v37 = 1;
  if ( !(unsigned int)SxspCreateAssemblyIdentityFromIdentityElement(v7, v6, 2u, &v36, v3, a3) )
  {
    v8 = off_180078F88;
LABEL_3:
    *v46 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v8);
    goto LABEL_19;
  }
  SetLastError(0);
  v9 = v36;
  if ( !(unsigned int)CNodeFactory::ValidateIdentity(this, 10, 2, v36) )
  {
    v8 = off_180078F68;
    goto LABEL_3;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspGenerateTextuallyEncodedPolicyIdentityFromAssemblyIdentity(v10, v9, (char *)this + 1272) )
  {
    v8 = off_180078F48;
    goto LABEL_3;
  }
  SetLastError(0);
  CCountedStringHolder<CUnicodeCharTraits>::CCountedStringHolder<CUnicodeCharTraits>(v39, (char *)this + 1272);
  if ( !(unsigned int)CStringPtrTable<CPolicyStatement,CUnicodeCharTraits,1,CCaseInsensitiveUnicodeStringPtrTableHelper<CPolicyStatement>>::Find(
                        *((_QWORD *)this + 2) + 1656LL,
                        v39,
                        &v38) )
  {
    v8 = off_180078F28;
    goto LABEL_3;
  }
  if ( v38 )
  {
    CNodeFactory::LogParseError(
      this,
      0xC1010035,
      0x8Au,
      0,
      0,
      0,
      v17,
      v18,
      v19,
      v20,
      v21,
      v22,
      v23,
      v24,
      v25,
      v26,
      v27,
      v28,
      v29,
      v30,
      v31,
      v32,
      v33);
    goto LABEL_19;
  }
  v11 = HeapAlloc(g_hHeap, 0, 0x30u);
  v13 = v11;
  if ( !v11 )
  {
    FusionpTraceAllocFailure(v12);
    SetLastError(0xEu);
    *v46 = 0;
    goto LABEL_19;
  }
  v11[6] = 0;
  *((_QWORD *)v11 + 4) = 0;
  *(_QWORD *)v11 = v11;
  *((_QWORD *)v11 + 1) = v11;
  *((_QWORD *)v11 + 2) = v11;
  *((_BYTE *)v11 + 40) = 1;
  v34 = v11;
  v35 = 1;
  SetLastError(0);
  SetLastError(0);
  CCountedStringHolder<CUnicodeCharTraits>::CCountedStringHolder<CUnicodeCharTraits>(v39, (char *)this + 1272);
  if ( !(unsigned int)CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CPolicyStatement *,CPolicyStatement *,CCaseInsensitiveUnicodeStringPtrTableHelper<CPolicyStatement>,7,0>::Insert(
                        *((_QWORD *)this + 2) + 1656LL,
                        v39,
                        v13,
                        183) )
  {
    v8 = off_180078F08;
    goto LABEL_3;
  }
  *((_BYTE *)v13 + 40) = *(_DWORD *)(*((_QWORD *)this + 2) + 1300LL) <= 1u;
  v14 = (void *)*((_QWORD *)this + 156);
  v34 = 0;
  v35 = 0;
  *((_QWORD *)this + 157) = v13;
  if ( v14 )
    SxsDestroyAssemblyIdentity(v14);
  v36 = 0;
  v37 = 0;
  *((_QWORD *)this + 156) = v9;
  SetLastError(0);
  *v46 = 1;
LABEL_19:
  v15 = *v46;
  CSmartPtr<CPolicyStatement,CSmartPtrBaseTypeHelper<CPolicyStatement>>::~CSmartPtr<CPolicyStatement,CSmartPtrBaseTypeHelper<CPolicyStatement>>(&v34);
  CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>::~CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>(&v36);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v41);
  return v15;
}

```

## disassembly

```asm
0x180065700  mov     [rsp-28h+arg_8], rbx
0x180065705  push    rbp
0x180065706  push    rsi
0x180065707  push    rdi
0x180065708  push    r14
0x18006570a  push    r15
0x18006570c  mov     rbp, rsp
0x18006570f  sub     rsp, 140h
0x180065716  mov     rax, cs:__security_cookie
0x18006571d  xor     rax, rsp
0x180065720  mov     [rbp+var_10], rax
0x180065724  lea     rax, qword_180078FA8
0x18006572b  movzx   ebx, dx
0x18006572e  mov     [rbp+var_30], rax
0x180065732  mov     rsi, rcx
0x180065735  lea     rax, [rbp+var_48]
0x180065739  mov     [rbp+var_40], 1
0x180065740  xor     r15d, r15d
0x180065743  mov     [rbp+var_18], rax
0x180065747  lea     rcx, [rbp+var_40]; this
0x18006574b  mov     [rbp+var_48], r15d
0x18006574f  mov     rdi, r8
0x180065752  mov     [rbp+var_38], r15
0x180065756  mov     [rbp+var_28], 20737853h
0x18006575e  mov     [rbp+var_20], 0B89h
0x180065765  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18006576a  xor     ecx, ecx; dwErrCode
0x18006576c  mov     [rbp+var_70], r15
0x180065770  mov     [rbp+var_80], r15
0x180065774  mov     [rbp+var_78], r15b
0x180065778  mov     [rbp+var_60], r15
0x18006577c  call    cs:__imp_SetLastError
0x180065783  nop     dword ptr [rax+rax+00h]
0x180065788  mov     [rsp+140h+var_118], rdi; struct _SXS_NODE_INFO *
0x18006578d  lea     r9, [rbp+var_70]; struct _ASSEMBLY_IDENTITY **
0x180065791  mov     dword ptr [rsp+140h+var_120], ebx; unsigned int
0x180065795  lea     ebx, [r15+2]
0x180065799  mov     r8d, ebx; unsigned int
0x18006579c  mov     [rbp+var_68], 1
0x1800657a0  call    ?SxspCreateAssemblyIdentityFromIdentityElement@@YAHKPEBU_ACTCTXCTB_PARSE_CONTEXT@@KPEAPEAU_ASSEMBLY_IDENTITY@@KPEBU_SXS_NODE_INFO@@@Z; SxspCreateAssemblyIdentityFromIdentityElement(ulong,_ACTCTXCTB_PARSE_CONTEXT const *,ulong,_ASSEMBLY_IDENTITY * *,ulong,_SXS_NODE_INFO const *)
0x1800657a5  test    eax, eax
0x1800657a7  jnz     short loc_1800657C1
0x1800657a9  lea     rcx, off_180078F88; struct _CALL_SITE_INFO *
0x1800657b0  mov     rax, [rbp+var_18]
0x1800657b4  mov     [rax], r15d
0x1800657b7  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800657bc  jmp     loc_18006599D
0x1800657c1  xor     ecx, ecx; dwErrCode
0x1800657c3  call    cs:__imp_SetLastError
0x1800657ca  nop     dword ptr [rax+rax+00h]
0x1800657cf  mov     rdi, [rbp+var_70]
0x1800657d3  mov     r8d, ebx; unsigned int
0x1800657d6  mov     r9, rdi; struct _ASSEMBLY_IDENTITY *
0x1800657d9  mov     edx, 0Ah; unsigned int
0x1800657de  mov     rcx, rsi; this
0x1800657e1  call    ?ValidateIdentity@CNodeFactory@@QEAAHKKPEBU_ASSEMBLY_IDENTITY@@@Z; CNodeFactory::ValidateIdentity(ulong,ulong,_ASSEMBLY_IDENTITY const *)
0x1800657e6  test    eax, eax
0x1800657e8  jnz     short loc_1800657F3
0x1800657ea  lea     rcx, off_180078F68; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x1800657f1  jmp     short loc_1800657B0
0x1800657f3  xor     ecx, ecx; dwErrCode
0x1800657f5  call    cs:__imp_SetLastError
0x1800657fc  nop     dword ptr [rax+rax+00h]
0x180065801  lea     r14, [rsi+4F8h]
0x180065808  mov     rdx, rdi
0x18006580b  mov     r8, r14
0x18006580e  call    ?SxspGenerateTextuallyEncodedPolicyIdentityFromAssemblyIdentity@@YAHKPEBU_ASSEMBLY_IDENTITY@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEAPEAU1@@Z; SxspGenerateTextuallyEncodedPolicyIdentityFromAssemblyIdentity(ulong,_ASSEMBLY_IDENTITY const *,CGenericBaseStringBuffer<CUnicodeCharTraits> &,_ASSEMBLY_IDENTITY * *)
0x180065813  test    eax, eax
0x180065815  jnz     short loc_180065820
0x180065817  lea     rcx, off_180078F48; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x18006581e  jmp     short loc_1800657B0
0x180065820  xor     ecx, ecx; dwErrCode
0x180065822  call    cs:__imp_SetLastError
0x180065829  nop     dword ptr [rax+rax+00h]
0x18006582e  mov     rdx, r14
0x180065831  lea     rcx, [rbp+var_58]
0x180065835  call    ??0?$CCountedStringHolder@VCUnicodeCharTraits@@@@QEAA@AEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; CCountedStringHolder<CUnicodeCharTraits>::CCountedStringHolder<CUnicodeCharTraits>(CGenericBaseStringBuffer<CUnicodeCharTraits> const &)
0x18006583a  mov     rcx, [rsi+10h]
0x18006583e  lea     r8, [rbp+var_60]
0x180065842  add     rcx, 678h
0x180065849  lea     rdx, [rbp+var_58]
0x18006584d  call    ?Find@?$CStringPtrTable@VCPolicyStatement@@VCUnicodeCharTraits@@$00V?$CCaseInsensitiveUnicodeStringPtrTableHelper@VCPolicyStatement@@@@@@QEAAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@AEAPEAVCPolicyStatement@@@Z; CStringPtrTable<CPolicyStatement,CUnicodeCharTraits,1,CCaseInsensitiveUnicodeStringPtrTableHelper<CPolicyStatement>>::Find(CCountedStringHolder<CUnicodeCharTraits> const &,CPolicyStatement * &)
0x180065852  test    eax, eax
0x180065854  jnz     short loc_180065862
0x180065856  lea     rcx, off_180078F28; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x18006585d  jmp     loc_1800657B0
0x180065862  cmp     [rbp+var_60], r15
0x180065866  jz      short loc_18006588D
0x180065868  mov     [rsp+140h+var_118], r15; struct _UNICODE_STRING *
0x18006586d  xor     r9d, r9d; struct _UNICODE_STRING *
0x180065870  mov     edx, 0C1010035h; unsigned int
0x180065875  mov     [rsp+140h+var_120], r15; struct _UNICODE_STRING *
0x18006587a  mov     r8d, 8Ah; unsigned int
0x180065880  mov     rcx, rsi; this
0x180065883  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180065888  jmp     loc_18006599D
0x18006588d  mov     rcx, cs:g_hHeap; hHeap
0x180065894  xor     edx, edx; dwFlags
0x180065896  lea     r8d, [rdx+30h]; dwBytes
0x18006589a  call    cs:__imp_HeapAlloc
0x1800658a1  nop     dword ptr [rax+rax+00h]
0x1800658a6  mov     rbx, rax
0x1800658a9  test    rax, rax
0x1800658ac  jz      loc_180065980
0x1800658b2  mov     [rax+18h], r15d
0x1800658b6  mov     [rax+20h], r15
0x1800658ba  mov     [rax], rax
0x1800658bd  mov     [rax+8], rax
0x1800658c1  mov     [rax+10h], rax
0x1800658c5  mov     byte ptr [rax+28h], 1
0x1800658c9  mov     [rbp+var_80], rax
0x1800658cd  mov     [rbp+var_78], 1
0x1800658d1  xor     ecx, ecx; dwErrCode
0x1800658d3  call    cs:__imp_SetLastError
0x1800658da  nop     dword ptr [rax+rax+00h]
0x1800658df  xor     ecx, ecx; dwErrCode
0x1800658e1  call    cs:__imp_SetLastError
0x1800658e8  nop     dword ptr [rax+rax+00h]
0x1800658ed  mov     rdx, r14
0x1800658f0  lea     rcx, [rbp+var_58]
0x1800658f4  call    ??0?$CCountedStringHolder@VCUnicodeCharTraits@@@@QEAA@AEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; CCountedStringHolder<CUnicodeCharTraits>::CCountedStringHolder<CUnicodeCharTraits>(CGenericBaseStringBuffer<CUnicodeCharTraits> const &)
0x1800658f9  mov     rcx, [rsi+10h]
0x1800658fd  lea     rdx, [rbp+var_58]
0x180065901  add     rcx, 678h
0x180065908  mov     r9d, 0B7h
0x18006590e  mov     r8, rbx
0x180065911  call    ?Insert@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCPolicyStatement@@PEAV3@V?$CCaseInsensitiveUnicodeStringPtrTableHelper@VCPolicyStatement@@@@$06$0A@@@QEAAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@PEAVCPolicyStatement@@K@Z; CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CPolicyStatement *,CPolicyStatement *,CCaseInsensitiveUnicodeStringPtrTableHelper<CPolicyStatement>,7,0>::Insert(CCountedStringHolder<CUnicodeCharTraits> const &,CPolicyStatement *,ulong)
0x180065916  test    eax, eax
0x180065918  jnz     short loc_180065926
0x18006591a  lea     rcx, off_180078F08; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180065921  jmp     loc_1800657B0
0x180065926  mov     rax, [rsi+10h]
0x18006592a  cmp     dword ptr [rax+514h], 1
0x180065931  setbe   al
0x180065934  mov     [rbx+28h], al
0x180065937  mov     rcx, [rsi+4E0h]; lpMem
0x18006593e  mov     [rbp+var_80], r15
0x180065942  mov     [rbp+var_78], r15b
0x180065946  mov     [rsi+4E8h], rbx
0x18006594d  test    rcx, rcx
0x180065950  jz      short loc_180065957
0x180065952  call    SxsDestroyAssemblyIdentity
0x180065957  xor     ecx, ecx; dwErrCode
0x180065959  mov     [rbp+var_70], r15
0x18006595d  mov     [rbp+var_68], r15b
0x180065961  mov     [rsi+4E0h], rdi
0x180065968  call    cs:__imp_SetLastError
0x18006596f  nop     dword ptr [rax+rax+00h]
0x180065974  mov     rax, [rbp+var_18]
0x180065978  mov     dword ptr [rax], 1
0x18006597e  jmp     short loc_18006599D
0x180065980  call    ?FusionpTraceAllocFailure@@YAXPEBD@Z; FusionpTraceAllocFailure(char const *)
0x180065985  mov     ecx, 0Eh; dwErrCode
0x18006598a  call    cs:__imp_SetLastError
0x180065991  nop     dword ptr [rax+rax+00h]
0x180065996  mov     rax, [rbp+var_18]
0x18006599a  mov     [rax], r15d
0x18006599d  mov     rax, [rbp+var_18]
0x1800659a1  lea     rcx, [rbp+var_80]
0x1800659a5  mov     ebx, [rax]
0x1800659a7  call    ??1?$CSmartPtr@VCPolicyStatement@@V?$CSmartPtrBaseTypeHelper@VCPolicyStatement@@@@@@QEAA@XZ; CSmartPtr<CPolicyStatement,CSmartPtrBaseTypeHelper<CPolicyStatement>>::~CSmartPtr<CPolicyStatement,CSmartPtrBaseTypeHelper<CPolicyStatement>>(void)
0x1800659ac  lea     rcx, [rbp+var_70]
0x1800659b0  call    ??1?$CSmartPtrWithNamedDestructor@U_ASSEMBLY_IDENTITY@@$1?SxsDestroyAssemblyIdentity@@YAXPEAU1@@ZV?$CSmartPtrWithNamedDestructorHelper@U_ASSEMBLY_IDENTITY@@$1?SxsDestroyAssemblyIdentity@@YAXPEAU1@@Z@@@@QEAA@XZ; CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>::~CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>(void)
0x1800659b5  lea     rcx, [rbp+var_40]; this
0x1800659b9  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x1800659be  mov     eax, ebx
0x1800659c0  mov     rcx, [rbp+var_10]
0x1800659c4  xor     rcx, rsp; StackCookie
0x1800659c7  call    __security_check_cookie
0x1800659cc  mov     rbx, [rsp+140h+arg_8]
0x1800659d4  add     rsp, 140h
0x1800659db  pop     r15
0x1800659dd  pop     r14
0x1800659df  pop     rdi
0x1800659e0  pop     rsi
0x1800659e1  pop     rbp
0x1800659e2  retn
```
