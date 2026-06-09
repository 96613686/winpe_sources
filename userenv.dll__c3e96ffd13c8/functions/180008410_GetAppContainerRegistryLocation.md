# GetAppContainerRegistryLocation

- ea: `0x180008410`
- end: `0x180008445`
- name: `GetAppContainerRegistryLocation`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008410`
- `0x18000e9c0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!GetAppContainerRegistryLocationWorker` at `0x18000842d`
- `ext-ms-win-profile-userenv-l1-1-0!GetAppContainerRegistryLocationWorker` at `0x18000842d`

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
0x180008410  mov     [rsp+arg_0], rbx
0x180008415  push    rdi
0x180008416  sub     rsp, 20h
0x18000841a  mov     rbx, rdx
0x18000841d  mov     edi, ecx
0x18000841f  call    IsDeleteLinkFileWorkerPresent
0x180008424  test    al, al
0x180008426  jz      short loc_18000843E
0x180008428  mov     rdx, rbx
0x18000842b  mov     ecx, edi
0x18000842d  call    cs:__imp_GetAppContainerRegistryLocationWorker
0x180008433  mov     rbx, [rsp+28h+arg_0]
0x180008438  add     rsp, 20h
0x18000843c  pop     rdi
0x18000843d  retn
0x18000843e  mov     eax, 80004001h
0x180008443  jmp     short loc_180008433
```
