# DllFreeSplStr

- ea: `0x180001bf0`
- end: `0x180001c39`
- name: `DllFreeSplStr`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001bf0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c23`

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
0x180001bf0  sub     rsp, 28h
0x180001bf4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180001bfb  jnz     short loc_180001C1A
0x180001bfd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180001c04  mov     rax, [rax+390h]
0x180001c0b  add     rsp, 28h
0x180001c0f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001c14  add     rsp, 28h
0x180001c18  retn
0x180001c1a  test    rcx, rcx
0x180001c1d  jnz     short loc_180001C23
0x180001c1f  mov     eax, ecx
0x180001c21  jmp     short loc_180001C14
0x180001c23  call    cs:__imp_LocalFree
0x180001c2a  nop     dword ptr [rax+rax+00h]
0x180001c2f  xor     ecx, ecx
0x180001c31  test    rax, rax
0x180001c34  setnz   cl
0x180001c37  jmp     short loc_180001C1F
```
