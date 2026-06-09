# CTextNormMultiResult::HasReplaceVerbose(int *)

- ea: `0x180001f40`
- end: `0x180001f48`
- name: `?HasReplaceVerbose@CTextNormMultiResult@@UEAAJPEAH@Z`
- size: `8`
- prototype: `__int64 __fastcall(CTextNormMultiResult *__hidden this, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CTextNormMultiResult::HasReplaceVerbose(CTextNormMultiResult *this, int *a2)
{
  *a2 = *((_DWORD *)this + 20);
  return 0;
}

```

## disassembly

```asm
0x180001f40  mov     eax, [rcx+50h]
0x180001f43  mov     [rdx], eax
0x180001f45  xor     eax, eax
0x180001f47  retn
```
