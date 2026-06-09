# ComTaskHost::GetInput(ushort * *)

- ea: `0x140009d90`
- end: `0x140009dd3`
- name: `?GetInput@ComTaskHost@@UEAAJPEAPEAG@Z`
- size: `67`
- prototype: `__int64 __fastcall(ComTaskHost *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140009d90`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140009db2`
- `OLEAUT32!__imp_SysAllocString` at `0x140009db2`

## pseudocode

```c
__int64 __fastcall ComTaskHost::GetInput(ComTaskHost *this, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  unsigned __int16 *v4; // rax

  if ( a2 )
  {
    v3 = 0;
    v4 = SysAllocString(L"Put in input");
    *a2 = v4;
    if ( !v4 )
      return (unsigned int)-2147024882;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x140009d90  mov     [rsp+arg_0], rbx
0x140009d95  push    rdi
0x140009d96  sub     rsp, 20h
0x140009d9a  mov     rdi, rdx
0x140009d9d  test    rdx, rdx
0x140009da0  jnz     short loc_140009DA9
0x140009da2  mov     ebx, 80070057h
0x140009da7  jmp     short loc_140009DC6
0x140009da9  lea     rcx, aPutInInput; "Put in input"
0x140009db0  xor     ebx, ebx
0x140009db2  call    cs:__imp_SysAllocString
0x140009db8  test    rax, rax
0x140009dbb  mov     [rdi], rax
0x140009dbe  mov     ecx, 8007000Eh
0x140009dc3  cmovz   ebx, ecx
0x140009dc6  mov     eax, ebx
0x140009dc8  mov     rbx, [rsp+28h+arg_0]
0x140009dcd  add     rsp, 20h
0x140009dd1  pop     rdi
0x140009dd2  retn
```
