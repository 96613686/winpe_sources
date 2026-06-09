# DloadGetSRWLockFunctionPointers(void)

- ea: `0x1800148ec`
- end: `0x18001498a`
- name: `?DloadGetSRWLockFunctionPointers@@YAEXZ`
- size: `158`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014738`
- `0x18001482c`
- `0x180014bd0`

## callees

- `0x1800148ec`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014930`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001494c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014930`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001494c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014913`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014913`

## string_xrefs

- `0x18001490c`: `KERNEL32.DLL`

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
0x1800148ec  mov     [rsp+arg_0], rbx
0x1800148f1  push    rdi
0x1800148f2  sub     rsp, 20h
0x1800148f6  mov     rax, cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DloadKernel32
0x1800148fd  mov     edi, 1
0x180014902  cmp     rax, rdi
0x180014905  jz      short loc_18001497D
0x180014907  test    rax, rax
0x18001490a  jnz     short loc_180014978
0x18001490c  lea     rcx, aKernel32Dll; "KERNEL32.DLL"
0x180014913  call    cs:__imp_GetModuleHandleW
0x180014919  mov     rbx, rax
0x18001491c  test    rax, rax
0x18001491f  jnz     short loc_180014926
0x180014921  mov     rbx, rdi
0x180014924  jmp     short loc_18001495E
0x180014926  lea     rdx, aAcquiresrwlock; "AcquireSRWLockExclusive"
0x18001492d  mov     rcx, rbx; hModule
0x180014930  call    cs:__imp_GetProcAddress
0x180014936  test    rax, rax
0x180014939  jz      short loc_180014921
0x18001493b  lea     rdx, aReleasesrwlock; "ReleaseSRWLockExclusive"
0x180014942  mov     cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x180014949  mov     rcx, rbx; hModule
0x18001494c  call    cs:__imp_GetProcAddress
0x180014952  test    rax, rax
0x180014955  jz      short loc_180014921
0x180014957  mov     cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x18001495e  xor     eax, eax
0x180014960  lock cmpxchg cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * DloadKernel32
0x180014969  jnz     short loc_180014970
0x18001496b  cmp     rbx, rdi
0x18001496e  jz      short loc_18001497D
0x180014970  cmp     rax, rdi
0x180014973  setnz   al
0x180014976  jmp     short loc_18001497F
0x180014978  mov     al, dil
0x18001497b  jmp     short loc_18001497F
0x18001497d  xor     al, al
0x18001497f  mov     rbx, [rsp+28h+arg_0]
0x180014984  add     rsp, 20h
0x180014988  pop     rdi
0x180014989  retn
```
