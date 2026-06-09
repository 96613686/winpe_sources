# UmpoRpcLegacyEventRegisterNotification

- ea: `0x180003150`
- end: `0x180003265`
- name: `UmpoRpcLegacyEventRegisterNotification`
- size: `277`
- prototype: `__int64 __fastcall(__int64, PVOID, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001bd4`
- `0x18000219c`
- `0x180003150`
- `0x180004b80`
- `0x18000f3dc`

## import_xrefs

- `ntdll!DbgPrint` at `0x18000325a`
- `ntdll!DbgPrint` at `0x18000325a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800031e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800031e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003197`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003197`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800031fd`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800031fd`

## pseudocode

```c
__int64 __fastcall UmpoRpcLegacyEventRegisterNotification(__int64 a1, PVOID a2, const wchar_t *a3, int a4)
{
  PVOID *i; // rcx
  unsigned int v8; // ebx
  unsigned int v10; // eax
  __int64 v11; // rcx
  PVOID *v12; // [rsp+30h] [rbp-18h] BYREF

  if ( (UmpoDebug & 2) != 0 )
    DbgPrint("Calling PowerRegisterLegacyEventNotification: %S\n", a3);
  if ( !UmpoIsClientLocal() )
    return 5;
  if ( byte_180024F48 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection(&UmpoNotification);
  for ( i = (PVOID *)UmpoLegacyEventRegistrantList; i != &UmpoLegacyEventRegistrantList; i = (PVOID *)*i )
  {
    if ( *((_DWORD *)i + 5) == 1 && i[3] == a2 )
      goto LABEL_13;
  }
  i = 0;
LABEL_13:
  v12 = i;
  if ( a4 )
  {
    if ( i && *((_BYTE *)i + 45) )
    {
      *((_BYTE *)i + 45) = 0;
      UmpoDereferenceRegistrant();
    }
  }
  else if ( !i )
  {
    v10 = WTSGetServiceSessionId();
    v8 = UmpoNotifyRegister(v11, v10, a2, a3, &v12);
    if ( v8 )
      goto LABEL_16;
  }
  v8 = 0;
LABEL_16:
  if ( byte_180024F48 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LeaveCriticalSection(&UmpoNotification);
  return v8;
}

```

## disassembly

```asm
0x180003150  mov     [rsp+arg_0], rbx
0x180003155  mov     [rsp+arg_8], rsi
0x18000315a  push    rdi
0x18000315b  sub     rsp, 40h
0x18000315f  mov     eax, cs:UmpoDebug
0x180003165  mov     esi, r9d
0x180003168  mov     rbx, r8
0x18000316b  mov     rdi, rdx
0x18000316e  test    al, 2
0x180003170  jnz     loc_180003250
0x180003176  call    UmpoIsClientLocal
0x18000317b  test    eax, eax
0x18000317d  jz      loc_180003238
0x180003183  cmp     cs:byte_180024F48, 1
0x18000318a  jnz     loc_180003246
0x180003190  lea     rcx, UmpoNotification; lpCriticalSection
0x180003197  call    cs:__imp_EnterCriticalSection
0x18000319d  mov     rcx, cs:UmpoLegacyEventRegistrantList
0x1800031a4  lea     rax, UmpoLegacyEventRegistrantList
0x1800031ab  cmp     rcx, rax
0x1800031ae  jz      short loc_1800031C3
0x1800031b0  cmp     dword ptr [rcx+14h], 1
0x1800031b4  jz      short loc_1800031BB
0x1800031b6  mov     rcx, [rcx]
0x1800031b9  jmp     short loc_1800031A4
0x1800031bb  cmp     [rcx+18h], rdi
0x1800031bf  jnz     short loc_1800031B6
0x1800031c1  jmp     short loc_1800031C5
0x1800031c3  xor     ecx, ecx
0x1800031c5  mov     [rsp+48h+var_18], rcx
0x1800031ca  test    esi, esi
0x1800031cc  jnz     short loc_180003222
0x1800031ce  test    rcx, rcx
0x1800031d1  jz      short loc_1800031FD
0x1800031d3  xor     ebx, ebx
0x1800031d5  cmp     cs:byte_180024F48, 1
0x1800031dc  jnz     short loc_18000323F
0x1800031de  lea     rcx, UmpoNotification; lpCriticalSection
0x1800031e5  call    cs:__imp_LeaveCriticalSection
0x1800031eb  mov     rsi, [rsp+48h+arg_8]
0x1800031f0  mov     eax, ebx
0x1800031f2  mov     rbx, [rsp+48h+arg_0]
0x1800031f7  add     rsp, 40h
0x1800031fb  pop     rdi
0x1800031fc  retn
0x1800031fd  call    cs:__imp_WTSGetServiceSessionId
0x180003203  mov     r9, rbx
0x180003206  mov     r8, rdi
0x180003209  mov     edx, eax
0x18000320b  lea     rax, [rsp+48h+var_18]
0x180003210  mov     [rsp+48h+var_28], rax
0x180003215  call    UmpoNotifyRegister
0x18000321a  mov     ebx, eax
0x18000321c  test    eax, eax
0x18000321e  jnz     short loc_1800031D5
0x180003220  jmp     short loc_1800031D3
0x180003222  test    rcx, rcx
0x180003225  jz      short loc_1800031D3
0x180003227  cmp     byte ptr [rcx+2Dh], 0
0x18000322b  jz      short loc_1800031D3
0x18000322d  mov     byte ptr [rcx+2Dh], 0
0x180003231  call    UmpoDereferenceRegistrant
0x180003236  jmp     short loc_1800031D3
0x180003238  mov     ebx, 5
0x18000323d  jmp     short loc_1800031EB
0x18000323f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180003244  jmp     short loc_1800031DE
0x180003246  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000324b  jmp     loc_180003190
0x180003250  mov     rdx, rbx
0x180003253  lea     rcx, aCallingPowerre; "Calling PowerRegisterLegacyEventNotific"...
0x18000325a  call    cs:__imp_DbgPrint
0x180003260  jmp     loc_180003176
```
