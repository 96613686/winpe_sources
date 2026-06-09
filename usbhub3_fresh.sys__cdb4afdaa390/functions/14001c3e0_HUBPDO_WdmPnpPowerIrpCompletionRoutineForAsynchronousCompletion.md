# HUBPDO_WdmPnpPowerIrpCompletionRoutineForAsynchronousCompletion

- ea: `0x14001c3e0`
- end: `0x14001c568`
- name: `HUBPDO_WdmPnpPowerIrpCompletionRoutineForAsynchronousCompletion`
- size: `392`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x14001c3e0`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBPDO_WdmPnpPowerIrpCompletionRoutineForAsynchronousCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  int v6; // eax
  int v7; // edx
  int v9; // [rsp+28h] [rbp-58h]
  __int128 v10; // [rsp+30h] [rbp-50h] BYREF
  __int64 v11; // [rsp+40h] [rbp-40h]
  __int128 v12; // [rsp+48h] [rbp-38h] BYREF
  __int128 v13; // [rsp+58h] [rbp-28h]
  __int128 v14; // [rsp+68h] [rbp-18h]
  __int64 *v15; // [rsp+78h] [rbp-8h]
  __int64 v16; // [rsp+98h] [rbp+18h] BYREF

  v12 = 0;
  LODWORD(v15) = 0;
  v13 = 0;
  LODWORD(v11) = 0;
  v14 = 0;
  v16 = 0;
  v10 = 0;
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  v5 = *(_QWORD *)(a3 + 16);
  *(_QWORD *)&v13 = 0;
  v15 = off_14006B220;
  v12 = 0;
  LODWORD(v12) = 56;
  v14 = 0;
  *((_QWORD *)&v13 + 1) = 0x100000001LL;
  *(_QWORD *)&v14 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(
                      WdfDriverGlobals,
                      v5);
  v11 = 1;
  *(_QWORD *)&v10 = 24;
  *((_QWORD *)&v10 + 1) = HUBPDO_EvtCompleteIrpWorkItem;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64 *))(WdfFunctions_01015 + 3032))(
         WdfDriverGlobals,
         &v10,
         &v12,
         &v16);
  if ( v6 >= 0 )
  {
    *(_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                 WdfDriverGlobals,
                 v16,
                 off_14006B220) = a2;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3040))(WdfDriverGlobals, v16);
    return 3221225494LL;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = v6;
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a3 + 8) + 1432LL),
        v7,
        5,
        166,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        v9);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14001c3e0  mov     [rsp-8+arg_0], rbx
0x14001c3e5  mov     [rsp-8+arg_10], rdi
0x14001c3ea  push    rbp
0x14001c3eb  mov     rbp, rsp
0x14001c3ee  sub     rsp, 80h
0x14001c3f5  xor     eax, eax
0x14001c3f7  xorps   xmm0, xmm0
0x14001c3fa  mov     rdi, r8
0x14001c3fd  mov     rbx, rdx
0x14001c400  movups  [rbp+var_38], xmm0
0x14001c404  mov     dword ptr [rbp+var_8], eax
0x14001c407  movups  [rbp+var_28], xmm0
0x14001c40b  mov     dword ptr [rbp+var_40], eax
0x14001c40e  movups  [rbp+var_18], xmm0
0x14001c412  mov     [rbp+arg_8], rax
0x14001c416  movups  [rbp+var_50], xmm0
0x14001c41a  cmp     [rdx+41h], al
0x14001c41d  jz      short loc_14001C42A
0x14001c41f  mov     rax, [rdx+0B8h]
0x14001c426  or      byte ptr [rax+3], 1
0x14001c42a  mov     rax, cs:off_14006B220
0x14001c431  mov     rdx, [r8+10h]
0x14001c435  mov     rcx, cs:WdfDriverGlobals
0x14001c43c  movups  [rbp+var_28], xmm0
0x14001c440  mov     [rbp+var_8], rax
0x14001c444  mov     rax, cs:WdfFunctions_01015
0x14001c44b  movups  [rbp+var_38], xmm0
0x14001c44f  mov     dword ptr [rbp+var_38], 38h ; '8'
0x14001c456  movups  [rbp+var_18], xmm0
0x14001c45a  mov     dword ptr [rbp+var_28+8], 1
0x14001c461  mov     dword ptr [rbp+var_28+0Ch], 1
0x14001c468  mov     rax, [rax+660h]
0x14001c46f  call    _guard_dispatch_icall
0x14001c474  mov     rcx, cs:WdfDriverGlobals
0x14001c47b  lea     r9, [rbp+arg_8]
0x14001c47f  mov     qword ptr [rbp+var_18], rax
0x14001c483  lea     r8, [rbp+var_38]
0x14001c487  xor     eax, eax
0x14001c489  lea     rdx, [rbp+var_50]
0x14001c48d  mov     [rbp+var_40], rax
0x14001c491  xorps   xmm0, xmm0
0x14001c494  movups  [rbp+var_50], xmm0
0x14001c498  lea     rax, HUBPDO_EvtCompleteIrpWorkItem
0x14001c49f  mov     dword ptr [rbp+var_50], 18h
0x14001c4a6  mov     qword ptr [rbp+var_50+8], rax
0x14001c4aa  mov     rax, cs:WdfFunctions_01015
0x14001c4b1  mov     byte ptr [rbp+var_40], 1
0x14001c4b5  mov     rax, [rax+0BD8h]
0x14001c4bc  call    _guard_dispatch_icall
0x14001c4c1  test    eax, eax
0x14001c4c3  jns     short loc_14001C507
0x14001c4c5  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001c4cc  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001c4d3  jz      short loc_14001C503
0x14001c4d5  mov     rcx, [rdi+8]
0x14001c4d9  mov     r9d, 0A6h
0x14001c4df  mov     [rsp+80h+var_58], eax
0x14001c4e3  mov     r8d, 5
0x14001c4e9  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14001c4f0  mov     dl, 2
0x14001c4f2  mov     [rsp+80h+var_60], rax
0x14001c4f7  mov     rcx, [rcx+598h]
0x14001c4fe  call    WPP_RECORDER_SF_d
0x14001c503  xor     eax, eax
0x14001c505  jmp     short loc_14001C552
0x14001c507  mov     rax, cs:WdfFunctions_01015
0x14001c50e  mov     r8, cs:off_14006B220
0x14001c515  mov     rdx, [rbp+arg_8]
0x14001c519  mov     rcx, cs:WdfDriverGlobals
0x14001c520  mov     rax, [rax+650h]
0x14001c527  call    _guard_dispatch_icall
0x14001c52c  mov     [rax], rbx
0x14001c52f  mov     rax, cs:WdfFunctions_01015
0x14001c536  mov     rdx, [rbp+arg_8]
0x14001c53a  mov     rcx, cs:WdfDriverGlobals
0x14001c541  mov     rax, [rax+0BE0h]
0x14001c548  call    _guard_dispatch_icall
0x14001c54d  mov     eax, 0C0000016h
0x14001c552  lea     r11, [rsp+80h+var_s0]
0x14001c55a  mov     rbx, [r11+10h]
0x14001c55e  mov     rdi, [r11+20h]
0x14001c562  mov     rsp, r11
0x14001c565  pop     rbp
0x14001c566  retn
```
