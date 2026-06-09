# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x1800397e8`
- end: `0x18003984b`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180039428`
- `0x1800396d4`

## callees

- `0x1800397e8`
- `0x18003bc6c`
- `0x18003c684`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  __int64 v4; // rdi
  __int64 v6; // rbx
  const char *v7; // [rsp+20h] [rbp-8h]

  v4 = *(_QWORD *)(a1 + 40);
  v6 = *(_QWORD *)(a1 + 32);
  if ( (unsigned __int64)(v4 - v6) >= 0x10 )
  {
    while ( v6 != v4 )
    {
      wil_details_RecordCachedUsage(*(_DWORD *)v6, *(_QWORD *)(v6 + 8));
      v6 += 16;
    }
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32);
    wil::details::WilApi_RecordFeatureUsage(0, 0xFEu, 0, a4, v7);
  }
}

```

## disassembly

```asm
0x1800397e8  mov     [rsp+arg_0], rbx
0x1800397ed  mov     [rsp+arg_8], rsi
0x1800397f2  push    rdi; char *
0x1800397f3  sub     rsp, 20h
0x1800397f7  mov     rdi, [rcx+28h]
0x1800397fb  mov     rsi, rcx
0x1800397fe  mov     rbx, [rcx+20h]
0x180039802  mov     rax, rdi
0x180039805  sub     rax, rbx
0x180039808  cmp     rax, 10h
0x18003980c  jb      short loc_18003983B
0x18003980e  cmp     rbx, rdi
0x180039811  jz      short loc_180039824
0x180039813  mov     rdx, [rbx+8]
0x180039817  mov     ecx, [rbx]
0x180039819  call    wil_details_RecordCachedUsage
0x18003981e  add     rbx, 10h
0x180039822  jmp     short loc_18003980E
0x180039824  mov     rax, [rsi+20h]
0x180039828  xor     r8d, r8d; unsigned int
0x18003982b  mov     edx, 0FEh; unsigned int
0x180039830  mov     [rsi+28h], rax
0x180039834  xor     ecx, ecx; this
0x180039836  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18003983b  mov     rbx, [rsp+28h+arg_0]
0x180039840  mov     rsi, [rsp+28h+arg_8]
0x180039845  add     rsp, 20h
0x180039849  pop     rdi
0x18003984a  retn
```
