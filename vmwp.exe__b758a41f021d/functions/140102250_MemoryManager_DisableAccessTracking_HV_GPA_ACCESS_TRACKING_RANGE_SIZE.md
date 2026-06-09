# MemoryManager::DisableAccessTracking(_HV_GPA_ACCESS_TRACKING_RANGE_SIZE)

- ea: `0x140102250`
- end: `0x140102399`
- name: `?DisableAccessTracking@MemoryManager@@UEAAJW4_HV_GPA_ACCESS_TRACKING_RANGE_SIZE@@@Z`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400f6f30`

## callees

- `0x1400364a0`
- `0x14003e2b8`
- `0x1400e37f0`
- `0x140102250`
- `0x140102580`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1401022c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14010237a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1401022c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14010237a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401022db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140102344`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401022db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140102344`
- `vid!VidGpaAccessTrackingDisable` at `0x1401022ae`
- `vid!VidGpaAccessTrackingDisable` at `0x1401022ae`
- `vid!VidGpaAccessTrackingEnable` at `0x140102324`
- `vid!VidGpaAccessTrackingEnable` at `0x140102324`

## pseudocode

```c
__int64 __fastcall MemoryManager::DisableAccessTracking(_QWORD *a1, int a2)
{
  _QWORD *v2; // rsi
  int v5; // eax
  bool v6; // al
  __int64 v7; // rcx
  unsigned int v8; // ebx
  signed int v9; // eax
  signed int LastError; // eax
  _DWORD v12[6]; // [rsp+20h] [rbp-18h] BYREF

  v2 = a1 + 119;
  v12[0] = 0;
  Vml::VmSlimReaderWriterLock::AcquireExclusive((Vml::VmSlimReaderWriterLock *)(a1 + 119));
  v5 = 1;
  if ( a2 != 2 )
    v5 = a2;
  --*((_DWORD *)a1 + v5 + 192);
  v6 = MemoryManager::CheckGetSmallestRegisteredRangeSize(
         (MemoryManager *)a1,
         (enum _HV_GPA_ACCESS_TRACKING_RANGE_SIZE *)v12);
  v7 = a1[2];
  if ( v6 )
  {
    if ( !(unsigned int)VidGpaAccessTrackingEnable(v7, v12[0]) && (unsigned int)VmlIsDebugTraceEnabled(16416) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      VmlDebugTraceWithError(16416, &off_1402D0490, (unsigned int)LastError);
    }
    v8 = 0;
    *((_DWORD *)v2 + 2) = 0;
    goto LABEL_17;
  }
  if ( !(unsigned int)VidGpaAccessTrackingDisable(v7) )
  {
    v9 = GetLastError();
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTraceWithError(16416, &off_1402E4048, v8);
    *((_DWORD *)v2 + 2) = 0;
LABEL_17:
    ReleaseSRWLockExclusive((PSRWLOCK)v2);
    return v8;
  }
  *((_DWORD *)v2 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v2);
  return 0;
}

```

## disassembly

```asm
0x140102250  mov     [rsp+arg_8], rbx
0x140102255  mov     [rsp+arg_10], rsi
0x14010225a  push    rdi
0x14010225b  sub     rsp, 30h
0x14010225f  lea     rsi, [rcx+3B8h]
0x140102266  mov     [rsp+38h+var_18], 0
0x14010226e  mov     rdi, rcx
0x140102271  mov     ebx, edx
0x140102273  mov     rcx, rsi; this
0x140102276  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x14010227b  mov     eax, 1
0x140102280  lea     rdx, [rsp+38h+var_18]; enum _HV_GPA_ACCESS_TRACKING_RANGE_SIZE *
0x140102285  cmp     ebx, 2
0x140102288  cmovnz  eax, ebx
0x14010228b  movsxd  rcx, eax
0x14010228e  mov     eax, [rdi+rcx*4+300h]
0x140102295  dec     eax
0x140102297  mov     [rdi+rcx*4+300h], eax
0x14010229e  mov     rcx, rdi; this
0x1401022a1  call    ?CheckGetSmallestRegisteredRangeSize@MemoryManager@@AEBA_NPEAW4_HV_GPA_ACCESS_TRACKING_RANGE_SIZE@@@Z; MemoryManager::CheckGetSmallestRegisteredRangeSize(_HV_GPA_ACCESS_TRACKING_RANGE_SIZE *)
0x1401022a6  mov     rcx, [rdi+10h]
0x1401022aa  test    al, al
0x1401022ac  jnz     short loc_140102320
0x1401022ae  call    cs:__imp_VidGpaAccessTrackingDisable
0x1401022b5  nop     dword ptr [rax+rax+00h]
0x1401022ba  test    eax, eax
0x1401022bc  jz      short loc_1401022DB
0x1401022be  mov     rcx, rsi; SRWLock
0x1401022c1  mov     dword ptr [rsi+8], 0
0x1401022c8  call    cs:__imp_ReleaseSRWLockExclusive
0x1401022cf  nop     dword ptr [rax+rax+00h]
0x1401022d4  xor     ebx, ebx
0x1401022d6  jmp     loc_140102386
0x1401022db  call    cs:__imp_GetLastError
0x1401022e2  nop     dword ptr [rax+rax+00h]
0x1401022e7  mov     ebx, eax
0x1401022e9  test    eax, eax
0x1401022eb  jle     short loc_1401022F6
0x1401022ed  movzx   ebx, ax
0x1401022f0  or      ebx, 80070000h
0x1401022f6  mov     edi, 4020h
0x1401022fb  mov     ecx, edi
0x1401022fd  call    VmlIsDebugTraceEnabled
0x140102302  test    eax, eax
0x140102304  jz      short loc_140102317
0x140102306  mov     r8d, ebx
0x140102309  lea     rdx, off_1402E4048; "Failed to disable access tracking for t"...
0x140102310  mov     ecx, edi
0x140102312  call    VmlDebugTraceWithError
0x140102317  mov     dword ptr [rsi+8], 0
0x14010231e  jmp     short loc_140102377
0x140102320  mov     edx, [rsp+38h+var_18]
0x140102324  call    cs:__imp_VidGpaAccessTrackingEnable
0x14010232b  nop     dword ptr [rax+rax+00h]
0x140102330  test    eax, eax
0x140102332  jnz     short loc_140102372
0x140102334  mov     edi, 4020h
0x140102339  mov     ecx, edi
0x14010233b  call    VmlIsDebugTraceEnabled
0x140102340  test    eax, eax
0x140102342  jz      short loc_140102372
0x140102344  call    cs:__imp_GetLastError
0x14010234b  nop     dword ptr [rax+rax+00h]
0x140102350  test    eax, eax
0x140102352  jle     short loc_14010235C
0x140102354  movzx   eax, ax
0x140102357  or      eax, 80070000h
0x14010235c  mov     r9d, [rsp+38h+var_18]
0x140102361  lea     rdx, off_1402D0490; "Failed to change tracking size to %u"
0x140102368  mov     r8d, eax
0x14010236b  mov     ecx, edi
0x14010236d  call    VmlDebugTraceWithError
0x140102372  xor     ebx, ebx
0x140102374  mov     [rsi+8], ebx
0x140102377  mov     rcx, rsi; SRWLock
0x14010237a  call    cs:__imp_ReleaseSRWLockExclusive
0x140102381  nop     dword ptr [rax+rax+00h]
0x140102386  mov     rsi, [rsp+38h+arg_10]
0x14010238b  mov     eax, ebx
0x14010238d  mov     rbx, [rsp+38h+arg_8]
0x140102392  add     rsp, 30h
0x140102396  pop     rdi
0x140102397  retn
```
