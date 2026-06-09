# DeleteLinkFile

- ea: `0x180011ca0`
- end: `0x180011cdb`
- name: `DeleteLinkFile`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000e9c0`
- `0x180011ca0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeleteLinkFileWorker` at `0x180011cc8`
- `ext-ms-win-profile-userenv-l1-1-0!DeleteLinkFileWorker` at `0x180011cc8`

## pseudocode

```c
__int64 __fastcall DeleteLinkFile(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return DeleteLinkFileWorker(a1, a2, a3, a4);
  else
    return 0;
}

```

## disassembly

```asm
0x180011ca0  push    rbx
0x180011ca2  push    rbp
0x180011ca3  push    rsi
0x180011ca4  push    rdi
0x180011ca5  sub     rsp, 28h
0x180011ca9  mov     ebx, r9d
0x180011cac  mov     rdi, r8
0x180011caf  mov     rsi, rdx
0x180011cb2  mov     ebp, ecx
0x180011cb4  call    IsDeleteLinkFileWorkerPresent
0x180011cb9  test    al, al
0x180011cbb  jz      short loc_180011CD0
0x180011cbd  mov     r9d, ebx
0x180011cc0  mov     r8, rdi
0x180011cc3  mov     rdx, rsi
0x180011cc6  mov     ecx, ebp
0x180011cc8  call    cs:__imp_DeleteLinkFileWorker
0x180011cce  jmp     short loc_180011CD2
0x180011cd0  xor     eax, eax
0x180011cd2  add     rsp, 28h
0x180011cd6  pop     rdi
0x180011cd7  pop     rsi
0x180011cd8  pop     rbp
0x180011cd9  pop     rbx
0x180011cda  retn
```
