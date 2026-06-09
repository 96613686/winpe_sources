# HUBHTX_SetLinkStateToSSDisabledUsingControlTransfer

- ea: `0x140006038`
- end: `0x140006152`
- name: `HUBHTX_SetLinkStateToSSDisabledUsingControlTransfer`
- size: `282`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140013640`
- `0x140013670`

## callees

- `0x1400024b8`
- `0x140006038`
- `0x14002e270`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBHTX_SetLinkStateToSSDisabledUsingControlTransfer(__int64 a1)
{
  char v2; // al
  _QWORD *v3; // rdi
  __int64 result; // rax
  int v5; // [rsp+28h] [rbp-50h]
  __int64 v6; // [rsp+28h] [rbp-50h]

  v2 = *(_BYTE *)(a1 + 168) & 0x1C;
  *(_BYTE *)(a1 + 169) = 3;
  *(_WORD *)(a1 + 170) = 5;
  *(_BYTE *)(a1 + 168) = v2 | 0x23;
  *(_BYTE *)(a1 + 172) = *(_BYTE *)(a1 + 200);
  *(_WORD *)(a1 + 174) = 0;
  *(_BYTE *)(a1 + 173) = 4;
  v3 = (_QWORD *)(a1 + 1432);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v5 = *(unsigned __int16 *)(a1 + 200);
    WPP_RECORDER_SF_d(*v3, 4, 4, 120, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids, v5);
  }
  result = HUBMISC_ControlTransfer(
             *(_QWORD *)a1,
             *(_QWORD *)(*(_QWORD *)a1 + 248LL),
             a1,
             (_QWORD *)(a1 + 16),
             (__int64)HUBHTX_PortControlTransferComplete,
             0,
             0,
             0,
             *(_BYTE *)(*(_QWORD *)a1 + 2288LL));
  if ( (int)result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v6) = result;
      WPP_RECORDER_SF_d(*v3, 2, 4, 121, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids, v6);
    }
    return (*(__int64 (__fastcall **)(__int64, __int64))(a1 + 1240))(a1, 3008);
  }
  return result;
}

```

## disassembly

```asm
0x140006038  push    rbx
0x14000603a  push    rdi
0x14000603b  push    r14
0x14000603d  push    r15
0x14000603f  sub     rsp, 58h
0x140006043  mov     al, [rcx+0A8h]
0x140006049  mov     rbx, rcx
0x14000604c  and     al, 1Ch
0x14000604e  mov     byte ptr [rcx+0A9h], 3
0x140006055  or      al, 23h
0x140006057  mov     word ptr [rcx+0AAh], 5
0x140006060  mov     [rcx+0A8h], al
0x140006066  mov     al, [rcx+0C8h]
0x14000606c  mov     [rcx+0ACh], al
0x140006072  xor     eax, eax
0x140006074  mov     [rcx+0AEh], ax
0x14000607b  mov     byte ptr [rcx+0ADh], 4
0x140006082  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140006089  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140006090  lea     rdi, [rcx+598h]
0x140006097  lea     r15, WPP_70469c384dd13630d566350a6f2705ad_Traceguids
0x14000609e  jz      short loc_1400060C5
0x1400060a0  movzx   eax, word ptr [rcx+0C8h]
0x1400060a7  mov     r9d, 78h ; 'x'
0x1400060ad  mov     rcx, [rdi]
0x1400060b0  mov     dword ptr [rsp+78h+var_50], eax
0x1400060b4  mov     [rsp+78h+var_58], r15
0x1400060b9  lea     r8d, [r9-74h]
0x1400060bd  mov     dl, r8b
0x1400060c0  call    WPP_RECORDER_SF_d
0x1400060c5  mov     rcx, [rbx]
0x1400060c8  lea     r9, [rbx+10h]
0x1400060cc  mov     r8, rbx
0x1400060cf  mov     al, [rcx+8F0h]
0x1400060d5  mov     rdx, [rcx+0F8h]
0x1400060dc  mov     [rsp+78h+var_38], al
0x1400060e0  lea     rax, HUBHTX_PortControlTransferComplete
0x1400060e7  mov     [rsp+78h+var_40], 0
0x1400060ec  mov     [rsp+78h+var_48], 0
0x1400060f5  mov     [rsp+78h+var_50], 0
0x1400060fe  mov     [rsp+78h+var_58], rax
0x140006103  call    HUBMISC_ControlTransfer
0x140006108  test    eax, eax
0x14000610a  jns     short loc_140006146
0x14000610c  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140006113  jz      short loc_140006132
0x140006115  mov     rcx, [rdi]
0x140006118  mov     r9d, 79h ; 'y'
0x14000611e  mov     dword ptr [rsp+78h+var_50], eax
0x140006122  mov     dl, 2
0x140006124  mov     [rsp+78h+var_58], r15
0x140006129  lea     r8d, [r9-75h]
0x14000612d  call    WPP_RECORDER_SF_d
0x140006132  mov     rax, [rbx+4D8h]
0x140006139  mov     edx, 0BC0h
0x14000613e  mov     rcx, rbx
0x140006141  call    _guard_dispatch_icall
0x140006146  add     rsp, 58h
0x14000614a  pop     r15
0x14000614c  pop     r14
0x14000614e  pop     rdi
0x14000614f  pop     rbx
0x140006150  retn
```
