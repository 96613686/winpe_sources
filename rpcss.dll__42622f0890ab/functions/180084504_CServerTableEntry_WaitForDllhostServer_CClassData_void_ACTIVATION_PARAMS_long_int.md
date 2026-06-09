# CServerTableEntry::WaitForDllhostServer(CClassData *,void *,ACTIVATION_PARAMS *,long,int)

- ea: `0x180084504`
- end: `0x180084aad`
- name: `?WaitForDllhostServer@CServerTableEntry@@QEAAJPEAVCClassData@@PEAXPEAUACTIVATION_PARAMS@@JH@Z`
- size: `1449`
- prototype: `int(CServerTableEntry *__hidden this, struct CClassData *, void *, struct ACTIVATION_PARAMS *, int, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180067898`

## callees

- `0x1800030b4`
- `0x180003cd0`
- `0x180005c40`
- `0x180008648`
- `0x18000f1b8`
- `0x18002ba28`
- `0x18002f8cc`
- `0x180034540`
- `0x18004fc9c`
- `0x180055c44`
- `0x180081210`
- `0x180081830`
- `0x180084504`
- `0x18008b484`
- `0x18009df3c`
- `0x1800a203c`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180084967`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180084967`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18008495b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18008495b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800846e1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180084914`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800846e1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180084914`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800848cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800848cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008497a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084a86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008497a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084a86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008463c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800849c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180084a2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008463c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800849c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180084a2e`

## string_xrefs

- `0x180084576`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800849df`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180084a44`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180084a69`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180084a38`: `CServerTableEntry::WaitForDllhostServer`
- `0x180084a4b`: `Wait for dllhost server timed out, terminating server ClassIdentifier:%ws PID:%x`

## pseudocode

```c
__int64 __fastcall CServerTableEntry::WaitForDllhostServer(
        CServerTableEntry *this,
        HSTRING *a2,
        void *a3,
        struct ACTIVATION_PARAMS *a4,
        int a5,
        DWORD ExitCode)
{
  int v8; // eax
  __int64 v10; // rdi
  void *v11; // rax
  ActivationPropertiesIn *v12; // rcx
  int ActivationFlags; // eax
  unsigned int v14; // esi
  unsigned int matched; // r12d
  __int64 v17; // rax
  int v18; // r12d
  unsigned __int16 NativeArchitecture; // ax
  unsigned int v20; // eax
  int v21; // r8d
  int v22; // esi
  HSTRING v23; // rax
  int v24; // r13d
  int v25; // ebx
  CActivationStateList *v26; // rcx
  DWORD v27; // r12d
  bool v28; // zf
  __int64 v29; // rax
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  CProcess *v33; // rax
  struct ScmProcessReg *ProcessReg; // rbx
  bool v35; // cf
  DWORD v36; // eax
  void *v37; // rcx
  __int64 v38; // rax
  void (__fastcall *v39)(CServerTableEntry *, HSTRING *); // rbx
  __int64 v40; // r9
  wil::details::in1diag3 *v41; // rcx
  __int64 v42; // rdx
  unsigned int v43; // ebx
  int bAlertable; // [rsp+20h] [rbp-C9h]
  unsigned int bAlertablea; // [rsp+20h] [rbp-C9h]
  int v46; // [rsp+A8h] [rbp-41h]
  int v47; // [rsp+C0h] [rbp-29h]
  unsigned int v48; // [rsp+C4h] [rbp-25h]
  unsigned int dwMilliseconds; // [rsp+C8h] [rbp-21h]
  __int64 v50; // [rsp+D0h] [rbp-19h] BYREF
  PCWSTR StringRawBuffer; // [rsp+D8h] [rbp-11h]
  CProcess *v52; // [rsp+E0h] [rbp-9h]
  HANDLE Handles[9]; // [rsp+E8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+4Fh]
  HSTRING string; // [rsp+140h] [rbp+57h] BYREF
  BOOL v56; // [rsp+150h] [rbp+67h]
  int v57; // [rsp+158h] [rbp+6Fh]

  Handles[0] = a3;
  v50 = 0;
  v8 = -(ExitCode != 0);
  ExitCode = 0;
  dwMilliseconds = (v8 & 0xFFFF8ACF) + 30000;
  v10 = 0;
  v11 = (void *)*((_QWORD *)this + 3);
  v12 = (ActivationPropertiesIn *)(*((_QWORD *)a4 + 43) + 568LL);
  Handles[1] = v11;
  ActivationFlags = ActivationPropertiesIn::GetActivationFlags(v12, &ExitCode);
  v14 = ActivationFlags;
  if ( ActivationFlags < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC76,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
      (const char *)(unsigned int)ActivationFlags,
      bAlertable);
    return v14;
  }
  v48 = 0;
  v52 = 0;
  matched = ConvertActivationFlagsToMatchFlags(ExitCode);
  v17 = *((_QWORD *)a4 + 1);
  v18 = matched | 1;
  if ( v17 )
    NativeArchitecture = *(_WORD *)(v17 + 428);
  else
    NativeArchitecture = GetNativeArchitecture();
  v47 = NativeArchitecture;
  StringRawBuffer = 0;
  v56 = 0;
  v57 = 4;
  if ( a2 )
  {
    v20 = CClassData::AppIDFlags((CClassData *)a2);
    v22 = v18 | (v20 >> 3) & 0x200 | (32 * (v21 & v20)) | (v20 >> 3) & 0x1000 | (8 * (v20 & 0x80 | (4 * (v20 & 2))));
    if ( *((_BYTE *)a2 + 172) )
      StringRawBuffer = WindowsGetStringRawBuffer(a2[17], 0);
    else
      v22 |= 0x800u;
    LOBYTE(ExitCode) = 0;
    LOBYTE(string) = 0;
    CClassData::GetContextAndSubcontext(
      (struct CClassData *)a2,
      (unsigned __int8 *)&ExitCode,
      (unsigned __int8 *)&string);
    if ( (_BYTE)ExitCode == 3 )
      v56 = (_BYTE)string == 4;
    v23 = a2[11];
    if ( v23 )
      v24 = *((_DWORD *)v23 + 19);
    else
      v24 = -1;
    ExitCode = *((_DWORD *)a2 + 47);
  }
  else
  {
    v22 = v18;
    ExitCode = 0;
    v24 = -1;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
    || a2 )
  {
    v25 = *((_DWORD *)a2 + 33);
    v57 = v25;
  }
  else
  {
    v25 = 4;
  }
  v27 = WaitForMultipleObjectsEx(2u, Handles, 0, dwMilliseconds, 0);
  if ( !v27 )
    return 0;
  while ( v27 != 1 )
  {
    if ( v10 )
      goto LABEL_35;
    v28 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) == 0;
    v29 = *((_QWORD *)a4 + 1);
    if ( v28 )
    {
      if ( v29 )
        v32 = *(_QWORD *)(v29 + 32);
      else
        v32 = 0;
      LOBYTE(v46) = v56;
      v31 = CServerTableEntry::LookupServerOld(
              this,
              *((_QWORD *)a4 + 2),
              *((unsigned __int8 *)a4 + 188),
              *((unsigned int *)a4 + 48),
              v32,
              v22,
              v24,
              a5,
              *((_DWORD *)a4 + 32),
              *((_DWORD *)a4 + 104),
              v25,
              0,
              0,
              0,
              0,
              &GUID_NULL,
              0,
              0,
              StringRawBuffer,
              v47,
              ExitCode,
              v46,
              &v50);
    }
    else
    {
      if ( v29 )
        v30 = *(_QWORD *)(v29 + 32);
      else
        v30 = 0;
      LOBYTE(v46) = v56;
      v31 = CServerTableEntry::LookupServer(
              this,
              *((_QWORD *)a4 + 2),
              *((unsigned __int8 *)a4 + 188),
              *((unsigned int *)a4 + 48),
              v30,
              v22,
              v24,
              a5,
              *((_DWORD *)a4 + 32),
              *((_DWORD *)a4 + 104),
              v25,
              0,
              0,
              0,
              0,
              &GUID_NULL,
              0,
              0,
              StringRawBuffer,
              v47,
              ExitCode,
              v46,
              *((_QWORD *)a4 + 57),
              &v50);
    }
    if ( v31 )
    {
      v50 = 0;
LABEL_35:
      v33 = v52;
      goto LABEL_36;
    }
    v10 = v50;
    v33 = *(CProcess **)(v50 + 96);
    v52 = v33;
LABEL_36:
    if ( v33 && (ProcessReg = CProcess::GetProcessReg(v33)) != 0 )
    {
      v35 = GetTickCount() - *((_DWORD *)ProcessReg + 16) < 0x55D4A80;
    }
    else
    {
      v48 += 30000;
      v35 = v48 < 0x15F90;
    }
    if ( v35 )
    {
      v36 = WaitForMultipleObjectsEx(2u, Handles, 0, dwMilliseconds, 0);
      v25 = v57;
      v27 = v36;
      if ( v36 )
        continue;
    }
    break;
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( !v27 )
    return 0;
  CActivationStateList::ZeroPID(v26, *((_DWORD *)this + 4));
  v37 = (void *)*((_QWORD *)this + 3);
  ExitCode = 0;
  GetExitCodeProcess(v37, &ExitCode);
  TerminateProcess(*((HANDLE *)this + 3), 0);
  v38 = *(_QWORD *)this;
  string = 0;
  v39 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v38 + 32);
  WindowsDeleteString(0);
  string = 0;
  v39(this, &string);
  if ( v27 == 1 )
  {
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      WindowsGetStringRawBuffer(string, 0);
      ComTraceMessageT<unsigned long,unsigned short const *,unsigned long>();
    }
    v40 = ExitCode;
    v41 = retaddr;
    if ( ExitCode )
    {
      v42 = 3374;
      goto LABEL_59;
    }
    v43 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD33,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
      (const char *)0x80004005LL,
      bAlertablea);
  }
  else
  {
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      WindowsGetStringRawBuffer(string, 0);
      ComTraceMessageT<unsigned __int64,unsigned long>(
        (__int64)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (__int64)"CServerTableEntry::WaitForDllhostServer",
        0xD39u,
        0,
        (__int64)L"Wait for dllhost server timed out, terminating server ClassIdentifier:%ws PID:%x");
    }
    v41 = retaddr;
    v40 = 1460;
    v42 = 3386;
LABEL_59:
    v43 = wil::details::in1diag3::Return_Win32(
            v41,
            (void *)v42,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
            (const char *)v40,
            bAlertablea);
  }
  WindowsDeleteString(string);
  return v43;
}

```

## disassembly

```asm
0x180084504  mov     [rsp-8+arg_8], rbx
0x180084509  push    rbp
0x18008450a  push    rsi
0x18008450b  push    rdi
0x18008450c  push    r12
0x18008450e  push    r13
0x180084510  push    r14
0x180084512  push    r15
0x180084514  lea     rbp, [rsp-17h]
0x180084519  sub     rsp, 100h
0x180084520  xor     r13d, r13d
0x180084523  mov     [rbp+47h+Handles], r8
0x180084527  neg     [rbp+47h+ExitCode]
0x18008452a  mov     r14, rcx
0x18008452d  mov     rbx, rdx
0x180084530  mov     [rbp+47h+var_60], r13
0x180084534  sbb     eax, eax
0x180084536  mov     [rbp+47h+ExitCode], r13d
0x18008453a  and     eax, 0FFFF8ACFh
0x18008453f  lea     rdx, [rbp+47h+ExitCode]; unsigned int *
0x180084543  add     eax, 7530h
0x180084548  mov     r15, r9
0x18008454b  mov     [rbp+47h+dwMilliseconds], eax
0x18008454e  mov     edi, r13d
0x180084551  mov     rax, [rcx+18h]
0x180084555  mov     rcx, [r9+158h]
0x18008455c  add     rcx, 238h; this
0x180084563  mov     [rbp+47h+var_40], rax
0x180084567  call    ?GetActivationFlags@ActivationPropertiesIn@@UEAAJPEAK@Z; ActivationPropertiesIn::GetActivationFlags(ulong *)
0x18008456c  mov     esi, eax
0x18008456e  test    eax, eax
0x180084570  jns     short loc_180084591
0x180084572  mov     rcx, [rbp+4Fh]; this
0x180084576  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18008457d  mov     r9d, eax; char *
0x180084580  mov     edx, 0C76h; void *
0x180084585  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008458a  mov     eax, esi
0x18008458c  jmp     loc_180084A92
0x180084591  mov     ecx, [rbp+47h+ExitCode]; unsigned int
0x180084594  mov     [rbp+47h+var_6C], r13d
0x180084598  mov     [rbp+47h+var_50], r13
0x18008459c  call    ?ConvertActivationFlagsToMatchFlags@@YAKK@Z; ConvertActivationFlagsToMatchFlags(ulong)
0x1800845a1  mov     r12d, eax
0x1800845a4  mov     r8d, 1
0x1800845aa  mov     rax, [r15+8]
0x1800845ae  or      r12d, r8d
0x1800845b1  test    rax, rax
0x1800845b4  jz      short loc_1800845BF
0x1800845b6  movzx   eax, word ptr [rax+1ACh]
0x1800845bd  jmp     short loc_1800845CA
0x1800845bf  call    ?GetNativeArchitecture@@YAGXZ; GetNativeArchitecture(void)
0x1800845c4  mov     r8d, 1
0x1800845ca  movzx   eax, ax
0x1800845cd  mov     [rbp+47h+var_70], eax
0x1800845d0  mov     [rbp+47h+var_58], r13
0x1800845d4  mov     [rbp+47h+arg_10], r13d
0x1800845d8  mov     [rbp+47h+arg_18], 4
0x1800845df  test    rbx, rbx
0x1800845e2  jz      loc_18008469F
0x1800845e8  mov     rcx, rbx; this
0x1800845eb  call    ?AppIDFlags@CClassData@@QEAAKXZ; CClassData::AppIDFlags(void)
0x1800845f0  mov     edx, eax
0x1800845f2  mov     esi, eax
0x1800845f4  shr     edx, 3
0x1800845f7  and     esi, 2
0x1800845fa  mov     ecx, eax
0x1800845fc  shl     esi, 2
0x1800845ff  and     ecx, 80h
0x180084605  or      esi, ecx
0x180084607  and     edx, 200h
0x18008460d  shl     esi, 3
0x180084610  mov     ecx, eax
0x180084612  shr     ecx, 3
0x180084615  and     eax, r8d
0x180084618  and     ecx, 1000h
0x18008461e  shl     eax, 5
0x180084621  or      esi, ecx
0x180084623  or      esi, eax
0x180084625  or      esi, edx
0x180084627  or      esi, r12d
0x18008462a  cmp     [rbx+0ACh], dil
0x180084631  jz      short loc_180084648
0x180084633  mov     rcx, [rbx+88h]; string
0x18008463a  xor     edx, edx; length
0x18008463c  call    cs:__imp_WindowsGetStringRawBuffer
0x180084642  mov     [rbp+47h+var_58], rax
0x180084646  jmp     short loc_18008464C
0x180084648  bts     esi, 0Bh
0x18008464c  lea     r8, [rbp+47h+string]; unsigned __int8 *
0x180084650  mov     byte ptr [rbp+47h+ExitCode], dil
0x180084654  lea     rdx, [rbp+47h+ExitCode]; unsigned __int8 *
0x180084658  mov     byte ptr [rbp+47h+string], dil
0x18008465c  mov     rcx, rbx; this
0x18008465f  call    ?GetContextAndSubcontext@CClassData@@SAXPEAV1@PEAE1@Z; CClassData::GetContextAndSubcontext(CClassData *,uchar *,uchar *)
0x180084664  cmp     byte ptr [rbp+47h+ExitCode], 3
0x180084668  jnz     short loc_18008467F
0x18008466a  cmp     byte ptr [rbp+47h+string], 4
0x18008466e  mov     eax, 1
0x180084673  movzx   r13d, r13b
0x180084677  cmovz   r13d, eax
0x18008467b  mov     [rbp+47h+arg_10], r13d
0x18008467f  mov     rax, [rbx+58h]
0x180084683  test    rax, rax
0x180084686  jz      short loc_18008468E
0x180084688  mov     r13d, [rax+4Ch]
0x18008468c  jmp     short loc_180084692
0x18008468e  or      r13d, 0FFFFFFFFh
0x180084692  mov     r12d, [rbx+0BCh]
0x180084699  mov     [rbp+47h+ExitCode], r12d
0x18008469d  jmp     short loc_1800846A9
0x18008469f  mov     esi, r12d
0x1800846a2  mov     [rbp+47h+ExitCode], edi
0x1800846a5  or      r13d, 0FFFFFFFFh
0x1800846a9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800846b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800846b5  test    al, al
0x1800846b7  jnz     short loc_1800846C5
0x1800846b9  test    rbx, rbx
0x1800846bc  jnz     short loc_1800846C5
0x1800846be  mov     ebx, 4
0x1800846c3  jmp     short loc_1800846CE
0x1800846c5  mov     ebx, [rbx+84h]
0x1800846cb  mov     [rbp+47h+arg_18], ebx
0x1800846ce  mov     r9d, [rbp+47h+dwMilliseconds]; dwMilliseconds
0x1800846d2  lea     rdx, [rbp+47h+Handles]; lpHandles
0x1800846d6  xor     r8d, r8d; bWaitAll
0x1800846d9  mov     [rsp+130h+bAlertable], edi; bAlertable
0x1800846dd  lea     ecx, [r8+2]; nCount
0x1800846e1  call    cs:__imp_WaitForMultipleObjectsEx
0x1800846e7  mov     r12d, eax
0x1800846ea  test    eax, eax
0x1800846ec  jz      loc_180084A90
0x1800846f2  cmp     r12d, 1
0x1800846f6  jz      loc_180084928
0x1800846fc  test    rdi, rdi
0x1800846ff  jnz     loc_1800848B4
0x180084705  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18008470c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180084711  test    al, al
0x180084713  mov     rax, [r15+8]
0x180084717  jz      loc_1800847EF
0x18008471d  mov     rdx, [r15+1C8h]
0x180084724  mov     r9d, [r15+1A0h]
0x18008472b  mov     r10d, [r15+80h]
0x180084732  test    rax, rax
0x180084735  jz      short loc_18008473D
0x180084737  mov     rcx, [rax+20h]
0x18008473b  jmp     short loc_180084740
0x18008473d  mov     rcx, rdi
0x180084740  movzx   r8d, byte ptr [r15+0BCh]
0x180084748  lea     rax, [rbp+47h+var_60]
0x18008474c  mov     [rsp+130h+var_78], rax
0x180084754  mov     eax, [rbp+47h+arg_10]
0x180084757  mov     [rsp+130h+var_80], rdx
0x18008475f  mov     rdx, [r15+10h]
0x180084763  mov     [rsp+130h+var_88], al
0x18008476a  mov     eax, [rbp+47h+ExitCode]
0x18008476d  mov     [rsp+130h+var_90], eax
0x180084774  mov     eax, [rbp+47h+var_70]
0x180084777  mov     [rsp+130h+var_98], eax
0x18008477e  mov     rax, [rbp+47h+var_58]
0x180084782  mov     [rsp+130h+var_A0], rax
0x18008478a  lea     rax, GUID_NULL
0x180084791  mov     [rsp+130h+var_A8], rdi
0x180084799  mov     [rsp+130h+var_B0], rdi
0x1800847a1  mov     [rsp+130h+var_B8], rax
0x1800847a6  mov     eax, [rbp+47h+arg_20]
0x1800847a9  mov     [rsp+130h+var_C0], rdi
0x1800847ae  mov     [rsp+130h+var_C8], rdi
0x1800847b3  mov     [rsp+130h+var_D0], edi
0x1800847b7  mov     [rsp+130h+var_D8], edi
0x1800847bb  mov     [rsp+130h+var_E0], ebx
0x1800847bf  mov     [rsp+130h+var_E8], r9d
0x1800847c4  mov     r9d, [r15+0C0h]
0x1800847cb  mov     [rsp+130h+var_F0], r10d
0x1800847d0  mov     [rsp+130h+var_F8], eax
0x1800847d4  mov     dword ptr [rsp+130h+var_100], r13d
0x1800847d9  mov     dword ptr [rsp+130h+var_108], esi
0x1800847dd  mov     qword ptr [rsp+130h+bAlertable], rcx
0x1800847e2  mov     rcx, r14
0x1800847e5  call    ?LookupServer@CServerTableEntry@@QEAAJPEAVCToken@@HHPEAGKW4ServerProtectionLevel@@JJKW4_PSM_ACTIVATE_BACKGROUND_TYPE@@KKPEA_K_KAEBU_GUID@@0PEAUtagBLOB@@PEBGKK_N8PEAPEAVCServerListEntry@@@Z; CServerTableEntry::LookupServer(CToken *,int,int,ushort *,ulong,ServerProtectionLevel,long,long,ulong,_PSM_ACTIVATE_BACKGROUND_TYPE,ulong,ulong,unsigned __int64 *,unsigned __int64,_GUID const &,CToken *,tagBLOB *,ushort const *,ulong,ulong,bool,ushort const *,CServerListEntry * *)
0x1800847ea  jmp     loc_1800848AC
0x1800847ef  mov     edx, [r15+1A0h]
0x1800847f6  mov     r9d, [r15+80h]
0x1800847fd  test    rax, rax
0x180084800  jz      short loc_180084808
0x180084802  mov     rcx, [rax+20h]
0x180084806  jmp     short loc_18008480B
0x180084808  mov     rcx, rdi
0x18008480b  movzx   r8d, byte ptr [r15+0BCh]
0x180084813  lea     rax, [rbp+47h+var_60]
0x180084817  mov     [rsp+130h+var_80], rax
0x18008481f  mov     eax, [rbp+47h+arg_10]
0x180084822  mov     [rsp+130h+var_88], al
0x180084829  mov     eax, [rbp+47h+ExitCode]
0x18008482c  mov     [rsp+130h+var_90], eax
0x180084833  mov     eax, [rbp+47h+var_70]
0x180084836  mov     [rsp+130h+var_98], eax
0x18008483d  mov     rax, [rbp+47h+var_58]
0x180084841  mov     [rsp+130h+var_A0], rax
0x180084849  lea     rax, GUID_NULL
0x180084850  mov     [rsp+130h+var_A8], rdi
0x180084858  mov     [rsp+130h+var_B0], rdi
0x180084860  mov     [rsp+130h+var_B8], rax
0x180084865  mov     eax, [rbp+47h+arg_20]
0x180084868  mov     [rsp+130h+var_C0], rdi
0x18008486d  mov     [rsp+130h+var_C8], rdi
0x180084872  mov     [rsp+130h+var_D0], edi
0x180084876  mov     [rsp+130h+var_D8], edi
0x18008487a  mov     [rsp+130h+var_E0], ebx
0x18008487e  mov     [rsp+130h+var_E8], edx
0x180084882  mov     rdx, [r15+10h]
0x180084886  mov     [rsp+130h+var_F0], r9d
0x18008488b  mov     r9d, [r15+0C0h]
0x180084892  mov     [rsp+130h+var_F8], eax
0x180084896  mov     dword ptr [rsp+130h+var_100], r13d
0x18008489b  mov     dword ptr [rsp+130h+var_108], esi
0x18008489f  mov     qword ptr [rsp+130h+bAlertable], rcx
0x1800848a4  mov     rcx, r14
0x1800848a7  call    ?LookupServerOld@CServerTableEntry@@QEAAJPEAVCToken@@HHPEAGKW4ServerProtectionLevel@@JJKW4_PSM_ACTIVATE_BACKGROUND_TYPE@@KKPEA_K_KAEBU_GUID@@0PEAUtagBLOB@@PEBGKK_NPEAPEAVCServerListEntry@@@Z; CServerTableEntry::LookupServerOld(CToken *,int,int,ushort *,ulong,ServerProtectionLevel,long,long,ulong,_PSM_ACTIVATE_BACKGROUND_TYPE,ulong,ulong,unsigned __int64 *,unsigned __int64,_GUID const &,CToken *,tagBLOB *,ushort const *,ulong,ulong,bool,CServerListEntry * *)
0x1800848ac  test    eax, eax
0x1800848ae  jz      short loc_1800848DD
0x1800848b0  mov     [rbp+47h+var_60], rdi
0x1800848b4  mov     rax, [rbp+47h+var_50]
0x1800848b8  test    rax, rax
0x1800848bb  jz      short loc_1800848EB
0x1800848bd  mov     rcx, rax; this
0x1800848c0  call    ?GetProcessReg@CProcess@@QEAAPEAUScmProcessReg@@XZ; CProcess::GetProcessReg(void)
0x1800848c5  mov     rbx, rax
0x1800848c8  test    rax, rax
0x1800848cb  jz      short loc_1800848EB
0x1800848cd  call    cs:__imp_GetTickCount
0x1800848d3  sub     eax, [rbx+40h]
0x1800848d6  cmp     eax, 55D4A80h
0x1800848db  jmp     short loc_1800848FB
0x1800848dd  mov     rdi, [rbp+47h+var_60]
0x1800848e1  mov     rax, [rdi+60h]
0x1800848e5  mov     [rbp+47h+var_50], rax
0x1800848e9  jmp     short loc_1800848B8
0x1800848eb  mov     eax, [rbp+47h+var_6C]
0x1800848ee  add     eax, 7530h
0x1800848f3  mov     [rbp+47h+var_6C], eax
0x1800848f6  cmp     eax, 15F90h
0x1800848fb  jnb     short loc_180084928
0x1800848fd  mov     r9d, [rbp+47h+dwMilliseconds]; dwMilliseconds
0x180084901  lea     rdx, [rbp+47h+Handles]; lpHandles
0x180084905  xor     r8d, r8d; bWaitAll
0x180084908  mov     [rsp+130h+bAlertable], 0; int
0x180084910  lea     ecx, [r8+2]; nCount
0x180084914  call    cs:__imp_WaitForMultipleObjectsEx
0x18008491a  mov     ebx, [rbp+47h+arg_18]
0x18008491d  mov     r12d, eax
0x180084920  test    eax, eax
0x180084922  jnz     loc_1800846F2
0x180084928  xor     esi, esi
0x18008492a  test    rdi, rdi
0x18008492d  jz      short loc_18008493E
0x18008492f  mov     rax, [rdi]
0x180084932  mov     rcx, rdi
0x180084935  mov     rax, [rax+10h]
0x180084939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008493e  test    r12d, r12d
0x180084941  jz      loc_180084A90
0x180084947  mov     edx, [r14+10h]; unsigned int
0x18008494b  call    ?ZeroPID@CActivationStateList@@QEAAXK@Z; CActivationStateList::ZeroPID(ulong)
0x180084950  mov     rcx, [r14+18h]; hProcess
0x180084954  lea     rdx, [rbp+47h+ExitCode]; lpExitCode
0x180084958  mov     [rbp+47h+ExitCode], esi
0x18008495b  call    cs:__imp_GetExitCodeProcess
0x180084961  mov     rcx, [r14+18h]; hProcess
0x180084965  xor     edx, edx; uExitCode
0x180084967  call    cs:__imp_TerminateProcess
0x18008496d  mov     rax, [r14]
0x180084970  xor     ecx, ecx; string
0x180084972  mov     [rbp+47h+string], rsi
0x180084976  mov     rbx, [rax+20h]
0x18008497a  call    cs:__imp_WindowsDeleteString
0x180084980  lea     rdx, [rbp+47h+string]
0x180084984  mov     [rbp+47h+string], rsi
0x180084988  mov     rcx, r14
0x18008498b  mov     rax, rbx
0x18008498e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084993  mov     eax, cs:dword_18014E4B8
0x180084999  cmp     r12d, 1
0x18008499d  jnz     short loc_180084A0D
0x18008499f  test    eax, eax
0x1800849a1  jnz     short loc_1800849B6
0x1800849a3  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x1800849a9  jz      short loc_1800849DB
0x1800849ab  xor     ecx, ecx
0x1800849ad  call    IsWppLevelEnabled
0x1800849b2  test    al, al
0x1800849b4  jz      short loc_1800849DB
0x1800849b6  mov     rcx, [rbp+47h+string]; string
0x1800849ba  xor     edx, edx; length
0x1800849bc  mov     ebx, [r14+10h]
0x1800849c0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800849c6  mov     [rsp+130h+var_F8], ebx
0x1800849ca  mov     [rsp+130h+var_100], rax
  ... truncated ...
```
