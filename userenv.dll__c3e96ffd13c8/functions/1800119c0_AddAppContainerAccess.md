# AddAppContainerAccess

- ea: `0x1800119c0`
- end: `0x180011a00`
- name: `AddAppContainerAccess`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e96c`
- `0x1800119c0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-2!AddAppContainerAccessWorker` at `0x1800119ea`
- `ext-ms-win-profile-userenv-l1-1-2!AddAppContainerAccessWorker` at `0x1800119ea`

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
0x1800119c0  push    rbx
0x1800119c2  push    rbp
0x1800119c3  push    rsi
0x1800119c4  push    rdi
0x1800119c5  sub     rsp, 28h
0x1800119c9  mov     ebx, r9d
0x1800119cc  mov     edi, r8d
0x1800119cf  mov     rsi, rdx
0x1800119d2  mov     rbp, rcx
0x1800119d5  call    IsAddAppContainerAccessWorkerPresent
0x1800119da  test    al, al
0x1800119dc  jz      short loc_1800119F2
0x1800119de  mov     r9d, ebx
0x1800119e1  mov     r8d, edi
0x1800119e4  mov     rdx, rsi
0x1800119e7  mov     rcx, rbp
0x1800119ea  call    cs:__imp_AddAppContainerAccessWorker
0x1800119f0  jmp     short loc_1800119F7
0x1800119f2  mov     eax, 80004001h
0x1800119f7  add     rsp, 28h
0x1800119fb  pop     rdi
0x1800119fc  pop     rsi
0x1800119fd  pop     rbp
0x1800119fe  pop     rbx
0x1800119ff  retn
```
