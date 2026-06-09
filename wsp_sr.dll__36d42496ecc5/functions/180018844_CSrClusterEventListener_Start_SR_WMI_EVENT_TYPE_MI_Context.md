# CSrClusterEventListener::Start(_SR_WMI_EVENT_TYPE,_MI_Context *)

- ea: `0x180018844`
- end: `0x18001892e`
- name: `?Start@CSrClusterEventListener@@QEAAKW4_SR_WMI_EVENT_TYPE@@PEAU_MI_Context@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180018934`

## callees

- `0x180006778`
- `0x1800067a0`
- `0x180018844`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188cc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800188bd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800188bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001888e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001888e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800188ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800188ef`

## pseudocode

```c
__int64 __fastcall CSrClusterEventListener::Start(__int64 a1, int a2, __int64 a3)
{
  DWORD LastError; // edi
  HANDLE Thread; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids);
  LastError = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
  if ( !*(_BYTE *)(a1 + 28) )
  {
    *(_QWORD *)(a1 + 16) = a3;
    *(_BYTE *)(a1 + 28) = 1;
    *(_DWORD *)(a1 + 24) = a2;
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)SrClusterEventsWorkerThread, (LPVOID)a1, 0, 0);
    *(_QWORD *)(a1 + 32) = Thread;
    if ( !Thread )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        *(_BYTE *)(a1 + 28) = 0;
        *(_QWORD *)(a1 + 16) = 0;
        *(_DWORD *)(a1 + 24) = 0;
      }
    }
  }
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 8));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180018844  push    rbx
0x180018846  push    rbp
0x180018847  push    rsi
0x180018848  push    rdi
0x180018849  push    r12
0x18001884b  push    r14
0x18001884d  sub     rsp, 38h
0x180018851  mov     rbp, r8
0x180018854  mov     r14d, edx
0x180018857  mov     rbx, rcx
0x18001885a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018861  lea     r12, WPP_GLOBAL_Control
0x180018868  cmp     rcx, r12
0x18001886b  jz      short loc_180018888
0x18001886d  test    byte ptr [rcx+1Ch], 4
0x180018871  jz      short loc_180018888
0x180018873  mov     rcx, [rcx+10h]
0x180018877  lea     r8, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids
0x18001887e  mov     edx, 18h
0x180018883  call    WPP_SF_
0x180018888  lea     rcx, [rbx+8]; SRWLock
0x18001888c  xor     edi, edi
0x18001888e  call    cs:__imp_AcquireSRWLockExclusive
0x180018894  cmp     [rbx+1Ch], dil
0x180018898  jnz     short loc_1800188EB
0x18001889a  mov     [rsp+68h+lpThreadId], rdi; lpThreadId
0x18001889f  lea     r8, ?SrClusterEventsWorkerThread@@YAKPEAX@Z; lpStartAddress
0x1800188a6  mov     r9, rbx; lpParameter
0x1800188a9  mov     [rsp+68h+dwCreationFlags], edi; dwCreationFlags
0x1800188ad  xor     edx, edx; dwStackSize
0x1800188af  mov     [rbx+10h], rbp
0x1800188b3  xor     ecx, ecx; lpThreadAttributes
0x1800188b5  mov     byte ptr [rbx+1Ch], 1
0x1800188b9  mov     [rbx+18h], r14d
0x1800188bd  call    cs:__imp_CreateThread
0x1800188c3  mov     [rbx+20h], rax
0x1800188c7  test    rax, rax
0x1800188ca  jnz     short loc_1800188EB
0x1800188cc  call    cs:__imp_GetLastError
0x1800188d2  mov     edi, eax
0x1800188d4  test    eax, eax
0x1800188d6  jz      short loc_1800188EB
0x1800188d8  mov     byte ptr [rbx+1Ch], 0
0x1800188dc  mov     qword ptr [rbx+10h], 0
0x1800188e4  mov     dword ptr [rbx+18h], 0
0x1800188eb  lea     rcx, [rbx+8]; SRWLock
0x1800188ef  call    cs:__imp_ReleaseSRWLockExclusive
0x1800188f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800188fc  cmp     rcx, r12
0x1800188ff  jz      short loc_18001891F
0x180018901  test    byte ptr [rcx+1Ch], 1
0x180018905  jz      short loc_18001891F
0x180018907  mov     rcx, [rcx+10h]
0x18001890b  lea     r8, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids
0x180018912  mov     edx, 19h
0x180018917  mov     r9d, edi
0x18001891a  call    WPP_SF_d
0x18001891f  mov     eax, edi
0x180018921  add     rsp, 38h
0x180018925  pop     r14
0x180018927  pop     r12
0x180018929  pop     rdi
0x18001892a  pop     rsi
0x18001892b  pop     rbp
0x18001892c  pop     rbx
0x18001892d  retn
```
