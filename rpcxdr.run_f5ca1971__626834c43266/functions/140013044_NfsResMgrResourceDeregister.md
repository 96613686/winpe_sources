# NfsResMgrResourceDeregister

- ea: `0x140013044`
- end: `0x140013186`
- name: `NfsResMgrResourceDeregister`
- size: `322`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a24c`
- `0x140010d50`
- `0x1400123e8`
- `0x1400201dc`
- `0x140020640`

## callees

- `0x1400122e0`
- `0x140013044`
- `0x140013738`
- `0x140013828`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400130a3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400130e7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400130a3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400130e7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400130c8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140013119`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400130c8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140013119`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140013106`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140013106`

## pseudocode

```c
__int64 __fastcall NfsResMgrResourceDeregister(__int64 a1)
{
  int v1; // esi
  PVOID v2; // rdi
  int v3; // ebx
  unsigned __int32 v4; // eax
  unsigned __int32 v5; // eax
  _BYTE LockHandle[32]; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v8[32]; // [rsp+40h] [rbp-19h] BYREF
  __int128 Buffer; // [rsp+60h] [rbp+7h] BYREF
  __int128 v10; // [rsp+70h] [rbp+17h]
  __int64 v11; // [rsp+80h] [rbp+27h]
  PVOID P; // [rsp+C8h] [rbp+6Fh] BYREF

  P = 0;
  v10 = 0;
  DWORD2(v10) = a1;
  Buffer = 0;
  v11 = 0;
  memset(v8, 0, sizeof(v8));
  memset(LockHandle, 0, sizeof(LockHandle));
  v1 = NfsResMgrpResourceRecordLookupAndReference(a1, &P);
  if ( v1 >= 0 )
  {
    v2 = P;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)P + 3, (PKLOCK_QUEUE_HANDLE)LockHandle);
    LockHandle[24] = 1;
    *((_DWORD *)v2 + 103) |= 1u;
    v3 = *((_DWORD *)v2 + 100);
    LockHandle[24] = 0;
    KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)LockHandle);
    if ( v3 )
    {
      v5 = _InterlockedCompareExchange((volatile signed __int32 *)v2 + 1, 0, 0);
      if ( NfsRefHistoryTracingpGlobal )
        NfsReferenceHistoryCaptureRecord(v2, v5, 1);
      _InterlockedDecrement((volatile signed __int32 *)v2 + 1);
    }
    else
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)NfsResMgrpRoot + 3, (PKLOCK_QUEUE_HANDLE)v8);
      v8[24] = 1;
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)NfsResMgrpRoot + 48), &Buffer);
      v8[24] = 0;
      KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)v8);
      v4 = _InterlockedCompareExchange((volatile signed __int32 *)v2 + 1, 0, 0);
      if ( NfsRefHistoryTracingpGlobal )
        NfsReferenceHistoryCaptureRecord(v2, v4, 1);
      _InterlockedDecrement((volatile signed __int32 *)v2 + 1);
      NfsResMgrpResourceRecordCleanAndDelete((struct _LOOKASIDE_LIST_EX *)v2);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140013044  push    rbp
0x140013046  push    rbx
0x140013047  push    rsi
0x140013048  push    rdi
0x140013049  lea     rbp, [rsp-3Fh]
0x14001304e  sub     rsp, 98h
0x140013055  xorps   xmm0, xmm0
0x140013058  mov     [rbp+57h+P], 0
0x140013060  xorps   xmm1, xmm1
0x140013063  lea     rdx, [rbp+57h+P]
0x140013067  xor     eax, eax
0x140013069  movups  [rbp+57h+var_40], xmm0
0x14001306d  mov     dword ptr [rbp+57h+var_40+8], ecx
0x140013070  movups  [rbp+57h+Buffer], xmm0
0x140013074  mov     [rbp+57h+var_30], rax
0x140013078  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x14001307c  movups  xmmword ptr [rbp+57h+var_70+10h], xmm0
0x140013080  movups  xmmword ptr [rbp+57h+LockHandle], xmm1
0x140013084  movups  xmmword ptr [rbp+57h+LockHandle+10h], xmm1
0x140013088  call    NfsResMgrpResourceRecordLookupAndReference
0x14001308d  mov     esi, eax
0x14001308f  test    eax, eax
0x140013091  js      loc_140013177
0x140013097  mov     rdi, [rbp+57h+P]
0x14001309b  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14001309f  lea     rcx, [rdi+18h]; SpinLock
0x1400130a3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400130aa  nop     dword ptr [rax+rax+00h]
0x1400130af  mov     [rbp+57h+LockHandle+18h], 1
0x1400130b3  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x1400130b7  or      dword ptr [rdi+19Ch], 1
0x1400130be  mov     ebx, [rdi+190h]
0x1400130c4  mov     [rbp+57h+LockHandle+18h], 0
0x1400130c8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400130cf  nop     dword ptr [rax+rax+00h]
0x1400130d4  test    ebx, ebx
0x1400130d6  jnz     short loc_140013153
0x1400130d8  mov     rcx, cs:NfsResMgrpRoot
0x1400130df  lea     rdx, [rbp+57h+var_70]; LockHandle
0x1400130e3  add     rcx, 18h; SpinLock
0x1400130e7  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400130ee  nop     dword ptr [rax+rax+00h]
0x1400130f3  mov     rcx, cs:NfsResMgrpRoot
0x1400130fa  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1400130fe  add     rcx, 30h ; '0'; Table
0x140013102  mov     [rbp+57h+var_70+18h], 1
0x140013106  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14001310d  nop     dword ptr [rax+rax+00h]
0x140013112  lea     rcx, [rbp+57h+var_70]; LockHandle
0x140013116  mov     [rbp+57h+var_70+18h], bl
0x140013119  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140013120  nop     dword ptr [rax+rax+00h]
0x140013125  xor     ecx, ecx
0x140013127  xor     eax, eax
0x140013129  lock cmpxchg [rdi+4], ecx
0x14001312e  cmp     cs:NfsRefHistoryTracingpGlobal, rcx
0x140013135  jz      short loc_140013145
0x140013137  lea     r8d, [rbx+1]
0x14001313b  mov     edx, eax
0x14001313d  mov     rcx, rdi
0x140013140  call    NfsReferenceHistoryCaptureRecord
0x140013145  lock dec dword ptr [rdi+4]
0x140013149  mov     rcx, rdi; P
0x14001314c  call    NfsResMgrpResourceRecordCleanAndDelete
0x140013151  jmp     short loc_140013177
0x140013153  xor     ecx, ecx
0x140013155  xor     eax, eax
0x140013157  lock cmpxchg [rdi+4], ecx
0x14001315c  cmp     cs:NfsRefHistoryTracingpGlobal, rcx
0x140013163  jz      short loc_140013173
0x140013165  lea     r8d, [rcx+1]
0x140013169  mov     edx, eax
0x14001316b  mov     rcx, rdi
0x14001316e  call    NfsReferenceHistoryCaptureRecord
0x140013173  lock dec dword ptr [rdi+4]
0x140013177  mov     eax, esi
0x140013179  add     rsp, 98h
0x140013180  pop     rdi
0x140013181  pop     rsi
0x140013182  pop     rbx
0x140013183  pop     rbp
0x140013184  retn
```
