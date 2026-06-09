# CInitialConsentUI::Static_InitialDlgThreadRoutine(void *)

- ea: `0x18000dd40`
- end: `0x18000dd50`
- name: `?Static_InitialDlgThreadRoutine@CInitialConsentUI@@CAKPEAX@Z`
- size: `16`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000cbc8`

## pseudocode

```c
__int64 __fastcall CInitialConsentUI::Static_InitialDlgThreadRoutine(CInitialConsentUI *Parameter)
{
  CInitialConsentUI::InitialDlgThreadRoutine(Parameter);
  return 0;
}

```

## disassembly

```asm
0x18000dd40  sub     rsp, 28h
0x18000dd44  call    ?InitialDlgThreadRoutine@CInitialConsentUI@@QEAAJXZ; CInitialConsentUI::InitialDlgThreadRoutine(void)
0x18000dd49  xor     eax, eax
0x18000dd4b  add     rsp, 28h
0x18000dd4f  retn
```
