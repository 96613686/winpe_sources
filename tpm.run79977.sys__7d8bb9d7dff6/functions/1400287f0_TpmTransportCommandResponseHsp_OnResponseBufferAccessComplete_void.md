# TpmTransportCommandResponseHsp::OnResponseBufferAccessComplete(void)

- ea: `0x1400287f0`
- end: `0x140028996`
- name: `?OnResponseBufferAccessComplete@TpmTransportCommandResponseHsp@@MEAAJXZ`
- size: `422`
- prototype: `__int64 __fastcall(TpmTransportCommandResponseHsp *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140002f80`
- `0x140009278`
- `0x14001b1ac`
- `0x1400287f0`

## pseudocode

```c
__int64 __fastcall TpmTransportCommandResponseHsp::OnResponseBufferAccessComplete(
        TpmTransportCommandResponseHsp *this,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // ebx
  __int64 v4; // r8
  PDEVICE_OBJECT v5; // rcx
  PDEVICE_OBJECT v6; // rcx
  unsigned int v8; // [rsp+30h] [rbp-18h]

  if ( *((_QWORD *)this + 39) && *((_QWORD *)this + 68) && *((_QWORD *)this + 69) )
  {
    if ( **((_DWORD **)this + 68) == 1 || !**((_DWORD **)this + 69) )
    {
      v3 = -1073741434;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_424eb819144b3da1c0fd8eea13590484_Traceguids, 3221225862LL);
      if ( (TPMEnableBits & 1) != 0 )
        McTemplateK0dqq_EtwWriteTransfer((__int64)v6, (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR, a3, 52, 89, 134);
    }
    else
    {
      **((_DWORD **)this + 39) = 2;
      **((_DWORD **)this + 68) = 1;
      v3 = TpmTransportCommandResponse::PerformFastAndSlowHandshake(
             this,
             *((volatile unsigned int **)this + 68),
             1u,
             0xFFFFFFFF,
             0,
             0xFFFFFFFF,
             v8,
             0xC8u);
      if ( v3 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_424eb819144b3da1c0fd8eea13590484_Traceguids, v3);
        if ( (TPMEnableBits & 1) != 0 )
          McTemplateK0dqq_EtwWriteTransfer(
            (__int64)v5,
            (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR,
            v4,
            52,
            118,
            v3);
        if ( v3 == 258 )
          return (unsigned int)-1073741434;
      }
    }
  }
  else
  {
    v3 = -1073741811;
    if ( (TPMEnableBits & 1) != 0 )
      McTemplateK0dqq_EtwWriteTransfer((__int64)this, (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR, a3, 52, 72, 13);
  }
  return v3;
}

```

## disassembly

```asm
0x1400287f0  push    rbx
0x1400287f2  sub     rsp, 40h
0x1400287f6  cmp     qword ptr [rcx+138h], 0
0x1400287fe  mov     r10, rcx
0x140028801  jz      loc_14002895D
0x140028807  cmp     qword ptr [rcx+220h], 0
0x14002880f  jz      loc_14002895D
0x140028815  cmp     qword ptr [rcx+228h], 0
0x14002881d  jz      loc_14002895D
0x140028823  mov     rax, [rcx+220h]
0x14002882a  mov     ecx, [rax]
0x14002882c  cmp     ecx, 1
0x14002882f  jz      loc_140028908
0x140028835  mov     rax, [r10+228h]
0x14002883c  mov     ecx, [rax]
0x14002883e  test    ecx, ecx
0x140028840  jz      loc_140028908
0x140028846  mov     rax, [r10+138h]
0x14002884d  or      r9d, 0FFFFFFFFh; unsigned int
0x140028851  mov     [rsp+48h+var_10], 0C8h; unsigned int
0x140028859  mov     r8d, 1; unsigned int
0x14002885f  mov     [rsp+48h+var_20], r9d; unsigned int
0x140028864  mov     rcx, r10; this
0x140028867  mov     [rsp+48h+var_28], 0; unsigned int
0x14002886f  mov     dword ptr [rax], 2
0x140028875  mov     rax, [r10+220h]
0x14002887c  mov     dword ptr [rax], 1
0x140028882  mov     rdx, [r10+220h]; volatile unsigned int *
0x140028889  call    ?PerformFastAndSlowHandshake@TpmTransportCommandResponse@@AEAAJPECIIIIIII@Z; TpmTransportCommandResponse::PerformFastAndSlowHandshake(uint volatile *,uint,uint,uint,uint,uint,uint)
0x14002888e  mov     ebx, eax
0x140028890  test    eax, eax
0x140028892  jz      loc_14002898D
0x140028898  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002889f  lea     rax, WPP_GLOBAL_Control
0x1400288a6  cmp     rcx, rax
0x1400288a9  jz      short loc_1400288CB
0x1400288ab  mov     edx, [rcx+2Ch]
0x1400288ae  test    dl, 1
0x1400288b1  jz      short loc_1400288CB
0x1400288b3  mov     rcx, [rcx+18h]
0x1400288b7  lea     r8, WPP_424eb819144b3da1c0fd8eea13590484_Traceguids
0x1400288be  mov     edx, 13h
0x1400288c3  mov     r9d, ebx
0x1400288c6  call    WPP_SF_d
0x1400288cb  test    cs:TPMEnableBits, 1
0x1400288d2  jz      short loc_1400288F2
0x1400288d4  mov     [rsp+48h+var_20], ebx
0x1400288d8  lea     rdx, TPM_HW_PROTOCOL_ERROR
0x1400288df  mov     r9d, 34h ; '4'
0x1400288e5  mov     [rsp+48h+var_28], 276h
0x1400288ed  call    McTemplateK0dqq_EtwWriteTransfer
0x1400288f2  cmp     ebx, 102h
0x1400288f8  jnz     loc_14002898D
0x1400288fe  mov     ebx, 0C0000186h
0x140028903  jmp     loc_14002898D
0x140028908  mov     ebx, 0C0000186h
0x14002890d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028914  lea     rax, WPP_GLOBAL_Control
0x14002891b  cmp     rcx, rax
0x14002891e  jz      short loc_140028942
0x140028920  mov     eax, [rcx+2Ch]
0x140028923  test    al, 1
0x140028925  jz      short loc_140028942
0x140028927  mov     rcx, [rcx+18h]
0x14002892b  lea     r8, WPP_424eb819144b3da1c0fd8eea13590484_Traceguids
0x140028932  mov     edx, 12h
0x140028937  mov     r9d, 0C0000186h
0x14002893d  call    WPP_SF_d
0x140028942  test    cs:TPMEnableBits, 1
0x140028949  jz      short loc_14002898D
0x14002894b  mov     [rsp+48h+var_20], 0C0000186h
0x140028953  mov     [rsp+48h+var_28], 259h
0x14002895b  jmp     short loc_14002897B
0x14002895d  test    cs:TPMEnableBits, 1
0x140028964  mov     ebx, 0C000000Dh
0x140028969  jz      short loc_14002898D
0x14002896b  mov     [rsp+48h+var_20], 0C000000Dh
0x140028973  mov     [rsp+48h+var_28], 248h
0x14002897b  mov     r9d, 34h ; '4'
0x140028981  lea     rdx, TPM_HW_PROTOCOL_ERROR
0x140028988  call    McTemplateK0dqq_EtwWriteTransfer
0x14002898d  mov     eax, ebx
0x14002898f  add     rsp, 40h
0x140028993  pop     rbx
0x140028994  retn
```
