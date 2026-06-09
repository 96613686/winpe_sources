# HUBHTX_GetDescriptor

- ea: `0x1400046c0`
- end: `0x1400047d0`
- name: `HUBHTX_GetDescriptor`
- size: `272`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400048d8`
- `0x140008b20`
- `0x140008c60`

## callees

- `0x1400046c0`
- `0x14000686c`
- `0x140006d68`
- `0x14002e270`

## pseudocode

```c
__int64 __fastcall HUBHTX_GetDescriptor(__int64 a1, __int64 a2, int a3, char a4, int a5, char a6)
{
  char v7; // al
  __int64 v8; // rbp

  *(_WORD *)(a1 + 969) = 6;
  *(_BYTE *)(a1 + 971) = a4;
  v7 = *(_BYTE *)(a1 + 968);
  *(_WORD *)(a1 + 974) = a3;
  v8 = a2;
  *(_BYTE *)(a1 + 968) = v7 & 0x9C | (a6 != 0 ? -96 : 0x80);
  *(_WORD *)(a1 + 972) = 0;
  if ( a6 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_c(*(_QWORD *)(a1 + 2536), a2, 3, 15, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids, a4);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_cd(*(_QWORD *)(a1 + 2536), a2, a3, a4);
  }
  return HUBMISC_ControlTransfer(
           a1,
           *(_QWORD *)(a1 + 248),
           a1,
           (_QWORD *)(a1 + 816),
           (__int64)HUBHTX_HubControlTransferComplete,
           v8,
           a3,
           1,
           *(_BYTE *)(a1 + 2288));
}

```

## disassembly

```asm
0x1400046c0  push    rbx
0x1400046c2  push    rbp
0x1400046c3  push    rsi
0x1400046c4  push    rdi
0x1400046c5  sub     rsp, 58h
0x1400046c9  mov     r11b, [rsp+78h+arg_28]
0x1400046d1  mov     rsi, r8
0x1400046d4  mov     al, r11b
0x1400046d7  mov     word ptr [rcx+3C9h], 6
0x1400046e0  neg     al
0x1400046e2  mov     [rcx+3CBh], r9b
0x1400046e9  mov     al, [rcx+3C8h]
0x1400046ef  mov     dil, r9b
0x1400046f2  sbb     r10b, r10b
0x1400046f5  mov     [rcx+3CEh], si
0x1400046fc  and     r10b, 20h
0x140004700  and     al, 9Ch
0x140004702  add     r10b, 80h
0x140004706  mov     rbp, rdx
0x140004709  or      r10b, al
0x14000470c  mov     rbx, rcx
0x14000470f  xor     eax, eax
0x140004711  mov     [rcx+3C8h], r10b
0x140004718  mov     [rcx+3CCh], ax
0x14000471f  test    r11b, r11b
0x140004722  jnz     short loc_14000474F
0x140004724  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000472b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140004732  jz      short loc_140004788
0x140004734  mov     rcx, [rcx+9E8h]
0x14000473b  mov     dword ptr [rsp+78h+var_48], 0
0x140004743  mov     byte ptr [rsp+78h+var_50], r9b
0x140004748  call    WPP_RECORDER_SF_cd
0x14000474d  jmp     short loc_140004788
0x14000474f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140004756  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000475d  jz      short loc_140004788
0x14000475f  mov     rcx, [rcx+9E8h]
0x140004766  lea     rax, WPP_70469c384dd13630d566350a6f2705ad_Traceguids
0x14000476d  mov     r9d, 0Fh
0x140004773  mov     byte ptr [rsp+78h+var_50], dil
0x140004778  mov     dl, 4
0x14000477a  mov     [rsp+78h+var_58], rax
0x14000477f  lea     r8d, [r9-0Ch]
0x140004783  call    WPP_RECORDER_SF_c
0x140004788  mov     al, [rbx+8F0h]
0x14000478e  lea     r9, [rbx+330h]
0x140004795  mov     rdx, [rbx+0F8h]
0x14000479c  mov     r8, rbx
0x14000479f  mov     [rsp+78h+var_38], al
0x1400047a3  mov     rcx, rbx
0x1400047a6  mov     [rsp+78h+var_40], 1
0x1400047ab  lea     rax, HUBHTX_HubControlTransferComplete
0x1400047b2  mov     [rsp+78h+var_48], rsi
0x1400047b7  mov     [rsp+78h+var_50], rbp
0x1400047bc  mov     [rsp+78h+var_58], rax
0x1400047c1  call    HUBMISC_ControlTransfer
0x1400047c6  add     rsp, 58h
0x1400047ca  pop     rdi
0x1400047cb  pop     rsi
0x1400047cc  pop     rbp
0x1400047cd  pop     rbx
0x1400047ce  retn
```
