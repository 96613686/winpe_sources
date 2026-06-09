# SHActivateContext

- ea: `0x180004b44`
- end: `0x180004bad`
- name: `SHActivateContext`
- size: `105`
- prototype: `BOOL __fastcall(ULONG_PTR *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004cc0`

## callees

- `0x180004b44`
- `0x180004bb4`

## import_xrefs

- `KERNEL32!ActivateActCtx` at `0x180004ba6`

## pseudocode

```c
BOOL __fastcall SHActivateContext(ULONG_PTR *a1)
{
  HANDLE v2; // rcx

  *a1 = 0;
  v2 = g_hActCtx;
  if ( g_hActCtx != (HANDLE)-1LL )
    return ActivateActCtx(v2, a1);
  if ( !hModule )
    return 1;
  if ( hModule == (HMODULE)-1LL )
    return 0;
  SHFusionInitializeFromModuleID(hModule);
  v2 = g_hActCtx;
  return g_hActCtx == (HANDLE)-1LL || ActivateActCtx(v2, a1);
}

```

## disassembly

```asm
0x180004b44  push    rbx
0x180004b46  sub     rsp, 20h
0x180004b4a  mov     rbx, rcx
0x180004b4d  mov     qword ptr [rcx], 0
0x180004b54  mov     rcx, cs:g_hActCtx
0x180004b5b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004b5f  jnz     short loc_180004B9E
0x180004b61  mov     rcx, cs:hModule; hModule
0x180004b68  test    rcx, rcx
0x180004b6b  jz      short loc_180004B93
0x180004b6d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004b71  jnz     short loc_180004B7B
0x180004b73  xor     eax, eax
0x180004b75  add     rsp, 20h
0x180004b79  pop     rbx
0x180004b7a  retn
0x180004b7b  mov     edx, cs:dword_18000A360
0x180004b81  call    SHFusionInitializeFromModuleID
0x180004b86  mov     rcx, cs:g_hActCtx
0x180004b8d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004b91  jnz     short loc_180004B9E
0x180004b93  mov     eax, 1
0x180004b98  add     rsp, 20h
0x180004b9c  pop     rbx
0x180004b9d  retn
0x180004b9e  mov     rdx, rbx
0x180004ba1  add     rsp, 20h
0x180004ba5  pop     rbx
0x180004ba6  jmp     cs:__imp_ActivateActCtx
```
