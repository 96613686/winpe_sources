# _GetProcFromComCtl32

- ea: `0x180014fd0`
- end: `0x180015018`
- name: `_GetProcFromComCtl32`
- size: `72`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014cdc`
- `0x180014d78`
- `0x180014e28`
- `0x180014e90`
- `0x180014f1c`
- `0x180014f7c`

## callees

- `0x180014dd8`
- `0x180014fd0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180015004`
- `KERNEL32!GetProcAddress` at `0x180015004`

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
0x180014fd0  mov     [rsp+arg_0], rbx
0x180014fd5  push    rdi
0x180014fd6  sub     rsp, 20h
0x180014fda  mov     rbx, rcx
0x180014fdd  mov     rdi, rdx
0x180014fe0  mov     rcx, cs:g_hinstCC; hModule
0x180014fe7  test    rcx, rcx
0x180014fea  jnz     short loc_180015001
0x180014fec  call    DelayLoadCC
0x180014ff1  mov     rcx, cs:g_hinstCC
0x180014ff8  test    rcx, rcx
0x180014ffb  jnz     short loc_180015001
0x180014ffd  xor     eax, eax
0x180014fff  jmp     short loc_18001500A
0x180015001  mov     rdx, rdi; lpProcName
0x180015004  call    cs:__imp_GetProcAddress
0x18001500a  mov     [rbx], rax
0x18001500d  mov     rbx, [rsp+28h+arg_0]
0x180015012  add     rsp, 20h
0x180015016  pop     rdi
0x180015017  retn
```
