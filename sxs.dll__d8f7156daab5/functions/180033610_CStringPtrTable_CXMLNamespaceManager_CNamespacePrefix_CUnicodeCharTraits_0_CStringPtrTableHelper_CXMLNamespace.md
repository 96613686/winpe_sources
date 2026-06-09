# CStringPtrTable<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>>::Find(CCountedStringHolder<CUnicodeCharTraits> const &,CXMLNamespaceManager::CNamespacePrefix * &)

- ea: `0x180033610`
- end: `0x180033b42`
- name: `?Find@?$CStringPtrTable@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@@@QEAAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@AEAPEAVCNamespacePrefix@CXMLNamespaceManager@@@Z`
- size: `1330`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180032d70`

## callees

- `0x18000df40`
- `0x18001c2c8`
- `0x1800208dc`
- `0x180033610`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180033939`
- `ntdll!RtlCompareUnicodeString` at `0x180033939`
- `ntdll!RtlPopFrame` at `0x180033781`
- `ntdll!RtlPopFrame` at `0x1800337a2`
- `ntdll!RtlPopFrame` at `0x18003396d`
- `ntdll!RtlPopFrame` at `0x18003398e`
- `ntdll!RtlPopFrame` at `0x1800339b7`
- `ntdll!RtlPopFrame` at `0x1800339e4`
- `ntdll!RtlPopFrame` at `0x180033781`
- `ntdll!RtlPopFrame` at `0x1800337a2`
- `ntdll!RtlPopFrame` at `0x18003396d`
- `ntdll!RtlPopFrame` at `0x18003398e`
- `ntdll!RtlPopFrame` at `0x1800339b7`
- `ntdll!RtlPopFrame` at `0x1800339e4`
- `ntdll!RtlPushFrame` at `0x180033683`
- `ntdll!RtlPushFrame` at `0x1800336e1`
- `ntdll!RtlPushFrame` at `0x180033804`
- `ntdll!RtlPushFrame` at `0x180033683`
- `ntdll!RtlPushFrame` at `0x1800336e1`
- `ntdll!RtlPushFrame` at `0x180033804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033aca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033af9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033aca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033af9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800336a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800336fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003374e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800337b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003383c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033885`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800338dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033949`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800336a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800336fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003374e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800337b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003383c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033885`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800338dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033949`

## pseudocode

```c
__int64 __fastcall CStringPtrTable<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>>::Find(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v4; // r15
  unsigned __int64 v7; // rdi
  const unsigned __int16 *v8; // rsi
  unsigned int v9; // esi
  __int64 v10; // rdi
  __int64 v11; // rax
  _QWORD **v12; // r13
  _QWORD *i; // r14
  __int64 v14; // rsi
  WCHAR *v15; // rdi
  WCHAR *v16; // rax
  LONG v17; // edi
  DWORD LastError; // eax
  DWORD v20; // eax
  DWORD v21; // eax
  DWORD v22; // eax
  DWORD v23; // eax
  unsigned int v24; // [rsp+20h] [rbp-E0h]
  UNICODE_STRING String2; // [rsp+30h] [rbp-D0h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+54h] [rbp-ACh] BYREF
  int v30; // [rsp+58h] [rbp-A8h] BYREF
  int v31; // [rsp+5Ch] [rbp-A4h] BYREF
  struct _TEB_ACTIVE_FRAME v32; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+80h] [rbp-80h]
  int *v35; // [rsp+88h] [rbp-78h]
  struct _TEB_ACTIVE_FRAME v36; // [rsp+90h] [rbp-70h] BYREF
  __int64 v37; // [rsp+A8h] [rbp-58h]
  int v38; // [rsp+B0h] [rbp-50h]
  int *v39; // [rsp+B8h] [rbp-48h]
  struct _TEB_ACTIVE_FRAME v40; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v41; // [rsp+D8h] [rbp-28h]
  int v42; // [rsp+E0h] [rbp-20h]
  int *v43; // [rsp+E8h] [rbp-18h]
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v45; // [rsp+108h] [rbp+8h]
  int v46; // [rsp+110h] [rbp+10h]
  int *v47; // [rsp+118h] [rbp+18h]

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CStringPtrTable<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>>::Find'::`2'::__stc;
  v45 = 544438355;
  v4 = 0;
  v47 = &v31;
  v31 = 0;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v46 = 1461;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  *a3 = 0;
  SetLastError(0);
  v28 = 0;
  v36.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CStringTableHelper<CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CUnicodeCharTraits,0>::HashKey'::`2'::__stc;
  v36.Flags = 1;
  v39 = &v28;
  v36.Previous = 0;
  v37 = 544438355;
  v38 = 1287;
  RtlPushFrame(&v36);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  SetLastError(0);
  v7 = *(_QWORD *)(a2 + 8);
  v8 = *(const unsigned __int16 **)a2;
  v32.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CCharTraitsBase<unsigned short,char>::Win32HashString'::`2'::__stc;
  v35 = &v29;
  v29 = 0;
  v32.Flags = 1;
  v32.Previous = 0;
  v33 = 544438355;
  v34 = 156;
  CFrame::BaseEnter((CFrame *)&v32);
  SetLastError(0);
  v9 = FusionpHashUnicodeStringCaseSensitive(v8, v7);
  v24 = v9;
  v29 = 1;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v35 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&v32);
  v28 = 1;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v39 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v20 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v20, 0);
    }
  }
  RtlPopFrame(&v36);
  v10 = v9 % *(_DWORD *)a1;
  SetLastError(0);
  v11 = *(_QWORD *)(a1 + 8);
  v30 = 0;
  v40.Flags = 1;
  v40.Previous = 0;
  v12 = (_QWORD **)(v11 + 40 * v10);
  v41 = 544438355;
  v42 = 802;
  v40.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucketChain::Find'::`2'::__stc;
  v43 = &v30;
  RtlPushFrame(&v40);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  for ( i = *v12; i && i != v12; i = (_QWORD *)*i )
  {
    SetLastError(0);
    if ( *((_DWORD *)i - 2) == v9 )
    {
      v28 = 0;
      v39 = &v28;
      v36.Flags = 1;
      v36.Previous = 0;
      v36.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CStringTableHelper<CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CUnicodeCharTraits,0>::CompareKey'::`2'::__stc;
      v37 = 544438355;
      v38 = 1289;
      CFrame::BaseEnter((CFrame *)&v36);
      SetLastError(0);
      v32.Flags = 1;
      v33 = 544438355;
      v34 = 654;
      v14 = *(_QWORD *)(a2 + 8);
      v15 = *(WCHAR **)a2;
      v29 = 0;
      v32.Previous = 0;
      v32.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Equals'::`2'::__stc;
      v35 = &v29;
      CFrame::BaseEnter((CFrame *)&v32);
      SetLastError(0);
      v16 = (WCHAR *)*(i - 70);
      *(_QWORD *)&String1.Length = 0;
      String1.Buffer = v16;
      LOWORD(v16) = *((_WORD *)i - 272);
      *(&String2.MaximumLength + 2) = 0;
      String2.Buffer = v15;
      *(_QWORD *)&String1.Length = (unsigned __int16)(2 * (_WORD)v16);
      *(_DWORD *)&String1.MaximumLength = (unsigned __int16)(2 * (_WORD)v16);
      String2.Length = 2 * v14;
      *(_DWORD *)&String2.MaximumLength = (unsigned __int16)(2 * v14);
      v17 = RtlCompareUnicodeString(&String1, &String2, 0);
      SetLastError(0);
      *v35 = 1;
      if ( g_FusionEnterExitTracingEnabled )
        FusionpTraceCallSuccessfulExit(0);
      RtlPopFrame(&v32);
      v28 = 1;
      if ( g_FusionEnterExitTracingEnabled )
      {
        if ( *v39 )
        {
          FusionpTraceCallSuccessfulExit(0);
        }
        else
        {
          v21 = GetLastError();
          FusionpTraceCallWin32UnsuccessfulExit(v21, 0);
        }
      }
      RtlPopFrame(&v36);
      if ( !v17 )
      {
        v4 = i - 2;
        break;
      }
      v9 = v24;
    }
  }
  v30 = 1;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v43 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v22 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v22, 0);
    }
  }
  RtlPopFrame(&v40);
  if ( v4 )
    *a3 = *v4;
  v31 = 1;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v47 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v23 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v23, 0);
    }
  }
  RtlPopFrame(&Frame);
  return 1;
}

```

## disassembly

```asm
0x180033610  mov     [rsp-8+arg_0], rbx
0x180033615  push    rbp
0x180033616  push    rsi
0x180033617  push    rdi
0x180033618  push    r12
0x18003361a  push    r13
0x18003361c  push    r14
0x18003361e  push    r15
0x180033620  lea     rbp, [rsp-30h]
0x180033625  sub     rsp, 130h
0x18003362c  mov     rax, cs:__security_cookie
0x180033633  xor     rax, rsp
0x180033636  mov     [rbp+60h+var_40], rax
0x18003363a  lea     rax, ?__stc@?1??Find@?$CStringPtrTable@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@@@QEAAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@AEAPEAVCNamespacePrefix@CXMLNamespaceManager@@@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CStringPtrTable<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>>::Find(CCountedStringHolder<CUnicodeCharTraits> const &,CXMLNamespaceManager::CNamespacePrefix * &)'::`2'::__stc
0x180033641  mov     [rsp+160h+var_138], rdx
0x180033646  mov     [rbp+60h+Frame.Context], rax
0x18003364a  mov     r14, rcx
0x18003364d  lea     rax, [rsp+160h+var_104]
0x180033652  mov     [rbp+60h+var_58], 20737853h
0x18003365a  xor     r15d, r15d
0x18003365d  mov     [rbp+60h+var_48], rax
0x180033661  mov     ebx, 1
0x180033666  mov     [rsp+160h+var_104], r15d
0x18003366b  lea     rcx, [rbp+60h+Frame]; Frame
0x18003366f  mov     [rbp+60h+Frame.Flags], ebx
0x180033672  mov     r12, r8
0x180033675  mov     [rbp+60h+Frame.Previous], r15
0x180033679  mov     rsi, rdx
0x18003367c  mov     [rbp+60h+var_50], 5B5h
0x180033683  call    cs:__imp_RtlPushFrame
0x18003368a  nop     dword ptr [rax+rax+00h]
0x18003368f  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x180033696  jnz     loc_180033A2D
0x18003369c  xor     ecx, ecx; dwErrCode
0x18003369e  mov     [r12], r15
0x1800336a2  call    cs:__imp_SetLastError
0x1800336a9  nop     dword ptr [rax+rax+00h]
0x1800336ae  lea     rax, ?__stc@?1??HashKey@?$CStringTableHelper@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV12@VCUnicodeCharTraits@@$0A@@@SAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@AEAK@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CStringTableHelper<CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CUnicodeCharTraits,0>::HashKey(CCountedStringHolder<CUnicodeCharTraits> const &,ulong &)'::`2'::__stc
0x1800336b5  mov     [rsp+160h+var_110], r15d
0x1800336ba  mov     [rbp+60h+var_D0.Context], rax
0x1800336be  lea     rcx, [rbp+60h+var_D0]; Frame
0x1800336c2  lea     rax, [rsp+160h+var_110]
0x1800336c7  mov     [rbp+60h+var_D0.Flags], ebx
0x1800336ca  mov     [rbp+60h+var_A8], rax
0x1800336ce  mov     [rbp+60h+var_D0.Previous], r15
0x1800336d2  mov     [rbp+60h+var_B8], 20737853h
0x1800336da  mov     [rbp+60h+var_B0], 507h
0x1800336e1  call    cs:__imp_RtlPushFrame
0x1800336e8  nop     dword ptr [rax+rax+00h]
0x1800336ed  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x1800336f4  jnz     loc_180033A37
0x1800336fa  xor     ecx, ecx; dwErrCode
0x1800336fc  call    cs:__imp_SetLastError
0x180033703  nop     dword ptr [rax+rax+00h]
0x180033708  mov     rdi, [rsi+8]
0x18003370c  lea     rax, ?__stc@?1??Win32HashString@?$CCharTraitsBase@GD@@SAHPEBG_KAEAK_N@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CCharTraitsBase<ushort,char>::Win32HashString(ushort const *,unsigned __int64,ulong &,bool)'::`2'::__stc
0x180033713  mov     rsi, [rsi]
0x180033716  lea     rcx, [rsp+160h+var_100]; this
0x18003371b  mov     [rsp+160h+var_100.Context], rax
0x180033720  lea     rax, [rsp+160h+var_10C]
0x180033725  mov     [rbp+60h+var_D8], rax
0x180033729  mov     [rsp+160h+var_10C], r15d
0x18003372e  mov     [rsp+160h+var_100.Flags], ebx
0x180033732  mov     [rsp+160h+var_100.Previous], r15
0x180033737  mov     [rsp+160h+var_E8], 20737853h
0x180033740  mov     [rbp+60h+var_E0], 9Ch
0x180033747  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18003374c  xor     ecx, ecx; dwErrCode
0x18003374e  call    cs:__imp_SetLastError
0x180033755  nop     dword ptr [rax+rax+00h]
0x18003375a  mov     rdx, rdi; unsigned __int64
0x18003375d  mov     rcx, rsi; unsigned __int16 *
0x180033760  call    ?FusionpHashUnicodeStringCaseSensitive@@YAKPEBG_K@Z; FusionpHashUnicodeStringCaseSensitive(ushort const *,unsigned __int64)
0x180033765  mov     esi, eax
0x180033767  mov     [rsp+160h+var_140], eax
0x18003376b  mov     [rsp+160h+var_10C], ebx
0x18003376f  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x180033776  jnz     loc_180033A4B
0x18003377c  lea     rcx, [rsp+160h+var_100]; Frame
0x180033781  call    cs:__imp_RtlPopFrame
0x180033788  nop     dword ptr [rax+rax+00h]
0x18003378d  mov     [rsp+160h+var_110], ebx
0x180033791  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x180033798  jnz     loc_180033A7A
0x18003379e  lea     rcx, [rbp+60h+var_D0]; Frame
0x1800337a2  call    cs:__imp_RtlPopFrame
0x1800337a9  nop     dword ptr [rax+rax+00h]
0x1800337ae  xor     edx, edx
0x1800337b0  mov     eax, esi
0x1800337b2  div     dword ptr [r14]
0x1800337b5  xor     ecx, ecx; dwErrCode
0x1800337b7  mov     edi, edx
0x1800337b9  call    cs:__imp_SetLastError
0x1800337c0  nop     dword ptr [rax+rax+00h]
0x1800337c5  mov     rax, [r14+8]
0x1800337c9  lea     rcx, [rdi+rdi*4]
0x1800337cd  mov     [rsp+160h+var_108], r15d
0x1800337d2  mov     [rbp+60h+var_A0.Flags], ebx
0x1800337d5  mov     [rbp+60h+var_A0.Previous], r15
0x1800337d9  lea     r13, [rax+rcx*8]
0x1800337dd  mov     [rbp+60h+var_88], 20737853h
0x1800337e5  lea     rax, ?__stc@?1??Find@CBucketChain@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@QEAAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@KAEAPEAPEAVCNamespacePrefix@CXMLNamespaceManager@@@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucketChain::Find(CCountedStringHolder<CUnicodeCharTraits> const &,ulong,CXMLNamespaceManager::CNamespacePrefix * * &)'::`2'::__stc
0x1800337ec  mov     [rbp+60h+var_80], 322h
0x1800337f3  mov     [rbp+60h+var_A0.Context], rax
0x1800337f7  lea     rcx, [rbp+60h+var_A0]; Frame
0x1800337fb  lea     rax, [rsp+160h+var_108]
0x180033800  mov     [rbp+60h+var_78], rax
0x180033804  call    cs:__imp_RtlPushFrame
0x18003380b  nop     dword ptr [rax+rax+00h]
0x180033810  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x180033817  jnz     loc_180033A41
0x18003381d  mov     r14, [r13+0]
0x180033821  lea     rdi, ?__stc@?1??CompareKey@?$CStringTableHelper@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV12@VCUnicodeCharTraits@@$0A@@@SAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@AEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@AEA_N@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CStringTableHelper<CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CUnicodeCharTraits,0>::CompareKey(CCountedStringHolder<CUnicodeCharTraits> const &,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &)'::`2'::__stc
0x180033828  test    r14, r14
0x18003382b  jz      loc_1800339A2
0x180033831  cmp     r14, r13
0x180033834  jz      loc_1800339A2
0x18003383a  xor     ecx, ecx; dwErrCode
0x18003383c  call    cs:__imp_SetLastError
0x180033843  nop     dword ptr [rax+rax+00h]
0x180033848  cmp     [r14-8], esi
0x18003384c  jnz     loc_180033A25
0x180033852  lea     rax, [rsp+160h+var_110]
0x180033857  mov     [rsp+160h+var_110], r15d
0x18003385c  lea     rcx, [rbp+60h+var_D0]; this
0x180033860  mov     [rbp+60h+var_A8], rax
0x180033864  mov     [rbp+60h+var_D0.Flags], ebx
0x180033867  mov     [rbp+60h+var_D0.Previous], r15
0x18003386b  mov     [rbp+60h+var_D0.Context], rdi
0x18003386f  mov     [rbp+60h+var_B8], 20737853h
0x180033877  mov     [rbp+60h+var_B0], 509h
0x18003387e  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180033883  xor     ecx, ecx; dwErrCode
0x180033885  call    cs:__imp_SetLastError
0x18003388c  nop     dword ptr [rax+rax+00h]
0x180033891  mov     rax, [rsp+160h+var_138]
0x180033896  lea     rcx, [rsp+160h+var_100]; this
0x18003389b  mov     [rsp+160h+var_100.Flags], ebx
0x18003389f  mov     [rsp+160h+var_E8], 20737853h
0x1800338a8  mov     [rbp+60h+var_E0], 28Eh
0x1800338af  mov     rsi, [rax+8]
0x1800338b3  mov     rdi, [rax]
0x1800338b6  xor     eax, eax
0x1800338b8  mov     [rsp+160h+var_10C], eax
0x1800338bc  mov     [rsp+160h+var_100.Previous], rax
0x1800338c1  lea     rax, ?__stc@?1??Win32Equals@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEBG_KAEA_N_N@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Equals(ushort const *,unsigned __int64,bool &,bool)'::`2'::__stc
0x1800338c8  mov     [rsp+160h+var_100.Context], rax
0x1800338cd  lea     rax, [rsp+160h+var_10C]
0x1800338d2  mov     [rbp+60h+var_D8], rax
0x1800338d6  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800338db  xor     ecx, ecx; dwErrCode
0x1800338dd  call    cs:__imp_SetLastError
0x1800338e4  nop     dword ptr [rax+rax+00h]
0x1800338e9  mov     rax, [r14-230h]
0x1800338f0  lea     rdx, [rsp+160h+String2]; String2
0x1800338f5  xorps   xmm0, xmm0
0x1800338f8  lea     rcx, [rsp+160h+String1]; String1
0x1800338fd  movups  xmmword ptr [rsp+160h+String1.Length], xmm0
0x180033902  mov     [rsp+160h+String1.Buffer], rax
0x180033907  add     si, si
0x18003390a  movzx   eax, word ptr [r14-220h]
0x180033912  xorps   xmm1, xmm1
0x180033915  movups  xmmword ptr [rsp+160h+String2.Length], xmm1
0x18003391a  add     ax, ax
0x18003391d  mov     [rsp+160h+String2.Buffer], rdi
0x180033922  xor     r8d, r8d; CaseInsensitive
0x180033925  mov     [rsp+160h+String1.Length], ax
0x18003392a  mov     [rsp+160h+String1.MaximumLength], ax
0x18003392f  mov     [rsp+160h+String2.Length], si
0x180033934  mov     [rsp+160h+String2.MaximumLength], si
0x180033939  call    cs:__imp_RtlCompareUnicodeString
0x180033940  nop     dword ptr [rax+rax+00h]
0x180033945  xor     ecx, ecx; dwErrCode
0x180033947  mov     edi, eax
0x180033949  call    cs:__imp_SetLastError
0x180033950  nop     dword ptr [rax+rax+00h]
0x180033955  mov     rcx, [rbp+60h+var_D8]
0x180033959  mov     [rcx], ebx
0x18003395b  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x180033962  jnz     loc_180033AA9
0x180033968  lea     rcx, [rsp+160h+var_100]; Frame
0x18003396d  call    cs:__imp_RtlPopFrame
0x180033974  nop     dword ptr [rax+rax+00h]
0x180033979  mov     [rsp+160h+var_110], ebx
0x18003397d  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x180033984  jnz     loc_180033AB5
0x18003398a  lea     rcx, [rbp+60h+var_D0]; Frame
0x18003398e  call    cs:__imp_RtlPopFrame
0x180033995  nop     dword ptr [rax+rax+00h]
0x18003399a  test    edi, edi
0x18003399c  jnz     short loc_180033A1A
0x18003399e  lea     r15, [r14-10h]
0x1800339a2  mov     [rsp+160h+var_108], ebx
0x1800339a6  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x1800339ad  jnz     loc_180033AE4
0x1800339b3  lea     rcx, [rbp+60h+var_A0]; Frame
0x1800339b7  call    cs:__imp_RtlPopFrame
0x1800339be  nop     dword ptr [rax+rax+00h]
0x1800339c3  test    r15, r15
0x1800339c6  jz      short loc_1800339CF
0x1800339c8  mov     rax, [r15]
0x1800339cb  mov     [r12], rax
0x1800339cf  mov     [rsp+160h+var_104], ebx
0x1800339d3  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x1800339da  jnz     loc_180033B13
0x1800339e0  lea     rcx, [rbp+60h+Frame]; Frame
0x1800339e4  call    cs:__imp_RtlPopFrame
0x1800339eb  nop     dword ptr [rax+rax+00h]
0x1800339f0  mov     eax, ebx
0x1800339f2  mov     rcx, [rbp+60h+var_40]
0x1800339f6  xor     rcx, rsp; StackCookie
0x1800339f9  call    __security_check_cookie
0x1800339fe  mov     rbx, [rsp+160h+arg_0]
0x180033a06  add     rsp, 130h
0x180033a0d  pop     r15
0x180033a0f  pop     r14
0x180033a11  pop     r13
0x180033a13  pop     r12
0x180033a15  pop     rdi
0x180033a16  pop     rsi
0x180033a17  pop     rbp
0x180033a18  retn
0x180033a1a  mov     esi, [rsp+160h+var_140]
0x180033a1e  lea     rdi, ?__stc@?1??CompareKey@?$CStringTableHelper@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV12@VCUnicodeCharTraits@@$0A@@@SAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@AEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@AEA_N@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CStringTableHelper<CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CUnicodeCharTraits,0>::CompareKey(CCountedStringHolder<CUnicodeCharTraits> const &,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &)'::`2'::__stc
0x180033a25  mov     r14, [r14]
0x180033a28  jmp     loc_180033828
0x180033a2d  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180033a32  jmp     loc_18003369C
0x180033a37  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180033a3c  jmp     loc_1800336FA
0x180033a41  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180033a46  jmp     loc_18003381D
0x180033a4b  mov     rcx, [rbp+60h+var_D8]
0x180033a4f  cmp     [rcx], r15d
0x180033a52  jz      short loc_180033A60
0x180033a54  xor     ecx, ecx; char *
0x180033a56  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180033a5b  jmp     loc_18003377C
0x180033a60  call    cs:__imp_GetLastError
0x180033a67  nop     dword ptr [rax+rax+00h]
0x180033a6c  mov     ecx, eax; unsigned int
0x180033a6e  xor     edx, edx; Format
0x180033a70  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180033a75  jmp     loc_18003377C
0x180033a7a  mov     rax, [rbp+60h+var_A8]
0x180033a7e  cmp     [rax], r15d
0x180033a81  jz      short loc_180033A8F
0x180033a83  xor     ecx, ecx; char *
0x180033a85  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180033a8a  jmp     loc_18003379E
0x180033a8f  call    cs:__imp_GetLastError
0x180033a96  nop     dword ptr [rax+rax+00h]
0x180033a9b  mov     ecx, eax; unsigned int
0x180033a9d  xor     edx, edx; Format
0x180033a9f  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180033aa4  jmp     loc_18003379E
0x180033aa9  xor     ecx, ecx; char *
0x180033aab  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180033ab0  jmp     loc_180033968
0x180033ab5  mov     rax, [rbp+60h+var_A8]
0x180033ab9  cmp     [rax], r15d
0x180033abc  jz      short loc_180033ACA
0x180033abe  xor     ecx, ecx; char *
0x180033ac0  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180033ac5  jmp     loc_18003398A
0x180033aca  call    cs:__imp_GetLastError
0x180033ad1  nop     dword ptr [rax+rax+00h]
0x180033ad6  mov     ecx, eax; unsigned int
0x180033ad8  xor     edx, edx; Format
0x180033ada  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180033adf  jmp     loc_18003398A
0x180033ae4  mov     rax, [rbp+60h+var_78]
0x180033ae8  cmp     dword ptr [rax], 0
0x180033aeb  jz      short loc_180033AF9
0x180033aed  xor     ecx, ecx; char *
0x180033aef  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180033af4  jmp     loc_1800339B3
0x180033af9  call    cs:__imp_GetLastError
0x180033b00  nop     dword ptr [rax+rax+00h]
0x180033b05  mov     ecx, eax; unsigned int
0x180033b07  xor     edx, edx; Format
0x180033b09  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180033b0e  jmp     loc_1800339B3
0x180033b13  mov     rax, [rbp+60h+var_48]
0x180033b17  cmp     dword ptr [rax], 0
0x180033b1a  jz      short loc_180033B28
0x180033b1c  xor     ecx, ecx; char *
0x180033b1e  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180033b23  jmp     loc_1800339E0
0x180033b28  call    cs:__imp_GetLastError
0x180033b2f  nop     dword ptr [rax+rax+00h]
0x180033b34  mov     ecx, eax; unsigned int
0x180033b36  xor     edx, edx; Format
0x180033b38  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180033b3d  jmp     loc_1800339E0
```
