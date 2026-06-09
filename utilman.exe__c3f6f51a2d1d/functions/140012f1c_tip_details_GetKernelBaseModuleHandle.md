# tip_details_GetKernelBaseModuleHandle

- ea: `0x140012f1c`
- end: `0x140012f4c`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `48`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400121cc`
- `0x140012be8`
- `0x140012c3c`
- `0x140012cb4`
- `0x140012d08`
- `0x140023104`

## callees

- `0x140012f1c`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140012f33`
- `KERNEL32!GetModuleHandleW` at `0x140012f33`

## string_xrefs

- `0x140012f2c`: `kernelbase.dll`

## pseudocode

```c
HMODULE tip_details_GetKernelBaseModuleHandle()
{
  HMODULE result; // rax

  result = (HMODULE)g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    result = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = (__int64)result;
  }
  return result;
}

```

## disassembly

```asm
0x140012f1c  sub     rsp, 28h
0x140012f20  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x140012f27  test    rax, rax
0x140012f2a  jnz     short loc_140012F46
0x140012f2c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140012f33  call    cs:__imp_GetModuleHandleW
0x140012f3a  nop     dword ptr [rax+rax+00h]
0x140012f3f  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x140012f46  add     rsp, 28h
0x140012f4a  retn
```
