# SpInstanceInit(ulong,_SECPKG_DLL_FUNCTIONS *,void * *)

- ea: `0x180017f50`
- end: `0x180017f8b`
- name: `?SpInstanceInit@@YAJKPEAU_SECPKG_DLL_FUNCTIONS@@PEAPEAX@Z`
- size: `59`
- prototype: `__int64 __fastcall(unsigned int, struct _SECPKG_DLL_FUNCTIONS *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180017800`
- `0x180017f50`
- `0x18001b7e4`

## pseudocode

```c
__int64 __fastcall SpInstanceInit(__int64 a1, struct _SECPKG_DLL_FUNCTIONS *a2, void **a3)
{
  bool v3; // zf
  __int64 result; // rax

  v3 = TSGLobalIsInitialized == 0;
  *a3 = &TSGlobalUserFunctions;
  TSGlobalDllFunctions = a2;
  if ( !v3 )
    return TSContextTrackingInit();
  TSGlobalState = 2;
  result = TSLoadContextTable();
  if ( (int)result >= 0 )
    return TSContextTrackingInit();
  return result;
}

```

## disassembly

```asm
0x180017f50  sub     rsp, 28h
0x180017f54  cmp     cs:?TSGLobalIsInitialized@@3HA, 0; int TSGLobalIsInitialized
0x180017f5b  lea     rax, ?TSGlobalUserFunctions@@3U_SECPKG_USER_FUNCTION_TABLE@@A; _SECPKG_USER_FUNCTION_TABLE TSGlobalUserFunctions
0x180017f62  mov     [r8], rax
0x180017f65  mov     cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA, rdx; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180017f6c  jnz     short loc_180017F81
0x180017f6e  mov     cs:?TSGlobalState@@3W4_TS_STATE@@A, 2; _TS_STATE TSGlobalState
0x180017f78  call    ?TSLoadContextTable@@YAJXZ; TSLoadContextTable(void)
0x180017f7d  test    eax, eax
0x180017f7f  js      short loc_180017F86
0x180017f81  call    ?TSContextTrackingInit@@YAJXZ; TSContextTrackingInit(void)
0x180017f86  add     rsp, 28h
0x180017f8a  retn
```
