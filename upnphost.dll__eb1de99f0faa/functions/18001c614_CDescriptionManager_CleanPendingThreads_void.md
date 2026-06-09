# CDescriptionManager::CleanPendingThreads(void)

- ea: `0x18001c614`
- end: `0x18001c6b4`
- name: `?CleanPendingThreads@CDescriptionManager@@AEAAXXZ`
- size: `160`
- prototype: `void __fastcall(CDescriptionManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x18001c410`

## callees

- `0x18001c614`
- `0x18001da24`
- `0x18003850c`
- `0x18003a584`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c641`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c68d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c641`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c68d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c684`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c684`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c6ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001c631`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001c631`

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
    operator delete(v4);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  CTable<_GUID,_TP_WORK *>::Clear((char *)this + 320);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
}

```

## disassembly

```asm
0x18001c614  push    rbx
0x18001c616  push    rsi
0x18001c617  push    rdi
0x18001c618  push    r14
0x18001c61a  push    r15
0x18001c61c  sub     rsp, 20h
0x18001c620  xor     r8d, r8d; pvCleanupContext
0x18001c623  mov     rsi, rcx
0x18001c626  mov     rcx, [rcx+1D8h]; ptpcg
0x18001c62d  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18001c631  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001c637  lea     rbx, [rsi+1E8h]
0x18001c63e  mov     rcx, rbx; lpCriticalSection
0x18001c641  call    cs:__imp_EnterCriticalSection
0x18001c647  lea     r15, [rsi+260h]
0x18001c64e  mov     r14, [r15]
0x18001c651  jmp     short loc_18001C67C
0x18001c653  mov     rdx, [r14]
0x18001c656  mov     rdi, r14
0x18001c659  mov     rax, [r14+8]
0x18001c65d  mov     r14, rdx
0x18001c660  mov     [rax], rdx
0x18001c663  mov     [rdx+8], rax
0x18001c667  mov     rdx, rdi; struct SSDP_SERVICE_REGISTRATION_PARAMS *
0x18001c66a  call    ?PurgeRegistrationParams@CDescriptionManager@@AEAAXPEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z; CDescriptionManager::PurgeRegistrationParams(SSDP_SERVICE_REGISTRATION_PARAMS *)
0x18001c66f  mov     edx, 50h ; 'P'; unsigned __int64
0x18001c674  mov     rcx, rdi; void *
0x18001c677  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c67c  cmp     r14, r15
0x18001c67f  jnz     short loc_18001C653
0x18001c681  mov     rcx, rbx; lpCriticalSection
0x18001c684  call    cs:__imp_LeaveCriticalSection
0x18001c68a  mov     rcx, rbx; lpCriticalSection
0x18001c68d  call    cs:__imp_EnterCriticalSection
0x18001c693  lea     rcx, [rsi+140h]
0x18001c69a  call    ?Clear@?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAAXXZ; CTable<_GUID,_TP_WORK *>::Clear(void)
0x18001c69f  mov     rcx, rbx
0x18001c6a2  add     rsp, 20h
0x18001c6a6  pop     r15
0x18001c6a8  pop     r14
0x18001c6aa  pop     rdi
0x18001c6ab  pop     rsi
0x18001c6ac  pop     rbx
0x18001c6ad  jmp     cs:__imp_LeaveCriticalSection
```
