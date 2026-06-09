# DllFreeSplMem

- ea: `0x180001b60`
- end: `0x180001ba2`
- name: `DllFreeSplMem`
- size: `66`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004bf4`
- `0x180004df4`
- `0x18001285c`
- `0x180012bd0`
- `0x18001346c`
- `0x1800137a4`
- `0x180013c20`
- `0x180015c64`
- `0x1800161e8`

## callees

- `0x180001b60`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001b8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001b8a`

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
0x180001b60  sub     rsp, 28h
0x180001b64  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180001b6b  jnz     short loc_180001B8A
0x180001b6d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180001b74  mov     rax, [rax+368h]
0x180001b7b  add     rsp, 28h
0x180001b7f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001b84  add     rsp, 28h
0x180001b88  retn
0x180001b8a  call    cs:__imp_LocalFree
0x180001b91  nop     dword ptr [rax+rax+00h]
0x180001b96  xor     ecx, ecx
0x180001b98  test    rax, rax
0x180001b9b  setnz   cl
0x180001b9e  mov     eax, ecx
0x180001ba0  jmp     short loc_180001B84
```
