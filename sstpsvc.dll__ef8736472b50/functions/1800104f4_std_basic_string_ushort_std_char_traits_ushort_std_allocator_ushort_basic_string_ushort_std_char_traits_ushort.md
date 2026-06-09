# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800104f4`
- end: `0x180010524`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z`
- size: `48`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180010010`
- `0x18001019c`
- `0x1800101fc`
- `0x180010c08`
- `0x180012d3c`
- `0x1800130d0`
- `0x180013e00`
- `0x1800151e0`

## callees

- `0x180013610`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  std::wstring::assign(a1, a2, 0, -1);
  return a1;
}

```

## disassembly

```asm
0x1800104f4  push    rbx
0x1800104f6  sub     rsp, 20h
0x1800104fa  xor     eax, eax
0x1800104fc  mov     qword ptr [rcx+18h], 7
0x180010504  mov     [rcx+10h], rax
0x180010508  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001050c  xor     r8d, r8d
0x18001050f  mov     [rcx], ax
0x180010512  mov     rbx, rcx
0x180010515  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001051a  mov     rax, rbx
0x18001051d  add     rsp, 20h
0x180010521  pop     rbx
0x180010522  retn
```
