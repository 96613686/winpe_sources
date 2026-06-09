# UbpmUnsubscribeFromBrokerNotifications

- ea: `0x180013510`
- end: `0x1800136ee`
- name: `UbpmUnsubscribeFromBrokerNotifications`
- size: `478`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001311c`
- `0x1800136f4`
- `0x180016eb0`

## callees

- `0x180013510`
- `0x180018e3c`
- `0x18003488c`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x1800135d7`
- `ntdll!NtDeleteWnfStateName` at `0x1800135d7`
- `EventAggregation!EADeleteAggregateEvent` at `0x180013567`
- `EventAggregation!EADeleteAggregateEvent` at `0x180013680`
- `EventAggregation!EADeleteAggregateEvent` at `0x180013567`
- `EventAggregation!EADeleteAggregateEvent` at `0x180013680`
- `DABAPI!DabUnregisterTriggerConsumer` at `0x18001362e`
- `DABAPI!DabUnregisterTriggerConsumer` at `0x18001362e`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x1800135ab`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x1800135ab`

## pseudocode

```c
__int64 __fastcall UbpmUnsubscribeFromBrokerNotifications(__int64 a1)
{
  struct _UBPM_REPETITION_CONTEXT **v2; // rdi
  struct _UBPM_REPETITION_CONTEXT *v3; // rax
  __int64 result; // rax
  unsigned __int16 v5; // si
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rax
  _DWORD *v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  struct _UBPM_REPETITION_CONTEXT *v19; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct _UBPM_REPETITION_CONTEXT **)(a1 + 240);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == (struct _UBPM_REPETITION_CONTEXT *)v2 )
      break;
    if ( *((struct _UBPM_REPETITION_CONTEXT ***)v3 + 1) != v2
      || (v17 = *(_QWORD *)v3, *(struct _UBPM_REPETITION_CONTEXT **)(*(_QWORD *)v3 + 8LL) != v3) )
    {
      __fastfail(3u);
    }
    *v2 = (struct _UBPM_REPETITION_CONTEXT *)v17;
    *(_QWORD *)(v17 + 8) = v2;
    v19 = v3;
    UbpmpDeleteRepetitionContext(&v19);
  }
  result = *(_QWORD *)(a1 + 24);
  v5 = 0;
  if ( *(_DWORD *)(result + 20) )
  {
    do
    {
      v6 = 40LL * v5;
      if ( *(_QWORD *)(v6 + *(_QWORD *)(a1 + 32)) )
      {
        if ( (unsigned int)EADeleteAggregateEvent() )
          MicrosoftTelemetryAssertTriggeredNoArgs(v7);
        *(_QWORD *)(v6 + *(_QWORD *)(a1 + 32)) = 0;
      }
      if ( *(_QWORD *)(v6 + *(_QWORD *)(a1 + 32) + 8) )
      {
        if ( (unsigned int)EADeleteAggregateEvent() )
          MicrosoftTelemetryAssertTriggeredNoArgs(v18);
        *(_QWORD *)(v6 + *(_QWORD *)(a1 + 32) + 8) = 0;
      }
      v8 = v6 + *(_QWORD *)(a1 + 32);
      v9 = *(_DWORD *)(v8 + 24);
      if ( v9 == 2 )
      {
        if ( *(_DWORD *)(v8 + 16) || *(_DWORD *)(v8 + 20) )
        {
          if ( (int)CSebDeleteEvent(*(_QWORD *)(v8 + 16)) < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v10);
          *(_QWORD *)(v6 + *(_QWORD *)(a1 + 32) + 16) = 0;
        }
        v11 = *(_QWORD *)(a1 + 32);
        v12 = (_DWORD *)(v6 + v11 + 32);
        if ( *v12 || *(_DWORD *)(v6 + v11 + 36) )
        {
          if ( (int)NtDeleteWnfStateName(v12) < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v13);
          *(_QWORD *)(v6 + *(_QWORD *)(a1 + 32) + 32) = 0;
        }
      }
      else
      {
        v14 = v9 - 1;
        if ( v14 )
        {
          if ( v14 == 2 )
            *(_BYTE *)(a1 + 40) = 0;
        }
        else
        {
          v15 = (_QWORD *)(v8 + 32);
          if ( *v15 )
          {
            if ( (unsigned int)DabUnregisterTriggerConsumer(v15, 1, 0) )
              MicrosoftTelemetryAssertTriggeredNoArgs(v16);
            *(_QWORD *)(v6 + *(_QWORD *)(a1 + 32) + 32) = 0;
          }
        }
      }
      result = ++v5;
    }
    while ( (unsigned int)v5 < *(_DWORD *)(*(_QWORD *)(a1 + 24) + 20LL) );
  }
  return result;
}

```

## disassembly

```asm
0x180013510  mov     [rsp+arg_18], rbx
0x180013515  push    rdi
0x180013516  sub     rsp, 20h
0x18001351a  mov     rbx, rcx
0x18001351d  lea     rdi, [rcx+0F0h]
0x180013524  mov     rax, [rdi]
0x180013527  cmp     rax, rdi
0x18001352a  jnz     loc_180013647
0x180013530  mov     rax, [rbx+18h]
0x180013534  mov     [rsp+28h+arg_8], rbp
0x180013539  xor     ebp, ebp
0x18001353b  mov     [rsp+28h+arg_10], rsi
0x180013540  mov     esi, ebp
0x180013542  cmp     [rax+14h], ebp
0x180013545  jbe     loc_180013603
0x18001354b  movzx   eax, si
0x18001354e  lea     rcx, [rax+rax*4]
0x180013552  mov     rax, [rbx+20h]
0x180013556  lea     rdi, ds:0[rcx*8]
0x18001355e  mov     rcx, [rdi+rax]
0x180013562  test    rcx, rcx
0x180013565  jz      short loc_18001357D
0x180013567  call    cs:__imp_EADeleteAggregateEvent
0x18001356d  test    eax, eax
0x18001356f  jnz     loc_1800136B1
0x180013575  mov     rax, [rbx+20h]
0x180013579  mov     [rdi+rax], rbp
0x18001357d  mov     rax, [rbx+20h]
0x180013581  mov     rcx, [rdi+rax+8]
0x180013586  test    rcx, rcx
0x180013589  jnz     loc_180013680
0x18001358f  mov     rcx, [rbx+20h]
0x180013593  add     rcx, rdi
0x180013596  mov     eax, [rcx+18h]
0x180013599  cmp     eax, 2
0x18001359c  jnz     short loc_180013618
0x18001359e  cmp     [rcx+10h], ebp
0x1800135a1  jz      loc_1800136CC
0x1800135a7  mov     rcx, [rcx+10h]
0x1800135ab  call    cs:__imp_CSebDeleteEvent
0x1800135b1  test    eax, eax
0x1800135b3  js      loc_1800136DA
0x1800135b9  mov     rax, [rbx+20h]
0x1800135bd  xor     ecx, ecx
0x1800135bf  mov     [rdi+rax+10h], rcx
0x1800135c4  mov     rax, [rbx+20h]
0x1800135c8  lea     rcx, [rax+20h]
0x1800135cc  add     rcx, rdi
0x1800135cf  cmp     [rcx], ebp
0x1800135d1  jz      loc_180013671
0x1800135d7  call    cs:__imp_NtDeleteWnfStateName
0x1800135dd  test    eax, eax
0x1800135df  js      loc_1800136E4
0x1800135e5  mov     rax, [rbx+20h]
0x1800135e9  xor     ecx, ecx
0x1800135eb  mov     [rdi+rax+20h], rcx
0x1800135f0  mov     rcx, [rbx+18h]
0x1800135f4  inc     si
0x1800135f7  movzx   eax, si
0x1800135fa  cmp     eax, [rcx+14h]
0x1800135fd  jb      loc_18001354B
0x180013603  mov     rbp, [rsp+28h+arg_8]
0x180013608  mov     rsi, [rsp+28h+arg_10]
0x18001360d  mov     rbx, [rsp+28h+arg_18]
0x180013612  add     rsp, 20h
0x180013616  pop     rdi
0x180013617  retn
0x180013618  sub     eax, 1
0x18001361b  jnz     short loc_180013698
0x18001361d  add     rcx, 20h ; ' '
0x180013621  cmp     [rcx], rbp
0x180013624  jz      short loc_1800135F0
0x180013626  xor     r8d, r8d
0x180013629  mov     edx, 1
0x18001362e  call    cs:__imp_DabUnregisterTriggerConsumer
0x180013634  test    eax, eax
0x180013636  jnz     loc_1800136C2
0x18001363c  mov     rax, [rbx+20h]
0x180013640  mov     [rdi+rax+20h], rbp
0x180013645  jmp     short loc_1800135F0
0x180013647  cmp     [rax+8], rdi
0x18001364b  jnz     short loc_1800136AA
0x18001364d  mov     rcx, [rax]
0x180013650  cmp     [rcx+8], rax
0x180013654  jnz     short loc_1800136AA
0x180013656  mov     [rdi], rcx
0x180013659  mov     [rcx+8], rdi
0x18001365d  lea     rcx, [rsp+28h+arg_0]; struct _UBPM_REPETITION_CONTEXT **
0x180013662  mov     [rsp+28h+arg_0], rax
0x180013667  call    ?UbpmpDeleteRepetitionContext@@YAXPEAPEAU_UBPM_REPETITION_CONTEXT@@@Z; UbpmpDeleteRepetitionContext(_UBPM_REPETITION_CONTEXT * *)
0x18001366c  jmp     loc_180013524
0x180013671  cmp     [rdi+rax+24h], ebp
0x180013675  jz      loc_1800135F0
0x18001367b  jmp     loc_1800135D7
0x180013680  call    cs:__imp_EADeleteAggregateEvent
0x180013686  test    eax, eax
0x180013688  jnz     short loc_1800136BB
0x18001368a  mov     rax, [rbx+20h]
0x18001368e  mov     [rdi+rax+8], rbp
0x180013693  jmp     loc_18001358F
0x180013698  cmp     eax, 2
0x18001369b  jnz     loc_1800135F0
0x1800136a1  mov     [rbx+28h], bpl
0x1800136a5  jmp     loc_1800135F0
0x1800136aa  mov     ecx, 3
0x1800136af  int     29h; Win8: RtlFailFast(ecx)
0x1800136b1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800136b6  jmp     loc_180013575
0x1800136bb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800136c0  jmp     short loc_18001368A
0x1800136c2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800136c7  jmp     loc_18001363C
0x1800136cc  cmp     [rcx+14h], ebp
0x1800136cf  jz      loc_1800135C4
0x1800136d5  jmp     loc_1800135A7
0x1800136da  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800136df  jmp     loc_1800135B9
0x1800136e4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800136e9  jmp     loc_1800135E5
```
