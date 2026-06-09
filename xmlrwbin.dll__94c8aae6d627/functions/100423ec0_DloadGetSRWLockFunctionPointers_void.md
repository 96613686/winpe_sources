# DloadGetSRWLockFunctionPointers(void)

- ea: `0x100423ec0`
- end: `0x100423f5b`
- name: `?DloadGetSRWLockFunctionPointers@@YAEXZ`
- size: `155`
- prototype: `unsigned __int8(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100423e10`
- `0x100424138`

## callees

- `0x100423ec0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x100423ee7`
- `KERNEL32!GetModuleHandleW` at `0x100423ee7`
- `KERNEL32!GetProcAddress` at `0x100423f04`
- `KERNEL32!GetProcAddress` at `0x100423f20`
- `KERNEL32!GetProcAddress` at `0x100423f04`
- `KERNEL32!GetProcAddress` at `0x100423f20`

## string_xrefs

- `0x100423ee0`: `KERNEL32.DLL`

## pseudocode

```c
bool DloadGetSRWLockFunctionPointers(void)
{
  HMODULE ModuleHandleW; // rax
  signed __int64 v1; // rbx
  void (*ProcAddress)(unsigned __int64 *); // rax
  void (*v3)(unsigned __int64 *); // rax
  signed __int64 v4; // rax
  bool result; // al

  result = 0;
  if ( DloadKernel32 != (HINSTANCE)1 )
  {
    if ( DloadKernel32 )
      return 1;
    ModuleHandleW = GetModuleHandleW(L"KERNEL32.DLL");
    v1 = (signed __int64)ModuleHandleW;
    if ( ModuleHandleW
      && (ProcAddress = (void (*)(unsigned __int64 *))GetProcAddress(ModuleHandleW, "AcquireSRWLockExclusive")) != 0
      && (DloadAcquireSRWLockExclusive = ProcAddress,
          (v3 = (void (*)(unsigned __int64 *))GetProcAddress((HMODULE)v1, "ReleaseSRWLockExclusive")) != 0) )
    {
      DloadReleaseSRWLockExclusive = v3;
    }
    else
    {
      v1 = 1;
    }
    v4 = _InterlockedCompareExchange64((volatile signed __int64 *)&DloadKernel32, v1, 0);
    if ( (v4 || v1 != 1) && v4 != 1 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x100423ec0  mov     [rsp+arg_0], rbx
0x100423ec5  push    rdi
0x100423ec6  sub     rsp, 20h
0x100423eca  mov     rax, cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DloadKernel32
0x100423ed1  mov     edi, 1
0x100423ed6  cmp     rax, rdi
0x100423ed9  jz      short loc_100423F4E
0x100423edb  test    rax, rax
0x100423ede  jnz     short loc_100423F49
0x100423ee0  lea     rcx, aKernel32Dll_0; "KERNEL32.DLL"
0x100423ee7  call    cs:__imp_GetModuleHandleW
0x100423eed  mov     rbx, rax
0x100423ef0  test    rax, rax
0x100423ef3  jnz     short loc_100423EFA
0x100423ef5  mov     rbx, rdi
0x100423ef8  jmp     short loc_100423F32
0x100423efa  lea     rdx, aAcquiresrwlock; "AcquireSRWLockExclusive"
0x100423f01  mov     rcx, rbx; hModule
0x100423f04  call    cs:__imp_GetProcAddress
0x100423f0a  test    rax, rax
0x100423f0d  jz      short loc_100423EF5
0x100423f0f  lea     rdx, aReleasesrwlock; "ReleaseSRWLockExclusive"
0x100423f16  mov     cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x100423f1d  mov     rcx, rbx; hModule
0x100423f20  call    cs:__imp_GetProcAddress
0x100423f26  test    rax, rax
0x100423f29  jz      short loc_100423EF5
0x100423f2b  mov     cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x100423f32  xor     eax, eax
0x100423f34  lock cmpxchg cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * DloadKernel32
0x100423f3d  jnz     short loc_100423F44
0x100423f3f  cmp     rbx, rdi
0x100423f42  jz      short loc_100423F4E
0x100423f44  cmp     rax, rdi
0x100423f47  jz      short loc_100423F4E
0x100423f49  mov     al, dil
0x100423f4c  jmp     short loc_100423F50
0x100423f4e  xor     al, al
0x100423f50  mov     rbx, [rsp+28h+arg_0]
0x100423f55  add     rsp, 20h
0x100423f59  pop     rdi
0x100423f5a  retn
```
