# GuidNewSequentialidImpl

- ea: `0x1007dfd50`
- end: `0x1007dfeef`
- name: `GuidNewSequentialidImpl`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1007dfd30`

## callees

- `0x10045e890`
- `0x10045eb60`
- `0x1007dfd50`

## import_xrefs

- `RPCRT4!UuidCreateSequential` at `0x1007dfe20`
- `RPCRT4!UuidCreateSequential` at `0x1007dfe8b`
- `RPCRT4!UuidCreateSequential` at `0x1007dfe20`
- `RPCRT4!UuidCreateSequential` at `0x1007dfe8b`
- `sqldk!SystemThread_TlsIndex` at `0x1007dfdc2`
- `sqldk!SystemThread_TlsIndex` at `0x1007dfe31`
- `sqldk!SystemThread_TlsOffset` at `0x1007dfdcb`
- `sqldk!SystemThread_TlsOffset` at `0x1007dfe3a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1007dfde6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1007dfe54`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1007dfde6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1007dfe54`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007dfd67`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007dfd67`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007dfd7a`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007dfd7a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007dfd8d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007dfd8d`

## pseudocode

```c
void __fastcall GuidNewSequentialidImpl(__int64 a1, __int64 a2)
{
  struct CSessionTraceFlags *v3; // rax
  __int64 v4; // rdi
  __int64 v5; // rdx
  RPC_STATUS Sequential; // edi
  char v7; // cl
  char v8; // al
  char v9; // cl
  char v10; // al
  char v11; // cl
  char v12; // al
  char v13; // cl
  int v14; // [rsp+20h] [rbp-38h] BYREF
  __int64 v15; // [rsp+28h] [rbp-30h]
  __int64 v16; // [rsp+30h] [rbp-28h]
  __int64 v17; // [rsp+38h] [rbp-20h]
  __int64 v18; // [rsp+40h] [rbp-18h]

  if ( (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 1102) & 4) != 0
    || (v3 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v3, 0x2272u) )
  {
    Sequential = UuidCreateSequential((UUID *)(a2 + 8));
  }
  else
  {
    v14 = 4194733;
    v15 = 0;
    v17 = 0;
    v16 = 0;
    v18 = 0;
    v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v5 = *(_QWORD *)(v4 + 256);
    if ( !v5 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v5 = *(_QWORD *)(v4 + 256);
    }
    if ( v5 == qword_100AD9BA0 )
      ++qword_100AD9BB8;
    else
      ((void (__fastcall *)(void ***, __int64, __int64, int *))UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::LongWait)(
        &uuidCreateMutex,
        v5,
        0xFFFFFFFFLL,
        &v14);
    Sequential = UuidCreateSequential((UUID *)(a2 + 8));
    if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset
                    + 256LL) )
      SystemThread::MakeMiniSOSThread(0);
    if ( !--qword_100AD9BB8 )
    {
      qword_100AD9BA8 = 0;
      qword_100AD9BB0 = 0;
      qword_100AD9BA0 = 0;
      UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::WakeUpWaiters(&uuidCreateMutex);
    }
  }
  if ( !Sequential || Sequential == 1824 )
  {
    v7 = *(_BYTE *)(a2 + 10);
    *(_BYTE *)(a2 + 10) = *(_BYTE *)(a2 + 9);
    v8 = *(_BYTE *)(a2 + 8);
    *(_BYTE *)(a2 + 9) = v7;
    v9 = *(_BYTE *)(a2 + 11);
    *(_BYTE *)(a2 + 11) = v8;
    v10 = *(_BYTE *)(a2 + 13);
    *(_BYTE *)(a2 + 8) = v9;
    v11 = *(_BYTE *)(a2 + 12);
    *(_BYTE *)(a2 + 12) = v10;
    v12 = *(_BYTE *)(a2 + 15);
    *(_BYTE *)(a2 + 13) = v11;
    v13 = *(_BYTE *)(a2 + 14);
    *(_BYTE *)(a2 + 14) = v12;
    *(_BYTE *)(a2 + 15) = v13;
    *(_BYTE *)a2 = 0;
  }
}

```

## disassembly

```asm
0x1007dfd50  mov     [rsp+arg_8], rbx
0x1007dfd55  mov     [rsp+arg_10], rsi
0x1007dfd5a  push    rdi
0x1007dfd5b  sub     rsp, 50h
0x1007dfd5f  mov     [rsp+58h+arg_0], rbp
0x1007dfd64  mov     rsi, rdx
0x1007dfd67  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1007dfd6d  test    byte ptr [rax+44Eh], 4
0x1007dfd74  jnz     loc_1007DFE87
0x1007dfd7a  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x1007dfd80  test    rax, rax
0x1007dfd83  jz      short loc_1007DFD9B
0x1007dfd85  mov     edx, 2272h
0x1007dfd8a  mov     rcx, rax
0x1007dfd8d  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1007dfd93  test    eax, eax
0x1007dfd95  jnz     loc_1007DFE87
0x1007dfd9b  xor     ebp, ebp
0x1007dfd9d  mov     [rsp+58h+var_38], 4001ADh
0x1007dfda5  mov     [rsp+58h+var_30], rbp
0x1007dfdaa  mov     [rsp+58h+var_20], rbp
0x1007dfdaf  mov     [rsp+58h+var_28], rbp
0x1007dfdb4  mov     [rsp+58h+var_18], rbp
0x1007dfdb9  mov     rdx, gs:58h
0x1007dfdc2  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1007dfdc9  mov     ecx, [rax]
0x1007dfdcb  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1007dfdd2  mov     edi, [rax]
0x1007dfdd4  add     rdi, [rdx+rcx*8]
0x1007dfdd8  mov     rdx, [rdi+100h]
0x1007dfddf  test    rdx, rdx
0x1007dfde2  jnz     short loc_1007DFDF3
0x1007dfde4  xor     ecx, ecx
0x1007dfde6  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1007dfdec  mov     rdx, [rdi+100h]
0x1007dfdf3  cmp     rdx, cs:qword_100AD9BA0
0x1007dfdfa  jz      short loc_1007DFE15
0x1007dfdfc  lea     r9, [rsp+58h+var_38]
0x1007dfe01  mov     r8d, 0FFFFFFFFh
0x1007dfe07  lea     rcx, ?uuidCreateMutex@@3V?$UnfairRecursiveMutexInternal@USuspendQueueExpSLock@@$0A@@@A; UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0> uuidCreateMutex
0x1007dfe0e  call    ?LongWait@?$UnfairRecursiveMutexInternal@USuspendQueueExpSLock@@$0A@@@AEAA?AW4SOS_RESULT@@PEAVWorker@@KQEBVSOS_WaitInfo@@@Z; UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::LongWait(Worker *,ulong,SOS_WaitInfo const * const)
0x1007dfe13  jmp     short loc_1007DFE1C
0x1007dfe15  inc     cs:qword_100AD9BB8
0x1007dfe1c  lea     rcx, [rsi+8]; Uuid
0x1007dfe20  call    cs:__imp_UuidCreateSequential
0x1007dfe26  mov     r9, gs:58h
0x1007dfe2f  mov     edi, eax
0x1007dfe31  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x1007dfe38  mov     edx, [rcx]
0x1007dfe3a  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x1007dfe41  mov     rdx, [r9+rdx*8]
0x1007dfe45  mov     r8d, [rcx]
0x1007dfe48  cmp     [rdx+r8+100h], rbp
0x1007dfe50  jnz     short loc_1007DFE5A
0x1007dfe52  xor     ecx, ecx
0x1007dfe54  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1007dfe5a  sub     cs:qword_100AD9BB8, 1
0x1007dfe62  jnz     short loc_1007DFE93
0x1007dfe64  mov     cs:qword_100AD9BA8, rbp
0x1007dfe6b  lea     rcx, ?uuidCreateMutex@@3V?$UnfairRecursiveMutexInternal@USuspendQueueExpSLock@@$0A@@@A; UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0> uuidCreateMutex
0x1007dfe72  mov     cs:qword_100AD9BB0, rbp
0x1007dfe79  mov     cs:qword_100AD9BA0, rbp
0x1007dfe80  call    ?WakeUpWaiters@?$UnfairRecursiveMutexInternal@USuspendQueueExpSLock@@$0A@@@QEAAXXZ; UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::WakeUpWaiters(void)
0x1007dfe85  jmp     short loc_1007DFE93
0x1007dfe87  lea     rcx, [rsi+8]; Uuid
0x1007dfe8b  call    cs:__imp_UuidCreateSequential
0x1007dfe91  mov     edi, eax
0x1007dfe93  mov     rbp, [rsp+58h+arg_0]
0x1007dfe98  test    edi, edi
0x1007dfe9a  jz      short loc_1007DFEA4
0x1007dfe9c  cmp     edi, 720h
0x1007dfea2  jnz     short loc_1007DFEDF
0x1007dfea4  movzx   ecx, byte ptr [rsi+0Ah]
0x1007dfea8  movzx   eax, byte ptr [rsi+9]
0x1007dfeac  mov     [rsi+0Ah], al
0x1007dfeaf  movzx   eax, byte ptr [rsi+8]
0x1007dfeb3  mov     [rsi+9], cl
0x1007dfeb6  movzx   ecx, byte ptr [rsi+0Bh]
0x1007dfeba  mov     [rsi+0Bh], al
0x1007dfebd  movzx   eax, byte ptr [rsi+0Dh]
0x1007dfec1  mov     [rsi+8], cl
0x1007dfec4  movzx   ecx, byte ptr [rsi+0Ch]
0x1007dfec8  mov     [rsi+0Ch], al
0x1007dfecb  movzx   eax, byte ptr [rsi+0Fh]
0x1007dfecf  mov     [rsi+0Dh], cl
0x1007dfed2  movzx   ecx, byte ptr [rsi+0Eh]
0x1007dfed6  mov     [rsi+0Eh], al
0x1007dfed9  mov     [rsi+0Fh], cl
0x1007dfedc  mov     byte ptr [rsi], 0
0x1007dfedf  mov     rbx, [rsp+58h+arg_8]
0x1007dfee4  mov     rsi, [rsp+58h+arg_10]
0x1007dfee9  add     rsp, 50h
0x1007dfeed  pop     rdi
0x1007dfeee  retn
```
