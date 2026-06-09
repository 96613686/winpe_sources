# HUBHTX_SendInterruptTransferComplete

- ea: `0x140005dd0`
- end: `0x140005f10`
- name: `HUBHTX_SendInterruptTransferComplete`
- size: `320`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400025a4`
- `0x140005dd0`
- `0x140006644`
- `0x14000a53c`
- `0x140033530`

## pseudocode

```c
__int64 __fastcall HUBHTX_SendInterruptTransferComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // eax
  int v6; // ebx
  int v7; // ebp
  _QWORD *v8; // rsi
  __int64 v10; // [rsp+20h] [rbp-58h]
  __int64 v11; // [rsp+28h] [rbp-50h]
  __int64 v12; // [rsp+30h] [rbp-48h]

  v4 = *(unsigned __int16 *)(a4 + 1028);
  v6 = *(_DWORD *)(a3 + 8);
  v7 = *(_DWORD *)(a4 + 996);
  *(_WORD *)(a4 + 1146) = v4;
  *(_DWORD *)(a4 + 1152) = 8 * v4;
  *(_QWORD *)(a4 + 1160) = *(_QWORD *)(a4 + 1136);
  if ( v6 < 0 )
  {
    v8 = (_QWORD *)(a4 + 2536);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dD(*v8, 2, 3, 29, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids, v6, v7);
    if ( v6 != -1073741536 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dD(*v8, 2, 3, 30, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids, v6, v7);
      if ( (*(_DWORD *)(a4 + 2608) & 4) != 0 )
        HUBMISC_VerifierDbgBreak("HubHwVerifierInterruptTransferFailure", a4 + 1280);
      *(_DWORD *)(a4 + 2612) = 1073872898;
      if ( (byte_14006ED42 & 2) != 0 )
      {
        LODWORD(v12) = v6;
        LODWORD(v11) = v7;
        LODWORD(v10) = 0;
        McTemplateK0pqqq_EtwWriteTransfer(
          a1,
          (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_PORT_INTERRUPT_TRANSFER_ERROR,
          (const GUID *)(a4 + 2428),
          *(_QWORD *)(a4 + 248),
          v10,
          v11,
          v12);
      }
    }
  }
  return HUBSM_AddEvent(a4 + 1280, ((v6 >> 31) & 0xFFFFFFFC) + 2034);
}

```

## disassembly

```asm
0x140005dd0  push    rbx
0x140005dd2  push    rbp
0x140005dd3  push    rsi
0x140005dd4  push    rdi
0x140005dd5  push    r12
0x140005dd7  push    r14
0x140005dd9  sub     rsp, 48h
0x140005ddd  movzx   eax, word ptr [r9+404h]
0x140005de5  mov     rdi, r9
0x140005de8  mov     ebx, [r8+8]
0x140005dec  mov     ebp, [r9+3E4h]
0x140005df3  mov     [r9+47Ah], ax
0x140005dfb  shl     eax, 3
0x140005dfe  mov     [r9+480h], eax
0x140005e05  mov     rax, [r9+470h]
0x140005e0c  mov     [r9+488h], rax
0x140005e13  test    ebx, ebx
0x140005e15  jns     loc_140005EEA
0x140005e1b  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140005e22  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140005e29  lea     rsi, [r9+9E8h]
0x140005e30  lea     r12, WPP_70469c384dd13630d566350a6f2705ad_Traceguids
0x140005e37  jz      short loc_140005E5A
0x140005e39  mov     rcx, [rsi]
0x140005e3c  mov     r9d, 1Dh
0x140005e42  mov     dword ptr [rsp+78h+var_48], ebp
0x140005e46  mov     dl, 2
0x140005e48  mov     dword ptr [rsp+78h+var_50], ebx
0x140005e4c  mov     [rsp+78h+var_58], r12
0x140005e51  lea     r8d, [r9-1Ah]
0x140005e55  call    WPP_RECORDER_SF_dD
0x140005e5a  cmp     ebx, 0C0000120h
0x140005e60  jz      loc_140005EEA
0x140005e66  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140005e6d  jz      short loc_140005E90
0x140005e6f  mov     rcx, [rsi]
0x140005e72  mov     r9d, 1Eh
0x140005e78  mov     dword ptr [rsp+78h+var_48], ebp
0x140005e7c  mov     dl, 2
0x140005e7e  mov     dword ptr [rsp+78h+var_50], ebx
0x140005e82  mov     [rsp+78h+var_58], r12
0x140005e87  lea     r8d, [r9-1Bh]
0x140005e8b  call    WPP_RECORDER_SF_dD
0x140005e90  mov     eax, [rdi+0A30h]
0x140005e96  test    al, 4
0x140005e98  jz      short loc_140005EAD
0x140005e9a  lea     rdx, [rdi+500h]
0x140005ea1  lea     rcx, aHubhwverifieri; "HubHwVerifierInterruptTransferFailure"
0x140005ea8  call    HUBMISC_VerifierDbgBreak
0x140005ead  mov     dword ptr [rdi+0A34h], 40020002h
0x140005eb7  test    cs:byte_14006ED42, 2
0x140005ebe  jz      short loc_140005EEA
0x140005ec0  mov     r9, [rdi+0F8h]
0x140005ec7  lea     r8, [rdi+97Ch]
0x140005ece  mov     dword ptr [rsp+78h+var_48], ebx
0x140005ed2  lea     rdx, USBHUB3_ETW_EVENT_PORT_INTERRUPT_TRANSFER_ERROR
0x140005ed9  mov     dword ptr [rsp+78h+var_50], ebp
0x140005edd  mov     dword ptr [rsp+78h+var_58], 0
0x140005ee5  call    McTemplateK0pqqq_EtwWriteTransfer
0x140005eea  sar     ebx, 1Fh
0x140005eed  lea     rcx, [rdi+500h]
0x140005ef4  and     ebx, 0FFFFFFFCh
0x140005ef7  lea     edx, [rbx+7F2h]
0x140005efd  call    HUBSM_AddEvent
0x140005f02  add     rsp, 48h
0x140005f06  pop     r14
0x140005f08  pop     r12
0x140005f0a  pop     rdi
0x140005f0b  pop     rsi
0x140005f0c  pop     rbp
0x140005f0d  pop     rbx
0x140005f0e  retn
```
