# PMH_SUPPORT_FCNS::GetAppHostConfigFilename(ushort * *)

- ea: `0x180003880`
- end: `0x1800038a8`
- name: `?GetAppHostConfigFilename@PMH_SUPPORT_FCNS@@UEAAJPEAPEAG@Z`
- size: `40`
- prototype: `__int64 __fastcall(PMH_SUPPORT_FCNS *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000388d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000388d`

## pseudocode

```c
__int64 __fastcall PMH_SUPPORT_FCNS::GetAppHostConfigFilename(const OLECHAR **this, unsigned __int16 **a2)
{
  unsigned __int16 *v3; // rax

  v3 = SysAllocString(this[12]);
  *a2 = v3;
  return v3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180003880  push    rbx
0x180003882  sub     rsp, 20h
0x180003886  mov     rcx, [rcx+60h]; psz
0x18000388a  mov     rbx, rdx
0x18000388d  call    cs:__imp_SysAllocString
0x180003893  mov     [rbx], rax
0x180003896  neg     rax
0x180003899  sbb     eax, eax
0x18000389b  not     eax
0x18000389d  and     eax, 8007000Eh
0x1800038a2  add     rsp, 20h
0x1800038a6  pop     rbx
0x1800038a7  retn
```
