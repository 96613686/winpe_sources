# CaptureCompleteBulk

- ea: `0x1400029a0`
- end: `0x140002f5b`
- name: `CaptureCompleteBulk`
- size: `1467`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400015b0`
- `0x140002930`

## callees

- `0x140001544`
- `0x140001a40`
- `0x1400029a0`
- `0x140002f64`
- `0x1400030e0`
- `0x140012e3c`
- `0x1400135a0`
- `0x140019fc8`
- `0x14001b118`
- `0x14001b558`
- `0x14001d180`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140002c32`
- `ntoskrnl!KeSetEvent` at `0x140002dae`
- `ntoskrnl!KeSetEvent` at `0x140002c32`
- `ntoskrnl!KeSetEvent` at `0x140002dae`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140002cea`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140002e80`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140002cea`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140002e80`
- `ks!KsStreamPointerUnlock` at `0x140002b37`
- `ks!KsStreamPointerUnlock` at `0x140002ec9`
- `ks!KsStreamPointerUnlock` at `0x140002b37`
- `ks!KsStreamPointerUnlock` at `0x140002ec9`
- `ks!KsPinGetLeadingEdgeStreamPointer` at `0x140002a5d`
- `ks!KsPinGetLeadingEdgeStreamPointer` at `0x140002a5d`
- `ks!KsIncrementCountedWorker` at `0x140002e93`
- `ks!KsIncrementCountedWorker` at `0x140002e93`

## pseudocode

```c
__int64 __fastcall CaptureCompleteBulk(__int64 a1, __int64 a2, struct _LIST_ENTRY *a3)
{
  struct _KSPIN *Flink; // r15
  int v5; // r14d
  struct _LIST_ENTRY *v6; // r8
  char *Context; // rbx
  __int64 v8; // rsi
  int Flink_high; // edi
  __int64 v10; // rax
  int v11; // r12d
  int v12; // eax
  _QWORD *v13; // r14
  _DWORD *v14; // r13
  PKSSTREAM_POINTER LeadingEdgeStreamPointer; // rax
  __int64 v16; // rcx
  struct _KSSTREAM_POINTER *v17; // rdi
  int v18; // eax
  int v19; // ecx
  __int64 v20; // rdi
  int v21; // eax
  __int64 v23; // [rsp+A0h] [rbp+8h] BYREF
  int v24; // [rsp+A8h] [rbp+10h] BYREF
  PKSSTREAM_POINTER StreamPointer; // [rsp+B0h] [rbp+18h] BYREF
  PKSSTREAM_POINTER v26; // [rsp+B8h] [rbp+20h] BYREF

  v23 = a1;
  Flink = (struct _KSPIN *)a3[1].Flink;
  v5 = *(_DWORD *)(a2 + 48);
  v6 = a3[2].Flink;
  Context = (char *)Flink->Context;
  v8 = *((_QWORD *)Context + 12);
  StreamPointer = 0;
  v26 = 0;
  v24 = 0;
  LODWORD(v23) = 0;
  Flink_high = HIDWORD(v6->Flink);
  v10 = 36;
  if ( Context[440] )
    v10 = 52;
  v11 = *(_DWORD *)((char *)&v6->Flink + v10);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qdqqdD(WPP_GLOBAL_Control->AttachedDevice, 38, v6, Context, Flink->Id, a3, v6, v11, v5);
  _InterlockedDecrement((volatile signed __int32 *)Context + 9);
  if ( Flink_high )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        39,
        WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
        Context,
        a3,
        Flink_high);
    ++*(_DWORD *)(v8 + 68);
    v5 = -1073741668;
  }
  v12 = *((_DWORD *)Context + 9);
  if ( !*(_DWORD *)v8 )
  {
    if ( !v12 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          44,
          WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
          Context,
          a3,
          a3[2].Flink,
          v5);
      KeSetEvent((PRKEVENT)(Context + 128), 0, 0);
    }
LABEL_25:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        45,
        WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
        Context,
        a3,
        a3[2].Flink,
        v5);
    return 3221225494LL;
  }
  if ( !v12 )
  {
    KeSetEvent((PRKEVENT)(Context + 128), 0, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qqqD(WPP_GLOBAL_Control->AttachedDevice, 40, v6, Context, a3, a3[2].Flink, v5);
    ++*(_DWORD *)(v8 + 84);
  }
  if ( *((_DWORD *)Context + 13) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qqqD(WPP_GLOBAL_Control->AttachedDevice, 41, v6, Context, a3, a3[2].Flink, v5);
    ExInterlockedInsertTailList((PLIST_ENTRY)(v8 + 168), a3, (PKSPIN_LOCK)(v8 + 184));
    *(_DWORD *)(v8 + 24) = 0;
  }
  else
  {
    if ( v5 >= 0 )
    {
      if ( *(_DWORD *)(v8 + 8) )
      {
        *(_DWORD *)(v8 + 8) = 0;
      }
      else
      {
        v13 = Flink->Context;
        v14 = (_DWORD *)v13[12];
        LeadingEdgeStreamPointer = KsPinGetLeadingEdgeStreamPointer(Flink, KSSTREAM_POINTER_STATE_LOCKED);
        v17 = LeadingEdgeStreamPointer;
        if ( LeadingEdgeStreamPointer )
        {
          LeadingEdgeStreamPointer->StreamHeader->OptionsFlags |= 1u;
          v18 = *((_DWORD *)v13 + 6);
          if ( v18 )
          {
            if ( v18 == 2 )
              v17->StreamHeader->OptionsFlags &= ~0x100u;
          }
          else if ( *((_DWORD *)v13 + 47) )
          {
            v17->StreamHeader->OptionsFlags |= 0x100u;
            v17->StreamHeader->Duration = *((unsigned int *)v13 + 47);
          }
          if ( *((_BYTE *)v13 + 440) )
            v19 = *((_DWORD *)v17->StreamHeader->Data + 4) - *((_DWORD *)v17->StreamHeader->Data + 5);
          else
            v19 = v17->OffsetOut.Remaining - v14[13];
        }
        else
        {
          if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 4) != 0 )
            McTemplateK0_EtwWriteTransfer(v16, USBVideo_UserBufferStarvation);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_66b253ec74d53aaf8ff3b74d85196e58_Traceguids, 1);
          }
          ++v14[20];
          v19 = 0;
          v14[6] = 0;
        }
        v24 = v19;
        StreamPointer = v17;
        v20 = *(_QWORD *)(136LL * Flink->Id + *(_QWORD *)(*(_QWORD *)Context + 744LL) + 24);
        if ( v20 )
          v26 = (PKSSTREAM_POINTER)CaptureGetLeadingEdgeStreamPointer(v20, &v23, 1);
        if ( Context[440] )
          CaptureSecureBulkProcessDataPayload(
            (_DWORD)Flink,
            v20,
            (_DWORD)Context,
            (struct _LIST_ENTRY **)((char *)&a3[2].Flink[2].Flink + 4),
            HIDWORD(a3[2].Flink[3].Flink),
            (__int64)&StreamPointer,
            (__int64)&v26);
        else
          CaptureProcessDataPayload(
            (_DWORD)a3,
            (unsigned int)&StreamPointer,
            (unsigned int)&v26,
            a3[2].Blink,
            v11,
            (__int64)&v24,
            (__int64)&v23);
        if ( StreamPointer )
        {
          KsStreamPointerUnlock(StreamPointer, 0);
          StreamPointer = 0;
        }
        if ( v26 )
        {
          KsStreamPointerUnlock(v26, 0);
          v26 = 0;
        }
      }
      v21 = CaptureReQueueUrb(a3);
      v5 = v21;
      if ( v21 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return 3221225494LL;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          WPP_SF_qqqd(
            WPP_GLOBAL_Control->AttachedDevice,
            43,
            WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
            Context,
            a3,
            v8,
            v21);
      }
      goto LABEL_25;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qqqD(WPP_GLOBAL_Control->AttachedDevice, 42, v6, Context, a3, a3[2].Flink, v5);
    *((_DWORD *)Context + 13) = 1;
    *(_DWORD *)(v8 + 24) = 0;
    ExInterlockedInsertTailList((PLIST_ENTRY)(v8 + 168), a3, (PKSPIN_LOCK)(v8 + 184));
    KsIncrementCountedWorker(*(PKSWORKER *)(v8 + 208));
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400029a0  mov     rax, rsp
0x1400029a3  mov     [rax+8], rcx
0x1400029a7  push    rbx
0x1400029a8  push    rbp
0x1400029a9  push    rsi
0x1400029aa  push    rdi
0x1400029ab  push    r12
0x1400029ad  push    r13
0x1400029af  push    r14
0x1400029b1  push    r15
0x1400029b3  sub     rsp, 58h
0x1400029b7  mov     r15, [r8+10h]
0x1400029bb  mov     rbp, r8
0x1400029be  mov     r14d, [rdx+30h]
0x1400029c2  xor     edx, edx
0x1400029c4  mov     r8, [r8+20h]
0x1400029c8  mov     rbx, [r15+10h]
0x1400029cc  mov     rsi, [rbx+60h]
0x1400029d0  mov     [rax+18h], rdx
0x1400029d4  mov     [rax+20h], rdx
0x1400029d8  mov     [rax+10h], edx
0x1400029db  mov     [rax+8], edx
0x1400029de  cmp     [rbx+1B8h], dl
0x1400029e4  lea     r13, WPP_GLOBAL_Control
0x1400029eb  mov     edi, [r8+4]
0x1400029ef  mov     ecx, 34h ; '4'
0x1400029f4  mov     eax, 24h ; '$'
0x1400029f9  cmovnz  eax, ecx
0x1400029fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a03  mov     r12d, [rax+r8]
0x140002a07  cmp     rcx, r13
0x140002a0a  jnz     loc_140002BA7
0x140002a10  lock dec dword ptr [rbx+24h]
0x140002a14  test    edi, edi
0x140002a16  jnz     loc_140002D5F
0x140002a1c  cmp     dword ptr [rsi], 0
0x140002a1f  mov     eax, [rbx+24h]
0x140002a22  jz      loc_140002BE5
0x140002a28  test    eax, eax
0x140002a2a  jz      loc_140002DA2
0x140002a30  cmp     dword ptr [rbx+34h], 0
0x140002a34  jnz     loc_140002CC9
0x140002a3a  test    r14d, r14d
0x140002a3d  js      loc_140002E2D
0x140002a43  cmp     dword ptr [rsi+8], 0
0x140002a47  jnz     loc_140002C7F
0x140002a4d  mov     r14, [r15+10h]
0x140002a51  mov     edx, 1; State
0x140002a56  mov     rcx, r15; Pin
0x140002a59  mov     r13, [r14+60h]
0x140002a5d  call    cs:__imp_KsPinGetLeadingEdgeStreamPointer
0x140002a64  nop     dword ptr [rax+rax+00h]
0x140002a69  mov     rdi, rax
0x140002a6c  test    rax, rax
0x140002a6f  jz      loc_140002D02
0x140002a75  mov     rax, [rax+10h]
0x140002a79  or      dword ptr [rax+30h], 1
0x140002a7d  mov     eax, [r14+18h]
0x140002a81  test    eax, eax
0x140002a83  jz      loc_140002C9C
0x140002a89  cmp     eax, 2
0x140002a8c  jnz     short loc_140002A99
0x140002a8e  mov     rax, [rdi+10h]
0x140002a92  and     dword ptr [rax+30h], 0FFFFFEFFh
0x140002a99  cmp     byte ptr [r14+1B8h], 0
0x140002aa1  jnz     loc_140002C87
0x140002aa7  mov     ecx, [rdi+3Ch]
0x140002aaa  sub     ecx, [r13+34h]
0x140002aae  mov     [rsp+98h+arg_8], ecx
0x140002ab5  mov     [rsp+98h+StreamPointer], rdi
0x140002abd  mov     eax, [r15+18h]
0x140002ac1  imul    rdx, rax, 88h
0x140002ac8  mov     rax, [rbx]
0x140002acb  mov     rcx, [rax+2E8h]
0x140002ad2  mov     rdi, [rdx+rcx+18h]
0x140002ad7  test    rdi, rdi
0x140002ada  jnz     loc_140002EA4
0x140002ae0  cmp     byte ptr [rbx+1B8h], 0
0x140002ae7  jnz     loc_140002C43
0x140002aed  mov     r9, [rbp+28h]
0x140002af1  lea     rax, [rsp+98h+arg_0]
0x140002af9  mov     [rsp+98h+var_68], rax
0x140002afe  lea     r8, [rsp+98h+arg_18]
0x140002b06  lea     rax, [rsp+98h+arg_8]
0x140002b0e  mov     rcx, rbp
0x140002b11  mov     [rsp+98h+var_70], rax
0x140002b16  lea     rdx, [rsp+98h+StreamPointer]
0x140002b1e  mov     dword ptr [rsp+98h+var_78], r12d
0x140002b23  call    CaptureProcessDataPayload
0x140002b28  mov     rcx, [rsp+98h+StreamPointer]; StreamPointer
0x140002b30  test    rcx, rcx
0x140002b33  jz      short loc_140002B4F
0x140002b35  xor     edx, edx; Eject
0x140002b37  call    cs:__imp_KsStreamPointerUnlock
0x140002b3e  nop     dword ptr [rax+rax+00h]
0x140002b43  mov     [rsp+98h+StreamPointer], 0
0x140002b4f  mov     rcx, [rsp+98h+arg_18]; StreamPointer
0x140002b57  test    rcx, rcx
0x140002b5a  jnz     loc_140002EC7
0x140002b60  lea     r13, WPP_GLOBAL_Control
0x140002b67  mov     rcx, rbp
0x140002b6a  call    CaptureReQueueUrb
0x140002b6f  mov     r14d, eax
0x140002b72  test    eax, eax
0x140002b74  js      loc_140002EE6
0x140002b7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b81  cmp     rcx, r13
0x140002b84  jz      short loc_140002B90
0x140002b86  cmp     byte ptr [rcx+29h], 5
0x140002b8a  jnb     loc_140002F2B
0x140002b90  mov     eax, 0C0000016h
0x140002b95  add     rsp, 58h
0x140002b99  pop     r15
0x140002b9b  pop     r14
0x140002b9d  pop     r13
0x140002b9f  pop     r12
0x140002ba1  pop     rdi
0x140002ba2  pop     rsi
0x140002ba3  pop     rbp
0x140002ba4  pop     rbx
0x140002ba5  retn
0x140002ba7  cmp     byte ptr [rcx+29h], 5
0x140002bab  jb      loc_140002A10
0x140002bb1  mov     eax, [r15+18h]
0x140002bb5  mov     edx, 26h ; '&'
0x140002bba  mov     rcx, [rcx+18h]
0x140002bbe  mov     r9, rbx
0x140002bc1  mov     [rsp+98h+var_58], r14d
0x140002bc6  mov     [rsp+98h+var_60], r12d
0x140002bcb  mov     [rsp+98h+var_68], r8
0x140002bd0  mov     [rsp+98h+var_70], rbp
0x140002bd5  mov     dword ptr [rsp+98h+var_78], eax
0x140002bd9  call    WPP_SF_qdqqdD
0x140002bde  xor     edx, edx
0x140002be0  jmp     loc_140002A10
0x140002be5  test    eax, eax
0x140002be7  jnz     short loc_140002B7A
0x140002be9  mov     rcx, cs:WPP_GLOBAL_Control
0x140002bf0  cmp     rcx, r13
0x140002bf3  jz      short loc_140002C26
0x140002bf5  cmp     byte ptr [rcx+29h], 5
0x140002bf9  jb      short loc_140002C26
0x140002bfb  mov     rax, [rbp+20h]
0x140002bff  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x140002c06  mov     rcx, [rcx+18h]
0x140002c0a  mov     edx, 2Ch ; ','
0x140002c0f  mov     dword ptr [rsp+98h+var_68], r14d
0x140002c14  mov     r9, rbx
0x140002c17  mov     [rsp+98h+var_70], rax
0x140002c1c  mov     [rsp+98h+var_78], rbp
0x140002c21  call    WPP_SF_qqqd
0x140002c26  lea     rcx, [rbx+80h]; Event
0x140002c2d  xor     r8d, r8d; Wait
0x140002c30  xor     edx, edx; Increment
0x140002c32  call    cs:__imp_KeSetEvent
0x140002c39  nop     dword ptr [rax+rax+00h]
0x140002c3e  jmp     loc_140002B7A
0x140002c43  mov     rax, [rbp+20h]
0x140002c47  lea     rcx, [rsp+98h+arg_18]
0x140002c4f  mov     [rsp+98h+var_68], rcx
0x140002c54  mov     r8, rbx
0x140002c57  lea     rcx, [rsp+98h+StreamPointer]
0x140002c5f  mov     rdx, rdi
0x140002c62  mov     [rsp+98h+var_70], rcx
0x140002c67  mov     rcx, r15
0x140002c6a  lea     r9, [rax+24h]
0x140002c6e  mov     eax, [rax+34h]
0x140002c71  mov     dword ptr [rsp+98h+var_78], eax
0x140002c75  call    CaptureSecureBulkProcessDataPayload
0x140002c7a  jmp     loc_140002B28
0x140002c7f  mov     [rsi+8], edx
0x140002c82  jmp     loc_140002B67
0x140002c87  mov     rax, [rdi+10h]
0x140002c8b  mov     rcx, [rax+28h]
0x140002c8f  mov     eax, [rcx+14h]
0x140002c92  mov     ecx, [rcx+10h]
0x140002c95  sub     ecx, eax
0x140002c97  jmp     loc_140002AAE
0x140002c9c  cmp     dword ptr [r14+0BCh], 0
0x140002ca4  jz      loc_140002A99
0x140002caa  mov     rax, [rdi+10h]
0x140002cae  or      dword ptr [rax+30h], 100h
0x140002cb5  mov     rax, [rdi+10h]
0x140002cb9  mov     ecx, [r14+0BCh]
0x140002cc0  mov     [rax+18h], rcx
0x140002cc4  jmp     loc_140002A99
0x140002cc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140002cd0  cmp     rcx, r13
0x140002cd3  jnz     loc_140002DFA
0x140002cd9  lea     r8, [rsi+0B8h]; Lock
0x140002ce0  mov     rdx, rbp; ListEntry
0x140002ce3  lea     rcx, [rsi+0A8h]; ListHead
0x140002cea  call    cs:__imp_ExInterlockedInsertTailList
0x140002cf1  nop     dword ptr [rax+rax+00h]
0x140002cf6  mov     dword ptr [rsi+18h], 0
0x140002cfd  jmp     loc_140002B90
0x140002d02  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 4
0x140002d09  jz      short loc_140002D17
0x140002d0b  lea     rdx, USBVideo_UserBufferStarvation
0x140002d12  call    McTemplateK0_EtwWriteTransfer
0x140002d17  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d1e  lea     rax, WPP_GLOBAL_Control
0x140002d25  cmp     rcx, rax
0x140002d28  jz      short loc_140002D4C
0x140002d2a  mov     eax, [rcx+2Ch]
0x140002d2d  test    al, 2
0x140002d2f  jz      short loc_140002D4C
0x140002d31  mov     rcx, [rcx+18h]
0x140002d35  lea     r8, WPP_66b253ec74d53aaf8ff3b74d85196e58_Traceguids
0x140002d3c  mov     edx, 0Ah
0x140002d41  mov     r9d, 1
0x140002d47  call    WPP_SF_d
0x140002d4c  inc     dword ptr [r13+50h]
0x140002d50  xor     ecx, ecx
0x140002d52  mov     dword ptr [r13+18h], 0
0x140002d5a  jmp     loc_140002AAE
0x140002d5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d66  cmp     rcx, r13
0x140002d69  jz      short loc_140002D94
0x140002d6b  cmp     byte ptr [rcx+29h], 3
0x140002d6f  jb      short loc_140002D94
0x140002d71  mov     rcx, [rcx+18h]
0x140002d75  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x140002d7c  mov     edx, 27h ; '''
0x140002d81  mov     dword ptr [rsp+98h+var_70], edi
0x140002d85  mov     r9, rbx
0x140002d88  mov     [rsp+98h+var_78], rbp
0x140002d8d  call    WPP_SF_qqD
0x140002d92  xor     edx, edx
0x140002d94  inc     dword ptr [rsi+44h]
0x140002d97  mov     r14d, 0C000009Ch
0x140002d9d  jmp     loc_140002A1C
0x140002da2  lea     rcx, [rbx+80h]; Event
0x140002da9  xor     r8d, r8d; Wait
0x140002dac  xor     edx, edx; Increment
0x140002dae  call    cs:__imp_KeSetEvent
0x140002db5  nop     dword ptr [rax+rax+00h]
0x140002dba  mov     rcx, cs:WPP_GLOBAL_Control
0x140002dc1  cmp     rcx, r13
0x140002dc4  jz      short loc_140002DF0
0x140002dc6  cmp     byte ptr [rcx+29h], 3
0x140002dca  jb      short loc_140002DF0
0x140002dcc  mov     rax, [rbp+20h]
0x140002dd0  mov     edx, 28h ; '('
0x140002dd5  mov     rcx, [rcx+18h]
0x140002dd9  mov     r9, rbx
0x140002ddc  mov     dword ptr [rsp+98h+var_68], r14d
0x140002de1  mov     [rsp+98h+var_70], rax
0x140002de6  mov     [rsp+98h+var_78], rbp
0x140002deb  call    WPP_SF_qqqD
0x140002df0  inc     dword ptr [rsi+54h]
0x140002df3  xor     edx, edx
0x140002df5  jmp     loc_140002A30
0x140002dfa  cmp     byte ptr [rcx+29h], 3
0x140002dfe  jb      loc_140002CD9
0x140002e04  mov     rax, [rbp+20h]
0x140002e08  mov     edx, 29h ; ')'
0x140002e0d  mov     rcx, [rcx+18h]
0x140002e11  mov     r9, rbx
0x140002e14  mov     dword ptr [rsp+98h+var_68], r14d
0x140002e19  mov     [rsp+98h+var_70], rax
0x140002e1e  mov     [rsp+98h+var_78], rbp
0x140002e23  call    WPP_SF_qqqD
0x140002e28  jmp     loc_140002CD9
0x140002e2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e34  cmp     rcx, r13
0x140002e37  jz      short loc_140002E65
0x140002e39  cmp     byte ptr [rcx+29h], 3
0x140002e3d  jb      short loc_140002E65
0x140002e3f  mov     rax, [rbp+20h]
0x140002e43  mov     edx, 2Ah ; '*'
0x140002e48  mov     rcx, [rcx+18h]
0x140002e4c  mov     r9, rbx
0x140002e4f  mov     dword ptr [rsp+98h+var_68], r14d
0x140002e54  mov     [rsp+98h+var_70], rax
0x140002e59  mov     [rsp+98h+var_78], rbp
0x140002e5e  call    WPP_SF_qqqD
0x140002e63  xor     edx, edx
0x140002e65  mov     dword ptr [rbx+34h], 1
0x140002e6c  lea     r8, [rsi+0B8h]; Lock
0x140002e73  mov     [rsi+18h], edx
0x140002e76  lea     rcx, [rsi+0A8h]; ListHead
0x140002e7d  mov     rdx, rbp; ListEntry
0x140002e80  call    cs:__imp_ExInterlockedInsertTailList
0x140002e87  nop     dword ptr [rax+rax+00h]
0x140002e8c  mov     rcx, [rsi+0D0h]; Worker
0x140002e93  call    cs:__imp_KsIncrementCountedWorker
0x140002e9a  nop     dword ptr [rax+rax+00h]
0x140002e9f  jmp     loc_140002B90
0x140002ea4  mov     r8d, 1
0x140002eaa  lea     rdx, [rsp+98h+arg_0]
0x140002eb2  mov     rcx, rdi
0x140002eb5  call    CaptureGetLeadingEdgeStreamPointer
0x140002eba  mov     [rsp+98h+arg_18], rax
0x140002ec2  jmp     loc_140002AE0
0x140002ec7  xor     edx, edx; Eject
0x140002ec9  call    cs:__imp_KsStreamPointerUnlock
0x140002ed0  nop     dword ptr [rax+rax+00h]
0x140002ed5  mov     [rsp+98h+arg_18], 0
0x140002ee1  jmp     loc_140002B60
  ... truncated ...
```
