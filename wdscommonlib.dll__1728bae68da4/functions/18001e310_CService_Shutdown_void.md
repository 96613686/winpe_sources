# CService::Shutdown(void)

- ea: `0x18001e310`
- end: `0x18001e38e`
- name: `?Shutdown@CService@@QEAAKXZ`
- size: `126`
- prototype: `unsigned int __fastcall(CService *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x18001dd50`
- `0x18001e140`

## callees

- `0x18001e310`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001e36c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e36c`
- `ADVAPI32!CloseServiceHandle` at `0x18001e33b`
- `ADVAPI32!CloseServiceHandle` at `0x18001e35a`
- `ADVAPI32!CloseServiceHandle` at `0x18001e33b`
- `ADVAPI32!CloseServiceHandle` at `0x18001e35a`

## pseudocode

```c
__int64 __fastcall CService::Shutdown(SC_HANDLE **this)
{
  SC_HANDLE *v1; // rdi
  unsigned int v2; // ebx
  SC_HANDLE *v4; // rdi

  v1 = *this;
  v2 = 0;
  if ( *this )
  {
    if ( *v1 )
    {
      CloseServiceHandle(*v1);
      *v1 = 0;
    }
    v4 = *this;
    if ( *this )
    {
      if ( *v4 )
      {
        CloseServiceHandle(*v4);
        *v4 = 0;
      }
      operator delete(v4);
    }
    *this = 0;
  }
  else
  {
    return 5023;
  }
  return v2;
}

```

## disassembly

```asm
0x18001e310  mov     [rsp+arg_0], rbx
0x18001e315  mov     [rsp+arg_8], rsi
0x18001e31a  push    rdi
0x18001e31b  sub     rsp, 20h
0x18001e31f  mov     rdi, [rcx]
0x18001e322  xor     ebx, ebx
0x18001e324  mov     rsi, rcx
0x18001e327  test    rdi, rdi
0x18001e32a  jnz     short loc_18001E333
0x18001e32c  mov     ebx, 139Fh
0x18001e331  jmp     short loc_18001E37B
0x18001e333  cmp     [rdi], rbx
0x18001e336  jz      short loc_18001E34A
0x18001e338  mov     rcx, [rdi]; hSCObject
0x18001e33b  call    cs:__imp_CloseServiceHandle
0x18001e342  nop     dword ptr [rax+rax+00h]
0x18001e347  mov     [rdi], rbx
0x18001e34a  mov     rdi, [rsi]
0x18001e34d  test    rdi, rdi
0x18001e350  jz      short loc_18001E378
0x18001e352  cmp     [rdi], rbx
0x18001e355  jz      short loc_18001E369
0x18001e357  mov     rcx, [rdi]; hSCObject
0x18001e35a  call    cs:__imp_CloseServiceHandle
0x18001e361  nop     dword ptr [rax+rax+00h]
0x18001e366  mov     [rdi], rbx
0x18001e369  mov     rcx, rdi
0x18001e36c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e373  nop     dword ptr [rax+rax+00h]
0x18001e378  mov     [rsi], rbx
0x18001e37b  mov     rsi, [rsp+28h+arg_8]
0x18001e380  mov     eax, ebx
0x18001e382  mov     rbx, [rsp+28h+arg_0]
0x18001e387  add     rsp, 20h
0x18001e38b  pop     rdi
0x18001e38c  retn
```
