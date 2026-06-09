# WbemCoImpersonateClient(void)

- ea: `0x180007ca8`
- end: `0x180007cfb`
- name: `?WbemCoImpersonateClient@@YAJXZ`
- size: `83`
- prototype: `__int64(void)`
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800042f0`
- `0x1800043c0`
- `0x180006524`
- `0x180007100`
- `0x180007b50`
- `0x18000dfd0`
- `0x18000e2b0`
- `0x18000e5a0`
- `0x18000e750`

## callees

- `0x180007ca8`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180007cc3`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180007cc3`

## pseudocode

```c
__int64 WbemCoImpersonateClient(void)
{
  unsigned int v0; // ebx
  void *ppInterface; // [rsp+30h] [rbp+8h] BYREF

  ppInterface = 0;
  v0 = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
  if ( !v0 )
  {
    v0 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
  }
  return v0;
}

```

## disassembly

```asm
0x180007ca8  push    rbx
0x180007caa  sub     rsp, 20h
0x180007cae  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x180007cb3  mov     [rsp+28h+ppInterface], 0
0x180007cbc  lea     rcx, IID_IServerSecurity; riid
0x180007cc3  call    cs:__imp_CoGetCallContext
0x180007cc9  mov     ebx, eax
0x180007ccb  test    eax, eax
0x180007ccd  jnz     short loc_180007CF3
0x180007ccf  mov     rcx, [rsp+28h+ppInterface]
0x180007cd4  mov     rax, [rcx]
0x180007cd7  mov     rax, [rax+20h]
0x180007cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce0  mov     rcx, [rsp+28h+ppInterface]
0x180007ce5  mov     ebx, eax
0x180007ce7  mov     rax, [rcx]
0x180007cea  mov     rax, [rax+10h]
0x180007cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cf3  mov     eax, ebx
0x180007cf5  add     rsp, 20h
0x180007cf9  pop     rbx
0x180007cfa  retn
```
