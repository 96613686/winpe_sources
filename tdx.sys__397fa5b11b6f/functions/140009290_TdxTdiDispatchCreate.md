# TdxTdiDispatchCreate

- ea: `0x140009290`
- end: `0x140009ac4`
- name: `TdxTdiDispatchCreate`
- size: `2100`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400047d0`
- `0x1400054ec`
- `0x140008c50`
- `0x140009290`
- `0x14000a8d0`
- `0x14000a908`
- `0x14000a950`
- `0x14000b330`
- `0x14001303c`
- `0x140013af4`
- `0x140013c84`
- `0x140018e20`

## import_xrefs

- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1400097bb`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1400097bb`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000979a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400099af`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000979a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400099af`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400093c5`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400093e6`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400093c5`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400093e6`
- `ntoskrnl!ExAllocatePool2` at `0x14000939e`
- `ntoskrnl!ExAllocatePool2` at `0x14000974f`
- `ntoskrnl!ExAllocatePool2` at `0x14000939e`
- `ntoskrnl!ExAllocatePool2` at `0x14000974f`
- `ntoskrnl!IofCompleteRequest` at `0x140009714`
- `ntoskrnl!IofCompleteRequest` at `0x140009714`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009433`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009466`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000955a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009643`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009433`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009466`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000955a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009643`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400094b9`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400095b4`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400096a1`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400094b9`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400095b4`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400096a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400094f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009547`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400095dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400096cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009a13`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400094f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009547`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400095dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400096cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009a13`

## string_xrefs

- `0x140009656`: `TdxTdiDispatchCreate`
- `0x14000956c`: `TdxCreateConnection`
- `0x14000991c`: `TdxCreateConnection`
- `0x140009a1f`: `TdxCreateConnection`

## pseudocode

```c
__int64 __fastcall TdxTdiDispatchCreate(__int64 a1, IRP *a2)
{
  KSPIN_LOCK v4; // r14
  struct _IRP *MasterIrp; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  KPROCESSOR_MODE RequestorMode; // bp
  unsigned int EaLength; // edx
  NTSTATUS TransportAddress; // ebp
  unsigned int i; // ecx
  char *v11; // r13
  __int64 v12; // r12
  KSPIN_LOCK v13; // rdi
  PFILE_OBJECT v14; // r13
  KSPIN_LOCK *v15; // rax
  KSPIN_LOCK *v16; // rbp
  KSPIN_LOCK *v17; // r15
  KSPIN_LOCK *v18; // rdi
  KIRQL v19; // cl
  KIRQL v20; // di
  int v21; // eax
  KSPIN_LOCK v22; // rdx
  bool v23; // zf
  KSPIN_LOCK v24; // r14
  KSPIN_LOCK **v25; // rax
  KIRQL v26; // dl
  KSPIN_LOCK *v27; // rcx
  KIRQL v28; // di
  int v29; // eax
  KSPIN_LOCK *v30; // rsi
  int v31; // edx
  int v32; // r8d
  KSPIN_LOCK *v33; // r14
  KIRQL v34; // di
  int v35; // eax
  KSPIN_LOCK *v36; // r15
  int v37; // edx
  int v38; // r8d
  PFILE_OBJECT FileObject; // rsi
  __int64 Pool2; // rax
  volatile signed __int32 *v42; // rdi
  PFILE_OBJECT v43; // rdx
  char *v44; // r8
  int v45; // ecx
  PVOID v46; // [rsp+80h] [rbp+8h] BYREF
  PVOID CallersAddress; // [rsp+88h] [rbp+10h] BYREF
  PKSPIN_LOCK SpinLock; // [rsp+90h] [rbp+18h]

  a2->IoStatus.Information = 0;
  if ( (PDEVICE_OBJECT)a1 == TdxDeviceObject )
    goto LABEL_42;
  v4 = **(_QWORD **)(a1 + 64);
  if ( !v4 )
  {
    TransportAddress = -1073741661;
    goto LABEL_28;
  }
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  RequestorMode = a2->RequestorMode;
  if ( !MasterIrp )
  {
    FileObject = CurrentStackLocation->FileObject;
    Pool2 = ExAllocatePool2(64, 56, 1668834388);
    v42 = (volatile signed __int32 *)Pool2;
    if ( !Pool2 )
    {
      TransportAddress = -1073741801;
      goto LABEL_28;
    }
    TdxInitializeObjectHeader(Pool2);
    v45 = 0;
    *((_DWORD *)v42 + 1) = 3;
    if ( !RequestorMode )
      v45 = 2;
    *v42 = *v42 & 0xFFFFFFFD | v45;
    if ( !(unsigned __int8)TdxAttachObjectToTransport(v4, v42) )
    {
      TdxDereferenceControlChannel((PVOID)v42);
      goto LABEL_51;
    }
    _InterlockedIncrement(v42 + 4);
    FileObject->FsContext = (PVOID)v42;
    FileObject->FsContext2 = (PVOID)3;
    TdxDereferenceControlChannel((PVOID)v42);
    _InterlockedIncrement((_DWORD *)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine + 1);
LABEL_42:
    TransportAddress = 0;
    goto LABEL_28;
  }
  if ( RequestorMode )
  {
    TransportAddress = -1073741790;
    goto LABEL_28;
  }
  EaLength = CurrentStackLocation->Parameters.Create.EaLength;
  TransportAddress = -1073741811;
  LODWORD(CallersAddress) = EaLength;
  for ( i = 0; ; i += *(_DWORD *)v11 )
  {
    LODWORD(v46) = i;
    if ( EaLength < i + 8 )
      goto LABEL_28;
    v11 = (char *)MasterIrp + i;
    v12 = (unsigned __int8)v11[5];
    LODWORD(SpinLock) = *((unsigned __int16 *)v11 + 3);
    if ( EaLength < i + (_DWORD)v12 + (_DWORD)SpinLock + 9 )
      goto LABEL_28;
    if ( (_BYTE)v12 == 17 )
    {
      if ( !memcmp(v11 + 8, "ConnectionContext", (unsigned int)v12) )
      {
        if ( (_WORD)SpinLock != 8
          || a1 != *(_QWORD *)(v4 + 88) && a1 != *(_QWORD *)(v4 + 96)
          || *(_WORD *)(v4 + 36) != 1 )
        {
          goto LABEL_28;
        }
        v13 = *(_QWORD *)&v11[v12 + 9];
        v14 = CurrentStackLocation->FileObject;
        v15 = (KSPIN_LOCK *)ExAllocatePool2(64, 640, 1131963476);
        v16 = v15;
        if ( !v15 )
        {
          TransportAddress = -1073741801;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            WPP_SF_sd(
              WPP_GLOBAL_Control->AttachedDevice,
              12,
              (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
              (unsigned int)"TdxCreateConnection",
              23);
          }
          goto LABEL_28;
        }
        v17 = v15 + 3;
        v15[4] = (KSPIN_LOCK)(v15 + 3);
        v15[3] = (KSPIN_LOCK)(v15 + 3);
        KeInitializeSpinLock(v15 + 1);
        *((_DWORD *)v16 + 4) = 1;
        *((_DWORD *)v16 + 1) = 2;
        KeInitializeSpinLock(v16 + 46);
        v16[10] = v13;
        *((_DWORD *)v16 + 19) = 0;
        v18 = (KSPIN_LOCK *)(v4 + 16);
        v16[13] = (KSPIN_LOCK)(v16 + 12);
        v16[12] = (KSPIN_LOCK)(v16 + 12);
        v16[39] = (KSPIN_LOCK)(v16 + 38);
        v16[38] = (KSPIN_LOCK)(v16 + 38);
        v16[41] = (KSPIN_LOCK)(v16 + 40);
        v16[40] = (KSPIN_LOCK)(v16 + 40);
        SpinLock = (PKSPIN_LOCK)(v4 + 16);
        v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 16));
        LOBYTE(v46) = v19;
        if ( (*(_DWORD *)(v4 + 168) & 1) != 0 )
        {
          v33 = 0;
          KeReleaseSpinLock(v18, v19);
          DbgTdxDereferenceConnection(v16, "TdxCreateConnection", 219);
          TransportAddress = -1073741811;
LABEL_21:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            WPP_SF_sd(
              WPP_GLOBAL_Control->AttachedDevice,
              14,
              (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
              (unsigned int)"TdxCreateConnection",
              TransportAddress);
          }
          if ( TransportAddress >= 0 )
          {
            v34 = KeAcquireSpinLockRaiseToDpc(v33 + 46);
            v35 = *((_DWORD *)v33 + 4);
            v36 = &v33[4 * *((unsigned int *)v33 + 158)];
            v46 = 0;
            *((_DWORD *)v36 + 100) = v35 - 1;
            v36[47] = (KSPIN_LOCK)"TdxTdiDispatchCreate";
            *((_DWORD *)v36 + 96) = 233;
            RtlGetCallersAddress(&v46, (PVOID *)v36 + 49);
            *((_DWORD *)v33 + 158) = ((unsigned __int8)*((_DWORD *)v33 + 158) + 1) & 7;
            KeReleaseSpinLock(v33 + 46, v34);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
            {
              WPP_SF_qdssD(
                WPP_GLOBAL_Control->AttachedDevice,
                v37,
                v38,
                (_DWORD)v33,
                *((_DWORD *)v36 + 100),
                (__int64)"--",
                (__int64)"TdxTdiDispatchCreate",
                233);
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v33 + 4, 0xFFFFFFFF) == 1 )
              TdxCleanupObjectHeader(v33);
            _InterlockedIncrement((_DWORD *)&WPP_MAIN_CB.Queue.Wcb.1 + 5);
          }
          goto LABEL_28;
        }
        v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 216));
        v21 = *(_DWORD *)(v4 + 24);
        v22 = v4 + 32 * (*(unsigned int *)(v4 + 1184) + 7LL);
        CallersAddress = 0;
        *(_DWORD *)(v22 + 24) = v21 + 1;
        *(_QWORD *)v22 = "minio\\netio\\session\\tdi\\transport.c";
        *(_DWORD *)(v22 + 8) = 228;
        RtlGetCallersAddress(&CallersAddress, (PVOID *)(v22 + 16));
        *(_DWORD *)(v4 + 1184) = (*(_DWORD *)(v4 + 1184) + 1) % 0x1Eu;
        KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 216), v20);
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 24));
        _InterlockedIncrement((volatile signed __int32 *)v16 + 4);
        v23 = *((_DWORD *)v16 + 1) == 1;
        v16[5] = v4;
        if ( v23 )
        {
          v24 = v4 + 176;
          v25 = *(KSPIN_LOCK ***)(v24 + 8);
          if ( *v25 == (KSPIN_LOCK *)v24 )
            goto LABEL_17;
        }
        else
        {
          v24 = v4 + 192;
          v25 = *(KSPIN_LOCK ***)(v24 + 8);
          if ( *v25 == (KSPIN_LOCK *)v24 )
          {
LABEL_17:
            v26 = (unsigned __int8)v46;
            v27 = SpinLock;
            *v17 = v24;
            v17[1] = (KSPIN_LOCK)v25;
            *v25 = v17;
            *(_QWORD *)(v24 + 8) = v17;
            KeReleaseSpinLock(v27, v26);
            v28 = KeAcquireSpinLockRaiseToDpc(v16 + 46);
            v29 = *((_DWORD *)v16 + 4);
            v30 = &v16[4 * *((unsigned int *)v16 + 158)];
            v46 = 0;
            *((_DWORD *)v30 + 100) = v29 + 1;
            v30[47] = (KSPIN_LOCK)"TdxCreateConnection";
            *((_DWORD *)v30 + 96) = 222;
            RtlGetCallersAddress(&v46, (PVOID *)v30 + 49);
            *((_DWORD *)v16 + 158) = ((unsigned __int8)*((_DWORD *)v16 + 158) + 1) & 7;
            KeReleaseSpinLock(v16 + 46, v28);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
            {
              WPP_SF_qdssD(
                WPP_GLOBAL_Control->AttachedDevice,
                v31,
                v32,
                (_DWORD)v16,
                *((_DWORD *)v30 + 100),
                (__int64)"++",
                (__int64)"TdxCreateConnection",
                222);
            }
            _InterlockedIncrement((volatile signed __int32 *)v16 + 4);
            v14->FsContext = v16;
            v14->FsContext2 = (PVOID)2;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
            {
              WPP_SF_sq(
                WPP_GLOBAL_Control->AttachedDevice,
                13,
                (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
                (unsigned int)"TdxCreateConnection",
                (char)v16);
            }
            v33 = v16;
            TransportAddress = 0;
            goto LABEL_21;
          }
        }
        __fastfail(3u);
      }
      goto LABEL_63;
    }
    if ( (_BYTE)v12 != 16 )
      goto LABEL_64;
    if ( !memcmp(v11 + 8, "TransportAddress", (unsigned int)v12) )
      break;
LABEL_63:
    EaLength = (unsigned int)CallersAddress;
    i = (unsigned int)v46;
LABEL_64:
    if ( !*(_DWORD *)v11 )
      goto LABEL_28;
  }
  v46 = 0;
  if ( IoGetTopLevelIrp() != (PIRP)5 && IoGetTopLevelIrp() != (PIRP)6 )
  {
    v46 = 0;
LABEL_35:
    if ( *((unsigned __int16 *)v11 + 3) >= 8u )
    {
      v43 = CurrentStackLocation->FileObject;
      v44 = &v11[(unsigned __int8)v11[5] + 9];
      CallersAddress = 0;
      TransportAddress = TdxCreateTransportAddress(v4, v43, v44);
      if ( TransportAddress >= 0 )
      {
        DbgTdxDereferenceTransportAddress(CallersAddress, "minio\\netio\\session\\tdi\\tdiprovider.c", 283);
        _InterlockedIncrement((volatile signed __int32 *)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
      }
      goto LABEL_28;
    }
LABEL_51:
    TransportAddress = -1073741811;
    goto LABEL_28;
  }
  TransportAddress = IoGetIrpExtraCreateParameter(a2, (struct _ECP_LIST **)&v46);
  if ( TransportAddress >= 0 )
    goto LABEL_35;
LABEL_28:
  a2->IoStatus.Status = TransportAddress;
  IofCompleteRequest(a2, 2);
  return (unsigned int)TransportAddress;
}

```

## disassembly

```asm
0x140009290  mov     [rsp+arg_18], rbx
0x140009295  push    rbp
0x140009296  push    rsi
0x140009297  push    rdi
0x140009298  push    r12
0x14000929a  push    r13
0x14000929c  push    r14
0x14000929e  push    r15
0x1400092a0  sub     rsp, 40h
0x1400092a4  mov     qword ptr [rdx+38h], 0
0x1400092ac  mov     rbx, rdx
0x1400092af  cmp     rcx, cs:TdxDeviceObject
0x1400092b6  mov     rdi, rcx
0x1400092b9  jz      loc_1400098A6
0x1400092bf  mov     rax, [rcx+40h]
0x1400092c3  mov     r14, [rax]
0x1400092c6  test    r14, r14
0x1400092c9  jz      loc_1400099D5
0x1400092cf  mov     rsi, [rdx+18h]
0x1400092d3  mov     r15, [rdx+0B8h]
0x1400092da  movzx   ebp, byte ptr [rdx+40h]
0x1400092de  test    rsi, rsi
0x1400092e1  jz      loc_14000973B
0x1400092e7  test    bpl, bpl
0x1400092ea  jnz     loc_1400099DF
0x1400092f0  mov     edx, [r15+20h]
0x1400092f4  mov     ebp, 0C000000Dh
0x1400092f9  mov     dword ptr [rsp+78h+CallersAddress], edx
0x140009300  xor     ecx, ecx
0x140009302  lea     eax, [rcx+8]
0x140009305  mov     dword ptr [rsp+78h+arg_0], ecx
0x14000930c  cmp     edx, eax
0x14000930e  jb      loc_14000970C
0x140009314  mov     r13d, ecx
0x140009317  add     r13, rsi
0x14000931a  movzx   eax, word ptr [r13+6]
0x14000931f  movzx   r12d, byte ptr [r13+5]
0x140009324  mov     dword ptr [rsp+78h+SpinLock], eax
0x14000932b  add     eax, 9
0x14000932e  add     eax, r12d
0x140009331  add     eax, ecx
0x140009333  cmp     edx, eax
0x140009335  jb      loc_14000970C
0x14000933b  mov     r8d, r12d; Size
0x14000933e  cmp     r12b, 11h
0x140009342  jnz     loc_14000976E
0x140009348  lea     rdx, aConnectioncont; "ConnectionContext"
0x14000934f  lea     rcx, [r13+8]; Buf1
0x140009353  call    memcmp
0x140009358  test    eax, eax
0x14000935a  jnz     loc_1400099E9
0x140009360  cmp     word ptr [rsp+78h+SpinLock], 8
0x140009369  jnz     loc_14000970C
0x14000936f  cmp     rdi, [r14+58h]
0x140009373  jnz     loc_1400099A0
0x140009379  cmp     word ptr [r14+24h], 1
0x14000937f  jnz     loc_14000970C
0x140009385  mov     rdi, [r12+r13+9]
0x14000938a  mov     edx, 280h
0x14000938f  mov     r13, [r15+30h]
0x140009393  mov     ecx, 40h ; '@'
0x140009398  mov     r8d, 43786454h
0x14000939e  call    cs:__imp_ExAllocatePool2
0x1400093a5  nop     dword ptr [rax+rax+00h]
0x1400093aa  mov     rbp, rax
0x1400093ad  test    rax, rax
0x1400093b0  jz      loc_1400098E5
0x1400093b6  lea     r15, [rax+18h]
0x1400093ba  lea     rcx, [rax+8]; SpinLock
0x1400093be  mov     [r15+8], r15
0x1400093c2  mov     [r15], r15
0x1400093c5  call    cs:__imp_KeInitializeSpinLock
0x1400093cc  nop     dword ptr [rax+rax+00h]
0x1400093d1  mov     dword ptr [rbp+10h], 1
0x1400093d8  lea     rcx, [rbp+170h]; SpinLock
0x1400093df  mov     dword ptr [rbp+4], 2
0x1400093e6  call    cs:__imp_KeInitializeSpinLock
0x1400093ed  nop     dword ptr [rax+rax+00h]
0x1400093f2  mov     [rbp+50h], rdi
0x1400093f6  lea     rax, [rbp+60h]
0x1400093fa  mov     dword ptr [rbp+4Ch], 0
0x140009401  lea     rdi, [r14+10h]
0x140009405  mov     [rax+8], rax
0x140009409  mov     rcx, rdi; SpinLock
0x14000940c  mov     [rax], rax
0x14000940f  lea     rax, [rbp+130h]
0x140009416  mov     [rax+8], rax
0x14000941a  mov     [rax], rax
0x14000941d  lea     rax, [rbp+140h]
0x140009424  mov     [rax+8], rax
0x140009428  mov     [rax], rax
0x14000942b  mov     [rsp+78h+SpinLock], rdi
0x140009433  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000943a  nop     dword ptr [rax+rax+00h]
0x14000943f  movzx   ecx, al
0x140009442  mov     byte ptr [rsp+78h+arg_0], al
0x140009449  mov     eax, [r14+0A8h]
0x140009450  lea     r12, WPP_GLOBAL_Control
0x140009457  test    al, 1
0x140009459  jnz     loc_140009A0A
0x14000945f  lea     rcx, [r14+0D8h]; SpinLock
0x140009466  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000946d  nop     dword ptr [rax+rax+00h]
0x140009472  mov     edx, [r14+4A0h]
0x140009479  lea     rcx, [rsp+78h+CallersAddress]; CallersAddress
0x140009481  add     rdx, 7
0x140009485  movzx   edi, al
0x140009488  mov     eax, [r14+18h]
0x14000948c  shl     rdx, 5
0x140009490  add     rdx, r14
0x140009493  mov     [rsp+78h+CallersAddress], 0
0x14000949f  inc     eax
0x1400094a1  mov     [rdx+18h], eax
0x1400094a4  lea     rax, aMinioNetioSess_4; "minio\\netio\\session\\tdi\\transport.c"
0x1400094ab  mov     [rdx], rax
0x1400094ae  mov     dword ptr [rdx+8], 0E4h
0x1400094b5  add     rdx, 10h; CallersCaller
0x1400094b9  call    cs:__imp_RtlGetCallersAddress
0x1400094c0  nop     dword ptr [rax+rax+00h]
0x1400094c5  mov     r8d, [r14+4A0h]
0x1400094cc  lea     rcx, [r14+0D8h]; SpinLock
0x1400094d3  inc     r8d
0x1400094d6  mov     eax, 88888889h
0x1400094db  mul     r8d
0x1400094de  shr     edx, 4
0x1400094e1  imul    eax, edx, 1Eh
0x1400094e4  movzx   edx, dil; NewIrql
0x1400094e8  sub     r8d, eax
0x1400094eb  mov     [r14+4A0h], r8d
0x1400094f2  call    cs:__imp_KeReleaseSpinLock
0x1400094f9  nop     dword ptr [rax+rax+00h]
0x1400094fe  lock inc dword ptr [r14+18h]
0x140009503  lock inc dword ptr [rbp+10h]
0x140009507  cmp     dword ptr [rbp+4], 1
0x14000950b  mov     [rbp+28h], r14
0x14000950f  jnz     loc_140009985
0x140009515  add     r14, 0B0h
0x14000951c  mov     rax, [r14+8]
0x140009520  cmp     [rax], r14
0x140009523  jnz     loc_140009999
0x140009529  movzx   edx, byte ptr [rsp+78h+arg_0]; NewIrql
0x140009531  mov     rcx, [rsp+78h+SpinLock]; SpinLock
0x140009539  mov     [r15], r14
0x14000953c  mov     [r15+8], rax
0x140009540  mov     [rax], r15
0x140009543  mov     [r14+8], r15
0x140009547  call    cs:__imp_KeReleaseSpinLock
0x14000954e  nop     dword ptr [rax+rax+00h]
0x140009553  lea     rcx, [rbp+170h]; SpinLock
0x14000955a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009561  nop     dword ptr [rax+rax+00h]
0x140009566  mov     esi, [rbp+278h]
0x14000956c  lea     r15, aTdxcreateconne; "TdxCreateConnection"
0x140009573  movzx   edi, al
0x140009576  shl     rsi, 5
0x14000957a  mov     eax, [rbp+10h]
0x14000957d  lea     rcx, [rsp+78h+arg_0]; CallersAddress
0x140009585  add     rsi, rbp
0x140009588  mov     [rsp+78h+arg_0], 0
0x140009594  inc     eax
0x140009596  lea     rdx, [rsi+188h]; CallersCaller
0x14000959d  mov     [rsi+190h], eax
0x1400095a3  mov     [rsi+178h], r15
0x1400095aa  mov     dword ptr [rsi+180h], 0DEh
0x1400095b4  call    cs:__imp_RtlGetCallersAddress
0x1400095bb  nop     dword ptr [rax+rax+00h]
0x1400095c0  mov     eax, [rbp+278h]
0x1400095c6  lea     rcx, [rbp+170h]; SpinLock
0x1400095cd  inc     eax
0x1400095cf  movzx   edx, dil; NewIrql
0x1400095d3  and     eax, 7
0x1400095d6  mov     [rbp+278h], eax
0x1400095dc  call    cs:__imp_KeReleaseSpinLock
0x1400095e3  nop     dword ptr [rax+rax+00h]
0x1400095e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400095ef  cmp     rcx, r12
0x1400095f2  jz      short loc_1400095FE
0x1400095f4  cmp     byte ptr [rcx+29h], 5
0x1400095f8  jnb     loc_140009A41
0x1400095fe  lock inc dword ptr [rbp+10h]
0x140009602  mov     eax, 2
0x140009607  mov     [r13+18h], rbp
0x14000960b  mov     [r13+20h], rax
0x14000960f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009616  cmp     rcx, r12
0x140009619  jnz     loc_14000994C
0x14000961f  mov     r14, rbp
0x140009622  xor     ebp, ebp
0x140009624  mov     rcx, cs:WPP_GLOBAL_Control
0x14000962b  cmp     rcx, r12
0x14000962e  jnz     loc_1400098AD
0x140009634  test    ebp, ebp
0x140009636  js      loc_14000970C
0x14000963c  lea     rcx, [r14+170h]; SpinLock
0x140009643  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000964a  nop     dword ptr [rax+rax+00h]
0x14000964f  mov     r15d, [r14+278h]
0x140009656  lea     r13, aTdxtdidispatch; "TdxTdiDispatchCreate"
0x14000965d  movzx   edi, al
0x140009660  shl     r15, 5
0x140009664  mov     eax, [r14+10h]
0x140009668  lea     rcx, [rsp+78h+arg_0]; CallersAddress
0x140009670  add     r15, r14
0x140009673  mov     [rsp+78h+arg_0], 0
0x14000967f  dec     eax
0x140009681  lea     rdx, [r15+188h]; CallersCaller
0x140009688  mov     [r15+190h], eax
0x14000968f  mov     [r15+178h], r13
0x140009696  mov     dword ptr [r15+180h], 0E9h
0x1400096a1  call    cs:__imp_RtlGetCallersAddress
0x1400096a8  nop     dword ptr [rax+rax+00h]
0x1400096ad  mov     eax, [r14+278h]
0x1400096b4  lea     rcx, [r14+170h]; SpinLock
0x1400096bb  inc     eax
0x1400096bd  movzx   edx, dil; NewIrql
0x1400096c1  and     eax, 7
0x1400096c4  mov     [r14+278h], eax
0x1400096cb  call    cs:__imp_KeReleaseSpinLock
0x1400096d2  nop     dword ptr [rax+rax+00h]
0x1400096d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400096de  cmp     rcx, r12
0x1400096e1  jz      short loc_1400096ED
0x1400096e3  cmp     byte ptr [rcx+29h], 5
0x1400096e7  jnb     loc_140009A82
0x1400096ed  mov     eax, 0FFFFFFFFh
0x1400096f2  lock xadd [r14+10h], eax
0x1400096f8  cmp     eax, 1
0x1400096fb  jnz     short loc_140009705
0x1400096fd  mov     rcx, r14
0x140009700  call    TdxCleanupObjectHeader
0x140009705  lock inc dword ptr cs:WPP_MAIN_CB.Queue+14h
0x14000970c  mov     dl, 2; PriorityBoost
0x14000970e  mov     [rbx+30h], ebp
0x140009711  mov     rcx, rbx; Irp
0x140009714  call    cs:__imp_IofCompleteRequest
0x14000971b  nop     dword ptr [rax+rax+00h]
0x140009720  mov     rbx, [rsp+78h+arg_18]
0x140009728  mov     eax, ebp
0x14000972a  add     rsp, 40h
0x14000972e  pop     r15
0x140009730  pop     r14
0x140009732  pop     r13
0x140009734  pop     r12
0x140009736  pop     rdi
0x140009737  pop     rsi
0x140009738  pop     rbp
0x140009739  retn
0x14000973b  mov     rsi, [r15+30h]
0x14000973f  mov     edx, 38h ; '8'
0x140009744  mov     ecx, 40h ; '@'
0x140009749  mov     r8d, 63786454h
0x14000974f  call    cs:__imp_ExAllocatePool2
0x140009756  nop     dword ptr [rax+rax+00h]
0x14000975b  mov     rdi, rax
0x14000975e  test    rax, rax
0x140009761  jnz     loc_14000984F
0x140009767  mov     ebp, 0C0000017h
0x14000976c  jmp     short loc_14000970C
0x14000976e  cmp     r12b, 10h
0x140009772  jnz     loc_1400099F7
0x140009778  lea     rdx, aTransportaddre; "TransportAddress"
0x14000977f  lea     rcx, [r13+8]; Buf1
0x140009783  call    memcmp
0x140009788  test    eax, eax
0x14000978a  jnz     loc_1400099E9
0x140009790  xor     edi, edi
0x140009792  mov     [rsp+78h+arg_0], rdi
0x14000979a  call    cs:__imp_IoGetTopLevelIrp
0x1400097a1  nop     dword ptr [rax+rax+00h]
0x1400097a6  cmp     rax, 5
0x1400097aa  jnz     loc_1400099AF
0x1400097b0  lea     rdx, [rsp+78h+arg_0]; ExtraCreateParameter
0x1400097b8  mov     rcx, rbx; Irp
0x1400097bb  call    cs:__imp_IoGetIrpExtraCreateParameter
0x1400097c2  nop     dword ptr [rax+rax+00h]
0x1400097c7  mov     ebp, eax
0x1400097c9  test    eax, eax
0x1400097cb  js      loc_14000970C
0x1400097d1  mov     rcx, [rsp+78h+arg_0]
0x1400097d9  movzx   r9d, word ptr [r13+6]
0x1400097de  cmp     r9d, 8
0x1400097e2  jb      loc_140009942
0x1400097e8  movzx   r8d, byte ptr [r13+5]
0x1400097ed  lea     rax, [rsp+78h+CallersAddress]
0x1400097f5  mov     rdx, [r15+30h]
0x1400097f9  add     r8, 9
0x1400097fd  mov     [rsp+78h+var_48], rax
0x140009802  add     r8, r13
0x140009805  mov     [rsp+78h+var_50], rcx
0x14000980a  mov     rcx, r14
0x14000980d  mov     [rsp+78h+CallersAddress], rdi
0x140009815  mov     [rsp+78h+var_58], r15
0x14000981a  call    TdxCreateTransportAddress
0x14000981f  mov     ebp, eax
0x140009821  test    eax, eax
0x140009823  js      loc_14000970C
0x140009829  mov     rcx, [rsp+78h+CallersAddress]
0x140009831  lea     rdx, aMinioNetioSess_1; "minio\\netio\\session\\tdi\\tdiprovider"...
0x140009838  mov     r8d, 11Bh
0x14000983e  call    DbgTdxDereferenceTransportAddress
  ... truncated ...
```
