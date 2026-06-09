# HTTP2CurrentUserTable::HashSid(void *)

- ea: `0x18000ce68`
- end: `0x18000cea4`
- name: `?HashSid@HTTP2CurrentUserTable@@IEAAKPEAX@Z`
- size: `60`
- prototype: `unsigned int(HTTP2CurrentUserTable *__hidden this, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180008a5c`
- `0x180016bc4`

## callees

- `0x18000ce68`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x18000ce74`
- `ADVAPI32!GetLengthSid` at `0x18000ce74`

## pseudocode

```c
__int64 __fastcall HTTP2CurrentUserTable::HashSid(HTTP2CurrentUserTable *this, unsigned __int8 *a2)
{
  DWORD LengthSid; // r9d
  DWORD v4; // r8d
  __int64 result; // rax
  __int64 v6; // rcx

  LengthSid = GetLengthSid(a2);
  v4 = 0;
  for ( result = 0; v4 < LengthSid; result = 1048583 * a2[v6] + (unsigned int)result )
    v6 = (int)v4++;
  return result;
}

```

## disassembly

```asm
0x18000ce68  push    rbx
0x18000ce6a  sub     rsp, 20h
0x18000ce6e  mov     rcx, rdx; pSid
0x18000ce71  mov     rbx, rdx
0x18000ce74  call    cs:__imp_GetLengthSid
0x18000ce7a  mov     r9d, eax
0x18000ce7d  xor     r8d, r8d
0x18000ce80  xor     eax, eax
0x18000ce82  test    r9d, r9d
0x18000ce85  jz      short loc_18000CE9E
0x18000ce87  movsxd  rcx, r8d
0x18000ce8a  inc     r8d
0x18000ce8d  movzx   edx, byte ptr [rcx+rbx]
0x18000ce91  imul    ecx, edx, 100007h
0x18000ce97  add     eax, ecx
0x18000ce99  cmp     r8d, r9d
0x18000ce9c  jb      short loc_18000CE87
0x18000ce9e  add     rsp, 20h
0x18000cea2  pop     rbx
0x18000cea3  retn
```
