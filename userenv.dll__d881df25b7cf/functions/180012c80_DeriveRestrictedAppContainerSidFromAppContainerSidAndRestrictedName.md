# DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedName

- ea: `0x180012c80`
- end: `0x180012cce`
- name: `DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedName`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000f670`
- `0x180012c80`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker` at `0x180012caa`
- `ext-ms-win-profile-userenv-l1-1-0!DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker` at `0x180012caa`

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
0x180012c80  mov     [rsp+arg_0], rbx
0x180012c85  mov     [rsp+arg_8], rsi
0x180012c8a  push    rdi
0x180012c8b  sub     rsp, 20h
0x180012c8f  mov     rbx, r8
0x180012c92  mov     rdi, rdx
0x180012c95  mov     rsi, rcx
0x180012c98  call    IsDeleteLinkFileWorkerPresent
0x180012c9d  test    al, al
0x180012c9f  jz      short loc_180012CB8
0x180012ca1  mov     r8, rbx
0x180012ca4  mov     rdx, rdi
0x180012ca7  mov     rcx, rsi
0x180012caa  call    cs:__imp_DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker
0x180012cb1  nop     dword ptr [rax+rax+00h]
0x180012cb6  jmp     short loc_180012CBD
0x180012cb8  mov     eax, 80004001h
0x180012cbd  mov     rbx, [rsp+28h+arg_0]
0x180012cc2  mov     rsi, [rsp+28h+arg_8]
0x180012cc7  add     rsp, 20h
0x180012ccb  pop     rdi
0x180012ccc  retn
```
