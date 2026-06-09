# CSQLSatelliteConnection::CleanMessages(SOS_IOCompRequestList *,SQLSatelliteMessageSLock *)

- ea: `0x100471880`
- end: `0x100471a9d`
- name: `?CleanMessages@CSQLSatelliteConnection@@QEAAXPEAVSOS_IOCompRequestList@@PEAUSQLSatelliteMessageSLock@@@Z`
- size: `541`
- prototype: `void __fastcall(CSQLSatelliteConnection *__hidden this, struct SOS_IOCompRequestList *, struct SQLSatelliteMessageSLock *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100470fa0`
- `0x100475aa0`

## callees

- `0x100415950`
- `0x100415a50`
- `0x100415c70`
- `0x10041f180`
- `0x100471880`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100471939`
- `KERNEL32!QueryPerformanceCounter` at `0x100471992`
- `KERNEL32!QueryPerformanceCounter` at `0x100471939`
- `KERNEL32!QueryPerformanceCounter` at `0x100471992`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100471a28`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100471926`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10047197e`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100471951`
- `sqldk!SystemThread_TlsIndex` at `0x1004718f8`
- `sqldk!SystemThread_TlsOffset` at `0x100471901`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004718d8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100471a34`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100471a34`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CSQLSatelliteConnection::CleanMessages(
        CSQLSatelliteConnection *this,
        struct SOS_IOCompRequestList *a2,
        struct SQLSatelliteMessageSLock *a3)
{
  struct SNI_Packet *v5; // rdi
  LARGE_INTEGER v6; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v8; // rbp
  __int64 v9; // r8
  LARGE_INTEGER v10; // rcx
  LONGLONG v11; // rax
  int i; // r8d
  struct SOS_IOCompRequestList *v13; // rcx
  char *v14; // rdx
  _QWORD *v15; // rcx
  __int64 v16; // rax
  struct SNI_Packet *v17; // rdx
  int v18; // r8d
  struct SNI_Packet *v19; // rbx
  LARGE_INTEGER PerformanceCount; // [rsp+88h] [rbp+10h] BYREF
  LARGE_INTEGER v21; // [rsp+90h] [rbp+18h] BYREF

  v5 = 0;
  v6.QuadPart = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)a3 || _InterlockedCompareExchange64((volatile signed __int64 *)a3, UniqueThread_low, 0) )
  {
    v8 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v9 && *(_QWORD *)(v9 + 272) == v9 )
        v8 = *(_QWORD *)(v9 + 256);
      if ( v8 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v6 = PerformanceCount;
        }
        else
        {
          v6.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<8,19,258>::SpinToAcquireWithExponentialBackoff(a3, UniqueThread_low);
    else
      Spinlock<8,19,258>::SpinToAcquireOptimistic(a3, v8, UniqueThread_low);
    if ( v8 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v21);
        v10 = v21;
      }
      else
      {
        v10.QuadPart = MEMORY[0x7FFE0008];
      }
      v11 = 0;
      if ( v10.QuadPart >= (unsigned __int64)v6.QuadPart )
        v11 = v10.QuadPart - v6.QuadPart;
      *(_QWORD *)(v8 + 3192) += v11;
    }
  }
  for ( i = *((_DWORD *)a2 + 4); i; i = *((_DWORD *)a2 + 4) )
  {
    v13 = (struct SOS_IOCompRequestList *)*((_QWORD *)a2 + 1);
    if ( v13 == a2 )
      goto LABEL_27;
    v14 = 0;
    if ( v13 )
      v14 = (char *)v13 - 40;
    if ( !v14 )
    {
LABEL_27:
      v17 = 0;
    }
    else
    {
      *((_DWORD *)a2 + 4) = i - 1;
      v15 = (_QWORD *)*((_QWORD *)v14 + 6);
      v16 = *((_QWORD *)v14 + 5);
      *(_QWORD *)(v16 + 8) = v15;
      *v15 = v16;
      *((_QWORD *)v14 + 6) = 0;
      *((_QWORD *)v14 + 5) = 0;
      v17 = (struct SNI_Packet *)(v14 - 16);
    }
    *((_QWORD *)v17 + 26) = v5;
    v5 = v17;
  }
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v18 = rand();
    if ( v18 == 5 * (v18 / 5) )
      Spinlock<8,19,258>::UpdateStatSnapshot();
  }
  *(_QWORD *)a3 = 0;
  if ( v5 )
  {
    do
    {
      v19 = (struct SNI_Packet *)*((_QWORD *)v5 + 26);
      *((_QWORD *)v5 + 26) = 0;
      SNIPacketRelease(v5);
      v5 = v19;
    }
    while ( v19 );
  }
}

```

## disassembly

```asm
0x100471880  push    rbx
0x100471882  push    rbp
0x100471883  push    rsi
0x100471884  push    rdi
0x100471885  push    r12
0x100471887  push    r14
0x100471889  push    r15
0x10047188b  sub     rsp, 40h
0x10047188f  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x100471898  mov     r14, r8
0x10047189b  mov     rsi, rdx
0x10047189e  xor     r12d, r12d
0x1004718a1  mov     edi, r12d
0x1004718a4  mov     [rsp+78h+var_50], r8
0x1004718a9  mov     [rsp+78h+var_48], r12d
0x1004718ae  mov     ebx, r12d
0x1004718b1  mov     eax, gs:48h
0x1004718b9  mov     r15d, eax
0x1004718bc  mov     eax, [r8]
0x1004718bf  test    eax, eax
0x1004718c1  jnz     short loc_1004718D8
0x1004718c3  xor     eax, eax
0x1004718c5  lock cmpxchg [r8], r15
0x1004718ca  mov     eax, r12d
0x1004718cd  setz    al
0x1004718d0  test    eax, eax
0x1004718d2  jnz     loc_1004719C1
0x1004718d8  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004718df  mov     ecx, [rax]
0x1004718e1  and     ecx, 84h
0x1004718e7  mov     rbp, r12
0x1004718ea  cmp     cl, 84h
0x1004718ed  jnz     short loc_100471951
0x1004718ef  mov     rdx, gs:58h
0x1004718f8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004718ff  mov     ecx, [rax]
0x100471901  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100471908  mov     r8d, [rax]
0x10047190b  add     r8, [rdx+rcx*8]
0x10047190f  jz      short loc_100471921
0x100471911  cmp     [r8+110h], r8
0x100471918  jnz     short loc_100471921
0x10047191a  mov     rbp, [r8+100h]
0x100471921  test    rbp, rbp
0x100471924  jz      short loc_100471951
0x100471926  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10047192d  cmp     [rax], ebx
0x10047192f  jz      short loc_100471949
0x100471931  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x100471939  call    cs:__imp_QueryPerformanceCounter
0x10047193f  mov     rbx, qword ptr [rsp+78h+PerformanceCount]
0x100471947  jmp     short loc_100471951
0x100471949  mov     rbx, ds:7FFE0008h
0x100471951  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100471958  mov     rcx, r14
0x10047195b  cmp     byte ptr [rax+0C7h], 0
0x100471962  jge     short loc_100471971
0x100471964  mov     r8, r15
0x100471967  mov     rdx, rbp
0x10047196a  call    ?SpinToAcquireOptimistic@?$Spinlock@$07$0BD@$0BAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<8,19,258>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10047196f  jmp     short loc_100471979
0x100471971  mov     rdx, r15
0x100471974  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$07$0BD@$0BAC@@@AEAAX_K@Z; Spinlock<8,19,258>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100471979  test    rbp, rbp
0x10047197c  jz      short loc_1004719C1
0x10047197e  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100471985  cmp     dword ptr [rax], 0
0x100471988  jz      short loc_1004719A2
0x10047198a  lea     rcx, [rsp+78h+arg_10]; lpPerformanceCount
0x100471992  call    cs:__imp_QueryPerformanceCounter
0x100471998  mov     rcx, qword ptr [rsp+78h+arg_10]
0x1004719a0  jmp     short loc_1004719AA
0x1004719a2  mov     rcx, ds:7FFE0008h
0x1004719aa  mov     rdx, rcx
0x1004719ad  sub     rdx, rbx
0x1004719b0  mov     rax, r12
0x1004719b3  cmp     rcx, rbx
0x1004719b6  cmovnb  rax, rdx
0x1004719ba  add     [rbp+0C78h], rax
0x1004719c1  mov     [rsp+78h+var_48], 1
0x1004719c9  mov     r8d, [rsi+10h]
0x1004719cd  test    r8d, r8d
0x1004719d0  jz      short loc_100471A28
0x1004719d2  mov     rcx, [rsi+8]
0x1004719d6  cmp     rcx, rsi
0x1004719d9  jz      short loc_100471A12
0x1004719db  lea     rax, [rcx-28h]
0x1004719df  mov     rdx, r12
0x1004719e2  test    rcx, rcx
0x1004719e5  cmovnz  rdx, rax
0x1004719e9  test    rdx, rdx
0x1004719ec  jz      short loc_100471A12
0x1004719ee  lea     eax, [r8-1]
0x1004719f2  mov     [rsi+10h], eax
0x1004719f5  mov     rcx, [rdx+30h]
0x1004719f9  mov     rax, [rdx+28h]
0x1004719fd  mov     [rax+8], rcx
0x100471a01  mov     [rcx], rax
0x100471a04  mov     [rdx+30h], r12
0x100471a08  mov     [rdx+28h], r12
0x100471a0c  add     rdx, 0FFFFFFFFFFFFFFF0h
0x100471a10  jmp     short loc_100471A15
0x100471a12  mov     rdx, r12
0x100471a15  mov     [rdx+0D0h], rdi
0x100471a1c  mov     rdi, rdx
0x100471a1f  mov     r8d, [rsi+10h]
0x100471a23  test    r8d, r8d
0x100471a26  jnz     short loc_1004719D2
0x100471a28  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100471a2f  cmp     byte ptr [rax], 0
0x100471a32  jz      short loc_100471A5B
0x100471a34  call    cs:__imp_rand
0x100471a3a  mov     r8d, eax
0x100471a3d  mov     eax, 66666667h
0x100471a42  imul    r8d
0x100471a45  sar     edx, 1
0x100471a47  mov     ecx, edx
0x100471a49  shr     ecx, 1Fh
0x100471a4c  add     edx, ecx
0x100471a4e  lea     ecx, [rdx+rdx*4]
0x100471a51  cmp     r8d, ecx
0x100471a54  jnz     short loc_100471A5B
0x100471a56  call    ?UpdateStatSnapshot@?$Spinlock@$07$0BD@$0BAC@@@AEAAXXZ; Spinlock<8,19,258>::UpdateStatSnapshot(void)
0x100471a5b  mov     [r14], r12
0x100471a5e  mov     [rsp+78h+var_50], r12
0x100471a63  mov     [rsp+78h+var_48], r12d
0x100471a68  test    rdi, rdi
0x100471a6b  jz      short loc_100471A8E
0x100471a6d  nop     dword ptr [rax]
0x100471a70  mov     rbx, [rdi+0D0h]
0x100471a77  mov     [rdi+0D0h], r12
0x100471a7e  mov     rcx, rdi; struct SNI_Packet *
0x100471a81  call    SNIPacketRelease
0x100471a86  mov     rdi, rbx
0x100471a89  test    rbx, rbx
0x100471a8c  jnz     short loc_100471A70
0x100471a8e  add     rsp, 40h
0x100471a92  pop     r15
0x100471a94  pop     r14
0x100471a96  pop     r12
0x100471a98  pop     rdi
0x100471a99  pop     rsi
0x100471a9a  pop     rbp
0x100471a9b  pop     rbx
0x100471a9c  retn
```
