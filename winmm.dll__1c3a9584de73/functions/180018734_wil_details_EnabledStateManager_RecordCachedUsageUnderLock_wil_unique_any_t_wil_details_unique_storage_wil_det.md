# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180018734`
- end: `0x180018798`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800064a4`
- `0x180009314`

## callees

- `0x180009580`
- `0x18000ae28`
- `0x180018734`

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

  v5 = *(_QWORD *)(a1 + 32);
  v6 = *(_QWORD *)(a1 + 40);
  if ( (unsigned __int64)(v6 - v5) >= 0x10 )
  {
    while ( v5 != v6 )
    {
      wil_details_RecordCachedUsage(*(_DWORD *)v5, *(_QWORD *)(v5 + 8));
      v5 += 16;
    }
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32);
    wil::details::WilApi_RecordFeatureUsage(0, 0xFEu, 0, a4, v7);
  }
}

```

## disassembly

```asm
0x180018734  mov     [rsp+arg_0], rbx
0x180018739  mov     [rsp+arg_8], rsi
0x18001873e  push    rdi; char *
0x18001873f  sub     rsp, 20h
0x180018743  mov     rsi, rcx
0x180018746  mov     rbx, [rcx+20h]
0x18001874a  mov     rdi, [rcx+28h]
0x18001874e  mov     rax, rdi
0x180018751  sub     rax, rbx
0x180018754  cmp     rax, 10h
0x180018758  jb      short loc_180018788
0x18001875a  cmp     rbx, rdi
0x18001875d  jz      short loc_180018770
0x18001875f  mov     rdx, [rbx+8]
0x180018763  mov     ecx, [rbx]
0x180018765  call    wil_details_RecordCachedUsage
0x18001876a  add     rbx, 10h
0x18001876e  jmp     short loc_18001875A
0x180018770  mov     rax, [rsi+20h]
0x180018774  mov     [rsi+28h], rax
0x180018778  xor     r8d, r8d; unsigned int
0x18001877b  mov     edx, 0FEh; unsigned int
0x180018780  xor     ecx, ecx; this
0x180018782  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180018787  nop
0x180018788  mov     rbx, [rsp+28h+arg_0]
0x18001878d  mov     rsi, [rsp+28h+arg_8]
0x180018792  add     rsp, 20h
0x180018796  pop     rdi
0x180018797  retn
```
