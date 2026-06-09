# cxl::Token::TryOpenThreadToken(ulong,int,void *)

- ea: `0x180016300`
- end: `0x18001634f`
- name: `?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z`
- size: `79`
- prototype: `unsigned int(cxl::Token *__hidden this, unsigned int, int, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001cabc`
- `0x18002006c`
- `0x180020f6c`
- `0x18005b4b4`

## callees

- `0x180015be4`
- `0x180016300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016335`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016325`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016325`

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
0x180016300  push    rbx
0x180016302  push    rbp
0x180016303  push    rsi
0x180016304  push    rdi
0x180016305  sub     rsp, 28h
0x180016309  mov     rbp, r9
0x18001630c  mov     edi, r8d
0x18001630f  mov     esi, edx
0x180016311  mov     rbx, rcx
0x180016314  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x180016319  lea     r9, [rbx+8]; TokenHandle
0x18001631d  mov     r8d, edi; OpenAsSelf
0x180016320  mov     edx, esi; DesiredAccess
0x180016322  mov     rcx, rbp; ThreadHandle
0x180016325  call    cs:__imp_OpenThreadToken
0x18001632c  nop     dword ptr [rax+rax+00h]
0x180016331  test    eax, eax
0x180016333  jnz     short loc_180016343
0x180016335  call    cs:__imp_GetLastError
0x18001633c  nop     dword ptr [rax+rax+00h]
0x180016341  jmp     short loc_180016345
0x180016343  xor     eax, eax
0x180016345  add     rsp, 28h
0x180016349  pop     rdi
0x18001634a  pop     rsi
0x18001634b  pop     rbp
0x18001634c  pop     rbx
0x18001634d  retn
```
