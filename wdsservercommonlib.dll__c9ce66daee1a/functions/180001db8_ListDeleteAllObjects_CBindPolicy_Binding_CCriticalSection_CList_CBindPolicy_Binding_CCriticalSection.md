# ListDeleteAllObjects<CBindPolicy::Binding,CCriticalSection>(CList<CBindPolicy::Binding,CCriticalSection> *)

- ea: `0x180001db8`
- end: `0x180001e50`
- name: `??$ListDeleteAllObjects@UBinding@CBindPolicy@@VCCriticalSection@@@@YAXPEAV?$CList@UBinding@CBindPolicy@@VCCriticalSection@@@@@Z`
- size: `152`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180004160`
- `0x18000f4e0`
- `0x18000fc70`

## callees

- `0x180001db8`
- `0x1800035a0`
- `0x18002e468`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180001dd1`
- `KERNEL32!EnterCriticalSection` at `0x180001de0`
- `KERNEL32!EnterCriticalSection` at `0x180001dd1`
- `KERNEL32!EnterCriticalSection` at `0x180001de0`
- `KERNEL32!LeaveCriticalSection` at `0x180001df2`
- `KERNEL32!LeaveCriticalSection` at `0x180001df2`
- `KERNEL32!LeaveCriticalSection` at `0x180001e44`

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
0x180001db8  mov     [rsp+arg_8], rbx
0x180001dbd  mov     [rsp+arg_10], rsi
0x180001dc2  push    rdi
0x180001dc3  sub     rsp, 20h
0x180001dc7  lea     rdi, [rcx+10h]
0x180001dcb  mov     rsi, rcx
0x180001dce  mov     rcx, rdi; lpCriticalSection
0x180001dd1  call    cs:__imp_EnterCriticalSection
0x180001dd8  nop     dword ptr [rax+rax+00h]
0x180001ddd  mov     rcx, rdi; lpCriticalSection
0x180001de0  call    cs:__imp_EnterCriticalSection
0x180001de7  nop     dword ptr [rax+rax+00h]
0x180001dec  mov     rbx, [rsi]
0x180001def  mov     rcx, rdi; lpCriticalSection
0x180001df2  call    cs:__imp_LeaveCriticalSection
0x180001df9  nop     dword ptr [rax+rax+00h]
0x180001dfe  test    rbx, rbx
0x180001e01  jz      short loc_180001E32
0x180001e03  mov     rax, [rsi]
0x180001e06  mov     [rsp+28h+arg_0], rax
0x180001e0b  test    rax, rax
0x180001e0e  jz      short loc_180001E32
0x180001e10  lea     rdx, [rsp+28h+arg_0]
0x180001e15  mov     rcx, rsi
0x180001e18  call    ?DeleteAt@?$CList@UBinding@CBindPolicy@@VCCriticalSection@@@@QEAAPEAUBinding@CBindPolicy@@AEAPEAX@Z; CList<CBindPolicy::Binding,CCriticalSection>::DeleteAt(void * &)
0x180001e1d  test    rax, rax
0x180001e20  jz      short loc_180001E2A
0x180001e22  mov     rcx, rax; lpMem
0x180001e25  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001e2a  cmp     [rsp+28h+arg_0], 0
0x180001e30  jnz     short loc_180001E10
0x180001e32  mov     rcx, rdi
0x180001e35  mov     rbx, [rsp+28h+arg_8]
0x180001e3a  mov     rsi, [rsp+28h+arg_10]
0x180001e3f  add     rsp, 20h
0x180001e43  pop     rdi
0x180001e44  jmp     cs:__imp_LeaveCriticalSection
```
