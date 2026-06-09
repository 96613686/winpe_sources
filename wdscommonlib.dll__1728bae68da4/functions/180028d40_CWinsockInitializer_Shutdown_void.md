# CWinsockInitializer::Shutdown(void)

- ea: `0x180028d40`
- end: `0x180028d64`
- name: `?Shutdown@CWinsockInitializer@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(CWinsockInitializer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180028c70`

## callees

- `0x180028d40`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x180028d4e`
- `WS2_32!__imp_WSACleanup` at `0x180028d4e`

## pseudocode

```c
void __fastcall CWinsockInitializer::Shutdown(CWinsockInitializer *this)
{
  if ( *(_DWORD *)this )
  {
    WSACleanup();
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180028d40  push    rbx
0x180028d42  sub     rsp, 20h
0x180028d46  cmp     dword ptr [rcx], 0
0x180028d49  mov     rbx, rcx
0x180028d4c  jz      short loc_180028D5D
0x180028d4e  call    cs:__imp_WSACleanup
0x180028d55  nop     dword ptr [rax+rax+00h]
0x180028d5a  and     dword ptr [rbx], 0
0x180028d5d  add     rsp, 20h
0x180028d61  pop     rbx
0x180028d62  retn
```
