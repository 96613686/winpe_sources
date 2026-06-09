# DeleteAppContainerProfileInternal

- ea: `0x180009420`
- end: `0x18000945c`
- name: `DeleteAppContainerProfileInternal`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009410`

## callees

- `0x180009420`
- `0x18000f670`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeleteAppContainerProfileWorker` at `0x18000943d`
- `ext-ms-win-profile-userenv-l1-1-0!DeleteAppContainerProfileWorker` at `0x18000943d`

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
0x180009420  mov     [rsp+arg_0], rbx
0x180009425  push    rdi
0x180009426  sub     rsp, 20h
0x18000942a  mov     ebx, edx
0x18000942c  mov     rdi, rcx
0x18000942f  call    IsDeleteLinkFileWorkerPresent
0x180009434  test    al, al
0x180009436  jz      short loc_180009455
0x180009438  mov     edx, ebx
0x18000943a  mov     rcx, rdi
0x18000943d  call    cs:__imp_DeleteAppContainerProfileWorker
0x180009444  nop     dword ptr [rax+rax+00h]
0x180009449  mov     rbx, [rsp+28h+arg_0]
0x18000944e  add     rsp, 20h
0x180009452  pop     rdi
0x180009453  retn
0x180009455  mov     eax, 80004001h
0x18000945a  jmp     short loc_180009449
```
