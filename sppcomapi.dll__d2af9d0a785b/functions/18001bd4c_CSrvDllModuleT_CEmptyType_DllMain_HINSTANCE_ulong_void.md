# CSrvDllModuleT<CEmptyType>::DllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x18001bd4c`
- end: `0x18001bfe6`
- name: `?DllMain@?$CSrvDllModuleT@VCEmptyType@@@@SAJPEAUHINSTANCE__@@KPEAX@Z`
- size: `666`
- prototype: `__int64 __fastcall(HMODULE hLibModule)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001df6c`

## callees

- `0x180003520`
- `0x180004288`
- `0x180019d04`
- `0x18001a0a8`
- `0x18001bd4c`
- `0x18001bfec`
- `0x18001ca2c`
- `0x18001cdb0`
- `0x18003c330`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bdea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bf07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bdea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bf07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bf1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bf1b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bdff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bdff`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001bea5`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001bea5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bee5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bee5`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001bf6d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001bf82`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001bf6d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001bf82`

## pseudocode

```c
__int64 __fastcall CSrvDllModuleT<CEmptyType>::DllMain(HMODULE hLibModule, int a2, _QWORD *a3)
{
  const char *i; // rcx
  void *v6; // rsi
  unsigned int v7; // edi
  HANDLE ProcessHeap; // rax
  _QWORD *v9; // rax
  char v10; // cl
  _QWORD *v11; // rbx
  __int64 v12; // rcx
  int v13; // eax
  _QWORD *v14; // rbx
  void *v15; // rcx
  HANDLE v16; // rax
  __int64 j; // rbx
  __int64 (*v18)(void); // rax
  int v19; // eax
  _QWORD *v21; // [rsp+60h] [rbp+18h] BYREF
  _QWORD *v22; // [rsp+68h] [rbp+20h] BYREF

  v21 = a3;
  if ( (g_SymCryptFlags & 1) == 0 )
  {
    SymCryptDetectCpuFeaturesByCpuid();
    g_SymCryptCpuFeaturesNotPresent = g_SymCryptCpuFeaturesNotPresent & 0xFFFFFFCF | 0x10;
    _InterlockedOr(&g_SymCryptFlags, 1u);
    for ( i = "v104.0.0__2026-03-28T02:17:10+00:00_df5eaa1_2026-03-30T17:48:52"; *i; ++i )
      ;
    g_SymCryptCpuFeaturesPresentCheck = ~g_SymCryptCpuFeaturesNotPresent;
  }
  v21 = 0;
  v6 = 0;
  v7 = 0;
  if ( a2 )
  {
    if ( a2 != 1 )
      goto LABEL_28;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    ProcessHeap = GetProcessHeap();
    v9 = HeapAlloc(ProcessHeap, 0, 0x48u);
    if ( v9 )
    {
      *v9 = 1;
      v10 = 0;
      v9[5] = 0;
      v9[6] = 0;
      v9[7] = 0;
      v9[1] = 0;
      v9[2] = 0;
      v9[3] = 0;
      v9[4] = 0;
      v9[8] = 0;
    }
    else
    {
      v10 = 1;
      v9 = 0;
    }
    v11 = 0;
    if ( !v10 )
      v11 = v9;
    v22 = v11;
    if ( v11 )
    {
      v13 = CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>::Init(v11);
      v7 = v13;
      if ( v13 >= 0 )
      {
        v22 = 0;
        v6 = v11;
        v21 = v11;
LABEL_18:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
        SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>::~SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>(&v22);
        if ( (v7 & 0x80000000) == 0 )
        {
          DisableThreadLibraryCalls(hLibModule);
          v21 = 0;
          CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState = v6;
        }
        else
        {
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
        }
        goto LABEL_28;
      }
      v12 = (unsigned int)v13;
    }
    else
    {
      v7 = -2147024882;
      v12 = 2147942414LL;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
    goto LABEL_18;
  }
  v14 = CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState;
  if ( CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState
    && _InterlockedExchangeAdd(
         (volatile signed __int32 *)CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState,
         0xFFFFFFFF) == 1
    && v14 )
  {
    v15 = (void *)v14[8];
    if ( v15 )
    {
      CloseHandle(v15);
      v14[8] = 0;
    }
    CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>(v14 + 3);
    CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>(v14 + 1);
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v14);
  }
  CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState = 0;
LABEL_28:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>::~SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>(&v21);
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_29;
  if ( !a2 )
  {
    CGlobalInitializer<1>::Done();
    goto LABEL_44;
  }
  if ( a2 == 1 )
  {
    COverriddenOperatorsSafeGuardT<CEmptyType>::OperatorsSafeGuardFunc();
    for ( j = CGlobalList<CGlobalInitializer<1>>::g_pFirst; ; j = *(_QWORD *)j )
    {
      if ( !j )
      {
        v7 = 0;
        goto LABEL_40;
      }
      if ( !*(_DWORD *)(j + 24) )
      {
        if ( DecodePointer(*(PVOID *)(j + 8)) )
        {
          v18 = (__int64 (*)(void))DecodePointer(*(PVOID *)(j + 8));
          v19 = v18();
          v7 = v19;
          if ( v19 < 0 )
          {
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v19);
            CGlobalInitializer<1>::Done();
LABEL_40:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
            if ( (v7 & 0x80000000) != 0 )
LABEL_29:
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
            break;
          }
        }
        *(_DWORD *)(j + 24) = 1;
      }
    }
  }
LABEL_44:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  return v7;
}

```

## disassembly

```asm
0x18001bd4c  mov     [rsp+arg_0], rbx
0x18001bd51  mov     [rsp+arg_10], r8
0x18001bd56  push    rbp
0x18001bd57  push    rsi
0x18001bd58  push    rdi
0x18001bd59  push    r14
0x18001bd5b  push    r15
0x18001bd5d  sub     rsp, 20h
0x18001bd61  xor     r15d, r15d
0x18001bd64  mov     ebp, edx
0x18001bd66  test    byte ptr cs:g_SymCryptFlags, 1
0x18001bd6d  mov     r14, rcx
0x18001bd70  jnz     short loc_18001BDC5
0x18001bd72  call    SymCryptDetectCpuFeaturesByCpuid
0x18001bd77  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x18001bd7d  and     eax, 0FFFFFFDFh
0x18001bd80  or      eax, 10h
0x18001bd83  mov     cs:g_SymCryptCpuFeaturesNotPresent, eax
0x18001bd89  lock or cs:g_SymCryptFlags, 1
0x18001bd91  cmp     byte ptr cs:aV1040020260328, r15b; "v104.0.0__2026-03-28T02:17:10+00:00_df5"...
0x18001bd98  lea     rcx, aV1040020260328; "v104.0.0__2026-03-28T02:17:10+00:00_df5"...
0x18001bd9f  mov     [rsp+48h+arg_8], 680000h
0x18001bda7  jz      short loc_18001BDB7
0x18001bda9  mov     al, [rcx]
0x18001bdab  inc     rcx
0x18001bdae  mov     byte ptr [rsp+48h+arg_8], al
0x18001bdb2  cmp     [rcx], r15b
0x18001bdb5  jnz     short loc_18001BDA9
0x18001bdb7  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x18001bdbd  not     eax
0x18001bdbf  mov     cs:g_SymCryptCpuFeaturesPresentCheck, eax
0x18001bdc5  mov     [rsp+48h+arg_10], r15
0x18001bdca  mov     rsi, r15
0x18001bdcd  mov     edi, r15d
0x18001bdd0  mov     eax, ebp
0x18001bdd2  test    ebp, ebp
0x18001bdd4  jz      loc_18001BEBF
0x18001bdda  cmp     eax, 1
0x18001bddd  jnz     loc_18001BF2E
0x18001bde3  xor     ecx, ecx
0x18001bde5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001bdea  call    cs:__imp_GetProcessHeap
0x18001bdf1  nop     dword ptr [rax+rax+00h]
0x18001bdf6  xor     edx, edx; dwFlags
0x18001bdf8  lea     r8d, [rbp+47h]; dwBytes
0x18001bdfc  mov     rcx, rax; hHeap
0x18001bdff  call    cs:__imp_HeapAlloc
0x18001be06  nop     dword ptr [rax+rax+00h]
0x18001be0b  test    rax, rax
0x18001be0e  jz      short loc_18001BE3C
0x18001be10  mov     qword ptr [rax], 1
0x18001be17  mov     cl, r15b
0x18001be1a  mov     [rax+28h], r15
0x18001be1e  mov     [rax+30h], r15
0x18001be22  mov     [rax+38h], r15
0x18001be26  mov     [rax+8], r15
0x18001be2a  mov     [rax+10h], r15
0x18001be2e  mov     [rax+18h], r15
0x18001be32  mov     [rax+20h], r15
0x18001be36  mov     [rax+40h], r15
0x18001be3a  jmp     short loc_18001BE41
0x18001be3c  mov     cl, 1
0x18001be3e  mov     rax, r15
0x18001be41  test    cl, cl
0x18001be43  mov     rbx, r15
0x18001be46  cmovz   rbx, rax
0x18001be4a  mov     [rsp+48h+arg_18], rbx
0x18001be4f  test    rbx, rbx
0x18001be52  jnz     short loc_18001BE62
0x18001be54  mov     edi, 8007000Eh
0x18001be59  mov     ecx, edi
0x18001be5b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001be60  jmp     short loc_18001BE81
0x18001be62  mov     rcx, rbx
0x18001be65  call    ?Init@?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@AEAAJXZ; CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>::Init(void)
0x18001be6a  mov     edi, eax
0x18001be6c  test    eax, eax
0x18001be6e  jns     short loc_18001BE74
0x18001be70  mov     ecx, eax
0x18001be72  jmp     short loc_18001BE5B
0x18001be74  mov     [rsp+48h+arg_18], r15
0x18001be79  mov     rsi, rbx
0x18001be7c  mov     [rsp+48h+arg_10], rbx
0x18001be81  mov     ecx, edi
0x18001be83  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001be88  lea     rcx, [rsp+48h+arg_18]
0x18001be8d  call    ??1?$SP@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@V?$SP_COM@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@@@QEAA@XZ; SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>::~SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>(void)
0x18001be92  test    edi, edi
0x18001be94  jns     short loc_18001BEA2
0x18001be96  mov     ecx, edi
0x18001be98  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001be9d  jmp     loc_18001BF2E
0x18001bea2  mov     rcx, r14; hLibModule
0x18001bea5  call    cs:__imp_DisableThreadLibraryCalls
0x18001beac  nop     dword ptr [rax+rax+00h]
0x18001beb1  mov     [rsp+48h+arg_10], r15
0x18001beb6  mov     cs:?g_pGlobalState@?$CComMainDllModuleT@V?$CSrvDllModuleT@VCEmptyType@@@@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@0PEAV?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@EA, rsi; CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>> * CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState
0x18001bebd  jmp     short loc_18001BF2E
0x18001bebf  mov     rbx, cs:?g_pGlobalState@?$CComMainDllModuleT@V?$CSrvDllModuleT@VCEmptyType@@@@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@0PEAV?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@EA; CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>> * CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState
0x18001bec6  test    rbx, rbx
0x18001bec9  jz      short loc_18001BF27
0x18001becb  or      eax, 0FFFFFFFFh
0x18001bece  lock xadd [rbx], eax
0x18001bed2  cmp     eax, 1
0x18001bed5  jnz     short loc_18001BF27
0x18001bed7  test    rbx, rbx
0x18001beda  jz      short loc_18001BF27
0x18001bedc  mov     rcx, [rbx+40h]; hObject
0x18001bee0  test    rcx, rcx
0x18001bee3  jz      short loc_18001BEF5
0x18001bee5  call    cs:__imp_CloseHandle
0x18001beec  nop     dword ptr [rax+rax+00h]
0x18001bef1  mov     [rbx+40h], r15
0x18001bef5  lea     rcx, [rbx+18h]
0x18001bef9  call    ??1?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAA@XZ; CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>(void)
0x18001befe  lea     rcx, [rbx+8]
0x18001bf02  call    ??1?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAA@XZ; CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>(void)
0x18001bf07  call    cs:__imp_GetProcessHeap
0x18001bf0e  nop     dword ptr [rax+rax+00h]
0x18001bf13  mov     r8, rbx; lpMem
0x18001bf16  xor     edx, edx; dwFlags
0x18001bf18  mov     rcx, rax; hHeap
0x18001bf1b  call    cs:__imp_HeapFree
0x18001bf22  nop     dword ptr [rax+rax+00h]
0x18001bf27  mov     cs:?g_pGlobalState@?$CComMainDllModuleT@V?$CSrvDllModuleT@VCEmptyType@@@@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@0PEAV?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@EA, r15; CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>> * CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState
0x18001bf2e  mov     ecx, edi
0x18001bf30  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001bf35  lea     rcx, [rsp+48h+arg_10]
0x18001bf3a  call    ??1?$SP@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@V?$SP_COM@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@@@QEAA@XZ; SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>::~SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>(void)
0x18001bf3f  test    edi, edi
0x18001bf41  jns     short loc_18001BF4C
0x18001bf43  mov     ecx, edi
0x18001bf45  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001bf4a  jmp     short loc_18001BFCB
0x18001bf4c  test    ebp, ebp
0x18001bf4e  jz      short loc_18001BFC6
0x18001bf50  cmp     ebp, 1
0x18001bf53  jnz     short loc_18001BFCB
0x18001bf55  call    ?OperatorsSafeGuardFunc@?$COverriddenOperatorsSafeGuardT@VCEmptyType@@@@SAJXZ; COverriddenOperatorsSafeGuardT<CEmptyType>::OperatorsSafeGuardFunc(void)
0x18001bf5a  mov     rbx, cs:?g_pFirst@?$CGlobalList@V?$CGlobalInitializer@$00@@@@2PEAV?$CGlobalInitializer@$00@@EA; CGlobalInitializer<1> * CGlobalList<CGlobalInitializer<1>>::g_pFirst
0x18001bf61  jmp     short loc_18001BFA3
0x18001bf63  cmp     [rbx+18h], r15d
0x18001bf67  jnz     short loc_18001BFA0
0x18001bf69  mov     rcx, [rbx+8]; Ptr
0x18001bf6d  call    cs:__imp_DecodePointer
0x18001bf74  nop     dword ptr [rax+rax+00h]
0x18001bf79  test    rax, rax
0x18001bf7c  jz      short loc_18001BF99
0x18001bf7e  mov     rcx, [rbx+8]; Ptr
0x18001bf82  call    cs:__imp_DecodePointer
0x18001bf89  nop     dword ptr [rax+rax+00h]
0x18001bf8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf93  mov     edi, eax
0x18001bf95  test    eax, eax
0x18001bf97  js      short loc_18001BFB8
0x18001bf99  mov     dword ptr [rbx+18h], 1
0x18001bfa0  mov     rbx, [rbx]
0x18001bfa3  test    rbx, rbx
0x18001bfa6  jnz     short loc_18001BF63
0x18001bfa8  mov     edi, r15d
0x18001bfab  mov     ecx, edi
0x18001bfad  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001bfb2  test    edi, edi
0x18001bfb4  jns     short loc_18001BFCB
0x18001bfb6  jmp     short loc_18001BF43
0x18001bfb8  mov     ecx, eax
0x18001bfba  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001bfbf  call    ?Done@?$CGlobalInitializer@$00@@SAJXZ; CGlobalInitializer<1>::Done(void)
0x18001bfc4  jmp     short loc_18001BFAB
0x18001bfc6  call    ?Done@?$CGlobalInitializer@$00@@SAJXZ; CGlobalInitializer<1>::Done(void)
0x18001bfcb  mov     ecx, edi
0x18001bfcd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001bfd2  mov     rbx, [rsp+48h+arg_0]
0x18001bfd7  mov     eax, edi
0x18001bfd9  add     rsp, 20h
0x18001bfdd  pop     r15
0x18001bfdf  pop     r14
0x18001bfe1  pop     rdi
0x18001bfe2  pop     rsi
0x18001bfe3  pop     rbp
0x18001bfe4  retn
```
