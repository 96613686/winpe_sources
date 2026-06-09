# CAutoImpersonate::ResetImpersonation(void)

- ea: `0x18001aa28`
- end: `0x18001aa79`
- name: `?ResetImpersonation@CAutoImpersonate@@QEAAXXZ`
- size: `81`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a6a0`

## callees

- `0x18000cfc4`
- `0x18001aa28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001aa3c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001aa3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aa62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aa62`

## string_xrefs

- `0x18001aa4b`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAutoImpersonate::ResetImpersonation(HANDLE *this)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_BYTE *)this + 8) )
  {
    if ( !SetThreadToken(0, *this) )
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
        v2);
    if ( *this )
      CloseHandle(*this);
    *this = 0;
    *((_BYTE *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x18001aa28  push    rbx
0x18001aa2a  sub     rsp, 20h
0x18001aa2e  cmp     byte ptr [rcx+8], 0
0x18001aa32  mov     rbx, rcx
0x18001aa35  jz      short loc_18001AA73
0x18001aa37  mov     rdx, [rcx]; Token
0x18001aa3a  xor     ecx, ecx; Thread
0x18001aa3c  call    cs:__imp_SetThreadToken
0x18001aa42  test    eax, eax
0x18001aa44  jnz     short loc_18001AA5A
0x18001aa46  mov     rcx, [rsp+28h]; this
0x18001aa4b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001aa52  lea     edx, [rax+4Fh]; void *
0x18001aa55  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001aa5a  mov     rcx, [rbx]; hObject
0x18001aa5d  test    rcx, rcx
0x18001aa60  jz      short loc_18001AA68
0x18001aa62  call    cs:__imp_CloseHandle
0x18001aa68  mov     qword ptr [rbx], 0
0x18001aa6f  mov     byte ptr [rbx+8], 0
0x18001aa73  add     rsp, 20h
0x18001aa77  pop     rbx
0x18001aa78  retn
```
