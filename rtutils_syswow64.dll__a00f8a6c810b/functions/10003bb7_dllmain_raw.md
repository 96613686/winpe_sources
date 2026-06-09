# dllmain_raw

- ea: `0x10003bb7`
- end: `0x10003be4`
- name: `dllmain_raw`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10003aa8`

## callees

- `0x10003bb7`
- `0x10004190`

## pseudocode

```c
int __stdcall dllmain_raw(int a1, int a2, int a3)
{
  if ( _pRawDllMain )
    return _pRawDllMain(_pRawDllMain, a1, a2, a3);
  else
    return 1;
}

```

## disassembly

```asm
0x10003bb7  mov     edi, edi
0x10003bb9  push    ebp
0x10003bba  mov     ebp, esp
0x10003bbc  push    esi
0x10003bbd  mov     esi, ds:__pRawDllMain
0x10003bc3  test    esi, esi
0x10003bc5  jnz     short loc_10003BCC
0x10003bc7  xor     eax, eax
0x10003bc9  inc     eax
0x10003bca  jmp     short loc_10003BDF
0x10003bcc  push    [ebp+arg_8]
0x10003bcf  mov     ecx, esi
0x10003bd1  push    [ebp+arg_4]
0x10003bd4  push    [ebp+arg_0]
0x10003bd7  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10003bdd  call    esi ; __pRawDllMain
0x10003bdf  pop     esi
0x10003be0  pop     ebp
0x10003be1  retn    0Ch
```
