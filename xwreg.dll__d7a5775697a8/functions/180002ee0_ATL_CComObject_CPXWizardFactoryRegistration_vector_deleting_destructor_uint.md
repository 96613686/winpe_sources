# ATL::CComObject<CPXWizardFactoryRegistration>::`vector deleting destructor'(uint)

- ea: `0x180002ee0`
- end: `0x180002f10`
- name: `??_E?$CComObject@VCPXWizardFactoryRegistration@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002c68`
- `0x180002ee0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002efc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002efc`

## pseudocode

```c
void *__fastcall ATL::CComObject<CPXWizardFactoryRegistration>::`vector deleting destructor'(void *a1, char a2)
{
  ATL::CComObject<CPXWizardFactoryRegistration>::~CComObject<CPXWizardFactoryRegistration>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002ee0  mov     [rsp+arg_0], rbx
0x180002ee5  push    rdi
0x180002ee6  sub     rsp, 20h
0x180002eea  mov     ebx, edx
0x180002eec  mov     rdi, rcx
0x180002eef  call    ??1?$CComObject@VCPXWizardFactoryRegistration@@@ATL@@UEAA@XZ; ATL::CComObject<CPXWizardFactoryRegistration>::~CComObject<CPXWizardFactoryRegistration>(void)
0x180002ef4  test    bl, 1
0x180002ef7  jz      short loc_180002F02
0x180002ef9  mov     rcx, rdi
0x180002efc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002f02  mov     rbx, [rsp+28h+arg_0]
0x180002f07  mov     rax, rdi
0x180002f0a  add     rsp, 20h
0x180002f0e  pop     rdi
0x180002f0f  retn
```
