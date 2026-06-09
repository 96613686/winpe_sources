# CreateAppContainerFromPolicy

- ea: `0x180011a60`
- end: `0x180011aa5`
- name: `CreateAppContainerFromPolicy`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000e96c`
- `0x180011a60`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-2!CreateAppContainerFromPolicyWorker` at `0x180011a88`
- `ext-ms-win-profile-userenv-l1-1-2!CreateAppContainerFromPolicyWorker` at `0x180011a88`

## pseudocode

```c
__int64 __fastcall CreateAppContainerFromPolicy(__int64 a1, unsigned int a2, __int64 a3)
{
  if ( (unsigned __int8)IsAddAppContainerAccessWorkerPresent() )
    return CreateAppContainerFromPolicyWorker(a1, a2, a3);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180011a60  mov     [rsp+arg_0], rbx
0x180011a65  mov     [rsp+arg_8], rsi
0x180011a6a  push    rdi
0x180011a6b  sub     rsp, 20h
0x180011a6f  mov     rbx, r8
0x180011a72  mov     edi, edx
0x180011a74  mov     rsi, rcx
0x180011a77  call    IsAddAppContainerAccessWorkerPresent
0x180011a7c  test    al, al
0x180011a7e  jz      short loc_180011A90
0x180011a80  mov     r8, rbx
0x180011a83  mov     edx, edi
0x180011a85  mov     rcx, rsi
0x180011a88  call    cs:__imp_CreateAppContainerFromPolicyWorker
0x180011a8e  jmp     short loc_180011A95
0x180011a90  mov     eax, 80004001h
0x180011a95  mov     rbx, [rsp+28h+arg_0]
0x180011a9a  mov     rsi, [rsp+28h+arg_8]
0x180011a9f  add     rsp, 20h
0x180011aa3  pop     rdi
0x180011aa4  retn
```
