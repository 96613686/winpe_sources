# TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(SOS_ResourceGroup *)

- ea: `0x10040af70`
- end: `0x10040b10f`
- name: `?RemoveElem@?$TList@VGroupList@@VSOS_ResourceGroup@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_ResourceGroup@@@Z`
- size: `415`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100409530`
- `0x100409760`
- `0x100409d40`
- `0x10041d870`
- `0x10041fa30`
- `0x10041fab0`

## callees

- `0x100408910`
- `0x100408b50`
- `0x100408e00`
- `0x10040af70`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10040b021`
- `KERNEL32!QueryPerformanceCounter` at `0x10040b074`
- `KERNEL32!QueryPerformanceCounter` at `0x10040b021`
- `KERNEL32!QueryPerformanceCounter` at `0x10040b074`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10040b036`
- `sqldk!SystemThread_TlsOffset` at `0x10040afec`
- `sqldk!SystemThread_TlsIndex` at `0x10040afe3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040b011`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040b063`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040b0bb`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040afbe`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040b0d8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040b0d8`

## pseudocode

```c
__int64 __fastcall TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(__int64 a1, _QWORD *a2)
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
  v11 = a2[2];
  v12 = (_QWORD *)a2[3];
  *(_QWORD *)(v11 + 8) = v12;
  *v12 = v11;
  result = *(_QWORD *)&SOS_PublicGlobals::sm_SpinlockStatSnapshot;
  a2[3] = 0;
  a2[2] = 0;
  --*(_DWORD *)(a1 + 24);
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v14 = rand();
    result = (unsigned int)(1717986919 * v14);
    if ( v14 == 5 * (v14 / 5) )
      result = Spinlock<19,1,268435714>::UpdateStatSnapshot();
  }
  *v2 = 0;
  a2[4] = 0;
  return result;
}

```

## disassembly

```asm
0x10040af70  push    rsi
0x10040af72  push    rdi
0x10040af73  push    r12
0x10040af75  sub     rsp, 40h
0x10040af79  mov     eax, gs:48h
0x10040af81  lea     rdi, [rcx+10h]
0x10040af85  mov     [rsp+58h+var_20], rbx
0x10040af8a  xor     r12d, r12d
0x10040af8d  mov     [rsp+58h+var_30], r14
0x10040af92  mov     rsi, rdx
0x10040af95  mov     r14d, eax
0x10040af98  mov     ebx, r12d
0x10040af9b  mov     eax, [rdi]
0x10040af9d  mov     [rsp+58h+var_38], r15
0x10040afa2  mov     r15, rcx
0x10040afa5  test    eax, eax
0x10040afa7  jnz     short loc_10040AFBE
0x10040afa9  xor     eax, eax
0x10040afab  lock cmpxchg [rdi], r14
0x10040afb0  mov     eax, r12d
0x10040afb3  setz    al
0x10040afb6  test    eax, eax
0x10040afb8  jnz     loc_10040B0A2
0x10040afbe  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040afc5  mov     [rsp+58h+var_28], rbp
0x10040afca  mov     rbp, r12
0x10040afcd  mov     ecx, [rax]
0x10040afcf  and     ecx, 84h
0x10040afd5  cmp     cl, 84h
0x10040afd8  jnz     short loc_10040B036
0x10040afda  mov     rdx, gs:58h
0x10040afe3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040afea  mov     ecx, [rax]
0x10040afec  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040aff3  mov     r8d, [rax]
0x10040aff6  add     r8, [rdx+rcx*8]
0x10040affa  jz      short loc_10040B00C
0x10040affc  cmp     [r8+110h], r8
0x10040b003  jnz     short loc_10040B00C
0x10040b005  mov     rbp, [r8+100h]
0x10040b00c  test    rbp, rbp
0x10040b00f  jz      short loc_10040B036
0x10040b011  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040b018  cmp     [rax], ebx
0x10040b01a  jz      short loc_10040B02E
0x10040b01c  lea     rcx, [rsp+58h+PerformanceCount]; lpPerformanceCount
0x10040b021  call    cs:__imp_QueryPerformanceCounter
0x10040b027  mov     rbx, qword ptr [rsp+58h+PerformanceCount]
0x10040b02c  jmp     short loc_10040B036
0x10040b02e  mov     rbx, ds:7FFE0008h
0x10040b036  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10040b03d  mov     rcx, rdi
0x10040b040  cmp     [rax+0C7h], r12b
0x10040b047  jge     short loc_10040B056
0x10040b049  mov     r8, r14
0x10040b04c  mov     rdx, rbp
0x10040b04f  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10040b054  jmp     short loc_10040B05E
0x10040b056  mov     rdx, r14
0x10040b059  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10040b05e  test    rbp, rbp
0x10040b061  jz      short loc_10040B09D
0x10040b063  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040b06a  cmp     [rax], r12d
0x10040b06d  jz      short loc_10040B081
0x10040b06f  lea     rcx, [rsp+58h+arg_8]; lpPerformanceCount
0x10040b074  call    cs:__imp_QueryPerformanceCounter
0x10040b07a  mov     rax, qword ptr [rsp+58h+arg_8]
0x10040b07f  jmp     short loc_10040B089
0x10040b081  mov     rax, ds:7FFE0008h
0x10040b089  mov     rcx, rax
0x10040b08c  sub     rcx, rbx
0x10040b08f  cmp     rax, rbx
0x10040b092  cmovb   rcx, r12
0x10040b096  add     [rbp+0C78h], rcx
0x10040b09d  mov     rbp, [rsp+58h+var_28]
0x10040b0a2  mov     rax, [rsi+10h]
0x10040b0a6  mov     rcx, [rsi+18h]
0x10040b0aa  mov     r14, [rsp+58h+var_30]
0x10040b0af  mov     rbx, [rsp+58h+var_20]
0x10040b0b4  mov     [rax+8], rcx
0x10040b0b8  mov     [rcx], rax
0x10040b0bb  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10040b0c2  mov     [rsi+18h], r12
0x10040b0c6  mov     [rsi+10h], r12
0x10040b0ca  dec     dword ptr [r15+18h]
0x10040b0ce  mov     r15, [rsp+58h+var_38]
0x10040b0d3  cmp     [rax], r12b
0x10040b0d6  jz      short loc_10040B0FF
0x10040b0d8  call    cs:__imp_rand
0x10040b0de  mov     r8d, eax
0x10040b0e1  mov     eax, 66666667h
0x10040b0e6  imul    r8d
0x10040b0e9  sar     edx, 1
0x10040b0eb  mov     ecx, edx
0x10040b0ed  shr     ecx, 1Fh
0x10040b0f0  add     edx, ecx
0x10040b0f2  lea     ecx, [rdx+rdx*4]
0x10040b0f5  cmp     r8d, ecx
0x10040b0f8  jnz     short loc_10040B0FF
0x10040b0fa  call    ?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<19,1,268435714>::UpdateStatSnapshot(void)
0x10040b0ff  mov     [rdi], r12
0x10040b102  mov     [rsi+20h], r12
0x10040b106  add     rsp, 40h
0x10040b10a  pop     r12
0x10040b10c  pop     rdi
0x10040b10d  pop     rsi
0x10040b10e  retn
```
