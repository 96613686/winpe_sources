# WcPreRead

- ea: `0x1400033a0`
- end: `0x140003922`
- name: `WcPreRead`
- size: `1410`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x140001b00`
- `0x1400033a0`
- `0x140004198`
- `0x140007c60`
- `0x140007dc0`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x14000362c`
- `ntoskrnl!PsIsHostSilo` at `0x14000362c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400037ed`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400037ed`
- `ntoskrnl!IoGetSilo` at `0x140003613`
- `ntoskrnl!IoGetSilo` at `0x140003613`
- `ntoskrnl!EtwWriteTransfer` at `0x1400034ff`
- `ntoskrnl!EtwWriteTransfer` at `0x1400034ff`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400035d3`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400035d3`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400035ef`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400038c3`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400035ef`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400038c3`
- `FLTMGR!FltAcquireResourceShared` at `0x1400037a2`
- `FLTMGR!FltAcquireResourceShared` at `0x1400037a2`
- `FLTMGR!FltReadFileEx` at `0x14000375a`
- `FLTMGR!FltReadFileEx` at `0x14000375a`
- `FLTMGR!FltReleaseResource` at `0x140003860`
- `FLTMGR!FltReleaseResource` at `0x140003881`
- `FLTMGR!FltReleaseResource` at `0x140003860`
- `FLTMGR!FltReleaseResource` at `0x140003881`
- `FLTMGR!FltLockUserBuffer` at `0x140003702`
- `FLTMGR!FltLockUserBuffer` at `0x140003702`
- `FLTMGR!FltGetFileContext` at `0x14000359d`
- `FLTMGR!FltGetFileContext` at `0x14000359d`
- `FLTMGR!FltGetStreamContext` at `0x1400035bb`
- `FLTMGR!FltGetStreamContext` at `0x1400035bb`
- `FLTMGR!FltSetCallbackDataDirty` at `0x1400038a9`
- `FLTMGR!FltSetCallbackDataDirty` at `0x1400038a9`
- `FLTMGR!FltReleaseContext` at `0x1400036a5`
- `FLTMGR!FltReleaseContext` at `0x14000377f`
- `FLTMGR!FltReleaseContext` at `0x14000386f`
- `FLTMGR!FltReleaseContext` at `0x1400038d2`
- `FLTMGR!FltReleaseContext` at `0x1400038e6`
- `FLTMGR!FltReleaseContext` at `0x1400036a5`
- `FLTMGR!FltReleaseContext` at `0x14000377f`
- `FLTMGR!FltReleaseContext` at `0x14000386f`
- `FLTMGR!FltReleaseContext` at `0x1400038d2`
- `FLTMGR!FltReleaseContext` at `0x1400038e6`

## string_xrefs

- `0x140003522`: `onecore\base\fs\wci\wcifs\readwrite.c`
- `0x14000365d`: `onecore\base\fs\wci\wcifs\readwrite.c`

## pseudocode

```c
__int64 __fastcall WcPreRead(PFLT_CALLBACK_DATA Data, __int64 a2, __int64 a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  ULONG IrpFlags; // r13d
  int v7; // edx
  __int64 result; // rax
  struct _FILE_OBJECT *v9; // rsi
  unsigned int v10; // ebx
  struct _FLT_INSTANCE *v11; // r15
  _DWORD *v12; // r15
  char *v13; // rsi
  struct _FAST_MUTEX *v14; // rcx
  __int64 Silo; // rax
  int v16; // r13d
  __int64 v17; // r12
  int v18; // eax
  PFLT_IO_PARAMETER_BLOCK v19; // rax
  struct _MDL *MdlAddress; // rcx
  PVOID MappedSystemVa; // rcx
  NTSTATUS v22; // r14d
  PFLT_IO_PARAMETER_BLOCK v23; // rax
  LARGE_INTEGER v24; // r9
  LARGE_INTEGER ByteOffset; // r8
  size_t Length; // rbx
  void *v27; // rcx
  char v28; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v29; // [rsp+64h] [rbp-55h]
  int v30; // [rsp+68h] [rbp-51h] BYREF
  PFLT_CONTEXT v31; // [rsp+70h] [rbp-49h] BYREF
  PFLT_CONTEXT Context; // [rsp+78h] [rbp-41h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+80h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-29h] BYREF
  char *v35; // [rsp+A0h] [rbp-19h]
  int v36; // [rsp+A8h] [rbp-11h]
  int v37; // [rsp+ACh] [rbp-Dh]
  char *v38; // [rsp+B0h] [rbp-9h]
  __int64 v39; // [rsp+B8h] [rbp-1h]
  PFLT_CONTEXT *v40; // [rsp+C0h] [rbp+7h]
  __int64 v41; // [rsp+C8h] [rbp+Fh]

  Iopb = Data->Iopb;
  v30 = 0;
  *(_QWORD *)&EventDescriptor.Id = a3;
  IrpFlags = Iopb->IrpFlags;
  v29 = Iopb->IrpFlags;
  if ( BYTE2(qword_14000E6A2)
    || (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x400000) == 0
    || Data->RequestorMode != 1
    || !(unsigned __int8)WcIsSiloFileObject(*(_QWORD *)(a2 + 24)) )
  {
    v9 = *(struct _FILE_OBJECT **)(a2 + 32);
    v10 = 1;
    v11 = *(struct _FLT_INSTANCE **)(a2 + 24);
    Context = 0;
    v31 = 0;
    if ( FltGetFileContext(v11, v9, &Context) < 0 )
      return v10;
    FltGetStreamContext(v11, v9, &v31);
    v12 = Context;
    v13 = (char *)v31;
    ExAcquireFastMutex((PFAST_MUTEX)((char *)Context + 8));
    v14 = (struct _FAST_MUTEX *)(v12 + 2);
    if ( (v12[22] & 2) == 0 )
    {
      ExReleaseFastMutex(v14);
      goto LABEL_49;
    }
    ExReleaseFastMutex(v14);
    if ( !v13 || (*((_DWORD *)v13 + 6) & 0x10) != 0 )
    {
LABEL_49:
      FltReleaseContext(v12);
      if ( v13 )
        goto LABEL_50;
      return v10;
    }
    Silo = IoGetSilo(*(_QWORD *)(a2 + 32));
    v16 = IrpFlags & 2;
    if ( !v16 && (unsigned __int8)PsIsHostSilo(Silo) && *(_DWORD *)(*((_QWORD *)v13 + 5) + 28LL) == 3 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sD(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          2,
          11,
          (__int64)WPP_74e98403bd0930425909d23d2522dfc9_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\readwrite.c",
          131);
      Data->IoStatus.Status = -1073741790;
      v10 = 4;
      FltReleaseContext(v12);
      goto LABEL_50;
    }
    v17 = *(_QWORD *)(*((_QWORD *)v13 + 7) + 24LL);
    if ( (v29 & 1) == 0 )
    {
      if ( *(_QWORD *)(*(_QWORD *)(a2 + 32) + 40LL) == *(_QWORD *)(*(_QWORD *)(v17 + 16) + 40LL) )
        goto LABEL_47;
      goto LABEL_49;
    }
    if ( !v16 )
    {
      if ( *(_QWORD *)(*(_QWORD *)(a2 + 32) + 40LL) == *(_QWORD *)(*(_QWORD *)(v17 + 16) + 40LL) )
        goto LABEL_47;
      v18 = FltLockUserBuffer(Data);
      if ( v18 >= 0 )
      {
        v18 = FltReadFileEx(
                *(_QWORD *)(a2 + 24),
                *(_QWORD *)(a2 + 32),
                &Data->Iopb->Parameters.QuerySecurity.SecurityBuffer,
                Data->Iopb->Parameters.Read.Length,
                0,
                5,
                &v30,
                0,
                0,
                &Data->Iopb->Parameters.QueryEa.EaList,
                Data->Iopb->Parameters.Create.EaBuffer);
        if ( v18 >= 0 )
        {
          if ( v30 )
            goto LABEL_47;
        }
      }
      Data->IoStatus.Status = v18;
      v10 = 4;
      FltReleaseContext(v12);
LABEL_50:
      v27 = v13;
      goto LABEL_51;
    }
    if ( *((_QWORD *)v13 + 28) )
    {
      FltAcquireResourceShared((PERESOURCE)(v13 + 120));
      if ( *((_QWORD *)v13 + 28) )
      {
        v19 = Data->Iopb;
        MdlAddress = v19->Parameters.Read.MdlAddress;
        if ( MdlAddress )
        {
          if ( (MdlAddress->MdlFlags & 5) != 0 )
            MappedSystemVa = MdlAddress->MappedSystemVa;
          else
            MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
          if ( !MappedSystemVa )
          {
            v22 = -1073741670;
LABEL_45:
            Data->IoStatus.Status = v22;
            v10 = 4;
            FltReleaseResource((PERESOURCE)(v13 + 120));
            FltReleaseContext(v12);
            goto LABEL_50;
          }
        }
        else
        {
          MappedSystemVa = v19->Parameters.CreatePipe.Parameters;
        }
        v23 = Data->Iopb;
        v24 = *(LARGE_INTEGER *)(v13 + 72);
        ByteOffset = v23->Parameters.Read.ByteOffset;
        if ( ByteOffset.QuadPart <= (unsigned __int64)v24.QuadPart )
        {
          Length = v24.QuadPart - ByteOffset.QuadPart;
          v22 = 0;
          if ( (unsigned __int64)v23->Parameters.Read.Length + ByteOffset.QuadPart <= v24.QuadPart )
            Length = v23->Parameters.Read.Length;
          memmove(MappedSystemVa, (const void *)(ByteOffset.QuadPart + *((_QWORD *)v13 + 28)), Length);
          Data->IoStatus.Information = Length;
        }
        else
        {
          v22 = -1073741807;
        }
        goto LABEL_45;
      }
      FltReleaseResource((PERESOURCE)(v13 + 120));
    }
LABEL_47:
    Data->Iopb->TargetFileObject = *(PFILE_OBJECT *)(v17 + 16);
    Data->Iopb->TargetInstance = *(PFLT_INSTANCE *)v17;
    FltSetCallbackDataDirty(Data);
    v10 = 0;
    v27 = v12;
    **(_QWORD **)&EventDescriptor.Id = v13;
LABEL_51:
    FltReleaseContext(v27);
    return v10;
  }
  if ( (unsigned int)dword_14000E060 > 5 )
  {
    v7 = 0;
    if ( (qword_14000E070 & 0x400000000000LL) != 0 && (qword_14000E078 & 0x400000000000LL) == qword_14000E078 )
    {
      EventDescriptor.Keyword = 0x400000000000LL;
      v38 = &v28;
      v28 = 2;
      v40 = &v31;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_14000E068;
      v39 = 1;
      v31 = (PFLT_CONTEXT)3;
      v41 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      UserData.Size = *(unsigned __int16 *)off_14000E068;
      v35 = byte_14000B863;
      UserData.Reserved = 2;
      v36 = 52;
      v37 = 1;
      v29 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 3;
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      2,
      10,
      (__int64)WPP_74e98403bd0930425909d23d2522dfc9_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\readwrite.c",
      90);
  }
  Data->IoStatus.Status = -1073741637;
  result = 4;
  Data->IoStatus.Information = 0;
  return result;
}

```

## disassembly

```asm
0x1400033a0  push    rbp
0x1400033a2  push    rbx
0x1400033a3  push    rdi
0x1400033a4  push    r12
0x1400033a6  push    r13
0x1400033a8  push    r14
0x1400033aa  lea     rbp, [rsp-2Fh]
0x1400033af  sub     rsp, 0E8h
0x1400033b6  mov     rax, cs:__security_cookie
0x1400033bd  xor     rax, rsp
0x1400033c0  mov     [rbp+57h+var_40], rax
0x1400033c4  mov     rax, [rcx+10h]
0x1400033c8  xor     r12d, r12d
0x1400033cb  cmp     byte ptr cs:qword_14000E6A2+2, r12b
0x1400033d2  mov     r14, rdx
0x1400033d5  mov     [rbp+57h+var_A8], r12d
0x1400033d9  mov     rdi, rcx
0x1400033dc  mov     qword ptr [rbp+57h+EventDescriptor.Id], r8
0x1400033e0  mov     r13d, [rax]
0x1400033e3  mov     [rbp+57h+var_AC], r13d
0x1400033e7  jnz     loc_14000356E
0x1400033ed  mov     rdx, [rdx+20h]
0x1400033f1  test    dword ptr [rdx+50h], 400000h
0x1400033f8  jz      loc_14000356E
0x1400033fe  cmp     byte ptr [rcx+50h], 1
0x140003402  jnz     loc_14000356E
0x140003408  mov     rcx, [r14+18h]
0x14000340c  call    WcIsSiloFileObject
0x140003411  test    al, al
0x140003413  jz      loc_14000356E
0x140003419  mov     eax, cs:dword_14000E060
0x14000341f  cmp     eax, 5
0x140003422  jbe     loc_14000350B
0x140003428  mov     rcx, cs:qword_14000E078
0x14000342f  mov     rdx, 400000000000h
0x140003439  mov     rax, cs:qword_14000E070
0x140003440  test    rdx, rax
0x140003443  jz      loc_14000350B
0x140003449  mov     rax, rcx
0x14000344c  and     rax, rdx
0x14000344f  cmp     rax, rcx
0x140003452  jnz     loc_14000350B
0x140003458  mov     [rbp+57h+EventDescriptor.Keyword], rdx
0x14000345c  lea     rax, [rbp+57h+var_B0]
0x140003460  mov     [rbp+57h+var_60], rax
0x140003464  lea     rcx, _TraceLoggingMetadata
0x14000346b  lea     rax, [rbp+57h+var_A0]
0x14000346f  mov     [rbp+57h+var_B0], 2
0x140003473  mov     [rbp+57h+var_50], rax
0x140003477  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x14000347b  movzx   eax, cs:word_14000B859
0x140003482  mov     ebx, 1
0x140003487  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x14000348a  xor     r9d, r9d; RelatedActivityId
0x14000348d  mov     rax, cs:off_14000E068
0x140003494  xor     r8d, r8d; ActivityId
0x140003497  mov     [rbp+57h+var_80.Ptr], rax
0x14000349b  mov     [rbp+57h+var_58], rbx
0x14000349f  mov     [rbp+57h+var_A0], 3
0x1400034a7  mov     [rbp+57h+var_48], 8
0x1400034af  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1400034b6  movzx   eax, word ptr [rax]
0x1400034b9  mov     [rbp+57h+var_80.Size], eax
0x1400034bc  lea     rax, byte_14000B863
0x1400034c3  mov     [rbp+57h+var_70], rax
0x1400034c7  lea     rax, _TraceLoggingMetadataEnd
0x1400034ce  sub     eax, ecx
0x1400034d0  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x1400034d7  mov     [rbp+57h+var_68], 34h ; '4'
0x1400034de  mov     [rbp+57h+var_64], ebx
0x1400034e1  mov     [rbp+57h+var_AC], eax
0x1400034e4  mov     eax, [rbp+57h+var_AC]
0x1400034e7  mov     rcx, cs:RegHandle; RegHandle
0x1400034ee  lea     rax, [rbp+57h+var_80]
0x1400034f2  mov     [rsp+110h+UserData], rax; UserData
0x1400034f7  mov     [rsp+110h+UserDataCount], 4; UserDataCount
0x1400034ff  call    cs:__imp_EtwWriteTransfer
0x140003506  nop     dword ptr [rax+rax+00h]
0x14000350b  lea     rax, WPP_RECORDER_INITIALIZED
0x140003512  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003519  jz      short loc_140003559
0x14000351b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003522  lea     rax, aOnecoreBaseFsW_7; "onecore\\base\\fs\\wci\\wcifs\\readwrit"...
0x140003529  mov     dword ptr [rsp+110h+var_E0], 5Ah ; 'Z'
0x140003531  mov     r9d, 0Ah
0x140003537  mov     [rsp+110h+UserData], rax
0x14000353c  mov     r8d, 2
0x140003542  lea     rax, WPP_74e98403bd0930425909d23d2522dfc9_Traceguids
0x140003549  mov     dl, 3
0x14000354b  mov     rcx, [rcx+40h]
0x14000354f  mov     qword ptr [rsp+110h+UserDataCount], rax
0x140003554  call    WPP_RECORDER_SF_sD
0x140003559  mov     dword ptr [rdi+18h], 0C00000BBh
0x140003560  mov     eax, 4
0x140003565  mov     [rdi+20h], r12
0x140003569  jmp     loc_140003904
0x14000356e  mov     [rsp+110h+arg_18], rsi
0x140003576  lea     r8, [rbp+57h+Context]; Context
0x14000357a  mov     rsi, [r14+20h]
0x14000357e  mov     ebx, 1
0x140003583  mov     [rsp+110h+var_30], r15
0x14000358b  mov     rdx, rsi; FileObject
0x14000358e  mov     r15, [r14+18h]
0x140003592  mov     rcx, r15; Instance
0x140003595  mov     [rbp+57h+Context], r12
0x140003599  mov     [rbp+57h+var_A0], r12
0x14000359d  call    cs:__imp_FltGetFileContext
0x1400035a4  nop     dword ptr [rax+rax+00h]
0x1400035a9  test    eax, eax
0x1400035ab  js      loc_1400038F2
0x1400035b1  lea     r8, [rbp+57h+var_A0]; Context
0x1400035b5  mov     rdx, rsi; FileObject
0x1400035b8  mov     rcx, r15; Instance
0x1400035bb  call    cs:__imp_FltGetStreamContext
0x1400035c2  nop     dword ptr [rax+rax+00h]
0x1400035c7  mov     r15, [rbp+57h+Context]
0x1400035cb  mov     rsi, [rbp+57h+var_A0]
0x1400035cf  lea     rcx, [r15+8]; FastMutex
0x1400035d3  call    cs:__imp_ExAcquireFastMutex
0x1400035da  nop     dword ptr [rax+rax+00h]
0x1400035df  mov     eax, [r15+58h]
0x1400035e3  lea     rcx, [r15+8]; FastMutex
0x1400035e7  test    al, 2
0x1400035e9  jz      loc_1400038C3
0x1400035ef  call    cs:__imp_ExReleaseFastMutex
0x1400035f6  nop     dword ptr [rax+rax+00h]
0x1400035fb  test    rsi, rsi
0x1400035fe  jz      loc_1400038CF
0x140003604  mov     eax, [rsi+18h]
0x140003607  test    al, 10h
0x140003609  jnz     loc_1400038CF
0x14000360f  mov     rcx, [r14+20h]
0x140003613  call    cs:__imp_IoGetSilo
0x14000361a  nop     dword ptr [rax+rax+00h]
0x14000361f  and     r13d, 2
0x140003623  jnz     loc_1400036B6
0x140003629  mov     rcx, rax
0x14000362c  call    cs:__imp_PsIsHostSilo
0x140003633  nop     dword ptr [rax+rax+00h]
0x140003638  test    al, al
0x14000363a  jz      short loc_1400036B6
0x14000363c  mov     rax, [rsi+28h]
0x140003640  cmp     dword ptr [rax+1Ch], 3
0x140003644  jnz     short loc_1400036B6
0x140003646  lea     rax, WPP_RECORDER_INITIALIZED
0x14000364d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003654  jz      short loc_140003696
0x140003656  mov     rcx, cs:WPP_GLOBAL_Control
0x14000365d  lea     rax, aOnecoreBaseFsW_7; "onecore\\base\\fs\\wci\\wcifs\\readwrit"...
0x140003664  mov     dword ptr [rsp+110h+var_E0], 83h
0x14000366c  mov     r8d, 2
0x140003672  mov     [rsp+110h+UserData], rax
0x140003677  mov     r9d, 0Bh
0x14000367d  lea     rax, WPP_74e98403bd0930425909d23d2522dfc9_Traceguids
0x140003684  movzx   edx, r8b
0x140003688  mov     rcx, [rcx+40h]
0x14000368c  mov     qword ptr [rsp+110h+UserDataCount], rax
0x140003691  call    WPP_RECORDER_SF_sD
0x140003696  mov     rcx, r15; Context
0x140003699  mov     dword ptr [rdi+18h], 0C0000022h
0x1400036a0  mov     ebx, 4
0x1400036a5  call    cs:__imp_FltReleaseContext
0x1400036ac  nop     dword ptr [rax+rax+00h]
0x1400036b1  jmp     loc_1400038E3
0x1400036b6  mov     rax, [rsi+38h]
0x1400036ba  mov     r12, [rax+18h]
0x1400036be  test    byte ptr [rbp+57h+var_AC], bl
0x1400036c1  jnz     short loc_1400036DF
0x1400036c3  mov     rax, [r12+10h]
0x1400036c8  mov     rcx, [r14+20h]
0x1400036cc  mov     rax, [rax+28h]
0x1400036d0  cmp     [rcx+28h], rax
0x1400036d4  jnz     loc_1400038CF
0x1400036da  jmp     loc_14000388D
0x1400036df  test    r13d, r13d
0x1400036e2  jnz     loc_140003790
0x1400036e8  mov     rax, [r12+10h]
0x1400036ed  mov     rcx, [r14+20h]
0x1400036f1  mov     rax, [rax+28h]
0x1400036f5  cmp     [rcx+28h], rax
0x1400036f9  jz      loc_14000388D
0x1400036ff  mov     rcx, rdi; CallbackData
0x140003702  call    cs:__imp_FltLockUserBuffer
0x140003709  nop     dword ptr [rax+rax+00h]
0x14000370e  test    eax, eax
0x140003710  js      short loc_140003774
0x140003712  mov     r9, [rdi+10h]
0x140003716  mov     rdx, [r14+20h]
0x14000371a  mov     rax, [r9+38h]
0x14000371e  lea     rcx, [r9+20h]
0x140003722  mov     [rsp+110h+var_C0], rax
0x140003727  lea     r8, [r9+28h]
0x14000372b  mov     r9d, [r9+18h]
0x14000372f  lea     rax, [rbp+57h+var_A8]
0x140003733  mov     [rsp+110h+var_C8], rcx
0x140003738  xor     ecx, ecx
0x14000373a  mov     [rsp+110h+var_D0], rcx
0x14000373f  mov     [rsp+110h+var_D8], rcx
0x140003744  mov     [rsp+110h+var_E0], rax
0x140003749  mov     dword ptr [rsp+110h+UserData], 5
0x140003751  mov     qword ptr [rsp+110h+UserDataCount], rcx
0x140003756  mov     rcx, [r14+18h]
0x14000375a  call    cs:__imp_FltReadFileEx
0x140003761  nop     dword ptr [rax+rax+00h]
0x140003766  test    eax, eax
0x140003768  js      short loc_140003774
0x14000376a  cmp     [rbp+57h+var_A8], r13d
0x14000376e  jnz     loc_14000388D
0x140003774  mov     rcx, r15; Context
0x140003777  mov     [rdi+18h], eax
0x14000377a  mov     ebx, 4
0x14000377f  call    cs:__imp_FltReleaseContext
0x140003786  nop     dword ptr [rax+rax+00h]
0x14000378b  jmp     loc_1400038E3
0x140003790  cmp     qword ptr [rsi+0E0h], 0
0x140003798  jz      loc_14000388D
0x14000379e  lea     rcx, [rsi+78h]; Resource
0x1400037a2  call    cs:__imp_FltAcquireResourceShared
0x1400037a9  nop     dword ptr [rax+rax+00h]
0x1400037ae  cmp     qword ptr [rsi+0E0h], 0
0x1400037b6  jz      loc_14000387D
0x1400037bc  mov     rax, [rdi+10h]
0x1400037c0  mov     rcx, [rax+38h]; MemoryDescriptorList
0x1400037c4  test    rcx, rcx
0x1400037c7  jz      short loc_140003809
0x1400037c9  test    byte ptr [rcx+0Ah], 5
0x1400037cd  jz      short loc_1400037D5
0x1400037cf  mov     rcx, [rcx+18h]
0x1400037d3  jmp     short loc_1400037FC
0x1400037d5  mov     dword ptr [rsp+110h+UserData], 40000010h; Priority
0x1400037dd  xor     r9d, r9d; RequestedAddress
0x1400037e0  mov     r8d, ebx; CacheType
0x1400037e3  mov     [rsp+110h+UserDataCount], 0; BugCheckOnFailure
0x1400037eb  xor     edx, edx; AccessMode
0x1400037ed  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400037f4  nop     dword ptr [rax+rax+00h]
0x1400037f9  mov     rcx, rax
0x1400037fc  test    rcx, rcx
0x1400037ff  jnz     short loc_14000380D
0x140003801  mov     r14d, 0C000009Ah
0x140003807  jmp     short loc_140003853
0x140003809  mov     rcx, [rax+30h]; void *
0x14000380d  mov     rax, [rdi+10h]
0x140003811  mov     r9, [rsi+48h]
0x140003815  mov     r8, [rax+28h]
0x140003819  cmp     r8, r9
0x14000381c  jbe     short loc_140003826
0x14000381e  mov     r14d, 0C0000011h
0x140003824  jmp     short loc_140003853
0x140003826  mov     edx, [rax+18h]
0x140003829  mov     rbx, r9
0x14000382c  sub     rbx, r8
0x14000382f  xor     r14d, r14d
0x140003832  lea     rax, [rdx+r8]
0x140003836  cmp     rax, r9
0x140003839  cmovbe  rbx, rdx
0x14000383d  mov     rdx, [rsi+0E0h]
0x140003844  add     rdx, r8; Src
0x140003847  mov     r8, rbx; Size
0x14000384a  call    memmove
0x14000384f  mov     [rdi+20h], rbx
0x140003853  lea     rcx, [rsi+78h]; Resource
0x140003857  mov     [rdi+18h], r14d
0x14000385b  mov     ebx, 4
0x140003860  call    cs:__imp_FltReleaseResource
0x140003867  nop     dword ptr [rax+rax+00h]
0x14000386c  mov     rcx, r15; Context
0x14000386f  call    cs:__imp_FltReleaseContext
0x140003876  nop     dword ptr [rax+rax+00h]
0x14000387b  jmp     short loc_1400038E3
0x14000387d  lea     rcx, [rsi+78h]; Resource
0x140003881  call    cs:__imp_FltReleaseResource
0x140003888  nop     dword ptr [rax+rax+00h]
0x14000388d  mov     rdx, [rdi+10h]
0x140003891  mov     rcx, rdi; Data
0x140003894  mov     rax, [r12+10h]
0x140003899  mov     [rdx+8], rax
0x14000389d  mov     rdx, [rdi+10h]
0x1400038a1  mov     rax, [r12]
0x1400038a5  mov     [rdx+10h], rax
0x1400038a9  call    cs:__imp_FltSetCallbackDataDirty
0x1400038b0  nop     dword ptr [rax+rax+00h]
0x1400038b5  mov     rax, qword ptr [rbp+57h+EventDescriptor.Id]
0x1400038b9  xor     ebx, ebx
0x1400038bb  mov     rcx, r15
0x1400038be  mov     [rax], rsi
0x1400038c1  jmp     short loc_1400038E6
0x1400038c3  call    cs:__imp_ExReleaseFastMutex
0x1400038ca  nop     dword ptr [rax+rax+00h]
0x1400038cf  mov     rcx, r15; Context
0x1400038d2  call    cs:__imp_FltReleaseContext
0x1400038d9  nop     dword ptr [rax+rax+00h]
0x1400038de  test    rsi, rsi
0x1400038e1  jz      short loc_1400038F2
0x1400038e3  mov     rcx, rsi; Context
0x1400038e6  call    cs:__imp_FltReleaseContext
0x1400038ed  nop     dword ptr [rax+rax+00h]
0x1400038f2  mov     rsi, [rsp+110h+arg_18]
0x1400038fa  mov     eax, ebx
0x1400038fc  mov     r15, [rsp+110h+var_30]
  ... truncated ...
```
