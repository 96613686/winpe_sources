# SxsOleAut32MapIIDToTLBPath

- ea: `0x18001e620`
- end: `0x18001ece3`
- name: `SxsOleAut32MapIIDToTLBPath`
- size: `1731`
- prototype: `__int64 __fastcall(GUID *lpGuidToFind, unsigned __int64, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800075a0`
- `0x18001c2c8`
- `0x18001e5c0`
- `0x18001e620`
- `0x18002e98c`
- `0x18005b8a0`
- `0x18005bf78`
- `0x18005c304`
- `0x18005cd40`
- `0x18005d2b0`
- `0x180062288`
- `0x180067170`
- `0x18006a0f5`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18001e8b2`
- `ntdll!RtlPopFrame` at `0x18001ea40`
- `ntdll!RtlPopFrame` at `0x18001e8b2`
- `ntdll!RtlPopFrame` at `0x18001ea40`
- `ntdll!_snprintf_s` at `0x18001e7db`
- `ntdll!_snprintf_s` at `0x18001e7db`
- `ntdll!RtlGetFrame` at `0x18001e780`
- `ntdll!RtlGetFrame` at `0x18001e780`
- `ntdll!RtlPushFrame` at `0x18001e698`
- `ntdll!RtlPushFrame` at `0x18001e99a`
- `ntdll!RtlPushFrame` at `0x18001e698`
- `ntdll!RtlPushFrame` at `0x18001e99a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001e7f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001e7f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e81c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ecaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e81c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ecaa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e803`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e82c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e953`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001eb2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ebbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ec50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ecd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e803`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e82c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e953`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001eb2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ebbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ec50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ecd2`
- `KERNEL32!FindActCtxSectionGuid` at `0x18001e9f7`
- `KERNEL32!FindActCtxSectionGuid` at `0x18001ec10`
- `KERNEL32!FindActCtxSectionGuid` at `0x18001e9f7`
- `KERNEL32!FindActCtxSectionGuid` at `0x18001ec10`

## pseudocode

```c
__int64 __fastcall SxsOleAut32MapIIDToTLBPath(
        GUID *lpGuidToFind,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 *a4)
{
  const char *v8; // rcx
  const char *v9; // r14
  const char *FrameName; // r15
  int Previous; // edi
  PTEB_ACTIVE_FRAME v12; // rax
  PTEB_ACTIVE_FRAME v13; // rcx
  DWORD LastError; // ebx
  unsigned int v15; // esi
  DWORD v16; // ebx
  PCTEB_ACTIVE_FRAME_CONTEXT Context; // rdx
  const GUID *v19; // r12
  signed int v20; // eax
  signed int v21; // ebx
  __int64 v22; // rdi
  __int64 v23; // rcx
  int TypeLibraryFullPath; // eax
  int v25; // ebx
  DWORD v26; // edi
  int v27; // ecx
  signed int v28; // eax
  DWORD v29; // ebx
  int v30; // ecx
  _QWORD v31[15]; // [rsp+40h] [rbp-C8h] BYREF
  struct tagACTCTX_SECTION_KEYED_DATA ReturnedData; // [rsp+B8h] [rbp-50h] BYREF
  int v33; // [rsp+128h] [rbp+20h] BYREF
  int v34; // [rsp+12Ch] [rbp+24h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+130h] [rbp+28h] BYREF
  __int64 v36; // [rsp+148h] [rbp+40h]
  int v37; // [rsp+150h] [rbp+48h]
  int *v38; // [rsp+158h] [rbp+50h]
  struct _TEB_ACTIVE_FRAME v39; // [rsp+160h] [rbp+58h] BYREF
  __int64 v40; // [rsp+178h] [rbp+70h]
  int v41; // [rsp+180h] [rbp+78h]
  int *v42; // [rsp+188h] [rbp+80h]
  void **v43; // [rsp+198h] [rbp+90h] BYREF
  int v44; // [rsp+1A0h] [rbp+98h]
  unsigned __int16 *InlineBuffer; // [rsp+1A8h] [rbp+A0h]
  __int64 v46; // [rsp+1B0h] [rbp+A8h]
  unsigned __int64 v47; // [rsp+1B8h] [rbp+B0h]
  __int16 v48; // [rsp+1C0h] [rbp+B8h] BYREF
  char Buffer[512]; // [rsp+248h] [rbp+140h] BYREF

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D0C0;
  v38 = &v33;
  v33 = -2147418113;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v36 = 544438355;
  v37 = 492;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v44 = 0;
  InlineBuffer = 0;
  v43 = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  memset(&v31[1], 0, 112);
  v46 = 0;
  v47 = 0;
  v48 = 0;
  InlineBuffer = (unsigned __int16 *)CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(&v43);
  v46 = ((__int64 (__fastcall *)(void ***))v43[3])(&v43);
  if ( (unsigned int)Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline() )
    memset_0(InlineBuffer, 0, 2 * v46);
  if ( !lpGuidToFind )
  {
    v37 = 498;
    v9 = byte_18008517D;
    FrameName = byte_18008517D;
    Previous = 0;
    v12 = RtlGetFrame();
    if ( v12 && (v12->Flags & 1) != 0 )
    {
      v13 = v12;
    }
    else
    {
      v13 = 0;
      if ( !v12 )
      {
LABEL_8:
        LastError = GetLastError();
        _snprintf_s(
          Buffer,
          0x200u,
          0x1FFu,
          "%s(%d): Input parameter validation failed in function %s\n   Validation expression: %s\n",
          v9,
          Previous,
          FrameName,
          byte_18008517D);
        Buffer[511] = 0;
        OutputDebugStringA(Buffer);
        SetLastError(LastError);
LABEL_9:
        *v38 = -2147024809;
        v15 = v33;
        v16 = GetLastError();
        goto LABEL_10;
      }
    }
    Context = v12->Context;
    if ( Context )
    {
      if ( Context->FrameName )
        FrameName = Context->FrameName;
      if ( (Context->Flags & 1) != 0 && *(_QWORD *)&Context[1].Flags )
        v9 = *(const char **)&Context[1].Flags;
    }
    if ( v13 && *(_QWORD *)&v13[1].Flags == 544438355 && LODWORD(v13[1].Previous) )
      Previous = (int)v13[1].Previous;
    goto LABEL_8;
  }
  if ( !a3 )
  {
    v37 = 499;
    FusionpTraceParameterCheck(v8);
    goto LABEL_9;
  }
  if ( !a4 )
  {
    v37 = 500;
    FusionpTraceParameterCheck(v8);
    goto LABEL_9;
  }
  if ( !a2 )
  {
    v37 = 501;
    FusionpTraceParameterCheck(v8);
    goto LABEL_9;
  }
  SetLastError(0);
  v34 = -2147418113;
  v39.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D6A0;
  v39.Flags = 1;
  v42 = &v34;
  v39.Previous = 0;
  v40 = 544438355;
  v41 = 453;
  RtlPushFrame(&v39);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  ReturnedData.cbSize = 112;
  memset(&ReturnedData.ulDataFormatVersion, 0, 108);
  if ( FindActCtxSectionGuid(0, 0, 5u, lpGuidToFind, &ReturnedData) )
  {
    v21 = 0;
    v19 = (const GUID *)((char *)ReturnedData.lpData + 28);
  }
  else
  {
    v19 = 0;
    v20 = GetLastError();
    v21 = v20;
    if ( v20 == 14007 || v20 == 14000 )
    {
      v21 = 1;
    }
    else if ( v20 > 0 )
    {
      v21 = (unsigned __int16)v20 | 0x80070000;
    }
  }
  v34 = v21;
  if ( g_FusionEnterExitTracingEnabled )
  {
    v26 = GetLastError();
    v27 = *v42;
    if ( *v42 < 0 )
      FusionpTraceCOMFailure(v27, 0);
    else
      FusionpTraceCallCOMSuccessfulExit(v27, 0);
    SetLastError(v26);
  }
  RtlPopFrame(&v39);
  v33 = v21;
  if ( v21 < 0 )
  {
    FusionpTraceCOMFailure(v21, byte_18008517D);
    CFnTracerHR::MarkCOMFailure((CFnTracerHR *)&Frame, v21);
    v15 = v33;
    goto LABEL_48;
  }
  v22 = -1;
  if ( v21 != 1 )
  {
    LODWORD(v31[1]) = 112;
    if ( FindActCtxSectionGuid(3u, 0, 6u, v19, (PACTCTX_SECTION_KEYED_DATA)&v31[1]) )
    {
      if ( v31[8] != -1 )
        v22 = v31[8];
      SetLastError(0);
      TypeLibraryFullPath = HrFusionpOleaut_GetTypeLibraryFullPath((struct tagACTCTX_SECTION_KEYED_DATA *)&v31[1]);
      v25 = TypeLibraryFullPath;
      if ( TypeLibraryFullPath < 0
        || (SetLastError(0),
            TypeLibraryFullPath = HrFusionpOleaut_CopyString(a3, a2, a4, InlineBuffer, v47),
            v25 = TypeLibraryFullPath,
            TypeLibraryFullPath < 0) )
      {
        FusionpTraceCOMFailure(TypeLibraryFullPath, byte_18008517D);
        CFnTracerHR::MarkCOMFailure((CFnTracerHR *)&Frame, v25);
      }
      else
      {
        v33 = 0;
      }
      goto LABEL_37;
    }
    v28 = GetLastError();
    v15 = v28;
    if ( v28 == 14007 || v28 == 14000 )
    {
      v15 = 1;
    }
    else if ( v28 > 0 )
    {
      v15 = (unsigned __int16)v28 | 0x80070000;
    }
    v33 = v15;
LABEL_48:
    v16 = GetLastError();
    goto LABEL_10;
  }
LABEL_37:
  v15 = v33;
  v16 = GetLastError();
  if ( v22 != -1 )
    COperatorReleaseActCtx::operator()(v23, v22);
LABEL_10:
  SetLastError(v16);
  v43 = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( InlineBuffer != (unsigned __int16 *)&v48 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v43);
  InlineBuffer = 0;
  v46 = 0;
  v43 = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  if ( g_FusionEnterExitTracingEnabled )
  {
    v29 = GetLastError();
    v30 = *v38;
    if ( *v38 < 0 )
      FusionpTraceCOMFailure(v30, 0);
    else
      FusionpTraceCallCOMSuccessfulExit(v30, 0);
    SetLastError(v29);
  }
  RtlPopFrame(&Frame);
  return v15;
}

```

## disassembly

```asm
0x18001e620  mov     r11, rsp
0x18001e623  push    rbp
0x18001e624  push    rbx
0x18001e625  push    rsi
0x18001e626  lea     rbp, [r11-398h]
0x18001e62d  sub     rsp, 480h
0x18001e634  mov     rax, cs:__security_cookie
0x18001e63b  xor     rax, rsp
0x18001e63e  mov     [rbp+390h+var_50], rax
0x18001e645  mov     [r11-30h], r13
0x18001e649  lea     rax, qword_18006D0C0
0x18001e650  mov     [r11-38h], r14
0x18001e654  mov     rbx, rcx
0x18001e657  mov     [rbp+390h+Frame.Context], rax
0x18001e65b  lea     rcx, [rbp+390h+Frame]; Frame
0x18001e65f  lea     rax, [rbp+390h+var_370]
0x18001e663  mov     [r11-40h], r15
0x18001e667  xor     r13d, r13d
0x18001e66a  mov     [rbp+390h+var_340], rax
0x18001e66e  mov     r15, r9
0x18001e671  mov     [rbp+390h+var_370], 8000FFFFh
0x18001e678  mov     r14, r8
0x18001e67b  mov     [rbp+390h+Frame.Flags], 1
0x18001e682  mov     rsi, rdx
0x18001e685  mov     [rbp+390h+Frame.Previous], r13
0x18001e689  mov     [rbp+390h+var_350], 20737853h
0x18001e691  mov     [rbp+390h+var_348], 1ECh
0x18001e698  call    cs:__imp_RtlPushFrame
0x18001e69f  nop     dword ptr [rax+rax+00h]
0x18001e6a4  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x18001e6ab  jnz     loc_18001EAA6
0x18001e6b1  xorps   xmm0, xmm0
0x18001e6b4  mov     [rbp+390h+var_2F8], r13d
0x18001e6bb  lea     rax, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x18001e6c2  mov     [rbp+390h+var_2F0], r13
0x18001e6c9  lea     rcx, [rbp+390h+var_300]
0x18001e6d0  mov     [rbp+390h+var_300], rax
0x18001e6d7  movups  xmmword ptr [rsp+490h+var_458+8], xmm0
0x18001e6dc  mov     [rbp+390h+var_2E8], r13
0x18001e6e3  movups  xmmword ptr [rsp+490h+var_458+18h], xmm0
0x18001e6e8  mov     [rbp+390h+var_2E0], r13
0x18001e6ef  movups  xmmword ptr [rsp+490h+var_458+28h], xmm0
0x18001e6f4  mov     [rbp+390h+var_2D8], r13w
0x18001e6fc  movups  xmmword ptr [rsp+490h+var_458+38h], xmm0
0x18001e701  movups  xmmword ptr [rbp+390h+var_458+48h], xmm0
0x18001e705  movups  xmmword ptr [rbp+390h+var_458+58h], xmm0
0x18001e709  movups  xmmword ptr [rbp+390h+var_458+68h], xmm0
0x18001e70d  call    ?GetInlineBuffer@?$CGenericStringBuffer@$00VCUnicodeCharTraits@@@@MEBAPEAGXZ; CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(void)
0x18001e712  mov     [rbp+390h+var_2F0], rax
0x18001e719  lea     rcx, [rbp+390h+var_300]
0x18001e720  mov     rax, [rbp+390h+var_300]
0x18001e727  mov     rax, [rax+18h]
0x18001e72b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e730  mov     [rbp+390h+var_2E8], rax
0x18001e737  call    Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline
0x18001e73c  test    eax, eax
0x18001e73e  jz      short loc_18001E758
0x18001e740  mov     r8, [rbp+390h+var_2E8]
0x18001e747  xor     edx, edx; Val
0x18001e749  mov     rcx, [rbp+390h+var_2F0]; void *
0x18001e750  add     r8, r8; Size
0x18001e753  call    memset_0
0x18001e758  mov     [rsp+478h], rdi
0x18001e760  test    rbx, rbx
0x18001e763  jnz     loc_18001E936
0x18001e769  lea     rsi, byte_18008517D
0x18001e770  mov     [rbp+390h+var_348], 1F2h
0x18001e777  mov     r14, rsi
0x18001e77a  mov     r15, rsi
0x18001e77d  mov     edi, r13d
0x18001e780  call    cs:__imp_RtlGetFrame
0x18001e787  nop     dword ptr [rax+rax+00h]
0x18001e78c  test    rax, rax
0x18001e78f  jnz     loc_18001E8DB
0x18001e795  mov     rcx, r13
0x18001e798  test    rax, rax
0x18001e79b  jnz     loc_18001E8E7
0x18001e7a1  call    cs:__imp_GetLastError
0x18001e7a8  nop     dword ptr [rax+rax+00h]
0x18001e7ad  mov     qword ptr [rsp+490h+var_458], rsi
0x18001e7b2  lea     r9, aSDInputParamet; "%s(%d): Input parameter validation fail"...
0x18001e7b9  mov     [rsp+490h+var_460], r15
0x18001e7be  lea     rcx, [rbp+390h+Buffer]; Buffer
0x18001e7c5  mov     dword ptr [rsp+490h+var_468], edi
0x18001e7c9  mov     edx, 200h; BufferCount
0x18001e7ce  mov     r8d, 1FFh; MaxCount
0x18001e7d4  mov     [rsp+490h+ReturnedData], r14
0x18001e7d9  mov     ebx, eax
0x18001e7db  call    cs:__imp__snprintf_s
0x18001e7e2  nop     dword ptr [rax+rax+00h]
0x18001e7e7  lea     rcx, [rbp+390h+Buffer]; lpOutputString
0x18001e7ee  mov     [rbp+390h+var_51], r13b
0x18001e7f5  call    cs:__imp_OutputDebugStringA
0x18001e7fc  nop     dword ptr [rax+rax+00h]
0x18001e801  mov     ecx, ebx; dwErrCode
0x18001e803  call    cs:__imp_SetLastError
0x18001e80a  nop     dword ptr [rax+rax+00h]
0x18001e80f  mov     rax, [rbp+390h+var_340]
0x18001e813  mov     dword ptr [rax], 80070057h
0x18001e819  mov     esi, [rbp+390h+var_370]
0x18001e81c  call    cs:__imp_GetLastError
0x18001e823  nop     dword ptr [rax+rax+00h]
0x18001e828  mov     ebx, eax
0x18001e82a  mov     ecx, ebx; dwErrCode
0x18001e82c  call    cs:__imp_SetLastError
0x18001e833  nop     dword ptr [rax+rax+00h]
0x18001e838  mov     rdx, [rbp+390h+var_2F0]
0x18001e83f  lea     rax, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x18001e846  mov     r15, [rsp+490h+var_38]
0x18001e84e  mov     r14, [rsp+490h+var_30]
0x18001e856  mov     rdi, [rsp+478h]
0x18001e85e  mov     [rbp+390h+var_300], rax
0x18001e865  lea     rax, [rbp+390h+var_2D8]
0x18001e86c  cmp     rdx, rax
0x18001e86f  jz      short loc_18001E87D
0x18001e871  lea     rcx, [rbp+390h+var_300]
0x18001e878  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x18001e87d  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18001e884  lea     rax, ??_7?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@6B@; const CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable'
0x18001e88b  mov     [rbp+390h+var_2F0], r13
0x18001e892  mov     [rbp+390h+var_2E8], r13
0x18001e899  mov     r13, [rsp+490h+var_28]
0x18001e8a1  mov     [rbp+390h+var_300], rax
0x18001e8a8  jnz     loc_18001ECAA
0x18001e8ae  lea     rcx, [rbp+390h+Frame]; Frame
0x18001e8b2  call    cs:__imp_RtlPopFrame
0x18001e8b9  nop     dword ptr [rax+rax+00h]
0x18001e8be  mov     eax, esi
0x18001e8c0  mov     rcx, [rbp+390h+var_50]
0x18001e8c7  xor     rcx, rsp; StackCookie
0x18001e8ca  call    __security_check_cookie
0x18001e8cf  add     rsp, 480h
0x18001e8d6  pop     rsi
0x18001e8d7  pop     rbx
0x18001e8d8  pop     rbp
0x18001e8d9  retn
0x18001e8db  test    byte ptr [rax], 1
0x18001e8de  jz      loc_18001E795
0x18001e8e4  mov     rcx, rax
0x18001e8e7  mov     rdx, [rax+10h]
0x18001e8eb  test    rdx, rdx
0x18001e8ee  jz      short loc_18001E90D
0x18001e8f0  mov     rax, [rdx+8]
0x18001e8f4  test    rax, rax
0x18001e8f7  jz      short loc_18001E8FC
0x18001e8f9  mov     r15, rax
0x18001e8fc  test    byte ptr [rdx], 1
0x18001e8ff  jz      short loc_18001E90D
0x18001e901  mov     rax, [rdx+10h]
0x18001e905  test    rax, rax
0x18001e908  jz      short loc_18001E90D
0x18001e90a  mov     r14, rax
0x18001e90d  test    rcx, rcx
0x18001e910  jz      loc_18001E7A1
0x18001e916  cmp     qword ptr [rcx+18h], 20737853h
0x18001e91e  jnz     loc_18001E7A1
0x18001e924  mov     eax, [rcx+20h]
0x18001e927  test    eax, eax
0x18001e929  jz      loc_18001E7A1
0x18001e92f  mov     edi, eax
0x18001e931  jmp     loc_18001E7A1
0x18001e936  test    r14, r14
0x18001e939  jz      loc_18001EA95
0x18001e93f  test    r15, r15
0x18001e942  jz      loc_18001EB70
0x18001e948  test    rsi, rsi
0x18001e94b  jz      loc_18001EAB0
0x18001e951  xor     ecx, ecx; dwErrCode
0x18001e953  call    cs:__imp_SetLastError
0x18001e95a  nop     dword ptr [rax+rax+00h]
0x18001e95f  lea     rax, qword_18006D6A0
0x18001e966  mov     [rbp+390h+var_36C], 8000FFFFh
0x18001e96d  mov     [rbp+390h+var_338.Context], rax
0x18001e971  lea     rcx, [rbp+390h+var_338]; Frame
0x18001e975  lea     rax, [rbp+390h+var_36C]
0x18001e979  mov     [rbp+390h+var_338.Flags], 1
0x18001e980  mov     [rbp+390h+var_310], rax
0x18001e987  mov     [rbp+390h+var_338.Previous], r13
0x18001e98b  mov     [rbp+390h+var_320], 20737853h
0x18001e993  mov     [rbp+390h+var_318], 1C5h
0x18001e99a  call    cs:__imp_RtlPushFrame
0x18001e9a1  nop     dword ptr [rax+rax+00h]
0x18001e9a6  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x18001e9ad  jnz     loc_18001EAD1
0x18001e9b3  xorps   xmm0, xmm0
0x18001e9b6  mov     [rsp+490h+var_20], r12
0x18001e9be  lea     rax, [rbp+390h+var_3E0]
0x18001e9c2  mov     [rbp+390h+var_3E0.cbSize], 70h ; 'p'
0x18001e9c9  movups  xmmword ptr [rbp+390h+var_3E0.AssemblyMetadata.lpSectionBase+4], xmm0
0x18001e9cd  mov     r9, rbx; lpGuidToFind
0x18001e9d0  mov     [rsp+490h+ReturnedData], rax; ReturnedData
0x18001e9d5  xor     edx, edx; lpExtensionGuid
0x18001e9d7  xor     ecx, ecx; dwFlags
0x18001e9d9  mov     r8d, 5; ulSectionId
0x18001e9df  movups  xmmword ptr [rbp+390h+var_3E0.AssemblyMetadata.lpSectionGlobalDataBase], xmm0
0x18001e9e3  movups  xmmword ptr [rbp+390h+var_3E0.ulDataFormatVersion], xmm0
0x18001e9e7  movups  xmmword ptr [rbp+390h+var_3E0+14h], xmm0
0x18001e9eb  movups  xmmword ptr [rbp+390h+var_3E0+24h], xmm0
0x18001e9ef  movups  xmmword ptr [rbp+390h+var_3E0+34h], xmm0
0x18001e9f3  movups  xmmword ptr [rbp+390h+var_3E0.ulFlags], xmm0
0x18001e9f7  call    cs:__imp_FindActCtxSectionGuid
0x18001e9fe  nop     dword ptr [rax+rax+00h]
0x18001ea03  test    eax, eax
0x18001ea05  jnz     loc_18001EAC1
0x18001ea0b  mov     r12, r13
0x18001ea0e  call    cs:__imp_GetLastError
0x18001ea15  nop     dword ptr [rax+rax+00h]
0x18001ea1a  mov     ebx, eax
0x18001ea1c  cmp     eax, 36B7h
0x18001ea21  jnz     loc_18001EB81
0x18001ea27  mov     ebx, 1
0x18001ea2c  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x18001ea33  mov     [rbp+390h+var_36C], ebx
0x18001ea36  jnz     loc_18001EB91
0x18001ea3c  lea     rcx, [rbp+390h+var_338]; Frame
0x18001ea40  call    cs:__imp_RtlPopFrame
0x18001ea47  nop     dword ptr [rax+rax+00h]
0x18001ea4c  mov     [rbp+390h+var_370], ebx
0x18001ea4f  test    ebx, ebx
0x18001ea51  js      loc_18001EBCD
0x18001ea57  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001ea5e  cmp     ebx, 1
0x18001ea61  jnz     loc_18001EBEE
0x18001ea67  mov     esi, [rbp+390h+var_370]
0x18001ea6a  call    cs:__imp_GetLastError
0x18001ea71  nop     dword ptr [rax+rax+00h]
0x18001ea76  mov     ebx, eax
0x18001ea78  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001ea7c  jnz     short loc_18001EA8B
0x18001ea7e  mov     r12, [rsp+490h+var_20]
0x18001ea86  jmp     loc_18001E82A
0x18001ea8b  mov     rdx, rdi
0x18001ea8e  call    ??RCOperatorReleaseActCtx@@QEBAHPEAX@Z; COperatorReleaseActCtx::operator()(void *)
0x18001ea93  jmp     short loc_18001EA7E
0x18001ea95  mov     [rbp+390h+var_348], 1F3h
0x18001ea9c  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18001eaa1  jmp     loc_18001E80F
0x18001eaa6  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18001eaab  jmp     loc_18001E6B1
0x18001eab0  mov     [rbp+390h+var_348], 1F5h
0x18001eab7  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18001eabc  jmp     loc_18001E80F
0x18001eac1  mov     r12, [rbp+390h+var_3E0.lpData]
0x18001eac5  mov     ebx, r13d
0x18001eac8  add     r12, 1Ch
0x18001eacc  jmp     loc_18001EA2C
0x18001ead1  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18001ead6  jmp     loc_18001E9B3
0x18001eadb  test    eax, eax
0x18001eadd  jle     loc_18001EA2C
0x18001eae3  movzx   ebx, ax
0x18001eae6  or      ebx, 80070000h
0x18001eaec  jmp     loc_18001EA2C
0x18001eaf1  test    eax, eax
0x18001eaf3  jle     short loc_18001EAFE
0x18001eaf5  movzx   esi, ax
0x18001eaf8  or      esi, 80070000h
0x18001eafe  mov     [rbp+390h+var_370], esi
0x18001eb01  call    cs:__imp_GetLastError
0x18001eb08  nop     dword ptr [rax+rax+00h]
0x18001eb0d  mov     r12, [rsp+490h+var_20]
0x18001eb15  mov     ebx, eax
0x18001eb17  jmp     loc_18001E82A
0x18001eb1c  mov     rax, qword ptr [rsp+490h+var_458+40h]
0x18001eb21  cmp     rax, rdi
0x18001eb24  jz      short loc_18001EB29
0x18001eb26  mov     rdi, rax
0x18001eb29  xor     ecx, ecx; dwErrCode
0x18001eb2b  call    cs:__imp_SetLastError
0x18001eb32  nop     dword ptr [rax+rax+00h]
0x18001eb37  lea     rdx, [rbp+390h+var_300]
0x18001eb3e  lea     rcx, [rsp+490h+var_458+8]; struct tagACTCTX_SECTION_KEYED_DATA *
0x18001eb43  call    ?HrFusionpOleaut_GetTypeLibraryFullPath@@YAJPEBUtagACTCTX_SECTION_KEYED_DATA@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; HrFusionpOleaut_GetTypeLibraryFullPath(tagACTCTX_SECTION_KEYED_DATA const *,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18001eb48  mov     ebx, eax
0x18001eb4a  test    eax, eax
0x18001eb4c  jns     loc_18001EC4E
0x18001eb52  lea     rdx, byte_18008517D; char *
0x18001eb59  mov     ecx, eax; int
0x18001eb5b  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x18001eb60  mov     edx, ebx; int
0x18001eb62  lea     rcx, [rbp+390h+Frame]; this
0x18001eb66  call    ?MarkCOMFailure@CFnTracerHR@@QEAAXJ@Z; CFnTracerHR::MarkCOMFailure(long)
0x18001eb6b  jmp     loc_18001EA67
0x18001eb70  mov     [rbp+390h+var_348], 1F4h
0x18001eb77  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18001eb7c  jmp     loc_18001E80F
0x18001eb81  cmp     eax, 36B0h
0x18001eb86  jz      loc_18001EA27
0x18001eb8c  jmp     loc_18001EADB
0x18001eb91  call    cs:__imp_GetLastError
0x18001eb98  nop     dword ptr [rax+rax+00h]
0x18001eb9d  mov     rcx, [rbp+390h+var_310]
0x18001eba4  xor     edx, edx; char *
0x18001eba6  mov     edi, eax
0x18001eba8  mov     ecx, [rcx]; int
0x18001ebaa  test    ecx, ecx
0x18001ebac  js      short loc_18001EBB5
0x18001ebae  call    ?FusionpTraceCallCOMSuccessfulExit@@YAXJPEBDZZ; FusionpTraceCallCOMSuccessfulExit(long,char const *,...)
0x18001ebb3  jmp     short loc_18001EBBA
0x18001ebb5  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
  ... truncated ...
```
