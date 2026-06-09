# SxspComponentParsePolicyCore(ulong,_ACTCTXGENCTX *,CProbedAssemblyInformation const &,CPolicyStatement * &,IStream *,_ACTCTXCTB_ASSEMBLY_CONTEXT *)

- ea: `0x18002af5c`
- end: `0x18002b4ba`
- name: `?SxspComponentParsePolicyCore@@YAHKPEAU_ACTCTXGENCTX@@AEBVCProbedAssemblyInformation@@AEAPEAVCPolicyStatement@@PEAUIStream@@PEAU_ACTCTXCTB_ASSEMBLY_CONTEXT@@@Z`
- size: `1374`
- prototype: `int(unsigned int, struct _ACTCTXGENCTX *, const struct CProbedAssemblyInformation *, struct CPolicyStatement **, struct IStream *, struct _ACTCTXCTB_ASSEMBLY_CONTEXT *)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003e424`

## callees

- `0x1800057e0`
- `0x180005d30`
- `0x18000df40`
- `0x18000dffc`
- `0x180010bd0`
- `0x1800176fc`
- `0x18001c270`
- `0x180029930`
- `0x18002af5c`
- `0x18002b4c0`
- `0x18002b514`
- `0x18002b580`
- `0x18002b5e4`
- `0x18002e9e0`
- `0x18002ed00`
- `0x180030148`
- `0x180033e98`
- `0x18004e630`
- `0x18004e818`
- `0x180051a70`
- `0x180057e98`
- `0x18005c978`
- `0x18005cdcc`
- `0x18005d2b0`
- `0x18006a0f5`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b407`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b060`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b087`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b0cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b0f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b136`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b164`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b1b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b201`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b237`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b279`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b2a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b2e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b334`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b351`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b384`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b44c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b060`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b087`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b0cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b0f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b136`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b164`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b1b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b201`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b237`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b279`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b2a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b2e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b334`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b351`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b384`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b44c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b0a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b1cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b0a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b1cc`

## pseudocode

```c
__int64 __fastcall SxspComponentParsePolicyCore(
        __int64 a1,
        struct _ACTCTXGENCTX *a2,
        const struct CProbedAssemblyInformation *a3,
        struct CPolicyStatement **a4,
        struct IStream *a5)
{
  const struct _ACTCTXCTB_ASSEMBLY_CONTEXT *v8; // rsi
  _ASSEMBLY *v9; // rdi
  const char *v10; // rcx
  _ASSEMBLY *v11; // rax
  char **v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  int v15; // ebx
  int v16; // edx
  CNodeFactory *v17; // rax
  CNodeFactory *v18; // rbx
  const struct _GUID *v19; // rcx
  int v20; // eax
  int v21; // esi
  int v22; // esi
  DWORD v23; // eax
  __int64 i; // rsi
  __int64 v25; // r14
  DWORD j; // ebx
  unsigned int v27; // ebx
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  char v31; // [rsp+40h] [rbp-C0h]
  CNodeFactory *v32; // [rsp+48h] [rbp-B8h] BYREF
  char v33; // [rsp+50h] [rbp-B0h]
  int v34; // [rsp+58h] [rbp-A8h] BYREF
  void *v35; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+70h] [rbp-90h]
  __int64 *v38; // [rsp+78h] [rbp-88h]
  __int64 v39; // [rsp+80h] [rbp-80h]
  int v40; // [rsp+88h] [rbp-78h]
  int *v41; // [rsp+90h] [rbp-70h]
  __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  int v43; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v44; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v45; // [rsp+B8h] [rbp-48h] BYREF
  int v46; // [rsp+C0h] [rbp-40h]
  __int64 v47; // [rsp+C8h] [rbp-38h]
  __int64 v48; // [rsp+D0h] [rbp-30h]
  __int64 v49; // [rsp+D8h] [rbp-28h]
  __int128 v50; // [rsp+E0h] [rbp-20h]
  __int128 v51; // [rsp+F0h] [rbp-10h]
  __int128 v52; // [rsp+100h] [rbp+0h]
  __int64 v53; // [rsp+110h] [rbp+10h]
  __int64 v54; // [rsp+118h] [rbp+18h]
  __int64 v55; // [rsp+120h] [rbp+20h]
  _BYTE v56[24]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v57[56]; // [rsp+148h] [rbp+48h] BYREF

  v38 = &qword_18006DF08;
  v34 = 0;
  v41 = &v34;
  v36 = 1;
  v37 = 0;
  v39 = 544438355;
  v8 = 0;
  v40 = 42;
  CFrame::BaseEnter((CFrame *)&v36);
  v32 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v33 = 0;
  v35 = 0;
  v9 = 0;
  v30 = 0;
  v31 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  memset_0(v56, 0, 0x50u);
  *a4 = 0;
  if ( !a2 )
  {
    v40 = 54;
LABEL_3:
    FusionpTraceParameterCheck(v10);
    SetLastError(0x57u);
    *v41 = 0;
    goto LABEL_41;
  }
  if ( !a5 )
  {
    v40 = 55;
    goto LABEL_3;
  }
  SetLastError(0);
  v11 = (_ASSEMBLY *)HeapAlloc(g_hHeap, 0, 0x370u);
  if ( !v11 || (v9 = _ASSEMBLY::_ASSEMBLY(v11)) == 0 )
  {
    v12 = off_18006FD10;
    goto LABEL_38;
  }
  SetLastError(0);
  if ( !(unsigned int)CProbedAssemblyInformation::Initialize((_ASSEMBLY *)((char *)v9 + 32), a3) )
  {
    v12 = off_180077260;
LABEL_38:
    *v41 = 0;
    goto LABEL_39;
  }
  SetLastError(0);
  v13 = *(_QWORD *)a3;
  v31 = 1;
  if ( !(unsigned int)SxsDuplicateAssemblyIdentity(0, v13, &v30) )
  {
    v12 = off_180077240;
    goto LABEL_38;
  }
  v49 = v30;
  v31 = 0;
  SetLastError(0);
  if ( !(unsigned int)CProbedAssemblyInformation::GetManifestPath(a3, (const unsigned __int16 **)&v44, &v45) )
  {
    v12 = off_180077220;
    goto LABEL_38;
  }
  SetLastError(0);
  v14 = (*(__int64 (__fastcall **)(struct IStream *, _BYTE *, __int64))(*(_QWORD *)a5 + 96LL))(a5, v56, 1);
  v15 = v14;
  if ( v14 >= 0 )
  {
    SetLastError(0);
    v17 = (CNodeFactory *)HeapAlloc(g_hHeap, 0, 0x738u);
    if ( v17 && (v32 = CNodeFactory::CNodeFactory(v17), (v18 = v32) != 0) )
    {
      v33 = 1;
      SetLastError(0);
      if ( (unsigned int)CNodeFactory::Initialize(v18, a2, v9, (struct _ACTCTXCTB_ASSEMBLY_CONTEXT *)&v42) )
      {
        SetLastError(0);
        if ( (unsigned int)CNodeFactory::SetParseType((_DWORD)v18, 2, *((_DWORD *)a3 + 2), (int)a3 + 16, (__int64)v57) )
        {
          SetLastError(0);
          if ( (unsigned int)SxspGetXMLParser(v19, &v35) )
          {
            SetLastError(0);
            v20 = (*(__int64 (__fastcall **)(void *, CNodeFactory *))(*(_QWORD *)v35 + 24LL))(v35, v18);
            v21 = v20;
            if ( v20 >= 0 )
            {
              SetLastError(0);
              v22 = (*(__int64 (__fastcall **)(void *, struct IStream *))(*(_QWORD *)v35 + 128LL))(v35, a5);
              if ( v22 < 0
                || (SetLastError(0),
                    v22 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v35 + 192LL))(v35, 0xFFFFFFFFLL),
                    v22 < 0) )
              {
                FusionpTraceCOMFailureOrigination(v22, byte_18008517D);
                v29 = v22;
                FusionpConvertCOMFailure(&v29);
                v23 = FusionpHRESULTToWin32(v29);
                SetLastError(v23);
                *v41 = 0;
              }
              else
              {
                for ( i = 0; (unsigned int)i < *((_DWORD *)a2 + 2); i = (unsigned int)(i + 1) )
                {
                  SetLastError(0);
                  if ( !(unsigned int)CActivationContextGenerationContextContributor::Fire_ParseEnding(
                                        (CActivationContextGenerationContextContributor *)(*(_QWORD *)a2 + 48 * i),
                                        a2,
                                        (const struct _ACTCTXCTB_ASSEMBLY_CONTEXT *)&v42) )
                  {
                    v12 = off_1800771A0;
                    *v41 = 0;
                    goto LABEL_39;
                  }
                }
                *a4 = (struct CPolicyStatement *)*((_QWORD *)v18 + 157);
                *((_QWORD *)v18 + 157) = 0;
                v34 = 1;
              }
              goto LABEL_40;
            }
            FusionpTraceCOMFailureOrigination(v20, byte_18008517D);
            v16 = v21;
            goto LABEL_16;
          }
          v12 = off_1800771C0;
          *v41 = 0;
        }
        else
        {
          v12 = off_1800771E0;
          *v41 = 0;
        }
      }
      else
      {
        v12 = off_180077200;
        *v41 = 0;
      }
    }
    else
    {
      v12 = off_18006DE88;
      *v41 = 0;
    }
LABEL_39:
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v12);
    goto LABEL_40;
  }
  FusionpTraceCOMFailureOrigination(v14, byte_18008517D);
  v16 = v15;
LABEL_16:
  CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&v36, v16);
LABEL_40:
  v8 = (const struct _ACTCTXCTB_ASSEMBLY_CONTEXT *)&v42;
LABEL_41:
  v25 = 0;
  for ( j = GetLastError(); (unsigned int)v25 < *((_DWORD *)a2 + 2); v25 = (unsigned int)(v25 + 1) )
    CActivationContextGenerationContextContributor::Fire_ParseEnded(
      (CActivationContextGenerationContextContributor *)(*(_QWORD *)a2 + 48 * v25),
      a2,
      v8);
  if ( v9 )
    _ASSEMBLY::Release(v9);
  SetLastError(j);
  v27 = v34;
  _ACTCTXCTB_ASSEMBLY_CONTEXT::~_ACTCTXCTB_ASSEMBLY_CONTEXT((_ACTCTXCTB_ASSEMBLY_CONTEXT *)&v42);
  CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>::~CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>(&v30);
  CSmartRef<CAssemblyName>::~CSmartRef<CAssemblyName>(&v35);
  CSmartPtr<CNodeFactory,CSmartPtrBaseTypeHelper<CNodeFactory>>::~CSmartPtr<CNodeFactory,CSmartPtrBaseTypeHelper<CNodeFactory>>(&v32);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v36);
  return v27;
}

```

## disassembly

```asm
0x18002af5c  mov     [rsp-8+arg_0], rbx
0x18002af61  push    rbp
0x18002af62  push    rsi
0x18002af63  push    rdi
0x18002af64  push    r12
0x18002af66  push    r13
0x18002af68  push    r14
0x18002af6a  push    r15
0x18002af6c  lea     rbp, [rsp-90h]
0x18002af74  sub     rsp, 190h
0x18002af7b  mov     rax, cs:__security_cookie
0x18002af82  xor     rax, rsp
0x18002af85  mov     [rbp+0C0h+var_40], rax
0x18002af8c  mov     r12, [rbp+0C0h+arg_20]
0x18002af93  lea     rax, qword_18006DF08
0x18002af9a  xor     ebx, ebx
0x18002af9c  mov     [rsp+1C0h+var_148], rax
0x18002afa1  lea     rax, [rsp+1C0h+var_168]
0x18002afa6  mov     [rsp+1C0h+var_168], ebx
0x18002afaa  lea     rcx, [rsp+1C0h+var_158]; this
0x18002afaf  mov     [rbp+0C0h+var_130], rax
0x18002afb3  mov     r13, r9
0x18002afb6  mov     [rsp+1C0h+var_158], 1
0x18002afbe  mov     r14, r8
0x18002afc1  mov     [rsp+1C0h+var_150], rbx
0x18002afc6  mov     r15, rdx
0x18002afc9  mov     [rbp+0C0h+var_140], 20737853h
0x18002afd1  mov     esi, ebx
0x18002afd3  mov     [rbp+0C0h+var_138], 2Ah ; '*'
0x18002afda  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002afdf  xorps   xmm0, xmm0
0x18002afe2  mov     [rsp+1C0h+var_178], rbx
0x18002afe7  xorps   xmm1, xmm1
0x18002afea  movdqa  [rbp+0C0h+var_E0], xmm0
0x18002afef  xor     edx, edx; Val
0x18002aff1  movdqa  [rbp+0C0h+var_D0], xmm1
0x18002aff6  lea     r8d, [rbx+50h]; Size
0x18002affa  movdqa  [rbp+0C0h+var_C0], xmm0
0x18002afff  lea     rcx, [rbp+0C0h+var_90]; void *
0x18002b003  mov     [rsp+1C0h+var_170], bl
0x18002b007  mov     [rsp+1C0h+var_160], rbx
0x18002b00c  mov     edi, ebx
0x18002b00e  mov     [rsp+1C0h+var_188], rbx
0x18002b013  mov     [rsp+1C0h+var_180], bl
0x18002b017  mov     [rbp+0C0h+var_120], rbx
0x18002b01b  mov     [rbp+0C0h+var_118], ebx
0x18002b01e  mov     [rbp+0C0h+var_110], rbx
0x18002b022  mov     [rbp+0C0h+var_108], rbx
0x18002b026  mov     [rbp+0C0h+var_100], ebx
0x18002b029  mov     [rbp+0C0h+var_F8], rbx
0x18002b02d  mov     [rbp+0C0h+var_F0], rbx
0x18002b031  mov     [rbp+0C0h+var_E8], rbx
0x18002b035  mov     [rbp+0C0h+var_B0], rbx
0x18002b039  mov     [rbp+0C0h+var_A8], rbx
0x18002b03d  mov     [rbp+0C0h+var_A0], rbx
0x18002b041  call    memset_0
0x18002b046  mov     [r13+0], rbx
0x18002b04a  test    r15, r15
0x18002b04d  jnz     short loc_18002B077
0x18002b04f  mov     [rbp+0C0h+var_138], 36h ; '6'
0x18002b056  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18002b05b  mov     ecx, 57h ; 'W'; dwErrCode
0x18002b060  call    cs:__imp_SetLastError
0x18002b067  nop     dword ptr [rax+rax+00h]
0x18002b06c  mov     rax, [rbp+0C0h+var_130]
0x18002b070  mov     [rax], ebx
0x18002b072  jmp     loc_18002B407
0x18002b077  test    r12, r12
0x18002b07a  jnz     short loc_18002B085
0x18002b07c  mov     [rbp+0C0h+var_138], 37h ; '7'
0x18002b083  jmp     short loc_18002B056
0x18002b085  xor     ecx, ecx; dwErrCode
0x18002b087  call    cs:__imp_SetLastError
0x18002b08e  nop     dword ptr [rax+rax+00h]
0x18002b093  mov     rcx, cs:g_hHeap; hHeap
0x18002b09a  xor     edx, edx; dwFlags
0x18002b09c  mov     r8d, 370h; dwBytes
0x18002b0a2  call    cs:__imp_HeapAlloc
0x18002b0a9  nop     dword ptr [rax+rax+00h]
0x18002b0ae  test    rax, rax
0x18002b0b1  jz      loc_18002B3F1
0x18002b0b7  mov     rcx, rax; this
0x18002b0ba  call    ??0_ASSEMBLY@@QEAA@XZ; _ASSEMBLY::_ASSEMBLY(void)
0x18002b0bf  mov     rdi, rax
0x18002b0c2  test    rax, rax
0x18002b0c5  jz      loc_18002B3F1
0x18002b0cb  xor     ecx, ecx; dwErrCode
0x18002b0cd  call    cs:__imp_SetLastError
0x18002b0d4  nop     dword ptr [rax+rax+00h]
0x18002b0d9  lea     rcx, [rdi+20h]; this
0x18002b0dd  mov     rdx, r14; struct CProbedAssemblyInformation *
0x18002b0e0  call    ?Initialize@CProbedAssemblyInformation@@QEAAHAEBV1@@Z; CProbedAssemblyInformation::Initialize(CProbedAssemblyInformation const &)
0x18002b0e5  test    eax, eax
0x18002b0e7  jnz     short loc_18002B0F5
0x18002b0e9  lea     rcx, off_180077260; "clientcore\\base\\win32\\fusion\\sxs\\p"...
0x18002b0f0  jmp     loc_18002B3F8
0x18002b0f5  xor     ecx, ecx; dwErrCode
0x18002b0f7  call    cs:__imp_SetLastError
0x18002b0fe  nop     dword ptr [rax+rax+00h]
0x18002b103  mov     rdx, [r14]
0x18002b106  lea     r8, [rsp+1C0h+var_188]
0x18002b10b  xor     ecx, ecx
0x18002b10d  mov     [rsp+1C0h+var_180], 1
0x18002b112  call    SxsDuplicateAssemblyIdentity
0x18002b117  test    eax, eax
0x18002b119  jnz     short loc_18002B127
0x18002b11b  lea     rcx, off_180077240; "clientcore\\base\\win32\\fusion\\sxs\\p"...
0x18002b122  jmp     loc_18002B3F8
0x18002b127  mov     rax, [rsp+1C0h+var_188]
0x18002b12c  xor     ecx, ecx; dwErrCode
0x18002b12e  mov     [rbp+0C0h+var_E8], rax
0x18002b132  mov     [rsp+1C0h+var_180], bl
0x18002b136  call    cs:__imp_SetLastError
0x18002b13d  nop     dword ptr [rax+rax+00h]
0x18002b142  lea     r8, [rbp+0C0h+var_108]; unsigned __int64 *
0x18002b146  mov     rcx, r14; this
0x18002b149  lea     rdx, [rbp+0C0h+var_110]; unsigned __int16 **
0x18002b14d  call    ?GetManifestPath@CProbedAssemblyInformation@@QEBAHPEAPEBGPEA_K@Z; CProbedAssemblyInformation::GetManifestPath(ushort const * *,unsigned __int64 *)
0x18002b152  test    eax, eax
0x18002b154  jnz     short loc_18002B162
0x18002b156  lea     rcx, off_180077220; "clientcore\\base\\win32\\fusion\\sxs\\p"...
0x18002b15d  jmp     loc_18002B3F8
0x18002b162  xor     ecx, ecx; dwErrCode
0x18002b164  call    cs:__imp_SetLastError
0x18002b16b  nop     dword ptr [rax+rax+00h]
0x18002b170  mov     rax, [r12]
0x18002b174  lea     rdx, [rbp+0C0h+var_90]
0x18002b178  mov     r8d, 1
0x18002b17e  mov     rcx, r12
0x18002b181  mov     rax, [rax+60h]
0x18002b185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b18a  mov     ebx, eax
0x18002b18c  test    eax, eax
0x18002b18e  jns     short loc_18002B1AF
0x18002b190  lea     rdx, byte_18008517D; char *
0x18002b197  mov     ecx, eax; int
0x18002b199  call    ?FusionpTraceCOMFailureOrigination@@YAXJPEBDZZ; FusionpTraceCOMFailureOrigination(long,char const *,...)
0x18002b19e  mov     edx, ebx; int
0x18002b1a0  lea     rcx, [rsp+1C0h+var_158]; this
0x18002b1a5  call    ?MarkCOMFailure@CFnTracerWin32@@QEAAXJ@Z; CFnTracerWin32::MarkCOMFailure(long)
0x18002b1aa  jmp     loc_18002B403
0x18002b1af  xor     ecx, ecx; dwErrCode
0x18002b1b1  call    cs:__imp_SetLastError
0x18002b1b8  nop     dword ptr [rax+rax+00h]
0x18002b1bd  mov     rcx, cs:g_hHeap; hHeap
0x18002b1c4  xor     edx, edx; dwFlags
0x18002b1c6  mov     r8d, 738h; dwBytes
0x18002b1cc  call    cs:__imp_HeapAlloc
0x18002b1d3  nop     dword ptr [rax+rax+00h]
0x18002b1d8  test    rax, rax
0x18002b1db  jz      loc_18002B3E2
0x18002b1e1  mov     rcx, rax; this
0x18002b1e4  call    ??0CNodeFactory@@QEAA@XZ; CNodeFactory::CNodeFactory(void)
0x18002b1e9  mov     [rsp+1C0h+var_178], rax
0x18002b1ee  mov     rbx, rax
0x18002b1f1  test    rax, rax
0x18002b1f4  jz      loc_18002B3E2
0x18002b1fa  mov     [rsp+1C0h+var_170], 1
0x18002b1ff  xor     ecx, ecx; dwErrCode
0x18002b201  call    cs:__imp_SetLastError
0x18002b208  nop     dword ptr [rax+rax+00h]
0x18002b20d  lea     r9, [rbp+0C0h+var_120]; struct _ACTCTXCTB_ASSEMBLY_CONTEXT *
0x18002b211  mov     r8, rdi; struct _ASSEMBLY *
0x18002b214  mov     rdx, r15; struct _ACTCTXGENCTX *
0x18002b217  mov     rcx, rbx; this
0x18002b21a  call    ?Initialize@CNodeFactory@@QEAAHPEAU_ACTCTXGENCTX@@PEAU_ASSEMBLY@@PEAU_ACTCTXCTB_ASSEMBLY_CONTEXT@@@Z; CNodeFactory::Initialize(_ACTCTXGENCTX *,_ASSEMBLY *,_ACTCTXCTB_ASSEMBLY_CONTEXT *)
0x18002b21f  test    eax, eax
0x18002b221  jnz     short loc_18002B235
0x18002b223  mov     rax, [rbp+0C0h+var_130]
0x18002b227  lea     rcx, off_180077200; "clientcore\\base\\win32\\fusion\\sxs\\p"...
0x18002b22e  mov     [rax], esi
0x18002b230  jmp     loc_18002B3FE
0x18002b235  xor     ecx, ecx; dwErrCode
0x18002b237  call    cs:__imp_SetLastError
0x18002b23e  nop     dword ptr [rax+rax+00h]
0x18002b243  mov     r8d, [r14+8]
0x18002b247  lea     rax, [rbp+0C0h+var_78]
0x18002b24b  lea     r9, [r14+10h]
0x18002b24f  mov     [rsp+1C0h+var_1A0], rax
0x18002b254  mov     edx, 2
0x18002b259  mov     rcx, rbx
0x18002b25c  call    ?SetParseType@CNodeFactory@@QEAAHKKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@AEBU_FILETIME@@@Z; CNodeFactory::SetParseType(ulong,ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,_FILETIME const &)
0x18002b261  test    eax, eax
0x18002b263  jnz     short loc_18002B277
0x18002b265  mov     rax, [rbp+0C0h+var_130]
0x18002b269  lea     rcx, off_1800771E0; "clientcore\\base\\win32\\fusion\\sxs\\p"...
0x18002b270  mov     [rax], esi
0x18002b272  jmp     loc_18002B3FE
0x18002b277  xor     ecx, ecx; dwErrCode
0x18002b279  call    cs:__imp_SetLastError
0x18002b280  nop     dword ptr [rax+rax+00h]
0x18002b285  lea     rdx, [rsp+1C0h+var_160]; void **
0x18002b28a  call    ?SxspGetXMLParser@@YAHAEBU_GUID@@PEAPEAX@Z; SxspGetXMLParser(_GUID const &,void * *)
0x18002b28f  test    eax, eax
0x18002b291  jnz     short loc_18002B2A5
0x18002b293  mov     rax, [rbp+0C0h+var_130]
0x18002b297  lea     rcx, off_1800771C0; "clientcore\\base\\win32\\fusion\\sxs\\p"...
0x18002b29e  mov     [rax], esi
0x18002b2a0  jmp     loc_18002B3FE
0x18002b2a5  xor     ecx, ecx; dwErrCode
0x18002b2a7  call    cs:__imp_SetLastError
0x18002b2ae  nop     dword ptr [rax+rax+00h]
0x18002b2b3  mov     rcx, [rsp+1C0h+var_160]
0x18002b2b8  mov     rdx, rbx
0x18002b2bb  mov     rax, [rcx]
0x18002b2be  mov     rax, [rax+18h]
0x18002b2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2c7  mov     esi, eax
0x18002b2c9  test    eax, eax
0x18002b2cb  jns     short loc_18002B2E2
0x18002b2cd  lea     rdx, byte_18008517D; char *
0x18002b2d4  mov     ecx, eax; int
0x18002b2d6  call    ?FusionpTraceCOMFailureOrigination@@YAXJPEBDZZ; FusionpTraceCOMFailureOrigination(long,char const *,...)
0x18002b2db  mov     edx, esi
0x18002b2dd  jmp     loc_18002B1A0
0x18002b2e2  xor     ecx, ecx; dwErrCode
0x18002b2e4  call    cs:__imp_SetLastError
0x18002b2eb  nop     dword ptr [rax+rax+00h]
0x18002b2f0  mov     rcx, [rsp+1C0h+var_160]
0x18002b2f5  mov     rdx, r12
0x18002b2f8  mov     rax, [rcx]
0x18002b2fb  mov     rax, [rax+80h]
0x18002b302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b307  mov     esi, eax
0x18002b309  test    eax, eax
0x18002b30b  jns     short loc_18002B34F
0x18002b30d  lea     rdx, byte_18008517D; char *
0x18002b314  mov     ecx, esi; int
0x18002b316  call    ?FusionpTraceCOMFailureOrigination@@YAXJPEBDZZ; FusionpTraceCOMFailureOrigination(long,char const *,...)
0x18002b31b  lea     rcx, [rsp+1C0h+var_190]; int *
0x18002b320  mov     [rsp+1C0h+var_190], esi
0x18002b324  call    ?FusionpConvertCOMFailure@@YAXAEAJ@Z; FusionpConvertCOMFailure(long &)
0x18002b329  mov     ecx, [rsp+1C0h+var_190]; int
0x18002b32d  call    ?FusionpHRESULTToWin32@@YAKJ@Z; FusionpHRESULTToWin32(long)
0x18002b332  mov     ecx, eax; dwErrCode
0x18002b334  call    cs:__imp_SetLastError
0x18002b33b  nop     dword ptr [rax+rax+00h]
0x18002b340  mov     rax, [rbp+0C0h+var_130]
0x18002b344  mov     dword ptr [rax], 0
0x18002b34a  jmp     loc_18002B403
0x18002b34f  xor     ecx, ecx; dwErrCode
0x18002b351  call    cs:__imp_SetLastError
0x18002b358  nop     dword ptr [rax+rax+00h]
0x18002b35d  mov     rcx, [rsp+1C0h+var_160]
0x18002b362  or      edx, 0FFFFFFFFh
0x18002b365  mov     rax, [rcx]
0x18002b368  mov     rax, [rax+0C0h]
0x18002b36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b374  mov     esi, eax
0x18002b376  test    eax, eax
0x18002b378  js      short loc_18002B30D
0x18002b37a  xor     esi, esi
0x18002b37c  cmp     esi, [r15+8]
0x18002b380  jnb     short loc_18002B3C2
0x18002b382  xor     ecx, ecx; dwErrCode
0x18002b384  call    cs:__imp_SetLastError
0x18002b38b  nop     dword ptr [rax+rax+00h]
0x18002b390  lea     rcx, [rsi+rsi*2]
0x18002b394  mov     rdx, r15; struct _ACTCTXGENCTX *
0x18002b397  shl     rcx, 4
0x18002b39b  lea     r8, [rbp+0C0h+var_120]; struct _ACTCTXCTB_ASSEMBLY_CONTEXT *
0x18002b39f  add     rcx, [r15]; this
0x18002b3a2  call    ?Fire_ParseEnding@CActivationContextGenerationContextContributor@@QEAAHPEAU_ACTCTXGENCTX@@PEBU_ACTCTXCTB_ASSEMBLY_CONTEXT@@@Z; CActivationContextGenerationContextContributor::Fire_ParseEnding(_ACTCTXGENCTX *,_ACTCTXCTB_ASSEMBLY_CONTEXT const *)
0x18002b3a7  test    eax, eax
0x18002b3a9  jz      short loc_18002B3AF
0x18002b3ab  inc     esi
0x18002b3ad  jmp     short loc_18002B37C
0x18002b3af  mov     rax, [rbp+0C0h+var_130]
0x18002b3b3  lea     rcx, off_1800771A0; "clientcore\\base\\win32\\fusion\\sxs\\p"...
0x18002b3ba  mov     dword ptr [rax], 0
0x18002b3c0  jmp     short loc_18002B3FE
0x18002b3c2  mov     rax, [rbx+4E8h]
0x18002b3c9  mov     [r13+0], rax
0x18002b3cd  mov     qword ptr [rbx+4E8h], 0
0x18002b3d8  mov     [rsp+1C0h+var_168], 1
0x18002b3e0  jmp     short loc_18002B403
0x18002b3e2  mov     rax, [rbp+0C0h+var_130]
0x18002b3e6  lea     rcx, off_18006DE88; "clientcore\\base\\win32\\fusion\\sxs\\p"...
0x18002b3ed  mov     [rax], esi
0x18002b3ef  jmp     short loc_18002B3FE
0x18002b3f1  lea     rcx, off_18006FD10; struct _CALL_SITE_INFO *
0x18002b3f8  mov     rax, [rbp+0C0h+var_130]
0x18002b3fc  mov     [rax], ebx
0x18002b3fe  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002b403  lea     rsi, [rbp+0C0h+var_120]
0x18002b407  call    cs:__imp_GetLastError
0x18002b40e  nop     dword ptr [rax+rax+00h]
0x18002b413  xor     r14d, r14d
0x18002b416  mov     ebx, eax
0x18002b418  cmp     [r15+8], r14d
0x18002b41c  jbe     short loc_18002B43D
0x18002b41e  lea     rcx, [r14+r14*2]
0x18002b422  mov     r8, rsi; struct _ACTCTXCTB_ASSEMBLY_CONTEXT *
0x18002b425  shl     rcx, 4
0x18002b429  mov     rdx, r15; struct _ACTCTXGENCTX *
0x18002b42c  add     rcx, [r15]; this
0x18002b42f  call    ?Fire_ParseEnded@CActivationContextGenerationContextContributor@@QEAAXPEAU_ACTCTXGENCTX@@PEBU_ACTCTXCTB_ASSEMBLY_CONTEXT@@@Z; CActivationContextGenerationContextContributor::Fire_ParseEnded(_ACTCTXGENCTX *,_ACTCTXCTB_ASSEMBLY_CONTEXT const *)
0x18002b434  inc     r14d
0x18002b437  cmp     r14d, [r15+8]
0x18002b43b  jb      short loc_18002B41E
  ... truncated ...
```
