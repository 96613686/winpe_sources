# SxspCreateAssemblyIdentityFromIdentityElement(ulong,_ACTCTXCTB_PARSE_CONTEXT const *,ulong,_ASSEMBLY_IDENTITY * *,ulong,_SXS_NODE_INFO const *)

- ea: `0x180041f10`
- end: `0x1800426e7`
- name: `?SxspCreateAssemblyIdentityFromIdentityElement@@YAHKPEBU_ACTCTXCTB_PARSE_CONTEXT@@KPEAPEAU_ASSEMBLY_IDENTITY@@KPEBU_SXS_NODE_INFO@@@Z`
- size: `2007`
- prototype: `__int64 __fastcall(unsigned int, const struct _ACTCTXCTB_PARSE_CONTEXT *, unsigned int, struct _ASSEMBLY_IDENTITY **, unsigned int, const struct _SXS_NODE_INFO *)`
- caller_count: `4`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180040a30`
- `0x1800434a0`
- `0x180065520`
- `0x180065700`

## callees

- `0x1800075a0`
- `0x18000df40`
- `0x18000dffc`
- `0x180019cc0`
- `0x18001c2c8`
- `0x18001e5c0`
- `0x180022d40`
- `0x180041f10`
- `0x180042868`
- `0x18005b8a0`
- `0x18005cf40`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a0dd`
- `0x18006a0f5`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180042433`
- `ntdll!RtlCompareUnicodeString` at `0x18004248d`
- `ntdll!RtlCompareUnicodeString` at `0x1800424e7`
- `ntdll!RtlCompareUnicodeString` at `0x180042545`
- `ntdll!RtlCompareUnicodeString` at `0x1800425a4`
- `ntdll!RtlCompareUnicodeString` at `0x180042433`
- `ntdll!RtlCompareUnicodeString` at `0x18004248d`
- `ntdll!RtlCompareUnicodeString` at `0x1800424e7`
- `ntdll!RtlCompareUnicodeString` at `0x180042545`
- `ntdll!RtlCompareUnicodeString` at `0x1800425a4`
- `ntdll!RtlPopFrame` at `0x180042108`
- `ntdll!RtlPopFrame` at `0x1800422fd`
- `ntdll!RtlPopFrame` at `0x180042108`
- `ntdll!RtlPopFrame` at `0x1800422fd`
- `ntdll!RtlPushFrame` at `0x1800420ca`
- `ntdll!RtlPushFrame` at `0x1800420ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800426cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800426cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042055`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042182`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800421c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800425ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042675`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042055`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042182`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800421c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800425ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042675`

## pseudocode

```c
__int64 __fastcall SxspCreateAssemblyIdentityFromIdentityElement(
        __int64 a1,
        const struct _ACTCTXCTB_PARSE_CONTEXT *a2,
        unsigned int a3,
        struct _ASSEMBLY_IDENTITY **a4,
        unsigned int a5,
        const struct _SXS_NODE_INFO *a6)
{
  const struct _SXS_NODE_INFO *v7; // r15
  const char *v9; // rcx
  __int64 v10; // rcx
  __int64 i; // rbx
  char *v12; // rsi
  char v13; // dl
  __int64 v14; // rdi
  unsigned __int64 v15; // r13
  unsigned __int64 v16; // r12
  const void *v17; // r9
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r15
  unsigned __int64 v21; // rdx
  _WORD *v22; // r15
  unsigned int v23; // ebx
  unsigned __int64 v25; // rdi
  size_t v26; // rdi
  void *v27; // rax
  DWORD LastError; // eax
  LPVOID lpMem; // [rsp+38h] [rbp-D0h] BYREF
  char *v30; // [rsp+40h] [rbp-C8h]
  const void *v31; // [rsp+48h] [rbp-C0h]
  const struct _SXS_NODE_INFO *v32; // [rsp+50h] [rbp-B8h]
  struct _ASSEMBLY_IDENTITY **v33; // [rsp+58h] [rbp-B0h]
  void *v34; // [rsp+60h] [rbp-A8h] BYREF
  UNICODE_STRING String2; // [rsp+68h] [rbp-A0h] BYREF
  UNICODE_STRING String1; // [rsp+78h] [rbp-90h] BYREF
  UNICODE_STRING v37; // [rsp+88h] [rbp-80h] BYREF
  UNICODE_STRING v38; // [rsp+98h] [rbp-70h] BYREF
  UNICODE_STRING v39; // [rsp+A8h] [rbp-60h] BYREF
  UNICODE_STRING v40; // [rsp+B8h] [rbp-50h] BYREF
  UNICODE_STRING v41; // [rsp+C8h] [rbp-40h] BYREF
  UNICODE_STRING v42; // [rsp+D8h] [rbp-30h] BYREF
  UNICODE_STRING v43; // [rsp+E8h] [rbp-20h] BYREF
  UNICODE_STRING v44; // [rsp+F8h] [rbp-10h] BYREF
  int v45; // [rsp+108h] [rbp+0h] BYREF
  struct _TEB_ACTIVE_FRAME v46; // [rsp+110h] [rbp+8h] BYREF
  __int64 v47; // [rsp+128h] [rbp+20h]
  int v48; // [rsp+130h] [rbp+28h]
  int *v49; // [rsp+138h] [rbp+30h]
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+140h] [rbp+38h] BYREF
  __int64 v51; // [rsp+158h] [rbp+50h]
  __int64 v52; // [rsp+160h] [rbp+58h]
  __int64 v53; // [rsp+168h] [rbp+60h]
  void *v54; // [rsp+170h] [rbp+68h]
  void **v55; // [rsp+178h] [rbp+70h] BYREF
  int v56; // [rsp+180h] [rbp+78h]
  void *Src; // [rsp+188h] [rbp+80h]
  unsigned __int64 v58; // [rsp+190h] [rbp+88h]
  unsigned __int64 v59; // [rsp+198h] [rbp+90h]
  __int16 v60; // [rsp+1A0h] [rbp+98h] BYREF

  v7 = a6;
  v46.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180070FD0;
  v32 = a6;
  v33 = a4;
  v45 = 0;
  v46.Flags = 1;
  v46.Previous = 0;
  v47 = 544438355;
  v48 = 911;
  v49 = &v45;
  CFrame::BaseEnter((CFrame *)&v46);
  lpMem = 0;
  v55 = &CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable';
  v56 = 0;
  Src = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  Src = (void *)CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(&v55);
  v58 = ((__int64 (__fastcall *)(void ***))v55[3])(&v55);
  if ( (unsigned int)Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline() )
    memset_0(Src, 0, 2 * v58);
  if ( a4 )
    *a4 = 0;
  if ( a3 - 1 > 1 )
  {
    v48 = 926;
    goto LABEL_66;
  }
  if ( !a4 )
  {
    v48 = 927;
    goto LABEL_66;
  }
  if ( !a6 )
  {
    v48 = 928;
LABEL_66:
    FusionpTraceParameterCheck(v9);
    SetLastError(0x57u);
    *v49 = 0;
    goto LABEL_36;
  }
  if ( *((_DWORD *)a6 + 1) != 1 )
  {
    v48 = 929;
    goto LABEL_66;
  }
  SetLastError(0);
  if ( (unsigned int)SxsCreateAssemblyIdentity(v10, a3, &lpMem) )
  {
    LODWORD(i) = 1;
    while ( 1 )
    {
      if ( (unsigned int)i >= a5 )
      {
        v45 = 1;
        *v33 = (struct _ASSEMBLY_IDENTITY *)lpMem;
        goto LABEL_36;
      }
      v12 = (char *)v7 + 192 * (unsigned int)i;
      if ( *((_DWORD *)v12 + 1) != 2 )
        break;
      Frame.Flags = 1;
      Frame.Previous = 0;
      Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear'::`2'::__stc;
      v51 = 544438355;
      LODWORD(v52) = 579;
      RtlPushFrame(&Frame);
      v13 = g_FusionEnterExitTracingEnabled;
      if ( g_FusionEnterExitTracingEnabled )
      {
        FusionpTraceCallEntry();
        v13 = g_FusionEnterExitTracingEnabled;
      }
      if ( Src )
        *(_WORD *)Src = 0;
      v59 = 0;
      if ( v13 )
        FusionpTraceCallExit();
      RtlPopFrame(&Frame);
      for ( i = (unsigned int)(i + 1); (unsigned int)i < a5; i = (unsigned int)(i + 1) )
      {
        v14 = 192 * i;
        if ( *((_DWORD *)v7 + 48 * i + 1) != 13 )
          break;
        SetLastError(0);
        v15 = *(_QWORD *)((char *)v7 + v14 + 184);
        v16 = v15 + 1;
        if ( v15 + 1 > 1 )
        {
          v17 = *(const void **)((char *)v7 + v14 + 176);
          v18 = v59;
          v19 = v58;
          v31 = v17;
          v20 = v59 + v16;
          if ( v59 + v16 > v58 )
          {
            v34 = 0;
            if ( !((unsigned int (__fastcall *)(void ***, unsigned __int64, void **))*v55)(&v55, v59 + v16, &v34) )
            {
              *v49 = 0;
              FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180079668);
              goto LABEL_75;
            }
            if ( v20 )
            {
              v30 = (char *)v34;
              if ( Src )
              {
                v25 = v59;
                if ( v59 >= v20 )
                  v25 = v20 - 1;
                v26 = 2 * v25;
                memcpy_0(v34, Src, v26);
                *(_WORD *)&v30[v26] = 0;
              }
              else
              {
                *(_WORD *)v34 = 0;
              }
            }
            if ( Src )
            {
              v27 = (void *)((__int64 (__fastcall *)(void ***))v55[2])(&v55);
              if ( Src != v27 )
                ((void (__fastcall *)(void ***))v55[1])(&v55);
            }
            v19 = v20;
            v18 = v59;
            v17 = v31;
            Src = v34;
            v58 = v20;
          }
          v21 = v19 - v18;
          if ( v21 )
          {
            v22 = (char *)Src + 2 * v18;
            if ( v17 )
            {
              if ( v15 >= v21 )
                v15 = v21 - 1;
              memcpy_0((char *)Src + 2 * v18, v17, 2 * v15);
              v22[v15] = 0;
            }
            else
            {
              *v22 = 0;
            }
            v18 = v59;
          }
          v7 = v32;
          v59 = v16 + v18 - 1;
        }
      }
      if ( *((_QWORD *)v12 + 5) )
        goto LABEL_82;
      if ( *((_QWORD *)v12 + 23) == 9 )
      {
        *(_QWORD *)&String1.Length = 1179666;
        String1.Buffer = L"publicKey";
        String2.Buffer = (PWSTR)*((_QWORD *)v12 + 22);
        *(_QWORD *)&String2.Length = 1179666;
        if ( !RtlCompareUnicodeString(&String1, &String2, 0) )
          continue;
      }
      if ( *((_QWORD *)v12 + 5) )
        goto LABEL_82;
      if ( *((_QWORD *)v12 + 23) == 9 )
      {
        *(_QWORD *)&v38.Length = 1179666;
        v38.Buffer = L"buildType";
        v37.Buffer = (PWSTR)*((_QWORD *)v12 + 22);
        *(_QWORD *)&v37.Length = 1179666;
        if ( !RtlCompareUnicodeString(&v38, &v37, 0) )
          continue;
      }
      if ( *((_QWORD *)v12 + 5) )
        goto LABEL_82;
      if ( *((_QWORD *)v12 + 23) == 12 )
      {
        *(_QWORD *)&v40.Length = 1572888;
        v40.Buffer = L"versionScope";
        v39.Buffer = (PWSTR)*((_QWORD *)v12 + 22);
        *(_QWORD *)&v39.Length = 1572888;
        if ( !RtlCompareUnicodeString(&v40, &v39, 0) )
          continue;
      }
      if ( *((_QWORD *)v12 + 5) )
        goto LABEL_82;
      if ( *((_QWORD *)v12 + 23) != 8 )
        goto LABEL_82;
      *(_QWORD *)&v42.Length = 1048592;
      v42.Buffer = L"language";
      v41.Buffer = (PWSTR)*((_QWORD *)v12 + 22);
      *(_QWORD *)&v41.Length = 1048592;
      if ( !RtlCompareUnicodeString(&v42, &v41, 0) )
      {
        if ( !v59 )
          continue;
        if ( v59 == 7 )
        {
          *(_QWORD *)&v44.Length = 917518;
          v44.Buffer = L"neutral";
          v43.Buffer = (PWSTR)Src;
          *(_QWORD *)&v43.Length = 917518;
          if ( !RtlCompareUnicodeString(&v44, &v43, 1u) )
            continue;
        }
      }
LABEL_82:
      Frame.Previous = (struct _TEB_ACTIVE_FRAME *)*((_QWORD *)v12 + 5);
      v52 = *((_QWORD *)v12 + 3);
      Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)*((_QWORD *)v12 + 23);
      v53 = *((_QWORD *)v12 + 22);
      v51 = v59;
      v54 = Src;
      *(_QWORD *)&Frame.Flags = 0;
      SetLastError(0);
      if ( !(unsigned int)SxsInsertAssemblyIdentityAttribute(0, lpMem, &Frame) )
      {
        *v49 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180079648);
        goto LABEL_75;
      }
    }
    SetLastError(0x54Fu);
    *v49 = 0;
  }
  else
  {
    *v49 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180079688);
  }
LABEL_75:
  if ( lpMem )
    SxsDestroyAssemblyIdentity(lpMem);
LABEL_36:
  v23 = v45;
  v55 = &CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable';
  if ( Src != &v60 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v55);
  Src = 0;
  v58 = 0;
  v55 = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v49 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&v46);
  return v23;
}

```

## disassembly

```asm
0x180041f10  mov     r11, rsp
0x180041f13  push    rbp
0x180041f14  push    rbx
0x180041f15  lea     rbp, [r11-2E8h]
0x180041f1c  sub     rsp, 3D8h
0x180041f23  mov     rax, cs:__security_cookie
0x180041f2a  xor     rax, rsp
0x180041f2d  mov     [rbp+2E0h+var_40], rax
0x180041f34  mov     [r11+8], rsi
0x180041f38  lea     rax, qword_180070FD0
0x180041f3f  mov     [r11-18h], rdi
0x180041f43  lea     rcx, [rbp+2E0h+var_2D8]; this
0x180041f47  mov     [r11-20h], r12
0x180041f4b  mov     rdi, r9
0x180041f4e  mov     [r11-38h], r15
0x180041f52  xor     r12d, r12d
0x180041f55  mov     r15, [rbp+2E0h+arg_28]
0x180041f5c  mov     ebx, r8d
0x180041f5f  mov     [rbp+2E0h+var_2D8.Context], rax
0x180041f63  lea     rax, [rbp+2E0h+var_2E0]
0x180041f67  mov     [rsp+3E0h+var_398], r15
0x180041f6c  mov     [rsp+3E0h+var_390], r9
0x180041f71  mov     [rbp+2E0h+var_2E0], r12d
0x180041f75  mov     [rbp+2E0h+var_2D8.Flags], 1
0x180041f7c  mov     [rbp+2E0h+var_2D8.Previous], r12
0x180041f80  mov     [rbp+2E0h+var_2C0], 20737853h
0x180041f88  mov     [rbp+2E0h+var_2B8], 38Fh
0x180041f8f  mov     [rbp+2E0h+var_2B0], rax
0x180041f93  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180041f98  lea     rsi, ??_7?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable'
0x180041f9f  mov     [rsp+3E0h+lpMem], r12
0x180041fa4  lea     rcx, [rbp+2E0h+var_270]
0x180041fa8  mov     [rbp+2E0h+var_270], rsi
0x180041fac  mov     [rbp+2E0h+var_268], r12d
0x180041fb0  mov     [rbp+2E0h+Src], r12
0x180041fb7  mov     [rbp+2E0h+var_258], r12
0x180041fbe  mov     [rbp+2E0h+var_250], r12
0x180041fc5  mov     [rbp+2E0h+var_248], r12w
0x180041fcd  call    ?GetInlineBuffer@?$CGenericStringBuffer@$00VCUnicodeCharTraits@@@@MEBAPEAGXZ; CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(void)
0x180041fd2  mov     [rbp+2E0h+Src], rax
0x180041fd9  lea     rcx, [rbp+2E0h+var_270]
0x180041fdd  mov     rax, [rbp+2E0h+var_270]
0x180041fe1  mov     rax, [rax+18h]
0x180041fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fea  mov     [rbp+2E0h+var_258], rax
0x180041ff1  call    Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline
0x180041ff6  test    eax, eax
0x180041ff8  jz      short loc_180042012
0x180041ffa  mov     r8, [rbp+2E0h+var_258]
0x180042001  xor     edx, edx; Val
0x180042003  mov     rcx, [rbp+2E0h+Src]; void *
0x18004200a  add     r8, r8; Size
0x18004200d  call    memset_0
0x180042012  test    rdi, rdi
0x180042015  jz      short loc_18004201A
0x180042017  mov     [rdi], r12
0x18004201a  lea     eax, [rbx-1]
0x18004201d  cmp     eax, 1
0x180042020  ja      loc_180042615
0x180042026  test    rdi, rdi
0x180042029  jz      loc_18004261E
0x18004202f  test    r15, r15
0x180042032  jz      loc_1800425BD
0x180042038  cmp     dword ptr [r15+4], 1
0x18004203d  jnz     loc_18004260C
0x180042043  mov     [rsp+3E0h+var_20], r13
0x18004204b  xor     ecx, ecx; dwErrCode
0x18004204d  mov     [rsp+3E0h+var_28], r14
0x180042055  call    cs:__imp_SetLastError
0x18004205c  nop     dword ptr [rax+rax+00h]
0x180042061  lea     r8, [rsp+3E0h+lpMem]
0x180042066  mov     edx, ebx
0x180042068  call    SxsCreateAssemblyIdentity
0x18004206d  test    eax, eax
0x18004206f  jz      loc_180042627
0x180042075  mov     r14d, [rbp+2E0h+arg_20]
0x18004207c  mov     ebx, 1
0x180042081  lea     rdx, ?__stc@?1??Clear@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAX_N@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear(bool)'::`2'::__stc
0x180042088  cmp     ebx, r14d
0x18004208b  jnb     loc_18004226A
0x180042091  mov     eax, ebx
0x180042093  lea     rsi, [rax+rax*2]
0x180042097  shl     rsi, 6
0x18004209b  add     rsi, r15
0x18004209e  cmp     dword ptr [rsi+4], 2
0x1800420a2  jnz     loc_180042670
0x1800420a8  lea     rcx, [rbp+2E0h+Frame]; Frame
0x1800420ac  mov     [rbp+2E0h+Frame.Flags], 1
0x1800420b3  mov     [rbp+2E0h+Frame.Previous], r12
0x1800420b7  mov     [rbp+2E0h+Frame.Context], rdx
0x1800420bb  mov     [rbp+2E0h+var_290], 20737853h
0x1800420c3  mov     dword ptr [rbp+2E0h+var_288], 243h
0x1800420ca  call    cs:__imp_RtlPushFrame
0x1800420d1  nop     dword ptr [rax+rax+00h]
0x1800420d6  movzx   edx, cs:g_FusionEnterExitTracingEnabled
0x1800420dd  test    dl, dl
0x1800420df  jnz     loc_1800425E6
0x1800420e5  mov     rcx, [rbp+2E0h+Src]
0x1800420ec  test    rcx, rcx
0x1800420ef  jz      short loc_1800420F5
0x1800420f1  mov     [rcx], r12w
0x1800420f5  mov     [rbp+2E0h+var_250], r12
0x1800420fc  test    dl, dl
0x1800420fe  jnz     loc_18004263C
0x180042104  lea     rcx, [rbp+2E0h+Frame]; Frame
0x180042108  call    cs:__imp_RtlPopFrame
0x18004210f  nop     dword ptr [rax+rax+00h]
0x180042114  inc     ebx
0x180042116  cmp     ebx, r14d
0x180042119  jnb     short loc_18004212F
0x18004211b  lea     rdi, [rbx+rbx*2]
0x18004211f  shl     rdi, 6
0x180042123  cmp     dword ptr [rdi+r15+4], 0Dh
0x180042129  jz      loc_1800421BE
0x18004212f  xor     r12d, r12d
0x180042132  cmp     [rsi+28h], r12
0x180042136  jz      loc_1800423F2
0x18004213c  mov     rax, [rsi+28h]
0x180042140  xor     ecx, ecx; dwErrCode
0x180042142  mov     [rbp+2E0h+Frame.Previous], rax
0x180042146  mov     rax, [rsi+18h]
0x18004214a  mov     [rbp+2E0h+var_288], rax
0x18004214e  mov     rax, [rsi+0B8h]
0x180042155  mov     [rbp+2E0h+Frame.Context], rax
0x180042159  mov     rax, [rsi+0B0h]
0x180042160  mov     [rbp+2E0h+var_280], rax
0x180042164  mov     rax, [rbp+2E0h+var_250]
0x18004216b  mov     [rbp+2E0h+var_290], rax
0x18004216f  mov     rax, [rbp+2E0h+Src]
0x180042176  mov     [rbp+2E0h+var_278], rax
0x18004217a  mov     qword ptr [rbp+2E0h+Frame.Flags], 0
0x180042182  call    cs:__imp_SetLastError
0x180042189  nop     dword ptr [rax+rax+00h]
0x18004218e  mov     rdx, [rsp+3E0h+lpMem]
0x180042193  lea     r8, [rbp+2E0h+Frame]
0x180042197  xor     ecx, ecx
0x180042199  call    SxsInsertAssemblyIdentityAttribute
0x18004219e  test    eax, eax
0x1800421a0  jnz     loc_180042081
0x1800421a6  mov     rax, [rbp+2E0h+var_2B0]
0x1800421aa  lea     rcx, off_180079648; struct _CALL_SITE_INFO *
0x1800421b1  mov     [rax], r12d
0x1800421b4  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800421b9  jmp     loc_180042688
0x1800421be  xor     ecx, ecx; dwErrCode
0x1800421c0  call    cs:__imp_SetLastError
0x1800421c7  nop     dword ptr [rax+rax+00h]
0x1800421cc  mov     r13, [rdi+r15+0B8h]
0x1800421d4  lea     r12, [r13+1]
0x1800421d8  cmp     r12, 1
0x1800421dc  jbe     loc_180042263
0x1800421e2  mov     r9, [rdi+r15+0B0h]
0x1800421ea  mov     rcx, [rbp+2E0h+var_250]
0x1800421f1  mov     rdx, [rbp+2E0h+var_258]
0x1800421f8  mov     [rsp+3E0h+var_3A0], r9
0x1800421fd  lea     r15, [rcx+r12]
0x180042201  cmp     r15, rdx
0x180042204  ja      loc_180042325
0x18004220a  sub     rdx, rcx
0x18004220d  jz      short loc_180042250
0x18004220f  mov     rax, [rbp+2E0h+Src]
0x180042216  lea     r15, [rax+rcx*2]
0x18004221a  test    r9, r9
0x18004221d  jz      loc_1800425F7
0x180042223  cmp     r13, rdx
0x180042226  jnb     loc_18004264F
0x18004222c  lea     rdi, ds:0[r13*2]
0x180042234  mov     rdx, r9; Src
0x180042237  mov     r8, rdi; Size
0x18004223a  mov     rcx, r15; void *
0x18004223d  call    memcpy_0
0x180042242  xor     eax, eax
0x180042244  mov     [rdi+r15], ax
0x180042249  mov     rcx, [rbp+2E0h+var_250]
0x180042250  mov     r15, [rsp+3E0h+var_398]
0x180042255  lea     rax, [rcx-1]
0x180042259  add     rax, r12
0x18004225c  mov     [rbp+2E0h+var_250], rax
0x180042263  inc     ebx
0x180042265  jmp     loc_180042116
0x18004226a  mov     rax, [rsp+3E0h+var_390]
0x18004226f  lea     rsi, ??_7?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable'
0x180042276  mov     rcx, [rsp+3E0h+lpMem]
0x18004227b  mov     [rbp+2E0h+var_2E0], 1
0x180042282  mov     [rax], rcx
0x180042285  mov     r13, [rsp+3E0h+var_20]
0x18004228d  mov     r14, [rsp+3E0h+var_28]
0x180042295  mov     rdx, [rbp+2E0h+Src]
0x18004229c  lea     rax, [rbp+2E0h+var_248]
0x1800422a3  mov     ebx, [rbp+2E0h+var_2E0]
0x1800422a6  mov     r15, [rsp+3E0h+var_30]
0x1800422ae  mov     rdi, [rsp+3D0h]
0x1800422b6  mov     [rbp+2E0h+var_270], rsi
0x1800422ba  mov     rsi, [rsp+3E0h+arg_0]
0x1800422c2  cmp     rdx, rax
0x1800422c5  jnz     loc_1800426AA
0x1800422cb  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x1800422d2  lea     rax, ??_7?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@6B@; const CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable'
0x1800422d9  mov     [rbp+2E0h+Src], r12
0x1800422e0  mov     [rbp+2E0h+var_258], r12
0x1800422e7  mov     r12, [rsp+3E0h+var_18]
0x1800422ef  mov     [rbp+2E0h+var_270], rax
0x1800422f3  jnz     loc_1800426B8
0x1800422f9  lea     rcx, [rbp+2E0h+var_2D8]; Frame
0x1800422fd  call    cs:__imp_RtlPopFrame
0x180042304  nop     dword ptr [rax+rax+00h]
0x180042309  mov     eax, ebx
0x18004230b  mov     rcx, [rbp+2E0h+var_40]
0x180042312  xor     rcx, rsp; StackCookie
0x180042315  call    __security_check_cookie
0x18004231a  add     rsp, 3D8h
0x180042321  pop     rbx
0x180042322  pop     rbp
0x180042323  retn
0x180042325  mov     rax, [rbp+2E0h+var_270]
0x180042329  lea     r8, [rsp+3E0h+var_388]
0x18004232e  mov     rdx, r15
0x180042331  mov     [rsp+3E0h+var_388], 0
0x18004233a  lea     rcx, [rbp+2E0h+var_270]
0x18004233e  mov     rax, [rax]
0x180042341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042346  test    eax, eax
0x180042348  jz      loc_180042658
0x18004234e  test    r15, r15
0x180042351  jz      short loc_180042393
0x180042353  mov     rdx, [rbp+2E0h+Src]; Src
0x18004235a  mov     rcx, [rsp+3E0h+var_388]; void *
0x18004235f  mov     [rsp+3E0h+var_3A8], rcx
0x180042364  test    rdx, rdx
0x180042367  jz      loc_180042602
0x18004236d  mov     rdi, [rbp+2E0h+var_250]
0x180042374  cmp     rdi, r15
0x180042377  jnb     loc_180042646
0x18004237d  add     rdi, rdi
0x180042380  mov     r8, rdi; Size
0x180042383  call    memcpy_0
0x180042388  mov     rcx, [rsp+3E0h+var_3A8]
0x18004238d  xor     eax, eax
0x18004238f  mov     [rcx+rdi], ax
0x180042393  cmp     [rbp+2E0h+Src], 0
0x18004239b  jz      short loc_1800423CB
0x18004239d  mov     rax, [rbp+2E0h+var_270]
0x1800423a1  lea     rcx, [rbp+2E0h+var_270]
0x1800423a5  mov     rax, [rax+10h]
0x1800423a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423ae  mov     rdx, [rbp+2E0h+Src]
0x1800423b5  cmp     rdx, rax
0x1800423b8  jz      short loc_1800423CB
0x1800423ba  mov     rax, [rbp+2E0h+var_270]
0x1800423be  lea     rcx, [rbp+2E0h+var_270]
0x1800423c2  mov     rax, [rax+8]
0x1800423c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423cb  mov     rax, [rsp+3E0h+var_388]
0x1800423d0  mov     rdx, r15
0x1800423d3  mov     rcx, [rbp+2E0h+var_250]
0x1800423da  mov     r9, [rsp+3E0h+var_3A0]
0x1800423df  mov     [rbp+2E0h+Src], rax
0x1800423e6  mov     [rbp+2E0h+var_258], rdx
0x1800423ed  jmp     loc_18004220A
0x1800423f2  cmp     qword ptr [rsi+0B8h], 9
0x1800423fa  jnz     short loc_180042447
0x1800423fc  lea     rax, aPublickey; "publicKey"
0x180042403  mov     qword ptr [rsp+3E0h+String1.Length], 120012h
0x18004240c  mov     [rsp+3E0h+String1.Buffer], rax
0x180042411  lea     rdx, [rsp+3E0h+String2]; String2
0x180042416  mov     rax, [rsi+0B0h]
0x18004241d  lea     rcx, [rsp+3E0h+String1]; String1
0x180042422  xor     r8d, r8d; CaseInsensitive
0x180042425  mov     [rsp+3E0h+String2.Buffer], rax
0x18004242a  mov     qword ptr [rsp+3E0h+String2.Length], 120012h
0x180042433  call    cs:__imp_RtlCompareUnicodeString
0x18004243a  nop     dword ptr [rax+rax+00h]
0x18004243f  test    eax, eax
0x180042441  jz      loc_180042081
0x180042447  cmp     qword ptr [rsi+28h], 0
0x18004244c  jnz     loc_18004213C
0x180042452  cmp     qword ptr [rsi+0B8h], 9
0x18004245a  jnz     short loc_1800424A1
0x18004245c  lea     rax, aBuildtype; "buildType"
0x180042463  mov     qword ptr [rbp+2E0h+var_350.Length], 120012h
0x18004246b  mov     [rbp+2E0h+var_350.Buffer], rax
0x18004246f  lea     rdx, [rbp+2E0h+var_360]; String2
0x180042473  mov     rax, [rsi+0B0h]
0x18004247a  lea     rcx, [rbp+2E0h+var_350]; String1
0x18004247e  xor     r8d, r8d; CaseInsensitive
0x180042481  mov     [rbp+2E0h+var_360.Buffer], rax
0x180042485  mov     qword ptr [rbp+2E0h+var_360.Length], 120012h
0x18004248d  call    cs:__imp_RtlCompareUnicodeString
0x180042494  nop     dword ptr [rax+rax+00h]
0x180042499  test    eax, eax
0x18004249b  jz      loc_180042081
0x1800424a1  cmp     qword ptr [rsi+28h], 0
0x1800424a6  jnz     loc_18004213C
0x1800424ac  cmp     qword ptr [rsi+0B8h], 0Ch
0x1800424b4  jnz     short loc_1800424FB
0x1800424b6  lea     rax, aVersionscope; "versionScope"
0x1800424bd  mov     qword ptr [rbp+2E0h+var_330.Length], 180018h
0x1800424c5  mov     [rbp+2E0h+var_330.Buffer], rax
0x1800424c9  lea     rdx, [rbp+2E0h+var_340]; String2
0x1800424cd  mov     rax, [rsi+0B0h]
  ... truncated ...
```
