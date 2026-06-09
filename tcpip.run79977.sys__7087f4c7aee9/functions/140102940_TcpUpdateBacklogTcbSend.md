# TcpUpdateBacklogTcbSend

- ea: `0x140102940`
- end: `0x140102b1f`
- name: `TcpUpdateBacklogTcbSend`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001c1d4`

## callees

- `0x14001d5c0`
- `0x140077580`
- `0x1400d66e8`
- `0x1400d6728`
- `0x140102940`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x140102976`
- `ntoskrnl!KeReadStateEvent` at `0x140102991`
- `ntoskrnl!KeReadStateEvent` at `0x140102a6e`
- `ntoskrnl!KeReadStateEvent` at `0x140102a89`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1d84`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1d99`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1df2`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1e07`
- `ntoskrnl!KeReadStateEvent` at `0x140102976`
- `ntoskrnl!KeReadStateEvent` at `0x140102991`
- `ntoskrnl!KeReadStateEvent` at `0x140102a6e`
- `ntoskrnl!KeReadStateEvent` at `0x140102a89`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1d84`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1d99`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1df2`
- `ntoskrnl!KeReadStateEvent` at `0x1401d1e07`

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

  if ( LOBYTE(WPP_MAIN_CB.Dpc.DeferredContext) )
  {
    if ( KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)
      || KeReadStateEvent(LowPagedPoolEvent) )
    {
      if ( dword_1402201D4
        && (!TcpipTraceFiltersExist || *(char *)(a1 + 804) < 0)
        && (BYTE2(WPP_MAIN_CB.Reserved) & 1) != 0 )
      {
        v15 = 0;
        v14 = a1;
        StateEvent = KeReadStateEvent(LowPagedPoolEvent);
        v12 = KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters);
        McTemplateK0qqqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)&TCP_ISB_BEGIN_THROTTLE,
          (unsigned int)&v14,
          0,
          0,
          v12,
          StateEvent);
      }
      LOBYTE(WPP_MAIN_CB.Dpc.DeferredContext) = 0;
    }
  }
  else if ( KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredRoutine)
         && KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceContext) )
  {
    if ( dword_1402201D4 && (!TcpipTraceFiltersExist || *(char *)(a1 + 804) < 0) && SBYTE1(WPP_MAIN_CB.Reserved) < 0 )
    {
      v15 = 0;
      v14 = a1;
      v9 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceContext);
      v10 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredRoutine);
      McTemplateK0qqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)&TCP_ISB_END_THROTTLE,
        (unsigned int)&v14,
        v10,
        v9,
        0,
        0);
    }
    LOBYTE(WPP_MAIN_CB.Dpc.DeferredContext) = 1;
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
          (unsigned int)&TCP_TCB_CHANGE_ISB,
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
0x140102940  mov     [rsp+arg_10], rbx
0x140102945  push    rbp
0x140102946  push    rsi
0x140102947  push    rdi
0x140102948  sub     rsp, 60h
0x14010294c  mov     rax, cs:__security_cookie
0x140102953  xor     rax, rsp
0x140102956  mov     [rsp+78h+var_28], rax
0x14010295b  xor     ebp, ebp
0x14010295d  mov     esi, edx
0x14010295f  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, bpl
0x140102966  mov     rdi, rcx
0x140102969  jz      loc_140102A67
0x14010296f  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+28h; Event
0x140102976  call    cs:__imp_KeReadStateEvent
0x14010297d  nop     dword ptr [rax+rax+00h]
0x140102982  test    eax, eax
0x140102984  jnz     loc_140102AE0
0x14010298a  mov     rcx, cs:LowPagedPoolEvent; Event
0x140102991  call    cs:__imp_KeReadStateEvent
0x140102998  nop     dword ptr [rax+rax+00h]
0x14010299d  test    eax, eax
0x14010299f  jnz     loc_140102AE0
0x1401029a5  movzx   eax, byte ptr [rdi+316h]
0x1401029ac  test    al, al
0x1401029ae  jnz     loc_140102A48
0x1401029b4  mov     cl, [rdi+0ACh]
0x1401029ba  test    cl, cl
0x1401029bc  jnz     short loc_1401029DC
0x1401029be  mov     rcx, [rsp+78h+var_28]
0x1401029c3  xor     rcx, rsp; StackCookie
0x1401029c6  call    __security_check_cookie
0x1401029cb  mov     rbx, [rsp+78h+arg_10]
0x1401029d3  add     rsp, 60h
0x1401029d7  pop     rdi
0x1401029d8  pop     rsi
0x1401029d9  pop     rbp
0x1401029da  retn
0x1401029dc  mov     r9d, [rdi+0A0h]
0x1401029e3  lea     r10, TcpBackLogRange
0x1401029ea  mov     r8b, bpl
0x1401029ed  movzx   eax, cl
0x1401029f0  mov     edx, [r10+rax*4-4]
0x1401029f5  cmp     cl, 2
0x1401029f8  jb      short loc_140102A02
0x1401029fa  movzx   eax, cl
0x1401029fd  add     edx, [r10+rax*4-8]
0x140102a02  shr     edx, 1
0x140102a04  cmp     r9d, edx
0x140102a07  jb      loc_140102AC9
0x140102a0d  test    r8b, r8b
0x140102a10  jz      short loc_1401029BE
0x140102a12  cmp     cs:dword_1402201D4, ebp
0x140102a18  jz      short loc_140102A34
0x140102a1a  cmp     cs:TcpipTraceFiltersExist, bpl
0x140102a21  jnz     loc_140102B0C
0x140102a27  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 10h
0x140102a2e  jnz     loc_1401D1E46
0x140102a34  bts     dword ptr [rdi+78h], 0Fh
0x140102a39  mov     edx, esi
0x140102a3b  mov     rcx, rdi
0x140102a3e  call    TcpTcbDelay
0x140102a43  jmp     loc_1401029BE
0x140102a48  shl     eax, 0Ah
0x140102a4b  neg     eax
0x140102a4d  and     eax, [rdi+0A0h]
0x140102a53  cmp     [rdi+0A8h], eax
0x140102a59  jbe     loc_1401029BE
0x140102a5f  mov     [rdi+0A8h], eax
0x140102a65  jmp     short loc_140102A12
0x140102a67  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine; Event
0x140102a6e  call    cs:__imp_KeReadStateEvent
0x140102a75  nop     dword ptr [rax+rax+00h]
0x140102a7a  test    eax, eax
0x140102a7c  jz      loc_1401029A5
0x140102a82  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; Event
0x140102a89  call    cs:__imp_KeReadStateEvent
0x140102a90  nop     dword ptr [rax+rax+00h]
0x140102a95  test    eax, eax
0x140102a97  jz      loc_1401029A5
0x140102a9d  cmp     cs:dword_1402201D4, ebp
0x140102aa3  jz      loc_1401D1DCC
0x140102aa9  cmp     cs:TcpipTraceFiltersExist, bpl
0x140102ab0  jz      loc_1401D1D6A
0x140102ab6  mov     al, [rdi+324h]
0x140102abc  test    al, al
0x140102abe  js      loc_1401D1D6A
0x140102ac4  jmp     loc_1401D1DCC
0x140102ac9  sub     cl, 1
0x140102acc  mov     r8b, 1
0x140102acf  mov     [rdi+0ACh], cl
0x140102ad5  jz      loc_140102A0D
0x140102adb  jmp     loc_1401029ED
0x140102ae0  cmp     cs:dword_1402201D4, ebp
0x140102ae6  jz      loc_1401D1E3A
0x140102aec  cmp     cs:TcpipTraceFiltersExist, bpl
0x140102af3  jz      loc_1401D1DD8
0x140102af9  mov     al, [rdi+324h]
0x140102aff  test    al, al
0x140102b01  js      loc_1401D1DD8
0x140102b07  jmp     loc_1401D1E3A
0x140102b0c  mov     al, [rdi+324h]
0x140102b12  test    al, al
0x140102b14  jns     loc_140102A34
0x140102b1a  jmp     loc_140102A27
0x1401d1d6a  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+1, bpl
0x1401d1d71  jge     short loc_1401D1DCC
0x1401d1d73  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; Event
0x1401d1d7a  mov     [rsp+78h+var_30], rbp
0x1401d1d7f  mov     [rsp+78h+var_38], rdi
0x1401d1d84  call    cs:__imp_KeReadStateEvent
0x1401d1d8b  nop     dword ptr [rax+rax+00h]
0x1401d1d90  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine; Event
0x1401d1d97  mov     ebx, eax
0x1401d1d99  call    cs:__imp_KeReadStateEvent
0x1401d1da0  nop     dword ptr [rax+rax+00h]
0x1401d1da5  mov     [rsp+78h+var_48], ebp
0x1401d1da9  lea     r8, [rsp+78h+var_38]
0x1401d1dae  mov     r9d, eax
0x1401d1db1  mov     [rsp+78h+var_50], ebp
0x1401d1db5  lea     rdx, TCP_ISB_END_THROTTLE
0x1401d1dbc  mov     [rsp+78h+var_58], ebx
0x1401d1dc0  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401d1dc7  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401d1dcc  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 1
0x1401d1dd3  jmp     loc_1401029A5
0x1401d1dd8  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 1
0x1401d1ddf  jz      short loc_1401D1E3A
0x1401d1de1  mov     rcx, cs:LowPagedPoolEvent; Event
0x1401d1de8  mov     [rsp+78h+var_30], rbp
0x1401d1ded  mov     [rsp+78h+var_38], rdi
0x1401d1df2  call    cs:__imp_KeReadStateEvent
0x1401d1df9  nop     dword ptr [rax+rax+00h]
0x1401d1dfe  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+28h; Event
0x1401d1e05  mov     ebx, eax
0x1401d1e07  call    cs:__imp_KeReadStateEvent
0x1401d1e0e  nop     dword ptr [rax+rax+00h]
0x1401d1e13  mov     [rsp+78h+var_48], ebx
0x1401d1e17  lea     r8, [rsp+78h+var_38]
0x1401d1e1c  mov     [rsp+78h+var_50], eax
0x1401d1e20  lea     rdx, TCP_ISB_BEGIN_THROTTLE
0x1401d1e27  xor     r9d, r9d
0x1401d1e2a  mov     [rsp+78h+var_58], ebp
0x1401d1e2e  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401d1e35  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401d1e3a  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, bpl
0x1401d1e41  jmp     loc_1401029A5
0x1401d1e46  mov     rcx, rdi
0x1401d1e49  mov     [rsp+78h+var_30], rbp
0x1401d1e4e  mov     [rsp+78h+var_38], rdi
0x1401d1e53  call    TcpComputeBacklogTcbSend
0x1401d1e58  mov     r9, rax
0x1401d1e5b  lea     r8, [rsp+78h+var_38]
0x1401d1e60  mov     eax, [rdi+0C8h]
0x1401d1e66  lea     rdx, TCP_TCB_CHANGE_ISB
0x1401d1e6d  mov     [rsp+78h+var_40], eax
0x1401d1e71  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401d1e78  mov     eax, [rdi+1C0h]
0x1401d1e7e  mov     [rsp+78h+var_48], eax
0x1401d1e82  mov     eax, [rdi+0A0h]
0x1401d1e88  mov     [rsp+78h+var_50], eax
0x1401d1e8c  mov     eax, [rdi+0C4h]
0x1401d1e92  mov     [rsp+78h+var_58], eax
0x1401d1e96  call    McTemplateK0qqqqq_EtwWriteTransfer
0x1401d1e9b  nop
0x1401d1e9c  jmp     loc_140102A34
```
