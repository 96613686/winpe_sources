# DeleteAppContainerProfileInternal

- ea: `0x180008ba0`
- end: `0x180008bd5`
- name: `DeleteAppContainerProfileInternal`
- size: `53`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008b90`

## callees

- `0x180008ba0`
- `0x18000e9c0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeleteAppContainerProfileWorker` at `0x180008bbd`
- `ext-ms-win-profile-userenv-l1-1-0!DeleteAppContainerProfileWorker` at `0x180008bbd`

## pseudocode

```c
__int64 __fastcall DeleteAppContainerProfileInternal(__int64 a1, unsigned int a2)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return DeleteAppContainerProfileWorker(a1, a2);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180008ba0  mov     [rsp+arg_0], rbx
0x180008ba5  push    rdi
0x180008ba6  sub     rsp, 20h
0x180008baa  mov     ebx, edx
0x180008bac  mov     rdi, rcx
0x180008baf  call    IsDeleteLinkFileWorkerPresent
0x180008bb4  test    al, al
0x180008bb6  jz      short loc_180008BCE
0x180008bb8  mov     edx, ebx
0x180008bba  mov     rcx, rdi
0x180008bbd  call    cs:__imp_DeleteAppContainerProfileWorker
0x180008bc3  mov     rbx, [rsp+28h+arg_0]
0x180008bc8  add     rsp, 20h
0x180008bcc  pop     rdi
0x180008bcd  retn
0x180008bce  mov     eax, 80004001h
0x180008bd3  jmp     short loc_180008BC3
```
