# CWinsockInitializer::Shutdown(void)

- ea: `0x180027bf0`
- end: `0x180027c14`
- name: `?Shutdown@CWinsockInitializer@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(CWinsockInitializer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180027b20`

## callees

- `0x180027bf0`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x180027bfe`
- `WS2_32!__imp_WSACleanup` at `0x180027bfe`

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
0x180027bf0  push    rbx
0x180027bf2  sub     rsp, 20h
0x180027bf6  cmp     dword ptr [rcx], 0
0x180027bf9  mov     rbx, rcx
0x180027bfc  jz      short loc_180027C0D
0x180027bfe  call    cs:__imp_WSACleanup
0x180027c05  nop     dword ptr [rax+rax+00h]
0x180027c0a  and     dword ptr [rbx], 0
0x180027c0d  add     rsp, 20h
0x180027c11  pop     rbx
0x180027c12  retn
```
