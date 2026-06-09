# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x1800155ec`
- end: `0x180015650`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800153c8`
- `0x1800154c0`

## callees

- `0x1800155ec`
- `0x180016328`
- `0x180016ec4`

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
0x1800155ec  mov     [rsp+arg_0], rbx
0x1800155f1  mov     [rsp+arg_8], rsi
0x1800155f6  push    rdi; char *
0x1800155f7  sub     rsp, 20h
0x1800155fb  mov     rsi, rcx
0x1800155fe  mov     rbx, [rcx+20h]
0x180015602  mov     rdi, [rcx+28h]
0x180015606  mov     rax, rdi
0x180015609  sub     rax, rbx
0x18001560c  cmp     rax, 10h
0x180015610  jb      short loc_180015640
0x180015612  cmp     rbx, rdi
0x180015615  jz      short loc_180015628
0x180015617  mov     rdx, [rbx+8]
0x18001561b  mov     ecx, [rbx]
0x18001561d  call    wil_details_RecordCachedUsage
0x180015622  add     rbx, 10h
0x180015626  jmp     short loc_180015612
0x180015628  mov     rax, [rsi+20h]
0x18001562c  mov     [rsi+28h], rax
0x180015630  xor     r8d, r8d; unsigned int
0x180015633  mov     edx, 0FEh; unsigned int
0x180015638  xor     ecx, ecx; this
0x18001563a  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18001563f  nop
0x180015640  mov     rbx, [rsp+28h+arg_0]
0x180015645  mov     rsi, [rsp+28h+arg_8]
0x18001564a  add     rsp, 20h
0x18001564e  pop     rdi
0x18001564f  retn
```
