# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000a394`
- end: `0x18000a3f7`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `99`
- prototype: `void __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009fb8`

## callees

- `0x18000a394`
- `0x18000b9d4`
- `0x18000cb40`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned int *v4; // rdi
  unsigned int *v6; // rbx
  const char *v7; // [rsp+20h] [rbp-8h]

  v4 = *(unsigned int **)(a1 + 40);
  v6 = *(unsigned int **)(a1 + 32);
  if ( (unsigned __int64)((char *)v4 - (char *)v6) >= 0x10 )
  {
    while ( v6 != v4 )
    {
      wil_details_RecordCachedUsage(*v6, *((_QWORD *)v6 + 1));
      v6 += 4;
    }
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32);
    wil::details::WilApi_RecordFeatureUsage(0, 0xFEu, 0, a4, v7);
  }
}

```

## disassembly

```asm
0x18000a394  mov     [rsp+arg_0], rbx
0x18000a399  mov     [rsp+arg_8], rsi
0x18000a39e  push    rdi; char *
0x18000a39f  sub     rsp, 20h
0x18000a3a3  mov     rdi, [rcx+28h]
0x18000a3a7  mov     rsi, rcx
0x18000a3aa  mov     rbx, [rcx+20h]
0x18000a3ae  mov     rax, rdi
0x18000a3b1  sub     rax, rbx
0x18000a3b4  cmp     rax, 10h
0x18000a3b8  jb      short loc_18000A3E7
0x18000a3ba  cmp     rbx, rdi
0x18000a3bd  jz      short loc_18000A3D0
0x18000a3bf  mov     rdx, [rbx+8]
0x18000a3c3  mov     ecx, [rbx]
0x18000a3c5  call    wil_details_RecordCachedUsage
0x18000a3ca  add     rbx, 10h
0x18000a3ce  jmp     short loc_18000A3BA
0x18000a3d0  mov     rax, [rsi+20h]
0x18000a3d4  xor     r8d, r8d; unsigned int
0x18000a3d7  mov     edx, 0FEh; unsigned int
0x18000a3dc  mov     [rsi+28h], rax
0x18000a3e0  xor     ecx, ecx; this
0x18000a3e2  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000a3e7  mov     rbx, [rsp+28h+arg_0]
0x18000a3ec  mov     rsi, [rsp+28h+arg_8]
0x18000a3f1  add     rsp, 20h
0x18000a3f5  pop     rdi
0x18000a3f6  retn
```
