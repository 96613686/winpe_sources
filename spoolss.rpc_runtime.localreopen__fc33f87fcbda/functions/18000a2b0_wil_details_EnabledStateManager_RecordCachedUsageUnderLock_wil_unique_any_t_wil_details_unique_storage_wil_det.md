# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000a2b0`
- end: `0x18000a315`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004890`
- `0x180009d20`

## callees

- `0x18000a2b0`
- `0x18000c094`
- `0x180010a84`

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
0x18000a2b0  mov     [rsp+arg_0], rbx
0x18000a2b5  mov     [rsp+arg_8], rsi
0x18000a2ba  push    rdi; char *
0x18000a2bb  sub     rsp, 20h
0x18000a2bf  mov     rsi, rcx
0x18000a2c2  mov     rbx, [rcx+30h]
0x18000a2c6  mov     rdi, [rcx+38h]
0x18000a2ca  mov     rax, rdi
0x18000a2cd  sub     rax, rbx
0x18000a2d0  cmp     rax, 10h
0x18000a2d4  jb      short loc_18000A304
0x18000a2d6  cmp     rbx, rdi
0x18000a2d9  jz      short loc_18000A2EC
0x18000a2db  mov     rdx, [rbx+8]
0x18000a2df  mov     ecx, [rbx]
0x18000a2e1  call    wil_details_RecordCachedUsage
0x18000a2e6  add     rbx, 10h
0x18000a2ea  jmp     short loc_18000A2D6
0x18000a2ec  mov     rax, [rsi+30h]
0x18000a2f0  mov     [rsi+38h], rax
0x18000a2f4  xor     r8d, r8d; unsigned int
0x18000a2f7  mov     edx, 0FEh; unsigned int
0x18000a2fc  xor     ecx, ecx; this
0x18000a2fe  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000a303  nop
0x18000a304  mov     rbx, [rsp+28h+arg_0]
0x18000a309  mov     rsi, [rsp+28h+arg_8]
0x18000a30e  add     rsp, 20h
0x18000a312  pop     rdi
0x18000a313  retn
```
