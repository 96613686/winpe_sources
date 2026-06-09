# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180009b24`
- end: `0x180009b88`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800044e8`
- `0x1800095d8`

## callees

- `0x180009b24`
- `0x18000b770`
- `0x18000f9a0`

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
0x180009b24  mov     [rsp+arg_0], rbx
0x180009b29  mov     [rsp+arg_8], rsi
0x180009b2e  push    rdi; char *
0x180009b2f  sub     rsp, 20h
0x180009b33  mov     rsi, rcx
0x180009b36  mov     rbx, [rcx+20h]
0x180009b3a  mov     rdi, [rcx+28h]
0x180009b3e  mov     rax, rdi
0x180009b41  sub     rax, rbx
0x180009b44  cmp     rax, 10h
0x180009b48  jb      short loc_180009B78
0x180009b4a  cmp     rbx, rdi
0x180009b4d  jz      short loc_180009B60
0x180009b4f  mov     rdx, [rbx+8]
0x180009b53  mov     ecx, [rbx]
0x180009b55  call    wil_details_RecordCachedUsage
0x180009b5a  add     rbx, 10h
0x180009b5e  jmp     short loc_180009B4A
0x180009b60  mov     rax, [rsi+20h]
0x180009b64  mov     [rsi+28h], rax
0x180009b68  xor     r8d, r8d; unsigned int
0x180009b6b  mov     edx, 0FEh; unsigned int
0x180009b70  xor     ecx, ecx; this
0x180009b72  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180009b77  nop
0x180009b78  mov     rbx, [rsp+28h+arg_0]
0x180009b7d  mov     rsi, [rsp+28h+arg_8]
0x180009b82  add     rsp, 20h
0x180009b86  pop     rdi
0x180009b87  retn
```
