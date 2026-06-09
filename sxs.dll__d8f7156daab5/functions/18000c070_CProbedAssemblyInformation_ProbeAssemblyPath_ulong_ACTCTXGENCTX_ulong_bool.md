# CProbedAssemblyInformation::ProbeAssemblyPath(ulong,_ACTCTXGENCTX *,ulong,bool &)

- ea: `0x18000c070`
- end: `0x18000c819`
- name: `?ProbeAssemblyPath@CProbedAssemblyInformation@@QEAAHKPEAU_ACTCTXGENCTX@@KAEA_N@Z`
- size: `1961`
- prototype: `__int64 __usercall@<rax>(CProbedAssemblyInformation *__hidden this@<rcx>, unsigned int@<edx>, struct _ACTCTXGENCTX *@<r8>, unsigned int@<r9d>, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18000cd10`

## callees

- `0x18000bc20`
- `0x18000c000`
- `0x18000c070`
- `0x18000c820`
- `0x18000dffc`
- `0x18001c2c8`
- `0x180053760`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000c1c5`
- `ntdll!EtwEventWrite` at `0x18000c311`
- `ntdll!EtwEventWrite` at `0x18000c3f2`
- `ntdll!EtwEventWrite` at `0x18000c521`
- `ntdll!EtwEventWrite` at `0x18000c5ca`
- `ntdll!EtwEventWrite` at `0x18000c682`
- `ntdll!EtwEventWrite` at `0x18000c1c5`
- `ntdll!EtwEventWrite` at `0x18000c311`
- `ntdll!EtwEventWrite` at `0x18000c3f2`
- `ntdll!EtwEventWrite` at `0x18000c521`
- `ntdll!EtwEventWrite` at `0x18000c5ca`
- `ntdll!EtwEventWrite` at `0x18000c682`
- `ntdll!RtlPopFrame` at `0x18000c6a3`
- `ntdll!RtlPopFrame` at `0x18000c6a3`
- `ntdll!RtlPushFrame` at `0x18000c0ee`
- `ntdll!RtlPushFrame` at `0x18000c0ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c1ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c400`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c5d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c6ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c747`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c788`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c1ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c400`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c5d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c6ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c747`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c788`

## string_xrefs

- `0x18000c326`: `SXS.DLL: Probing for manifest: %S\n`
- `0x18000c450`: `SXS.DLL: Probed manifest: %S is found.\n`

## pseudocode

```c
__int64 __fastcall CProbedAssemblyInformation::ProbeAssemblyPath(
        CProbedAssemblyInformation *this,
        int a2,
        struct _ACTCTXGENCTX *a3,
        __int64 a4,
        bool *a5)
{
  char v7; // di
  int v8; // r14d
  int v9; // r12d
  unsigned __int64 *v10; // r15
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rax
  bool v15; // zf
  bool *v16; // rdi
  __int64 v17; // rax
  __int64 v18; // r8
  int *v19; // rdx
  unsigned int v20; // ebx
  unsigned __int64 i; // rcx
  DWORD LastError; // eax
  char v24; // [rsp+50h] [rbp-B0h] BYREF
  bool v25; // [rsp+51h] [rbp-AFh] BYREF
  int v26; // [rsp+54h] [rbp-ACh] BYREF
  bool *v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  int v31; // [rsp+70h] [rbp-90h] BYREF
  int v32; // [rsp+78h] [rbp-88h] BYREF
  int v33; // [rsp+80h] [rbp-80h] BYREF
  int v34; // [rsp+88h] [rbp-78h] BYREF
  int v35; // [rsp+8Ch] [rbp-74h]
  __int64 v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+98h] [rbp-68h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-48h]
  int v40; // [rsp+C0h] [rbp-40h]
  int *v41; // [rsp+C8h] [rbp-38h]
  _WIN32_FILE_ATTRIBUTE_DATA FileInformation; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v43[5]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v44; // [rsp+150h] [rbp+50h]
  int *v45; // [rsp+160h] [rbp+60h] BYREF
  __int64 v46; // [rsp+168h] [rbp+68h]
  __int64 v47; // [rsp+170h] [rbp+70h]
  int v48; // [rsp+178h] [rbp+78h]
  int v49; // [rsp+17Ch] [rbp+7Ch]
  int *v50; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v51; // [rsp+1B8h] [rbp+B8h]

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006C8E0;
  v32 = a2;
  v41 = &v37;
  v27 = a5;
  v37 = 0;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v39 = 544438355;
  v40 = 520;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v26 = 0;
  v7 = 0;
  v8 = 0;
  v44 = 0;
  v25 = 0;
  v33 = *((_DWORD *)a3 + 326);
  v31 = v33;
  memset(v43, 0, sizeof(v43));
  v24 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( g_TraceEnabled
    && (unsigned __int8)(g_TraceLevel - 1) > 2u
    && (g_OrKeywordMask & 0x100) != 0
    && (g_AndKeywordMask & 0x100) == g_AndKeywordMask )
  {
    v45 = &v31;
    v34 = 206;
    v35 = 6750212;
    v36 = 256;
    v46 = 4;
    EtwEventWrite(g_hTraceHandle, &v34, 1, &v45);
  }
  *a5 = 0;
  v9 = 0;
  v10 = (unsigned __int64 *)((char *)this + 48);
  v11 = -1;
  while ( 1 )
  {
    if ( v7 )
    {
      v16 = v27;
      goto LABEL_40;
    }
    SetLastError(0);
    if ( !(unsigned int)SxspGenerateManifestPathForProbing(
                          v9,
                          v32,
                          *((_QWORD *)a3 + 11),
                          *((_QWORD *)a3 + 13),
                          (__int64)a3 + 2392,
                          *(_QWORD *)this,
                          (__int64)v43,
                          (__int64)this + 16,
                          (__int64)&v26,
                          (__int64)&v24) )
    {
      *v41 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180078708);
      goto LABEL_47;
    }
    v10 = (unsigned __int64 *)((char *)this + 48);
    if ( !*((_QWORD *)this + 6) )
    {
      v8 = v26;
      if ( !v9 && !v26 )
      {
        v31 = *((_DWORD *)a3 + 326);
        if ( g_TraceEnabled )
        {
          if ( (unsigned __int8)(g_TraceLevel - 1) > 2u
            && (g_OrKeywordMask & 0x100) != 0
            && (g_AndKeywordMask & 0x100) == g_AndKeywordMask )
          {
            v50 = &v31;
            v28 = 262;
            v29 = 6750212;
            v30 = 256;
            v51 = 4;
            EtwEventWrite(g_hTraceHandle, &v28, 1, &v50);
          }
        }
      }
      goto LABEL_30;
    }
    FusionpDbgPrintEx(0x80800000, "SXS.DLL: Probing for manifest: %S\n", *((const wchar_t **)this + 4));
    v31 = *((_DWORD *)a3 + 326);
    if ( g_TraceEnabled
      && (unsigned __int8)(g_TraceLevel - 1) > 2u
      && (g_OrKeywordMask & 0x100) != 0
      && (g_AndKeywordMask & 0x100) == g_AndKeywordMask )
    {
      v12 = *((_QWORD *)this + 4);
      v34 = 250;
      v35 = 6750212;
      v13 = 1;
      v36 = 256;
      v45 = &v31;
      v46 = 4;
      if ( v12 )
      {
        v47 = v12;
        v14 = -1;
        do
          v15 = *(_WORD *)(v12 + 2 * v14++ + 2) == 0;
        while ( !v15 );
        v49 = 0;
        v48 = 2 * v14 + 2;
        v13 = 2;
      }
      EtwEventWrite(g_hTraceHandle, &v34, v13, &v45);
    }
    SetLastError(0);
    v16 = v27;
    v8 = v26;
    if ( !(unsigned int)CProbedAssemblyInformation::ProbeManifestExistence(this, v26, v27, &v25, &FileInformation) )
    {
      *v41 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800786E8);
      goto LABEL_47;
    }
    if ( *v16 )
      break;
LABEL_30:
    v7 = v24;
    ++v9;
  }
  FusionpDbgPrintEx(0x80800000, "SXS.DLL: Probed manifest: %S is found.\n", *((const wchar_t **)this + 4));
  v32 = *((_DWORD *)a3 + 326);
  if ( g_TraceEnabled
    && (unsigned __int8)(g_TraceLevel - 1) > 2u
    && (g_OrKeywordMask & 0x100) != 0
    && (g_AndKeywordMask & 0x100) == g_AndKeywordMask )
  {
    v17 = *((_QWORD *)this + 4);
    v45 = &v32;
    v18 = 1;
    v28 = 251;
    v29 = 6750212;
    v30 = 256;
    v46 = 4;
    if ( v17 )
    {
      v47 = v17;
      do
        v15 = *(_WORD *)(v17 + 2 * v11++ + 2) == 0;
      while ( !v15 );
      v49 = 0;
      v48 = 2 * v11 + 2;
      v18 = 2;
    }
    EtwEventWrite(g_hTraceHandle, &v28, v18, &v45);
  }
LABEL_40:
  if ( !*v16 )
  {
    v32 = *((_DWORD *)a3 + 326);
    if ( g_TraceEnabled
      && (unsigned __int8)(g_TraceLevel - 1) > 2u
      && (g_OrKeywordMask & 0x100) != 0
      && (g_AndKeywordMask & 0x100) == g_AndKeywordMask )
    {
      v50 = &v32;
      v28 = 260;
      v29 = 6750212;
      v30 = 256;
      v51 = 4;
      EtwEventWrite(g_hTraceHandle, &v28, 1, &v50);
    }
LABEL_46:
    SetLastError(0);
    *v41 = 1;
    goto LABEL_47;
  }
  *((_DWORD *)this + 2) = 2;
  *((_DWORD *)this + 148) = 0;
  SetLastError(0);
  if ( (unsigned int)CProbedAssemblyInformation::ValidateManifestPath(this, &FileInformation, v8) )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= *v10 )
      {
        SetLastError(0x54Fu);
        *v41 = 0;
        goto LABEL_47;
      }
      if ( *(_WORD *)(*((_QWORD *)this + 4) + 2 * i) == 92 )
        break;
    }
    SetLastError(0);
    *((_QWORD *)this + 72) = FileInformation.ftLastWriteTime;
    if ( v25 )
      *((_DWORD *)this + 148) = 2;
    if ( v8 )
      *((_DWORD *)this + 148) |= 0x10u;
    goto LABEL_46;
  }
  *v41 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006DA78);
LABEL_47:
  v19 = v41;
  v20 = *v41;
  if ( g_TraceEnabled
    && (unsigned __int8)(g_TraceLevel - 1) > 2u
    && (g_OrKeywordMask & 0x100) != 0
    && (g_AndKeywordMask & 0x100) == g_AndKeywordMask )
  {
    v50 = &v33;
    v28 = 207;
    v29 = 6750212;
    v30 = 256;
    v51 = 4;
    EtwEventWrite(g_hTraceHandle, &v28, 1, &v50);
    v19 = v41;
  }
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v19 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v20;
}

```

## disassembly

```asm
0x18000c070  mov     [rsp-8+arg_18], rbx
0x18000c075  push    rbp
0x18000c076  push    rsi
0x18000c077  push    rdi
0x18000c078  push    r12
0x18000c07a  push    r13
0x18000c07c  push    r14
0x18000c07e  push    r15
0x18000c080  lea     rbp, [rsp-110h]
0x18000c088  sub     rsp, 210h
0x18000c08f  mov     rax, cs:__security_cookie
0x18000c096  xor     rax, rsp
0x18000c099  mov     [rbp+140h+var_40], rax
0x18000c0a0  mov     rbx, [rbp+140h+arg_20]
0x18000c0a7  lea     rax, qword_18006C8E0
0x18000c0ae  mov     [rbp+140h+Frame.Context], rax
0x18000c0b2  mov     rsi, rcx
0x18000c0b5  lea     rax, [rbp+140h+var_1A8]
0x18000c0b9  mov     [rsp+240h+var_1C8], edx
0x18000c0bd  xor     r15d, r15d
0x18000c0c0  mov     [rbp+140h+var_178], rax
0x18000c0c4  lea     rcx, [rbp+140h+Frame]; Frame
0x18000c0c8  mov     [rsp+240h+var_1E8], rbx
0x18000c0cd  mov     r13, r8
0x18000c0d0  mov     [rbp+140h+var_1A8], r15d
0x18000c0d4  mov     [rbp+140h+Frame.Flags], 1
0x18000c0db  mov     [rbp+140h+Frame.Previous], r15
0x18000c0df  mov     [rbp+140h+var_188], 20737853h
0x18000c0e7  mov     [rbp+140h+var_180], 208h
0x18000c0ee  call    cs:__imp_RtlPushFrame
0x18000c0f5  nop     dword ptr [rax+rax+00h]
0x18000c0fa  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x18000c101  jnz     loc_18000C779
0x18000c107  xorps   xmm0, xmm0
0x18000c10a  mov     [rsp+240h+var_1EC], r15d
0x18000c10f  xor     eax, eax
0x18000c111  xor     dil, dil
0x18000c114  cmp     cs:?g_TraceEnabled@@3KA, r15d; ulong g_TraceEnabled
0x18000c11b  mov     r14d, r15d
0x18000c11e  mov     [rbp+140h+var_F0], rax
0x18000c122  mov     [rsp+240h+var_1EF], al
0x18000c126  mov     [rbp+140h+FileInformation.nFileSizeLow], eax
0x18000c129  mov     eax, [r13+518h]
0x18000c130  mov     [rbp+140h+var_1C0], eax
0x18000c133  mov     [rsp+240h+var_1D0], eax
0x18000c137  movups  [rbp+140h+var_140], xmm0
0x18000c13b  mov     [rsp+240h+var_1F0], dil
0x18000c140  movups  [rbp+140h+var_130], xmm0
0x18000c144  movups  [rbp+140h+var_120], xmm0
0x18000c148  movups  [rbp+140h+var_110], xmm0
0x18000c14c  movups  [rbp+140h+var_100], xmm0
0x18000c150  movups  xmmword ptr [rbp+140h+FileInformation.dwFileAttributes], xmm0
0x18000c154  movups  xmmword ptr [rbp+140h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18000c158  jz      short loc_18000C1D1
0x18000c15a  movzx   eax, cs:?g_TraceLevel@@3EA; uchar g_TraceLevel
0x18000c161  dec     al
0x18000c163  cmp     al, 2
0x18000c165  jbe     short loc_18000C1D1
0x18000c167  test    cs:?g_OrKeywordMask@@3_KA, 100h; unsigned __int64 g_OrKeywordMask
0x18000c172  jz      short loc_18000C1D1
0x18000c174  mov     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18000c17b  and     eax, 100h
0x18000c180  cmp     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18000c187  jnz     short loc_18000C1D1
0x18000c189  mov     rcx, cs:?g_hTraceHandle@@3_KA; unsigned __int64 g_hTraceHandle
0x18000c190  lea     rax, [rsp+240h+var_1D0]
0x18000c195  lea     r9, [rbp+140h+var_E0]
0x18000c199  mov     [rbp+140h+var_E0], rax
0x18000c19d  mov     r8d, 1
0x18000c1a3  mov     [rbp+140h+var_1B8], 0CEh
0x18000c1aa  lea     rdx, [rbp+140h+var_1B8]
0x18000c1ae  mov     [rbp+140h+var_1B4], 670004h
0x18000c1b5  mov     [rbp+140h+var_1B0], 100h
0x18000c1bd  mov     [rbp+140h+var_D8], 4
0x18000c1c5  call    cs:__imp_EtwEventWrite
0x18000c1cc  nop     dword ptr [rax+rax+00h]
0x18000c1d1  mov     [rbx], dil
0x18000c1d4  mov     r12d, r15d
0x18000c1d7  lea     r15, [rsi+30h]
0x18000c1db  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000c1e2  test    dil, dil
0x18000c1e5  jnz     loc_18000C79F
0x18000c1eb  xor     ecx, ecx; dwErrCode
0x18000c1ed  call    cs:__imp_SetLastError
0x18000c1f4  nop     dword ptr [rax+rax+00h]
0x18000c1f9  mov     r9, [r13+68h]
0x18000c1fd  lea     rcx, [r13+958h]
0x18000c204  mov     r8, [r13+58h]
0x18000c208  lea     rdx, [rsp+240h+var_1F0]
0x18000c20d  mov     [rsp+240h+var_1F8], rdx
0x18000c212  lea     rax, [rsi+10h]
0x18000c216  lea     rdx, [rsp+240h+var_1EC]
0x18000c21b  mov     [rsp+240h+var_200], rdx
0x18000c220  mov     edx, [rsp+240h+var_1C8]
0x18000c224  mov     [rsp+240h+var_208], rax
0x18000c229  lea     rax, [rbp+140h+var_140]
0x18000c22d  mov     [rsp+240h+var_210], rax
0x18000c232  mov     rax, [rsi]
0x18000c235  mov     [rsp+240h+var_218], rax
0x18000c23a  mov     [rsp+240h+lpFileInformation], rcx
0x18000c23f  mov     ecx, r12d
0x18000c242  call    ?SxspGenerateManifestPathForProbing@@YAHKKPEBG_KPEBV?$CFusionArray@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@V1@$0A@$0CA@@@PEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEAHAEA_N@Z; SxspGenerateManifestPathForProbing(ulong,ulong,ushort const *,unsigned __int64,CFusionArray<CGenericStringBuffer<260,CUnicodeCharTraits>,CGenericStringBuffer<260,CUnicodeCharTraits>,0,32> const *,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,CGenericBaseStringBuffer<CUnicodeCharTraits> &,int *,bool &)
0x18000c247  test    eax, eax
0x18000c249  jz      loc_18000C7C4
0x18000c24f  cmp     qword ptr [rsi+30h], 0
0x18000c254  lea     r15, [rsi+30h]
0x18000c258  jnz     loc_18000C322
0x18000c25e  mov     r14d, [rsp+240h+var_1EC]
0x18000c263  test    r12d, r12d
0x18000c266  jnz     loc_18000C43F
0x18000c26c  test    r14d, r14d
0x18000c26f  jnz     loc_18000C43F
0x18000c275  cmp     cs:?g_TraceEnabled@@3KA, r12d; ulong g_TraceEnabled
0x18000c27c  mov     eax, [r13+518h]
0x18000c283  mov     [rsp+240h+var_1D0], eax
0x18000c287  jz      loc_18000C43F
0x18000c28d  movzx   eax, cs:?g_TraceLevel@@3EA; uchar g_TraceLevel
0x18000c294  dec     al
0x18000c296  cmp     al, 2
0x18000c298  jbe     loc_18000C43F
0x18000c29e  test    cs:?g_OrKeywordMask@@3_KA, 100h; unsigned __int64 g_OrKeywordMask
0x18000c2a9  jz      loc_18000C43F
0x18000c2af  mov     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18000c2b6  and     eax, 100h
0x18000c2bb  cmp     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18000c2c2  jnz     loc_18000C43F
0x18000c2c8  mov     rcx, cs:?g_hTraceHandle@@3_KA; unsigned __int64 g_hTraceHandle
0x18000c2cf  lea     rax, [rsp+240h+var_1D0]
0x18000c2d4  lea     r9, [rbp+140h+var_90]
0x18000c2db  mov     [rbp+140h+var_90], rax
0x18000c2e2  mov     r8d, 1
0x18000c2e8  mov     [rsp+240h+var_1E0], 106h
0x18000c2f0  lea     rdx, [rsp+240h+var_1E0]
0x18000c2f5  mov     [rsp+240h+var_1DC], 670004h
0x18000c2fd  mov     [rsp+240h+var_1D8], 100h
0x18000c306  mov     [rbp+140h+var_88], 4
0x18000c311  call    cs:__imp_EtwEventWrite
0x18000c318  nop     dword ptr [rax+rax+00h]
0x18000c31d  jmp     loc_18000C43F
0x18000c322  mov     r8, [rsi+20h]
0x18000c326  lea     rdx, aSxsDllProbingF; "SXS.DLL: Probing for manifest: %S\n"
0x18000c32d  mov     ecx, 80800000h; unsigned int
0x18000c332  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18000c337  cmp     cs:?g_TraceEnabled@@3KA, 0; ulong g_TraceEnabled
0x18000c33e  mov     eax, [r13+518h]
0x18000c345  mov     [rsp+240h+var_1D0], eax
0x18000c349  jz      loc_18000C3FE
0x18000c34f  movzx   eax, cs:?g_TraceLevel@@3EA; uchar g_TraceLevel
0x18000c356  dec     al
0x18000c358  cmp     al, 2
0x18000c35a  jbe     loc_18000C3FE
0x18000c360  test    cs:?g_OrKeywordMask@@3_KA, 100h; unsigned __int64 g_OrKeywordMask
0x18000c36b  jz      loc_18000C3FE
0x18000c371  mov     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18000c378  and     eax, 100h
0x18000c37d  cmp     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18000c384  jnz     short loc_18000C3FE
0x18000c386  mov     rcx, [rsi+20h]
0x18000c38a  lea     rax, [rsp+240h+var_1D0]
0x18000c38f  xor     edx, edx
0x18000c391  mov     [rbp+140h+var_1B8], 0FAh
0x18000c398  mov     [rbp+140h+var_1B4], 670004h
0x18000c39f  mov     r8d, 1
0x18000c3a5  mov     [rbp+140h+var_1B0], 100h
0x18000c3ad  mov     [rbp+140h+var_E0], rax
0x18000c3b1  mov     [rbp+140h+var_D8], 4
0x18000c3b9  test    rcx, rcx
0x18000c3bc  jz      short loc_18000C3E3
0x18000c3be  mov     [rbp+140h+var_D0], rcx
0x18000c3c2  mov     rax, rbx
0x18000c3c5  cmp     [rcx+rax*2+2], dx
0x18000c3ca  lea     rax, [rax+1]
0x18000c3ce  jnz     short loc_18000C3C5
0x18000c3d0  lea     eax, ds:2[rax*2]
0x18000c3d7  mov     [rbp+140h+var_C4], edx
0x18000c3da  mov     [rbp+140h+var_C8], eax
0x18000c3dd  mov     r8d, 2
0x18000c3e3  mov     rcx, cs:?g_hTraceHandle@@3_KA; unsigned __int64 g_hTraceHandle
0x18000c3ea  lea     r9, [rbp+140h+var_E0]
0x18000c3ee  lea     rdx, [rbp+140h+var_1B8]
0x18000c3f2  call    cs:__imp_EtwEventWrite
0x18000c3f9  nop     dword ptr [rax+rax+00h]
0x18000c3fe  xor     ecx, ecx; dwErrCode
0x18000c400  call    cs:__imp_SetLastError
0x18000c407  nop     dword ptr [rax+rax+00h]
0x18000c40c  mov     rdi, [rsp+240h+var_1E8]
0x18000c411  lea     rax, [rbp+140h+FileInformation]
0x18000c415  mov     r14d, [rsp+240h+var_1EC]
0x18000c41a  lea     r9, [rsp+240h+var_1EF]; bool *
0x18000c41f  mov     r8, rdi; bool *
0x18000c422  mov     [rsp+240h+lpFileInformation], rax; lpFileInformation
0x18000c427  mov     edx, r14d; int
0x18000c42a  mov     rcx, rsi; this
0x18000c42d  call    ?ProbeManifestExistence@CProbedAssemblyInformation@@QEBAHHAEA_N0AEAU_WIN32_FILE_ATTRIBUTE_DATA@@@Z; CProbedAssemblyInformation::ProbeManifestExistence(int,bool &,bool &,_WIN32_FILE_ATTRIBUTE_DATA &)
0x18000c432  test    eax, eax
0x18000c434  jz      loc_18000C7A9
0x18000c43a  cmp     byte ptr [rdi], 0
0x18000c43d  jnz     short loc_18000C44C
0x18000c43f  movzx   edi, [rsp+240h+var_1F0]
0x18000c444  inc     r12d
0x18000c447  jmp     loc_18000C1E2
0x18000c44c  mov     r8, [rsi+20h]
0x18000c450  lea     rdx, aSxsDllProbedMa; "SXS.DLL: Probed manifest: %S is found."...
0x18000c457  mov     ecx, 80800000h; unsigned int
0x18000c45c  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18000c461  cmp     cs:?g_TraceEnabled@@3KA, 0; ulong g_TraceEnabled
0x18000c468  mov     eax, [r13+518h]
0x18000c46f  mov     [rsp+240h+var_1C8], eax
0x18000c473  jz      loc_18000C52D
0x18000c479  movzx   eax, cs:?g_TraceLevel@@3EA; uchar g_TraceLevel
0x18000c480  dec     al
0x18000c482  cmp     al, 2
0x18000c484  jbe     loc_18000C52D
0x18000c48a  test    cs:?g_OrKeywordMask@@3_KA, 100h; unsigned __int64 g_OrKeywordMask
0x18000c495  jz      loc_18000C52D
0x18000c49b  mov     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18000c4a2  and     eax, 100h
0x18000c4a7  cmp     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18000c4ae  jnz     loc_18000C52D
0x18000c4b4  mov     rax, [rsi+20h]
0x18000c4b8  lea     rcx, [rsp+240h+var_1C8]
0x18000c4bd  mov     [rbp+140h+var_E0], rcx
0x18000c4c1  mov     r8d, 1
0x18000c4c7  xor     ecx, ecx
0x18000c4c9  mov     [rsp+240h+var_1E0], 0FBh
0x18000c4d1  mov     [rsp+240h+var_1DC], 670004h
0x18000c4d9  mov     [rsp+240h+var_1D8], 100h
0x18000c4e2  mov     [rbp+140h+var_D8], 4
0x18000c4ea  test    rax, rax
0x18000c4ed  jz      short loc_18000C511
0x18000c4ef  mov     [rbp+140h+var_D0], rax
0x18000c4f3  cmp     [rax+rbx*2+2], cx
0x18000c4f8  lea     rbx, [rbx+1]
0x18000c4fc  jnz     short loc_18000C4F3
0x18000c4fe  lea     eax, ds:2[rbx*2]
0x18000c505  mov     [rbp+140h+var_C4], ecx
0x18000c508  mov     [rbp+140h+var_C8], eax
0x18000c50b  mov     r8d, 2
0x18000c511  mov     rcx, cs:?g_hTraceHandle@@3_KA; unsigned __int64 g_hTraceHandle
0x18000c518  lea     r9, [rbp+140h+var_E0]
0x18000c51c  lea     rdx, [rsp+240h+var_1E0]
0x18000c521  call    cs:__imp_EtwEventWrite
0x18000c528  nop     dword ptr [rax+rax+00h]
0x18000c52d  cmp     byte ptr [rdi], 0
0x18000c530  jnz     loc_18000C6DC
0x18000c536  cmp     cs:?g_TraceEnabled@@3KA, 0; ulong g_TraceEnabled
0x18000c53d  mov     eax, [r13+518h]
0x18000c544  mov     [rsp+240h+var_1C8], eax
0x18000c548  jz      loc_18000C5D6
0x18000c54e  movzx   eax, cs:?g_TraceLevel@@3EA; uchar g_TraceLevel
0x18000c555  dec     al
0x18000c557  cmp     al, 2
0x18000c559  jbe     loc_18000C5D6
0x18000c55f  test    cs:?g_OrKeywordMask@@3_KA, 100h; unsigned __int64 g_OrKeywordMask
0x18000c56a  jz      short loc_18000C5D6
0x18000c56c  mov     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18000c573  and     eax, 100h
0x18000c578  cmp     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18000c57f  jnz     short loc_18000C5D6
0x18000c581  mov     rcx, cs:?g_hTraceHandle@@3_KA; unsigned __int64 g_hTraceHandle
0x18000c588  lea     rax, [rsp+240h+var_1C8]
0x18000c58d  lea     r9, [rbp+140h+var_90]
0x18000c594  mov     [rbp+140h+var_90], rax
0x18000c59b  mov     r8d, 1
0x18000c5a1  mov     [rsp+240h+var_1E0], 104h
0x18000c5a9  lea     rdx, [rsp+240h+var_1E0]
0x18000c5ae  mov     [rsp+240h+var_1DC], 670004h
0x18000c5b6  mov     [rsp+240h+var_1D8], 100h
0x18000c5bf  mov     [rbp+140h+var_88], 4
0x18000c5ca  call    cs:__imp_EtwEventWrite
0x18000c5d1  nop     dword ptr [rax+rax+00h]
0x18000c5d6  xor     ecx, ecx; dwErrCode
0x18000c5d8  call    cs:__imp_SetLastError
0x18000c5df  nop     dword ptr [rax+rax+00h]
0x18000c5e4  mov     rax, [rbp+140h+var_178]
0x18000c5e8  mov     dword ptr [rax], 1
0x18000c5ee  cmp     cs:?g_TraceEnabled@@3KA, 0; ulong g_TraceEnabled
0x18000c5f5  mov     rdx, [rbp+140h+var_178]
0x18000c5f9  mov     eax, [rbp+140h+var_1C0]
0x18000c5fc  mov     [rbp+140h+var_1C0], eax
0x18000c5ff  mov     ebx, [rdx]
0x18000c601  jz      loc_18000C692
0x18000c607  movzx   eax, cs:?g_TraceLevel@@3EA; uchar g_TraceLevel
0x18000c60e  dec     al
0x18000c610  cmp     al, 2
0x18000c612  jbe     loc_18000C692
0x18000c618  test    cs:?g_OrKeywordMask@@3_KA, 100h; unsigned __int64 g_OrKeywordMask
0x18000c623  jz      short loc_18000C692
0x18000c625  mov     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18000c62c  and     eax, 100h
0x18000c631  cmp     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18000c638  jnz     short loc_18000C692
0x18000c63a  mov     rcx, cs:?g_hTraceHandle@@3_KA; unsigned __int64 g_hTraceHandle
0x18000c641  lea     rax, [rbp+140h+var_1C0]
0x18000c645  lea     r9, [rbp+140h+var_90]
0x18000c64c  mov     [rbp+140h+var_90], rax
0x18000c653  mov     r8d, 1
0x18000c659  mov     [rsp+240h+var_1E0], 0CFh
0x18000c661  lea     rdx, [rsp+240h+var_1E0]
0x18000c666  mov     [rsp+240h+var_1DC], 670004h
  ... truncated ...
```
