# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(wchar_t const * const)

- ea: `0x180005890`
- end: `0x1800058cb`
- name: `??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z`
- size: `59`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `118`
- callee_count: `2`
- tags: ``

## callers

- `0x180005db8`
- `0x180006320`
- `0x180007770`
- `0x180007f98`
- `0x180008fb0`
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
- `0x18000bec0`
- `0x18000c2b4`
- `0x18000cfa4`
- `0x18000ed90`
- `0x18000efc0`
- `0x18000f290`
- `0x18000ffc4`
- `0x180011670`
- `0x180011e78`
- `0x1800126cc`
- `0x180013a5c`
- `0x180013c50`
- `0x180014050`
- `0x180014540`
- `0x1800152ec`
- `0x1800154a4`
- `0x180015e78`
- `0x1800162b8`
- `0x180016568`
- `0x1800167c8`
- `0x180016b28`
- `0x180016f84`
- `0x1800181a0`
- `0x180018294`
- `0x180018388`
- `0x18001859c`
- `0x18001935c`
- `0x180019550`
- `0x1800198cc`
- `0x180019cb8`
- `0x18001a0c4`
- `0x18001a748`

## callees

- `0x1800055d8`
- `0x18000673c`

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
0x180005890  push    rbx
0x180005892  sub     rsp, 20h
0x180005896  xorps   xmm0, xmm0
0x180005899  mov     rbx, rcx
0x18000589c  movups  xmmword ptr [rcx], xmm0
0x18000589f  mov     qword ptr [rcx+10h], 0
0x1800058a7  mov     qword ptr [rcx+18h], 0
0x1800058af  mov     rcx, rdx
0x1800058b2  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800058b7  mov     r8, rax
0x1800058ba  mov     rcx, rbx
0x1800058bd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800058c2  mov     rax, rbx
0x1800058c5  add     rsp, 20h
0x1800058c9  pop     rbx
0x1800058ca  retn
```
