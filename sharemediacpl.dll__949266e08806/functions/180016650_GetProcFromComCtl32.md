# _GetProcFromComCtl32

- ea: `0x180016650`
- end: `0x180016698`
- name: `_GetProcFromComCtl32`
- size: `72`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016328`
- `0x180016374`
- `0x1800163c0`
- `0x180016414`
- `0x180016460`
- `0x1800164b8`
- `0x180016574`
- `0x1800165e8`

## callees

- `0x180016524`
- `0x180016650`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180016684`
- `KERNEL32!GetProcAddress` at `0x180016684`

## pseudocode

```c
FARPROC __fastcall GetProcFromComCtl32(FARPROC *a1, const CHAR *a2)
{
  HMODULE v4; // rcx
  FARPROC result; // rax

  v4 = g_hinstCC;
  if ( g_hinstCC || (DelayLoadCC(), (v4 = g_hinstCC) != 0) )
    result = GetProcAddress(v4, a2);
  else
    result = 0;
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x180016650  mov     [rsp+arg_0], rbx
0x180016655  push    rdi
0x180016656  sub     rsp, 20h
0x18001665a  mov     rbx, rcx
0x18001665d  mov     rdi, rdx
0x180016660  mov     rcx, cs:g_hinstCC; hModule
0x180016667  test    rcx, rcx
0x18001666a  jnz     short loc_180016681
0x18001666c  call    DelayLoadCC
0x180016671  mov     rcx, cs:g_hinstCC
0x180016678  test    rcx, rcx
0x18001667b  jnz     short loc_180016681
0x18001667d  xor     eax, eax
0x18001667f  jmp     short loc_18001668A
0x180016681  mov     rdx, rdi; lpProcName
0x180016684  call    cs:__imp_GetProcAddress
0x18001668a  mov     [rbx], rax
0x18001668d  mov     rbx, [rsp+28h+arg_0]
0x180016692  add     rsp, 20h
0x180016696  pop     rdi
0x180016697  retn
```
