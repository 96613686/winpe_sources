# TSAllocate(unsigned __int64)

- ea: `0x1800032c0`
- end: `0x180003335`
- name: `?TSAllocate@@YAPEAX_K@Z`
- size: `117`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `44`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800029b0`
- `0x180004460`
- `0x1800059a8`
- `0x180006650`
- `0x180007fd0`
- `0x180008840`
- `0x1800099a8`
- `0x180009bd0`
- `0x180009cac`
- `0x180009db4`
- `0x180009f18`
- `0x18000a480`
- `0x180012930`
- `0x180012af0`
- `0x180013200`
- `0x1800139d0`
- `0x180013f70`
- `0x1800141bc`
- `0x18001449c`
- `0x180014a84`
- `0x180014e90`
- `0x180015304`
- `0x180015bac`
- `0x180015f00`
- `0x1800168c4`
- `0x180016b38`
- `0x180017314`
- `0x180017fa0`
- `0x1800182f0`
- `0x1800186b0`
- `0x180018898`
- `0x180018b28`
- `0x180018b8c`
- `0x180018e20`
- `0x180018e3c`
- `0x1800190bc`
- `0x180019958`
- `0x180019ef0`
- `0x180019fac`
- `0x18001a0c0`
- `0x18001a700`
- `0x18001acf0`
- `0x18001b1f0`
- `0x18001b408`

## callees

- `0x1800032c0`
- `0x18000c1a4`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall TSAllocate(size_t Size)
{
  void *v2; // rdi
  void *v4; // rax

  if ( Size > 0xFFFFFFFF )
    return 0;
  if ( TSGlobalState == 1 )
    return ((__int64 (__fastcall *)(_QWORD))TSGlobalLsaFunctions->AllocatePrivateHeap)((unsigned int)Size);
  v4 = (void *)((__int64 (*)(void))TSGlobalDllFunctions->AllocateHeap)();
  v2 = v4;
  if ( v4 )
    memset_0(v4, 0, Size);
  return (__int64)v2;
}

```

## disassembly

```asm
0x1800032c0  push    rbx
0x1800032c2  sub     rsp, 20h
0x1800032c6  mov     eax, 0FFFFFFFFh
0x1800032cb  mov     rbx, rcx
0x1800032ce  cmp     rcx, rax
0x1800032d1  ja      short loc_180003307
0x1800032d3  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x1800032da  mov     [rsp+28h+arg_0], rdi
0x1800032df  jnz     short loc_18000330F
0x1800032e1  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800032e8  mov     ecx, ebx
0x1800032ea  mov     rax, [rax+180h]
0x1800032f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032f6  mov     rdi, rax
0x1800032f9  mov     rax, rdi
0x1800032fc  mov     rdi, [rsp+28h+arg_0]
0x180003301  add     rsp, 20h
0x180003305  pop     rbx
0x180003306  retn
0x180003307  xor     eax, eax
0x180003309  add     rsp, 20h
0x18000330d  pop     rbx
0x18000330e  retn
0x18000330f  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180003316  mov     rax, [rax]
0x180003319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000331e  mov     rdi, rax
0x180003321  test    rax, rax
0x180003324  jz      short loc_1800032F9
0x180003326  mov     r8, rbx; Size
0x180003329  xor     edx, edx; Val
0x18000332b  mov     rcx, rax; void *
0x18000332e  call    memset_0
0x180003333  jmp     short loc_1800032F9
```
