# RdpWinTaskScheduler::TerminateInstance(void)

- ea: `0x180019ca0`
- end: `0x180019cfe`
- name: `?TerminateInstance@RdpWinTaskScheduler@@UEAA?AW4_XResult32@@XZ`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180019ca0`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180019cc7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180019cc7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180019cd1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180019cd1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180019ce8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180019ce8`

## pseudocode

```c
__int64 __fastcall RdpWinTaskScheduler::TerminateInstance(__int64 a1)
{
  struct _TP_CLEANUP_GROUP *v2; // rcx
  struct _TP_POOL *v3; // rcx

  (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 + 16) + 24LL))(a1 + 16);
  v2 = *(struct _TP_CLEANUP_GROUP **)(a1 + 48);
  if ( v2 )
  {
    CloseThreadpoolCleanupGroupMembers(v2, 0, 0);
    CloseThreadpoolCleanupGroup(*(PTP_CLEANUP_GROUP *)(a1 + 48));
    *(_QWORD *)(a1 + 48) = 0;
  }
  v3 = *(struct _TP_POOL **)(a1 + 40);
  if ( v3 )
  {
    CloseThreadpool(v3);
    *(_QWORD *)(a1 + 40) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180019ca0  push    rbx
0x180019ca2  sub     rsp, 20h
0x180019ca6  mov     rbx, rcx
0x180019ca9  add     rcx, 10h
0x180019cad  mov     rax, [rcx]
0x180019cb0  mov     rax, [rax+18h]
0x180019cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cb9  mov     rcx, [rbx+30h]; ptpcg
0x180019cbd  test    rcx, rcx
0x180019cc0  jz      short loc_180019CDF
0x180019cc2  xor     r8d, r8d; pvCleanupContext
0x180019cc5  xor     edx, edx; fCancelPendingCallbacks
0x180019cc7  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180019ccd  mov     rcx, [rbx+30h]; ptpcg
0x180019cd1  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180019cd7  mov     qword ptr [rbx+30h], 0
0x180019cdf  mov     rcx, [rbx+28h]; ptpp
0x180019ce3  test    rcx, rcx
0x180019ce6  jz      short loc_180019CF6
0x180019ce8  call    cs:__imp_CloseThreadpool
0x180019cee  mov     qword ptr [rbx+28h], 0
0x180019cf6  xor     eax, eax
0x180019cf8  add     rsp, 20h
0x180019cfc  pop     rbx
0x180019cfd  retn
```
