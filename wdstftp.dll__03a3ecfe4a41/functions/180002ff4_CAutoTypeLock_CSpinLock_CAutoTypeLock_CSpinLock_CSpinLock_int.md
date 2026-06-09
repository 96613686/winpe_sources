# CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)

- ea: `0x180002ff4`
- end: `0x180003065`
- name: `??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z`
- size: `113`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001754`
- `0x180002ccc`
- `0x180002d84`
- `0x180002e50`
- `0x180003070`
- `0x18000615c`
- `0x180008310`
- `0x1800083e0`
- `0x1800094bc`
- `0x18000a4b8`
- `0x18000a760`

## callees

- `0x180002ff4`

## import_xrefs

- `KERNEL32!SwitchToThread` at `0x180003038`
- `KERNEL32!SwitchToThread` at `0x180003038`
- `KERNEL32!GetCurrentThreadId` at `0x180003017`
- `KERNEL32!GetCurrentThreadId` at `0x180003017`

## pseudocode

```c
__int64 *__fastcall CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(__int64 *a1)
{
  int v1; // eax
  __int64 v3; // rdi
  int v4; // esi
  DWORD CurrentThreadId; // ecx
  signed __int32 v6; // eax

  v1 = *((_DWORD *)a1 + 2);
  if ( !v1 )
  {
    v3 = *a1;
    while ( 1 )
    {
      v4 = 0;
      if ( *(_DWORD *)(v3 + 8) )
        break;
LABEL_7:
      SwitchToThread();
    }
    while ( 1 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)v3, CurrentThreadId, 0);
      if ( !v6 || v6 == CurrentThreadId )
        break;
      if ( (unsigned int)++v4 >= *(_DWORD *)(v3 + 8) )
        goto LABEL_7;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 4));
    v1 = *((_DWORD *)a1 + 2);
  }
  *((_DWORD *)a1 + 2) = v1 + 1;
  return a1;
}

```

## disassembly

```asm
0x180002ff4  mov     [rsp+arg_0], rbx
0x180002ff9  mov     [rsp+arg_8], rsi
0x180002ffe  push    rdi
0x180002fff  sub     rsp, 20h
0x180003003  mov     eax, [rcx+8]
0x180003006  mov     rbx, rcx
0x180003009  test    eax, eax
0x18000300b  jnz     short loc_18000304D
0x18000300d  mov     rdi, [rcx]
0x180003010  xor     esi, esi
0x180003012  cmp     [rdi+8], esi
0x180003015  jbe     short loc_180003038
0x180003017  call    cs:__imp_GetCurrentThreadId
0x18000301e  nop     dword ptr [rax+rax+00h]
0x180003023  mov     ecx, eax
0x180003025  xor     eax, eax
0x180003027  lock cmpxchg [rdi], ecx
0x18000302b  jz      short loc_180003046
0x18000302d  cmp     eax, ecx
0x18000302f  jz      short loc_180003046
0x180003031  inc     esi
0x180003033  cmp     esi, [rdi+8]
0x180003036  jb      short loc_180003017
0x180003038  call    cs:__imp_SwitchToThread
0x18000303f  nop     dword ptr [rax+rax+00h]
0x180003044  jmp     short loc_180003010
0x180003046  lock inc dword ptr [rdi+4]
0x18000304a  mov     eax, [rbx+8]
0x18000304d  mov     rsi, [rsp+28h+arg_8]
0x180003052  inc     eax
0x180003054  mov     [rbx+8], eax
0x180003057  mov     rax, rbx
0x18000305a  mov     rbx, [rsp+28h+arg_0]
0x18000305f  add     rsp, 20h
0x180003063  pop     rdi
0x180003064  retn
```
