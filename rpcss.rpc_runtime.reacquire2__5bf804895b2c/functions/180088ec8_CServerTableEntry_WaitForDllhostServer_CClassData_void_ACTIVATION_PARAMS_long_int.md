# CServerTableEntry::WaitForDllhostServer(CClassData *,void *,ACTIVATION_PARAMS *,long,int)

- ea: `0x180088ec8`
- end: `0x1800894ae`
- name: `?WaitForDllhostServer@CServerTableEntry@@QEAAJPEAVCClassData@@PEAXPEAUACTIVATION_PARAMS@@JH@Z`
- size: `1510`
- prototype: `int(CServerTableEntry *__hidden this, struct CClassData *, void *, struct ACTIVATION_PARAMS *, int, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006c680`

## callees

- `0x1800065a4`
- `0x18000902c`
- `0x180013b18`
- `0x1800210f8`
- `0x180025950`
- `0x180034260`
- `0x180034c74`
- `0x180050fd0`
- `0x1800522a0`
- `0x18005232c`
- `0x1800855d8`
- `0x180085b7c`
- `0x180088ec8`
- `0x1800902a4`
- `0x1800905d0`
- `0x1800a77c8`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180089349`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180089349`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180089337`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180089337`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800890ab`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800892ea`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800890ab`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800892ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008929d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008929d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089362`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089480`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089362`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089480`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180089000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800893ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180089422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180089000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800893ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180089422`

## string_xrefs

- `0x180088f3a`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800893d3`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18008943e`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180089463`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180089432`: `CServerTableEntry::WaitForDllhostServer`
- `0x180089445`: `Wait for dllhost server timed out, terminating server ClassIdentifier:%ws PID:%x`

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
  void *v10; // rax
  ActivationPropertiesIn *v11; // rcx
  int ActivationFlags; // eax
  unsigned int v13; // esi
  CActivationStateList *v15; // rcx
  DWORD v16; // r12d
  bool v17; // zf
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  CProcess *v22; // rax
  struct ScmProcessReg *ProcessReg; // rbx
  bool v24; // cf
  void *v25; // rcx
  __int64 v26; // rax
  void (__fastcall *v27)(CServerTableEntry *, HSTRING *); // rbx
  int v28; // ebx
  PCWSTR StringRawBuffer; // rax
  int v30; // edx
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  __int64 v34; // r9
  wil::details::in1diag3 *v35; // rcx
  __int64 v36; // rdx
  unsigned int v37; // ebx
  int bAlertable; // [rsp+20h] [rbp-C9h]
  unsigned int bAlertablea; // [rsp+20h] [rbp-C9h]
  unsigned int v40; // [rsp+C4h] [rbp-25h]
  unsigned int dwMilliseconds; // [rsp+C8h] [rbp-21h]
  CProcess *v42; // [rsp+E0h] [rbp-9h]
  HANDLE Handles[9]; // [rsp+E8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+4Fh]
  HSTRING string; // [rsp+140h] [rbp+57h] BYREF
  BOOL v46; // [rsp+150h] [rbp+67h]
  int v47; // [rsp+158h] [rbp+6Fh]

  Handles[0] = a3;
  v8 = -(ExitCode != 0);
  ExitCode = 0;
  dwMilliseconds = (v8 & 0xFFFF8ACF) + 30000;
  v10 = (void *)*((_QWORD *)this + 3);
  v11 = (ActivationPropertiesIn *)(*((_QWORD *)a4 + 43) + 568LL);
  Handles[1] = v10;
  ActivationFlags = ActivationPropertiesIn::GetActivationFlags(v11, &ExitCode);
  v13 = ActivationFlags;
  if ( ActivationFlags < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC76,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
      (const char *)(unsigned int)ActivationFlags,
      bAlertable);
    return v13;
  }
  v40 = 0;
  v42 = 0;
  ConvertActivationFlagsToMatchFlags(ExitCode);
  if ( !*((_QWORD *)a4 + 1) )
    GetNativeArchitecture();
  v46 = 0;
  v47 = 4;
  if ( a2 )
  {
    CClassData::AppIDFlags((CClassData *)a2);
    if ( *((_BYTE *)a2 + 172) )
      WindowsGetStringRawBuffer(a2[17], 0);
    LOBYTE(ExitCode) = 0;
    LOBYTE(string) = 0;
    CClassData::GetContextAndSubcontext(
      (struct CClassData *)a2,
      (unsigned __int8 *)&ExitCode,
      (unsigned __int8 *)&string);
    if ( (_BYTE)ExitCode == 3 )
      v46 = (_BYTE)string == 4;
    ExitCode = *((_DWORD *)a2 + 47);
  }
  else
  {
    ExitCode = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
    || a2 )
  {
    v47 = *((_DWORD *)a2 + 33);
  }
  v16 = WaitForMultipleObjectsEx(2u, Handles, 0, dwMilliseconds, 0);
  if ( v16 )
  {
    do
    {
      if ( v16 == 1 )
        break;
      v17 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) == 0;
      v18 = *((_QWORD *)a4 + 1);
      if ( v17 )
      {
        if ( v18 )
          v21 = *(_QWORD *)(v18 + 32);
        else
          LODWORD(v21) = 0;
        bAlertablea = v21;
        v20 = CServerTableEntry::LookupServerOld(
                this,
                *((_QWORD *)a4 + 2),
                *((unsigned __int8 *)a4 + 188),
                *((unsigned int *)a4 + 48));
      }
      else
      {
        if ( v18 )
          v19 = *(_QWORD *)(v18 + 32);
        else
          LODWORD(v19) = 0;
        bAlertablea = v19;
        v20 = CServerTableEntry::LookupServer(
                this,
                *((_QWORD *)a4 + 2),
                *((unsigned __int8 *)a4 + 188),
                *((unsigned int *)a4 + 48));
      }
      if ( v20 )
      {
        v22 = v42;
      }
      else
      {
        v22 = (CProcess *)MEMORY[0x60];
        v42 = (CProcess *)MEMORY[0x60];
      }
      if ( v22 && (ProcessReg = CProcess::GetProcessReg(v22)) != 0 )
      {
        v24 = GetTickCount() - *((_DWORD *)ProcessReg + 16) < 0x55D4A80;
      }
      else
      {
        v40 += 30000;
        v24 = v40 < 0x15F90;
      }
      if ( !v24 )
        break;
      v16 = WaitForMultipleObjectsEx(2u, Handles, 0, dwMilliseconds, 0);
    }
    while ( v16 );
    if ( v16 )
    {
      CActivationStateList::ZeroPID(v15, *((_DWORD *)this + 4));
      v25 = (void *)*((_QWORD *)this + 3);
      ExitCode = 0;
      GetExitCodeProcess(v25, &ExitCode);
      TerminateProcess(*((HANDLE *)this + 3), 0);
      v26 = *(_QWORD *)this;
      string = 0;
      v27 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v26 + 32);
      WindowsDeleteString(0);
      string = 0;
      v27(this, &string);
      if ( v16 == 1 )
      {
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v28 = *((_DWORD *)this + 4);
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          ComTraceMessageT<unsigned long,unsigned short const *,unsigned long>(
            v31,
            v30,
            v32,
            v33,
            bAlertablea,
            ExitCode,
            (__int64)StringRawBuffer,
            v28);
        }
        v34 = ExitCode;
        v35 = retaddr;
        if ( !ExitCode )
        {
          v37 = -2147467259;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD33,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
            (const char *)0x80004005LL,
            bAlertablea);
LABEL_50:
          WindowsDeleteString(string);
          return v37;
        }
        v36 = 3374;
      }
      else
      {
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          WindowsGetStringRawBuffer(string, 0);
          ComTraceMessageT<unsigned __int64,unsigned long>(
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
            (unsigned int)"CServerTableEntry::WaitForDllhostServer",
            3385,
            0,
            (__int64)L"Wait for dllhost server timed out, terminating server ClassIdentifier:%ws PID:%x");
        }
        v35 = retaddr;
        v34 = 1460;
        v36 = 3386;
      }
      v37 = wil::details::in1diag3::Return_Win32(
              v35,
              (void *)v36,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
              (const char *)v34,
              bAlertablea);
      goto LABEL_50;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180088ec8  mov     [rsp-8+arg_8], rbx
0x180088ecd  push    rbp
0x180088ece  push    rsi
0x180088ecf  push    rdi
0x180088ed0  push    r12
0x180088ed2  push    r13
0x180088ed4  push    r14
0x180088ed6  push    r15
0x180088ed8  lea     rbp, [rsp-17h]
0x180088edd  sub     rsp, 100h
0x180088ee4  xor     r13d, r13d
0x180088ee7  mov     [rbp+47h+Handles], r8
0x180088eeb  neg     [rbp+47h+ExitCode]
0x180088eee  mov     r14, rcx
0x180088ef1  mov     rbx, rdx
0x180088ef4  mov     [rbp+47h+var_60], r13
0x180088ef8  sbb     eax, eax
0x180088efa  mov     [rbp+47h+ExitCode], r13d
0x180088efe  and     eax, 0FFFF8ACFh
0x180088f03  lea     rdx, [rbp+47h+ExitCode]; unsigned int *
0x180088f07  add     eax, 7530h
0x180088f0c  mov     r15, r9
0x180088f0f  mov     [rbp+47h+dwMilliseconds], eax
0x180088f12  mov     edi, r13d
0x180088f15  mov     rax, [rcx+18h]
0x180088f19  mov     rcx, [r9+158h]
0x180088f20  add     rcx, 238h; this
0x180088f27  mov     [rbp+47h+var_40], rax
0x180088f2b  call    ?GetActivationFlags@ActivationPropertiesIn@@UEAAJPEAK@Z; ActivationPropertiesIn::GetActivationFlags(ulong *)
0x180088f30  mov     esi, eax
0x180088f32  test    eax, eax
0x180088f34  jns     short loc_180088F55
0x180088f36  mov     rcx, [rbp+4Fh]; this
0x180088f3a  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180088f41  mov     r9d, eax; char *
0x180088f44  mov     edx, 0C76h; void *
0x180088f49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088f4e  mov     eax, esi
0x180088f50  jmp     loc_180089492
0x180088f55  mov     ecx, [rbp+47h+ExitCode]; unsigned int
0x180088f58  mov     [rbp+47h+var_6C], r13d
0x180088f5c  mov     [rbp+47h+var_50], r13
0x180088f60  call    ?ConvertActivationFlagsToMatchFlags@@YAKK@Z; ConvertActivationFlagsToMatchFlags(ulong)
0x180088f65  mov     r12d, eax
0x180088f68  mov     r8d, 1
0x180088f6e  mov     rax, [r15+8]
0x180088f72  or      r12d, r8d
0x180088f75  test    rax, rax
0x180088f78  jz      short loc_180088F83
0x180088f7a  movzx   eax, word ptr [rax+1ACh]
0x180088f81  jmp     short loc_180088F8E
0x180088f83  call    ?GetNativeArchitecture@@YAGXZ; GetNativeArchitecture(void)
0x180088f88  mov     r8d, 1
0x180088f8e  movzx   eax, ax
0x180088f91  mov     [rbp+47h+var_70], eax
0x180088f94  mov     [rbp+47h+var_58], r13
0x180088f98  mov     [rbp+47h+arg_10], r13d
0x180088f9c  mov     [rbp+47h+arg_18], 4
0x180088fa3  test    rbx, rbx
0x180088fa6  jz      loc_180089069
0x180088fac  mov     rcx, rbx; this
0x180088faf  call    ?AppIDFlags@CClassData@@QEAAKXZ; CClassData::AppIDFlags(void)
0x180088fb4  mov     edx, eax
0x180088fb6  mov     esi, eax
0x180088fb8  shr     edx, 3
0x180088fbb  and     esi, 2
0x180088fbe  mov     ecx, eax
0x180088fc0  shl     esi, 2
0x180088fc3  and     ecx, 80h
0x180088fc9  or      esi, ecx
0x180088fcb  and     edx, 200h
0x180088fd1  shl     esi, 3
0x180088fd4  mov     ecx, eax
0x180088fd6  shr     ecx, 3
0x180088fd9  and     eax, r8d
0x180088fdc  and     ecx, 1000h
0x180088fe2  shl     eax, 5
0x180088fe5  or      esi, ecx
0x180088fe7  or      esi, eax
0x180088fe9  or      esi, edx
0x180088feb  or      esi, r12d
0x180088fee  cmp     [rbx+0ACh], dil
0x180088ff5  jz      short loc_180089012
0x180088ff7  mov     rcx, [rbx+88h]; string
0x180088ffe  xor     edx, edx; length
0x180089000  call    cs:__imp_WindowsGetStringRawBuffer
0x180089007  nop     dword ptr [rax+rax+00h]
0x18008900c  mov     [rbp+47h+var_58], rax
0x180089010  jmp     short loc_180089016
0x180089012  bts     esi, 0Bh
0x180089016  lea     r8, [rbp+47h+string]; unsigned __int8 *
0x18008901a  mov     byte ptr [rbp+47h+ExitCode], dil
0x18008901e  lea     rdx, [rbp+47h+ExitCode]; unsigned __int8 *
0x180089022  mov     byte ptr [rbp+47h+string], dil
0x180089026  mov     rcx, rbx; this
0x180089029  call    ?GetContextAndSubcontext@CClassData@@SAXPEAV1@PEAE1@Z; CClassData::GetContextAndSubcontext(CClassData *,uchar *,uchar *)
0x18008902e  cmp     byte ptr [rbp+47h+ExitCode], 3
0x180089032  jnz     short loc_180089049
0x180089034  cmp     byte ptr [rbp+47h+string], 4
0x180089038  mov     eax, 1
0x18008903d  movzx   r13d, r13b
0x180089041  cmovz   r13d, eax
0x180089045  mov     [rbp+47h+arg_10], r13d
0x180089049  mov     rax, [rbx+58h]
0x18008904d  test    rax, rax
0x180089050  jz      short loc_180089058
0x180089052  mov     r13d, [rax+4Ch]
0x180089056  jmp     short loc_18008905C
0x180089058  or      r13d, 0FFFFFFFFh
0x18008905c  mov     r12d, [rbx+0BCh]
0x180089063  mov     [rbp+47h+ExitCode], r12d
0x180089067  jmp     short loc_180089073
0x180089069  mov     esi, r12d
0x18008906c  mov     [rbp+47h+ExitCode], edi
0x18008906f  or      r13d, 0FFFFFFFFh
0x180089073  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18008907a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18008907f  test    al, al
0x180089081  jnz     short loc_18008908F
0x180089083  test    rbx, rbx
0x180089086  jnz     short loc_18008908F
0x180089088  mov     ebx, 4
0x18008908d  jmp     short loc_180089098
0x18008908f  mov     ebx, [rbx+84h]
0x180089095  mov     [rbp+47h+arg_18], ebx
0x180089098  mov     r9d, [rbp+47h+dwMilliseconds]; dwMilliseconds
0x18008909c  lea     rdx, [rbp+47h+Handles]; lpHandles
0x1800890a0  xor     r8d, r8d; bWaitAll
0x1800890a3  mov     [rsp+130h+bAlertable], edi; bAlertable
0x1800890a7  lea     ecx, [r8+2]; nCount
0x1800890ab  call    cs:__imp_WaitForMultipleObjectsEx
0x1800890b2  nop     dword ptr [rax+rax+00h]
0x1800890b7  mov     r12d, eax
0x1800890ba  test    eax, eax
0x1800890bc  jz      loc_180089490
0x1800890c2  cmp     r12d, 1
0x1800890c6  jz      loc_180089304
0x1800890cc  test    rdi, rdi
0x1800890cf  jnz     loc_180089284
0x1800890d5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800890dc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800890e1  test    al, al
0x1800890e3  mov     rax, [r15+8]
0x1800890e7  jz      loc_1800891BF
0x1800890ed  mov     rdx, [r15+1C8h]
0x1800890f4  mov     r9d, [r15+1A0h]
0x1800890fb  mov     r10d, [r15+80h]
0x180089102  test    rax, rax
0x180089105  jz      short loc_18008910D
0x180089107  mov     rcx, [rax+20h]
0x18008910b  jmp     short loc_180089110
0x18008910d  mov     rcx, rdi
0x180089110  movzx   r8d, byte ptr [r15+0BCh]
0x180089118  lea     rax, [rbp+47h+var_60]
0x18008911c  mov     [rsp+130h+var_78], rax
0x180089124  mov     eax, [rbp+47h+arg_10]
0x180089127  mov     [rsp+130h+var_80], rdx
0x18008912f  mov     rdx, [r15+10h]
0x180089133  mov     [rsp+130h+var_88], al
0x18008913a  mov     eax, [rbp+47h+ExitCode]
0x18008913d  mov     [rsp+130h+var_90], eax
0x180089144  mov     eax, [rbp+47h+var_70]
0x180089147  mov     [rsp+130h+var_98], eax
0x18008914e  mov     rax, [rbp+47h+var_58]
0x180089152  mov     [rsp+130h+var_A0], rax
0x18008915a  lea     rax, GUID_NULL
0x180089161  mov     [rsp+130h+var_A8], rdi
0x180089169  mov     [rsp+130h+var_B0], rdi
0x180089171  mov     [rsp+130h+var_B8], rax
0x180089176  mov     eax, [rbp+47h+arg_20]
0x180089179  mov     [rsp+130h+var_C0], rdi
0x18008917e  mov     [rsp+130h+var_C8], rdi
0x180089183  mov     [rsp+130h+var_D0], edi
0x180089187  mov     [rsp+130h+var_D8], edi
0x18008918b  mov     [rsp+130h+var_E0], ebx
0x18008918f  mov     [rsp+130h+var_E8], r9d
0x180089194  mov     r9d, [r15+0C0h]
0x18008919b  mov     [rsp+130h+var_F0], r10d
0x1800891a0  mov     [rsp+130h+var_F8], eax
0x1800891a4  mov     dword ptr [rsp+130h+var_100], r13d
0x1800891a9  mov     dword ptr [rsp+130h+var_108], esi
0x1800891ad  mov     qword ptr [rsp+130h+bAlertable], rcx
0x1800891b2  mov     rcx, r14
0x1800891b5  call    ?LookupServer@CServerTableEntry@@QEAAJPEAVCToken@@HHPEAGKW4ServerProtectionLevel@@JJKW4_PSM_ACTIVATE_BACKGROUND_TYPE@@KKPEA_K_KAEBU_GUID@@0PEAUtagBLOB@@PEBGKK_N8PEAPEAVCServerListEntry@@@Z; CServerTableEntry::LookupServer(CToken *,int,int,ushort *,ulong,ServerProtectionLevel,long,long,ulong,_PSM_ACTIVATE_BACKGROUND_TYPE,ulong,ulong,unsigned __int64 *,unsigned __int64,_GUID const &,CToken *,tagBLOB *,ushort const *,ulong,ulong,bool,ushort const *,CServerListEntry * *)
0x1800891ba  jmp     loc_18008927C
0x1800891bf  mov     edx, [r15+1A0h]
0x1800891c6  mov     r9d, [r15+80h]
0x1800891cd  test    rax, rax
0x1800891d0  jz      short loc_1800891D8
0x1800891d2  mov     rcx, [rax+20h]
0x1800891d6  jmp     short loc_1800891DB
0x1800891d8  mov     rcx, rdi
0x1800891db  movzx   r8d, byte ptr [r15+0BCh]
0x1800891e3  lea     rax, [rbp+47h+var_60]
0x1800891e7  mov     [rsp+130h+var_80], rax
0x1800891ef  mov     eax, [rbp+47h+arg_10]
0x1800891f2  mov     [rsp+130h+var_88], al
0x1800891f9  mov     eax, [rbp+47h+ExitCode]
0x1800891fc  mov     [rsp+130h+var_90], eax
0x180089203  mov     eax, [rbp+47h+var_70]
0x180089206  mov     [rsp+130h+var_98], eax
0x18008920d  mov     rax, [rbp+47h+var_58]
0x180089211  mov     [rsp+130h+var_A0], rax
0x180089219  lea     rax, GUID_NULL
0x180089220  mov     [rsp+130h+var_A8], rdi
0x180089228  mov     [rsp+130h+var_B0], rdi
0x180089230  mov     [rsp+130h+var_B8], rax
0x180089235  mov     eax, [rbp+47h+arg_20]
0x180089238  mov     [rsp+130h+var_C0], rdi
0x18008923d  mov     [rsp+130h+var_C8], rdi
0x180089242  mov     [rsp+130h+var_D0], edi
0x180089246  mov     [rsp+130h+var_D8], edi
0x18008924a  mov     [rsp+130h+var_E0], ebx
0x18008924e  mov     [rsp+130h+var_E8], edx
0x180089252  mov     rdx, [r15+10h]
0x180089256  mov     [rsp+130h+var_F0], r9d
0x18008925b  mov     r9d, [r15+0C0h]
0x180089262  mov     [rsp+130h+var_F8], eax
0x180089266  mov     dword ptr [rsp+130h+var_100], r13d
0x18008926b  mov     dword ptr [rsp+130h+var_108], esi
0x18008926f  mov     qword ptr [rsp+130h+bAlertable], rcx
0x180089274  mov     rcx, r14
0x180089277  call    ?LookupServerOld@CServerTableEntry@@QEAAJPEAVCToken@@HHPEAGKW4ServerProtectionLevel@@JJKW4_PSM_ACTIVATE_BACKGROUND_TYPE@@KKPEA_K_KAEBU_GUID@@0PEAUtagBLOB@@PEBGKK_NPEAPEAVCServerListEntry@@@Z; CServerTableEntry::LookupServerOld(CToken *,int,int,ushort *,ulong,ServerProtectionLevel,long,long,ulong,_PSM_ACTIVATE_BACKGROUND_TYPE,ulong,ulong,unsigned __int64 *,unsigned __int64,_GUID const &,CToken *,tagBLOB *,ushort const *,ulong,ulong,bool,CServerListEntry * *)
0x18008927c  test    eax, eax
0x18008927e  jz      short loc_1800892B3
0x180089280  mov     [rbp+47h+var_60], rdi
0x180089284  mov     rax, [rbp+47h+var_50]
0x180089288  test    rax, rax
0x18008928b  jz      short loc_1800892C1
0x18008928d  mov     rcx, rax; this
0x180089290  call    ?GetProcessReg@CProcess@@QEAAPEAUScmProcessReg@@XZ; CProcess::GetProcessReg(void)
0x180089295  mov     rbx, rax
0x180089298  test    rax, rax
0x18008929b  jz      short loc_1800892C1
0x18008929d  call    cs:__imp_GetTickCount
0x1800892a4  nop     dword ptr [rax+rax+00h]
0x1800892a9  sub     eax, [rbx+40h]
0x1800892ac  cmp     eax, 55D4A80h
0x1800892b1  jmp     short loc_1800892D1
0x1800892b3  mov     rdi, [rbp+47h+var_60]
0x1800892b7  mov     rax, [rdi+60h]
0x1800892bb  mov     [rbp+47h+var_50], rax
0x1800892bf  jmp     short loc_180089288
0x1800892c1  mov     eax, [rbp+47h+var_6C]
0x1800892c4  add     eax, 7530h
0x1800892c9  mov     [rbp+47h+var_6C], eax
0x1800892cc  cmp     eax, 15F90h
0x1800892d1  jnb     short loc_180089304
0x1800892d3  mov     r9d, [rbp+47h+dwMilliseconds]; dwMilliseconds
0x1800892d7  lea     rdx, [rbp+47h+Handles]; lpHandles
0x1800892db  xor     r8d, r8d; bWaitAll
0x1800892de  mov     [rsp+130h+bAlertable], 0; int
0x1800892e6  lea     ecx, [r8+2]; nCount
0x1800892ea  call    cs:__imp_WaitForMultipleObjectsEx
0x1800892f1  nop     dword ptr [rax+rax+00h]
0x1800892f6  mov     ebx, [rbp+47h+arg_18]
0x1800892f9  mov     r12d, eax
0x1800892fc  test    eax, eax
0x1800892fe  jnz     loc_1800890C2
0x180089304  xor     esi, esi
0x180089306  test    rdi, rdi
0x180089309  jz      short loc_18008931A
0x18008930b  mov     rax, [rdi]
0x18008930e  mov     rcx, rdi
0x180089311  mov     rax, [rax+10h]
0x180089315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008931a  test    r12d, r12d
0x18008931d  jz      loc_180089490
0x180089323  mov     edx, [r14+10h]; unsigned int
0x180089327  call    ?ZeroPID@CActivationStateList@@QEAAXK@Z; CActivationStateList::ZeroPID(ulong)
0x18008932c  mov     rcx, [r14+18h]; hProcess
0x180089330  lea     rdx, [rbp+47h+ExitCode]; lpExitCode
0x180089334  mov     [rbp+47h+ExitCode], esi
0x180089337  call    cs:__imp_GetExitCodeProcess
0x18008933e  nop     dword ptr [rax+rax+00h]
0x180089343  mov     rcx, [r14+18h]; hProcess
0x180089347  xor     edx, edx; uExitCode
0x180089349  call    cs:__imp_TerminateProcess
0x180089350  nop     dword ptr [rax+rax+00h]
0x180089355  mov     rax, [r14]
0x180089358  xor     ecx, ecx; string
0x18008935a  mov     [rbp+47h+string], rsi
0x18008935e  mov     rbx, [rax+20h]
0x180089362  call    cs:__imp_WindowsDeleteString
0x180089369  nop     dword ptr [rax+rax+00h]
0x18008936e  lea     rdx, [rbp+47h+string]
0x180089372  mov     [rbp+47h+string], rsi
0x180089376  mov     rcx, r14
0x180089379  mov     rax, rbx
0x18008937c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089381  mov     eax, cs:dword_1801574B8
0x180089387  cmp     r12d, 1
0x18008938b  jnz     short loc_180089401
0x18008938d  test    eax, eax
0x18008938f  jnz     short loc_1800893A4
0x180089391  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x180089397  jz      short loc_1800893CF
0x180089399  xor     ecx, ecx
0x18008939b  call    IsWppLevelEnabled
0x1800893a0  test    al, al
  ... truncated ...
```
