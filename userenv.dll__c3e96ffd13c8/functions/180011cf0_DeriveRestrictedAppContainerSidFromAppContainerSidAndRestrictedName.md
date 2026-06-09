# DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedName

- ea: `0x180011cf0`
- end: `0x180011d37`
- name: `DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedName`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000e9c0`
- `0x180011cf0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker` at `0x180011d1a`
- `ext-ms-win-profile-userenv-l1-1-0!DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker` at `0x180011d1a`

## pseudocode

```c
__int64 __fastcall DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedName(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker(a1, a2, a3);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180011cf0  mov     [rsp+arg_0], rbx
0x180011cf5  mov     [rsp+arg_8], rsi
0x180011cfa  push    rdi
0x180011cfb  sub     rsp, 20h
0x180011cff  mov     rbx, r8
0x180011d02  mov     rdi, rdx
0x180011d05  mov     rsi, rcx
0x180011d08  call    IsDeleteLinkFileWorkerPresent
0x180011d0d  test    al, al
0x180011d0f  jz      short loc_180011D22
0x180011d11  mov     r8, rbx
0x180011d14  mov     rdx, rdi
0x180011d17  mov     rcx, rsi
0x180011d1a  call    cs:__imp_DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker
0x180011d20  jmp     short loc_180011D27
0x180011d22  mov     eax, 80004001h
0x180011d27  mov     rbx, [rsp+28h+arg_0]
0x180011d2c  mov     rsi, [rsp+28h+arg_8]
0x180011d31  add     rsp, 20h
0x180011d35  pop     rdi
0x180011d36  retn
```
