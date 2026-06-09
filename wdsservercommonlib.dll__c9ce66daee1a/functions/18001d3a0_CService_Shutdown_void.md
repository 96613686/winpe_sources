# CService::Shutdown(void)

- ea: `0x18001d3a0`
- end: `0x18001d417`
- name: `?Shutdown@CService@@QEAAKXZ`
- size: `119`
- prototype: `unsigned int __fastcall(CService *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18001cdf0`
- `0x18001d1d0`

## callees

- `0x18001d3a0`
- `0x18002e468`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x18001d3cb`
- `ADVAPI32!CloseServiceHandle` at `0x18001d3ea`
- `ADVAPI32!CloseServiceHandle` at `0x18001d3cb`
- `ADVAPI32!CloseServiceHandle` at `0x18001d3ea`

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
0x18001d3a0  mov     [rsp+arg_0], rbx
0x18001d3a5  mov     [rsp+arg_8], rsi
0x18001d3aa  push    rdi
0x18001d3ab  sub     rsp, 20h
0x18001d3af  mov     rdi, [rcx]
0x18001d3b2  xor     ebx, ebx
0x18001d3b4  mov     rsi, rcx
0x18001d3b7  test    rdi, rdi
0x18001d3ba  jnz     short loc_18001D3C3
0x18001d3bc  mov     ebx, 139Fh
0x18001d3c1  jmp     short loc_18001D404
0x18001d3c3  cmp     [rdi], rbx
0x18001d3c6  jz      short loc_18001D3DA
0x18001d3c8  mov     rcx, [rdi]; hSCObject
0x18001d3cb  call    cs:__imp_CloseServiceHandle
0x18001d3d2  nop     dword ptr [rax+rax+00h]
0x18001d3d7  mov     [rdi], rbx
0x18001d3da  mov     rdi, [rsi]
0x18001d3dd  test    rdi, rdi
0x18001d3e0  jz      short loc_18001D401
0x18001d3e2  cmp     [rdi], rbx
0x18001d3e5  jz      short loc_18001D3F9
0x18001d3e7  mov     rcx, [rdi]; hSCObject
0x18001d3ea  call    cs:__imp_CloseServiceHandle
0x18001d3f1  nop     dword ptr [rax+rax+00h]
0x18001d3f6  mov     [rdi], rbx
0x18001d3f9  mov     rcx, rdi; lpMem
0x18001d3fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d401  mov     [rsi], rbx
0x18001d404  mov     rsi, [rsp+28h+arg_8]
0x18001d409  mov     eax, ebx
0x18001d40b  mov     rbx, [rsp+28h+arg_0]
0x18001d410  add     rsp, 20h
0x18001d414  pop     rdi
0x18001d415  retn
```
