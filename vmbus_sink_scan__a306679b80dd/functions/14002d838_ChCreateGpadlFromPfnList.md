# ChCreateGpadlFromPfnList

- ea: `0x14002d838`
- end: `0x14002d900`
- name: `ChCreateGpadlFromPfnList`
- size: `200`
- prototype: `__int64 __fastcall(__int64, const void *, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002c990`

## callees

- `0x14000f158`
- `0x140017240`
- `0x14002d838`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14002d87a`
- `ntoskrnl!IoAllocateMdl` at `0x14002d87a`
- `ntoskrnl!IoFreeMdl` at `0x14002d8e8`
- `ntoskrnl!IoFreeMdl` at `0x14002d8e8`

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
  result = ChpCreateGpadlFromNtmdl(a1, v10, 0, 0, BusChGpadlCreated, a5, 1);
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
0x14002d838  push    rbx
0x14002d83a  push    rbp
0x14002d83b  push    rsi
0x14002d83c  push    rdi
0x14002d83d  sub     rsp, 48h
0x14002d841  mov     rax, [rcx+0D8h]
0x14002d848  mov     rbp, rdx
0x14002d84b  mov     esi, r8d
0x14002d84e  mov     rdi, rcx
0x14002d851  cmp     byte ptr [rax+142h], 0
0x14002d858  jz      short loc_14002D864
0x14002d85a  mov     eax, 0C00000BBh
0x14002d85f  jmp     loc_14002D8F6
0x14002d864  mov     edx, esi
0x14002d866  mov     [rsp+68h+Irp], 0; Irp
0x14002d86f  shl     edx, 0Ch; Length
0x14002d872  xor     r9d, r9d; ChargeQuota
0x14002d875  xor     r8d, r8d; SecondaryBuffer
0x14002d878  xor     ecx, ecx; VirtualAddress
0x14002d87a  call    cs:__imp_IoAllocateMdl
0x14002d881  nop     dword ptr [rax+rax+00h]
0x14002d886  mov     rbx, rax
0x14002d889  test    rax, rax
0x14002d88c  jnz     short loc_14002D895
0x14002d88e  mov     eax, 0C000009Ah
0x14002d893  jmp     short loc_14002D8F6
0x14002d895  or      word ptr [rax+0Ah], 2
0x14002d89a  lea     rcx, [rax+30h]; void *
0x14002d89e  mov     r8, rsi
0x14002d8a1  mov     rdx, rbp; Src
0x14002d8a4  shl     r8, 3; Size
0x14002d8a8  call    memmove
0x14002d8ad  mov     rax, [rsp+68h+arg_20]
0x14002d8b5  xor     r9d, r9d
0x14002d8b8  mov     [rsp+68h+var_38], 1
0x14002d8c0  xor     r8d, r8d
0x14002d8c3  mov     [rsp+68h+var_40], rax
0x14002d8c8  mov     rdx, rbx
0x14002d8cb  lea     rax, BusChGpadlCreated
0x14002d8d2  mov     rcx, rdi
0x14002d8d5  mov     [rsp+68h+Irp], rax
0x14002d8da  call    ChpCreateGpadlFromNtmdl
0x14002d8df  mov     edi, eax
0x14002d8e1  test    eax, eax
0x14002d8e3  jns     short loc_14002D8F6
0x14002d8e5  mov     rcx, rbx; Mdl
0x14002d8e8  call    cs:__imp_IoFreeMdl
0x14002d8ef  nop     dword ptr [rax+rax+00h]
0x14002d8f4  mov     eax, edi
0x14002d8f6  add     rsp, 48h
0x14002d8fa  pop     rdi
0x14002d8fb  pop     rsi
0x14002d8fc  pop     rbp
0x14002d8fd  pop     rbx
0x14002d8fe  retn
```
