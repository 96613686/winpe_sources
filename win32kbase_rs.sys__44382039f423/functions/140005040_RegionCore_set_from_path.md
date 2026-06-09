# RegionCore_set_from_path

- ea: `0x140005040`
- end: `0x140005096`
- name: `RegionCore_set_from_path`
- size: `86`
- prototype: `_BOOL8 __fastcall(int, __int64, char, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140005040`
- `0x1400101f0`
- `0x140018630`

## string_xrefs

- `0x14000507d`: `assertion failed: !self.ppath.is_null()()`

## pseudocode

```c
_BOOL8 __fastcall RegionCore_set_from_path(int a1, __int64 a2, char a3, int a4)
{
  __int64 v5; // rdx

  v5 = *(_QWORD *)(a2 + 8);
  if ( !v5 )
    RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
      "assertion failed: !self.ppath.is_null()()",
      39,
      &anon_a8fd038c6262e9509fdc3dc075c337f5_10_llvm_2925242432639944874);
  return (unsigned int)RNvNtNtCs7vXzV21FY6F_8gdi_rust6region9from_path20region_from_path_mut(
                         a1,
                         (int)v5 + 24,
                         (unsigned __int8)(a3 & 2) >> 1,
                         a4,
                         1,
                         *(_DWORD *)(a2 + 4)) == 0;
}

```

## disassembly

```asm
0x140005040  sub     rsp, 38h
0x140005044  mov     rax, rdx
0x140005047  mov     rdx, [rdx+8]
0x14000504b  test    rdx, rdx
0x14000504e  jz      short loc_14000507D
0x140005050  add     rdx, 18h
0x140005054  and     r8d, 2
0x140005058  shr     r8d, 1
0x14000505b  mov     eax, [rax+4]
0x14000505e  mov     [rsp+38h+var_10], eax
0x140005062  mov     [rsp+38h+var_18], 1
0x14000506a  call    _RNvNtNtCs7vXzV21FY6F_8gdi_rust6region9from_path20region_from_path_mut
0x14000506f  xor     ecx, ecx
0x140005071  test    eax, eax
0x140005073  setz    cl
0x140005076  mov     eax, ecx
0x140005078  add     rsp, 38h
0x14000507c  retn
0x14000507d  lea     rcx, anon_a8fd038c6262e9509fdc3dc075c337f5_8_llvm_2925242432639944874; "assertion failed: !self.ppath.is_null()"...
0x140005084  lea     r8, anon_a8fd038c6262e9509fdc3dc075c337f5_10_llvm_2925242432639944874
0x14000508b  mov     edx, 27h ; '''
0x140005090  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
```
