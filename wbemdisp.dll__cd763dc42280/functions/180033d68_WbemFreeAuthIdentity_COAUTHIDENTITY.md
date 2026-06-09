# WbemFreeAuthIdentity(_COAUTHIDENTITY *)

- ea: `0x180033d68`
- end: `0x180033da4`
- name: `?WbemFreeAuthIdentity@@YAJPEAU_COAUTHIDENTITY@@@Z`
- size: `60`
- prototype: `__int64 __fastcall(struct _COAUTHIDENTITY *pv)`
- caller_count: `13`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800055c0`
- `0x180005f20`
- `0x180006300`
- `0x180006440`
- `0x180006580`
- `0x180006850`
- `0x180008de0`
- `0x18000a7b0`
- `0x18000aef0`
- `0x1800186bc`
- `0x18001e408`
- `0x18001e5dc`
- `0x18001eb00`

## callees

- `0x180033d68`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033d84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033d8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033d96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033d84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033d8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033d96`

## pseudocode

```c
__int64 __fastcall WbemFreeAuthIdentity(struct _COAUTHIDENTITY *pv)
{
  if ( pv )
  {
    CoTaskMemFree(pv->Password);
    CoTaskMemFree(pv->Domain);
    CoTaskMemFree(pv->User);
    CoTaskMemFree(pv);
  }
  return 0;
}

```

## disassembly

```asm
0x180033d68  push    rbx
0x180033d6a  sub     rsp, 20h
0x180033d6e  mov     rbx, rcx
0x180033d71  test    rcx, rcx
0x180033d74  jz      short loc_180033D9C
0x180033d76  mov     rcx, [rcx+20h]; pv
0x180033d7a  call    cs:__imp_CoTaskMemFree
0x180033d80  mov     rcx, [rbx+10h]; pv
0x180033d84  call    cs:__imp_CoTaskMemFree
0x180033d8a  mov     rcx, [rbx]; pv
0x180033d8d  call    cs:__imp_CoTaskMemFree
0x180033d93  mov     rcx, rbx; pv
0x180033d96  call    cs:__imp_CoTaskMemFree
0x180033d9c  xor     eax, eax
0x180033d9e  add     rsp, 20h
0x180033da2  pop     rbx
0x180033da3  retn
```
