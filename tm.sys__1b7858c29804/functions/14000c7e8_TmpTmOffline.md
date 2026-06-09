# TmpTmOffline

- ea: `0x14000c7e8`
- end: `0x14000c9a6`
- name: `TmpTmOffline`
- size: `446`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140002140`
- `0x140015920`
- `0x140016550`
- `0x14001df60`

## callees

- `0x14000c664`
- `0x14000c7e8`
- `0x14000d330`
- `0x14001d510`
- `0x14001d630`

## import_xrefs

- `CLFS!ClfsDeleteMarshallingArea` at `0x14000c906`
- `CLFS!ClfsDeleteMarshallingArea` at `0x14000c906`
- `CLFS!ClfsCloseLogFileObject` at `0x14000c929`
- `CLFS!ClfsCloseLogFileObject` at `0x14000c929`
- `CLFS!ClfsMgmtDeregisterManagedClient` at `0x14000c98e`
- `CLFS!ClfsMgmtDeregisterManagedClient` at `0x14000c98e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c7f4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c7f4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c818`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c818`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000c8d4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000c8d4`
- `ntoskrnl!KeReleaseMutex` at `0x14000c82f`
- `ntoskrnl!KeReleaseMutex` at `0x14000c958`
- `ntoskrnl!KeReleaseMutex` at `0x14000c82f`
- `ntoskrnl!KeReleaseMutex` at `0x14000c958`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c943`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c943`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c83b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c964`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c83b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c964`

## pseudocode

```c
__int64 __fastcall TmpTmOffline(__int64 a1)
{
  void *v2; // rsi
  void *v3; // rcx
  FILE_OBJECT *v4; // rcx
  __int64 v5; // rbx

  KeEnterCriticalRegion();
  KeWaitForSingleObject((PVOID)(a1 + 8), Executive, 0, 0, 0);
  if ( *(_DWORD *)(a1 + 64) == 5 )
  {
    KeReleaseMutex((PRKMUTEX)(a1 + 8), 0);
    KeLeaveCriticalRegion();
  }
  else
  {
    v2 = 0;
    if ( (*(_DWORD *)(a1 + 128) & 1) == 0 )
      TmpCheckpoint(a1, 0);
    *(_DWORD *)(a1 + 64) = 5;
    if ( (*(_DWORD *)(a1 + 128) & 4) != 0 )
      _InterlockedExchange(&dword_1400071C0, 0);
    if ( (*(_DWORD *)(a1 + 128) & 2) != 0 )
      _InterlockedExchange(&dword_1400071C4, 0);
    TmpNamespaceExpire(a1 + 344);
    TmpNamespaceForEach((PRTL_AVL_TABLE)(a1 + 344));
    TmpNamespaceForEach((PRTL_AVL_TABLE)(a1 + 176));
    ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 784), 1u);
    if ( *(_QWORD *)(a1 + 168) )
    {
      v2 = *(void **)(a1 + 168);
      *(_QWORD *)(a1 + 168) = 0;
    }
    v3 = *(void **)(a1 + 160);
    if ( v3 )
    {
      ClfsDeleteMarshallingArea(v3);
      *(_QWORD *)(a1 + 160) = 0;
    }
    v4 = *(FILE_OBJECT **)(a1 + 152);
    if ( v4 )
    {
      ClfsCloseLogFileObject(v4);
      *(_QWORD *)(a1 + 152) = 0;
    }
    ExReleaseResourceLite((PERESOURCE)(a1 + 784));
    v5 = *(_QWORD *)(a1 + 72);
    KeReleaseMutex((PRKMUTEX)(a1 + 8), 0);
    KeLeaveCriticalRegion();
    if ( v5 )
      TmpNamespaceRemove(&TmpTmNamespace, 0, a1);
    if ( v2 )
      ClfsMgmtDeregisterManagedClient(v2);
  }
  return 0;
}

```

## disassembly

```asm
0x14000c7e8  push    rbx
0x14000c7ea  push    rbp
0x14000c7eb  push    rsi
0x14000c7ec  push    rdi
0x14000c7ed  sub     rsp, 38h
0x14000c7f1  mov     rdi, rcx
0x14000c7f4  call    cs:__imp_KeEnterCriticalRegion
0x14000c7fb  nop     dword ptr [rax+rax+00h]
0x14000c800  lea     rbp, [rdi+8]
0x14000c804  mov     [rsp+58h+Timeout], 0; Timeout
0x14000c80d  mov     rcx, rbp; Object
0x14000c810  xor     r9d, r9d; Alertable
0x14000c813  xor     r8d, r8d; WaitMode
0x14000c816  xor     edx, edx; WaitReason
0x14000c818  call    cs:__imp_KeWaitForSingleObject
0x14000c81f  nop     dword ptr [rax+rax+00h]
0x14000c824  cmp     dword ptr [rdi+40h], 5
0x14000c828  jnz     short loc_14000C84C
0x14000c82a  xor     edx, edx; Wait
0x14000c82c  mov     rcx, rbp; Mutex
0x14000c82f  call    cs:__imp_KeReleaseMutex
0x14000c836  nop     dword ptr [rax+rax+00h]
0x14000c83b  call    cs:__imp_KeLeaveCriticalRegion
0x14000c842  nop     dword ptr [rax+rax+00h]
0x14000c847  jmp     loc_14000C99A
0x14000c84c  mov     eax, [rdi+80h]
0x14000c852  xor     esi, esi
0x14000c854  test    al, 1
0x14000c856  jnz     short loc_14000C862
0x14000c858  xor     edx, edx
0x14000c85a  mov     rcx, rdi
0x14000c85d  call    TmpCheckpoint
0x14000c862  mov     dword ptr [rdi+40h], 5
0x14000c869  mov     eax, [rdi+80h]
0x14000c86f  test    al, 4
0x14000c871  jz      short loc_14000C87B
0x14000c873  xor     eax, eax
0x14000c875  xchg    eax, cs:dword_1400071C0
0x14000c87b  mov     eax, [rdi+80h]
0x14000c881  test    al, 2
0x14000c883  jz      short loc_14000C88D
0x14000c885  xor     eax, eax
0x14000c887  xchg    eax, cs:dword_1400071C4
0x14000c88d  lea     rbx, [rdi+158h]
0x14000c894  mov     rcx, rbx
0x14000c897  call    TmpNamespaceExpire
0x14000c89c  xor     r9d, r9d
0x14000c89f  lea     r8, TmpExpireNamespaceResourceManager
0x14000c8a6  xor     edx, edx
0x14000c8a8  mov     rcx, rbx; Table
0x14000c8ab  call    TmpNamespaceForEach
0x14000c8b0  lea     rcx, [rdi+0B0h]; Table
0x14000c8b7  xor     r9d, r9d
0x14000c8ba  lea     r8, TmpForgetAllEnlistmentsTransaction
0x14000c8c1  xor     edx, edx
0x14000c8c3  call    TmpNamespaceForEach
0x14000c8c8  lea     rbx, [rdi+310h]
0x14000c8cf  mov     dl, 1; Wait
0x14000c8d1  mov     rcx, rbx; Resource
0x14000c8d4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000c8db  nop     dword ptr [rax+rax+00h]
0x14000c8e0  mov     rax, [rdi+0A8h]
0x14000c8e7  test    rax, rax
0x14000c8ea  jz      short loc_14000C8FA
0x14000c8ec  mov     rsi, rax
0x14000c8ef  mov     qword ptr [rdi+0A8h], 0
0x14000c8fa  mov     rcx, [rdi+0A0h]; pvMarshalContext
0x14000c901  test    rcx, rcx
0x14000c904  jz      short loc_14000C91D
0x14000c906  call    cs:__imp_ClfsDeleteMarshallingArea
0x14000c90d  nop     dword ptr [rax+rax+00h]
0x14000c912  mov     qword ptr [rdi+0A0h], 0
0x14000c91d  mov     rcx, [rdi+98h]; plfoLog
0x14000c924  test    rcx, rcx
0x14000c927  jz      short loc_14000C940
0x14000c929  call    cs:__imp_ClfsCloseLogFileObject
0x14000c930  nop     dword ptr [rax+rax+00h]
0x14000c935  mov     qword ptr [rdi+98h], 0
0x14000c940  mov     rcx, rbx; Resource
0x14000c943  call    cs:__imp_ExReleaseResourceLite
0x14000c94a  nop     dword ptr [rax+rax+00h]
0x14000c94f  mov     rbx, [rdi+48h]
0x14000c953  xor     edx, edx; Wait
0x14000c955  mov     rcx, rbp; Mutex
0x14000c958  call    cs:__imp_KeReleaseMutex
0x14000c95f  nop     dword ptr [rax+rax+00h]
0x14000c964  call    cs:__imp_KeLeaveCriticalRegion
0x14000c96b  nop     dword ptr [rax+rax+00h]
0x14000c970  test    rbx, rbx
0x14000c973  jz      short loc_14000C986
0x14000c975  mov     r8, rdi
0x14000c978  lea     rcx, TmpTmNamespace; Table
0x14000c97f  xor     edx, edx; Object
0x14000c981  call    TmpNamespaceRemove
0x14000c986  test    rsi, rsi
0x14000c989  jz      short loc_14000C99A
0x14000c98b  mov     rcx, rsi; ClientCookie
0x14000c98e  call    cs:__imp_ClfsMgmtDeregisterManagedClient
0x14000c995  nop     dword ptr [rax+rax+00h]
0x14000c99a  xor     eax, eax
0x14000c99c  add     rsp, 38h
0x14000c9a0  pop     rdi
0x14000c9a1  pop     rsi
0x14000c9a2  pop     rbp
0x14000c9a3  pop     rbx
0x14000c9a4  retn
```
