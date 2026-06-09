# DllFreeSplStr

- ea: `0x180001be0`
- end: `0x180001c22`
- name: `DllFreeSplStr`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001be0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c12`

## pseudocode

```c
__int64 __fastcall DllFreeSplStr(void *a1)
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 114))();
  if ( a1 )
    LODWORD(a1) = LocalFree(a1) != 0;
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180001be0  sub     rsp, 28h
0x180001be4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180001beb  jnz     short loc_180001C09
0x180001bed  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180001bf4  mov     rax, [rax+390h]
0x180001bfb  add     rsp, 28h
0x180001bff  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001c04  add     rsp, 28h
0x180001c08  retn
0x180001c09  test    rcx, rcx
0x180001c0c  jnz     short loc_180001C12
0x180001c0e  mov     eax, ecx
0x180001c10  jmp     short loc_180001C04
0x180001c12  call    cs:__imp_LocalFree
0x180001c18  xor     ecx, ecx
0x180001c1a  test    rax, rax
0x180001c1d  setnz   cl
0x180001c20  jmp     short loc_180001C0E
```
