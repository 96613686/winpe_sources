# lbfoRemoveVmsPortInner

- ea: `0x14016ba48`
- end: `0x14016bd5d`
- name: `lbfoRemoveVmsPortInner`
- size: `789`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14015e73c`
- `0x140160b20`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x1400eadf8`
- `0x14010fa60`
- `0x14016b938`
- `0x14016ba48`
- `0x140170db8`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14016baf4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14016bb96`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14016bd2b`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14016baf4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14016bb96`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14016bd2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016bba7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016bc80`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016bd3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016bba7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016bc80`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016bd3c`

## pseudocode

```c
void __fastcall lbfoRemoveVmsPortInner(__int64 a1, __int64 a2)
{
  _QWORD **v4; // rsi
  _QWORD *v5; // rax
  _QWORD *v6; // rcx
  _QWORD *v7; // rbp
  __int64 v8; // rdx
  _QWORD *v9; // rcx
  __int64 v10; // rsi
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // r11
  __int64 v14; // rcx
  _QWORD *v15; // rdx
  __int64 v16; // rax
  int v17; // [rsp+20h] [rbp-68h]

  if ( !*(_DWORD *)(a2 + 40) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      14,
      (__int64)WPP_92be587034f338e77c3b074d1450231a_Traceguids,
      (__int64)"VmsPort->VmsPortId != NDIS_SWITCH_DEFAULT_PORT_ID");
    if ( !*(_DWORD *)(a2 + 40) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( *(_QWORD *)(a1 + 1688) == a2 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      15,
      (__int64)WPP_92be587034f338e77c3b074d1450231a_Traceguids,
      (__int64)"Team->DefaultVmsPort != VmsPort");
    if ( *(_QWORD *)(a1 + 1688) == a2 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  *(_QWORD *)(*(_QWORD *)(a2 + 80) + 10832LL) = 0;
  RtlRemoveEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 1608), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)a2, 0);
  v4 = (_QWORD **)(a2 + 48);
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == v4 )
      break;
    if ( (_QWORD **)v5[1] != v4 )
      goto LABEL_33;
    v6 = (_QWORD *)*v5;
    if ( *(_QWORD **)(*v5 + 8LL) != v5 )
      goto LABEL_33;
    *v4 = v6;
    v7 = v5 - 6;
    v6[1] = v4;
    if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_q_MAC_dd(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        23,
        16,
        (__int64)WPP_92be587034f338e77c3b074d1450231a_Traceguids,
        a1,
        (__int64)(v7 + 3),
        *((_BYTE *)v7 + 30),
        *(_DWORD *)(a2 + 40));
    RtlRemoveEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 1648), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v7, 0);
    ExFreePoolWithTag(v7, 0);
  }
  --*(_WORD *)(a1 + 1600);
  v8 = *(_QWORD *)(a2 + 24);
  if ( *(_QWORD *)(v8 + 8) != a2 + 24 )
    goto LABEL_33;
  v9 = *(_QWORD **)(a2 + 32);
  if ( *v9 != a2 + 24 )
    goto LABEL_33;
  v10 = *(_QWORD *)(a2 + 64);
  *v9 = v8;
  *(_QWORD *)(v8 + 8) = v9;
  *(_WORD *)(v10 + 80) ^= (*(_WORD *)(v10 + 80) ^ (*(_WORD *)(v10 + 80) - 1)) & 0x3FFF;
  lbfoLBUpdateCfgMacsOffloadPreferenceMasksForCfgMac(v10);
  v13 = *(_QWORD *)(v10 + 40);
  if ( v13 )
    *(_WORD *)(v13 + 730) ^= (*(_WORD *)(v13 + 730) ^ (*(_WORD *)(v13 + 730) - 1)) & 0x7FFF;
  if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_qd_MAC_d(
      WPP_GLOBAL_Control->DeviceExtension,
      *(_WORD *)(v10 + 30) & 0xFFF,
      v11,
      v12,
      v17,
      a1,
      *(_DWORD *)(a2 + 40),
      v10 + 24,
      *(_BYTE *)(v10 + 30));
  ExFreePoolWithTag((PVOID)a2, 0);
  if ( (*(_WORD *)(v10 + 80) & 0x3FFF) == 0 )
  {
    if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_q_MAC_d(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        23,
        18,
        (__int64)WPP_92be587034f338e77c3b074d1450231a_Traceguids,
        a1,
        v10 + 24,
        *(_BYTE *)(v10 + 30));
    v14 = *(_QWORD *)(v10 + 48);
    if ( *(_QWORD *)(v14 + 8) == v10 + 48 )
    {
      v15 = *(_QWORD **)(v10 + 56);
      if ( *v15 == v10 + 48 )
      {
        *v15 = v14;
        *(_QWORD *)(v14 + 8) = v15;
        v16 = *(_QWORD *)(v10 + 40);
        if ( v16 )
          --*(_WORD *)(v16 + 728);
        else
          --*(_WORD *)(a1 + 2310);
        RtlRemoveEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 1648), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v10, 0);
        ExFreePoolWithTag((PVOID)v10, 0);
        return;
      }
    }
LABEL_33:
    __fastfail(3u);
  }
}

```

## disassembly

```asm
0x14016ba48  push    rbx
0x14016ba4a  push    rbp
0x14016ba4b  push    rsi
0x14016ba4c  push    rdi
0x14016ba4d  push    r12
0x14016ba4f  push    r14
0x14016ba51  sub     rsp, 58h
0x14016ba55  xor     r14d, r14d
0x14016ba58  lea     r12, WPP_92be587034f338e77c3b074d1450231a_Traceguids
0x14016ba5f  mov     rdi, rdx
0x14016ba62  mov     rbx, rcx
0x14016ba65  mov     esi, 13h
0x14016ba6a  cmp     [rdx+28h], r14d
0x14016ba6e  jnz     short loc_14016BA9F
0x14016ba70  mov     rcx, cs:VmsIfrLog
0x14016ba77  lea     rax, aVmsportVmsport_0; "VmsPort->VmsPortId != NDIS_SWITCH_DEFAU"...
0x14016ba7e  mov     [rsp+88h+var_60], rax
0x14016ba83  lea     r9d, [rsi-5]
0x14016ba87  mov     r8d, esi
0x14016ba8a  mov     [rsp+88h+var_68], r12
0x14016ba8f  call    WPP_RECORDER_SF_s
0x14016ba94  cmp     [rdi+28h], r14d
0x14016ba98  jnz     short loc_14016BA9F
0x14016ba9a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "VmsPort->VmsPortId != 0")
0x14016ba9f  cmp     [rbx+698h], rdi
0x14016baa6  jnz     short loc_14016BADC
0x14016baa8  mov     rcx, cs:VmsIfrLog
0x14016baaf  lea     rax, aTeamDefaultvms; "Team->DefaultVmsPort != VmsPort"
0x14016bab6  mov     [rsp+88h+var_60], rax
0x14016babb  mov     r9d, 0Fh
0x14016bac1  mov     r8d, esi
0x14016bac4  mov     [rsp+88h+var_68], r12
0x14016bac9  call    WPP_RECORDER_SF_s
0x14016bace  cmp     [rbx+698h], rdi
0x14016bad5  jnz     short loc_14016BADC
0x14016bad7  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Team->DefaultVmsPort != VmsPort")
0x14016badc  mov     rax, [rdi+50h]
0x14016bae0  lea     rcx, [rbx+648h]; HashTable
0x14016bae7  xor     r8d, r8d; Context
0x14016baea  mov     rdx, rdi; Entry
0x14016baed  mov     [rax+2A50h], r14
0x14016baf4  call    cs:__imp_RtlRemoveEntryHashTable
0x14016bafb  nop     dword ptr [rax+rax+00h]
0x14016bb00  lea     rsi, [rdi+30h]
0x14016bb04  mov     rax, [rsi]
0x14016bb07  cmp     rax, rsi
0x14016bb0a  jz      loc_14016BBB8
0x14016bb10  cmp     [rax+8], rsi
0x14016bb14  jnz     loc_14016BD56
0x14016bb1a  mov     rcx, [rax]
0x14016bb1d  cmp     [rcx+8], rax
0x14016bb21  jnz     loc_14016BD56
0x14016bb27  mov     [rsi], rcx
0x14016bb2a  lea     rbp, [rax-30h]
0x14016bb2e  mov     [rcx+8], rsi
0x14016bb32  mov     rcx, cs:WPP_GLOBAL_Control
0x14016bb39  mov     al, [rcx+29h]
0x14016bb3c  dec     al
0x14016bb3e  cmp     al, 2
0x14016bb40  ja      short loc_14016BB49
0x14016bb42  cmp     [rcx+48h], r14w
0x14016bb47  jz      short loc_14016BB89
0x14016bb49  movzx   r8d, word ptr [rbp+1Eh]
0x14016bb4e  lea     rdx, [rbp+18h]
0x14016bb52  mov     eax, [rdi+28h]
0x14016bb55  and     r8d, 0FFFh
0x14016bb5c  mov     rcx, [rcx+40h]
0x14016bb60  mov     r9d, 10h
0x14016bb66  mov     [rsp+88h+var_48], eax
0x14016bb6a  mov     dword ptr [rsp+88h+var_50], r8d
0x14016bb6f  mov     [rsp+88h+var_58], rdx
0x14016bb74  xor     edx, edx
0x14016bb76  mov     [rsp+88h+var_60], rbx
0x14016bb7b  lea     r8d, [r9+7]
0x14016bb7f  mov     [rsp+88h+var_68], r12
0x14016bb84  call    WPP_RECORDER_SF_q_MAC_dd
0x14016bb89  lea     rcx, [rbx+670h]; HashTable
0x14016bb90  xor     r8d, r8d; Context
0x14016bb93  mov     rdx, rbp; Entry
0x14016bb96  call    cs:__imp_RtlRemoveEntryHashTable
0x14016bb9d  nop     dword ptr [rax+rax+00h]
0x14016bba2  xor     edx, edx; Tag
0x14016bba4  mov     rcx, rbp; P
0x14016bba7  call    cs:__imp_ExFreePoolWithTag
0x14016bbae  nop     dword ptr [rax+rax+00h]
0x14016bbb3  jmp     loc_14016BB04
0x14016bbb8  lea     rax, [rdi+18h]
0x14016bbbc  mov     ebp, 0FFFFh
0x14016bbc1  add     [rbx+640h], bp
0x14016bbc8  mov     rdx, [rax]
0x14016bbcb  cmp     [rdx+8], rax
0x14016bbcf  jnz     loc_14016BD56
0x14016bbd5  mov     rcx, [rax+8]
0x14016bbd9  cmp     [rcx], rax
0x14016bbdc  jnz     loc_14016BD56
0x14016bbe2  mov     rsi, [rdi+40h]
0x14016bbe6  mov     [rcx], rdx
0x14016bbe9  mov     [rdx+8], rcx
0x14016bbed  mov     edx, 3FFFh
0x14016bbf2  movzx   eax, word ptr [rsi+50h]
0x14016bbf6  lea     ecx, [rax-1]
0x14016bbf9  xor     cx, ax
0x14016bbfc  and     cx, dx
0x14016bbff  xor     cx, ax
0x14016bc02  mov     [rsi+50h], cx
0x14016bc06  mov     rcx, rsi
0x14016bc09  call    lbfoLBUpdateCfgMacsOffloadPreferenceMasksForCfgMac
0x14016bc0e  mov     r11, [rsi+28h]
0x14016bc12  test    r11, r11
0x14016bc15  jz      short loc_14016BC38
0x14016bc17  movzx   eax, word ptr [r11+2DAh]
0x14016bc1f  mov     edx, 7FFFh
0x14016bc24  lea     ecx, [rax-1]
0x14016bc27  xor     cx, ax
0x14016bc2a  and     cx, dx
0x14016bc2d  xor     cx, ax
0x14016bc30  mov     [r11+2DAh], cx
0x14016bc38  mov     rcx, cs:WPP_GLOBAL_Control
0x14016bc3f  mov     al, [rcx+29h]
0x14016bc42  dec     al
0x14016bc44  cmp     al, 2
0x14016bc46  ja      short loc_14016BC4F
0x14016bc48  cmp     [rcx+48h], r14w
0x14016bc4d  jz      short loc_14016BC7B
0x14016bc4f  movzx   edx, word ptr [rsi+1Eh]
0x14016bc53  lea     rax, [rsi+18h]
0x14016bc57  mov     rcx, [rcx+40h]
0x14016bc5b  and     edx, 0FFFh
0x14016bc61  mov     [rsp+88h+var_48], edx
0x14016bc65  mov     [rsp+88h+var_50], rax
0x14016bc6a  mov     eax, [rdi+28h]
0x14016bc6d  mov     dword ptr [rsp+88h+var_58], eax
0x14016bc71  mov     [rsp+88h+var_60], rbx
0x14016bc76  call    WPP_RECORDER_SF_qd_MAC_d
0x14016bc7b  xor     edx, edx; Tag
0x14016bc7d  mov     rcx, rdi; P
0x14016bc80  call    cs:__imp_ExFreePoolWithTag
0x14016bc87  nop     dword ptr [rax+rax+00h]
0x14016bc8c  mov     ecx, 3FFFh
0x14016bc91  test    [rsi+50h], cx
0x14016bc95  jnz     loc_14016BD48
0x14016bc9b  mov     rcx, cs:WPP_GLOBAL_Control
0x14016bca2  mov     al, [rcx+29h]
0x14016bca5  dec     al
0x14016bca7  cmp     al, 2
0x14016bca9  ja      short loc_14016BCB2
0x14016bcab  cmp     [rcx+48h], r14w
0x14016bcb0  jz      short loc_14016BCE8
0x14016bcb2  movzx   edx, word ptr [rsi+1Eh]
0x14016bcb6  lea     rax, [rsi+18h]
0x14016bcba  mov     rcx, [rcx+40h]
0x14016bcbe  and     edx, 0FFFh
0x14016bcc4  mov     dword ptr [rsp+88h+var_50], edx
0x14016bcc8  mov     r9d, 12h
0x14016bcce  mov     [rsp+88h+var_58], rax
0x14016bcd3  xor     edx, edx
0x14016bcd5  mov     [rsp+88h+var_60], rbx
0x14016bcda  mov     [rsp+88h+var_68], r12
0x14016bcdf  lea     r8d, [r9+5]
0x14016bce3  call    WPP_RECORDER_SF_q_MAC_d
0x14016bce8  lea     rax, [rsi+30h]
0x14016bcec  mov     rcx, [rax]
0x14016bcef  cmp     [rcx+8], rax
0x14016bcf3  jnz     short loc_14016BD56
0x14016bcf5  mov     rdx, [rax+8]
0x14016bcf9  cmp     [rdx], rax
0x14016bcfc  jnz     short loc_14016BD56
0x14016bcfe  mov     [rdx], rcx
0x14016bd01  mov     [rcx+8], rdx
0x14016bd05  mov     rax, [rsi+28h]
0x14016bd09  test    rax, rax
0x14016bd0c  jz      short loc_14016BD17
0x14016bd0e  add     [rax+2D8h], bp
0x14016bd15  jmp     short loc_14016BD1E
0x14016bd17  add     [rbx+906h], bp
0x14016bd1e  lea     rcx, [rbx+670h]; HashTable
0x14016bd25  xor     r8d, r8d; Context
0x14016bd28  mov     rdx, rsi; Entry
0x14016bd2b  call    cs:__imp_RtlRemoveEntryHashTable
0x14016bd32  nop     dword ptr [rax+rax+00h]
0x14016bd37  xor     edx, edx; Tag
0x14016bd39  mov     rcx, rsi; P
0x14016bd3c  call    cs:__imp_ExFreePoolWithTag
0x14016bd43  nop     dword ptr [rax+rax+00h]
0x14016bd48  add     rsp, 58h
0x14016bd4c  pop     r14
0x14016bd4e  pop     r12
0x14016bd50  pop     rdi
0x14016bd51  pop     rsi
0x14016bd52  pop     rbp
0x14016bd53  pop     rbx
0x14016bd54  retn
0x14016bd56  mov     ecx, 3
0x14016bd5b  int     29h; Win8: RtlFailFast(ecx)
```
