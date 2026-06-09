# ComTaskHost::GetContext(ushort * *)

- ea: `0x140009d50`
- end: `0x140009d7b`
- name: `?GetContext@ComTaskHost@@UEAAJPEAPEAG@Z`
- size: `43`
- prototype: `__int64 __fastcall(ComTaskHost *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140009d60`
- `OLEAUT32!__imp_SysAllocString` at `0x140009d60`

## pseudocode

```c
__int64 __fastcall ComTaskHost::GetContext(ComTaskHost *this, unsigned __int16 **a2)
{
  unsigned __int16 *v3; // rax

  v3 = SysAllocString(L"Context Text");
  *a2 = v3;
  return v3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x140009d50  push    rbx
0x140009d52  sub     rsp, 20h
0x140009d56  lea     rcx, psz; "Context Text"
0x140009d5d  mov     rbx, rdx
0x140009d60  call    cs:__imp_SysAllocString
0x140009d66  mov     [rbx], rax
0x140009d69  neg     rax
0x140009d6c  sbb     eax, eax
0x140009d6e  not     eax
0x140009d70  and     eax, 8007000Eh
0x140009d75  add     rsp, 20h
0x140009d79  pop     rbx
0x140009d7a  retn
```
