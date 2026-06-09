# DuplicateSID(void * const)

- ea: `0x1800307e0`
- end: `0x180030839`
- name: `?DuplicateSID@@YAPEAXQEAX@Z`
- size: `89`
- prototype: `void *__fastcall(PSID pSourceSid)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029fc0`
- `0x18002aa3c`
- `0x18002f480`
- `0x180031af0`
- `0x18005c214`
- `0x180087400`
- `0x1800937c4`
- `0x1800bae38`

## callees

- `0x180023020`
- `0x1800307e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180030817`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180030817`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800307f2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800307f2`

## pseudocode

```c
void *__fastcall DuplicateSID(PSID pSourceSid)
{
  DWORD LengthSid; // esi
  void *result; // rax
  void *v4; // rbx

  LengthSid = GetLengthSid(pSourceSid);
  result = AllocWrapper(LengthSid);
  v4 = result;
  if ( result )
  {
    CopySid(LengthSid, result, pSourceSid);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800307e0  mov     [rsp+arg_0], rbx
0x1800307e5  mov     [rsp+arg_8], rsi
0x1800307ea  push    rdi
0x1800307eb  sub     rsp, 20h
0x1800307ef  mov     rdi, rcx
0x1800307f2  call    cs:__imp_GetLengthSid
0x1800307f9  nop     dword ptr [rax+rax+00h]
0x1800307fe  mov     ecx, eax; dwBytes
0x180030800  mov     esi, eax
0x180030802  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180030807  mov     rbx, rax
0x18003080a  test    rax, rax
0x18003080d  jz      short loc_180030837
0x18003080f  mov     r8, rdi; pSourceSid
0x180030812  mov     rdx, rax; pDestinationSid
0x180030815  mov     ecx, esi; nDestinationSidLength
0x180030817  call    cs:__imp_CopySid
0x18003081e  nop     dword ptr [rax+rax+00h]
0x180030823  mov     rax, rbx
0x180030826  mov     rbx, [rsp+28h+arg_0]
0x18003082b  mov     rsi, [rsp+28h+arg_8]
0x180030830  add     rsp, 20h
0x180030834  pop     rdi
0x180030835  retn
0x180030837  jmp     short loc_180030826
```
