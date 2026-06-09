# TcpUpdateBacklogTcbSend

- ea: `0x14010ec3c`
- end: `0x14010ee1b`
- name: `TcpUpdateBacklogTcbSend`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400356d8`

## callees

- `0x140059a60`
- `0x140063720`
- `0x1400ce848`
- `0x1400ce888`
- `0x14010ec3c`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x14010ec72`
- `ntoskrnl!KeReadStateEvent` at `0x14010ec8d`
- `ntoskrnl!KeReadStateEvent` at `0x14010ed6a`
- `ntoskrnl!KeReadStateEvent` at `0x14010ed85`
- `ntoskrnl!KeReadStateEvent` at `0x1401d5ed4`
- `ntoskrnl!KeReadStateEvent` at `0x1401d5ee9`
- `ntoskrnl!KeReadStateEvent` at `0x1401d5f42`
- `ntoskrnl!KeReadStateEvent` at `0x1401d5f57`
- `ntoskrnl!KeReadStateEvent` at `0x14010ec72`
- `ntoskrnl!KeReadStateEvent` at `0x14010ec8d`
- `ntoskrnl!KeReadStateEvent` at `0x14010ed6a`
- `ntoskrnl!KeReadStateEvent` at `0x14010ed85`
- `ntoskrnl!KeReadStateEvent` at `0x1401d5ed4`
- `ntoskrnl!KeReadStateEvent` at `0x1401d5ee9`
- `ntoskrnl!KeReadStateEvent` at `0x1401d5f42`
- `ntoskrnl!KeReadStateEvent` at `0x1401d5f57`

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

  if ( BYTE4(WPP_MAIN_CB.Queue.Wcb.DeviceObject) )
  {
    if ( KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) || KeReadStateEvent(LowPagedPoolEvent) )
    {
      if ( dword_1402241D4
        && (!TcpipTraceFiltersExist || *(char *)(a1 + 804) < 0)
        && (BYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) & 1) != 0 )
      {
        v15 = 0;
        v14 = a1;
        StateEvent = KeReadStateEvent(LowPagedPoolEvent);
        v12 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
        McTemplateK0qqqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_ISB_BEGIN_THROTTLE,
          (unsigned int)&v14,
          0,
          0,
          v12,
          StateEvent);
      }
      BYTE4(WPP_MAIN_CB.Queue.Wcb.DeviceObject) = 0;
    }
  }
  else if ( KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.CurrentIrp)
         && KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels) )
  {
    if ( dword_1402241D4
      && (!TcpipTraceFiltersExist || *(char *)(a1 + 804) < 0)
      && SBYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
    {
      v15 = 0;
      v14 = a1;
      v9 = KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
      v10 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
      McTemplateK0qqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCP_ISB_END_THROTTLE,
        (unsigned int)&v14,
        v10,
        v9,
        0,
        0);
    }
    BYTE4(WPP_MAIN_CB.Queue.Wcb.DeviceObject) = 1;
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
      if ( dword_1402241D4
        && (!TcpipTraceFiltersExist || *(char *)(a1 + 804) < 0)
        && (BYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x10) != 0 )
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
0x14010ec3c  mov     [rsp+arg_10], rbx
0x14010ec41  push    rbp
0x14010ec42  push    rsi
0x14010ec43  push    rdi
0x14010ec44  sub     rsp, 60h
0x14010ec48  mov     rax, cs:__security_cookie
0x14010ec4f  xor     rax, rsp
0x14010ec52  mov     [rsp+78h+var_28], rax
0x14010ec57  xor     ebp, ebp
0x14010ec59  mov     esi, edx
0x14010ec5b  cmp     byte ptr cs:WPP_MAIN_CB.Queue+34h, bpl
0x14010ec62  mov     rdi, rcx
0x14010ec65  jz      loc_14010ED63
0x14010ec6b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+18h; Event
0x14010ec72  call    cs:__imp_KeReadStateEvent
0x14010ec79  nop     dword ptr [rax+rax+00h]
0x14010ec7e  test    eax, eax
0x14010ec80  jnz     loc_14010EDDC
0x14010ec86  mov     rcx, cs:LowPagedPoolEvent; Event
0x14010ec8d  call    cs:__imp_KeReadStateEvent
0x14010ec94  nop     dword ptr [rax+rax+00h]
0x14010ec99  test    eax, eax
0x14010ec9b  jnz     loc_14010EDDC
0x14010eca1  movzx   eax, byte ptr [rdi+316h]
0x14010eca8  test    al, al
0x14010ecaa  jnz     loc_14010ED44
0x14010ecb0  mov     cl, [rdi+0ACh]
0x14010ecb6  test    cl, cl
0x14010ecb8  jnz     short loc_14010ECD8
0x14010ecba  mov     rcx, [rsp+78h+var_28]
0x14010ecbf  xor     rcx, rsp; StackCookie
0x14010ecc2  call    __security_check_cookie
0x14010ecc7  mov     rbx, [rsp+78h+arg_10]
0x14010eccf  add     rsp, 60h
0x14010ecd3  pop     rdi
0x14010ecd4  pop     rsi
0x14010ecd5  pop     rbp
0x14010ecd6  retn
0x14010ecd8  mov     r9d, [rdi+0A0h]
0x14010ecdf  lea     r10, TcpBackLogRange
0x14010ece6  mov     r8b, bpl
0x14010ece9  movzx   eax, cl
0x14010ecec  mov     edx, [r10+rax*4-4]
0x14010ecf1  cmp     cl, 2
0x14010ecf4  jb      short loc_14010ECFE
0x14010ecf6  movzx   eax, cl
0x14010ecf9  add     edx, [r10+rax*4-8]
0x14010ecfe  shr     edx, 1
0x14010ed00  cmp     r9d, edx
0x14010ed03  jb      loc_14010EDC5
0x14010ed09  test    r8b, r8b
0x14010ed0c  jz      short loc_14010ECBA
0x14010ed0e  cmp     cs:dword_1402241D4, ebp
0x14010ed14  jz      short loc_14010ED30
0x14010ed16  cmp     cs:TcpipTraceFiltersExist, bpl
0x14010ed1d  jnz     loc_14010EE08
0x14010ed23  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+2, 10h
0x14010ed2a  jnz     loc_1401D5F96
0x14010ed30  bts     dword ptr [rdi+78h], 0Fh
0x14010ed35  mov     edx, esi
0x14010ed37  mov     rcx, rdi
0x14010ed3a  call    TcpTcbDelay
0x14010ed3f  jmp     loc_14010ECBA
0x14010ed44  shl     eax, 0Ah
0x14010ed47  neg     eax
0x14010ed49  and     eax, [rdi+0A0h]
0x14010ed4f  cmp     [rdi+0A8h], eax
0x14010ed55  jbe     loc_14010ECBA
0x14010ed5b  mov     [rdi+0A8h], eax
0x14010ed61  jmp     short loc_14010ED0E
0x14010ed63  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h; Event
0x14010ed6a  call    cs:__imp_KeReadStateEvent
0x14010ed71  nop     dword ptr [rax+rax+00h]
0x14010ed76  test    eax, eax
0x14010ed78  jz      loc_14010ECA1
0x14010ed7e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h; Event
0x14010ed85  call    cs:__imp_KeReadStateEvent
0x14010ed8c  nop     dword ptr [rax+rax+00h]
0x14010ed91  test    eax, eax
0x14010ed93  jz      loc_14010ECA1
0x14010ed99  cmp     cs:dword_1402241D4, ebp
0x14010ed9f  jz      loc_1401D5F1C
0x14010eda5  cmp     cs:TcpipTraceFiltersExist, bpl
0x14010edac  jz      loc_1401D5EBA
0x14010edb2  mov     al, [rdi+324h]
0x14010edb8  test    al, al
0x14010edba  js      loc_1401D5EBA
0x14010edc0  jmp     loc_1401D5F1C
0x14010edc5  sub     cl, 1
0x14010edc8  mov     r8b, 1
0x14010edcb  mov     [rdi+0ACh], cl
0x14010edd1  jz      loc_14010ED09
0x14010edd7  jmp     loc_14010ECE9
0x14010eddc  cmp     cs:dword_1402241D4, ebp
0x14010ede2  jz      loc_1401D5F8A
0x14010ede8  cmp     cs:TcpipTraceFiltersExist, bpl
0x14010edef  jz      loc_1401D5F28
0x14010edf5  mov     al, [rdi+324h]
0x14010edfb  test    al, al
0x14010edfd  js      loc_1401D5F28
0x14010ee03  jmp     loc_1401D5F8A
0x14010ee08  mov     al, [rdi+324h]
0x14010ee0e  test    al, al
0x14010ee10  jns     loc_14010ED30
0x14010ee16  jmp     loc_14010ED23
0x1401d5eba  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+1, bpl
0x1401d5ec1  jge     short loc_1401D5F1C
0x1401d5ec3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h; Event
0x1401d5eca  mov     [rsp+78h+var_30], rbp
0x1401d5ecf  mov     [rsp+78h+var_38], rdi
0x1401d5ed4  call    cs:__imp_KeReadStateEvent
0x1401d5edb  nop     dword ptr [rax+rax+00h]
0x1401d5ee0  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h; Event
0x1401d5ee7  mov     ebx, eax
0x1401d5ee9  call    cs:__imp_KeReadStateEvent
0x1401d5ef0  nop     dword ptr [rax+rax+00h]
0x1401d5ef5  mov     [rsp+78h+var_48], ebp
0x1401d5ef9  lea     r8, [rsp+78h+var_38]
0x1401d5efe  mov     r9d, eax
0x1401d5f01  mov     [rsp+78h+var_50], ebp
0x1401d5f05  lea     rdx, TCP_ISB_END_THROTTLE
0x1401d5f0c  mov     [rsp+78h+var_58], ebx
0x1401d5f10  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401d5f17  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401d5f1c  mov     byte ptr cs:WPP_MAIN_CB.Queue+34h, 1
0x1401d5f23  jmp     loc_14010ECA1
0x1401d5f28  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+2, 1
0x1401d5f2f  jz      short loc_1401D5F8A
0x1401d5f31  mov     rcx, cs:LowPagedPoolEvent; Event
0x1401d5f38  mov     [rsp+78h+var_30], rbp
0x1401d5f3d  mov     [rsp+78h+var_38], rdi
0x1401d5f42  call    cs:__imp_KeReadStateEvent
0x1401d5f49  nop     dword ptr [rax+rax+00h]
0x1401d5f4e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+18h; Event
0x1401d5f55  mov     ebx, eax
0x1401d5f57  call    cs:__imp_KeReadStateEvent
0x1401d5f5e  nop     dword ptr [rax+rax+00h]
0x1401d5f63  mov     [rsp+78h+var_48], ebx
0x1401d5f67  lea     r8, [rsp+78h+var_38]
0x1401d5f6c  mov     [rsp+78h+var_50], eax
0x1401d5f70  lea     rdx, TCP_ISB_BEGIN_THROTTLE
0x1401d5f77  xor     r9d, r9d
0x1401d5f7a  mov     [rsp+78h+var_58], ebp
0x1401d5f7e  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401d5f85  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401d5f8a  mov     byte ptr cs:WPP_MAIN_CB.Queue+34h, bpl
0x1401d5f91  jmp     loc_14010ECA1
0x1401d5f96  mov     rcx, rdi
0x1401d5f99  mov     [rsp+78h+var_30], rbp
0x1401d5f9e  mov     [rsp+78h+var_38], rdi
0x1401d5fa3  call    TcpComputeBacklogTcbSend
0x1401d5fa8  mov     r9, rax
0x1401d5fab  lea     r8, [rsp+78h+var_38]
0x1401d5fb0  mov     eax, [rdi+0C8h]
0x1401d5fb6  lea     rdx, TCP_TCB_CHANGE_ISB
0x1401d5fbd  mov     [rsp+78h+var_40], eax
0x1401d5fc1  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401d5fc8  mov     eax, [rdi+1C0h]
0x1401d5fce  mov     [rsp+78h+var_48], eax
0x1401d5fd2  mov     eax, [rdi+0A0h]
0x1401d5fd8  mov     [rsp+78h+var_50], eax
0x1401d5fdc  mov     eax, [rdi+0C4h]
0x1401d5fe2  mov     [rsp+78h+var_58], eax
0x1401d5fe6  call    McTemplateK0qqqqq_EtwWriteTransfer
0x1401d5feb  nop
0x1401d5fec  jmp     loc_14010ED30
```
