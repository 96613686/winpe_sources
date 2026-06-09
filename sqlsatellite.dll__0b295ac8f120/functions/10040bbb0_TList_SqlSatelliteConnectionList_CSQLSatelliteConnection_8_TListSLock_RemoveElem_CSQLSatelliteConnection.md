# TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(CSQLSatelliteConnection *)

- ea: `0x10040bbb0`
- end: `0x10040bd4f`
- name: `?RemoveElem@?$TList@VSqlSatelliteConnectionList@@VCSQLSatelliteConnection@@$07UTListSLock@@@@QEAAXPEAVCSQLSatelliteConnection@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `27`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1004083a0`
- `0x100408710`
- `0x100408800`
- `0x10040a520`
- `0x10040af40`
- `0x10040b850`
- `0x10040b8a0`
- `0x10046ffe0`
- `0x100470280`
- `0x100470c20`
- `0x100471ab0`
- `0x100471d80`
- `0x100472000`
- `0x1004723b0`
- `0x100472490`
- `0x100472580`
- `0x100473980`
- `0x1004739f0`
- `0x100473a60`
- `0x100475aa0`
- `0x100475c00`
- `0x100475fd0`
- `0x100476570`
- `0x100476740`
- `0x100476c60`
- `0x10047ede0`
- `0x10047ef60`

## callees

- `0x100403420`
- `0x100403520`
- `0x100403760`
- `0x10040bbb0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10040bc61`
- `KERNEL32!QueryPerformanceCounter` at `0x10040bcb4`
- `KERNEL32!QueryPerformanceCounter` at `0x10040bc61`
- `KERNEL32!QueryPerformanceCounter` at `0x10040bcb4`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040bcfb`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040bc51`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040bca3`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10040bc76`
- `sqldk!SystemThread_TlsIndex` at `0x10040bc23`
- `sqldk!SystemThread_TlsOffset` at `0x10040bc2c`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040bbfe`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040bd18`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040bd18`

## pseudocode

```c
__int64 __fastcall TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(
        __int64 a1,
        _QWORD *a2)
{
  volatile signed __int64 *v2; // rdi
  signed __int64 UniqueThread_low; // r14
  LARGE_INTEGER v5; // rbx
  __int64 v7; // rbp
  __int64 v8; // r8
  LARGE_INTEGER v9; // rax
  LONGLONG v10; // rcx
  __int64 v11; // rax
  _QWORD *v12; // rcx
  __int64 result; // rax
  int v14; // r8d
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp+8h] BYREF
  LARGE_INTEGER v16; // [rsp+68h] [rbp+10h] BYREF

  v2 = (volatile signed __int64 *)(a1 + 16);
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  v5.QuadPart = 0;
  if ( *(_DWORD *)(a1 + 16) || _InterlockedCompareExchange64(v2, UniqueThread_low, 0) )
  {
    v7 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v8 && *(_QWORD *)(v8 + 272) == v8 )
        v7 = *(_QWORD *)(v8 + 256);
      if ( v7 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v5 = PerformanceCount;
        }
        else
        {
          v5.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(v2, UniqueThread_low);
    else
      Spinlock<19,1,268435714>::SpinToAcquireOptimistic(v2, v7, UniqueThread_low);
    if ( v7 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v16);
        v9 = v16;
      }
      else
      {
        v9.QuadPart = MEMORY[0x7FFE0008];
      }
      v10 = v9.QuadPart - v5.QuadPart;
      if ( v9.QuadPart < (unsigned __int64)v5.QuadPart )
        v10 = 0;
      *(_QWORD *)(v7 + 3192) += v10;
    }
  }
  v11 = a2[1];
  v12 = (_QWORD *)a2[2];
  *(_QWORD *)(v11 + 8) = v12;
  *v12 = v11;
  result = *(_QWORD *)&SOS_PublicGlobals::sm_SpinlockStatSnapshot;
  a2[2] = 0;
  a2[1] = 0;
  --*(_DWORD *)(a1 + 24);
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v14 = rand();
    result = (unsigned int)(1717986919 * v14);
    if ( v14 == 5 * (v14 / 5) )
      result = Spinlock<19,1,268435714>::UpdateStatSnapshot();
  }
  *v2 = 0;
  a2[3] = 0;
  return result;
}

```

## disassembly

```asm
0x10040bbb0  push    rsi
0x10040bbb2  push    rdi
0x10040bbb3  push    r12
0x10040bbb5  sub     rsp, 40h
0x10040bbb9  mov     eax, gs:48h
0x10040bbc1  lea     rdi, [rcx+10h]
0x10040bbc5  mov     [rsp+58h+var_20], rbx
0x10040bbca  xor     r12d, r12d
0x10040bbcd  mov     [rsp+58h+var_30], r14
0x10040bbd2  mov     rsi, rdx
0x10040bbd5  mov     r14d, eax
0x10040bbd8  mov     ebx, r12d
0x10040bbdb  mov     eax, [rdi]
0x10040bbdd  mov     [rsp+58h+var_38], r15
0x10040bbe2  mov     r15, rcx
0x10040bbe5  test    eax, eax
0x10040bbe7  jnz     short loc_10040BBFE
0x10040bbe9  xor     eax, eax
0x10040bbeb  lock cmpxchg [rdi], r14
0x10040bbf0  mov     eax, r12d
0x10040bbf3  setz    al
0x10040bbf6  test    eax, eax
0x10040bbf8  jnz     loc_10040BCE2
0x10040bbfe  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040bc05  mov     [rsp+58h+var_28], rbp
0x10040bc0a  mov     rbp, r12
0x10040bc0d  mov     ecx, [rax]
0x10040bc0f  and     ecx, 84h
0x10040bc15  cmp     cl, 84h
0x10040bc18  jnz     short loc_10040BC76
0x10040bc1a  mov     rdx, gs:58h
0x10040bc23  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040bc2a  mov     ecx, [rax]
0x10040bc2c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040bc33  mov     r8d, [rax]
0x10040bc36  add     r8, [rdx+rcx*8]
0x10040bc3a  jz      short loc_10040BC4C
0x10040bc3c  cmp     [r8+110h], r8
0x10040bc43  jnz     short loc_10040BC4C
0x10040bc45  mov     rbp, [r8+100h]
0x10040bc4c  test    rbp, rbp
0x10040bc4f  jz      short loc_10040BC76
0x10040bc51  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040bc58  cmp     [rax], ebx
0x10040bc5a  jz      short loc_10040BC6E
0x10040bc5c  lea     rcx, [rsp+58h+PerformanceCount]; lpPerformanceCount
0x10040bc61  call    cs:__imp_QueryPerformanceCounter
0x10040bc67  mov     rbx, qword ptr [rsp+58h+PerformanceCount]
0x10040bc6c  jmp     short loc_10040BC76
0x10040bc6e  mov     rbx, ds:7FFE0008h
0x10040bc76  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10040bc7d  mov     rcx, rdi
0x10040bc80  cmp     [rax+0C7h], r12b
0x10040bc87  jge     short loc_10040BC96
0x10040bc89  mov     r8, r14
0x10040bc8c  mov     rdx, rbp
0x10040bc8f  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10040bc94  jmp     short loc_10040BC9E
0x10040bc96  mov     rdx, r14
0x10040bc99  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10040bc9e  test    rbp, rbp
0x10040bca1  jz      short loc_10040BCDD
0x10040bca3  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040bcaa  cmp     [rax], r12d
0x10040bcad  jz      short loc_10040BCC1
0x10040bcaf  lea     rcx, [rsp+58h+arg_8]; lpPerformanceCount
0x10040bcb4  call    cs:__imp_QueryPerformanceCounter
0x10040bcba  mov     rax, qword ptr [rsp+58h+arg_8]
0x10040bcbf  jmp     short loc_10040BCC9
0x10040bcc1  mov     rax, ds:7FFE0008h
0x10040bcc9  mov     rcx, rax
0x10040bccc  sub     rcx, rbx
0x10040bccf  cmp     rax, rbx
0x10040bcd2  cmovb   rcx, r12
0x10040bcd6  add     [rbp+0C78h], rcx
0x10040bcdd  mov     rbp, [rsp+58h+var_28]
0x10040bce2  mov     rax, [rsi+8]
0x10040bce6  mov     rcx, [rsi+10h]
0x10040bcea  mov     r14, [rsp+58h+var_30]
0x10040bcef  mov     rbx, [rsp+58h+var_20]
0x10040bcf4  mov     [rax+8], rcx
0x10040bcf8  mov     [rcx], rax
0x10040bcfb  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10040bd02  mov     [rsi+10h], r12
0x10040bd06  mov     [rsi+8], r12
0x10040bd0a  dec     dword ptr [r15+18h]
0x10040bd0e  mov     r15, [rsp+58h+var_38]
0x10040bd13  cmp     [rax], r12b
0x10040bd16  jz      short loc_10040BD3F
0x10040bd18  call    cs:__imp_rand
0x10040bd1e  mov     r8d, eax
0x10040bd21  mov     eax, 66666667h
0x10040bd26  imul    r8d
0x10040bd29  sar     edx, 1
0x10040bd2b  mov     ecx, edx
0x10040bd2d  shr     ecx, 1Fh
0x10040bd30  add     edx, ecx
0x10040bd32  lea     ecx, [rdx+rdx*4]
0x10040bd35  cmp     r8d, ecx
0x10040bd38  jnz     short loc_10040BD3F
0x10040bd3a  call    ?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<19,1,268435714>::UpdateStatSnapshot(void)
0x10040bd3f  mov     [rdi], r12
0x10040bd42  mov     [rsi+18h], r12
0x10040bd46  add     rsp, 40h
0x10040bd4a  pop     r12
0x10040bd4c  pop     rdi
0x10040bd4d  pop     rsi
0x10040bd4e  retn
```
