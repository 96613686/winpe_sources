# CreateAppContainerFromPolicy

- ea: `0x1800129e0`
- end: `0x180012a2c`
- name: `CreateAppContainerFromPolicy`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f61c`
- `0x1800129e0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-2!CreateAppContainerFromPolicyWorker` at `0x180012a08`
- `ext-ms-win-profile-userenv-l1-1-2!CreateAppContainerFromPolicyWorker` at `0x180012a08`

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
0x1800129e0  mov     [rsp+arg_0], rbx
0x1800129e5  mov     [rsp+arg_8], rsi
0x1800129ea  push    rdi
0x1800129eb  sub     rsp, 20h
0x1800129ef  mov     rbx, r8
0x1800129f2  mov     edi, edx
0x1800129f4  mov     rsi, rcx
0x1800129f7  call    IsAddAppContainerAccessWorkerPresent
0x1800129fc  test    al, al
0x1800129fe  jz      short loc_180012A16
0x180012a00  mov     r8, rbx
0x180012a03  mov     edx, edi
0x180012a05  mov     rcx, rsi
0x180012a08  call    cs:__imp_CreateAppContainerFromPolicyWorker
0x180012a0f  nop     dword ptr [rax+rax+00h]
0x180012a14  jmp     short loc_180012A1B
0x180012a16  mov     eax, 80004001h
0x180012a1b  mov     rbx, [rsp+28h+arg_0]
0x180012a20  mov     rsi, [rsp+28h+arg_8]
0x180012a25  add     rsp, 20h
0x180012a29  pop     rdi
0x180012a2a  retn
```
