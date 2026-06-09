# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180005884`
- end: `0x1800058c0`
- name: `??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z`
- size: `60`
- prototype: ``
- caller_count: `25`
- callee_count: `2`
- tags: ``

## callers

- `0x180005c70`
- `0x18000795c`
- `0x18000950c`
- `0x180009994`
- `0x18000b030`
- `0x18000c13c`
- `0x18000dbe4`
- `0x18000e5a8`
- `0x18000e848`
- `0x18001152c`
- `0x1800135d0`
- `0x180013b60`
- `0x180015b70`
- `0x180016170`
- `0x180019904`
- `0x18001aed0`
- `0x18001babc`
- `0x18001bcbc`
- `0x180020138`
- `0x180020d68`
- `0x180021f64`
- `0x180022ea4`
- `0x1800241b0`
- `0x180025ef0`
- `0x1800288bc`

## callees

- `0x1800056ac`
- `0x180005884`

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
0x180005884  push    rbx
0x180005886  sub     rsp, 20h
0x18000588a  xorps   xmm0, xmm0
0x18000588d  mov     rbx, rcx
0x180005890  movups  xmmword ptr [rcx], xmm0
0x180005893  mov     qword ptr [rcx+10h], 0
0x18000589b  mov     qword ptr [rcx+18h], 0
0x1800058a3  cmp     qword ptr [rdx+18h], 7
0x1800058a8  mov     r8, [rdx+10h]
0x1800058ac  jbe     short loc_1800058B1
0x1800058ae  mov     rdx, [rdx]
0x1800058b1  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800058b6  mov     rax, rbx
0x1800058b9  add     rsp, 20h
0x1800058bd  pop     rbx
0x1800058be  retn
```
