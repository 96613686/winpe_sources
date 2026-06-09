# DeleteGroup

- ea: `0x180012bf0`
- end: `0x180012c29`
- name: `DeleteGroup`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f670`
- `0x180012bf0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeleteGroupWorker` at `0x180012c0d`
- `ext-ms-win-profile-userenv-l1-1-0!DeleteGroupWorker` at `0x180012c0d`

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
0x180012bf0  mov     [rsp+arg_0], rbx
0x180012bf5  push    rdi
0x180012bf6  sub     rsp, 20h
0x180012bfa  mov     ebx, edx
0x180012bfc  mov     rdi, rcx
0x180012bff  call    IsDeleteLinkFileWorkerPresent
0x180012c04  test    al, al
0x180012c06  jz      short loc_180012C1B
0x180012c08  mov     edx, ebx
0x180012c0a  mov     rcx, rdi
0x180012c0d  call    cs:__imp_DeleteGroupWorker
0x180012c14  nop     dword ptr [rax+rax+00h]
0x180012c19  jmp     short loc_180012C1D
0x180012c1b  xor     eax, eax
0x180012c1d  mov     rbx, [rsp+28h+arg_0]
0x180012c22  add     rsp, 20h
0x180012c26  pop     rdi
0x180012c27  retn
```
