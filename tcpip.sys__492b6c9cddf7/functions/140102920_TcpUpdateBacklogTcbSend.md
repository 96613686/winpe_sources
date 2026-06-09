# TcpUpdateBacklogTcbSend

- ea: `0x140102920`
- end: `0x140102aff`
- name: `TcpUpdateBacklogTcbSend`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001bf34`

## callees

- `0x14001d320`
- `0x1400772e0`
- `0x1400d6908`
- `0x1400d6948`
- `0x140102920`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x140102956`
- `ntoskrnl!KeReadStateEvent` at `0x140102971`
- `ntoskrnl!KeReadStateEvent` at `0x140102a4e`
- `ntoskrnl!KeReadStateEvent` at `0x140102a69`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1c44`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1c59`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1cb2`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1cc7`
- `ntoskrnl!KeReadStateEvent` at `0x140102956`
- `ntoskrnl!KeReadStateEvent` at `0x140102971`
- `ntoskrnl!KeReadStateEvent` at `0x140102a4e`
- `ntoskrnl!KeReadStateEvent` at `0x140102a69`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1c44`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1c59`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1cb2`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1cc7`

## pseudocode

```c
__int64 __fastcall TcpUpdateBacklogTcbSend(__int64 a1, unsigned int a2)
{
  __int64 result; // rax
  unsigned __int8 v5; // cl
  unsigned int v6; // r9d
  char v7; // r8
  unsigned int v8; // edx
  char v9; // bl
  LONG v10; // eax
  char StateEvent; // bl
  char v12; // al
  int v13; // eax
  __int64 v14; // [rsp+40h] [rbp-38h] BYREF
  __int64 v15; // [rsp+48h] [rbp-30h]

  if ( LOBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) )
  {
    if ( KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceContext) || KeReadStateEvent(LowPagedPoolEvent) )
    {
      if ( dword_1402201D4
        && (!TcpipTraceFiltersExist || *(char *)(a1 + 804) < 0)
        && (BYTE2(WPP_MAIN_CB.Reserved) & 1) != 0 )
      {
        v15 = 0;
        v14 = a1;
        StateEvent = KeReadStateEvent(LowPagedPoolEvent);
        v12 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceContext);
        McTemplateK0qqqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_ISB_BEGIN_THROTTLE,
          (unsigned int)&v14,
          0,
          0,
          v12,
          StateEvent);
      }
      LOBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) = 0;
    }
  }
  else if ( KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredContext)
         && KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) )
  {
    if ( dword_1402201D4 && (!TcpipTraceFiltersExist || *(char *)(a1 + 804) < 0) && SBYTE1(WPP_MAIN_CB.Reserved) < 0 )
    {
      v15 = 0;
      v14 = a1;
      v9 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
      v10 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredContext);
      McTemplateK0qqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCP_ISB_END_THROTTLE,
        (unsigned int)&v14,
        v10,
        v9,
        0,
        0);
    }
    LOBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) = 1;
  }
  result = *(unsigned __int8 *)(a1 + 790);
  if ( (_BYTE)result )
  {
    result = *(_DWORD *)(a1 + 160) & (unsigned int)(-1024 * result);
    if ( *(_DWORD *)(a1 + 168) <= (unsigned int)result )
      return result;
    *(_DWORD *)(a1 + 168) = result;
    goto LABEL_12;
  }
  v5 = *(_BYTE *)(a1 + 172);
  if ( v5 )
  {
    v6 = *(_DWORD *)(a1 + 160);
    v7 = 0;
    do
    {
      result = v5;
      v8 = TcpBackLogRange[v5 - 1];
      if ( v5 >= 2u )
      {
        result = v5;
        v8 += TcpBackLogRange[v5 - 2];
      }
      if ( v6 >= v8 >> 1 )
        break;
      --v5;
      v7 = 1;
      *(_BYTE *)(a1 + 172) = v5;
    }
    while ( v5 );
    if ( v7 )
    {
LABEL_12:
      if ( dword_1402201D4
        && (!TcpipTraceFiltersExist || *(char *)(a1 + 804) < 0)
        && (BYTE2(WPP_MAIN_CB.Reserved) & 0x10) != 0 )
      {
        v15 = 0;
        v14 = a1;
        v13 = TcpComputeBacklogTcbSend(a1);
        McTemplateK0qqqqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_TCB_CHANGE_ISB,
          (unsigned int)&v14,
          v13,
          *(_DWORD *)(a1 + 196),
          *(_DWORD *)(a1 + 160),
          *(_DWORD *)(a1 + 448),
          *(_DWORD *)(a1 + 200));
      }
      *(_DWORD *)(a1 + 120) |= 0x8000u;
      return TcpTcbDelay(a1, a2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140102920  mov     [rsp+arg_10], rbx
0x140102925  push    rbp
0x140102926  push    rsi
0x140102927  push    rdi
0x140102928  sub     rsp, 60h
0x14010292c  mov     rax, cs:__security_cookie
0x140102933  xor     rax, rsp
0x140102936  mov     [rsp+78h+var_28], rax
0x14010293b  xor     ebp, ebp
0x14010293d  mov     esi, edx
0x14010293f  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, bpl
0x140102946  mov     rdi, rcx
0x140102949  jz      loc_140102A47
0x14010294f  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; Event
0x140102956  call    cs:__imp_KeReadStateEvent
0x14010295d  nop     dword ptr [rax+rax+00h]
0x140102962  test    eax, eax
0x140102964  jnz     loc_140102AC0
0x14010296a  mov     rcx, cs:LowPagedPoolEvent; Event
0x140102971  call    cs:__imp_KeReadStateEvent
0x140102978  nop     dword ptr [rax+rax+00h]
0x14010297d  test    eax, eax
0x14010297f  jnz     loc_140102AC0
0x140102985  movzx   eax, byte ptr [rdi+316h]
0x14010298c  test    al, al
0x14010298e  jnz     loc_140102A28
0x140102994  mov     cl, [rdi+0ACh]
0x14010299a  test    cl, cl
0x14010299c  jnz     short loc_1401029BC
0x14010299e  mov     rcx, [rsp+78h+var_28]
0x1401029a3  xor     rcx, rsp; StackCookie
0x1401029a6  call    __security_check_cookie
0x1401029ab  mov     rbx, [rsp+78h+arg_10]
0x1401029b3  add     rsp, 60h
0x1401029b7  pop     rdi
0x1401029b8  pop     rsi
0x1401029b9  pop     rbp
0x1401029ba  retn
0x1401029bc  mov     r9d, [rdi+0A0h]
0x1401029c3  lea     r10, TcpBackLogRange
0x1401029ca  mov     r8b, bpl
0x1401029cd  movzx   eax, cl
0x1401029d0  mov     edx, [r10+rax*4-4]
0x1401029d5  cmp     cl, 2
0x1401029d8  jb      short loc_1401029E2
0x1401029da  movzx   eax, cl
0x1401029dd  add     edx, [r10+rax*4-8]
0x1401029e2  shr     edx, 1
0x1401029e4  cmp     r9d, edx
0x1401029e7  jb      loc_140102AA9
0x1401029ed  test    r8b, r8b
0x1401029f0  jz      short loc_14010299E
0x1401029f2  cmp     cs:dword_1402201D4, ebp
0x1401029f8  jz      short loc_140102A14
0x1401029fa  cmp     cs:TcpipTraceFiltersExist, bpl
0x140102a01  jnz     loc_140102AEC
0x140102a07  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 10h
0x140102a0e  jnz     loc_1401D1D06
0x140102a14  bts     dword ptr [rdi+78h], 0Fh
0x140102a19  mov     edx, esi
0x140102a1b  mov     rcx, rdi
0x140102a1e  call    TcpTcbDelay
0x140102a23  jmp     loc_14010299E
0x140102a28  shl     eax, 0Ah
0x140102a2b  neg     eax
0x140102a2d  and     eax, [rdi+0A0h]
0x140102a33  cmp     [rdi+0A8h], eax
0x140102a39  jbe     loc_14010299E
0x140102a3f  mov     [rdi+0A8h], eax
0x140102a45  jmp     short loc_1401029F2
0x140102a47  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredContext; Event
0x140102a4e  call    cs:__imp_KeReadStateEvent
0x140102a55  nop     dword ptr [rax+rax+00h]
0x140102a5a  test    eax, eax
0x140102a5c  jz      loc_140102985
0x140102a62  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+18h; Event
0x140102a69  call    cs:__imp_KeReadStateEvent
0x140102a70  nop     dword ptr [rax+rax+00h]
0x140102a75  test    eax, eax
0x140102a77  jz      loc_140102985
0x140102a7d  cmp     cs:dword_1402201D4, ebp
0x140102a83  jz      loc_1401D1C8C
0x140102a89  cmp     cs:TcpipTraceFiltersExist, bpl
0x140102a90  jz      loc_1401D1C2A
0x140102a96  mov     al, [rdi+324h]
0x140102a9c  test    al, al
0x140102a9e  js      loc_1401D1C2A
0x140102aa4  jmp     loc_1401D1C8C
0x140102aa9  sub     cl, 1
0x140102aac  mov     r8b, 1
0x140102aaf  mov     [rdi+0ACh], cl
0x140102ab5  jz      loc_1401029ED
0x140102abb  jmp     loc_1401029CD
0x140102ac0  cmp     cs:dword_1402201D4, ebp
0x140102ac6  jz      loc_1401D1CFA
0x140102acc  cmp     cs:TcpipTraceFiltersExist, bpl
0x140102ad3  jz      loc_1401D1C98
0x140102ad9  mov     al, [rdi+324h]
0x140102adf  test    al, al
0x140102ae1  js      loc_1401D1C98
0x140102ae7  jmp     loc_1401D1CFA
0x140102aec  mov     al, [rdi+324h]
0x140102af2  test    al, al
0x140102af4  jns     loc_140102A14
0x140102afa  jmp     loc_140102A07
0x1401d1c2a  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+1, bpl
0x1401d1c31  jge     short loc_1401D1C8C
0x1401d1c33  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+18h; Event
0x1401d1c3a  mov     [rsp+78h+var_30], rbp
0x1401d1c3f  mov     [rsp+78h+var_38], rdi
0x1401d1c44  call    cs:__imp_KeReadStateEvent
0x1401d1c4b  nop     dword ptr [rax+rax+00h]
0x1401d1c50  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredContext; Event
0x1401d1c57  mov     ebx, eax
0x1401d1c59  call    cs:__imp_KeReadStateEvent
0x1401d1c60  nop     dword ptr [rax+rax+00h]
0x1401d1c65  mov     [rsp+78h+var_48], ebp
0x1401d1c69  lea     r8, [rsp+78h+var_38]
0x1401d1c6e  mov     r9d, eax
0x1401d1c71  mov     [rsp+78h+var_50], ebp
0x1401d1c75  lea     rdx, TCP_ISB_END_THROTTLE
0x1401d1c7c  mov     [rsp+78h+var_58], ebx
0x1401d1c80  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401d1c87  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401d1c8c  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 1
0x1401d1c93  jmp     loc_140102985
0x1401d1c98  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 1
0x1401d1c9f  jz      short loc_1401D1CFA
0x1401d1ca1  mov     rcx, cs:LowPagedPoolEvent; Event
0x1401d1ca8  mov     [rsp+78h+var_30], rbp
0x1401d1cad  mov     [rsp+78h+var_38], rdi
0x1401d1cb2  call    cs:__imp_KeReadStateEvent
0x1401d1cb9  nop     dword ptr [rax+rax+00h]
0x1401d1cbe  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; Event
0x1401d1cc5  mov     ebx, eax
0x1401d1cc7  call    cs:__imp_KeReadStateEvent
0x1401d1cce  nop     dword ptr [rax+rax+00h]
0x1401d1cd3  mov     [rsp+78h+var_48], ebx
0x1401d1cd7  lea     r8, [rsp+78h+var_38]
0x1401d1cdc  mov     [rsp+78h+var_50], eax
0x1401d1ce0  lea     rdx, TCP_ISB_BEGIN_THROTTLE
0x1401d1ce7  xor     r9d, r9d
0x1401d1cea  mov     [rsp+78h+var_58], ebp
0x1401d1cee  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401d1cf5  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401d1cfa  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, bpl
0x1401d1d01  jmp     loc_140102985
0x1401d1d06  mov     rcx, rdi
0x1401d1d09  mov     [rsp+78h+var_30], rbp
0x1401d1d0e  mov     [rsp+78h+var_38], rdi
0x1401d1d13  call    TcpComputeBacklogTcbSend
0x1401d1d18  mov     r9, rax
0x1401d1d1b  lea     r8, [rsp+78h+var_38]
0x1401d1d20  mov     eax, [rdi+0C8h]
0x1401d1d26  lea     rdx, TCP_TCB_CHANGE_ISB
0x1401d1d2d  mov     [rsp+78h+var_40], eax
0x1401d1d31  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401d1d38  mov     eax, [rdi+1C0h]
0x1401d1d3e  mov     [rsp+78h+var_48], eax
0x1401d1d42  mov     eax, [rdi+0A0h]
0x1401d1d48  mov     [rsp+78h+var_50], eax
0x1401d1d4c  mov     eax, [rdi+0C4h]
0x1401d1d52  mov     [rsp+78h+var_58], eax
0x1401d1d56  call    McTemplateK0qqqqq_EtwWriteTransfer
0x1401d1d5b  nop
0x1401d1d5c  jmp     loc_140102A14
```
