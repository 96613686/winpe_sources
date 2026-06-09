# SqosDelayedJobQueueRemoveIo

- ea: `0x140006890`
- end: `0x1400068c8`
- name: `SqosDelayedJobQueueRemoveIo`
- size: `56`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140006890`

## pseudocode

```c
void __fastcall SqosDelayedJobQueueRemoveIo(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)
{
  union _FLT_CALLBACK_DATA::$312C66EF40AEDAF2A3A5D4554FF51F28 *p_QueueLinks; // rax
  struct _LIST_ENTRY *Flink; // r9
  struct _LIST_ENTRY *Blink; // r8

  p_QueueLinks = (union _FLT_CALLBACK_DATA::$312C66EF40AEDAF2A3A5D4554FF51F28 *)&Cbd->QueueLinks;
  Flink = Cbd->QueueLinks.Flink;
  if ( Flink->Blink != &Cbd->QueueLinks
    || (Blink = Cbd->QueueLinks.Blink,
        (union _FLT_CALLBACK_DATA::$312C66EF40AEDAF2A3A5D4554FF51F28 *)Blink->Flink != p_QueueLinks) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  Cbd->QueueLinks.Blink = 0;
  p_QueueLinks->QueueLinks.Flink = 0;
  --LODWORD(Cbdq[-1].CompleteCanceledIo);
}

```

## disassembly

```asm
0x140006890  lea     rax, [rdx+30h]
0x140006894  mov     r9, [rax]
0x140006897  cmp     [r9+8], rax
0x14000689b  jnz     short loc_1400068C1
0x14000689d  mov     r8, [rax+8]
0x1400068a1  cmp     [r8], rax
0x1400068a4  jnz     short loc_1400068C1
0x1400068a6  mov     [r8], r9
0x1400068a9  mov     [r9+8], r8
0x1400068ad  mov     qword ptr [rdx+38h], 0
0x1400068b5  mov     qword ptr [rax], 0
0x1400068bc  dec     dword ptr [rcx-8]
0x1400068bf  retn
0x1400068c1  mov     ecx, 3
0x1400068c6  int     29h; Win8: RtlFailFast(ecx)
```
