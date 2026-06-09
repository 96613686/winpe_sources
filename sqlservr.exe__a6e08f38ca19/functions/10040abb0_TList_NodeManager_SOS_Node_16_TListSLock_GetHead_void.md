# TList<NodeManager,SOS_Node,16,TListSLock>::GetHead(void)

- ea: `0x10040abb0`
- end: `0x10040ad82`
- name: `?GetHead@?$TList@VNodeManager@@VSOS_Node@@$0BA@UTListSLock@@@@QEAAPEAVSOS_Node@@XZ`
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
- `0x10040abb0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10040ac52`
- `KERNEL32!QueryPerformanceCounter` at `0x10040aca5`
- `KERNEL32!QueryPerformanceCounter` at `0x10040ac52`
- `KERNEL32!QueryPerformanceCounter` at `0x10040aca5`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10040ac67`
- `sqldk!SystemThread_TlsOffset` at `0x10040ac1d`
- `sqldk!SystemThread_TlsIndex` at `0x10040ac14`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040ac42`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040ac94`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040ad38`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040abf0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040ad49`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040ad49`

## pseudocode

```c
__int64 __fastcall TList<NodeManager,SOS_Node,16,TListSLock>::GetHead(__int64 a1)
{
  volatile signed __int64 *v1; // r14
  LARGE_INTEGER v2; // rbx
  signed __int64 UniqueThread_low; // rbp
  __int64 v5; // rdi
  __int64 v6; // r8
  LARGE_INTEGER v7; // rcx
  LONGLONG v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rbx
  signed __int32 v11; // ecx
  __int64 v12; // rcx
  int v13; // eax
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp+8h] BYREF
  LARGE_INTEGER v16; // [rsp+58h] [rbp+10h] BYREF

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
        QueryPerformanceCounter(&v16);
        v7 = v16;
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
  v9 = *(_QWORD *)(a1 + 8);
  v10 = 0;
  if ( v9 != a1 )
  {
    if ( v9 )
      v10 = v9 - 16;
    if ( v10 )
    {
      while ( 1 )
      {
        v11 = *(_DWORD *)(v10 + 40);
        if ( v11 )
        {
          while ( v11 != _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 40), v11 + 1, v11) )
          {
            _mm_pause();
            v11 = *(_DWORD *)(v10 + 40);
            if ( !v11 )
              goto LABEL_30;
          }
          if ( v11 != -1 )
            break;
        }
LABEL_30:
        v12 = *(_QWORD *)(v10 + 24);
        v10 = 0;
        if ( v12 != a1 )
        {
          if ( v12 )
            v10 = v12 - 16;
          if ( v10 )
            continue;
        }
        break;
      }
    }
  }
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v13 = rand();
    if ( v13 == 5 * (v13 / 5) )
      Spinlock<19,1,268435714>::UpdateStatSnapshot();
  }
  *v1 = 0;
  return v10;
}

```

## disassembly

```asm
0x10040abb0  push    rbx
0x10040abb2  push    r14
0x10040abb4  sub     rsp, 38h
0x10040abb8  mov     eax, gs:48h
0x10040abc0  lea     r14, [rcx+10h]
0x10040abc4  mov     [rsp+48h+var_18], rbp
0x10040abc9  xor     ebx, ebx
0x10040abcb  mov     ebp, eax
0x10040abcd  mov     eax, [r14]
0x10040abd0  mov     [rsp+48h+var_20], rsi
0x10040abd5  mov     rsi, rcx
0x10040abd8  test    eax, eax
0x10040abda  jnz     short loc_10040ABF0
0x10040abdc  xor     eax, eax
0x10040abde  lock cmpxchg [r14], rbp
0x10040abe3  mov     eax, ebx
0x10040abe5  setz    al
0x10040abe8  test    eax, eax
0x10040abea  jnz     loc_10040ACD5
0x10040abf0  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040abf7  mov     [rsp+48h+var_28], rdi
0x10040abfc  xor     edi, edi
0x10040abfe  mov     ecx, [rax]
0x10040ac00  and     ecx, 84h
0x10040ac06  cmp     cl, 84h
0x10040ac09  jnz     short loc_10040AC67
0x10040ac0b  mov     rdx, gs:58h
0x10040ac14  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040ac1b  mov     ecx, [rax]
0x10040ac1d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040ac24  mov     r8d, [rax]
0x10040ac27  add     r8, [rdx+rcx*8]
0x10040ac2b  jz      short loc_10040AC3D
0x10040ac2d  cmp     [r8+110h], r8
0x10040ac34  jnz     short loc_10040AC3D
0x10040ac36  mov     rdi, [r8+100h]
0x10040ac3d  test    rdi, rdi
0x10040ac40  jz      short loc_10040AC67
0x10040ac42  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040ac49  cmp     [rax], ebx
0x10040ac4b  jz      short loc_10040AC5F
0x10040ac4d  lea     rcx, [rsp+48h+PerformanceCount]; lpPerformanceCount
0x10040ac52  call    cs:__imp_QueryPerformanceCounter
0x10040ac58  mov     rbx, qword ptr [rsp+48h+PerformanceCount]
0x10040ac5d  jmp     short loc_10040AC67
0x10040ac5f  mov     rbx, ds:7FFE0008h
0x10040ac67  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10040ac6e  mov     rcx, r14
0x10040ac71  cmp     byte ptr [rax+0C7h], 0
0x10040ac78  jge     short loc_10040AC87
0x10040ac7a  mov     r8, rbp
0x10040ac7d  mov     rdx, rdi
0x10040ac80  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10040ac85  jmp     short loc_10040AC8F
0x10040ac87  mov     rdx, rbp
0x10040ac8a  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10040ac8f  test    rdi, rdi
0x10040ac92  jz      short loc_10040ACD0
0x10040ac94  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040ac9b  cmp     dword ptr [rax], 0
0x10040ac9e  jz      short loc_10040ACB2
0x10040aca0  lea     rcx, [rsp+48h+arg_8]; lpPerformanceCount
0x10040aca5  call    cs:__imp_QueryPerformanceCounter
0x10040acab  mov     rcx, qword ptr [rsp+48h+arg_8]
0x10040acb0  jmp     short loc_10040ACBA
0x10040acb2  mov     rcx, ds:7FFE0008h
0x10040acba  xor     eax, eax
0x10040acbc  mov     rdx, rcx
0x10040acbf  sub     rdx, rbx
0x10040acc2  cmp     rcx, rbx
0x10040acc5  cmovnb  rax, rdx
0x10040acc9  add     [rdi+0C78h], rax
0x10040acd0  mov     rdi, [rsp+48h+var_28]
0x10040acd5  mov     rcx, [rsi+8]
0x10040acd9  xor     ebx, ebx
0x10040acdb  mov     rbp, [rsp+48h+var_18]
0x10040ace0  cmp     rcx, rsi
0x10040ace3  jz      short loc_10040AD38
0x10040ace5  test    rcx, rcx
0x10040ace8  lea     rax, [rcx-10h]
0x10040acec  cmovnz  rbx, rax
0x10040acf0  test    rbx, rbx
0x10040acf3  jz      short loc_10040AD38
0x10040acf5  mov     ecx, [rbx+28h]
0x10040acf8  test    ecx, ecx
0x10040acfa  jz      short loc_10040AD1D
0x10040acfc  nop     dword ptr [rax]
0x10040acff  nop
0x10040ad00  lea     edx, [rcx+1]
0x10040ad03  mov     eax, ecx
0x10040ad05  lock cmpxchg [rbx+28h], edx
0x10040ad0a  cmp     ecx, eax
0x10040ad0c  jz      short loc_10040AD19
0x10040ad0e  pause
0x10040ad10  mov     ecx, [rbx+28h]
0x10040ad13  test    ecx, ecx
0x10040ad15  jnz     short loc_10040AD00
0x10040ad17  jmp     short loc_10040AD1D
0x10040ad19  test    edx, edx
0x10040ad1b  jnz     short loc_10040AD38
0x10040ad1d  mov     rcx, [rbx+18h]
0x10040ad21  xor     ebx, ebx
0x10040ad23  cmp     rcx, rsi
0x10040ad26  jz      short loc_10040AD38
0x10040ad28  test    rcx, rcx
0x10040ad2b  lea     rax, [rcx-10h]
0x10040ad2f  cmovnz  rbx, rax
0x10040ad33  test    rbx, rbx
0x10040ad36  jnz     short loc_10040ACF5
0x10040ad38  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10040ad3f  mov     rsi, [rsp+48h+var_20]
0x10040ad44  cmp     byte ptr [rax], 0
0x10040ad47  jz      short loc_10040AD70
0x10040ad49  call    cs:__imp_rand
0x10040ad4f  mov     r8d, eax
0x10040ad52  mov     eax, 66666667h
0x10040ad57  imul    r8d
0x10040ad5a  sar     edx, 1
0x10040ad5c  mov     ecx, edx
0x10040ad5e  shr     ecx, 1Fh
0x10040ad61  add     edx, ecx
0x10040ad63  lea     ecx, [rdx+rdx*4]
0x10040ad66  cmp     r8d, ecx
0x10040ad69  jnz     short loc_10040AD70
0x10040ad6b  call    ?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<19,1,268435714>::UpdateStatSnapshot(void)
0x10040ad70  mov     qword ptr [r14], 0
0x10040ad77  mov     rax, rbx
0x10040ad7a  add     rsp, 38h
0x10040ad7e  pop     r14
0x10040ad80  pop     rbx
0x10040ad81  retn
```
