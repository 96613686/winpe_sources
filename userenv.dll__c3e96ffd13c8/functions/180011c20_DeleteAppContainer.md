# DeleteAppContainer

- ea: `0x180011c20`
- end: `0x180011c4c`
- name: `DeleteAppContainer`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e96c`
- `0x180011c20`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-2!DeleteAppContainerWorker` at `0x180011c3a`

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
0x180011c20  push    rbx
0x180011c22  sub     rsp, 20h
0x180011c26  mov     rbx, rcx
0x180011c29  call    IsAddAppContainerAccessWorkerPresent
0x180011c2e  test    al, al
0x180011c30  jz      short loc_180011C41
0x180011c32  mov     rcx, rbx
0x180011c35  add     rsp, 20h
0x180011c39  pop     rbx
0x180011c3a  jmp     cs:__imp_DeleteAppContainerWorker
0x180011c41  mov     eax, 80004001h
0x180011c46  add     rsp, 20h
0x180011c4a  pop     rbx
0x180011c4b  retn
```
