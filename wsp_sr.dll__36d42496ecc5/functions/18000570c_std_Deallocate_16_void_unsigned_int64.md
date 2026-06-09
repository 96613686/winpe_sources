# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x18000570c`
- end: `0x180005744`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `56`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `61`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800057ac`
- `0x180006688`
- `0x1800066d8`
- `0x180007988`
- `0x180007de8`
- `0x180008814`
- `0x180008878`
- `0x1800088a0`
- `0x18000d3ec`
- `0x18000d85c`
- `0x18000d920`
- `0x18000d940`
- `0x18000db70`
- `0x18000dc04`
- `0x18000de40`
- `0x1800100d0`
- `0x18001039c`
- `0x18001056c`
- `0x1800107f8`
- `0x180010a68`
- `0x180010c38`
- `0x180010ec0`
- `0x1800135d4`
- `0x180015be0`
- `0x180015d80`
- `0x180017190`
- `0x180017248`
- `0x180017380`
- `0x1800174b0`
- `0x180017798`
- `0x180017974`
- `0x180017998`
- `0x180017a08`
- `0x180017a4c`
- `0x180017b50`
- `0x180017b74`
- `0x180018f54`
- `0x180019174`
- `0x18001a4cc`
- `0x18001a58c`
- `0x18001cecc`
- `0x18001d268`
- `0x18001d2cc`
- `0x18001d308`
- `0x18001fcc0`
- `0x18001fce0`
- `0x180020684`
- `0x180020fa0`
- `0x18002186c`
- `0x180021b90`

## callees

- `0x180002510`
- `0x18000570c`
- `0x180006590`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(void *a1, unsigned __int64 a2)
{
  void *v2; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int64 v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = a2;
  v2 = a1;
  if ( a2 >= 0x1000 )
  {
    std::_Adjust_manually_vector_aligned(&v2, &v3);
    a2 = v3;
    a1 = v2;
  }
  operator delete(a1, a2);
}

```

## disassembly

```asm
0x18000570c  mov     rax, rsp
0x18000570f  mov     [rax+10h], rdx
0x180005713  mov     [rax+8], rcx
0x180005717  sub     rsp, 28h
0x18000571b  cmp     rdx, 1000h
0x180005722  jb      short loc_18000573B
0x180005724  lea     rdx, [rax+10h]; unsigned __int64 *
0x180005728  lea     rcx, [rax+8]; void **
0x18000572c  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180005731  mov     rdx, [rsp+28h+arg_8]; unsigned __int64
0x180005736  mov     rcx, [rsp+28h+arg_0]; void *
0x18000573b  add     rsp, 28h
0x18000573f  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
