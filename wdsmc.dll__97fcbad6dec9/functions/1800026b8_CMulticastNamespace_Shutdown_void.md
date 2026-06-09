# CMulticastNamespace::Shutdown(void)

- ea: `0x1800026b8`
- end: `0x180002808`
- name: `?Shutdown@CMulticastNamespace@@QEAAKXZ`
- size: `336`
- prototype: `unsigned int __fastcall(CMulticastNamespace *__hidden this)`
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800022f0`
- `0x180002368`
- `0x180005a4c`
- `0x180005f18`
- `0x180006488`
- `0x1800067f0`
- `0x180007a24`

## callees

- `0x1800026b8`
- `0x180009dc8`
- `0x18000b0c4`
- `0x1800220f8`
- `0x1800229c0`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800027eb`
- `KERNEL32!LeaveCriticalSection` at `0x1800027eb`
- `KERNEL32!EnterCriticalSection` at `0x1800026d3`
- `KERNEL32!EnterCriticalSection` at `0x1800026d3`
- `WdsDiag!WdsDiagRecordEvent` at `0x180002740`
- `WdsDiag!WdsDiagRecordEvent` at `0x180002740`

## string_xrefs

- `0x180002794`: `WDSMCNS[%u:%s] Namespace shutdown complete.`

## pseudocode

```c

```

## disassembly

```asm
0x1800026b8  mov     [rsp+arg_0], rbx
0x1800026bd  mov     [rsp+arg_8], rbp
0x1800026c2  mov     [rsp+arg_10], rsi
0x1800026c7  push    rdi
0x1800026c8  sub     rsp, 50h
0x1800026cc  mov     rbx, rcx
0x1800026cf  add     rcx, 10h; lpCriticalSection
0x1800026d3  call    cs:__imp_EnterCriticalSection
0x1800026d9  xor     edi, edi
0x1800026db  mov     ebp, 1
0x1800026e0  cmp     [rbx+158h], edi
0x1800026e6  jz      short loc_18000274C
0x1800026e8  mov     rdx, [rbx+68h]
0x1800026ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800026f0  mov     r8, [rbx+50h]
0x1800026f4  mov     rcx, rax
0x1800026f7  inc     rcx
0x1800026fa  cmp     [rdx+rcx*2], di
0x1800026fe  jnz     short loc_1800026F7
0x180002700  lea     rcx, ds:2[rcx*2]
0x180002708  inc     rax
0x18000270b  cmp     [r8+rax*2], di
0x180002710  jnz     short loc_180002708
0x180002712  mov     [rsp+58h+var_18], rdx
0x180002717  lea     rax, ds:2[rax*2]
0x18000271f  mov     [rsp+58h+var_20], rcx
0x180002724  mov     r9d, ebp
0x180002727  mov     ecx, 2
0x18000272c  mov     [rsp+58h+var_28], ebp
0x180002730  mov     [rsp+58h+var_30], r8
0x180002735  mov     r8d, ecx
0x180002738  mov     [rsp+58h+var_38], rax
0x18000273d  lea     edx, [rcx+12h]
0x180002740  call    cs:__imp_?WdsDiagRecordEvent@@YAKW4_WDS_DIAG_MODULE_ID@@W4_WDS_DIAG_EVENT_ID@@KZZ; WdsDiagRecordEvent(_WDS_DIAG_MODULE_ID,_WDS_DIAG_EVENT_ID,ulong,...)
0x180002746  mov     [rbx+158h], edi
0x18000274c  mov     rcx, [rbx+0B0h]; lpCriticalSection
0x180002753  test    rcx, rcx
0x180002756  jz      short loc_180002784
0x180002758  mov     rdx, [rbx+160h]; void *
0x18000275f  test    rdx, rdx
0x180002762  jz      short loc_180002784
0x180002764  call    ?CloseInstance@CContentProvider@@QEAAKPEAX@Z; CContentProvider::CloseInstance(void *)
0x180002769  mov     ecx, eax; unsigned int
0x18000276b  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180002772  mov     r9d, 0E3h; unsigned int
0x180002778  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000277d  mov     [rbx+160h], rdi
0x180002784  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000278b  test    rax, rax
0x18000278e  jz      short loc_1800027A4
0x180002790  mov     r8, [rbx+50h]
0x180002794  lea     rcx, aWdsmcnsUSNames; "WDSMCNS[%u:%s] Namespace shutdown compl"...
0x18000279b  mov     edx, [rbx+38h]
0x18000279e  call    cs:__guard_dispatch_icall_fptr
0x1800027a4  lea     rcx, [rbx+40h]; struct _WDSTPT_NAMESPACE *
0x1800027a8  xor     edx, edx; int
0x1800027aa  call    ?FreeNamespace@CTptControlPacket@@SAXPEAU_WDSTPT_NAMESPACE@@H@Z; CTptControlPacket::FreeNamespace(_WDSTPT_NAMESPACE *,int)
0x1800027af  lea     rcx, [rbx+168h]; lpCriticalSection
0x1800027b6  call    ?Shutdown@CMcNsClients@@QEAAKXZ; CMcNsClients::Shutdown(void)
0x1800027bb  mov     eax, edi
0x1800027bd  lock xadd [rbx+154h], eax
0x1800027c5  test    eax, eax
0x1800027c7  jz      short loc_1800027E7
0x1800027c9  mov     r9d, ebp
0x1800027cc  mov     dword ptr [rsp+58h+var_38], ebp
0x1800027d0  xor     r8d, r8d
0x1800027d3  lea     rcx, qword_1800336A0; this
0x1800027da  mov     edx, ebp; unsigned int
0x1800027dc  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x1800027e1  xchg    edi, [rbx+154h]
0x1800027e7  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800027eb  call    cs:__imp_LeaveCriticalSection
0x1800027f1  mov     rbx, [rsp+58h+arg_0]
0x1800027f6  xor     eax, eax
0x1800027f8  mov     rbp, [rsp+58h+arg_8]
0x1800027fd  mov     rsi, [rsp+58h+arg_10]
0x180002802  add     rsp, 50h
0x180002806  pop     rdi
0x180002807  retn
```
