# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000f02c`
- end: `0x18000f091`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ec14`
- `0x180016350`

## callees

- `0x18000f02c`
- `0x1800109f8`
- `0x180014588`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  const char *v7; // [rsp+20h] [rbp-8h]

  v5 = *(_QWORD *)(a1 + 48);
  v6 = *(_QWORD *)(a1 + 56);
  if ( (unsigned __int64)(v6 - v5) >= 0x10 )
  {
    while ( v5 != v6 )
    {
      wil_details_RecordCachedUsage(*(_DWORD *)v5, *(_QWORD *)(v5 + 8));
      v5 += 16;
    }
    *(_QWORD *)(a1 + 56) = *(_QWORD *)(a1 + 48);
    wil::details::WilApi_RecordFeatureUsage(0, 0xFEu, 0, a4, v7);
  }
}

```

## disassembly

```asm
0x18000f02c  mov     [rsp+arg_8], rbx
0x18000f031  mov     [rsp+arg_10], rsi
0x18000f036  push    rdi; char *
0x18000f037  sub     rsp, 20h
0x18000f03b  mov     rsi, rcx
0x18000f03e  mov     rbx, [rcx+30h]
0x18000f042  mov     rdi, [rcx+38h]
0x18000f046  mov     rax, rdi
0x18000f049  sub     rax, rbx
0x18000f04c  cmp     rax, 10h
0x18000f050  jb      short loc_18000F080
0x18000f052  cmp     rbx, rdi
0x18000f055  jz      short loc_18000F068
0x18000f057  mov     rdx, [rbx+8]
0x18000f05b  mov     ecx, [rbx]
0x18000f05d  call    wil_details_RecordCachedUsage
0x18000f062  add     rbx, 10h
0x18000f066  jmp     short loc_18000F052
0x18000f068  mov     rax, [rsi+30h]
0x18000f06c  mov     [rsi+38h], rax
0x18000f070  xor     r8d, r8d; unsigned int
0x18000f073  mov     edx, 0FEh; unsigned int
0x18000f078  xor     ecx, ecx; this
0x18000f07a  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000f07f  nop
0x18000f080  mov     rbx, [rsp+28h+arg_8]
0x18000f085  mov     rsi, [rsp+28h+arg_10]
0x18000f08a  add     rsp, 20h
0x18000f08e  pop     rdi
0x18000f08f  retn
```
