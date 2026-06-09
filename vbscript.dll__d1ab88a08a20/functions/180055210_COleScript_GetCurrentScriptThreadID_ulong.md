# COleScript::GetCurrentScriptThreadID(ulong *)

- ea: `0x180055210`
- end: `0x18005523c`
- name: `?GetCurrentScriptThreadID@COleScript@@UEAAJPEAK@Z`
- size: `44`
- prototype: `__int64 __fastcall(COleScript *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180055210`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180055225`
- `KERNEL32!GetCurrentThreadId` at `0x180055225`

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
0x180055210  push    rbx
0x180055212  sub     rsp, 20h
0x180055216  mov     rbx, rdx
0x180055219  test    rdx, rdx
0x18005521c  jnz     short loc_180055225
0x18005521e  mov     eax, 80004003h
0x180055223  jmp     short loc_180055235
0x180055225  call    cs:__imp_GetCurrentThreadId
0x18005522c  nop     dword ptr [rax+rax+00h]
0x180055231  mov     [rbx], eax
0x180055233  xor     eax, eax
0x180055235  add     rsp, 20h
0x180055239  pop     rbx
0x18005523a  retn
```
