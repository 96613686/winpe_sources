# UmpoPowerRequestDeleteEntry

- ea: `0x18000410c`
- end: `0x180004168`
- name: `UmpoPowerRequestDeleteEntry`
- size: `92`
- prototype: `BOOLEAN __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003dac`
- `0x180003e40`
- `0x180015280`

## callees

- `0x18000410c`
- `0x18000f3dc`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180004149`
- `ntdll!RtlFreeHeap` at `0x18000412b`
- `ntdll!RtlFreeHeap` at `0x180004159`
- `ntdll!RtlFreeHeap` at `0x18000412b`
- `ntdll!RtlFreeHeap` at `0x180004159`

## pseudocode

```c
BOOLEAN __fastcall UmpoPowerRequestDeleteEntry(__int64 a1)
{
  void *v2; // r8

  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *(_QWORD *)a1 )
    RtlFreeHeap(UmpoHeapHandle, 0, *(PVOID *)a1);
  v2 = *(void **)(a1 + 16);
  if ( v2 )
    RtlFreeHeap(UmpoHeapHandle, 0, v2);
  return RtlDeleteElementGenericTableAvl(&UmpoPowerRequestTable, (PVOID)a1);
}

```

## disassembly

```asm
0x18000410c  push    rbx
0x18000410e  sub     rsp, 20h
0x180004112  mov     rbx, rcx
0x180004115  test    rcx, rcx
0x180004118  jz      short loc_180004161
0x18000411a  mov     r8, [rbx]; P
0x18000411d  test    r8, r8
0x180004120  jz      short loc_180004131
0x180004122  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180004129  xor     edx, edx; Flags
0x18000412b  call    cs:__imp_RtlFreeHeap
0x180004131  mov     r8, [rbx+10h]; P
0x180004135  test    r8, r8
0x180004138  jnz     short loc_180004150
0x18000413a  mov     rdx, rbx
0x18000413d  lea     rcx, UmpoPowerRequestTable
0x180004144  add     rsp, 20h
0x180004148  pop     rbx
0x180004149  jmp     cs:__imp_RtlDeleteElementGenericTableAvl
0x180004150  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180004157  xor     edx, edx; Flags
0x180004159  call    cs:__imp_RtlFreeHeap
0x18000415f  jmp     short loc_18000413A
0x180004161  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004166  jmp     short loc_18000411A
```
