# cxl::Token::TryOpenThreadToken(ulong,int,void *)

- ea: `0x1800140e8`
- end: `0x18001412a`
- name: `?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z`
- size: `66`
- prototype: `unsigned int(cxl::Token *__hidden this, unsigned int, int, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180018f1c`
- `0x18001d094`

## callees

- `0x180013ec0`
- `0x1800140e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014117`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001410d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001410d`

## pseudocode

```c
DWORD __fastcall cxl::Token::TryOpenThreadToken(void **this, DWORD a2, BOOL a3, void *a4)
{
  cxl::Token::Clear((cxl::Token *)this);
  if ( OpenThreadToken(a4, a2, a3, this + 1) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800140e8  push    rbx
0x1800140ea  push    rbp
0x1800140eb  push    rsi
0x1800140ec  push    rdi
0x1800140ed  sub     rsp, 28h
0x1800140f1  mov     rbp, r9
0x1800140f4  mov     edi, r8d
0x1800140f7  mov     esi, edx
0x1800140f9  mov     rbx, rcx
0x1800140fc  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x180014101  lea     r9, [rbx+8]; TokenHandle
0x180014105  mov     r8d, edi; OpenAsSelf
0x180014108  mov     edx, esi; DesiredAccess
0x18001410a  mov     rcx, rbp; ThreadHandle
0x18001410d  call    cs:__imp_OpenThreadToken
0x180014113  test    eax, eax
0x180014115  jnz     short loc_18001411F
0x180014117  call    cs:__imp_GetLastError
0x18001411d  jmp     short loc_180014121
0x18001411f  xor     eax, eax
0x180014121  add     rsp, 28h
0x180014125  pop     rdi
0x180014126  pop     rsi
0x180014127  pop     rbp
0x180014128  pop     rbx
0x180014129  retn
```
