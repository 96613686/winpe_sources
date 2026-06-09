# TList<NodeManager,SOS_Node,16,TListSLock>::GetTail(void)

- ea: `0x10040ad90`
- end: `0x10040af62`
- name: `?GetTail@?$TList@VNodeManager@@VSOS_Node@@$0BA@UTListSLock@@@@QEAAPEAVSOS_Node@@XZ`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10040ca90`

## callees

- `0x100408910`
- `0x100408b50`
- `0x100408e00`
- `0x10040ad90`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10040ae32`
- `KERNEL32!QueryPerformanceCounter` at `0x10040ae85`
- `KERNEL32!QueryPerformanceCounter` at `0x10040ae32`
- `KERNEL32!QueryPerformanceCounter` at `0x10040ae85`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10040ae47`
- `sqldk!SystemThread_TlsOffset` at `0x10040adfd`
- `sqldk!SystemThread_TlsIndex` at `0x10040adf4`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040ae22`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040ae74`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040af18`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040add0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040af29`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040af29`

## pseudocode

```c
__int64 __fastcall TList<NodeManager,SOS_Node,16,TListSLock>::GetTail(__int64 a1)
{
  volatile signed __int64 *v1; // r14
  LARGE_INTEGER v2; // rbx
  signed __int64 UniqueThread_low; // rbp
  __int64 v5; // rdi
  __int64 v6; // r8
  LARGE_INTEGER v7; // rcx
  LONGLONG v8; // rax
  __int64 v9; // rbx
  signed __int32 v10; // ecx
  __int64 v11; // rcx
  int v12; // eax
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp+8h] BYREF
  LARGE_INTEGER v15; // [rsp+58h] [rbp+10h] BYREF

  v1 = (volatile signed __int64 *)(a1 + 16);
  v2.QuadPart = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)(a1 + 16) || _InterlockedCompareExchange64(v1, UniqueThread_low, 0) )
  {
    v5 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v6 && *(_QWORD *)(v6 + 272) == v6 )
        v5 = *(_QWORD *)(v6 + 256);
      if ( v5 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v2 = PerformanceCount;
        }
        else
        {
          v2.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(v1, UniqueThread_low);
    else
      Spinlock<19,1,268435714>::SpinToAcquireOptimistic((SpinlockBase *)v1, v5, UniqueThread_low);
    if ( v5 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v15);
        v7 = v15;
      }
      else
      {
        v7.QuadPart = MEMORY[0x7FFE0008];
      }
      v8 = 0;
      if ( v7.QuadPart >= (unsigned __int64)v2.QuadPart )
        v8 = v7.QuadPart - v2.QuadPart;
      *(_QWORD *)(v5 + 3192) += v8;
    }
  }
  v9 = 0;
  if ( *(_QWORD *)(a1 + 8) != a1 )
  {
    if ( *(_QWORD *)a1 )
      v9 = *(_QWORD *)a1 - 16LL;
    if ( v9 )
    {
      while ( 1 )
      {
        v10 = *(_DWORD *)(v9 + 40);
        if ( v10 )
        {
          while ( v10 != _InterlockedCompareExchange((volatile signed __int32 *)(v9 + 40), v10 + 1, v10) )
          {
            _mm_pause();
            v10 = *(_DWORD *)(v9 + 40);
            if ( !v10 )
              goto LABEL_30;
          }
          if ( v10 != -1 )
            break;
        }
LABEL_30:
        v11 = *(_QWORD *)(v9 + 16);
        v9 = 0;
        if ( v11 != a1 )
        {
          if ( v11 )
            v9 = v11 - 16;
          if ( v9 )
            continue;
        }
        break;
      }
    }
  }
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v12 = rand();
    if ( v12 == 5 * (v12 / 5) )
      Spinlock<19,1,268435714>::UpdateStatSnapshot();
  }
  *v1 = 0;
  return v9;
}

```

## disassembly

```asm
0x10040ad90  push    rbx
0x10040ad92  push    r14
0x10040ad94  sub     rsp, 38h
0x10040ad98  mov     eax, gs:48h
0x10040ada0  lea     r14, [rcx+10h]
0x10040ada4  mov     [rsp+48h+var_18], rbp
0x10040ada9  xor     ebx, ebx
0x10040adab  mov     ebp, eax
0x10040adad  mov     eax, [r14]
0x10040adb0  mov     [rsp+48h+var_20], rsi
0x10040adb5  mov     rsi, rcx
0x10040adb8  test    eax, eax
0x10040adba  jnz     short loc_10040ADD0
0x10040adbc  xor     eax, eax
0x10040adbe  lock cmpxchg [r14], rbp
0x10040adc3  mov     eax, ebx
0x10040adc5  setz    al
0x10040adc8  test    eax, eax
0x10040adca  jnz     loc_10040AEB5
0x10040add0  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040add7  mov     [rsp+48h+var_28], rdi
0x10040addc  xor     edi, edi
0x10040adde  mov     ecx, [rax]
0x10040ade0  and     ecx, 84h
0x10040ade6  cmp     cl, 84h
0x10040ade9  jnz     short loc_10040AE47
0x10040adeb  mov     rdx, gs:58h
0x10040adf4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040adfb  mov     ecx, [rax]
0x10040adfd  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040ae04  mov     r8d, [rax]
0x10040ae07  add     r8, [rdx+rcx*8]
0x10040ae0b  jz      short loc_10040AE1D
0x10040ae0d  cmp     [r8+110h], r8
0x10040ae14  jnz     short loc_10040AE1D
0x10040ae16  mov     rdi, [r8+100h]
0x10040ae1d  test    rdi, rdi
0x10040ae20  jz      short loc_10040AE47
0x10040ae22  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040ae29  cmp     [rax], ebx
0x10040ae2b  jz      short loc_10040AE3F
0x10040ae2d  lea     rcx, [rsp+48h+PerformanceCount]; lpPerformanceCount
0x10040ae32  call    cs:__imp_QueryPerformanceCounter
0x10040ae38  mov     rbx, qword ptr [rsp+48h+PerformanceCount]
0x10040ae3d  jmp     short loc_10040AE47
0x10040ae3f  mov     rbx, ds:7FFE0008h
0x10040ae47  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10040ae4e  mov     rcx, r14
0x10040ae51  cmp     byte ptr [rax+0C7h], 0
0x10040ae58  jge     short loc_10040AE67
0x10040ae5a  mov     r8, rbp
0x10040ae5d  mov     rdx, rdi
0x10040ae60  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10040ae65  jmp     short loc_10040AE6F
0x10040ae67  mov     rdx, rbp
0x10040ae6a  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10040ae6f  test    rdi, rdi
0x10040ae72  jz      short loc_10040AEB0
0x10040ae74  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040ae7b  cmp     dword ptr [rax], 0
0x10040ae7e  jz      short loc_10040AE92
0x10040ae80  lea     rcx, [rsp+48h+arg_8]; lpPerformanceCount
0x10040ae85  call    cs:__imp_QueryPerformanceCounter
0x10040ae8b  mov     rcx, qword ptr [rsp+48h+arg_8]
0x10040ae90  jmp     short loc_10040AE9A
0x10040ae92  mov     rcx, ds:7FFE0008h
0x10040ae9a  xor     eax, eax
0x10040ae9c  mov     rdx, rcx
0x10040ae9f  sub     rdx, rbx
0x10040aea2  cmp     rcx, rbx
0x10040aea5  cmovnb  rax, rdx
0x10040aea9  add     [rdi+0C78h], rax
0x10040aeb0  mov     rdi, [rsp+48h+var_28]
0x10040aeb5  mov     rbp, [rsp+48h+var_18]
0x10040aeba  xor     ebx, ebx
0x10040aebc  cmp     [rsi+8], rsi
0x10040aec0  jz      short loc_10040AF18
0x10040aec2  mov     rcx, [rsi]
0x10040aec5  test    rcx, rcx
0x10040aec8  lea     rax, [rcx-10h]
0x10040aecc  cmovnz  rbx, rax
0x10040aed0  test    rbx, rbx
0x10040aed3  jz      short loc_10040AF18
0x10040aed5  mov     ecx, [rbx+28h]
0x10040aed8  test    ecx, ecx
0x10040aeda  jz      short loc_10040AEFD
0x10040aedc  nop     dword ptr [rax]
0x10040aedf  nop
0x10040aee0  lea     edx, [rcx+1]
0x10040aee3  mov     eax, ecx
0x10040aee5  lock cmpxchg [rbx+28h], edx
0x10040aeea  cmp     ecx, eax
0x10040aeec  jz      short loc_10040AEF9
0x10040aeee  pause
0x10040aef0  mov     ecx, [rbx+28h]
0x10040aef3  test    ecx, ecx
0x10040aef5  jnz     short loc_10040AEE0
0x10040aef7  jmp     short loc_10040AEFD
0x10040aef9  test    edx, edx
0x10040aefb  jnz     short loc_10040AF18
0x10040aefd  mov     rcx, [rbx+10h]
0x10040af01  xor     ebx, ebx
0x10040af03  cmp     rcx, rsi
0x10040af06  jz      short loc_10040AF18
0x10040af08  test    rcx, rcx
0x10040af0b  lea     rax, [rcx-10h]
0x10040af0f  cmovnz  rbx, rax
0x10040af13  test    rbx, rbx
0x10040af16  jnz     short loc_10040AED5
0x10040af18  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10040af1f  mov     rsi, [rsp+48h+var_20]
0x10040af24  cmp     byte ptr [rax], 0
0x10040af27  jz      short loc_10040AF50
0x10040af29  call    cs:__imp_rand
0x10040af2f  mov     r8d, eax
0x10040af32  mov     eax, 66666667h
0x10040af37  imul    r8d
0x10040af3a  sar     edx, 1
0x10040af3c  mov     ecx, edx
0x10040af3e  shr     ecx, 1Fh
0x10040af41  add     edx, ecx
0x10040af43  lea     ecx, [rdx+rdx*4]
0x10040af46  cmp     r8d, ecx
0x10040af49  jnz     short loc_10040AF50
0x10040af4b  call    ?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<19,1,268435714>::UpdateStatSnapshot(void)
0x10040af50  mov     qword ptr [r14], 0
0x10040af57  mov     rax, rbx
0x10040af5a  add     rsp, 38h
0x10040af5e  pop     r14
0x10040af60  pop     rbx
0x10040af61  retn
```
