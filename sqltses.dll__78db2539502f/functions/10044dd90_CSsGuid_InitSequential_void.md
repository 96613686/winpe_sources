# CSsGuid::InitSequential(void)

- ea: `0x10044dd90`
- end: `0x10044df30`
- name: `?InitSequential@CSsGuid@@QEAAHXZ`
- size: `416`
- prototype: `__int64 __fastcall(UUID *Uuid)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x10044dd90`
- `0x10045e890`
- `0x10045eb60`

## import_xrefs

- `RPCRT4!UuidCreateSequential` at `0x10044de5a`
- `RPCRT4!UuidCreateSequential` at `0x10044dec4`
- `RPCRT4!UuidCreateSequential` at `0x10044de5a`
- `RPCRT4!UuidCreateSequential` at `0x10044dec4`
- `sqldk!SystemThread_TlsIndex` at `0x10044ddfd`
- `sqldk!SystemThread_TlsIndex` at `0x10044de6b`
- `sqldk!SystemThread_TlsOffset` at `0x10044de06`
- `sqldk!SystemThread_TlsOffset` at `0x10044de74`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044de21`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044de8e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044de21`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044de8e`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10044dda2`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10044dda2`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10044ddb5`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10044ddb5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10044ddc8`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10044ddc8`

## pseudocode

```c
__int64 __fastcall CSsGuid::InitSequential(UUID *Uuid)
{
  struct CSessionTraceFlags *v2; // rax
  __int64 v3; // rdi
  __int64 v4; // rdx
  RPC_STATUS Sequential; // edi
  __int64 result; // rax
  char v7; // cl
  char Data1; // al
  char Data1_high; // cl
  char Data2_high; // al
  char Data2; // cl
  char Data3_high; // al
  char Data3; // cl
  int v14; // [rsp+20h] [rbp-38h] BYREF
  __int64 v15; // [rsp+28h] [rbp-30h]
  __int64 v16; // [rsp+30h] [rbp-28h]
  __int64 v17; // [rsp+38h] [rbp-20h]
  __int64 v18; // [rsp+40h] [rbp-18h]

  if ( (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 1102) & 4) != 0
    || (v2 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v2, 0x2272u) )
  {
    Sequential = UuidCreateSequential(Uuid);
  }
  else
  {
    v14 = 4194733;
    v15 = 0;
    v17 = 0;
    v16 = 0;
    v18 = 0;
    v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v4 = *(_QWORD *)(v3 + 256);
    if ( !v4 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v4 = *(_QWORD *)(v3 + 256);
    }
    if ( v4 == qword_100AD9BA0 )
      ++qword_100AD9BB8;
    else
      ((void (__fastcall *)(void ***, __int64, __int64, int *))UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::LongWait)(
        &uuidCreateMutex,
        v4,
        0xFFFFFFFFLL,
        &v14);
    Sequential = UuidCreateSequential(Uuid);
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
  if ( Sequential && Sequential != 1824 )
    return 0;
  v7 = BYTE2(Uuid->Data1);
  BYTE2(Uuid->Data1) = BYTE1(Uuid->Data1);
  Data1 = Uuid->Data1;
  BYTE1(Uuid->Data1) = v7;
  Data1_high = HIBYTE(Uuid->Data1);
  HIBYTE(Uuid->Data1) = Data1;
  Data2_high = HIBYTE(Uuid->Data2);
  LOBYTE(Uuid->Data1) = Data1_high;
  Data2 = Uuid->Data2;
  LOBYTE(Uuid->Data2) = Data2_high;
  Data3_high = HIBYTE(Uuid->Data3);
  HIBYTE(Uuid->Data2) = Data2;
  Data3 = Uuid->Data3;
  LOBYTE(Uuid->Data3) = Data3_high;
  result = 1;
  HIBYTE(Uuid->Data3) = Data3;
  return result;
}

```

## disassembly

```asm
0x10044dd90  mov     [rsp+arg_8], rbx
0x10044dd95  push    rdi
0x10044dd96  sub     rsp, 50h
0x10044dd9a  mov     [rsp+58h+arg_0], rsi
0x10044dd9f  mov     rbx, rcx
0x10044dda2  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10044dda8  test    byte ptr [rax+44Eh], 4
0x10044ddaf  jnz     loc_10044DEC1
0x10044ddb5  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10044ddbb  test    rax, rax
0x10044ddbe  jz      short loc_10044DDD6
0x10044ddc0  mov     edx, 2272h
0x10044ddc5  mov     rcx, rax
0x10044ddc8  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10044ddce  test    eax, eax
0x10044ddd0  jnz     loc_10044DEC1
0x10044ddd6  xor     esi, esi
0x10044ddd8  mov     [rsp+58h+var_38], 4001ADh
0x10044dde0  mov     [rsp+58h+var_30], rsi
0x10044dde5  mov     [rsp+58h+var_20], rsi
0x10044ddea  mov     [rsp+58h+var_28], rsi
0x10044ddef  mov     [rsp+58h+var_18], rsi
0x10044ddf4  mov     rdx, gs:58h
0x10044ddfd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044de04  mov     ecx, [rax]
0x10044de06  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044de0d  mov     edi, [rax]
0x10044de0f  add     rdi, [rdx+rcx*8]
0x10044de13  mov     rdx, [rdi+100h]
0x10044de1a  test    rdx, rdx
0x10044de1d  jnz     short loc_10044DE2E
0x10044de1f  xor     ecx, ecx
0x10044de21  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044de27  mov     rdx, [rdi+100h]
0x10044de2e  cmp     rdx, cs:qword_100AD9BA0
0x10044de35  jz      short loc_10044DE50
0x10044de37  lea     r9, [rsp+58h+var_38]
0x10044de3c  mov     r8d, 0FFFFFFFFh
0x10044de42  lea     rcx, ?uuidCreateMutex@@3V?$UnfairRecursiveMutexInternal@USuspendQueueExpSLock@@$0A@@@A; UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0> uuidCreateMutex
0x10044de49  call    ?LongWait@?$UnfairRecursiveMutexInternal@USuspendQueueExpSLock@@$0A@@@AEAA?AW4SOS_RESULT@@PEAVWorker@@KQEBVSOS_WaitInfo@@@Z; UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::LongWait(Worker *,ulong,SOS_WaitInfo const * const)
0x10044de4e  jmp     short loc_10044DE57
0x10044de50  inc     cs:qword_100AD9BB8
0x10044de57  mov     rcx, rbx; Uuid
0x10044de5a  call    cs:__imp_UuidCreateSequential
0x10044de60  mov     r9, gs:58h
0x10044de69  mov     edi, eax
0x10044de6b  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x10044de72  mov     edx, [rcx]
0x10044de74  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10044de7b  mov     rdx, [r9+rdx*8]
0x10044de7f  mov     r8d, [rcx]
0x10044de82  cmp     [rdx+r8+100h], rsi
0x10044de8a  jnz     short loc_10044DE94
0x10044de8c  xor     ecx, ecx
0x10044de8e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044de94  sub     cs:qword_100AD9BB8, 1
0x10044de9c  jnz     short loc_10044DECC
0x10044de9e  mov     cs:qword_100AD9BA8, rsi
0x10044dea5  lea     rcx, ?uuidCreateMutex@@3V?$UnfairRecursiveMutexInternal@USuspendQueueExpSLock@@$0A@@@A; UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0> uuidCreateMutex
0x10044deac  mov     cs:qword_100AD9BB0, rsi
0x10044deb3  mov     cs:qword_100AD9BA0, rsi
0x10044deba  call    ?WakeUpWaiters@?$UnfairRecursiveMutexInternal@USuspendQueueExpSLock@@$0A@@@QEAAXXZ; UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::WakeUpWaiters(void)
0x10044debf  jmp     short loc_10044DECC
0x10044dec1  mov     rcx, rbx; Uuid
0x10044dec4  call    cs:__imp_UuidCreateSequential
0x10044deca  mov     edi, eax
0x10044decc  mov     rsi, [rsp+58h+arg_0]
0x10044ded1  test    edi, edi
0x10044ded3  jz      short loc_10044DEEA
0x10044ded5  cmp     edi, 720h
0x10044dedb  jz      short loc_10044DEEA
0x10044dedd  xor     eax, eax
0x10044dedf  mov     rbx, [rsp+58h+arg_8]
0x10044dee4  add     rsp, 50h
0x10044dee8  pop     rdi
0x10044dee9  retn
0x10044deea  movzx   eax, byte ptr [rbx+1]
0x10044deee  movzx   ecx, byte ptr [rbx+2]
0x10044def2  mov     [rbx+2], al
0x10044def5  movzx   eax, byte ptr [rbx]
0x10044def8  mov     [rbx+1], cl
0x10044defb  movzx   ecx, byte ptr [rbx+3]
0x10044deff  mov     [rbx+3], al
0x10044df02  movzx   eax, byte ptr [rbx+5]
0x10044df06  mov     [rbx], cl
0x10044df08  movzx   ecx, byte ptr [rbx+4]
0x10044df0c  mov     [rbx+4], al
0x10044df0f  movzx   eax, byte ptr [rbx+7]
0x10044df13  mov     [rbx+5], cl
0x10044df16  movzx   ecx, byte ptr [rbx+6]
0x10044df1a  mov     [rbx+6], al
0x10044df1d  mov     eax, 1
0x10044df22  mov     [rbx+7], cl
0x10044df25  mov     rbx, [rsp+58h+arg_8]
0x10044df2a  add     rsp, 50h
0x10044df2e  pop     rdi
0x10044df2f  retn
```
