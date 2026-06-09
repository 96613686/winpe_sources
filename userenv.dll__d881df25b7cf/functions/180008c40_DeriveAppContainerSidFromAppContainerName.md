# DeriveAppContainerSidFromAppContainerName

- ea: `0x180008c40`
- end: `0x180008c7e`
- name: `DeriveAppContainerSidFromAppContainerName`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008c40`
- `0x18000f670`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeriveAppContainerSidFromAppContainerNameWorker` at `0x180008c5f`
- `ext-ms-win-profile-userenv-l1-1-0!DeriveAppContainerSidFromAppContainerNameWorker` at `0x180008c5f`

## pseudocode

```c
__int64 __fastcall DeriveAppContainerSidFromAppContainerName(__int64 a1, __int64 a2)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return DeriveAppContainerSidFromAppContainerNameWorker(a1, a2);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180008c40  mov     [rsp+arg_0], rbx
0x180008c45  push    rdi
0x180008c46  sub     rsp, 20h
0x180008c4a  mov     rbx, rdx
0x180008c4d  mov     rdi, rcx
0x180008c50  call    IsDeleteLinkFileWorkerPresent
0x180008c55  test    al, al
0x180008c57  jz      short loc_180008C77
0x180008c59  mov     rdx, rbx
0x180008c5c  mov     rcx, rdi
0x180008c5f  call    cs:__imp_DeriveAppContainerSidFromAppContainerNameWorker
0x180008c66  nop     dword ptr [rax+rax+00h]
0x180008c6b  mov     rbx, [rsp+28h+arg_0]
0x180008c70  add     rsp, 20h
0x180008c74  pop     rdi
0x180008c75  retn
0x180008c77  mov     eax, 80004001h
0x180008c7c  jmp     short loc_180008C6B
```
