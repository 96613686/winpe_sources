# RunDLL_UninitActCtx(void *,unsigned __int64)

- ea: `0x140007fd8`
- end: `0x140008002`
- name: `?RunDLL_UninitActCtx@@YAXPEAX_K@Z`
- size: `42`
- prototype: `void __fastcall(HANDLE hActCtx, ULONG_PTR)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140007798`

## callees

- `0x140007fd8`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x140007fed`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x140007fed`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x140007ff6`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x140007ff6`

## pseudocode

```c
void __fastcall RunDLL_UninitActCtx(HANDLE hActCtx, ULONG_PTR a2)
{
  if ( hActCtx != (HANDLE)-1LL )
  {
    if ( a2 )
      DeactivateActCtx(0, a2);
    ReleaseActCtx(hActCtx);
  }
}

```

## disassembly

```asm
0x140007fd8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140007fdc  jz      short locret_140008001
0x140007fde  push    rbx
0x140007fdf  sub     rsp, 20h
0x140007fe3  mov     rbx, rcx
0x140007fe6  test    rdx, rdx
0x140007fe9  jz      short loc_140007FF3
0x140007feb  xor     ecx, ecx; dwFlags
0x140007fed  call    cs:__imp_DeactivateActCtx
0x140007ff3  mov     rcx, rbx; hActCtx
0x140007ff6  call    cs:__imp_ReleaseActCtx
0x140007ffc  add     rsp, 20h
0x140008000  pop     rbx
0x140008001  retn
```
