# PMH_SUPPORT_FCNS::GetRootWebConfigFilename(ushort * *)

- ea: `0x180003d20`
- end: `0x180003d4b`
- name: `?GetRootWebConfigFilename@PMH_SUPPORT_FCNS@@UEAAJPEAPEAG@Z`
- size: `43`
- prototype: `__int64 __fastcall(PMH_SUPPORT_FCNS *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180003d30`
- `OLEAUT32!__imp_SysAllocString` at `0x180003d30`

## pseudocode

```c
__int64 __fastcall PMH_SUPPORT_FCNS::GetRootWebConfigFilename(const OLECHAR **this, unsigned __int16 **a2)
{
  unsigned __int16 *v3; // rax

  v3 = SysAllocString(this[19]);
  *a2 = v3;
  return v3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180003d20  push    rbx
0x180003d22  sub     rsp, 20h
0x180003d26  mov     rcx, [rcx+98h]; psz
0x180003d2d  mov     rbx, rdx
0x180003d30  call    cs:__imp_SysAllocString
0x180003d36  mov     [rbx], rax
0x180003d39  neg     rax
0x180003d3c  sbb     eax, eax
0x180003d3e  not     eax
0x180003d40  and     eax, 8007000Eh
0x180003d45  add     rsp, 20h
0x180003d49  pop     rbx
0x180003d4a  retn
```
