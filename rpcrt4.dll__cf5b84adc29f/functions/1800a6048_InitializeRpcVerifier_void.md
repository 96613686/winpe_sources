# InitializeRpcVerifier(void)

- ea: `0x1800a6048`
- end: `0x1800a68eb`
- name: `?InitializeRpcVerifier@@YAXXZ`
- size: `2211`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x1800258b4`

## callees

- `0x180023020`
- `0x1800a6048`
- `0x1800a68f4`
- `0x1800d7010`

## import_xrefs

- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a61f0`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6268`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6373`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a63b5`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a63ec`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a641e`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6466`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6498`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a64ca`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a64fc`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a652e`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6560`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6592`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a65c4`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a65f6`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6631`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6666`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a66b3`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a66ef`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6721`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6753`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6785`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a67bd`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a67ef`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6827`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6859`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a61f0`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6268`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6373`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a63b5`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a63ec`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a641e`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6466`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6498`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a64ca`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a64fc`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a652e`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6560`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6592`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a65c4`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a65f6`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6631`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6666`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a66b3`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a66ef`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6721`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6753`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6785`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a67bd`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a67ef`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6827`
- `ntdll!LdrQueryImageFileExecutionOptions` at `0x1800a6859`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a620e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a620e`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800a6225`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800a6225`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a68cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a68cf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a613a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a613a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a6158`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a6158`

## string_xrefs

- `0x1800a6131`: `verifier.dll`
- `0x1800a63dd`: `RpcVerifierProbFaultInjectImpersonateClient`
- `0x1800a63ff`: `RpcVerifierDelayFaultInjectImpersonateClient`
- `0x1800a6622`: `NDRVerifierMaxExtensionFactor`
- `0x1800a6644`: `NDRVerifierMaxExtensionBufferLength`

## pseudocode

```c
void InitializeRpcVerifier(void)
{
  char *v0; // rax
  bool v1; // zf
  HMODULE Library; // rax
  HMODULE v3; // rsi
  FARPROC ProcAddress; // rax
  void *v5; // rbx
  SIZE_T v6; // rdi
  HANDLE ProcessHeap; // rax
  void *v8; // rax
  unsigned int v9; // eax
  struct _tRpcVerifierSettings *v10; // rcx
  struct _tRpcVerifierSettings *v11; // r9
  struct _UNICODE_STRING *v12; // rcx
  struct _tRpcVerifierSettings *v13; // rax
  struct _tRpcVerifierSettings *v14; // rax
  unsigned int Buffer; // [rsp+70h] [rbp+40h] BYREF
  int v16; // [rsp+78h] [rbp+48h] BYREF
  int v17; // [rsp+80h] [rbp+50h] BYREF
  int v18; // [rsp+88h] [rbp+58h] BYREF

  v0 = (char *)AllocWrapper(0xE0u);
  pRpcVerifierSettings = (struct _tRpcVerifierSettings *)v0;
  if ( v0 )
  {
    v1 = gfAppVerifierEnabled == 0;
    *(_DWORD *)v0 = 0;
    *((_DWORD *)v0 + 11) = 10;
    *(_QWORD *)(v0 + 76) = 10;
    *((_DWORD *)v0 + 22) = 10;
    *((_DWORD *)v0 + 31) = 10;
    DispatchToStubInC = DispatchToStubInCAvrf;
    *(_QWORD *)(v0 + 4) = 100;
    *(_QWORD *)(v0 + 12) = 0;
    *(_QWORD *)(v0 + 20) = 0;
    *(_QWORD *)(v0 + 28) = 0;
    *((_DWORD *)v0 + 9) = 100;
    *((_DWORD *)v0 + 10) = 100;
    *((_DWORD *)v0 + 12) = 4;
    *((_DWORD *)v0 + 13) = 1;
    *((_QWORD *)v0 + 7) = 2;
    *((_DWORD *)v0 + 16) = 0;
    *(_QWORD *)(v0 + 68) = 16;
    *((_DWORD *)v0 + 21) = 0;
    *(_QWORD *)(v0 + 92) = 100;
    *((_DWORD *)v0 + 25) = 1;
    *((_DWORD *)v0 + 26) = 100;
    *((_DWORD *)v0 + 27) = 1;
    *((_QWORD *)v0 + 14) = 150;
    *((_DWORD *)v0 + 30) = 100;
    *((_DWORD *)v0 + 33) = 0;
    *((_QWORD *)v0 + 17) = 0;
    *((_QWORD *)v0 + 18) = 0;
    *((_DWORD *)v0 + 38) = 20;
    *(_QWORD *)(v0 + 156) = 0x2000000;
    *((_QWORD *)v0 + 27) = 0;
    if ( v1 )
    {
      gfRPCVerifierEnabled = 1;
      v3 = 0;
      *((_DWORD *)v0 + 33) = 1;
    }
    else
    {
      Library = LoadLibraryExW(L"verifier.dll", 0, 0);
      v3 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "VerifierQueryRuntimeFlags");
        if ( ProcAddress )
        {
          v17 = 0;
          v18 = 0;
          if ( !((unsigned int (__fastcall *)(int *, int *))ProcAddress)(&v17, &v18) && v17 && (v18 & 0x80u) != 0 )
            gfRPCVerifierEnabled = 1;
        }
      }
    }
    if ( gfRPCVerifierEnabled )
    {
      v16 = 0;
      if ( RpcEvents )
      {
        Buffer = 2 * EventArrayLength;
        LdrQueryImageFileExecutionOptions(pBaseNameUnicodeString, L"RpcLogSize", 4u, &Buffer, 4u, 0);
        v5 = RpcEvents;
        v6 = 72LL * Buffer;
        ProcessHeap = GetProcessHeap();
        v8 = HeapReAlloc(ProcessHeap, 0, v5, v6);
        if ( v8 )
        {
          RpcEvents = v8;
          EventArrayLength = Buffer;
        }
      }
      LdrQueryImageFileExecutionOptions(pBaseNameUnicodeString, L"RpcVerifierFlags", 4u, &RpcVerifierFlags, 4u, 0);
      v9 = RpcVerifierFlags;
      v10 = pRpcVerifierSettings;
      if ( (RpcVerifierFlags & 1) != 0 )
      {
        *(_DWORD *)pRpcVerifierSettings = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x10) != 0 )
      {
        *((_DWORD *)v10 + 3) = 1;
        v9 = RpcVerifierFlags;
        gfRpcVerifierCorruptionExpected = 1;
      }
      if ( (v9 & 0x20) != 0 )
      {
        *((_DWORD *)v10 + 4) = 1;
        v9 = RpcVerifierFlags;
        gfRpcVerifierCorruptionExpected = 1;
      }
      if ( (v9 & 0x40) != 0 )
      {
        *((_DWORD *)v10 + 5) = 1;
        v9 = RpcVerifierFlags;
        gfRpcVerifierCorruptionExpected = 1;
      }
      if ( (v9 & 0x80u) != 0 )
      {
        *((_DWORD *)v10 + 6) = 1;
        *((_DWORD *)v10 + 8) = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x40000) != 0 )
      {
        *((_DWORD *)v10 + 7) = 1;
        *((_DWORD *)v10 + 8) = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x100) != 0 )
      {
        *((_DWORD *)v10 + 18) = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x200) != 0 )
      {
        *((_DWORD *)v10 + 21) = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x1000) != 0 )
      {
        *((_DWORD *)v10 + 24) = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x2000) != 0 )
      {
        *((_DWORD *)v10 + 29) = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x10000) != 0 )
      {
        *((_DWORD *)v10 + 33) = 1;
        v9 = RpcVerifierFlags;
      }
      if ( (v9 & 0x20000) != 0 )
        LODWORD(gBCacheMode) = 1;
      LdrQueryImageFileExecutionOptions(pBaseNameUnicodeString, L"PageHeapFaultProbability", 4u, &v16, 4u, 0);
      if ( v16 )
      {
        v11 = pRpcVerifierSettings;
        v12 = pBaseNameUnicodeString;
        *(_DWORD *)pRpcVerifierSettings = 1;
        *((_DWORD *)v11 + 1) = v16;
        LdrQueryImageFileExecutionOptions(v12, L"PageHeapFaultTimeOut", 4u, (char *)v11 + 8, 4u, 0);
      }
      v13 = pRpcVerifierSettings;
      if ( *(_DWORD *)pRpcVerifierSettings )
      {
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierProbFaultInjectImpersonateClient",
          4u,
          (char *)pRpcVerifierSettings + 4,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierDelayFaultInjectImpersonateClient",
          4u,
          (char *)pRpcVerifierSettings + 8,
          4u,
          0);
        v13 = pRpcVerifierSettings;
      }
      if ( *((_DWORD *)v13 + 3) || *((_DWORD *)v13 + 4) || *((_DWORD *)v13 + 5) )
      {
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierProbRpcHeaderCorruption",
          4u,
          (char *)v13 + 36,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierProbDataCorruption",
          4u,
          (char *)pRpcVerifierSettings + 40,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierProbSecureDataCorruption",
          4u,
          (char *)pRpcVerifierSettings + 44,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierCorruptionPattern",
          4u,
          (char *)pRpcVerifierSettings + 48,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierCorruptionSizeType",
          4u,
          (char *)pRpcVerifierSettings + 52,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierCorruptionSize",
          4u,
          (char *)pRpcVerifierSettings + 56,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierCorruptionDistributionType",
          4u,
          (char *)pRpcVerifierSettings + 60,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierProbBufferTruncation",
          4u,
          (char *)pRpcVerifierSettings + 64,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierMaxBufferTruncationSize",
          4u,
          (char *)pRpcVerifierSettings + 68,
          4u,
          0);
        v13 = pRpcVerifierSettings;
      }
      if ( *((_DWORD *)v13 + 8) )
      {
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"NDRVerifierMaxExtensionFactor",
          4u,
          (char *)v13 + 152,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"NDRVerifierMaxExtensionBufferLength",
          4u,
          (char *)pRpcVerifierSettings + 156,
          4u,
          0);
        v13 = pRpcVerifierSettings;
      }
      if ( *((_DWORD *)v13 + 3) || *((_DWORD *)v13 + 4) || *((_DWORD *)v13 + 5) || *((_DWORD *)v13 + 8) )
      {
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierDelayCorruption",
          4u,
          (char *)v13 + 160,
          4u,
          0);
        v13 = pRpcVerifierSettings;
      }
      if ( *((_DWORD *)v13 + 24) )
      {
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierPauseInjectIntervalType",
          4u,
          (char *)v13 + 100,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierPauseInjectIntervalLength",
          4u,
          (char *)pRpcVerifierSettings + 104,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierPauseInjectPauseType",
          4u,
          (char *)pRpcVerifierSettings + 108,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierPauseInjectPauseLength",
          4u,
          (char *)pRpcVerifierSettings + 112,
          4u,
          0);
        v13 = pRpcVerifierSettings;
      }
      if ( *((_DWORD *)v13 + 18) )
      {
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierProbFaultInjectTransports",
          4u,
          (char *)v13 + 76,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierDelayFaultInjectTransports",
          4u,
          (char *)pRpcVerifierSettings + 80,
          4u,
          0);
        v13 = pRpcVerifierSettings;
      }
      if ( *((_DWORD *)v13 + 21) )
      {
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierSendReplaySentBufferListSize",
          4u,
          (char *)v13 + 88,
          4u,
          0);
        LdrQueryImageFileExecutionOptions(
          pBaseNameUnicodeString,
          L"RpcVerifierSendReplayReplayFrequency",
          4u,
          (char *)pRpcVerifierSettings + 92,
          4u,
          0);
        v13 = pRpcVerifierSettings;
      }
      if ( *((_DWORD *)v13 + 3)
        || *((_DWORD *)v13 + 4)
        || *((_DWORD *)v13 + 5)
        || *((_DWORD *)v13 + 8)
        || *((_DWORD *)v13 + 24)
        || *((_DWORD *)v13 + 21)
        || *((_DWORD *)v13 + 18) )
      {
        if ( (unsigned int)LoadRpcShim() )
        {
          v14 = pRpcVerifierSettings;
          *(_QWORD *)((char *)pRpcVerifierSettings + 12) = 0;
          *(_QWORD *)((char *)v14 + 20) = 0;
          *(_QWORD *)((char *)v14 + 28) = 0;
          *((_DWORD *)v14 + 24) = 0;
          *((_DWORD *)v14 + 21) = 0;
          *((_DWORD *)v14 + 18) = 0;
        }
      }
    }
    else
    {
      LODWORD(gBCacheMode) = 1;
    }
    if ( v3 )
      FreeLibrary(v3);
  }
}

```

## disassembly

```asm
0x1800a6048  push    rbp
0x1800a604a  push    rbx
0x1800a604b  push    rsi
0x1800a604c  push    rdi
0x1800a604d  push    r12
0x1800a604f  push    r14
0x1800a6051  push    r15
0x1800a6053  mov     rbp, rsp
0x1800a6056  sub     rsp, 30h
0x1800a605a  mov     ecx, 0E0h; dwBytes
0x1800a605f  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800a6064  xor     r14d, r14d
0x1800a6067  mov     cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA, rax; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a606e  test    rax, rax
0x1800a6071  jz      loc_1800A68DB
0x1800a6077  cmp     cs:?gfAppVerifierEnabled@@3HA, r14d; int gfAppVerifierEnabled
0x1800a607e  lea     edx, [r14+64h]
0x1800a6082  lea     ecx, [rdx-5Ah]
0x1800a6085  mov     [rax], r14d
0x1800a6088  lea     r12d, [r14+1]
0x1800a608c  mov     [rax+2Ch], ecx
0x1800a608f  mov     [rax+4Ch], rcx
0x1800a6093  lea     r15d, [r14+4]
0x1800a6097  mov     [rax+58h], ecx
0x1800a609a  mov     [rax+7Ch], ecx
0x1800a609d  lea     rcx, DispatchToStubInCAvrf
0x1800a60a4  mov     cs:DispatchToStubInC, rcx
0x1800a60ab  mov     [rax+4], rdx
0x1800a60af  mov     [rax+0Ch], r14
0x1800a60b3  mov     [rax+14h], r14
0x1800a60b7  mov     [rax+1Ch], r14
0x1800a60bb  mov     [rax+24h], edx
0x1800a60be  mov     [rax+28h], edx
0x1800a60c1  mov     [rax+30h], r15d
0x1800a60c5  mov     [rax+34h], r12d
0x1800a60c9  mov     qword ptr [rax+38h], 2
0x1800a60d1  mov     [rax+40h], r14d
0x1800a60d5  mov     qword ptr [rax+44h], 10h
0x1800a60dd  mov     [rax+54h], r14d
0x1800a60e1  mov     [rax+5Ch], rdx
0x1800a60e5  mov     [rax+64h], r12d
0x1800a60e9  mov     [rax+68h], edx
0x1800a60ec  mov     [rax+6Ch], r12d
0x1800a60f0  mov     qword ptr [rax+70h], 96h
0x1800a60f8  mov     [rax+78h], edx
0x1800a60fb  mov     [rax+84h], r14d
0x1800a6102  mov     [rax+88h], r14
0x1800a6109  mov     [rax+90h], r14
0x1800a6110  mov     dword ptr [rax+98h], 14h
0x1800a611a  mov     qword ptr [rax+9Ch], 2000000h
0x1800a6125  mov     [rax+0D8h], r14
0x1800a612c  jz      short loc_1800A6197
0x1800a612e  xor     r8d, r8d; dwFlags
0x1800a6131  lea     rcx, aVerifierDll; "verifier.dll"
0x1800a6138  xor     edx, edx; hFile
0x1800a613a  call    cs:__imp_LoadLibraryExW
0x1800a6141  nop     dword ptr [rax+rax+00h]
0x1800a6146  mov     rsi, rax
0x1800a6149  test    rax, rax
0x1800a614c  jz      short loc_1800A61A8
0x1800a614e  lea     rdx, aVerifierqueryr; "VerifierQueryRuntimeFlags"
0x1800a6155  mov     rcx, rax; hModule
0x1800a6158  call    cs:__imp_GetProcAddress
0x1800a615f  nop     dword ptr [rax+rax+00h]
0x1800a6164  test    rax, rax
0x1800a6167  jz      short loc_1800A61A8
0x1800a6169  lea     rdx, [rbp+arg_18]
0x1800a616d  mov     [rbp+arg_10], r14d
0x1800a6171  lea     rcx, [rbp+arg_10]
0x1800a6175  mov     [rbp+arg_18], r14d
0x1800a6179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a617e  test    eax, eax
0x1800a6180  jnz     short loc_1800A61A8
0x1800a6182  cmp     [rbp+arg_10], r14d
0x1800a6186  jz      short loc_1800A61A8
0x1800a6188  test    byte ptr [rbp+arg_18], 80h
0x1800a618c  jz      short loc_1800A61A8
0x1800a618e  mov     cs:?gfRPCVerifierEnabled@@3HA, r12d; int gfRPCVerifierEnabled
0x1800a6195  jmp     short loc_1800A61A8
0x1800a6197  mov     cs:?gfRPCVerifierEnabled@@3HA, r12d; int gfRPCVerifierEnabled
0x1800a619e  mov     rsi, r14
0x1800a61a1  mov     [rax+84h], r12d
0x1800a61a8  cmp     cs:?gfRPCVerifierEnabled@@3HA, r14d; int gfRPCVerifierEnabled
0x1800a61af  jz      loc_1800A68C0
0x1800a61b5  cmp     cs:?RpcEvents@@3PEAURPC_EVENT@@EA, r14; RPC_EVENT * RpcEvents
0x1800a61bc  mov     [rbp+arg_8], r14d
0x1800a61c0  jz      loc_1800A6246
0x1800a61c6  mov     eax, cs:?EventArrayLength@@3KA; ulong EventArrayLength
0x1800a61cc  lea     r9, [rbp+Buffer]; Buffer
0x1800a61d0  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a61d7  lea     rdx, aRpclogsize; "RpcLogSize"
0x1800a61de  add     eax, eax
0x1800a61e0  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a61e5  mov     r8d, r15d; ValueSize
0x1800a61e8  mov     [rbp+Buffer], eax
0x1800a61eb  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a61f0  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a61f7  nop     dword ptr [rax+rax+00h]
0x1800a61fc  mov     eax, [rbp+Buffer]
0x1800a61ff  mov     rbx, cs:?RpcEvents@@3PEAURPC_EVENT@@EA; RPC_EVENT * RpcEvents
0x1800a6206  lea     rdi, [rax+rax*8]
0x1800a620a  shl     rdi, 3
0x1800a620e  call    cs:__imp_GetProcessHeap
0x1800a6215  nop     dword ptr [rax+rax+00h]
0x1800a621a  mov     r9, rdi; dwBytes
0x1800a621d  mov     r8, rbx; lpMem
0x1800a6220  mov     rcx, rax; hHeap
0x1800a6223  xor     edx, edx; dwFlags
0x1800a6225  call    cs:__imp_HeapReAlloc
0x1800a622c  nop     dword ptr [rax+rax+00h]
0x1800a6231  test    rax, rax
0x1800a6234  jz      short loc_1800A6246
0x1800a6236  mov     cs:?RpcEvents@@3PEAURPC_EVENT@@EA, rax; RPC_EVENT * RpcEvents
0x1800a623d  mov     eax, [rbp+Buffer]
0x1800a6240  mov     cs:?EventArrayLength@@3KA, eax; ulong EventArrayLength
0x1800a6246  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a624d  lea     r9, ?RpcVerifierFlags@@3KA; Buffer
0x1800a6254  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a6259  lea     rdx, aRpcverifierfla; "RpcVerifierFlags"
0x1800a6260  mov     r8d, r15d; ValueSize
0x1800a6263  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a6268  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a626f  nop     dword ptr [rax+rax+00h]
0x1800a6274  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a627a  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a6281  test    r12b, al
0x1800a6284  jz      short loc_1800A628F
0x1800a6286  mov     [rcx], r12d
0x1800a6289  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a628f  test    al, 10h
0x1800a6291  jz      short loc_1800A62A4
0x1800a6293  mov     [rcx+0Ch], r12d
0x1800a6297  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a629d  mov     cs:?gfRpcVerifierCorruptionExpected@@3HA, r12d; int gfRpcVerifierCorruptionExpected
0x1800a62a4  test    al, 20h
0x1800a62a6  jz      short loc_1800A62B9
0x1800a62a8  mov     [rcx+10h], r12d
0x1800a62ac  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a62b2  mov     cs:?gfRpcVerifierCorruptionExpected@@3HA, r12d; int gfRpcVerifierCorruptionExpected
0x1800a62b9  test    al, 40h
0x1800a62bb  jz      short loc_1800A62CE
0x1800a62bd  mov     [rcx+14h], r12d
0x1800a62c1  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a62c7  mov     cs:?gfRpcVerifierCorruptionExpected@@3HA, r12d; int gfRpcVerifierCorruptionExpected
0x1800a62ce  test    al, al
0x1800a62d0  jns     short loc_1800A62E0
0x1800a62d2  mov     [rcx+18h], r12d
0x1800a62d6  mov     [rcx+20h], r12d
0x1800a62da  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a62e0  bt      eax, 12h
0x1800a62e4  jnb     short loc_1800A62F4
0x1800a62e6  mov     [rcx+1Ch], r12d
0x1800a62ea  mov     [rcx+20h], r12d
0x1800a62ee  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a62f4  bt      eax, 8
0x1800a62f8  jnb     short loc_1800A6304
0x1800a62fa  mov     [rcx+48h], r12d
0x1800a62fe  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a6304  bt      eax, 9
0x1800a6308  jnb     short loc_1800A6314
0x1800a630a  mov     [rcx+54h], r12d
0x1800a630e  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a6314  bt      eax, 0Ch
0x1800a6318  jnb     short loc_1800A6324
0x1800a631a  mov     [rcx+60h], r12d
0x1800a631e  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a6324  bt      eax, 0Dh
0x1800a6328  jnb     short loc_1800A6334
0x1800a632a  mov     [rcx+74h], r12d
0x1800a632e  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a6334  bt      eax, 10h
0x1800a6338  jnb     short loc_1800A6347
0x1800a633a  mov     [rcx+84h], r12d
0x1800a6341  mov     eax, cs:?RpcVerifierFlags@@3KA; ulong RpcVerifierFlags
0x1800a6347  bt      eax, 11h
0x1800a634b  jnb     short loc_1800A6354
0x1800a634d  mov     cs:?gBCacheMode@@3W4BCacheMode@@A, r12d; BCacheMode gBCacheMode
0x1800a6354  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a635b  lea     r9, [rbp+arg_8]; Buffer
0x1800a635f  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a6364  lea     rdx, aPageheapfaultp; "PageHeapFaultProbability"
0x1800a636b  mov     r8d, r15d; ValueSize
0x1800a636e  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a6373  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a637a  nop     dword ptr [rax+rax+00h]
0x1800a637f  cmp     [rbp+arg_8], r14d
0x1800a6383  jz      short loc_1800A63C1
0x1800a6385  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a638c  lea     rdx, aPageheapfaultt; "PageHeapFaultTimeOut"
0x1800a6393  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a639a  mov     r8d, r15d; ValueSize
0x1800a639d  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a63a2  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a63a7  mov     [r9], r12d
0x1800a63aa  mov     eax, [rbp+arg_8]
0x1800a63ad  mov     [r9+4], eax
0x1800a63b1  add     r9, 8; Buffer
0x1800a63b5  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a63bc  nop     dword ptr [rax+rax+00h]
0x1800a63c1  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a63c8  cmp     [rax], r14d
0x1800a63cb  jz      short loc_1800A6431
0x1800a63cd  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a63d4  lea     r9, [rax+4]; Buffer
0x1800a63d8  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a63dd  lea     rdx, aRpcverifierpro; "RpcVerifierProbFaultInjectImpersonateCl"...
0x1800a63e4  mov     r8d, r15d; ValueSize
0x1800a63e7  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a63ec  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a63f3  nop     dword ptr [rax+rax+00h]
0x1800a63f8  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a63ff  lea     rdx, aRpcverifierdel_1; "RpcVerifierDelayFaultInjectImpersonateC"...
0x1800a6406  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a640d  add     r9, 8; Buffer
0x1800a6411  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a6416  mov     r8d, r15d; ValueSize
0x1800a6419  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a641e  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a6425  nop     dword ptr [rax+rax+00h]
0x1800a642a  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a6431  cmp     [rax+0Ch], r14d
0x1800a6435  jnz     short loc_1800A6447
0x1800a6437  cmp     [rax+10h], r14d
0x1800a643b  jnz     short loc_1800A6447
0x1800a643d  cmp     [rax+14h], r14d
0x1800a6441  jz      loc_1800A6609
0x1800a6447  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a644e  lea     r9, [rax+24h]; Buffer
0x1800a6452  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a6457  lea     rdx, aRpcverifierpro_3; "RpcVerifierProbRpcHeaderCorruption"
0x1800a645e  mov     r8d, r15d; ValueSize
0x1800a6461  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a6466  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a646d  nop     dword ptr [rax+rax+00h]
0x1800a6472  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a6479  lea     rdx, aRpcverifierpro_4; "RpcVerifierProbDataCorruption"
0x1800a6480  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a6487  add     r9, 28h ; '('; Buffer
0x1800a648b  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a6490  mov     r8d, r15d; ValueSize
0x1800a6493  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a6498  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a649f  nop     dword ptr [rax+rax+00h]
0x1800a64a4  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a64ab  lea     rdx, aRpcverifierpro_2; "RpcVerifierProbSecureDataCorruption"
0x1800a64b2  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a64b9  add     r9, 2Ch ; ','; Buffer
0x1800a64bd  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a64c2  mov     r8d, r15d; ValueSize
0x1800a64c5  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a64ca  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a64d1  nop     dword ptr [rax+rax+00h]
0x1800a64d6  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a64dd  lea     rdx, aRpcverifiercor_2; "RpcVerifierCorruptionPattern"
0x1800a64e4  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a64eb  add     r9, 30h ; '0'; Buffer
0x1800a64ef  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a64f4  mov     r8d, r15d; ValueSize
0x1800a64f7  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a64fc  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a6503  nop     dword ptr [rax+rax+00h]
0x1800a6508  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a650f  lea     rdx, aRpcverifiercor_0; "RpcVerifierCorruptionSizeType"
0x1800a6516  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a651d  add     r9, 34h ; '4'; Buffer
0x1800a6521  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a6526  mov     r8d, r15d; ValueSize
0x1800a6529  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a652e  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a6535  nop     dword ptr [rax+rax+00h]
0x1800a653a  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a6541  lea     rdx, aRpcverifiercor_1; "RpcVerifierCorruptionSize"
0x1800a6548  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a654f  add     r9, 38h ; '8'; Buffer
0x1800a6553  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a6558  mov     r8d, r15d; ValueSize
0x1800a655b  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a6560  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a6567  nop     dword ptr [rax+rax+00h]
0x1800a656c  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a6573  lea     rdx, aRpcverifiercor; "RpcVerifierCorruptionDistributionType"
0x1800a657a  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a6581  add     r9, 3Ch ; '<'; Buffer
0x1800a6585  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a658a  mov     r8d, r15d; ValueSize
0x1800a658d  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a6592  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a6599  nop     dword ptr [rax+rax+00h]
0x1800a659e  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a65a5  lea     rdx, aRpcverifierpro_0; "RpcVerifierProbBufferTruncation"
0x1800a65ac  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
0x1800a65b3  add     r9, 40h ; '@'; Buffer
0x1800a65b7  mov     [rsp+30h+RetunedLength], r14; RetunedLength
0x1800a65bc  mov     r8d, r15d; ValueSize
0x1800a65bf  mov     [rsp+30h+BufferSize], r15d; BufferSize
0x1800a65c4  call    cs:__imp_LdrQueryImageFileExecutionOptions
0x1800a65cb  nop     dword ptr [rax+rax+00h]
0x1800a65d0  mov     r9, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a65d7  lea     rdx, aRpcverifiermax; "RpcVerifierMaxBufferTruncationSize"
0x1800a65de  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; SubKey
  ... truncated ...
```
