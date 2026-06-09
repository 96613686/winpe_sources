# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180010eb0`
- end: `0x180010f13`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800062f0`
- `0x180010db0`

## callees

- `0x180010eb0`
- `0x180011e9c`
- `0x1800120e4`

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
0x180010eb0  mov     [rsp+arg_0], rbx
0x180010eb5  mov     [rsp+arg_8], rsi
0x180010eba  push    rdi; char *
0x180010ebb  sub     rsp, 20h
0x180010ebf  mov     rdi, [rcx+28h]
0x180010ec3  mov     rsi, rcx
0x180010ec6  mov     rbx, [rcx+20h]
0x180010eca  mov     rax, rdi
0x180010ecd  sub     rax, rbx
0x180010ed0  cmp     rax, 10h
0x180010ed4  jb      short loc_180010F03
0x180010ed6  cmp     rbx, rdi
0x180010ed9  jz      short loc_180010EEC
0x180010edb  mov     rdx, [rbx+8]
0x180010edf  mov     ecx, [rbx]
0x180010ee1  call    wil_details_RecordCachedUsage
0x180010ee6  add     rbx, 10h
0x180010eea  jmp     short loc_180010ED6
0x180010eec  mov     rax, [rsi+20h]
0x180010ef0  xor     r8d, r8d; unsigned int
0x180010ef3  mov     edx, 0FEh; unsigned int
0x180010ef8  mov     [rsi+28h], rax
0x180010efc  xor     ecx, ecx; this
0x180010efe  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180010f03  mov     rbx, [rsp+28h+arg_0]
0x180010f08  mov     rsi, [rsp+28h+arg_8]
0x180010f0d  add     rsp, 20h
0x180010f11  pop     rdi
0x180010f12  retn
```
