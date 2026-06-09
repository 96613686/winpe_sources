# HUBDTX_SendMsOs20AltEnumCommandUsingControlTransfer

- ea: `0x14002b618`
- end: `0x14002b6f6`
- name: `HUBDTX_SendMsOs20AltEnumCommandUsingControlTransfer`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140023880`

## callees

- `0x1400024b8`
- `0x14000a53c`
- `0x14002b618`
- `0x14002e270`

## pseudocode

```c
__int64 __fastcall HUBDTX_SendMsOs20AltEnumCommandUsingControlTransfer(__int64 a1)
{
  __int64 result; // rax
  int v3; // edx
  __int64 v4; // [rsp+28h] [rbp-30h]

  *(_BYTE *)(a1 + 408) = 64;
  *(_BYTE *)(a1 + 409) = *(_BYTE *)(a1 + 2060);
  *(_BYTE *)(a1 + 411) = *(_BYTE *)(a1 + 2495);
  *(_BYTE *)(a1 + 410) = 0;
  *(_DWORD *)(a1 + 412) = 8;
  result = HUBMISC_ControlTransfer(
             *(_QWORD *)a1,
             *(_QWORD *)(a1 + 24),
             a1,
             (_QWORD *)(a1 + 256),
             (__int64)HUBDTX_ControlTransferComplete,
             0,
             0,
             1,
             *(_BYTE *)(a1 + 1520));
  if ( (int)result >= 0 )
  {
    _InterlockedOr((volatile signed __int32 *)(a1 + 2476), 1u);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v4) = result;
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        v3,
        5,
        50,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
        v4);
    }
    return HUBSM_AddEvent(a1 + 512, 4004);
  }
  return result;
}

```

## disassembly

```asm
0x14002b618  push    rbx
0x14002b61a  sub     rsp, 50h
0x14002b61e  mov     byte ptr [rcx+198h], 40h ; '@'
0x14002b625  lea     r9, [rcx+100h]
0x14002b62c  mov     al, [rcx+80Ch]
0x14002b632  mov     rbx, rcx
0x14002b635  mov     [rcx+199h], al
0x14002b63b  mov     r8, rcx
0x14002b63e  mov     al, [rcx+9BFh]
0x14002b644  mov     [rcx+19Bh], al
0x14002b64a  mov     byte ptr [rcx+19Ah], 0
0x14002b651  mov     dword ptr [rcx+19Ch], 8
0x14002b65b  mov     al, [rcx+5F0h]
0x14002b661  mov     rdx, [rcx+18h]
0x14002b665  mov     rcx, [rcx]
0x14002b668  mov     [rsp+58h+var_18], al
0x14002b66c  lea     rax, HUBDTX_ControlTransferComplete
0x14002b673  mov     [rsp+58h+var_20], 1
0x14002b678  mov     [rsp+58h+var_28], 0
0x14002b681  mov     [rsp+58h+var_30], 0
0x14002b68a  mov     [rsp+58h+var_38], rax
0x14002b68f  call    HUBMISC_ControlTransfer
0x14002b694  test    eax, eax
0x14002b696  jns     short loc_14002B6E7
0x14002b698  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002b69f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002b6a6  jz      short loc_14002B6D4
0x14002b6a8  mov     rcx, [rbx+8]
0x14002b6ac  mov     r9d, 32h ; '2'
0x14002b6b2  mov     dword ptr [rsp+58h+var_30], eax
0x14002b6b6  mov     dl, 2
0x14002b6b8  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002b6bf  mov     [rsp+58h+var_38], rax
0x14002b6c4  mov     rcx, [rcx+598h]
0x14002b6cb  lea     r8d, [r9-2Dh]
0x14002b6cf  call    WPP_RECORDER_SF_d
0x14002b6d4  lea     rcx, [rbx+200h]
0x14002b6db  mov     edx, 0FA4h
0x14002b6e0  call    HUBSM_AddEvent
0x14002b6e5  jmp     short loc_14002B6EF
0x14002b6e7  lock or dword ptr [rbx+9ACh], 1
0x14002b6ef  add     rsp, 50h
0x14002b6f3  pop     rbx
0x14002b6f4  retn
```
