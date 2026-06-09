# TetheringService::InterfaceOperStatusChangeCallback(_NET_LUID_LH const &,IF_OPER_STATUS,void *)

- ea: `0x180019fe0`
- end: `0x18001a216`
- name: `?InterfaceOperStatusChangeCallback@TetheringService@@CAXAEBT_NET_LUID_LH@@W4IF_OPER_STATUS@@PEAX@Z`
- size: `566`
- prototype: `void __fastcall(const union _NET_LUID_LH *, enum IF_OPER_STATUS, HANDLE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x1800132c8`
- `0x180019fe0`
- `0x18001acb4`
- `0x18001ad34`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18001a056`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18001a056`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001a15b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001a15b`

## pseudocode

```c
void __fastcall TetheringService::InterfaceOperStatusChangeCallback(
        const union _NET_LUID_LH *a1,
        enum IF_OPER_STATUS a2,
        HANDLE *a3)
{
  TetheringServiceTelemetry *v6; // rcx
  NTSTATUS SharedInterfaceIndices; // eax
  __int64 v8; // rdx
  unsigned int v9[4]; // [rsp+20h] [rbp-10h] BYREF
  ULONG InterfaceIndex; // [rsp+70h] [rbp+40h] BYREF
  unsigned int v11; // [rsp+78h] [rbp+48h] BYREF

  if ( !a3 )
    return;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 352, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (unsigned int)(a2 - 1) > 1 )
    goto LABEL_39;
  InterfaceIndex = 0;
  SharedInterfaceIndices = ConvertInterfaceLuidToIndex(a1, &InterfaceIndex);
  if ( SharedInterfaceIndices )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_39;
    v8 = 356;
LABEL_37:
    WPP_SF_d(
      *((_QWORD *)v6 + 2),
      v8,
      &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
      (unsigned int)SharedInterfaceIndices);
    goto LABEL_38;
  }
  v11 = 0;
  v9[0] = 0;
  SharedInterfaceIndices = InterfaceMgr::GetSharedInterfaceIndices((InterfaceMgr *)(a3 + 44), &v11, v9);
  if ( SharedInterfaceIndices < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_39;
    v8 = 355;
    goto LABEL_37;
  }
  if ( a2 == IfOperStatusDown )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        353,
        &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
        InterfaceIndex);
      v6 = WPP_GLOBAL_Control;
    }
    if ( InterfaceIndex == v11 )
    {
      TetheringService::NotifyPublicConnectionDown((TetheringService *)a3, a1);
    }
    else
    {
      if ( InterfaceIndex != v9[0] || !*((_BYTE *)a3 + 1744) )
      {
LABEL_39:
        if ( v6 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)v6 + 2), 357, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
        return;
      }
      TetheringService::NotifyPrivateConnectionDown((TetheringService *)a3);
    }
LABEL_38:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_39;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 354, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, InterfaceIndex);
    v6 = WPP_GLOBAL_Control;
  }
  if ( InterfaceIndex != v11 )
  {
    if ( InterfaceIndex != v9[0] )
      goto LABEL_39;
    *((_BYTE *)a3 + 1744) = 1;
    goto LABEL_38;
  }
  if ( v6 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v6 + 2), 294, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  if ( ChangeTimerQueueTimer(a3[201], a3[200], 0xFFFFFFFF, 0xFFFFFFFF) )
    *((_BYTE *)a3 + 1620) = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_39;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 295, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    goto LABEL_38;
  }
}

```

## disassembly

```asm
0x180019fe0  test    r8, r8
0x180019fe3  jz      locret_18001A215
0x180019fe9  mov     [rsp-28h+arg_0], rbx
0x180019fee  push    rbp
0x180019fef  push    rsi
0x180019ff0  push    rdi
0x180019ff1  push    r12
0x180019ff3  push    r14
0x180019ff5  mov     rbp, rsp
0x180019ff8  sub     rsp, 30h
0x180019ffc  mov     rbx, r8
0x180019fff  mov     edi, edx
0x18001a001  mov     rsi, rcx
0x18001a004  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a00b  lea     r14, WPP_GLOBAL_Control
0x18001a012  lea     r12, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001a019  cmp     rcx, r14
0x18001a01c  jz      short loc_18001A03C
0x18001a01e  test    byte ptr [rcx+1Ch], 8
0x18001a022  jz      short loc_18001A03C
0x18001a024  mov     rcx, [rcx+10h]
0x18001a028  mov     edx, 160h
0x18001a02d  mov     r8, r12
0x18001a030  call    WPP_SF_
0x18001a035  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a03c  lea     eax, [rdi-1]
0x18001a03f  cmp     eax, 1
0x18001a042  ja      loc_18001A1E9
0x18001a048  lea     rdx, [rbp+InterfaceIndex]; InterfaceIndex
0x18001a04c  mov     [rbp+InterfaceIndex], 0
0x18001a053  mov     rcx, rsi; InterfaceLuid
0x18001a056  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18001a05c  test    eax, eax
0x18001a05e  jnz     loc_18001A1BC
0x18001a064  lea     rcx, [rbx+160h]; this
0x18001a06b  mov     [rbp+arg_18], eax
0x18001a06e  lea     r8, [rbp+var_10]; unsigned int *
0x18001a072  mov     [rbp+var_10], eax
0x18001a075  lea     rdx, [rbp+arg_18]; unsigned int *
0x18001a079  call    ?GetSharedInterfaceIndices@InterfaceMgr@@QEAAJPEAK0@Z; InterfaceMgr::GetSharedInterfaceIndices(ulong *,ulong *)
0x18001a07e  test    eax, eax
0x18001a080  js      loc_18001A1A3
0x18001a086  cmp     edi, 2
0x18001a089  jnz     short loc_18001A0F4
0x18001a08b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a092  cmp     rcx, r14
0x18001a095  jz      short loc_18001A0B9
0x18001a097  test    byte ptr [rcx+1Ch], 8
0x18001a09b  jz      short loc_18001A0B9
0x18001a09d  mov     r9d, [rbp+InterfaceIndex]
0x18001a0a1  mov     edx, 161h
0x18001a0a6  mov     rcx, [rcx+10h]
0x18001a0aa  mov     r8, r12
0x18001a0ad  call    WPP_SF_d
0x18001a0b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0b9  mov     eax, [rbp+InterfaceIndex]
0x18001a0bc  cmp     eax, [rbp+arg_18]
0x18001a0bf  jnz     short loc_18001A0D1
0x18001a0c1  mov     rdx, rsi; union _NET_LUID_LH *
0x18001a0c4  mov     rcx, rbx; this
0x18001a0c7  call    ?NotifyPublicConnectionDown@TetheringService@@QEAAXAEBT_NET_LUID_LH@@@Z; TetheringService::NotifyPublicConnectionDown(_NET_LUID_LH const &)
0x18001a0cc  jmp     loc_18001A1E2
0x18001a0d1  cmp     eax, [rbp+var_10]
0x18001a0d4  jnz     loc_18001A1E9
0x18001a0da  cmp     byte ptr [rbx+6D0h], 0
0x18001a0e1  jz      loc_18001A1E9
0x18001a0e7  mov     rcx, rbx; this
0x18001a0ea  call    ?NotifyPrivateConnectionDown@TetheringService@@QEAAXXZ; TetheringService::NotifyPrivateConnectionDown(void)
0x18001a0ef  jmp     loc_18001A1E2
0x18001a0f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0fb  cmp     rcx, r14
0x18001a0fe  jz      short loc_18001A122
0x18001a100  test    byte ptr [rcx+1Ch], 8
0x18001a104  jz      short loc_18001A122
0x18001a106  mov     r9d, [rbp+InterfaceIndex]
0x18001a10a  mov     edx, 162h
0x18001a10f  mov     rcx, [rcx+10h]
0x18001a113  mov     r8, r12
0x18001a116  call    WPP_SF_d
0x18001a11b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a122  mov     eax, [rbp+InterfaceIndex]
0x18001a125  cmp     eax, [rbp+arg_18]
0x18001a128  jnz     short loc_18001A195
0x18001a12a  cmp     rcx, r14
0x18001a12d  jz      short loc_18001A146
0x18001a12f  test    byte ptr [rcx+1Ch], 8
0x18001a133  jz      short loc_18001A146
0x18001a135  mov     rcx, [rcx+10h]
0x18001a139  mov     edx, 126h
0x18001a13e  mov     r8, r12
0x18001a141  call    WPP_SF_
0x18001a146  mov     rdx, [rbx+640h]; Timer
0x18001a14d  or      r8d, 0FFFFFFFFh; DueTime
0x18001a151  mov     rcx, [rbx+648h]; TimerQueue
0x18001a158  mov     r9d, r8d; Period
0x18001a15b  call    cs:__imp_ChangeTimerQueueTimer
0x18001a161  test    eax, eax
0x18001a163  jz      short loc_18001A16C
0x18001a165  mov     byte ptr [rbx+654h], 0
0x18001a16c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a173  cmp     rcx, r14
0x18001a176  jz      loc_18001A205
0x18001a17c  test    byte ptr [rcx+1Ch], 8
0x18001a180  jz      short loc_18001A1E9
0x18001a182  mov     rcx, [rcx+10h]
0x18001a186  mov     edx, 127h
0x18001a18b  mov     r8, r12
0x18001a18e  call    WPP_SF_
0x18001a193  jmp     short loc_18001A1E2
0x18001a195  cmp     eax, [rbp+var_10]
0x18001a198  jnz     short loc_18001A1E9
0x18001a19a  mov     byte ptr [rbx+6D0h], 1
0x18001a1a1  jmp     short loc_18001A1E2
0x18001a1a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1aa  cmp     rcx, r14
0x18001a1ad  jz      short loc_18001A205
0x18001a1af  test    byte ptr [rcx+1Ch], 1
0x18001a1b3  jz      short loc_18001A1E9
0x18001a1b5  mov     edx, 163h
0x18001a1ba  jmp     short loc_18001A1D3
0x18001a1bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1c3  cmp     rcx, r14
0x18001a1c6  jz      short loc_18001A205
0x18001a1c8  test    byte ptr [rcx+1Ch], 1
0x18001a1cc  jz      short loc_18001A1E9
0x18001a1ce  mov     edx, 164h
0x18001a1d3  mov     rcx, [rcx+10h]
0x18001a1d7  mov     r9d, eax
0x18001a1da  mov     r8, r12
0x18001a1dd  call    WPP_SF_d
0x18001a1e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1e9  cmp     rcx, r14
0x18001a1ec  jz      short loc_18001A205
0x18001a1ee  test    byte ptr [rcx+1Ch], 8
0x18001a1f2  jz      short loc_18001A205
0x18001a1f4  mov     rcx, [rcx+10h]
0x18001a1f8  mov     edx, 165h
0x18001a1fd  mov     r8, r12
0x18001a200  call    WPP_SF_
0x18001a205  mov     rbx, [rsp+30h+arg_0]
0x18001a20a  add     rsp, 30h
0x18001a20e  pop     r14
0x18001a210  pop     r12
0x18001a212  pop     rdi
0x18001a213  pop     rsi
0x18001a214  pop     rbp
0x18001a215  retn
```
