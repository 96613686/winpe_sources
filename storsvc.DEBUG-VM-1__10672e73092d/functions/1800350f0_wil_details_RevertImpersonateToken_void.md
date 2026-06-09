# wil::details::RevertImpersonateToken(void *)

- ea: `0x1800350f0`
- end: `0x180035122`
- name: `?RevertImpersonateToken@details@wil@@YAXPEAX@Z`
- size: `50`
- prototype: `void __fastcall(HANDLE hObject, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180034a50`
- `0x180035688`

## callees

- `0x180013354`
- `0x1800350f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800350fe`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800350fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035116`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035116`

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
0x1800350f0  push    rbx
0x1800350f2  sub     rsp, 20h
0x1800350f6  mov     rbx, rcx
0x1800350f9  mov     rdx, rcx; Token
0x1800350fc  xor     ecx, ecx; Thread
0x1800350fe  call    cs:__imp_SetThreadToken
0x180035104  test    eax, eax
0x180035106  jnz     short loc_18003510E
0x180035108  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003510e  test    rbx, rbx
0x180035111  jz      short loc_18003511C
0x180035113  mov     rcx, rbx; hObject
0x180035116  call    cs:__imp_CloseHandle
0x18003511c  add     rsp, 20h
0x180035120  pop     rbx
0x180035121  retn
```
