# JobsService::EnableOperationalLog(int)

- ea: `0x180059bf8`
- end: `0x180059cdf`
- name: `?EnableOperationalLog@JobsService@@CAJH@Z`
- size: `231`
- prototype: `__int64 __fastcall(BOOL)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180059864`

## callees

- `0x18004f90c`
- `0x180052584`
- `0x180059bf8`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x180059c60`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x180059c60`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x180059c24`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x180059c24`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x180059cc7`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x180059cc7`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x180059c9b`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x180059c9b`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSaveChannelConfig` at `0x180059caa`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSaveChannelConfig` at `0x180059caa`

## string_xrefs

- `0x180059c14`: `Microsoft-Windows-TaskScheduler/Operational`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x180059bf8  mov     rax, rsp
0x180059bfb  mov     [rax+8], rbx
0x180059bff  mov     [rax+18h], rsi
0x180059c03  push    rdi
0x180059c04  sub     rsp, 40h
0x180059c08  mov     esi, ecx
0x180059c0a  mov     dword ptr [rax+10h], 0
0x180059c11  xorps   xmm0, xmm0
0x180059c14  lea     rdx, aMicrosoftWindo_1; "Microsoft-Windows-TaskScheduler/Operati"...
0x180059c1b  xor     ecx, ecx; Session
0x180059c1d  xor     r8d, r8d; Flags
0x180059c20  movups  xmmword ptr [rax-18h], xmm0
0x180059c24  call    cs:__imp_EvtOpenChannelConfig
0x180059c2a  mov     rdi, rax
0x180059c2d  test    rax, rax
0x180059c30  jnz     short loc_180059C3E
0x180059c32  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180059c37  mov     ebx, eax
0x180059c39  jmp     loc_180059CCD
0x180059c3e  lea     rax, [rsp+48h+arg_8]
0x180059c43  mov     r9d, 10h; PropertyValueBufferSize
0x180059c49  mov     [rsp+48h+PropertyValueBufferUsed], rax; PropertyValueBufferUsed
0x180059c4e  xor     r8d, r8d; Flags
0x180059c51  lea     rax, [rsp+48h+PropertyValue]
0x180059c56  xor     edx, edx; PropertyId
0x180059c58  mov     rcx, rdi; ChannelConfig
0x180059c5b  mov     [rsp+48h+PropertyValueBuffer], rax; PropertyValueBuffer
0x180059c60  call    cs:__imp_EvtGetChannelConfigProperty
0x180059c66  test    eax, eax
0x180059c68  jnz     short loc_180059C73
0x180059c6a  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180059c6f  mov     ebx, eax
0x180059c71  jmp     short loc_180059CC4
0x180059c73  xor     ebx, ebx
0x180059c75  cmp     [rsp+48h+PropertyValue.Type], 0Dh
0x180059c7a  jnz     short loc_180059C82
0x180059c7c  cmp     dword ptr [rsp+48h+PropertyValue], esi
0x180059c80  jz      short loc_180059CC4
0x180059c82  lea     r9, [rsp+48h+PropertyValue]; PropertyValue
0x180059c87  mov     [rsp+48h+PropertyValue.Type], 0Dh
0x180059c8f  xor     r8d, r8d; Flags
0x180059c92  mov     dword ptr [rsp+48h+PropertyValue], esi
0x180059c96  xor     edx, edx; PropertyId
0x180059c98  mov     rcx, rdi; ChannelConfig
0x180059c9b  call    cs:__imp_EvtSetChannelConfigProperty
0x180059ca1  test    eax, eax
0x180059ca3  jz      short loc_180059C6A
0x180059ca5  xor     edx, edx; Flags
0x180059ca7  mov     rcx, rdi; ChannelConfig
0x180059caa  call    cs:__imp_EvtSaveChannelConfig
0x180059cb0  test    eax, eax
0x180059cb2  jz      short loc_180059C6A
0x180059cb4  test    esi, esi
0x180059cb6  jnz     short loc_180059CC4
0x180059cb8  lea     rdx, SCHEDULE_OPERATIONAL_LOG_DISABLED; struct _EVENT_DESCRIPTOR *
0x180059cbf  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,void *,_GUID const *)
0x180059cc4  mov     rcx, rdi; Object
0x180059cc7  call    cs:__imp_EvtClose
0x180059ccd  mov     rsi, [rsp+48h+arg_10]
0x180059cd2  mov     eax, ebx
0x180059cd4  mov     rbx, [rsp+48h+arg_0]
0x180059cd9  add     rsp, 40h
0x180059cdd  pop     rdi
0x180059cde  retn
```
