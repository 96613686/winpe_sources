# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)

- ea: `0x18000669c`
- end: `0x1800066bd`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z`
- size: `33`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `39`
- callee_count: `2`
- tags: ``

## callers

- `0x180003810`
- `0x180004434`
- `0x1800052cc`
- `0x180005ad0`
- `0x180007844`
- `0x180008828`
- `0x180009170`
- `0x180009a10`
- `0x18000bbec`
- `0x18000dc4c`
- `0x18000e01c`
- `0x18000f1f8`
- `0x1800103b8`
- `0x1800128c0`
- `0x180012f20`
- `0x1800145cc`
- `0x18001483c`
- `0x180015134`
- `0x180015dd4`
- `0x1800165c0`
- `0x18001ab58`
- `0x18001bdac`
- `0x18001c750`
- `0x18001dd2c`
- `0x18001dd6c`
- `0x18001ddac`
- `0x18001de2c`
- `0x18001dec4`
- `0x18001df04`
- `0x18001e08c`
- `0x18001e0cc`
- `0x18001e10c`
- `0x18001e14c`
- `0x18001e18c`
- `0x18001e1cc`
- `0x18001e20c`
- `0x18001e808`
- `0x18001ebc4`
- `0x180021149`

## callees

- `0x1800066c4`
- `0x180006854`

## pseudocode

```c
__int64 __fastcall std::wstring::assign(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 v4; // r10

  v2 = std::char_traits<unsigned short>::length(a2);
  return std::wstring::assign(v4, v3, v2);
}

```

## disassembly

```asm
0x18000669c  sub     rsp, 28h
0x1800066a0  mov     r10, rcx
0x1800066a3  mov     rcx, rdx
0x1800066a6  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1800066ab  mov     rdx, rcx
0x1800066ae  mov     r8, rax
0x1800066b1  mov     rcx, r10
0x1800066b4  add     rsp, 28h
0x1800066b8  jmp     ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
```
