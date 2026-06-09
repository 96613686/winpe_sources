# CDescriptionManager::CleanPendingThreads(void)

- ea: `0x1800114c8`
- end: `0x180011585`
- name: `?CleanPendingThreads@CDescriptionManager@@AEAAXXZ`
- size: `189`
- prototype: `void __fastcall(CDescriptionManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x1800112b0`

## callees

- `0x1800114c8`
- `0x18001252c`
- `0x18003a9a0`
- `0x18003cb84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800114fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011553`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800114fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011553`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011544`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011544`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011579`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800114e5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800114e5`

## pseudocode

```c
void __fastcall CDescriptionManager::CleanPendingThreads(CDescriptionManager *this)
{
  CDescriptionManager *v2; // rcx
  struct SSDP_SERVICE_REGISTRATION_PARAMS *v3; // r14
  struct SSDP_SERVICE_REGISTRATION_PARAMS *v4; // rdi
  struct SSDP_SERVICE_REGISTRATION_PARAMS **v5; // rax

  CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)this + 59), 1, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  v3 = (struct SSDP_SERVICE_REGISTRATION_PARAMS *)*((_QWORD *)this + 76);
  while ( v3 != (CDescriptionManager *)((char *)this + 608) )
  {
    v4 = v3;
    v5 = (struct SSDP_SERVICE_REGISTRATION_PARAMS **)*((_QWORD *)v3 + 1);
    v3 = *(struct SSDP_SERVICE_REGISTRATION_PARAMS **)v3;
    *v5 = v3;
    *((_QWORD *)v3 + 1) = v5;
    CDescriptionManager::PurgeRegistrationParams(v2, v4);
    operator delete(v4, 0x50u);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  CTable<_GUID,_TP_WORK *>::Clear((char *)this + 320);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
}

```

## disassembly

```asm
0x1800114c8  push    rbx
0x1800114ca  push    rsi
0x1800114cb  push    rdi
0x1800114cc  push    r14
0x1800114ce  push    r15
0x1800114d0  sub     rsp, 20h
0x1800114d4  xor     r8d, r8d; pvCleanupContext
0x1800114d7  mov     rsi, rcx
0x1800114da  mov     rcx, [rcx+1D8h]; ptpcg
0x1800114e1  lea     edx, [r8+1]; fCancelPendingCallbacks
0x1800114e5  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800114ec  nop     dword ptr [rax+rax+00h]
0x1800114f1  lea     rbx, [rsi+1E8h]
0x1800114f8  mov     rcx, rbx; lpCriticalSection
0x1800114fb  call    cs:__imp_EnterCriticalSection
0x180011502  nop     dword ptr [rax+rax+00h]
0x180011507  lea     r15, [rsi+260h]
0x18001150e  mov     r14, [r15]
0x180011511  jmp     short loc_18001153C
0x180011513  mov     rdx, [r14]
0x180011516  mov     rdi, r14
0x180011519  mov     rax, [r14+8]
0x18001151d  mov     r14, rdx
0x180011520  mov     [rax], rdx
0x180011523  mov     [rdx+8], rax
0x180011527  mov     rdx, rdi; struct SSDP_SERVICE_REGISTRATION_PARAMS *
0x18001152a  call    ?PurgeRegistrationParams@CDescriptionManager@@AEAAXPEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z; CDescriptionManager::PurgeRegistrationParams(SSDP_SERVICE_REGISTRATION_PARAMS *)
0x18001152f  mov     edx, 50h ; 'P'; unsigned __int64
0x180011534  mov     rcx, rdi; void *
0x180011537  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001153c  cmp     r14, r15
0x18001153f  jnz     short loc_180011513
0x180011541  mov     rcx, rbx; lpCriticalSection
0x180011544  call    cs:__imp_LeaveCriticalSection
0x18001154b  nop     dword ptr [rax+rax+00h]
0x180011550  mov     rcx, rbx; lpCriticalSection
0x180011553  call    cs:__imp_EnterCriticalSection
0x18001155a  nop     dword ptr [rax+rax+00h]
0x18001155f  lea     rcx, [rsi+140h]
0x180011566  call    ?Clear@?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAAXXZ; CTable<_GUID,_TP_WORK *>::Clear(void)
0x18001156b  mov     rcx, rbx
0x18001156e  add     rsp, 20h
0x180011572  pop     r15
0x180011574  pop     r14
0x180011576  pop     rdi
0x180011577  pop     rsi
0x180011578  pop     rbx
0x180011579  jmp     cs:__imp_LeaveCriticalSection
```
