# WcIsSiloFileObject

- ea: `0x140001b00`
- end: `0x140001b8c`
- name: `WcIsSiloFileObject`
- size: `140`
- prototype: `_BOOL8 __fastcall(struct _FLT_INSTANCE *, __int64)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1400033a0`
- `0x140003930`
- `0x1400149c0`
- `0x140019c40`
- `0x140019da0`
- `0x1400231a0`
- `0x140023694`
- `0x140024214`
- `0x140028680`
- `0x140028ad0`
- `0x140030438`

## callees

- `0x140001b00`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x140001b49`
- `ntoskrnl!PsIsHostSilo` at `0x140001b49`
- `ntoskrnl!IoGetSilo` at `0x140001b3a`
- `ntoskrnl!IoGetSilo` at `0x140001b3a`
- `FLTMGR!FltReleaseContext` at `0x140001b72`
- `FLTMGR!FltReleaseContext` at `0x140001b72`
- `FLTMGR!FltGetInstanceContext` at `0x140001b17`
- `FLTMGR!FltGetInstanceContext` at `0x140001b17`

## pseudocode

```c
_BOOL8 __fastcall WcIsSiloFileObject(struct _FLT_INSTANCE *a1, __int64 a2)
{
  PFLT_CONTEXT v3; // rcx
  __int64 Silo; // rax
  bool v5; // bl
  PFLT_CONTEXT Context; // [rsp+40h] [rbp+18h] BYREF

  Context = 0;
  FltGetInstanceContext(a1, &Context);
  v3 = Context;
  if ( *((_QWORD *)Context + 7) )
  {
    v5 = 1;
  }
  else
  {
    Silo = IoGetSilo(a2);
    v5 = (unsigned __int8)PsIsHostSilo(Silo) == 0;
    v3 = Context;
  }
  if ( v3 )
    FltReleaseContext(v3);
  return v5;
}

```

## disassembly

```asm
0x140001b00  push    rbx
0x140001b02  sub     rsp, 20h
0x140001b06  mov     rbx, rdx
0x140001b09  mov     [rsp+28h+Context], 0
0x140001b12  lea     rdx, [rsp+28h+Context]; Context
0x140001b17  call    cs:__imp_FltGetInstanceContext
0x140001b1e  nop     dword ptr [rax+rax+00h]
0x140001b23  mov     rcx, [rsp+28h+Context]
0x140001b28  cmp     qword ptr [rcx+38h], 0
0x140001b2d  jnz     short loc_140001B88
0x140001b2f  mov     [rsp+28h+arg_0], rdi
0x140001b34  mov     rcx, rbx
0x140001b37  xor     dil, dil
0x140001b3a  call    cs:__imp_IoGetSilo
0x140001b41  nop     dword ptr [rax+rax+00h]
0x140001b46  mov     rcx, rax
0x140001b49  call    cs:__imp_PsIsHostSilo
0x140001b50  nop     dword ptr [rax+rax+00h]
0x140001b55  movzx   ebx, dil
0x140001b59  mov     ecx, 1
0x140001b5e  mov     rdi, [rsp+28h+arg_0]
0x140001b63  test    al, al
0x140001b65  cmovz   ebx, ecx
0x140001b68  mov     rcx, [rsp+28h+Context]; Context
0x140001b6d  test    rcx, rcx
0x140001b70  jz      short loc_140001B7E
0x140001b72  call    cs:__imp_FltReleaseContext
0x140001b79  nop     dword ptr [rax+rax+00h]
0x140001b7e  movzx   eax, bl
0x140001b81  add     rsp, 20h
0x140001b85  pop     rbx
0x140001b86  retn
0x140001b88  mov     bl, 1
0x140001b8a  jmp     short loc_140001B6D
```
