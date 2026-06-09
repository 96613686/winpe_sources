# ListDeleteAllObjects<CBindPolicy::Binding,CCriticalSection>(CList<CBindPolicy::Binding,CCriticalSection> *)

- ea: `0x180002818`
- end: `0x1800028b7`
- name: `??$ListDeleteAllObjects@UBinding@CBindPolicy@@VCCriticalSection@@@@YAXPEAV?$CList@UBinding@CBindPolicy@@VCCriticalSection@@@@@Z`
- size: `159`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180004c00`
- `0x180010090`
- `0x180010830`

## callees

- `0x180002818`
- `0x180004040`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002885`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002885`
- `KERNEL32!EnterCriticalSection` at `0x180002831`
- `KERNEL32!EnterCriticalSection` at `0x180002840`
- `KERNEL32!EnterCriticalSection` at `0x180002831`
- `KERNEL32!EnterCriticalSection` at `0x180002840`
- `KERNEL32!LeaveCriticalSection` at `0x180002852`
- `KERNEL32!LeaveCriticalSection` at `0x180002852`
- `KERNEL32!LeaveCriticalSection` at `0x1800028ab`

## pseudocode

```c
void __fastcall ListDeleteAllObjects<CBindPolicy::Binding,CCriticalSection>(__int64 *a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v3; // rbx
  void *v4; // rax
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 2);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 2));
  EnterCriticalSection(v1);
  v3 = *a1;
  LeaveCriticalSection(v1);
  if ( v3 )
  {
    v5 = *a1;
    while ( v5 )
    {
      v4 = (void *)CList<CBindPolicy::Binding,CCriticalSection>::DeleteAt(a1, &v5);
      if ( v4 )
        operator delete(v4);
    }
  }
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180002818  mov     [rsp+arg_8], rbx
0x18000281d  mov     [rsp+arg_10], rsi
0x180002822  push    rdi
0x180002823  sub     rsp, 20h
0x180002827  lea     rdi, [rcx+10h]
0x18000282b  mov     rsi, rcx
0x18000282e  mov     rcx, rdi; lpCriticalSection
0x180002831  call    cs:__imp_EnterCriticalSection
0x180002838  nop     dword ptr [rax+rax+00h]
0x18000283d  mov     rcx, rdi; lpCriticalSection
0x180002840  call    cs:__imp_EnterCriticalSection
0x180002847  nop     dword ptr [rax+rax+00h]
0x18000284c  mov     rbx, [rsi]
0x18000284f  mov     rcx, rdi; lpCriticalSection
0x180002852  call    cs:__imp_LeaveCriticalSection
0x180002859  nop     dword ptr [rax+rax+00h]
0x18000285e  test    rbx, rbx
0x180002861  jz      short loc_180002899
0x180002863  mov     rax, [rsi]
0x180002866  mov     [rsp+28h+arg_0], rax
0x18000286b  test    rax, rax
0x18000286e  jz      short loc_180002899
0x180002870  lea     rdx, [rsp+28h+arg_0]
0x180002875  mov     rcx, rsi
0x180002878  call    ?DeleteAt@?$CList@UBinding@CBindPolicy@@VCCriticalSection@@@@QEAAPEAUBinding@CBindPolicy@@AEAPEAX@Z; CList<CBindPolicy::Binding,CCriticalSection>::DeleteAt(void * &)
0x18000287d  test    rax, rax
0x180002880  jz      short loc_180002891
0x180002882  mov     rcx, rax
0x180002885  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000288c  nop     dword ptr [rax+rax+00h]
0x180002891  cmp     [rsp+28h+arg_0], 0
0x180002897  jnz     short loc_180002870
0x180002899  mov     rcx, rdi
0x18000289c  mov     rbx, [rsp+28h+arg_8]
0x1800028a1  mov     rsi, [rsp+28h+arg_10]
0x1800028a6  add     rsp, 20h
0x1800028aa  pop     rdi
0x1800028ab  jmp     cs:__imp_LeaveCriticalSection
```
