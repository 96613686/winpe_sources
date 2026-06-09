# TpmTransportCommandResponseHsp::PrepareForSubmitCommand(void *,uint,TpmTransport::TpmTimeouts *,int)

- ea: `0x1400028a0`
- end: `0x140002a7b`
- name: `?PrepareForSubmitCommand@TpmTransportCommandResponseHsp@@MEAAJPEAXIPEAVTpmTimeouts@TpmTransport@@H@Z`
- size: `475`
- prototype: `__int64 __fastcall(TpmTransportCommandResponseHsp *__hidden this, void *, unsigned int, struct TpmTransport::TpmTimeouts *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400028a0`
- `0x140002f80`
- `0x1400078b8`
- `0x140009278`
- `0x14001b1ac`

## pseudocode

```c
__int64 __fastcall TpmTransportCommandResponseHsp::PrepareForSubmitCommand(
        TpmTransportCommandResponseHsp *this,
        void *a2,
        __int64 a3,
        struct TpmTransport::TpmTimeouts *a4)
{
  TpmTransportCommandResponseHsp *v4; // rdi
  unsigned int v5; // ebx
  __int64 v6; // r8
  PDEVICE_OBJECT v7; // rcx
  PDEVICE_OBJECT v8; // rcx
  unsigned int v10; // [rsp+30h] [rbp-18h]

  v4 = this;
  if ( *((_QWORD *)this + 39)
    && *((_QWORD *)this + 68)
    && *((_QWORD *)this + 69)
    && (this = (TpmTransportCommandResponseHsp *)**((unsigned int **)this + 68), (_DWORD)this != 1) )
  {
    if ( **((_DWORD **)v4 + 69) )
    {
      **((_DWORD **)v4 + 39) = 1;
      **((_DWORD **)v4 + 68) = 1;
      v5 = TpmTransportCommandResponse::PerformFastAndSlowHandshake(
             v4,
             *((volatile unsigned int **)v4 + 68),
             1u,
             0xFFFFFFFF,
             0,
             0xFFFFFFFF,
             v10,
             0xC8u);
      if ( (v5 & 0x80000000) == 0 )
      {
        if ( **((_DWORD **)v4 + 69) != 1 )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_424eb819144b3da1c0fd8eea13590484_Traceguids, v5);
          }
          v5 = -1073741434;
          if ( (TPMEnableBits & 1) != 0 )
            McTemplateK0dqq_EtwWriteTransfer(
              (__int64)v8,
              (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR,
              v6,
              52,
              120,
              134);
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_424eb819144b3da1c0fd8eea13590484_Traceguids, v5);
        v5 = -1073741434;
        if ( (TPMEnableBits & 1) != 0 )
          McTemplateK0dqq_EtwWriteTransfer(
            (__int64)v7,
            (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR,
            v6,
            52,
            106,
            134);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_424eb819144b3da1c0fd8eea13590484_Traceguids);
      return (unsigned int)-1073740024;
    }
  }
  else
  {
    v5 = -1073741811;
    if ( (TPMEnableBits & 1) != 0 )
      McTemplateK0dqq_EtwWriteTransfer((__int64)this, (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR, a3, 52, 63, 13);
  }
  return v5;
}

```

## disassembly

```asm
0x1400028a0  mov     [rsp+arg_0], rbx
0x1400028a5  mov     [rsp+arg_8], rsi
0x1400028aa  push    rdi
0x1400028ab  sub     rsp, 40h
0x1400028af  cmp     qword ptr [rcx+138h], 0
0x1400028b7  mov     rdi, rcx
0x1400028ba  mov     esi, 1
0x1400028bf  jz      loc_140002A38
0x1400028c5  cmp     qword ptr [rcx+220h], 0
0x1400028cd  jz      loc_140002A38
0x1400028d3  cmp     qword ptr [rcx+228h], 0
0x1400028db  jz      loc_140002A38
0x1400028e1  mov     rax, [rcx+220h]
0x1400028e8  mov     ecx, [rax]
0x1400028ea  cmp     ecx, esi
0x1400028ec  jz      loc_140002A38
0x1400028f2  mov     rax, [rdi+228h]
0x1400028f9  mov     ecx, [rax]
0x1400028fb  test    ecx, ecx
0x1400028fd  jnz     short loc_140002937
0x1400028ff  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140002906  lea     rax, WPP_GLOBAL_Control
0x14000290d  cmp     rcx, rax
0x140002910  jz      short loc_14000292D
0x140002912  mov     eax, [rcx+2Ch]
0x140002915  test    sil, al
0x140002918  jz      short loc_14000292D
0x14000291a  mov     rcx, [rcx+18h]
0x14000291e  lea     edx, [rsi+0Dh]
0x140002921  lea     r8, WPP_424eb819144b3da1c0fd8eea13590484_Traceguids
0x140002928  call    WPP_SF_
0x14000292d  mov     ebx, 0C0000708h
0x140002932  jmp     loc_140002A68
0x140002937  mov     rax, [rdi+138h]
0x14000293e  or      r9d, 0FFFFFFFFh; unsigned int
0x140002942  mov     [rsp+48h+var_10], 0C8h; unsigned int
0x14000294a  mov     r8d, esi; unsigned int
0x14000294d  mov     [rsp+48h+var_20], r9d; unsigned int
0x140002952  mov     rcx, rdi; this
0x140002955  mov     [rsp+48h+var_28], 0; unsigned int
0x14000295d  mov     [rax], esi
0x14000295f  mov     rax, [rdi+220h]
0x140002966  mov     [rax], esi
0x140002968  mov     rdx, [rdi+220h]; volatile unsigned int *
0x14000296f  call    ?PerformFastAndSlowHandshake@TpmTransportCommandResponse@@AEAAJPECIIIIIII@Z; TpmTransportCommandResponse::PerformFastAndSlowHandshake(uint volatile *,uint,uint,uint,uint,uint,uint)
0x140002974  mov     ebx, eax
0x140002976  test    eax, eax
0x140002978  jns     short loc_1400029D4
0x14000297a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140002981  lea     rax, WPP_GLOBAL_Control
0x140002988  cmp     rcx, rax
0x14000298b  jz      short loc_1400029AD
0x14000298d  mov     edx, [rcx+2Ch]
0x140002990  test    sil, dl
0x140002993  jz      short loc_1400029AD
0x140002995  mov     rcx, [rcx+18h]
0x140002999  lea     r8, WPP_424eb819144b3da1c0fd8eea13590484_Traceguids
0x1400029a0  mov     edx, 0Fh
0x1400029a5  mov     r9d, ebx
0x1400029a8  call    WPP_SF_d
0x1400029ad  test    cs:TPMEnableBits, sil
0x1400029b4  mov     ebx, 0C0000186h
0x1400029b9  jz      loc_140002A68
0x1400029bf  mov     [rsp+48h+var_20], 0C0000186h
0x1400029c7  mov     [rsp+48h+var_28], 16Ah
0x1400029cf  jmp     loc_140002A56
0x1400029d4  mov     rax, [rdi+228h]
0x1400029db  mov     ecx, [rax]
0x1400029dd  cmp     ecx, esi
0x1400029df  jz      loc_140002A68
0x1400029e5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400029ec  lea     rax, WPP_GLOBAL_Control
0x1400029f3  cmp     rcx, rax
0x1400029f6  jz      short loc_140002A18
0x1400029f8  mov     eax, [rcx+2Ch]
0x1400029fb  test    sil, al
0x1400029fe  jz      short loc_140002A18
0x140002a00  mov     rcx, [rcx+18h]
0x140002a04  lea     r8, WPP_424eb819144b3da1c0fd8eea13590484_Traceguids
0x140002a0b  mov     edx, 10h
0x140002a10  mov     r9d, ebx
0x140002a13  call    WPP_SF_d
0x140002a18  test    cs:TPMEnableBits, sil
0x140002a1f  mov     ebx, 0C0000186h
0x140002a24  jz      short loc_140002A68
0x140002a26  mov     [rsp+48h+var_20], 0C0000186h
0x140002a2e  mov     [rsp+48h+var_28], 178h
0x140002a36  jmp     short loc_140002A56
0x140002a38  test    cs:TPMEnableBits, sil
0x140002a3f  mov     ebx, 0C000000Dh
0x140002a44  jz      short loc_140002A68
0x140002a46  mov     [rsp+48h+var_20], 0C000000Dh
0x140002a4e  mov     [rsp+48h+var_28], 13Fh
0x140002a56  mov     r9d, 34h ; '4'
0x140002a5c  lea     rdx, TPM_HW_PROTOCOL_ERROR
0x140002a63  call    McTemplateK0dqq_EtwWriteTransfer
0x140002a68  mov     rsi, [rsp+48h+arg_8]
0x140002a6d  mov     eax, ebx
0x140002a6f  mov     rbx, [rsp+48h+arg_0]
0x140002a74  add     rsp, 40h
0x140002a78  pop     rdi
0x140002a79  retn
```
