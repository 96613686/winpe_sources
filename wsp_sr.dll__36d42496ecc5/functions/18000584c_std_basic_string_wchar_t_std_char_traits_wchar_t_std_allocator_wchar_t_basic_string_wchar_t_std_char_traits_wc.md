# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18000584c`
- end: `0x180005887`
- name: `??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z`
- size: `59`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `25`
- callee_count: `2`
- tags: ``

## callers

- `0x180005c30`
- `0x18000787c`
- `0x18000934c`
- `0x180009844`
- `0x18000aec8`
- `0x18000c0a8`
- `0x18000dce8`
- `0x18000e5d4`
- `0x18000e874`
- `0x180011670`
- `0x1800136cc`
- `0x180013c50`
- `0x180015cc0`
- `0x1800162b8`
- `0x1800198cc`
- `0x18001aeb8`
- `0x18001ba4c`
- `0x18001bc4c`
- `0x18001fff4`
- `0x180020c04`
- `0x180021dbc`
- `0x180022ce4`
- `0x180023ee0`
- `0x180025bc8`
- `0x180028474`

## callees

- `0x180005680`
- `0x18000584c`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, _QWORD *a2)
{
  __int64 v3; // r8

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v3 = a2[2];
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::wstring::_Construct<2,wchar_t const *>(a1, a2, v3);
  return a1;
}

```

## disassembly

```asm
0x18000584c  push    rbx
0x18000584e  sub     rsp, 20h
0x180005852  xorps   xmm0, xmm0
0x180005855  mov     rbx, rcx
0x180005858  movups  xmmword ptr [rcx], xmm0
0x18000585b  mov     qword ptr [rcx+10h], 0
0x180005863  mov     qword ptr [rcx+18h], 0
0x18000586b  cmp     qword ptr [rdx+18h], 7
0x180005870  mov     r8, [rdx+10h]
0x180005874  jbe     short loc_180005879
0x180005876  mov     rdx, [rdx]
0x180005879  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000587e  mov     rax, rbx
0x180005881  add     rsp, 20h
0x180005885  pop     rbx
0x180005886  retn
```
