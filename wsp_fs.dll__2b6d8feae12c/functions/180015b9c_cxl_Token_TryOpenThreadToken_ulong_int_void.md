# cxl::Token::TryOpenThreadToken(ulong,int,void *)

- ea: `0x180015b9c`
- end: `0x180015bde`
- name: `?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z`
- size: `66`
- prototype: `unsigned int(cxl::Token *__hidden this, unsigned int, int, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001bffc`
- `0x18001f440`
- `0x1800202e4`
- `0x18005a3b4`

## callees

- `0x1800154e0`
- `0x180015b9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bcb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015bc1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015bc1`

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
0x180015b9c  push    rbx
0x180015b9e  push    rbp
0x180015b9f  push    rsi
0x180015ba0  push    rdi
0x180015ba1  sub     rsp, 28h
0x180015ba5  mov     rbp, r9
0x180015ba8  mov     edi, r8d
0x180015bab  mov     esi, edx
0x180015bad  mov     rbx, rcx
0x180015bb0  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x180015bb5  lea     r9, [rbx+8]; TokenHandle
0x180015bb9  mov     r8d, edi; OpenAsSelf
0x180015bbc  mov     edx, esi; DesiredAccess
0x180015bbe  mov     rcx, rbp; ThreadHandle
0x180015bc1  call    cs:__imp_OpenThreadToken
0x180015bc7  test    eax, eax
0x180015bc9  jnz     short loc_180015BD3
0x180015bcb  call    cs:__imp_GetLastError
0x180015bd1  jmp     short loc_180015BD5
0x180015bd3  xor     eax, eax
0x180015bd5  add     rsp, 28h
0x180015bd9  pop     rdi
0x180015bda  pop     rsi
0x180015bdb  pop     rbp
0x180015bdc  pop     rbx
0x180015bdd  retn
```
