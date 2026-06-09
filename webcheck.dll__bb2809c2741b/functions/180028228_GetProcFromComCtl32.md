# _GetProcFromComCtl32

- ea: `0x180028228`
- end: `0x180028270`
- name: `_GetProcFromComCtl32`
- size: `72`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028018`
- `0x1800280fc`
- `0x18002814c`
- `0x18002819c`
- `0x1800286e8`

## callees

- `0x1800280ac`
- `0x180028228`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002825c`
- `KERNEL32!GetProcAddress` at `0x18002825c`

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
0x180028228  mov     [rsp+arg_0], rbx
0x18002822d  push    rdi
0x18002822e  sub     rsp, 20h
0x180028232  mov     rbx, rcx
0x180028235  mov     rdi, rdx
0x180028238  mov     rcx, cs:g_hinstCC; hModule
0x18002823f  test    rcx, rcx
0x180028242  jnz     short loc_180028259
0x180028244  call    DelayLoadCC
0x180028249  mov     rcx, cs:g_hinstCC
0x180028250  test    rcx, rcx
0x180028253  jnz     short loc_180028259
0x180028255  xor     eax, eax
0x180028257  jmp     short loc_180028262
0x180028259  mov     rdx, rdi; lpProcName
0x18002825c  call    cs:__imp_GetProcAddress
0x180028262  mov     [rbx], rax
0x180028265  mov     rbx, [rsp+28h+arg_0]
0x18002826a  add     rsp, 20h
0x18002826e  pop     rdi
0x18002826f  retn
```
