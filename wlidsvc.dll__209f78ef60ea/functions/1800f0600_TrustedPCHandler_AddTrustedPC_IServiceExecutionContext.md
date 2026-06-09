# TrustedPCHandler::AddTrustedPC(IServiceExecutionContext *)

- ea: `0x1800f0600`
- end: `0x1800f0839`
- name: `?AddTrustedPC@TrustedPCHandler@@SAJPEAVIServiceExecutionContext@@@Z`
- size: `569`
- prototype: `__int64 __fastcall(struct IServiceExecutionContext *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18009ef98`

## callees

- `0x180009e98`
- `0x18000a36c`
- `0x18000c050`
- `0x18000fd04`
- `0x18001a9c0`
- `0x18001ad00`
- `0x1800a3b60`
- `0x1800e09a8`
- `0x1800f0600`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0732`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800f0728`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800f0728`
- `ntdll!RtlAcquireResourceShared` at `0x1800f06c0`
- `ntdll!RtlAcquireResourceShared` at `0x1800f06c0`
- `ntdll!RtlReleaseResource` at `0x1800f07ec`
- `ntdll!RtlReleaseResource` at `0x1800f07ec`

## string_xrefs

- `0x1800f070c`: `hr = pExecutionContext->GetServiceWrapper()->HandleCreateContext(L"", CREATECONTEXT_SET_APP_IDENTITY, &hUser, c_addTrustedPCApplicationId)`
- `0x1800f0679`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\trustedpchandler.cpp`
- `0x1800f07a0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\trustedpchandler.cpp`
- `0x1800f0788`: `hr = pExecutionContext->GetServiceWrapper()->HandleAssociateDeviceToUser(g_szStrongAuthAppId, hUser, machineName, DeviceAssociationTypes::TrustedPC )`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall TrustedPCHandler::AddTrustedPC(struct IServiceExecutionContext *a1)
{
  struct _RTL_RESOURCE *v2; // rdi
  __int64 v3; // rax
  int v4; // eax
  bool *v5; // r8
  signed int LastError; // eax
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rdx
  unsigned int v11; // ebx
  char *v13; // [rsp+20h] [rbp-69h]
  int v14; // [rsp+30h] [rbp-59h] BYREF
  __int64 v15; // [rsp+38h] [rbp-51h] BYREF
  DWORD nSize; // [rsp+40h] [rbp-49h] BYREF
  __int64 v17; // [rsp+48h] [rbp-41h] BYREF
  int *v18[4]; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v19[5]; // [rsp+70h] [rbp-19h] BYREF
  WCHAR Buffer[8]; // [rsp+98h] [rbp+Fh] BYREF
  __int128 v21; // [rsp+A8h] [rbp+1Fh]

  v14 = 0;
  v15 = 0;
  *(_OWORD *)Buffer = 0;
  v21 = 0;
  nSize = 16;
  v17 = 0;
  v19[0] = "TrustedPCHandler::AddTrustedPC";
  v19[1] = &v14;
  v19[2] = 0;
  v19[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\trustedpchandler.cpp",
    "TrustedPCHandler::AddTrustedPC",
    (const char *)0x3C,
    0,
    (const unsigned __int16 *)v13);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v18, "TrustedPCHandler::AddTrustedPC", &v14, 0x35u, &qword_18017D1C0);
  v2 = (struct _RTL_RESOURCE *)((char *)g_pPPCRL + 2136);
  v19[4] = (char *)g_pPPCRL + 2136;
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)g_pPPCRL + 2136), 1u);
  v3 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 80LL))(a1);
  v4 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, __int64 *, const wchar_t *))(*(_QWORD *)v3 + 104LL))(
         v3,
         &qword_18013DE20,
         0x800000,
         &v15,
         L"{cacf4700-5e74-446f-9320-7eca7abf9037}");
  v14 = v4;
  if ( v4 >= 0 )
  {
    if ( GetComputerNameW(Buffer, &nSize) )
    {
      v7 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 80LL))(a1);
      v8 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, WCHAR *, int))(*(_QWORD *)v7 + 112LL))(
             v7,
             L"{AFDA72BF-3409-413a-B54E-2AB8D66A7826}",
             v15,
             Buffer,
             100);
      v14 = v8;
      if ( v8 < 0 )
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\trustedpchandler.cpp",
          "TrustedPCHandler::AddTrustedPC",
          0x68u,
          v8,
          "hr = pExecutionContext->GetServiceWrapper()->HandleAssociateDeviceToUser(g_szStrongAuthAppId, hUser, machineNa"
          "me, DeviceAssociationTypes::TrustedPC )");
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v14 = LastError;
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\trustedpchandler.cpp",
      "TrustedPCHandler::AddTrustedPC",
      0x54u,
      v4,
      "hr = pExecutionContext->GetServiceWrapper()->HandleCreateContext(L\"\", CREATECONTEXT_SET_APP_IDENTITY, &hUser, c_"
      "addTrustedPCApplicationId)");
  }
  if ( v15 )
  {
    v9 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 80LL))(a1);
    LOBYTE(v10) = 1;
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v9 + 120LL))(v9, v10, v15);
  }
  v11 = ErrorHandlingUtilities::MapInternalErrorToExternal(v14, 0, v5);
  v14 = v11;
  RtlReleaseResource(v2);
  ErrorVerifier::CheckAgainstList((const char *)v18[3], *v18[2], (unsigned __int64)v18[1], v18[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v19);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v17);
  return v11;
}

```

## disassembly

```asm
0x1800f0600  push    rbp
0x1800f0602  push    rbx
0x1800f0603  push    rdi
0x1800f0604  push    r14
0x1800f0606  lea     rbp, [rsp-3Fh]
0x1800f060b  sub     rsp, 0C8h
0x1800f0612  mov     rax, cs:__security_cookie
0x1800f0619  xor     rax, rsp
0x1800f061c  mov     [rbp+57h+var_28], rax
0x1800f0620  mov     rbx, rcx
0x1800f0623  mov     [rbp+57h+var_B0], 0
0x1800f062a  mov     [rbp+57h+var_A8], 0
0x1800f0632  xorps   xmm0, xmm0
0x1800f0635  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1800f0639  movups  [rbp+57h+var_38], xmm0
0x1800f063d  mov     [rbp+57h+nSize], 10h
0x1800f0644  mov     [rbp+57h+var_98], 0
0x1800f064c  lea     r14, aTrustedpchandl; "TrustedPCHandler::AddTrustedPC"
0x1800f0653  mov     [rbp+57h+var_70], r14
0x1800f0657  lea     rax, [rbp+57h+var_B0]
0x1800f065b  mov     [rbp+57h+var_68], rax
0x1800f065f  mov     [rbp+57h+var_60], 0
0x1800f0667  mov     [rbp+57h+var_58], 0
0x1800f066f  xor     r9d, r9d; unsigned int
0x1800f0672  lea     r8d, [r9+3Ch]; char *
0x1800f0676  mov     rdx, r14; char *
0x1800f0679  lea     rcx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f0680  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800f0685  nop
0x1800f0686  lea     rax, qword_18017D1C0
0x1800f068d  mov     [rsp+0E0h+var_C0], rax; int *
0x1800f0692  mov     r9d, 35h ; '5'; unsigned __int64
0x1800f0698  lea     r8, [rbp+57h+var_B0]; int *
0x1800f069c  mov     rdx, r14; char *
0x1800f069f  lea     rcx, [rbp+57h+var_90]; this
0x1800f06a3  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x1800f06a8  nop
0x1800f06a9  mov     rdi, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x1800f06b0  add     rdi, 858h
0x1800f06b7  mov     [rbp+57h+var_50], rdi
0x1800f06bb  mov     dl, 1; Wait
0x1800f06bd  mov     rcx, rdi; Resource
0x1800f06c0  call    cs:__imp_RtlAcquireResourceShared
0x1800f06c6  nop
0x1800f06c7  mov     rax, [rbx]
0x1800f06ca  mov     rcx, rbx
0x1800f06cd  mov     rax, [rax+50h]
0x1800f06d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f06d6  mov     r10, rax
0x1800f06d9  mov     rcx, [rax]
0x1800f06dc  mov     rax, [rcx+68h]
0x1800f06e0  lea     rcx, aCacf47005e7444; "{cacf4700-5e74-446f-9320-7eca7abf9037}"
0x1800f06e7  mov     [rsp+0E0h+var_C0], rcx
0x1800f06ec  lea     r9, [rbp+57h+var_A8]
0x1800f06f0  mov     r8d, 800000h
0x1800f06f6  lea     rdx, qword_18013DE20
0x1800f06fd  mov     rcx, r10
0x1800f0700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0705  mov     [rbp+57h+var_B0], eax
0x1800f0708  test    eax, eax
0x1800f070a  jns     short loc_1800F0720
0x1800f070c  lea     rcx, aHrPexecutionco_5; "hr = pExecutionContext->GetServiceWrapp"...
0x1800f0713  mov     [rsp+0E0h+var_C0], rcx
0x1800f0718  mov     r8d, 54h ; 'T'
0x1800f071e  jmp     short loc_1800F079A
0x1800f0720  lea     rdx, [rbp+57h+nSize]; nSize
0x1800f0724  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x1800f0728  call    cs:__imp_GetComputerNameW
0x1800f072e  test    eax, eax
0x1800f0730  jnz     short loc_1800F0749
0x1800f0732  call    cs:__imp_GetLastError
0x1800f0738  test    eax, eax
0x1800f073a  jle     short loc_1800F0744
0x1800f073c  movzx   eax, ax
0x1800f073f  or      eax, 80070000h
0x1800f0744  mov     [rbp+57h+var_B0], eax
0x1800f0747  jmp     short loc_1800F07AC
0x1800f0749  mov     rax, [rbx]
0x1800f074c  mov     rcx, rbx
0x1800f074f  mov     rax, [rax+50h]
0x1800f0753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0758  mov     r10, rax
0x1800f075b  mov     rcx, [rax]
0x1800f075e  mov     rax, [rcx+70h]
0x1800f0762  mov     dword ptr [rsp+0E0h+var_C0], 64h ; 'd'
0x1800f076a  lea     r9, [rbp+57h+Buffer]
0x1800f076e  mov     r8, [rbp+57h+var_A8]
0x1800f0772  lea     rdx, aAfda72bf340941; "{AFDA72BF-3409-413a-B54E-2AB8D66A7826}"
0x1800f0779  mov     rcx, r10
0x1800f077c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0781  mov     [rbp+57h+var_B0], eax
0x1800f0784  test    eax, eax
0x1800f0786  jns     short loc_1800F07AC
0x1800f0788  lea     rdx, aHrPexecutionco; "hr = pExecutionContext->GetServiceWrapp"...
0x1800f078f  mov     [rsp+0E0h+var_C0], rdx; char *
0x1800f0794  mov     r8d, 68h ; 'h'; unsigned int
0x1800f079a  mov     r9d, eax; int
0x1800f079d  mov     rdx, r14; char *
0x1800f07a0  lea     rcx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f07a7  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800f07ac  cmp     [rbp+57h+var_A8], 0
0x1800f07b1  jz      short loc_1800F07DA
0x1800f07b3  mov     rax, [rbx]
0x1800f07b6  mov     rcx, rbx
0x1800f07b9  mov     rax, [rax+50h]
0x1800f07bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f07c2  mov     r9, rax
0x1800f07c5  mov     rcx, [rax]
0x1800f07c8  mov     rax, [rcx+78h]
0x1800f07cc  mov     r8, [rbp+57h+var_A8]
0x1800f07d0  mov     dl, 1
0x1800f07d2  mov     rcx, r9
0x1800f07d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f07da  xor     edx, edx; bool
0x1800f07dc  mov     ecx, [rbp+57h+var_B0]; int
0x1800f07df  call    ?MapInternalErrorToExternal@ErrorHandlingUtilities@@SAJJ_NPEA_N@Z; ErrorHandlingUtilities::MapInternalErrorToExternal(long,bool,bool *)
0x1800f07e4  mov     ebx, eax
0x1800f07e6  mov     [rbp+57h+var_B0], eax
0x1800f07e9  mov     rcx, rdi; Resource
0x1800f07ec  call    cs:__imp_RtlReleaseResource
0x1800f07f2  nop
0x1800f07f3  mov     r9, [rbp+57h+var_90]; int *
0x1800f07f7  mov     r8, [rbp+57h+var_88]; unsigned __int64
0x1800f07fb  mov     rdx, [rbp+57h+var_80]
0x1800f07ff  mov     edx, [rdx]; int
0x1800f0801  mov     rcx, [rbp+57h+var_78]; char *
0x1800f0805  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x1800f080a  nop
0x1800f080b  lea     rcx, [rbp+57h+var_70]
0x1800f080f  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800f0814  nop
0x1800f0815  lea     rcx, [rbp+57h+var_98]
0x1800f0819  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x1800f081e  mov     eax, ebx
0x1800f0820  mov     rcx, [rbp+57h+var_28]
0x1800f0824  xor     rcx, rsp; StackCookie
0x1800f0827  call    __security_check_cookie
0x1800f082c  add     rsp, 0C8h
0x1800f0833  pop     r14
0x1800f0835  pop     rdi
0x1800f0836  pop     rbx
0x1800f0837  pop     rbp
0x1800f0838  retn
```
