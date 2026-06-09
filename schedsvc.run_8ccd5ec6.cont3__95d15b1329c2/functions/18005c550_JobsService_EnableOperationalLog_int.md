# JobsService::EnableOperationalLog(int)

- ea: `0x18005c550`
- end: `0x18005c656`
- name: `?EnableOperationalLog@JobsService@@CAJH@Z`
- size: `262`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005c25c`

## callees

- `0x1800521cc`
- `0x180054c80`
- `0x18005c550`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x18005c5be`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x18005c5be`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18005c57c`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18005c57c`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18005c637`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18005c637`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x18005c5ff`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x18005c5ff`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSaveChannelConfig` at `0x18005c614`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSaveChannelConfig` at `0x18005c614`

## string_xrefs

- `0x18005c56c`: `Microsoft-Windows-TaskScheduler/Operational`

## pseudocode

```c
__int64 __fastcall JobsService::EnableOperationalLog(BOOL a1)
{
  int v2; // edx
  tsched *v3; // rcx
  EVT_HANDLE v4; // rdi
  unsigned int LastHrError; // ebx
  int v6; // edx
  EventManager *v7; // rcx
  void *v8; // r8
  const struct _GUID *v9; // r9
  struct _EVT_VARIANT PropertyValue; // [rsp+30h] [rbp-18h] BYREF
  DWORD PropertyValueBufferUsed; // [rsp+58h] [rbp+10h] BYREF

  PropertyValueBufferUsed = 0;
  PropertyValue = 0;
  v4 = EvtOpenChannelConfig(0, L"Microsoft-Windows-TaskScheduler/Operational", 0);
  if ( v4 )
  {
    if ( EvtGetChannelConfigProperty(v4, EvtChannelConfigEnabled, 0, 0x10u, &PropertyValue, &PropertyValueBufferUsed) )
    {
      LastHrError = 0;
      if ( PropertyValue.Type == 13 && PropertyValue.BooleanVal == a1 )
        goto LABEL_11;
      PropertyValue.Type = 13;
      PropertyValue.BooleanVal = a1;
      if ( EvtSetChannelConfigProperty(v4, EvtChannelConfigEnabled, 0, &PropertyValue) && EvtSaveChannelConfig(v4, 0) )
      {
        if ( !a1 )
          EventManager::EvtReport(v7, &SCHEDULE_OPERATIONAL_LOG_DISABLED, v8, v9);
        goto LABEL_11;
      }
    }
    LastHrError = tsched::GetLastHrError(v7, v6);
LABEL_11:
    EvtClose(v4);
    return LastHrError;
  }
  return (unsigned int)tsched::GetLastHrError(v3, v2);
}

```

## disassembly

```asm
0x18005c550  mov     rax, rsp
0x18005c553  mov     [rax+8], rbx
0x18005c557  mov     [rax+18h], rsi
0x18005c55b  push    rdi
0x18005c55c  sub     rsp, 40h
0x18005c560  mov     esi, ecx
0x18005c562  mov     dword ptr [rax+10h], 0
0x18005c569  xorps   xmm0, xmm0
0x18005c56c  lea     rdx, aMicrosoftWindo_1; "Microsoft-Windows-TaskScheduler/Operati"...
0x18005c573  xor     ecx, ecx; Session
0x18005c575  xor     r8d, r8d; Flags
0x18005c578  movups  xmmword ptr [rax-18h], xmm0
0x18005c57c  call    cs:__imp_EvtOpenChannelConfig
0x18005c583  nop     dword ptr [rax+rax+00h]
0x18005c588  mov     rdi, rax
0x18005c58b  test    rax, rax
0x18005c58e  jnz     short loc_18005C59C
0x18005c590  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18005c595  mov     ebx, eax
0x18005c597  jmp     loc_18005C643
0x18005c59c  lea     rax, [rsp+48h+arg_8]
0x18005c5a1  mov     r9d, 10h; PropertyValueBufferSize
0x18005c5a7  mov     [rsp+48h+PropertyValueBufferUsed], rax; PropertyValueBufferUsed
0x18005c5ac  xor     r8d, r8d; Flags
0x18005c5af  lea     rax, [rsp+48h+PropertyValue]
0x18005c5b4  xor     edx, edx; PropertyId
0x18005c5b6  mov     rcx, rdi; ChannelConfig
0x18005c5b9  mov     [rsp+48h+PropertyValueBuffer], rax; PropertyValueBuffer
0x18005c5be  call    cs:__imp_EvtGetChannelConfigProperty
0x18005c5c5  nop     dword ptr [rax+rax+00h]
0x18005c5ca  test    eax, eax
0x18005c5cc  jnz     short loc_18005C5D7
0x18005c5ce  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18005c5d3  mov     ebx, eax
0x18005c5d5  jmp     short loc_18005C634
0x18005c5d7  xor     ebx, ebx
0x18005c5d9  cmp     [rsp+48h+PropertyValue.Type], 0Dh
0x18005c5de  jnz     short loc_18005C5E6
0x18005c5e0  cmp     dword ptr [rsp+48h+PropertyValue], esi
0x18005c5e4  jz      short loc_18005C634
0x18005c5e6  lea     r9, [rsp+48h+PropertyValue]; PropertyValue
0x18005c5eb  mov     [rsp+48h+PropertyValue.Type], 0Dh
0x18005c5f3  xor     r8d, r8d; Flags
0x18005c5f6  mov     dword ptr [rsp+48h+PropertyValue], esi
0x18005c5fa  xor     edx, edx; PropertyId
0x18005c5fc  mov     rcx, rdi; ChannelConfig
0x18005c5ff  call    cs:__imp_EvtSetChannelConfigProperty
0x18005c606  nop     dword ptr [rax+rax+00h]
0x18005c60b  test    eax, eax
0x18005c60d  jz      short loc_18005C5CE
0x18005c60f  xor     edx, edx; Flags
0x18005c611  mov     rcx, rdi; ChannelConfig
0x18005c614  call    cs:__imp_EvtSaveChannelConfig
0x18005c61b  nop     dword ptr [rax+rax+00h]
0x18005c620  test    eax, eax
0x18005c622  jz      short loc_18005C5CE
0x18005c624  test    esi, esi
0x18005c626  jnz     short loc_18005C634
0x18005c628  lea     rdx, SCHEDULE_OPERATIONAL_LOG_DISABLED; struct _EVENT_DESCRIPTOR *
0x18005c62f  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,void *,_GUID const *)
0x18005c634  mov     rcx, rdi; Object
0x18005c637  call    cs:__imp_EvtClose
0x18005c63e  nop     dword ptr [rax+rax+00h]
0x18005c643  mov     rsi, [rsp+48h+arg_10]
0x18005c648  mov     eax, ebx
0x18005c64a  mov     rbx, [rsp+48h+arg_0]
0x18005c64f  add     rsp, 40h
0x18005c653  pop     rdi
0x18005c654  retn
```
