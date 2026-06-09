# AddAppContainerAccess

- ea: `0x180012930`
- end: `0x180012977`
- name: `AddAppContainerAccess`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f61c`
- `0x180012930`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-2!AddAppContainerAccessWorker` at `0x18001295a`
- `ext-ms-win-profile-userenv-l1-1-2!AddAppContainerAccessWorker` at `0x18001295a`

## pseudocode

```c
__int64 __fastcall AddAppContainerAccess(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  if ( (unsigned __int8)IsAddAppContainerAccessWorkerPresent() )
    return AddAppContainerAccessWorker(a1, a2, a3, a4);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180012930  push    rbx
0x180012932  push    rbp
0x180012933  push    rsi
0x180012934  push    rdi
0x180012935  sub     rsp, 28h
0x180012939  mov     ebx, r9d
0x18001293c  mov     edi, r8d
0x18001293f  mov     rsi, rdx
0x180012942  mov     rbp, rcx
0x180012945  call    IsAddAppContainerAccessWorkerPresent
0x18001294a  test    al, al
0x18001294c  jz      short loc_180012968
0x18001294e  mov     r9d, ebx
0x180012951  mov     r8d, edi
0x180012954  mov     rdx, rsi
0x180012957  mov     rcx, rbp
0x18001295a  call    cs:__imp_AddAppContainerAccessWorker
0x180012961  nop     dword ptr [rax+rax+00h]
0x180012966  jmp     short loc_18001296D
0x180012968  mov     eax, 80004001h
0x18001296d  add     rsp, 28h
0x180012971  pop     rdi
0x180012972  pop     rsi
0x180012973  pop     rbp
0x180012974  pop     rbx
0x180012975  retn
```
