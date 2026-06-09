# SxspCreateAssemblyIdentityFromTextualString

- ea: `0x18002cc78`
- end: `0x18002d241`
- name: `SxspCreateAssemblyIdentityFromTextualString`
- size: `1481`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18002b7e0`
- `0x18002bdb4`
- `0x180058284`
- `0x180060390`
- `0x180061f6c`

## callees

- `0x1800075a0`
- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x180013af0`
- `0x180017bc0`
- `0x18001c270`
- `0x180020820`
- `0x18002b580`
- `0x18002cc78`
- `0x180042868`
- `0x18005a4c8`
- `0x18005d2b0`
- `0x18005d38c`
- `0x18006a110`

## import_xrefs

- `ntdll!wcschr` at `0x18002ce09`
- `ntdll!wcschr` at `0x18002cebf`
- `ntdll!wcschr` at `0x18002cef7`
- `ntdll!wcschr` at `0x18002cf72`
- `ntdll!wcschr` at `0x18002ce09`
- `ntdll!wcschr` at `0x18002cebf`
- `ntdll!wcschr` at `0x18002cef7`
- `ntdll!wcschr` at `0x18002cf72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cd35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cd6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cda8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ce25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ce52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cfa5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cfd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cff7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d051`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d11c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d14c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cd35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cd6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cda8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ce25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ce52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cfa5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cfd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cff7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d051`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d11c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d14c`

## pseudocode

```c
__int64 __fastcall SxspCreateAssemblyIdentityFromTextualString(_WORD *a1, struct _ASSEMBLY_IDENTITY **a2)
{
  const char *v4; // rcx
  __int64 v5; // rcx
  char **v6; // rcx
  __int64 v7; // r8
  unsigned __int16 *v8; // rdi
  unsigned __int16 *v9; // rbx
  unsigned __int16 *v10; // rsi
  unsigned __int16 *v11; // r14
  wchar_t v12; // dx
  unsigned __int64 v13; // rbx
  struct _ASSEMBLY_IDENTITY *v14; // r14
  wchar_t *v15; // rbx
  wchar_t *v16; // rdi
  wchar_t *v17; // r14
  wchar_t v18; // dx
  __int64 v19; // rdi
  wchar_t *v20; // r15
  wchar_t *v21; // r14
  wchar_t *v22; // r12
  unsigned __int64 v23; // rdi
  wchar_t *v24; // rdx
  unsigned __int16 *v25; // r12
  unsigned __int16 *v26; // rax
  unsigned __int16 *v27; // r15
  wchar_t *v28; // r14
  wchar_t *v29; // rbx
  wchar_t v30; // dx
  unsigned __int64 v31; // r14
  unsigned __int16 *v32; // rbx
  unsigned int v33; // ebx
  struct _ASSEMBLY_IDENTITY *v35; // [rsp+30h] [rbp-D0h] BYREF
  char v36; // [rsp+38h] [rbp-C8h]
  wchar_t *v37; // [rsp+40h] [rbp-C0h]
  const char *v38; // [rsp+48h] [rbp-B8h]
  struct _ASSEMBLY_IDENTITY *v39; // [rsp+50h] [rbp-B0h]
  char *v40; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A0h]
  wchar_t *v42; // [rsp+68h] [rbp-98h]
  const char *v43; // [rsp+70h] [rbp-90h]
  int v44; // [rsp+78h] [rbp-88h] BYREF
  __int64 v45; // [rsp+80h] [rbp-80h]
  __int64 *v46; // [rsp+88h] [rbp-78h]
  __int64 v47; // [rsp+90h] [rbp-70h]
  int v48; // [rsp+98h] [rbp-68h]
  unsigned int *v49; // [rsp+A0h] [rbp-60h]
  int v50; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v51[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v52; // [rsp+C0h] [rbp-40h]
  __int64 v53; // [rsp+C8h] [rbp-38h]
  char *v54; // [rsp+D0h] [rbp-30h]
  char v55; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v56[2]; // [rsp+160h] [rbp+60h] BYREF
  char *v57; // [rsp+170h] [rbp+70h]
  __int64 v58; // [rsp+178h] [rbp+78h]
  __int64 v59; // [rsp+180h] [rbp+80h]
  char v60; // [rsp+188h] [rbp+88h] BYREF
  _QWORD v61[2]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 *v62; // [rsp+220h] [rbp+120h]
  __int64 v63; // [rsp+228h] [rbp+128h]
  __int64 v64; // [rsp+230h] [rbp+130h]
  char v65; // [rsp+238h] [rbp+138h] BYREF

  v47 = 544438355;
  v50 = 0;
  v46 = &qword_18006FD50;
  v45 = 0;
  v48 = 3658;
  v44 = 1;
  v49 = (unsigned int *)&v50;
  CFrame::BaseEnter((CFrame *)&v44);
  v35 = 0;
  v36 = 0;
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v51);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v61);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v56);
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    v48 = 3670;
    goto LABEL_5;
  }
  if ( !*a1 )
  {
    v48 = 3671;
    goto LABEL_5;
  }
  if ( !a2 )
  {
    v48 = 3672;
LABEL_5:
    FusionpTraceParameterCheck(v4);
    SetLastError(0x57u);
LABEL_6:
    *v49 = 0;
    goto LABEL_64;
  }
  SetLastError(0);
  v36 = 1;
  if ( !(unsigned int)SxsCreateAssemblyIdentity(v5, 1, &v35) )
  {
    v6 = off_180075250;
LABEL_13:
    *v49 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v6);
    goto LABEL_64;
  }
  SetLastError(0);
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(v61, a1, v7) )
  {
    v6 = off_18006FFB0;
    goto LABEL_13;
  }
  v8 = v62;
  v9 = v62;
  v10 = &v62[v64];
  do
  {
    v11 = v9;
    if ( v9 == v10 )
      break;
    v12 = *v9++;
  }
  while ( !wcschr(L",", v12) );
  v13 = (int)(v11 - v8);
  SetLastError(0);
  if ( !(unsigned int)SxspDequoteString(v8, v13) )
  {
    v6 = off_180075230;
    goto LABEL_13;
  }
  SetLastError(0);
  v14 = v35;
  v39 = v35;
  if ( !(unsigned int)SxspSetAssemblyIdentityAttributeValue(
                        0,
                        v35,
                        (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_name,
                        v52,
                        v54) )
  {
    v6 = off_180075210;
    goto LABEL_13;
  }
  v15 = &v8[v13 + 1];
  while ( v15 < v10 )
  {
    v16 = v15;
    do
    {
      v17 = v16;
      if ( v16 == v10 )
        break;
      v18 = *v16++;
    }
    while ( !wcschr(L"=", v18) );
    v19 = (int)(v17 - v15);
    v20 = &v15[v19];
    v21 = v20;
    do
    {
      v22 = v21;
      if ( v21 == v15 )
        break;
      --v21;
    }
    while ( !wcschr(L":", *v21) );
    v4 = (const char *)(int)(v20 - v22);
    v23 = v19 - (_QWORD)v4;
    v38 = v4;
    v24 = &v15[v23];
    v25 = (unsigned __int16 *)((unsigned __int64)v15 & -(__int64)(v23 != 0));
    v37 = v24;
    if ( v23 )
      --v23;
    v26 = &v24[(_QWORD)(v4 + 1)];
    if ( v26 >= v10 || *v26 != 34 )
    {
      v48 = 3719;
      goto LABEL_5;
    }
    v27 = v26 + 1;
    v28 = v26 + 1;
    do
    {
      v29 = v28;
      if ( v28 == v10 )
        break;
      v30 = *v28++;
    }
    while ( !wcschr(L"\"", v30) );
    v31 = (int)(v29 - v27);
    v32 = &v27[v31];
    if ( v32 >= v10 || *v32 != 34 )
    {
      v48 = 3725;
      FusionpTraceParameterCheck(v4);
      SetLastError(0x57u);
      goto LABEL_6;
    }
    SetLastError(0);
    if ( !(unsigned int)SxspDequoteString(v27, v31) )
    {
      v6 = off_1800751F0;
      goto LABEL_13;
    }
    if ( v23 )
    {
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(v56, v25, v23) )
      {
        v6 = off_1800751D0;
        goto LABEL_13;
      }
      SetLastError(0);
      if ( !(unsigned int)SxspDequoteString(v25, v23) )
      {
        v6 = off_1800751B0;
        goto LABEL_13;
      }
      v40 = v57;
      v41 = v59;
    }
    else
    {
      v40 = 0;
      v41 = 0;
    }
    v42 = v37;
    v43 = v38;
    SetLastError(0);
    v14 = v39;
    if ( !(unsigned int)SxspSetAssemblyIdentityAttributeValue(
                          0,
                          v39,
                          (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)&v40,
                          v52,
                          v54) )
    {
      v6 = off_180075190;
      goto LABEL_13;
    }
    v15 = v32 + 1;
    if ( v15 == v10 )
    {
      if ( *v15 )
      {
        v48 = 3768;
        goto LABEL_5;
      }
    }
    else
    {
      if ( v15 >= v10 )
      {
        CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v44, 0x57u);
        FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180075170);
        goto LABEL_64;
      }
      if ( *v15 != 44 )
      {
        v48 = 3772;
        goto LABEL_5;
      }
      ++v15;
    }
  }
  v35 = 0;
  v36 = 0;
  *a2 = v14;
  SetLastError(0);
  *v49 = 1;
LABEL_64:
  v33 = *v49;
  v56[0] = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( v57 != &v60 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(v56);
  v57 = 0;
  v58 = 0;
  v56[0] = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  v61[0] = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( v62 != (unsigned __int16 *)&v65 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(v61);
  v62 = 0;
  v63 = 0;
  v61[0] = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  v51[0] = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( v52 != (unsigned __int16 *)&v55 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(v51);
  v52 = 0;
  v53 = 0;
  v51[0] = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>::~CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>(&v35);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v44);
  return v33;
}

```

## disassembly

```asm
0x18002cc78  mov     [rsp-8+arg_10], rbx
0x18002cc7d  push    rbp
0x18002cc7e  push    rsi
0x18002cc7f  push    rdi
0x18002cc80  push    r12
0x18002cc82  push    r13
0x18002cc84  push    r14
0x18002cc86  push    r15
0x18002cc88  lea     rbp, [rsp-1D0h]
0x18002cc90  sub     rsp, 2D0h
0x18002cc97  mov     rax, cs:__security_cookie
0x18002cc9e  xor     rax, rsp
0x18002cca1  mov     [rbp+200h+var_40], rax
0x18002cca8  xor     r15d, r15d
0x18002ccab  mov     [rbp+200h+var_270], 20737853h
0x18002ccb3  lea     rax, qword_18006FD50
0x18002ccba  mov     [rbp+200h+var_258], r15d
0x18002ccbe  mov     [rbp+200h+var_278], rax
0x18002ccc2  mov     rbx, rcx
0x18002ccc5  lea     rax, [rbp+200h+var_258]
0x18002ccc9  mov     [rbp+200h+var_280], r15
0x18002cccd  lea     r12d, [r15+1]
0x18002ccd1  mov     [rbp+200h+var_268], 0E4Ah
0x18002ccd8  lea     rcx, [rsp+300h+var_288]; this
0x18002ccdd  mov     [rsp+300h+var_288], r12d
0x18002cce2  mov     r13, rdx
0x18002cce5  mov     [rbp+200h+var_260], rax
0x18002cce9  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002ccee  lea     rcx, [rbp+200h+var_250]
0x18002ccf2  mov     [rsp+300h+var_2D0], r15
0x18002ccf7  mov     [rsp+300h+var_2C8], r15b
0x18002ccfc  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18002cd01  lea     rcx, [rbp+200h+var_F0]
0x18002cd08  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18002cd0d  lea     rcx, [rbp+200h+var_1A0]
0x18002cd11  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18002cd16  test    r13, r13
0x18002cd19  jz      short loc_18002CD1F
0x18002cd1b  mov     [r13+0], r15
0x18002cd1f  test    rbx, rbx
0x18002cd22  jnz     short loc_18002CD4D
0x18002cd24  mov     [rbp+200h+var_268], 0E56h
0x18002cd2b  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18002cd30  mov     ecx, 57h ; 'W'; dwErrCode
0x18002cd35  call    cs:__imp_SetLastError
0x18002cd3c  nop     dword ptr [rax+rax+00h]
0x18002cd41  mov     rax, [rbp+200h+var_260]
0x18002cd45  mov     [rax], r15d
0x18002cd48  jmp     loc_18002D162
0x18002cd4d  cmp     [rbx], r15w
0x18002cd51  jnz     short loc_18002CD5C
0x18002cd53  mov     [rbp+200h+var_268], 0E57h
0x18002cd5a  jmp     short loc_18002CD2B
0x18002cd5c  test    r13, r13
0x18002cd5f  jnz     short loc_18002CD6A
0x18002cd61  mov     [rbp+200h+var_268], 0E58h
0x18002cd68  jmp     short loc_18002CD2B
0x18002cd6a  xor     ecx, ecx; dwErrCode
0x18002cd6c  call    cs:__imp_SetLastError
0x18002cd73  nop     dword ptr [rax+rax+00h]
0x18002cd78  lea     r8, [rsp+300h+var_2D0]
0x18002cd7d  mov     [rsp+300h+var_2C8], r12b
0x18002cd82  mov     edx, r12d
0x18002cd85  call    SxsCreateAssemblyIdentity
0x18002cd8a  test    eax, eax
0x18002cd8c  jnz     short loc_18002CDA6
0x18002cd8e  lea     rcx, off_180075250; struct _CALL_SITE_INFO *
0x18002cd95  mov     rax, [rbp+200h+var_260]
0x18002cd99  mov     [rax], r15d
0x18002cd9c  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002cda1  jmp     loc_18002D162
0x18002cda6  xor     ecx, ecx; dwErrCode
0x18002cda8  call    cs:__imp_SetLastError
0x18002cdaf  nop     dword ptr [rax+rax+00h]
0x18002cdb4  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002cdb8  inc     r8
0x18002cdbb  cmp     [rbx+r8*2], r15w
0x18002cdc0  jnz     short loc_18002CDB8
0x18002cdc2  mov     rdx, rbx
0x18002cdc5  lea     rcx, [rbp+200h+var_F0]
0x18002cdcc  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)
0x18002cdd1  test    eax, eax
0x18002cdd3  jnz     short loc_18002CDDE
0x18002cdd5  lea     rcx, off_18006FFB0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18002cddc  jmp     short loc_18002CD95
0x18002cdde  mov     rdi, [rbp+200h+var_E0]
0x18002cde5  mov     rax, [rbp+200h+var_D0]
0x18002cdec  mov     rbx, rdi
0x18002cdef  lea     rsi, [rdi+rax*2]
0x18002cdf3  mov     r14, rbx
0x18002cdf6  cmp     rbx, rsi
0x18002cdf9  jz      short loc_18002CE1A
0x18002cdfb  movzx   edx, word ptr [rbx]; Ch
0x18002cdfe  lea     rcx, asc_18007F060; ","
0x18002ce05  add     rbx, 2
0x18002ce09  call    cs:__imp_wcschr
0x18002ce10  nop     dword ptr [rax+rax+00h]
0x18002ce15  test    rax, rax
0x18002ce18  jz      short loc_18002CDF3
0x18002ce1a  sub     r14, rdi
0x18002ce1d  xor     ecx, ecx; dwErrCode
0x18002ce1f  sar     r14, 1
0x18002ce22  movsxd  rbx, r14d
0x18002ce25  call    cs:__imp_SetLastError
0x18002ce2c  nop     dword ptr [rax+rax+00h]
0x18002ce31  lea     r8, [rbp+200h+var_250]
0x18002ce35  mov     rdx, rbx; unsigned __int64
0x18002ce38  mov     rcx, rdi; unsigned __int16 *
0x18002ce3b  call    ?SxspDequoteString@@YAHPEBG_KAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspDequoteString(ushort const *,unsigned __int64,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18002ce40  test    eax, eax
0x18002ce42  jnz     short loc_18002CE50
0x18002ce44  lea     rcx, off_180075230; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18002ce4b  jmp     loc_18002CD95
0x18002ce50  xor     ecx, ecx; dwErrCode
0x18002ce52  call    cs:__imp_SetLastError
0x18002ce59  nop     dword ptr [rax+rax+00h]
0x18002ce5e  mov     r14, [rsp+300h+var_2D0]
0x18002ce63  lea     r8, s_IdentityAttribute_name; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x18002ce6a  mov     rax, [rbp+200h+var_230]
0x18002ce6e  mov     rdx, r14; struct _ASSEMBLY_IDENTITY *
0x18002ce71  mov     r9, [rbp+200h+var_240]; unsigned __int16 *
0x18002ce75  xor     ecx, ecx; unsigned int
0x18002ce77  mov     [rsp+300h+var_2E0], rax; char *
0x18002ce7c  mov     [rsp+300h+var_2B0], r14
0x18002ce81  call    ?SxspSetAssemblyIdentityAttributeValue@@YAHKPEAU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEBG_K@Z; SxspSetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const *,unsigned __int64)
0x18002ce86  test    eax, eax
0x18002ce88  jnz     short loc_18002CE96
0x18002ce8a  lea     rcx, off_180075210; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18002ce91  jmp     loc_18002CD95
0x18002ce96  inc     rbx
0x18002ce99  lea     rbx, [rdi+rbx*2]
0x18002ce9d  cmp     rbx, rsi
0x18002cea0  jnb     loc_18002D13C
0x18002cea6  mov     rdi, rbx
0x18002cea9  mov     r14, rdi
0x18002ceac  cmp     rdi, rsi
0x18002ceaf  jz      short loc_18002CED0
0x18002ceb1  movzx   edx, word ptr [rdi]; Ch
0x18002ceb4  lea     rcx, asc_18007F05C; "="
0x18002cebb  add     rdi, 2
0x18002cebf  call    cs:__imp_wcschr
0x18002cec6  nop     dword ptr [rax+rax+00h]
0x18002cecb  test    rax, rax
0x18002cece  jz      short loc_18002CEA9
0x18002ced0  sub     r14, rbx
0x18002ced3  sar     r14, 1
0x18002ced6  movsxd  rdi, r14d
0x18002ced9  lea     r15, [rbx+rdi*2]
0x18002cedd  mov     r14, r15
0x18002cee0  mov     r12, r14
0x18002cee3  cmp     r14, rbx
0x18002cee6  jz      short loc_18002CF08
0x18002cee8  sub     r14, 2
0x18002ceec  lea     rcx, asc_180088440; ":"
0x18002cef3  movzx   edx, word ptr [r14]; Ch
0x18002cef7  call    cs:__imp_wcschr
0x18002cefe  nop     dword ptr [rax+rax+00h]
0x18002cf03  test    rax, rax
0x18002cf06  jz      short loc_18002CEE0
0x18002cf08  sub     r15, r12
0x18002cf0b  sar     r15, 1
0x18002cf0e  movsxd  rcx, r15d
0x18002cf11  sub     rdi, rcx
0x18002cf14  mov     [rsp+300h+var_2B8], rcx
0x18002cf19  mov     rax, rdi
0x18002cf1c  neg     rax
0x18002cf1f  sbb     r12, r12
0x18002cf22  lea     rdx, [rbx+rdi*2]
0x18002cf26  and     r12, rbx
0x18002cf29  mov     [rsp+300h+var_2C0], rdx
0x18002cf2e  xor     r15d, r15d
0x18002cf31  test    rdi, rdi
0x18002cf34  jz      short loc_18002CF39
0x18002cf36  dec     rdi
0x18002cf39  lea     rax, [rcx+1]
0x18002cf3d  lea     rax, [rdx+rax*2]
0x18002cf41  cmp     rax, rsi
0x18002cf44  jnb     loc_18002D130
0x18002cf4a  cmp     word ptr [rax], 22h ; '"'
0x18002cf4e  jnz     loc_18002D130
0x18002cf54  lea     r15, [rax+2]
0x18002cf58  mov     r14, r15
0x18002cf5b  mov     rbx, r14
0x18002cf5e  cmp     r14, rsi
0x18002cf61  jz      short loc_18002CF83
0x18002cf63  movzx   edx, word ptr [r14]; Ch
0x18002cf67  lea     rcx, asc_18007F130; "\""
0x18002cf6e  add     r14, 2
0x18002cf72  call    cs:__imp_wcschr
0x18002cf79  nop     dword ptr [rax+rax+00h]
0x18002cf7e  test    rax, rax
0x18002cf81  jz      short loc_18002CF5B
0x18002cf83  sub     rbx, r15
0x18002cf86  sar     rbx, 1
0x18002cf89  movsxd  r14, ebx
0x18002cf8c  lea     rbx, [r15+r14*2]
0x18002cf90  cmp     rbx, rsi
0x18002cf93  jnb     loc_18002D10B
0x18002cf99  cmp     word ptr [rbx], 22h ; '"'
0x18002cf9d  jnz     loc_18002D10B
0x18002cfa3  xor     ecx, ecx; dwErrCode
0x18002cfa5  call    cs:__imp_SetLastError
0x18002cfac  nop     dword ptr [rax+rax+00h]
0x18002cfb1  lea     r8, [rbp+200h+var_250]
0x18002cfb5  mov     rdx, r14; unsigned __int64
0x18002cfb8  mov     rcx, r15; unsigned __int16 *
0x18002cfbb  call    ?SxspDequoteString@@YAHPEBG_KAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspDequoteString(ushort const *,unsigned __int64,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18002cfc0  xor     r15d, r15d
0x18002cfc3  test    eax, eax
0x18002cfc5  jz      loc_18002D0FF
0x18002cfcb  test    rdi, rdi
0x18002cfce  jz      short loc_18002D031
0x18002cfd0  xor     ecx, ecx; dwErrCode
0x18002cfd2  call    cs:__imp_SetLastError
0x18002cfd9  nop     dword ptr [rax+rax+00h]
0x18002cfde  mov     r8, rdi
0x18002cfe1  lea     rcx, [rbp+200h+var_1A0]
0x18002cfe5  mov     rdx, r12
0x18002cfe8  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)
0x18002cfed  test    eax, eax
0x18002cfef  jz      loc_18002D0BE
0x18002cff5  xor     ecx, ecx; dwErrCode
0x18002cff7  call    cs:__imp_SetLastError
0x18002cffe  nop     dword ptr [rax+rax+00h]
0x18002d003  lea     r8, [rbp+200h+var_1A0]
0x18002d007  mov     rdx, rdi; unsigned __int64
0x18002d00a  mov     rcx, r12; unsigned __int16 *
0x18002d00d  call    ?SxspDequoteString@@YAHPEBG_KAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspDequoteString(ushort const *,unsigned __int64,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18002d012  test    eax, eax
0x18002d014  jz      loc_18002D0B2
0x18002d01a  mov     rax, [rbp+200h+var_190]
0x18002d01e  mov     [rsp+300h+var_2A8], rax
0x18002d023  mov     rax, [rbp+200h+var_180]
0x18002d02a  mov     [rsp+300h+var_2A0], rax
0x18002d02f  jmp     short loc_18002D03B
0x18002d031  mov     [rsp+300h+var_2A8], r15
0x18002d036  mov     [rsp+300h+var_2A0], r15
0x18002d03b  mov     rax, [rsp+300h+var_2C0]
0x18002d040  xor     ecx, ecx; dwErrCode
0x18002d042  mov     [rsp+300h+var_298], rax
0x18002d047  mov     rax, [rsp+300h+var_2B8]
0x18002d04c  mov     [rsp+300h+var_290], rax
0x18002d051  call    cs:__imp_SetLastError
0x18002d058  nop     dword ptr [rax+rax+00h]
0x18002d05d  mov     rax, [rbp+200h+var_230]
0x18002d061  lea     r8, [rsp+300h+var_2A8]; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x18002d066  mov     r14, [rsp+300h+var_2B0]
0x18002d06b  xor     ecx, ecx; unsigned int
0x18002d06d  mov     r9, [rbp+200h+var_240]; unsigned __int16 *
0x18002d071  mov     rdx, r14; struct _ASSEMBLY_IDENTITY *
0x18002d074  mov     [rsp+300h+var_2E0], rax; char *
0x18002d079  call    ?SxspSetAssemblyIdentityAttributeValue@@YAHKPEAU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEBG_K@Z; SxspSetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const *,unsigned __int64)
0x18002d07e  test    eax, eax
0x18002d080  jz      short loc_18002D0F3
0x18002d082  add     rbx, 2
0x18002d086  cmp     rbx, rsi
0x18002d089  jnz     short loc_18002D0A1
0x18002d08b  cmp     [rbx], r15w
0x18002d08f  jz      loc_18002CE9D
0x18002d095  mov     [rbp+200h+var_268], 0EB8h
0x18002d09c  jmp     loc_18002CD2B
0x18002d0a1  jnb     short loc_18002D0D6
0x18002d0a3  cmp     word ptr [rbx], 2Ch ; ','
0x18002d0a7  jnz     short loc_18002D0CA
0x18002d0a9  add     rbx, 2
0x18002d0ad  jmp     loc_18002CE9D
0x18002d0b2  lea     rcx, off_1800751B0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18002d0b9  jmp     loc_18002CD95
0x18002d0be  lea     rcx, off_1800751D0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18002d0c5  jmp     loc_18002CD95
0x18002d0ca  mov     [rbp+200h+var_268], 0EBCh
0x18002d0d1  jmp     loc_18002CD2B
0x18002d0d6  mov     edx, 57h ; 'W'; unsigned int
0x18002d0db  lea     rcx, [rsp+300h+var_288]; this
0x18002d0e0  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x18002d0e5  lea     rcx, off_180075170; struct _CALL_SITE_INFO *
0x18002d0ec  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18002d0f1  jmp     short loc_18002D162
0x18002d0f3  lea     rcx, off_180075190; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18002d0fa  jmp     loc_18002CD95
0x18002d0ff  lea     rcx, off_1800751F0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18002d106  jmp     loc_18002CD95
0x18002d10b  mov     [rbp+200h+var_268], 0E8Dh
0x18002d112  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18002d117  mov     ecx, 57h ; 'W'; dwErrCode
0x18002d11c  call    cs:__imp_SetLastError
0x18002d123  nop     dword ptr [rax+rax+00h]
0x18002d128  xor     r15d, r15d
0x18002d12b  jmp     loc_18002CD41
0x18002d130  mov     [rbp+200h+var_268], 0E87h
0x18002d137  jmp     loc_18002CD2B
0x18002d13c  xor     ecx, ecx; dwErrCode
0x18002d13e  mov     [rsp+300h+var_2D0], r15
0x18002d143  mov     [rsp+300h+var_2C8], r15b
0x18002d148  mov     [r13+0], r14
0x18002d14c  call    cs:__imp_SetLastError
0x18002d153  nop     dword ptr [rax+rax+00h]
0x18002d158  mov     rax, [rbp+200h+var_260]
0x18002d15c  mov     dword ptr [rax], 1
0x18002d162  mov     rax, [rbp+200h+var_260]
  ... truncated ...
```
