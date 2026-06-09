# CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)

- ea: `0x1800025f0`
- end: `0x18000265a`
- name: `??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z`
- size: `106`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002948`
- `0x180006bf0`
- `0x180008f00`
- `0x18000abac`
- `0x18000ace0`

## callees

- `0x1800025f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002613`
- `KERNEL32!GetCurrentThreadId` at `0x180002613`
- `KERNEL32!SwitchToThread` at `0x180002631`
- `KERNEL32!SwitchToThread` at `0x180002631`

## pseudocode

```c
__int64 __fastcall CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(__int64 a1, __int64 a2)
{
  unsigned int i; // esi
  DWORD CurrentThreadId; // ecx
  signed __int32 v6; // eax

  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = a2;
LABEL_2:
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)(a2 + 8) )
    {
      SwitchToThread();
      goto LABEL_2;
    }
    CurrentThreadId = GetCurrentThreadId();
    v6 = _InterlockedCompareExchange((volatile signed __int32 *)a2, CurrentThreadId, 0);
    if ( !v6 || v6 == CurrentThreadId )
      break;
  }
  _InterlockedIncrement((volatile signed __int32 *)(a2 + 4));
  ++*(_DWORD *)(a1 + 8);
  return a1;
}

```

## disassembly

```asm
0x1800025f0  mov     [rsp+arg_0], rbx
0x1800025f5  mov     [rsp+arg_8], rsi
0x1800025fa  push    rdi
0x1800025fb  sub     rsp, 20h
0x1800025ff  and     dword ptr [rcx+8], 0
0x180002603  mov     rbx, rdx
0x180002606  mov     rdi, rcx
0x180002609  mov     [rcx], rdx
0x18000260c  xor     esi, esi
0x18000260e  cmp     esi, [rbx+8]
0x180002611  jnb     short loc_180002631
0x180002613  call    cs:__imp_GetCurrentThreadId
0x18000261a  nop     dword ptr [rax+rax+00h]
0x18000261f  mov     ecx, eax
0x180002621  xor     eax, eax
0x180002623  lock cmpxchg [rbx], ecx
0x180002627  jz      short loc_18000263F
0x180002629  cmp     eax, ecx
0x18000262b  jz      short loc_18000263F
0x18000262d  inc     esi
0x18000262f  jmp     short loc_18000260E
0x180002631  call    cs:__imp_SwitchToThread
0x180002638  nop     dword ptr [rax+rax+00h]
0x18000263d  jmp     short loc_18000260C
0x18000263f  lock inc dword ptr [rbx+4]
0x180002643  inc     dword ptr [rdi+8]
0x180002646  mov     rax, rdi
0x180002649  mov     rbx, [rsp+28h+arg_0]
0x18000264e  mov     rsi, [rsp+28h+arg_8]
0x180002653  add     rsp, 20h
0x180002657  pop     rdi
0x180002658  retn
```
