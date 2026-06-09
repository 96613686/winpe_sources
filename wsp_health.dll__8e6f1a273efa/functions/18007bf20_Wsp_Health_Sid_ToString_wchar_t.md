# Wsp::Health::Sid::ToString(wchar_t * *)

- ea: `0x18007bf20`
- end: `0x18007bf77`
- name: `?ToString@Sid@Health@Wsp@@QEAAKPEAPEA_W@Z`
- size: `87`
- prototype: `unsigned int(Wsp::Health::Sid *__hidden this, wchar_t **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007ae8c`
- `0x18007bba4`

## callees

- `0x180016318`
- `0x18007bf20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bf5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bf5b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007bf4b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007bf4b`

## pseudocode

```c
DWORD __fastcall Wsp::Health::Sid::ToString(struct _SID **this, wchar_t **a2)
{
  if ( !Wsp::Health::Sid::IsValidSid(this[1]) )
    return 1337;
  if ( ConvertSidToStringSidW(this[1], a2) )
    return 0;
  return GetLastError();
}

```

## disassembly

```asm
0x18007bf20  mov     [rsp+arg_0], rbx
0x18007bf25  push    rdi
0x18007bf26  sub     rsp, 20h
0x18007bf2a  mov     rbx, rcx
0x18007bf2d  mov     rdi, rdx
0x18007bf30  mov     rcx, [rcx+8]; struct _SID *
0x18007bf34  call    ?IsValidSid@Sid@Health@Wsp@@SA_NPEBU_SID@@@Z; Wsp::Health::Sid::IsValidSid(_SID const *)
0x18007bf39  test    al, al
0x18007bf3b  jnz     short loc_18007BF44
0x18007bf3d  mov     eax, 539h
0x18007bf42  jmp     short loc_18007BF6B
0x18007bf44  mov     rcx, [rbx+8]; Sid
0x18007bf48  mov     rdx, rdi; StringSid
0x18007bf4b  call    cs:__imp_ConvertSidToStringSidW
0x18007bf52  nop     dword ptr [rax+rax+00h]
0x18007bf57  test    eax, eax
0x18007bf59  jnz     short loc_18007BF69
0x18007bf5b  call    cs:__imp_GetLastError
0x18007bf62  nop     dword ptr [rax+rax+00h]
0x18007bf67  jmp     short loc_18007BF6B
0x18007bf69  xor     eax, eax
0x18007bf6b  mov     rbx, [rsp+28h+arg_0]
0x18007bf70  add     rsp, 20h
0x18007bf74  pop     rdi
0x18007bf75  retn
```
