# TpmTransportCommandResponse::PrepareForSubmitCommand(void *,uint,TpmTransport::TpmTimeouts *,int)

- ea: `0x140002a90`
- end: `0x140002d79`
- name: `?PrepareForSubmitCommand@TpmTransportCommandResponse@@MEAAJPEAXIPEAVTpmTimeouts@TpmTransport@@H@Z`
- size: `745`
- prototype: `__int64 __fastcall(TpmTransportCommandResponse *__hidden this, void *, unsigned int, struct TpmTransport::TpmTimeouts *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002a90`
- `0x140003110`
- `0x140003208`
- `0x1400078b8`
- `0x140009278`
- `0x14001b1ac`
- `0x140039780`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140002bea`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002bea`

## pseudocode

```c
__int64 __fastcall TpmTransportCommandResponse::PrepareForSubmitCommand(
        TpmTransportCommandResponse *this,
        void *a2,
        __int64 a3,
        struct TpmTransport::TpmTimeouts *a4)
{
  unsigned int v5; // edi
  int v6; // edi
  volatile unsigned int *v8; // r14
  unsigned int v9; // esi
  __int64 v10; // r8
  unsigned __int64 v11; // rsi
  PDEVICE_OBJECT v12; // rcx
  PDEVICE_OBJECT v13; // rcx
  union _LARGE_INTEGER Timeout; // [rsp+60h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 39) )
    return 3221225485LL;
  if ( *((_QWORD *)this + 42) )
  {
    v6 = TpmTransportCommandResponse::CheckRequestPttLocalityZero(this);
    if ( v6 < 0 )
      goto LABEL_5;
  }
  v5 = **((_DWORD **)this + 39);
  if ( v5 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_2fc68934a9f83936555335448f322e27_Traceguids, v5);
    if ( v5 - 1 > 1 )
    {
      v6 = -1073741434;
      if ( (TPMEnableBits & 1) != 0 )
        McTemplateK0dqq_EtwWriteTransfer(
          (__int64)v12,
          (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR,
          a3,
          42,
          134,
          134);
      goto LABEL_5;
    }
    return 3221227272LL;
  }
  **((_DWORD **)this + 39) = 1;
  v6 = (*(__int64 (__fastcall **)(TpmTransportCommandResponse *, void *, __int64, struct TpmTransport::TpmTimeouts *))(*(_QWORD *)this + 176LL))(
         this,
         a2,
         a3,
         a4);
  if ( v6 >= 0 )
  {
    v8 = (volatile unsigned int *)*((_QWORD *)this + 39);
    v9 = TpmTransportCommandResponse::PerformFastHandshake(this, v8, 1u, 0xFFFFFFFF, 0, 0xFFFFFFFF, 0x64u);
    if ( v9 == 258 )
    {
      Timeout.QuadPart = 0;
      if ( v8 )
      {
        Timeout.QuadPart = -100000;
        v11 = MEMORY[0xFFFFF78000000008] + 2000000LL;
        while ( 1 )
        {
          if ( !*v8 )
          {
            v9 = 0;
            goto LABEL_8;
          }
          if ( *v8 != 1 )
            break;
          KeWaitForSingleObject((char *)this + 40, Executive, 0, 0, &Timeout);
          if ( MEMORY[0xFFFFF78000000008] >= v11 )
          {
            v9 = TpmTransportCommandResponse::PerformFastHandshake(this, v8, 1u, 0xFFFFFFFF, 0, 0xFFFFFFFF, 0);
            goto LABEL_8;
          }
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_2fc68934a9f83936555335448f322e27_Traceguids);
        v9 = -1073741434;
      }
      else
      {
        v9 = -1073741811;
      }
    }
LABEL_8:
    if ( !TpmTransportType::m_TalkingToTpmSimulator || v9 != 258 )
    {
      if ( !v9 )
        return 0;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_2fc68934a9f83936555335448f322e27_Traceguids, v9);
      if ( (TPMEnableBits & 1) != 0 )
        McTemplateK0dqq_EtwWriteTransfer(
          (__int64)v13,
          (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR,
          v10,
          42,
          173,
          v9);
      if ( v9 == 258 )
        v9 = -1073741434;
      v6 = v9;
      goto LABEL_5;
    }
    **((_DWORD **)this + 39) = 0;
    return 3221227272LL;
  }
LABEL_5:
  *((_DWORD *)this + 2) = v6;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140002a90  push    rbx
0x140002a92  push    rsi
0x140002a93  sub     rsp, 48h
0x140002a97  cmp     qword ptr [rcx+138h], 0
0x140002a9f  mov     rbx, rcx
0x140002aa2  jz      loc_140002C3D
0x140002aa8  cmp     qword ptr [rcx+150h], 0
0x140002ab0  mov     [rsp+58h+arg_8], rbp
0x140002ab5  mov     [rsp+58h+arg_10], rdi
0x140002aba  mov     [rsp+58h+var_18], r15
0x140002abf  jnz     loc_140002B88
0x140002ac5  mov     rax, [rbx+138h]
0x140002acc  mov     edi, [rax]
0x140002ace  test    edi, edi
0x140002ad0  jnz     loc_140002C47
0x140002ad6  mov     rax, [rbx+138h]
0x140002add  mov     rcx, rbx
0x140002ae0  mov     dword ptr [rax], 1
0x140002ae6  mov     rax, [rbx]
0x140002ae9  mov     rax, [rax+0B0h]
0x140002af0  call    _guard_dispatch_icall
0x140002af5  mov     edi, eax
0x140002af7  test    eax, eax
0x140002af9  jns     short loc_140002B17
0x140002afb  mov     [rbx+8], edi
0x140002afe  mov     eax, edi
0x140002b00  mov     rdi, [rsp+58h+arg_10]
0x140002b05  mov     rbp, [rsp+58h+arg_8]
0x140002b0a  mov     r15, [rsp+58h+var_18]
0x140002b0f  add     rsp, 48h
0x140002b13  pop     rsi
0x140002b14  pop     rbx
0x140002b15  retn
0x140002b17  mov     [rsp+58h+var_28], 64h ; 'd'; unsigned int
0x140002b1f  xor     r15d, r15d
0x140002b22  mov     [rsp+58h+arg_18], r14
0x140002b27  mov     r9d, 0FFFFFFFFh; unsigned int
0x140002b2d  mov     r14, [rbx+138h]
0x140002b34  mov     r8d, 1; unsigned int
0x140002b3a  mov     rdx, r14; volatile unsigned int *
0x140002b3d  mov     [rsp+58h+var_30], 0FFFFFFFFh; unsigned int
0x140002b45  mov     rcx, rbx; this
0x140002b48  mov     dword ptr [rsp+58h+Timeout], r15d; unsigned int
0x140002b4d  call    ?PerformFastHandshake@TpmTransportCommandResponse@@AEAAJPECIIIIII@Z; TpmTransportCommandResponse::PerformFastHandshake(uint volatile *,uint,uint,uint,uint,uint)
0x140002b52  lea     rbp, WPP_GLOBAL_Control
0x140002b59  mov     esi, eax
0x140002b5b  mov     edi, 0C0000186h
0x140002b60  cmp     eax, 102h
0x140002b65  jz      short loc_140002B9C
0x140002b67  cmp     cs:?m_TalkingToTpmSimulator@TpmTransportType@@0HA, r15d; int TpmTransportType::m_TalkingToTpmSimulator
0x140002b6e  mov     r14, [rsp+58h+arg_18]
0x140002b73  jnz     loc_140002CF7
0x140002b79  test    esi, esi
0x140002b7b  jnz     loc_140002D17
0x140002b81  mov     eax, esi
0x140002b83  jmp     loc_140002B00
0x140002b88  call    ?CheckRequestPttLocalityZero@TpmTransportCommandResponse@@AEAAJXZ; TpmTransportCommandResponse::CheckRequestPttLocalityZero(void)
0x140002b8d  mov     edi, eax
0x140002b8f  test    eax, eax
0x140002b91  jns     loc_140002AC5
0x140002b97  jmp     loc_140002AFB
0x140002b9c  mov     qword ptr [rsp+58h+arg_0], r15
0x140002ba1  test    r14, r14
0x140002ba4  jz      loc_140002CBE
0x140002baa  mov     rax, ds:0FFFFF78000000008h
0x140002bb4  mov     qword ptr [rsp+58h+arg_0], 0FFFFFFFFFFFE7960h
0x140002bbd  lea     rsi, [rax+1E8480h]
0x140002bc4  mov     ecx, [r14]
0x140002bc7  test    ecx, ecx
0x140002bc9  jz      short loc_140002C35
0x140002bcb  cmp     ecx, 1
0x140002bce  jnz     loc_140002CC8
0x140002bd4  lea     rax, [rsp+58h+arg_0]
0x140002bd9  xor     r9d, r9d; Alertable
0x140002bdc  lea     rcx, [rbx+28h]; Object
0x140002be0  mov     [rsp+58h+Timeout], rax; Timeout
0x140002be5  xor     r8d, r8d; WaitMode
0x140002be8  xor     edx, edx; WaitReason
0x140002bea  call    cs:__imp_KeWaitForSingleObject
0x140002bf1  nop     dword ptr [rax+rax+00h]
0x140002bf6  mov     rax, ds:0FFFFF78000000008h
0x140002c00  cmp     rax, rsi
0x140002c03  jb      short loc_140002BC4
0x140002c05  mov     [rsp+58h+var_28], r15d; unsigned int
0x140002c0a  mov     r9d, 0FFFFFFFFh; unsigned int
0x140002c10  mov     [rsp+58h+var_30], 0FFFFFFFFh; unsigned int
0x140002c18  mov     r8d, 1; unsigned int
0x140002c1e  mov     rdx, r14; volatile unsigned int *
0x140002c21  mov     dword ptr [rsp+58h+Timeout], r15d; unsigned int
0x140002c26  mov     rcx, rbx; this
0x140002c29  call    ?PerformFastHandshake@TpmTransportCommandResponse@@AEAAJPECIIIIII@Z; TpmTransportCommandResponse::PerformFastHandshake(uint volatile *,uint,uint,uint,uint,uint)
0x140002c2e  mov     esi, eax
0x140002c30  jmp     loc_140002B67
0x140002c35  mov     esi, r15d
0x140002c38  jmp     loc_140002B67
0x140002c3d  mov     eax, 0C000000Dh
0x140002c42  jmp     loc_140002B0F
0x140002c47  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140002c4e  lea     rbp, WPP_GLOBAL_Control
0x140002c55  cmp     rcx, rbp
0x140002c58  jz      short loc_140002C79
0x140002c5a  mov     eax, [rcx+2Ch]
0x140002c5d  test    al, 1
0x140002c5f  jz      short loc_140002C79
0x140002c61  mov     rcx, [rcx+18h]
0x140002c65  lea     r8, WPP_2fc68934a9f83936555335448f322e27_Traceguids
0x140002c6c  mov     edx, 10h
0x140002c71  mov     r9d, edi
0x140002c74  call    WPP_SF_d
0x140002c79  lea     eax, [rdi-1]
0x140002c7c  cmp     eax, 1
0x140002c7f  jbe     loc_140002D0D
0x140002c85  test    cs:TPMEnableBits, 1
0x140002c8c  mov     edi, 0C0000186h
0x140002c91  jz      loc_140002AFB
0x140002c97  mov     [rsp+58h+var_30], 0C0000186h
0x140002c9f  lea     rdx, TPM_HW_PROTOCOL_ERROR
0x140002ca6  mov     r9d, 2Ah ; '*'
0x140002cac  mov     dword ptr [rsp+58h+Timeout], 186h
0x140002cb4  call    McTemplateK0dqq_EtwWriteTransfer
0x140002cb9  jmp     loc_140002AFB
0x140002cbe  mov     esi, 0C000000Dh
0x140002cc3  jmp     loc_140002B67
0x140002cc8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140002ccf  cmp     rcx, rbp
0x140002cd2  jz      short loc_140002CF0
0x140002cd4  mov     eax, [rcx+2Ch]
0x140002cd7  test    al, 1
0x140002cd9  jz      short loc_140002CF0
0x140002cdb  mov     rcx, [rcx+18h]
0x140002cdf  lea     r8, WPP_2fc68934a9f83936555335448f322e27_Traceguids
0x140002ce6  mov     edx, 15h
0x140002ceb  call    WPP_SF_
0x140002cf0  mov     esi, edi
0x140002cf2  jmp     loc_140002B67
0x140002cf7  cmp     esi, 102h
0x140002cfd  jnz     loc_140002B79
0x140002d03  mov     rax, [rbx+138h]
0x140002d0a  mov     [rax], r15d
0x140002d0d  mov     eax, 0C0000708h
0x140002d12  jmp     loc_140002B00
0x140002d17  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140002d1e  cmp     rcx, rbp
0x140002d21  jz      short loc_140002D42
0x140002d23  mov     eax, [rcx+2Ch]
0x140002d26  test    al, 1
0x140002d28  jz      short loc_140002D42
0x140002d2a  mov     rcx, [rcx+18h]
0x140002d2e  lea     r8, WPP_2fc68934a9f83936555335448f322e27_Traceguids
0x140002d35  mov     edx, 11h
0x140002d3a  mov     r9d, esi
0x140002d3d  call    WPP_SF_d
0x140002d42  test    cs:TPMEnableBits, 1
0x140002d49  jz      short loc_140002D69
0x140002d4b  mov     [rsp+58h+var_30], esi
0x140002d4f  lea     rdx, TPM_HW_PROTOCOL_ERROR
0x140002d56  mov     r9d, 2Ah ; '*'
0x140002d5c  mov     dword ptr [rsp+58h+Timeout], 1ADh
0x140002d64  call    McTemplateK0dqq_EtwWriteTransfer
0x140002d69  cmp     esi, 102h
0x140002d6f  cmovz   esi, edi
0x140002d72  mov     edi, esi
0x140002d74  jmp     loc_140002AFB
```
