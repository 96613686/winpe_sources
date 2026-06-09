# DuplicateSID(void * const)

- ea: `0x18002f460`
- end: `0x18002f4ac`
- name: `?DuplicateSID@@YAPEAXQEAX@Z`
- size: `76`
- prototype: `void *__fastcall(PSID pSourceSid)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028d70`
- `0x180029798`
- `0x18002e0f0`
- `0x180030754`
- `0x18004980c`
- `0x180053dfc`
- `0x180085440`
- `0x1800b6c88`

## callees

- `0x180021e70`
- `0x18002f460`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002f491`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002f491`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002f472`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002f472`

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
0x18002f460  mov     [rsp+arg_0], rbx
0x18002f465  mov     [rsp+arg_8], rsi
0x18002f46a  push    rdi
0x18002f46b  sub     rsp, 20h
0x18002f46f  mov     rdi, rcx
0x18002f472  call    cs:__imp_GetLengthSid
0x18002f478  mov     ecx, eax; dwBytes
0x18002f47a  mov     esi, eax
0x18002f47c  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18002f481  mov     rbx, rax
0x18002f484  test    rax, rax
0x18002f487  jz      short loc_18002F4AA
0x18002f489  mov     r8, rdi; pSourceSid
0x18002f48c  mov     rdx, rax; pDestinationSid
0x18002f48f  mov     ecx, esi; nDestinationSidLength
0x18002f491  call    cs:__imp_CopySid
0x18002f497  mov     rax, rbx
0x18002f49a  mov     rbx, [rsp+28h+arg_0]
0x18002f49f  mov     rsi, [rsp+28h+arg_8]
0x18002f4a4  add     rsp, 20h
0x18002f4a8  pop     rdi
0x18002f4a9  retn
0x18002f4aa  jmp     short loc_18002F49A
```
