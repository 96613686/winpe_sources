# wil::details::RevertImpersonateToken(void *)

- ea: `0x1800154a4`
- end: `0x1800154e3`
- name: `?RevertImpersonateToken@details@wil@@YAXPEAX@Z`
- size: `63`
- prototype: `void __fastcall(HANDLE hObject, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180015420`
- `0x180015544`

## callees

- `0x180012780`
- `0x1800154a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800154b2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800154b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800154d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800154d0`

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
0x1800154a4  push    rbx
0x1800154a6  sub     rsp, 20h
0x1800154aa  mov     rbx, rcx
0x1800154ad  mov     rdx, rcx; Token
0x1800154b0  xor     ecx, ecx; Thread
0x1800154b2  call    cs:__imp_SetThreadToken
0x1800154b9  nop     dword ptr [rax+rax+00h]
0x1800154be  test    eax, eax
0x1800154c0  jnz     short loc_1800154C8
0x1800154c2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800154c8  test    rbx, rbx
0x1800154cb  jz      short loc_1800154DC
0x1800154cd  mov     rcx, rbx; hObject
0x1800154d0  call    cs:__imp_CloseHandle
0x1800154d7  nop     dword ptr [rax+rax+00h]
0x1800154dc  add     rsp, 20h
0x1800154e0  pop     rbx
0x1800154e1  retn
```
