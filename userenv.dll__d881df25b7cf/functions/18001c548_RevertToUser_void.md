# RevertToUser(void * *)

- ea: `0x18001c548`
- end: `0x18001c5c8`
- name: `?RevertToUser@@YAJPEAPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c51c`

## callees

- `0x18000dc30`
- `0x18001c548`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001c55a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001c55a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c588`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c5a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c588`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c5a7`

## string_xrefs

- `0x18001c56f`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
__int64 __fastcall RevertToUser(void **a1)
{
  const char *v2; // r9
  unsigned int LastError; // edi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( SetThreadToken(0, *a1) )
  {
    if ( *a1 )
    {
      CloseHandle(*a1);
      *a1 = 0;
    }
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4F,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
                  v2);
    if ( *a1 )
    {
      CloseHandle(*a1);
      *a1 = 0;
    }
    return LastError;
  }
}

```

## disassembly

```asm
0x18001c548  mov     [rsp+arg_0], rbx
0x18001c54d  push    rdi
0x18001c54e  sub     rsp, 20h
0x18001c552  mov     rdx, [rcx]; Token
0x18001c555  mov     rbx, rcx
0x18001c558  xor     ecx, ecx; Thread
0x18001c55a  call    cs:__imp_SetThreadToken
0x18001c561  nop     dword ptr [rax+rax+00h]
0x18001c566  test    eax, eax
0x18001c568  jnz     short loc_18001C59F
0x18001c56a  mov     rcx, [rsp+28h]; this
0x18001c56f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001c576  lea     edx, [rax+4Fh]; void *
0x18001c579  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c57e  mov     rcx, [rbx]; hObject
0x18001c581  mov     edi, eax
0x18001c583  test    rcx, rcx
0x18001c586  jz      short loc_18001C59B
0x18001c588  call    cs:__imp_CloseHandle
0x18001c58f  nop     dword ptr [rax+rax+00h]
0x18001c594  mov     qword ptr [rbx], 0
0x18001c59b  mov     eax, edi
0x18001c59d  jmp     short loc_18001C5BC
0x18001c59f  mov     rcx, [rbx]; hObject
0x18001c5a2  test    rcx, rcx
0x18001c5a5  jz      short loc_18001C5BA
0x18001c5a7  call    cs:__imp_CloseHandle
0x18001c5ae  nop     dword ptr [rax+rax+00h]
0x18001c5b3  mov     qword ptr [rbx], 0
0x18001c5ba  xor     eax, eax
0x18001c5bc  mov     rbx, [rsp+28h+arg_0]
0x18001c5c1  add     rsp, 20h
0x18001c5c5  pop     rdi
0x18001c5c6  retn
```
