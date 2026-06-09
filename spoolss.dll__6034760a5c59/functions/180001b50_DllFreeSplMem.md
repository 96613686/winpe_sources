# DllFreeSplMem

- ea: `0x180001b50`
- end: `0x180001b8b`
- name: `DllFreeSplMem`
- size: `59`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800048b4`
- `0x180004aa8`
- `0x1800111f0`
- `0x1800114cc`
- `0x180011d48`
- `0x180012044`
- `0x180012500`
- `0x180014360`
- `0x180014854`

## callees

- `0x180001b50`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001b79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001b79`

## pseudocode

```c
__int64 __fastcall DllFreeSplMem(void *a1)
{
  if ( g_bSandbox )
    return LocalFree(a1) != 0;
  else
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 109))();
}

```

## disassembly

```asm
0x180001b50  sub     rsp, 28h
0x180001b54  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180001b5b  jnz     short loc_180001B79
0x180001b5d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180001b64  mov     rax, [rax+368h]
0x180001b6b  add     rsp, 28h
0x180001b6f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001b74  add     rsp, 28h
0x180001b78  retn
0x180001b79  call    cs:__imp_LocalFree
0x180001b7f  xor     ecx, ecx
0x180001b81  test    rax, rax
0x180001b84  setnz   cl
0x180001b87  mov     eax, ecx
0x180001b89  jmp     short loc_180001B74
```
