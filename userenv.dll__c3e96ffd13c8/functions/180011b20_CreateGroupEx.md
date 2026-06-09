# CreateGroupEx

- ea: `0x180011b20`
- end: `0x180011b5b`
- name: `CreateGroupEx`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000e9c0`
- `0x180011b20`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateGroupExWorker` at `0x180011b48`
- `ext-ms-win-profile-userenv-l1-1-0!CreateGroupExWorker` at `0x180011b48`

## pseudocode

```c
__int64 __fastcall CreateGroupEx(__int64 a1, unsigned int a2, __int64 a3, unsigned int a4)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return CreateGroupExWorker(a1, a2, a3, a4);
  else
    return 0;
}

```

## disassembly

```asm
0x180011b20  push    rbx
0x180011b22  push    rbp
0x180011b23  push    rsi
0x180011b24  push    rdi
0x180011b25  sub     rsp, 28h
0x180011b29  mov     ebx, r9d
0x180011b2c  mov     rdi, r8
0x180011b2f  mov     esi, edx
0x180011b31  mov     rbp, rcx
0x180011b34  call    IsDeleteLinkFileWorkerPresent
0x180011b39  test    al, al
0x180011b3b  jz      short loc_180011B50
0x180011b3d  mov     r9d, ebx
0x180011b40  mov     r8, rdi
0x180011b43  mov     edx, esi
0x180011b45  mov     rcx, rbp
0x180011b48  call    cs:__imp_CreateGroupExWorker
0x180011b4e  jmp     short loc_180011B52
0x180011b50  xor     eax, eax
0x180011b52  add     rsp, 28h
0x180011b56  pop     rdi
0x180011b57  pop     rsi
0x180011b58  pop     rbp
0x180011b59  pop     rbx
0x180011b5a  retn
```
