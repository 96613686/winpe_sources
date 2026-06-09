# cxxbridge1$PsIsThreadTerminating

- ea: `0x1400177ac`
- end: `0x1400177cd`
- name: `cxxbridge1$PsIsThreadTerminating`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400101f0`

## import_xrefs

- `ntoskrnl!PsIsThreadTerminating` at `0x1400177b8`
- `ntoskrnl!PsIsThreadTerminating` at `0x1400177b8`

## pseudocode

```c
BOOLEAN __fastcall cxxbridge1_PsIsThreadTerminating(PETHREAD *a1, BOOLEAN *a2)
{
  BOOLEAN result; // al

  result = PsIsThreadTerminating(*a1);
  *a2 = result;
  return result;
}

```

## disassembly

```asm
0x1400177ac  push    rbx
0x1400177ae  sub     rsp, 20h
0x1400177b2  mov     rcx, [rcx]; Thread
0x1400177b5  mov     rbx, rdx
0x1400177b8  call    cs:__imp_PsIsThreadTerminating
0x1400177bf  nop     dword ptr [rax+rax+00h]
0x1400177c4  mov     [rbx], al
0x1400177c6  add     rsp, 20h
0x1400177ca  pop     rbx
0x1400177cb  retn
```
