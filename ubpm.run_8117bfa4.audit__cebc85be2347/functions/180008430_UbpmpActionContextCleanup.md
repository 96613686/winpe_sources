# UbpmpActionContextCleanup

- ea: `0x180008430`
- end: `0x180008715`
- name: `UbpmpActionContextCleanup`
- size: `741`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180007000`
- `0x180007ec0`
- `0x180009a30`
- `0x180011480`

## callees

- `0x180004c30`
- `0x180005320`
- `0x180008430`
- `0x18001131c`
- `0x180030d58`
- `0x18003f7c4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800085ea`
- `ntdll!RtlFreeHeap` at `0x1800085ea`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008481`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008662`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008481`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008662`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008518`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000856a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000869f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008518`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000856a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000869f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000848d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000866e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000848d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000866e`

## pseudocode

```c
char __fastcall UbpmpActionContextCleanup(__int64 a1)
{
  _UNKNOWN **v1; // rax
  void *v2; // rdi
  void *v4; // rbx
  __int64 v5; // r13
  __int64 v6; // r14
  void *v7; // rbp
  __int64 v8; // r8
  char v9; // al
  int v10; // r12d
  __int64 v11; // r8
  __int64 v12; // r9
  _QWORD *v13; // rax
  void **v14; // rcx
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h] BYREF
  __int64 v17; // [rsp+70h] [rbp+8h] BYREF

  v1 = &retaddr;
  v2 = (void *)(a1 + 224);
  v4 = *(void **)(a1 + 224);
  if ( v4 != (void *)(a1 + 224) )
  {
    while ( 1 )
    {
      v5 = *((_QWORD *)v4 + 4);
      v6 = *((_QWORD *)v4 + 5);
      v7 = *(void **)v4;
      v17 = v6;
      if ( !v5 )
        goto LABEL_16;
      RtlAcquireSRWLockExclusive(v5 + 64);
      *(_DWORD *)(v5 + 72) = GetCurrentThreadId();
      if ( v6 )
      {
        if ( (*(_BYTE *)(v6 + 104) & 1) != 0 )
          break;
      }
      v9 = *(_BYTE *)(v5 + 104);
      if ( (v9 & 4) != 0 )
      {
        v10 = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_qdqd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            v8,
            v5,
            *(_DWORD *)(v5 + 32),
            v6,
            *(unsigned __int16 *)(v5 + 196));
        if ( v6 )
          goto LABEL_14;
      }
      else
      {
        v10 = 0;
        if ( !v6 && (v9 & 0x10) != 0 )
        {
          v10 = 1;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            WPP_SF_qdqd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50,
              v8,
              v5,
              *(_DWORD *)(v5 + 32),
              0,
              *(unsigned __int16 *)(v5 + 196));
            *(_DWORD *)(v5 + 72) = 0;
            RtlReleaseSRWLockExclusive(v5 + 64);
LABEL_16:
            if ( *(_QWORD *)(*(_QWORD *)(a1 + 24) + 48LL) )
            {
              RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
              dword_18004FFE8 = GetCurrentThreadId();
              UbpmpMaintenanceTaskStoppedCallout(a1, v4, 0);
              dword_18004FFE8 = 0;
              RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
            }
            UbpmQueueConsumerClose(*((void **)v4 + 13));
            v13 = *(_QWORD **)v4;
            if ( *(void **)(*(_QWORD *)v4 + 8LL) != v4 || (v14 = (void **)*((_QWORD *)v4 + 1), *v14 != v4) )
              __fastfail(3u);
            *v14 = v13;
            v13[1] = v14;
            *((_QWORD *)v4 + 1) = v4;
            *(_QWORD *)v4 = v4;
            v17 = *((_QWORD *)v4 + 4);
            if ( v17 )
              UbpmpDecrementRefAndDelete(&v17, 1, v11, v12);
            LOBYTE(v1) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
            goto LABEL_23;
          }
        }
      }
LABEL_15:
      *(_DWORD *)(v5 + 72) = 0;
      LOBYTE(v1) = RtlReleaseSRWLockExclusive(v5 + 64);
      if ( v10 )
        goto LABEL_16;
LABEL_23:
      v4 = v7;
      if ( v7 == v2 )
        return (char)v1;
    }
    v10 = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_qdqd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        v8,
        v5,
        *(_DWORD *)(v5 + 32),
        v6,
        *(unsigned __int16 *)(v5 + 196));
LABEL_14:
    UbpmpDecrementTaskRefAndDelete(&v17);
    goto LABEL_15;
  }
  return (char)v1;
}

```

## disassembly

```asm
0x180008430  mov     rax, rsp
0x180008433  push    rbx
0x180008434  push    rsi
0x180008435  push    rdi
0x180008436  sub     rsp, 50h
0x18000843a  lea     rdi, [rcx+0E0h]
0x180008441  mov     rsi, rcx
0x180008444  mov     rbx, [rdi]
0x180008447  cmp     rbx, rdi
0x18000844a  jz      loc_180008621
0x180008450  mov     [rax+10h], rbp
0x180008454  mov     [rax+20h], r13
0x180008458  mov     [rax-20h], r14
0x18000845c  mov     [rax+18h], r12
0x180008460  mov     [rax-28h], r15
0x180008464  mov     r13, [rbx+20h]
0x180008468  mov     r14, [rbx+28h]
0x18000846c  mov     rbp, [rbx]
0x18000846f  mov     [rsp+68h+arg_0], r14
0x180008474  test    r13, r13
0x180008477  jz      loc_18000857B
0x18000847d  lea     rcx, [r13+40h]
0x180008481  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180008488  nop     dword ptr [rax+rax+00h]
0x18000848d  call    cs:__imp_GetCurrentThreadId
0x180008494  nop     dword ptr [rax+rax+00h]
0x180008499  mov     [r13+48h], eax
0x18000849d  test    r14, r14
0x1800084a0  jnz     loc_180008526
0x1800084a6  movzx   eax, byte ptr [r13+68h]
0x1800084ab  test    al, 4
0x1800084ad  jnz     loc_18000862A
0x1800084b3  xor     r12d, r12d
0x1800084b6  test    r14, r14
0x1800084b9  jnz     loc_18000855E
0x1800084bf  test    al, 10h
0x1800084c1  jz      loc_18000855E
0x1800084c7  mov     r12d, 1
0x1800084cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084d4  lea     rax, WPP_GLOBAL_Control
0x1800084db  cmp     rcx, rax
0x1800084de  jz      short loc_18000855E
0x1800084e0  test    byte ptr [rcx+1Ch], 80h
0x1800084e4  jz      short loc_18000855E
0x1800084e6  movzx   eax, word ptr [r13+0C4h]
0x1800084ee  mov     edx, 32h ; '2'
0x1800084f3  mov     rcx, [rcx+10h]
0x1800084f7  mov     r9, r13
0x1800084fa  mov     [rsp+68h+var_38], eax
0x1800084fe  mov     eax, [r13+20h]
0x180008502  mov     [rsp+68h+var_40], r14
0x180008507  mov     [rsp+68h+var_48], eax
0x18000850b  call    WPP_SF_qdqd
0x180008510  lea     rcx, [r13+40h]
0x180008514  mov     [r13+48h], r14d
0x180008518  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000851f  nop     dword ptr [rax+rax+00h]
0x180008524  jmp     short loc_18000857B
0x180008526  test    byte ptr [r14+68h], 1
0x18000852b  jz      loc_1800084A6
0x180008531  mov     r12d, 1
0x180008537  mov     rcx, cs:WPP_GLOBAL_Control
0x18000853e  lea     rax, WPP_GLOBAL_Control
0x180008545  cmp     rcx, rax
0x180008548  jz      short loc_180008554
0x18000854a  test    byte ptr [rcx+1Ch], 80h
0x18000854e  jnz     loc_1800086B7
0x180008554  lea     rcx, [rsp+68h+arg_0]
0x180008559  call    UbpmpDecrementTaskRefAndDelete
0x18000855e  lea     rcx, [r13+40h]
0x180008562  mov     dword ptr [r13+48h], 0
0x18000856a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008571  nop     dword ptr [rax+rax+00h]
0x180008576  test    r12d, r12d
0x180008579  jz      short loc_1800085F6
0x18000857b  mov     rax, [rsi+18h]
0x18000857f  cmp     qword ptr [rax+30h], 0
0x180008584  jnz     loc_18000865B
0x18000858a  mov     rcx, [rbx+68h]; void *
0x18000858e  call    UbpmQueueConsumerClose
0x180008593  mov     rax, [rbx]
0x180008596  cmp     [rax+8], rbx
0x18000859a  jnz     loc_1800086B0
0x1800085a0  mov     rcx, [rbx+8]
0x1800085a4  cmp     [rcx], rbx
0x1800085a7  jnz     loc_1800086B0
0x1800085ad  mov     [rcx], rax
0x1800085b0  mov     [rax+8], rcx
0x1800085b4  mov     [rbx+8], rbx
0x1800085b8  mov     [rbx], rbx
0x1800085bb  mov     rax, [rbx+20h]
0x1800085bf  mov     [rsp+68h+arg_0], rax
0x1800085c4  test    rax, rax
0x1800085c7  jz      short loc_1800085D8
0x1800085c9  mov     edx, 1
0x1800085ce  lea     rcx, [rsp+68h+arg_0]
0x1800085d3  call    UbpmpDecrementRefAndDelete
0x1800085d8  mov     rcx, gs:60h
0x1800085e1  mov     r8, rbx; P
0x1800085e4  xor     edx, edx; Flags
0x1800085e6  mov     rcx, [rcx+30h]; HeapHandle
0x1800085ea  call    cs:__imp_RtlFreeHeap
0x1800085f1  nop     dword ptr [rax+rax+00h]
0x1800085f6  mov     rbx, rbp
0x1800085f9  cmp     rbp, rdi
0x1800085fc  jnz     loc_180008464
0x180008602  mov     r12, [rsp+68h+arg_10]
0x18000860a  mov     r15, [rsp+68h+var_28]
0x18000860f  mov     r13, [rsp+68h+arg_18]
0x180008617  mov     rbp, [rsp+68h+arg_8]
0x18000861c  mov     r14, [rsp+68h+var_20]
0x180008621  add     rsp, 50h
0x180008625  pop     rdi
0x180008626  pop     rsi
0x180008627  pop     rbx
0x180008628  retn
0x18000862a  mov     r12d, 1
0x180008630  mov     rcx, cs:WPP_GLOBAL_Control
0x180008637  lea     rax, WPP_GLOBAL_Control
0x18000863e  cmp     rcx, rax
0x180008641  jz      short loc_18000864D
0x180008643  test    byte ptr [rcx+1Ch], 80h
0x180008647  jnz     loc_1800086E6
0x18000864d  test    r14, r14
0x180008650  jnz     loc_180008554
0x180008656  jmp     loc_18000855E
0x18000865b  lea     rcx, g_MaintenanceLaunchLock
0x180008662  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180008669  nop     dword ptr [rax+rax+00h]
0x18000866e  call    cs:__imp_GetCurrentThreadId
0x180008675  nop     dword ptr [rax+rax+00h]
0x18000867a  xor     r8d, r8d
0x18000867d  mov     rdx, rbx
0x180008680  mov     rcx, rsi
0x180008683  mov     cs:dword_18004FFE8, eax
0x180008689  call    UbpmpMaintenanceTaskStoppedCallout
0x18000868e  lea     rcx, g_MaintenanceLaunchLock
0x180008695  mov     cs:dword_18004FFE8, 0
0x18000869f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800086a6  nop     dword ptr [rax+rax+00h]
0x1800086ab  jmp     loc_18000858A
0x1800086b0  mov     ecx, 3
0x1800086b5  int     29h; Win8: RtlFailFast(ecx)
0x1800086b7  movzx   eax, word ptr [r13+0C4h]
0x1800086bf  mov     edx, 30h ; '0'
0x1800086c4  mov     rcx, [rcx+10h]
0x1800086c8  mov     r9, r13
0x1800086cb  mov     [rsp+68h+var_38], eax
0x1800086cf  mov     eax, [r13+20h]
0x1800086d3  mov     [rsp+68h+var_40], r14
0x1800086d8  mov     [rsp+68h+var_48], eax
0x1800086dc  call    WPP_SF_qdqd
0x1800086e1  jmp     loc_180008554
0x1800086e6  movzx   eax, word ptr [r13+0C4h]
0x1800086ee  mov     edx, 31h ; '1'
0x1800086f3  mov     rcx, [rcx+10h]
0x1800086f7  mov     r9, r13
0x1800086fa  mov     [rsp+68h+var_38], eax
0x1800086fe  mov     eax, [r13+20h]
0x180008702  mov     [rsp+68h+var_40], r14
0x180008707  mov     [rsp+68h+var_48], eax
0x18000870b  call    WPP_SF_qdqd
0x180008710  jmp     loc_18000864D
```
