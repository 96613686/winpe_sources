# PfsCombineWorker

- ea: `0x180055f70`
- end: `0x180056205`
- name: `PfsCombineWorker`
- size: `661`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18003c534`
- `0x180055f70`
- `0x18005b8a4`
- `0x18005c148`
- `0x1800665e8`
- `0x1800668d4`
- `0x180086bf4`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18005603f`
- `ntdll!NtQueryInformationThread` at `0x18005603f`
- `ntdll!NtSetInformationThread` at `0x180056069`
- `ntdll!NtSetInformationThread` at `0x180056069`
- `ntdll!NtSetSystemInformation` at `0x18005611f`
- `ntdll!NtSetSystemInformation` at `0x18005611f`
- `ntdll!RtlNtStatusToDosError` at `0x18005604b`
- `ntdll!RtlNtStatusToDosError` at `0x18005604b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180055fe3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180055fe3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180056000`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180056000`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005619e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005619e`

## pseudocode

```c
__int64 __fastcall PfsCombineWorker(__int64 a1)
{
  ULONG PrefetchServiceThreadPrivileges; // edi
  __int64 v3; // rcx
  HANDLE CurrentThread; // rax
  unsigned int v5; // r14d
  int v6; // eax
  unsigned int v7; // ecx
  unsigned int v8; // r8d
  unsigned int v9; // r10d
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // r10d
  int v13; // eax
  unsigned int v14; // edx
  __int64 v15; // rcx
  __int64 v16; // rdx
  void *v17; // r8
  __int64 v18; // r8
  _BYTE SystemInformation[24]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v21; // [rsp+48h] [rbp-30h] BYREF
  __int128 ThreadInformation; // [rsp+58h] [rbp-20h] BYREF

  ThreadInformation = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  v21 = 0;
  PfsCombineLog(&PFS_COMBINE_START);
  PrefetchServiceThreadPrivileges = PfSvGetPrefetchServiceThreadPrivileges(1);
  if ( !PrefetchServiceThreadPrivileges )
  {
    v3 = *(_QWORD *)&PfSvcGlobals;
    if ( (*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 244LL) & 0x30000u) < 0x30000 )
    {
      CurrentThread = GetCurrentThread();
      v3 = *(_QWORD *)&PfSvcGlobals;
      if ( (*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 244LL) & 0x30000) == 0 )
      {
        SetThreadPriority(CurrentThread, -15);
        v3 = *(_QWORD *)&PfSvcGlobals;
      }
    }
    v5 = 3;
    if ( *(_DWORD *)(v3 + 332) == 3
      && ((v6 = NtQueryInformationThread(
                  (HANDLE)0xFFFFFFFFFFFFFFFELL,
                  MaxThreadInfoClass|ThreadPriority,
                  &ThreadInformation,
                  0x10u,
                  0),
           v6 < 0)
       || (*(_QWORD *)&ThreadInformation = ThreadInformation & 0xFFFFFFFFFFFFFFFDuLL,
           v6 = NtSetInformationThread(
                  (HANDLE)0xFFFFFFFFFFFFFFFELL,
                  MaxThreadInfoClass|ThreadPriority,
                  &ThreadInformation,
                  0x10u),
           v6 < 0)) )
    {
      PrefetchServiceThreadPrivileges = RtlNtStatusToDosError(v6);
    }
    else
    {
      PrefetchServiceThreadPrivileges = 0;
      if ( *(_DWORD *)(a1 + 56) )
      {
        PfsQueryCombineStats(&v21);
        if ( *(_DWORD *)(a1 + 56) == DWORD1(v21) )
        {
          v7 = *(_DWORD *)(a1 + 60);
          v8 = v7 - (HIDWORD(v21) - DWORD2(v21));
          v9 = v7 + HIDWORD(v21) - DWORD2(v21);
          if ( v7 < HIDWORD(v21) - DWORD2(v21) )
            v8 = 0;
          v10 = MEMORY[0x7FFE03B0];
          v11 = MEMORY[0x7FFE0008];
          v12 = v9 >> 1;
          while ( v10 != MEMORY[0x7FFE03B0] )
          {
            _mm_pause();
            v10 = MEMORY[0x7FFE03B0];
            v11 = MEMORY[0x7FFE0008];
          }
          PfsRecordCombineStats(a1, v12, v8, ((unsigned int)((v11 - v10) / 0x989680uLL) - *(_DWORD *)(a1 + 48)) / 0x3C);
        }
      }
      *(_QWORD *)SystemInformation = *(_QWORD *)(a1 + 8);
      *(_OWORD *)&SystemInformation[8] = 0;
      NtSetSystemInformation((SYSTEM_INFORMATION_CLASS)130, SystemInformation, 0x18u);
      PfsQueryCombineStats(&v21);
      v13 = DWORD1(v21);
      v14 = HIDWORD(v21) - DWORD2(v21);
      *(_DWORD *)(a1 + 56) = DWORD1(v21);
      *(_DWORD *)(a1 + 60) = v14;
      if ( v13 == 1 )
        PfsRecordCombineStats(a1, v14, 0, 0);
      v15 = MEMORY[0x7FFE03B0];
      v16 = MEMORY[0x7FFE0008];
      while ( v15 != MEMORY[0x7FFE03B0] )
      {
        _mm_pause();
        v15 = MEMORY[0x7FFE03B0];
        v16 = MEMORY[0x7FFE0008];
      }
      v17 = *(void **)(a1 + 40);
      *(_DWORD *)(a1 + 48) = (v16 - v15) / 0x989680uLL;
      if ( v17 )
      {
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v17);
        *(_QWORD *)(a1 + 40) = 0;
      }
      PfsGetSortedProcessSnapshot(a1 + 40);
      if ( (unsigned int)(*(_DWORD *)(a1 + 24) - 1) <= 1 )
      {
        v18 = 240000;
      }
      else
      {
        v18 = *(unsigned int *)(a1 + 28);
        v5 = 0;
      }
      PfsQueueCombineTimer(a1, v5, v18, 0);
    }
  }
  PfsCombineLog(&PFS_COMBINE_STOP);
  return PrefetchServiceThreadPrivileges;
}

```

## disassembly

```asm
0x180055f70  push    rbp
0x180055f72  push    rbx
0x180055f73  push    rsi
0x180055f74  push    rdi
0x180055f75  push    r12
0x180055f77  push    r14
0x180055f79  mov     rbp, rsp
0x180055f7c  sub     rsp, 78h
0x180055f80  mov     rax, cs:__security_cookie
0x180055f87  xor     rax, rsp
0x180055f8a  mov     [rbp+var_10], rax
0x180055f8e  xorps   xmm0, xmm0
0x180055f91  mov     rbx, rcx
0x180055f94  xorps   xmm1, xmm1
0x180055f97  lea     rcx, PFS_COMBINE_START; EventDescriptor
0x180055f9e  xor     eax, eax
0x180055fa0  xor     edx, edx
0x180055fa2  movups  [rbp+ThreadInformation], xmm0
0x180055fa6  mov     [rbp+var_38], rax
0x180055faa  movups  [rbp+SystemInformation], xmm1
0x180055fae  movups  [rbp+var_30], xmm0
0x180055fb2  call    PfsCombineLog
0x180055fb7  mov     ecx, 1
0x180055fbc  call    PfSvGetPrefetchServiceThreadPrivileges
0x180055fc1  mov     edi, eax
0x180055fc3  test    eax, eax
0x180055fc5  jnz     loc_1800561DA
0x180055fcb  mov     rcx, cs:PfSvcGlobals
0x180055fd2  mov     edi, 30000h
0x180055fd7  mov     eax, [rcx+0F4h]
0x180055fdd  and     eax, edi
0x180055fdf  cmp     eax, edi
0x180055fe1  jnb     short loc_18005600D
0x180055fe3  call    cs:__imp_GetCurrentThread
0x180055fe9  mov     rcx, cs:PfSvcGlobals
0x180055ff0  test    [rcx+0F4h], edi
0x180055ff6  jnz     short loc_18005600D
0x180055ff8  mov     edx, 0FFFFFFF1h; nPriority
0x180055ffd  mov     rcx, rax; hThread
0x180056000  call    cs:__imp_SetThreadPriority
0x180056006  mov     rcx, cs:PfSvcGlobals
0x18005600d  mov     r14d, 3
0x180056013  cmp     [rcx+14Ch], r14d
0x18005601a  jnz     short loc_180056073
0x18005601c  lea     edi, [r14+0Dh]
0x180056020  mov     [rsp+78h+ReturnLength], 0; ReturnLength
0x180056029  lea     esi, [rdi+0Eh]
0x18005602c  mov     r12, 0FFFFFFFFFFFFFFFEh
0x180056033  mov     edx, esi; ThreadInformationClass
0x180056035  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x180056039  mov     r9d, edi; ThreadInformationLength
0x18005603c  mov     rcx, r12; ThreadHandle
0x18005603f  call    cs:__imp_NtQueryInformationThread
0x180056045  test    eax, eax
0x180056047  jns     short loc_180056058
0x180056049  mov     ecx, eax; Status
0x18005604b  call    cs:__imp_RtlNtStatusToDosError
0x180056051  mov     edi, eax
0x180056053  jmp     loc_1800561DA
0x180056058  and     qword ptr [rbp+ThreadInformation], 0FFFFFFFFFFFFFFFDh
0x18005605d  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x180056061  mov     r9d, edi; ThreadInformationLength
0x180056064  mov     edx, esi; ThreadInformationClass
0x180056066  mov     rcx, r12; ThreadHandle
0x180056069  call    cs:__imp_NtSetInformationThread
0x18005606f  test    eax, eax
0x180056071  js      short loc_180056049
0x180056073  xor     edi, edi
0x180056075  mov     esi, 7FFE03B0h
0x18005607a  mov     r12d, 7FFE0008h
0x180056080  cmp     [rbx+38h], edi
0x180056083  jz      short loc_180056101
0x180056085  lea     rcx, [rbp+var_30]
0x180056089  call    PfsQueryCombineStats
0x18005608e  mov     eax, dword ptr [rbp+var_30+4]
0x180056091  cmp     [rbx+38h], eax
0x180056094  jnz     short loc_180056101
0x180056096  mov     ecx, [rbx+3Ch]
0x180056099  xor     eax, eax
0x18005609b  mov     edx, dword ptr [rbp+var_30+0Ch]
0x18005609e  mov     r8d, ecx
0x1800560a1  sub     edx, dword ptr [rbp+var_30+8]
0x1800560a4  sub     r8d, edx
0x1800560a7  cmp     ecx, edx
0x1800560a9  lea     r10d, [rcx+rdx]
0x1800560ad  cmovb   r8d, eax
0x1800560b1  mov     rcx, [rsi]
0x1800560b4  mov     rdx, ds:7FFE0008h
0x1800560bc  shr     r10d, 1
0x1800560bf  mov     rax, [rsi]
0x1800560c2  cmp     rcx, rax
0x1800560c5  jz      short loc_1800560D2
0x1800560c7  pause
0x1800560c9  mov     rcx, [rsi]
0x1800560cc  mov     rdx, [r12]
0x1800560d0  jmp     short loc_1800560BF
0x1800560d2  sub     rdx, rcx
0x1800560d5  mov     rax, 0D6BF94D5E57A42BDh
0x1800560df  mul     rdx
0x1800560e2  mov     eax, 88888889h
0x1800560e7  mov     rcx, rbx
0x1800560ea  shr     rdx, 17h
0x1800560ee  sub     edx, [rbx+30h]
0x1800560f1  mul     edx
0x1800560f3  shr     edx, 5
0x1800560f6  mov     r9d, edx
0x1800560f9  mov     edx, r10d
0x1800560fc  call    PfsRecordCombineStats
0x180056101  mov     rax, [rbx+8]
0x180056105  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x180056109  mov     r8d, 18h; SystemInformationLength
0x18005610f  mov     qword ptr [rbp+SystemInformation], rax
0x180056113  xorps   xmm0, xmm0
0x180056116  movdqu  [rbp+SystemInformation+8], xmm0
0x18005611b  lea     ecx, [r8+6Ah]; SystemInformationClass
0x18005611f  call    cs:__imp_NtSetSystemInformation
0x180056125  lea     rcx, [rbp+var_30]
0x180056129  call    PfsQueryCombineStats
0x18005612e  mov     eax, dword ptr [rbp+var_30+4]
0x180056131  mov     edx, dword ptr [rbp+var_30+0Ch]
0x180056134  sub     edx, dword ptr [rbp+var_30+8]
0x180056137  mov     [rbx+38h], eax
0x18005613a  mov     [rbx+3Ch], edx
0x18005613d  cmp     eax, 1
0x180056140  jnz     short loc_180056150
0x180056142  xor     r9d, r9d
0x180056145  xor     r8d, r8d
0x180056148  mov     rcx, rbx
0x18005614b  call    PfsRecordCombineStats
0x180056150  mov     rcx, [rsi]
0x180056153  mov     rdx, ds:7FFE0008h
0x18005615b  jmp     short loc_180056166
0x18005615d  pause
0x18005615f  mov     rcx, [rsi]
0x180056162  mov     rdx, [r12]
0x180056166  mov     rax, [rsi]
0x180056169  cmp     rcx, rax
0x18005616c  jnz     short loc_18005615D
0x18005616e  sub     rdx, rcx
0x180056171  lea     rsi, [rbx+28h]
0x180056175  mov     r8, [rsi]; lpMem
0x180056178  mov     rax, 0D6BF94D5E57A42BDh
0x180056182  mul     rdx
0x180056185  shr     rdx, 17h
0x180056189  mov     [rbx+30h], edx
0x18005618c  test    r8, r8
0x18005618f  jz      short loc_1800561AB
0x180056191  mov     rcx, cs:PfSvcGlobals
0x180056198  xor     edx, edx; dwFlags
0x18005619a  mov     rcx, [rcx+58h]; hHeap
0x18005619e  call    cs:__imp_HeapFree
0x1800561a4  mov     qword ptr [rsi], 0
0x1800561ab  mov     rcx, rsi
0x1800561ae  call    PfsGetSortedProcessSnapshot
0x1800561b3  mov     eax, [rbx+18h]
0x1800561b6  dec     eax
0x1800561b8  cmp     eax, 1
0x1800561bb  jbe     short loc_1800561C6
0x1800561bd  mov     r8d, [rbx+1Ch]
0x1800561c1  xor     r14d, r14d
0x1800561c4  jmp     short loc_1800561CC
0x1800561c6  mov     r8d, 3A980h
0x1800561cc  xor     r9d, r9d
0x1800561cf  mov     edx, r14d
0x1800561d2  mov     rcx, rbx
0x1800561d5  call    PfsQueueCombineTimer
0x1800561da  lea     rdx, [rbp+SystemInformation+8]
0x1800561de  lea     rcx, PFS_COMBINE_STOP; EventDescriptor
0x1800561e5  call    PfsCombineLog
0x1800561ea  mov     eax, edi
0x1800561ec  mov     rcx, [rbp+var_10]
0x1800561f0  xor     rcx, rsp; StackCookie
0x1800561f3  call    __security_check_cookie
0x1800561f8  add     rsp, 78h
0x1800561fc  pop     r14
0x1800561fe  pop     r12
0x180056200  pop     rdi
0x180056201  pop     rsi
0x180056202  pop     rbx
0x180056203  pop     rbp
0x180056204  retn
```
