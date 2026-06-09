# TpmTransportCommandResponse::PerformFastAndSlowHandshake(uint volatile *,uint,uint,uint,uint,uint,uint)

- ea: `0x140002f80`
- end: `0x140003103`
- name: `?PerformFastAndSlowHandshake@TpmTransportCommandResponse@@AEAAJPECIIIIIII@Z`
- size: `387`
- prototype: `__int64 __fastcall(TpmTransportCommandResponse *__hidden this, volatile unsigned int *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400028a0`
- `0x140003208`
- `0x1400287f0`

## callees

- `0x140002f80`
- `0x140003110`
- `0x1400078b8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000307f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000307f`

## pseudocode

```c
__int64 __fastcall TpmTransportCommandResponse::PerformFastAndSlowHandshake(
        TpmTransportCommandResponse *this,
        volatile unsigned int *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  __int64 result; // rax
  unsigned __int64 v13; // r12
  union _LARGE_INTEGER Timeout; // [rsp+40h] [rbp-38h] BYREF

  result = TpmTransportCommandResponse::PerformFastHandshake(this, a2, a3, a4, a5, a6, 0x64u);
  if ( (_DWORD)result == 258 )
  {
    Timeout.QuadPart = 0;
    if ( a2 )
    {
      v13 = MEMORY[0xFFFFF78000000008] + 10000LL * a8;
      Timeout.QuadPart = -100000;
      while ( 1 )
      {
        if ( (a6 & *a2) == a5 )
          return 0;
        if ( (a4 & *a2) != a3 )
          break;
        if ( !a8 )
          return 258;
        KeWaitForSingleObject((char *)this + 40, Executive, 0, 0, &Timeout);
        if ( MEMORY[0xFFFFF78000000008] >= v13 )
          return TpmTransportCommandResponse::PerformFastHandshake(this, a2, a3, a4, a5, a6, 0);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_2fc68934a9f83936555335448f322e27_Traceguids);
      return 3221225862LL;
    }
    else
    {
      return 3221225485LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002f80  mov     [rsp+arg_10], rbx
0x140002f85  push    rbp
0x140002f86  push    rsi
0x140002f87  push    r13
0x140002f89  push    r14
0x140002f8b  push    r15
0x140002f8d  sub     rsp, 50h
0x140002f91  mov     r14d, [rsp+78h+arg_28]
0x140002f99  mov     esi, r9d
0x140002f9c  mov     r15d, [rsp+78h+arg_20]
0x140002fa4  mov     ebp, r8d
0x140002fa7  mov     [rsp+78h+var_48], 64h ; 'd'; unsigned int
0x140002faf  mov     rbx, rdx
0x140002fb2  mov     [rsp+78h+var_50], r14d; unsigned int
0x140002fb7  mov     r13, rcx
0x140002fba  mov     dword ptr [rsp+78h+Timeout], r15d; unsigned int
0x140002fbf  call    ?PerformFastHandshake@TpmTransportCommandResponse@@AEAAJPECIIIIII@Z; TpmTransportCommandResponse::PerformFastHandshake(uint volatile *,uint,uint,uint,uint,uint)
0x140002fc4  cmp     eax, 102h
0x140002fc9  jnz     loc_140003053
0x140002fcf  mov     qword ptr [rsp+78h+var_38], 0
0x140002fd8  test    rbx, rbx
0x140002fdb  jz      loc_1400030C3
0x140002fe1  mov     [rsp+78h+arg_0], rdi
0x140002fe9  mov     rax, 0FFFFF78000000008h
0x140002ff3  mov     edi, [rsp+78h+arg_38]
0x140002ffa  mov     [rsp+78h+arg_8], r12
0x140003002  imul    r12, rdi, 2710h
0x140003009  mov     rax, [rax]
0x14000300c  add     r12, rax
0x14000300f  mov     qword ptr [rsp+78h+var_38], 0FFFFFFFFFFFE7960h
0x140003018  nop     dword ptr [rax+rax+00000000h]
0x140003020  mov     eax, [rbx]
0x140003022  mov     ecx, eax
0x140003024  and     ecx, r14d
0x140003027  cmp     ecx, r15d
0x14000302a  jz      loc_1400030BF
0x140003030  and     eax, esi
0x140003032  cmp     eax, ebp
0x140003034  jnz     loc_1400030CA
0x14000303a  test    edi, edi
0x14000303c  jnz     short loc_140003069
0x14000303e  mov     eax, 102h
0x140003043  mov     rdi, [rsp+78h+arg_0]
0x14000304b  mov     r12, [rsp+78h+arg_8]
0x140003053  mov     rbx, [rsp+78h+arg_10]
0x14000305b  add     rsp, 50h
0x14000305f  pop     r15
0x140003061  pop     r14
0x140003063  pop     r13
0x140003065  pop     rsi
0x140003066  pop     rbp
0x140003067  retn
0x140003069  lea     rax, [rsp+78h+var_38]
0x14000306e  xor     r9d, r9d; Alertable
0x140003071  lea     rcx, [r13+28h]; Object
0x140003075  mov     [rsp+78h+Timeout], rax; Timeout
0x14000307a  xor     r8d, r8d; WaitMode
0x14000307d  xor     edx, edx; WaitReason
0x14000307f  call    cs:__imp_KeWaitForSingleObject
0x140003086  nop     dword ptr [rax+rax+00h]
0x14000308b  mov     rax, ds:0FFFFF78000000008h
0x140003095  cmp     rax, r12
0x140003098  jb      short loc_140003020
0x14000309a  mov     [rsp+78h+var_48], 0; unsigned int
0x1400030a2  mov     r9d, esi; unsigned int
0x1400030a5  mov     [rsp+78h+var_50], r14d; unsigned int
0x1400030aa  mov     r8d, ebp; unsigned int
0x1400030ad  mov     rdx, rbx; volatile unsigned int *
0x1400030b0  mov     dword ptr [rsp+78h+Timeout], r15d; unsigned int
0x1400030b5  mov     rcx, r13; this
0x1400030b8  call    ?PerformFastHandshake@TpmTransportCommandResponse@@AEAAJPECIIIIII@Z; TpmTransportCommandResponse::PerformFastHandshake(uint volatile *,uint,uint,uint,uint,uint)
0x1400030bd  jmp     short loc_140003043
0x1400030bf  xor     eax, eax
0x1400030c1  jmp     short loc_140003043
0x1400030c3  mov     eax, 0C000000Dh
0x1400030c8  jmp     short loc_140003053
0x1400030ca  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400030d1  lea     rax, WPP_GLOBAL_Control
0x1400030d8  cmp     rcx, rax
0x1400030db  jz      short loc_1400030F9
0x1400030dd  mov     eax, [rcx+2Ch]
0x1400030e0  test    al, 1
0x1400030e2  jz      short loc_1400030F9
0x1400030e4  mov     rcx, [rcx+18h]
0x1400030e8  lea     r8, WPP_2fc68934a9f83936555335448f322e27_Traceguids
0x1400030ef  mov     edx, 15h
0x1400030f4  call    WPP_SF_
0x1400030f9  mov     eax, 0C0000186h
0x1400030fe  jmp     loc_140003043
```
