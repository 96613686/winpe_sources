# UbpmpInitPidInHardeningList

- ea: `0x1800203d0`
- end: `0x180020463`
- name: `UbpmpInitPidInHardeningList`
- size: `147`
- prototype: `__int64 __fastcall(PSID pSid1)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180021060`

## callees

- `0x1800203d0`
- `0x1800208bc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002044e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002044e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800203fd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800203fd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002043f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002043f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020403`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020403`

## pseudocode

```c
void __fastcall UbpmpInitPidInHardeningList(PSID pSid1, int a2)
{
  DWORD CurrentThreadId; // eax
  struct _LIST_ENTRY *Flink; // rbx

  if ( pSid1 && UbpmUtilsSidSupportsHardening(pSid1) )
  {
    RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
    CurrentThreadId = GetCurrentThreadId();
    Flink = g_leTaskHostHardeningListHead.Flink;
    dword_18004CF18 = CurrentThreadId;
    while ( Flink != &g_leTaskHostHardeningListHead )
    {
      if ( !Flink[3].Flink && EqualSid(pSid1, Flink[1].Blink) && !LODWORD(Flink[3].Blink) )
        LODWORD(Flink[3].Blink) = a2;
      Flink = Flink->Flink;
    }
    dword_18004CF18 = 0;
    RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
  }
}

```

## disassembly

```asm
0x1800203d0  test    rcx, rcx
0x1800203d3  jz      short locret_1800203F5
0x1800203d5  push    rbx
0x1800203d6  push    rsi
0x1800203d7  push    rdi
0x1800203d8  push    r14
0x1800203da  sub     rsp, 28h
0x1800203de  mov     esi, edx
0x1800203e0  mov     rdi, rcx
0x1800203e3  call    ?UbpmUtilsSidSupportsHardening@@YAEPEAX@Z; UbpmUtilsSidSupportsHardening(void *)
0x1800203e8  test    al, al
0x1800203ea  jnz     short loc_1800203F6
0x1800203ec  add     rsp, 28h
0x1800203f0  pop     r14
0x1800203f2  pop     rdi
0x1800203f3  pop     rsi
0x1800203f4  pop     rbx
0x1800203f5  retn
0x1800203f6  lea     rcx, g_TaskHostContextListLock
0x1800203fd  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180020403  call    cs:__imp_GetCurrentThreadId
0x180020409  mov     rbx, cs:?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x180020410  lea     r14, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x180020417  mov     cs:dword_18004CF18, eax
0x18002041d  cmp     rbx, r14
0x180020420  jz      short loc_18002042E
0x180020422  cmp     qword ptr [rbx+30h], 0
0x180020427  jz      short loc_180020447
0x180020429  mov     rbx, [rbx]
0x18002042c  jmp     short loc_18002041D
0x18002042e  lea     rcx, g_TaskHostContextListLock
0x180020435  mov     cs:dword_18004CF18, 0
0x18002043f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180020445  jmp     short loc_1800203EC
0x180020447  mov     rdx, [rbx+18h]; pSid2
0x18002044b  mov     rcx, rdi; pSid1
0x18002044e  call    cs:__imp_EqualSid
0x180020454  test    eax, eax
0x180020456  jz      short loc_180020429
0x180020458  cmp     dword ptr [rbx+38h], 0
0x18002045c  jnz     short loc_180020429
0x18002045e  mov     [rbx+38h], esi
0x180020461  jmp     short loc_180020429
```
