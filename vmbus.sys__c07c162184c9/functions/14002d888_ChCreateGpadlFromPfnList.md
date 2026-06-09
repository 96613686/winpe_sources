# ChCreateGpadlFromPfnList

- ea: `0x14002d888`
- end: `0x14002d950`
- name: `ChCreateGpadlFromPfnList`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002c9e0`

## callees

- `0x14000f158`
- `0x140017240`
- `0x14002d888`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14002d8ca`
- `ntoskrnl!IoAllocateMdl` at `0x14002d8ca`
- `ntoskrnl!IoFreeMdl` at `0x14002d938`
- `ntoskrnl!IoFreeMdl` at `0x14002d938`

## pseudocode

```c
__int64 __fastcall ChCreateGpadlFromPfnList(__int64 a1, const void *a2, unsigned int a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rsi
  __int64 result; // rax
  PMDL Mdl; // rax
  struct _MDL *v10; // rbx
  unsigned int v11; // edi

  v6 = a3;
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 216) + 322LL) )
    return 3221225659LL;
  Mdl = IoAllocateMdl(0, a3 << 12, 0, 0, 0);
  v10 = Mdl;
  if ( !Mdl )
    return 3221225626LL;
  Mdl->MdlFlags |= 2u;
  memmove(&Mdl[1], a2, 8 * v6);
  result = ChpCreateGpadlFromNtmdl(a1, (__int64)v10, 0, 0, (__int64)BusChGpadlCreated, a5, 1);
  v11 = result;
  if ( (int)result < 0 )
  {
    IoFreeMdl(v10);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x14002d888  push    rbx
0x14002d88a  push    rbp
0x14002d88b  push    rsi
0x14002d88c  push    rdi
0x14002d88d  sub     rsp, 48h
0x14002d891  mov     rax, [rcx+0D8h]
0x14002d898  mov     rbp, rdx
0x14002d89b  mov     esi, r8d
0x14002d89e  mov     rdi, rcx
0x14002d8a1  cmp     byte ptr [rax+142h], 0
0x14002d8a8  jz      short loc_14002D8B4
0x14002d8aa  mov     eax, 0C00000BBh
0x14002d8af  jmp     loc_14002D946
0x14002d8b4  mov     edx, esi
0x14002d8b6  mov     [rsp+68h+Irp], 0; Irp
0x14002d8bf  shl     edx, 0Ch; Length
0x14002d8c2  xor     r9d, r9d; ChargeQuota
0x14002d8c5  xor     r8d, r8d; SecondaryBuffer
0x14002d8c8  xor     ecx, ecx; VirtualAddress
0x14002d8ca  call    cs:__imp_IoAllocateMdl
0x14002d8d1  nop     dword ptr [rax+rax+00h]
0x14002d8d6  mov     rbx, rax
0x14002d8d9  test    rax, rax
0x14002d8dc  jnz     short loc_14002D8E5
0x14002d8de  mov     eax, 0C000009Ah
0x14002d8e3  jmp     short loc_14002D946
0x14002d8e5  or      word ptr [rax+0Ah], 2
0x14002d8ea  lea     rcx, [rax+30h]; void *
0x14002d8ee  mov     r8, rsi
0x14002d8f1  mov     rdx, rbp; Src
0x14002d8f4  shl     r8, 3; Size
0x14002d8f8  call    memmove
0x14002d8fd  mov     rax, [rsp+68h+arg_20]
0x14002d905  xor     r9d, r9d
0x14002d908  mov     [rsp+68h+var_38], 1
0x14002d910  xor     r8d, r8d
0x14002d913  mov     [rsp+68h+var_40], rax
0x14002d918  mov     rdx, rbx
0x14002d91b  lea     rax, BusChGpadlCreated
0x14002d922  mov     rcx, rdi
0x14002d925  mov     [rsp+68h+Irp], rax
0x14002d92a  call    ChpCreateGpadlFromNtmdl
0x14002d92f  mov     edi, eax
0x14002d931  test    eax, eax
0x14002d933  jns     short loc_14002D946
0x14002d935  mov     rcx, rbx; Mdl
0x14002d938  call    cs:__imp_IoFreeMdl
0x14002d93f  nop     dword ptr [rax+rax+00h]
0x14002d944  mov     eax, edi
0x14002d946  add     rsp, 48h
0x14002d94a  pop     rdi
0x14002d94b  pop     rsi
0x14002d94c  pop     rbp
0x14002d94d  pop     rbx
0x14002d94e  retn
```
