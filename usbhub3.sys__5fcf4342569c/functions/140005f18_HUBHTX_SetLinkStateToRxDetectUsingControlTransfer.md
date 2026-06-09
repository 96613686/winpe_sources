# HUBHTX_SetLinkStateToRxDetectUsingControlTransfer

- ea: `0x140005f18`
- end: `0x140006032`
- name: `HUBHTX_SetLinkStateToRxDetectUsingControlTransfer`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140013820`

## callees

- `0x1400024b8`
- `0x140005f18`
- `0x14002e270`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBHTX_SetLinkStateToRxDetectUsingControlTransfer(__int64 a1)
{
  char v2; // al
  _QWORD *v3; // rdi
  __int64 result; // rax
  int v5; // [rsp+28h] [rbp-50h]
  __int64 v6; // [rsp+28h] [rbp-50h]

  v2 = *(_BYTE *)(a1 + 168) & 0x1C;
  *(_BYTE *)(a1 + 169) = 3;
  *(_BYTE *)(a1 + 168) = v2 | 0x23;
  *(_WORD *)(a1 + 170) = 5;
  *(_BYTE *)(a1 + 172) = *(_BYTE *)(a1 + 200);
  *(_WORD *)(a1 + 174) = 0;
  *(_BYTE *)(a1 + 173) = 5;
  v3 = (_QWORD *)(a1 + 1432);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v5 = *(unsigned __int16 *)(a1 + 200);
    WPP_RECORDER_SF_d(*v3, 4, 4, 122, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids, v5);
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
      WPP_RECORDER_SF_d(*v3, 2, 4, 123, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids, v6);
    }
    return (*(__int64 (__fastcall **)(__int64, __int64))(a1 + 1240))(a1, 3008);
  }
  return result;
}

```

## disassembly

```asm
0x140005f18  push    rbx
0x140005f1a  push    rdi
0x140005f1b  push    r14
0x140005f1d  push    r15
0x140005f1f  sub     rsp, 58h
0x140005f23  mov     al, [rcx+0A8h]
0x140005f29  mov     rbx, rcx
0x140005f2c  and     al, 1Ch
0x140005f2e  mov     byte ptr [rcx+0A9h], 3
0x140005f35  or      al, 23h
0x140005f37  mov     [rcx+0A8h], al
0x140005f3d  mov     ecx, 5
0x140005f42  mov     [rbx+0AAh], cx
0x140005f49  mov     al, [rbx+0C8h]
0x140005f4f  mov     [rbx+0ACh], al
0x140005f55  xor     eax, eax
0x140005f57  mov     [rbx+0AEh], ax
0x140005f5e  mov     [rbx+0ADh], cl
0x140005f64  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140005f6b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140005f72  lea     rdi, [rbx+598h]
0x140005f79  lea     r14, WPP_70469c384dd13630d566350a6f2705ad_Traceguids
0x140005f80  jz      short loc_140005FA5
0x140005f82  movzx   eax, word ptr [rbx+0C8h]
0x140005f89  lea     r8d, [rcx-1]
0x140005f8d  lea     r9d, [rcx+75h]
0x140005f91  mov     dword ptr [rsp+78h+var_50], eax
0x140005f95  mov     rcx, [rdi]
0x140005f98  mov     dl, r8b
0x140005f9b  mov     [rsp+78h+var_58], r14
0x140005fa0  call    WPP_RECORDER_SF_d
0x140005fa5  mov     rcx, [rbx]
0x140005fa8  lea     r9, [rbx+10h]
0x140005fac  mov     r8, rbx
0x140005faf  mov     al, [rcx+8F0h]
0x140005fb5  mov     rdx, [rcx+0F8h]
0x140005fbc  mov     [rsp+78h+var_38], al
0x140005fc0  lea     rax, HUBHTX_PortControlTransferComplete
0x140005fc7  mov     [rsp+78h+var_40], 0
0x140005fcc  mov     [rsp+78h+var_48], 0
0x140005fd5  mov     [rsp+78h+var_50], 0
0x140005fde  mov     [rsp+78h+var_58], rax
0x140005fe3  call    HUBMISC_ControlTransfer
0x140005fe8  test    eax, eax
0x140005fea  jns     short loc_140006026
0x140005fec  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140005ff3  jz      short loc_140006012
0x140005ff5  mov     rcx, [rdi]
0x140005ff8  mov     r9d, 7Bh ; '{'
0x140005ffe  mov     dword ptr [rsp+78h+var_50], eax
0x140006002  mov     dl, 2
0x140006004  mov     [rsp+78h+var_58], r14
0x140006009  lea     r8d, [r9-77h]
0x14000600d  call    WPP_RECORDER_SF_d
0x140006012  mov     rax, [rbx+4D8h]
0x140006019  mov     edx, 0BC0h
0x14000601e  mov     rcx, rbx
0x140006021  call    _guard_dispatch_icall
0x140006026  add     rsp, 58h
0x14000602a  pop     r15
0x14000602c  pop     r14
0x14000602e  pop     rdi
0x14000602f  pop     rbx
0x140006030  retn
```
