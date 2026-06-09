# TSFree(void *)

- ea: `0x180005ed0`
- end: `0x180005f09`
- name: `?TSFree@@YAXPEAX@Z`
- size: `57`
- prototype: `void __fastcall(void *)`
- caller_count: `45`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001160`
- `0x1800029b0`
- `0x180003340`
- `0x180004170`
- `0x180004460`
- `0x1800059a8`
- `0x180006650`
- `0x180007fd0`
- `0x180008810`
- `0x180008840`
- `0x1800099a8`
- `0x180009b2c`
- `0x180009bd0`
- `0x180009f18`
- `0x180012af0`
- `0x180013200`
- `0x180013468`
- `0x1800139d0`
- `0x180014100`
- `0x1800141bc`
- `0x18001434c`
- `0x18001449c`
- `0x180015304`
- `0x180015bac`
- `0x180015f00`
- `0x1800168c4`
- `0x180016b38`
- `0x180016eec`
- `0x180017314`
- `0x180017fa0`
- `0x1800186b0`
- `0x180018898`
- `0x180018e30`
- `0x1800190bc`
- `0x180019460`
- `0x180019958`
- `0x180019e1c`
- `0x180019fac`
- `0x18001a0d0`
- `0x18001a3e0`
- `0x18001a700`
- `0x18001a820`
- `0x18001a914`
- `0x18001aa90`
- `0x18001acf0`

## callees

- `0x180005ed0`
- `0x18001d010`

## pseudocode

```c
void __fastcall TSFree(void *a1)
{
  void (*FreePrivateHeap)(void); // rax

  if ( a1 )
  {
    if ( TSGlobalState == 1 )
      FreePrivateHeap = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
    else
      FreePrivateHeap = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
    FreePrivateHeap();
  }
}

```

## disassembly

```asm
0x180005ed0  sub     rsp, 28h
0x180005ed4  test    rcx, rcx
0x180005ed7  jnz     short loc_180005EDE
0x180005ed9  add     rsp, 28h
0x180005edd  retn
0x180005ede  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180005ee5  jnz     short loc_180005EFC
0x180005ee7  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180005eee  mov     rax, [rax+188h]
0x180005ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005efa  jmp     short loc_180005ED9
0x180005efc  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180005f03  mov     rax, [rax+8]
0x180005f07  jmp     short loc_180005EF5
```
