# WofInstanceSetup

- ea: `0x14003bc70`
- end: `0x14003be7b`
- name: `WofInstanceSetup`
- size: `523`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x14000dbd8`
- `0x14000dc88`
- `0x14000dd74`
- `0x14003bc70`
- `0x14003e2d4`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003bcd0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003bcec`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003bd51`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003be5d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003bcd0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003bcec`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003bd51`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003be5d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14003bdcf`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14003bdcf`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003bcb8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003bd3c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003be48`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003bcb8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003bd3c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003be48`
- `FLTMGR!FltDeleteInstanceContext` at `0x14003be12`
- `FLTMGR!FltDeleteInstanceContext` at `0x14003be12`
- `FLTMGR!FltReleaseContext` at `0x14003bde8`
- `FLTMGR!FltReleaseContext` at `0x14003be00`
- `FLTMGR!FltReleaseContext` at `0x14003bde8`
- `FLTMGR!FltReleaseContext` at `0x14003be00`

## pseudocode

```c
__int64 __fastcall WofInstanceSetup(__int64 a1, int a2, __int64 a3, int a4)
{
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  int v11; // eax
  char v12; // bl
  int v13; // edx
  PFLT_CONTEXT v14; // rdi
  unsigned int v15; // ebx
  NTSTATUS v16; // eax
  int v17; // edx
  int v18; // r8d
  int Context; // [rsp+20h] [rbp-50h]
  PFLT_CONTEXT v20; // [rsp+40h] [rbp-30h] BYREF
  _OWORD Parameter[2]; // [rsp+48h] [rbp-28h] BYREF

  v20 = 0;
  memset(Parameter, 0, 28);
  if ( a4 != 2 && a4 != 28 )
    return 3223060495LL;
  ExAcquireFastMutexUnsafe(&FastMutex);
  if ( byte_140018464 )
  {
    ExReleaseFastMutexUnsafe(&FastMutex);
    return 3223060495LL;
  }
  ++dword_140018468;
  ExReleaseFastMutexUnsafe(&FastMutex);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_lLD(WPP_GLOBAL_Control->DeviceExtension, v8, v9, v10);
  v11 = WofAttachVolumeContext(a1, a4, &v20);
  v12 = v11;
  if ( v11 < 0 )
  {
    ExAcquireFastMutexUnsafe(&FastMutex);
    --dword_140018468;
    ExReleaseFastMutexUnsafe(&FastMutex);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        4,
        18,
        (__int64)WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids,
        v12);
    }
    return 3223060495LL;
  }
  v14 = v20;
  *((_QWORD *)&Parameter[0] + 1) = v20;
  LODWORD(Parameter[0]) = 0;
  *(_QWORD *)&Parameter[1] = a1;
  DWORD2(Parameter[1]) = a2;
  if ( KeExpandKernelStackAndCalloutEx(WofInstanceSetupNewStack, Parameter, 0x6000u, 0, 0) < 0
    || SLODWORD(Parameter[0]) < 0 )
  {
    v15 = -1071906801;
    FltReleaseContext(v14);
    v16 = FltDeleteInstanceContext(*(PFLT_INSTANCE *)(a1 + 24), 0);
    if ( v16 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(WPP_GLOBAL_Control->DeviceExtension, v17, v18, 19, Context, v16);
    ExAcquireFastMutexUnsafe(&FastMutex);
    --dword_140018468;
    ExReleaseFastMutexUnsafe(&FastMutex);
  }
  else
  {
    FltReleaseContext(v14);
    return 0;
  }
  return v15;
}

```

## disassembly

```asm
0x14003bc70  push    rbp
0x14003bc72  push    rbx
0x14003bc73  push    rsi
0x14003bc74  push    rdi
0x14003bc75  push    r13
0x14003bc77  push    r14
0x14003bc79  push    r15
0x14003bc7b  mov     rbp, rsp
0x14003bc7e  sub     rsp, 70h
0x14003bc82  xorps   xmm0, xmm0
0x14003bc85  mov     [rbp+var_30], 0
0x14003bc8d  xor     eax, eax
0x14003bc8f  mov     ebx, r9d
0x14003bc92  mov     edi, r8d
0x14003bc95  mov     r14d, edx
0x14003bc98  mov     rsi, rcx
0x14003bc9b  movups  [rbp+Parameter], xmm0
0x14003bc9f  movups  [rbp+Parameter+0Ch], xmm0
0x14003bca3  cmp     r9d, 2
0x14003bca7  jz      short loc_14003BCAE
0x14003bca9  cmp     ebx, 1Ch
0x14003bcac  jnz     short loc_14003BCDC
0x14003bcae  lea     r15, FastMutex
0x14003bcb5  mov     rcx, r15; FastMutex
0x14003bcb8  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003bcbf  nop     dword ptr [rax+rax+00h]
0x14003bcc4  cmp     cs:byte_140018464, 0
0x14003bccb  mov     rcx, r15; FastMutex
0x14003bcce  jz      short loc_14003BCE6
0x14003bcd0  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003bcd7  nop     dword ptr [rax+rax+00h]
0x14003bcdc  mov     eax, 0C01C000Fh
0x14003bce1  jmp     loc_14003BE6B
0x14003bce6  inc     cs:dword_140018468
0x14003bcec  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003bcf3  nop     dword ptr [rax+rax+00h]
0x14003bcf8  lea     r13, WPP_RECORDER_INITIALIZED
0x14003bcff  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003bd06  jz      short loc_14003BD25
0x14003bd08  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bd0f  mov     [rsp+70h+var_38], r14d
0x14003bd14  mov     [rsp+70h+var_40], ebx
0x14003bd18  mov     [rsp+70h+var_48], edi
0x14003bd1c  mov     rcx, [rcx+40h]
0x14003bd20  call    WPP_RECORDER_SF_lLD
0x14003bd25  lea     r8, [rbp+var_30]
0x14003bd29  mov     edx, ebx
0x14003bd2b  mov     rcx, rsi
0x14003bd2e  call    WofAttachVolumeContext
0x14003bd33  mov     ebx, eax
0x14003bd35  test    eax, eax
0x14003bd37  jns     short loc_14003BD9B
0x14003bd39  mov     rcx, r15; FastMutex
0x14003bd3c  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003bd43  nop     dword ptr [rax+rax+00h]
0x14003bd48  dec     cs:dword_140018468
0x14003bd4e  mov     rcx, r15; FastMutex
0x14003bd51  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003bd58  nop     dword ptr [rax+rax+00h]
0x14003bd5d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003bd64  jz      loc_14003BCDC
0x14003bd6a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bd71  lea     rax, WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids
0x14003bd78  mov     r9d, 12h
0x14003bd7e  mov     [rsp+70h+var_48], ebx
0x14003bd82  mov     dl, 2
0x14003bd84  mov     [rsp+70h+Context], rax
0x14003bd89  mov     rcx, [rcx+40h]
0x14003bd8d  lea     r8d, [r9-0Eh]
0x14003bd91  call    WPP_RECORDER_SF_d
0x14003bd96  jmp     loc_14003BCDC
0x14003bd9b  mov     rdi, [rbp+var_30]
0x14003bd9f  lea     rdx, [rbp+Parameter]; Parameter
0x14003bda3  xor     r9d, r9d; Wait
0x14003bda6  mov     qword ptr [rbp+Parameter+8], rdi
0x14003bdaa  mov     r8d, 6000h; Size
0x14003bdb0  mov     dword ptr [rbp+Parameter], 0
0x14003bdb7  lea     rcx, WofInstanceSetupNewStack; Callout
0x14003bdbe  mov     [rbp+var_18], rsi
0x14003bdc2  mov     [rbp+var_10], r14d
0x14003bdc6  mov     [rsp+70h+Context], 0; Context
0x14003bdcf  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14003bdd6  nop     dword ptr [rax+rax+00h]
0x14003bddb  test    eax, eax
0x14003bddd  js      short loc_14003BDF8
0x14003bddf  cmp     dword ptr [rbp+Parameter], 0
0x14003bde3  jl      short loc_14003BDF8
0x14003bde5  mov     rcx, rdi; Context
0x14003bde8  call    cs:__imp_FltReleaseContext
0x14003bdef  nop     dword ptr [rax+rax+00h]
0x14003bdf4  xor     ebx, ebx
0x14003bdf6  jmp     short loc_14003BE69
0x14003bdf8  mov     rcx, rdi; Context
0x14003bdfb  mov     ebx, 0C01C000Fh
0x14003be00  call    cs:__imp_FltReleaseContext
0x14003be07  nop     dword ptr [rax+rax+00h]
0x14003be0c  mov     rcx, [rsi+18h]; Instance
0x14003be10  xor     edx, edx; OldContext
0x14003be12  call    cs:__imp_FltDeleteInstanceContext
0x14003be19  nop     dword ptr [rax+rax+00h]
0x14003be1e  test    eax, eax
0x14003be20  jns     short loc_14003BE45
0x14003be22  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003be29  jz      short loc_14003BE45
0x14003be2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003be32  mov     r9d, 13h
0x14003be38  mov     [rsp+70h+var_48], eax
0x14003be3c  mov     rcx, [rcx+40h]
0x14003be40  call    WPP_RECORDER_SF_D
0x14003be45  mov     rcx, r15; FastMutex
0x14003be48  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003be4f  nop     dword ptr [rax+rax+00h]
0x14003be54  dec     cs:dword_140018468
0x14003be5a  mov     rcx, r15; FastMutex
0x14003be5d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003be64  nop     dword ptr [rax+rax+00h]
0x14003be69  mov     eax, ebx
0x14003be6b  add     rsp, 70h
0x14003be6f  pop     r15
0x14003be71  pop     r14
0x14003be73  pop     r13
0x14003be75  pop     rdi
0x14003be76  pop     rsi
0x14003be77  pop     rbx
0x14003be78  pop     rbp
0x14003be79  retn
```
