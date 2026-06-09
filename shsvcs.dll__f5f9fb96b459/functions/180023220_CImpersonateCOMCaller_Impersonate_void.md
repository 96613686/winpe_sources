# CImpersonateCOMCaller::Impersonate(void)

- ea: `0x180023220`
- end: `0x180023247`
- name: `?Impersonate@CImpersonateCOMCaller@@UEAAJXZ`
- size: `39`
- prototype: `HRESULT __fastcall(CImpersonateCOMCaller *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a150`

## callees

- `0x180023220`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180023229`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180023229`

## pseudocode

```c
HRESULT __fastcall CImpersonateCOMCaller::Impersonate(CImpersonateCOMCaller *this)
{
  HRESULT result; // eax

  result = CoImpersonateClient();
  if ( result < 0 )
    return -2147467259;
  *((_DWORD *)this + 2) = 1;
  return result;
}

```

## disassembly

```asm
0x180023220  push    rbx
0x180023222  sub     rsp, 20h
0x180023226  mov     rbx, rcx
0x180023229  call    cs:__imp_CoImpersonateClient
0x18002322f  test    eax, eax
0x180023231  js      short loc_18002323C
0x180023233  mov     dword ptr [rbx+8], 1
0x18002323a  jmp     short loc_180023241
0x18002323c  mov     eax, 80004005h
0x180023241  add     rsp, 20h
0x180023245  pop     rbx
0x180023246  retn
```
