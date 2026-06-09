# TpmTransportCommandResponse::CheckRequestPttLocalityZero(void)

- ea: `0x140003208`
- end: `0x140003350`
- name: `?CheckRequestPttLocalityZero@TpmTransportCommandResponse@@AEAAJXZ`
- size: `328`
- prototype: `__int64 __fastcall(TpmTransportCommandResponse *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140002a90`
- `0x140028630`

## callees

- `0x140002f80`
- `0x140003208`
- `0x140009278`
- `0x14001b1ac`
- `0x140039780`

## pseudocode

```c
__int64 __fastcall TpmTransportCommandResponse::CheckRequestPttLocalityZero(
        TpmTransportCommandResponse *this,
        __int64 a2,
        __int64 a3)
{
  unsigned int v4; // edx
  int v5; // ebx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // r8
  PDEVICE_OBJECT v9; // rcx
  unsigned int v10; // [rsp+30h] [rbp-18h]

  v4 = **((unsigned __int8 **)this + 42);
  if ( (v4 & 0x80u) == 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_2fc68934a9f83936555335448f322e27_Traceguids, v4);
    v5 = -1073741434;
    if ( (TPMEnableBits & 1) != 0 )
      McTemplateK0dqq_EtwWriteTransfer((__int64)v7, (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR, a3, 42, 10, 134);
  }
  else
  {
    v5 = 0;
    if ( (v4 & 2) == 0 )
    {
      *(_BYTE *)(*((_QWORD *)this + 42) + 8LL) = 1;
      v5 = (*(__int64 (__fastcall **)(TpmTransportCommandResponse *))(*(_QWORD *)this + 184LL))(this);
      if ( v5 >= 0 )
      {
        v5 = TpmTransportCommandResponse::PerformFastAndSlowHandshake(
               this,
               *((volatile unsigned int **)this + 42),
               0,
               0,
               0x82u,
               0x82u,
               v10,
               0x2EEu);
        if ( v5 < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              15,
              WPP_2fc68934a9f83936555335448f322e27_Traceguids,
              (unsigned int)v5);
          }
          v5 = -1073741434;
          if ( (TPMEnableBits & 1) != 0 )
            McTemplateK0dqq_EtwWriteTransfer(
              (__int64)v9,
              (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR,
              v8,
              42,
              41,
              134);
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140003208  mov     [rsp+arg_0], rbx
0x14000320d  push    rdi
0x14000320e  sub     rsp, 40h
0x140003212  mov     rax, [rcx+150h]
0x140003219  mov     rdi, rcx
0x14000321c  movzx   edx, byte ptr [rax]
0x14000321f  test    dl, dl
0x140003221  jns     short loc_140003238
0x140003223  xor     ebx, ebx
0x140003225  test    dl, 2
0x140003228  jz      short loc_14000328D
0x14000322a  mov     eax, ebx
0x14000322c  mov     rbx, [rsp+48h+arg_0]
0x140003231  add     rsp, 40h
0x140003235  pop     rdi
0x140003236  retn
0x140003238  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000323f  lea     rax, WPP_GLOBAL_Control
0x140003246  cmp     rcx, rax
0x140003249  jz      short loc_14000326A
0x14000324b  mov     eax, [rcx+2Ch]
0x14000324e  test    al, 1
0x140003250  jz      short loc_14000326A
0x140003252  mov     rcx, [rcx+18h]
0x140003256  lea     r8, WPP_2fc68934a9f83936555335448f322e27_Traceguids
0x14000325d  mov     r9d, edx
0x140003260  mov     edx, 0Eh
0x140003265  call    WPP_SF_d
0x14000326a  test    cs:TPMEnableBits, 1
0x140003271  mov     ebx, 0C0000186h
0x140003276  jz      short loc_14000322A
0x140003278  mov     [rsp+48h+var_20], 0C0000186h
0x140003280  mov     [rsp+48h+var_28], 10Ah
0x140003288  jmp     loc_140003339
0x14000328d  mov     rax, [rcx+150h]
0x140003294  mov     byte ptr [rax+8], 1
0x140003298  mov     rax, [rcx]
0x14000329b  mov     rax, [rax+0B8h]
0x1400032a2  call    _guard_dispatch_icall
0x1400032a7  mov     ebx, eax
0x1400032a9  test    eax, eax
0x1400032ab  js      loc_14000322A
0x1400032b1  mov     rdx, [rdi+150h]; volatile unsigned int *
0x1400032b8  mov     eax, 82h
0x1400032bd  mov     [rsp+48h+var_10], 2EEh; unsigned int
0x1400032c5  xor     r9d, r9d; unsigned int
0x1400032c8  mov     [rsp+48h+var_20], eax; unsigned int
0x1400032cc  xor     r8d, r8d; unsigned int
0x1400032cf  mov     rcx, rdi; this
0x1400032d2  mov     [rsp+48h+var_28], eax; unsigned int
0x1400032d6  call    ?PerformFastAndSlowHandshake@TpmTransportCommandResponse@@AEAAJPECIIIIIII@Z; TpmTransportCommandResponse::PerformFastAndSlowHandshake(uint volatile *,uint,uint,uint,uint,uint,uint)
0x1400032db  mov     ebx, eax
0x1400032dd  test    eax, eax
0x1400032df  jns     loc_14000322A
0x1400032e5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400032ec  lea     rax, WPP_GLOBAL_Control
0x1400032f3  cmp     rcx, rax
0x1400032f6  jz      short loc_140003317
0x1400032f8  mov     eax, [rcx+2Ch]
0x1400032fb  test    al, 1
0x1400032fd  jz      short loc_140003317
0x1400032ff  mov     rcx, [rcx+18h]
0x140003303  lea     r8, WPP_2fc68934a9f83936555335448f322e27_Traceguids
0x14000330a  mov     edx, 0Fh
0x14000330f  mov     r9d, ebx
0x140003312  call    WPP_SF_d
0x140003317  test    cs:TPMEnableBits, 1
0x14000331e  mov     ebx, 0C0000186h
0x140003323  jz      loc_14000322A
0x140003329  mov     [rsp+48h+var_20], 0C0000186h
0x140003331  mov     [rsp+48h+var_28], 129h
0x140003339  mov     r9d, 2Ah ; '*'
0x14000333f  lea     rdx, TPM_HW_PROTOCOL_ERROR
0x140003346  call    McTemplateK0dqq_EtwWriteTransfer
0x14000334b  jmp     loc_14000322A
```
