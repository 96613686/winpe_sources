# ChannelConfigSnapshot::ChannelConfigSnapshot(ChannelConfigReader const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x1400073ec`
- end: `0x140007503`
- name: `??0ChannelConfigSnapshot@@QEAA@AEBVChannelConfigReader@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z`
- size: `279`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x14002d8e4`
- `0x14002daf0`
- `0x14002ddb0`
- `0x14002e018`

## callees

- `0x140006de0`
- `0x1400073ec`
- `0x14000750c`
- `0x140007838`
- `0x1400158b4`
- `0x140015ac0`
- `0x140015b0c`
- `0x140015cac`
- `0x14001650c`
- `0x140019248`
- `0x1400196d8`
- `0x14001aec0`
- `0x14001b398`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ChannelConfigSnapshot::ChannelConfigSnapshot(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  char Isolation; // al
  int v8; // eax
  _QWORD v10[5]; // [rsp+20h] [rbp-28h] BYREF

  ChannelPublishingConfigData::ChannelPublishingConfigData(
    (ChannelPublishingConfigData *)a1,
    (const struct ChannelConfigReader *)a2);
  ChannelConfigReader::GetLogFilePath(a2, a1 + 56);
  ChannelConfigReader::GetFilterSnapshot(a2, (_BYTE *)(a1 + 88));
  *(_QWORD *)(a1 + 152) = ChannelConfigReader::GetMaxSize((ChannelConfigReader *)a2);
  *(_BYTE *)(a1 + 160) = ChannelConfigReader::GetRetention((ChannelConfigReader *)a2);
  *(_BYTE *)(a1 + 161) = ChannelConfigReader::GetAutoBackup((ChannelConfigReader *)a2);
  ChannelConfigReader::GetChannelAccessSddl((ChannelConfigReader *)a2, (LPCWSTR *)(a1 + 168));
  v10[0] = *(_QWORD *)(a2 + 32);
  v10[1] = (__int64)(*(_QWORD *)(a2 + 40) - v10[0]) >> 1;
  MakeOrThrowOOM(a1 + 200, v10);
  ChannelConfigReader::GetOwningPublisher((ChannelConfigReader *)a2, (struct _GUID *)(a1 + 232));
  v6 = *(_QWORD *)(a3 + 8);
  if ( v6 )
    Isolation = 0;
  else
    Isolation = ChannelConfigReader::GetIsolation((ChannelConfigReader *)a2);
  *(_BYTE *)(a1 + 248) = Isolation;
  if ( v6 )
    LOBYTE(v8) = 1;
  else
    v8 = *(_DWORD *)(a2 + 136);
  *(_BYTE *)(a1 + 249) = v8;
  *(_BYTE *)(a1 + 250) = *(_BYTE *)(a2 + 140);
  *(_BYTE *)(a1 + 251) = ChannelConfigReader::GetEnabledWithPolicyApplied((ChannelConfigReader *)a2);
  *(_BYTE *)(a1 + 252) = ChannelConfigReader::GetRawEnabled((ChannelConfigReader *)a2);
  return a1;
}

```

## disassembly

```asm
0x1400073ec  mov     [rsp+arg_10], rbx
0x1400073f1  mov     [rsp+arg_0], rcx
0x1400073f6  push    rbp
0x1400073f7  push    rsi
0x1400073f8  push    rdi
0x1400073f9  sub     rsp, 30h
0x1400073fd  mov     rdi, r8
0x140007400  mov     rbp, rdx
0x140007403  mov     rsi, rcx
0x140007406  call    ??0ChannelPublishingConfigData@@QEAA@AEBVChannelConfigReader@@@Z; ChannelPublishingConfigData::ChannelPublishingConfigData(ChannelConfigReader const &)
0x14000740b  lea     rbx, [rsi+38h]
0x14000740f  mov     [rsp+48h+arg_8], rbx
0x140007414  mov     rdx, rbx
0x140007417  mov     rcx, rbp
0x14000741a  call    ?GetLogFilePath@ChannelConfigReader@@QEBA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@XZ; ChannelConfigReader::GetLogFilePath(void)
0x14000741f  nop
0x140007420  lea     rdx, [rbx+20h]
0x140007424  mov     rcx, rbp
0x140007427  call    ?GetFilterSnapshot@ChannelConfigReader@@QEBA?AV?$optional@UQueryNode@@@utl@@XZ; ChannelConfigReader::GetFilterSnapshot(void)
0x14000742c  nop
0x14000742d  mov     rcx, rbp; this
0x140007430  call    ?GetMaxSize@ChannelConfigReader@@QEBA_KXZ; ChannelConfigReader::GetMaxSize(void)
0x140007435  mov     [rbx+60h], rax
0x140007439  mov     rcx, rbp; this
0x14000743c  call    ?GetRetention@ChannelConfigReader@@QEBA_NXZ; ChannelConfigReader::GetRetention(void)
0x140007441  mov     [rbx+68h], al
0x140007444  mov     rcx, rbp; this
0x140007447  call    ?GetAutoBackup@ChannelConfigReader@@QEBA_NXZ; ChannelConfigReader::GetAutoBackup(void)
0x14000744c  mov     [rbx+69h], al
0x14000744f  lea     rdx, [rsi+0A8h]
0x140007456  mov     rcx, rbp; this
0x140007459  call    ?GetChannelAccessSddl@ChannelConfigReader@@QEBA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@XZ; ChannelConfigReader::GetChannelAccessSddl(void)
0x14000745e  nop
0x14000745f  mov     rax, [rbp+20h]
0x140007463  mov     [rsp+48h+var_28], rax
0x140007468  mov     rcx, [rbp+28h]
0x14000746c  sub     rcx, rax
0x14000746f  sar     rcx, 1
0x140007472  mov     [rsp+48h+var_20], rcx
0x140007477  lea     rcx, [rsi+0C8h]
0x14000747e  lea     rdx, [rsp+48h+var_28]
0x140007483  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140007488  nop
0x140007489  lea     rdx, [rsi+0E8h]; retstr
0x140007490  mov     rcx, rbp; this
0x140007493  call    ?GetOwningPublisher@ChannelConfigReader@@QEBA?AU_GUID@@XZ; ChannelConfigReader::GetOwningPublisher(void)
0x140007498  mov     rbx, [rdi+8]
0x14000749c  test    rbx, rbx
0x14000749f  jnz     short loc_1400074AB
0x1400074a1  mov     rcx, rbp; this
0x1400074a4  call    ?GetIsolation@ChannelConfigReader@@QEBA?AW4_EVT_CHANNEL_ISOLATION_TYPE@@XZ; ChannelConfigReader::GetIsolation(void)
0x1400074a9  jmp     short loc_1400074AD
0x1400074ab  xor     eax, eax
0x1400074ad  mov     [rsi+0F8h], al
0x1400074b3  test    rbx, rbx
0x1400074b6  jnz     short loc_1400074C0
0x1400074b8  mov     eax, [rbp+88h]
0x1400074be  jmp     short loc_1400074C5
0x1400074c0  mov     eax, 1
0x1400074c5  mov     [rsi+0F9h], al
0x1400074cb  mov     al, [rbp+8Ch]
0x1400074d1  mov     [rsi+0FAh], al
0x1400074d7  mov     rcx, rbp; this
0x1400074da  call    ?GetEnabledWithPolicyApplied@ChannelConfigReader@@QEBA_NXZ; ChannelConfigReader::GetEnabledWithPolicyApplied(void)
0x1400074df  mov     [rsi+0FBh], al
0x1400074e5  mov     rcx, rbp; this
0x1400074e8  call    ?GetRawEnabled@ChannelConfigReader@@QEBA_NXZ; ChannelConfigReader::GetRawEnabled(void)
0x1400074ed  mov     [rsi+0FCh], al
0x1400074f3  mov     rax, rsi
0x1400074f6  mov     rbx, [rsp+48h+arg_10]
0x1400074fb  add     rsp, 30h
0x1400074ff  pop     rdi
0x140007500  pop     rsi
0x140007501  pop     rbp
0x140007502  retn
```
