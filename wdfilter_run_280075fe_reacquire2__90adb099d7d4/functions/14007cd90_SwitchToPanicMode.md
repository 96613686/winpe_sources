# SwitchToPanicMode

- ea: `0x14007cd90`
- end: `0x14007cf05`
- name: `SwitchToPanicMode`
- size: `373`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140056dc0`
- `0x140062588`

## callees

- `0x1400018a4`
- `0x1400051bc`
- `0x14007c758`
- `0x14007cd90`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x14007ce8f`
- `ntoskrnl!KeSetTimer` at `0x14007ce8f`
- `ntoskrnl!KeCancelTimer` at `0x14007ce51`
- `ntoskrnl!KeCancelTimer` at `0x14007ce51`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14007ce6b`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14007ce6b`

## pseudocode

```c
__int64 __fastcall SwitchToPanicMode(int a1, const UNICODE_STRING *a2, int a3)
{
  __int64 result; // rax
  __int64 v7; // rbx

  result = MpData;
  if ( !*(_BYTE *)(MpData + 208) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        102,
        WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
        KeGetCurrentThread(),
        dword_1400269D4 / 0x3E8u);
    v7 = -10000LL * (unsigned int)dword_1400269D4;
    *(_BYTE *)(MpData + 208) = 1;
    ++*(_DWORD *)(MpData + 212);
    KeCancelTimer((PKTIMER)(MpData + 688));
    KeRemoveQueueDpc((PRKDPC)(MpData + 624));
    KeSetTimer((PKTIMER)(MpData + 688), (LARGE_INTEGER)v7, (PKDPC)(MpData + 624));
    result = MpSendAsyncPanicModeMessage(a1, a2, 1, 1, a3);
    if ( (int)result < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      return WPP_SF_d(
               WPP_GLOBAL_Control->AttachedDevice,
               103,
               WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
               (unsigned int)result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14007cd90  mov     rax, rsp
0x14007cd93  mov     [rax+8], rbx
0x14007cd97  mov     [rax+10h], rbp
0x14007cd9b  mov     [rax+18h], rsi
0x14007cd9f  mov     [rax+20h], rdi
0x14007cda3  push    r14
0x14007cda5  sub     rsp, 30h
0x14007cda9  mov     rax, cs:MpData
0x14007cdb0  mov     edi, r8d
0x14007cdb3  mov     rsi, rdx
0x14007cdb6  mov     ebp, ecx
0x14007cdb8  mov     r9b, [rax+0D0h]
0x14007cdbf  test    r9b, r9b
0x14007cdc2  jnz     loc_14007CEE9
0x14007cdc8  mov     rax, cs:WPP_GLOBAL_Control
0x14007cdcf  lea     r14, WPP_GLOBAL_Control
0x14007cdd6  cmp     rax, r14
0x14007cdd9  jz      short loc_14007CE1B
0x14007cddb  mov     eax, [rax+2Ch]
0x14007cdde  test    al, 1
0x14007cde0  jz      short loc_14007CE1B
0x14007cde2  mov     r9, gs:188h
0x14007cdeb  lea     r8, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids
0x14007cdf2  mov     eax, 10624DD3h
0x14007cdf7  mul     cs:dword_1400269D4
0x14007cdfd  mov     ecx, edx
0x14007cdff  mov     edx, 66h ; 'f'
0x14007ce04  shr     ecx, 6
0x14007ce07  mov     [rsp+38h+var_18], ecx
0x14007ce0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ce12  mov     rcx, [rcx+18h]
0x14007ce16  call    WPP_SF_qD
0x14007ce1b  mov     eax, cs:dword_1400269D4
0x14007ce21  imul    rbx, rax, 0FFFFFFFFFFFFD8F0h
0x14007ce28  mov     rax, cs:MpData
0x14007ce2f  mov     byte ptr [rax+0D0h], 1
0x14007ce36  mov     rax, cs:MpData
0x14007ce3d  inc     dword ptr [rax+0D4h]
0x14007ce43  mov     rcx, cs:MpData
0x14007ce4a  add     rcx, 2B0h; PKTIMER
0x14007ce51  call    cs:__imp_KeCancelTimer
0x14007ce58  nop     dword ptr [rax+rax+00h]
0x14007ce5d  mov     rcx, cs:MpData
0x14007ce64  add     rcx, 270h; Dpc
0x14007ce6b  call    cs:__imp_KeRemoveQueueDpc
0x14007ce72  nop     dword ptr [rax+rax+00h]
0x14007ce77  mov     rcx, cs:MpData
0x14007ce7e  mov     rdx, rbx; DueTime
0x14007ce81  lea     r8, [rcx+270h]; Dpc
0x14007ce88  add     rcx, 2B0h; Timer
0x14007ce8f  call    cs:__imp_KeSetTimer
0x14007ce96  nop     dword ptr [rax+rax+00h]
0x14007ce9b  mov     r9b, 1
0x14007ce9e  mov     [rsp+38h+var_18], edi
0x14007cea2  mov     r8b, r9b
0x14007cea5  mov     rdx, rsi
0x14007cea8  mov     ecx, ebp
0x14007ceaa  call    MpSendAsyncPanicModeMessage
0x14007ceaf  test    eax, eax
0x14007ceb1  jns     short loc_14007CEE9
0x14007ceb3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ceba  cmp     rcx, r14
0x14007cebd  jz      short loc_14007CEE9
0x14007cebf  mov     ecx, [rcx+2Ch]
0x14007cec2  test    cl, 1
0x14007cec5  jz      short loc_14007CEE9
0x14007cec7  lfence
0x14007ceca  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ced1  lea     r8, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids
0x14007ced8  mov     edx, 67h ; 'g'
0x14007cedd  mov     r9d, eax
0x14007cee0  mov     rcx, [rcx+18h]
0x14007cee4  call    WPP_SF_d
0x14007cee9  mov     rbx, [rsp+38h+arg_0]
0x14007ceee  mov     rbp, [rsp+38h+arg_8]
0x14007cef3  mov     rsi, [rsp+38h+arg_10]
0x14007cef8  mov     rdi, [rsp+38h+arg_18]
0x14007cefd  add     rsp, 30h
0x14007cf01  pop     r14
0x14007cf03  retn
```
