# SxspGenerateManifestPathForProbing(ulong,ulong,ushort const *,unsigned __int64,CFusionArray<CGenericStringBuffer<260,CUnicodeCharTraits>,CGenericStringBuffer<260,CUnicodeCharTraits>,0,32> const *,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,CGenericBaseStringBuffer<CUnicodeCharTraits> &,int *,bool &)

- ea: `0x18000c820`
- end: `0x18000cd08`
- name: `?SxspGenerateManifestPathForProbing@@YAHKKPEBG_KPEBV?$CFusionArray@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@V1@$0A@$0CA@@@PEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEAHAEA_N@Z`
- size: `1256`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c070`

## callees

- `0x18000c820`
- `0x18000dffc`
- `0x18001c2c8`
- `0x180023320`
- `0x18005cf40`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18000c941`
- `ntdll!RtlPopFrame` at `0x18000ca0c`
- `ntdll!RtlPopFrame` at `0x18000ca33`
- `ntdll!RtlPopFrame` at `0x18000cbbf`
- `ntdll!RtlPopFrame` at `0x18000c941`
- `ntdll!RtlPopFrame` at `0x18000ca0c`
- `ntdll!RtlPopFrame` at `0x18000ca33`
- `ntdll!RtlPopFrame` at `0x18000cbbf`
- `ntdll!RtlPushFrame` at `0x18000c8ba`
- `ntdll!RtlPushFrame` at `0x18000c90a`
- `ntdll!RtlPushFrame` at `0x18000c9c9`
- `ntdll!RtlPushFrame` at `0x18000c8ba`
- `ntdll!RtlPushFrame` at `0x18000c90a`
- `ntdll!RtlPushFrame` at `0x18000c9c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ca83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ca83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc6d`

## pseudocode

```c
__int64 __fastcall SxspGenerateManifestPathForProbing(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        struct _ASSEMBLY_IDENTITY *a6,
        __int64 a7,
        _QWORD *a8,
        _DWORD *a9,
        _BYTE *a10)
{
  unsigned __int64 v10; // rsi
  struct _ASSEMBLY_IDENTITY *v11; // rdi
  unsigned int v12; // ebx
  __int64 v13; // r12
  char v14; // dl
  _WORD *v15; // rcx
  const char *v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rdi
  char v19; // dl
  __int64 v20; // rcx
  __int16 v21; // r8
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rax
  __int64 v24; // rbx
  unsigned int v25; // ebx
  DWORD LastError; // eax
  __int64 v29; // [rsp+48h] [rbp-A1h] BYREF
  __int64 v30; // [rsp+50h] [rbp-99h]
  _BYTE *v31; // [rsp+58h] [rbp-91h] BYREF
  __int64 v32; // [rsp+60h] [rbp-89h]
  struct _ASSEMBLY_IDENTITY *v33; // [rsp+68h] [rbp-81h]
  __int64 v34; // [rsp+70h] [rbp-79h]
  __int64 v35; // [rsp+78h] [rbp-71h]
  int v36; // [rsp+80h] [rbp-69h] BYREF
  int v37; // [rsp+84h] [rbp-65h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+88h] [rbp-61h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-49h]
  int v40; // [rsp+A8h] [rbp-41h]
  int *v41; // [rsp+B0h] [rbp-39h]
  struct _TEB_ACTIVE_FRAME v42; // [rsp+B8h] [rbp-31h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-19h]
  int v44; // [rsp+D8h] [rbp-11h]

  v10 = 0;
  v11 = a6;
  v12 = a2;
  v35 = a7;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006C7C0;
  v13 = a1;
  v41 = &v37;
  v29 = a4;
  v34 = a3;
  v33 = a6;
  v31 = a10;
  v37 = 0;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v39 = 544438355;
  v40 = 1841;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v36 = 0;
  *a10 = 0;
  if ( a9 )
    *a9 = 0;
  v42.Flags = 1;
  v42.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear'::`2'::__stc;
  v42.Previous = 0;
  v43 = 544438355;
  v44 = 579;
  RtlPushFrame(&v42);
  v14 = g_FusionEnterExitTracingEnabled;
  if ( g_FusionEnterExitTracingEnabled )
  {
    FusionpTraceCallEntry();
    v14 = g_FusionEnterExitTracingEnabled;
  }
  v15 = (_WORD *)a8[2];
  if ( v15 )
    *v15 = 0;
  a8[4] = 0;
  if ( v14 )
    FusionpTraceCallExit();
  RtlPopFrame(&v42);
  if ( !a6 )
  {
    v40 = 1851;
    goto LABEL_45;
  }
  if ( (v12 & 0xFFFFFF01) != 0 )
  {
    v40 = 1858;
    goto LABEL_45;
  }
  if ( !a5 )
  {
    if ( (unsigned int)v13 < 2 )
    {
LABEL_34:
      SetLastError(0);
      v30 = v34;
      v31 = 0;
      v32 = 0;
      if ( !(unsigned int)SxspExpandProbingCandidate(
                            v12,
                            &(&off_18006CA60)[2 * v13],
                            v11,
                            v35,
                            &v29,
                            (unsigned __int64 *)&v31,
                            a8,
                            &v36) )
      {
        *v41 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075750);
        goto LABEL_38;
      }
      goto LABEL_35;
    }
    if ( (v12 & 4) != 0 )
    {
LABEL_43:
      *v31 = 1;
LABEL_35:
      if ( a9 )
        *a9 = v36;
      v37 = 1;
      goto LABEL_38;
    }
    v40 = 1875;
LABEL_45:
    FusionpTraceParameterCheck(v16);
    SetLastError(0x57u);
    *v41 = 0;
    goto LABEL_38;
  }
  while ( v10 < *(_QWORD *)(a5 + 24) )
  {
    v17 = *(_QWORD *)(a5 + 8);
    v18 = 560 * v10;
    if ( !*(_QWORD *)(560 * v10 + v17 + 16) )
    {
      v40 = 1866;
      goto LABEL_45;
    }
    if ( !*(_QWORD *)(v18 + v17 + 32) )
    {
      v40 = 1867;
      goto LABEL_45;
    }
    v42.Flags = 1;
    v42.Previous = 0;
    v42.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericBaseStringBuffer<CUnicodeCharTraits>::HasTrailingPathSeparator'::`2'::__stc;
    v43 = 544438355;
    v44 = 1005;
    RtlPushFrame(&v42);
    v19 = g_FusionEnterExitTracingEnabled;
    if ( g_FusionEnterExitTracingEnabled )
    {
      FusionpTraceCallEntry();
      v19 = g_FusionEnterExitTracingEnabled;
    }
    v20 = *(_QWORD *)(v18 + v17 + 32);
    if ( !v20 || (v21 = *(_WORD *)(*(_QWORD *)(v18 + v17 + 16) + 2 * v20 - 2), v21 != 92) && v21 != 47 )
    {
      if ( v19 )
        FusionpTraceCallExit();
      RtlPopFrame(&v42);
      v40 = 1868;
      goto LABEL_45;
    }
    if ( v19 )
      FusionpTraceCallExit();
    RtlPopFrame(&v42);
    ++v10;
  }
  if ( (unsigned int)v13 < 2 )
  {
    v12 = a2;
    v11 = v33;
    goto LABEL_34;
  }
  v22 = *(_QWORD *)(a5 + 24);
  if ( !v22 )
    goto LABEL_43;
  v23 = (unsigned __int64)(unsigned int)(v13 - 2) >> 2;
  if ( v23 >= v22 )
    goto LABEL_43;
  v24 = *(_QWORD *)(a5 + 8) + 560 * v23;
  SetLastError(0);
  v31 = *(_BYTE **)(v24 + 32);
  v32 = *(_QWORD *)(v24 + 16);
  v30 = v34;
  if ( (unsigned int)SxspExpandProbingCandidate(
                       a2,
                       &(&off_18006CAA0)[2 * (((unsigned __int8)v13 - 2) & 3)],
                       v33,
                       v35,
                       &v29,
                       (unsigned __int64 *)&v31,
                       a8,
                       &v36) )
    goto LABEL_35;
  *v41 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075730);
LABEL_38:
  v25 = v37;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v41 )
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
  return v25;
}

```

## disassembly

```asm
0x18000c820  mov     [rsp-8+arg_10], rbx
0x18000c825  push    rbp
0x18000c826  push    rsi
0x18000c827  push    rdi
0x18000c828  push    r12
0x18000c82a  push    r13
0x18000c82c  push    r14
0x18000c82e  push    r15
0x18000c830  lea     rbp, [rsp-7]
0x18000c835  sub     rsp, 0F0h
0x18000c83c  mov     rax, cs:__security_cookie
0x18000c843  xor     rax, rsp
0x18000c846  mov     [rbp+37h+var_40], rax
0x18000c84a  mov     rax, [rbp+37h+arg_30]
0x18000c84e  xor     esi, esi
0x18000c850  mov     rdi, [rbp+37h+arg_28]
0x18000c854  mov     ebx, edx
0x18000c856  mov     r14, [rbp+37h+arg_48]
0x18000c85d  mov     r13, [rbp+37h+arg_38]
0x18000c861  mov     r15, [rbp+37h+arg_40]
0x18000c868  mov     [rbp+37h+var_A8], rax
0x18000c86c  lea     rax, qword_18006C7C0
0x18000c873  mov     [rbp+37h+Frame.Context], rax
0x18000c877  lea     rax, [rbp+37h+var_9C]
0x18000c87b  mov     r12d, ecx
0x18000c87e  lea     rcx, [rbp+37h+Frame]; Frame
0x18000c882  mov     [rbp+37h+var_70], rax
0x18000c886  mov     [rsp+120h+var_D8], r9
0x18000c88b  mov     [rbp+37h+var_B0], r8
0x18000c88f  mov     [rsp+120h+var_E0], edx
0x18000c893  mov     [rsp+120h+var_B8], rdi
0x18000c898  mov     [rsp+120h+var_C8], r14
0x18000c89d  mov     [rbp+37h+var_9C], esi
0x18000c8a0  mov     [rbp+37h+Frame.Flags], 1
0x18000c8a7  mov     [rbp+37h+Frame.Previous], rsi
0x18000c8ab  mov     [rbp+37h+var_80], 20737853h
0x18000c8b3  mov     [rbp+37h+var_78], 731h
0x18000c8ba  call    cs:__imp_RtlPushFrame
0x18000c8c1  nop     dword ptr [rax+rax+00h]
0x18000c8c6  cmp     cs:g_FusionEnterExitTracingEnabled, sil
0x18000c8cd  jnz     loc_18000CC34
0x18000c8d3  mov     [rbp+37h+var_A0], esi
0x18000c8d6  mov     [r14], sil
0x18000c8d9  test    r15, r15
0x18000c8dc  jz      short loc_18000C8E1
0x18000c8de  mov     [r15], esi
0x18000c8e1  lea     rax, ?__stc@?1??Clear@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAX_N@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear(bool)'::`2'::__stc
0x18000c8e8  mov     [rbp+37h+var_68.Flags], 1
0x18000c8ef  lea     rcx, [rbp+37h+var_68]; Frame
0x18000c8f3  mov     [rbp+37h+var_68.Context], rax
0x18000c8f7  mov     [rbp+37h+var_68.Previous], rsi
0x18000c8fb  mov     [rbp+37h+var_50], 20737853h
0x18000c903  mov     [rbp+37h+var_48], 243h
0x18000c90a  call    cs:__imp_RtlPushFrame
0x18000c911  nop     dword ptr [rax+rax+00h]
0x18000c916  movzx   edx, cs:g_FusionEnterExitTracingEnabled
0x18000c91d  test    dl, dl
0x18000c91f  jnz     loc_18000CC3E
0x18000c925  mov     rcx, [r13+10h]
0x18000c929  test    rcx, rcx
0x18000c92c  jz      short loc_18000C931
0x18000c92e  mov     [rcx], si
0x18000c931  mov     [r13+20h], rsi
0x18000c935  test    dl, dl
0x18000c937  jnz     loc_18000CC86
0x18000c93d  lea     rcx, [rbp+37h+var_68]; Frame
0x18000c941  call    cs:__imp_RtlPopFrame
0x18000c948  nop     dword ptr [rax+rax+00h]
0x18000c94d  test    rdi, rdi
0x18000c950  jz      loc_18000CC90
0x18000c956  test    ebx, 0FFFFFF01h
0x18000c95c  jnz     loc_18000CC99
0x18000c962  mov     r14, [rbp+37h+arg_20]
0x18000c966  test    r14, r14
0x18000c969  jz      loc_18000CC06
0x18000c96f  lea     rax, ?__stc@?1??HasTrailingPathSeparator@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBA_NXZ@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::HasTrailingPathSeparator(void)'::`2'::__stc
0x18000c976  cmp     rsi, [r14+18h]
0x18000c97a  jnb     loc_18000CA4B
0x18000c980  mov     rbx, [r14+8]
0x18000c984  imul    rdi, rsi, 230h
0x18000c98b  cmp     qword ptr [rdi+rbx+10h], 0
0x18000c991  jz      loc_18000CC5C
0x18000c997  cmp     qword ptr [rdi+rbx+20h], 0
0x18000c99d  jbe     loc_18000CCB9
0x18000c9a3  lea     rcx, [rbp+37h+var_68]; Frame
0x18000c9a7  mov     [rbp+37h+var_68.Flags], 1
0x18000c9ae  mov     [rbp+37h+var_68.Previous], 0
0x18000c9b6  mov     [rbp+37h+var_68.Context], rax
0x18000c9ba  mov     [rbp+37h+var_50], 20737853h
0x18000c9c2  mov     [rbp+37h+var_48], 3EDh
0x18000c9c9  call    cs:__imp_RtlPushFrame
0x18000c9d0  nop     dword ptr [rax+rax+00h]
0x18000c9d5  movzx   edx, cs:g_FusionEnterExitTracingEnabled
0x18000c9dc  test    dl, dl
0x18000c9de  jnz     loc_18000CBF5
0x18000c9e4  mov     rcx, [rdi+rbx+20h]
0x18000c9e9  test    rcx, rcx
0x18000c9ec  jz      short loc_18000CA27
0x18000c9ee  mov     rax, [rdi+rbx+10h]
0x18000c9f3  movzx   r8d, word ptr [rax+rcx*2-2]
0x18000c9f9  cmp     r8w, 5Ch ; '\'
0x18000c9fe  jnz     short loc_18000CA20
0x18000ca00  test    dl, dl
0x18000ca02  jnz     loc_18000CCA5
0x18000ca08  lea     rcx, [rbp+37h+var_68]; Frame
0x18000ca0c  call    cs:__imp_RtlPopFrame
0x18000ca13  nop     dword ptr [rax+rax+00h]
0x18000ca18  inc     rsi
0x18000ca1b  jmp     loc_18000C96F
0x18000ca20  cmp     r8w, 2Fh ; '/'
0x18000ca25  jz      short loc_18000CA00
0x18000ca27  test    dl, dl
0x18000ca29  jnz     loc_18000CCAF
0x18000ca2f  lea     rcx, [rbp+37h+var_68]; Frame
0x18000ca33  call    cs:__imp_RtlPopFrame
0x18000ca3a  nop     dword ptr [rax+rax+00h]
0x18000ca3f  mov     [rbp+37h+var_78], 74Ch
0x18000ca46  jmp     loc_18000CC63
0x18000ca4b  cmp     r12d, 2
0x18000ca4f  jb      loc_18000CB1A
0x18000ca55  mov     rcx, [r14+18h]
0x18000ca59  test    rcx, rcx
0x18000ca5c  jz      loc_18000CC4F
0x18000ca62  lea     eax, [r12-2]
0x18000ca67  mov     edi, eax
0x18000ca69  shr     rax, 2
0x18000ca6d  cmp     rax, rcx
0x18000ca70  jnb     loc_18000CC4F
0x18000ca76  imul    rbx, rax, 230h
0x18000ca7d  xor     ecx, ecx; dwErrCode
0x18000ca7f  add     rbx, [r14+8]
0x18000ca83  call    cs:__imp_SetLastError
0x18000ca8a  nop     dword ptr [rax+rax+00h]
0x18000ca8f  mov     rax, [rbx+20h]
0x18000ca93  lea     rdx, off_18006CAA0; "$.$L$N.DLL"
0x18000ca9a  mov     r9, [rbp+37h+var_A8]
0x18000ca9e  and     edi, 3
0x18000caa1  mov     r8, [rsp+120h+var_B8]
0x18000caa6  mov     ecx, [rsp+120h+var_E0]
0x18000caaa  mov     [rsp+120h+var_C8], rax
0x18000caaf  mov     rax, [rbx+10h]
0x18000cab3  mov     [rsp+120h+var_C0], rax
0x18000cab8  mov     rax, [rsp+120h+var_D8]
0x18000cabd  mov     [rsp+120h+var_D8], rax
0x18000cac2  mov     rax, [rbp+37h+var_B0]
0x18000cac6  mov     [rsp+120h+var_D0], rax
0x18000cacb  lea     rax, [rbp+37h+var_A0]
0x18000cacf  mov     [rsp+120h+var_E8], rax
0x18000cad4  lea     rax, [rsp+120h+var_C8]
0x18000cad9  mov     [rsp+120h+var_F0], r13
0x18000cade  mov     [rsp+120h+var_F8], rax
0x18000cae3  lea     rax, [rsp+120h+var_D8]
0x18000cae8  shl     rdi, 4
0x18000caec  add     rdx, rdi
0x18000caef  mov     [rsp+120h+var_100], rax
0x18000caf4  call    ?SxspExpandProbingCandidate@@YAHKAEBUSXSP_PROBING_CANDIDATE@@PEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEBVStringAndCch@@3AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEAH@Z; SxspExpandProbingCandidate(ulong,SXSP_PROBING_CANDIDATE const &,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,StringAndCch const &,StringAndCch const &,CGenericBaseStringBuffer<CUnicodeCharTraits> &,int *)
0x18000caf9  test    eax, eax
0x18000cafb  jnz     loc_18000CB99
0x18000cb01  mov     rax, [rbp+37h+var_70]
0x18000cb05  lea     rcx, off_180075730; struct _CALL_SITE_INFO *
0x18000cb0c  xor     esi, esi
0x18000cb0e  mov     [rax], esi
0x18000cb10  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18000cb15  jmp     loc_18000CBAB
0x18000cb1a  mov     ebx, [rsp+120h+var_E0]
0x18000cb1e  xor     esi, esi
0x18000cb20  mov     rdi, [rsp+120h+var_B8]
0x18000cb25  xor     ecx, ecx; dwErrCode
0x18000cb27  call    cs:__imp_SetLastError
0x18000cb2e  nop     dword ptr [rax+rax+00h]
0x18000cb33  mov     rax, [rsp+120h+var_D8]
0x18000cb38  mov     rdx, r12
0x18000cb3b  mov     r9, [rbp+37h+var_A8]
0x18000cb3f  mov     r8, rdi
0x18000cb42  mov     [rsp+120h+var_D8], rax
0x18000cb47  mov     ecx, ebx
0x18000cb49  mov     rax, [rbp+37h+var_B0]
0x18000cb4d  mov     [rsp+120h+var_D0], rax
0x18000cb52  lea     rax, off_18006CA60; "$M"
0x18000cb59  shl     rdx, 4
0x18000cb5d  add     rdx, rax
0x18000cb60  mov     [rsp+120h+var_C8], rsi
0x18000cb65  lea     rax, [rbp+37h+var_A0]
0x18000cb69  mov     [rsp+120h+var_C0], rsi
0x18000cb6e  mov     [rsp+120h+var_E8], rax
0x18000cb73  lea     rax, [rsp+120h+var_C8]
0x18000cb78  mov     [rsp+120h+var_F0], r13
0x18000cb7d  mov     [rsp+120h+var_F8], rax
0x18000cb82  lea     rax, [rsp+120h+var_D8]
0x18000cb87  mov     [rsp+120h+var_100], rax
0x18000cb8c  call    ?SxspExpandProbingCandidate@@YAHKAEBUSXSP_PROBING_CANDIDATE@@PEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEBVStringAndCch@@3AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEAH@Z; SxspExpandProbingCandidate(ulong,SXSP_PROBING_CANDIDATE const &,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,StringAndCch const &,StringAndCch const &,CGenericBaseStringBuffer<CUnicodeCharTraits> &,int *)
0x18000cb91  test    eax, eax
0x18000cb93  jz      loc_18000CCC2
0x18000cb99  test    r15, r15
0x18000cb9c  jz      short loc_18000CBA4
0x18000cb9e  mov     eax, [rbp+37h+var_A0]
0x18000cba1  mov     [r15], eax
0x18000cba4  mov     [rbp+37h+var_9C], 1
0x18000cbab  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18000cbb2  mov     ebx, [rbp+37h+var_9C]
0x18000cbb5  jnz     loc_18000CCD9
0x18000cbbb  lea     rcx, [rbp+37h+Frame]; Frame
0x18000cbbf  call    cs:__imp_RtlPopFrame
0x18000cbc6  nop     dword ptr [rax+rax+00h]
0x18000cbcb  mov     eax, ebx
0x18000cbcd  mov     rcx, [rbp+37h+var_40]
0x18000cbd1  xor     rcx, rsp; StackCookie
0x18000cbd4  call    __security_check_cookie
0x18000cbd9  mov     rbx, [rsp+120h+arg_10]
0x18000cbe1  add     rsp, 0F0h
0x18000cbe8  pop     r15
0x18000cbea  pop     r14
0x18000cbec  pop     r13
0x18000cbee  pop     r12
0x18000cbf0  pop     rdi
0x18000cbf1  pop     rsi
0x18000cbf2  pop     rbp
0x18000cbf3  retn
0x18000cbf5  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18000cbfa  movzx   edx, cs:g_FusionEnterExitTracingEnabled
0x18000cc01  jmp     loc_18000C9E4
0x18000cc06  cmp     r12d, 2
0x18000cc0a  jb      loc_18000CB25
0x18000cc10  test    bl, 4
0x18000cc13  jnz     short loc_18000CC4F
0x18000cc15  mov     [rbp+37h+var_78], 753h
0x18000cc1c  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18000cc21  mov     ecx, 57h ; 'W'; dwErrCode
0x18000cc26  call    cs:__imp_SetLastError
0x18000cc2d  nop     dword ptr [rax+rax+00h]
0x18000cc32  jmp     short loc_18000CC7B
0x18000cc34  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18000cc39  jmp     loc_18000C8D3
0x18000cc3e  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18000cc43  movzx   edx, cs:g_FusionEnterExitTracingEnabled
0x18000cc4a  jmp     loc_18000C925
0x18000cc4f  mov     rax, [rsp+120h+var_C8]
0x18000cc54  mov     byte ptr [rax], 1
0x18000cc57  jmp     loc_18000CB99
0x18000cc5c  mov     [rbp+37h+var_78], 74Ah
0x18000cc63  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18000cc68  mov     ecx, 57h ; 'W'; dwErrCode
0x18000cc6d  call    cs:__imp_SetLastError
0x18000cc74  nop     dword ptr [rax+rax+00h]
0x18000cc79  xor     esi, esi
0x18000cc7b  mov     rax, [rbp+37h+var_70]
0x18000cc7f  mov     [rax], esi
0x18000cc81  jmp     loc_18000CBAB
0x18000cc86  call    ?FusionpTraceCallExit@@YAXXZ; FusionpTraceCallExit(void)
0x18000cc8b  jmp     loc_18000C93D
0x18000cc90  mov     [rbp+37h+var_78], 73Bh
0x18000cc97  jmp     short loc_18000CC1C
0x18000cc99  mov     [rbp+37h+var_78], 742h
0x18000cca0  jmp     loc_18000CC1C
0x18000cca5  call    ?FusionpTraceCallExit@@YAXXZ; FusionpTraceCallExit(void)
0x18000ccaa  jmp     loc_18000CA08
0x18000ccaf  call    ?FusionpTraceCallExit@@YAXXZ; FusionpTraceCallExit(void)
0x18000ccb4  jmp     loc_18000CA2F
0x18000ccb9  mov     [rbp+37h+var_78], 74Bh
0x18000ccc0  jmp     short loc_18000CC63
0x18000ccc2  mov     rax, [rbp+37h+var_70]
0x18000ccc6  lea     rcx, off_180075750; struct _CALL_SITE_INFO *
0x18000cccd  mov     [rax], esi
0x18000cccf  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18000ccd4  jmp     loc_18000CBAB
0x18000ccd9  mov     rax, [rbp+37h+var_70]
0x18000ccdd  cmp     dword ptr [rax], 0
0x18000cce0  jz      short loc_18000CCEE
0x18000cce2  xor     ecx, ecx; char *
0x18000cce4  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18000cce9  jmp     loc_18000CBBB
0x18000ccee  call    cs:__imp_GetLastError
0x18000ccf5  nop     dword ptr [rax+rax+00h]
0x18000ccfa  mov     ecx, eax; unsigned int
0x18000ccfc  xor     edx, edx; Format
0x18000ccfe  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18000cd03  jmp     loc_18000CBBB
```
