# DeleteAppContainer

- ea: `0x180012bb0`
- end: `0x180012be2`
- name: `DeleteAppContainer`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f61c`
- `0x180012bb0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-2!DeleteAppContainerWorker` at `0x180012bca`

## pseudocode

```c
__int64 __fastcall DeleteAppContainer(__int64 a1)
{
  if ( (unsigned __int8)IsAddAppContainerAccessWorkerPresent() )
    return DeleteAppContainerWorker(a1);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180012bb0  push    rbx
0x180012bb2  sub     rsp, 20h
0x180012bb6  mov     rbx, rcx
0x180012bb9  call    IsAddAppContainerAccessWorkerPresent
0x180012bbe  test    al, al
0x180012bc0  jz      short loc_180012BD6
0x180012bc2  mov     rcx, rbx
0x180012bc5  add     rsp, 20h
0x180012bc9  pop     rbx
0x180012bca  jmp     cs:__imp_DeleteAppContainerWorker
0x180012bd6  mov     eax, 80004001h
0x180012bdb  add     rsp, 20h
0x180012bdf  pop     rbx
0x180012be0  retn
```
