# CWindowList::UpdateScene(void)

- ea: `0x18001f540`
- end: `0x18001f630`
- name: `?UpdateScene@CWindowList@@UEAAJXZ`
- size: `240`
- prototype: `__int64 __fastcall(CWindowList *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001d710`
- `0x18002e01c`

## callees

- `0x180014ea0`
- `0x180014ee4`
- `0x18001e630`
- `0x18001f540`
- `0x18001f640`
- `0x18001f680`
- `0x180081a68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f56e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f56e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f5b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f5e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f5b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f5e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f582`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f582`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWindowList::UpdateScene(CWindowList *this)
{
  int v2; // edi
  int updated; // eax
  unsigned int v4; // ebx
  CAnimationEngine *v6; // rax
  CAnimationEngine *v7; // rdi
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !*((_BYTE *)CDesktopManager::s_pDesktopManagerInstance + 25) )
    return 0;
  EnterCriticalSection(&CDesktopManager::s_csDwmInstance);
  v2 = *((_DWORD *)CDesktopManager::s_pDesktopManagerInstance + 282);
  if ( GetCurrentThreadId() != v2
    && (int)CAnimationScheduler::GetActiveStoryboardCount(*((CAnimationScheduler **)CDesktopManager::s_pDesktopManagerInstance
                                                          + 23)) > 0 )
  {
    v6 = CDesktopManager::AcquireAnimationEngine();
    v7 = v6;
    if ( v6 )
    {
      if ( CAnimationEngine::IsIdle(v6) )
      {
        CAnimationEngine::Release(v7);
        goto LABEL_5;
      }
      CAnimationEngine::Release(v7);
    }
  }
  updated = CWindowList::ForceUpdateScene(this);
  v4 = updated;
  if ( updated >= 0 )
  {
LABEL_5:
    LeaveCriticalSection(&CDesktopManager::s_csDwmInstance);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A82,
    (unsigned int)"clientcore\\windows\\dwm\\udwm\\windowlist.cpp",
    (const char *)(unsigned int)updated,
    v8);
  LeaveCriticalSection(&CDesktopManager::s_csDwmInstance);
  return v4;
}

```

## disassembly

```asm
0x18001f540  mov     [rsp+arg_0], rbx
0x18001f545  mov     [rsp+arg_10], rsi
0x18001f54a  push    rdi; int
0x18001f54b  sub     rsp, 20h
0x18001f54f  mov     rbx, rcx
0x18001f552  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18001f559  cmp     byte ptr [rax+19h], 0
0x18001f55d  jz      short loc_18001F5BA
0x18001f55f  lea     rsi, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; CDwmCS CDesktopManager::s_csDwmInstance
0x18001f566  mov     [rsp+28h+arg_8], rsi
0x18001f56b  mov     rcx, rsi; lpCriticalSection
0x18001f56e  call    cs:__imp_EnterCriticalSection
0x18001f574  nop
0x18001f575  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18001f57c  mov     edi, [rax+468h]
0x18001f582  call    cs:__imp_GetCurrentThreadId
0x18001f588  cmp     eax, edi
0x18001f58a  jz      short loc_18001F5A3
0x18001f58c  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18001f593  mov     rcx, [rcx+0B8h]; this
0x18001f59a  call    ?GetActiveStoryboardCount@CAnimationScheduler@@QEAAHXZ; CAnimationScheduler::GetActiveStoryboardCount(void)
0x18001f59f  test    eax, eax
0x18001f5a1  jg      short loc_18001F601
0x18001f5a3  mov     rcx, rbx; this
0x18001f5a6  call    ?ForceUpdateScene@CWindowList@@QEAAJXZ; CWindowList::ForceUpdateScene(void)
0x18001f5ab  mov     ebx, eax
0x18001f5ad  test    eax, eax
0x18001f5af  js      short loc_18001F5CC
0x18001f5b1  mov     rcx, rsi; lpCriticalSection
0x18001f5b4  call    cs:__imp_LeaveCriticalSection
0x18001f5ba  xor     eax, eax
0x18001f5bc  mov     rbx, [rsp+28h+arg_0]
0x18001f5c1  mov     rsi, [rsp+28h+arg_10]
0x18001f5c6  add     rsp, 20h
0x18001f5ca  pop     rdi
0x18001f5cb  retn
0x18001f5cc  mov     rcx, [rsp+28h]; this
0x18001f5d1  mov     r9d, ebx; char *
0x18001f5d4  lea     r8, aClientcoreWind_34; "clientcore\\windows\\dwm\\udwm\\windowl"...
0x18001f5db  mov     edx, 1A82h; void *
0x18001f5e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f5e5  nop
0x18001f5e6  mov     rcx, rsi; lpCriticalSection
0x18001f5e9  call    cs:__imp_LeaveCriticalSection
0x18001f5ef  mov     eax, ebx
0x18001f5f1  mov     rbx, [rsp+28h+arg_0]
0x18001f5f6  mov     rsi, [rsp+28h+arg_10]
0x18001f5fb  add     rsp, 20h
0x18001f5ff  pop     rdi
0x18001f600  retn
0x18001f601  call    ?AcquireAnimationEngine@CDesktopManager@@SAPEAVCAnimationEngine@@XZ; CDesktopManager::AcquireAnimationEngine(void)
0x18001f606  nop
0x18001f607  mov     rdi, rax
0x18001f60a  test    rax, rax
0x18001f60d  jz      short loc_18001F5A3
0x18001f60f  mov     rcx, rax; this
0x18001f612  call    ?IsIdle@CAnimationEngine@@QEAA_NXZ; CAnimationEngine::IsIdle(void)
0x18001f617  mov     rcx, rdi; this
0x18001f61a  test    al, al
0x18001f61c  jz      short loc_18001F625
0x18001f61e  call    ?Release@CAnimationEngine@@UEAAKXZ; CAnimationEngine::Release(void)
0x18001f623  jmp     short loc_18001F5B1
0x18001f625  call    ?Release@CAnimationEngine@@UEAAKXZ; CAnimationEngine::Release(void)
0x18001f62a  jmp     loc_18001F5A3
```
