# WimFSFCreateIntegrity

- ea: `0x140028488`
- end: `0x1400287c3`
- name: `WimFSFCreateIntegrity`
- size: `827`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002abe8`
- `0x14002c53c`

## callees

- `0x140011640`
- `0x140028488`
- `0x1400287cc`
- `0x1400298c0`
- `0x140029a90`
- `0x140029d60`
- `0x140029e4c`
- `0x14002a040`
- `0x14002a394`
- `0x14002a480`
- `0x14002a700`
- `0x14002a848`

## import_xrefs

- `ntoskrnl!PsInitialSystemProcess` at `0x140028599`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14002856c`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140028680`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14002856c`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140028680`
- `ntoskrnl!MmUnmapViewOfSection` at `0x1400285a6`
- `ntoskrnl!MmUnmapViewOfSection` at `0x1400285a6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400285ba`
- `ntoskrnl!ObfDereferenceObject` at `0x1400285d2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400285ba`
- `ntoskrnl!ObfDereferenceObject` at `0x1400285d2`
- `FLTMGR!FltClose` at `0x1400285ea`
- `FLTMGR!FltClose` at `0x1400285ea`

## pseudocode

```c
__int64 __fastcall WimFSFCreateIntegrity(
        __int64 a1,
        __int64 a2,
        struct _FILE_OBJECT *a3,
        void *a4,
        unsigned __int64 a5,
        __int64 Val,
        char a7,
        char **a8)
{
  char *v10; // rsi
  PVOID v11; // r14
  __int64 v12; // r15
  int v13; // edi
  int v14; // eax
  __int64 v15; // rcx
  __int64 v17; // rdx
  int v18; // eax
  int v19; // eax
  char v20; // [rsp+40h] [rbp-40h] BYREF
  char v21; // [rsp+41h] [rbp-3Fh] BYREF
  char v22[2]; // [rsp+42h] [rbp-3Eh] BYREF
  unsigned int v23; // [rsp+44h] [rbp-3Ch] BYREF
  PRTL_BITMAP BitMapHeader; // [rsp+48h] [rbp-38h] BYREF
  __int64 v25; // [rsp+50h] [rbp-30h] BYREF
  __int64 v26; // [rsp+58h] [rbp-28h] BYREF
  PVOID Object; // [rsp+60h] [rbp-20h] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-18h] BYREF
  __int64 v29; // [rsp+70h] [rbp-10h] BYREF
  __int64 v30; // [rsp+78h] [rbp-8h] BYREF
  char v31; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v32; // [rsp+C8h] [rbp+48h] BYREF
  void *v33; // [rsp+D8h] [rbp+58h]

  v33 = a4;
  v32 = a2;
  v31 = 0;
  v10 = 0;
  FileHandle = 0;
  v11 = 0;
  Object = 0;
  v12 = 0;
  BitMapHeader = 0;
  v20 = 0;
  v22[0] = 0;
  v21 = 0;
  v23 = 0;
  v25 = 0;
  v26 = 0;
  v29 = 0;
  v30 = 0;
  if ( a1 == a2 )
  {
    v13 = 0;
    *a8 = 0;
    return (unsigned int)v13;
  }
  v14 = WimpFSFIntegrityOpenIntegrityFile(a1, Val, &FileHandle, (PFILE_OBJECT *)&Object);
  v13 = v14;
  if ( v14 < 0 )
  {
    if ( v14 != -1073741809 )
      goto LABEL_10;
    v13 = WimpFSFIsIntegrityMandatory(Val, &v20);
    if ( v13 < 0 )
      goto LABEL_10;
    if ( v20 )
    {
      v13 = WimpFSFIsBitLockerEnabled(a1, &v31);
      if ( v13 < 0 )
      {
LABEL_10:
        RtlRunOnceExecuteOnce(&g_WimIntegrityRunOnce, WimpFSFInitializeIntegrity, 0, 0);
        WimpFSFIntegrityReportIntegrityFileEvent(v15, v13, Val, &a3->FileName.Length);
        if ( v10 )
          WimFSFDestroyIntegrity(v10);
        if ( v12 )
          MmUnmapViewOfSection(PsInitialSystemProcess);
        if ( v11 )
          ObfDereferenceObject(v11);
        goto LABEL_16;
      }
      if ( v31 )
      {
        v13 = -1073741501;
        goto LABEL_10;
      }
    }
    goto LABEL_21;
  }
  v13 = WimpFSFIsBitLockerEnabled(a1, &v31);
  if ( v13 < 0 )
    goto LABEL_10;
  if ( !v31 )
  {
    if ( ZwUpdateWnfStateDataWrapper )
    {
      LODWORD(v32) = 3;
      ZwUpdateWnfStateDataWrapper(&WNF_FVE_WIM_HASH_DELETION_TRIGGER, &v32, 4);
    }
LABEL_21:
    *a8 = 0;
LABEL_22:
    v13 = 0;
    goto LABEL_16;
  }
  v13 = RtlRunOnceExecuteOnce(&g_WimIntegrityRunOnce, WimpFSFInitializeIntegrity, 0, 0);
  if ( v13 < 0 )
    goto LABEL_10;
  v13 = WimpFSFIntegrityValidateIntegrityFile(a1, (struct _FILE_OBJECT *)Object, v33, a5, &v21, v22, &v23, 0);
  if ( v13 < 0 )
    goto LABEL_10;
  if ( !v21 )
  {
    v13 = -1073741116;
    goto LABEL_10;
  }
  if ( !v22[0] )
  {
    v17 = Val;
    *a8 = 0;
    WimpFSFIntegrityReportIntegrityFileEventWithoutStatus(&WofIntegrityFileNotReadyEventId, v17, &a3->FileName.Length);
    goto LABEL_22;
  }
  v18 = WimpFSFMapIntegrityHashes(FileHandle, v23, (PVOID *)&v25, &v26, &v30, &v29);
  v12 = v26;
  v13 = v18;
  v11 = (PVOID)v25;
  if ( v18 < 0 )
    goto LABEL_10;
  v19 = WimpFSFIntegrityBuildContext(a3, a5, v25, v26, v30, v29, a7, &BitMapHeader);
  v10 = (char *)BitMapHeader;
  v13 = v19;
  if ( v19 < 0 )
    goto LABEL_10;
  v11 = 0;
  v12 = 0;
  v13 = WimpFSFIntegrityValidateWimHeader(BitMapHeader, v32, a3);
  if ( v13 < 0 )
    goto LABEL_10;
  WimpFSFIntegrityReportIntegrityFileEventWithoutStatus(&WofIntegrityFileOpenEventId, Val, &a3->FileName.Length);
  *a8 = v10;
LABEL_16:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140028488  mov     [rsp-38h+arg_18], r9
0x14002848d  mov     [rsp-38h+arg_8], rdx
0x140028492  push    rbp
0x140028493  push    rsi
0x140028494  push    rdi
0x140028495  push    r12
0x140028497  push    r13
0x140028499  push    r14
0x14002849b  push    r15
0x14002849d  mov     rbp, rsp
0x1400284a0  sub     rsp, 80h
0x1400284a7  mov     r12, rcx
0x1400284aa  mov     r13, r8
0x1400284ad  xor     ecx, ecx
0x1400284af  mov     [rbp+arg_0], cl
0x1400284b2  mov     esi, ecx
0x1400284b4  mov     [rbp+FileHandle], rcx
0x1400284b8  mov     r14d, ecx
0x1400284bb  mov     [rbp+Object], rcx
0x1400284bf  mov     r15d, ecx
0x1400284c2  mov     [rbp+BitMapHeader], rcx
0x1400284c6  mov     [rbp+var_40], cl
0x1400284c9  mov     [rbp+var_3E], cl
0x1400284cc  mov     [rbp+var_3F], cl
0x1400284cf  mov     [rbp+var_3C], ecx
0x1400284d2  mov     [rbp+var_30], rcx
0x1400284d6  mov     [rbp+var_28], rcx
0x1400284da  mov     [rbp+var_10], rcx
0x1400284de  mov     [rbp+var_8], rcx
0x1400284e2  cmp     r12, rdx
0x1400284e5  jnz     short loc_1400284F5
0x1400284e7  mov     rax, [rbp+arg_38]
0x1400284eb  mov     edi, ecx
0x1400284ed  mov     [rax], rcx
0x1400284f0  jmp     loc_1400285F6
0x1400284f5  mov     rdx, [rbp+Val]
0x1400284f9  lea     r9, [rbp+Object]
0x1400284fd  lea     r8, [rbp+FileHandle]
0x140028501  mov     rcx, r12
0x140028504  call    WimpFSFIntegrityOpenIntegrityFile
0x140028509  mov     edi, eax
0x14002850b  test    eax, eax
0x14002850d  jns     loc_140028617
0x140028513  cmp     eax, 0C000000Fh
0x140028518  jnz     short loc_140028558
0x14002851a  mov     rcx, [rbp+Val]; Val
0x14002851e  lea     rdx, [rbp+var_40]
0x140028522  call    WimpFSFIsIntegrityMandatory
0x140028527  mov     edi, eax
0x140028529  test    eax, eax
0x14002852b  js      short loc_140028558
0x14002852d  cmp     [rbp+var_40], sil
0x140028531  jz      loc_14002860C
0x140028537  lea     rdx, [rbp+arg_0]
0x14002853b  mov     rcx, r12
0x14002853e  call    WimpFSFIsBitLockerEnabled
0x140028543  mov     edi, eax
0x140028545  test    eax, eax
0x140028547  js      short loc_140028558
0x140028549  cmp     [rbp+arg_0], sil
0x14002854d  jz      loc_14002860C
0x140028553  mov     edi, 0C0000143h
0x140028558  xor     r9d, r9d; Context
0x14002855b  lea     rdx, WimpFSFInitializeIntegrity; InitFn
0x140028562  xor     r8d, r8d; Parameter
0x140028565  lea     rcx, g_WimIntegrityRunOnce; RunOnce
0x14002856c  call    cs:__imp_RtlRunOnceExecuteOnce
0x140028573  nop     dword ptr [rax+rax+00h]
0x140028578  mov     r8, [rbp+Val]
0x14002857c  lea     r9, [r13+58h]
0x140028580  mov     edx, edi
0x140028582  call    WimpFSFIntegrityReportIntegrityFileEvent
0x140028587  test    rsi, rsi
0x14002858a  jz      short loc_140028594
0x14002858c  mov     rcx, rsi; P
0x14002858f  call    WimFSFDestroyIntegrity
0x140028594  test    r15, r15
0x140028597  jz      short loc_1400285B2
0x140028599  mov     rcx, cs:__imp_PsInitialSystemProcess
0x1400285a0  mov     rdx, r15
0x1400285a3  mov     rcx, [rcx]
0x1400285a6  call    cs:__imp_MmUnmapViewOfSection
0x1400285ad  nop     dword ptr [rax+rax+00h]
0x1400285b2  test    r14, r14
0x1400285b5  jz      short loc_1400285C6
0x1400285b7  mov     rcx, r14; Object
0x1400285ba  call    cs:__imp_ObfDereferenceObject
0x1400285c1  nop     dword ptr [rax+rax+00h]
0x1400285c6  mov     rax, [rbp+Object]
0x1400285ca  test    rax, rax
0x1400285cd  jz      short loc_1400285DE
0x1400285cf  mov     rcx, rax; Object
0x1400285d2  call    cs:__imp_ObfDereferenceObject
0x1400285d9  nop     dword ptr [rax+rax+00h]
0x1400285de  mov     rax, [rbp+FileHandle]
0x1400285e2  test    rax, rax
0x1400285e5  jz      short loc_1400285F6
0x1400285e7  mov     rcx, rax; FileHandle
0x1400285ea  call    cs:__imp_FltClose
0x1400285f1  nop     dword ptr [rax+rax+00h]
0x1400285f6  mov     eax, edi
0x1400285f8  add     rsp, 80h
0x1400285ff  pop     r15
0x140028601  pop     r14
0x140028603  pop     r13
0x140028605  pop     r12
0x140028607  pop     rdi
0x140028608  pop     rsi
0x140028609  pop     rbp
0x14002860a  retn
0x14002860c  mov     rax, [rbp+arg_38]
0x140028610  mov     [rax], rsi
0x140028613  xor     edi, edi
0x140028615  jmp     short loc_1400285C6
0x140028617  lea     rdx, [rbp+arg_0]
0x14002861b  mov     rcx, r12
0x14002861e  call    WimpFSFIsBitLockerEnabled
0x140028623  mov     edi, eax
0x140028625  test    eax, eax
0x140028627  js      loc_140028558
0x14002862d  cmp     [rbp+arg_0], sil
0x140028631  jnz     short loc_14002866C
0x140028633  mov     rax, cs:ZwUpdateWnfStateDataWrapper
0x14002863a  test    rax, rax
0x14002863d  jz      short loc_14002860C
0x14002863f  xor     r9d, r9d
0x140028642  mov     dword ptr [rsp+80h+var_50], esi
0x140028646  mov     dword ptr [rsp+80h+var_58], esi
0x14002864a  lea     rdx, [rbp+arg_8]
0x14002864e  lea     rcx, WNF_FVE_WIM_HASH_DELETION_TRIGGER
0x140028655  mov     dword ptr [rbp+arg_8], 3
0x14002865c  mov     [rsp+80h+var_60], rsi
0x140028661  lea     r8d, [r9+4]
0x140028665  call    _guard_dispatch_icall
0x14002866a  jmp     short loc_14002860C
0x14002866c  xor     r9d, r9d; Context
0x14002866f  lea     rdx, WimpFSFInitializeIntegrity; InitFn
0x140028676  xor     r8d, r8d; Parameter
0x140028679  lea     rcx, g_WimIntegrityRunOnce; RunOnce
0x140028680  call    cs:__imp_RtlRunOnceExecuteOnce
0x140028687  nop     dword ptr [rax+rax+00h]
0x14002868c  mov     edi, eax
0x14002868e  test    eax, eax
0x140028690  js      loc_140028558
0x140028696  mov     r9, [rbp+arg_20]
0x14002869a  lea     rax, [rbp+var_3C]
0x14002869e  mov     r8, [rbp+arg_18]
0x1400286a2  mov     rcx, r12
0x1400286a5  mov     rdx, [rbp+Object]
0x1400286a9  mov     [rsp+80h+var_48], rsi
0x1400286ae  mov     qword ptr [rsp+80h+var_50], rax
0x1400286b3  lea     rax, [rbp+var_3E]
0x1400286b7  mov     [rsp+80h+var_58], rax
0x1400286bc  lea     rax, [rbp+var_3F]
0x1400286c0  mov     [rsp+80h+var_60], rax
0x1400286c5  call    WimpFSFIntegrityValidateIntegrityFile
0x1400286ca  mov     edi, eax
0x1400286cc  test    eax, eax
0x1400286ce  js      loc_140028558
0x1400286d4  cmp     [rbp+var_3F], sil
0x1400286d8  jnz     short loc_1400286E4
0x1400286da  mov     edi, 0C00002C4h
0x1400286df  jmp     loc_140028558
0x1400286e4  cmp     [rbp+var_3E], sil
0x1400286e8  jnz     short loc_14002870A
0x1400286ea  mov     rax, [rbp+arg_38]
0x1400286ee  lea     r8, [r13+58h]
0x1400286f2  mov     rdx, [rbp+Val]
0x1400286f6  lea     rcx, WofIntegrityFileNotReadyEventId; EventDescriptor
0x1400286fd  mov     [rax], rsi
0x140028700  call    WimpFSFIntegrityReportIntegrityFileEventWithoutStatus
0x140028705  jmp     loc_140028613
0x14002870a  mov     edx, [rbp+var_3C]
0x14002870d  lea     rax, [rbp+var_10]
0x140028711  mov     rcx, [rbp+FileHandle]; FileHandle
0x140028715  lea     r9, [rbp+var_28]
0x140028719  mov     [rsp+80h+var_58], rax; __int64
0x14002871e  lea     r8, [rbp+var_30]
0x140028722  lea     rax, [rbp+var_8]
0x140028726  mov     [rsp+80h+var_60], rax; __int64
0x14002872b  call    WimpFSFMapIntegrityHashes
0x140028730  mov     r15, [rbp+var_28]
0x140028734  mov     edi, eax
0x140028736  mov     r14, [rbp+var_30]
0x14002873a  test    eax, eax
0x14002873c  js      loc_140028558
0x140028742  mov     rdx, [rbp+arg_20]
0x140028746  lea     rax, [rbp+BitMapHeader]
0x14002874a  mov     [rsp+80h+var_48], rax; __int64
0x14002874f  mov     r9, r15
0x140028752  mov     al, [rbp+arg_30]
0x140028755  mov     r8, r14
0x140028758  mov     [rsp+80h+var_50], al; char
0x14002875c  mov     rcx, r13; Object
0x14002875f  mov     rax, [rbp+var_10]
0x140028763  mov     [rsp+80h+var_58], rax; __int64
0x140028768  mov     rax, [rbp+var_8]
0x14002876c  mov     [rsp+80h+var_60], rax; __int64
0x140028771  call    WimpFSFIntegrityBuildContext
0x140028776  mov     rsi, [rbp+BitMapHeader]
0x14002877a  mov     edi, eax
0x14002877c  test    eax, eax
0x14002877e  js      loc_140028558
0x140028784  mov     rdx, [rbp+arg_8]
0x140028788  mov     r8, r13
0x14002878b  mov     rcx, rsi; BitMapHeader
0x14002878e  xor     r14d, r14d
0x140028791  xor     r15d, r15d
0x140028794  call    WimpFSFIntegrityValidateWimHeader
0x140028799  mov     edi, eax
0x14002879b  test    eax, eax
0x14002879d  js      loc_140028558
0x1400287a3  mov     rdx, [rbp+Val]
0x1400287a7  lea     r8, [r13+58h]
0x1400287ab  lea     rcx, WofIntegrityFileOpenEventId; EventDescriptor
0x1400287b2  call    WimpFSFIntegrityReportIntegrityFileEventWithoutStatus
0x1400287b7  mov     rax, [rbp+arg_38]
0x1400287bb  mov     [rax], rsi
0x1400287be  jmp     loc_1400285C6
```
