# ATL::CComAggObject<CPXWizardRegistration>::`scalar deleting destructor'(uint)

- ea: `0x180002e60`
- end: `0x180002e90`
- name: `??_G?$CComAggObject@VCPXWizardRegistration@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002bb8`
- `0x180002e60`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002e7c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002e7c`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CPXWizardRegistration>::`scalar deleting destructor'(void *a1, char a2)
{
  ATL::CComAggObject<CPXWizardRegistration>::~CComAggObject<CPXWizardRegistration>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002e60  mov     [rsp+arg_0], rbx
0x180002e65  push    rdi
0x180002e66  sub     rsp, 20h
0x180002e6a  mov     ebx, edx
0x180002e6c  mov     rdi, rcx
0x180002e6f  call    ??1?$CComAggObject@VCPXWizardRegistration@@@ATL@@UEAA@XZ; ATL::CComAggObject<CPXWizardRegistration>::~CComAggObject<CPXWizardRegistration>(void)
0x180002e74  test    bl, 1
0x180002e77  jz      short loc_180002E82
0x180002e79  mov     rcx, rdi
0x180002e7c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002e82  mov     rbx, [rsp+28h+arg_0]
0x180002e87  mov     rax, rdi
0x180002e8a  add     rsp, 20h
0x180002e8e  pop     rdi
0x180002e8f  retn
```
