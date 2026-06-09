# CUwfManagement::get_OverlayMaximumSize(bool,ulong *)

- ea: `0x180017050`
- end: `0x180017085`
- name: `?get_OverlayMaximumSize@CUwfManagement@@QEAAJ_NPEAK@Z`
- size: `53`
- prototype: `int __fastcall(CUwfManagement *this, char, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180018bf0`

## callees

- `0x18000af70`
- `0x180017050`

## pseudocode

```c
int __fastcall CUwfManagement::get_OverlayMaximumSize(CUwfManagement *this, char a2, unsigned int *a3)
{
  if ( a3 )
    return CUwfStaticConfiguration::get_OverlayMaximumSize(
             (CUwfManagement *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFD0uLL) + 168),
             a3);
  else
    return -2147467261;
}

```

## disassembly

```asm
0x180017050  sub     rsp, 28h
0x180017054  mov     rax, rcx
0x180017057  test    r8, r8
0x18001705a  jnz     short loc_180017066
0x18001705c  mov     eax, 80004003h
0x180017061  add     rsp, 28h
0x180017065  retn
0x180017066  neg     dl
0x180017068  mov     rdx, r8; unsigned int *
0x18001706b  sbb     rcx, rcx
0x18001706e  add     rax, 0A8h
0x180017074  and     rcx, 0FFFFFFFFFFFFFFD0h
0x180017078  add     rcx, rax; this
0x18001707b  call    ?get_OverlayMaximumSize@CUwfStaticConfiguration@@QEAAJPEAK@Z; CUwfStaticConfiguration::get_OverlayMaximumSize(ulong *)
0x180017080  add     rsp, 28h
0x180017084  retn
```
