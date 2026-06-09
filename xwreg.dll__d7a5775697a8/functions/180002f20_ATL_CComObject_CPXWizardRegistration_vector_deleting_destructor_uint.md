# ATL::CComObject<CPXWizardRegistration>::`vector deleting destructor'(uint)

- ea: `0x180002f20`
- end: `0x180002f50`
- name: `??_E?$CComObject@VCPXWizardRegistration@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002cac`
- `0x180002f20`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002f3c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002f3c`

## pseudocode

```c
void *__fastcall ATL::CComObject<CPXWizardRegistration>::`vector deleting destructor'(void *a1, char a2)
{
  ATL::CComObject<CPXWizardRegistration>::~CComObject<CPXWizardRegistration>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002f20  mov     [rsp+arg_0], rbx
0x180002f25  push    rdi
0x180002f26  sub     rsp, 20h
0x180002f2a  mov     ebx, edx
0x180002f2c  mov     rdi, rcx
0x180002f2f  call    ??1?$CComObject@VCPXWizardRegistration@@@ATL@@UEAA@XZ; ATL::CComObject<CPXWizardRegistration>::~CComObject<CPXWizardRegistration>(void)
0x180002f34  test    bl, 1
0x180002f37  jz      short loc_180002F42
0x180002f39  mov     rcx, rdi
0x180002f3c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002f42  mov     rbx, [rsp+28h+arg_0]
0x180002f47  mov     rax, rdi
0x180002f4a  add     rsp, 20h
0x180002f4e  pop     rdi
0x180002f4f  retn
```
