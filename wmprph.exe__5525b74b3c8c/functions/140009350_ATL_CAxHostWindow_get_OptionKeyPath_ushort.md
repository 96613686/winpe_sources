# ATL::CAxHostWindow::get_OptionKeyPath(ushort * *)

- ea: `0x140009350`
- end: `0x140009377`
- name: `?get_OptionKeyPath@CAxHostWindow@ATL@@UEAAJPEAPEAG@Z`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140009350`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::get_OptionKeyPath(ATL::CAxHostWindow *this, unsigned __int16 **a2)
{
  unsigned __int16 *v3; // rax

  if ( !a2 )
    return 2147500035LL;
  v3 = (unsigned __int16 *)*((_QWORD *)this + 24);
  *a2 = v3;
  return *((_QWORD *)this + 24) != (_QWORD)v3 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x140009350  test    rdx, rdx
0x140009353  jnz     short loc_14000935B
0x140009355  mov     eax, 80004003h
0x14000935a  retn
0x14000935b  mov     rax, [rcx+0C0h]
0x140009362  mov     [rdx], rax
0x140009365  sub     rax, [rcx+0C0h]
0x14000936c  neg     rax
0x14000936f  sbb     eax, eax
0x140009371  and     eax, 8007000Eh
0x140009376  retn
```
