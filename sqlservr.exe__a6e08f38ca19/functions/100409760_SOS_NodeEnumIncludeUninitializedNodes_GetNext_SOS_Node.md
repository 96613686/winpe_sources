# SOS_NodeEnumIncludeUninitializedNodes::GetNext(SOS_Node *)

- ea: `0x100409760`
- end: `0x100409bd6`
- name: `?GetNext@SOS_NodeEnumIncludeUninitializedNodes@@QEAAPEAVSOS_Node@@PEAV2@@Z`
- size: `1142`
- prototype: `struct SOS_Node *__fastcall(SOS_NodeEnumIncludeUninitializedNodes *__hidden this, struct SOS_Node *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10040ca90`

## callees

- `0x100408910`
- `0x100408b50`
- `0x100408e00`
- `0x100409760`
- `0x10040af70`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100409832`
- `KERNEL32!QueryPerformanceCounter` at `0x10040988b`
- `KERNEL32!QueryPerformanceCounter` at `0x100409a53`
- `KERNEL32!QueryPerformanceCounter` at `0x100409aa6`
- `KERNEL32!QueryPerformanceCounter` at `0x100409832`
- `KERNEL32!QueryPerformanceCounter` at `0x10040988b`
- `KERNEL32!QueryPerformanceCounter` at `0x100409a53`
- `KERNEL32!QueryPerformanceCounter` at `0x100409aa6`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10040984a`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100409a68`
- `sqldk!SystemThread_TlsOffset` at `0x1004097fa`
- `sqldk!SystemThread_TlsOffset` at `0x100409a1e`
- `sqldk!SystemThread_TlsIndex` at `0x1004097f1`
- `sqldk!SystemThread_TlsIndex` at `0x100409a15`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040981f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100409878`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100409a43`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100409a96`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100409919`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100409b39`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004097d4`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004099f5`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100409925`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100409b45`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100409925`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100409b45`

## pseudocode

```c
struct SOS_Node *__fastcall SOS_NodeEnumIncludeUninitializedNodes::GetNext(
        SOS_NodeEnumIncludeUninitializedNodes *this,
        struct SOS_Node *a2)
{
  __int64 v2; // rsi
  SOS_NodeEnumIncludeUninitializedNodes *v4; // rbp
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // r15
  LARGE_INTEGER v8; // rbx
  signed __int64 UniqueThread_low; // rbp
  __int64 v10; // r8
  __int64 v11; // rcx
  LARGE_INTEGER v12; // rcx
  LONGLONG v13; // rax
  __int64 v14; // rcx
  signed __int32 v15; // ecx
  __int64 v16; // rcx
  int v17; // eax
  LARGE_INTEGER v18; // rbx
  __int64 v19; // r15
  signed __int64 v20; // r14
  __int64 v21; // rbp
  __int64 v22; // r8
  __int64 v23; // rcx
  LARGE_INTEGER v24; // rcx
  LONGLONG v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rbx
  signed __int32 v28; // ecx
  __int64 v29; // rcx
  int v30; // eax
  LARGE_INTEGER v32; // [rsp+20h] [rbp-58h] BYREF
  LARGE_INTEGER v33; // [rsp+28h] [rbp-50h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp+18h] BYREF
  LARGE_INTEGER v36; // [rsp+98h] [rbp+20h] BYREF

  v2 = 0;
  v4 = this;
  v5 = 0;
  if ( a2 )
  {
    v6 = *(_QWORD *)this;
    if ( v6 )
    {
      if ( v6 == *((_QWORD *)v4 + 1) )
      {
        *(_QWORD *)v4 = 0;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 40), 0xFFFFFFFF) == 1 && *(_QWORD *)(v6 + 24) )
          goto LABEL_92;
      }
      else
      {
        v7 = *((_QWORD *)v4 + 2);
        v8.QuadPart = 0;
        UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)(v7 + 16)
          || _InterlockedCompareExchange64((volatile signed __int64 *)(v7 + 16), UniqueThread_low, 0) )
        {
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            if ( v10 && *(_QWORD *)(v10 + 272) == v10 )
              v5 = *(_QWORD *)(v10 + 256);
            if ( v5 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&PerformanceCount);
                v8 = PerformanceCount;
              }
              else
              {
                v8.QuadPart = MEMORY[0x7FFE0008];
              }
            }
          }
          v11 = v7 + 16;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(v11, UniqueThread_low);
          else
            Spinlock<19,1,268435714>::SpinToAcquireOptimistic(v11, v5, UniqueThread_low);
          if ( v5 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v36);
              v12 = v36;
            }
            else
            {
              v12.QuadPart = MEMORY[0x7FFE0008];
            }
            v13 = 0;
            if ( v12.QuadPart >= (unsigned __int64)v8.QuadPart )
              v13 = v12.QuadPart - v8.QuadPart;
            *(_QWORD *)(v5 + 3192) += v13;
          }
        }
        v14 = *((_QWORD *)a2 + 3);
        v5 = 0;
        if ( v14 != v7 )
        {
          if ( v14 )
            v5 = v14 - 16;
          if ( v5 )
          {
            while ( 1 )
            {
              v15 = *(_DWORD *)(v5 + 40);
              if ( v15 )
              {
                while ( v15 != _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 40), v15 + 1, v15) )
                {
                  _mm_pause();
                  v15 = *(_DWORD *)(v5 + 40);
                  if ( !v15 )
                    goto LABEL_34;
                }
                if ( v15 != -1 )
                  break;
              }
LABEL_34:
              v16 = *(_QWORD *)(v5 + 24);
              v5 = 0;
              if ( v16 != v7 )
              {
                if ( v16 )
                  v5 = v16 - 16;
                if ( v5 )
                  continue;
              }
              break;
            }
          }
        }
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v17 = rand();
          if ( v17 == 5 * (v17 / 5) )
            Spinlock<19,1,268435714>::UpdateStatSnapshot();
        }
        v4 = this;
        *(_QWORD *)(v7 + 16) = 0;
        *(_QWORD *)this = v5;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 10, 0xFFFFFFFF) == 1 && *((_QWORD *)a2 + 3) )
          TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*((_QWORD *)a2 + 4), a2);
      }
    }
  }
  else
  {
    v5 = *(_QWORD *)this;
  }
  if ( v5 && (*(_BYTE *)(v5 + 1568) & 4) != 0 )
  {
    v6 = *(_QWORD *)v4;
    if ( !*(_QWORD *)v4 )
      return (struct SOS_Node *)v2;
    if ( v6 != *((_QWORD *)v4 + 1) )
    {
      v18.QuadPart = 0;
      v19 = *((_QWORD *)v4 + 2);
      v20 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)(v19 + 16) || _InterlockedCompareExchange64((volatile signed __int64 *)(v19 + 16), v20, 0) )
      {
        v21 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v22 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v22 && *(_QWORD *)(v22 + 272) == v22 )
            v21 = *(_QWORD *)(v22 + 256);
          if ( v21 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v32);
              v18 = v32;
            }
            else
            {
              v18.QuadPart = MEMORY[0x7FFE0008];
            }
          }
        }
        v23 = v19 + 16;
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(v23, v20);
        else
          Spinlock<19,1,268435714>::SpinToAcquireOptimistic(v23, v21, v20);
        if ( v21 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v33);
            v24 = v33;
          }
          else
          {
            v24.QuadPart = MEMORY[0x7FFE0008];
          }
          v25 = 0;
          if ( v24.QuadPart >= (unsigned __int64)v18.QuadPart )
            v25 = v24.QuadPart - v18.QuadPart;
          *(_QWORD *)(v21 + 3192) += v25;
        }
        v4 = this;
      }
      v26 = *(_QWORD *)(v5 + 24);
      v27 = 0;
      if ( v26 != v19 )
      {
        if ( v26 )
          v27 = v26 - 16;
        if ( v27 )
        {
          while ( 1 )
          {
            v28 = *(_DWORD *)(v27 + 40);
            if ( v28 )
            {
              while ( v28 != _InterlockedCompareExchange((volatile signed __int32 *)(v27 + 40), v28 + 1, v28) )
              {
                _mm_pause();
                v28 = *(_DWORD *)(v27 + 40);
                if ( !v28 )
                  goto LABEL_80;
              }
              if ( v28 != -1 )
                break;
            }
LABEL_80:
            v29 = *(_QWORD *)(v27 + 24);
            v27 = 0;
            if ( v29 != v19 )
            {
              if ( v29 )
                v27 = v29 - 16;
              if ( v27 )
                continue;
            }
            break;
          }
        }
      }
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v30 = rand();
        if ( v30 == 5 * (v30 / 5) )
          Spinlock<19,1,268435714>::UpdateStatSnapshot();
      }
      *(_QWORD *)(v19 + 16) = 0;
      v2 = v27;
      *(_QWORD *)v4 = v27;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 40), 0xFFFFFFFF) == 1 && *(_QWORD *)(v5 + 24) )
      {
        TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v5 + 32), v5);
        return (struct SOS_Node *)v27;
      }
      return (struct SOS_Node *)v2;
    }
    *(_QWORD *)v4 = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 40), 0xFFFFFFFF) != 1 || !*(_QWORD *)(v6 + 24) )
      return (struct SOS_Node *)v2;
LABEL_92:
    TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v6 + 32), v6);
    return (struct SOS_Node *)v2;
  }
  return (struct SOS_Node *)v5;
}

```

## disassembly

```asm
0x100409760  mov     [rsp+arg_0], rcx
0x100409765  push    rbx
0x100409766  push    rbp
0x100409767  push    rsi
0x100409768  push    rdi
0x100409769  push    r12
0x10040976b  push    r13
0x10040976d  push    r14
0x10040976f  push    r15
0x100409771  sub     rsp, 38h
0x100409775  xor     esi, esi
0x100409777  mov     r14, rdx
0x10040977a  mov     rbp, rcx
0x10040977d  mov     edi, esi
0x10040977f  lea     r13d, [rsi-1]
0x100409783  test    rdx, rdx
0x100409786  jnz     short loc_100409790
0x100409788  mov     rdi, [rcx]
0x10040978b  jmp     loc_100409999
0x100409790  mov     rcx, [rcx]
0x100409793  test    rcx, rcx
0x100409796  jz      loc_100409999
0x10040979c  cmp     rcx, [rbp+8]
0x1004097a0  jz      loc_10040997E
0x1004097a6  mov     r15, [rbp+10h]
0x1004097aa  mov     rbx, rsi
0x1004097ad  mov     eax, gs:48h
0x1004097b5  mov     ebp, eax
0x1004097b7  mov     eax, [r15+10h]
0x1004097bb  test    eax, eax
0x1004097bd  jnz     short loc_1004097D4
0x1004097bf  xor     eax, eax
0x1004097c1  lock cmpxchg [r15+10h], rbp
0x1004097c7  mov     eax, esi
0x1004097c9  setz    al
0x1004097cc  test    eax, eax
0x1004097ce  jnz     loc_1004098BA
0x1004097d4  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004097db  mov     ecx, [rax]
0x1004097dd  and     ecx, 84h
0x1004097e3  cmp     cl, 84h
0x1004097e6  jnz     short loc_10040984A
0x1004097e8  mov     rdx, gs:58h
0x1004097f1  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004097f8  mov     ecx, [rax]
0x1004097fa  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100409801  mov     r8d, [rax]
0x100409804  add     r8, [rdx+rcx*8]
0x100409808  jz      short loc_10040981A
0x10040980a  cmp     [r8+110h], r8
0x100409811  jnz     short loc_10040981A
0x100409813  mov     rdi, [r8+100h]
0x10040981a  test    rdi, rdi
0x10040981d  jz      short loc_10040984A
0x10040981f  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100409826  cmp     [rax], ebx
0x100409828  jz      short loc_100409842
0x10040982a  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x100409832  call    cs:__imp_QueryPerformanceCounter
0x100409838  mov     rbx, qword ptr [rsp+78h+PerformanceCount]
0x100409840  jmp     short loc_10040984A
0x100409842  mov     rbx, ds:7FFE0008h
0x10040984a  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100409851  lea     rcx, [r15+10h]
0x100409855  cmp     [rax+0C7h], sil
0x10040985c  jge     short loc_10040986B
0x10040985e  mov     r8, rbp
0x100409861  mov     rdx, rdi
0x100409864  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100409869  jmp     short loc_100409873
0x10040986b  mov     rdx, rbp
0x10040986e  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100409873  test    rdi, rdi
0x100409876  jz      short loc_1004098BA
0x100409878  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040987f  cmp     [rax], esi
0x100409881  jz      short loc_10040989B
0x100409883  lea     rcx, [rsp+78h+arg_18]; lpPerformanceCount
0x10040988b  call    cs:__imp_QueryPerformanceCounter
0x100409891  mov     rcx, qword ptr [rsp+78h+arg_18]
0x100409899  jmp     short loc_1004098A3
0x10040989b  mov     rcx, ds:7FFE0008h
0x1004098a3  mov     rdx, rcx
0x1004098a6  mov     rax, rsi
0x1004098a9  sub     rdx, rbx
0x1004098ac  cmp     rcx, rbx
0x1004098af  cmovnb  rax, rdx
0x1004098b3  add     [rdi+0C78h], rax
0x1004098ba  mov     rcx, [r14+18h]
0x1004098be  mov     rdi, rsi
0x1004098c1  cmp     rcx, r15
0x1004098c4  jz      short loc_100409919
0x1004098c6  test    rcx, rcx
0x1004098c9  lea     rax, [rcx-10h]
0x1004098cd  cmovnz  rdi, rax
0x1004098d1  test    rdi, rdi
0x1004098d4  jz      short loc_100409919
0x1004098d6  mov     ecx, [rdi+28h]
0x1004098d9  test    ecx, ecx
0x1004098db  jz      short loc_1004098FD
0x1004098dd  nop     dword ptr [rax]
0x1004098e0  lea     edx, [rcx+1]
0x1004098e3  mov     eax, ecx
0x1004098e5  lock cmpxchg [rdi+28h], edx
0x1004098ea  cmp     ecx, eax
0x1004098ec  jz      short loc_1004098F9
0x1004098ee  pause
0x1004098f0  mov     ecx, [rdi+28h]
0x1004098f3  test    ecx, ecx
0x1004098f5  jnz     short loc_1004098E0
0x1004098f7  jmp     short loc_1004098FD
0x1004098f9  test    edx, edx
0x1004098fb  jnz     short loc_100409919
0x1004098fd  mov     rcx, [rdi+18h]
0x100409901  mov     rdi, rsi
0x100409904  cmp     rcx, r15
0x100409907  jz      short loc_100409919
0x100409909  test    rcx, rcx
0x10040990c  lea     rax, [rcx-10h]
0x100409910  cmovnz  rdi, rax
0x100409914  test    rdi, rdi
0x100409917  jnz     short loc_1004098D6
0x100409919  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100409920  cmp     [rax], sil
0x100409923  jz      short loc_10040994C
0x100409925  call    cs:__imp_rand
0x10040992b  mov     r8d, eax
0x10040992e  mov     eax, 66666667h
0x100409933  imul    r8d
0x100409936  sar     edx, 1
0x100409938  mov     ecx, edx
0x10040993a  shr     ecx, 1Fh
0x10040993d  add     edx, ecx
0x10040993f  lea     ecx, [rdx+rdx*4]
0x100409942  cmp     r8d, ecx
0x100409945  jnz     short loc_10040994C
0x100409947  call    ?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<19,1,268435714>::UpdateStatSnapshot(void)
0x10040994c  mov     rbp, [rsp+78h+arg_0]
0x100409954  mov     eax, r13d
0x100409957  mov     [r15+10h], rsi
0x10040995b  mov     [rbp+0], rdi
0x10040995f  lock xadd [r14+28h], eax
0x100409965  cmp     eax, 1
0x100409968  jnz     short loc_100409999
0x10040996a  cmp     [r14+18h], rsi
0x10040996e  jz      short loc_100409999
0x100409970  mov     rcx, [r14+20h]
0x100409974  mov     rdx, r14
0x100409977  call    ?RemoveElem@?$TList@VGroupList@@VSOS_ResourceGroup@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_ResourceGroup@@@Z; TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(SOS_ResourceGroup *)
0x10040997c  jmp     short loc_100409999
0x10040997e  mov     [rbp+0], rsi
0x100409982  mov     eax, r13d
0x100409985  lock xadd [rcx+28h], eax
0x10040998a  cmp     eax, 1
0x10040998d  jnz     short loc_100409999
0x10040998f  cmp     [rcx+18h], rsi
0x100409993  jnz     loc_100409BB1
0x100409999  test    rdi, rdi
0x10040999c  jz      loc_100409BC2
0x1004099a2  test    byte ptr [rdi+620h], 4
0x1004099a9  jz      loc_100409BC2
0x1004099af  mov     rcx, [rbp+0]
0x1004099b3  test    rcx, rcx
0x1004099b6  jz      loc_100409BBD
0x1004099bc  cmp     rcx, [rbp+8]
0x1004099c0  jz      loc_100409B9B
0x1004099c6  mov     eax, gs:48h
0x1004099ce  mov     rbx, rsi
0x1004099d1  mov     r15, [rbp+10h]
0x1004099d5  mov     r14d, eax
0x1004099d8  mov     eax, [r15+10h]
0x1004099dc  test    eax, eax
0x1004099de  jnz     short loc_1004099F5
0x1004099e0  xor     eax, eax
0x1004099e2  lock cmpxchg [r15+10h], r14
0x1004099e8  mov     eax, esi
0x1004099ea  setz    al
0x1004099ed  test    eax, eax
0x1004099ef  jnz     loc_100409ADA
0x1004099f5  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004099fc  mov     rbp, rsi
0x1004099ff  mov     ecx, [rax]
0x100409a01  and     ecx, 84h
0x100409a07  cmp     cl, 84h
0x100409a0a  jnz     short loc_100409A68
0x100409a0c  mov     rdx, gs:58h
0x100409a15  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100409a1c  mov     ecx, [rax]
0x100409a1e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100409a25  mov     r8d, [rax]
0x100409a28  add     r8, [rdx+rcx*8]
0x100409a2c  jz      short loc_100409A3E
0x100409a2e  cmp     [r8+110h], r8
0x100409a35  jnz     short loc_100409A3E
0x100409a37  mov     rbp, [r8+100h]
0x100409a3e  test    rbp, rbp
0x100409a41  jz      short loc_100409A68
0x100409a43  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100409a4a  cmp     [rax], ebx
0x100409a4c  jz      short loc_100409A60
0x100409a4e  lea     rcx, [rsp+78h+var_58]; lpPerformanceCount
0x100409a53  call    cs:__imp_QueryPerformanceCounter
0x100409a59  mov     rbx, qword ptr [rsp+78h+var_58]
0x100409a5e  jmp     short loc_100409A68
0x100409a60  mov     rbx, ds:7FFE0008h
0x100409a68  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100409a6f  lea     rcx, [r15+10h]
0x100409a73  cmp     [rax+0C7h], sil
0x100409a7a  jge     short loc_100409A89
0x100409a7c  mov     r8, r14
0x100409a7f  mov     rdx, rbp
0x100409a82  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100409a87  jmp     short loc_100409A91
0x100409a89  mov     rdx, r14
0x100409a8c  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100409a91  test    rbp, rbp
0x100409a94  jz      short loc_100409AD2
0x100409a96  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100409a9d  cmp     [rax], esi
0x100409a9f  jz      short loc_100409AB3
0x100409aa1  lea     rcx, [rsp+78h+var_50]; lpPerformanceCount
0x100409aa6  call    cs:__imp_QueryPerformanceCounter
0x100409aac  mov     rcx, qword ptr [rsp+78h+var_50]
0x100409ab1  jmp     short loc_100409ABB
0x100409ab3  mov     rcx, ds:7FFE0008h
0x100409abb  mov     rdx, rcx
0x100409abe  mov     rax, rsi
0x100409ac1  sub     rdx, rbx
0x100409ac4  cmp     rcx, rbx
0x100409ac7  cmovnb  rax, rdx
0x100409acb  add     [rbp+0C78h], rax
0x100409ad2  mov     rbp, [rsp+78h+arg_0]
0x100409ada  mov     rcx, [rdi+18h]
0x100409ade  mov     rbx, rsi
0x100409ae1  cmp     rcx, r15
0x100409ae4  jz      short loc_100409B39
0x100409ae6  test    rcx, rcx
0x100409ae9  lea     rax, [rcx-10h]
0x100409aed  cmovnz  rbx, rax
0x100409af1  test    rbx, rbx
0x100409af4  jz      short loc_100409B39
0x100409af6  mov     ecx, [rbx+28h]
0x100409af9  test    ecx, ecx
0x100409afb  jz      short loc_100409B1D
0x100409afd  nop     dword ptr [rax]
0x100409b00  lea     edx, [rcx+1]
0x100409b03  mov     eax, ecx
0x100409b05  lock cmpxchg [rbx+28h], edx
0x100409b0a  cmp     ecx, eax
0x100409b0c  jz      short loc_100409B19
0x100409b0e  pause
0x100409b10  mov     ecx, [rbx+28h]
0x100409b13  test    ecx, ecx
0x100409b15  jnz     short loc_100409B00
0x100409b17  jmp     short loc_100409B1D
0x100409b19  test    edx, edx
0x100409b1b  jnz     short loc_100409B39
0x100409b1d  mov     rcx, [rbx+18h]
0x100409b21  mov     rbx, rsi
0x100409b24  cmp     rcx, r15
0x100409b27  jz      short loc_100409B39
0x100409b29  test    rcx, rcx
0x100409b2c  lea     rax, [rcx-10h]
0x100409b30  cmovnz  rbx, rax
0x100409b34  test    rbx, rbx
0x100409b37  jnz     short loc_100409AF6
0x100409b39  mov     rcx, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100409b40  cmp     [rcx], sil
0x100409b43  jz      short loc_100409B6C
0x100409b45  call    cs:__imp_rand
0x100409b4b  mov     r8d, eax
0x100409b4e  mov     eax, 66666667h
0x100409b53  imul    r8d
0x100409b56  sar     edx, 1
0x100409b58  mov     ecx, edx
0x100409b5a  shr     ecx, 1Fh
0x100409b5d  add     edx, ecx
0x100409b5f  lea     ecx, [rdx+rdx*4]
0x100409b62  cmp     r8d, ecx
0x100409b65  jnz     short loc_100409B6C
0x100409b67  call    ?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<19,1,268435714>::UpdateStatSnapshot(void)
0x100409b6c  mov     [r15+10h], rsi
0x100409b70  mov     rsi, rbx
0x100409b73  mov     [rbp+0], rbx
0x100409b77  lock xadd [rdi+28h], r13d
0x100409b7d  cmp     r13d, 1
0x100409b81  jnz     short loc_100409BBD
0x100409b83  cmp     qword ptr [rdi+18h], 0
0x100409b88  jz      short loc_100409BBD
0x100409b8a  mov     rcx, [rdi+20h]
0x100409b8e  mov     rdx, rdi
0x100409b91  call    ?RemoveElem@?$TList@VGroupList@@VSOS_ResourceGroup@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_ResourceGroup@@@Z; TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(SOS_ResourceGroup *)
0x100409b96  mov     rax, rbx
0x100409b99  jmp     short loc_100409BC5
0x100409b9b  mov     [rbp+0], rsi
0x100409b9f  lock xadd [rcx+28h], r13d
0x100409ba5  cmp     r13d, 1
0x100409ba9  jnz     short loc_100409BBD
0x100409bab  cmp     [rcx+18h], rsi
0x100409baf  jz      short loc_100409BBD
  ... truncated ...
```
