# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(wchar_t const * const)

- ea: `0x1800058c8`
- end: `0x180005904`
- name: `??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z`
- size: `60`
- prototype: ``
- caller_count: `118`
- callee_count: `2`
- tags: ``

## callers

- `0x180005df8`
- `0x180006360`
- `0x18000784c`
- `0x1800080d4`
- `0x18000916c`
- `0x180009f4c`
- `0x18000a0f4`
- `0x18000a2c4`
- `0x18000a4b0`
- `0x18000a664`
- `0x18000a804`
- `0x18000aa00`
- `0x18000ab90`
- `0x18000ad2c`
- `0x18000aecc`
- `0x18000b030`
- `0x18000b2dc`
- `0x18000b494`
- `0x18000bf54`
- `0x18000c348`
- `0x18000cec8`
- `0x18000ed64`
- `0x18000ef94`
- `0x18000f264`
- `0x18000ff9c`
- `0x18001152c`
- `0x180011d40`
- `0x180012594`
- `0x180013964`
- `0x180013b60`
- `0x180013f60`
- `0x180014450`
- `0x1800151a0`
- `0x180015358`
- `0x180015d2c`
- `0x180016170`
- `0x180016424`
- `0x180016684`
- `0x1800169ec`
- `0x180016e4c`
- `0x180018020`
- `0x180018114`
- `0x180018208`
- `0x18001844c`
- `0x180019388`
- `0x180019584`
- `0x180019904`
- `0x180019cf0`
- `0x18001a0fc`
- `0x18001a758`

## callees

- `0x180005604`
- `0x180006794`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rdx

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v3 = std::_WChar_traits<wchar_t>::length(a2);
  std::wstring::_Construct<1,wchar_t const *>(a1, v4, v3);
  return a1;
}

```

## disassembly

```asm
0x1800058c8  push    rbx
0x1800058ca  sub     rsp, 20h
0x1800058ce  xorps   xmm0, xmm0
0x1800058d1  mov     rbx, rcx
0x1800058d4  movups  xmmword ptr [rcx], xmm0
0x1800058d7  mov     qword ptr [rcx+10h], 0
0x1800058df  mov     qword ptr [rcx+18h], 0
0x1800058e7  mov     rcx, rdx
0x1800058ea  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800058ef  mov     r8, rax
0x1800058f2  mov     rcx, rbx
0x1800058f5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800058fa  mov     rax, rbx
0x1800058fd  add     rsp, 20h
0x180005901  pop     rbx
0x180005902  retn
```
