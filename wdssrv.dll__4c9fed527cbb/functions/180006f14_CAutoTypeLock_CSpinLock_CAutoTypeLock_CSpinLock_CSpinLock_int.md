# CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)

- ea: `0x180006f14`
- end: `0x180006f81`
- name: `??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z`
- size: `109`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008158`
- `0x180008464`
- `0x180009cdc`
- `0x18000d380`
- `0x18000eb30`
- `0x1800102c4`
- `0x180010790`
- `0x18001687c`
- `0x1800171d0`
- `0x180017320`

## callees

- `0x180006f14`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006f37`
- `KERNEL32!GetCurrentThreadId` at `0x180006f37`
- `KERNEL32!SwitchToThread` at `0x180006f58`
- `KERNEL32!SwitchToThread` at `0x180006f58`

## pseudocode

```c
__int64 __fastcall CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(__int64 a1, __int64 a2)
{
  int v4; // esi
  DWORD CurrentThreadId; // ecx
  signed __int32 v6; // eax

  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = a2;
  while ( 1 )
  {
    v4 = 0;
    if ( *(_DWORD *)(a2 + 8) )
      break;
LABEL_6:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = _InterlockedCompareExchange((volatile signed __int32 *)a2, CurrentThreadId, 0);
    if ( !v6 || v6 == CurrentThreadId )
      break;
    if ( (unsigned int)++v4 >= *(_DWORD *)(a2 + 8) )
      goto LABEL_6;
  }
  _InterlockedIncrement((volatile signed __int32 *)(a2 + 4));
  ++*(_DWORD *)(a1 + 8);
  return a1;
}

```

## disassembly

```asm
0x180006f14  mov     [rsp+arg_0], rbx
0x180006f19  mov     [rsp+arg_8], rsi
0x180006f1e  push    rdi
0x180006f1f  sub     rsp, 20h
0x180006f23  and     dword ptr [rcx+8], 0
0x180006f27  mov     rbx, rdx
0x180006f2a  mov     rdi, rcx
0x180006f2d  mov     [rcx], rdx
0x180006f30  xor     esi, esi
0x180006f32  cmp     [rbx+8], esi
0x180006f35  jbe     short loc_180006F58
0x180006f37  call    cs:__imp_GetCurrentThreadId
0x180006f3e  nop     dword ptr [rax+rax+00h]
0x180006f43  mov     ecx, eax
0x180006f45  xor     eax, eax
0x180006f47  lock cmpxchg [rbx], ecx
0x180006f4b  jz      short loc_180006F66
0x180006f4d  cmp     eax, ecx
0x180006f4f  jz      short loc_180006F66
0x180006f51  inc     esi
0x180006f53  cmp     esi, [rbx+8]
0x180006f56  jb      short loc_180006F37
0x180006f58  call    cs:__imp_SwitchToThread
0x180006f5f  nop     dword ptr [rax+rax+00h]
0x180006f64  jmp     short loc_180006F30
0x180006f66  lock inc dword ptr [rbx+4]
0x180006f6a  inc     dword ptr [rdi+8]
0x180006f6d  mov     rax, rdi
0x180006f70  mov     rbx, [rsp+28h+arg_0]
0x180006f75  mov     rsi, [rsp+28h+arg_8]
0x180006f7a  add     rsp, 20h
0x180006f7e  pop     rdi
0x180006f7f  retn
```
