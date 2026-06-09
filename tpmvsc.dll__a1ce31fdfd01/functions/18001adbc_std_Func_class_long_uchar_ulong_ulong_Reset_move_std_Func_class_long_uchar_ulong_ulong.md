# std::_Func_class<long,uchar *,ulong,ulong *>::_Reset_move(std::_Func_class<long,uchar *,ulong,ulong *> &&)

- ea: `0x18001adbc`
- end: `0x18001ae0e`
- name: `?_Reset_move@?$_Func_class@JPEAEKPEAK@std@@IEAAX$$QEAV12@@Z`
- size: `82`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001789c`
- `0x180017948`

## callees

- `0x18001adbc`
- `0x18001ae40`
- `0x180037010`

## pseudocode

```c
void __fastcall std::_Func_class<long,unsigned char *,unsigned long,unsigned long *>::_Reset_move(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx

  v4 = *(_QWORD *)(a2 + 56);
  if ( v4 )
  {
    if ( v4 == a2 )
    {
      *(_QWORD *)(a1 + 56) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 8LL))(v4, a1);
      std::function<unsigned long (unsigned short const *,unsigned __int64 *,std::vector<unsigned char,wil::secure_allocator<unsigned char>> const &)>::~function<unsigned long (unsigned short const *,unsigned __int64 *,std::vector<unsigned char,wil::secure_allocator<unsigned char>> const &)>(
        a2,
        v5);
    }
    else
    {
      *(_QWORD *)(a1 + 56) = v4;
      *(_QWORD *)(a2 + 56) = 0;
    }
  }
}

```

## disassembly

```asm
0x18001adbc  mov     [rsp+arg_0], rbx
0x18001adc1  push    rdi
0x18001adc2  sub     rsp, 20h
0x18001adc6  mov     rdi, rcx
0x18001adc9  mov     rbx, rdx
0x18001adcc  mov     rcx, [rdx+38h]
0x18001add0  test    rcx, rcx
0x18001add3  jz      short loc_18001AE03
0x18001add5  cmp     rcx, rdx
0x18001add8  jnz     short loc_18001ADF7
0x18001adda  mov     rax, [rcx]
0x18001addd  mov     rdx, rdi
0x18001ade0  mov     rax, [rax+8]
0x18001ade4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ade9  mov     rcx, rbx
0x18001adec  mov     [rdi+38h], rax
0x18001adf0  call    ??1?$function@$$A6AKPEBGPEA_KAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z@std@@QEAA@XZ; std::function<ulong (ushort const *,unsigned __int64 *,std::vector<uchar,wil::secure_allocator<uchar>> const &)>::~function<ulong (ushort const *,unsigned __int64 *,std::vector<uchar,wil::secure_allocator<uchar>> const &)>(void)
0x18001adf5  jmp     short loc_18001AE03
0x18001adf7  mov     [rdi+38h], rcx
0x18001adfb  mov     qword ptr [rdx+38h], 0
0x18001ae03  mov     rbx, [rsp+28h+arg_0]
0x18001ae08  add     rsp, 20h
0x18001ae0c  pop     rdi
0x18001ae0d  retn
```
