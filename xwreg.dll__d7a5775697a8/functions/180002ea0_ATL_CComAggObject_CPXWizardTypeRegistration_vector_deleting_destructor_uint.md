# ATL::CComAggObject<CPXWizardTypeRegistration>::`vector deleting destructor'(uint)

- ea: `0x180002ea0`
- end: `0x180002ed0`
- name: `??_E?$CComAggObject@VCPXWizardTypeRegistration@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002bfc`
- `0x180002ea0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002ebc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002ebc`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CPXWizardTypeRegistration>::`vector deleting destructor'(void *a1, char a2)
{
  ATL::CComAggObject<CPXWizardTypeRegistration>::~CComAggObject<CPXWizardTypeRegistration>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002ea0  mov     [rsp+arg_0], rbx
0x180002ea5  push    rdi
0x180002ea6  sub     rsp, 20h
0x180002eaa  mov     ebx, edx
0x180002eac  mov     rdi, rcx
0x180002eaf  call    ??1?$CComAggObject@VCPXWizardTypeRegistration@@@ATL@@UEAA@XZ; ATL::CComAggObject<CPXWizardTypeRegistration>::~CComAggObject<CPXWizardTypeRegistration>(void)
0x180002eb4  test    bl, 1
0x180002eb7  jz      short loc_180002EC2
0x180002eb9  mov     rcx, rdi
0x180002ebc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002ec2  mov     rbx, [rsp+28h+arg_0]
0x180002ec7  mov     rax, rdi
0x180002eca  add     rsp, 20h
0x180002ece  pop     rdi
0x180002ecf  retn
```
