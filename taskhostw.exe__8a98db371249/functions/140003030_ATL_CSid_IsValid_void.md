# ATL::CSid::IsValid(void)

- ea: `0x140003030`
- end: `0x140003052`
- name: `?IsValid@CSid@ATL@@QEBA_NXZ`
- size: `34`
- prototype: `bool __fastcall(ATL::CSid *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002e30`

## callees

- `0x140003030`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14000303e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14000303e`

## pseudocode

```c
bool __fastcall ATL::CSid::IsValid(ATL::CSid *this)
{
  return *((_BYTE *)this + 76) && IsValidSid((char *)this + 8);
}

```

## disassembly

```asm
0x140003030  sub     rsp, 28h
0x140003034  cmp     byte ptr [rcx+4Ch], 0
0x140003038  jz      short loc_14000304E
0x14000303a  add     rcx, 8; pSid
0x14000303e  call    cs:__imp_IsValidSid
0x140003044  test    eax, eax
0x140003046  setnz   al
0x140003049  add     rsp, 28h
0x14000304d  retn
0x14000304e  xor     al, al
0x140003050  jmp     short loc_140003049
```
