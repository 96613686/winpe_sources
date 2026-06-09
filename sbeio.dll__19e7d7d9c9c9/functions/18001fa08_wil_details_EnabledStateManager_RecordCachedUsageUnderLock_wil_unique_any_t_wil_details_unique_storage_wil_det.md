# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18001fa08`
- end: `0x18001fa6b`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001da38`
- `0x18001f820`

## callees

- `0x18001fa08`
- `0x180026d8c`
- `0x1800277e4`

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
0x18001fa08  mov     [rsp+arg_0], rbx
0x18001fa0d  mov     [rsp+arg_8], rsi
0x18001fa12  push    rdi; char *
0x18001fa13  sub     rsp, 20h
0x18001fa17  mov     rdi, [rcx+28h]
0x18001fa1b  mov     rsi, rcx
0x18001fa1e  mov     rbx, [rcx+20h]
0x18001fa22  mov     rax, rdi
0x18001fa25  sub     rax, rbx
0x18001fa28  cmp     rax, 10h
0x18001fa2c  jb      short loc_18001FA5B
0x18001fa2e  cmp     rbx, rdi
0x18001fa31  jz      short loc_18001FA44
0x18001fa33  mov     rdx, [rbx+8]
0x18001fa37  mov     ecx, [rbx]
0x18001fa39  call    wil_details_RecordCachedUsage
0x18001fa3e  add     rbx, 10h
0x18001fa42  jmp     short loc_18001FA2E
0x18001fa44  mov     rax, [rsi+20h]
0x18001fa48  xor     r8d, r8d; unsigned int
0x18001fa4b  mov     edx, 0FEh; unsigned int
0x18001fa50  mov     [rsi+28h], rax
0x18001fa54  xor     ecx, ecx; this
0x18001fa56  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18001fa5b  mov     rbx, [rsp+28h+arg_0]
0x18001fa60  mov     rsi, [rsp+28h+arg_8]
0x18001fa65  add     rsp, 20h
0x18001fa69  pop     rdi
0x18001fa6a  retn
```
