# DloadGetSRWLockFunctionPointers(void)

- ea: `0x180046fac`
- end: `0x18004704a`
- name: `?DloadGetSRWLockFunctionPointers@@YAEXZ`
- size: `158`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180046df8`
- `0x180046eec`
- `0x180047290`

## callees

- `0x180046fac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046ff0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004700c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046ff0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004700c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046fd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046fd3`

## string_xrefs

- `0x180046fcc`: `KERNEL32.DLL`

## pseudocode

```c
bool DloadGetSRWLockFunctionPointers(void)
{
  HMODULE ModuleHandleW; // rax
  signed __int64 v1; // rbx
  void (*ProcAddress)(unsigned __int64 *); // rax
  void (*v3)(unsigned __int64 *); // rax
  signed __int64 v4; // rax

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
    if ( v4 || v1 != 1 )
      return v4 != 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180046fac  mov     [rsp+arg_0], rbx
0x180046fb1  push    rdi
0x180046fb2  sub     rsp, 20h
0x180046fb6  mov     rax, cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DloadKernel32
0x180046fbd  mov     edi, 1
0x180046fc2  cmp     rax, rdi
0x180046fc5  jz      short loc_18004703D
0x180046fc7  test    rax, rax
0x180046fca  jnz     short loc_180047038
0x180046fcc  lea     rcx, aKernel32Dll_0; "KERNEL32.DLL"
0x180046fd3  call    cs:__imp_GetModuleHandleW
0x180046fd9  mov     rbx, rax
0x180046fdc  test    rax, rax
0x180046fdf  jnz     short loc_180046FE6
0x180046fe1  mov     rbx, rdi
0x180046fe4  jmp     short loc_18004701E
0x180046fe6  lea     rdx, aAcquiresrwlock; "AcquireSRWLockExclusive"
0x180046fed  mov     rcx, rbx; hModule
0x180046ff0  call    cs:__imp_GetProcAddress
0x180046ff6  test    rax, rax
0x180046ff9  jz      short loc_180046FE1
0x180046ffb  lea     rdx, aReleasesrwlock; "ReleaseSRWLockExclusive"
0x180047002  mov     cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x180047009  mov     rcx, rbx; hModule
0x18004700c  call    cs:__imp_GetProcAddress
0x180047012  test    rax, rax
0x180047015  jz      short loc_180046FE1
0x180047017  mov     cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x18004701e  xor     eax, eax
0x180047020  lock cmpxchg cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * DloadKernel32
0x180047029  jnz     short loc_180047030
0x18004702b  cmp     rbx, rdi
0x18004702e  jz      short loc_18004703D
0x180047030  cmp     rax, rdi
0x180047033  setnz   al
0x180047036  jmp     short loc_18004703F
0x180047038  mov     al, dil
0x18004703b  jmp     short loc_18004703F
0x18004703d  xor     al, al
0x18004703f  mov     rbx, [rsp+28h+arg_0]
0x180047044  add     rsp, 20h
0x180047048  pop     rdi
0x180047049  retn
```
