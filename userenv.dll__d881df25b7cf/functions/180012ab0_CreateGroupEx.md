# CreateGroupEx

- ea: `0x180012ab0`
- end: `0x180012af2`
- name: `CreateGroupEx`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f670`
- `0x180012ab0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateGroupExWorker` at `0x180012ad8`
- `ext-ms-win-profile-userenv-l1-1-0!CreateGroupExWorker` at `0x180012ad8`

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
0x180012ab0  push    rbx
0x180012ab2  push    rbp
0x180012ab3  push    rsi
0x180012ab4  push    rdi
0x180012ab5  sub     rsp, 28h
0x180012ab9  mov     ebx, r9d
0x180012abc  mov     rdi, r8
0x180012abf  mov     esi, edx
0x180012ac1  mov     rbp, rcx
0x180012ac4  call    IsDeleteLinkFileWorkerPresent
0x180012ac9  test    al, al
0x180012acb  jz      short loc_180012AE6
0x180012acd  mov     r9d, ebx
0x180012ad0  mov     r8, rdi
0x180012ad3  mov     edx, esi
0x180012ad5  mov     rcx, rbp
0x180012ad8  call    cs:__imp_CreateGroupExWorker
0x180012adf  nop     dword ptr [rax+rax+00h]
0x180012ae4  jmp     short loc_180012AE8
0x180012ae6  xor     eax, eax
0x180012ae8  add     rsp, 28h
0x180012aec  pop     rdi
0x180012aed  pop     rsi
0x180012aee  pop     rbp
0x180012aef  pop     rbx
0x180012af0  retn
```
