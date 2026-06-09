# cxl::Token::TryOpenThreadToken(ulong,int,void *)

- ea: `0x180014878`
- end: `0x1800148c7`
- name: `?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z`
- size: `79`
- prototype: `unsigned int(cxl::Token *__hidden this, unsigned int, int, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800198ec`
- `0x18001dc2c`

## callees

- `0x180014620`
- `0x180014878`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148ad`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001489d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001489d`

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
0x180014878  push    rbx
0x18001487a  push    rbp
0x18001487b  push    rsi
0x18001487c  push    rdi
0x18001487d  sub     rsp, 28h
0x180014881  mov     rbp, r9
0x180014884  mov     edi, r8d
0x180014887  mov     esi, edx
0x180014889  mov     rbx, rcx
0x18001488c  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x180014891  lea     r9, [rbx+8]; TokenHandle
0x180014895  mov     r8d, edi; OpenAsSelf
0x180014898  mov     edx, esi; DesiredAccess
0x18001489a  mov     rcx, rbp; ThreadHandle
0x18001489d  call    cs:__imp_OpenThreadToken
0x1800148a4  nop     dword ptr [rax+rax+00h]
0x1800148a9  test    eax, eax
0x1800148ab  jnz     short loc_1800148BB
0x1800148ad  call    cs:__imp_GetLastError
0x1800148b4  nop     dword ptr [rax+rax+00h]
0x1800148b9  jmp     short loc_1800148BD
0x1800148bb  xor     eax, eax
0x1800148bd  add     rsp, 28h
0x1800148c1  pop     rdi
0x1800148c2  pop     rsi
0x1800148c3  pop     rbp
0x1800148c4  pop     rbx
0x1800148c5  retn
```
