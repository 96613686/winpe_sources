# wil::details::RevertImpersonateToken(void *)

- ea: `0x180014328`
- end: `0x18001435a`
- name: `?RevertImpersonateToken@details@wil@@YAXPEAX@Z`
- size: `50`
- prototype: `void __fastcall(HANDLE hObject, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800142ac`
- `0x1800143b0`

## callees

- `0x18001182c`
- `0x180014328`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180014336`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180014336`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001434e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001434e`

## pseudocode

```c
void __fastcall wil::details::RevertImpersonateToken(HANDLE hObject, void *a2)
{
  wil::details::in1diag3 *v3; // rcx

  if ( !SetThreadToken(0, hObject) )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x180014328  push    rbx
0x18001432a  sub     rsp, 20h
0x18001432e  mov     rbx, rcx
0x180014331  mov     rdx, rcx; Token
0x180014334  xor     ecx, ecx; Thread
0x180014336  call    cs:__imp_SetThreadToken
0x18001433c  test    eax, eax
0x18001433e  jnz     short loc_180014346
0x180014340  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180014346  test    rbx, rbx
0x180014349  jz      short loc_180014354
0x18001434b  mov     rcx, rbx; hObject
0x18001434e  call    cs:__imp_CloseHandle
0x180014354  add     rsp, 20h
0x180014358  pop     rbx
0x180014359  retn
```
