# WinHvUnregisterRemoteHvCallInterface

- ea: `0x140022240`
- end: `0x1400222ea`
- name: `WinHvUnregisterRemoteHvCallInterface`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000b040`
- `0x140022240`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x1400222b0`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400222b0`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002225e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002225e`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002224b`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002224b`
- `ntoskrnl!ExRundownCompleted` at `0x1400222d6`
- `ntoskrnl!ExRundownCompleted` at `0x1400222d6`

## pseudocode

```c
__int64 WinHvUnregisterRemoteHvCallInterface()
{
  void *v0; // rcx
  _QWORD *v1; // rax
  void **v2; // rdx

  ExWaitForRundownProtectionRelease(&RunRef);
  ExAcquireFastMutex(&WinHvpRemoteIdMapLock);
  while ( 1 )
  {
    v0 = WinHvpRemoteIdMap;
    if ( WinHvpRemoteIdMap == (_UNKNOWN *)&WinHvpRemoteIdMap )
      break;
    v1 = *(_QWORD **)WinHvpRemoteIdMap;
    if ( *(_UNKNOWN **)(*(_QWORD *)WinHvpRemoteIdMap + 8LL) != WinHvpRemoteIdMap
      || (v2 = (void **)*((_QWORD *)WinHvpRemoteIdMap + 1), *v2 != WinHvpRemoteIdMap) )
    {
      __fastfail(3u);
    }
    *v2 = v1;
    v1[1] = v2;
    WinHvpFreePoolWithTag(v0, 1500923991);
  }
  ExReleaseFastMutex(&WinHvpRemoteIdMapLock);
  *(_OWORD *)byte_1400160D0 = 0;
  qword_1400160E0 = 0;
  ExRundownCompleted(&RunRef);
  return 0;
}

```

## disassembly

```asm
0x140022240  sub     rsp, 28h
0x140022244  lea     rcx, RunRef; RunRef
0x14002224b  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140022252  nop     dword ptr [rax+rax+00h]
0x140022257  lea     rcx, WinHvpRemoteIdMapLock; FastMutex
0x14002225e  call    cs:__imp_ExAcquireFastMutex
0x140022265  nop     dword ptr [rax+rax+00h]
0x14002226a  mov     rcx, cs:WinHvpRemoteIdMap
0x140022271  lea     rax, WinHvpRemoteIdMap
0x140022278  cmp     rcx, rax
0x14002227b  jz      short loc_1400222A9
0x14002227d  mov     rax, [rcx]
0x140022280  cmp     [rax+8], rcx
0x140022284  jnz     short loc_1400222A2
0x140022286  mov     rdx, [rcx+8]
0x14002228a  cmp     [rdx], rcx
0x14002228d  jnz     short loc_1400222A2
0x14002228f  mov     [rdx], rax
0x140022292  mov     [rax+8], rdx
0x140022296  mov     edx, 59764857h
0x14002229b  call    WinHvpFreePoolWithTag
0x1400222a0  jmp     short loc_14002226A
0x1400222a2  mov     ecx, 3
0x1400222a7  int     29h; Win8: RtlFailFast(ecx)
0x1400222a9  lea     rcx, WinHvpRemoteIdMapLock; FastMutex
0x1400222b0  call    cs:__imp_ExReleaseFastMutex
0x1400222b7  nop     dword ptr [rax+rax+00h]
0x1400222bc  xorps   xmm0, xmm0
0x1400222bf  lea     rcx, RunRef; RunRef
0x1400222c6  xor     eax, eax
0x1400222c8  movups  xmmword ptr cs:byte_1400160D0, xmm0
0x1400222cf  mov     cs:qword_1400160E0, rax
0x1400222d6  call    cs:__imp_ExRundownCompleted
0x1400222dd  nop     dword ptr [rax+rax+00h]
0x1400222e2  xor     eax, eax
0x1400222e4  add     rsp, 28h
0x1400222e8  retn
```
