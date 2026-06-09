# ATL::CComAggObject<CPXWizardFactoryRegistration>::`vector deleting destructor'(uint)

- ea: `0x180002e20`
- end: `0x180002e50`
- name: `??_E?$CComAggObject@VCPXWizardFactoryRegistration@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002b74`
- `0x180002e20`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002e3c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002e3c`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CPXWizardFactoryRegistration>::`vector deleting destructor'(void *a1, char a2)
{
  ATL::CComAggObject<CPXWizardFactoryRegistration>::~CComAggObject<CPXWizardFactoryRegistration>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002e20  mov     [rsp+arg_0], rbx
0x180002e25  push    rdi
0x180002e26  sub     rsp, 20h
0x180002e2a  mov     ebx, edx
0x180002e2c  mov     rdi, rcx
0x180002e2f  call    ??1?$CComAggObject@VCPXWizardFactoryRegistration@@@ATL@@UEAA@XZ; ATL::CComAggObject<CPXWizardFactoryRegistration>::~CComAggObject<CPXWizardFactoryRegistration>(void)
0x180002e34  test    bl, 1
0x180002e37  jz      short loc_180002E42
0x180002e39  mov     rcx, rdi
0x180002e3c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002e42  mov     rbx, [rsp+28h+arg_0]
0x180002e47  mov     rax, rdi
0x180002e4a  add     rsp, 20h
0x180002e4e  pop     rdi
0x180002e4f  retn
```
