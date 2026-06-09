# HUBPDO_EvtDeviceWdmIrpPnPPowerPreprocess

- ea: `0x140016160`
- end: `0x1400165ae`
- name: `HUBPDO_EvtDeviceWdmIrpPnPPowerPreprocess`
- size: `1102`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400024b8`
- `0x140014e2c`
- `0x140016160`
- `0x1400178bc`
- `0x140017be0`
- `0x140017d84`
- `0x1400198f4`
- `0x14003f5b4`
- `0x140045570`
- `0x14007ecc0`
- `0x14008292c`
- `0x140082bd8`
- `0x140084e28`
- `0x14008a828`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400163d2`
- `ntoskrnl!IofCompleteRequest` at `0x1400163d2`

## pseudocode

```c
__int64 __fastcall HUBPDO_EvtDeviceWdmIrpPnPPowerPreprocess(__int64 a1, IRP *a2)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // r14
  unsigned int MinorFunction; // ecx
  __int64 v6; // r15
  int Status; // r12d
  int v8; // edi
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  __int64 v16; // rax
  __int64 v17; // rdi
  __int64 v18; // rax
  int v19; // edi
  unsigned int v20; // edi
  int v21; // edx
  int v22; // eax
  int v23; // edx
  __int64 v24; // rax
  int LowPart; // eax
  _IO_STACK_LOCATION *v26; // rax
  _IO_STACK_LOCATION *v27; // rax
  __int64 v29; // [rsp+28h] [rbp-40h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->MajorFunction == 22 )
  {
    if ( CurrentStackLocation->MinorFunction != 2 || CurrentStackLocation->Parameters.Create.Options != 1 )
      goto LABEL_52;
    v6 = *(_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                       WdfDriverGlobals,
                       a1,
                       off_14006B1D0)
                   + 24);
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 4 && *(_DWORD *)(v6 + 2468) == 3 )
    {
      v22 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 688))(
              WdfDriverGlobals,
              a1,
              3221226195LL);
      if ( v22 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v23) = 3;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
          v23,
          5,
          51,
          (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
          v22);
      }
      v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
              WdfDriverGlobals,
              a1,
              off_14006B1D0);
      HUBIDLE_AddEvent(v24 + 72, 6008, 0);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v29) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
      LOBYTE(v21) = 4;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
        v21,
        5,
        52,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        v29);
    }
    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    if ( LowPart > 1 )
      *(_DWORD *)(v6 + 2716) = LowPart;
    *(_DWORD *)(v6 + 2468) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
LABEL_51:
    v26 = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v26[-1].MajorFunction = *(_OWORD *)&v26->MajorFunction;
    *(_OWORD *)&v26[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v26->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v26[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v26->Parameters.SetQuota + 6);
    v26[-1].FileObject = v26->FileObject;
    v26[-1].Control = 0;
    v27 = a2->Tail.Overlay.CurrentStackLocation;
    v27[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))HUBPDO_WdmPnpPowerIrpCompletionRoutineForAsynchronousCompletion;
    v27[-1].Context = (void *)v6;
    v27[-1].Control = -32;
    return (unsigned int)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, IRP *))(WdfFunctions_01015 + 272))(
                           WdfDriverGlobals,
                           a1,
                           a2);
  }
  if ( CurrentStackLocation->MajorFunction != 27 )
  {
LABEL_52:
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    return (unsigned int)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, IRP *))(WdfFunctions_01015 + 272))(
                           WdfDriverGlobals,
                           a1,
                           a2);
  }
  MinorFunction = CurrentStackLocation->MinorFunction;
  v6 = 0;
  Status = a2->IoStatus.Status;
  v8 = 2;
  if ( MinorFunction > 0xC )
  {
    v13 = MinorFunction - 19;
    if ( !v13 )
    {
      HUBPDO_EvtDeviceWdmIrpQueryIdPreprocess(a1, (__int64)a2);
      goto LABEL_33;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      HUBPDO_DispatchWdmPnpPowerIrpSynchronously(a1);
      if ( a2->IoStatus.Information )
      {
        v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                WdfDriverGlobals,
                a1,
                off_14006B1D0);
        v6 = *(_QWORD *)(v18 + 24);
        if ( *(_DWORD *)(v6 + 2440) )
        {
          HUBREG_UpdateSqmEnumerationFailureCode(*(_QWORD *)(v18 + 24));
          HUBMISC_ReportPnPFailureProblem(a1, *(_DWORD *)(v6 + 2440));
        }
        goto LABEL_17;
      }
      goto LABEL_11;
    }
    v15 = v14 - 3;
    if ( v15 )
    {
      if ( v15 == 2 )
      {
        HUBPDO_DispatchWdmPnpPowerIrpSynchronously(a1);
        HUBPDO_QueryForD3ColdSupportInAcpi(a1);
        v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                WdfDriverGlobals,
                a1,
                off_14006B1D0);
        v17 = v16;
        if ( *(_QWORD *)(*(_QWORD *)(v16 + 24) + 2656LL) )
          HUBPDO_PublishBillboardDetails(v16);
        if ( (*(_DWORD *)(*(_QWORD *)(v17 + 24) + 1640LL) & 0x40000) != 0 )
          HUBPDO_PublishDualRoleFeaturesProperty(v17);
        HUBPDO_AssignUsb4TunnelStateProperty(v17);
        a2->IoStatus.Status = 0;
        goto LABEL_17;
      }
      goto LABEL_33;
    }
LABEL_18:
    HUBPDO_DispatchWdmPnpPowerIrpSynchronously(a1);
    goto LABEL_17;
  }
  if ( MinorFunction == 12 )
    return (unsigned int)HUBPDO_EvtDeviceWdmIrpQueryDeviceTextPreprocess(a1, a2);
  if ( !CurrentStackLocation->MinorFunction )
    goto LABEL_18;
  v9 = MinorFunction - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( !v10 )
    {
      *(_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                    WdfDriverGlobals,
                    a1,
                    off_14006B1D0)
                + 64) = 0;
      goto LABEL_33;
    }
    v11 = v10 - 6;
    if ( v11 )
    {
      if ( v11 != 3 )
        goto LABEL_33;
      HUBPDO_DispatchWdmPnpPowerIrpSynchronously(a1);
LABEL_11:
      a2->IoStatus.Status = Status;
LABEL_17:
      v8 = 0;
      goto LABEL_33;
    }
    return (unsigned int)HUBPDO_EvtDeviceWdmIrpQueryInterfacePreprocess(a1, a2);
  }
  v6 = *(_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                     WdfDriverGlobals,
                     a1,
                     off_14006B1D0)
                 + 24);
  if ( (*(_DWORD *)(v6 + 1652) & 0x4000000) != 0
    && *(_BYTE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                    WdfDriverGlobals,
                    a1,
                    off_14006B1D0)
                + 536) == 1 )
  {
    a2->IoStatus.Status = -1073740537;
    goto LABEL_17;
  }
LABEL_33:
  if ( !v8 )
  {
    v20 = a2->IoStatus.Status;
    IofCompleteRequest(a2, 0);
    return v20;
  }
  v19 = v8 - 1;
  if ( !v19 )
    goto LABEL_51;
  if ( v19 == 1 )
    goto LABEL_52;
  return (unsigned int)-1073741823;
}

```

## disassembly

```asm
0x140016160  push    rbx
0x140016162  push    rsi
0x140016163  push    rdi
0x140016164  push    r12
0x140016166  push    r13
0x140016168  push    r14
0x14001616a  push    r15
0x14001616c  sub     rsp, 30h
0x140016170  mov     r14, [rdx+0B8h]
0x140016177  mov     rbx, rdx
0x14001617a  mov     rsi, rcx
0x14001617d  mov     al, [r14]
0x140016180  cmp     al, 16h
0x140016182  jz      loc_1400163E3
0x140016188  cmp     al, 1Bh
0x14001618a  jnz     loc_14001656E
0x140016190  movzx   ecx, byte ptr [r14+1]
0x140016195  xor     r15d, r15d
0x140016198  mov     r12d, [rdx+30h]
0x14001619c  mov     edi, 2
0x1400161a1  cmp     ecx, 0Ch
0x1400161a4  ja      loc_1400162AA
0x1400161aa  jz      loc_14001629D
0x1400161b0  test    ecx, ecx
0x1400161b2  jz      loc_140016293
0x1400161b8  sub     ecx, 1
0x1400161bb  jz      short loc_14001621B
0x1400161bd  sub     ecx, 1
0x1400161c0  jz      short loc_1400161EE
0x1400161c2  sub     ecx, 6
0x1400161c5  jz      short loc_1400161E1
0x1400161c7  cmp     ecx, 3
0x1400161ca  jnz     loc_1400163AA
0x1400161d0  mov     rcx, rsi
0x1400161d3  call    HUBPDO_DispatchWdmPnpPowerIrpSynchronously
0x1400161d8  mov     [rbx+30h], r12d
0x1400161dc  jmp     loc_14001628C
0x1400161e1  mov     rcx, rsi
0x1400161e4  call    HUBPDO_EvtDeviceWdmIrpQueryInterfacePreprocess
0x1400161e9  jmp     loc_140016599
0x1400161ee  mov     rax, cs:WdfFunctions_01015
0x1400161f5  mov     rdx, rsi
0x1400161f8  mov     r8, cs:off_14006B1D0
0x1400161ff  mov     rcx, cs:WdfDriverGlobals
0x140016206  mov     rax, [rax+650h]
0x14001620d  call    _guard_dispatch_icall
0x140016212  mov     [rax+40h], r15
0x140016216  jmp     loc_1400163AA
0x14001621b  mov     rax, cs:WdfFunctions_01015
0x140016222  mov     rdx, rsi
0x140016225  mov     r8, cs:off_14006B1D0
0x14001622c  mov     rcx, cs:WdfDriverGlobals
0x140016233  mov     rax, [rax+650h]
0x14001623a  call    _guard_dispatch_icall
0x14001623f  mov     r15, [rax+18h]
0x140016243  test    dword ptr [r15+674h], 4000000h
0x14001624e  jz      loc_1400163AA
0x140016254  mov     rax, cs:WdfFunctions_01015
0x14001625b  mov     rdx, rsi
0x14001625e  mov     r8, cs:off_14006B1D0
0x140016265  mov     rcx, cs:WdfDriverGlobals
0x14001626c  mov     rax, [rax+650h]
0x140016273  call    _guard_dispatch_icall
0x140016278  cmp     byte ptr [rax+218h], 1
0x14001627f  jnz     loc_1400163AA
0x140016285  mov     dword ptr [rbx+30h], 0C0000507h
0x14001628c  xor     edi, edi
0x14001628e  jmp     loc_1400163AA
0x140016293  mov     rcx, rsi
0x140016296  call    HUBPDO_DispatchWdmPnpPowerIrpSynchronously
0x14001629b  jmp     short loc_14001628C
0x14001629d  mov     rcx, rsi
0x1400162a0  call    HUBPDO_EvtDeviceWdmIrpQueryDeviceTextPreprocess
0x1400162a5  jmp     loc_140016599
0x1400162aa  sub     ecx, 13h
0x1400162ad  jz      loc_1400163A2
0x1400162b3  sub     ecx, 1
0x1400162b6  jz      loc_14001633E
0x1400162bc  sub     ecx, 3
0x1400162bf  jz      short loc_140016293
0x1400162c1  cmp     ecx, edi
0x1400162c3  jnz     loc_1400163AA
0x1400162c9  mov     rcx, rsi
0x1400162cc  call    HUBPDO_DispatchWdmPnpPowerIrpSynchronously
0x1400162d1  mov     rcx, rsi
0x1400162d4  call    HUBPDO_QueryForD3ColdSupportInAcpi
0x1400162d9  mov     rax, cs:WdfFunctions_01015
0x1400162e0  mov     rdx, rsi
0x1400162e3  mov     r8, cs:off_14006B1D0
0x1400162ea  mov     rcx, cs:WdfDriverGlobals
0x1400162f1  mov     rax, [rax+650h]
0x1400162f8  call    _guard_dispatch_icall
0x1400162fd  mov     rdi, rax
0x140016300  mov     rcx, [rax+18h]
0x140016304  cmp     [rcx+0A60h], r15
0x14001630b  jz      short loc_140016315
0x14001630d  mov     rcx, rax
0x140016310  call    HUBPDO_PublishBillboardDetails
0x140016315  mov     rcx, [rdi+18h]
0x140016319  test    dword ptr [rcx+668h], 40000h
0x140016323  jz      short loc_14001632D
0x140016325  mov     rcx, rdi
0x140016328  call    HUBPDO_PublishDualRoleFeaturesProperty
0x14001632d  mov     rcx, rdi
0x140016330  call    HUBPDO_AssignUsb4TunnelStateProperty
0x140016335  mov     [rbx+30h], r15d
0x140016339  jmp     loc_14001628C
0x14001633e  mov     rcx, rsi
0x140016341  call    HUBPDO_DispatchWdmPnpPowerIrpSynchronously
0x140016346  cmp     [rbx+38h], r15
0x14001634a  jz      loc_1400161D8
0x140016350  mov     rax, cs:WdfFunctions_01015
0x140016357  mov     rdx, rsi
0x14001635a  mov     r8, cs:off_14006B1D0
0x140016361  mov     rcx, cs:WdfDriverGlobals
0x140016368  mov     rax, [rax+650h]
0x14001636f  call    _guard_dispatch_icall
0x140016374  mov     r15, [rax+18h]
0x140016378  cmp     dword ptr [r15+988h], 0
0x140016380  jz      loc_14001628C
0x140016386  mov     rcx, r15
0x140016389  call    HUBREG_UpdateSqmEnumerationFailureCode
0x14001638e  mov     edx, [r15+988h]
0x140016395  mov     rcx, rsi
0x140016398  call    HUBMISC_ReportPnPFailureProblem
0x14001639d  jmp     loc_14001628C
0x1400163a2  mov     rcx, rsi
0x1400163a5  call    HUBPDO_EvtDeviceWdmIrpQueryIdPreprocess
0x1400163aa  test    edi, edi
0x1400163ac  jz      short loc_1400163CA
0x1400163ae  sub     edi, 1
0x1400163b1  jz      loc_140016526
0x1400163b7  cmp     edi, 1
0x1400163ba  jz      loc_14001656E
0x1400163c0  mov     edi, 0C0000001h
0x1400163c5  jmp     loc_14001659B
0x1400163ca  mov     edi, [rbx+30h]
0x1400163cd  xor     edx, edx; PriorityBoost
0x1400163cf  mov     rcx, rbx; Irp
0x1400163d2  call    cs:__imp_IofCompleteRequest
0x1400163d9  nop     dword ptr [rax+rax+00h]
0x1400163de  jmp     loc_14001659B
0x1400163e3  mov     edi, 2
0x1400163e8  cmp     [r14+1], dil
0x1400163ec  jnz     loc_14001656E
0x1400163f2  cmp     dword ptr [r14+10h], 1
0x1400163f7  jnz     loc_14001656E
0x1400163fd  mov     rax, cs:WdfFunctions_01015
0x140016404  mov     rdx, rsi
0x140016407  mov     r8, cs:off_14006B1D0
0x14001640e  mov     rcx, cs:WdfDriverGlobals
0x140016415  mov     rax, [rax+650h]
0x14001641c  call    _guard_dispatch_icall
0x140016421  cmp     dword ptr [r14+18h], 4
0x140016426  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001642d  lea     r13, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140016434  mov     r12d, 5
0x14001643a  mov     r15, [rax+18h]
0x14001643e  jnz     loc_1400164DA
0x140016444  cmp     dword ptr [r15+9A4h], 3
0x14001644c  jnz     loc_1400164DA
0x140016452  mov     rax, cs:WdfFunctions_01015
0x140016459  mov     r8d, 0C00002D3h
0x14001645f  mov     rcx, cs:WdfDriverGlobals
0x140016466  mov     rdx, rsi
0x140016469  mov     rax, [rax+2B0h]
0x140016470  call    _guard_dispatch_icall
0x140016475  test    eax, eax
0x140016477  jns     short loc_1400164A5
0x140016479  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140016480  jz      short loc_1400164A5
0x140016482  mov     rcx, [r15+8]
0x140016486  lea     r9d, [r12+2Eh]
0x14001648b  mov     dword ptr [rsp+68h+var_40], eax
0x14001648f  mov     r8d, r12d
0x140016492  mov     dl, 3
0x140016494  mov     [rsp+68h+var_48], r13
0x140016499  mov     rcx, [rcx+598h]
0x1400164a0  call    WPP_RECORDER_SF_d
0x1400164a5  mov     rax, cs:WdfFunctions_01015
0x1400164ac  mov     rdx, rsi
0x1400164af  mov     r8, cs:off_14006B1D0
0x1400164b6  mov     rcx, cs:WdfDriverGlobals
0x1400164bd  mov     rax, [rax+650h]
0x1400164c4  call    _guard_dispatch_icall
0x1400164c9  xor     r8d, r8d
0x1400164cc  mov     edx, 1778h
0x1400164d1  lea     rcx, [rax+48h]
0x1400164d5  call    HUBIDLE_AddEvent
0x1400164da  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x1400164e1  jz      short loc_14001650B
0x1400164e3  mov     rcx, [r15+8]
0x1400164e7  mov     r9d, 34h ; '4'
0x1400164ed  mov     eax, [r14+18h]
0x1400164f1  mov     r8d, r12d
0x1400164f4  mov     dword ptr [rsp+68h+var_40], eax
0x1400164f8  mov     dl, 4
0x1400164fa  mov     [rsp+68h+var_48], r13
0x1400164ff  mov     rcx, [rcx+598h]
0x140016506  call    WPP_RECORDER_SF_d
0x14001650b  mov     eax, [r14+18h]
0x14001650f  cmp     eax, 1
0x140016512  jle     short loc_14001651B
0x140016514  mov     [r15+0A9Ch], eax
0x14001651b  mov     eax, [r14+18h]
0x14001651f  mov     [r15+9A4h], eax
0x140016526  mov     rax, [rbx+0B8h]
0x14001652d  lea     rcx, HUBPDO_WdmPnpPowerIrpCompletionRoutineForAsynchronousCompletion
0x140016534  movups  xmm0, xmmword ptr [rax]
0x140016537  movups  xmmword ptr [rax-48h], xmm0
0x14001653b  movups  xmm1, xmmword ptr [rax+10h]
0x14001653f  movups  xmmword ptr [rax-38h], xmm1
0x140016543  movups  xmm0, xmmword ptr [rax+20h]
0x140016547  movups  xmmword ptr [rax-28h], xmm0
0x14001654b  movsd   xmm1, qword ptr [rax+30h]
0x140016550  movsd   qword ptr [rax-18h], xmm1
0x140016555  mov     byte ptr [rax-45h], 0
0x140016559  mov     rax, [rbx+0B8h]
0x140016560  mov     [rax-10h], rcx
0x140016564  mov     [rax-8], r15
0x140016568  mov     byte ptr [rax-45h], 0E0h
0x14001656c  jmp     short loc_140016579
0x14001656e  inc     byte ptr [rbx+43h]
0x140016571  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140016579  mov     rax, cs:WdfFunctions_01015
0x140016580  mov     r8, rbx
0x140016583  mov     rcx, cs:WdfDriverGlobals
0x14001658a  mov     rdx, rsi
0x14001658d  mov     rax, [rax+110h]
0x140016594  call    _guard_dispatch_icall
0x140016599  mov     edi, eax
0x14001659b  mov     eax, edi
0x14001659d  add     rsp, 30h
0x1400165a1  pop     r15
0x1400165a3  pop     r14
0x1400165a5  pop     r13
0x1400165a7  pop     r12
0x1400165a9  pop     rdi
0x1400165aa  pop     rsi
0x1400165ab  pop     rbx
0x1400165ac  retn
```
