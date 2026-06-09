# CMulticastContent::Shutdown(void)

- ea: `0x180004184`
- end: `0x180004335`
- name: `?Shutdown@CMulticastContent@@QEAAKXZ`
- size: `433`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180002810`
- `0x180002c70`
- `0x180003868`
- `0x1800074bc`

## callees

- `0x180004184`
- `0x180004438`
- `0x18000a018`
- `0x18000b430`
- `0x18001a9a8`
- `0x1800229c0`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180004318`
- `KERNEL32!LeaveCriticalSection` at `0x180004318`
- `KERNEL32!EnterCriticalSection` at `0x18000419b`
- `KERNEL32!EnterCriticalSection` at `0x18000419b`
- `WDSSRV!WdsPacketFree` at `0x1800041ff`
- `WDSSRV!WdsPacketFree` at `0x1800041ff`
- `WdsDiag!WdsDiagRecordEvent` at `0x1800042b6`
- `WdsDiag!WdsDiagRecordEvent` at `0x1800042b6`

## string_xrefs

- `0x180004305`: `WDSMCCO[%u:%s] Shutdown complete.`

## pseudocode

```c

```

## disassembly

```asm
0x180004184  mov     [rsp+arg_0], rbx
0x180004189  mov     [rsp+arg_8], rbp
0x18000418e  mov     [rsp+arg_10], rsi
0x180004193  push    rdi
0x180004194  sub     rsp, 50h
0x180004198  mov     rdi, rcx
0x18000419b  call    cs:__imp_EnterCriticalSection
0x1800041a1  mov     rcx, rdi; lpCriticalSection
0x1800041a4  call    ?Cleanup@CMulticastContent@@QEAAXXZ; CMulticastContent::Cleanup(void)
0x1800041a9  mov     rdx, [rdi+0F8h]; void *
0x1800041b0  xor     ebp, ebp
0x1800041b2  test    rdx, rdx
0x1800041b5  jz      short loc_1800041DB
0x1800041b7  mov     rcx, [rdi+38h]; lpCriticalSection
0x1800041bb  call    ?CloseContent@CContentProvider@@QEAAKPEAX@Z; CContentProvider::CloseContent(void *)
0x1800041c0  mov     ecx, eax; unsigned int
0x1800041c2  lea     r8, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800041c9  mov     r9d, 0CAh; unsigned int
0x1800041cf  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800041d4  mov     [rdi+0F8h], rbp
0x1800041db  mov     r8, [rdi+108h]
0x1800041e2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800041e6  test    r8, r8
0x1800041e9  jz      short loc_180004216
0x1800041eb  mov     rcx, cs:qword_1800336E8
0x1800041f2  xor     edx, edx
0x1800041f4  mov     rbx, [rdi+38h]
0x1800041f8  mov     rcx, [rcx+120h]
0x1800041ff  call    cs:__imp_WdsPacketFree
0x180004205  lock add [rbx+48h], esi
0x180004209  mov     [rdi+108h], rbp
0x180004210  mov     [rdi+110h], ebp
0x180004216  lea     rcx, [rdi+138h]; this
0x18000421d  call    ?Shutdown@CMcCoClients@@QEAAKXZ; CMcCoClients::Shutdown(void)
0x180004222  mov     eax, ebp
0x180004224  lock xadd [rdi+11Ch], eax
0x18000422c  mov     ebx, 1
0x180004231  test    eax, eax
0x180004233  jz      short loc_180004255
0x180004235  mov     r9d, ebx
0x180004238  mov     dword ptr [rsp+58h+var_38], ebx
0x18000423c  mov     r8d, ebx
0x18000423f  lea     rcx, qword_1800336A0; this
0x180004246  mov     edx, ebx; unsigned int
0x180004248  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x18000424d  mov     eax, ebp
0x18000424f  xchg    eax, [rdi+11Ch]
0x180004255  cmp     [rdi+0F0h], ebp
0x18000425b  jz      short loc_1800042C2
0x18000425d  mov     rcx, [rdi+0E8h]
0x180004264  mov     rax, rsi
0x180004267  mov     rdx, [rdi+0E0h]
0x18000426e  inc     rax
0x180004271  cmp     [rcx+rax*2], bp
0x180004275  jnz     short loc_18000426E
0x180004277  lea     r8, ds:2[rax*2]
0x18000427f  inc     rsi
0x180004282  cmp     [rdx+rsi*2], bp
0x180004286  jnz     short loc_18000427F
0x180004288  mov     [rsp+58h+var_18], rcx
0x18000428d  lea     rax, ds:2[rsi*2]
0x180004295  mov     [rsp+58h+var_20], r8
0x18000429a  mov     ecx, 2
0x18000429f  mov     [rsp+58h+var_28], ebx
0x1800042a3  mov     r9d, ebx
0x1800042a6  mov     [rsp+58h+var_30], rdx
0x1800042ab  mov     r8d, ecx
0x1800042ae  mov     [rsp+58h+var_38], rax
0x1800042b3  lea     edx, [rcx+14h]
0x1800042b6  call    cs:__imp_?WdsDiagRecordEvent@@YAKW4_WDS_DIAG_MODULE_ID@@W4_WDS_DIAG_EVENT_ID@@KZZ; WdsDiagRecordEvent(_WDS_DIAG_MODULE_ID,_WDS_DIAG_EVENT_ID,ulong,...)
0x1800042bc  mov     [rdi+0F0h], ebp
0x1800042c2  mov     rcx, [rdi+0E8h]; void *
0x1800042c9  test    rcx, rcx
0x1800042cc  jz      short loc_1800042DA
0x1800042ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800042d3  mov     [rdi+0E8h], rbp
0x1800042da  mov     rcx, [rdi+0E0h]; void *
0x1800042e1  test    rcx, rcx
0x1800042e4  jz      short loc_1800042F2
0x1800042e6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800042eb  mov     [rdi+0E0h], rbp
0x1800042f2  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800042f9  test    rax, rax
0x1800042fc  jz      short loc_180004315
0x1800042fe  mov     r8, [rdi+0E8h]
0x180004305  lea     rcx, aWdsmccoUSShutd; "WDSMCCO[%u:%s] Shutdown complete."
0x18000430c  mov     edx, [rdi+28h]
0x18000430f  call    cs:__guard_dispatch_icall_fptr
0x180004315  mov     rcx, rdi; lpCriticalSection
0x180004318  call    cs:__imp_LeaveCriticalSection
0x18000431e  mov     rbx, [rsp+58h+arg_0]
0x180004323  xor     eax, eax
0x180004325  mov     rbp, [rsp+58h+arg_8]
0x18000432a  mov     rsi, [rsp+58h+arg_10]
0x18000432f  add     rsp, 50h
0x180004333  pop     rdi
0x180004334  retn
```
