# WimFSFCreateIntegrity

- ea: `0x1400284d8`
- end: `0x140028813`
- name: `WimFSFCreateIntegrity`
- size: `827`
- prototype: `__int64 __fastcall(__int64, __int64, char *, __int64, __int64, __int64 Val, char, PRTL_BITMAP *)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002ac38`
- `0x14002c58c`

## callees

- `0x140011640`
- `0x1400284d8`
- `0x14002881c`
- `0x140029910`
- `0x140029ae0`
- `0x140029db0`
- `0x140029e9c`
- `0x14002a090`
- `0x14002a3e4`
- `0x14002a4d0`
- `0x14002a750`
- `0x14002a898`

## import_xrefs

- `ntoskrnl!PsInitialSystemProcess` at `0x1400285e9`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1400285bc`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1400286d0`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1400285bc`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1400286d0`
- `ntoskrnl!MmUnmapViewOfSection` at `0x1400285f6`
- `ntoskrnl!MmUnmapViewOfSection` at `0x1400285f6`
- `ntoskrnl!ObfDereferenceObject` at `0x14002860a`
- `ntoskrnl!ObfDereferenceObject` at `0x140028622`
- `ntoskrnl!ObfDereferenceObject` at `0x14002860a`
- `ntoskrnl!ObfDereferenceObject` at `0x140028622`
- `FLTMGR!FltClose` at `0x14002863a`
- `FLTMGR!FltClose` at `0x14002863a`

## pseudocode

```c
__int64 __fastcall WimFSFCreateIntegrity(
        __int64 a1,
        __int64 a2,
        char *a3,
        __int64 a4,
        __int64 a5,
        __int64 Val,
        char a7,
        PRTL_BITMAP *a8)
{
  PRTL_BITMAP v10; // rsi
  PVOID v11; // r14
  __int64 v12; // r15
  NTSTATUS v13; // edi
  int v14; // eax
  __int64 v15; // rcx
  int v17; // eax
  int v18; // eax
  char v19; // [rsp+41h] [rbp-3Fh] BYREF
  _BYTE v20[2]; // [rsp+42h] [rbp-3Eh] BYREF
  unsigned int v21; // [rsp+44h] [rbp-3Ch] BYREF
  PRTL_BITMAP BitMapHeader; // [rsp+48h] [rbp-38h] BYREF
  PVOID v23; // [rsp+50h] [rbp-30h] BYREF
  __int64 v24; // [rsp+58h] [rbp-28h] BYREF
  PVOID Object; // [rsp+60h] [rbp-20h] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-18h] BYREF
  __int64 v27; // [rsp+70h] [rbp-10h] BYREF
  __int64 v28; // [rsp+78h] [rbp-8h] BYREF
  char v29; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v30; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v31; // [rsp+D8h] [rbp+58h]

  v31 = a4;
  v30 = a2;
  v29 = 0;
  v10 = 0;
  FileHandle = 0;
  v11 = 0;
  Object = 0;
  v12 = 0;
  BitMapHeader = 0;
  v20[0] = 0;
  v19 = 0;
  v21 = 0;
  v23 = 0;
  v24 = 0;
  v27 = 0;
  v28 = 0;
  if ( a1 == a2 )
  {
    v13 = 0;
    *a8 = 0;
    return (unsigned int)v13;
  }
  v14 = WimpFSFIntegrityOpenIntegrityFile(a1, Val, &FileHandle, &Object);
  v13 = v14;
  if ( v14 < 0 )
  {
    if ( v14 != -1073741809 )
      goto LABEL_6;
    v13 = WimpFSFIsIntegrityMandatory(Val);
    if ( v13 < 0 )
      goto LABEL_6;
    goto LABEL_17;
  }
  v13 = WimpFSFIsBitLockerEnabled(a1, &v29);
  if ( v13 < 0 )
  {
LABEL_6:
    RtlRunOnceExecuteOnce(&g_WimIntegrityRunOnce, WimpFSFInitializeIntegrity, 0, 0);
    WimpFSFIntegrityReportIntegrityFileEvent(v15, (unsigned int)v13, Val, a3 + 88);
    if ( v10 )
      WimFSFDestroyIntegrity(v10);
    if ( v12 )
      MmUnmapViewOfSection(PsInitialSystemProcess, v12);
    if ( v11 )
      ObfDereferenceObject(v11);
    goto LABEL_12;
  }
  if ( !v29 )
  {
    if ( ZwUpdateWnfStateDataWrapper )
    {
      LODWORD(v30) = 3;
      ZwUpdateWnfStateDataWrapper(&WNF_FVE_WIM_HASH_DELETION_TRIGGER, &v30, 4);
    }
LABEL_17:
    *a8 = 0;
LABEL_18:
    v13 = 0;
    goto LABEL_12;
  }
  v13 = RtlRunOnceExecuteOnce(&g_WimIntegrityRunOnce, WimpFSFInitializeIntegrity, 0, 0);
  if ( v13 < 0 )
    goto LABEL_6;
  v13 = WimpFSFIntegrityValidateIntegrityFile(a1, Object, v31, a5, &v19, v20, &v21, 0);
  if ( v13 < 0 )
    goto LABEL_6;
  if ( !v19 )
  {
    v13 = -1073741116;
    goto LABEL_6;
  }
  if ( !v20[0] )
  {
    *a8 = 0;
    WimpFSFIntegrityReportIntegrityFileEventWithoutStatus(&WofIntegrityFileNotReadyEventId);
    goto LABEL_18;
  }
  v17 = WimpFSFMapIntegrityHashes(FileHandle, v21, &v23, &v24, &v28, &v27);
  v12 = v24;
  v13 = v17;
  v11 = v23;
  if ( v17 < 0 )
    goto LABEL_6;
  v18 = WimpFSFIntegrityBuildContext(a3, v28, v27, a7, (__int64)&BitMapHeader);
  v10 = BitMapHeader;
  v13 = v18;
  if ( v18 < 0 )
    goto LABEL_6;
  v11 = 0;
  v12 = 0;
  v13 = WimpFSFIntegrityValidateWimHeader(BitMapHeader);
  if ( v13 < 0 )
    goto LABEL_6;
  WimpFSFIntegrityReportIntegrityFileEventWithoutStatus(&WofIntegrityFileOpenEventId);
  *a8 = v10;
LABEL_12:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400284d8  mov     [rsp-38h+arg_18], r9
0x1400284dd  mov     [rsp-38h+arg_8], rdx
0x1400284e2  push    rbp
0x1400284e3  push    rsi
0x1400284e4  push    rdi
0x1400284e5  push    r12
0x1400284e7  push    r13
0x1400284e9  push    r14
0x1400284eb  push    r15
0x1400284ed  mov     rbp, rsp
0x1400284f0  sub     rsp, 80h
0x1400284f7  mov     r12, rcx
0x1400284fa  mov     r13, r8
0x1400284fd  xor     ecx, ecx
0x1400284ff  mov     [rbp+arg_0], cl
0x140028502  mov     esi, ecx
0x140028504  mov     [rbp+FileHandle], rcx
0x140028508  mov     r14d, ecx
0x14002850b  mov     [rbp+Object], rcx
0x14002850f  mov     r15d, ecx
0x140028512  mov     [rbp+BitMapHeader], rcx
0x140028516  mov     [rbp+var_40], cl
0x140028519  mov     [rbp+var_3E], cl
0x14002851c  mov     [rbp+var_3F], cl
0x14002851f  mov     [rbp+var_3C], ecx
0x140028522  mov     [rbp+var_30], rcx
0x140028526  mov     [rbp+var_28], rcx
0x14002852a  mov     [rbp+var_10], rcx
0x14002852e  mov     [rbp+var_8], rcx
0x140028532  cmp     r12, rdx
0x140028535  jnz     short loc_140028545
0x140028537  mov     rax, [rbp+arg_38]
0x14002853b  mov     edi, ecx
0x14002853d  mov     [rax], rcx
0x140028540  jmp     loc_140028646
0x140028545  mov     rdx, [rbp+Val]
0x140028549  lea     r9, [rbp+Object]
0x14002854d  lea     r8, [rbp+FileHandle]
0x140028551  mov     rcx, r12
0x140028554  call    WimpFSFIntegrityOpenIntegrityFile
0x140028559  mov     edi, eax
0x14002855b  test    eax, eax
0x14002855d  jns     loc_140028667
0x140028563  cmp     eax, 0C000000Fh
0x140028568  jnz     short loc_1400285A8
0x14002856a  mov     rcx, [rbp+Val]; Val
0x14002856e  lea     rdx, [rbp+var_40]
0x140028572  call    WimpFSFIsIntegrityMandatory
0x140028577  mov     edi, eax
0x140028579  test    eax, eax
0x14002857b  js      short loc_1400285A8
0x14002857d  cmp     [rbp+var_40], sil
0x140028581  jz      loc_14002865C
0x140028587  lea     rdx, [rbp+arg_0]
0x14002858b  mov     rcx, r12
0x14002858e  call    WimpFSFIsBitLockerEnabled
0x140028593  mov     edi, eax
0x140028595  test    eax, eax
0x140028597  js      short loc_1400285A8
0x140028599  cmp     [rbp+arg_0], sil
0x14002859d  jz      loc_14002865C
0x1400285a3  mov     edi, 0C0000143h
0x1400285a8  xor     r9d, r9d; Context
0x1400285ab  lea     rdx, WimpFSFInitializeIntegrity; InitFn
0x1400285b2  xor     r8d, r8d; Parameter
0x1400285b5  lea     rcx, g_WimIntegrityRunOnce; RunOnce
0x1400285bc  call    cs:__imp_RtlRunOnceExecuteOnce
0x1400285c3  nop     dword ptr [rax+rax+00h]
0x1400285c8  mov     r8, [rbp+Val]
0x1400285cc  lea     r9, [r13+58h]
0x1400285d0  mov     edx, edi
0x1400285d2  call    WimpFSFIntegrityReportIntegrityFileEvent
0x1400285d7  test    rsi, rsi
0x1400285da  jz      short loc_1400285E4
0x1400285dc  mov     rcx, rsi; P
0x1400285df  call    WimFSFDestroyIntegrity
0x1400285e4  test    r15, r15
0x1400285e7  jz      short loc_140028602
0x1400285e9  mov     rcx, cs:__imp_PsInitialSystemProcess
0x1400285f0  mov     rdx, r15
0x1400285f3  mov     rcx, [rcx]
0x1400285f6  call    cs:__imp_MmUnmapViewOfSection
0x1400285fd  nop     dword ptr [rax+rax+00h]
0x140028602  test    r14, r14
0x140028605  jz      short loc_140028616
0x140028607  mov     rcx, r14; Object
0x14002860a  call    cs:__imp_ObfDereferenceObject
0x140028611  nop     dword ptr [rax+rax+00h]
0x140028616  mov     rax, [rbp+Object]
0x14002861a  test    rax, rax
0x14002861d  jz      short loc_14002862E
0x14002861f  mov     rcx, rax; Object
0x140028622  call    cs:__imp_ObfDereferenceObject
0x140028629  nop     dword ptr [rax+rax+00h]
0x14002862e  mov     rax, [rbp+FileHandle]
0x140028632  test    rax, rax
0x140028635  jz      short loc_140028646
0x140028637  mov     rcx, rax; FileHandle
0x14002863a  call    cs:__imp_FltClose
0x140028641  nop     dword ptr [rax+rax+00h]
0x140028646  mov     eax, edi
0x140028648  add     rsp, 80h
0x14002864f  pop     r15
0x140028651  pop     r14
0x140028653  pop     r13
0x140028655  pop     r12
0x140028657  pop     rdi
0x140028658  pop     rsi
0x140028659  pop     rbp
0x14002865a  retn
0x14002865c  mov     rax, [rbp+arg_38]
0x140028660  mov     [rax], rsi
0x140028663  xor     edi, edi
0x140028665  jmp     short loc_140028616
0x140028667  lea     rdx, [rbp+arg_0]
0x14002866b  mov     rcx, r12
0x14002866e  call    WimpFSFIsBitLockerEnabled
0x140028673  mov     edi, eax
0x140028675  test    eax, eax
0x140028677  js      loc_1400285A8
0x14002867d  cmp     [rbp+arg_0], sil
0x140028681  jnz     short loc_1400286BC
0x140028683  mov     rax, cs:ZwUpdateWnfStateDataWrapper
0x14002868a  test    rax, rax
0x14002868d  jz      short loc_14002865C
0x14002868f  xor     r9d, r9d
0x140028692  mov     dword ptr [rsp+80h+var_50], esi
0x140028696  mov     dword ptr [rsp+80h+var_58], esi
0x14002869a  lea     rdx, [rbp+arg_8]
0x14002869e  lea     rcx, WNF_FVE_WIM_HASH_DELETION_TRIGGER
0x1400286a5  mov     dword ptr [rbp+arg_8], 3
0x1400286ac  mov     [rsp+80h+var_60], rsi
0x1400286b1  lea     r8d, [r9+4]
0x1400286b5  call    _guard_dispatch_icall
0x1400286ba  jmp     short loc_14002865C
0x1400286bc  xor     r9d, r9d; Context
0x1400286bf  lea     rdx, WimpFSFInitializeIntegrity; InitFn
0x1400286c6  xor     r8d, r8d; Parameter
0x1400286c9  lea     rcx, g_WimIntegrityRunOnce; RunOnce
0x1400286d0  call    cs:__imp_RtlRunOnceExecuteOnce
0x1400286d7  nop     dword ptr [rax+rax+00h]
0x1400286dc  mov     edi, eax
0x1400286de  test    eax, eax
0x1400286e0  js      loc_1400285A8
0x1400286e6  mov     r9, [rbp+arg_20]
0x1400286ea  lea     rax, [rbp+var_3C]
0x1400286ee  mov     r8, [rbp+arg_18]
0x1400286f2  mov     rcx, r12
0x1400286f5  mov     rdx, [rbp+Object]
0x1400286f9  mov     [rsp+80h+var_48], rsi
0x1400286fe  mov     qword ptr [rsp+80h+var_50], rax
0x140028703  lea     rax, [rbp+var_3E]
0x140028707  mov     [rsp+80h+var_58], rax
0x14002870c  lea     rax, [rbp+var_3F]
0x140028710  mov     [rsp+80h+var_60], rax
0x140028715  call    WimpFSFIntegrityValidateIntegrityFile
0x14002871a  mov     edi, eax
0x14002871c  test    eax, eax
0x14002871e  js      loc_1400285A8
0x140028724  cmp     [rbp+var_3F], sil
0x140028728  jnz     short loc_140028734
0x14002872a  mov     edi, 0C00002C4h
0x14002872f  jmp     loc_1400285A8
0x140028734  cmp     [rbp+var_3E], sil
0x140028738  jnz     short loc_14002875A
0x14002873a  mov     rax, [rbp+arg_38]
0x14002873e  lea     r8, [r13+58h]
0x140028742  mov     rdx, [rbp+Val]
0x140028746  lea     rcx, WofIntegrityFileNotReadyEventId; EventDescriptor
0x14002874d  mov     [rax], rsi
0x140028750  call    WimpFSFIntegrityReportIntegrityFileEventWithoutStatus
0x140028755  jmp     loc_140028663
0x14002875a  mov     edx, [rbp+var_3C]
0x14002875d  lea     rax, [rbp+var_10]
0x140028761  mov     rcx, [rbp+FileHandle]; FileHandle
0x140028765  lea     r9, [rbp+var_28]
0x140028769  mov     [rsp+80h+var_58], rax; __int64
0x14002876e  lea     r8, [rbp+var_30]
0x140028772  lea     rax, [rbp+var_8]
0x140028776  mov     [rsp+80h+var_60], rax; __int64
0x14002877b  call    WimpFSFMapIntegrityHashes
0x140028780  mov     r15, [rbp+var_28]
0x140028784  mov     edi, eax
0x140028786  mov     r14, [rbp+var_30]
0x14002878a  test    eax, eax
0x14002878c  js      loc_1400285A8
0x140028792  mov     rdx, [rbp+arg_20]
0x140028796  lea     rax, [rbp+BitMapHeader]
0x14002879a  mov     [rsp+80h+var_48], rax; __int64
0x14002879f  mov     r9, r15
0x1400287a2  mov     al, [rbp+arg_30]
0x1400287a5  mov     r8, r14
0x1400287a8  mov     [rsp+80h+var_50], al; char
0x1400287ac  mov     rcx, r13; Object
0x1400287af  mov     rax, [rbp+var_10]
0x1400287b3  mov     [rsp+80h+var_58], rax; __int64
0x1400287b8  mov     rax, [rbp+var_8]
0x1400287bc  mov     [rsp+80h+var_60], rax; __int64
0x1400287c1  call    WimpFSFIntegrityBuildContext
0x1400287c6  mov     rsi, [rbp+BitMapHeader]
0x1400287ca  mov     edi, eax
0x1400287cc  test    eax, eax
0x1400287ce  js      loc_1400285A8
0x1400287d4  mov     rdx, [rbp+arg_8]
0x1400287d8  mov     r8, r13
0x1400287db  mov     rcx, rsi; BitMapHeader
0x1400287de  xor     r14d, r14d
0x1400287e1  xor     r15d, r15d
0x1400287e4  call    WimpFSFIntegrityValidateWimHeader
0x1400287e9  mov     edi, eax
0x1400287eb  test    eax, eax
0x1400287ed  js      loc_1400285A8
0x1400287f3  mov     rdx, [rbp+Val]
0x1400287f7  lea     r8, [r13+58h]
0x1400287fb  lea     rcx, WofIntegrityFileOpenEventId; EventDescriptor
0x140028802  call    WimpFSFIntegrityReportIntegrityFileEventWithoutStatus
0x140028807  mov     rax, [rbp+arg_38]
0x14002880b  mov     [rax], rsi
0x14002880e  jmp     loc_140028616
```
