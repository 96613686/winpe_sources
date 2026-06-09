# RedirectedCredContextTable::~RedirectedCredContextTable(void)

- ea: `0x18001b648`
- end: `0x18001b697`
- name: `??1RedirectedCredContextTable@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180012904`

## callees

- `0x18001b648`
- `0x18001d010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18001b65a`
- `ntdll!RtlFreeUnicodeString` at `0x18001b65a`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001b67e`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001b67e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001b673`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001b673`

## pseudocode

```c
void __fastcall RedirectedCredContextTable::~RedirectedCredContextTable(PRTL_AVL_TABLE Table)
{
  struct _RTL_AVL_TABLE *i; // rdi
  struct _UNICODE_STRING *v2; // rax
  struct _UNICODE_STRING *v3; // rbx

  for ( i = Table; ; Table = i )
  {
    v2 = (struct _UNICODE_STRING *)RtlEnumerateGenericTableAvl(Table, 1u);
    v3 = v2;
    if ( !v2 )
      break;
    RtlFreeUnicodeString(v2);
    (*(void (__fastcall **)(_QWORD))&v3[2].Length)(*(_QWORD *)&v3[1].Length);
    RtlDeleteElementGenericTableAvl(i, v3);
  }
}

```

## disassembly

```asm
0x18001b648  mov     [rsp+arg_0], rbx
0x18001b64d  push    rdi
0x18001b64e  sub     rsp, 20h
0x18001b652  mov     rdi, rcx
0x18001b655  jmp     short loc_18001B67C
0x18001b657  mov     rcx, rbx; UnicodeString
0x18001b65a  call    cs:__imp_RtlFreeUnicodeString
0x18001b660  mov     rcx, [rbx+10h]
0x18001b664  mov     rax, [rbx+20h]
0x18001b668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b66d  mov     rdx, rbx; Buffer
0x18001b670  mov     rcx, rdi; Table
0x18001b673  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18001b679  mov     rcx, rdi; Table
0x18001b67c  mov     dl, 1; Restart
0x18001b67e  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18001b684  mov     rbx, rax
0x18001b687  test    rax, rax
0x18001b68a  jnz     short loc_18001B657
0x18001b68c  mov     rbx, [rsp+28h+arg_0]
0x18001b691  add     rsp, 20h
0x18001b695  pop     rdi
0x18001b696  retn
```
