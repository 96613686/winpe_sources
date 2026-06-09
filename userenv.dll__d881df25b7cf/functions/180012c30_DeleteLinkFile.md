# DeleteLinkFile

- ea: `0x180012c30`
- end: `0x180012c72`
- name: `DeleteLinkFile`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f670`
- `0x180012c30`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeleteLinkFileWorker` at `0x180012c58`
- `ext-ms-win-profile-userenv-l1-1-0!DeleteLinkFileWorker` at `0x180012c58`

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
0x180012c30  push    rbx
0x180012c32  push    rbp
0x180012c33  push    rsi
0x180012c34  push    rdi
0x180012c35  sub     rsp, 28h
0x180012c39  mov     ebx, r9d
0x180012c3c  mov     rdi, r8
0x180012c3f  mov     rsi, rdx
0x180012c42  mov     ebp, ecx
0x180012c44  call    IsDeleteLinkFileWorkerPresent
0x180012c49  test    al, al
0x180012c4b  jz      short loc_180012C66
0x180012c4d  mov     r9d, ebx
0x180012c50  mov     r8, rdi
0x180012c53  mov     rdx, rsi
0x180012c56  mov     ecx, ebp
0x180012c58  call    cs:__imp_DeleteLinkFileWorker
0x180012c5f  nop     dword ptr [rax+rax+00h]
0x180012c64  jmp     short loc_180012C68
0x180012c66  xor     eax, eax
0x180012c68  add     rsp, 28h
0x180012c6c  pop     rdi
0x180012c6d  pop     rsi
0x180012c6e  pop     rbp
0x180012c6f  pop     rbx
0x180012c70  retn
```
