# TpmTransportCommandResponse::OnResponseBufferAccessComplete(void)

- ea: `0x140002d80`
- end: `0x140002f73`
- name: `?OnResponseBufferAccessComplete@TpmTransportCommandResponse@@MEAAJXZ`
- size: `499`
- prototype: `__int64 __fastcall(TpmTransportCommandResponse *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140002d80`
- `0x140003110`
- `0x1400078b8`
- `0x140009278`
- `0x14001b1ac`
- `0x140039780`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140002e76`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002e76`

## pseudocode

```c
__int64 __fastcall TpmTransportCommandResponse::OnResponseBufferAccessComplete(TpmTransportCommandResponse *this)
{
  _DWORD *v1; // rax
  unsigned int v3; // ebx
  volatile unsigned int *v4; // rsi
  __int64 v5; // r8
  unsigned __int64 v7; // rbx
  PDEVICE_OBJECT v8; // rcx
  union _LARGE_INTEGER Timeout; // [rsp+60h] [rbp+8h] BYREF

  v1 = (_DWORD *)*((_QWORD *)this + 39);
  if ( v1 )
  {
    *v1 = 2;
    v3 = (*(__int64 (**)(void))(*(_QWORD *)this + 176LL))();
    if ( (v3 & 0x80000000) == 0 )
    {
      v4 = (volatile unsigned int *)*((_QWORD *)this + 39);
      v3 = TpmTransportCommandResponse::PerformFastHandshake(this, v4, 2u, 0xFFFFFFFF, 0, 0xFFFFFFFF, 0x64u);
      if ( v3 == 258 )
      {
        Timeout.QuadPart = 0;
        if ( v4 )
        {
          Timeout.QuadPart = -100000;
          v7 = MEMORY[0xFFFFF78000000008] + 2000000LL;
          while ( 1 )
          {
            if ( !*v4 )
            {
              v3 = 0;
              goto LABEL_4;
            }
            if ( *v4 != 2 )
              break;
            KeWaitForSingleObject((char *)this + 40, Executive, 0, 0, &Timeout);
            if ( MEMORY[0xFFFFF78000000008] >= v7 )
            {
              v3 = TpmTransportCommandResponse::PerformFastHandshake(this, v4, 2u, 0xFFFFFFFF, 0, 0xFFFFFFFF, 0);
              goto LABEL_4;
            }
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_2fc68934a9f83936555335448f322e27_Traceguids);
          }
          v3 = -1073741434;
        }
        else
        {
          v3 = -1073741811;
        }
      }
LABEL_4:
      if ( !v3 )
        return v3;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_2fc68934a9f83936555335448f322e27_Traceguids, v3);
      if ( (TPMEnableBits & 1) != 0 )
        McTemplateK0dqq_EtwWriteTransfer((__int64)v8, (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR, v5, 42, 63, v3);
      if ( v3 == 258 )
        v3 = -1073741434;
    }
    *((_DWORD *)this + 2) = v3;
    return v3;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140002d80  push    rbx
0x140002d82  push    rdi
0x140002d83  sub     rsp, 48h
0x140002d87  mov     rax, [rcx+138h]
0x140002d8e  mov     rdi, rcx
0x140002d91  test    rax, rax
0x140002d94  jz      loc_140002EC6
0x140002d9a  mov     dword ptr [rax], 2
0x140002da0  mov     rax, [rcx]
0x140002da3  mov     [rsp+58h+var_18], r14
0x140002da8  mov     rax, [rax+0B0h]
0x140002daf  call    _guard_dispatch_icall
0x140002db4  mov     ebx, eax
0x140002db6  test    eax, eax
0x140002db8  js      loc_140002F6B
0x140002dbe  mov     [rsp+58h+arg_8], rbp
0x140002dc3  mov     r9d, 0FFFFFFFFh; unsigned int
0x140002dc9  mov     [rsp+58h+var_28], 64h ; 'd'; unsigned int
0x140002dd1  xor     ebp, ebp
0x140002dd3  mov     [rsp+58h+arg_10], rsi
0x140002dd8  mov     r8d, 2; unsigned int
0x140002dde  mov     rsi, [rdi+138h]
0x140002de5  mov     rcx, rdi; this
0x140002de8  mov     rdx, rsi; volatile unsigned int *
0x140002deb  mov     [rsp+58h+var_30], 0FFFFFFFFh; unsigned int
0x140002df3  mov     dword ptr [rsp+58h+Timeout], ebp; unsigned int
0x140002df7  call    ?PerformFastHandshake@TpmTransportCommandResponse@@AEAAJPECIIIIII@Z; TpmTransportCommandResponse::PerformFastHandshake(uint volatile *,uint,uint,uint,uint,uint)
0x140002dfc  lea     r14, WPP_GLOBAL_Control
0x140002e03  mov     ebx, eax
0x140002e05  cmp     eax, 102h
0x140002e0a  jz      short loc_140002E2D
0x140002e0c  mov     rsi, [rsp+58h+arg_10]
0x140002e11  mov     rbp, [rsp+58h+arg_8]
0x140002e16  test    ebx, ebx
0x140002e18  jnz     loc_140002F0C
0x140002e1e  mov     r14, [rsp+58h+var_18]
0x140002e23  mov     eax, ebx
0x140002e25  add     rsp, 48h
0x140002e29  pop     rdi
0x140002e2a  pop     rbx
0x140002e2b  retn
0x140002e2d  mov     qword ptr [rsp+58h+arg_0], rbp
0x140002e32  test    rsi, rsi
0x140002e35  jz      loc_140002ED0
0x140002e3b  mov     rax, ds:0FFFFF78000000008h
0x140002e45  mov     qword ptr [rsp+58h+arg_0], 0FFFFFFFFFFFE7960h
0x140002e4e  lea     rbx, [rax+1E8480h]
0x140002e55  mov     ecx, [rsi]
0x140002e57  test    ecx, ecx
0x140002e59  jz      short loc_140002EBF
0x140002e5b  cmp     ecx, 2
0x140002e5e  jnz     short loc_140002EDA
0x140002e60  lea     rax, [rsp+58h+arg_0]
0x140002e65  xor     r9d, r9d; Alertable
0x140002e68  lea     rcx, [rdi+28h]; Object
0x140002e6c  mov     [rsp+58h+Timeout], rax; Timeout
0x140002e71  xor     r8d, r8d; WaitMode
0x140002e74  xor     edx, edx; WaitReason
0x140002e76  call    cs:__imp_KeWaitForSingleObject
0x140002e7d  nop     dword ptr [rax+rax+00h]
0x140002e82  mov     rax, ds:0FFFFF78000000008h
0x140002e8c  cmp     rax, rbx
0x140002e8f  jb      short loc_140002E55
0x140002e91  mov     [rsp+58h+var_28], ebp; unsigned int
0x140002e95  mov     r9d, 0FFFFFFFFh; unsigned int
0x140002e9b  mov     [rsp+58h+var_30], 0FFFFFFFFh; unsigned int
0x140002ea3  mov     r8d, 2; unsigned int
0x140002ea9  mov     rdx, rsi; volatile unsigned int *
0x140002eac  mov     dword ptr [rsp+58h+Timeout], ebp; unsigned int
0x140002eb0  mov     rcx, rdi; this
0x140002eb3  call    ?PerformFastHandshake@TpmTransportCommandResponse@@AEAAJPECIIIIII@Z; TpmTransportCommandResponse::PerformFastHandshake(uint volatile *,uint,uint,uint,uint,uint)
0x140002eb8  mov     ebx, eax
0x140002eba  jmp     loc_140002E0C
0x140002ebf  mov     ebx, ebp
0x140002ec1  jmp     loc_140002E0C
0x140002ec6  mov     eax, 0C000000Dh
0x140002ecb  jmp     loc_140002E25
0x140002ed0  mov     ebx, 0C000000Dh
0x140002ed5  jmp     loc_140002E0C
0x140002eda  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140002ee1  cmp     rcx, r14
0x140002ee4  jz      short loc_140002F02
0x140002ee6  mov     eax, [rcx+2Ch]
0x140002ee9  test    al, 1
0x140002eeb  jz      short loc_140002F02
0x140002eed  mov     rcx, [rcx+18h]
0x140002ef1  lea     r8, WPP_2fc68934a9f83936555335448f322e27_Traceguids
0x140002ef8  mov     edx, 15h
0x140002efd  call    WPP_SF_
0x140002f02  mov     ebx, 0C0000186h
0x140002f07  jmp     loc_140002E0C
0x140002f0c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140002f13  cmp     rcx, r14
0x140002f16  jz      short loc_140002F37
0x140002f18  mov     eax, [rcx+2Ch]
0x140002f1b  test    al, 1
0x140002f1d  jz      short loc_140002F37
0x140002f1f  mov     rcx, [rcx+18h]
0x140002f23  lea     r8, WPP_2fc68934a9f83936555335448f322e27_Traceguids
0x140002f2a  mov     edx, 13h
0x140002f2f  mov     r9d, ebx
0x140002f32  call    WPP_SF_d
0x140002f37  test    cs:TPMEnableBits, 1
0x140002f3e  jz      short loc_140002F5E
0x140002f40  mov     [rsp+58h+var_30], ebx
0x140002f44  lea     rdx, TPM_HW_PROTOCOL_ERROR
0x140002f4b  mov     r9d, 2Ah ; '*'
0x140002f51  mov     dword ptr [rsp+58h+Timeout], 23Fh
0x140002f59  call    McTemplateK0dqq_EtwWriteTransfer
0x140002f5e  cmp     ebx, 102h
0x140002f64  jnz     short loc_140002F6B
0x140002f66  mov     ebx, 0C0000186h
0x140002f6b  mov     [rdi+8], ebx
0x140002f6e  jmp     loc_140002E1E
```
