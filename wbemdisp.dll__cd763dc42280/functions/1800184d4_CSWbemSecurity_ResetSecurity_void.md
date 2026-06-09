# CSWbemSecurity::ResetSecurity(void *)

- ea: `0x1800184d4`
- end: `0x180018514`
- name: `?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z`
- size: `64`
- prototype: `void __fastcall(CSWbemSecurity *__hidden this, void *)`
- caller_count: `33`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800012b0`
- `0x180001e14`
- `0x180001f70`
- `0x1800023b0`
- `0x180002610`
- `0x1800028b0`
- `0x1800031b0`
- `0x180003420`
- `0x180008230`
- `0x180008800`
- `0x18001710c`
- `0x18001d250`
- `0x18001d490`
- `0x18001d630`
- `0x18001d830`
- `0x18001dc50`
- `0x18001e010`
- `0x18001e260`
- `0x18001f270`
- `0x1800296a0`
- `0x1800298b0`
- `0x180029a70`
- `0x180029c10`
- `0x180029d90`
- `0x180029f10`
- `0x18002a090`
- `0x18002a200`
- `0x18002a4e0`
- `0x18002a6d0`
- `0x18002abf0`
- `0x18002b880`
- `0x18002c860`
- `0x18002cb20`

## callees

- `0x1800184d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001850c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001850c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800184ee`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800184ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018505`

## pseudocode

```c
void __fastcall CSWbemSecurity::ResetSecurity(CSWbemSecurity *this, void *a2)
{
  if ( CSWbemSecurity::s_bIsNT )
  {
    if ( !SetThreadToken(0, a2) )
      GetLastError();
    if ( a2 )
      CloseHandle(a2);
  }
}

```

## disassembly

```asm
0x1800184d4  push    rbx
0x1800184d6  sub     rsp, 20h
0x1800184da  cmp     cs:?s_bIsNT@CSWbemSecurity@@0_NA, 0; bool CSWbemSecurity::s_bIsNT
0x1800184e1  mov     rbx, rdx
0x1800184e4  jnz     short loc_1800184EC
0x1800184e6  add     rsp, 20h
0x1800184ea  pop     rbx
0x1800184eb  retn
0x1800184ec  xor     ecx, ecx; Thread
0x1800184ee  call    cs:__imp_SetThreadToken
0x1800184f4  test    eax, eax
0x1800184f6  jz      short loc_18001850C
0x1800184f8  test    rbx, rbx
0x1800184fb  jz      short loc_1800184E6
0x1800184fd  mov     rcx, rbx
0x180018500  add     rsp, 20h
0x180018504  pop     rbx
0x180018505  jmp     cs:__imp_CloseHandle
0x18001850c  call    cs:__imp_GetLastError
0x180018512  jmp     short loc_1800184F8
```
