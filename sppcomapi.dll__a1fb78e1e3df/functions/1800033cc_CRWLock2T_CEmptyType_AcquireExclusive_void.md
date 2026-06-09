# CRWLock2T<CEmptyType>::AcquireExclusive(void)

- ea: `0x1800033cc`
- end: `0x180003519`
- name: `?AcquireExclusive@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ`
- size: `333`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003020`
- `0x1800050f0`
- `0x18001c300`
- `0x18001c470`
- `0x18001c5e0`
- `0x18001c750`
- `0x18001c8c0`
- `0x18001f5f0`
- `0x18001f760`

## callees

- `0x1800033cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800033f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003449`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800033f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003449`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003476`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800034c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003476`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800034c4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800034dd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800034dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003493`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800034fa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003493`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800034fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003422`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003422`

## pseudocode

```c
void __fastcall CRWLock2T<CEmptyType>::AcquireExclusive(__int64 a1)
{
  DWORD CurrentThreadId; // r15d
  DWORD *v3; // rsi
  int v4; // ebp
  DWORD v5; // eax
  DWORD v6; // r12d
  int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // rax

  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v3 = (DWORD *)(a1 + 80);
  if ( !*(_DWORD *)(a1 + 64) )
  {
    *(_DWORD *)(a1 + 76) = 1;
    *v3 = CurrentThreadId;
    *(_DWORD *)(a1 + 84) = 1;
    *(_DWORD *)(a1 + 64) = 1;
    goto LABEL_20;
  }
  if ( !*(_DWORD *)(a1 + 76) || *v3 != CurrentThreadId )
  {
    v4 = 0;
    v5 = GetCurrentThreadId();
    v6 = v5;
    if ( *(_DWORD *)(a1 + 64) )
    {
      if ( *v3 == v5 )
      {
        v7 = *(_DWORD *)(a1 + 84);
LABEL_16:
        if ( v7 )
          RaiseException(0xC0000194, 0, 0, 0);
        goto LABEL_18;
      }
      if ( !*(_DWORD *)(a1 + 76) )
      {
        v7 = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
        if ( *(_DWORD *)(a1 + 96) )
        {
          v8 = *(_QWORD *)(a1 + 88);
          v9 = 0;
          while ( *(_DWORD *)(v8 + 8 * v9) != v6 )
          {
            v9 = (unsigned int)(v9 + 1);
            if ( (unsigned int)v9 >= *(_DWORD *)(a1 + 96) )
              goto LABEL_15;
          }
          v7 = *(_DWORD *)(v8 + 8 * v9 + 4);
        }
LABEL_15:
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
        goto LABEL_16;
      }
    }
LABEL_18:
    ++*(_DWORD *)(a1 + 72);
    goto LABEL_21;
  }
  ++*(_DWORD *)(a1 + 84);
LABEL_20:
  v4 = 1;
LABEL_21:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( !v4 )
  {
    if ( WaitForSingleObject(*(HANDLE *)(a1 + 48), 0x337F9800u) )
      RaiseException(0xC0000194, 0, 0, 0);
    *(_DWORD *)(a1 + 80) = CurrentThreadId;
  }
}

```

## disassembly

```asm
0x1800033cc  push    rbx
0x1800033ce  push    rbp
0x1800033cf  push    rsi
0x1800033d0  push    r12
0x1800033d2  push    r14
0x1800033d4  push    r15
0x1800033d6  sub     rsp, 28h
0x1800033da  mov     rbx, rcx
0x1800033dd  call    cs:__imp_GetCurrentThreadId
0x1800033e4  nop     dword ptr [rax+rax+00h]
0x1800033e9  lea     r14, [rbx+8]
0x1800033ed  mov     r15d, eax
0x1800033f0  mov     rcx, r14; lpCriticalSection
0x1800033f3  call    cs:__imp_EnterCriticalSection
0x1800033fa  nop     dword ptr [rax+rax+00h]
0x1800033ff  cmp     dword ptr [rbx+40h], 0
0x180003403  lea     rsi, [rbx+50h]
0x180003407  jbe     loc_1800034A4
0x18000340d  cmp     dword ptr [rbx+4Ch], 0
0x180003411  jz      short loc_180003420
0x180003413  cmp     [rsi], r15d
0x180003416  jnz     short loc_180003420
0x180003418  inc     dword ptr [rbx+54h]
0x18000341b  jmp     loc_1800034BC
0x180003420  xor     ebp, ebp
0x180003422  call    cs:__imp_GetCurrentThreadId
0x180003429  nop     dword ptr [rax+rax+00h]
0x18000342e  mov     r12d, eax
0x180003431  cmp     [rbx+40h], ebp
0x180003434  jbe     short loc_18000349F
0x180003436  cmp     [rsi], eax
0x180003438  jnz     short loc_18000343F
0x18000343a  mov     esi, [rbx+54h]
0x18000343d  jmp     short loc_180003482
0x18000343f  cmp     [rbx+4Ch], ebp
0x180003442  jnz     short loc_18000349F
0x180003444  mov     rcx, r14; lpCriticalSection
0x180003447  xor     esi, esi
0x180003449  call    cs:__imp_EnterCriticalSection
0x180003450  nop     dword ptr [rax+rax+00h]
0x180003455  cmp     [rbx+60h], esi
0x180003458  jbe     short loc_180003473
0x18000345a  mov     rdx, [rbx+58h]
0x18000345e  xor     eax, eax
0x180003460  cmp     [rdx+rax*8], r12d
0x180003464  jz      short loc_18000346F
0x180003466  inc     eax
0x180003468  cmp     eax, [rbx+60h]
0x18000346b  jb      short loc_180003460
0x18000346d  jmp     short loc_180003473
0x18000346f  mov     esi, [rdx+rax*8+4]
0x180003473  mov     rcx, r14; lpCriticalSection
0x180003476  call    cs:__imp_LeaveCriticalSection
0x18000347d  nop     dword ptr [rax+rax+00h]
0x180003482  test    esi, esi
0x180003484  jz      short loc_18000349F
0x180003486  xor     r9d, r9d; lpArguments
0x180003489  xor     r8d, r8d; nNumberOfArguments
0x18000348c  xor     edx, edx; dwExceptionFlags
0x18000348e  mov     ecx, 0C0000194h; dwExceptionCode
0x180003493  call    cs:__imp_RaiseException
0x18000349a  nop     dword ptr [rax+rax+00h]
0x18000349f  inc     dword ptr [rbx+48h]
0x1800034a2  jmp     short loc_1800034C1
0x1800034a4  mov     dword ptr [rbx+4Ch], 1
0x1800034ab  mov     [rsi], r15d
0x1800034ae  mov     dword ptr [rbx+54h], 1
0x1800034b5  mov     dword ptr [rbx+40h], 1
0x1800034bc  mov     ebp, 1
0x1800034c1  mov     rcx, r14; lpCriticalSection
0x1800034c4  call    cs:__imp_LeaveCriticalSection
0x1800034cb  nop     dword ptr [rax+rax+00h]
0x1800034d0  test    ebp, ebp
0x1800034d2  jnz     short loc_18000350A
0x1800034d4  mov     rcx, [rbx+30h]; hHandle
0x1800034d8  mov     edx, 337F9800h; dwMilliseconds
0x1800034dd  call    cs:__imp_WaitForSingleObject
0x1800034e4  nop     dword ptr [rax+rax+00h]
0x1800034e9  test    eax, eax
0x1800034eb  jz      short loc_180003506
0x1800034ed  xor     r9d, r9d; lpArguments
0x1800034f0  xor     r8d, r8d; nNumberOfArguments
0x1800034f3  xor     edx, edx; dwExceptionFlags
0x1800034f5  mov     ecx, 0C0000194h; dwExceptionCode
0x1800034fa  call    cs:__imp_RaiseException
0x180003501  nop     dword ptr [rax+rax+00h]
0x180003506  mov     [rbx+50h], r15d
0x18000350a  add     rsp, 28h
0x18000350e  pop     r15
0x180003510  pop     r14
0x180003512  pop     r12
0x180003514  pop     rsi
0x180003515  pop     rbp
0x180003516  pop     rbx
0x180003517  retn
```
