# p9fs::Task<util::BasicExpected<uint,long>>::~Task<util::BasicExpected<uint,long>>(void)

- ea: `0x180005fc4`
- end: `0x180006016`
- name: `??1?$Task@V?$BasicExpected@IJ@util@@@p9fs@@QEAA@XZ`
- size: `82`
- prototype: ``
- caller_count: `30`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18002f567`
- `0x18002f61b`
- `0x18002f6d0`
- `0x18002f8a5`
- `0x18002f9b1`
- `0x18002fb80`
- `0x18002fca8`
- `0x1800300fe`
- `0x18003024d`
- `0x180030311`
- `0x180030714`
- `0x1800308fd`
- `0x18003092e`
- `0x18003095f`
- `0x180030990`
- `0x180030d2d`
- `0x180030f26`
- `0x18003101e`
- `0x180031172`
- `0x18003119d`
- `0x18003123d`
- `0x180031424`
- `0x180031554`
- `0x1800315b6`
- `0x180031887`
- `0x180031b44`
- `0x1800321cc`
- `0x180032439`
- `0x1800333cc`
- `0x180033632`

## callees

- `0x180005fc4`
- `0x1800074e0`
- `0x180034010`

## string_xrefs

- `0x180006004`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
__int64 __fastcall p9fs::Task<util::BasicExpected<unsigned int,long>>::~Task<util::BasicExpected<unsigned int,long>>(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = *a1;
  if ( *a1 )
  {
    if ( *(_WORD *)(result + 8) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
        a4);
    *(_QWORD *)(result + 8) |= 1uLL;
    result = (*(__int64 (__fastcall **)(__int64))result)(*a1);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005fc4  mov     [rsp+arg_0], rbx
0x180005fc9  push    rdi
0x180005fca  sub     rsp, 20h
0x180005fce  mov     rax, [rcx]
0x180005fd1  xor     edi, edi
0x180005fd3  mov     rbx, rcx
0x180005fd6  test    rax, rax
0x180005fd9  jz      short loc_180005FF4
0x180005fdb  cmp     [rax+8], di
0x180005fdf  jnz     short loc_180005FFF
0x180005fe1  or      qword ptr [rax+8], 1
0x180005fe6  mov     rcx, [rcx]
0x180005fe9  mov     rax, [rax]
0x180005fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ff1  mov     [rbx], rdi
0x180005ff4  mov     rbx, [rsp+28h+arg_0]
0x180005ff9  add     rsp, 20h
0x180005ffd  pop     rdi
0x180005ffe  retn
0x180005fff  mov     rcx, [rsp+28h]; this
0x180006004  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18000600b  mov     edx, 34h ; '4'; void *
0x180006010  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
