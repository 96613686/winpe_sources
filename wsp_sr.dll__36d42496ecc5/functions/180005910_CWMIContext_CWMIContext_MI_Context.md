# CWMIContext::CWMIContext(_MI_Context *)

- ea: `0x180005910`
- end: `0x18000596e`
- name: `??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z`
- size: `94`
- prototype: `CWMIContext *__fastcall(CWMIContext *__hidden this, struct _MI_Context *)`
- caller_count: `30`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005cdc`
- `0x180008fb0`
- `0x18000934c`
- `0x180009844`
- `0x18000999c`
- `0x180009a88`
- `0x180009c48`
- `0x18000bec0`
- `0x18000c2b4`
- `0x18000c8a0`
- `0x18000e5d4`
- `0x18000e874`
- `0x18000ebd4`
- `0x18000fee8`
- `0x18000ffc4`
- `0x1800100d0`
- `0x18001039c`
- `0x18001056c`
- `0x1800107f8`
- `0x180010a68`
- `0x180010c38`
- `0x180011d9c`
- `0x180013970`
- `0x180015200`
- `0x1800152ec`
- `0x180015fdc`
- `0x1800160c8`
- `0x1800161cc`
- `0x180019270`
- `0x180019e60`

## callees

- `0x180005570`
- `0x1800058d4`
- `0x18000673c`

## pseudocode

```c
CWMIContext *__fastcall CWMIContext::CWMIContext(CWMIContext *this, struct _MI_Context *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rcx

  *(_QWORD *)this = &CWMIContext::`vftable';
  std::wstring::wstring((__int64)this + 16);
  *((_QWORD *)this + 7) = v3;
  *((_WORD *)this + 4) = 0;
  v4 = std::_WChar_traits<wchar_t>::length(byte_1800AA410);
  std::wstring::_Assign<wchar_t>((char *)this + 16, v5, v4);
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 8) = 0;
  return this;
}

```

## disassembly

```asm
0x180005910  mov     [rsp+arg_0], rcx
0x180005915  push    rbx
0x180005916  sub     rsp, 20h
0x18000591a  mov     rbx, rcx
0x18000591d  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180005924  mov     [rcx], rax
0x180005927  add     rcx, 10h
0x18000592b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180005930  nop
0x180005931  mov     [rbx+38h], rdx
0x180005935  mov     word ptr [rbx+8], 0
0x18000593b  lea     rcx, byte_1800AA410
0x180005942  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180005947  mov     r8, rax
0x18000594a  mov     rdx, rcx
0x18000594d  lea     rcx, [rbx+10h]
0x180005951  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180005956  mov     dword ptr [rbx+30h], 0
0x18000595d  mov     qword ptr [rbx+40h], 0
0x180005965  mov     rax, rbx
0x180005968  add     rsp, 20h
0x18000596c  pop     rbx
0x18000596d  retn
```
