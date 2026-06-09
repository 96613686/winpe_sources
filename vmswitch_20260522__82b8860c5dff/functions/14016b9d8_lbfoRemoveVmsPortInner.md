# lbfoRemoveVmsPortInner

- ea: `0x14016b9d8`
- end: `0x14016bced`
- name: `lbfoRemoveVmsPortInner`
- size: `789`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14015e6cc`
- `0x140160ab0`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x1400ead88`
- `0x14010f9f0`
- `0x14016b8c8`
- `0x14016b9d8`
- `0x140170d48`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14016ba84`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14016bb26`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14016bcbb`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14016ba84`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14016bb26`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14016bcbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016bb37`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016bc10`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016bccc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016bb37`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016bc10`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016bccc`

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
0x14016b9d8  push    rbx
0x14016b9da  push    rbp
0x14016b9db  push    rsi
0x14016b9dc  push    rdi
0x14016b9dd  push    r12
0x14016b9df  push    r14
0x14016b9e1  sub     rsp, 58h
0x14016b9e5  xor     r14d, r14d
0x14016b9e8  lea     r12, WPP_92be587034f338e77c3b074d1450231a_Traceguids
0x14016b9ef  mov     rdi, rdx
0x14016b9f2  mov     rbx, rcx
0x14016b9f5  mov     esi, 13h
0x14016b9fa  cmp     [rdx+28h], r14d
0x14016b9fe  jnz     short loc_14016BA2F
0x14016ba00  mov     rcx, cs:VmsIfrLog
0x14016ba07  lea     rax, aVmsportVmsport_0; "VmsPort->VmsPortId != NDIS_SWITCH_DEFAU"...
0x14016ba0e  mov     [rsp+88h+var_60], rax
0x14016ba13  lea     r9d, [rsi-5]
0x14016ba17  mov     r8d, esi
0x14016ba1a  mov     [rsp+88h+var_68], r12
0x14016ba1f  call    WPP_RECORDER_SF_s
0x14016ba24  cmp     [rdi+28h], r14d
0x14016ba28  jnz     short loc_14016BA2F
0x14016ba2a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "VmsPort->VmsPortId != 0")
0x14016ba2f  cmp     [rbx+698h], rdi
0x14016ba36  jnz     short loc_14016BA6C
0x14016ba38  mov     rcx, cs:VmsIfrLog
0x14016ba3f  lea     rax, aTeamDefaultvms; "Team->DefaultVmsPort != VmsPort"
0x14016ba46  mov     [rsp+88h+var_60], rax
0x14016ba4b  mov     r9d, 0Fh
0x14016ba51  mov     r8d, esi
0x14016ba54  mov     [rsp+88h+var_68], r12
0x14016ba59  call    WPP_RECORDER_SF_s
0x14016ba5e  cmp     [rbx+698h], rdi
0x14016ba65  jnz     short loc_14016BA6C
0x14016ba67  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Team->DefaultVmsPort != VmsPort")
0x14016ba6c  mov     rax, [rdi+50h]
0x14016ba70  lea     rcx, [rbx+648h]; HashTable
0x14016ba77  xor     r8d, r8d; Context
0x14016ba7a  mov     rdx, rdi; Entry
0x14016ba7d  mov     [rax+2A50h], r14
0x14016ba84  call    cs:__imp_RtlRemoveEntryHashTable
0x14016ba8b  nop     dword ptr [rax+rax+00h]
0x14016ba90  lea     rsi, [rdi+30h]
0x14016ba94  mov     rax, [rsi]
0x14016ba97  cmp     rax, rsi
0x14016ba9a  jz      loc_14016BB48
0x14016baa0  cmp     [rax+8], rsi
0x14016baa4  jnz     loc_14016BCE6
0x14016baaa  mov     rcx, [rax]
0x14016baad  cmp     [rcx+8], rax
0x14016bab1  jnz     loc_14016BCE6
0x14016bab7  mov     [rsi], rcx
0x14016baba  lea     rbp, [rax-30h]
0x14016babe  mov     [rcx+8], rsi
0x14016bac2  mov     rcx, cs:WPP_GLOBAL_Control
0x14016bac9  mov     al, [rcx+29h]
0x14016bacc  dec     al
0x14016bace  cmp     al, 2
0x14016bad0  ja      short loc_14016BAD9
0x14016bad2  cmp     [rcx+48h], r14w
0x14016bad7  jz      short loc_14016BB19
0x14016bad9  movzx   r8d, word ptr [rbp+1Eh]
0x14016bade  lea     rdx, [rbp+18h]
0x14016bae2  mov     eax, [rdi+28h]
0x14016bae5  and     r8d, 0FFFh
0x14016baec  mov     rcx, [rcx+40h]
0x14016baf0  mov     r9d, 10h
0x14016baf6  mov     [rsp+88h+var_48], eax
0x14016bafa  mov     dword ptr [rsp+88h+var_50], r8d
0x14016baff  mov     [rsp+88h+var_58], rdx
0x14016bb04  xor     edx, edx
0x14016bb06  mov     [rsp+88h+var_60], rbx
0x14016bb0b  lea     r8d, [r9+7]
0x14016bb0f  mov     [rsp+88h+var_68], r12
0x14016bb14  call    WPP_RECORDER_SF_q_MAC_dd
0x14016bb19  lea     rcx, [rbx+670h]; HashTable
0x14016bb20  xor     r8d, r8d; Context
0x14016bb23  mov     rdx, rbp; Entry
0x14016bb26  call    cs:__imp_RtlRemoveEntryHashTable
0x14016bb2d  nop     dword ptr [rax+rax+00h]
0x14016bb32  xor     edx, edx; Tag
0x14016bb34  mov     rcx, rbp; P
0x14016bb37  call    cs:__imp_ExFreePoolWithTag
0x14016bb3e  nop     dword ptr [rax+rax+00h]
0x14016bb43  jmp     loc_14016BA94
0x14016bb48  lea     rax, [rdi+18h]
0x14016bb4c  mov     ebp, 0FFFFh
0x14016bb51  add     [rbx+640h], bp
0x14016bb58  mov     rdx, [rax]
0x14016bb5b  cmp     [rdx+8], rax
0x14016bb5f  jnz     loc_14016BCE6
0x14016bb65  mov     rcx, [rax+8]
0x14016bb69  cmp     [rcx], rax
0x14016bb6c  jnz     loc_14016BCE6
0x14016bb72  mov     rsi, [rdi+40h]
0x14016bb76  mov     [rcx], rdx
0x14016bb79  mov     [rdx+8], rcx
0x14016bb7d  mov     edx, 3FFFh
0x14016bb82  movzx   eax, word ptr [rsi+50h]
0x14016bb86  lea     ecx, [rax-1]
0x14016bb89  xor     cx, ax
0x14016bb8c  and     cx, dx
0x14016bb8f  xor     cx, ax
0x14016bb92  mov     [rsi+50h], cx
0x14016bb96  mov     rcx, rsi
0x14016bb99  call    lbfoLBUpdateCfgMacsOffloadPreferenceMasksForCfgMac
0x14016bb9e  mov     r11, [rsi+28h]
0x14016bba2  test    r11, r11
0x14016bba5  jz      short loc_14016BBC8
0x14016bba7  movzx   eax, word ptr [r11+2DAh]
0x14016bbaf  mov     edx, 7FFFh
0x14016bbb4  lea     ecx, [rax-1]
0x14016bbb7  xor     cx, ax
0x14016bbba  and     cx, dx
0x14016bbbd  xor     cx, ax
0x14016bbc0  mov     [r11+2DAh], cx
0x14016bbc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14016bbcf  mov     al, [rcx+29h]
0x14016bbd2  dec     al
0x14016bbd4  cmp     al, 2
0x14016bbd6  ja      short loc_14016BBDF
0x14016bbd8  cmp     [rcx+48h], r14w
0x14016bbdd  jz      short loc_14016BC0B
0x14016bbdf  movzx   edx, word ptr [rsi+1Eh]
0x14016bbe3  lea     rax, [rsi+18h]
0x14016bbe7  mov     rcx, [rcx+40h]
0x14016bbeb  and     edx, 0FFFh
0x14016bbf1  mov     [rsp+88h+var_48], edx
0x14016bbf5  mov     [rsp+88h+var_50], rax
0x14016bbfa  mov     eax, [rdi+28h]
0x14016bbfd  mov     dword ptr [rsp+88h+var_58], eax
0x14016bc01  mov     [rsp+88h+var_60], rbx
0x14016bc06  call    WPP_RECORDER_SF_qd_MAC_d
0x14016bc0b  xor     edx, edx; Tag
0x14016bc0d  mov     rcx, rdi; P
0x14016bc10  call    cs:__imp_ExFreePoolWithTag
0x14016bc17  nop     dword ptr [rax+rax+00h]
0x14016bc1c  mov     ecx, 3FFFh
0x14016bc21  test    [rsi+50h], cx
0x14016bc25  jnz     loc_14016BCD8
0x14016bc2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14016bc32  mov     al, [rcx+29h]
0x14016bc35  dec     al
0x14016bc37  cmp     al, 2
0x14016bc39  ja      short loc_14016BC42
0x14016bc3b  cmp     [rcx+48h], r14w
0x14016bc40  jz      short loc_14016BC78
0x14016bc42  movzx   edx, word ptr [rsi+1Eh]
0x14016bc46  lea     rax, [rsi+18h]
0x14016bc4a  mov     rcx, [rcx+40h]
0x14016bc4e  and     edx, 0FFFh
0x14016bc54  mov     dword ptr [rsp+88h+var_50], edx
0x14016bc58  mov     r9d, 12h
0x14016bc5e  mov     [rsp+88h+var_58], rax
0x14016bc63  xor     edx, edx
0x14016bc65  mov     [rsp+88h+var_60], rbx
0x14016bc6a  mov     [rsp+88h+var_68], r12
0x14016bc6f  lea     r8d, [r9+5]
0x14016bc73  call    WPP_RECORDER_SF_q_MAC_d
0x14016bc78  lea     rax, [rsi+30h]
0x14016bc7c  mov     rcx, [rax]
0x14016bc7f  cmp     [rcx+8], rax
0x14016bc83  jnz     short loc_14016BCE6
0x14016bc85  mov     rdx, [rax+8]
0x14016bc89  cmp     [rdx], rax
0x14016bc8c  jnz     short loc_14016BCE6
0x14016bc8e  mov     [rdx], rcx
0x14016bc91  mov     [rcx+8], rdx
0x14016bc95  mov     rax, [rsi+28h]
0x14016bc99  test    rax, rax
0x14016bc9c  jz      short loc_14016BCA7
0x14016bc9e  add     [rax+2D8h], bp
0x14016bca5  jmp     short loc_14016BCAE
0x14016bca7  add     [rbx+906h], bp
0x14016bcae  lea     rcx, [rbx+670h]; HashTable
0x14016bcb5  xor     r8d, r8d; Context
0x14016bcb8  mov     rdx, rsi; Entry
0x14016bcbb  call    cs:__imp_RtlRemoveEntryHashTable
0x14016bcc2  nop     dword ptr [rax+rax+00h]
0x14016bcc7  xor     edx, edx; Tag
0x14016bcc9  mov     rcx, rsi; P
0x14016bccc  call    cs:__imp_ExFreePoolWithTag
0x14016bcd3  nop     dword ptr [rax+rax+00h]
0x14016bcd8  add     rsp, 58h
0x14016bcdc  pop     r14
0x14016bcde  pop     r12
0x14016bce0  pop     rdi
0x14016bce1  pop     rsi
0x14016bce2  pop     rbp
0x14016bce3  pop     rbx
0x14016bce4  retn
0x14016bce6  mov     ecx, 3
0x14016bceb  int     29h; Win8: RtlFailFast(ecx)
```
