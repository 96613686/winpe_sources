# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000fdb0`
- end: `0x18000fe14`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000f7ac`
- `0x18000f8a8`

## callees

- `0x18000fdb0`
- `0x180011da4`
- `0x1800138f0`

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
0x18000fdb0  mov     [rsp+arg_0], rbx
0x18000fdb5  mov     [rsp+arg_8], rsi
0x18000fdba  push    rdi; char *
0x18000fdbb  sub     rsp, 20h
0x18000fdbf  mov     rsi, rcx
0x18000fdc2  mov     rbx, [rcx+20h]
0x18000fdc6  mov     rdi, [rcx+28h]
0x18000fdca  mov     rax, rdi
0x18000fdcd  sub     rax, rbx
0x18000fdd0  cmp     rax, 10h
0x18000fdd4  jb      short loc_18000FE04
0x18000fdd6  cmp     rbx, rdi
0x18000fdd9  jz      short loc_18000FDEC
0x18000fddb  mov     rdx, [rbx+8]
0x18000fddf  mov     ecx, [rbx]
0x18000fde1  call    wil_details_RecordCachedUsage
0x18000fde6  add     rbx, 10h
0x18000fdea  jmp     short loc_18000FDD6
0x18000fdec  mov     rax, [rsi+20h]
0x18000fdf0  mov     [rsi+28h], rax
0x18000fdf4  xor     r8d, r8d; unsigned int
0x18000fdf7  mov     edx, 0FEh; unsigned int
0x18000fdfc  xor     ecx, ecx; this
0x18000fdfe  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000fe03  nop
0x18000fe04  mov     rbx, [rsp+28h+arg_0]
0x18000fe09  mov     rsi, [rsp+28h+arg_8]
0x18000fe0e  add     rsp, 20h
0x18000fe12  pop     rdi
0x18000fe13  retn
```
