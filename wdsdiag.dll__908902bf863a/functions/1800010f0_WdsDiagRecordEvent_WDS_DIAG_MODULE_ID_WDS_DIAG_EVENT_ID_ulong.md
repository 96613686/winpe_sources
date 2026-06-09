# WdsDiagRecordEvent(_WDS_DIAG_MODULE_ID,_WDS_DIAG_EVENT_ID,ulong,...)

- ea: `0x1800010f0`
- end: `0x18000116b`
- name: `?WdsDiagRecordEvent@@YAKW4_WDS_DIAG_MODULE_ID@@W4_WDS_DIAG_EVENT_ID@@KZZ`
- size: `123`
- prototype: `__int64(int, int, unsigned int, ...)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800010f0`
- `0x180001338`
- `0x18000145c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180001119`
- `KERNEL32!EnterCriticalSection` at `0x180001119`

## pseudocode

```c
__int64 WdsDiagRecordEvent(int a1, int a2, unsigned int a3, ...)
{
  __int64 v3; // rbx
  unsigned int v4; // edi
  __int64 v5; // rsi
  struct _RTL_CRITICAL_SECTION *v7; // [rsp+20h] [rbp-28h] BYREF
  int v8; // [rsp+28h] [rbp-20h]
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  v3 = a1;
  v4 = 0;
  v7 = &g_CSModules;
  v5 = a2;
  EnterCriticalSection(&g_CSModules);
  v8 = 1;
  if ( *((_DWORD *)&g_Modules + v3) )
    v4 = CEventLog2::LogV((CEventLog2 *)&RegHandle, (const struct _EVENT_DESCRIPTOR *)(&g_EventMapping)[v5], a3, va);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(&v7);
  return v4;
}

```

## disassembly

```asm
0x1800010f0  mov     rax, rsp
0x1800010f3  mov     [rax+18h], r8d
0x1800010f7  mov     [rax+20h], r9
0x1800010fb  push    rbx
0x1800010fc  push    rsi
0x1800010fd  push    rdi
0x1800010fe  sub     rsp, 30h
0x180001102  movsxd  rbx, ecx
0x180001105  xor     edi, edi
0x180001107  lea     rcx, ?g_CSModules@@3VCCriticalSection@@A; lpCriticalSection
0x18000110e  mov     [rax-28h], rdi
0x180001112  mov     [rax-28h], rcx
0x180001116  movsxd  rsi, edx
0x180001119  call    cs:__imp_EnterCriticalSection
0x18000111f  lea     rcx, cs:180000000h
0x180001126  mov     [rsp+48h+var_20], 1
0x18000112e  cmp     dword ptr rva ?g_Modules@@3PAHA[rcx+rbx*4], edi; int near * g_Modules ...
0x180001135  jz      short loc_180001157
0x180001137  mov     rdx, ds:rva ?g_EventMapping@@3PAPEBU_EVENT_DESCRIPTOR@@A[rcx+rsi*8]; struct _EVENT_DESCRIPTOR *
0x18000113f  lea     r9, [rsp+48h+arg_18]; char *
0x180001144  mov     r8d, [rsp+48h+arg_10]; unsigned int
0x180001149  lea     rcx, RegHandle; this
0x180001150  call    ?LogV@CEventLog2@@QEAAKPEBU_EVENT_DESCRIPTOR@@KPEAD@Z; CEventLog2::LogV(_EVENT_DESCRIPTOR const *,ulong,char *)
0x180001155  mov     edi, eax
0x180001157  lea     rcx, [rsp+48h+var_28]
0x18000115c  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180001161  mov     eax, edi
0x180001163  add     rsp, 30h
0x180001167  pop     rdi
0x180001168  pop     rsi
0x180001169  pop     rbx
0x18000116a  retn
```
