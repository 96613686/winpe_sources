# RegionCore_iCombine

- ea: `0x140004da0`
- end: `0x140004e16`
- name: `RegionCore_iCombine`
- size: `118`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140004da0`
- `0x140005340`
- `0x14000ca10`
- `0x14000fdc0`

## pseudocode

```c
__int64 __fastcall RegionCore_iCombine(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned int v8; // edx
  char v9; // cl
  __int64 result; // rax

  if ( !*(_QWORD *)(a2 + 16) )
  {
    RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback();
    if ( (unsigned int)RNvNtCs7vXzV21FY6F_8gdi_rust6region26try_repair_zero_sized_scan(a2, a1) )
      return 0;
  }
  if ( !*(_QWORD *)(a3 + 16) )
  {
    RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback();
    if ( (unsigned int)RNvNtCs7vXzV21FY6F_8gdi_rust6region26try_repair_zero_sized_scan(a3, a1) )
      return 0;
  }
  v9 = RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore7combine(a1, a2, a3, a4);
  result = 0;
  if ( (v9 & 1) == 0 )
    return v8;
  return result;
}

```

## disassembly

```asm
0x140004da0  push    r14
0x140004da2  push    rsi
0x140004da3  push    rdi
0x140004da4  push    rbx
0x140004da5  sub     rsp, 28h
0x140004da9  mov     esi, r9d
0x140004dac  mov     rdi, r8
0x140004daf  mov     rbx, rdx
0x140004db2  mov     r14, rcx
0x140004db5  cmp     qword ptr [rdx+10h], 0
0x140004dba  jz      short loc_140004DE0
0x140004dbc  cmp     qword ptr [rdi+10h], 0
0x140004dc1  jz      short loc_140004DF6
0x140004dc3  mov     rcx, r14
0x140004dc6  mov     rdx, rbx
0x140004dc9  mov     r8, rdi
0x140004dcc  mov     r9d, esi
0x140004dcf  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore7combine
0x140004dd4  mov     ecx, eax
0x140004dd6  xor     eax, eax
0x140004dd8  test    cl, 1
0x140004ddb  cmovz   eax, edx
0x140004dde  jmp     short loc_140004E0C
0x140004de0  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback
0x140004de5  mov     rcx, rbx
0x140004de8  mov     rdx, r14
0x140004deb  call    _RNvNtCs7vXzV21FY6F_8gdi_rust6region26try_repair_zero_sized_scan
0x140004df0  test    eax, eax
0x140004df2  jnz     short loc_140004E0A
0x140004df4  jmp     short loc_140004DBC
0x140004df6  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback
0x140004dfb  mov     rcx, rdi
0x140004dfe  mov     rdx, r14
0x140004e01  call    _RNvNtCs7vXzV21FY6F_8gdi_rust6region26try_repair_zero_sized_scan
0x140004e06  test    eax, eax
0x140004e08  jz      short loc_140004DC3
0x140004e0a  xor     eax, eax
0x140004e0c  add     rsp, 28h
0x140004e10  pop     rbx
0x140004e11  pop     rdi
0x140004e12  pop     rsi
0x140004e13  pop     r14
0x140004e15  retn
```
