# _DbgpRegistryChangeNotifycationCallback(void *,uchar)

- ea: `0x180036570`
- end: `0x180036610`
- name: `?_DbgpRegistryChangeNotifycationCallback@@YAXPEAXE@Z`
- size: `160`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800369dc`

## callees

- `0x180035c7c`
- `0x180036360`
- `0x180036570`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036596`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800365c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036596`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800365c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800365f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800365ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800365f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800365ff`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800365ed`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800365ed`

## pseudocode

```c
void __fastcall _DbgpRegistryChangeNotifycationCallback(void *a1, unsigned __int8 a2)
{
  int v2; // r14d
  struct _RTL_CRITICAL_SECTION *SharedMem; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  PRTL_CRITICAL_SECTION_DEBUG i; // rdi

  v2 = a2;
  SharedMem = (struct _RTL_CRITICAL_SECTION *)_DbgpOpenOrCreateSharedMem();
  v5 = SharedMem;
  if ( SharedMem )
  {
    v6 = SharedMem + 2;
    EnterCriticalSection(SharedMem + 2);
    v7 = v5 + 1;
    for ( i = v7->DebugInfo; i != (PRTL_CRITICAL_SECTION_DEBUG)v7; i = *(PRTL_CRITICAL_SECTION_DEBUG *)&i->Type )
    {
      if ( *(void **)&i[4].Flags == a1 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)&i[4]);
        _DbgpControlTracingThroughRegistry((struct _DBG_TRACE_CONTROL_BLOCK *)i, v2);
        RegNotifyChangeKeyValue((HKEY)i[3].ProcessLocksList.Blink, 0, 4u, i[3].CriticalSection, 1);
        LeaveCriticalSection((LPCRITICAL_SECTION)&i[4]);
        break;
      }
    }
    LeaveCriticalSection(v6);
  }
}

```

## disassembly

```asm
0x180036570  push    rbx
0x180036572  push    rbp
0x180036573  push    rsi
0x180036574  push    rdi
0x180036575  push    r14
0x180036577  sub     rsp, 30h
0x18003657b  movzx   r14d, dl
0x18003657f  mov     rbp, rcx
0x180036582  call    ?_DbgpOpenOrCreateSharedMem@@YAPEAU_DBG_TCB_HEADER@@XZ; _DbgpOpenOrCreateSharedMem(void)
0x180036587  mov     rbx, rax
0x18003658a  test    rax, rax
0x18003658d  jz      short loc_180036605
0x18003658f  lea     rsi, [rax+50h]
0x180036593  mov     rcx, rsi; lpCriticalSection
0x180036596  call    cs:__imp_EnterCriticalSection
0x18003659c  add     rbx, 28h ; '('
0x1800365a0  mov     rdi, [rbx]
0x1800365a3  cmp     rdi, rbx
0x1800365a6  jz      short loc_1800365FC
0x1800365a8  cmp     [rdi+0E8h], rbp
0x1800365af  jz      short loc_1800365B6
0x1800365b1  mov     rdi, [rdi]
0x1800365b4  jmp     short loc_1800365A3
0x1800365b6  lea     rbx, [rdi+0C0h]
0x1800365bd  mov     rcx, rbx; lpCriticalSection
0x1800365c0  call    cs:__imp_EnterCriticalSection
0x1800365c6  mov     edx, r14d; int
0x1800365c9  mov     rcx, rdi; struct _DBG_TRACE_CONTROL_BLOCK *
0x1800365cc  call    ?_DbgpControlTracingThroughRegistry@@YAKPEAU_DBG_TRACE_CONTROL_BLOCK@@H@Z; _DbgpControlTracingThroughRegistry(_DBG_TRACE_CONTROL_BLOCK *,int)
0x1800365d1  mov     r9, [rdi+98h]; hEvent
0x1800365d8  xor     edx, edx; bWatchSubtree
0x1800365da  mov     rcx, [rdi+0A8h]; hKey
0x1800365e1  mov     [rsp+58h+fAsynchronous], 1; fAsynchronous
0x1800365e9  lea     r8d, [rdx+4]; dwNotifyFilter
0x1800365ed  call    cs:__imp_RegNotifyChangeKeyValue
0x1800365f3  mov     rcx, rbx; lpCriticalSection
0x1800365f6  call    cs:__imp_LeaveCriticalSection
0x1800365fc  mov     rcx, rsi; lpCriticalSection
0x1800365ff  call    cs:__imp_LeaveCriticalSection
0x180036605  add     rsp, 30h
0x180036609  pop     r14
0x18003660b  pop     rdi
0x18003660c  pop     rsi
0x18003660d  pop     rbp
0x18003660e  pop     rbx
0x18003660f  retn
```
