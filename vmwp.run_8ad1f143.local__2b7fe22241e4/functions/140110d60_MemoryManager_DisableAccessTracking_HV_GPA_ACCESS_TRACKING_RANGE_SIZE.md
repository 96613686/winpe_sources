# MemoryManager::DisableAccessTracking(_HV_GPA_ACCESS_TRACKING_RANGE_SIZE)

- ea: `0x140110d60`
- end: `0x140110ea9`
- name: `?DisableAccessTracking@MemoryManager@@UEAAJW4_HV_GPA_ACCESS_TRACKING_RANGE_SIZE@@@Z`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1401071d0`

## callees

- `0x14002dd88`
- `0x140042260`
- `0x1400f2c90`
- `0x140110d60`
- `0x140111090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140110dd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140110e8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140110dd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140110e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140110deb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140110e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140110deb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140110e54`
- `vid!VidGpaAccessTrackingDisable` at `0x140110dbe`
- `vid!VidGpaAccessTrackingDisable` at `0x140110dbe`
- `vid!VidGpaAccessTrackingEnable` at `0x140110e34`
- `vid!VidGpaAccessTrackingEnable` at `0x140110e34`

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
      VmlDebugTraceWithError(16416, &off_1402C75A0, (unsigned int)LastError);
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
      VmlDebugTraceWithError(16416, &off_1402DAC38, v8);
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
0x140110d60  mov     [rsp+arg_8], rbx
0x140110d65  mov     [rsp+arg_10], rsi
0x140110d6a  push    rdi
0x140110d6b  sub     rsp, 30h
0x140110d6f  lea     rsi, [rcx+3B8h]
0x140110d76  mov     [rsp+38h+var_18], 0
0x140110d7e  mov     rdi, rcx
0x140110d81  mov     ebx, edx
0x140110d83  mov     rcx, rsi; this
0x140110d86  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x140110d8b  mov     eax, 1
0x140110d90  lea     rdx, [rsp+38h+var_18]; enum _HV_GPA_ACCESS_TRACKING_RANGE_SIZE *
0x140110d95  cmp     ebx, 2
0x140110d98  cmovnz  eax, ebx
0x140110d9b  movsxd  rcx, eax
0x140110d9e  mov     eax, [rdi+rcx*4+300h]
0x140110da5  dec     eax
0x140110da7  mov     [rdi+rcx*4+300h], eax
0x140110dae  mov     rcx, rdi; this
0x140110db1  call    ?CheckGetSmallestRegisteredRangeSize@MemoryManager@@AEBA_NPEAW4_HV_GPA_ACCESS_TRACKING_RANGE_SIZE@@@Z; MemoryManager::CheckGetSmallestRegisteredRangeSize(_HV_GPA_ACCESS_TRACKING_RANGE_SIZE *)
0x140110db6  mov     rcx, [rdi+10h]
0x140110dba  test    al, al
0x140110dbc  jnz     short loc_140110E30
0x140110dbe  call    cs:__imp_VidGpaAccessTrackingDisable
0x140110dc5  nop     dword ptr [rax+rax+00h]
0x140110dca  test    eax, eax
0x140110dcc  jz      short loc_140110DEB
0x140110dce  mov     rcx, rsi; SRWLock
0x140110dd1  mov     dword ptr [rsi+8], 0
0x140110dd8  call    cs:__imp_ReleaseSRWLockExclusive
0x140110ddf  nop     dword ptr [rax+rax+00h]
0x140110de4  xor     ebx, ebx
0x140110de6  jmp     loc_140110E96
0x140110deb  call    cs:__imp_GetLastError
0x140110df2  nop     dword ptr [rax+rax+00h]
0x140110df7  mov     ebx, eax
0x140110df9  test    eax, eax
0x140110dfb  jle     short loc_140110E06
0x140110dfd  movzx   ebx, ax
0x140110e00  or      ebx, 80070000h
0x140110e06  mov     edi, 4020h
0x140110e0b  mov     ecx, edi
0x140110e0d  call    VmlIsDebugTraceEnabled
0x140110e12  test    eax, eax
0x140110e14  jz      short loc_140110E27
0x140110e16  mov     r8d, ebx
0x140110e19  lea     rdx, off_1402DAC38; "Failed to disable access tracking for t"...
0x140110e20  mov     ecx, edi
0x140110e22  call    VmlDebugTraceWithError
0x140110e27  mov     dword ptr [rsi+8], 0
0x140110e2e  jmp     short loc_140110E87
0x140110e30  mov     edx, [rsp+38h+var_18]
0x140110e34  call    cs:__imp_VidGpaAccessTrackingEnable
0x140110e3b  nop     dword ptr [rax+rax+00h]
0x140110e40  test    eax, eax
0x140110e42  jnz     short loc_140110E82
0x140110e44  mov     edi, 4020h
0x140110e49  mov     ecx, edi
0x140110e4b  call    VmlIsDebugTraceEnabled
0x140110e50  test    eax, eax
0x140110e52  jz      short loc_140110E82
0x140110e54  call    cs:__imp_GetLastError
0x140110e5b  nop     dword ptr [rax+rax+00h]
0x140110e60  test    eax, eax
0x140110e62  jle     short loc_140110E6C
0x140110e64  movzx   eax, ax
0x140110e67  or      eax, 80070000h
0x140110e6c  mov     r9d, [rsp+38h+var_18]
0x140110e71  lea     rdx, off_1402C75A0; "Failed to change tracking size to %u"
0x140110e78  mov     r8d, eax
0x140110e7b  mov     ecx, edi
0x140110e7d  call    VmlDebugTraceWithError
0x140110e82  xor     ebx, ebx
0x140110e84  mov     [rsi+8], ebx
0x140110e87  mov     rcx, rsi; SRWLock
0x140110e8a  call    cs:__imp_ReleaseSRWLockExclusive
0x140110e91  nop     dword ptr [rax+rax+00h]
0x140110e96  mov     rsi, [rsp+38h+arg_10]
0x140110e9b  mov     eax, ebx
0x140110e9d  mov     rbx, [rsp+38h+arg_8]
0x140110ea2  add     rsp, 30h
0x140110ea6  pop     rdi
0x140110ea7  retn
```
