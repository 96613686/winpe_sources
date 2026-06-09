# ATL::CComObject<CPXWizardTypeRegistration>::`vector deleting destructor'(uint)

- ea: `0x180002f60`
- end: `0x180002f90`
- name: `??_E?$CComObject@VCPXWizardTypeRegistration@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002cf0`
- `0x180002f60`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002f7c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002f7c`

## pseudocode

```c
void *__fastcall ATL::CComObject<CPXWizardTypeRegistration>::`vector deleting destructor'(void *a1, char a2)
{
  ATL::CComObject<CPXWizardTypeRegistration>::~CComObject<CPXWizardTypeRegistration>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002f60  mov     [rsp+arg_0], rbx
0x180002f65  push    rdi
0x180002f66  sub     rsp, 20h
0x180002f6a  mov     ebx, edx
0x180002f6c  mov     rdi, rcx
0x180002f6f  call    ??1?$CComObject@VCPXWizardTypeRegistration@@@ATL@@UEAA@XZ; ATL::CComObject<CPXWizardTypeRegistration>::~CComObject<CPXWizardTypeRegistration>(void)
0x180002f74  test    bl, 1
0x180002f77  jz      short loc_180002F82
0x180002f79  mov     rcx, rdi
0x180002f7c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002f82  mov     rbx, [rsp+28h+arg_0]
0x180002f87  mov     rax, rdi
0x180002f8a  add     rsp, 20h
0x180002f8e  pop     rdi
0x180002f8f  retn
```
