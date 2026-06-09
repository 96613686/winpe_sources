# GetAppContainerRegistryLocation

- ea: `0x180008bf0`
- end: `0x180008c2c`
- name: `GetAppContainerRegistryLocation`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008bf0`
- `0x18000f670`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!GetAppContainerRegistryLocationWorker` at `0x180008c0d`
- `ext-ms-win-profile-userenv-l1-1-0!GetAppContainerRegistryLocationWorker` at `0x180008c0d`

## pseudocode

```c
__int64 __fastcall GetAppContainerRegistryLocation(unsigned int a1, __int64 a2)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return GetAppContainerRegistryLocationWorker(a1, a2);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180008bf0  mov     [rsp+arg_0], rbx
0x180008bf5  push    rdi
0x180008bf6  sub     rsp, 20h
0x180008bfa  mov     rbx, rdx
0x180008bfd  mov     edi, ecx
0x180008bff  call    IsDeleteLinkFileWorkerPresent
0x180008c04  test    al, al
0x180008c06  jz      short loc_180008C25
0x180008c08  mov     rdx, rbx
0x180008c0b  mov     ecx, edi
0x180008c0d  call    cs:__imp_GetAppContainerRegistryLocationWorker
0x180008c14  nop     dword ptr [rax+rax+00h]
0x180008c19  mov     rbx, [rsp+28h+arg_0]
0x180008c1e  add     rsp, 20h
0x180008c22  pop     rdi
0x180008c23  retn
0x180008c25  mov     eax, 80004001h
0x180008c2a  jmp     short loc_180008C19
```
