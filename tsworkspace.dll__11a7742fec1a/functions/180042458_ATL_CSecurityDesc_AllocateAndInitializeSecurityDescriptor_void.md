# ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor(void)

- ea: `0x180042458`
- end: `0x1800424c2`
- name: `?AllocateAndInitializeSecurityDescriptor@CSecurityDesc@ATL@@IEAAXXZ`
- size: `106`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045490`
- `0x18004561c`
- `0x180045720`

## callees

- `0x180006d14`
- `0x180007598`
- `0x180042458`

## import_xrefs

- `msvcrt!malloc` at `0x18004246a`
- `msvcrt!malloc` at `0x18004246a`
- `msvcrt!free` at `0x1800424a1`
- `msvcrt!free` at `0x1800424a1`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18004248c`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18004248c`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor(ATL::CSecurityDesc *this)
{
  void *v2; // rax
  int Error; // ebx

  v2 = malloc(0x28u);
  *((_QWORD *)this + 1) = v2;
  if ( !v2 )
    ATL::AtlThrowImpl(-2147024882);
  if ( !InitializeSecurityDescriptor(v2, 1u) )
  {
    Error = ATL::AtlHresultFromLastError();
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
    ATL::AtlThrowImpl(Error);
  }
}

```

## disassembly

```asm
0x180042458  mov     [rsp+arg_0], rbx
0x18004245d  push    rdi
0x18004245e  sub     rsp, 20h
0x180042462  mov     rdi, rcx
0x180042465  mov     ecx, 28h ; '('; Size
0x18004246a  call    cs:__imp_malloc
0x180042470  mov     [rdi+8], rax
0x180042474  test    rax, rax
0x180042477  jnz     short loc_180042484
0x180042479  mov     ecx, 8007000Eh; int
0x18004247e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180042484  mov     edx, 1; dwRevision
0x180042489  mov     rcx, rax; pSecurityDescriptor
0x18004248c  call    cs:__imp_InitializeSecurityDescriptor
0x180042492  test    eax, eax
0x180042494  jnz     short loc_1800424B7
0x180042496  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18004249b  mov     rcx, [rdi+8]; Block
0x18004249f  mov     ebx, eax
0x1800424a1  call    cs:__imp_free
0x1800424a7  mov     ecx, ebx; int
0x1800424a9  mov     qword ptr [rdi+8], 0
0x1800424b1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800424b7  mov     rbx, [rsp+28h+arg_0]
0x1800424bc  add     rsp, 20h
0x1800424c0  pop     rdi
0x1800424c1  retn
```
