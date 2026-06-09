# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const *)

- ea: `0x180003810`
- end: `0x180003838`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z`
- size: `40`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `28`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f08`
- `0x180004b80`
- `0x180007c00`
- `0x180009170`
- `0x180009a10`
- `0x18000a938`
- `0x18000b260`
- `0x18000b300`
- `0x18000bae0`
- `0x18000d15c`
- `0x18000d830`
- `0x18000d940`
- `0x18000da2c`
- `0x18000ef44`
- `0x18000fb2c`
- `0x18000fd88`
- `0x18001259c`
- `0x180014310`
- `0x1800155e8`
- `0x180015c30`
- `0x180017510`
- `0x18001764c`
- `0x18001780c`
- `0x1800178f0`
- `0x180018bd4`
- `0x180018cdc`
- `0x18001ab58`
- `0x18001c750`

## callees

- `0x18000669c`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  std::wstring::assign(a1, a2);
  return a1;
}

```

## disassembly

```asm
0x180003810  push    rbx
0x180003812  sub     rsp, 20h
0x180003816  xor     eax, eax
0x180003818  mov     qword ptr [rcx+18h], 7
0x180003820  mov     [rcx+10h], rax
0x180003824  mov     rbx, rcx
0x180003827  mov     [rcx], ax
0x18000382a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000382f  mov     rax, rbx
0x180003832  add     rsp, 20h
0x180003836  pop     rbx
0x180003837  retn
```
