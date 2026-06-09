# CWMIContext::CWMIContext(_MI_Context *)

- ea: `0x180005948`
- end: `0x1800059a7`
- name: `??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z`
- size: `95`
- prototype: `CWMIContext *__fastcall(CWMIContext *__hidden this, struct _MI_Context *)`
- caller_count: `30`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005d1c`
- `0x18000916c`
- `0x18000950c`
- `0x180009994`
- `0x180009aec`
- `0x180009bd8`
- `0x180009d9c`
- `0x18000bf54`
- `0x18000c348`
- `0x18000c8c8`
- `0x18000e5a8`
- `0x18000e848`
- `0x18000eba8`
- `0x18000fec0`
- `0x18000ff9c`
- `0x1800100a8`
- `0x180010354`
- `0x1800104f0`
- `0x18001075c`
- `0x180010998`
- `0x180010b34`
- `0x180011c64`
- `0x180013878`
- `0x1800150b4`
- `0x1800151a0`
- `0x180015e90`
- `0x180015f7c`
- `0x180016084`
- `0x18001929c`
- `0x180019e90`

## callees

- `0x18000559c`
- `0x18000590c`
- `0x180006794`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CWMIContext *__fastcall CWMIContext::CWMIContext(CWMIContext *this, struct _MI_Context *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rcx

  *(_QWORD *)this = &CWMIContext::`vftable';
  std::wstring::wstring((char *)this + 16);
  *((_QWORD *)this + 7) = v3;
  *((_WORD *)this + 4) = 0;
  v4 = std::_WChar_traits<wchar_t>::length(byte_1800AA3F0);
  std::wstring::_Assign<wchar_t>((char *)this + 16, v5, v4);
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 8) = 0;
  return this;
}

```

## disassembly

```asm
0x180005948  mov     [rsp+arg_0], rcx
0x18000594d  push    rbx
0x18000594e  sub     rsp, 20h
0x180005952  mov     rbx, rcx
0x180005955  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000595c  mov     [rcx], rax
0x18000595f  add     rcx, 10h
0x180005963  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180005968  nop
0x180005969  mov     [rbx+38h], rdx
0x18000596d  mov     word ptr [rbx+8], 0
0x180005973  lea     rcx, byte_1800AA3F0
0x18000597a  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18000597f  mov     r8, rax
0x180005982  mov     rdx, rcx
0x180005985  lea     rcx, [rbx+10h]
0x180005989  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000598e  mov     dword ptr [rbx+30h], 0
0x180005995  mov     qword ptr [rbx+40h], 0
0x18000599d  mov     rax, rbx
0x1800059a0  add     rsp, 20h
0x1800059a4  pop     rbx
0x1800059a5  retn
```
