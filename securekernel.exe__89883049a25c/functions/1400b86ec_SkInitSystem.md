# SkInitSystem

- ea: `0x1400b86ec`
- end: `0x1400b8ace`
- name: `SkInitSystem`
- size: `994`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140014dd0`
- `0x140102008`

## callees

- `0x140044b88`
- `0x140059dcc`
- `0x14005a0f8`
- `0x14005aa8c`
- `0x14005e988`
- `0x140086198`
- `0x140092184`
- `0x140093180`
- `0x1400a0fa0`
- `0x1400a4194`
- `0x1400ae210`
- `0x1400b82c8`
- `0x1400b86ec`
- `0x1400b8ad4`
- `0x1400b8c90`
- `0x1400b99e8`
- `0x1400bb254`
- `0x1400bb5b4`
- `0x1400bb8a8`
- `0x1400bc544`
- `0x1400bf18c`
- `0x1400bfa88`
- `0x1400f3620`
- `0x1400f38f0`
- `0x1400f9a80`

## import_xrefs

- `cng!BCryptGenRandom` at `0x1400b8839`
- `cng!BCryptGenRandom` at `0x1400b8839`
- `cng!EntropyPoolTriggerReseedForIum` at `0x1400b8817`
- `cng!EntropyPoolTriggerReseedForIum` at `0x1400b8817`
- `cng!EntropyRegisterSource` at `0x1400b8809`
- `cng!EntropyRegisterSource` at `0x1400b8809`

## string_xrefs

- `0x1400b87f6`: `Microsoft Windows Exchange VSM (SK side)`

## pseudocode

```c
__int64 __fastcall SkInitSystem(int a1, __int64 a2)
{
  int v4; // ebx
  int inited; // ebx
  __int64 v6; // rdx
  const signed __int16 *i; // rdi
  __int64 (__fastcall *v8)(_QWORD, _QWORD); // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int128 v13; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v14; // [rsp+40h] [rbp-C0h]
  __int128 v15; // [rsp+50h] [rbp-B0h]
  _DWORD v16[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v17; // [rsp+68h] [rbp-98h]
  __int128 v18; // [rsp+88h] [rbp-78h]
  __int64 v19; // [rsp+98h] [rbp-68h]
  unsigned __int64 v20; // [rsp+B0h] [rbp-50h]
  __int64 v21; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v22; // [rsp+C0h] [rbp-40h]
  UCHAR pbBuffer[32]; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(v16, 0, 0x68u);
  v13 = 0;
  v14 = 0;
  v15 = 0;
  if ( a1 )
  {
    v4 = a1 - 3;
    if ( v4 )
    {
      if ( v4 == 1 )
      {
        inited = SkmmInitSystem(4, 0);
        if ( inited >= 0 )
        {
          inited = SkeInitSystem(4, 0);
          if ( inited >= 0 )
          {
            SkeInitializeXSave(4);
            SkInitTraceLoggining(0, 4);
            if ( (SkpFlags & 1) != 0 )
              McGenEventRegister_EtwRegister(
                SLEEPSTUDY_ETW_PROVIDER,
                v6,
                SLEEPSTUDY_ETW_PROVIDER_Context,
                SLEEPSTUDY_ETW_PROVIDER_Context);
            for ( i = *(const signed __int16 **)SkLoadedModuleList;
                  i != (const signed __int16 *)&SkLoadedModuleList;
                  i = *(const signed __int16 **)i )
            {
              if ( !_bittest16(i + 55, 9u) )
              {
                v8 = (__int64 (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)i + 7);
                if ( v8 )
                {
                  inited = v8(0, 0);
                  if ( inited < 0 )
                    goto LABEL_25;
                }
              }
            }
            SkpCopyKeysFromLoaderBlock();
            EntropyRegisterSource(
              &g_hExchangeVsmSource,
              ENTROPY_SOURCE_TYPE_HIGH_PUSH,
              L"Microsoft Windows Exchange VSM (SK side)");
            EntropyPoolTriggerReseedForIum(0);
            inited = BCryptGenRandom(0, pbBuffer, 0x20u, 2u);
            if ( inited >= 0 )
            {
              inited = SkKSAddKey(&IumMkPerBootHandle, pbBuffer, 32);
              if ( inited >= 0 )
              {
                inited = SkPreAllocatePageEncryptionResources();
                if ( inited >= 0 )
                {
                  inited = SkInitHiberCrashSupport(0, 0);
                  if ( inited >= 0 )
                  {
                    inited = SkmmInitializePageEncryption();
                    if ( inited >= 0 )
                    {
                      inited = SkmmCreateSecureSection(
                                 0,
                                 *(_QWORD *)(SkeLoaderBlock + 1464),
                                 *(_DWORD *)(SkeLoaderBlock + 1472),
                                 2,
                                 (__int64)&SkApisetSection);
                      if ( inited >= 0 )
                      {
                        SkInitializeKsr();
                        SkInitializeVmSvc();
                        v9 = *(_QWORD *)(SkeLoaderBlock + 1448);
                        if ( v9 )
                          SkmmFreeBootLoadedPages(v9, *(unsigned int *)(SkeLoaderBlock + 1456));
                        v10 = *(_QWORD *)(SkeLoaderBlock + 1408);
                        if ( v10 )
                          SkmmFreeBootLoadedPages(v10, *(unsigned int *)(SkeLoaderBlock + 1416));
                      }
                    }
                  }
                }
              }
            }
LABEL_25:
            SkWriteSecureKernelStartEvent((unsigned int)inited);
          }
        }
      }
      else
      {
        return (unsigned int)-1073741823;
      }
    }
    else if ( *(_DWORD *)(a2 + 40) == 104 )
    {
      RtlCopyVolatileMemory(v16, *(const void **)(a2 + 24), 0x68u);
      if ( v16[0] == 167772178 )
      {
        inited = SkmmInitSystem(3, v17 >> 12);
        if ( inited >= 0 )
        {
          IumInitializeSystem();
          *(_QWORD *)&v13 = v20 >> 12;
          *((_QWORD *)&v13 + 1) = v22 >> 12;
          v14 = v18;
          LODWORD(v15) = v16[1];
          *((_QWORD *)&v15 + 1) = v19;
          inited = SkpsCreateAndPrepareSystemProcess();
          if ( inited >= 0 )
          {
            inited = SkeInitSystem(3, &v13);
            if ( inited >= 0 )
            {
              LOBYTE(v11) = 1;
              SkobpNamespaceLock = 0;
              SkobpNamespaceTable = 0;
              qword_14014E8B8 = 0;
              inited = SkobCreateHandleTable(v11);
              if ( inited >= 0 )
              {
                inited = SkmmInitializeCodeIntegrity();
                if ( inited >= 0 )
                {
                  inited = SkpgInitSystem(v16);
                  if ( inited >= 0 )
                  {
                    inited = SkInitializeNls(SkLoadedModuleList);
                    if ( inited >= 0 )
                    {
                      inited = 0;
                      SkiHyperlaunchEntrypoint = v21;
                    }
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        return (unsigned int)-1073741735;
      }
    }
    else
    {
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    inited = 0;
    dword_14016A218 = ((*(_BYTE *)(SkeLoaderBlock + 1968) & 1) != 0) + 1;
    SkBootEnvironmentInformation = *(_OWORD *)(SkeLoaderBlock + 2100);
    qword_14016A220 = *(_QWORD *)(SkeLoaderBlock + 2088);
    SkpFlags = SkpFlags & 0xFFFFFFFE | (*(_DWORD *)(SkeLoaderBlock + 1440) >> 3) & 1;
    SkLoaderApiVersion = *(_DWORD *)(SkeLoaderBlock + 2096);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1400b86ec  push    rbp
0x1400b86ee  push    rbx
0x1400b86ef  push    rdi
0x1400b86f0  push    r14
0x1400b86f2  lea     rbp, [rsp-8]
0x1400b86f7  sub     rsp, 108h
0x1400b86fe  mov     rax, cs:__security_cookie
0x1400b8705  xor     rax, rsp
0x1400b8708  mov     [rbp+20h+var_30], rax
0x1400b870c  mov     rdi, rdx
0x1400b870f  mov     ebx, ecx
0x1400b8711  xor     edx, edx; Val
0x1400b8713  lea     rcx, [rsp+120h+var_C0]; void *
0x1400b8718  lea     r8d, [rdx+68h]; Size
0x1400b871c  call    memset_0
0x1400b8721  xorps   xmm0, xmm0
0x1400b8724  movups  [rsp+120h+var_F0], xmm0
0x1400b8729  movups  [rsp+120h+var_E0], xmm0
0x1400b872e  movups  [rsp+120h+var_D0], xmm0
0x1400b8733  test    ebx, ebx
0x1400b8735  jz      loc_1400B8A4D
0x1400b873b  mov     r14d, 3
0x1400b8741  sub     ebx, r14d
0x1400b8744  jz      loc_1400B891C
0x1400b874a  cmp     ebx, 1
0x1400b874d  jz      short loc_1400B8759
0x1400b874f  mov     ebx, 0C0000001h
0x1400b8754  jmp     loc_1400B8AB2
0x1400b8759  xor     edx, edx
0x1400b875b  lea     edi, [rdx+4]
0x1400b875e  mov     ecx, edi
0x1400b8760  call    SkmmInitSystem
0x1400b8765  mov     ebx, eax
0x1400b8767  test    eax, eax
0x1400b8769  js      loc_1400B8AB2
0x1400b876f  xor     edx, edx
0x1400b8771  mov     ecx, edi
0x1400b8773  call    SkeInitSystem
0x1400b8778  mov     ebx, eax
0x1400b877a  test    eax, eax
0x1400b877c  js      loc_1400B8AB2
0x1400b8782  mov     ecx, edi
0x1400b8784  call    SkeInitializeXSave
0x1400b8789  mov     edx, edi
0x1400b878b  xor     ecx, ecx
0x1400b878d  call    SkInitTraceLoggining
0x1400b8792  mov     eax, cs:SkpFlags
0x1400b8798  test    al, 1
0x1400b879a  jz      short loc_1400B87B2
0x1400b879c  lea     r8, SLEEPSTUDY_ETW_PROVIDER_Context
0x1400b87a3  mov     r9, r8
0x1400b87a6  lea     rcx, SLEEPSTUDY_ETW_PROVIDER
0x1400b87ad  call    McGenEventRegister_EtwRegister
0x1400b87b2  mov     rax, cs:SkLoadedModuleList
0x1400b87b9  lea     r14, SkLoadedModuleList
0x1400b87c0  mov     rdi, [rax]
0x1400b87c3  jmp     short loc_1400B87EC
0x1400b87c5  bt      word ptr [rdi+6Eh], 9
0x1400b87cb  jb      short loc_1400B87E9
0x1400b87cd  mov     rax, [rdi+38h]
0x1400b87d1  test    rax, rax
0x1400b87d4  jz      short loc_1400B87E9
0x1400b87d6  xor     edx, edx
0x1400b87d8  xor     ecx, ecx
0x1400b87da  call    rax
0x1400b87dc  nop     dword ptr [rax]
0x1400b87df  mov     ebx, eax
0x1400b87e1  test    eax, eax
0x1400b87e3  js      loc_1400B8910
0x1400b87e9  mov     rdi, [rdi]
0x1400b87ec  cmp     rdi, r14
0x1400b87ef  jnz     short loc_1400B87C5
0x1400b87f1  call    SkpCopyKeysFromLoaderBlock
0x1400b87f6  lea     r8, entropySourceName; "Microsoft Windows Exchange VSM (SK side"...
0x1400b87fd  mov     edx, 1; entropySourceType
0x1400b8802  lea     rcx, g_hExchangeVsmSource; phEntropySource
0x1400b8809  call    cs:__imp_EntropyRegisterSource
0x1400b8810  nop     dword ptr [rax+rax+00h]
0x1400b8815  xor     ecx, ecx
0x1400b8817  call    cs:__imp_EntropyPoolTriggerReseedForIum
0x1400b881e  nop     dword ptr [rax+rax+00h]
0x1400b8823  mov     r14d, 2
0x1400b8829  lea     rdx, [rbp+20h+pbBuffer]; pbBuffer
0x1400b882d  mov     r9d, r14d; dwFlags
0x1400b8830  xor     ecx, ecx; hAlgorithm
0x1400b8832  lea     edi, [r14+1Eh]
0x1400b8836  mov     r8d, edi; cbBuffer
0x1400b8839  call    cs:__imp_BCryptGenRandom
0x1400b8840  nop     dword ptr [rax+rax+00h]
0x1400b8845  mov     ebx, eax
0x1400b8847  test    eax, eax
0x1400b8849  js      loc_1400B8910
0x1400b884f  mov     r8d, edi
0x1400b8852  lea     rdx, [rbp+20h+pbBuffer]
0x1400b8856  lea     rcx, IumMkPerBootHandle
0x1400b885d  call    SkKSAddKey
0x1400b8862  mov     ebx, eax
0x1400b8864  test    eax, eax
0x1400b8866  js      loc_1400B8910
0x1400b886c  call    SkPreAllocatePageEncryptionResources
0x1400b8871  mov     ebx, eax
0x1400b8873  test    eax, eax
0x1400b8875  js      loc_1400B8910
0x1400b887b  xor     edx, edx
0x1400b887d  xor     ecx, ecx
0x1400b887f  call    SkInitHiberCrashSupport
0x1400b8884  mov     ebx, eax
0x1400b8886  test    eax, eax
0x1400b8888  js      loc_1400B8910
0x1400b888e  call    SkmmInitializePageEncryption
0x1400b8893  mov     ebx, eax
0x1400b8895  test    eax, eax
0x1400b8897  js      short loc_1400B8910
0x1400b8899  mov     rdx, cs:SkeLoaderBlock
0x1400b88a0  lea     rax, SkApisetSection
0x1400b88a7  mov     r9d, r14d
0x1400b88aa  mov     [rsp+120h+var_100], rax
0x1400b88af  xor     ecx, ecx
0x1400b88b1  mov     r8d, [rdx+5C0h]
0x1400b88b8  mov     rdx, [rdx+5B8h]
0x1400b88bf  call    SkmmCreateSecureSection
0x1400b88c4  mov     ebx, eax
0x1400b88c6  test    eax, eax
0x1400b88c8  js      short loc_1400B8910
0x1400b88ca  call    SkInitializeKsr
0x1400b88cf  call    SkInitializeVmSvc
0x1400b88d4  mov     rax, cs:SkeLoaderBlock
0x1400b88db  mov     rcx, [rax+5A8h]
0x1400b88e2  test    rcx, rcx
0x1400b88e5  jz      short loc_1400B88F2
0x1400b88e7  mov     edx, [rax+5B0h]
0x1400b88ed  call    SkmmFreeBootLoadedPages
0x1400b88f2  mov     rax, cs:SkeLoaderBlock
0x1400b88f9  mov     rcx, [rax+580h]
0x1400b8900  test    rcx, rcx
0x1400b8903  jz      short loc_1400B8910
0x1400b8905  mov     edx, [rax+588h]
0x1400b890b  call    SkmmFreeBootLoadedPages
0x1400b8910  mov     ecx, ebx
0x1400b8912  call    SkWriteSecureKernelStartEvent
0x1400b8917  jmp     loc_1400B8AB2
0x1400b891c  cmp     dword ptr [rdi+28h], 68h ; 'h'
0x1400b8920  jz      short loc_1400B892C
0x1400b8922  mov     ebx, 0C000000Dh
0x1400b8927  jmp     loc_1400B8AB2
0x1400b892c  mov     rdx, [rdi+18h]; Src
0x1400b8930  lea     rcx, [rsp+120h+var_C0]; void *
0x1400b8935  mov     r8d, 68h ; 'h'; Size
0x1400b893b  call    RtlCopyVolatileMemory
0x1400b8940  cmp     [rsp+120h+var_C0], 0A000012h
0x1400b8948  jz      short loc_1400B8954
0x1400b894a  mov     ebx, 0C0000059h
0x1400b894f  jmp     loc_1400B8AB2
0x1400b8954  mov     rdx, [rsp+120h+var_B8]
0x1400b8959  mov     ecx, r14d
0x1400b895c  shr     rdx, 0Ch
0x1400b8960  call    SkmmInitSystem
0x1400b8965  mov     ebx, eax
0x1400b8967  test    eax, eax
0x1400b8969  js      loc_1400B8AB2
0x1400b896f  call    IumInitializeSystem
0x1400b8974  mov     rax, [rbp+20h+var_70]
0x1400b8978  shr     rax, 0Ch
0x1400b897c  mov     qword ptr [rsp+120h+var_F0], rax
0x1400b8981  mov     rax, [rbp+20h+var_60]
0x1400b8985  shr     rax, 0Ch
0x1400b8989  mov     qword ptr [rsp+120h+var_F0+8], rax
0x1400b898e  mov     rax, qword ptr [rbp+20h+var_98]
0x1400b8992  mov     qword ptr [rsp+120h+var_E0], rax
0x1400b8997  mov     rax, qword ptr [rbp+20h+var_98+8]
0x1400b899b  mov     qword ptr [rsp+120h+var_E0+8], rax
0x1400b89a0  mov     eax, [rsp+120h+var_BC]
0x1400b89a4  mov     dword ptr [rsp+120h+var_D0], eax
0x1400b89a8  mov     rax, [rbp+20h+var_88]
0x1400b89ac  mov     qword ptr [rsp+120h+var_D0+8], rax
0x1400b89b1  call    SkpsCreateAndPrepareSystemProcess
0x1400b89b6  mov     ebx, eax
0x1400b89b8  test    eax, eax
0x1400b89ba  js      loc_1400B8AB2
0x1400b89c0  lea     rdx, [rsp+120h+var_F0]
0x1400b89c5  mov     ecx, r14d
0x1400b89c8  call    SkeInitSystem
0x1400b89cd  mov     ebx, eax
0x1400b89cf  test    eax, eax
0x1400b89d1  js      loc_1400B8AB2
0x1400b89d7  mov     cl, 1
0x1400b89d9  mov     cs:SkobpNamespaceLock, 0
0x1400b89e4  mov     cs:SkobpNamespaceTable, 0
0x1400b89ef  mov     cs:qword_14014E8B8, 0
0x1400b89fa  call    SkobCreateHandleTable
0x1400b89ff  mov     ebx, eax
0x1400b8a01  test    eax, eax
0x1400b8a03  js      loc_1400B8AB2
0x1400b8a09  call    SkmmInitializeCodeIntegrity
0x1400b8a0e  mov     ebx, eax
0x1400b8a10  test    eax, eax
0x1400b8a12  js      loc_1400B8AB2
0x1400b8a18  lea     rcx, [rsp+120h+var_C0]
0x1400b8a1d  call    SkpgInitSystem
0x1400b8a22  mov     ebx, eax
0x1400b8a24  test    eax, eax
0x1400b8a26  js      loc_1400B8AB2
0x1400b8a2c  mov     rcx, cs:SkLoadedModuleList
0x1400b8a33  call    SkInitializeNls
0x1400b8a38  mov     ebx, eax
0x1400b8a3a  test    eax, eax
0x1400b8a3c  js      short loc_1400B8AB2
0x1400b8a3e  mov     rax, [rbp+20h+var_68]
0x1400b8a42  xor     ebx, ebx
0x1400b8a44  mov     cs:SkiHyperlaunchEntrypoint, rax
0x1400b8a4b  jmp     short loc_1400B8AB2
0x1400b8a4d  mov     rdx, cs:SkeLoaderBlock
0x1400b8a54  xor     ebx, ebx
0x1400b8a56  mov     al, [rdx+7B0h]
0x1400b8a5c  and     al, 1
0x1400b8a5e  neg     al
0x1400b8a60  sbb     eax, eax
0x1400b8a62  neg     eax
0x1400b8a64  inc     eax
0x1400b8a66  mov     cs:dword_14016A218, eax
0x1400b8a6c  movups  xmm0, xmmword ptr [rdx+834h]
0x1400b8a73  movdqu  cs:SkBootEnvironmentInformation, xmm0
0x1400b8a7b  mov     rax, [rdx+828h]
0x1400b8a82  mov     cs:qword_14016A220, rax
0x1400b8a89  mov     ecx, [rdx+5A0h]
0x1400b8a8f  mov     eax, cs:SkpFlags
0x1400b8a95  shr     ecx, 3
0x1400b8a98  and     eax, 0FFFFFFFEh
0x1400b8a9b  and     ecx, 1
0x1400b8a9e  or      ecx, eax
0x1400b8aa0  mov     cs:SkpFlags, ecx
0x1400b8aa6  mov     eax, [rdx+830h]
0x1400b8aac  mov     cs:SkLoaderApiVersion, eax
0x1400b8ab2  mov     eax, ebx
0x1400b8ab4  mov     rcx, [rbp+20h+var_30]
0x1400b8ab8  xor     rcx, rsp; StackCookie
0x1400b8abb  call    __security_check_cookie
0x1400b8ac0  add     rsp, 108h
0x1400b8ac7  pop     r14
0x1400b8ac9  pop     rdi
0x1400b8aca  pop     rbx
0x1400b8acb  pop     rbp
0x1400b8acc  retn
```
