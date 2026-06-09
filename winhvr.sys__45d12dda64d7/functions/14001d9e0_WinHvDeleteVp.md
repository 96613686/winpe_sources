# WinHvDeleteVp

- ea: `0x14001d9e0`
- end: `0x14001da61`
- name: `WinHvDeleteVp`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001d900`

## callees

- `0x140002ce8`
- `0x140004564`
- `0x14001d9e0`
- `0x140023654`
- `0x14002648c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14001da24`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001da24`

## pseudocode

```c
__int64 __fastcall WinHvDeleteVp(__int64 a1, int a2)
{
  unsigned int v4; // ebx
  __int64 v6; // [rsp+20h] [rbp-18h] BYREF
  int v7; // [rsp+28h] [rbp-10h]
  int v8; // [rsp+2Ch] [rbp-Ch]

  v8 = 0;
  if ( WinHvpRootSchedulerActive )
    WinHvpDeleteVpObject();
  WinHvpInitializeFastHypercall(&v6);
  v6 = a1;
  v7 = a2;
  ExAcquireFastMutex(&WinHvpStatsTableLock);
  v4 = WinHvpFastHypercall(79, &v6);
  WinHvpCompleteVpStatsDelete(v4, a1, a2);
  return v4;
}

```

## disassembly

```asm
0x14001d9e0  mov     [rsp+arg_0], rbx
0x14001d9e5  mov     [rsp+arg_8], rsi
0x14001d9ea  push    rdi
0x14001d9eb  sub     rsp, 30h
0x14001d9ef  cmp     cs:WinHvpRootSchedulerActive, 0
0x14001d9f6  mov     edi, edx
0x14001d9f8  mov     rsi, rcx
0x14001d9fb  mov     [rsp+38h+var_C], 0
0x14001da03  jz      short loc_14001DA0A
0x14001da05  call    WinHvpDeleteVpObject
0x14001da0a  lea     rcx, [rsp+38h+var_18]
0x14001da0f  call    WinHvpInitializeFastHypercall
0x14001da14  lea     rcx, WinHvpStatsTableLock; FastMutex
0x14001da1b  mov     [rsp+38h+var_18], rsi
0x14001da20  mov     [rsp+38h+var_10], edi
0x14001da24  call    cs:__imp_ExAcquireFastMutex
0x14001da2b  nop     dword ptr [rax+rax+00h]
0x14001da30  lea     rdx, [rsp+38h+var_18]
0x14001da35  mov     ecx, 4Fh ; 'O'
0x14001da3a  call    WinHvpFastHypercall
0x14001da3f  mov     r8d, edi
0x14001da42  mov     rdx, rsi
0x14001da45  mov     ecx, eax
0x14001da47  mov     ebx, eax
0x14001da49  call    WinHvpCompleteVpStatsDelete
0x14001da4e  mov     rsi, [rsp+38h+arg_8]
0x14001da53  mov     eax, ebx
0x14001da55  mov     rbx, [rsp+38h+arg_0]
0x14001da5a  add     rsp, 30h
0x14001da5e  pop     rdi
0x14001da5f  retn
```
