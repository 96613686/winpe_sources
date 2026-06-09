# UbpmpActionContextCleanup

- ea: `0x180007990`
- end: `0x180007c40`
- name: `UbpmpActionContextCleanup`
- size: `688`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180006650`
- `0x180007480`
- `0x180008f30`
- `0x18000a710`

## callees

- `0x1800049b4`
- `0x180007990`
- `0x180009750`
- `0x18000c248`
- `0x18002eb98`
- `0x18003cdb0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180007b2e`
- `ntdll!RtlFreeHeap` at `0x180007b2e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800079e1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007b9f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800079e1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007b9f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007a68`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007ab4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007bd0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007a68`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007ab4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007bd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ba5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ba5`

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
  _QWORD *v11; // rax
  void **v12; // rcx
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h] BYREF
  __int64 v15; // [rsp+70h] [rbp+8h] BYREF

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
      v15 = v6;
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
              dword_18004CEE8 = GetCurrentThreadId();
              UbpmpMaintenanceTaskStoppedCallout(a1, v4, 0);
              dword_18004CEE8 = 0;
              RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
            }
            UbpmQueueConsumerClose(*((void **)v4 + 13));
            v11 = *(_QWORD **)v4;
            if ( *(void **)(*(_QWORD *)v4 + 8LL) != v4 || (v12 = (void **)*((_QWORD *)v4 + 1), *v12 != v4) )
              __fastfail(3u);
            *v12 = v11;
            v11[1] = v12;
            *((_QWORD *)v4 + 1) = v4;
            *(_QWORD *)v4 = v4;
            v15 = *((_QWORD *)v4 + 4);
            if ( v15 )
              UbpmpDecrementRefAndDelete(&v15, 1);
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
    UbpmpDecrementTaskRefAndDelete(&v15);
    goto LABEL_15;
  }
  return (char)v1;
}

```

## disassembly

```asm
0x180007990  mov     rax, rsp
0x180007993  push    rbx
0x180007994  push    rsi
0x180007995  push    rdi
0x180007996  sub     rsp, 50h
0x18000799a  lea     rdi, [rcx+0E0h]
0x1800079a1  mov     rsi, rcx
0x1800079a4  mov     rbx, [rdi]
0x1800079a7  cmp     rbx, rdi
0x1800079aa  jz      loc_180007B5F
0x1800079b0  mov     [rax+10h], rbp
0x1800079b4  mov     [rax+20h], r13
0x1800079b8  mov     [rax-20h], r14
0x1800079bc  mov     [rax+18h], r12
0x1800079c0  mov     [rax-28h], r15
0x1800079c4  mov     r13, [rbx+20h]
0x1800079c8  mov     r14, [rbx+28h]
0x1800079cc  mov     rbp, [rbx]
0x1800079cf  mov     [rsp+68h+arg_0], r14
0x1800079d4  test    r13, r13
0x1800079d7  jz      loc_180007ABF
0x1800079dd  lea     rcx, [r13+40h]
0x1800079e1  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800079e7  call    cs:__imp_GetCurrentThreadId
0x1800079ed  mov     [r13+48h], eax
0x1800079f1  test    r14, r14
0x1800079f4  jnz     short loc_180007A70
0x1800079f6  movzx   eax, byte ptr [r13+68h]
0x1800079fb  test    al, 4
0x1800079fd  jnz     loc_180007B67
0x180007a03  xor     r12d, r12d
0x180007a06  test    r14, r14
0x180007a09  jnz     loc_180007AA8
0x180007a0f  test    al, 10h
0x180007a11  jz      loc_180007AA8
0x180007a17  mov     r12d, 1
0x180007a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a24  lea     rax, WPP_GLOBAL_Control
0x180007a2b  cmp     rcx, rax
0x180007a2e  jz      short loc_180007AA8
0x180007a30  test    byte ptr [rcx+1Ch], 80h
0x180007a34  jz      short loc_180007AA8
0x180007a36  movzx   eax, word ptr [r13+0C4h]
0x180007a3e  mov     edx, 32h ; '2'
0x180007a43  mov     rcx, [rcx+10h]
0x180007a47  mov     r9, r13
0x180007a4a  mov     [rsp+68h+var_38], eax
0x180007a4e  mov     eax, [r13+20h]
0x180007a52  mov     [rsp+68h+var_40], r14
0x180007a57  mov     [rsp+68h+var_48], eax
0x180007a5b  call    WPP_SF_qdqd
0x180007a60  lea     rcx, [r13+40h]
0x180007a64  mov     [r13+48h], r14d
0x180007a68  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180007a6e  jmp     short loc_180007ABF
0x180007a70  test    byte ptr [r14+68h], 1
0x180007a75  jz      loc_1800079F6
0x180007a7b  mov     r12d, 1
0x180007a81  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a88  lea     rax, WPP_GLOBAL_Control
0x180007a8f  cmp     rcx, rax
0x180007a92  jz      short loc_180007A9E
0x180007a94  test    byte ptr [rcx+1Ch], 80h
0x180007a98  jnz     loc_180007BE2
0x180007a9e  lea     rcx, [rsp+68h+arg_0]
0x180007aa3  call    UbpmpDecrementTaskRefAndDelete
0x180007aa8  lea     rcx, [r13+40h]
0x180007aac  mov     dword ptr [r13+48h], 0
0x180007ab4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180007aba  test    r12d, r12d
0x180007abd  jz      short loc_180007B34
0x180007abf  mov     rax, [rsi+18h]
0x180007ac3  cmp     qword ptr [rax+30h], 0
0x180007ac8  jnz     loc_180007B98
0x180007ace  mov     rcx, [rbx+68h]; void *
0x180007ad2  call    UbpmQueueConsumerClose
0x180007ad7  mov     rax, [rbx]
0x180007ada  cmp     [rax+8], rbx
0x180007ade  jnz     loc_180007BDB
0x180007ae4  mov     rcx, [rbx+8]
0x180007ae8  cmp     [rcx], rbx
0x180007aeb  jnz     loc_180007BDB
0x180007af1  mov     [rcx], rax
0x180007af4  mov     [rax+8], rcx
0x180007af8  mov     [rbx+8], rbx
0x180007afc  mov     [rbx], rbx
0x180007aff  mov     rax, [rbx+20h]
0x180007b03  mov     [rsp+68h+arg_0], rax
0x180007b08  test    rax, rax
0x180007b0b  jz      short loc_180007B1C
0x180007b0d  mov     edx, 1
0x180007b12  lea     rcx, [rsp+68h+arg_0]
0x180007b17  call    UbpmpDecrementRefAndDelete
0x180007b1c  mov     rcx, gs:60h
0x180007b25  mov     r8, rbx; P
0x180007b28  xor     edx, edx; Flags
0x180007b2a  mov     rcx, [rcx+30h]; HeapHandle
0x180007b2e  call    cs:__imp_RtlFreeHeap
0x180007b34  mov     rbx, rbp
0x180007b37  cmp     rbp, rdi
0x180007b3a  jnz     loc_1800079C4
0x180007b40  mov     r12, [rsp+68h+arg_10]
0x180007b48  mov     r15, [rsp+68h+var_28]
0x180007b4d  mov     r13, [rsp+68h+arg_18]
0x180007b55  mov     rbp, [rsp+68h+arg_8]
0x180007b5a  mov     r14, [rsp+68h+var_20]
0x180007b5f  add     rsp, 50h
0x180007b63  pop     rdi
0x180007b64  pop     rsi
0x180007b65  pop     rbx
0x180007b66  retn
0x180007b67  mov     r12d, 1
0x180007b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b74  lea     rax, WPP_GLOBAL_Control
0x180007b7b  cmp     rcx, rax
0x180007b7e  jz      short loc_180007B8A
0x180007b80  test    byte ptr [rcx+1Ch], 80h
0x180007b84  jnz     loc_180007C11
0x180007b8a  test    r14, r14
0x180007b8d  jnz     loc_180007A9E
0x180007b93  jmp     loc_180007AA8
0x180007b98  lea     rcx, g_MaintenanceLaunchLock
0x180007b9f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180007ba5  call    cs:__imp_GetCurrentThreadId
0x180007bab  xor     r8d, r8d
0x180007bae  mov     rdx, rbx
0x180007bb1  mov     rcx, rsi
0x180007bb4  mov     cs:dword_18004CEE8, eax
0x180007bba  call    UbpmpMaintenanceTaskStoppedCallout
0x180007bbf  lea     rcx, g_MaintenanceLaunchLock
0x180007bc6  mov     cs:dword_18004CEE8, 0
0x180007bd0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180007bd6  jmp     loc_180007ACE
0x180007bdb  mov     ecx, 3
0x180007be0  int     29h; Win8: RtlFailFast(ecx)
0x180007be2  movzx   eax, word ptr [r13+0C4h]
0x180007bea  mov     edx, 30h ; '0'
0x180007bef  mov     rcx, [rcx+10h]
0x180007bf3  mov     r9, r13
0x180007bf6  mov     [rsp+68h+var_38], eax
0x180007bfa  mov     eax, [r13+20h]
0x180007bfe  mov     [rsp+68h+var_40], r14
0x180007c03  mov     [rsp+68h+var_48], eax
0x180007c07  call    WPP_SF_qdqd
0x180007c0c  jmp     loc_180007A9E
0x180007c11  movzx   eax, word ptr [r13+0C4h]
0x180007c19  mov     edx, 31h ; '1'
0x180007c1e  mov     rcx, [rcx+10h]
0x180007c22  mov     r9, r13
0x180007c25  mov     [rsp+68h+var_38], eax
0x180007c29  mov     eax, [r13+20h]
0x180007c2d  mov     [rsp+68h+var_40], r14
0x180007c32  mov     [rsp+68h+var_48], eax
0x180007c36  call    WPP_SF_qdqd
0x180007c3b  jmp     loc_180007B8A
```
