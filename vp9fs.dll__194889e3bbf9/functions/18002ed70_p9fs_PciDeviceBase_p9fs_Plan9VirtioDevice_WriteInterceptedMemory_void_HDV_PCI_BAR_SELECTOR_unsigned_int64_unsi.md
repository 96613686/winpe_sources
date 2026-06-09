# p9fs::PciDeviceBase<p9fs::Plan9VirtioDevice>::WriteInterceptedMemory(void *,HDV_PCI_BAR_SELECTOR,unsigned __int64,unsigned __int64,uchar const *)

- ea: `0x18002ed70`
- end: `0x18002edc3`
- name: `?WriteInterceptedMemory@?$PciDeviceBase@VPlan9VirtioDevice@p9fs@@@p9fs@@SAJPEAXW4HDV_PCI_BAR_SELECTOR@@_K2PEBE@Z`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001c93c`
- `0x18002ed70`

## import_xrefs

- `vmvirtio!VirtioWriteInterceptedBar` at `0x18002edab`
- `vmvirtio!VirtioWriteInterceptedBar` at `0x18002edab`

## pseudocode

```c
__int64 __fastcall p9fs::PciDeviceBase<p9fs::Plan9VirtioDevice>::WriteInterceptedMemory(
        gsl::details *a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  if ( a4 == -1 || !a5 && a4 )
    gsl::details::terminate(a1);
  if ( (a2 & 0xFFFFFFFD) != 0 )
    return a2 != 4 ? 0x80004005 : 0;
  else
    return VirtioWriteInterceptedBar(*((_QWORD *)a1 + 17));
}

```

## disassembly

```asm
0x18002ed70  sub     rsp, 38h
0x18002ed74  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18002ed78  jz      short loc_18002EDBC
0x18002ed7a  mov     rax, [rsp+38h+arg_20]
0x18002ed7f  test    rax, rax
0x18002ed82  jnz     short loc_18002ED89
0x18002ed84  test    r9, r9
0x18002ed87  jnz     short loc_18002EDBC
0x18002ed89  test    edx, 0FFFFFFFDh
0x18002ed8f  jz      short loc_18002ED9F
0x18002ed91  sub     edx, 4
0x18002ed94  neg     edx
0x18002ed96  sbb     eax, eax
0x18002ed98  and     eax, 80004005h
0x18002ed9d  jmp     short loc_18002EDB1
0x18002ed9f  mov     [rsp+38h+var_18], rax
0x18002eda4  mov     rcx, [rcx+88h]
0x18002edab  call    cs:__imp_VirtioWriteInterceptedBar
0x18002edb1  jmp     short loc_18002EDB7
0x18002edb3  mov     eax, [rsp+38h+arg_18]
0x18002edb7  add     rsp, 38h
0x18002edbb  retn
0x18002edbc  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
