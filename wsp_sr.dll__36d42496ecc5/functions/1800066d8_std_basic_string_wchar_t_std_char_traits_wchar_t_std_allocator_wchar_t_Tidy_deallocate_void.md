# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Tidy_deallocate(void)

- ea: `0x1800066d8`
- end: `0x180006712`
- name: `?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ`
- size: `58`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `198`
- callee_count: `2`
- tags: ``

## callers

- `0x18000574c`
- `0x180005a24`
- `0x180005a5c`
- `0x180005ad0`
- `0x180005cdc`
- `0x180005db8`
- `0x180006004`
- `0x180006320`
- `0x180008804`
- `0x180008948`
- `0x180008a04`
- `0x180008fb0`
- `0x18000934c`
- `0x180009844`
- `0x18000999c`
- `0x180009a88`
- `0x180009c48`
- `0x180009df4`
- `0x180009f9c`
- `0x18000a16c`
- `0x18000a354`
- `0x18000a508`
- `0x18000a6a8`
- `0x18000a89c`
- `0x18000aa28`
- `0x18000abc4`
- `0x18000ad64`
- `0x18000aec8`
- `0x18000b174`
- `0x18000b328`
- `0x18000b48c`
- `0x18000b98c`
- `0x18000bec0`
- `0x18000c0a8`
- `0x18000c2b4`
- `0x18000c8a0`
- `0x18000cfa4`
- `0x18000dce8`
- `0x18000dda0`
- `0x18000e5d4`
- `0x18000e874`
- `0x18000ebd4`
- `0x18000ed90`
- `0x18000efc0`
- `0x18000f290`
- `0x18000f440`
- `0x18000f6d4`
- `0x18000fae4`
- `0x18000fc98`
- `0x18000fee8`

## callees

- `0x18000570c`
- `0x1800066d8`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy_deallocate(__int64 a1)
{
  unsigned __int64 v1; // rdx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 > 7 )
    std::_Deallocate<16>(*(void **)a1, 2 * v1 + 2);
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800066d8  push    rbx
0x1800066da  sub     rsp, 20h
0x1800066de  mov     rdx, [rcx+18h]
0x1800066e2  mov     rbx, rcx
0x1800066e5  cmp     rdx, 7
0x1800066e9  jbe     short loc_1800066FB
0x1800066eb  mov     rcx, [rcx]
0x1800066ee  lea     rdx, ds:2[rdx*2]
0x1800066f6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800066fb  xor     eax, eax
0x1800066fd  mov     qword ptr [rbx+18h], 7
0x180006705  mov     [rbx+10h], rax
0x180006709  mov     [rbx], ax
0x18000670c  add     rsp, 20h
0x180006710  pop     rbx
0x180006711  retn
```
