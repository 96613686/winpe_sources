# DeleteGroup

- ea: `0x180011c60`
- end: `0x180011c92`
- name: `DeleteGroup`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000e9c0`
- `0x180011c60`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeleteGroupWorker` at `0x180011c7d`
- `ext-ms-win-profile-userenv-l1-1-0!DeleteGroupWorker` at `0x180011c7d`

## pseudocode

```c
__int64 __fastcall DeleteGroup(__int64 a1, unsigned int a2)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return DeleteGroupWorker(a1, a2);
  else
    return 0;
}

```

## disassembly

```asm
0x180011c60  mov     [rsp+arg_0], rbx
0x180011c65  push    rdi
0x180011c66  sub     rsp, 20h
0x180011c6a  mov     ebx, edx
0x180011c6c  mov     rdi, rcx
0x180011c6f  call    IsDeleteLinkFileWorkerPresent
0x180011c74  test    al, al
0x180011c76  jz      short loc_180011C85
0x180011c78  mov     edx, ebx
0x180011c7a  mov     rcx, rdi
0x180011c7d  call    cs:__imp_DeleteGroupWorker
0x180011c83  jmp     short loc_180011C87
0x180011c85  xor     eax, eax
0x180011c87  mov     rbx, [rsp+28h+arg_0]
0x180011c8c  add     rsp, 20h
0x180011c90  pop     rdi
0x180011c91  retn
```
