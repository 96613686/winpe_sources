# DloadGetSRWLockFunctionPointers(void)

- ea: `0x1004396f8`
- end: `0x100439793`
- name: `?DloadGetSRWLockFunctionPointers@@YAEXZ`
- size: `155`
- prototype: `unsigned __int8(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100439648`
- `0x100439970`

## callees

- `0x1004396f8`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x10043971f`
- `KERNEL32!GetModuleHandleW` at `0x10043971f`
- `KERNEL32!GetProcAddress` at `0x10043973c`
- `KERNEL32!GetProcAddress` at `0x100439758`
- `KERNEL32!GetProcAddress` at `0x10043973c`
- `KERNEL32!GetProcAddress` at `0x100439758`

## string_xrefs

- `0x100439718`: `KERNEL32.DLL`

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
0x1004396f8  mov     [rsp+arg_0], rbx
0x1004396fd  push    rdi
0x1004396fe  sub     rsp, 20h
0x100439702  mov     rax, cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DloadKernel32
0x100439709  mov     edi, 1
0x10043970e  cmp     rax, rdi
0x100439711  jz      short loc_100439786
0x100439713  test    rax, rax
0x100439716  jnz     short loc_100439781
0x100439718  lea     rcx, aKernel32Dll_0; "KERNEL32.DLL"
0x10043971f  call    cs:__imp_GetModuleHandleW
0x100439725  mov     rbx, rax
0x100439728  test    rax, rax
0x10043972b  jnz     short loc_100439732
0x10043972d  mov     rbx, rdi
0x100439730  jmp     short loc_10043976A
0x100439732  lea     rdx, aAcquiresrwlock; "AcquireSRWLockExclusive"
0x100439739  mov     rcx, rbx; hModule
0x10043973c  call    cs:__imp_GetProcAddress
0x100439742  test    rax, rax
0x100439745  jz      short loc_10043972D
0x100439747  lea     rdx, aReleasesrwlock; "ReleaseSRWLockExclusive"
0x10043974e  mov     cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x100439755  mov     rcx, rbx; hModule
0x100439758  call    cs:__imp_GetProcAddress
0x10043975e  test    rax, rax
0x100439761  jz      short loc_10043972D
0x100439763  mov     cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x10043976a  xor     eax, eax
0x10043976c  lock cmpxchg cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * DloadKernel32
0x100439775  jnz     short loc_10043977C
0x100439777  cmp     rbx, rdi
0x10043977a  jz      short loc_100439786
0x10043977c  cmp     rax, rdi
0x10043977f  jz      short loc_100439786
0x100439781  mov     al, dil
0x100439784  jmp     short loc_100439788
0x100439786  xor     al, al
0x100439788  mov     rbx, [rsp+28h+arg_0]
0x10043978d  add     rsp, 20h
0x100439791  pop     rdi
0x100439792  retn
```
