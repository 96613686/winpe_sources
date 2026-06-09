# COleScript::GetCurrentScriptThreadID(ulong *)

- ea: `0x180053960`
- end: `0x180053985`
- name: `?GetCurrentScriptThreadID@COleScript@@UEAAJPEAK@Z`
- size: `37`
- prototype: `__int64 __fastcall(COleScript *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180053960`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180053975`
- `KERNEL32!GetCurrentThreadId` at `0x180053975`

## pseudocode

```c
__int64 __fastcall COleScript::GetCurrentScriptThreadID(COleScript *this, unsigned int *a2)
{
  if ( !a2 )
    return 2147500035LL;
  *a2 = GetCurrentThreadId();
  return 0;
}

```

## disassembly

```asm
0x180053960  push    rbx
0x180053962  sub     rsp, 20h
0x180053966  mov     rbx, rdx
0x180053969  test    rdx, rdx
0x18005396c  jnz     short loc_180053975
0x18005396e  mov     eax, 80004003h
0x180053973  jmp     short loc_18005397F
0x180053975  call    cs:__imp_GetCurrentThreadId
0x18005397b  mov     [rbx], eax
0x18005397d  xor     eax, eax
0x18005397f  add     rsp, 20h
0x180053983  pop     rbx
0x180053984  retn
```
