# HandleFdoDeviceUsageNotification

- ea: `0x1400258cc`
- end: `0x1400259db`
- name: `HandleFdoDeviceUsageNotification`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140028800`

## callees

- `0x1400258cc`
- `0x140029e6c`
- `0x14002a0b0`

## import_xrefs

- `ntoskrnl!RtlCheckRegistryKey` at `0x140025946`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140025946`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400258ec`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400258ec`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14002596e`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14002596e`

## string_xrefs

- `0x140025988`: `noIdleDpcPendingEvent (wait for DPC to complete)`
- `0x1400259a2`: `idleCallbackBusyEvent (waiting for IdleCallback to run to completion)`
- `0x1400259bc`: `idleCompleteEvent`

## pseudocode

```c
__int64 __fastcall HandleFdoDeviceUsageNotification(__int64 a1, IRP *a2)
{
  unsigned int Options; // esi
  BOOLEAN v4; // al
  unsigned int v5; // edi
  __int64 v6; // r8
  int v7; // edx
  unsigned int v8; // edx

  Options = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options;
  v4 = IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(a1 + 40), a2);
  v5 = v4 == 0 ? 0xC0000001 : 0;
  if ( v4 )
  {
    if ( Options - 1 <= 2 )
    {
      v6 = *(_QWORD *)(a1 + 32);
      v7 = *(_DWORD *)(v6 + 48);
      if ( (*(_DWORD *)(*(_QWORD *)(a1 + 40) + 48LL) & 0x2000) != 0 )
        v8 = v7 | 0x2000;
      else
        v8 = v7 & 0xFFFFDFFF;
      *(_DWORD *)(v6 + 48) = v8;
    }
    if ( RtlCheckRegistryKey(2u, (PWSTR)L"MiniNT") < 0 && !*(_BYTE *)(a1 + 1376) )
    {
      *(_BYTE *)(a1 + 1376) = 1;
      TerminateIdleTimer(a1);
      KeFlushQueuedDpcs();
      WaitForSignal((PVOID)(a1 + 768));
      WaitForSignal((PVOID)(a1 + 872));
      WaitForSignal((PVOID)(a1 + 960));
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1400258cc  mov     [rsp+arg_0], rbx
0x1400258d1  mov     [rsp+arg_8], rsi
0x1400258d6  push    rdi
0x1400258d7  sub     rsp, 20h
0x1400258db  mov     rax, [rdx+0B8h]
0x1400258e2  mov     rbx, rcx
0x1400258e5  mov     rcx, [rcx+28h]; DeviceObject
0x1400258e9  mov     esi, [rax+10h]
0x1400258ec  call    cs:__imp_IoForwardIrpSynchronously
0x1400258f3  nop     dword ptr [rax+rax+00h]
0x1400258f8  mov     dl, al
0x1400258fa  neg     dl
0x1400258fc  sbb     edi, edi
0x1400258fe  not     edi
0x140025900  and     edi, 0C0000001h
0x140025906  test    al, al
0x140025908  jz      loc_1400259C8
0x14002590e  lea     eax, [rsi-1]
0x140025911  cmp     eax, 2
0x140025914  ja      short loc_14002593A
0x140025916  mov     rax, [rbx+28h]
0x14002591a  mov     r8, [rbx+20h]
0x14002591e  mov     ecx, [rax+30h]
0x140025921  mov     eax, 2000h
0x140025926  mov     edx, [r8+30h]
0x14002592a  test    eax, ecx
0x14002592c  jnz     short loc_140025934
0x14002592e  btr     edx, 0Dh
0x140025932  jmp     short loc_140025936
0x140025934  or      edx, eax
0x140025936  mov     [r8+30h], edx
0x14002593a  lea     rdx, Path; "MiniNT"
0x140025941  mov     ecx, 2; RelativeTo
0x140025946  call    cs:__imp_RtlCheckRegistryKey
0x14002594d  nop     dword ptr [rax+rax+00h]
0x140025952  test    eax, eax
0x140025954  jns     short loc_1400259C8
0x140025956  cmp     byte ptr [rbx+560h], 0
0x14002595d  jnz     short loc_1400259C8
0x14002595f  mov     rcx, rbx
0x140025962  mov     byte ptr [rbx+560h], 1
0x140025969  call    TerminateIdleTimer
0x14002596e  call    cs:__imp_KeFlushQueuedDpcs
0x140025975  nop     dword ptr [rax+rax+00h]
0x14002597a  mov     r8, [rbx+558h]
0x140025981  lea     rcx, [rbx+300h]; Object
0x140025988  lea     rdx, aNoidledpcpendi; "noIdleDpcPendingEvent (wait for DPC to "...
0x14002598f  call    WaitForSignal
0x140025994  mov     r8, [rbx+558h]
0x14002599b  lea     rcx, [rbx+368h]; Object
0x1400259a2  lea     rdx, aIdlecallbackbu; "idleCallbackBusyEvent (waiting for Idle"...
0x1400259a9  call    WaitForSignal
0x1400259ae  mov     r8, [rbx+558h]
0x1400259b5  lea     rcx, [rbx+3C0h]; Object
0x1400259bc  lea     rdx, aIdlecompleteev; "idleCompleteEvent"
0x1400259c3  call    WaitForSignal
0x1400259c8  mov     rbx, [rsp+28h+arg_0]
0x1400259cd  mov     eax, edi
0x1400259cf  mov     rsi, [rsp+28h+arg_8]
0x1400259d4  add     rsp, 20h
0x1400259d8  pop     rdi
0x1400259d9  retn
```
