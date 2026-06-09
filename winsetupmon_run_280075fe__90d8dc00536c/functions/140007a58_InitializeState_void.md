# InitializeState(void)

- ea: `0x140007a58`
- end: `0x140007cef`
- name: `?InitializeState@@YAJXZ`
- size: `663`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140022078`

## callees

- `0x140003780`
- `0x140007a58`
- `0x14000fd40`
- `0x14001f130`

## import_xrefs

- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x140007c26`
- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x140007c40`
- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x140007c26`
- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x140007c40`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140007c01`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140007c01`
- `ntoskrnl!RtlCreateHashTable` at `0x140007be3`
- `ntoskrnl!RtlCreateHashTable` at `0x140007be3`
- `ntoskrnl!KeInitializeEvent` at `0x140007ad8`
- `ntoskrnl!KeInitializeEvent` at `0x140007b0b`
- `ntoskrnl!KeInitializeEvent` at `0x140007c6b`
- `ntoskrnl!KeInitializeEvent` at `0x140007ad8`
- `ntoskrnl!KeInitializeEvent` at `0x140007b0b`
- `ntoskrnl!KeInitializeEvent` at `0x140007c6b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140007b30`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140007b30`
- `ntoskrnl!KeInitializeMutex` at `0x140007a84`
- `ntoskrnl!KeInitializeMutex` at `0x140007a84`
- `FLTMGR!FltInitializePushLock` at `0x140007b97`
- `FLTMGR!FltInitializePushLock` at `0x140007bcb`
- `FLTMGR!FltInitializePushLock` at `0x140007c90`
- `FLTMGR!FltInitializePushLock` at `0x140007ca3`
- `FLTMGR!FltInitializePushLock` at `0x140007cb6`
- `FLTMGR!FltInitializePushLock` at `0x140007b97`
- `FLTMGR!FltInitializePushLock` at `0x140007bcb`
- `FLTMGR!FltInitializePushLock` at `0x140007c90`
- `FLTMGR!FltInitializePushLock` at `0x140007ca3`
- `FLTMGR!FltInitializePushLock` at `0x140007cb6`

## pseudocode

```c
__int64 InitializeState(void)
{
  wchar_t *PoolWithTag; // rax
  wchar_t *v1; // rbx
  const char *v2; // rcx
  unsigned int v3; // ebx

  memset(&Object, 0, 0x150u);
  KeInitializeMutex(&Object, 0);
  byte_140019538 = 0;
  qword_140019548 = (__int64)&qword_140019540;
  qword_140019540 = &qword_140019540;
  FastMutex.Count = 1;
  FastMutex.Owner = 0;
  FastMutex.Contention = 0;
  KeInitializeEvent(&FastMutex.Event, SynchronizationEvent, 0);
  stru_140019608.Count = 1;
  stru_140019608.Owner = 0;
  stru_140019608.Contention = 0;
  KeInitializeEvent(&stru_140019608.Event, SynchronizationEvent, 0);
  stru_140019640.MaximumLength = 2048;
  PoolWithTag = (wchar_t *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0x800u, 0x6E6D7377u);
  v1 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported || !PoolWithTag )
  {
    stru_140019640.Buffer = PoolWithTag;
    if ( !PoolWithTag )
    {
      UninitializeLogger();
      v2 = "WinSetupMon::InitializeState: Failed InitializeLogger";
      goto LABEL_10;
    }
  }
  else
  {
    memset(PoolWithTag, 0, 0x800u);
    stru_140019640.Buffer = v1;
  }
  stru_140019640.Length = 0;
  memset(&qword_140019650, 0, 0x1A8u);
  FltInitializePushLock(&qword_140019650);
  *(_OWORD *)&qword_140019378 = 0;
  *(_QWORD *)&Enumerator.BucketIndex = 0;
  Enumerator.HashEntry.Linkage = 0;
  *((_OWORD *)&Enumerator.CurEntry + 1) = 0;
  FltInitializePushLock(&qword_140019378);
  if ( !RtlCreateHashTable(&HashTable, 0, 0) || !RtlInitEnumerationHashTable(HashTable, &Enumerator) )
  {
    v2 = "WinSetupMon::InitializeState: Failed InitializeProcessMap";
LABEL_10:
    v3 = -1073741670;
    TraceError(v2, 3221225626LL);
    return v3;
  }
  v3 = 0;
  RtlInitializeUnicodePrefix(&g_TrackingInfo);
  qword_140019448 = 0;
  RtlInitializeUnicodePrefix(&PrefixTable);
  stru_140019468.Count = 1;
  stru_140019468.Owner = 0;
  stru_140019468.Contention = 0;
  KeInitializeEvent(&stru_140019468.Event, SynchronizationEvent, 0);
  memset(&qword_1400193B0, 0, 0x78u);
  FltInitializePushLock(&qword_1400193B0);
  FltInitializePushLock(&qword_140019400);
  FltInitializePushLock(&PushLock);
  return v3;
}

```

## disassembly

```asm
0x140007a58  mov     [rsp+arg_0], rbx
0x140007a5d  mov     [rsp+arg_8], rbp
0x140007a62  push    rsi
0x140007a63  sub     rsp, 20h
0x140007a67  xor     edx, edx; Val
0x140007a69  lea     rcx, Object; void *
0x140007a70  mov     r8d, 150h; Size
0x140007a76  call    memset
0x140007a7b  xor     edx, edx; Level
0x140007a7d  lea     rcx, Object; Mutex
0x140007a84  call    cs:__imp_KeInitializeMutex
0x140007a8b  nop     dword ptr [rax+rax+00h]
0x140007a90  lea     rax, qword_140019540
0x140007a97  mov     cs:byte_140019538, 0
0x140007a9e  mov     esi, 1
0x140007aa3  mov     cs:qword_140019548, rax
0x140007aaa  mov     edx, esi; Type
0x140007aac  mov     cs:qword_140019540, rax
0x140007ab3  xor     r8d, r8d; State
0x140007ab6  mov     cs:FastMutex.Count, esi
0x140007abc  lea     rcx, FastMutex.Event; Event
0x140007ac3  mov     cs:FastMutex.Owner, 0
0x140007ace  mov     cs:FastMutex.Contention, 0
0x140007ad8  call    cs:__imp_KeInitializeEvent
0x140007adf  nop     dword ptr [rax+rax+00h]
0x140007ae4  xor     r8d, r8d; State
0x140007ae7  mov     cs:stru_140019608.Count, esi
0x140007aed  mov     edx, esi; Type
0x140007aef  mov     cs:stru_140019608.Owner, 0
0x140007afa  lea     rcx, stru_140019608.Event; Event
0x140007b01  mov     cs:stru_140019608.Contention, 0
0x140007b0b  call    cs:__imp_KeInitializeEvent
0x140007b12  nop     dword ptr [rax+rax+00h]
0x140007b17  mov     ebp, 800h
0x140007b1c  mov     r8d, 6E6D7377h; Tag
0x140007b22  mov     edx, ebp; NumberOfBytes
0x140007b24  mov     cs:stru_140019640.MaximumLength, bp
0x140007b2b  mov     ecx, 401h; PoolType
0x140007b30  call    cs:__imp_ExAllocatePoolWithTag
0x140007b37  nop     dword ptr [rax+rax+00h]
0x140007b3c  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140007b43  mov     rbx, rax
0x140007b46  jnz     short loc_140007B63
0x140007b48  test    rax, rax
0x140007b4b  jz      short loc_140007B63
0x140007b4d  mov     r8d, ebp; Size
0x140007b50  xor     edx, edx; Val
0x140007b52  mov     rcx, rax; void *
0x140007b55  call    memset
0x140007b5a  mov     cs:stru_140019640.Buffer, rbx
0x140007b61  jmp     short loc_140007B73
0x140007b63  mov     cs:stru_140019640.Buffer, rbx
0x140007b6a  test    rbx, rbx
0x140007b6d  jz      loc_140007CC4
0x140007b73  xor     eax, eax
0x140007b75  mov     cs:stru_140019640.Length, ax
0x140007b7c  xor     edx, edx; Val
0x140007b7e  lea     rcx, qword_140019650; void *
0x140007b85  mov     r8d, 1A8h; Size
0x140007b8b  call    memset
0x140007b90  lea     rcx, qword_140019650; PushLock
0x140007b97  call    cs:__imp_FltInitializePushLock
0x140007b9e  nop     dword ptr [rax+rax+00h]
0x140007ba3  xorps   xmm0, xmm0
0x140007ba6  lea     rcx, qword_140019378; PushLock
0x140007bad  xor     eax, eax
0x140007baf  movups  xmmword ptr cs:qword_140019378, xmm0
0x140007bb6  mov     qword ptr cs:Enumerator.BucketIndex, rax
0x140007bbd  movups  xmmword ptr cs:Enumerator, xmm0
0x140007bc4  movups  xmmword ptr cs:Enumerator+10h, xmm0
0x140007bcb  call    cs:__imp_FltInitializePushLock
0x140007bd2  nop     dword ptr [rax+rax+00h]
0x140007bd7  xor     r8d, r8d; Flags
0x140007bda  lea     rcx, HashTable; HashTable
0x140007be1  xor     edx, edx; Shift
0x140007be3  call    cs:__imp_RtlCreateHashTable
0x140007bea  nop     dword ptr [rax+rax+00h]
0x140007bef  test    al, al
0x140007bf1  jz      short loc_140007C11
0x140007bf3  mov     rcx, cs:HashTable; HashTable
0x140007bfa  lea     rdx, Enumerator; Enumerator
0x140007c01  call    cs:__imp_RtlInitEnumerationHashTable
0x140007c08  nop     dword ptr [rax+rax+00h]
0x140007c0d  test    al, al
0x140007c0f  jnz     short loc_140007C1D
0x140007c11  lea     rcx, aWinsetupmonIni; "WinSetupMon::InitializeState: Failed In"...
0x140007c18  jmp     loc_140007CD0
0x140007c1d  lea     rcx, ?g_TrackingInfo@@3U_TRACKED_PATHS_TABLE@@A; PrefixTable
0x140007c24  xor     ebx, ebx
0x140007c26  call    cs:__imp_RtlInitializeUnicodePrefix
0x140007c2d  nop     dword ptr [rax+rax+00h]
0x140007c32  lea     rcx, PrefixTable; PrefixTable
0x140007c39  mov     cs:qword_140019448, rbx
0x140007c40  call    cs:__imp_RtlInitializeUnicodePrefix
0x140007c47  nop     dword ptr [rax+rax+00h]
0x140007c4c  xor     r8d, r8d; State
0x140007c4f  mov     cs:stru_140019468.Count, esi
0x140007c55  mov     edx, esi; Type
0x140007c57  mov     cs:stru_140019468.Owner, rbx
0x140007c5e  lea     rcx, stru_140019468.Event; Event
0x140007c65  mov     cs:stru_140019468.Contention, ebx
0x140007c6b  call    cs:__imp_KeInitializeEvent
0x140007c72  nop     dword ptr [rax+rax+00h]
0x140007c77  xor     edx, edx; Val
0x140007c79  lea     r8d, [rbx+78h]; Size
0x140007c7d  lea     rcx, qword_1400193B0; void *
0x140007c84  call    memset
0x140007c89  lea     rcx, qword_1400193B0; PushLock
0x140007c90  call    cs:__imp_FltInitializePushLock
0x140007c97  nop     dword ptr [rax+rax+00h]
0x140007c9c  lea     rcx, qword_140019400; PushLock
0x140007ca3  call    cs:__imp_FltInitializePushLock
0x140007caa  nop     dword ptr [rax+rax+00h]
0x140007caf  lea     rcx, PushLock; PushLock
0x140007cb6  call    cs:__imp_FltInitializePushLock
0x140007cbd  nop     dword ptr [rax+rax+00h]
0x140007cc2  jmp     short loc_140007CDC
0x140007cc4  call    ?UninitializeLogger@@YAXXZ; UninitializeLogger(void)
0x140007cc9  lea     rcx, aWinsetupmonIni_0; "WinSetupMon::InitializeState: Failed In"...
0x140007cd0  mov     ebx, 0C000009Ah
0x140007cd5  mov     edx, ebx
0x140007cd7  call    TraceError
0x140007cdc  mov     rbp, [rsp+28h+arg_8]
0x140007ce1  mov     eax, ebx
0x140007ce3  mov     rbx, [rsp+28h+arg_0]
0x140007ce8  add     rsp, 20h
0x140007cec  pop     rsi
0x140007ced  retn
```
