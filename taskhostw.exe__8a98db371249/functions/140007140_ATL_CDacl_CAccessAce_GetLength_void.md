# ATL::CDacl::CAccessAce::GetLength(void)

- ea: `0x140007140`
- end: `0x140007156`
- name: `?GetLength@CAccessAce@CDacl@ATL@@UEBAIXZ`
- size: `22`
- prototype: `__int64 __fastcall(ATL::CDacl::CAccessAce *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140007148`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140007148`

## pseudocode

```c
__int64 __fastcall ATL::CDacl::CAccessAce::GetLength(ATL::CDacl::CAccessAce *this)
{
  return GetLengthSid((char *)this + 16) + 8;
}

```

## disassembly

```asm
0x140007140  sub     rsp, 28h
0x140007144  add     rcx, 10h; pSid
0x140007148  call    cs:__imp_GetLengthSid
0x14000714e  add     eax, 8
0x140007151  add     rsp, 28h
0x140007155  retn
```
